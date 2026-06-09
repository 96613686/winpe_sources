# EapLm::RasAuthAttributes::operator=(_RAS_AUTH_ATTRIBUTE const *)

- ea: `0x18003278c`
- end: `0x1800327dc`
- name: `??4RasAuthAttributes@EapLm@@QEAAAEAV01@PEBU_RAS_AUTH_ATTRIBUTE@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(EapLm::RasAuthAttributes *this, EapLm *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800136e0`
- `0x180032618`

## callees

- `0x18002fe84`
- `0x18003278c`
- `0x1800329c0`
- `0x180032b20`

## string_xrefs

- `0x1800327ae`: `RasAuthAttributeCopy`

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
0x18003278c  mov     [rsp+arg_0], rbx
0x180032791  push    rdi
0x180032792  sub     rsp, 20h
0x180032796  mov     rbx, rcx
0x180032799  test    rdx, rdx
0x18003279c  jz      short loc_1800327C8
0x18003279e  mov     rcx, rdx; this
0x1800327a1  call    ?RasAuthAttributeCopy@EapLm@@YAPEAU_RAS_AUTH_ATTRIBUTE@@PEAU2@@Z; EapLm::RasAuthAttributeCopy(_RAS_AUTH_ATTRIBUTE *)
0x1800327a6  mov     rdi, rax
0x1800327a9  test    rax, rax
0x1800327ac  jnz     short loc_1800327BB
0x1800327ae  lea     rcx, aRasauthattribu_0; "RasAuthAttributeCopy"
0x1800327b5  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x1800327bb  mov     rcx, rbx; this
0x1800327be  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x1800327c3  mov     [rbx], rdi
0x1800327c6  jmp     short loc_1800327CD
0x1800327c8  call    ?Destroy@RasAuthAttributes@EapLm@@AEAAXXZ; EapLm::RasAuthAttributes::Destroy(void)
0x1800327cd  mov     rax, rbx
0x1800327d0  mov     rbx, [rsp+28h+arg_0]
0x1800327d5  add     rsp, 20h
0x1800327d9  pop     rdi
0x1800327da  retn
```
