# _GetVolatileCertIdString(_CERT_CONTEXT const *)

- ea: `0x180004790`
- end: `0x1800048c8`
- name: `?_GetVolatileCertIdString@@YAPEAGPEBU_CERT_CONTEXT@@@Z`
- size: `312`
- prototype: `unsigned __int16 *__fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180001480`
- `0x180001970`
- `0x180002b10`

## callees

- `0x180004790`
- `0x180004c50`
- `0x180008864`
- `0x18000a800`

## import_xrefs

- `CRYPT32!CertNameToStrW` at `0x180004853`
- `CRYPT32!CertNameToStrW` at `0x180004853`
- `CRYPT32!CryptBinaryToStringW` at `0x18000482b`
- `CRYPT32!CryptBinaryToStringW` at `0x18000482b`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800047f7`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800047f7`

## pseudocode

```c
unsigned __int16 *__fastcall _GetVolatileCertIdString(PCCERT_CONTEXT pCertContext)
{
  unsigned __int64 v2; // rdx
  unsigned __int16 *v3; // rcx
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rdx
  unsigned __int16 *v6; // rcx
  DWORD pcbData; // [rsp+30h] [rbp-98h] BYREF
  DWORD pcchString; // [rsp+34h] [rbp-94h] BYREF
  BYTE pvData[24]; // [rsp+38h] [rbp-90h] BYREF
  WCHAR pszString[48]; // [rsp+50h] [rbp-78h] BYREF

  pcbData = 20;
  psz = 0;
  if ( !pCertContext )
    return L"Empty";
  if ( eksvcDebugEnabled(3u) )
  {
    if ( CertGetCertificateContextProperty(pCertContext, 3u, pvData, &pcbData) )
    {
      pcchString = 41;
      if ( CryptBinaryToStringW(pvData, pcbData, 0x4000000Cu, pszString, &pcchString) )
      {
        CertNameToStrW(1u, &pCertContext->pCertInfo->Subject, 0x12000003u, &psz, 0x80u);
        v4 = -1;
        do
          ++v4;
        while ( *(&psz + v4) );
        if ( v4 > 0x55 )
          dword_18001282A = 43;
        StringCchCatW(v3, v2, L":");
        StringCchCatW(v6, v5, pszString);
      }
    }
  }
  if ( psz )
    return &psz;
  else
    return L"Empty";
}

```

## disassembly

```asm
0x180004790  mov     [rsp+arg_8], rbx
0x180004795  push    rdi
0x180004796  sub     rsp, 0C0h
0x18000479d  mov     rax, cs:__security_cookie
0x1800047a4  xor     rax, rsp
0x1800047a7  mov     [rsp+0C8h+var_18], rax
0x1800047af  xor     eax, eax
0x1800047b1  mov     [rsp+0C8h+pcbData], 14h
0x1800047b9  mov     cs:psz, ax
0x1800047c0  mov     rbx, rcx
0x1800047c3  test    rcx, rcx
0x1800047c6  jz      loc_1800048A0
0x1800047cc  mov     ecx, 3; unsigned int
0x1800047d1  call    ?eksvcDebugEnabled@@YA_NK@Z; eksvcDebugEnabled(ulong)
0x1800047d6  lea     rdi, psz
0x1800047dd  test    al, al
0x1800047df  jz      loc_180004890
0x1800047e5  lea     r9, [rsp+0C8h+pcbData]; pcbData
0x1800047ea  mov     edx, 3; dwPropId
0x1800047ef  lea     r8, [rsp+0C8h+pvData]; pvData
0x1800047f4  mov     rcx, rbx; pCertContext
0x1800047f7  call    cs:__imp_CertGetCertificateContextProperty
0x1800047fd  test    eax, eax
0x1800047ff  jz      loc_180004890
0x180004805  mov     edx, [rsp+0C8h+pcbData]; cbBinary
0x180004809  lea     rax, [rsp+0C8h+var_94]
0x18000480e  lea     r9, [rsp+0C8h+pszString]; pszString
0x180004813  mov     [rsp+0C8h+pcchString], rax; pcchString
0x180004818  mov     r8d, 4000000Ch; dwFlags
0x18000481e  mov     [rsp+0C8h+var_94], 29h ; ')'
0x180004826  lea     rcx, [rsp+0C8h+pvData]; pbBinary
0x18000482b  call    cs:__imp_CryptBinaryToStringW
0x180004831  test    eax, eax
0x180004833  jz      short loc_180004890
0x180004835  mov     rdx, [rbx+18h]
0x180004839  mov     r9, rdi; psz
0x18000483c  add     rdx, 50h ; 'P'; pName
0x180004840  mov     dword ptr [rsp+0C8h+pcchString], 80h; csz
0x180004848  mov     ecx, 1; dwCertEncodingType
0x18000484d  mov     r8d, 12000003h; dwStrType
0x180004853  call    cs:__imp_CertNameToStrW
0x180004859  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180004860  inc     rax
0x180004863  cmp     word ptr [rdi+rax*2], 0
0x180004868  jnz     short loc_180004860
0x18000486a  cmp     rax, 55h ; 'U'
0x18000486e  jbe     short loc_18000487A
0x180004870  mov     cs:dword_18001282A, 2Bh ; '+'
0x18000487a  lea     r8, asc_18000E7E8; ":"
0x180004881  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004886  lea     r8, [rsp+0C8h+pszString]; unsigned __int16 *
0x18000488b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180004890  xor     ecx, ecx
0x180004892  cmp     cx, cs:psz
0x180004899  jz      short loc_1800048A0
0x18000489b  mov     rax, rdi
0x18000489e  jmp     short loc_1800048A7
0x1800048a0  lea     rax, aEmpty; "Empty"
0x1800048a7  mov     rcx, [rsp+0C8h+var_18]
0x1800048af  xor     rcx, rsp; StackCookie
0x1800048b2  call    __security_check_cookie
0x1800048b7  mov     rbx, [rsp+0C8h+arg_8]
0x1800048bf  add     rsp, 0C0h
0x1800048c6  pop     rdi
0x1800048c7  retn
```
