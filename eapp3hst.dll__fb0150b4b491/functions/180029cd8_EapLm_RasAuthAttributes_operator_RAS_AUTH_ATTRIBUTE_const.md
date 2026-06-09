# EapLm::RasAuthAttributes::operator=(_RAS_AUTH_ATTRIBUTE const *)

- ea: `0x180029cd8`
- end: `0x180029d27`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@PEBU_RAS_AUTH_ATTRIBUTE@@@Z`
- size: `79`
- prototype: `EapLm::RasAuthAttributes *__fastcall(EapLm::RasAuthAttributes *this, EapLm *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180029b48`

## callees

- `0x180012a00`
- `0x180029cd8`
- `0x180029f14`
- `0x18002a074`

## string_xrefs

- `0x180029cfa`: `RasAuthAttributeCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
EapLm::RasAuthAttributes *__fastcall EapLm::RasAuthAttributes::operator=(EapLm::RasAuthAttributes *this, EapLm *a2)
{
  struct _RAS_AUTH_ATTRIBUTE *v3; // rdi

  if ( a2 )
  {
    v3 = EapLm::RasAuthAttributeCopy(a2, (struct _RAS_AUTH_ATTRIBUTE *)a2);
    if ( !v3 )
      LowMemoryError::Throw(L"RasAuthAttributeCopy");
    EapLm::RasAuthAttributes::Destroy(this);
    *(_QWORD *)this = v3;
  }
  else
  {
    EapLm::RasAuthAttributes::Destroy(this);
  }
  return this;
}

```

## disassembly

```asm
0x180029cd8  mov     [rsp+arg_0], rbx
0x180029cdd  push    rdi
0x180029cde  sub     rsp, 20h
0x180029ce2  mov     rbx, rcx
0x180029ce5  test    rdx, rdx
0x180029ce8  jz      short loc_180029D14
0x180029cea  mov     rcx, rdx; this
0x180029ced  call    ?RasAuthAttributeCopy@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@PEAU2@@Z; EapLm::RasAuthAttributeCopy(_RAS_AUTH_ATTRIBUTE *)
0x180029cf2  mov     rdi, rax
0x180029cf5  test    rax, rax
0x180029cf8  jnz     short loc_180029D07
0x180029cfa  lea     rcx, aRasauthattribu_0; "RasAuthAttributeCopy"
0x180029d01  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180029d07  mov     rcx, rbx; this
0x180029d0a  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x180029d0f  mov     [rbx], rdi
0x180029d12  jmp     short loc_180029D19
0x180029d14  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x180029d19  mov     rax, rbx
0x180029d1c  mov     rbx, [rsp+28h+arg_0]
0x180029d21  add     rsp, 20h
0x180029d25  pop     rdi
0x180029d26  retn
```
