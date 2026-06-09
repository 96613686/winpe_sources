# DumpModuleTable(DebugClient *,ulong,ushort const *,unsigned __int64)

- ea: `0x1802a6200`
- end: `0x1802a6eb9`
- name: `?DumpModuleTable@@YAXPEAVDebugClient@@KPEBG_K@Z`
- size: `3257`
- prototype: `void __fastcall(struct DebugClient *, unsigned int, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1802ab1b0`
- `0x1802ab4ec`

## callees

- `0x1800727b8`
- `0x180072c8c`
- `0x180075b88`
- `0x1800804c4`
- `0x180085700`
- `0x1800986ec`
- `0x1800b3bd0`
- `0x1800c899c`
- `0x1800ce2d4`
- `0x1800f0f40`
- `0x1800f2998`
- `0x18019679c`
- `0x18019a800`
- `0x1802650f4`
- `0x1802667fc`
- `0x1802a55c8`
- `0x1802a6200`
- `0x1802aa8f0`
- `0x1802e7ecc`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802a6465`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1802a6465`
- `dbghelp!SymGetModuleInfoW64` at `0x1802a6637`
- `dbghelp!SymGetModuleInfoW64` at `0x1802a6637`
- `dbghelp!SymMatchStringW` at `0x1802a65c6`
- `dbghelp!SymMatchStringW` at `0x1802a65c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1802a6ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x1802a6b50`
- `OLEAUT32!__imp_SysFreeString` at `0x1802a6ac3`
- `OLEAUT32!__imp_SysFreeString` at `0x1802a6b50`

## string_xrefs

- `0x1802a6837`: `ntdll`
- `0x1802a63a9`: `<link cmd="%s">start</link>%Y{as}    end%Y{as}        module name\n`
- `0x1802a63ee`: `<link cmd="%s">Browse full module list</link>\n`
- `0x1802a63bd`: `start%Y{as}    end%Y{as}        <link cmd="%s">module name</link>\n`
- `0x1802a6961`: `<link cmd="lmDvm%s">%s</link>`
- `0x1802a6ad1`: `(service symbols)        `
- `0x1802a6ab2`: `(service symbols: %s)        `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DumpModuleTable(struct DebugClient *a1, __int64 a2, const unsigned __int16 *a3, unsigned __int64 a4)
{
  const WCHAR *v5; // r13
  unsigned int v6; // r14d
  struct DebugClient *v7; // rsi
  __int64 v8; // r8
  int v9; // edi
  int v10; // eax
  __int16 *v11; // rbx
  int v12; // eax
  ImageInfo *v13; // rbx
  ImageInfo *v14; // rcx
  ImageInfo *v15; // rsi
  ImageInfo *v16; // rdi
  const wchar_t *v17; // rdx
  const wchar_t *v18; // rcx
  ImageInfo *v19; // r8
  ImageInfo *v20; // rax
  ImageInfo *v21; // rdx
  ImageInfo *v22; // rax
  ImageInfo *v23; // rdx
  ImageInfo *v24; // rax
  const WCHAR *v25; // rcx
  BOOL matched; // eax
  ImageInfo *v27; // r10
  unsigned int v28; // ecx
  int v29; // r15d
  __int64 v30; // r10
  __int64 v31; // rax
  __int64 v32; // rax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // r10
  int v35; // esi
  __int64 v36; // rax
  struct MachineInfo *v37; // rcx
  unsigned __int16 *v38; // rbx
  struct MachineInfo *v39; // rcx
  unsigned __int64 v40; // r8
  struct MachineInfo *v41; // rcx
  unsigned __int16 *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  int (__fastcall ***v45)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int v46; // ebx
  int (__fastcall *v47)(_QWORD, GUID *, __int64 *); // rbx
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v49)(_QWORD, GUID *, __int64 *); // rbx
  int v50; // eax
  const unsigned __int16 *v51; // rcx
  const wchar_t *v52; // rdx
  const wchar_t *v53; // rdx
  const wchar_t *v54; // rdx
  unsigned int v55; // ebx
  unsigned __int16 *v56; // rax
  unsigned int v57; // eax
  int v58; // edx
  int v59; // edx
  const wchar_t *v60; // rdx
  ImageInfo *v61; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v62; // [rsp+40h] [rbp-C8h]
  BSTR bstrString; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v64; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+58h] [rbp-B0h] BYREF
  BSTR v66; // [rsp+60h] [rbp-A8h] BYREF
  struct DebugClient *v67; // [rsp+68h] [rbp-A0h]
  const unsigned __int16 *v68; // [rsp+70h] [rbp-98h]
  __int64 v69; // [rsp+78h] [rbp-90h]
  struct IMAGE_COR20_HEADER v70; // [rsp+88h] [rbp-80h] BYREF
  _BYTE ModuleInfo[3272]; // [rsp+D8h] [rbp-30h] BYREF
  unsigned __int16 *v72[2]; // [rsp+DA8h] [rbp+CA0h] BYREF
  __int128 v73; // [rsp+DB8h] [rbp+CB0h]
  const unsigned __int16 *v74; // [rsp+DC8h] [rbp+CC0h]
  int v75; // [rsp+DD0h] [rbp+CC8h] BYREF
  __int16 v76; // [rsp+DD4h] [rbp+CCCh]
  __int16 v77; // [rsp+DD6h] [rbp+CCEh] BYREF
  char v78; // [rsp+DD8h] [rbp+CD0h] BYREF

  v69 = -2;
  v5 = a3;
  v68 = a3;
  v6 = a2;
  v7 = a1;
  v67 = a1;
  v61 = 0;
  memset(ModuleInfo, 0, sizeof(ModuleInfo));
  v8 = 4096;
  v9 = a2 & 0x400;
  LODWORD(v62) = v9;
  if ( (a2 & 0x400) == 0 )
  {
    LOWORD(v75) = 0;
    if ( (a2 & 0x10000) == 0 )
      goto LABEL_36;
    v75 = 7143532;
    v76 = 68;
    v10 = a2 & 0x1008;
    if ( v10 == 4096 )
      v77 = 99;
    v11 = &v77;
    if ( v10 == 4096 )
      v11 = (__int16 *)&v78;
    if ( (a2 & 0x200) != 0 )
      *v11++ = 101;
    if ( (a2 & 4) != 0 )
      *v11++ = 107;
    if ( (a2 & 1) != 0 )
      *v11++ = 108;
    if ( (a2 & 0x4000) != 0 )
      *v11++ = 111;
    if ( (a2 & 0x88) == 0x80 )
      *v11++ = 116;
    if ( (a2 & 2) != 0 )
      *v11++ = 117;
    if ( (a2 & 8) != 0 )
      *v11++ = 118;
    v12 = a2 & 0x2070;
    if ( (a2 & 0x2070) != 0 )
    {
      switch ( v12 )
      {
        case 0x20:
          *v11 = 112;
          break;
        case 0x40:
          *v11 = 102;
          break;
        case 0x2000:
          *v11 = 110;
          break;
        default:
          goto LABEL_30;
      }
    }
    else
    {
      *v11 = 105;
    }
    ++v11;
LABEL_30:
    *v11 = 0;
    if ( !v5 && !a4 )
    {
      ExecuteRegisteredCommand(a1, L"lmD", 0, 0);
      if ( (v6 & 0x8000) != 0 )
      {
        DmlOut(L"<link cmd=\"%s\">start</link>%Y{as}    end%Y{as}        module name\n", &v75);
      }
      else
      {
        *(_DWORD *)v11 = 7143539;
        v11[2] = 0;
        DmlOut(L"start%Y{as}    end%Y{as}        <link cmd=\"%s\">module name</link>\n", &v75);
      }
      goto LABEL_37;
    }
    ExecuteRegisteredCommand(a1, L"lmD", 0, 0);
    DmlOut(L"<link cmd=\"%s\">Browse full module list</link>\n", &v75);
LABEL_36:
    dprintf64(L"start%Y{as}    end%Y{as}        module name\n", a2, v8);
  }
