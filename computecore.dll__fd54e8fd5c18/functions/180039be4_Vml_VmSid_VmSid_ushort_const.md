# Vml::VmSid::VmSid(ushort const *)

- ea: `0x180039be4`
- end: `0x180039cd1`
- name: `??0VmSid@Vml@@QEAA@PEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(Vml::VmSid *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003ae9c`
- `0x18003b0dc`
- `0x18003ba60`
- `0x18003bc98`
- `0x18003d788`

## callees

- `0x1800067c0`
- `0x18001017c`
- `0x180039be4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039c6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039c6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039c54`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180039c54`

## string_xrefs

- `0x180039cbf`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Vml::VmSid *__fastcall Vml::VmSid::VmSid(Vml::VmSid *this, const unsigned __int16 *a2)
{
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  const char *v5; // r9
  void *v6; // rcx
  PSID Sid; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  v3 = (_QWORD *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  v4 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  Sid = 0;
  if ( !ConvertStringSidToSidW(
          L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704",
          &Sid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x156D,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v5);
  v6 = *(void **)this;
  *(_QWORD *)this = Sid;
  if ( v6 )
    LocalFree(v6);
  *((_DWORD *)this + 2) = 7;
  v4[2] = 0;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_WORD *)v4 = 0;
  v3[2] = 0;
  if ( v3[3] > 7u )
    v3 = (_QWORD *)*v3;
  *(_WORD *)v3 = 0;
  return this;
}

```

## disassembly

```asm
0x180039be4  push    rbx
0x180039be6  push    rsi
0x180039be7  push    rdi
0x180039be8  push    r14
0x180039bea  sub     rsp, 48h
0x180039bee  mov     rax, cs:__security_cookie
0x180039bf5  xor     rax, rsp
0x180039bf8  mov     [rsp+68h+var_30], rax
0x180039bfd  mov     rsi, rcx
0x180039c00  mov     [rsp+68h+var_48], rcx
0x180039c05  mov     qword ptr [rcx], 0
0x180039c0c  mov     r14d, 7
0x180039c12  mov     [rcx+8], r14d
0x180039c16  lea     rbx, [rcx+10h]
0x180039c1a  xorps   xmm0, xmm0
0x180039c1d  movups  xmmword ptr [rbx], xmm0
0x180039c20  mov     qword ptr [rbx+10h], 0
0x180039c28  mov     [rbx+18h], r14
0x180039c2c  xor     eax, eax
0x180039c2e  mov     [rbx], ax
0x180039c31  lea     rdi, [rcx+30h]
0x180039c35  movups  xmmword ptr [rdi], xmm0
0x180039c38  mov     [rdi+10h], rax
0x180039c3c  mov     [rdi+18h], r14
0x180039c40  mov     [rdi], ax
0x180039c43  mov     [rsp+68h+Sid], rax
0x180039c48  lea     rdx, [rsp+68h+Sid]; Sid
0x180039c4d  lea     rcx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x180039c54  call    cs:__imp_ConvertStringSidToSidW
0x180039c5a  test    eax, eax
0x180039c5c  jz      short loc_180039CBA
0x180039c5e  mov     rcx, [rsi]; hMem
0x180039c61  mov     rax, [rsp+68h+Sid]
0x180039c66  mov     [rsi], rax
0x180039c69  test    rcx, rcx
0x180039c6c  jz      short loc_180039C74
0x180039c6e  call    cs:__imp_LocalFree
0x180039c74  mov     [rsi+8], r14d
0x180039c78  mov     qword ptr [rdi+10h], 0
0x180039c80  cmp     [rdi+18h], r14
0x180039c84  jbe     short loc_180039C89
0x180039c86  mov     rdi, [rdi]
0x180039c89  xor     eax, eax
0x180039c8b  mov     [rdi], ax
0x180039c8e  mov     [rbx+10h], rax
0x180039c92  cmp     [rbx+18h], r14
0x180039c96  jbe     short loc_180039C9B
0x180039c98  mov     rbx, [rbx]
0x180039c9b  xor     ecx, ecx
0x180039c9d  mov     [rbx], cx
0x180039ca0  mov     rax, rsi
0x180039ca3  mov     rcx, [rsp+68h+var_30]
0x180039ca8  xor     rcx, rsp; StackCookie
0x180039cab  call    __security_check_cookie
0x180039cb0  add     rsp, 48h
0x180039cb4  pop     r14
0x180039cb6  pop     rdi
0x180039cb7  pop     rsi
0x180039cb8  pop     rbx
0x180039cb9  retn
0x180039cba  mov     rcx, [rsp+68h]; this
0x180039cbf  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x180039cc6  mov     edx, 156Dh; void *
0x180039ccb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
