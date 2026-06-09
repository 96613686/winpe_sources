# AddFilterInterface

- ea: `0x180012914`
- end: `0x1800133e9`
- name: `AddFilterInterface`
- size: `2773`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180014740`

## callees

- `0x180011790`
- `0x180012914`
- `0x1800133f0`
- `0x180013c70`
- `0x1800149ec`
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

- `KERNEL32!HeapFree` at `0x180012b68`
- `KERNEL32!HeapFree` at `0x180012cfd`
- `KERNEL32!HeapFree` at `0x180012d1c`
- `KERNEL32!HeapFree` at `0x180012d95`
- `KERNEL32!HeapFree` at `0x180012db0`
- `KERNEL32!HeapFree` at `0x180012dc3`
- `KERNEL32!HeapFree` at `0x18001324e`
- `KERNEL32!HeapFree` at `0x180013265`
- `KERNEL32!HeapFree` at `0x180013289`
- `KERNEL32!HeapFree` at `0x1800132a5`
- `KERNEL32!HeapFree` at `0x180012b68`
- `KERNEL32!HeapFree` at `0x180012cfd`
- `KERNEL32!HeapFree` at `0x180012d1c`
- `KERNEL32!HeapFree` at `0x180012d95`
- `KERNEL32!HeapFree` at `0x180012db0`
- `KERNEL32!HeapFree` at `0x180012dc3`
- `KERNEL32!HeapFree` at `0x18001324e`
- `KERNEL32!HeapFree` at `0x180013265`
- `KERNEL32!HeapFree` at `0x180013289`
- `KERNEL32!HeapFree` at `0x1800132a5`
- `KERNEL32!HeapAlloc` at `0x180012ae8`
- `KERNEL32!HeapAlloc` at `0x180012b4d`
- `KERNEL32!HeapAlloc` at `0x180012cdc`
- `KERNEL32!HeapAlloc` at `0x180012d71`
- `KERNEL32!HeapAlloc` at `0x180012ae8`
- `KERNEL32!HeapAlloc` at `0x180012b4d`
- `KERNEL32!HeapAlloc` at `0x180012cdc`
- `KERNEL32!HeapAlloc` at `0x180012d71`

## string_xrefs

- `0x180013020`: `AddFilterInterface: Error %d adding frag cache filter to %ws`

## pseudocode

```c
__int64 __fastcall AddFilterInterface(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 v6; // r15
  __int128 *v7; // r9
  __int64 v9; // rdx
  __int64 PointerToTocEntry; // rax
  __int64 v11; // r9
  __int64 v12; // r13
  unsigned int v13; // edx
  __int64 v14; // rcx
  _QWORD *v15; // rsi
  __int64 v16; // r12
  __int64 v17; // rcx
  unsigned int *v18; // r14
  unsigned int v19; // r15d
  void *v20; // rax
  __int64 v21; // r8
  const wchar_t *v22; // rdx
  char *v23; // rax
  __int64 *v24; // rdx
  __int64 v25; // r11
  unsigned int v26; // r15d
  char *v27; // r8
  __int64 v28; // r10
  __int64 v29; // rdx
  __int64 v30; // r9
  char *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r9
  unsigned int v34; // ecx
  _QWORD *v35; // r14
  __int64 v36; // rax
  unsigned int *v37; // rdi
  unsigned int v38; // r13d
  void *v39; // rax
  void *v40; // r8
  char *v41; // rax
  void *v42; // r8
  __int128 *v43; // r9
  __int64 v44; // r13
  unsigned int v45; // r9d
  char *v46; // r10
  __int64 v47; // r11
  __int64 v48; // rdx
  __int64 v49; // r8
  char *v50; // rcx
  __int64 v51; // rax
  __int64 v52; // r8
  unsigned int v53; // ecx
  void **v54; // r13
  InterfaceContainer *v55; // rcx
  unsigned int v56; // eax
  unsigned int v57; // edi
  __int64 v58; // r9
  __int128 *v59; // r9
  __int64 v60; // r9
  __int128 *v61; // r9
  unsigned int v62; // eax
  InterfaceContainer *v63; // rcx
  const wchar_t *v64; // rdx
  __int64 v65; // r9
  __int128 *v66; // r9
  unsigned int v67; // eax
  __int64 v68; // r9
  __int128 *v69; // r9
  void *v70; // r8
  void *v71; // r8
  __int128 *v72; // r9
  char v73; // al
  __int64 v74; // r8
  __int128 *v75; // r9
  __int128 *v76; // r9
  enum _PfForwardAction v77; // [rsp+40h] [rbp-AA8h]
  enum _PfForwardAction v78; // [rsp+44h] [rbp-AA4h]
  __int128 v80; // [rsp+50h] [rbp-A98h] BYREF
  int v81; // [rsp+60h] [rbp-A88h] BYREF
  __int128 v82; // [rsp+64h] [rbp-A84h]
  __int128 v83; // [rsp+74h] [rbp-A74h]
  int v84; // [rsp+84h] [rbp-A64h]
  int v85; // [rsp+90h] [rbp-A58h] BYREF
  char v86[2044]; // [rsp+94h] [rbp-A54h] BYREF
  char v87[528]; // [rsp+890h] [rbp-258h] BYREF

  LODWORD(v6) = 0;
  v85 = 0;
  memset_0(v86, 0, sizeof(v86));
  v81 = 0;
  v84 = 0;
  v82 = 0;
  v83 = 0;
  v80 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v81) = 0;
    v7 = &v80;
    if ( a1 != -688 )
      LODWORD(v7) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: AddFilterInterface",
      (_DWORD)v7,
      *(_QWORD *)(a1 + 72),
      (__int64)&v81);
  }
  *(_QWORD *)(a1 + 96) = -1;
  SetGlobalFilterOnIf(a1, a2);
  if ( !*(_DWORD *)(a1 + 516) )
    return AddV6FilterInterface(a1, a2, a3);
  GetPointerToTocEntry(4294901761LL, a2);
  PointerToTocEntry = GetPointerToTocEntry(4294901762LL, v9);
  v12 = PointerToTocEntry;
  if ( v11 )
  {
    if ( *(_DWORD *)(v11 + 4) )
    {
      v13 = *(_DWORD *)(a2 + 4);
      if ( *(_DWORD *)(v11 + 12) < v13 )
      {
        v14 = a2 + *(unsigned int *)(v11 + 12);
        if ( v14 )
        {
          if ( *(_DWORD *)(v14 + 4) || *(_DWORD *)(v14 + 8) == 1 )
          {
            v78 = PF_ACTION_FORWARD;
            v15 = 0;
            LODWORD(v16) = 0;
LABEL_21:
            if ( *(_DWORD *)(v11 + 4) )
            {
              if ( *(_DWORD *)(v11 + 12) < v13 )
              {
                v18 = (unsigned int *)(a2 + *(unsigned int *)(v11 + 12));
                if ( v18 )
                {
                  v16 = v18[1];
                  v19 = 28 * v16 + 12;
                  v20 = HeapAlloc(IPRouterHeap, 0, v19);
                  *(_QWORD *)(a1 + 112) = v20;
                  if ( !v20 )
                  {
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
                      return 8;
                    v21 = v19;
                    v22 = L"AddFilterInterface: Error allocating %d bytes for in filters";
                    goto LABEL_60;
                  }
                  memcpy_0(v20, v18, v19);
                  LODWORD(v6) = 0;
                  v78 = v18[2];
                  if ( (_DWORD)v16 )
                  {
                    v23 = (char *)HeapAlloc(IPRouterHeap, 0, (unsigned int)(80 * v16 + 8));
                    v15 = v23;
                    if ( !v23 )
                    {
                      HeapFree(IPRouterHeap, 0, *(LPVOID *)(a1 + 112));
                      *(_QWORD *)(a1 + 112) = 0;
                      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                      {
                        LOWORD(v85) = 0;
                        LOWORD(v81) = 0;
                        FormatRRASErrorString(
                          &v85,
                          L"AddFilterInterface: Error allocating %d bytes",
                          (unsigned int)(80 * v16 + 8));
                        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                        {
                          v24 = RasRtrmgrParamTraceInfo;
LABEL_62:
                          v43 = &v80;
                          if ( a1 != -688 )
                            LODWORD(v43) = a1 + 688;
                          McTemplateU0zjzz_EventWriteTransfer(
                            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                            (_DWORD)v24,
                            (unsigned int)&v85,
                            (_DWORD)v43,
                            *(_QWORD *)(a1 + 72),
                            (__int64)&v81);
                        }
                      }
                      return 8;
                    }
                    v25 = 0;
                    v26 = 0;
                    v27 = &v23[64 * v16];
                    v28 = 0;
                    do
                    {
                      v29 = v28 << 6;
                      v30 = 0;
                      *(_QWORD *)((char *)v15 + v29) = 0;
                      *(_DWORD *)((char *)v15 + v29 + 8) = 0;
                      do
                      {
                        v31 = &v27[4 * v25];
                        v25 = (unsigned int)(v25 + 1);
                        v32 = v30 + 8 * v28;
                        ++v30;
                        v15[v32 + 2] = v31;
                      }
                      while ( v30 != 4 );
                      v33 = 7 * v28;
                      **(_DWORD **)((char *)v15 + v29 + 16) = v18[7 * v28 + 3];
                      **(_DWORD **)((char *)v15 + v29 + 24) = v18[7 * v28 + 4];
                      **(_DWORD **)((char *)v15 + v29 + 32) = v18[7 * v28 + 5];
                      **(_DWORD **)((char *)v15 + v29 + 40) = v18[7 * v28 + 6];
                      v34 = v18[7 * v28 + 7];
                      *(_DWORD *)((char *)v15 + v29 + 48) = v34;
                      *(_DWORD *)((char *)v15 + v29 + 52) = v18[7 * v28 + 8];
                      if ( v34 == 6 && (v18[v33 + 8] & 0x40) != 0 )
                        *(_DWORD *)((char *)v15 + v29) |= 1u;
                      ++v26;
                      *(_WORD *)((char *)v15 + v29 + 56) = v18[v33 + 9];
                      *(_WORD *)((char *)v15 + v29 + 58) = HIWORD(v18[v33 + 9]);
                      ++v28;
                      *(_DWORD *)((char *)v15 + v29 + 60) = 0;
                    }
                    while ( v26 < (unsigned int)v16 );
                    LODWORD(v6) = 0;
                  }
                }
              }
            }
LABEL_40:
            v77 = PF_ACTION_FORWARD;
            v35 = 0;
            if ( v12 )
            {
              if ( *(_DWORD *)(v12 + 4) )
              {
                v36 = *(unsigned int *)(v12 + 12);
                if ( (unsigned int)v36 < *(_DWORD *)(a2 + 4) )
                {
                  v37 = (unsigned int *)(v36 + a2);
                  if ( v37 )
                  {
                    v6 = v37[1];
                    v38 = 28 * v6 + 12;
                    v39 = HeapAlloc(IPRouterHeap, 0, v38);
                    *(_QWORD *)(a1 + 120) = v39;
                    if ( !v39 )
                    {
                      v40 = *(void **)(a1 + 112);
                      if ( v40 )
                      {
                        HeapFree(IPRouterHeap, 0, v40);
                        *(_QWORD *)(a1 + 112) = 0;
                      }
                      if ( v15 )
                        HeapFree(IPRouterHeap, 0, v15);
                      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
                        return 8;
                      v22 = L"AddFilterInterface: Error allocating %d bytes for out filters";
                      goto LABEL_59;
                    }
                    memcpy_0(v39, v37, v38);
                    v77 = v37[2];
                    if ( (_DWORD)v6 )
                    {
                      v38 = 80 * v6 + 8;
                      v41 = (char *)HeapAlloc(IPRouterHeap, 0, v38);
                      v35 = v41;
                      if ( !v41 )
                      {
                        v42 = *(void **)(a1 + 112);
                        if ( v42 )
                        {
                          HeapFree(IPRouterHeap, 0, v42);
                          *(_QWORD *)(a1 + 112) = 0;
                        }
                        if ( v15 )
                          HeapFree(IPRouterHeap, 0, v15);
                        HeapFree(IPRouterHeap, 0, *(LPVOID *)(a1 + 120));
                        *(_QWORD *)(a1 + 120) = 0;
                        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
                          return 8;
                        v22 = L"AddFilterInterface: Error allocating %d bytes";
LABEL_59:
                        v21 = v38;
LABEL_60:
                        LOWORD(v85) = 0;
                        LOWORD(v81) = 0;
                        FormatRRASErrorString(&v85, v22, v21);
                        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                        {
                          v24 = RasRtrMgrParamTraceError;
                          goto LABEL_62;
                        }
                        return 8;
                      }
                      v44 = 0;
                      v45 = 0;
                      v46 = &v41[64 * v6];
                      v47 = 0;
                      do
                      {
                        v48 = v47 << 6;
                        v49 = 0;
                        *(_QWORD *)((char *)v35 + v48) = 0;
                        *(_DWORD *)((char *)v35 + v48 + 8) = 0;
                        do
                        {
                          v50 = &v46[4 * v44];
                          v44 = (unsigned int)(v44 + 1);
                          v51 = v49 + 8 * v47;
                          ++v49;
                          v35[v51 + 2] = v50;
                        }
                        while ( v49 != 4 );
                        v52 = 7 * v47;
                        **(_DWORD **)((char *)v35 + v48 + 16) = v37[7 * v47 + 3];
                        **(_DWORD **)((char *)v35 + v48 + 24) = v37[7 * v47 + 4];
                        **(_DWORD **)((char *)v35 + v48 + 32) = v37[7 * v47 + 5];
                        **(_DWORD **)((char *)v35 + v48 + 40) = v37[7 * v47 + 6];
                        v53 = v37[7 * v47 + 7];
                        *(_DWORD *)((char *)v35 + v48 + 48) = v53;
                        *(_DWORD *)((char *)v35 + v48 + 52) = v37[7 * v47 + 8];
                        if ( v53 == 6 && (v37[v52 + 8] & 0x40) != 0 )
                          *(_DWORD *)((char *)v35 + v48) |= 1u;
                        ++v45;
                        *(_WORD *)((char *)v35 + v48 + 56) = v37[v52 + 9];
                        *(_WORD *)((char *)v35 + v48 + 58) = HIWORD(v37[v52 + 9]);
                        ++v47;
                        *(_DWORD *)((char *)v35 + v48 + 60) = 0;
                      }
                      while ( v45 < (unsigned int)v6 );
                    }
                  }
                }
              }
            }
            GetInterfaceFriendlyName(*(_QWORD *)(a1 + 72), v87);
            v54 = (void **)(a1 + 96);
            v56 = InterfaceContainer::AddInterface(v55, 0, v78, v77, 0, 0, (void **)(a1 + 96), PF_IPV4);
            v57 = v56;
            if ( v56 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              {
                v58 = *(_QWORD *)(a1 + 72);
                LOWORD(v85) = 0;
                LOWORD(v81) = 0;
                FormatRRASErrorString(&v85, L"AddFilterInterface: Err %d creating filter i/f for %ws", v56, v58);
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  v59 = &v80;
                  if ( a1 != -688 )
                    LODWORD(v59) = a1 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)&v85,
                    (_DWORD)v59,
                    *(_QWORD *)(a1 + 72),
                    (__int64)&v81);
                }
              }
              *a3 = 1;
              goto LABEL_108;
            }
            v57 = PfInternAddGlobalFilterToInterface(*v54);
            if ( v57 )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
              {
                v60 = *(_QWORD *)(a1 + 72);
                LOWORD(v85) = 0;
                LOWORD(v81) = 0;
                FormatRRASErrorString(&v85, L"AddFilterInterface: Error %d adding frag cache filter to %ws", v57, v60);
                if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v61 = &v80;
                  if ( a1 != -688 )
                    LODWORD(v61) = a1 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)&v85,
                    (_DWORD)v61,
                    *(_QWORD *)(a1 + 72),
                    (__int64)&v81);
                }
              }
              v57 = 0;
            }
            if ( (_DWORD)v6 + (_DWORD)v16
              && (v62 = PfInternAddFiltersToInterface(*v54, (__int64)v35, 0), (v57 = v62) != 0) )
            {
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              {
LABEL_99:
                *a3 = 1;
                InterfaceContainer::DeleteInterface(v63, *v54);
LABEL_108:
                if ( v15 )
                  HeapFree(IPRouterHeap, 0, v15);
                if ( v35 )
                  HeapFree(IPRouterHeap, 0, v35);
                if ( v57 )
                {
                  v70 = *(void **)(a1 + 112);
                  *v54 = (void *)-1LL;
                  if ( v70 )
                  {
                    HeapFree(IPRouterHeap, 0, v70);
                    *(_QWORD *)(a1 + 112) = 0;
                  }
                  v71 = *(void **)(a1 + 120);
                  if ( v71 )
                  {
                    HeapFree(IPRouterHeap, 0, v71);
                    *(_QWORD *)(a1 + 120) = 0;
                  }
                }
                if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
                {
                  LOWORD(v81) = 0;
                  v72 = &v80;
                  if ( a1 != -688 )
                    LODWORD(v72) = a1 + 688;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)L"SetInterfaceFilterInfo",
                    (_DWORD)v72,
                    *(_QWORD *)(a1 + 72),
                    (__int64)&v81);
                }
                return v57;
              }
              v64 = L"AddFilterInterface: Err %d setting filters on %ws";
            }
            else
            {
              if ( !*(_DWORD *)(a1 + 512) || (v62 = BindFilterInterface(a1), (v57 = v62) == 0) )
              {
                if ( *(_DWORD *)(a1 + 136) )
                {
                  v67 = PfInternAddGlobalFilterToInterface(*v54);
                  v57 = v67;
                  if ( v67 )
                  {
                    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                    {
                      v68 = *(_QWORD *)(a1 + 72);
                      LOWORD(v85) = 0;
                      LOWORD(v81) = 0;
                      FormatRRASErrorString(&v85, L"AddFilterInterface: Error %d adding frag filter to %ws", v67, v68);
                      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                      {
                        v69 = &v80;
                        if ( a1 != -688 )
                          LODWORD(v69) = a1 + 688;
                        McTemplateU0zjzz_EventWriteTransfer(
                          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                          (unsigned int)RasRtrMgrParamTraceError,
                          (unsigned int)&v85,
                          (_DWORD)v69,
                          *(_QWORD *)(a1 + 72),
                          (__int64)&v81);
                      }
                    }
                    *(_DWORD *)(a1 + 136) = 0;
                    v57 = 0;
                  }
                }
                goto LABEL_108;
              }
              if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
                goto LABEL_99;
              v64 = L"AddFilterInterface: Err %d binding filters on %ws";
            }
            v65 = *(_QWORD *)(a1 + 72);
            LOWORD(v85) = 0;
            LOWORD(v81) = 0;
            FormatRRASErrorString(&v85, v64, v62, v65);
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            {
              v66 = &v80;
              if ( a1 != -688 )
                LODWORD(v66) = a1 + 688;
              McTemplateU0zjzz_EventWriteTransfer(
                (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                (unsigned int)RasRtrMgrParamTraceError,
                (unsigned int)&v85,
                (_DWORD)v66,
                *(_QWORD *)(a1 + 72),
                (__int64)&v81);
            }
            goto LABEL_99;
          }
        }
      }
    }
  }
  if ( PointerToTocEntry )
  {
    if ( *(_DWORD *)(PointerToTocEntry + 4) )
    {
      v13 = *(_DWORD *)(a2 + 4);
      if ( *(_DWORD *)(PointerToTocEntry + 12) < v13 )
      {
        v17 = a2 + *(unsigned int *)(PointerToTocEntry + 12);
        if ( v17 )
        {
          if ( *(_DWORD *)(v17 + 4) || *(_DWORD *)(v17 + 8) == 1 )
          {
            v78 = PF_ACTION_FORWARD;
            v15 = 0;
            LODWORD(v16) = 0;
            if ( !v11 )
              goto LABEL_40;
            goto LABEL_21;
          }
        }
      }
    }
  }
  v73 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v74 = *(_QWORD *)(a1 + 72);
    LOWORD(v85) = 0;
    LOWORD(v81) = 0;
    FormatRRASErrorString(
      &v85,
      L"AddFilterInterface: Both filters info are NULL or info size 0 for both for %ws, so leaving",
      v74);
    v73 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v75 = &v80;
      if ( a1 != -688 )
        LODWORD(v75) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v85,
        (_DWORD)v75,
        *(_QWORD *)(a1 + 72),
        (__int64)&v81);
      v73 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( v73 < 0 )
  {
    LOWORD(v81) = 0;
    v76 = &v80;
    if ( a1 != -688 )
      LODWORD(v76) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Leaving: AddFilterInterface",
      (_DWORD)v76,
      *(_QWORD *)(a1 + 72),
      (__int64)&v81);
  }
  return 0;
}

