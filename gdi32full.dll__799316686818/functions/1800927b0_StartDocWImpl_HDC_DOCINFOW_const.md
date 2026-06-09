# StartDocWImpl(HDC__ *,_DOCINFOW const *)

- ea: `0x1800927b0`
- end: `0x180093103`
- name: `?StartDocWImpl@@YAHPEAUHDC__@@PEBU_DOCINFOW@@@Z`
- size: `2387`
- prototype: `__int64 __fastcall(HDC, const struct _DOCINFOW *)`
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180021fa0`
- `0x180022f88`
- `0x1800449c8`
- `0x180044b18`
- `0x180044b38`
- `0x180044b88`
- `0x180044d48`
- `0x180045c30`
- `0x18004ba98`
- `0x18006cda8`
- `0x1800710c4`
- `0x18007a11c`
- `0x18007a488`
- `0x18007ac50`
- `0x1800927b0`
- `0x180093120`
- `0x1800a2df0`
- `0x1800a3514`
- `0x1800a5010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093064`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180093064`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092f2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180092f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092cfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092cfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180092859`
- `GDI32!AbortDoc` at `0x1800930e0`
- `GDI32!AbortDoc` at `0x1800930e0`
- `GDI32!ExtEscape` at `0x180092c3c`
- `GDI32!ExtEscape` at `0x180092c3c`
- `GDI32!GdiGetEntry` at `0x18009288c`
- `GDI32!GdiGetEntry` at `0x180092a0f`
- `GDI32!GdiGetEntry` at `0x180092acf`
- `GDI32!GdiGetEntry` at `0x180092f62`
- `GDI32!GdiGetEntry` at `0x18009288c`
- `GDI32!GdiGetEntry` at `0x180092a0f`
- `GDI32!GdiGetEntry` at `0x180092acf`
- `GDI32!GdiGetEntry` at `0x180092f62`
- `GDI32!gW32PID` at `0x1800928cb`
- `GDI32!gW32PID` at `0x180092a4e`
- `GDI32!gW32PID` at `0x180092b0e`
- `GDI32!gW32PID` at `0x180092f95`
- `GDI32!gCookie` at `0x1800928e8`
- `GDI32!gCookie` at `0x180092a6b`
- `GDI32!gCookie` at `0x180092b2b`
- `GDI32!gCookie` at `0x180092faa`
- `GDI32!gMaxGdiHandleCount` at `0x180092869`
- `GDI32!gMaxGdiHandleCount` at `0x1800929ec`
- `GDI32!gMaxGdiHandleCount` at `0x180092aac`
- `GDI32!gMaxGdiHandleCount` at `0x180092f3d`
- `GDI32!pldcGet` at `0x180092837`
- `GDI32!pldcGet` at `0x180092837`
- `GDI32!GdiSetLastError` at `0x1800930f8`
- `GDI32!GdiSetLastError` at `0x1800930f8`
- `ntdll!RtlDecodePointer` at `0x1800929bd`
- `ntdll!RtlDecodePointer` at `0x180092cd7`
- `ntdll!RtlDecodePointer` at `0x1800929bd`
- `ntdll!RtlDecodePointer` at `0x180092cd7`
- `USER32!GetAppCompatFlags` at `0x180092c0d`
- `USER32!GetAppCompatFlags` at `0x180092c0d`
- `win32u!NtGdiStartDoc` at `0x180093026`
- `win32u!NtGdiStartDoc` at `0x180093026`

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
0x1800927b0  mov     [rsp-8+arg_10], rbx
0x1800927b5  push    rbp
0x1800927b6  push    rsi
0x1800927b7  push    rdi
0x1800927b8  push    r12
0x1800927ba  push    r13
0x1800927bc  push    r14
0x1800927be  push    r15
0x1800927c0  lea     rbp, [rsp-70h]
0x1800927c5  sub     rsp, 170h
0x1800927cc  mov     rax, cs:__security_cookie
0x1800927d3  xor     rax, rsp
0x1800927d6  mov     [rbp+0A0h+var_40], rax
0x1800927da  mov     r14, rdx
0x1800927dd  mov     rdi, rcx
0x1800927e0  mov     [rsp+1A0h+var_158], 0FFFFFFFFh
0x1800927e8  xorps   xmm0, xmm0
0x1800927eb  xor     eax, eax
0x1800927ed  movups  xmmword ptr [rbp+0A0h+var_118.cbSize], xmm0
0x1800927f1  movups  xmmword ptr [rbp+0A0h+var_118.lpszOutput], xmm0
0x1800927f5  mov     qword ptr [rbp+0A0h+var_118.fwType], rax
0x1800927f9  xor     r13d, r13d
0x1800927fc  mov     r15d, r13d
0x1800927ff  mov     [rsp+1A0h+var_154], r13d
0x180092804  mov     ebx, r13d
0x180092807  mov     [rsp+1A0h+var_128], ebx
0x18009280b  lea     r12, Default
0x180092812  mov     eax, ecx
0x180092814  and     eax, 7F0000h
0x180092819  lea     esi, [r13+40h]
0x18009281d  cmp     eax, 10000h
0x180092822  jz      loc_180092F35
0x180092828  cmp     eax, 660000h
0x18009282d  jz      loc_180092F35
0x180092833  mov     [rbp+0A0h+var_120], r13d
0x180092837  call    cs:__imp_pldcGet
0x18009283d  mov     rbx, rax
0x180092840  test    rax, rax
0x180092843  jz      loc_1800930F3
0x180092849  mov     eax, [rax+8]
0x18009284c  bt      eax, 18h
0x180092850  jnb     loc_18009291D
0x180092856  lea     ecx, [rsi-3Ah]; dwErrCode
0x180092859  call    cs:__imp_SetLastError
0x18009285f  mov     rcx, rdi
0x180092862  call    HANDLE_TO_INDEX
0x180092867  mov     ecx, eax
0x180092869  mov     rax, cs:__imp_gMaxGdiHandleCount
0x180092870  cmp     ecx, [rax]
0x180092872  jnb     loc_180092FDC
0x180092878  xorps   xmm0, xmm0
0x18009287b  xor     eax, eax
0x18009287d  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x180092882  mov     [rsp+1A0h+var_140], rax
0x180092887  lea     rdx, [rsp+1A0h+var_150]
0x18009288c  call    cs:__imp_GdiGetEntry
0x180092892  test    eax, eax
0x180092894  js      loc_180092FDC
0x18009289a  cmp     [rsp+1A0h+var_150+0Eh], 1
0x18009289f  jnz     loc_180092FDC
0x1800928a5  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x1800928aa  shl     cx, 8
0x1800928ae  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x1800928b3  or      cx, ax
0x1800928b6  mov     eax, edi
0x1800928b8  shr     eax, 10h
0x1800928bb  cmp     cx, ax
0x1800928be  jnz     loc_180092FDC
0x1800928c4  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x1800928c8  and     ecx, 0FFFFFFFEh
0x1800928cb  mov     rax, cs:__imp_gW32PID
0x1800928d2  cmp     ecx, [rax]
0x1800928d4  jnz     loc_180092FDC
0x1800928da  mov     rdx, [rsp+1A0h+var_140]
0x1800928df  test    rdx, rdx
0x1800928e2  jz      loc_180092FDC
0x1800928e8  mov     rax, cs:__imp_gCookie
0x1800928ef  mov     r8, [rax]
0x1800928f2  mov     eax, r8d
0x1800928f5  and     eax, 3Fh
0x1800928f8  sub     esi, eax
0x1800928fa  mov     cl, sil
0x1800928fd  ror     rdx, cl
0x180092900  xor     rdx, r8
0x180092903  jz      loc_180092FDC
0x180092909  lea     rax, aStartdocOnInfo; "StartDoc On Info DC"
0x180092910  mov     qword ptr [rsp+1A0h+cjOutput], rax
0x180092915  xor     r9d, r9d
0x180092918  jmp     loc_180092FCF
0x18009291d  btr     eax, 10h
0x180092921  mov     [rbx+8], eax
0x180092924  xor     ecx, ecx
0x180092926  test    r14, r14
0x180092929  jz      short loc_18009297D
0x18009292b  movups  xmm2, xmmword ptr [r14]
0x18009292f  movups  xmmword ptr [rbp+0A0h+var_118.cbSize], xmm2
0x180092933  movups  xmm0, xmmword ptr [r14+10h]
0x180092938  movups  xmmword ptr [rbp+0A0h+var_118.lpszOutput], xmm0
0x18009293c  movsd   xmm1, qword ptr [r14+20h]
0x180092942  movsd   qword ptr [rbp+0A0h+var_118.fwType], xmm1
0x180092947  movd    eax, xmm2
0x18009294b  cmp     eax, 18h
0x18009294e  jz      short loc_180092974
0x180092950  mov     [rbp+0A0h+var_118.cbSize], 28h ; '('
0x180092957  mov     [rbp+0A0h+var_118.lpszDatatype], rcx
0x18009295b  mov     [rbp+0A0h+var_118.fwType], ecx
0x18009295e  lea     r8, [rsp+1A0h+var_154]; int *
0x180092963  lea     rdx, [rbp+0A0h+var_118]; struct _DOCINFOW *
0x180092967  mov     rcx, r14; struct _DOCINFOW *
0x18009296a  call    ?TryReadDocInfo@@YAXPEBU_DOCINFOW@@AEAU1@AEAH@Z; TryReadDocInfo(_DOCINFOW const *,_DOCINFOW &,int &)
0x18009296f  mov     r15d, [rsp+1A0h+var_154]
0x180092974  mov     rax, [rbp+0A0h+var_118.lpszOutput]
0x180092978  xor     r14d, r14d
0x18009297b  jmp     short loc_18009299A
0x18009297d  mov     [rbp+0A0h+var_118.cbSize], 28h ; '('
0x180092984  xor     r14d, r14d
0x180092987  mov     [rbp+0A0h+var_118.lpszDatatype], r14
0x18009298b  mov     eax, r14d
0x18009298e  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x180092992  mov     [rbp+0A0h+var_118.lpszDocName], r14
0x180092996  mov     [rbp+0A0h+var_118.fwType], r14d
0x18009299a  test    rax, rax
0x18009299d  jnz     short loc_1800929AC
0x18009299f  cmp     [rbx+18h], r14
0x1800929a3  cmovnz  rax, [rbx+18h]
0x1800929a8  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x1800929ac  cmp     [rbx+30h], r14
0x1800929b0  jz      loc_180092B67
0x1800929b6  mov     rcx, cs:fpStartDocDlgW; Pointer
0x1800929bd  call    cs:__imp_RtlDecodePointer
0x1800929c3  lea     rdx, [rbp+0A0h+var_118]
0x1800929c7  mov     rcx, [rbx+30h]
0x1800929cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800929d0  mov     r13, rax
0x1800929d3  cmp     rax, 0FFFFFFFFFFFFFFFEh
0x1800929d7  jnz     loc_180092A98
0x1800929dd  bts     dword ptr [rbx+8], 10h
0x1800929e2  mov     rcx, rdi
0x1800929e5  call    HANDLE_TO_INDEX
0x1800929ea  mov     ecx, eax
0x1800929ec  mov     rax, cs:__imp_gMaxGdiHandleCount
0x1800929f3  cmp     ecx, [rax]
0x1800929f5  jnb     loc_180092FDC
0x1800929fb  xorps   xmm0, xmm0
0x1800929fe  xor     eax, eax
0x180092a00  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x180092a05  mov     [rsp+1A0h+var_140], rax
0x180092a0a  lea     rdx, [rsp+1A0h+var_150]
0x180092a0f  call    cs:__imp_GdiGetEntry
0x180092a15  test    eax, eax
0x180092a17  js      loc_180092FDC
0x180092a1d  cmp     [rsp+1A0h+var_150+0Eh], 1
0x180092a22  jnz     loc_180092FDC
0x180092a28  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x180092a2d  shl     cx, 8
0x180092a31  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x180092a36  or      cx, ax
0x180092a39  mov     eax, edi
0x180092a3b  shr     eax, 10h
0x180092a3e  cmp     cx, ax
0x180092a41  jnz     loc_180092FDC
0x180092a47  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x180092a4b  and     ecx, 0FFFFFFFEh
0x180092a4e  mov     rax, cs:__imp_gW32PID
0x180092a55  cmp     ecx, [rax]
0x180092a57  jnz     loc_180092FDC
0x180092a5d  mov     rdx, [rsp+1A0h+var_140]
0x180092a62  test    rdx, rdx
0x180092a65  jz      loc_180092FDC
0x180092a6b  mov     rax, cs:__imp_gCookie
0x180092a72  mov     r8, [rax]
0x180092a75  mov     eax, r8d
0x180092a78  and     eax, 3Fh
0x180092a7b  sub     esi, eax
0x180092a7d  mov     cl, sil
0x180092a80  ror     rdx, cl
0x180092a83  xor     rdx, r8
0x180092a86  jz      loc_180092FDC
0x180092a8c  lea     rax, aCanceledFromSt; "Canceled from StartDocDlgW"
0x180092a93  jmp     loc_180092910
0x180092a98  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180092a9c  jnz     loc_180092B58
0x180092aa2  mov     rcx, rdi
0x180092aa5  call    HANDLE_TO_INDEX
0x180092aaa  mov     ecx, eax
0x180092aac  mov     rax, cs:__imp_gMaxGdiHandleCount
0x180092ab3  cmp     ecx, [rax]
0x180092ab5  jnb     loc_180092FDC
0x180092abb  xorps   xmm0, xmm0
0x180092abe  xor     eax, eax
0x180092ac0  movups  xmmword ptr [rsp+1A0h+var_150], xmm0
0x180092ac5  mov     [rsp+1A0h+var_140], rax
0x180092aca  lea     rdx, [rsp+1A0h+var_150]
0x180092acf  call    cs:__imp_GdiGetEntry
0x180092ad5  test    eax, eax
0x180092ad7  js      loc_180092FDC
0x180092add  cmp     [rsp+1A0h+var_150+0Eh], 1
0x180092ae2  jnz     loc_180092FDC
0x180092ae8  movzx   ecx, [rsp+1A0h+var_150+0Dh]
0x180092aed  shl     cx, 8
0x180092af1  movzx   eax, [rsp+1A0h+var_150+0Ch]
0x180092af6  or      cx, ax
0x180092af9  mov     eax, edi
0x180092afb  shr     eax, 10h
0x180092afe  cmp     cx, ax
0x180092b01  jnz     loc_180092FDC
0x180092b07  mov     ecx, dword ptr [rsp+1A0h+var_150+8]
0x180092b0b  and     ecx, 0FFFFFFFEh
0x180092b0e  mov     rax, cs:__imp_gW32PID
0x180092b15  cmp     ecx, [rax]
0x180092b17  jnz     loc_180092FDC
0x180092b1d  mov     rdx, [rsp+1A0h+var_140]
0x180092b22  test    rdx, rdx
0x180092b25  jz      loc_180092FDC
0x180092b2b  mov     rax, cs:__imp_gCookie
0x180092b32  mov     r8, [rax]
0x180092b35  mov     eax, r8d
0x180092b38  and     eax, 3Fh
0x180092b3b  sub     esi, eax
0x180092b3d  mov     cl, sil
0x180092b40  ror     rdx, cl
0x180092b43  xor     rdx, r8
0x180092b46  jz      loc_180092FDC
0x180092b4c  lea     rax, aErrorFromStart; "Error from StartDocDlgW"
0x180092b53  jmp     loc_180092910
0x180092b58  mov     rax, [rbp+0A0h+var_118.lpszOutput]
0x180092b5c  test    r13, r13
0x180092b5f  cmovnz  rax, r13
0x180092b63  mov     [rbp+0A0h+var_118.lpszOutput], rax
0x180092b67  mov     [rsp+1A0h+var_154], r14d
0x180092b6c  cmp     [rbx+30h], r14
0x180092b70  jz      loc_180092C03
0x180092b76  lea     rax, [rbp+0A0h+var_118]
0x180092b7a  mov     [rsp+1A0h+var_130], rax
0x180092b7f  mov     rdx, rbx
0x180092b82  lea     rcx, [rsp+1A0h+InData]
0x180092b87  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x180092b8c  nop
0x180092b8d  mov     [rsp+1A0h+var_168], r14; void *
0x180092b92  mov     [rsp+1A0h+var_170], r14d; unsigned int
0x180092b97  lea     rax, [rsp+1A0h+var_130]
0x180092b9c  mov     [rsp+1A0h+lpOutData], rax; void *
0x180092ba1  mov     [rsp+1A0h+cjOutput], 8; unsigned int
0x180092ba9  mov     r9d, 5; int
0x180092baf  mov     r8, rdi; HDC
0x180092bb2  mov     rdx, [rbx+30h]; void *
0x180092bb6  lea     rcx, [rsp+1A0h+InData]; this
0x180092bbb  call    ?DocumentEventEx@@YAHAEAVUmpdPtr@@PEAXPEAUHDC__@@HK1K1@Z; DocumentEventEx(UmpdPtr &,void *,HDC__ *,int,ulong,void *,ulong,void *)
0x180092bc0  mov     [rsp+1A0h+var_158], eax
0x180092bc4  cmp     eax, 0FFFFFFFFh
0x180092bc7  jnz     short loc_180092BE1
0x180092bc9  lea     r12, aErrorFromDrive; "Error from driver UI"
0x180092bd0  xor     edx, edx; struct _UMPD *
0x180092bd2  lea     rcx, [rsp+1A0h+InData]; this
0x180092bd7  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180092bdc  jmp     loc_180092EDF
0x180092be1  cmp     eax, 0FFFFFFFEh
0x180092be4  jnz     short loc_180092BF7
0x180092be6  bts     dword ptr [rbx+8], 10h
0x180092beb  lea     r12, aCancelledFromD; "Cancelled from driver UI"
0x180092bf2  jmp     loc_180092F17
0x180092bf7  xor     edx, edx; struct _UMPD *
0x180092bf9  lea     rcx, [rsp+1A0h+InData]; this
0x180092bfe  call    ?reset@UmpdPtr@@QEAAXPEAU_UMPD@@@Z; UmpdPtr::reset(_UMPD *)
0x180092c03  mov     dword ptr [rsp+1A0h+var_130], 1
0x180092c0b  xor     ecx, ecx
0x180092c0d  call    cs:__imp_GetAppCompatFlags
0x180092c13  bt      eax, 1Ah
0x180092c17  jnb     short loc_180092C4D
0x180092c19  mov     dword ptr [rsp+1A0h+InData], 1013h
0x180092c21  mov     [rsp+1A0h+lpOutData], r14; lpOutData
0x180092c26  mov     [rsp+1A0h+cjOutput], r14d; cjOutput
0x180092c2b  lea     r9, [rsp+1A0h+InData]; lpInData
0x180092c30  mov     edx, 8; iEscape
0x180092c35  lea     r8d, [rdx-4]; cjInput
0x180092c39  mov     rcx, rdi; hdc
0x180092c3c  call    cs:__imp_ExtEscape
0x180092c42  test    eax, eax
0x180092c44  mov     eax, 1
0x180092c49  cmovnz  r15d, eax
0x180092c4d  mov     rdx, rbx
0x180092c50  lea     rcx, [rsp+1A0h+InData]
0x180092c55  call    ?LdcGetUmpd@@YA?AVUmpdPtr@@PEAU_LDC@@@Z; LdcGetUmpd(_LDC *)
0x180092c5a  nop
0x180092c5b  test    r15d, r15d
0x180092c5e  jnz     short loc_180092C7E
0x180092c60  xor     r8d, r8d
0x180092c63  xor     edx, edx
0x180092c65  mov     rcx, rdi
0x180092c68  call    GetDCDWord
0x180092c6d  test    eax, eax
0x180092c6f  jz      short loc_180092C7E
0x180092c71  mov     rcx, [rbx+30h]
0x180092c75  call    RemoteRasterizerCompatible
0x180092c7a  test    eax, eax
0x180092c7c  jnz     short loc_180092CA9
0x180092c7e  lea     rcx, [rsp+1A0h+InData]
0x180092c83  call    ??BUmpdPtr@@QEAA_NXZ; UmpdPtr::operator bool(void)
0x180092c88  test    al, al
0x180092c8a  jz      loc_180092D75
  ... truncated ...
```
