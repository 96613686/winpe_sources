# EapLm::RasAuthAttributes::operator=(_RAS_AUTH_ATTRIBUTE const *)

- ea: `0x180031590`
- end: `0x1800315df`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@PEBU_RAS_AUTH_ATTRIBUTE@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(EapLm::RasAuthAttributes *this, EapLm *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003141c`

## callees

- `0x18002ed84`
- `0x180031590`
- `0x1800317bc`
- `0x18003191c`

## string_xrefs

- `0x1800315b2`: `RasAuthAttributeCopy`

## pseudocode

```c
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
0x180031590  mov     [rsp+arg_0], rbx
0x180031595  push    rdi
0x180031596  sub     rsp, 20h
0x18003159a  mov     rbx, rcx
0x18003159d  test    rdx, rdx
0x1800315a0  jz      short loc_1800315CC
0x1800315a2  mov     rcx, rdx; this
0x1800315a5  call    ?RasAuthAttributeCopy@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@PEAU2@@Z; EapLm::RasAuthAttributeCopy(_RAS_AUTH_ATTRIBUTE *)
0x1800315aa  mov     rdi, rax
0x1800315ad  test    rax, rax
0x1800315b0  jnz     short loc_1800315BF
0x1800315b2  lea     rcx, aRasauthattribu_0; "RasAuthAttributeCopy"
0x1800315b9  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x1800315bf  mov     rcx, rbx; this
0x1800315c2  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x1800315c7  mov     [rbx], rdi
0x1800315ca  jmp     short loc_1800315D1
0x1800315cc  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x1800315d1  mov     rax, rbx
0x1800315d4  mov     rbx, [rsp+28h+arg_0]
0x1800315d9  add     rsp, 20h
0x1800315dd  pop     rdi
0x1800315de  retn
```
