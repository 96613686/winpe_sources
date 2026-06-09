# StartAutoDisconnectForPort

- ea: `0x180013bb4`
- end: `0x18001404f`
- name: `StartAutoDisconnectForPort`
- size: `1179`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e364`
- `0x18000e86c`
- `0x180013584`
- `0x180015320`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x18000f334`
- `0x18000f528`
- `0x180013bb4`
- `0x18001a4bc`
- `0x18001aa34`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013def`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013def`

## pseudocode

```c
void __fastcall StartAutoDisconnectForPort(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  _DWORD *v4; // rdi
  __int64 VendorSpecific; // rax
  _DWORD *v6; // rcx
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // edi
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int8 *v13; // rcx
  int v14; // ebx
  unsigned __int64 v15; // rdi
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v18; // r8
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  if ( (*(_BYTE *)(a1 + 56) & 4) != 0 )
  {
    v3 = *(_QWORD *)(a1 + 168);
    if ( !v3 )
      v3 = *(_QWORD *)(a1 + 160);
    v4 = *(_DWORD **)(a1 + 8);
    if ( v4[330] != 2 )
    {
      VendorSpecific = RasAuthAttributeGetVendorSpecific(v2, 37, v3);
      if ( VendorSpecific )
      {
        v4[19] = v4[18];
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 72LL) = *(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 9LL)
                                                + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 6LL) << 24)
                                                + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 8LL) << 8)
                                                + (*(unsigned __int8 *)(*(_QWORD *)(VendorSpecific + 8) + 7LL) << 16);
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x4000u;
      }
    }
    v6 = *(_DWORD **)(a1 + 8);
    if ( (v6[13] & 0x4000) != 0 && (v6[19] != v6[18] || v6[21] != v6[20]) )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 4);
      InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 4, *(_DWORD *)(*(_QWORD *)(a1 + 8) + 72LL));
      if ( (byte_18004CF34 & 1) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v20,
          L"AuthAttribute Quarantine Session Timeout = %d",
          *(unsigned int *)(v7 + 72));
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
            (const wchar_t *)&v20);
      }
    }
    v8 = RasAuthAttributeGet(27, v3);
    v9 = *(unsigned int *)(a1 + 80);
    *(_DWORD *)(a1 + 84) = v9;
    if ( v8 )
    {
      v10 = *(_DWORD *)(v8 + 8);
      *(_DWORD *)(a1 + 80) = v10;
    }
    else
    {
      *(_DWORD *)(a1 + 80) = dword_18004CA10;
      v10 = dword_18004CA10;
    }
    v11 = RasAuthAttributeGetVendorSpecific(v9, 46, v3);
    if ( !v10 && !v11 || (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) & 0x4000) != 0 )
    {
LABEL_42:
      if ( (*(_BYTE *)(a1 + 56) & 4) != 0 && *(_DWORD *)(*(_QWORD *)(a1 + 8) + 1320LL) == 2 )
        return;
      goto LABEL_44;
    }
    LODWORD(v12) = 0;
    if ( v11 )
    {
      v13 = *(unsigned __int8 **)(v11 + 8);
      SystemTimeAsFileTime = 0;
      v14 = 10000000 * (v13[9] + (v13[6] << 24) + (v13[8] << 8) + (v13[7] << 16) - 1240428288);
      v15 = (10000000 * ((unsigned __int64)(v13[9] + (v13[6] << 24) + (v13[8] << 8) + (v13[7] << 16)) + 0x2B6109100LL)) >> 32;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( __PAIR64__(v15, v14) > *(_QWORD *)&SystemTimeAsFileTime )
        v12 = (__PAIR64__(v15, v14) - *(_QWORD *)&SystemTimeAsFileTime) / 0x989680;
    }
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v16 = *(unsigned int *)(a1 + 80);
      LOWORD(v20) = 0;
      FormatRRASErrorString((wchar_t *)&v20, L"AuthAttribute SessionTimeout = %d", v16);
      if ( (byte_18004CF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
          (const wchar_t *)&v20);
        if ( (byte_18004CF34 & 1) != 0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString((wchar_t *)&v20, L"AuthAttribute GraceTimeout   = %d", (unsigned int)v12);
          if ( (byte_18004CF34 & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
              (const wchar_t *)&v20);
        }
      }
    }
    if ( (_DWORD)v12 && (v17 = *(_DWORD *)(a1 + 80)) != 0 )
    {
      if ( (unsigned int)v12 > v17 )
        LODWORD(v12) = *(_DWORD *)(a1 + 80);
    }
    else if ( *(_DWORD *)(a1 + 80) )
    {
      LODWORD(v12) = *(_DWORD *)(a1 + 80);
    }
    else if ( !(_DWORD)v12 )
    {
LABEL_40:
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
          L"Not Setting SessionTimeout");
      goto LABEL_42;
    }
    if ( *(_DWORD *)(a1 + 84) != (_DWORD)v12
      || *(_DWORD *)(*(_QWORD *)(a1 + 8) + 84LL) != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL) )
    {
      if ( (byte_18004CF34 & 1) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString((wchar_t *)&v20, L"Setting SessionTimeout to %d", (unsigned int)v12);
        if ( (byte_18004CF34 & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(
            &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
            (const wchar_t *)&v20);
      }
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 4);
      InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 4, v12);
      goto LABEL_42;
    }
    goto LABEL_40;
  }
LABEL_44:
  if ( *(_DWORD *)(a1 + 88) )
  {
    if ( (byte_18004CF34 & 1) != 0 )
    {
      v18 = *(_QWORD *)(a1 + 16);
      LOWORD(v20) = 0;
      FormatRRASErrorString((wchar_t *)&v20, L"Inserting autodisconnect in timer q for port=%d, sec=%d", v18);
      if ( (byte_18004CF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
          (const wchar_t *)&v20);
    }
    RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 1);
    InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 1, *(_DWORD *)(a1 + 88));
  }
}

```

