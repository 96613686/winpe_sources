# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800175b4`
- end: `0x180017624`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018aa0`

## callees

- `0x1800175b4`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180017608`
- `KERNEL32!DeleteCriticalSection` at `0x180017608`

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
0x1800175b4  mov     [rsp+arg_0], rbx
0x1800175b9  mov     [rsp+arg_8], rsi
0x1800175be  push    rdi
0x1800175bf  sub     rsp, 20h
0x1800175c3  cmp     dword ptr [rcx], 0
0x1800175c6  mov     rbx, rcx
0x1800175c9  jz      short loc_180017614
0x1800175cb  mov     rdi, [rcx+10h]
0x1800175cf  cmp     rdi, [rcx+18h]
0x1800175d3  jnb     short loc_180017604
0x1800175d5  mov     rsi, [rdi]
0x1800175d8  test    rsi, rsi
0x1800175db  jz      short loc_1800175FA
0x1800175dd  mov     rcx, [rsi+20h]
0x1800175e1  test    rcx, rcx
0x1800175e4  jz      short loc_1800175F2
0x1800175e6  mov     rax, [rcx]
0x1800175e9  mov     rax, [rax+10h]
0x1800175ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175f2  mov     qword ptr [rsi+20h], 0
0x1800175fa  add     rdi, 8
0x1800175fe  cmp     rdi, [rbx+18h]
0x180017602  jb      short loc_1800175D5
0x180017604  lea     rcx, [rbx+20h]; lpCriticalSection
0x180017608  call    cs:__imp_DeleteCriticalSection
0x18001760e  mov     dword ptr [rbx], 0
0x180017614  mov     rbx, [rsp+28h+arg_0]
0x180017619  mov     rsi, [rsp+28h+arg_8]
0x18001761e  add     rsp, 20h
0x180017622  pop     rdi
0x180017623  retn
```
