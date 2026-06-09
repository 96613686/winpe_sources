# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x14000eefc`
- end: `0x14000ef6c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000f920`

## callees

- `0x14000eefc`
- `0x140010010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000ef50`
- `KERNEL32!DeleteCriticalSection` at `0x14000ef50`

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
0x14000eefc  mov     [rsp+arg_0], rbx
0x14000ef01  mov     [rsp+arg_8], rsi
0x14000ef06  push    rdi
0x14000ef07  sub     rsp, 20h
0x14000ef0b  cmp     dword ptr [rcx], 0
0x14000ef0e  mov     rbx, rcx
0x14000ef11  jz      short loc_14000EF5C
0x14000ef13  mov     rdi, [rcx+10h]
0x14000ef17  cmp     rdi, [rcx+18h]
0x14000ef1b  jnb     short loc_14000EF4C
0x14000ef1d  mov     rsi, [rdi]
0x14000ef20  test    rsi, rsi
0x14000ef23  jz      short loc_14000EF42
0x14000ef25  mov     rcx, [rsi+20h]
0x14000ef29  test    rcx, rcx
0x14000ef2c  jz      short loc_14000EF3A
0x14000ef2e  mov     rax, [rcx]
0x14000ef31  mov     rax, [rax+10h]
0x14000ef35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ef3a  mov     qword ptr [rsi+20h], 0
0x14000ef42  add     rdi, 8
0x14000ef46  cmp     rdi, [rbx+18h]
0x14000ef4a  jb      short loc_14000EF1D
0x14000ef4c  lea     rcx, [rbx+20h]; lpCriticalSection
0x14000ef50  call    cs:__imp_DeleteCriticalSection
0x14000ef56  mov     dword ptr [rbx], 0
0x14000ef5c  mov     rbx, [rsp+28h+arg_0]
0x14000ef61  mov     rsi, [rsp+28h+arg_8]
0x14000ef66  add     rsp, 20h
0x14000ef6a  pop     rdi
0x14000ef6b  retn
```
