# IECompatLogEvent

- ea: `0x180066b80`
- end: `0x180066eaf`
- name: `IECompatLogEvent`
- size: `815`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066f00`
- `0x180066f40`
- `0x180066f90`
- `0x180066fd0`
- `0x180067010`
- `0x180067060`
- `0x1800670a0`
- `0x180067150`
- `0x180067240`
- `0x180067280`
- `0x180067330`
- `0x180067390`

## callees

- `0x18004a830`
- `0x18006685c`
- `0x1800668b0`
- `0x180066a90`
- `0x180066b80`
- `0x180083bc2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066e91`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066c2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066d84`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066c2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180066d84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066d73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066c7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180066d73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066c54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066c8c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066c54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180066c8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066c72`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180066e83`
- `api-ms-win-eventlog-legacy-l1-1-0!ReportEventW` at `0x180066e83`

## string_xrefs

- `0x180066cf9`: `UrlPath`
- `0x180066dca`: `UrlPath`

## pseudocode

```c
__int64 __fastcall IECompatLogEvent(
        DWORD a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v7; // esi
  unsigned __int16 *v9; // r15
  unsigned __int16 *lpRawData; // r12
  unsigned __int16 **v13; // r14
  signed int appended; // ebx
  SIZE_T v15; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 **v17; // rax
  HANDLE v18; // rax
  __int64 k; // rsi
  HANDLE v20; // rax
  unsigned __int64 CchXMLField; // rax
  SIZE_T v22; // r11
  __int64 v23; // r10
  unsigned __int64 v24; // r13
  __int64 i; // r10
  int v26; // r10d
  SIZE_T v27; // rbx
  HANDLE v28; // rax
  __int64 j; // rsi
  signed int LastError; // eax
  unsigned __int16 *v31; // [rsp+50h] [rbp-48h] BYREF
  LPCWSTR Strings; // [rsp+58h] [rbp-40h] BYREF

  v7 = 0;
  v9 = 0;
  v31 = 0;
  Strings = 0;
  if ( !(unsigned int)IECompatLoggingEnabledInternal() )
    return 1;
  lpRawData = 0;
  v13 = 0;
  if ( a4 || !a3 || !*a3 )
  {
    appended = HTMLEncodeString(a3, &v31);
    if ( appended >= 0 )
    {
      if ( a5 )
      {
        v15 = 8LL * a5;
        if ( !is_mul_ok(a5, 8u) )
          v15 = -1;
        ProcessHeap = GetProcessHeap();
        v17 = (unsigned __int16 **)HeapAlloc(ProcessHeap, 8u, v15);
        v13 = v17;
        if ( !v17 )
        {
          appended = -2147024882;
          goto LABEL_13;
        }
        memset_0(v17, 0, 8LL * a5);
      }
      if ( a7 )
      {
        while ( v7 < a5 )
        {
          appended = HTMLEncodeString(*(const unsigned __int16 **)(a7 + 8LL * v7), &v13[v7]);
          if ( appended < 0 )
            goto LABEL_13;
          ++v7;
        }
      }
      v9 = v31;
      GetCchXMLField(L"UrlPath", v31);
      GetCchXMLField(L"MitigationCode", a2);
      CchXMLField = GetCchXMLField(L"UrlZone", a4);
      v24 = v23 + CchXMLField + 1;
      if ( a6 )
      {
        for ( i = 0; (unsigned int)i < a5; i = (unsigned int)(v26 + 1) )
          v24 += GetCchXMLField(*(const unsigned __int16 **)(a6 + 8 * i), v13[i]);
      }
      v27 = 2 * v24;
      if ( !is_mul_ok(v24, 2u) )
        v27 = v22;
      v28 = GetProcessHeap();
      lpRawData = (unsigned __int16 *)HeapAlloc(v28, 8u, v27);
      if ( lpRawData )
      {
        *lpRawData = 0;
        appended = AppendXMLField(lpRawData, (unsigned int)v24, L"MitigationCode", a2);
        if ( appended >= 0 )
        {
          appended = AppendXMLField(lpRawData, (unsigned int)v24, L"UrlPath", v9);
          if ( appended >= 0 )
          {
            appended = AppendXMLField(lpRawData, (unsigned int)v24, L"UrlZone", a4);
            if ( appended >= 0 )
            {
              if ( a6 )
              {
                for ( j = 0; (unsigned int)j < a5; j = (unsigned int)(j + 1) )
                {
                  appended = AppendXMLField(lpRawData, (unsigned int)v24, *(unsigned __int16 **)(a6 + 8 * j), v13[j]);
                  if ( appended < 0 )
                    goto LABEL_14;
                }
              }
              Strings = &word_1801758E4;
              if ( !ReportEventW(hEventLog, 1u, 0, a1, 0, 1u, 2 * v24, &Strings, lpRawData) )
              {
                LastError = GetLastError();
                appended = LastError;
                if ( LastError > 0 )
                  appended = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
      }
      else
      {
        appended = -2147024882;
      }
      goto LABEL_14;
    }
LABEL_13:
    v9 = v31;
    goto LABEL_14;
  }
  appended = -2147467259;
LABEL_14:
  v18 = GetProcessHeap();
  HeapFree(v18, 0, lpRawData);
  CoTaskMemFree(v9);
  if ( v13 )
  {
    for ( k = 0; (unsigned int)k < a5; k = (unsigned int)(k + 1) )
      CoTaskMemFree(v13[k]);
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v13);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180066b80  mov     rax, rsp
0x180066b83  mov     [rax+18h], rbx
0x180066b87  mov     [rax+20h], r9
0x180066b8b  mov     [rax+10h], rdx
0x180066b8f  mov     [rax+8], ecx
0x180066b92  push    rbp
0x180066b93  push    rsi
0x180066b94  push    rdi
0x180066b95  push    r12
0x180066b97  push    r13
0x180066b99  push    r14
0x180066b9b  push    r15
0x180066b9d  sub     rsp, 60h
0x180066ba1  xor     esi, esi
0x180066ba3  mov     r13, r9
0x180066ba6  mov     r15d, esi
0x180066ba9  mov     [rax-48h], rsi
0x180066bad  mov     [rax-40h], rsi
0x180066bb1  mov     rbx, r8
0x180066bb4  call    ?IECompatLoggingEnabledInternal@@YAHXZ; IECompatLoggingEnabledInternal(void)
0x180066bb9  test    eax, eax
0x180066bbb  jnz     short loc_180066BC5
0x180066bbd  lea     eax, [rsi+1]
0x180066bc0  jmp     loc_180066C94
0x180066bc5  mov     ebp, [rsp+98h+arg_20]
0x180066bcc  mov     r12, rsi
0x180066bcf  mov     r14, rsi
0x180066bd2  mov     edi, 1
0x180066bd7  test    r13, r13
0x180066bda  jnz     short loc_180066BED
0x180066bdc  test    rbx, rbx
0x180066bdf  jz      short loc_180066BED
0x180066be1  cmp     [rbx], si
0x180066be4  jz      short loc_180066BED
0x180066be6  mov     ebx, 80004005h
0x180066beb  jmp     short loc_180066C46
0x180066bed  lea     rdx, [rsp+98h+var_48]; unsigned __int16 **
0x180066bf2  mov     rcx, rbx; unsigned __int16 *
0x180066bf5  call    ?HTMLEncodeString@@YAJPEBGPEAPEAG@Z; HTMLEncodeString(ushort const *,ushort * *)
0x180066bfa  mov     ebx, eax
0x180066bfc  test    eax, eax
0x180066bfe  js      short loc_180066C41
0x180066c00  or      r11, 0FFFFFFFFFFFFFFFFh
0x180066c04  mov     r15d, 8
0x180066c0a  test    ebp, ebp
0x180066c0c  jz      loc_180066CC2
0x180066c12  mov     eax, r15d
0x180066c15  mul     rbp
0x180066c18  mov     rbx, rax
0x180066c1b  cmovb   rbx, r11
0x180066c1f  call    cs:__imp_GetProcessHeap
0x180066c25  mov     r8, rbx; dwBytes
0x180066c28  mov     edx, r15d; dwFlags
0x180066c2b  mov     rcx, rax; hHeap
0x180066c2e  call    cs:__imp_HeapAlloc
0x180066c34  mov     r14, rax
0x180066c37  test    rax, rax
0x180066c3a  jnz     short loc_180066CAC
0x180066c3c  mov     ebx, 8007000Eh
0x180066c41  mov     r15, [rsp+98h+var_48]
0x180066c46  call    cs:__imp_GetProcessHeap
0x180066c4c  mov     r8, r12; lpMem
0x180066c4f  xor     edx, edx; dwFlags
0x180066c51  mov     rcx, rax; hHeap
0x180066c54  call    cs:__imp_HeapFree
0x180066c5a  mov     rcx, r15; pv
0x180066c5d  call    cs:__imp_CoTaskMemFree
0x180066c63  test    r14, r14
0x180066c66  jz      short loc_180066C92
0x180066c68  xor     esi, esi
0x180066c6a  test    ebp, ebp
0x180066c6c  jz      short loc_180066C7E
0x180066c6e  mov     rcx, [r14+rsi*8]; pv
0x180066c72  call    cs:__imp_CoTaskMemFree
0x180066c78  add     esi, edi
0x180066c7a  cmp     esi, ebp
0x180066c7c  jb      short loc_180066C6E
0x180066c7e  call    cs:__imp_GetProcessHeap
0x180066c84  mov     r8, r14; lpMem
0x180066c87  xor     edx, edx; dwFlags
0x180066c89  mov     rcx, rax; hHeap
0x180066c8c  call    cs:__imp_HeapFree
0x180066c92  mov     eax, ebx
0x180066c94  mov     rbx, [rsp+98h+arg_10]
0x180066c9c  add     rsp, 60h
0x180066ca0  pop     r15
0x180066ca2  pop     r14
0x180066ca4  pop     r13
0x180066ca6  pop     r12
0x180066ca8  pop     rdi
0x180066ca9  pop     rsi
0x180066caa  pop     rbp
0x180066cab  retn
0x180066cac  lea     r8, ds:0[rbp*8]; Size
0x180066cb4  xor     edx, edx; Val
0x180066cb6  mov     rcx, rax; void *
0x180066cb9  call    memset_0
0x180066cbe  or      r11, 0FFFFFFFFFFFFFFFFh
0x180066cc2  mov     r15, [rsp+98h+arg_30]
0x180066cca  test    r15, r15
0x180066ccd  jz      short loc_180066CF4
0x180066ccf  cmp     esi, ebp
0x180066cd1  jnb     short loc_180066CF0
0x180066cd3  mov     ecx, esi
0x180066cd5  lea     rdx, [r14+rcx*8]; unsigned __int16 **
0x180066cd9  mov     rcx, [r15+rcx*8]; unsigned __int16 *
0x180066cdd  call    ?HTMLEncodeString@@YAJPEBGPEAPEAG@Z; HTMLEncodeString(ushort const *,ushort * *)
0x180066ce2  mov     ebx, eax
0x180066ce4  test    eax, eax
0x180066ce6  js      loc_180066C41
0x180066cec  add     esi, edi
0x180066cee  jmp     short loc_180066CCF
0x180066cf0  or      r11, 0FFFFFFFFFFFFFFFFh
0x180066cf4  mov     r15, [rsp+98h+var_48]
0x180066cf9  lea     rcx, aUrlpath; "UrlPath"
0x180066d00  mov     rdx, r15; unsigned __int16 *
0x180066d03  call    ?GetCchXMLField@@YA_KPEBG0@Z; GetCchXMLField(ushort const *,ushort const *)
0x180066d08  mov     rdx, [rsp+98h+arg_8]; unsigned __int16 *
0x180066d10  lea     rcx, aMitigationcode; "MitigationCode"
0x180066d17  mov     r10, rax
0x180066d1a  call    ?GetCchXMLField@@YA_KPEBG0@Z; GetCchXMLField(ushort const *,ushort const *)
0x180066d1f  mov     rdx, r13; unsigned __int16 *
0x180066d22  lea     rcx, aUrlzone; "UrlZone"
0x180066d29  add     r10, rax
0x180066d2c  call    ?GetCchXMLField@@YA_KPEBG0@Z; GetCchXMLField(ushort const *,ushort const *)
0x180066d31  mov     rsi, [rsp+98h+arg_28]
0x180066d39  lea     r13, [rax+1]
0x180066d3d  add     r13, r10
0x180066d40  test    rsi, rsi
0x180066d43  jz      short loc_180066D64
0x180066d45  xor     r10d, r10d
0x180066d48  test    ebp, ebp
0x180066d4a  jz      short loc_180066D64
0x180066d4c  mov     rdx, [r14+r10*8]; unsigned __int16 *
0x180066d50  mov     rcx, [rsi+r10*8]; unsigned __int16 *
0x180066d54  call    ?GetCchXMLField@@YA_KPEBG0@Z; GetCchXMLField(ushort const *,ushort const *)
0x180066d59  add     r13, rax
0x180066d5c  add     r10d, edi
0x180066d5f  cmp     r10d, ebp
0x180066d62  jb      short loc_180066D4C
0x180066d64  mov     eax, 2
0x180066d69  mul     r13
0x180066d6c  mov     rbx, rax
0x180066d6f  cmovb   rbx, r11
0x180066d73  call    cs:__imp_GetProcessHeap
0x180066d79  mov     r8, rbx; dwBytes
0x180066d7c  mov     edx, 8; dwFlags
0x180066d81  mov     rcx, rax; hHeap
0x180066d84  call    cs:__imp_HeapAlloc
0x180066d8a  mov     r12, rax
0x180066d8d  test    rax, rax
0x180066d90  jnz     short loc_180066D9C
0x180066d92  mov     ebx, 8007000Eh
0x180066d97  jmp     loc_180066C46
0x180066d9c  mov     r9, [rsp+98h+arg_8]; unsigned __int16 *
0x180066da4  lea     r8, aMitigationcode; "MitigationCode"
0x180066dab  xor     eax, eax
0x180066dad  mov     edx, r13d; unsigned __int64
0x180066db0  mov     rcx, r12; unsigned __int16 *
0x180066db3  mov     [r12], ax
0x180066db8  call    AppendXMLField
0x180066dbd  mov     ebx, eax
0x180066dbf  test    eax, eax
0x180066dc1  js      loc_180066C46
0x180066dc7  mov     r9, r15; unsigned __int16 *
0x180066dca  lea     r8, aUrlpath; "UrlPath"
0x180066dd1  mov     edx, r13d; unsigned __int64
0x180066dd4  mov     rcx, r12; unsigned __int16 *
0x180066dd7  call    AppendXMLField
0x180066ddc  mov     ebx, eax
0x180066dde  test    eax, eax
0x180066de0  js      loc_180066C46
0x180066de6  mov     r9, [rsp+98h+arg_18]; unsigned __int16 *
0x180066dee  lea     r8, aUrlzone; "UrlZone"
0x180066df5  mov     edx, r13d; unsigned __int64
0x180066df8  mov     rcx, r12; unsigned __int16 *
0x180066dfb  call    AppendXMLField
0x180066e00  mov     ebx, eax
0x180066e02  test    eax, eax
0x180066e04  js      loc_180066C46
0x180066e0a  test    rsi, rsi
0x180066e0d  jz      short loc_180066E3E
0x180066e0f  xor     esi, esi
0x180066e11  cmp     esi, ebp
0x180066e13  jnb     short loc_180066E3E
0x180066e15  mov     rax, [rsp+98h+arg_28]
0x180066e1d  mov     edx, r13d; unsigned __int64
0x180066e20  mov     r9, [r14+rsi*8]; unsigned __int16 *
0x180066e24  mov     rcx, r12; unsigned __int16 *
0x180066e27  mov     r8, [rax+rsi*8]; unsigned __int16 *
0x180066e2b  call    AppendXMLField
0x180066e30  mov     ebx, eax
0x180066e32  test    eax, eax
0x180066e34  js      loc_180066C46
0x180066e3a  add     esi, edi
0x180066e3c  jmp     short loc_180066E11
0x180066e3e  mov     r9d, [rsp+98h+dwEventID]; dwEventID
0x180066e46  lea     rax, word_1801758E4
0x180066e4d  mov     [rsp+98h+lpRawData], r12; lpRawData
0x180066e52  lea     rcx, [rsp+98h+Strings]
0x180066e57  mov     [rsp+98h+lpStrings], rcx; lpStrings
0x180066e5c  xor     r8d, r8d; wCategory
0x180066e5f  mov     rcx, cs:hEventLog; hEventLog
0x180066e66  mov     edx, edi; wType
0x180066e68  mov     [rsp+98h+Strings], rax
0x180066e6d  lea     eax, ds:0[r13*2]
0x180066e75  mov     [rsp+98h+dwDataSize], eax; dwDataSize
0x180066e79  mov     [rsp+98h+wNumStrings], di; wNumStrings
0x180066e7e  mov     [rsp+98h+lpUserSid], r8; lpUserSid
0x180066e83  call    cs:__imp_ReportEventW
0x180066e89  test    eax, eax
0x180066e8b  jnz     loc_180066C46
0x180066e91  call    cs:__imp_GetLastError
0x180066e97  mov     ebx, eax
0x180066e99  test    eax, eax
0x180066e9b  jle     loc_180066C46
0x180066ea1  movzx   ebx, ax
0x180066ea4  or      ebx, 80070000h
0x180066eaa  jmp     loc_180066C46
```
