# Vml::CreateType5Guid(_GUID const &,void const *,ulong)

- ea: `0x1800368c8`
- end: `0x180036ad7`
- name: `?CreateType5Guid@Vml@@YA?AU_GUID@@AEBU2@PEBXK@Z`
- size: `527`
- prototype: `struct _GUID *(Vml *__hidden this, struct _GUID *__return_ptr __struct_ptr retstr, const struct _GUID *, const void *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036040`

## callees

- `0x1800067c0`
- `0x1800368c8`
- `0x180039700`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180036a34`
- `bcrypt!BCryptDestroyHash` at `0x180036a34`
- `bcrypt!BCryptCreateHash` at `0x18003694f`
- `bcrypt!BCryptCreateHash` at `0x18003694f`
- `bcrypt!BCryptHashData` at `0x180036989`
- `bcrypt!BCryptHashData` at `0x1800369a8`
- `bcrypt!BCryptHashData` at `0x180036989`
- `bcrypt!BCryptHashData` at `0x1800369a8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180036a46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180036a46`
- `bcrypt!BCryptFinishHash` at `0x1800369c9`
- `bcrypt!BCryptFinishHash` at `0x1800369c9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003690e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003690e`

## string_xrefs

- `0x180036a71`: `onecore\vm\common\vml\VmGuid.h`
- `0x180036a86`: `onecore\vm\common\vml\VmGuid.h`
- `0x180036a9b`: `onecore\vm\common\vml\VmGuid.h`
- `0x180036ab0`: `onecore\vm\common\vml\VmGuid.h`
- `0x180036ac5`: `onecore\vm\common\vml\VmGuid.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct _GUID *__fastcall Vml::CreateType5Guid(Vml *this, struct _GUID *__return_ptr retstr, UCHAR *a3, const void *a4)
{
  ULONG v4; // esi
  NTSTATUS v7; // eax
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // eax
  __int16 v12; // cx
  __int16 v13; // dx
  char v14; // r8
  int pbSecret; // [rsp+20h] [rbp-60h]
  int pbSecreta; // [rsp+20h] [rbp-60h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-40h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-38h] BYREF
  UCHAR pbInput[4]; // [rsp+50h] [rbp-30h] BYREF
  int v21; // [rsp+54h] [rbp-2Ch]
  __int64 v22; // [rsp+58h] [rbp-28h]
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-20h] BYREF
  __int16 v24; // [rsp+64h] [rbp-1Ch]
  __int16 v25; // [rsp+66h] [rbp-1Ah]
  char v26; // [rsp+68h] [rbp-18h]
  int v27; // [rsp+69h] [rbp-17h]
  __int16 v28; // [rsp+6Dh] [rbp-13h]
  char v29; // [rsp+6Fh] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v4 = (unsigned int)a4;
  phAlgorithm = 0;
  v7 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4CC,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v7,
      pbSecret);
  phHash = 0;
  v8 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4D6,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v8,
      pbSecreta);
  v22 = *(_QWORD *)`ComputeService::Management::GetComputeSystemGuid'::`2'::c_ComputeSystemSeedId.Data4;
  *(_DWORD *)pbInput = 1141094346;
  v21 = -465449990;
  v9 = BCryptHashData(phHash, pbInput, 0x10u, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4E4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v9,
      pbSecreta);
  v10 = BCryptHashData(phHash, a3, v4, 0);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v10,
      pbSecreta);
  v11 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x4F4,
      (unsigned int)"onecore\\vm\\common\\vml\\VmGuid.h",
      (const char *)(unsigned int)v11,
      pbSecreta);
  v12 = v24;
  v13 = v25;
  v14 = v26;
  *(_DWORD *)this = _byteswap_ulong(*(unsigned int *)pbOutput);
  *((_WORD *)this + 2) = __ROR2__(v12, 8);
  *((_WORD *)this + 3) = __ROR2__(v13, 8) & 0xFFF | 0x5000;
  *((_BYTE *)this + 8) = v14 & 0x3F | 0x80;
  *(_DWORD *)((char *)this + 9) = v27;
  *(_WORD *)((char *)this + 13) = v28;
  *((_BYTE *)this + 15) = v29;
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (struct _GUID *)this;
}

