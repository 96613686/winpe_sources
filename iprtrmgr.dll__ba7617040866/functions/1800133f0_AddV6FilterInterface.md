# AddV6FilterInterface

- ea: `0x1800133f0`
- end: `0x180013c60`
- name: `AddV6FilterInterface`
- size: `2160`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180012914`

## callees

- `0x180011790`
- `0x1800133f0`
- `0x180013c70`
- `0x18001e490`
- `0x180053214`
- `0x180053c38`
- `0x180053d48`
- `0x180054bb0`
- `0x180054c30`
- `0x1800583cc`
- `0x18005852a`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180013b7b`
- `KERNEL32!HeapFree` at `0x180013b92`
- `KERNEL32!HeapFree` at `0x180013bb6`
- `KERNEL32!HeapFree` at `0x180013bd6`
- `KERNEL32!HeapFree` at `0x180013b7b`
- `KERNEL32!HeapFree` at `0x180013b92`
- `KERNEL32!HeapFree` at `0x180013bb6`
- `KERNEL32!HeapFree` at `0x180013bd6`
- `KERNEL32!HeapAlloc` at `0x1800134cd`
- `KERNEL32!HeapAlloc` at `0x180013591`
- `KERNEL32!HeapAlloc` at `0x1800136cd`
- `KERNEL32!HeapAlloc` at `0x180013786`
- `KERNEL32!HeapAlloc` at `0x1800134cd`
- `KERNEL32!HeapAlloc` at `0x180013591`
- `KERNEL32!HeapAlloc` at `0x1800136cd`
- `KERNEL32!HeapAlloc` at `0x180013786`

## string_xrefs

- `0x180013952`: `AddV6FilterInterface: Error %d adding frag cache filter to %ws`

## pseudocode

