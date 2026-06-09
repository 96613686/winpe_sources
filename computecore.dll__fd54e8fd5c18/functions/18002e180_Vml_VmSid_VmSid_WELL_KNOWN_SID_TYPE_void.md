# Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)

- ea: `0x18002e180`
- end: `0x18002e2d7`
- name: `??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z`
- size: `343`
- prototype: `_QWORD(Vml::VmSid *__hidden this, enum WELL_KNOWN_SID_TYPE, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18002e5e0`

## callees

- `0x1800067c0`
- `0x18001017c`
- `0x18002e180`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e24e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e24e`
- `KERNELBASE!LocalAlloc` at `0x18002e223`
- `KERNELBASE!LocalAlloc` at `0x18002e223`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e207`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18002e207`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002e23d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18002e23d`

## string_xrefs

- `0x18002e2b3`: `onecore\vm\common\vml\VmSecurity.h`
- `0x18002e2c5`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Vml::VmSid *__fastcall Vml::VmSid::VmSid(Vml::VmSid *this, enum WELL_KNOWN_SID_TYPE a2, void *a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rdi
  const char *v6; // r9
  HLOCAL v7; // rax
  const char *v8; // r9
  HLOCAL v9; // rbp
  void *v10; // rcx
  DWORD cbSid[4]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 7;
  v4 = (_QWORD *)((char *)this + 16);
  *((_OWORD *)this + 1) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 7;
  *((_WORD *)this + 8) = 0;
  v5 = (_QWORD *)((char *)this + 48);
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 7;
  *((_WORD *)this + 24) = 0;
  cbSid[0] = 68;
  if ( !CreateWellKnownSid(a2, 0, pSid, cbSid) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1469,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v6);
  v7 = LocalAlloc(0, cbSid[0]);
  v9 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146F,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      v8);
  CopySid(cbSid[0], v7, pSid);
  v10 = *(void **)this;
  *(_QWORD *)this = v9;
  if ( v10 )
    LocalFree(v10);
  *((_DWORD *)this + 2) = 7;
  v5[2] = 0;
  if ( v5[3] > 7u )
    v5 = (_QWORD *)*v5;
  *(_WORD *)v5 = 0;
  v4[2] = 0;
  if ( v4[3] > 7u )
    v4 = (_QWORD *)*v4;
  *(_WORD *)v4 = 0;
  return this;
}

```

## disassembly

```asm
0x18002e180  mov     [rsp+arg_10], rbx
0x18002e185  mov     [rsp+arg_18], rbp
0x18002e18a  push    rsi
0x18002e18b  push    rdi
0x18002e18c  push    r15
0x18002e18e  sub     rsp, 0A0h
0x18002e195  mov     rax, cs:__security_cookie
0x18002e19c  xor     rax, rsp
0x18002e19f  mov     [rsp+0B8h+var_28], rax
0x18002e1a7  mov     r10d, edx
0x18002e1aa  mov     rsi, rcx
0x18002e1ad  mov     [rsp+0B8h+var_98], rcx
0x18002e1b2  mov     qword ptr [rcx], 0
0x18002e1b9  mov     r15d, 7
0x18002e1bf  mov     [rcx+8], r15d
0x18002e1c3  lea     rbx, [rcx+10h]
0x18002e1c7  xorps   xmm0, xmm0
0x18002e1ca  movups  xmmword ptr [rbx], xmm0
0x18002e1cd  mov     qword ptr [rbx+10h], 0
0x18002e1d5  mov     [rbx+18h], r15
0x18002e1d9  xor     eax, eax
0x18002e1db  mov     [rbx], ax
0x18002e1de  lea     rdi, [rcx+30h]
0x18002e1e2  movups  xmmword ptr [rdi], xmm0
0x18002e1e5  mov     [rdi+10h], rax
0x18002e1e9  mov     [rdi+18h], r15
0x18002e1ed  mov     [rdi], ax
0x18002e1f0  mov     [rsp+0B8h+cbSid], 44h ; 'D'
0x18002e1f8  lea     r9, [rsp+0B8h+cbSid]; cbSid
0x18002e1fd  lea     r8, [rsp+0B8h+pSid]; pSid
0x18002e202  xor     edx, edx; DomainSid
0x18002e204  mov     ecx, r10d; WellKnownSidType
0x18002e207  call    cs:__imp_CreateWellKnownSid
0x18002e20d  mov     rcx, [rsp+0B8h]; this
0x18002e215  test    eax, eax
0x18002e217  jz      loc_18002E2C5
0x18002e21d  mov     edx, [rsp+0B8h+cbSid]; uBytes
0x18002e221  xor     ecx, ecx; uFlags
0x18002e223  call    cs:__imp_LocalAlloc
0x18002e229  mov     rbp, rax
0x18002e22c  test    rax, rax
0x18002e22f  jz      short loc_18002E2AB
0x18002e231  lea     r8, [rsp+0B8h+pSid]; pSourceSid
0x18002e236  mov     rdx, rax; pDestinationSid
0x18002e239  mov     ecx, [rsp+0B8h+cbSid]; nDestinationSidLength
0x18002e23d  call    cs:__imp_CopySid
0x18002e243  mov     rcx, [rsi]; hMem
0x18002e246  mov     [rsi], rbp
0x18002e249  test    rcx, rcx
0x18002e24c  jz      short loc_18002E254
0x18002e24e  call    cs:__imp_LocalFree
0x18002e254  mov     [rsi+8], r15d
0x18002e258  mov     qword ptr [rdi+10h], 0
0x18002e260  cmp     [rdi+18h], r15
0x18002e264  jbe     short loc_18002E269
0x18002e266  mov     rdi, [rdi]
0x18002e269  xor     eax, eax
0x18002e26b  mov     [rdi], ax
0x18002e26e  mov     [rbx+10h], rax
0x18002e272  cmp     [rbx+18h], r15
0x18002e276  jbe     short loc_18002E27B
0x18002e278  mov     rbx, [rbx]
0x18002e27b  xor     ecx, ecx
0x18002e27d  mov     [rbx], cx
0x18002e280  mov     rax, rsi
0x18002e283  mov     rcx, [rsp+0B8h+var_28]
0x18002e28b  xor     rcx, rsp; StackCookie
0x18002e28e  call    __security_check_cookie
0x18002e293  lea     r11, [rsp+0B8h+var_18]
0x18002e29b  mov     rbx, [r11+30h]
0x18002e29f  mov     rbp, [r11+38h]
0x18002e2a3  mov     rsp, r11
0x18002e2a6  pop     r15
0x18002e2a8  pop     rdi
0x18002e2a9  pop     rsi
0x18002e2aa  retn
0x18002e2ab  mov     rcx, [rsp+0B8h]; this
0x18002e2b3  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18002e2ba  mov     edx, 146Fh; void *
0x18002e2bf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002e2c5  lea     r8, aOnecoreVmCommo_31; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x18002e2cc  mov     edx, 1469h; void *
0x18002e2d1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