```

## disassembly

```asm
0x1800368c8  mov     [rsp-18h+arg_0], rbx
0x1800368cd  push    rbp
0x1800368ce  push    rsi
0x1800368cf  push    rdi
0x1800368d0  mov     rbp, rsp
0x1800368d3  sub     rsp, 80h
0x1800368da  mov     rax, cs:__security_cookie
0x1800368e1  xor     rax, rsp
0x1800368e4  mov     [rbp+var_8], rax
0x1800368e8  mov     esi, r9d
0x1800368eb  mov     rdi, r8
0x1800368ee  mov     rbx, rcx
0x1800368f1  mov     [rbp+phAlgorithm], 0
0x1800368f9  xor     r9d, r9d; dwFlags
0x1800368fc  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180036903  lea     rdx, pszAlgId; "SHA1"
0x18003690a  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003690e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180036914  mov     rcx, [rbp+18h]; this
0x180036918  test    eax, eax
0x18003691a  js      loc_180036A83
0x180036920  mov     [rbp+phHash], 0
0x180036928  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180036930  mov     [rsp+80h+cbSecret], 0; cbSecret
0x180036938  mov     [rsp+80h+pbSecret], 0; int
0x180036941  xor     r9d, r9d; cbHashObject
0x180036944  xor     r8d, r8d; pbHashObject
0x180036947  lea     rdx, [rbp+phHash]; phHash
0x18003694b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003694f  call    cs:__imp_BCryptCreateHash
0x180036955  mov     rcx, [rbp+18h]; this
0x180036959  test    eax, eax
0x18003695b  js      loc_180036A98
0x180036961  mov     rax, qword ptr cs:?c_ComputeSystemSeedId@?1??GetComputeSystemGuid@Management@ComputeService@@YA?AU_GUID@@PEBG@Z@4U4@B.Data4; _GUID const `ComputeService::Management::GetComputeSystemGuid(ushort const *)'::`2'::c_ComputeSystemSeedId ...
0x180036968  mov     [rbp+var_28], rax
0x18003696c  mov     dword ptr [rbp+pbInput], 4403B7CAh
0x180036973  mov     [rbp+var_2C], 0E441CBFAh
0x18003697a  xor     r9d, r9d; dwFlags
0x18003697d  lea     r8d, [r9+10h]; cbInput
0x180036981  lea     rdx, [rbp+pbInput]; pbInput
0x180036985  mov     rcx, [rbp+phHash]; hHash
0x180036989  call    cs:__imp_BCryptHashData
0x18003698f  mov     rcx, [rbp+18h]; this
0x180036993  test    eax, eax
0x180036995  js      loc_180036AAD
0x18003699b  xor     r9d, r9d; dwFlags
0x18003699e  mov     r8d, esi; cbInput
0x1800369a1  mov     rdx, rdi; pbInput
0x1800369a4  mov     rcx, [rbp+phHash]; hHash
0x1800369a8  call    cs:__imp_BCryptHashData
0x1800369ae  mov     rcx, [rbp+18h]; this
0x1800369b2  test    eax, eax
0x1800369b4  js      loc_180036AC2
0x1800369ba  xor     r9d, r9d; dwFlags
0x1800369bd  lea     r8d, [r9+14h]; cbOutput
0x1800369c1  lea     rdx, [rbp+pbOutput]; pbOutput
0x1800369c5  mov     rcx, [rbp+phHash]; hHash
0x1800369c9  call    cs:__imp_BCryptFinishHash
0x1800369cf  mov     rcx, [rbp+18h]; this
0x1800369d3  test    eax, eax
0x1800369d5  js      loc_180036A6E
0x1800369db  mov     eax, dword ptr [rbp+pbOutput]
0x1800369de  movzx   ecx, [rbp+var_1C]
0x1800369e2  movzx   edx, [rbp+var_1A]
0x1800369e6  mov     r8b, [rbp+var_18]
0x1800369ea  bswap   eax
0x1800369ec  mov     [rbx], eax
0x1800369ee  ror     cx, 8
0x1800369f2  mov     [rbx+4], cx
0x1800369f6  ror     dx, 8
0x1800369fa  mov     eax, 0FFFh
0x1800369ff  and     dx, ax
0x180036a02  or      dx, 5000h
0x180036a07  mov     [rbx+6], dx
0x180036a0b  and     r8b, 3Fh
0x180036a0f  or      r8b, 80h
0x180036a13  mov     [rbx+8], r8b
0x180036a17  mov     eax, [rbp+var_17]
0x180036a1a  mov     [rbx+9], eax
0x180036a1d  movzx   eax, [rbp+var_13]
0x180036a21  mov     [rbx+0Dh], ax
0x180036a25  mov     al, [rbp+var_11]
0x180036a28  mov     [rbx+0Fh], al
0x180036a2b  mov     rcx, [rbp+phHash]; hHash
0x180036a2f  test    rcx, rcx
0x180036a32  jz      short loc_180036A3B
0x180036a34  call    cs:__imp_BCryptDestroyHash
0x180036a3a  nop
0x180036a3b  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180036a3f  test    rcx, rcx
0x180036a42  jz      short loc_180036A4C
0x180036a44  xor     edx, edx; dwFlags
0x180036a46  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180036a4c  mov     rax, rbx
0x180036a4f  mov     rcx, [rbp+var_8]
0x180036a53  xor     rcx, rsp; StackCookie
0x180036a56  call    __security_check_cookie
0x180036a5b  mov     rbx, [rsp+80h+arg_0]
0x180036a63  add     rsp, 80h
0x180036a6a  pop     rdi
0x180036a6b  pop     rsi
0x180036a6c  pop     rbp
0x180036a6d  retn
0x180036a6e  mov     r9d, eax; char *
0x180036a71  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x180036a78  mov     edx, 4F4h; void *
0x180036a7d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036a83  mov     r9d, eax; char *
0x180036a86  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x180036a8d  mov     edx, 4CCh; void *
0x180036a92  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036a98  mov     r9d, eax; char *
0x180036a9b  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x180036aa2  mov     edx, 4D6h; void *
0x180036aa7  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036aad  mov     r9d, eax; char *
0x180036ab0  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x180036ab7  mov     edx, 4E4h; void *
0x180036abc  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180036ac2  mov     r9d, eax; char *
0x180036ac5  lea     r8, aOnecoreVmCommo_17; "onecore\\vm\\common\\vml\\VmGuid.h"
0x180036acc  mov     edx, 4EBh; void *
0x180036ad1  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