```c
__int64 __fastcall AddV6FilterInterface(__int64 a1, __int64 a2, _DWORD *a3)
{
  void *v5; // r12
  unsigned int v6; // r13d
  __int64 PointerToTocEntry; // rax
  char *v8; // r11
  unsigned int v9; // eax
  _DWORD *v10; // rbx
  unsigned int v11; // esi
  void *v12; // rax
  const wchar_t *v13; // rdx
  __int128 *v14; // r9
  unsigned int v15; // ebx
  char *v16; // rax
  unsigned int v17; // r10d
  __int64 v18; // r9
  __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // ecx
  char *v22; // r14
  unsigned int v23; // esi
  __int64 v24; // rax
  int v25; // r11d
  unsigned int v26; // ecx
  _DWORD *v27; // rbx
  unsigned int v28; // r15d
  void *v29; // rax
  __int128 *v30; // r9
  unsigned int v31; // r11d
  __int64 v32; // r10
  __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // ecx
  void **v36; // r15
  InterfaceContainer *v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // r9
  __int128 *v40; // r9
  __int64 v41; // r9
  __int128 *v42; // r9
  InterfaceContainer *v43; // rcx
  __int64 v44; // r9
  __int64 *v45; // rdx
  __int128 *v46; // r9
  __int64 v47; // r9
  __int64 v48; // r9
  __int128 *v49; // r9
  void *v50; // r8
  void *v51; // r8
  __int128 *v52; // r9
  enum _PfForwardAction v54; // [rsp+40h] [rbp-C0h]
  enum _PfForwardAction v55; // [rsp+44h] [rbp-BCh]
  __int128 v57; // [rsp+50h] [rbp-B0h] BYREF
  int v58; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v59; // [rsp+64h] [rbp-9Ch]
  __int128 v60; // [rsp+74h] [rbp-8Ch]
  int v61; // [rsp+84h] [rbp-7Ch]
  int v62; // [rsp+90h] [rbp-70h] BYREF
  char v63[2044]; // [rsp+94h] [rbp-6Ch] BYREF
  char v64[528]; // [rsp+890h] [rbp+790h] BYREF

  v62 = 0;
  memset_0(v63, 0, sizeof(v63));
  v58 = 0;
  v61 = 0;
  v54 = PF_ACTION_FORWARD;
  v59 = 0;
  v5 = 0;
  v6 = 0;
  v60 = 0;
  v57 = 0;
  PointerToTocEntry = GetPointerToTocEntry(4294901777LL, a2);
  if ( PointerToTocEntry )
  {
    if ( *(_DWORD *)(PointerToTocEntry + 4) != (_DWORD)v8 )
    {
      v9 = *(_DWORD *)(PointerToTocEntry + 12);
      if ( v9 < *(_DWORD *)(a2 + 4) )
      {
        v10 = (_DWORD *)(a2 + v9);
        if ( v10 )
        {
          if ( v10[1] != (_DWORD)v8 || v10[2] == 1 )
          {
            v6 = v10[1];
            v11 = 52 * v6 + 12;
            v12 = HeapAlloc(IPRouterHeap, 0, v11);
            *(_QWORD *)(a1 + 112) = v12;
            if ( !v12 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                v13 = L"AddV6FilterInterface: Error allocating %d bytes for in filters";
                goto LABEL_10;
              }
              goto LABEL_14;
            }
            memcpy_0(v12, v10, 52 * v6 + 12);
            v8 = 0;
            v54 = v10[2];
            if ( v6 )
            {
              v11 = 80 * v6 + 8;
              v16 = (char *)HeapAlloc(IPRouterHeap, 0, v11);
              v8 = 0;
              v5 = v16;
              if ( !v16 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v13 = L"AddV6FilterInterface: Error allocating %d bytes";
LABEL_10:
                  LOWORD(v58) = 0;
                  LOWORD(v62) = 0;
                  FormatRRASErrorString(&v62, v13, v11);
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v14 = &v57;
                    if ( a1 != -688 )
                      LODWORD(v14) = a1 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v62,
                      (_DWORD)v14,
                      *(_QWORD *)(a1 + 72),
                      (__int64)&v58);
                  }
                }
LABEL_14:
                v15 = 8;
LABEL_90:
                v50 = *(void **)(a1 + 112);
                *(_QWORD *)(a1 + 96) = -1;
                if ( v50 )
                {
                  HeapFree(IPRouterHeap, 0, v50);
                  *(_QWORD *)(a1 + 112) = 0;
                }
                v51 = *(void **)(a1 + 120);
                if ( v51 )
                {
                  HeapFree(IPRouterHeap, 0, v51);
                  *(_QWORD *)(a1 + 120) = 0;
                }
                goto LABEL_94;
              }
              v17 = 0;
              v18 = 0;
              do
              {
                v19 = 13 * v18;
                v20 = v18 << 6;
                *(_QWORD *)&v16[v20 + 16] = &v10[13 * v18 + 3];
                *(_QWORD *)&v16[v20] = 0;
                *(_QWORD *)&v16[v20 + 24] = &v10[13 * v18 + 7];
                *(_DWORD *)&v16[v20 + 8] = 1;
                *(_QWORD *)&v16[v20 + 32] = &v10[13 * v18 + 8];
                *(_QWORD *)&v16[v20 + 40] = &v10[13 * v18 + 12];
                v21 = v10[13 * v18 + 13];
                *(_DWORD *)&v16[v20 + 48] = v21;
                *(_DWORD *)&v16[v20 + 52] = v10[13 * v18 + 14];
                if ( v21 == 6 && (v10[v19 + 14] & 0x40) != 0 )
                  *(_DWORD *)&v16[v20] = 1;
                ++v17;
                *(_WORD *)&v16[v20 + 56] = v10[v19 + 15];
                ++v18;
                *(_WORD *)&v16[v20 + 58] = HIWORD(v10[v19 + 15]);
                *(_DWORD *)&v16[v20 + 60] = 0;
              }
              while ( v17 < v6 );
            }
          }
        }
      }
    }
  }
  v55 = (int)v8;
  v22 = v8;
  v23 = (unsigned int)v8;
  v24 = GetPointerToTocEntry(4294901778LL, a2);
  if ( v24 )
  {
    if ( *(_DWORD *)(v24 + 4) != v25 )
    {
      v26 = *(_DWORD *)(v24 + 12);
      if ( v26 < *(_DWORD *)(a2 + 4) )
      {
        v27 = (_DWORD *)(a2 + v26);
        if ( v27 )
        {
          if ( v27[1] != v25 || v27[2] == 1 )
          {
            v23 = v27[1];
            v28 = 52 * v23 + 12;
            v29 = HeapAlloc(IPRouterHeap, 0, v28);
            *(_QWORD *)(a1 + 120) = v29;
            if ( !v29 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                LOWORD(v62) = 0;
                LOWORD(v58) = 0;
                FormatRRASErrorString(&v62, L"AddV6FilterInterface: Error allocating %d bytes for out filters", v28);
                goto LABEL_34;
              }
              goto LABEL_38;
            }
            memcpy_0(v29, v27, v28);
            v55 = v27[2];
            if ( v23 )
            {
              v22 = (char *)HeapAlloc(IPRouterHeap, 0, 80 * v23 + 8);
              if ( !v22 )
              {
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  LOWORD(v62) = 0;
                  LOWORD(v58) = 0;
                  FormatRRASErrorString(&v62, L"AddV6FilterInterface: Error allocating %d bytes", 80 * v23 + 8);
LABEL_34:
                  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                  {
                    v30 = &v57;
                    if ( a1 != -688 )
                      LODWORD(v30) = a1 + 688;
                    McTemplateU0zjzz_EventWriteTransfer(
                      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                      (unsigned int)RasRtrMgrParamTraceError,
                      (unsigned int)&v62,
                      (_DWORD)v30,
                      *(_QWORD *)(a1 + 72),
                      (__int64)&v58);
                  }
                }
LABEL_38:
                v15 = 8;
                goto LABEL_85;
              }
              v31 = 0;
              v32 = 0;
              do
              {
                v33 = 13 * v32;
                v34 = v32 << 6;
                *(_QWORD *)&v22[v34 + 16] = &v27[13 * v32 + 3];
                *(_QWORD *)&v22[v34] = 0;
                *(_QWORD *)&v22[v34 + 24] = &v27[13 * v32 + 7];
                *(_DWORD *)&v22[v34 + 8] = 1;
                *(_QWORD *)&v22[v34 + 32] = &v27[13 * v32 + 8];
                *(_QWORD *)&v22[v34 + 40] = &v27[13 * v32 + 12];
                v35 = v27[13 * v32 + 13];
                *(_DWORD *)&v22[v34 + 48] = v35;
                *(_DWORD *)&v22[v34 + 52] = v27[13 * v32 + 14];
                if ( v35 == 6 && (v27[v33 + 14] & 0x40) != 0 )
                  *(_DWORD *)&v22[v34] = 1;
                ++v31;
                *(_WORD *)&v22[v34 + 56] = v27[v33 + 15];
                ++v32;
                *(_WORD *)&v22[v34 + 58] = HIWORD(v27[v33 + 15]);
                *(_DWORD *)&v22[v34 + 60] = 0;
              }
              while ( v31 < v23 );
            }
          }
        }
      }
    }
  }
  GetInterfaceFriendlyName(*(_QWORD *)(a1 + 72), v64);
  v36 = (void **)(a1 + 96);
  v38 = InterfaceContainer::AddInterface(v37, 0, v54, v55, 0, 0, (void **)(a1 + 96), PF_IPV6);
  v15 = v38;
  if ( v38 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v39 = *(_QWORD *)(a1 + 72);
      LOWORD(v62) = 0;
      LOWORD(v58) = 0;
      FormatRRASErrorString(&v62, L"AddV6FilterInterface: Err %d creating filter i/f for %ws", v38, v39);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v40 = &v57;
        if ( a1 != -688 )
          LODWORD(v40) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v62,
          (_DWORD)v40,
          *(_QWORD *)(a1 + 72),
          (__int64)&v58);
      }
    }
    *a3 = 1;
    goto LABEL_85;
  }
  v15 = PfInternAddGlobalFilterToInterface(*v36);
  if ( v15 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v41 = *(_QWORD *)(a1 + 72);
      LOWORD(v62) = 0;
      LOWORD(v58) = 0;
      FormatRRASErrorString(&v62, L"AddV6FilterInterface: Error %d adding frag cache filter to %ws", v15, v41);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v42 = &v57;
        if ( a1 != -688 )
          LODWORD(v42) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v62,
          (_DWORD)v42,
          *(_QWORD *)(a1 + 72),
          (__int64)&v58);
      }
    }
    v15 = 0;
  }
  if ( v23 + v6 )
  {
    v15 = PfInternAddFiltersToInterface(*v36, (__int64)v22, 0);
    if ( v15 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v44 = *(_QWORD *)(a1 + 72);
        LOWORD(v62) = 0;
        LOWORD(v58) = 0;
        FormatRRASErrorString(&v62, L"AddV6FilterInterface: Err %d setting filters on %ws", v15, v44);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          v45 = RasRtrmgrParamTraceInfo;
LABEL_68:
          v46 = &v57;
          if ( a1 != -688 )
            LODWORD(v46) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (_DWORD)v45,
            (unsigned int)&v62,
            (_DWORD)v46,
            *(_QWORD *)(a1 + 72),
            (__int64)&v58);
          goto LABEL_71;
        }
      }
      goto LABEL_71;
    }
  }
  if ( *(_DWORD *)(a1 + 512) )
  {
    v15 = BindFilterInterface(a1);
    if ( v15 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v47 = *(_QWORD *)(a1 + 72);
        LOWORD(v62) = 0;
        LOWORD(v58) = 0;
        FormatRRASErrorString(&v62, L"AddV6FilterInterface: Err %d binding filters on %ws", v15, v47);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v45 = RasRtrMgrParamTraceError;
          goto LABEL_68;
        }
      }
LABEL_71:
      *a3 = 1;
      InterfaceContainer::DeleteInterface(v43, *v36);
      goto LABEL_85;
    }
  }
  if ( *(_DWORD *)(a1 + 136) )
  {
    v15 = PfInternAddGlobalFilterToInterface(*v36);
    if ( v15 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v48 = *(_QWORD *)(a1 + 72);
        LOWORD(v62) = 0;
        LOWORD(v58) = 0;
        FormatRRASErrorString(&v62, L"AddV6FilterInterface: Error %d adding frag drop filter to %ws", v15, v48);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v49 = &v57;
          if ( a1 != -688 )
            LODWORD(v49) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v62,
            (_DWORD)v49,
            *(_QWORD *)(a1 + 72),
            (__int64)&v58);
        }
      }
      *(_DWORD *)(a1 + 136) = 0;
      v15 = 0;
    }
  }
LABEL_85:
  if ( v5 )
    HeapFree(IPRouterHeap, 0, v5);
  if ( v22 )
    HeapFree(IPRouterHeap, 0, v22);
  if ( v15 )
    goto LABEL_90;
LABEL_94:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v52 = &v57;
    LOWORD(v58) = 0;
    if ( a1 != -688 )
      LODWORD(v52) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: AddV6FilterInterface",
      (_DWORD)v52,
      *(_QWORD *)(a1 + 72),
      (__int64)&v58);
  }
  return v15;
}

```