LABEL_37:
  v13 = 0;
  v14 = (ImageInfo *)*((_QWORD *)g_Process + 16);
  v61 = v14;
  if ( (v6 & 0x8000) != 0 )
  {
    if ( !v14 )
      goto LABEL_73;
    while ( 1 )
    {
      v15 = 0;
      v16 = v13;
      if ( !v13 )
        goto LABEL_52;
      while ( 1 )
      {
        v17 = *((_DWORD *)v14 + 59) < 2u ? 0LL : (const wchar_t *)*((_QWORD *)v14 + 28);
        v18 = *((_DWORD *)v16 + 59) < 2u ? 0LL : (const wchar_t *)*((_QWORD *)v16 + 28);
        if ( _wcsicmp(v18, v17) >= 0 )
          break;
        v15 = v16;
        v16 = (ImageInfo *)*((_QWORD *)v16 + 218);
        if ( !v16 )
          break;
        v14 = v61;
      }
      if ( !v15 )
        break;
      *((_QWORD *)v15 + 218) = v61;
      v14 = v61;
LABEL_53:
      *((_QWORD *)v14 + 218) = v16;
      v14 = (ImageInfo *)*((_QWORD *)v61 + 1);
      v61 = v14;
      if ( !v14 )
      {
        v9 = v62;
        v7 = v67;
        goto LABEL_73;
      }
    }
    v14 = v61;
LABEL_52:
    v13 = v14;
    goto LABEL_53;
  }
  if ( (v6 & 0x20000) != 0 )
  {
    if ( v14 )
    {
      v19 = v14;
      do
      {
        v20 = v13;
        if ( !v13 )
          goto LABEL_64;
        v21 = 0;
        do
        {
          if ( *((_DWORD *)v20 + 438) > *((_DWORD *)v19 + 438) )
            break;
          v21 = v20;
          v20 = (ImageInfo *)*((_QWORD *)v20 + 218);
        }
        while ( v20 );
        if ( v21 )
        {
          *((_QWORD *)v21 + 218) = v14;
          v14 = v61;
        }
        else
        {
LABEL_64:
          v13 = v14;
        }
        *((_QWORD *)v14 + 218) = v20;
        v14 = (ImageInfo *)*((_QWORD *)v61 + 1);
        v61 = v14;
        v19 = v14;
      }
      while ( v14 );
    }
  }
  else if ( v14 )
  {
    v22 = 0;
    v23 = v14;
    do
    {
      if ( v22 )
      {
        *((_QWORD *)v22 + 218) = v14;
        v14 = v61;
      }
      else
      {
        v13 = v23;
      }
      *((_QWORD *)v14 + 218) = 0;
      v22 = v61;
      v14 = (ImageInfo *)*((_QWORD *)v61 + 1);
      v61 = v14;
      v23 = v14;
    }
    while ( v14 );
  }
