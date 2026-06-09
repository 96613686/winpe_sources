# StartDocWImpl(HDC__ *,_DOCINFOW const *)

- ea: `0x1800983f0`
- end: `0x180098da4`
- name: `?StartDocWImpl@@YAHPEAUHDC__@@PEBU_DOCINFOW@@@Z`
- size: `2484`
- prototype: `__int64 __fastcall(HDC, const struct _DOCINFOW *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002ada0`
- `0x18002bea8`
- `0x18003e758`
- `0x18003e8c0`
- `0x18003e8e0`
- `0x18003e930`
- `0x18003eb04`
- `0x18003fa88`
- `0x180051a78`
- `0x1800718f4`
- `0x1800756cc`
- `0x18007ee20`
- `0x18007f1bc`
- `0x18007f800`
- `0x1800983f0`
- `0x180098dc4`
- `0x1800a6138`
- `0x1800a68d4`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098cf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180098cf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ba7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098974`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098974`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009849f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009849f`
- `GDI32!AbortDoc` at `0x180098d75`
- `GDI32!AbortDoc` at `0x180098d75`
- `GDI32!ExtEscape` at `0x1800988a6`
- `GDI32!ExtEscape` at `0x1800988a6`
- `GDI32!GdiGetEntry` at `0x1800984d8`
- `GDI32!GdiGetEntry` at `0x180098667`
- `GDI32!GdiGetEntry` at `0x18009872d`
- `GDI32!GdiGetEntry` at `0x180098be4`
- `GDI32!GdiGetEntry` at `0x1800984d8`
- `GDI32!GdiGetEntry` at `0x180098667`
- `GDI32!GdiGetEntry` at `0x18009872d`
- `GDI32!GdiGetEntry` at `0x180098be4`
- `GDI32!gW32PID` at `0x18009851d`
- `GDI32!gW32PID` at `0x1800986ac`
- `GDI32!gW32PID` at `0x180098772`
- `GDI32!gW32PID` at `0x180098c1d`
- `GDI32!gCookie` at `0x18009853a`
- `GDI32!gCookie` at `0x1800986c9`
- `GDI32!gCookie` at `0x18009878f`
- `GDI32!gCookie` at `0x180098c32`
- `GDI32!gMaxGdiHandleCount` at `0x1800984b5`
- `GDI32!gMaxGdiHandleCount` at `0x180098644`
- `GDI32!gMaxGdiHandleCount` at `0x18009870a`
- `GDI32!gMaxGdiHandleCount` at `0x180098bbf`
- `GDI32!pldcGet` at `0x180098477`
- `GDI32!pldcGet` at `0x180098477`
- `GDI32!GdiSetLastError` at `0x180098d93`
- `GDI32!GdiSetLastError` at `0x180098d93`
- `ntdll!RtlDecodePointer` at `0x18009860f`
- `ntdll!RtlDecodePointer` at `0x180098947`
- `ntdll!RtlDecodePointer` at `0x18009860f`
- `ntdll!RtlDecodePointer` at `0x180098947`
- `USER32!GetAppCompatFlags` at `0x180098871`
- `USER32!GetAppCompatFlags` at `0x180098871`
- `win32u!NtGdiStartDoc` at `0x180098caf`
- `win32u!NtGdiStartDoc` at `0x180098caf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StartDocWImpl(HDC a1, const struct _DOCINFOW *a2)
{
  void *v4; // r13
  int v5; // r15d
  int v6; // ebx
  const wchar_t *v7; // r12
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  const wchar_t *v13; // rax
  const WCHAR *lpszOutput; // rax
  int v15; // r14d
  __int64 (__fastcall *v16)(_QWORD, struct _DOCINFOW *); // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int v19; // eax
  const WCHAR *v20; // rax
  unsigned int v21; // eax
  __int64 (__fastcall *v22)(_QWORD, __int64, unsigned __int8 *); // rax
  int started; // r14d
  int v24; // edx
  unsigned int v25; // r15d
  __int64 (__fastcall *v26)(_QWORD, _WORD *); // r14
  __int64 v27; // rax
  size_t v28; // r8
  int v29; // eax
  const wchar_t *v30; // rcx
  unsigned int v31; // r8d
  unsigned int v32; // eax
  __int64 v33; // rdx
  int v35; // eax
  CHAR InData[8]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned __int8 v39[16]; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+68h] [rbp-98h]
  struct _DOCINFOW *v42; // [rsp+70h] [rbp-90h] BYREF
  int v43; // [rsp+78h] [rbp-88h] BYREF
  int v44; // [rsp+80h] [rbp-80h] BYREF
  struct _DOCINFOW v45; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v46[16]; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v47[80]; // [rsp+C0h] [rbp-40h] BYREF

  v37 = -1;
  memset(&v45, 0, sizeof(v45));
  v4 = 0;
  v5 = 0;
  v38 = 0;
  v6 = 0;
  v43 = 0;
  v7 = &Default;
  if ( ((unsigned int)a1 & 0x7F0000) == 0x10000 || ((unsigned int)a1 & 0x7F0000) == 0x660000 )
  {
LABEL_88:
    v32 = HANDLE_TO_INDEX(a1);
    if ( v32 < gMaxGdiHandleCount )
    {
      *(_OWORD *)v39 = 0;
      v40 = 0;
      if ( (int)GdiGetEntry(v32, v39) >= 0
        && v39[14] == 1
        && *(_WORD *)&v39[12] == WORD1(a1)
        && (*(_DWORD *)&v39[8] & 0xFFFFFFFE) == gW32PID )
      {
        if ( v40 )
        {
          v33 = gCookie ^ __ROR8__(v40, 64 - (gCookie & 0x3Fu));
          if ( v33 )
            LogStartDocTelemetry((_DWORD)a1, v33, v37, v6, (__int64)v7);
        }
      }
    }
    return v37;
  }
  v44 = 0;
  v8 = pldcGet(a1);
  v9 = v8;
  if ( !v8 )
  {
    GdiSetLastError(6);
    return v37;
  }
  v10 = *(_DWORD *)(v8 + 8);
  if ( (v10 & 0x1000000) != 0 )
  {
    SetLastError(6u);
    v11 = HANDLE_TO_INDEX(a1);
    if ( v11 < gMaxGdiHandleCount )
    {
      *(_OWORD *)v39 = 0;
      v40 = 0;
      if ( (int)GdiGetEntry(v11, v39) >= 0
        && v39[14] == 1
        && *(_WORD *)&v39[12] == WORD1(a1)
        && (*(_DWORD *)&v39[8] & 0xFFFFFFFE) == gW32PID )
      {
        if ( v40 )
        {
          v12 = gCookie ^ __ROR8__(v40, 64 - (gCookie & 0x3Fu));
          if ( v12 )
          {
            v13 = L"StartDoc On Info DC";
LABEL_13:
            LogStartDocTelemetry((_DWORD)a1, v12, v37, 0, (__int64)v13);
            return v37;
          }
        }
      }
    }
    return v37;
  }
  *(_DWORD *)(v9 + 8) = v10 & 0xFFFEFFFF;
  if ( a2 )
  {
    v45 = *a2;
    if ( _mm_cvtsi128_si32(*(__m128i *)&v45.cbSize) != 24 )
    {
      v45.cbSize = 40;
      v45.lpszDatatype = 0;
      v45.fwType = 0;
      TryReadDocInfo(a2, &v45, &v38);
      v5 = v38;
    }
    lpszOutput = v45.lpszOutput;
    v15 = 0;
  }
  else
  {
    v45.cbSize = 40;
    v15 = 0;
    lpszOutput = 0;
    memset(&v45.lpszDocName, 0, 28);
  }
  if ( !lpszOutput )
  {
    if ( *(_QWORD *)(v9 + 24) )
      lpszOutput = *(const WCHAR **)(v9 + 24);
    v45.lpszOutput = lpszOutput;
  }
  if ( !*(_QWORD *)(v9 + 48) )
  {
LABEL_45:
    v38 = 0;
    if ( *(_QWORD *)(v9 + 48) )
    {
      v42 = &v45;
      LdcGetUmpd(InData, v9);
      v21 = DocumentEventEx((struct UmpdPtr *)InData, *(void **)(v9 + 48), a1, 5, 8u, &v42, 0, 0);
      v37 = v21;
      if ( v21 == -1 )
      {
        v7 = L"Error from driver UI";
        UmpdPtr::reset((UmpdPtr *)InData, 0);
LABEL_81:
        v25 = v38;
        goto LABEL_82;
      }
      if ( v21 == -2 )
      {
        *(_DWORD *)(v9 + 8) |= 0x10000u;
        v7 = L"Cancelled from driver UI";
LABEL_85:
        UmpdPtr::reset((UmpdPtr *)InData, 0);
        if ( v4 )
          LocalFree(v4);
        v6 = v43;
        goto LABEL_88;
      }
      UmpdPtr::reset((UmpdPtr *)InData, 0);
    }
    LODWORD(v42) = 1;
    if ( (GetAppCompatFlags(0) & 0x4000000) != 0 )
    {
      *(_DWORD *)InData = 4115;
      if ( ExtEscape(a1, 8, 4, InData, 0, 0) )
        v5 = 1;
    }
    LdcGetUmpd(InData, v9);
    if ( !v5 && (unsigned int)GetDCDWord(a1, 0) && (unsigned int)RemoteRasterizerCompatible(*(_QWORD *)(v9 + 48))
      || (unsigned __int8)UmpdPtr::operator bool(InData)
      && (UmpdPtr::assert((UmpdPtr *)InData), (*(_BYTE *)(*(_QWORD *)InData + 32LL) & 2) != 0) )
    {
      v41 = 1;
      *(_QWORD *)v39 = v45.lpszDocName;
      *(_QWORD *)&v39[8] = v45.lpszOutput;
      v40 = L"NT EMF 1.008";
      v22 = (__int64 (__fastcall *)(_QWORD, __int64, unsigned __int8 *))RtlDecodePointer(fpStartDocPrinterW);
      started = v22(*(_QWORD *)(v9 + 48), 3, v39);
      v43 = started;
      if ( started > 0 )
      {
        if ( !(unsigned int)MFP_StartDocW(a1, &v45, 0) )
        {
          v25 = 1;
          v7 = L"error calling MFP_StartDocW";
          UmpdPtr::reset((UmpdPtr *)InData, 0);
          v15 = (int)v42;
LABEL_82:
          v37 = -1;
          LdcGetUmpd(InData, v9);
          if ( v15 && (unsigned __int8)UmpdPtr::operator bool(InData) )
            AbortPrinterEx(v9, v25);
          goto LABEL_85;
        }
        v37 = started;
        UmpdPtr::reset((UmpdPtr *)InData, 0);
        goto LABEL_106;
      }
      if ( GetLastError() != 1804 )
      {
        v7 = L"StartDocPrinter failed w/ error other than INVALID_DATA_TYPE";
        UmpdPtr::reset((UmpdPtr *)InData, 0);
        v15 = v24;
        goto LABEL_81;
      }
    }
    else
    {
      started = v43;
    }
    UmpdPtr::reset((UmpdPtr *)InData, 0);
    LdcGetUmpd(InData, v9);
    if ( (unsigned __int8)UmpdPtr::operator bool(InData) )
    {
      *(_QWORD *)v39 = v45.lpszDocName;
      *(_QWORD *)&v39[8] = v45.lpszOutput;
      v40 = 0;
      UmpdPtr::assert((UmpdPtr *)InData);
      v26 = *(__int64 (__fastcall **)(_QWORD, _WORD *))(*(_QWORD *)InData + 584LL);
      if ( v26 )
      {
        v47[0] = 0;
        if ( v45.lpszDatatype )
        {
          v27 = -1;
          do
            ++v27;
          while ( v45.lpszDatatype[v27] );
          v28 = 2 * (int)v27 + 2;
          if ( v28 < 0xA0 )
            memcpy_0(v47, v45.lpszDatatype, v28);
        }
        v29 = v26(*(_QWORD *)(*(_QWORD *)(v9 + 80) + 8LL), v47);
        v30 = v47;
        if ( !v29 )
          v30 = v40;
        v40 = v30;
      }
      LdcGetUmpd(&v43, v9);
      UmpdPtr::operator=((UmpdPtr *)InData);
      UmpdPtr::reset((UmpdPtr *)&v43, 0);
      started = StartDocPrinterWEx((struct UmpdPtr *)InData, *(void **)(v9 + 48), v31, v39);
      v43 = started;
    }
    LdcGetUmpd(v46, v9);
    UmpdPtr::operator=((UmpdPtr *)InData);
    UmpdPtr::reset((UmpdPtr *)v46, 0);
    if ( (unsigned __int8)UmpdPtr::operator bool(InData) )
    {
      UmpdPtr::assert((UmpdPtr *)InData);
      if ( (*(_BYTE *)(*(_QWORD *)InData + 32LL) & 2) != 0 )
      {
        v7 = L"StartDocW failed because EMF failed and METAFILE_DRIVER is on";
        UmpdPtr::reset((UmpdPtr *)InData, 0);
LABEL_80:
        v15 = (int)v42;
        goto LABEL_81;
      }
    }
    UmpdPtr::reset((UmpdPtr *)InData, 0);
    *(_DWORD *)(v9 + 8) |= 0x40000u;
    v37 = NtGdiStartDoc(a1, &v45, &v44, (unsigned int)started);
    if ( !v37 )
      goto LABEL_80;
    if ( *(_QWORD *)(v9 + 32) )
    {
      vSAPCallback(v9);
      v35 = *(_DWORD *)(v9 + 8);
      if ( (v35 & 0x10000) != 0 )
      {
        v7 = L"Job Cancelled";
        goto LABEL_80;
      }
      *(_DWORD *)(v9 + 8) = v35 | 0x20;
      *(_DWORD *)(v9 + 40) = GetTickCount();
    }
    *(_DWORD *)(v9 + 8) |= 0x40u;
    if ( v44 )
    {
      if ( !(unsigned int)MFP_StartDocW(a1, 0, 1) )
        v37 = -1;
    }
    else
    {
      *(_DWORD *)(v9 + 8) |= 0x100u;
    }
LABEL_106:
    LdcGetUmpd(InData, v9);
    if ( (unsigned int)DocumentEventEx((struct UmpdPtr *)InData, *(void **)(v9 + 48), a1, 13, 4u, &v37, 0, 0) == -1 )
    {
      AbortDoc(a1);
      v37 = -1;
    }
    goto LABEL_85;
  }
  v16 = (__int64 (__fastcall *)(_QWORD, struct _DOCINFOW *))RtlDecodePointer(fpStartDocDlgW);
  v17 = v16(*(_QWORD *)(v9 + 48), &v45);
  v4 = (void *)v17;
  if ( v17 != -2 )
  {
    if ( v17 == -1 )
    {
      v19 = HANDLE_TO_INDEX(a1);
      if ( v19 < gMaxGdiHandleCount )
      {
        *(_OWORD *)v39 = 0;
        v40 = 0;
        if ( (int)GdiGetEntry(v19, v39) >= 0
          && v39[14] == 1
          && *(_WORD *)&v39[12] == WORD1(a1)
          && (*(_DWORD *)&v39[8] & 0xFFFFFFFE) == gW32PID )
        {
          if ( v40 )
          {
            v12 = gCookie ^ __ROR8__(v40, 64 - (gCookie & 0x3Fu));
            if ( v12 )
            {
              v13 = L"Error from StartDocDlgW";
              goto LABEL_13;
            }
          }
        }
      }
      return v37;
    }
    v20 = v45.lpszOutput;
    if ( v4 )
      v20 = (const WCHAR *)v4;
    v45.lpszOutput = v20;
    goto LABEL_45;
  }
  *(_DWORD *)(v9 + 8) |= 0x10000u;
  v18 = HANDLE_TO_INDEX(a1);
  if ( v18 < gMaxGdiHandleCount )
  {
    *(_OWORD *)v39 = 0;
    v40 = 0;
    if ( (int)GdiGetEntry(v18, v39) >= 0
      && v39[14] == 1
      && *(_WORD *)&v39[12] == WORD1(a1)
      && (*(_DWORD *)&v39[8] & 0xFFFFFFFE) == gW32PID )
    {
      if ( v40 )
      {
        v12 = gCookie ^ __ROR8__(v40, 64 - (gCookie & 0x3Fu));
        if ( v12 )
        {
          v13 = L"Canceled from StartDocDlgW";
          goto LABEL_13;
        }
      }
    }
  }
  return v37;
}

