# IkeCompareCertificateName

- ea: `0x18008b1a4`
- end: `0x18008b26d`
- name: `IkeCompareCertificateName`
- size: `201`
- prototype: `__int64 __fastcall(PCERT_NAME_BLOB pName, PCERT_NAME_BLOB)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000413c`
- `0x18008b274`

## callees

- `0x1800037c4`
- `0x18004aa3c`
- `0x18008a130`
- `0x18008b1a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008b21e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18008b21e`
- `CRYPT32!CertCompareCertificateName` at `0x18008b231`
- `CRYPT32!CertCompareCertificateName` at `0x18008b231`

## string_xrefs

- `0x18008b1cf`: `IkeCompareCertificateName`
- `0x18008b24f`: `IkeCompareCertificateName`

## pseudocode

```c
__int64 __fastcall IkeCompareCertificateName(PCERT_NAME_BLOB pName, PCERT_NAME_BLOB a2)
{
  unsigned int v4; // ebx
  PCNZWCH lpString1; // [rsp+50h] [rbp+18h] BYREF
  PCNZWCH lpString2; // [rsp+58h] [rbp+20h] BYREF

  lpString1 = 0;
  lpString2 = 0;
  v4 = 1;
  TraceLogHelper("IkeCompareCertificateName", 1);
  if ( IkeCertNameToStr(pName) || IkeCertNameToStr(a2) || CompareStringW(0x7Fu, 0, lpString1, -1, lpString2, -1) != 2 )
    v4 = CertCompareCertificateName(1u, pName, a2);
  WfpMemFree((LPCVOID *)&lpString1);
  WfpMemFree((LPCVOID *)&lpString2);
  TraceLogHelper("IkeCompareCertificateName", 0);
  return v4;
}

```

## disassembly

```asm
0x18008b1a4  mov     rax, rsp
0x18008b1a7  mov     [rax+8], rbx
0x18008b1ab  mov     [rax+10h], rsi
0x18008b1af  push    rdi
0x18008b1b0  sub     rsp, 30h
0x18008b1b4  mov     rdi, rdx
0x18008b1b7  mov     qword ptr [rax+18h], 0
0x18008b1bf  mov     rsi, rcx
0x18008b1c2  mov     qword ptr [rax+20h], 0
0x18008b1ca  mov     ebx, 1
0x18008b1cf  lea     rcx, aIkecomparecert; "IkeCompareCertificateName"
0x18008b1d6  mov     edx, ebx
0x18008b1d8  call    TraceLogHelper
0x18008b1dd  lea     rdx, [rsp+38h+lpString1]
0x18008b1e2  mov     rcx, rsi; pName
0x18008b1e5  call    IkeCertNameToStr
0x18008b1ea  test    rax, rax
0x18008b1ed  jnz     short loc_18008B229
0x18008b1ef  lea     rdx, [rsp+38h+arg_18]
0x18008b1f4  mov     rcx, rdi; pName
0x18008b1f7  call    IkeCertNameToStr
0x18008b1fc  test    rax, rax
0x18008b1ff  jnz     short loc_18008B229
0x18008b201  mov     rax, [rsp+38h+arg_18]
0x18008b206  lea     ecx, [rbx+7Eh]; Locale
0x18008b209  mov     r8, [rsp+38h+lpString1]; lpString1
0x18008b20e  or      r9d, 0FFFFFFFFh; cchCount1
0x18008b212  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18008b217  xor     edx, edx; dwCmpFlags
0x18008b219  mov     [rsp+38h+lpString2], rax; lpString2
0x18008b21e  call    cs:__imp_CompareStringW
0x18008b224  cmp     eax, 2
0x18008b227  jz      short loc_18008B239
0x18008b229  mov     r8, rdi; pCertName2
0x18008b22c  mov     rdx, rsi; pCertName1
0x18008b22f  mov     ecx, ebx; dwCertEncodingType
0x18008b231  call    cs:__imp_CertCompareCertificateName
0x18008b237  mov     ebx, eax
0x18008b239  lea     rcx, [rsp+38h+lpString1]
0x18008b23e  call    WfpMemFree
0x18008b243  lea     rcx, [rsp+38h+arg_18]
0x18008b248  call    WfpMemFree
0x18008b24d  xor     edx, edx
0x18008b24f  lea     rcx, aIkecomparecert; "IkeCompareCertificateName"
0x18008b256  call    TraceLogHelper
0x18008b25b  mov     rsi, [rsp+38h+arg_8]
0x18008b260  mov     eax, ebx
0x18008b262  mov     rbx, [rsp+38h+arg_0]
0x18008b267  add     rsp, 30h
0x18008b26b  pop     rdi
0x18008b26c  retn
```
