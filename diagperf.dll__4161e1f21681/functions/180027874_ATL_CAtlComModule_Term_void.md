# ATL::CAtlComModule::Term(void)

- ea: `0x180027874`
- end: `0x1800278e4`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800d58e0`

## callees

- `0x180027874`
- `0x1800d6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800278c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800278c8`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::Term(ATL::CAtlComModule *this)
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
0x180027874  mov     [rsp+arg_0], rbx
0x180027879  mov     [rsp+arg_8], rsi
0x18002787e  push    rdi
0x18002787f  sub     rsp, 20h
0x180027883  cmp     dword ptr [rcx], 0
0x180027886  mov     rbx, rcx
0x180027889  jz      short loc_1800278D4
0x18002788b  mov     rdi, [rcx+10h]
0x18002788f  cmp     rdi, [rcx+18h]
0x180027893  jnb     short loc_1800278C4
0x180027895  mov     rsi, [rdi]
0x180027898  test    rsi, rsi
0x18002789b  jz      short loc_1800278BA
0x18002789d  mov     rcx, [rsi+20h]
0x1800278a1  test    rcx, rcx
0x1800278a4  jz      short loc_1800278B2
0x1800278a6  mov     rax, [rcx]
0x1800278a9  mov     rax, [rax+10h]
0x1800278ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278b2  mov     qword ptr [rsi+20h], 0
0x1800278ba  add     rdi, 8
0x1800278be  cmp     rdi, [rbx+18h]
0x1800278c2  jb      short loc_180027895
0x1800278c4  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800278c8  call    cs:__imp_DeleteCriticalSection
0x1800278ce  mov     dword ptr [rbx], 0
0x1800278d4  mov     rbx, [rsp+28h+arg_0]
0x1800278d9  mov     rsi, [rsp+28h+arg_8]
0x1800278de  add     rsp, 20h
0x1800278e2  pop     rdi
0x1800278e3  retn
```