LABEL_73:
  v61 = v13;
  if ( v13 )
  {
    v24 = v13;
    while ( 1 )
    {
      if ( !v5 )
        goto LABEL_81;
      if ( (v6 & 0x800) != 0 )
        break;
      if ( *((_DWORD *)v24 + 59) < 2u )
        goto LABEL_79;
      v25 = (const WCHAR *)*((_QWORD *)v24 + 28);
LABEL_80:
      matched = SymMatchStringW(v25, v5, 0);
      v13 = v61;
      if ( !matched )
        goto LABEL_84;
LABEL_81:
      if ( a4 && *((_QWORD *)v13 + 4) > a4 || *((_QWORD *)v13 + 4) + (unsigned __int64)*((unsigned int *)v13 + 10) <= a4 )
      {
LABEL_84:
        v13 = (ImageInfo *)*((_QWORD *)v13 + 218);
        goto LABEL_233;
      }
      *(_DWORD *)ModuleInfo = 3272;
      *(_DWORD *)&ModuleInfo[3264] = 1;
      if ( !SymGetModuleInfoW64(*((HANDLE *)g_Process + 51), *((_QWORD *)v13 + 4), (PIMAGEHLP_MODULEW64)ModuleInfo) )
      {
        memset(ModuleInfo, 0, sizeof(ModuleInfo));
        *(_DWORD *)ModuleInfo = 3272;
        *(_DWORD *)&ModuleInfo[32] = 0;
        CopyNStringW(&ModuleInfo[612]);
      }
      if ( (v6 & 1) != 0 && *(_DWORD *)&ModuleInfo[32] == 5 )
      {
        v27 = v61;
      }
      else
      {
        v27 = v61;
        if ( ((v6 & 0x200) == 0 || (*(_DWORD *)&ModuleInfo[32] & 0xFFFFFFFB) == 0 || *((_DWORD *)v61 + 52) != 1)
          && (!g_Target
           || *((_DWORD *)g_Target + 1026) != 1
           || ((v6 & 2) == 0 || *((_QWORD *)v61 + 4) < *((_QWORD *)g_Target + 31))
           && ((v6 & 4) == 0 || *((_QWORD *)v61 + 4) > *((_QWORD *)g_Target + 31))) )
        {
          if ( v9 )
          {
            dprintf(L"%s\n", *((_QWORD *)v61 + 28));
LABEL_232:
            ThrowInterrupt(v28);
            v13 = (ImageInfo *)*((_QWORD *)v61 + 218);
            goto LABEL_233;
          }
          if ( (v6 & 0x88) != 0 )
          {
            IMAGE_HEADER_INFO::Update(
              (ImageInfo *)((char *)v61 + 48),
              *(struct ProcessInfo **)v61,
              *((_QWORD *)v61 + 4),
              *((void **)v61 + 3),
              0x2DFFu);
            v27 = v61;
          }
          *(_OWORD *)v72 = 0;
          v73 = 0;
          v74 = 0;
          v29 = v6 & 0x10000;
          if ( (v6 & 0x10000) != 0 )
          {
            v72[0] = *((unsigned __int16 **)v27 + 28);
            ExecuteRegisteredCommand(v7, L"lmDm", (const unsigned __int16 **)v72, 1u);
          }
          v72[0] = (unsigned __int16 *)&ModuleInfo[612];
          v72[1] = (unsigned __int16 *)ModInfoSymFile((struct _IMAGEHLP_MODULEW64 *)ModuleInfo);
          if ( *(_DWORD *)(v30 + 980) < 2u )
            v31 = 0;
          else
            v31 = *(_QWORD *)(v30 + 968);
          *(_QWORD *)&v73 = v31;
          if ( *(_DWORD *)(v30 + 548) < 2u )
            v32 = 0;
          else
            v32 = *(_QWORD *)(v30 + 536);
          *((_QWORD *)&v73 + 1) = v32;
          if ( *(_DWORD *)(v30 + 548) < 2u )
            v33 = 0;
          else
            v33 = *(const unsigned __int16 **)(v30 + 536);
          v74 = PathTail(v33);
          if ( (v6 & 0x10) != 0 )
          {
            v35 = 1;
          }
          else if ( (v6 & 0x20) != 0 )
          {
            v35 = 2;
          }
          else if ( (v6 & 0x40) != 0 )
          {
            v35 = 3;
          }
          else
          {
            v35 = (v6 >> 11) & 4;
          }
          if ( wcsstr(*(const wchar_t **)(v34 + 224), L"ntdll")
            && *((_QWORD *)v61 + 4) > 0x100000000uLL
            && (v36 = *((_QWORD *)g_Target + 85)) != 0
            && !*(_BYTE *)(v36 + 56)
            && (v37 = (struct MachineInfo *)*((_QWORD *)g_Target + 83)) != 0
            && *((_BYTE *)v37 + 56) )
          {
            v38 = FormatMachineAddr64(v37, *((_QWORD *)v61 + 4) + *((unsigned int *)v61 + 10));
            v39 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
            v40 = *((_QWORD *)v61 + 4);
          }
          else
          {
            if ( g_Target )
            {
              if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                || (v41 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
              {
                v41 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
              }
            }
            else
            {
              v41 = 0;
            }
            v38 = FormatMachineAddr64(v41, *((unsigned int *)v61 + 10) + *((_QWORD *)v61 + 4));
            v40 = *((_QWORD *)v61 + 4);
            if ( g_Target )
            {
              if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                || (v39 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
              {
                v39 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
              }
            }
            else
            {
              v39 = 0;
            }
          }
          v42 = FormatMachineAddr64(v39, v40);
          dprintf(L"%s %s   ", v42, v38);
          if ( v29 )
          {
            DmlOut(L"<link cmd=\"lmDvm%s\">%s</link>", *((_QWORD *)v61 + 28), *((_QWORD *)v61 + 28));
            if ( *((_DWORD *)v61 + 59) < 2u )
              v43 = 0;
            else
              v43 = *((_QWORD *)v61 + 28);
            v44 = -1;
            do
              ++v44;
            while ( *(_WORD *)(v43 + 2 * v44) );
            if ( (unsigned int)v44 >= 9 )
              dprintf(L" ");
            else
              dprintf(L"%*c", (unsigned int)(9 - v44), 32);
          }
          else
          {
            dprintf(L"%-8s ", *((_QWORD *)v61 + 28));
          }
          if ( (unsigned int)(v35 - 2) <= 2 )
          {
            v53 = L"<none>";
            if ( *v72[v35] )
              v53 = v72[v35];
            dprintf(L"%-12s", v53);
          }
          else if ( (v6 & 0x100) == 0 )
          {
            switch ( *((_DWORD *)v61 + 52) )
            {
              case 1:
                dprintf(L"  ");
                break;
              case 2:
                dprintf(L"M ");
                break;
              case 3:
                dprintf(L"T ");
                break;
              case 4:
                dprintf(L"C ");
                break;
              case 5:
                dprintf(L"# ");
                break;
            }
            v45 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v61 + 231);
            v46 = 0;
            if ( v45 )
            {
              bstrString = 0;
              v65 = 0;
              v47 = **v45;
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v65);
              if ( v47(v45, &GUID_131e4723_1cc2_4ec7_bb12_9f40edf63b66, &v65) < 0
                || (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v65 + 24LL))(v65, &bstrString) < 0 )
              {
                dprintf(L"(service symbols)        ");
              }
              else
              {
                dprintf(L"(service symbols: %s)        ", bstrString);
                SysFreeString(bstrString);
              }
              v64 = 0;
              v66 = 0;
              v48 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v61 + 231);
              v49 = **v48;
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v64);
              v50 = v49(v48, &GUID_d9f5a718_e130_46c2_aecd_d66c557027b8, &v64);
              v46 = 0;
              if ( v50 >= 0 && (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v64 + 32LL))(v64, &v66) >= 0 )
              {
                dprintf(L"%s", v66);
                SysFreeString(v66);
              }
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v64);
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v65);
              goto LABEL_194;
            }
            if ( *(_DWORD *)&ModuleInfo[32] == 5 )
            {
              dprintf(L"(deferred)             ");
              goto LABEL_194;
            }
            if ( !*(_DWORD *)&ModuleInfo[32] )
            {
              dprintf(L"(no symbols)           ");
              goto LABEL_194;
            }
            if ( *(_DWORD *)&ModuleInfo[32] == 1 )
            {
              v51 = L"(coff symbols)         ";
              goto LABEL_186;
            }
            if ( *(_DWORD *)&ModuleInfo[32] == 2 )
            {
              dprintf(L"(codeview symbols)     ");
            }
            else
            {
              if ( *(_DWORD *)&ModuleInfo[32] != 3 )
              {
                if ( *(_DWORD *)&ModuleInfo[32] == 4 )
                  dprintf(L"(export symbols)       ");
                goto LABEL_187;
              }
              v51 = L"(private pdb symbols)  ";
              if ( !*(_DWORD *)&ModuleInfo[3236] )
                v51 = L"(pdb symbols)          ";
LABEL_186:
              dprintf(v51);
            }
