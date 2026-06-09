# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x140006548`
- end: `0x1400065b8`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006800`

## callees

- `0x140006548`
- `0x140007010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000659c`
- `KERNEL32!DeleteCriticalSection` at `0x14000659c`

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
0x140006548  mov     [rsp+arg_0], rbx
0x14000654d  mov     [rsp+arg_8], rsi
0x140006552  push    rdi
0x140006553  sub     rsp, 20h
0x140006557  cmp     dword ptr [rcx], 0
0x14000655a  mov     rbx, rcx
0x14000655d  jz      short loc_1400065A8
0x14000655f  mov     rdi, [rcx+10h]
0x140006563  cmp     rdi, [rcx+18h]
0x140006567  jnb     short loc_140006598
0x140006569  mov     rsi, [rdi]
0x14000656c  test    rsi, rsi
0x14000656f  jz      short loc_14000658E
0x140006571  mov     rcx, [rsi+20h]
0x140006575  test    rcx, rcx
0x140006578  jz      short loc_140006586
0x14000657a  mov     rax, [rcx]
0x14000657d  mov     rax, [rax+10h]
0x140006581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006586  mov     qword ptr [rsi+20h], 0
0x14000658e  add     rdi, 8
0x140006592  cmp     rdi, [rbx+18h]
0x140006596  jb      short loc_140006569
0x140006598  lea     rcx, [rbx+20h]; lpCriticalSection
0x14000659c  call    cs:__imp_DeleteCriticalSection
0x1400065a2  mov     dword ptr [rbx], 0
0x1400065a8  mov     rbx, [rsp+28h+arg_0]
0x1400065ad  mov     rsi, [rsp+28h+arg_8]
0x1400065b2  add     rsp, 20h
0x1400065b6  pop     rdi
0x1400065b7  retn
```
