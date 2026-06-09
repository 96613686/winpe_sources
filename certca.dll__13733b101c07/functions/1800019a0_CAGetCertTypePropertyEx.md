# CAGetCertTypePropertyEx

- ea: `0x1800019a0`
- end: `0x180001be7`
- name: `CAGetCertTypePropertyEx`
- size: `583`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002d1c0`
- `0x18002e710`
- `0x18003211c`

## callees

- `0x180001920`
- `0x1800019a0`
- `0x180002ef0`
- `0x18000d520`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a43`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001aaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ae1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001b5c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a0d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a43`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001a79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001aaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ae1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001b5c`

## string_xrefs

- `0x180001a88`: `msPKI-Template-Schema-Version`
- `0x180001b35`: `msPKI-Template-Schema-Version`
- `0x1800019e4`: `msPKI-Template-Minor-Revision`

## pseudocode

```c
DWORD __fastcall CAGetCertTypePropertyEx(CCertTypeInfo *this, PCNZWCH lpString1, HLOCAL *a3)
{
  int v6; // ebp

  if ( !this )
    return -2147467261;
  if ( !*((_DWORD *)this + 42) && (unsigned int)mylstrcmpNLSub(L"cn", lpString1, -1, 1u) )
    return -2147467263;
  if ( !lpString1 || !a3 )
    return -2147467261;
  if ( !*((_DWORD *)this + 22) && (unsigned int)IsV2Property(lpString1) )
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
    {
      *(_DWORD *)a3 = 1;
      return 0;
    }
    return -2147023728;
  }
  v6 = 0;
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"msPKI-Template-Minor-Revision", -1) == 2 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 16);
    return v6;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"msPKI-RA-Signature", -1) == 2 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 21);
    return 0;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"msPKI-Minimal-Key-Size", -1) == 2 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 20);
    return v6;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"msPKI-Template-Schema-Version", -1) == 2 )
  {
    *(_DWORD *)a3 = *((_DWORD *)this + 22);
    return v6;
  }
  if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"revision", -1) != 2 )
    return CCertTypeInfo::GetProperty(this, lpString1, a3);
  *(_DWORD *)a3 = *((_DWORD *)this + 36);
  return 0;
}

```

## disassembly