LABEL_187:
            v52 = L"<none>";
            if ( *v72[v35] )
              v52 = v72[v35];
            dprintf(L"%s", v52);
LABEL_194:
            if ( (v6 & 8) != 0 )
            {
              dprintf(L"\n");
              do
              {
                if ( v46 != v35 && *v72[v46] )
                  dprintf(L"    %s: %s\n", (&g_DmtNameDescs)[v46]);
                ++v46;
              }
              while ( v46 < 5 );
              v5 = v68;
              if ( v29 )
              {
                bstrString = (BSTR)&v61;
                Debugger::Utils::ConvertException__lambda_0049af44b011288ebd65db7cab944903___(&bstrString);
              }
              memset(&v70, 0, sizeof(v70));
              if ( !ImageInfo::GetClrHeader(v61, &v70) )
              {
                v54 = L"set";
                if ( (v70.Flags & 0x10000) == 0 )
                  v54 = L"not set";
                dprintf(L"    Has CLR image header, track-debug-data flag %s\n", v54);
              }
              if ( *((_BYTE *)v61 + 117) )
                dprintf(L"    Image was built with /Brepro flag.\n");
              dprintf(L"    Timestamp:       ");
            }
            if ( (v6 & 0x80u) != 0 )
            {
              if ( *((_BYTE *)v61 + 117) )
              {
                dprintf(L" %08X (This is a reproducible build file hash, not a timestamp)", *((unsigned int *)v61 + 16));
              }
              else
              {
                v55 = *((_DWORD *)v61 + 16);
                v56 = TimeToStr(v55);
                dprintf(L" %s (%08X)", v56, v55);
              }
            }
            if ( (v6 & 8) != 0 )
              dprintf(L"\n    CheckSum:        ");
            if ( (v6 & 0x1000) != 0 )
            {
              if ( (*((_BYTE *)v61 + 56) & 1) != 0 )
                dprintf(L" %08X", *((unsigned int *)v61 + 15));
              else
                dprintf(L" missing");
            }
            dprintf(L"\n");
            if ( (v6 & 8) != 0 )
            {
              v57 = *((_DWORD *)v61 + 11);
              if ( !v57 || v57 == *((_DWORD *)v61 + 10) )
                dprintf(L"    ImageSize:        %08X\n", *((unsigned int *)v61 + 10));
              else
                dprintf(L"    ImageSize:        (header) %08X, (mapped) 0x%08X\n", v57);
              v58 = *((_DWORD *)v61 + 352);
              if ( !v58 )
                goto LABEL_229;
              v59 = v58 - 1;
              if ( v59 )
              {
                if ( v59 == 1 )
                {
                  v60 = L"Flat";
                  goto LABEL_230;
                }
LABEL_229:
                v60 = L"Unknown";
              }
              else
              {
                v60 = L"Loaded";
              }
LABEL_230:
              dprintf(L"    Mapping Form:     %s\n", v60);
              ImageInfo::OutputVersionInformation(v61);
            }
            v9 = v62;
            goto LABEL_232;
          }
          v46 = 0;
          goto LABEL_194;
        }
      }
      v13 = (ImageInfo *)*((_QWORD *)v27 + 218);