## disassembly

```asm
0x1800133f0  mov     [rsp-8+arg_18], rbx
0x1800133f5  push    rbp
0x1800133f6  push    rsi
0x1800133f7  push    rdi
0x1800133f8  push    r12
0x1800133fa  push    r13
0x1800133fc  push    r14
0x1800133fe  push    r15
0x180013400  lea     rbp, [rsp-9B0h]
0x180013408  sub     rsp, 0AB0h
0x18001340f  mov     rax, cs:__security_cookie
0x180013416  xor     rax, rsp
0x180013419  mov     [rbp+9E0h+var_40], rax
0x180013420  mov     [rsp+0AE0h+var_A98], r8
0x180013425  mov     r15, rdx
0x180013428  mov     rdi, rcx
0x18001342b  xor     eax, eax
0x18001342d  xor     edx, edx; Val
0x18001342f  mov     [rbp+9E0h+var_A50], eax
0x180013432  mov     r8d, 7FCh; Size
0x180013438  lea     rcx, [rbp+9E0h+var_A4C]; void *
0x18001343c  call    memset_0
0x180013441  xor     r11d, r11d
0x180013444  xorps   xmm0, xmm0
0x180013447  xor     eax, eax
0x180013449  mov     [rsp+0AE0h+var_A80], r11d
0x18001344e  mov     rdx, r15
0x180013451  mov     [rbp+9E0h+var_A5C], eax
0x180013454  mov     ecx, 0FFFF0011h
0x180013459  mov     [rsp+0AE0h+var_AA0], r11d
0x18001345e  movups  [rsp+0AE0h+var_A7C], xmm0
0x180013463  mov     r12d, r11d
0x180013466  mov     r13d, r11d
0x180013469  movups  [rsp+0AE0h+var_A6C], xmm0
0x18001346e  movups  [rsp+0AE0h+var_A90], xmm0
0x180013473  call    GetPointerToTocEntry
0x180013478  test    rax, rax
0x18001347b  jz      loc_180013663
0x180013481  cmp     [rax+4], r11d
0x180013485  jz      loc_180013663
0x18001348b  mov     eax, [rax+0Ch]
0x18001348e  cmp     eax, [r15+4]
0x180013492  jnb     loc_180013663
0x180013498  mov     ebx, eax
0x18001349a  add     rbx, r15
0x18001349d  jz      loc_180013663
0x1800134a3  cmp     [rbx+4], r11d
0x1800134a7  jnz     short loc_1800134B3
0x1800134a9  cmp     dword ptr [rbx+8], 1
0x1800134ad  jnz     loc_180013663
0x1800134b3  mov     r13d, [rbx+4]
0x1800134b7  xor     edx, edx; dwFlags
0x1800134b9  mov     rcx, cs:IPRouterHeap; hHeap
0x1800134c0  imul    esi, r13d, 34h ; '4'
0x1800134c4  add     esi, 0Ch
0x1800134c7  mov     r8d, esi; dwBytes
0x1800134ca  mov     r14d, esi
0x1800134cd  call    cs:__imp_HeapAlloc
0x1800134d3  mov     [rdi+70h], rax
0x1800134d7  test    rax, rax
0x1800134da  jnz     short loc_180013553
0x1800134dc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800134e3  jz      short loc_180013549
0x1800134e5  lea     rdx, aAddv6filterint_5; "AddV6FilterInterface: Error allocating "...
0x1800134ec  xor     eax, eax
0x1800134ee  lea     rcx, [rbp+9E0h+var_A50]
0x1800134f2  mov     r8d, esi
0x1800134f5  mov     word ptr [rsp+0AE0h+var_A80], ax
0x1800134fa  mov     word ptr [rbp+9E0h+var_A50], ax
0x1800134fe  call    FormatRRASErrorString
0x180013503  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001350a  jz      short loc_180013549
0x18001350c  lea     rax, [rdi+2B0h]
0x180013513  test    rax, rax
0x180013516  lea     r9, [rsp+0AE0h+var_A90]
0x18001351b  lea     r8, [rbp+9E0h+var_A50]
0x18001351f  cmovnz  r9, rax
0x180013523  lea     rdx, RasRtrMgrParamTraceError
0x18001352a  lea     rax, [rsp+0AE0h+var_A80]
0x18001352f  mov     [rsp+0AE0h+var_AB8], rax
0x180013534  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001353b  mov     rax, [rdi+48h]
0x18001353f  mov     [rsp+0AE0h+var_AC0], rax
0x180013544  call    McTemplateU0zjzz_EventWriteTransfer
0x180013549  mov     ebx, 8
0x18001354e  jmp     loc_180013B9C
0x180013553  mov     r8, r14; Size
0x180013556  mov     rdx, rbx; Src
0x180013559  mov     rcx, rax; void *
0x18001355c  call    memcpy_0
0x180013561  mov     eax, [rbx+8]
0x180013564  xor     r11d, r11d
0x180013567  mov     [rsp+0AE0h+var_AA0], eax
0x18001356b  test    r13d, r13d
0x18001356e  jz      loc_180013663
0x180013574  mov     rcx, cs:IPRouterHeap; hHeap
0x18001357b  lea     esi, ds:0[r13*4]
0x180013583  add     esi, r13d
0x180013586  xor     edx, edx; dwFlags
0x180013588  shl     esi, 4
0x18001358b  add     esi, 8
0x18001358e  mov     r8d, esi; dwBytes
0x180013591  call    cs:__imp_HeapAlloc
0x180013597  xor     r11d, r11d
0x18001359a  mov     r12, rax
0x18001359d  test    rax, rax
0x1800135a0  jnz     short loc_1800135B7
0x1800135a2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800135a9  jz      short loc_180013549
0x1800135ab  lea     rdx, aAddv6filterint_6; "AddV6FilterInterface: Error allocating "...
0x1800135b2  jmp     loc_1800134EC
0x1800135b7  mov     r10d, r11d
0x1800135ba  test    r13d, r13d
0x1800135bd  jz      loc_180013663
0x1800135c3  mov     r9, r11
0x1800135c6  imul    r8, r9, 34h ; '4'
0x1800135ca  mov     rdx, r9
0x1800135cd  lea     rax, [rbx+0Ch]
0x1800135d1  shl     rdx, 6
0x1800135d5  add     rax, r8
0x1800135d8  mov     [rdx+r12+10h], rax
0x1800135dd  lea     rax, [rbx+1Ch]
0x1800135e1  add     rax, r8
0x1800135e4  mov     [rdx+r12], r11
0x1800135e8  mov     [rdx+r12+18h], rax
0x1800135ed  lea     rax, [rbx+20h]
0x1800135f1  add     rax, r8
0x1800135f4  mov     dword ptr [rdx+r12+8], 1
0x1800135fd  mov     [rdx+r12+20h], rax
0x180013602  lea     rax, [rbx+30h]
0x180013606  add     rax, r8
0x180013609  mov     [rdx+r12+28h], rax
0x18001360e  mov     ecx, [r8+rbx+34h]
0x180013613  mov     [rdx+r12+30h], ecx
0x180013618  mov     eax, [r8+rbx+38h]
0x18001361d  mov     [rdx+r12+34h], eax
0x180013622  cmp     ecx, 6
0x180013625  jnz     short loc_180013637
0x180013627  test    byte ptr [r8+rbx+38h], 40h
0x18001362d  jz      short loc_180013637
0x18001362f  mov     dword ptr [rdx+r12], 1
0x180013637  movzx   eax, word ptr [r8+rbx+3Ch]
0x18001363d  inc     r10d
0x180013640  mov     [rdx+r12+38h], ax
0x180013646  inc     r9
0x180013649  movzx   eax, word ptr [r8+rbx+3Eh]
0x18001364f  mov     [rdx+r12+3Ah], ax
0x180013655  mov     [rdx+r12+3Ch], r11d
0x18001365a  cmp     r10d, r13d
0x18001365d  jb      loc_1800135C6
0x180013663  mov     rdx, r15
0x180013666  mov     [rsp+0AE0h+var_A9C], r11d
0x18001366b  mov     ecx, 0FFFF0012h
0x180013670  mov     r14, r11
0x180013673  mov     esi, r11d
0x180013676  call    GetPointerToTocEntry
0x18001367b  test    rax, rax
0x18001367e  jz      loc_180013865
0x180013684  cmp     [rax+4], r11d
0x180013688  jz      loc_180013865
0x18001368e  mov     ecx, [rax+0Ch]
0x180013691  cmp     ecx, [r15+4]
0x180013695  jnb     loc_180013865
0x18001369b  mov     ebx, ecx
0x18001369d  add     rbx, r15
0x1800136a0  jz      loc_180013865
0x1800136a6  cmp     [rbx+4], r11d
0x1800136aa  jnz     short loc_1800136B6
0x1800136ac  cmp     dword ptr [rbx+8], 1
0x1800136b0  jnz     loc_180013865
0x1800136b6  mov     esi, [rbx+4]
0x1800136b9  xor     edx, edx; dwFlags
0x1800136bb  mov     rcx, cs:IPRouterHeap; hHeap
0x1800136c2  imul    r15d, esi, 34h ; '4'
0x1800136c6  add     r15d, 0Ch
0x1800136ca  mov     r8d, r15d; dwBytes
0x1800136cd  call    cs:__imp_HeapAlloc
0x1800136d3  mov     [rdi+78h], rax
0x1800136d7  test    rax, rax
0x1800136da  jnz     short loc_180013751
0x1800136dc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800136e3  jz      short loc_180013747
0x1800136e5  mov     word ptr [rbp+9E0h+var_A50], ax
0x1800136e9  lea     rdx, aAddv6filterint_0; "AddV6FilterInterface: Error allocating "...
0x1800136f0  mov     word ptr [rsp+0AE0h+var_A80], ax
0x1800136f5  mov     r8d, r15d
0x1800136f8  lea     rcx, [rbp+9E0h+var_A50]
0x1800136fc  call    FormatRRASErrorString
0x180013701  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180013708  jz      short loc_180013747
0x18001370a  lea     rax, [rdi+2B0h]
0x180013711  test    rax, rax
0x180013714  lea     r9, [rsp+0AE0h+var_A90]
0x180013719  lea     r8, [rbp+9E0h+var_A50]
0x18001371d  cmovnz  r9, rax
0x180013721  lea     rdx, RasRtrMgrParamTraceError
0x180013728  lea     rax, [rsp+0AE0h+var_A80]
0x18001372d  mov     [rsp+0AE0h+var_AB8], rax
0x180013732  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180013739  mov     rax, [rdi+48h]
0x18001373d  mov     [rsp+0AE0h+var_AC0], rax
0x180013742  call    McTemplateU0zjzz_EventWriteTransfer
0x180013747  mov     ebx, 8
0x18001374c  jmp     loc_180013B6A
0x180013751  mov     r8d, r15d; Size
0x180013754  mov     rdx, rbx; Src
0x180013757  mov     rcx, rax; void *
0x18001375a  call    memcpy_0
0x18001375f  mov     eax, [rbx+8]
0x180013762  mov     [rsp+0AE0h+var_A9C], eax
0x180013766  test    esi, esi
0x180013768  jz      loc_180013865
0x18001376e  mov     rcx, cs:IPRouterHeap; hHeap
0x180013775  lea     r15d, [rsi+rsi*4]
0x180013779  shl     r15d, 4
0x18001377d  xor     edx, edx; dwFlags
0x18001377f  add     r15d, 8
0x180013783  mov     r8d, r15d; dwBytes
0x180013786  call    cs:__imp_HeapAlloc
0x18001378c  mov     r14, rax
0x18001378f  test    rax, rax
0x180013792  jnz     short loc_1800137B4
0x180013794  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001379b  jz      short loc_180013747
0x18001379d  xor     ecx, ecx
0x18001379f  lea     rdx, aAddv6filterint_6; "AddV6FilterInterface: Error allocating "...
0x1800137a6  mov     word ptr [rbp+9E0h+var_A50], cx
0x1800137aa  mov     word ptr [rsp+0AE0h+var_A80], cx
0x1800137af  jmp     loc_1800136F5
0x1800137b4  xor     r11d, r11d
0x1800137b7  test    esi, esi
0x1800137b9  jz      loc_180013865
0x1800137bf  xor     r10d, r10d
0x1800137c2  imul    r8, r10, 34h ; '4'
0x1800137c6  mov     rdx, r10
0x1800137c9  lea     rax, [rbx+0Ch]
0x1800137cd  shl     rdx, 6
0x1800137d1  add     rax, r8
0x1800137d4  mov     [rdx+r14+10h], rax
0x1800137d9  lea     rax, [rbx+1Ch]
0x1800137dd  add     rax, r8
0x1800137e0  mov     qword ptr [rdx+r14], 0
0x1800137e8  mov     [rdx+r14+18h], rax
0x1800137ed  lea     rax, [rbx+20h]
0x1800137f1  add     rax, r8
0x1800137f4  mov     dword ptr [rdx+r14+8], 1
0x1800137fd  mov     [rdx+r14+20h], rax
0x180013802  lea     rax, [rbx+30h]
0x180013806  add     rax, r8
0x180013809  mov     [rdx+r14+28h], rax
0x18001380e  mov     ecx, [rbx+r8+34h]
0x180013813  mov     [rdx+r14+30h], ecx
0x180013818  mov     eax, [rbx+r8+38h]
0x18001381d  mov     [rdx+r14+34h], eax
0x180013822  cmp     ecx, 6
0x180013825  jnz     short loc_180013837
0x180013827  test    byte ptr [rbx+r8+38h], 40h
0x18001382d  jz      short loc_180013837
0x18001382f  mov     dword ptr [rdx+r14], 1
0x180013837  movzx   eax, word ptr [rbx+r8+3Ch]
0x18001383d  inc     r11d
0x180013840  mov     [rdx+r14+38h], ax
0x180013846  inc     r10
0x180013849  movzx   eax, word ptr [rbx+r8+3Eh]
0x18001384f  mov     [rdx+r14+3Ah], ax
0x180013855  xor     eax, eax
0x180013857  mov     [rdx+r14+3Ch], eax
0x18001385c  cmp     r11d, esi
0x18001385f  jb      loc_1800137C2
0x180013865  mov     rcx, [rdi+48h]
0x180013869  lea     rdx, [rbp+9E0h+var_250]
0x180013870  call    GetInterfaceFriendlyName
0x180013875  mov     r9d, [rsp+0AE0h+var_A9C]; enum _PfForwardAction
0x18001387a  lea     r15, [rdi+60h]
0x18001387e  mov     r8d, [rsp+0AE0h+var_AA0]; enum _PfForwardAction
0x180013883  xor     edx, edx; unsigned int
0x180013885  mov     [rsp+0AE0h+var_AA8], 1; enum _PfAddresType
0x18001388d  mov     [rsp+0AE0h+var_AB0], r15; void **
0x180013892  mov     dword ptr [rsp+0AE0h+var_AB8], 0; int
0x18001389a  mov     dword ptr [rsp+0AE0h+var_AC0], 0; int
0x1800138a2  call    ?AddInterface@InterfaceContainer@@QEAAKKW4_PfForwardAction@@0HHPEAPEAXW4_PfAddresType@@@Z; InterfaceContainer::AddInterface(ulong,_PfForwardAction,_PfForwardAction,int,int,void * *,_PfAddresType)
0x1800138a7  mov     ebx, eax
0x1800138a9  test    eax, eax
0x1800138ab  jz      loc_180013932
0x1800138b1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800138b8  jge     short loc_180013922
0x1800138ba  mov     r9, [rdi+48h]
0x1800138be  lea     rdx, aAddv6filterint; "AddV6FilterInterface: Err %d creating f"...
0x1800138c5  xor     ecx, ecx
0x1800138c7  mov     r8d, eax
0x1800138ca  mov     word ptr [rbp+9E0h+var_A50], cx
0x1800138ce  mov     word ptr [rsp+0AE0h+var_A80], cx
0x1800138d3  lea     rcx, [rbp+9E0h+var_A50]
0x1800138d7  call    FormatRRASErrorString
0x1800138dc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800138e3  jge     short loc_180013922
0x1800138e5  lea     rax, [rdi+2B0h]
0x1800138ec  test    rax, rax
0x1800138ef  lea     r9, [rsp+0AE0h+var_A90]
0x1800138f4  lea     r8, [rbp+9E0h+var_A50]
  ... truncated ...
```