## disassembly

```asm
0x180013bb4  mov     [rsp-8+arg_8], rbx
0x180013bb9  mov     [rsp-8+arg_10], rsi
0x180013bbe  push    rbp
0x180013bbf  push    rdi
0x180013bc0  push    r12
0x180013bc2  push    r13
0x180013bc4  push    r14
0x180013bc6  lea     rbp, [rsp-760h]
0x180013bce  sub     rsp, 860h
0x180013bd5  mov     rax, cs:__security_cookie
0x180013bdc  xor     rax, rsp
0x180013bdf  mov     [rbp+780h+var_30], rax
0x180013be6  mov     rsi, rcx
0x180013be9  xor     eax, eax
0x180013beb  lea     rcx, [rsp+880h+var_82C]; void *
0x180013bf0  mov     [rsp+880h+var_830], eax
0x180013bf4  xor     edx, edx; Val
0x180013bf6  mov     r8d, 7FCh; Size
0x180013bfc  call    memset_0
0x180013c01  test    byte ptr [rsi+38h], 4
0x180013c05  lea     r13, RasPppTraceInfo
0x180013c0c  mov     r12d, 1
0x180013c12  jz      loc_180013F9E
0x180013c18  mov     rbx, [rsi+0A8h]
0x180013c1f  test    rbx, rbx
0x180013c22  jnz     short loc_180013C2B
0x180013c24  mov     rbx, [rsi+0A0h]
0x180013c2b  mov     rdi, [rsi+8]
0x180013c2f  mov     r14d, 4000h
0x180013c35  cmp     dword ptr [rdi+528h], 2
0x180013c3c  jz      short loc_180013C88
0x180013c3e  mov     r8, rbx
0x180013c41  mov     edx, 25h ; '%'
0x180013c46  call    RasAuthAttributeGetVendorSpecific
0x180013c4b  test    rax, rax
0x180013c4e  jz      short loc_180013C88
0x180013c50  mov     ecx, [rdi+48h]
0x180013c53  mov     [rdi+4Ch], ecx
0x180013c56  mov     rcx, [rax+8]
0x180013c5a  movzx   eax, byte ptr [rcx+8]
0x180013c5e  movzx   edx, byte ptr [rcx+7]
0x180013c62  shl     eax, 8
0x180013c65  shl     edx, 10h
0x180013c68  add     edx, eax
0x180013c6a  movzx   eax, byte ptr [rcx+6]
0x180013c6e  shl     eax, 18h
0x180013c71  add     edx, eax
0x180013c73  movzx   eax, byte ptr [rcx+9]
0x180013c77  add     edx, eax
0x180013c79  mov     rax, [rsi+8]
0x180013c7d  mov     [rax+48h], edx
0x180013c80  mov     rax, [rsi+8]
0x180013c84  or      [rax+34h], r14d
0x180013c88  mov     rcx, [rsi+8]
0x180013c8c  test    [rcx+34h], r14d
0x180013c90  jz      loc_180013D35
0x180013c96  mov     eax, [rcx+48h]
0x180013c99  cmp     [rcx+4Ch], eax
0x180013c9c  jnz     short loc_180013CAA
0x180013c9e  mov     eax, [rcx+50h]
0x180013ca1  cmp     [rcx+54h], eax
0x180013ca4  jz      loc_180013D35
0x180013caa  mov     ecx, [rsi+40h]
0x180013cad  xor     r9d, r9d
0x180013cb0  xor     r8d, r8d
0x180013cb3  mov     [rsp+880h+var_860], 4
0x180013cbb  xor     edx, edx
0x180013cbd  call    RemoveFromTimerQ
0x180013cc2  mov     rax, [rsi+8]
0x180013cc6  xor     r9d, r9d
0x180013cc9  mov     rdx, [rsi+10h]
0x180013ccd  xor     r8d, r8d
0x180013cd0  mov     ecx, [rax+48h]
0x180013cd3  mov     [rsp+880h+var_850], ecx
0x180013cd7  mov     ecx, [rsi+40h]
0x180013cda  mov     [rsp+880h+var_858], 4
0x180013ce2  mov     [rsp+880h+var_860], 0
0x180013cea  call    InsertInTimerQ
0x180013cef  test    cs:byte_18004CF34, r12b
0x180013cf6  jz      short loc_180013D35
0x180013cf8  mov     r8, [rsi+8]
0x180013cfc  lea     rdx, aAuthattributeQ; "AuthAttribute Quarantine Session Timeou"...
0x180013d03  xor     eax, eax
0x180013d05  lea     rcx, [rsp+880h+var_830]
0x180013d0a  mov     word ptr [rsp+880h+var_830], ax
0x180013d0f  mov     r8d, [r8+48h]
0x180013d13  call    FormatRRASErrorString
0x180013d18  test    cs:byte_18004CF34, r12b
0x180013d1f  jz      short loc_180013D35
0x180013d21  lea     r8, [rsp+880h+var_830]
0x180013d26  mov     rdx, r13
0x180013d29  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013d30  call    McTemplateU0z_EventWriteTransfer
0x180013d35  mov     rdx, rbx
0x180013d38  mov     ecx, 1Bh
0x180013d3d  call    RasAuthAttributeGet
0x180013d42  mov     ecx, [rsi+50h]
0x180013d45  mov     [rsi+54h], ecx
0x180013d48  test    rax, rax
0x180013d4b  jz      short loc_180013D55
0x180013d4d  mov     edi, [rax+8]
0x180013d50  mov     [rsi+50h], edi
0x180013d53  jmp     short loc_180013D64
0x180013d55  mov     eax, cs:dword_18004CA10
0x180013d5b  mov     [rsi+50h], eax
0x180013d5e  mov     edi, cs:dword_18004CA10
0x180013d64  mov     r8, rbx
0x180013d67  mov     edx, 2Eh ; '.'
0x180013d6c  call    RasAuthAttributeGetVendorSpecific
0x180013d71  test    edi, edi
0x180013d73  jnz     short loc_180013D7E
0x180013d75  test    rax, rax
0x180013d78  jz      loc_180013F87
0x180013d7e  mov     rcx, [rsi+8]
0x180013d82  test    [rcx+34h], r14d
0x180013d86  jnz     loc_180013F87
0x180013d8c  xor     r14d, r14d
0x180013d8f  test    rax, rax
0x180013d92  jz      loc_180013E22
0x180013d98  mov     rcx, [rax+8]
0x180013d9c  mov     qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180013da1  mov     dword ptr [rsp+880h+var_840+4], r14d
0x180013da6  movzx   edx, byte ptr [rcx+7]
0x180013daa  movzx   eax, byte ptr [rcx+8]
0x180013dae  shl     eax, 8
0x180013db1  shl     edx, 10h
0x180013db4  add     edx, eax
0x180013db6  movzx   eax, byte ptr [rcx+6]
0x180013dba  shl     eax, 18h
0x180013dbd  add     edx, eax
0x180013dbf  movzx   eax, byte ptr [rcx+9]
0x180013dc3  add     edx, eax
0x180013dc5  mov     rcx, 2B6109100h
0x180013dcf  mov     dword ptr [rsp+880h+var_840], edx
0x180013dd3  add     rcx, [rsp+880h+var_840]
0x180013dd8  imul    rdi, rcx, 989680h
0x180013ddf  lea     rcx, [rsp+880h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013de4  mov     [rsp+880h+var_840], rdi
0x180013de9  mov     ebx, edi
0x180013deb  shr     rdi, 20h
0x180013def  call    cs:__imp_GetSystemTimeAsFileTime
0x180013df5  mov     dword ptr [rsp+880h+var_840], ebx
0x180013df9  mov     dword ptr [rsp+880h+var_840+4], edi
0x180013dfd  mov     rcx, [rsp+880h+var_840]
0x180013e02  cmp     rcx, qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime]
0x180013e07  jbe     short loc_180013E22
0x180013e09  sub     rcx, qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime]
0x180013e0e  mov     rax, 0D6BF94D5E57A42BDh
0x180013e18  mul     rcx
0x180013e1b  mov     r14, rdx
0x180013e1e  shr     r14, 17h
0x180013e22  test    cs:byte_18004CF34, r12b
0x180013e29  jz      short loc_180013EA5
0x180013e2b  mov     r8d, [rsi+50h]
0x180013e2f  lea     rdx, aAuthattributeS; "AuthAttribute SessionTimeout = %d"
0x180013e36  xor     eax, eax
0x180013e38  lea     rcx, [rsp+880h+var_830]
0x180013e3d  mov     word ptr [rsp+880h+var_830], ax
0x180013e42  call    FormatRRASErrorString
0x180013e47  test    cs:byte_18004CF34, r12b
0x180013e4e  jz      short loc_180013EA5
0x180013e50  lea     r8, [rsp+880h+var_830]
0x180013e55  mov     rdx, r13
0x180013e58  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013e5f  call    McTemplateU0z_EventWriteTransfer
0x180013e64  test    cs:byte_18004CF34, r12b
0x180013e6b  jz      short loc_180013EA5
0x180013e6d  xor     eax, eax
0x180013e6f  lea     rdx, aAuthattributeG; "AuthAttribute GraceTimeout   = %d"
0x180013e76  mov     r8d, r14d
0x180013e79  mov     word ptr [rsp+880h+var_830], ax
0x180013e7e  lea     rcx, [rsp+880h+var_830]
0x180013e83  call    FormatRRASErrorString
0x180013e88  test    cs:byte_18004CF34, r12b
0x180013e8f  jz      short loc_180013EA5
0x180013e91  lea     r8, [rsp+880h+var_830]
0x180013e96  mov     rdx, r13
0x180013e99  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013ea0  call    McTemplateU0z_EventWriteTransfer
0x180013ea5  test    r14d, r14d
0x180013ea8  jz      short loc_180013EBB
0x180013eaa  mov     eax, [rsi+50h]
0x180013ead  test    eax, eax
0x180013eaf  jz      short loc_180013EBB
0x180013eb1  cmp     r14d, eax
0x180013eb4  jbe     short loc_180013ED0
0x180013eb6  mov     r14d, eax
0x180013eb9  jmp     short loc_180013ED0
0x180013ebb  cmp     dword ptr [rsi+50h], 0
0x180013ebf  jz      short loc_180013EC7
0x180013ec1  mov     r14d, [rsi+50h]
0x180013ec5  jmp     short loc_180013ED0
0x180013ec7  test    r14d, r14d
0x180013eca  jz      loc_180013F68
0x180013ed0  cmp     [rsi+54h], r14d
0x180013ed4  jnz     short loc_180013EE6
0x180013ed6  mov     rcx, [rsi+8]
0x180013eda  mov     eax, [rcx+50h]
0x180013edd  cmp     [rcx+54h], eax
0x180013ee0  jz      loc_180013F68
0x180013ee6  test    cs:byte_18004CF34, r12b
0x180013eed  jz      short loc_180013F27
0x180013eef  xor     eax, eax
0x180013ef1  lea     rdx, aSettingSession; "Setting SessionTimeout to %d"
0x180013ef8  mov     r8d, r14d
0x180013efb  mov     word ptr [rsp+880h+var_830], ax
0x180013f00  lea     rcx, [rsp+880h+var_830]
0x180013f05  call    FormatRRASErrorString
0x180013f0a  test    cs:byte_18004CF34, r12b
0x180013f11  jz      short loc_180013F27
0x180013f13  lea     r8, [rsp+880h+var_830]
0x180013f18  mov     rdx, r13
0x180013f1b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013f22  call    McTemplateU0z_EventWriteTransfer
0x180013f27  mov     ecx, [rsi+40h]
0x180013f2a  xor     r9d, r9d
0x180013f2d  xor     r8d, r8d
0x180013f30  mov     [rsp+880h+var_860], 4
0x180013f38  xor     edx, edx
0x180013f3a  call    RemoveFromTimerQ
0x180013f3f  mov     rdx, [rsi+10h]
0x180013f43  xor     r9d, r9d
0x180013f46  mov     ecx, [rsi+40h]
0x180013f49  xor     r8d, r8d
0x180013f4c  mov     [rsp+880h+var_850], r14d
0x180013f51  mov     [rsp+880h+var_858], 4
0x180013f59  mov     [rsp+880h+var_860], 0
0x180013f61  call    InsertInTimerQ
0x180013f66  jmp     short loc_180013F87
0x180013f68  test    cs:byte_18004CF34, r12b
0x180013f6f  jz      short loc_180013F87
0x180013f71  lea     r8, aNotSettingSess; "Not Setting SessionTimeout"
0x180013f78  mov     rdx, r13
0x180013f7b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013f82  call    McTemplateU0z_EventWriteTransfer
0x180013f87  test    byte ptr [rsi+38h], 4
0x180013f8b  jz      short loc_180013F9E
0x180013f8d  mov     rax, [rsi+8]
0x180013f91  cmp     dword ptr [rax+528h], 2
0x180013f98  jz      loc_180014024
0x180013f9e  mov     r9d, [rsi+58h]
0x180013fa2  test    r9d, r9d
0x180013fa5  jz      short loc_180014024
0x180013fa7  test    cs:byte_18004CF34, r12b
0x180013fae  jz      short loc_180013FE9
0x180013fb0  mov     r8, [rsi+10h]
0x180013fb4  lea     rdx, aInsertingAutod; "Inserting autodisconnect in timer q for"...
0x180013fbb  xor     eax, eax
0x180013fbd  lea     rcx, [rsp+880h+var_830]
0x180013fc2  mov     word ptr [rsp+880h+var_830], ax
0x180013fc7  call    FormatRRASErrorString
0x180013fcc  test    cs:byte_18004CF34, r12b
0x180013fd3  jz      short loc_180013FE9
0x180013fd5  lea     r8, [rsp+880h+var_830]
0x180013fda  mov     rdx, r13
0x180013fdd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013fe4  call    McTemplateU0z_EventWriteTransfer
0x180013fe9  mov     ecx, [rsi+40h]
0x180013fec  xor     r9d, r9d
0x180013fef  xor     r8d, r8d
0x180013ff2  mov     [rsp+880h+var_860], r12d
0x180013ff7  xor     edx, edx
0x180013ff9  call    RemoveFromTimerQ
0x180013ffe  mov     eax, [rsi+58h]
0x180014001  xor     r9d, r9d
0x180014004  mov     rdx, [rsi+10h]
0x180014008  xor     r8d, r8d
0x18001400b  mov     ecx, [rsi+40h]
0x18001400e  mov     [rsp+880h+var_850], eax
0x180014012  mov     [rsp+880h+var_858], r12d
0x180014017  mov     [rsp+880h+var_860], 0
0x18001401f  call    InsertInTimerQ
0x180014024  mov     rcx, [rbp+780h+var_30]
0x18001402b  xor     rcx, rsp; StackCookie
0x18001402e  call    __security_check_cookie
0x180014033  lea     r11, [rsp+880h+var_20]
0x18001403b  mov     rbx, [r11+38h]
0x18001403f  mov     rsi, [r11+40h]
0x180014043  mov     rsp, r11
0x180014046  pop     r14
0x180014048  pop     r13
0x18001404a  pop     r12
0x18001404c  pop     rdi
0x18001404d  pop     rbp
0x18001404e  retn
```
