# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800074d0`
- end: `0x180007540`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ea20`

## callees

- `0x1800074d0`
- `0x18002f010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180007524`
- `KERNEL32!DeleteCriticalSection` at `0x180007524`

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
0x1800074d0  mov     [rsp+arg_0], rbx
0x1800074d5  mov     [rsp+arg_8], rsi
0x1800074da  push    rdi
0x1800074db  sub     rsp, 20h
0x1800074df  cmp     dword ptr [rcx], 0
0x1800074e2  mov     rbx, rcx
0x1800074e5  jz      short loc_180007530
0x1800074e7  mov     rdi, [rcx+10h]
0x1800074eb  cmp     rdi, [rcx+18h]
0x1800074ef  jnb     short loc_180007520
0x1800074f1  mov     rsi, [rdi]
0x1800074f4  test    rsi, rsi
0x1800074f7  jz      short loc_180007516
0x1800074f9  mov     rcx, [rsi+20h]
0x1800074fd  test    rcx, rcx
0x180007500  jz      short loc_18000750E
0x180007502  mov     rax, [rcx]
0x180007505  mov     rax, [rax+10h]
0x180007509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750e  mov     qword ptr [rsi+20h], 0
0x180007516  add     rdi, 8
0x18000751a  cmp     rdi, [rbx+18h]
0x18000751e  jb      short loc_1800074F1
0x180007520  lea     rcx, [rbx+20h]; lpCriticalSection
0x180007524  call    cs:__imp_DeleteCriticalSection
0x18000752a  mov     dword ptr [rbx], 0
0x180007530  mov     rbx, [rsp+28h+arg_0]
0x180007535  mov     rsi, [rsp+28h+arg_8]
0x18000753a  add     rsp, 20h
0x18000753e  pop     rdi
0x18000753f  retn
```
