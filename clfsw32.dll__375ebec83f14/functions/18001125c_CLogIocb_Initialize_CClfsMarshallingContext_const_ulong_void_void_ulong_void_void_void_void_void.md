# CLogIocb::Initialize(CClfsMarshallingContext * const,ulong,void *,void * (*)(ulong,void *),void (*)(void *,void *),void *)

- ea: `0x18001125c`
- end: `0x18001132a`
- name: `?Initialize@CLogIocb@@QEAAKQEAVCClfsMarshallingContext@@KPEAXP6APEAXK1@ZP6AX11@Z1@Z`
- size: `206`
- prototype: `unsigned int __fastcall(CLogIocb *__hidden this, struct CClfsMarshallingContext *const, unsigned int, void *, void *(*)(unsigned int, void *), void (*)(void *, void *), void *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e750`
- `0x180010bdc`

## callees

- `0x18001125c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800112fb`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800112e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800112e6`

## pseudocode

```c
DWORD __fastcall CLogIocb::Initialize(
        CLogIocb *this,
        struct CClfsMarshallingContext *const a2,
        __int64 a3,
        void *a4,
        void *(*a5)(unsigned int, void *),
        void (*a6)(void *, void *))
{
  HANDLE EventA; // rax

  if ( *((_QWORD *)this + 7)
    || *((_QWORD *)this + 24)
    || *((_QWORD *)this + 8)
    || *((_QWORD *)this + 25)
    || *((_QWORD *)this + 26) )
  {
    return 1247;
  }
  if ( !a5 )
  {
    if ( !a6 )
    {
      *((_QWORD *)this + 15) = 0;
      goto LABEL_12;
    }
    return 87;
  }
  if ( !a6 )
    return 87;
LABEL_12:
  *((_QWORD *)this + 25) = a5;
  *((_QWORD *)this + 26) = a6;
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)this + 7) = EventA;
  if ( !EventA )
    return GetLastError();
  if ( a2 )
    *((_QWORD *)this + 24) = a2;
  return 0;
}

```

## disassembly

```asm
0x18001125c  mov     [rsp+arg_0], rbx
0x180011261  push    rdi
0x180011262  sub     rsp, 20h
0x180011266  cmp     qword ptr [rcx+38h], 0
0x18001126b  mov     rdi, rdx
0x18001126e  mov     rbx, rcx
0x180011271  jnz     loc_180011319
0x180011277  cmp     qword ptr [rcx+0C0h], 0
0x18001127f  jnz     loc_180011319
0x180011285  cmp     qword ptr [rcx+40h], 0
0x18001128a  jnz     loc_180011319
0x180011290  cmp     qword ptr [rcx+0C8h], 0
0x180011298  jnz     short loc_180011319
0x18001129a  cmp     qword ptr [rcx+0D0h], 0
0x1800112a2  jnz     short loc_180011319
0x1800112a4  mov     rcx, [rsp+28h+arg_20]
0x1800112a9  mov     rax, [rsp+28h+arg_28]
0x1800112ae  test    rcx, rcx
0x1800112b1  jz      short loc_1800112BA
0x1800112b3  test    rax, rax
0x1800112b6  jz      short loc_1800112BF
0x1800112b8  jmp     short loc_1800112CE
0x1800112ba  test    rax, rax
0x1800112bd  jz      short loc_1800112C6
0x1800112bf  mov     eax, 57h ; 'W'
0x1800112c4  jmp     short loc_18001131E
0x1800112c6  mov     qword ptr [rbx+78h], 0
0x1800112ce  mov     [rbx+0C8h], rcx
0x1800112d5  xor     r9d, r9d; lpName
0x1800112d8  xor     ecx, ecx; lpEventAttributes
0x1800112da  mov     [rbx+0D0h], rax
0x1800112e1  xor     r8d, r8d; bInitialState
0x1800112e4  xor     edx, edx; bManualReset
0x1800112e6  call    cs:__imp_CreateEventA
0x1800112ed  nop     dword ptr [rax+rax+00h]
0x1800112f2  mov     [rbx+38h], rax
0x1800112f6  test    rax, rax
0x1800112f9  jnz     short loc_180011309
0x1800112fb  call    cs:__imp_GetLastError
0x180011302  nop     dword ptr [rax+rax+00h]
0x180011307  jmp     short loc_18001131E
0x180011309  test    rdi, rdi
0x18001130c  jz      short loc_180011315
0x18001130e  mov     [rbx+0C0h], rdi
0x180011315  xor     eax, eax
0x180011317  jmp     short loc_18001131E
0x180011319  mov     eax, 4DFh
0x18001131e  mov     rbx, [rsp+28h+arg_0]
0x180011323  add     rsp, 20h
0x180011327  pop     rdi
0x180011328  retn
```
