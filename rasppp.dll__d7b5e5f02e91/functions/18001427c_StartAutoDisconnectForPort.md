# StartAutoDisconnectForPort

- ea: `0x18001427c`
- end: `0x18001471e`
- name: `StartAutoDisconnectForPort`
- size: `1186`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e7a4`
- `0x18000ecac`
- `0x180013c48`
- `0x180015a80`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x18000f780`
- `0x18000f984`
- `0x18001427c`
- `0x18001ae70`
- `0x18001b424`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800144b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800144b7`

## pseudocode

```c
void __fastcall StartAutoDisconnectForPort(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  _DWORD *v4; // rdi
  _DWORD *VendorSpecific; // rax
  _DWORD *v6; // rcx
  __int64 v7; // r8
  _DWORD *v8; // rax
  __int64 v9; // rcx
  int v10; // edi
  _DWORD *v11; // rax
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
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 72LL) = *(unsigned __int8 *)(*((_QWORD *)VendorSpecific + 1) + 9LL)
                                                + (*(unsigned __int8 *)(*((_QWORD *)VendorSpecific + 1) + 6LL) << 24)
                                                + (*(unsigned __int8 *)(*((_QWORD *)VendorSpecific + 1) + 8LL) << 8)
                                                + (*(unsigned __int8 *)(*((_QWORD *)VendorSpecific + 1) + 7LL) << 16);
        *(_DWORD *)(*(_QWORD *)(a1 + 8) + 52LL) |= 0x4000u;
      }
    }
    v6 = *(_DWORD **)(a1 + 8);
    if ( (v6[13] & 0x4000) != 0 && (v6[19] != v6[18] || v6[21] != v6[20]) )
    {
      RemoveFromTimerQ(*(_DWORD *)(a1 + 64), 0, 0, 0, 4);
      InsertInTimerQ(*(_DWORD *)(a1 + 64), *(_QWORD *)(a1 + 16), 0, 0, 0, 4, *(_DWORD *)(*(_QWORD *)(a1 + 8) + 72LL));
      if ( (byte_18004DF34 & 1) != 0 )
      {
        v7 = *(_QWORD *)(a1 + 8);
        LOWORD(v20) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v20,
          L"AuthAttribute Quarantine Session Timeout = %d",
          *(unsigned int *)(v7 + 72));
        if ( (byte_18004DF34 & 1) != 0 )
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
      v10 = v8[2];
      *(_DWORD *)(a1 + 80) = v10;
    }
    else
    {
      *(_DWORD *)(a1 + 80) = dword_18004DA10;
      v10 = dword_18004DA10;
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
      v13 = (unsigned __int8 *)*((_QWORD *)v11 + 1);
      SystemTimeAsFileTime = 0;
      v14 = 10000000 * (v13[9] + (v13[6] << 24) + (v13[8] << 8) + (v13[7] << 16) - 1240428288);
      v15 = (10000000 * ((unsigned __int64)(v13[9] + (v13[6] << 24) + (v13[8] << 8) + (v13[7] << 16)) + 0x2B6109100LL)) >> 32;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( __PAIR64__(v15, v14) > *(_QWORD *)&SystemTimeAsFileTime )
        v12 = (__PAIR64__(v15, v14) - *(_QWORD *)&SystemTimeAsFileTime) / 0x989680;
    }
    if ( (byte_18004DF34 & 1) != 0 )
    {
      v16 = *(unsigned int *)(a1 + 80);
      LOWORD(v20) = 0;
      FormatRRASErrorString((wchar_t *)&v20, L"AuthAttribute SessionTimeout = %d", v16);
      if ( (byte_18004DF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
          (const wchar_t *)&v20);
        if ( (byte_18004DF34 & 1) != 0 )
        {
          LOWORD(v20) = 0;
          FormatRRASErrorString((wchar_t *)&v20, L"AuthAttribute GraceTimeout   = %d", (unsigned int)v12);
          if ( (byte_18004DF34 & 1) != 0 )
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
      if ( (byte_18004DF34 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasPppTraceInfo,
          L"Not Setting SessionTimeout");
      goto LABEL_42;
    }
    if ( *(_DWORD *)(a1 + 84) != (_DWORD)v12
      || *(_DWORD *)(*(_QWORD *)(a1 + 8) + 84LL) != *(_DWORD *)(*(_QWORD *)(a1 + 8) + 80LL) )
    {
      if ( (byte_18004DF34 & 1) != 0 )
      {
        LOWORD(v20) = 0;
        FormatRRASErrorString((wchar_t *)&v20, L"Setting SessionTimeout to %d", (unsigned int)v12);
        if ( (byte_18004DF34 & 1) != 0 )
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
    if ( (byte_18004DF34 & 1) != 0 )
    {
      v18 = *(_QWORD *)(a1 + 16);
      LOWORD(v20) = 0;
      FormatRRASErrorString((wchar_t *)&v20, L"Inserting autodisconnect in timer q for port=%d, sec=%d", v18);
      if ( (byte_18004DF34 & 1) != 0 )
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
0x18001427c  mov     [rsp-8+arg_8], rbx
0x180014281  mov     [rsp-8+arg_10], rsi
0x180014286  push    rbp
0x180014287  push    rdi
0x180014288  push    r12
0x18001428a  push    r13
0x18001428c  push    r14
0x18001428e  lea     rbp, [rsp-760h]
0x180014296  sub     rsp, 860h
0x18001429d  mov     rax, cs:__security_cookie
0x1800142a4  xor     rax, rsp
0x1800142a7  mov     [rbp+780h+var_30], rax
0x1800142ae  mov     rsi, rcx
0x1800142b1  xor     eax, eax
0x1800142b3  lea     rcx, [rsp+880h+var_82C]; void *
0x1800142b8  mov     [rsp+880h+var_830], eax
0x1800142bc  xor     edx, edx; Val
0x1800142be  mov     r8d, 7FCh; Size
0x1800142c4  call    memset_0
0x1800142c9  test    byte ptr [rsi+38h], 4
0x1800142cd  lea     r13, RasPppTraceInfo
0x1800142d4  mov     r12d, 1
0x1800142da  jz      loc_18001466C
0x1800142e0  mov     rbx, [rsi+0A8h]
0x1800142e7  test    rbx, rbx
0x1800142ea  jnz     short loc_1800142F3
0x1800142ec  mov     rbx, [rsi+0A0h]
0x1800142f3  mov     rdi, [rsi+8]
0x1800142f7  mov     r14d, 4000h
0x1800142fd  cmp     dword ptr [rdi+528h], 2
0x180014304  jz      short loc_180014350
0x180014306  mov     r8, rbx
0x180014309  mov     edx, 25h ; '%'
0x18001430e  call    RasAuthAttributeGetVendorSpecific
0x180014313  test    rax, rax
0x180014316  jz      short loc_180014350
0x180014318  mov     ecx, [rdi+48h]
0x18001431b  mov     [rdi+4Ch], ecx
0x18001431e  mov     rcx, [rax+8]
0x180014322  movzx   eax, byte ptr [rcx+8]
0x180014326  movzx   edx, byte ptr [rcx+7]
0x18001432a  shl     eax, 8
0x18001432d  shl     edx, 10h
0x180014330  add     edx, eax
0x180014332  movzx   eax, byte ptr [rcx+6]
0x180014336  shl     eax, 18h
0x180014339  add     edx, eax
0x18001433b  movzx   eax, byte ptr [rcx+9]
0x18001433f  add     edx, eax
0x180014341  mov     rax, [rsi+8]
0x180014345  mov     [rax+48h], edx
0x180014348  mov     rax, [rsi+8]
0x18001434c  or      [rax+34h], r14d
0x180014350  mov     rcx, [rsi+8]
0x180014354  test    [rcx+34h], r14d
0x180014358  jz      loc_1800143FD
0x18001435e  mov     eax, [rcx+48h]
0x180014361  cmp     [rcx+4Ch], eax
0x180014364  jnz     short loc_180014372
0x180014366  mov     eax, [rcx+50h]
0x180014369  cmp     [rcx+54h], eax
0x18001436c  jz      loc_1800143FD
0x180014372  mov     ecx, [rsi+40h]
0x180014375  xor     r9d, r9d
0x180014378  xor     r8d, r8d
0x18001437b  mov     [rsp+880h+var_860], 4
0x180014383  xor     edx, edx
0x180014385  call    RemoveFromTimerQ
0x18001438a  mov     rax, [rsi+8]
0x18001438e  xor     r9d, r9d
0x180014391  mov     rdx, [rsi+10h]
0x180014395  xor     r8d, r8d
0x180014398  mov     ecx, [rax+48h]
0x18001439b  mov     [rsp+880h+var_850], ecx
0x18001439f  mov     ecx, [rsi+40h]
0x1800143a2  mov     [rsp+880h+var_858], 4
0x1800143aa  mov     [rsp+880h+var_860], 0
0x1800143b2  call    InsertInTimerQ
0x1800143b7  test    cs:byte_18004DF34, r12b
0x1800143be  jz      short loc_1800143FD
0x1800143c0  mov     r8, [rsi+8]
0x1800143c4  lea     rdx, aAuthattributeQ; "AuthAttribute Quarantine Session Timeou"...
0x1800143cb  xor     eax, eax
0x1800143cd  lea     rcx, [rsp+880h+var_830]
0x1800143d2  mov     word ptr [rsp+880h+var_830], ax
0x1800143d7  mov     r8d, [r8+48h]
0x1800143db  call    FormatRRASErrorString
0x1800143e0  test    cs:byte_18004DF34, r12b
0x1800143e7  jz      short loc_1800143FD
0x1800143e9  lea     r8, [rsp+880h+var_830]
0x1800143ee  mov     rdx, r13
0x1800143f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800143f8  call    McTemplateU0z_EventWriteTransfer
0x1800143fd  mov     rdx, rbx
0x180014400  mov     ecx, 1Bh
0x180014405  call    RasAuthAttributeGet
0x18001440a  mov     ecx, [rsi+50h]
0x18001440d  mov     [rsi+54h], ecx
0x180014410  test    rax, rax
0x180014413  jz      short loc_18001441D
0x180014415  mov     edi, [rax+8]
0x180014418  mov     [rsi+50h], edi
0x18001441b  jmp     short loc_18001442C
0x18001441d  mov     eax, cs:dword_18004DA10
0x180014423  mov     [rsi+50h], eax
0x180014426  mov     edi, cs:dword_18004DA10
0x18001442c  mov     r8, rbx
0x18001442f  mov     edx, 2Eh ; '.'
0x180014434  call    RasAuthAttributeGetVendorSpecific
0x180014439  test    edi, edi
0x18001443b  jnz     short loc_180014446
0x18001443d  test    rax, rax
0x180014440  jz      loc_180014655
0x180014446  mov     rcx, [rsi+8]
0x18001444a  test    [rcx+34h], r14d
0x18001444e  jnz     loc_180014655
0x180014454  xor     r14d, r14d
0x180014457  test    rax, rax
0x18001445a  jz      loc_1800144F0
0x180014460  mov     rcx, [rax+8]
0x180014464  mov     qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime], r14
0x180014469  mov     dword ptr [rsp+880h+var_840+4], r14d
0x18001446e  movzx   edx, byte ptr [rcx+7]
0x180014472  movzx   eax, byte ptr [rcx+8]
0x180014476  shl     eax, 8
0x180014479  shl     edx, 10h
0x18001447c  add     edx, eax
0x18001447e  movzx   eax, byte ptr [rcx+6]
0x180014482  shl     eax, 18h
0x180014485  add     edx, eax
0x180014487  movzx   eax, byte ptr [rcx+9]
0x18001448b  add     edx, eax
0x18001448d  mov     rcx, 2B6109100h
0x180014497  mov     dword ptr [rsp+880h+var_840], edx
0x18001449b  add     rcx, [rsp+880h+var_840]
0x1800144a0  imul    rdi, rcx, 989680h
0x1800144a7  lea     rcx, [rsp+880h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800144ac  mov     [rsp+880h+var_840], rdi
0x1800144b1  mov     ebx, edi
0x1800144b3  shr     rdi, 20h
0x1800144b7  call    cs:__imp_GetSystemTimeAsFileTime
0x1800144be  nop     dword ptr [rax+rax+00h]
0x1800144c3  mov     dword ptr [rsp+880h+var_840], ebx
0x1800144c7  mov     dword ptr [rsp+880h+var_840+4], edi
0x1800144cb  mov     rcx, [rsp+880h+var_840]
0x1800144d0  cmp     rcx, qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime]
0x1800144d5  jbe     short loc_1800144F0
0x1800144d7  sub     rcx, qword ptr [rsp+880h+SystemTimeAsFileTime.dwLowDateTime]
0x1800144dc  mov     rax, 0D6BF94D5E57A42BDh
0x1800144e6  mul     rcx
0x1800144e9  mov     r14, rdx
0x1800144ec  shr     r14, 17h
0x1800144f0  test    cs:byte_18004DF34, r12b
0x1800144f7  jz      short loc_180014573
0x1800144f9  mov     r8d, [rsi+50h]
0x1800144fd  lea     rdx, aAuthattributeS; "AuthAttribute SessionTimeout = %d"
0x180014504  xor     eax, eax
0x180014506  lea     rcx, [rsp+880h+var_830]
0x18001450b  mov     word ptr [rsp+880h+var_830], ax
0x180014510  call    FormatRRASErrorString
0x180014515  test    cs:byte_18004DF34, r12b
0x18001451c  jz      short loc_180014573
0x18001451e  lea     r8, [rsp+880h+var_830]
0x180014523  mov     rdx, r13
0x180014526  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001452d  call    McTemplateU0z_EventWriteTransfer
0x180014532  test    cs:byte_18004DF34, r12b
0x180014539  jz      short loc_180014573
0x18001453b  xor     eax, eax
0x18001453d  lea     rdx, aAuthattributeG; "AuthAttribute GraceTimeout   = %d"
0x180014544  mov     r8d, r14d
0x180014547  mov     word ptr [rsp+880h+var_830], ax
0x18001454c  lea     rcx, [rsp+880h+var_830]
0x180014551  call    FormatRRASErrorString
0x180014556  test    cs:byte_18004DF34, r12b
0x18001455d  jz      short loc_180014573
0x18001455f  lea     r8, [rsp+880h+var_830]
0x180014564  mov     rdx, r13
0x180014567  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001456e  call    McTemplateU0z_EventWriteTransfer
0x180014573  test    r14d, r14d
0x180014576  jz      short loc_180014589
0x180014578  mov     eax, [rsi+50h]
0x18001457b  test    eax, eax
0x18001457d  jz      short loc_180014589
0x18001457f  cmp     r14d, eax
0x180014582  jbe     short loc_18001459E
0x180014584  mov     r14d, eax
0x180014587  jmp     short loc_18001459E
0x180014589  cmp     dword ptr [rsi+50h], 0
0x18001458d  jz      short loc_180014595
0x18001458f  mov     r14d, [rsi+50h]
0x180014593  jmp     short loc_18001459E
0x180014595  test    r14d, r14d
0x180014598  jz      loc_180014636
0x18001459e  cmp     [rsi+54h], r14d
0x1800145a2  jnz     short loc_1800145B4
0x1800145a4  mov     rcx, [rsi+8]
0x1800145a8  mov     eax, [rcx+50h]
0x1800145ab  cmp     [rcx+54h], eax
0x1800145ae  jz      loc_180014636
0x1800145b4  test    cs:byte_18004DF34, r12b
0x1800145bb  jz      short loc_1800145F5
0x1800145bd  xor     eax, eax
0x1800145bf  lea     rdx, aSettingSession; "Setting SessionTimeout to %d"
0x1800145c6  mov     r8d, r14d
0x1800145c9  mov     word ptr [rsp+880h+var_830], ax
0x1800145ce  lea     rcx, [rsp+880h+var_830]
0x1800145d3  call    FormatRRASErrorString
0x1800145d8  test    cs:byte_18004DF34, r12b
0x1800145df  jz      short loc_1800145F5
0x1800145e1  lea     r8, [rsp+880h+var_830]
0x1800145e6  mov     rdx, r13
0x1800145e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800145f0  call    McTemplateU0z_EventWriteTransfer
0x1800145f5  mov     ecx, [rsi+40h]
0x1800145f8  xor     r9d, r9d
0x1800145fb  xor     r8d, r8d
0x1800145fe  mov     [rsp+880h+var_860], 4
0x180014606  xor     edx, edx
0x180014608  call    RemoveFromTimerQ
0x18001460d  mov     rdx, [rsi+10h]
0x180014611  xor     r9d, r9d
0x180014614  mov     ecx, [rsi+40h]
0x180014617  xor     r8d, r8d
0x18001461a  mov     [rsp+880h+var_850], r14d
0x18001461f  mov     [rsp+880h+var_858], 4
0x180014627  mov     [rsp+880h+var_860], 0
0x18001462f  call    InsertInTimerQ
0x180014634  jmp     short loc_180014655
0x180014636  test    cs:byte_18004DF34, r12b
0x18001463d  jz      short loc_180014655
0x18001463f  lea     r8, aNotSettingSess; "Not Setting SessionTimeout"
0x180014646  mov     rdx, r13
0x180014649  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180014650  call    McTemplateU0z_EventWriteTransfer
0x180014655  test    byte ptr [rsi+38h], 4
0x180014659  jz      short loc_18001466C
0x18001465b  mov     rax, [rsi+8]
0x18001465f  cmp     dword ptr [rax+528h], 2
0x180014666  jz      loc_1800146F2
0x18001466c  mov     r9d, [rsi+58h]
0x180014670  test    r9d, r9d
0x180014673  jz      short loc_1800146F2
0x180014675  test    cs:byte_18004DF34, r12b
0x18001467c  jz      short loc_1800146B7
0x18001467e  mov     r8, [rsi+10h]
0x180014682  lea     rdx, aInsertingAutod; "Inserting autodisconnect in timer q for"...
0x180014689  xor     eax, eax
0x18001468b  lea     rcx, [rsp+880h+var_830]
0x180014690  mov     word ptr [rsp+880h+var_830], ax
0x180014695  call    FormatRRASErrorString
0x18001469a  test    cs:byte_18004DF34, r12b
0x1800146a1  jz      short loc_1800146B7
0x1800146a3  lea     r8, [rsp+880h+var_830]
0x1800146a8  mov     rdx, r13
0x1800146ab  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800146b2  call    McTemplateU0z_EventWriteTransfer
0x1800146b7  mov     ecx, [rsi+40h]
0x1800146ba  xor     r9d, r9d
0x1800146bd  xor     r8d, r8d
0x1800146c0  mov     [rsp+880h+var_860], r12d
0x1800146c5  xor     edx, edx
0x1800146c7  call    RemoveFromTimerQ
0x1800146cc  mov     eax, [rsi+58h]
0x1800146cf  xor     r9d, r9d
0x1800146d2  mov     rdx, [rsi+10h]
0x1800146d6  xor     r8d, r8d
0x1800146d9  mov     ecx, [rsi+40h]
0x1800146dc  mov     [rsp+880h+var_850], eax
0x1800146e0  mov     [rsp+880h+var_858], r12d
0x1800146e5  mov     [rsp+880h+var_860], 0
0x1800146ed  call    InsertInTimerQ
0x1800146f2  mov     rcx, [rbp+780h+var_30]
0x1800146f9  xor     rcx, rsp; StackCookie
0x1800146fc  call    __security_check_cookie
0x180014701  lea     r11, [rsp+880h+var_20]
0x180014709  mov     rbx, [r11+38h]
0x18001470d  mov     rsi, [r11+40h]
0x180014711  mov     rsp, r11
0x180014714  pop     r14
0x180014716  pop     r13
0x180014718  pop     r12
0x18001471a  pop     rdi
0x18001471b  pop     rbp
0x18001471c  retn
```
