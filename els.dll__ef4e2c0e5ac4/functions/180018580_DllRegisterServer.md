# DllRegisterServer

- ea: `0x180018580`
- end: `0x180018dc9`
- name: `DllRegisterServer`
- size: `2121`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800181f0`
- `0x18001828c`
- `0x180018580`
- `0x18001abd8`
- `0x18001ac74`
- `0x18001ae60`
- `0x18001b11c`
- `0x180020430`
- `0x1800222d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800186e2`
- `msvcrt!swprintf_s` at `0x18001882b`
- `msvcrt!swprintf_s` at `0x1800186e2`
- `msvcrt!swprintf_s` at `0x18001882b`
- `KERNEL32!GetModuleFileNameW` at `0x1800185d2`
- `KERNEL32!GetModuleFileNameW` at `0x1800185d2`

## string_xrefs

- `0x180018d06`: `Extensions`
- `0x1800187c9`: `Event Viewer Extension`
- `0x1800188e0`: `CLSID`
- `0x18001899d`: `ThreadingModel`

## pseudocode

```c
HRESULT __stdcall DllRegisterServer()
{
  HRESULT NodeKeys; // ebx
  unsigned int v1; // r8d
  unsigned int v2; // r8d
  __int64 v3; // rdi
  __int64 v4; // rax
  unsigned int v5; // r8d
  __int64 v6; // rax
  unsigned int v7; // r8d
  struct NODE_GUID_INFO *v8; // rdx
  unsigned int v9; // r8d
  __int64 v10; // rax
  unsigned int v11; // r8d
  __int64 v12; // rax
  unsigned int v13; // r8d
  struct NODE_GUID_INFO *v14; // rdx
  unsigned int v15; // r8d
  __int64 v16; // rax
  unsigned int v17; // r8d
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  __int64 v20; // rax
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  __int64 v23; // rax
  unsigned int v24; // r8d
  unsigned int v25; // r8d
  __int64 v26; // rax
  unsigned int v27; // r8d
  __int64 v28; // rax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  unsigned __int16 *v32; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v33; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v34; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v35; // [rsp+20h] [rbp-E0h]
  HKEY v36; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v37; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v38; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v39; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v40; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v41; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v42[80]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Filename[264]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t Destination[80]; // [rsp+310h] [rbp+210h] BYREF
  wchar_t Buffer[520]; // [rsp+3B0h] [rbp+2B0h] BYREF

  v37 = 0;
  NodeKeys = -2147220991;
  v39 = 0;
  v41 = 0;
  if ( GetModuleFileNameW(g_hinst, Filename, 0x104u) )
  {
    v36 = 0;
    NodeKeys = CSafeReg::Open((CSafeReg *)&v36, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MMC\\SnapIns", 0x20006u);
    if ( NodeKeys < 0 )
      goto LABEL_58;
    v38 = 0;
    NodeKeys = CSafeReg::Create(&v36, L"{975797FC-4E2A-11D0-B702-00C04FD8DBF7}", &v38);
    if ( NodeKeys < 0 )
      goto LABEL_57;
    NodeKeys = CSafeReg::SetValue((CSafeReg *)&v38, L"NodeType", v1, L"{DC1C6BEC-4E2A-11D0-B702-00C04FD8DBF7}", 0x4Eu);
    if ( NodeKeys < 0 )
      goto LABEL_57;
    LoadStr(0x6Eu, Destination, 0x50u, (wchar_t *)L"Event Viewer");
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( Destination[v4] );
    NodeKeys = CSafeReg::SetValue((CSafeReg *)&v38, L"NameString", v2, (const unsigned __int8 *)Destination, 2 * v4 + 2);
    if ( NodeKeys < 0 )
      goto LABEL_57;
    LODWORD(v32) = 110;
    swprintf_s(Buffer, 0x208u, L"@%s,-%d", Filename, v32);
    v6 = -1;
    do
      ++v6;
    while ( Buffer[v6] );
    NodeKeys = CSafeReg::SetValue(
                 (CSafeReg *)&v38,
                 L"NameStringIndirect",
                 v5,
                 (const unsigned __int8 *)Buffer,
                 2 * v6 + 2);
    if ( NodeKeys < 0
      || (CSafeReg::SetValue(
            (CSafeReg *)&v38,
            L"About",
            v7,
            (const unsigned __int8 *)L"{F778C6B4-C08B-11D2-976C-00C04F79DB19}",
            0x4Eu),
          CSafeReg::Create(&v38, L"StandAlone", &v37),
          CSafeReg::Close((CSafeReg *)&v37),
          NodeKeys = CSafeReg::Create(&v38, L"NodeTypes", &v37),
          NodeKeys < 0)
      || (NodeKeys = CreateNodeKeys((struct CSafeReg *)&v37, v8), CSafeReg::Close((CSafeReg *)&v37), NodeKeys < 0)
      || (NodeKeys = CSafeReg::Create(&v36, L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}", &v37), NodeKeys < 0) )
    {
LABEL_57:
      CSafeReg::Close((CSafeReg *)&v38);
      goto LABEL_58;
    }
    LoadStr(0x6Fu, v42, 0x50u, (wchar_t *)L"Event Viewer Extension");
    v10 = -1;
    do
      ++v10;
    while ( v42[v10] );
    CSafeReg::SetValue((CSafeReg *)&v37, L"NameString", v9, (const unsigned __int8 *)v42, 2 * v10 + 2);
    LODWORD(v33) = 111;
    swprintf_s(Buffer, 0x208u, L"@%s,-%d", Filename, v33);
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    CSafeReg::SetValue((CSafeReg *)&v37, L"NameStringIndirect", v11, (const unsigned __int8 *)Buffer, 2 * v12 + 2);
    CSafeReg::SetValue(
      (CSafeReg *)&v37,
      L"About",
      v13,
      (const unsigned __int8 *)L"{F778C6B4-C08B-11D2-976C-00C04F79DB19}",
      0x4Eu);
    CSafeReg::Close((CSafeReg *)&v37);
    CSafeReg::Close((CSafeReg *)&v38);
    CSafeReg::Close((CSafeReg *)&v36);
    NodeKeys = CSafeReg::Open((CSafeReg *)&v41, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\MMC\\NodeTypes", 0x20006u);
    if ( NodeKeys >= 0 )
    {
      NodeKeys = CreateNodeKeys((struct CSafeReg *)&v41, v14);
      if ( NodeKeys >= 0 )
      {
        NodeKeys = CSafeReg::Open((CSafeReg *)&v39, HKEY_CLASSES_ROOT, L"CLSID", 0x20006u);
        if ( NodeKeys >= 0 )
        {
          v36 = 0;
          NodeKeys = CSafeReg::Create(&v39, L"{975797FC-4E2A-11D0-B702-00C04FD8DBF7}", &v37);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::Create(&v37, L"InprocServer32", &v36);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          v16 = -1;
          do
            ++v16;
          while ( Filename[v16] );
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, 0, v15, (const unsigned __int8 *)Filename, 2 * v16 + 2);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, L"ThreadingModel", v17, L"Apartment", 0x14u);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v36);
          v36 = 0;
          NodeKeys = CSafeReg::Create(&v39, L"{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}", &v37);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v37, 0, v18, L"PSFactoryBuffer", 0x20u);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::Create(&v37, L"InprocServer32", &v36);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          v20 = -1;
          do
            ++v20;
          while ( Filename[v20] );
          CSafeReg::SetValue((CSafeReg *)&v36, 0, v19, (const unsigned __int8 *)Filename, 2 * v20 + 2);
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, L"ThreadingModel", v21, L"Apartment", 0x14u);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          CSafeReg::Close((CSafeReg *)&v36);
          v36 = 0;
          NodeKeys = CSafeReg::Create(&v39, L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}", &v37);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::Create(&v37, L"InprocServer32", &v36);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          v23 = -1;
          do
            ++v23;
          while ( Filename[v23] );
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, 0, v22, (const unsigned __int8 *)Filename, 2 * v23 + 2);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, L"ThreadingModel", v24, L"Apartment", 0x14u);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          CSafeReg::Close((CSafeReg *)&v36);
          v36 = 0;
          NodeKeys = CSafeReg::Create(&v39, L"{F778C6B4-C08B-11D2-976C-00C04F79DB19}", &v37);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::Create(&v37, L"InprocServer32", &v36);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          LoadStr(0x137u, Buffer, 0x104u, (wchar_t *)L"Event viewer snapin ISnapinAbout provider");
          v26 = -1;
          do
            ++v26;
          while ( Buffer[v26] );
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v37, 0, v25, (const unsigned __int8 *)Buffer, 2 * v26 + 2);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          v28 = -1;
          do
            ++v28;
          while ( Filename[v28] );
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, 0, v27, (const unsigned __int8 *)Filename, 2 * v28 + 2);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          NodeKeys = CSafeReg::SetValue((CSafeReg *)&v36, L"ThreadingModel", v29, L"Apartment", 0x14u);
          if ( NodeKeys < 0 )
            goto LABEL_58;
          CSafeReg::Close((CSafeReg *)&v37);
          CSafeReg::Close((CSafeReg *)&v36);
          NodeKeys = CSafeReg::Open((CSafeReg *)&v37, HKEY_CLASSES_ROOT, L"Interface", 0x20006u);
          if ( NodeKeys >= 0 )
          {
            NodeKeys = RegisterInterface(
                         (struct CSafeReg *)&v37,
                         L"{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}",
                         L"INamespacePrshtActions",
                         L"4",
                         v34);
            if ( NodeKeys >= 0 )
            {
              NodeKeys = RegisterInterface(
                           (struct CSafeReg *)&v37,
                           L"{12DD72EE-A6E5-11D0-9A84-00C04FD8DBF7}",
                           L"IResultPrshtActions",
                           L"8",
                           v35);
              if ( NodeKeys >= 0 )
              {
                CSafeReg::Close((CSafeReg *)&v37);
                v36 = 0;
                NodeKeys = CSafeReg::Create(&v41, L"{476e6448-aaff-11d0-b944-00c04fd8d5b0}", &v36);
                if ( NodeKeys >= 0 )
                {
                  v38 = 0;
                  NodeKeys = CSafeReg::Create(&v36, L"Extensions", &v38);
                  if ( NodeKeys >= 0 )
                  {
                    v40 = 0;
                    NodeKeys = CSafeReg::Create(&v38, L"NameSpace", &v40);
                    if ( NodeKeys >= 0 )
                    {
                      do
                        ++v3;
                      while ( v42[v3] );
                      NodeKeys = CSafeReg::SetValue(
                                   (CSafeReg *)&v40,
                                   L"{394C052E-B830-11D0-9A86-00C04FD8DBF7}",
                                   v30,
                                   (const unsigned __int8 *)v42,
                                   2 * v3 + 2);
                    }
                    CSafeReg::Close((CSafeReg *)&v40);
                  }
                  goto LABEL_57;
                }
LABEL_58:
                CSafeReg::Close((CSafeReg *)&v36);
              }
            }
          }
        }
      }
    }
  }
  CSafeReg::Close((CSafeReg *)&v41);
  CSafeReg::Close((CSafeReg *)&v39);
  CSafeReg::Close((CSafeReg *)&v37);
  return NodeKeys;
}

