# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001d000`
- end: `0x18001d070`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002fe40`

## callees

- `0x18001d000`
- `0x180030010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001d054`
- `KERNEL32!DeleteCriticalSection` at `0x18001d054`

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
0x18001d000  mov     [rsp+arg_0], rbx
0x18001d005  mov     [rsp+arg_8], rsi
0x18001d00a  push    rdi
0x18001d00b  sub     rsp, 20h
0x18001d00f  cmp     dword ptr [rcx], 0
0x18001d012  mov     rbx, rcx
0x18001d015  jz      short loc_18001D060
0x18001d017  mov     rdi, [rcx+10h]
0x18001d01b  cmp     rdi, [rcx+18h]
0x18001d01f  jnb     short loc_18001D050
0x18001d021  mov     rsi, [rdi]
0x18001d024  test    rsi, rsi
0x18001d027  jz      short loc_18001D046
0x18001d029  mov     rcx, [rsi+20h]
0x18001d02d  test    rcx, rcx
0x18001d030  jz      short loc_18001D03E
0x18001d032  mov     rax, [rcx]
0x18001d035  mov     rax, [rax+10h]
0x18001d039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d03e  mov     qword ptr [rsi+20h], 0
0x18001d046  add     rdi, 8
0x18001d04a  cmp     rdi, [rbx+18h]
0x18001d04e  jb      short loc_18001D021
0x18001d050  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001d054  call    cs:__imp_DeleteCriticalSection
0x18001d05a  mov     dword ptr [rbx], 0
0x18001d060  mov     rbx, [rsp+28h+arg_0]
0x18001d065  mov     rsi, [rsp+28h+arg_8]
0x18001d06a  add     rsp, 20h
0x18001d06e  pop     rdi
0x18001d06f  retn
```
