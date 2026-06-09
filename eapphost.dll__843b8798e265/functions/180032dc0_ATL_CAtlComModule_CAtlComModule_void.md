# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180032dc0`
- end: `0x180032e37`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180038900`

## callees

- `0x180032dc0`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032e14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180032e14`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180032dc0  mov     [rsp+arg_0], rbx
0x180032dc5  mov     [rsp+arg_8], rsi
0x180032dca  push    rdi
0x180032dcb  sub     rsp, 20h
0x180032dcf  cmp     dword ptr [rcx], 0
0x180032dd2  mov     rbx, rcx
0x180032dd5  jz      short loc_180032E26
0x180032dd7  mov     rdi, [rcx+10h]
0x180032ddb  cmp     rdi, [rcx+18h]
0x180032ddf  jnb     short loc_180032E10
0x180032de1  mov     rsi, [rdi]
0x180032de4  test    rsi, rsi
0x180032de7  jz      short loc_180032E06
0x180032de9  mov     rcx, [rsi+20h]
0x180032ded  test    rcx, rcx
0x180032df0  jz      short loc_180032DFE
0x180032df2  mov     rax, [rcx]
0x180032df5  mov     rax, [rax+10h]
0x180032df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dfe  mov     qword ptr [rsi+20h], 0
0x180032e06  add     rdi, 8
0x180032e0a  cmp     rdi, [rbx+18h]
0x180032e0e  jb      short loc_180032DE1
0x180032e10  lea     rcx, [rbx+20h]; lpCriticalSection
0x180032e14  call    cs:__imp_DeleteCriticalSection
0x180032e1b  nop     dword ptr [rax+rax+00h]
0x180032e20  mov     dword ptr [rbx], 0
0x180032e26  mov     rbx, [rsp+28h+arg_0]
0x180032e2b  mov     rsi, [rsp+28h+arg_8]
0x180032e30  add     rsp, 20h
0x180032e34  pop     rdi
0x180032e35  retn
```