```

## disassembly

```asm
0x180018580  push    rbp
0x180018582  push    rbx
0x180018583  push    rsi
0x180018584  push    rdi
0x180018585  push    r12
0x180018587  push    r13
0x180018589  push    r14
0x18001858b  lea     rbp, [rsp-6D0h]
0x180018593  sub     rsp, 7D0h
0x18001859a  mov     rax, cs:__security_cookie
0x1800185a1  xor     rax, rsp
0x1800185a4  mov     [rbp+700h+var_40], rax
0x1800185ab  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hModule
0x1800185b2  lea     rdx, [rbp+700h+Filename]; lpFilename
0x1800185b6  xor     esi, esi
0x1800185b8  mov     r8d, 104h; nSize
0x1800185be  mov     [rsp+800h+var_7C8], rsi
0x1800185c3  mov     ebx, 80040201h
0x1800185c8  mov     [rsp+800h+var_7B8], rsi
0x1800185cd  mov     [rsp+800h+var_7A8], rsi
0x1800185d2  call    cs:__imp_GetModuleFileNameW
0x1800185d8  test    eax, eax
0x1800185da  jz      loc_180018D88
0x1800185e0  mov     r13, 0FFFFFFFF80000002h
0x1800185e7  mov     [rsp+800h+var_7D0], rsi
0x1800185ec  mov     rdx, r13; HKEY
0x1800185ef  lea     r8, SNAPINS_KEY; "Software\\Microsoft\\MMC\\SnapIns"
0x1800185f6  mov     r9d, 20006h; unsigned int
0x1800185fc  lea     rcx, [rsp+800h+var_7D0]; this
0x180018601  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x180018606  lea     rcx, [rsp+800h+var_7D0]; this
0x18001860b  mov     ebx, eax
0x18001860d  test    eax, eax
0x18001860f  js      loc_180018D83
0x180018615  lea     r8, [rsp+800h+var_7C0]; struct CSafeReg *
0x18001861a  mov     [rsp+800h+var_7C0], rsi
0x18001861f  lea     rdx, a975797fc4e2a11; "{975797FC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180018626  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x18001862b  lea     rcx, [rsp+800h+var_7C0]; this
0x180018630  mov     ebx, eax
0x180018632  test    eax, eax
0x180018634  js      loc_180018D79
0x18001863a  lea     r12d, [rsi+4Eh]
0x18001863e  lea     r9, aDc1c6bec4e2a11; "{DC1C6BEC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180018645  mov     dword ptr [rsp+800h+var_7E0], r12d; unsigned int
0x18001864a  lea     rdx, g_szNodeType; "NodeType"
0x180018651  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018656  mov     ebx, eax
0x180018658  test    eax, eax
0x18001865a  js      loc_180018D74
0x180018660  lea     r14d, [rsi+6Eh]
0x180018664  mov     ecx, r14d; uID
0x180018667  lea     r9, aEventViewer; "Event Viewer"
0x18001866e  lea     r8d, [rsi+50h]; SizeInWords
0x180018672  lea     rdx, [rbp+700h+Destination]; Destination
0x180018679  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x18001867e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180018682  lea     rcx, [rbp+700h+Destination]
0x180018689  mov     rax, rdi
0x18001868c  inc     rax
0x18001868f  cmp     [rcx+rax*2], si
0x180018693  jnz     short loc_18001868C
0x180018695  lea     eax, ds:2[rax*2]
0x18001869c  lea     r9, [rbp+700h+Destination]; unsigned __int8 *
0x1800186a3  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x1800186a7  lea     rdx, g_szNameString; "NameString"
0x1800186ae  lea     rcx, [rsp+800h+var_7C0]; this
0x1800186b3  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x1800186b8  mov     ebx, eax
0x1800186ba  test    eax, eax
0x1800186bc  js      loc_180018D74
0x1800186c2  mov     dword ptr [rsp+800h+var_7E0], r14d
0x1800186c7  lea     r9, [rbp+700h+Filename]
0x1800186cb  mov     r14d, 208h
0x1800186d1  lea     r8, aSD; "@%s,-%d"
0x1800186d8  mov     edx, r14d; BufferCount
0x1800186db  lea     rcx, [rbp+700h+Buffer]; Buffer
0x1800186e2  call    cs:__imp_swprintf_s
0x1800186e8  lea     rcx, [rbp+700h+Buffer]
0x1800186ef  mov     rax, rdi
0x1800186f2  inc     rax
0x1800186f5  cmp     [rcx+rax*2], si
0x1800186f9  jnz     short loc_1800186F2
0x1800186fb  lea     eax, ds:2[rax*2]
0x180018702  lea     r9, [rbp+700h+Buffer]; unsigned __int8 *
0x180018709  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x18001870d  lea     rdx, g_szNameStringIndirect; "NameStringIndirect"
0x180018714  lea     rcx, [rsp+800h+var_7C0]; this
0x180018719  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x18001871e  lea     rcx, [rsp+800h+var_7C0]; this
0x180018723  mov     ebx, eax
0x180018725  test    eax, eax
0x180018727  js      loc_180018D79
0x18001872d  lea     r9, aF778c6b4C08b11; "{F778C6B4-C08B-11D2-976C-00C04F79DB19}"
0x180018734  mov     dword ptr [rsp+800h+var_7E0], r12d; unsigned int
0x180018739  lea     rdx, g_szAbout; "About"
0x180018740  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018745  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x18001874a  lea     rdx, g_szStandAlone; "StandAlone"
0x180018751  lea     rcx, [rsp+800h+var_7C0]; this
0x180018756  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x18001875b  lea     rcx, [rsp+800h+var_7C8]; this
0x180018760  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018765  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x18001876a  lea     rdx, g_szNodeTypes; "NodeTypes"
0x180018771  lea     rcx, [rsp+800h+var_7C0]; this
0x180018776  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x18001877b  mov     ebx, eax
0x18001877d  test    eax, eax
0x18001877f  js      loc_180018D74
0x180018785  lea     rcx, [rsp+800h+var_7C8]; this
0x18001878a  call    ?CreateNodeKeys@@YAJPEAVCSafeReg@@QEAUNODE_GUID_INFO@@@Z; CreateNodeKeys(CSafeReg *,NODE_GUID_INFO * const)
0x18001878f  lea     rcx, [rsp+800h+var_7C8]; this
0x180018794  mov     ebx, eax
0x180018796  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001879b  test    ebx, ebx
0x18001879d  js      loc_180018D74
0x1800187a3  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x1800187a8  lea     rdx, a394c052eB83011; "{394C052E-B830-11D0-9A86-00C04FD8DBF7}"
0x1800187af  lea     rcx, [rsp+800h+var_7D0]; this
0x1800187b4  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x1800187b9  mov     ebx, eax
0x1800187bb  test    eax, eax
0x1800187bd  js      loc_180018D74
0x1800187c3  mov     r8d, 50h ; 'P'; SizeInWords
0x1800187c9  lea     r9, aEventViewerExt; "Event Viewer Extension"
0x1800187d0  lea     rdx, [rsp+800h+var_7A0]; Destination
0x1800187d5  lea     ebx, [r8+1Fh]
0x1800187d9  mov     ecx, ebx; uID
0x1800187db  call    ?LoadStr@@YAJKPEAGKPEBG@Z; LoadStr(ulong,ushort *,ulong,ushort const *)
0x1800187e0  lea     rcx, [rsp+800h+var_7A0]
0x1800187e5  mov     rax, rdi
0x1800187e8  inc     rax
0x1800187eb  cmp     [rcx+rax*2], si
0x1800187ef  jnz     short loc_1800187E8
0x1800187f1  lea     eax, ds:2[rax*2]
0x1800187f8  lea     r9, [rsp+800h+var_7A0]; unsigned __int8 *
0x1800187fd  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x180018801  lea     rdx, g_szNameString; "NameString"
0x180018808  lea     rcx, [rsp+800h+var_7C8]; this
0x18001880d  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018812  lea     r9, [rbp+700h+Filename]
0x180018816  mov     dword ptr [rsp+800h+var_7E0], ebx
0x18001881a  lea     r8, aSD; "@%s,-%d"
0x180018821  mov     rdx, r14; BufferCount
0x180018824  lea     rcx, [rbp+700h+Buffer]; Buffer
0x18001882b  call    cs:__imp_swprintf_s
0x180018831  lea     rcx, [rbp+700h+Buffer]
0x180018838  mov     rax, rdi
0x18001883b  inc     rax
0x18001883e  cmp     [rcx+rax*2], si
0x180018842  jnz     short loc_18001883B
0x180018844  lea     eax, ds:2[rax*2]
0x18001884b  lea     r9, [rbp+700h+Buffer]; unsigned __int8 *
0x180018852  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x180018856  lea     rdx, g_szNameStringIndirect; "NameStringIndirect"
0x18001885d  lea     rcx, [rsp+800h+var_7C8]; this
0x180018862  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018867  lea     r9, aF778c6b4C08b11; "{F778C6B4-C08B-11D2-976C-00C04F79DB19}"
0x18001886e  mov     dword ptr [rsp+800h+var_7E0], r12d; unsigned int
0x180018873  lea     rdx, g_szAbout; "About"
0x18001887a  lea     rcx, [rsp+800h+var_7C8]; this
0x18001887f  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018884  lea     rcx, [rsp+800h+var_7C8]; this
0x180018889  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x18001888e  lea     rcx, [rsp+800h+var_7C0]; this
0x180018893  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018898  lea     rcx, [rsp+800h+var_7D0]; this
0x18001889d  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800188a2  mov     r14d, 20006h
0x1800188a8  lea     r8, NODE_TYPES_KEY; "Software\\Microsoft\\MMC\\NodeTypes"
0x1800188af  mov     r9d, r14d; unsigned int
0x1800188b2  lea     rcx, [rsp+800h+var_7A8]; this
0x1800188b7  mov     rdx, r13; HKEY
0x1800188ba  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800188bf  mov     ebx, eax
0x1800188c1  test    eax, eax
0x1800188c3  js      loc_180018D88
0x1800188c9  lea     rcx, [rsp+800h+var_7A8]; this
0x1800188ce  call    ?CreateNodeKeys@@YAJPEAVCSafeReg@@QEAUNODE_GUID_INFO@@@Z; CreateNodeKeys(CSafeReg *,NODE_GUID_INFO * const)
0x1800188d3  mov     ebx, eax
0x1800188d5  test    eax, eax
0x1800188d7  js      loc_180018D88
0x1800188dd  mov     r9d, r14d; unsigned int
0x1800188e0  lea     r8, aClsid; "CLSID"
0x1800188e7  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x1800188ee  lea     rcx, [rsp+800h+var_7B8]; this
0x1800188f3  call    ?Open@CSafeReg@@QEAAJPEAUHKEY__@@PEBGK@Z; CSafeReg::Open(HKEY__ *,ushort const *,ulong)
0x1800188f8  mov     ebx, eax
0x1800188fa  test    eax, eax
0x1800188fc  js      loc_180018D88
0x180018902  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x180018907  mov     [rsp+800h+var_7D0], rsi
0x18001890c  lea     rdx, a975797fc4e2a11; "{975797FC-4E2A-11D0-B702-00C04FD8DBF7}"
0x180018913  lea     rcx, [rsp+800h+var_7B8]; this
0x180018918  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x18001891d  mov     ebx, eax
0x18001891f  test    eax, eax
0x180018921  js      loc_180018D7E
0x180018927  lea     r14, aInprocserver32; "InprocServer32"
0x18001892e  mov     rdx, r14; unsigned __int16 *
0x180018931  lea     r8, [rsp+800h+var_7D0]; struct CSafeReg *
0x180018936  lea     rcx, [rsp+800h+var_7C8]; this
0x18001893b  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x180018940  mov     ebx, eax
0x180018942  test    eax, eax
0x180018944  js      loc_180018D7E
0x18001894a  lea     rcx, [rsp+800h+var_7C8]; this
0x18001894f  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018954  lea     rcx, [rbp+700h+Filename]
0x180018958  mov     rax, rdi
0x18001895b  inc     rax
0x18001895e  cmp     [rcx+rax*2], si
0x180018962  jnz     short loc_18001895B
0x180018964  lea     eax, ds:2[rax*2]
0x18001896b  xor     edx, edx; unsigned __int16 *
0x18001896d  lea     r9, [rbp+700h+Filename]; unsigned __int8 *
0x180018971  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x180018975  lea     rcx, [rsp+800h+var_7D0]; this
0x18001897a  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x18001897f  lea     rcx, [rsp+800h+var_7D0]; this
0x180018984  mov     ebx, eax
0x180018986  test    eax, eax
0x180018988  js      loc_180018D83
0x18001898e  lea     r12, aApartment; "Apartment"
0x180018995  mov     dword ptr [rsp+800h+var_7E0], 14h; unsigned int
0x18001899d  lea     r13, aThreadingmodel; "ThreadingModel"
0x1800189a4  mov     r9, r12; unsigned __int8 *
0x1800189a7  mov     rdx, r13; unsigned __int16 *
0x1800189aa  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x1800189af  lea     rcx, [rsp+800h+var_7D0]; this
0x1800189b4  mov     ebx, eax
0x1800189b6  test    eax, eax
0x1800189b8  js      loc_180018D83
0x1800189be  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x1800189c3  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x1800189c8  mov     [rsp+800h+var_7D0], rsi
0x1800189cd  lea     rdx, a05238c14A6e111; "{05238C14-A6E1-11D0-9A84-00C04FD8DBF7}"
0x1800189d4  lea     rcx, [rsp+800h+var_7B8]; this
0x1800189d9  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x1800189de  mov     ebx, eax
0x1800189e0  test    eax, eax
0x1800189e2  js      loc_180018D7E
0x1800189e8  lea     r9, aPsfactorybuffe; "PSFactoryBuffer"
0x1800189ef  mov     dword ptr [rsp+800h+var_7E0], 20h ; ' '; unsigned int
0x1800189f7  xor     edx, edx; unsigned __int16 *
0x1800189f9  lea     rcx, [rsp+800h+var_7C8]; this
0x1800189fe  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018a03  mov     ebx, eax
0x180018a05  test    eax, eax
0x180018a07  js      loc_180018D7E
0x180018a0d  lea     r8, [rsp+800h+var_7D0]; struct CSafeReg *
0x180018a12  mov     rdx, r14; unsigned __int16 *
0x180018a15  lea     rcx, [rsp+800h+var_7C8]; this
0x180018a1a  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x180018a1f  mov     ebx, eax
0x180018a21  test    eax, eax
0x180018a23  js      loc_180018D7E
0x180018a29  lea     rcx, [rbp+700h+Filename]
0x180018a2d  mov     rax, rdi
0x180018a30  inc     rax
0x180018a33  cmp     [rcx+rax*2], si
0x180018a37  jnz     short loc_180018A30
0x180018a39  lea     eax, ds:2[rax*2]
0x180018a40  xor     edx, edx; unsigned __int16 *
0x180018a42  lea     r9, [rbp+700h+Filename]; unsigned __int8 *
0x180018a46  mov     dword ptr [rsp+800h+var_7E0], eax; unsigned int
0x180018a4a  lea     rcx, [rsp+800h+var_7D0]; this
0x180018a4f  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018a54  mov     r9, r12; unsigned __int8 *
0x180018a57  mov     dword ptr [rsp+800h+var_7E0], 14h; unsigned int
0x180018a5f  mov     rdx, r13; unsigned __int16 *
0x180018a62  lea     rcx, [rsp+800h+var_7D0]; this
0x180018a67  call    ?SetValue@CSafeReg@@QEAAJPEBGKPEBEK@Z; CSafeReg::SetValue(ushort const *,ulong,uchar const *,ulong)
0x180018a6c  mov     ebx, eax
0x180018a6e  test    eax, eax
0x180018a70  js      loc_180018D7E
0x180018a76  lea     rcx, [rsp+800h+var_7C8]; this
0x180018a7b  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018a80  lea     rcx, [rsp+800h+var_7D0]; this
0x180018a85  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018a8a  lea     r8, [rsp+800h+var_7C8]; struct CSafeReg *
0x180018a8f  mov     [rsp+800h+var_7D0], rsi
0x180018a94  lea     rdx, a394c052eB83011; "{394C052E-B830-11D0-9A86-00C04FD8DBF7}"
0x180018a9b  lea     rcx, [rsp+800h+var_7B8]; this
0x180018aa0  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x180018aa5  mov     ebx, eax
0x180018aa7  test    eax, eax
0x180018aa9  js      loc_180018D7E
0x180018aaf  lea     r8, [rsp+800h+var_7D0]; struct CSafeReg *
0x180018ab4  mov     rdx, r14; unsigned __int16 *
0x180018ab7  lea     rcx, [rsp+800h+var_7C8]; this
0x180018abc  call    ?Create@CSafeReg@@QEAAJPEBGPEAV1@@Z; CSafeReg::Create(ushort const *,CSafeReg *)
0x180018ac1  mov     ebx, eax
0x180018ac3  test    eax, eax
0x180018ac5  js      loc_180018D7E
0x180018acb  lea     rcx, [rsp+800h+var_7C8]; this
0x180018ad0  call    ?Close@CSafeReg@@QEAAXXZ; CSafeReg::Close(void)
0x180018ad5  lea     rcx, [rbp+700h+Filename]
0x180018ad9  mov     rax, rdi
  ... truncated ...
```