```

## disassembly

```asm
0x180012914  push    rbx
0x180012916  push    rsi
0x180012917  push    rdi
0x180012918  push    r12
0x18001291a  push    r13
0x18001291c  push    r14
0x18001291e  push    r15
0x180012920  sub     rsp, 0AB0h
0x180012927  mov     rax, cs:__security_cookie
0x18001292e  xor     rax, rsp
0x180012931  mov     [rsp+0AE8h+var_48], rax
0x180012939  mov     rsi, r8
0x18001293c  mov     [rsp+0AE8h+var_AA0], r8
0x180012941  mov     rdi, rdx
0x180012944  mov     rbx, rcx
0x180012947  xor     r15d, r15d
0x18001294a  lea     rcx, [rsp+0AE8h+var_A54]; void *
0x180012952  xor     edx, edx; Val
0x180012954  mov     [rsp+0AE8h+var_A58], r15d
0x18001295c  mov     r8d, 7FCh; Size
0x180012962  call    memset_0
0x180012967  xor     eax, eax
0x180012969  mov     [rsp+0AE8h+var_A88], r15d
0x18001296e  xorps   xmm0, xmm0
0x180012971  mov     [rsp+0AE8h+var_A64], eax
0x180012978  mov     al, byte ptr cs:Microsoft_Windows_RRASEnableBits
0x18001297e  lea     r12, RasRtrmgrParamTraceInfo
0x180012985  and     al, 80h
0x180012987  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001298e  mov     byte ptr [rsp+0AE8h+var_AA8], al
0x180012992  movups  [rsp+0AE8h+var_A84], xmm0
0x180012997  movups  [rsp+0AE8h+var_A74], xmm0
0x18001299c  movups  [rsp+0AE8h+var_A98], xmm0
0x1800129a1  jz      short loc_1800129E1
0x1800129a3  lea     rax, [rbx+2B0h]
0x1800129aa  mov     word ptr [rsp+0AE8h+var_A88], r15w
0x1800129b0  test    rax, rax
0x1800129b3  lea     r9, [rsp+0AE8h+var_A98]
0x1800129b8  lea     r8, aEnteredAddfilt; "Entered: AddFilterInterface"
0x1800129bf  mov     rdx, r12
0x1800129c2  cmovnz  r9, rax
0x1800129c6  mov     rcx, r14
0x1800129c9  lea     rax, [rsp+0AE8h+var_A88]
0x1800129ce  mov     [rsp+0AE8h+var_AC0], rax
0x1800129d3  mov     rax, [rbx+48h]
0x1800129d7  mov     [rsp+0AE8h+var_AC8], rax
0x1800129dc  call    McTemplateU0zjzz_EventWriteTransfer
0x1800129e1  mov     rdx, rdi
0x1800129e4  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x1800129ec  mov     rcx, rbx
0x1800129ef  call    SetGlobalFilterOnIf
0x1800129f4  mov     rdx, rdi
0x1800129f7  cmp     [rbx+204h], r15d
0x1800129fe  jnz     short loc_180012A10
0x180012a00  mov     r8, rsi
0x180012a03  mov     rcx, rbx
0x180012a06  call    AddV6FilterInterface
0x180012a0b  jmp     loc_1800133C6
0x180012a10  mov     ecx, 0FFFF0001h
0x180012a15  call    GetPointerToTocEntry
0x180012a1a  mov     ecx, 0FFFF0002h
0x180012a1f  mov     r9, rax
0x180012a22  call    GetPointerToTocEntry
0x180012a27  mov     r13, rax
0x180012a2a  test    r9, r9
0x180012a2d  jz      short loc_180012A60
0x180012a2f  cmp     [r9+4], r15d
0x180012a33  jz      short loc_180012A60
0x180012a35  mov     edx, [rdi+4]
0x180012a38  cmp     [r9+0Ch], edx
0x180012a3c  jnb     short loc_180012A60
0x180012a3e  mov     ecx, [r9+0Ch]
0x180012a42  add     rcx, rdi
0x180012a45  jz      short loc_180012A60
0x180012a47  cmp     [rcx+4], r15d
0x180012a4b  jnz     short loc_180012A53
0x180012a4d  cmp     dword ptr [rcx+8], 1
0x180012a51  jnz     short loc_180012A60
0x180012a53  mov     [rsp+0AE8h+var_AA4], r15d
0x180012a58  mov     rsi, r15
0x180012a5b  mov     r12d, r15d
0x180012a5e  jmp     short loc_180012AAF
0x180012a60  test    r13, r13
0x180012a63  jz      loc_180013305
0x180012a69  cmp     [rax+4], r15d
0x180012a6d  jz      loc_180013305
0x180012a73  mov     edx, [rdi+4]
0x180012a76  cmp     [rax+0Ch], edx
0x180012a79  jnb     loc_180013305
0x180012a7f  mov     ecx, [rax+0Ch]
0x180012a82  add     rcx, rdi
0x180012a85  jz      loc_180013305
0x180012a8b  cmp     [rcx+4], r15d
0x180012a8f  jnz     short loc_180012A9B
0x180012a91  cmp     dword ptr [rcx+8], 1
0x180012a95  jnz     loc_180013305
0x180012a9b  mov     [rsp+0AE8h+var_AA4], r15d
0x180012aa0  mov     rsi, r15
0x180012aa3  mov     r12d, r15d
0x180012aa6  test    r9, r9
0x180012aa9  jz      loc_180012C92
0x180012aaf  cmp     [r9+4], r15d
0x180012ab3  jz      loc_180012C92
0x180012ab9  cmp     [r9+0Ch], edx
0x180012abd  jnb     loc_180012C92
0x180012ac3  mov     r14d, [r9+0Ch]
0x180012ac7  add     r14, rdi
0x180012aca  jz      loc_180012C92
0x180012ad0  mov     r12d, [r14+4]
0x180012ad4  xor     edx, edx; dwFlags
0x180012ad6  mov     rcx, cs:IPRouterHeap; hHeap
0x180012add  imul    r15d, r12d, 1Ch
0x180012ae1  add     r15d, 0Ch
0x180012ae5  mov     r8d, r15d; dwBytes
0x180012ae8  call    cs:__imp_HeapAlloc
0x180012aee  mov     [rbx+70h], rax
0x180012af2  test    rax, rax
0x180012af5  jnz     short loc_180012B13
0x180012af7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180012afe  jz      loc_180012E4A
0x180012b04  mov     r8d, r15d
0x180012b07  lea     rdx, aAddfilterinter_3; "AddFilterInterface: Error allocating %d"...
0x180012b0e  jmp     loc_180012DE4
0x180012b13  mov     r8d, r15d; Size
0x180012b16  mov     rdx, r14; Src
0x180012b19  mov     rcx, rax; void *
0x180012b1c  call    memcpy_0
0x180012b21  mov     eax, [r14+8]
0x180012b25  xor     r15d, r15d
0x180012b28  mov     [rsp+0AE8h+var_AA4], eax
0x180012b2c  test    r12d, r12d
0x180012b2f  jz      loc_180012C92
0x180012b35  mov     rcx, cs:IPRouterHeap; hHeap
0x180012b3c  lea     r15d, [r12+r12*4]
0x180012b40  shl     r15d, 4
0x180012b44  xor     edx, edx; dwFlags
0x180012b46  add     r15d, 8
0x180012b4a  mov     r8d, r15d; dwBytes
0x180012b4d  call    cs:__imp_HeapAlloc
0x180012b53  mov     rsi, rax
0x180012b56  test    rax, rax
0x180012b59  jnz     short loc_180012BBE
0x180012b5b  mov     r8, [rbx+70h]; lpMem
0x180012b5f  xor     edx, edx; dwFlags
0x180012b61  mov     rcx, cs:IPRouterHeap; hHeap
0x180012b68  call    cs:__imp_HeapFree
0x180012b6e  xor     edi, edi
0x180012b70  mov     [rbx+70h], rdi
0x180012b74  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180012b7b  jge     loc_180012E4A
0x180012b81  mov     r8d, r15d
0x180012b84  mov     word ptr [rsp+0AE8h+var_A58], di
0x180012b8c  lea     rdx, aAddfilterinter_4; "AddFilterInterface: Error allocating %d"...
0x180012b93  mov     word ptr [rsp+0AE8h+var_A88], di
0x180012b98  lea     rcx, [rsp+0AE8h+var_A58]
0x180012ba0  call    FormatRRASErrorString
0x180012ba5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180012bac  jge     loc_180012E4A
0x180012bb2  lea     rdx, RasRtrmgrParamTraceInfo
0x180012bb9  jmp     loc_180012E10
0x180012bbe  mov     r8, r12
0x180012bc1  xor     r11d, r11d
0x180012bc4  shl     r8, 6
0x180012bc8  xor     r15d, r15d
0x180012bcb  add     r8, rsi
0x180012bce  test    r12d, r12d
0x180012bd1  jz      loc_180012C92
0x180012bd7  xor     r10d, r10d
0x180012bda  mov     rdx, r10
0x180012bdd  shl     rdx, 6
0x180012be1  xor     r9d, r9d
0x180012be4  mov     qword ptr [rdx+rsi], 0
0x180012bec  mov     dword ptr [rdx+rsi+8], 0
0x180012bf4  lea     rcx, [r8+r11*4]
0x180012bf8  inc     r11d
0x180012bfb  lea     rax, [r9+r10*8]
0x180012bff  inc     r9
0x180012c02  mov     [rsi+rax*8+10h], rcx
0x180012c07  cmp     r9, 4
0x180012c0b  jnz     short loc_180012BF4
0x180012c0d  mov     rcx, [rdx+rsi+10h]
0x180012c12  imul    r9, r10, 1Ch
0x180012c16  mov     eax, [r9+r14+0Ch]
0x180012c1b  mov     [rcx], eax
0x180012c1d  mov     eax, [r9+r14+10h]
0x180012c22  mov     rcx, [rdx+rsi+18h]
0x180012c27  mov     [rcx], eax
0x180012c29  mov     eax, [r9+r14+14h]
0x180012c2e  mov     rcx, [rdx+rsi+20h]
0x180012c33  mov     [rcx], eax
0x180012c35  mov     eax, [r9+r14+18h]
0x180012c3a  mov     rcx, [rdx+rsi+28h]
0x180012c3f  mov     [rcx], eax
0x180012c41  mov     ecx, [r9+r14+1Ch]
0x180012c46  mov     [rdx+rsi+30h], ecx
0x180012c4a  mov     eax, [r9+r14+20h]
0x180012c4f  mov     [rdx+rsi+34h], eax
0x180012c53  cmp     ecx, 6
0x180012c56  jnz     short loc_180012C64
0x180012c58  test    byte ptr [r9+r14+20h], 40h
0x180012c5e  jz      short loc_180012C64
0x180012c60  or      dword ptr [rdx+rsi], 1
0x180012c64  movzx   eax, word ptr [r9+r14+24h]
0x180012c6a  inc     r15d
0x180012c6d  mov     [rdx+rsi+38h], ax
0x180012c72  movzx   eax, word ptr [r9+r14+26h]
0x180012c78  mov     [rdx+rsi+3Ah], ax
0x180012c7d  xor     eax, eax
0x180012c7f  inc     r10
0x180012c82  mov     [rdx+rsi+3Ch], eax
0x180012c86  cmp     r15d, r12d
0x180012c89  jb      loc_180012BDA
0x180012c8f  xor     r15d, r15d
0x180012c92  mov     [rsp+0AE8h+var_AA8], r15d
0x180012c97  mov     r14, r15
0x180012c9a  test    r13, r13
0x180012c9d  jz      loc_180012F2C
0x180012ca3  cmp     dword ptr [r13+4], 0
0x180012ca8  jz      loc_180012F2C
0x180012cae  mov     eax, [r13+0Ch]
0x180012cb2  cmp     eax, [rdi+4]
0x180012cb5  jnb     loc_180012F2C
0x180012cbb  add     rdi, rax
0x180012cbe  jz      loc_180012F2C
0x180012cc4  mov     r15d, [rdi+4]
0x180012cc8  xor     edx, edx; dwFlags
0x180012cca  mov     rcx, cs:IPRouterHeap; hHeap
0x180012cd1  imul    r13d, r15d, 1Ch
0x180012cd5  add     r13d, 0Ch
0x180012cd9  mov     r8d, r13d; dwBytes
0x180012cdc  call    cs:__imp_HeapAlloc
0x180012ce2  mov     [rbx+78h], rax
0x180012ce6  test    rax, rax
0x180012ce9  jnz     short loc_180012D3B
0x180012ceb  mov     r8, [rbx+70h]; lpMem
0x180012cef  test    r8, r8
0x180012cf2  jz      short loc_180012D0B
0x180012cf4  mov     rcx, cs:IPRouterHeap; hHeap
0x180012cfb  xor     edx, edx; dwFlags
0x180012cfd  call    cs:__imp_HeapFree
0x180012d03  mov     qword ptr [rbx+70h], 0
0x180012d0b  test    rsi, rsi
0x180012d0e  jz      short loc_180012D22
0x180012d10  mov     rcx, cs:IPRouterHeap; hHeap
0x180012d17  mov     r8, rsi; lpMem
0x180012d1a  xor     edx, edx; dwFlags
0x180012d1c  call    cs:__imp_HeapFree
0x180012d22  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180012d29  jz      loc_180012E4A
0x180012d2f  lea     rdx, aAddfilterinter_2; "AddFilterInterface: Error allocating %d"...
0x180012d36  jmp     loc_180012DE1
0x180012d3b  mov     r8d, r13d; Size
0x180012d3e  mov     rdx, rdi; Src
0x180012d41  mov     rcx, rax; void *
0x180012d44  call    memcpy_0
0x180012d49  mov     eax, [rdi+8]
0x180012d4c  mov     [rsp+0AE8h+var_AA8], eax
0x180012d50  test    r15d, r15d
0x180012d53  jz      loc_180012F2C
0x180012d59  mov     rcx, cs:IPRouterHeap; hHeap
0x180012d60  lea     r13d, [r15+r15*4]
0x180012d64  shl     r13d, 4
0x180012d68  xor     edx, edx; dwFlags
0x180012d6a  add     r13d, 8
0x180012d6e  mov     r8d, r13d; dwBytes
0x180012d71  call    cs:__imp_HeapAlloc
0x180012d77  mov     r14, rax
0x180012d7a  test    rax, rax
0x180012d7d  jnz     loc_180012E54
0x180012d83  mov     r8, [rbx+70h]; lpMem
0x180012d87  test    r8, r8
0x180012d8a  jz      short loc_180012D9F
0x180012d8c  mov     rcx, cs:IPRouterHeap; hHeap
0x180012d93  xor     edx, edx; dwFlags
0x180012d95  call    cs:__imp_HeapFree
0x180012d9b  mov     [rbx+70h], r14
0x180012d9f  test    rsi, rsi
0x180012da2  jz      short loc_180012DB6
0x180012da4  mov     rcx, cs:IPRouterHeap; hHeap
0x180012dab  mov     r8, rsi; lpMem
0x180012dae  xor     edx, edx; dwFlags
0x180012db0  call    cs:__imp_HeapFree
0x180012db6  mov     r8, [rbx+78h]; lpMem
0x180012dba  xor     edx, edx; dwFlags
0x180012dbc  mov     rcx, cs:IPRouterHeap; hHeap
0x180012dc3  call    cs:__imp_HeapFree
0x180012dc9  mov     qword ptr [rbx+78h], 0
0x180012dd1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180012dd8  jz      short loc_180012E4A
0x180012dda  lea     rdx, aAddfilterinter_4; "AddFilterInterface: Error allocating %d"...
0x180012de1  mov     r8d, r13d
0x180012de4  xor     eax, eax
0x180012de6  lea     rcx, [rsp+0AE8h+var_A58]
0x180012dee  mov     word ptr [rsp+0AE8h+var_A58], ax
0x180012df6  mov     word ptr [rsp+0AE8h+var_A88], ax
0x180012dfb  call    FormatRRASErrorString
0x180012e00  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180012e07  jz      short loc_180012E4A
0x180012e09  lea     rdx, RasRtrMgrParamTraceError
0x180012e10  lea     rax, [rbx+2B0h]
  ... truncated ...
```