LABEL_233:
      v61 = v13;
      v24 = v13;
      v7 = v67;
      if ( !v13 )
        goto LABEL_234;
    }
    if ( *((_DWORD *)v24 + 137) >= 2u )
    {
      v25 = (const WCHAR *)*((_QWORD *)v24 + 67);
      goto LABEL_80;
    }
LABEL_79:
    v25 = 0;
    goto LABEL_80;
  }
LABEL_234:
  if ( (v6 & 0x4203) == 0 )
    ListUnloadedModules(g_Thread, (v6 >> 2) & 2 | (v9 != 0 ? 0x10 : 0) | ((v6 & 0x80 | 0x10) >> 4), v5, a4, L"\n");
}

```

## disassembly

```asm
0x1802a6200  mov     rax, rsp
0x1802a6203  push    rbp
0x1802a6204  push    rsi
0x1802a6205  push    rdi
0x1802a6206  push    r12
0x1802a6208  push    r13
0x1802a620a  push    r14
0x1802a620c  push    r15
0x1802a620e  lea     rbp, [rax-0D38h]
0x1802a6215  sub     rsp, 0E00h
0x1802a621c  mov     [rsp+0E30h+var_DC0], 0FFFFFFFFFFFFFFFEh
0x1802a6225  mov     [rax+10h], rbx
0x1802a6229  mov     rax, cs:__security_cookie
0x1802a6230  xor     rax, rsp
0x1802a6233  mov     [rbp+0D30h+var_40], rax
0x1802a623a  mov     r12, r9
0x1802a623d  mov     r13, r8
0x1802a6240  mov     [rsp+0E30h+var_DC8], r8
0x1802a6245  mov     r14d, edx
0x1802a6248  mov     rsi, rcx
0x1802a624b  mov     [rsp+0E30h+var_DD0], rcx
0x1802a6250  xor     r15d, r15d
0x1802a6253  mov     [rsp+0E30h+var_E00], r15
0x1802a6258  mov     qword ptr [rbp+0D30h+ModuleInfo.SizeOfStruct], r15
0x1802a625c  xor     edx, edx; Val
0x1802a625e  mov     r8d, 0CC0h; Size
0x1802a6264  lea     rcx, [rbp+0D30h+ModuleInfo.BaseOfImage]; void *
0x1802a6268  call    memset
0x1802a626d  mov     edi, r14d
0x1802a6270  mov     r8d, 1000h
0x1802a6276  and     edi, 400h
0x1802a627c  mov     dword ptr [rsp+0E30h+var_DF8], edi
0x1802a6280  jnz     loc_1802A6406
0x1802a6286  mov     word ptr [rbp+0D30h+var_68], r15w
0x1802a628e  bt      r14d, 10h
0x1802a6293  jnb     loc_1802A63FA
0x1802a6299  lea     edx, [r15+6Ch]
0x1802a629d  mov     [rbp+0D30h+var_68], 6D006Ch
0x1802a62a7  lea     eax, [rdx-28h]
0x1802a62aa  mov     [rbp+0D30h+var_64], ax
0x1802a62b1  mov     eax, r14d
0x1802a62b4  and     eax, 1008h
0x1802a62b9  cmp     eax, r8d
0x1802a62bc  jnz     short loc_1802A62C8
0x1802a62be  lea     ecx, [rdx-9]
0x1802a62c1  mov     [rbp+0D30h+var_62], cx
0x1802a62c8  lea     rbx, [rbp+0D30h+var_62]
0x1802a62cf  lea     rcx, [rbp+0D30h+var_60]
0x1802a62d6  cmovz   rbx, rcx
0x1802a62da  bt      r14d, 9
0x1802a62df  jnb     short loc_1802A62EA
0x1802a62e1  mov     word ptr [rbx], 65h ; 'e'
0x1802a62e6  add     rbx, 2
0x1802a62ea  test    r14b, 4
0x1802a62ee  jz      short loc_1802A62F9
0x1802a62f0  mov     word ptr [rbx], 6Bh ; 'k'
0x1802a62f5  add     rbx, 2
0x1802a62f9  test    r14b, 1
0x1802a62fd  jz      short loc_1802A6306
0x1802a62ff  mov     [rbx], dx
0x1802a6302  add     rbx, 2
0x1802a6306  bt      r14d, 0Eh
0x1802a630b  jnb     short loc_1802A6316
0x1802a630d  mov     word ptr [rbx], 6Fh ; 'o'
0x1802a6312  add     rbx, 2
0x1802a6316  mov     eax, r14d
0x1802a6319  and     al, 88h
0x1802a631b  cmp     al, 80h
0x1802a631d  jnz     short loc_1802A6328
0x1802a631f  mov     word ptr [rbx], 74h ; 't'
0x1802a6324  add     rbx, 2
0x1802a6328  test    r14b, 2
0x1802a632c  jz      short loc_1802A6337
0x1802a632e  mov     word ptr [rbx], 75h ; 'u'
0x1802a6333  add     rbx, 2
0x1802a6337  test    r14b, 8
0x1802a633b  jz      short loc_1802A6346
0x1802a633d  mov     word ptr [rbx], 76h ; 'v'
0x1802a6342  add     rbx, 2
0x1802a6346  mov     eax, r14d
0x1802a6349  and     eax, 2070h
0x1802a634e  jz      short loc_1802A6376
0x1802a6350  cmp     eax, 20h ; ' '
0x1802a6353  jz      short loc_1802A636F
0x1802a6355  cmp     eax, 40h ; '@'
0x1802a6358  jz      short loc_1802A6368
0x1802a635a  cmp     eax, 2000h
0x1802a635f  jnz     short loc_1802A637F
0x1802a6361  mov     word ptr [rbx], 6Eh ; 'n'
0x1802a6366  jmp     short loc_1802A637B
0x1802a6368  mov     word ptr [rbx], 66h ; 'f'
0x1802a636d  jmp     short loc_1802A637B
0x1802a636f  mov     word ptr [rbx], 70h ; 'p'
0x1802a6374  jmp     short loc_1802A637B
0x1802a6376  mov     word ptr [rbx], 69h ; 'i'
0x1802a637b  add     rbx, 2
0x1802a637f  mov     [rbx], r15w
0x1802a6383  test    r13, r13
0x1802a6386  jnz     short loc_1802A63D2
0x1802a6388  test    r12, r12
0x1802a638b  jnz     short loc_1802A63D2
0x1802a638d  xor     r9d, r9d; unsigned int
0x1802a6390  xor     r8d, r8d; unsigned __int16 **
0x1802a6393  lea     rdx, aLmd; "lmD"
0x1802a639a  mov     rcx, rsi; struct DebugClient *
0x1802a639d  call    ?ExecuteRegisteredCommand@@YAJPEAVDebugClient@@PEBGPEAPEBGK@Z; ExecuteRegisteredCommand(DebugClient *,ushort const *,ushort const * *,ulong)
0x1802a63a2  bt      r14d, 0Fh
0x1802a63a7  jnb     short loc_1802A63B2
0x1802a63a9  lea     rcx, aLinkCmdSStartL; "<link cmd=\"%s\">start</link>%Y{as}    "...
0x1802a63b0  jmp     short loc_1802A63C4
0x1802a63b2  mov     dword ptr [rbx], 6D0073h
0x1802a63b8  mov     [rbx+4], r15w
0x1802a63bd  lea     rcx, aStartYAsEndYAs; "start%Y{as}    end%Y{as}        <link c"...
0x1802a63c4  lea     rdx, [rbp+0D30h+var_68]
0x1802a63cb  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802a63d0  jmp     short loc_1802A6406
0x1802a63d2  xor     r9d, r9d; unsigned int
0x1802a63d5  xor     r8d, r8d; unsigned __int16 **
0x1802a63d8  lea     rdx, aLmd; "lmD"
0x1802a63df  mov     rcx, rsi; struct DebugClient *
0x1802a63e2  call    ?ExecuteRegisteredCommand@@YAJPEAVDebugClient@@PEBGPEAPEBGK@Z; ExecuteRegisteredCommand(DebugClient *,ushort const *,ushort const * *,ulong)
0x1802a63e7  lea     rdx, [rbp+0D30h+var_68]
0x1802a63ee  lea     rcx, aLinkCmdSBrowse; "<link cmd=\"%s\">Browse full module lis"...
0x1802a63f5  call    ?DmlOut@@YAXPEBGZZ; DmlOut(ushort const *,...)
0x1802a63fa  lea     rcx, aStartYAsEndYAs_0; "start%Y{as}    end%Y{as}        module "...
0x1802a6401  call    ?dprintf64@@YAXPEBGZZ; dprintf64(ushort const *,...)
0x1802a6406  mov     rbx, r15
0x1802a6409  mov     rax, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x1802a6410  mov     rcx, [rax+80h]
0x1802a6417  mov     [rsp+0E30h+var_E00], rcx
0x1802a641c  bt      r14d, 0Fh
0x1802a6421  jnb     loc_1802A64D7
0x1802a6427  test    rcx, rcx
0x1802a642a  jz      loc_1802A6587
0x1802a6430  mov     rsi, r15
0x1802a6433  mov     rdi, rbx
0x1802a6436  test    rbx, rbx
0x1802a6439  jz      short loc_1802A64A8
0x1802a643b  cmp     dword ptr [rcx+0ECh], 2
0x1802a6442  jb      short loc_1802A644D
0x1802a6444  mov     rdx, [rcx+0E0h]
0x1802a644b  jmp     short loc_1802A6450
0x1802a644d  mov     rdx, r15; String2
0x1802a6450  cmp     dword ptr [rdi+0ECh], 2
0x1802a6457  jb      short loc_1802A6462
0x1802a6459  mov     rcx, [rdi+0E0h]
0x1802a6460  jmp     short loc_1802A6465
0x1802a6462  mov     rcx, r15; String1
0x1802a6465  call    cs:__imp__wcsicmp
0x1802a646c  nop     dword ptr [rax+rax+00h]
0x1802a6471  test    eax, eax
0x1802a6473  jns     short loc_1802A648B
0x1802a6475  mov     rsi, rdi
0x1802a6478  mov     rdi, [rdi+6D0h]
0x1802a647f  test    rdi, rdi
0x1802a6482  jz      short loc_1802A648B
0x1802a6484  mov     rcx, [rsp+0E30h+var_E00]
0x1802a6489  jmp     short loc_1802A643B
0x1802a648b  test    rsi, rsi
0x1802a648e  jz      short loc_1802A64A3
0x1802a6490  mov     rax, [rsp+0E30h+var_E00]
0x1802a6495  mov     [rsi+6D0h], rax
0x1802a649c  mov     rcx, [rsp+0E30h+var_E00]
0x1802a64a1  jmp     short loc_1802A64AB
0x1802a64a3  mov     rcx, [rsp+0E30h+var_E00]
0x1802a64a8  mov     rbx, rcx
0x1802a64ab  mov     [rcx+6D0h], rdi
0x1802a64b2  mov     rax, [rsp+0E30h+var_E00]
0x1802a64b7  mov     rcx, [rax+8]
0x1802a64bb  mov     [rsp+0E30h+var_E00], rcx
0x1802a64c0  test    rcx, rcx
0x1802a64c3  jnz     loc_1802A6430
0x1802a64c9  mov     edi, dword ptr [rsp+0E30h+var_DF8]
0x1802a64cd  mov     rsi, [rsp+0E30h+var_DD0]
0x1802a64d2  jmp     loc_1802A6587
0x1802a64d7  bt      r14d, 11h
0x1802a64dc  jnb     short loc_1802A6549
0x1802a64de  test    rcx, rcx
0x1802a64e1  jz      loc_1802A6587
0x1802a64e7  mov     r8, rcx
0x1802a64ea  mov     rax, rbx
0x1802a64ed  test    rbx, rbx
0x1802a64f0  jz      short loc_1802A6527
0x1802a64f2  mov     rdx, r15
0x1802a64f5  mov     r9d, [r8+6D8h]
0x1802a64fc  cmp     [rax+6D8h], r9d
0x1802a6503  ja      short loc_1802A6514
0x1802a6505  mov     rdx, rax
0x1802a6508  mov     rax, [rax+6D0h]
0x1802a650f  test    rax, rax
0x1802a6512  jnz     short loc_1802A64FC
0x1802a6514  test    rdx, rdx
0x1802a6517  jz      short loc_1802A6527
0x1802a6519  mov     [rdx+6D0h], rcx
0x1802a6520  mov     rcx, [rsp+0E30h+var_E00]
0x1802a6525  jmp     short loc_1802A652A
0x1802a6527  mov     rbx, rcx
0x1802a652a  mov     [rcx+6D0h], rax
0x1802a6531  mov     rax, [rsp+0E30h+var_E00]
0x1802a6536  mov     rcx, [rax+8]
0x1802a653a  mov     [rsp+0E30h+var_E00], rcx
0x1802a653f  mov     r8, rcx
0x1802a6542  test    rcx, rcx
0x1802a6545  jnz     short loc_1802A64EA
0x1802a6547  jmp     short loc_1802A6587
0x1802a6549  test    rcx, rcx
0x1802a654c  jz      short loc_1802A6587
0x1802a654e  mov     rax, r15
0x1802a6551  mov     rdx, rcx
0x1802a6554  test    rax, rax
0x1802a6557  jz      short loc_1802A6567
0x1802a6559  mov     [rax+6D0h], rcx
0x1802a6560  mov     rcx, [rsp+0E30h+var_E00]
0x1802a6565  jmp     short loc_1802A656A
0x1802a6567  mov     rbx, rdx
0x1802a656a  mov     [rcx+6D0h], r15
0x1802a6571  mov     rax, [rsp+0E30h+var_E00]
0x1802a6576  mov     rcx, [rax+8]
0x1802a657a  mov     [rsp+0E30h+var_E00], rcx
0x1802a657f  mov     rdx, rcx
0x1802a6582  test    rcx, rcx
0x1802a6585  jnz     short loc_1802A6554
0x1802a6587  mov     [rsp+0E30h+var_E00], rbx
0x1802a658c  lea     rcx, asc_1805BAA38; "\n"
0x1802a6593  test    rbx, rbx
0x1802a6596  jz      loc_1802A6E4B
0x1802a659c  mov     rax, rbx
0x1802a659f  test    r13, r13
0x1802a65a2  jz      short loc_1802A65DB
0x1802a65a4  bt      r14d, 0Bh
0x1802a65a9  jnb     short loc_1802A65FE
0x1802a65ab  cmp     dword ptr [rax+224h], 2
0x1802a65b2  jb      short loc_1802A65BD
0x1802a65b4  mov     rcx, [rax+218h]
0x1802a65bb  jmp     short loc_1802A65C0
0x1802a65bd  mov     rcx, r15; string
0x1802a65c0  xor     r8d, r8d; fCase
0x1802a65c3  mov     rdx, r13; expression
0x1802a65c6  call    cs:__imp_SymMatchStringW
0x1802a65cd  nop     dword ptr [rax+rax+00h]
0x1802a65d2  mov     rbx, [rsp+0E30h+var_E00]
0x1802a65d7  test    eax, eax
0x1802a65d9  jz      short loc_1802A65F2
0x1802a65db  test    r12, r12
0x1802a65de  jz      short loc_1802A65E6
0x1802a65e0  cmp     [rbx+20h], r12
0x1802a65e4  ja      short loc_1802A65F2
0x1802a65e6  mov     eax, [rbx+28h]
0x1802a65e9  add     rax, [rbx+20h]
0x1802a65ed  cmp     rax, r12
0x1802a65f0  ja      short loc_1802A6610
0x1802a65f2  mov     rbx, [rbx+6D0h]
0x1802a65f9  jmp     loc_1802A6E2E
0x1802a65fe  cmp     dword ptr [rax+0ECh], 2
0x1802a6605  jb      short loc_1802A65BD
0x1802a6607  mov     rcx, [rax+0E0h]
0x1802a660e  jmp     short loc_1802A65C0
0x1802a6610  mov     [rbp+0D30h+ModuleInfo.SizeOfStruct], 0CC8h
0x1802a6617  mov     [rbp+0D30h+var_A0], 1
0x1802a6621  lea     r8, [rbp+0D30h+ModuleInfo]; ModuleInfo
0x1802a6625  mov     rdx, [rbx+20h]; qwAddr
0x1802a6629  mov     rcx, cs:?g_Process@@3PEAVProcessInfo@@EA; ProcessInfo * g_Process
0x1802a6630  mov     rcx, [rcx+198h]; hProcess
0x1802a6637  call    cs:__imp_SymGetModuleInfoW64
0x1802a663e  nop     dword ptr [rax+rax+00h]
0x1802a6643  test    eax, eax
0x1802a6645  jnz     short loc_1802A667E
0x1802a6647  mov     ebx, 0CC8h
0x1802a664c  mov     r8d, ebx; Size
0x1802a664f  xor     edx, edx; Val
0x1802a6651  lea     rcx, [rbp+0D30h+ModuleInfo]; void *
0x1802a6655  call    memset
0x1802a665a  mov     [rbp+0D30h+ModuleInfo.SizeOfStruct], ebx
0x1802a665d  mov     [rbp+0D30h+ModuleInfo.SymType], r15d
0x1802a6661  mov     r9d, 100h
0x1802a6667  or      r8d, 0FFFFFFFFh
0x1802a666b  lea     rdx, aError_6; "<error>"
0x1802a6672  lea     rcx, [rbp+0D30h+ModuleInfo.LoadedImageName]; void *
0x1802a6679  call    CopyNStringW
0x1802a667e  mov     ebx, 1
0x1802a6683  test    bl, r14b
0x1802a6686  jz      short loc_1802A6695
0x1802a6688  cmp     [rbp+0D30h+ModuleInfo.SymType], 5
0x1802a668c  jnz     short loc_1802A6695
0x1802a668e  mov     r10, [rsp+0E30h+var_E00]
0x1802a6693  jmp     short loc_1802A66ED
0x1802a6695  mov     r10, [rsp+0E30h+var_E00]
0x1802a669a  bt      r14d, 9
0x1802a669f  jnb     short loc_1802A66B3
0x1802a66a1  test    [rbp+0D30h+ModuleInfo.SymType], 0FFFFFFFBh
0x1802a66a8  jz      short loc_1802A66B3
0x1802a66aa  cmp     [r10+0D0h], ebx
0x1802a66b1  jz      short loc_1802A66ED
0x1802a66b3  mov     rcx, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1802a66ba  test    rcx, rcx
0x1802a66bd  jz      short loc_1802A66F9
0x1802a66bf  cmp     [rcx+1008h], ebx
0x1802a66c5  jnz     short loc_1802A66F9
0x1802a66c7  test    r14b, 2
0x1802a66cb  jz      short loc_1802A66DA
  ... truncated ...
```