```

## disassembly

```asm
0x1800983f0  mov     [rsp-8+arg_10], rbx
0x1800983f5  push    rbp
0x1800983f6  push    rsi
0x1800983f7  push    rdi
0x1800983f8  push    r12
0x1800983fa  push    r13
0x1800983fc  push    r14
0x1800983fe  push    r15
0x180098400  lea     rbp, [rsp-70h]
0x180098405  sub     rsp, 170h
0x18009840c  mov     rax, cs:__security_cookie
0x180098413  xor     rax, rsp
0x180098416  mov     [rbp+0A0h+var_40], rax
0x18009841a  mov     r14, rdx
0x18009841d  mov     rdi, rcx
0x180098420  mov     [rsp+1A0h+var_158], 0FFFFFFFFh
0x180098428  xorps   xmm0, xmm0
0x18009842b  xor     eax, eax
0x18009842d  movups  xmmword ptr [rbp+0A0h+var_118.cbSize], xmm0
0x180098431  movups  xmmword ptr [rbp+0A0h+var_118.lpszOutput], xmm0
0x180098435  mov     qword ptr [rbp+0A0h+var_118.fwType], rax
0x180098439  xor     r13d, r13d
0x18009843c  mov     r15d, r13d
0x18009843f  mov     [rsp+1A0h+var_154], r13d
0x180098444  mov     ebx, r13d
0x180098447  mov     [rsp+1A0h+var_128], ebx
0x18009844b  lea     r12, Default
0x180098452  mov     eax, ecx
0x180098454  and     eax, 7F0000h
0x180098459  lea     esi, [r13+40h]
0x18009845d  cmp     eax, 10000h
0x180098462  jz      loc_180098BB7
0x180098468  cmp     eax, 660000h
0x18009846d  jz      loc_180098BB7
0x180098473  mov     [rbp+0A0h+var_120], r13d
0x180098477  call    cs:__imp_pldcGet
0x18009847e  nop     dword ptr [rax+rax+00h]
0x180098483  mov     rbx, rax
0x180098486  test    rax, rax
0x180098489  jz      loc_180098D8E
0x18009848f  mov     eax, [rax+8]
0x180098492  bt      eax, 18h
0x180098496  jnb     loc_18009856F
0x18009849c  lea     ecx, [rsi-3Ah]; dwErrCode
0x18009849f  call    cs:__imp_SetLastError
0x1800984a6  nop     dword ptr [rax+rax+00h]
0x1800984ab  mov     rcx, rdi
0x1800984ae  call    HANDLE_TO_INDEX
0x1800984b3  mov     ecx, eax
0x1800984b5  mov     rax, cs:__imp_gMaxGdiHandleCount
0x1800984bc  cmp     ecx, [rax]
0x1800984be  jnb     loc_180098C64
0x1800984c4  xorps   xmm0, xmm0
0x1800984c7  xor     eax, eax
0x1800984c9  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x1800984ce  mov     [rsp+1A0h+var_140], rax
0x1800984d3  lea     rdx, [rsp+1A0h+var_150]
0x1800984d8  call    cs:__imp_GdiGetEntry
0x1800984df  nop     dword ptr [rax+rax+00h]
0x1800984e4  test    eax, eax
0x1800984e6  js      loc_180098C64
0x1800984ec  cmp     [rsp+1A0h+var_150+0Eh], 1
0x1800984f1  jnz     loc_180098C64
0x1800984f7  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x1800984fc  shl     cx, 8
0x180098500  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x180098505  or      cx, ax
0x180098508  mov     eax, edi
0x18009850a  shr     eax, 10h
0x18009850d  cmp     cx, ax
0x180098510  jnz     loc_180098C64
0x180098516  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x18009851a  and     ecx, 0FFFFFFFEh
0x18009851d  mov     rax, cs:__imp_gW32PID
0x180098524  cmp     ecx, [rax]
0x180098526  jnz     loc_180098C64
0x18009852c  mov     rdx, [rsp+1A0h+var_140]
0x180098531  test    rdx, rdx
0x180098534  jz      loc_180098C64
0x18009853a  mov     rax, cs:__imp_gCookie
0x180098541  mov     r8, [rax]
0x180098544  mov     eax, r8d
0x180098547  and     eax, 3Fh
0x18009854a  sub     esi, eax
0x18009854c  mov     cl, sil
0x18009854f  ror     rdx, cl
0x180098552  xor     rdx, r8
0x180098555  jz      loc_180098C64
0x18009855b  lea     rax, aStartdocOnInfo; "StartDoc On Info DC"
0x180098562  mov     qword ptr [rsp+1A0h+cjOutput], rax
0x180098567  xor     r9d, r9d
0x18009856a  jmp     loc_180098C57
0x18009856f  btr     eax, 10h
0x180098573  mov     [rbx+8], eax
0x180098576  xor     ecx, ecx
0x180098578  test    r14, r14
0x18009857b  jz      short loc_1800985CF
0x18009857d  movups  xmm2, xmmword ptr [r14]
0x180098581  movups  xmmword ptr [rbp+0A0h+var_118.cbSize], xmm2
0x180098585  movups  xmm0, xmmword ptr [r14+10h]
0x18009858a  movups  xmmword ptr [rbp+0A0h+var_118.lpszOutput], xmm0
0x18009858e  movsd   xmm1, qword ptr [r14+20h]
0x180098594  movsd   qword ptr [rbp+0A0h+var_118.fwType], xmm1
0x180098599  movd    eax, xmm2
0x18009859d  cmp     eax, 18h
0x1800985a0  jz      short loc_1800985C6
0x1800985a2  mov     [rbp+0A0h+var_118.cbSize], 28h ; '('
0x1800985a9  mov     [rbp+0A0h+var_118.lpszDatatype], rcx
0x1800985ad  mov     [rbp+0A0h+var_118.fwType], ecx
0x1800985b0  lea     r8, [rsp+1A0h+var_154]; int *
0x1800985b5  lea     rdx, [rbp+0A0h+var_118]; struct _DOCINFOW *
0x1800985b9  mov     rcx, r14; struct _DOCINFOW *
0x1800985bc  call    ?TryReadDocInfo@@YAXPEBU_DOCINFOW@@AEAU1@AEAH@Z; TryReadDocInfo(_DOCINFOW const *,_DOCINFOW &,int &)
0x1800985c1  mov     r15d, [rsp+1A0h+var_154]
0x1800985c6  mov     rax, [rbp+0A0h+var_118.lpszOutput]
0x1800985ca  xor     r14d, r14d
0x1800985cd  jmp     short loc_1800985EC
0x1800985cf  mov     [rbp+0A0h+var_118.cbSize], 28h ; '('
0x1800985d6  xor     r14d, r14d
0x1800985d9  mov     [rbp+0A0h+var_118.lpszDatatype], r14
0x1800985dd  mov     eax, r14d
0x1800985e0  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x1800985e4  mov     [rbp+0A0h+var_118.lpszDocName], r14
0x1800985e8  mov     [rbp+0A0h+var_118.fwType], r14d
0x1800985ec  test    rax, rax
0x1800985ef  jnz     short loc_1800985FE
0x1800985f1  cmp     [rbx+18h], r14
0x1800985f5  cmovnz  rax, [rbx+18h]
0x1800985fa  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x1800985fe  cmp     [rbx+30h], r14
0x180098602  jz      loc_1800987CB
0x180098608  mov     rcx, cs:fpStartDocDlgW; Pointer
0x18009860f  call    cs:__imp_RtlDecodePointer
0x180098616  nop     dword ptr [rax+rax+00h]
0x18009861b  lea     rdx, [rbp+0A0h+var_118]
0x18009861f  mov     rcx, [rbx+30h]
0x180098623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098628  mov     r13, rax
0x18009862b  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x18009862f  jnz     loc_1800986F6
0x180098635  bts     dword ptr [rbx+8], 10h
0x18009863a  mov     rcx, rdi
0x18009863d  call    HANDLE_TO_INDEX
0x180098642  mov     ecx, eax
0x180098644  mov     rax, cs:__imp_gMaxGdiHandleCount
0x18009864b  cmp     ecx, [rax]
0x18009864d  jnb     loc_180098C64
0x180098653  xorps   xmm0, xmm0
0x180098656  xor     eax, eax
0x180098658  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x18009865d  mov     [rsp+1A0h+var_140], rax
0x180098662  lea     rdx, [rsp+1A0h+var_150]
0x180098667  call    cs:__imp_GdiGetEntry
0x18009866e  nop     dword ptr [rax+rax+00h]
0x180098673  test    eax, eax
0x180098675  js      loc_180098C64
0x18009867b  cmp     [rsp+1A0h+var_150+0Eh], 1
0x180098680  jnz     loc_180098C64
0x180098686  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x18009868b  shl     cx, 8
0x18009868f  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x180098694  or      cx, ax
0x180098697  mov     eax, edi
0x180098699  shr     eax, 10h
0x18009869c  cmp     cx, ax
0x18009869f  jnz     loc_180098C64
0x1800986a5  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x1800986a9  and     ecx, 0FFFFFFFEh
0x1800986ac  mov     rax, cs:__imp_gW32PID
0x1800986b3  cmp     ecx, [rax]
0x1800986b5  jnz     loc_180098C64
0x1800986bb  mov     rdx, [rsp+1A0h+var_140]
0x1800986c0  test    rdx, rdx
0x1800986c3  jz      loc_180098C64
0x1800986c9  mov     rax, cs:__imp_gCookie
0x1800986d0  mov     r8, [rax]
0x1800986d3  mov     eax, r8d
0x1800986d6  and     eax, 3Fh
0x1800986d9  sub     esi, eax
0x1800986db  mov     cl, sil
0x1800986de  ror     rdx, cl
0x1800986e1  xor     rdx, r8
0x1800986e4  jz      loc_180098C64
0x1800986ea  lea     rax, aCanceledFromSt; "Canceled from StartDocDlgW"
0x1800986f1  jmp     loc_180098562
0x1800986f6  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800986fa  jnz     loc_1800987BC
0x180098700  mov     rcx, rdi
0x180098703  call    HANDLE_TO_INDEX
0x180098708  mov     ecx, eax
0x18009870a  mov     rax, cs:__imp_gMaxGdiHandleCount
0x180098711  cmp     ecx, [rax]
0x180098713  jnb     loc_180098C64
0x180098719  xorps   xmm0, xmm0
0x18009871c  xor     eax, eax
0x18009871e  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x180098723  mov     [rsp+1A0h+var_140], rax
0x180098728  lea     rdx, [rsp+1A0h+var_150]
0x18009872d  call    cs:__imp_GdiGetEntry
0x180098734  nop     dword ptr [rax+rax+00h]
0x180098739  test    eax, eax
0x18009873b  js      loc_180098C64
0x180098741  cmp     [rsp+1A0h+var_150+0Eh], 1
0x180098746  jnz     loc_180098C64
0x18009874c  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x180098751  shl     cx, 8
0x180098755  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x18009875a  or      cx, ax
0x18009875d  mov     eax, edi
0x18009875f  shr     eax, 10h
0x180098762  cmp     cx, ax
0x180098765  jnz     loc_180098C64
0x18009876b  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x18009876f  and     ecx, 0FFFFFFFEh
0x180098772  mov     rax, cs:__imp_gW32PID
0x180098779  cmp     ecx, [rax]
0x18009877b  jnz     loc_180098C64
0x180098781  mov     rdx, [rsp+1A0h+var_140]
0x180098786  test    rdx, rdx
0x180098789  jz      loc_180098C64
0x18009878f  mov     rax, cs:__imp_gCookie
0x180098796  mov     r8, [rax]
0x180098799  mov     eax, r8d
0x18009879c  and     eax, 3Fh
0x18009879f  sub     esi, eax
0x1800987a1  mov     cl, sil
0x1800987a4  ror     rdx, cl
0x1800987a7  xor     rdx, r8
0x1800987aa  jz      loc_180098C64
0x1800987b0  lea     rax, aErrorFromStart; "Error from StartDocDlgW"
0x1800987b7  jmp     loc_180098562
0x1800987bc  mov     rax, [rbp+0A0h+var_118.lpszOutput]
0x1800987c0  test    r13, r13
0x1800987c3  cmovnz  rax, r13
0x1800987c7  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x1800987cb  mov     [rsp+1A0h+var_154], r14d
0x1800987d0  cmp     [rbx+30h], r14
0x1800987d4  jz      loc_180098867
0x1800987da  lea     rax, [rbp+0A0h+var_118]
0x1800987de  mov     [rsp+1A0h+var_130], rax
0x1800987e3  mov     rdx, rbx
0x1800987e6  lea     rcx, [rsp+1A0h+InData]
0x1800987eb  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x1800987f0  nop
0x1800987f1  mov     [rsp+1A0h+var_168], r14; void *
0x1800987f6  mov     [rsp+1A0h+var_170], r14d; unsigned int
0x1800987fb  lea     rax, [rsp+1A0h+var_130]
0x180098800  mov     [rsp+1A0h+lpOutData], rax; void *
0x180098805  mov     [rsp+1A0h+cjOutput], 8; unsigned int
0x18009880d  mov     r9d, 5; int
0x180098813  mov     r8, rdi; HDC
0x180098816  mov     rdx, [rbx+30h]; void *
0x18009881a  lea     rcx, [rsp+1A0h+InData]; this
0x18009881f  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x180098824  mov     [rsp+1A0h+var_158], eax
0x180098828  cmp     eax, 0FFFFFFFFh
0x18009882b  jnz     short loc_180098845
0x18009882d  lea     r12, aErrorFromDrive; "Error from driver UI"
0x180098834  xor     edx, edx; struct _UMPD *
0x180098836  lea     rcx, [rsp+1A0h+InData]; this
0x18009883b  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180098840  jmp     loc_180098B5B
0x180098845  cmp     eax, 0FFFFFFFEh
0x180098848  jnz     short loc_18009885B
0x18009884a  bts     dword ptr [rbx+8], 10h
0x18009884f  lea     r12, aCancelledFromD; "Cancelled from driver UI"
0x180098856  jmp     loc_180098B93
0x18009885b  xor     edx, edx; struct _UMPD *
0x18009885d  lea     rcx, [rsp+1A0h+InData]; this
0x180098862  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180098867  mov     dword ptr [rsp+1A0h+var_130], 1
0x18009886f  xor     ecx, ecx
0x180098871  call    cs:__imp_GetAppCompatFlags
0x180098878  nop     dword ptr [rax+rax+00h]
0x18009887d  bt      eax, 1Ah
0x180098881  jnb     short loc_1800988BD
0x180098883  mov     dword ptr [rsp+1A0h+InData], 1013h
0x18009888b  mov     [rsp+1A0h+lpOutData], r14; lpOutData
0x180098890  mov     [rsp+1A0h+cjOutput], r14d; cjOutput
0x180098895  lea     r9, [rsp+1A0h+InData]; lpInData
0x18009889a  mov     edx, 8; iEscape
0x18009889f  lea     r8d, [rdx-4]; cjInput
0x1800988a3  mov     rcx, rdi; hdc
0x1800988a6  call    cs:__imp_ExtEscape
0x1800988ad  nop     dword ptr [rax+rax+00h]
0x1800988b2  test    eax, eax
0x1800988b4  mov     eax, 1
0x1800988b9  cmovnz  r15d, eax
0x1800988bd  mov     rdx, rbx
0x1800988c0  lea     rcx, [rsp+1A0h+InData]
0x1800988c5  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x1800988ca  nop
0x1800988cb  test    r15d, r15d
0x1800988ce  jnz     short loc_1800988EE
0x1800988d0  xor     r8d, r8d
0x1800988d3  xor     edx, edx
0x1800988d5  mov     rcx, rdi
0x1800988d8  call    GetDCDWord
0x1800988dd  test    eax, eax
0x1800988df  jz      short loc_1800988EE
  ... truncated ...
```
