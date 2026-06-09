# ValidateOcspPreFetchContent

- ea: `0x180009f28`
- end: `0x180009fea`
- name: `ValidateOcspPreFetchContent`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003c90`

## callees

- `0x1800068b0`
- `0x180009f28`
- `0x180009ff0`
- `0x18000a138`
- `0x18000a204`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fce`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009f8e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009fa2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009f8e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180009fa2`

## pseudocode

```c
__int64 __fastcall ValidateOcspPreFetchContent(__int64 a1)
{
  unsigned int v2; // edi
  struct _OCSP_REQUEST_INFO *v3; // rbx
  struct _OCSP_BASIC_RESPONSE_INFO *Content; // r14
  struct _OCSP_REQUEST_INFO *OcspRequestInfoFromOcspUrl; // rax
  struct _OCSP_BASIC_RESPONSE_ENTRY *OcspResponseEntry; // rax
  const FILETIME *p_NextUpdate; // rsi

  v2 = 0;
  v3 = 0;
  Content = GetOcspBasicResponseInfoFromPreFetchContent(
              *(BYTE **)(*(_QWORD *)(*(_QWORD *)(a1 + 216) + 8LL) + 8LL),
              **(_DWORD **)(*(_QWORD *)(a1 + 216) + 8LL));
  if ( !Content )
    goto LABEL_9;
  OcspRequestInfoFromOcspUrl = GetOcspRequestInfoFromOcspUrl(*(LPCWSTR *)(a1 + 72));
  v3 = OcspRequestInfoFromOcspUrl;
  if ( !OcspRequestInfoFromOcspUrl )
    goto LABEL_9;
  if ( !OcspRequestInfoFromOcspUrl->cRequestEntry )
  {
    SetLastError(0xDu);
    goto LABEL_9;
  }
  OcspResponseEntry = FindOcspResponseEntry(&OcspRequestInfoFromOcspUrl->rgRequestEntry->CertId, Content);
  if ( !OcspResponseEntry )
  {
LABEL_9:
    v2 = -1;
    goto LABEL_7;
  }
  p_NextUpdate = &OcspResponseEntry->NextUpdate;
  if ( CompareFileTime(&OcspResponseEntry->ThisUpdate, (const FILETIME *)(a1 + 152)) > 0
    || CompareFileTime(p_NextUpdate, (const FILETIME *)(a1 + 160)) > 0 )
  {
    v2 = 1;
    *(FILETIME *)(a1 + 240) = *p_NextUpdate;
  }
LABEL_7:
  PkiFree(Content);
  PkiFree(v3);
  return v2;
}

```

## disassembly

```asm
0x180009f28  push    rbx
0x180009f2a  push    rbp
0x180009f2b  push    rsi
0x180009f2c  push    rdi
0x180009f2d  push    r14
0x180009f2f  sub     rsp, 20h
0x180009f33  mov     rax, [rcx+0D8h]
0x180009f3a  mov     rbp, rcx
0x180009f3d  xor     edi, edi
0x180009f3f  mov     ebx, edi
0x180009f41  mov     rcx, [rax+8]
0x180009f45  mov     edx, [rcx]; cbEncoded
0x180009f47  mov     rcx, [rcx+8]; pbEncoded
0x180009f4b  call    ?GetOcspBasicResponseInfoFromPreFetchContent@@YAPEAU_OCSP_BASIC_RESPONSE_INFO@@PEBEK@Z; GetOcspBasicResponseInfoFromPreFetchContent(uchar const *,ulong)
0x180009f50  mov     r14, rax
0x180009f53  test    rax, rax
0x180009f56  jz      short loc_180009FD4
0x180009f58  mov     rcx, [rbp+48h]; pwszUrl
0x180009f5c  call    ?GetOcspRequestInfoFromOcspUrl@@YAPEAU_OCSP_REQUEST_INFO@@PEBG@Z; GetOcspRequestInfoFromOcspUrl(ushort const *)
0x180009f61  mov     rbx, rax
0x180009f64  test    rax, rax
0x180009f67  jz      short loc_180009FD4
0x180009f69  cmp     [rax+10h], edi
0x180009f6c  jz      short loc_180009FC9
0x180009f6e  mov     rcx, [rax+18h]; struct _OCSP_CERT_ID *
0x180009f72  mov     rdx, r14; struct _OCSP_BASIC_RESPONSE_INFO *
0x180009f75  call    ?FindOcspResponseEntry@@YAPEAU_OCSP_BASIC_RESPONSE_ENTRY@@PEAU_OCSP_CERT_ID@@PEAU_OCSP_BASIC_RESPONSE_INFO@@@Z; FindOcspResponseEntry(_OCSP_CERT_ID *,_OCSP_BASIC_RESPONSE_INFO *)
0x180009f7a  test    rax, rax
0x180009f7d  jz      short loc_180009FD4
0x180009f7f  lea     rdx, [rbp+98h]; lpFileTime2
0x180009f86  lea     rcx, [rax+58h]; lpFileTime1
0x180009f8a  lea     rsi, [rax+60h]
0x180009f8e  call    cs:__imp_CompareFileTime
0x180009f94  test    eax, eax
0x180009f96  jg      short loc_180009FD9
0x180009f98  lea     rdx, [rbp+0A0h]; lpFileTime2
0x180009f9f  mov     rcx, rsi; lpFileTime1
0x180009fa2  call    cs:__imp_CompareFileTime
0x180009fa8  test    eax, eax
0x180009faa  jg      short loc_180009FD9
0x180009fac  mov     rcx, r14; hMem
0x180009faf  call    PkiFree
0x180009fb4  mov     rcx, rbx; hMem
0x180009fb7  call    PkiFree
0x180009fbc  mov     eax, edi
0x180009fbe  add     rsp, 20h
0x180009fc2  pop     r14
0x180009fc4  pop     rdi
0x180009fc5  pop     rsi
0x180009fc6  pop     rbp
0x180009fc7  pop     rbx
0x180009fc8  retn
0x180009fc9  mov     ecx, 0Dh; dwErrCode
0x180009fce  call    cs:__imp_SetLastError
0x180009fd4  or      edi, 0FFFFFFFFh
0x180009fd7  jmp     short loc_180009FAC
0x180009fd9  mov     rax, [rsi]
0x180009fdc  mov     edi, 1
0x180009fe1  mov     [rbp+0F0h], rax
0x180009fe8  jmp     short loc_180009FAC
```