```asm
0x1800019a0  push    rbx
0x1800019a2  push    rbp
0x1800019a3  push    rsi
0x1800019a4  push    rdi
0x1800019a5  sub     rsp, 38h
0x1800019a9  mov     rsi, r8
0x1800019ac  mov     rdi, rdx
0x1800019af  mov     rbx, rcx
0x1800019b2  test    rcx, rcx
0x1800019b5  jz      loc_180001B7A
0x1800019bb  cmp     dword ptr [rcx+0A8h], 0
0x1800019c2  jz      loc_180001B98
0x1800019c8  test    rdi, rdi
0x1800019cb  jz      loc_180001BDD
0x1800019d1  test    rsi, rsi
0x1800019d4  jz      loc_180001BDD
0x1800019da  cmp     dword ptr [rbx+58h], 0
0x1800019de  jz      loc_180001B25
0x1800019e4  lea     rax, aMspkiTemplateM; "msPKI-Template-Minor-Revision"
0x1800019eb  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800019f3  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800019f9  mov     [rsp+58h+lpString2], rax; lpString2
0x1800019fe  mov     r8, rdi; lpString1
0x180001a01  mov     edx, 1; dwCmpFlags
0x180001a06  mov     ecx, 7Fh; Locale
0x180001a0b  xor     ebp, ebp
0x180001a0d  call    cs:__imp_CompareStringW
0x180001a13  cmp     eax, 2
0x180001a16  jz      loc_180001BC9
0x180001a1c  lea     rax, aMspkiRaSignatu; "msPKI-RA-Signature"
0x180001a23  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001a2b  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001a31  mov     [rsp+58h+lpString2], rax; lpString2
0x180001a36  mov     r8, rdi; lpString1
0x180001a39  mov     edx, 1; dwCmpFlags
0x180001a3e  mov     ecx, 7Fh; Locale
0x180001a43  call    cs:__imp_CompareStringW
0x180001a49  cmp     eax, 2
0x180001a4c  jz      loc_180001B88
0x180001a52  lea     rax, aMspkiMinimalKe; "msPKI-Minimal-Key-Size"
0x180001a59  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001a61  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001a67  mov     [rsp+58h+lpString2], rax; lpString2
0x180001a6c  mov     r8, rdi; lpString1
0x180001a6f  mov     edx, 1; dwCmpFlags
0x180001a74  mov     ecx, 7Fh; Locale
0x180001a79  call    cs:__imp_CompareStringW
0x180001a7f  cmp     eax, 2
0x180001a82  jz      loc_180001BD3
0x180001a88  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001a8f  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001a97  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001a9d  mov     [rsp+58h+lpString2], rax; lpString2
0x180001aa2  mov     r8, rdi; lpString1
0x180001aa5  mov     edx, 1; dwCmpFlags
0x180001aaa  mov     ecx, 7Fh; Locale
0x180001aaf  call    cs:__imp_CompareStringW
0x180001ab5  cmp     eax, 2
0x180001ab8  jz      short loc_180001B02
0x180001aba  lea     rax, aRevision_0; "revision"
0x180001ac1  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001ac9  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001acf  mov     [rsp+58h+lpString2], rax; lpString2
0x180001ad4  mov     r8, rdi; lpString1
0x180001ad7  mov     edx, 1; dwCmpFlags
0x180001adc  mov     ecx, 7Fh; Locale
0x180001ae1  call    cs:__imp_CompareStringW
0x180001ae7  cmp     eax, 2
0x180001aea  jz      short loc_180001B12
0x180001aec  mov     r8, rsi; unsigned __int16 ***
0x180001aef  mov     rdx, rdi; unsigned __int16 *
0x180001af2  mov     rcx, rbx; this
0x180001af5  add     rsp, 38h
0x180001af9  pop     rdi
0x180001afa  pop     rsi
0x180001afb  pop     rbp
0x180001afc  pop     rbx
0x180001afd  jmp     ?GetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAPEAG@Z; CCertTypeInfo::GetProperty(ushort const *,ushort * * *)
0x180001b02  mov     eax, [rbx+58h]
0x180001b05  mov     [rsi], eax
0x180001b07  mov     eax, ebp
0x180001b09  add     rsp, 38h
0x180001b0d  pop     rdi
0x180001b0e  pop     rsi
0x180001b0f  pop     rbp
0x180001b10  pop     rbx
0x180001b11  retn
0x180001b12  mov     eax, [rbx+90h]
0x180001b18  mov     [rsi], eax
0x180001b1a  mov     eax, ebp
0x180001b1c  add     rsp, 38h
0x180001b20  pop     rdi
0x180001b21  pop     rsi
0x180001b22  pop     rbp
0x180001b23  pop     rbx
0x180001b24  retn
0x180001b25  mov     rcx, rdi; lpString1
0x180001b28  call    ?IsV2Property@@YAHPEBG@Z; IsV2Property(ushort const *)
0x180001b2d  test    eax, eax
0x180001b2f  jz      loc_1800019E4
0x180001b35  lea     rax, aMspkiTemplateS; "msPKI-Template-Schema-Version"
0x180001b3c  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180001b44  mov     r9d, 0FFFFFFFFh; cchCount1
0x180001b4a  mov     [rsp+58h+lpString2], rax; lpString2
0x180001b4f  mov     r8, rdi; lpString1
0x180001b52  mov     edx, 1; dwCmpFlags
0x180001b57  mov     ecx, 7Fh; Locale
0x180001b5c  call    cs:__imp_CompareStringW
0x180001b62  cmp     eax, 2
0x180001b65  jnz     short loc_180001BBF
0x180001b67  xor     ebp, ebp
0x180001b69  mov     dword ptr [rsi], 1
0x180001b6f  mov     eax, ebp
0x180001b71  add     rsp, 38h
0x180001b75  pop     rdi
0x180001b76  pop     rsi
0x180001b77  pop     rbp
0x180001b78  pop     rbx
0x180001b79  retn
0x180001b7a  mov     eax, 80004003h
0x180001b7f  add     rsp, 38h
0x180001b83  pop     rdi
0x180001b84  pop     rsi
0x180001b85  pop     rbp
0x180001b86  pop     rbx
0x180001b87  retn
0x180001b88  mov     eax, [rbx+54h]
0x180001b8b  mov     [rsi], eax
0x180001b8d  mov     eax, ebp
0x180001b8f  add     rsp, 38h
0x180001b93  pop     rdi
0x180001b94  pop     rsi
0x180001b95  pop     rbp
0x180001b96  pop     rbx
0x180001b97  retn
0x180001b98  mov     r9b, 1; bool
0x180001b9b  lea     rcx, aCn_1; "cn"
0x180001ba2  mov     r8d, 0FFFFFFFFh; int
0x180001ba8  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x180001bad  test    eax, eax
0x180001baf  jz      loc_1800019C8
0x180001bb5  mov     eax, 80004001h
0x180001bba  jmp     loc_180001B09
0x180001bbf  mov     ebp, 80070490h
0x180001bc4  jmp     loc_180001B07
0x180001bc9  mov     eax, [rbx+40h]
0x180001bcc  mov     [rsi], eax
0x180001bce  jmp     loc_180001B07
0x180001bd3  mov     eax, [rbx+50h]
0x180001bd6  mov     [rsi], eax
0x180001bd8  jmp     loc_180001B07
0x180001bdd  mov     ebp, 80004003h
0x180001be2  jmp     loc_180001B07
```
