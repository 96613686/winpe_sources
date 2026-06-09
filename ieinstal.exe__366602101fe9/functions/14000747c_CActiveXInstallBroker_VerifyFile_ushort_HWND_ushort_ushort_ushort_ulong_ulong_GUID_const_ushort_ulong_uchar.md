# CActiveXInstallBroker::VerifyFile(ushort *,HWND__ *,ushort *,ushort *,ushort *,ulong,ulong,_GUID const &,ushort * *,ulong *,uchar * *)

- ea: `0x14000747c`
- end: `0x140007bc5`
- name: `?VerifyFile@CActiveXInstallBroker@@QEAAJPEAGPEAUHWND__@@000KKAEBU_GUID@@PEAPEAGPEAKPEAPEAE@Z`
- size: `1865`
- prototype: `__int64 __fastcall(CActiveXInstallBroker *__hidden this, unsigned __int16 *, HWND, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, const struct _GUID *, unsigned __int16 **, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140008600`

## callees

- `0x140001af3`
- `0x140003978`
- `0x14000747c`
- `0x1400088a8`
- `0x140008984`
- `0x140008f78`
- `0x140009240`
- `0x1400094a4`
- `0x14000a6b8`
- `0x14000abd4`
- `0x14000bb30`
- `0x14000c0fc`
- `0x1400109c0`
- `0x140011010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140007b67`
- `KERNEL32!CloseHandle` at `0x140007b67`
- `KERNEL32!GetTempPath2A` at `0x14000773e`
- `KERNEL32!GetTempPath2A` at `0x14000773e`
- `KERNEL32!LeaveCriticalSection` at `0x140007b95`
- `KERNEL32!LeaveCriticalSection` at `0x140007b95`
- `KERNEL32!EnterCriticalSection` at `0x14000752f`
- `KERNEL32!EnterCriticalSection` at `0x14000752f`
- `KERNEL32!CreateFileW` at `0x1400077e8`
- `KERNEL32!CreateFileW` at `0x1400077e8`
- `KERNEL32!GetLastError` at `0x140007762`
- `KERNEL32!GetLastError` at `0x1400077ff`
- `KERNEL32!GetLastError` at `0x140007762`
- `KERNEL32!GetLastError` at `0x1400077ff`
- `ole32!CoTaskMemAlloc` at `0x140007626`
- `ole32!CoTaskMemAlloc` at `0x1400076dd`
- `ole32!CoTaskMemAlloc` at `0x140007626`
- `ole32!CoTaskMemAlloc` at `0x1400076dd`
- `OLEAUT32!__imp_SysAllocString` at `0x14000787d`
- `OLEAUT32!__imp_SysAllocString` at `0x14000787d`
- `OLEAUT32!__imp_SysFreeString` at `0x1400078bf`
- `OLEAUT32!__imp_SysFreeString` at `0x140007b1c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400078bf`
- `OLEAUT32!__imp_SysFreeString` at `0x140007b1c`
- `OLEAUT32!__imp_SysStringLen` at `0x14000790e`
- `OLEAUT32!__imp_SysStringLen` at `0x14000790e`
- `urlmon!CoInternetCreateSecurityManager` at `0x14000789b`
- `urlmon!CoInternetCreateSecurityManager` at `0x14000789b`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::VerifyFile(
        CActiveXInstallBroker *this,
        unsigned __int16 *a2,
        HWND a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned int a7,
        unsigned int a8,
        const struct _GUID *a9,
        unsigned __int16 **a10,
        unsigned int *a11,
        unsigned __int8 **a12)
{
  _QWORD *v15; // rdi
  int HasExtensionW; // ebx
  __int64 v17; // rdx
  int v18; // eax
  int v19; // ecx
  __int64 v20; // rcx
  char v21; // r15
  char v22; // r12
  _DWORD *v23; // rax
  __int64 v24; // rcx
  _DWORD *v25; // rax
  unsigned int v26; // r8d
  signed int LastError; // eax
  signed int v28; // eax
  _QWORD *v29; // rax
  OLECHAR *v30; // rax
  OLECHAR *v31; // r15
  _DWORD *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int128 v36; // xmm0
  const WCHAR *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const WCHAR *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  unsigned int hTemplateFile; // [rsp+30h] [rbp-D0h]
  unsigned int v42; // [rsp+38h] [rbp-C8h]
  struct _GUID ppSM; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-A0h]
  OLECHAR *psz; // [rsp+68h] [rbp-98h]
  BSTR pbstr; // [rsp+70h] [rbp-90h]
  HWND v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h] BYREF
  unsigned int *v49; // [rsp+88h] [rbp-78h]
  unsigned __int8 **v50; // [rsp+90h] [rbp-70h]
  int v51; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B8h] [rbp-48h]
  _DWORD *v55; // [rsp+C0h] [rbp-40h]
  size_t Size; // [rsp+C8h] [rbp-38h]
  int v57; // [rsp+D4h] [rbp-2Ch]
  int v58; // [rsp+D8h] [rbp-28h]
  CHAR MultiByteStr[272]; // [rsp+E0h] [rbp-20h] BYREF
  CHAR TemplateDirectory[272]; // [rsp+1F0h] [rbp+F0h] BYREF

  pbstr = a6;
  v49 = a11;
  v15 = 0;
  v47 = a3;
  v50 = a12;
  psz = a4;
  *(_QWORD *)&ppSM.Data1 = a5;
  hObject = 0;
  v48 = 0;
  memset_0(MultiByteStr, 0, 0x104u);
  memset_0(&v51, 0, 0x40u);
  if ( !*(_DWORD *)this )
  {
    HasExtensionW = -2147024882;
LABEL_80:
    if ( !a10 )
      goto LABEL_82;
    goto LABEL_81;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((int *)this + 12) < 1 )
  {
    HasExtensionW = -2147019873;
    goto LABEL_80;
  }
  if ( !a2 || !a5 || !a10 )
  {
    HasExtensionW = -2147024809;
    goto LABEL_80;
  }
  v17 = *((_QWORD *)this + 8) - (_QWORD)a2;
  do
  {
    v18 = *(unsigned __int16 *)((char *)a2 + v17);
    v19 = *a2 - v18;
    if ( v19 )
      break;
    ++a2;
  }
  while ( v18 );
  if ( v19 )
    goto LABEL_11;
  v52 = v48;
  v51 = 64;
  v57 = 0;
  v54 = 0;
  v53 = a4;
  if ( *((_DWORD *)this + 35) )
  {
    if ( g_fRunningAsSystem )
    {
      v20 = *((_QWORD *)this + 19);
      HasExtensionW = -2147024891;
      if ( !v20 )
        goto LABEL_81;
      HasExtensionW = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v20 + 24LL))(
                        v20,
                        a4,
                        a10);
      if ( HasExtensionW < 0 )
        goto LABEL_81;
      HasExtensionW = AxiPreScanPathW(*a10);
      if ( HasExtensionW < 0 )
        goto LABEL_81;
      HasExtensionW = VerifyFileHasExtensionW(*a10);
      if ( HasExtensionW < 0 )
        goto LABEL_81;
      v21 = 0;
      LODWORD(Size) = 88;
      v22 = 0;
      v23 = CoTaskMemAlloc(0x58u);
      v55 = v23;
      if ( v23 )
      {
        memset_0(v23, 0, (unsigned int)Size);
        *v55 = Size;
        v55[2] = 1;
      }
      else
      {
        v55 = 0;
      }
    }
    else
    {
      v21 = 1;
      if ( *((_DWORD *)this + 36) )
      {
        v24 = *((_QWORD *)this + 19);
        HasExtensionW = -2147024891;
        if ( !v24 )
          goto LABEL_81;
        HasExtensionW = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v24 + 24LL))(
                          v24,
                          a4,
                          a10);
        if ( HasExtensionW < 0 )
          goto LABEL_81;
        HasExtensionW = AxiPreScanPathW(*a10);
        if ( HasExtensionW < 0 )
          goto LABEL_81;
        HasExtensionW = VerifyFileHasExtensionW(*a10);
        if ( HasExtensionW < 0 )
          goto LABEL_81;
        v58 = 1;
        v22 = 0;
      }
      else
      {
        v22 = 1;
      }
    }
    LODWORD(Size) = 88;
    v25 = CoTaskMemAlloc(0x58u);
    v55 = v25;
    if ( v25 )
    {
      memset_0(v25, 0, (unsigned int)Size);
      *v55 = Size;
      v55[2] = 1;
    }
    else
    {
      v55 = 0;
      LODWORD(Size) = 0;
    }
  }
  else
  {
    v21 = 1;
    v22 = 1;
  }
  if ( v22 )
  {
    MultiByteStr[0] = 0;
    if ( (unsigned int)GetTempPath2A(260, TemplateDirectory) )
    {
      HasExtensionW = MakeRandomTempDirectory(TemplateDirectory, MultiByteStr, v26);
    }
    else
    {
      LastError = GetLastError();
      HasExtensionW = LastError;
      if ( LastError > 0 )
        HasExtensionW = (unsigned __int16)LastError | 0x80070000;
    }
    if ( HasExtensionW < 0 )
      goto LABEL_81;
    HasExtensionW = CopyFileToRandomDir(MultiByteStr, *(LPCWSTR *)&ppSM.Data1, a10);
    if ( HasExtensionW < 0 )
      goto LABEL_81;
    HasExtensionW = AxiPreScanPathW(*a10);
    if ( HasExtensionW < 0 )
      goto LABEL_81;
    HasExtensionW = VerifyFileHasExtensionW(*a10);
    if ( HasExtensionW < 0 )
      goto LABEL_81;
    hObject = CreateFileW(*a10, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( hObject == (HANDLE)-1LL )
    {
      v28 = GetLastError();
      HasExtensionW = v28;
      if ( v28 > 0 )
        HasExtensionW = (unsigned __int16)v28 | 0x80070000;
      goto LABEL_81;
    }
  }
  if ( !v21 )
    goto LABEL_60;
  v29 = operator new(0x20u);
  v15 = v29;
  if ( !v29 )
  {
    HasExtensionW = -2147024882;
    v15 = 0;
    goto LABEL_81;
  }
  *((_DWORD *)v29 + 2) = 1;
  *v29 = &CActiveXInstallSecurityManager::`vftable';
  v30 = psz;
  v15[3] = 0;
  v15[2] = 0;
  *(_QWORD *)&ppSM.Data1 = 0;
  if ( !v30 )
  {
    HasExtensionW = -2147024809;
    goto LABEL_81;
  }
  v31 = SysAllocString(v30);
  if ( v31 )
  {
    HasExtensionW = CoInternetCreateSecurityManager(0, (IInternetSecurityManager **)&ppSM, 0);
    if ( HasExtensionW < 0 )
    {
      SysFreeString(v31);
    }
    else
    {
      v15[3] = *(_QWORD *)&ppSM.Data1;
      v15[2] = v31;
    }
  }
  else
  {
    HasExtensionW = -2147024882;
  }
  if ( HasExtensionW < 0 )
    goto LABEL_81;
  HasExtensionW = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v15)(
                    v15,
                    &IID_IInternetHostSecurityManager,
                    &v48);
  if ( HasExtensionW < 0 )
    goto LABEL_81;
  if ( pbstr && SysStringLen(pbstr) )
  {
    dwCreationDisposition = *a10;
    *(_QWORD *)&ppSM.Data1 = 0x11D0CD4400AAC56BLL;
    *(_DWORD *)ppSM.Data4 = -1073692020;
    *(_DWORD *)&ppSM.Data4[4] = -292175281;
    if ( (int)VerifyTrust(v47, &ppSM, psz, hObject, dwCreationDisposition, pbstr, a7, a8, &v51) >= 0 )
      goto LABEL_60;
    v42 = a8;
    hTemplateFile = a7;
    dwFlagsAndAttributes = pbstr;
  }
  else
  {
    v42 = a8;
    hTemplateFile = a7;
    dwFlagsAndAttributes = 0;
  }
  dwCreationDispositiona = *a10;
  *(_DWORD *)&ppSM.Data4[4] = 1091216207;
  *(_DWORD *)ppSM.Data4 = -1073690229;
  *(_QWORD *)&ppSM.Data1 = 0x11D1A407D41E4F1DLL;
  HasExtensionW = VerifyTrust(
                    v47,
                    &ppSM,
                    psz,
                    hObject,
                    dwCreationDispositiona,
                    dwFlagsAndAttributes,
                    hTemplateFile,
                    v42,
                    &v51);
  if ( HasExtensionW < 0 )
    goto LABEL_81;
LABEL_60:
  if ( !*((_DWORD *)this + 35) && !(unsigned int)ContainingPathIsTamperProof(*a10) )
  {
LABEL_11:
    HasExtensionW = -2147024891;
LABEL_81:
    SysFreeString(*a10);
    *a10 = 0;
    goto LABEL_82;
  }
  if ( v22 )
  {
    HasExtensionW = CopyFileToTempDir((LPCCH)this + 160, a10);
    if ( HasExtensionW < 0 )
      goto LABEL_81;
  }
  HasExtensionW = AddToFileListW(*a10, (struct sFNAME **)this + 16);
  if ( HasExtensionW < 0 )
    goto LABEL_81;
  v32 = v55;
  if ( v55 && (_DWORD)Size )
  {
    v33 = *((_QWORD *)v55 + 3);
    if ( v33 )
      *((_QWORD *)v55 + 3) = v33 - (_QWORD)v55;
    v34 = *((_QWORD *)v32 + 5);
    if ( v34 )
      *((_QWORD *)v32 + 5) = v34 - (_QWORD)v32;
    v35 = *((_QWORD *)v32 + 7);
    if ( v35 )
      *((_QWORD *)v32 + 7) = v35 - (_QWORD)v32;
    *v49 = Size;
    *v50 = (unsigned __int8 *)v55;
  }
  else
  {
    *v49 = 0;
    *v50 = 0;
  }
  v36 = (__int128)*a9;
  *((_DWORD *)this + 12) = 2;
  *(_OWORD *)((char *)this + 88) = v36;
LABEL_82:
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( HasExtensionW >= 0 )
    *((_DWORD *)this + 36) = 0;
  RemoveDirectoryAndChildren(MultiByteStr);
  if ( *(_DWORD *)this )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)HasExtensionW;
}

```

## disassembly

```asm
0x14000747c  push    rbp
0x14000747e  push    rbx
0x14000747f  push    rsi
0x140007480  push    rdi
0x140007481  push    r12
0x140007483  push    r14
0x140007485  push    r15
0x140007487  lea     rbp, [rsp-210h]
0x14000748f  sub     rsp, 310h
0x140007496  mov     rax, cs:__security_cookie
0x14000749d  xor     rax, rsp
0x1400074a0  mov     [rbp+240h+var_40], rax
0x1400074a7  mov     rax, [rbp+240h+arg_28]
0x1400074ae  mov     rbx, rdx
0x1400074b1  mov     r15, [rbp+240h+arg_20]
0x1400074b8  mov     r14, rcx
0x1400074bb  mov     rsi, [rbp+240h+arg_48]
0x1400074c2  lea     rcx, [rbp+240h+MultiByteStr]; void *
0x1400074c6  mov     [rsp+340h+pbstr], rax
0x1400074cb  xor     edx, edx; Val
0x1400074cd  mov     rax, [rbp+240h+arg_50]
0x1400074d4  mov     r12, r9
0x1400074d7  mov     [rbp+240h+var_2B8], rax
0x1400074db  xor     edi, edi
0x1400074dd  mov     rax, [rbp+240h+arg_58]
0x1400074e4  mov     [rsp+340h+var_2C8], r8
0x1400074e9  mov     r8d, 104h; Size
0x1400074ef  mov     [rbp+240h+var_2B0], rax
0x1400074f3  mov     [rsp+340h+psz], r9
0x1400074f8  mov     [rsp+340h+ppSM], r15
0x1400074fd  mov     [rsp+340h+hObject], 0
0x140007506  mov     [rbp+240h+var_2C0], 0
0x14000750e  call    memset_0
0x140007513  xor     edx, edx; Val
0x140007515  lea     r8d, [rdi+40h]; Size
0x140007519  lea     rcx, [rbp+240h+var_2A0]; void *
0x14000751d  call    memset_0
0x140007522  cmp     [r14], edi
0x140007525  jz      loc_140007B0F
0x14000752b  lea     rcx, [r14+8]; lpCriticalSection
0x14000752f  call    cs:__imp_EnterCriticalSection
0x140007536  nop     dword ptr [rax+rax+00h]
0x14000753b  cmp     dword ptr [r14+30h], 1
0x140007540  jge     short loc_14000754C
0x140007542  mov     ebx, 8007139Fh
0x140007547  jmp     loc_140007B14
0x14000754c  test    rbx, rbx
0x14000754f  jz      loc_140007B08
0x140007555  test    r15, r15
0x140007558  jz      loc_140007B08
0x14000755e  test    rsi, rsi
0x140007561  jz      loc_140007B08
0x140007567  mov     rdx, [r14+40h]
0x14000756b  sub     rdx, rbx
0x14000756e  movzx   ecx, word ptr [rbx]
0x140007571  movzx   eax, word ptr [rbx+rdx]
0x140007575  sub     ecx, eax
0x140007577  jnz     short loc_140007581
0x140007579  add     rbx, 2
0x14000757d  test    eax, eax
0x14000757f  jnz     short loc_14000756E
0x140007581  test    ecx, ecx
0x140007583  jz      short loc_14000758F
0x140007585  mov     ebx, 80070005h
0x14000758a  jmp     loc_140007B19
0x14000758f  mov     rax, [rbp+240h+var_2C0]
0x140007593  mov     [rbp+240h+var_298], rax
0x140007597  mov     [rbp+240h+var_2A0], 40h ; '@'
0x14000759e  mov     [rbp+240h+var_26C], edi
0x1400075a1  mov     [rbp+240h+var_288], edi
0x1400075a4  mov     [rbp+240h+var_290], r12
0x1400075a8  cmp     [r14+8Ch], edi
0x1400075af  jz      loc_14000771F
0x1400075b5  cmp     cs:?g_fRunningAsSystem@@3HA, edi; int g_fRunningAsSystem
0x1400075bb  jz      loc_140007665
0x1400075c1  mov     rcx, [r14+98h]
0x1400075c8  mov     ebx, 80070005h
0x1400075cd  test    rcx, rcx
0x1400075d0  jz      loc_140007B19
0x1400075d6  mov     rax, [rcx]
0x1400075d9  mov     r8, rsi
0x1400075dc  mov     rdx, r12
0x1400075df  mov     rax, [rax+18h]
0x1400075e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400075e8  mov     ebx, eax
0x1400075ea  test    eax, eax
0x1400075ec  js      loc_140007B19
0x1400075f2  mov     rcx, [rsi]; unsigned __int16 *
0x1400075f5  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x1400075fa  mov     ebx, eax
0x1400075fc  test    eax, eax
0x1400075fe  js      loc_140007B19
0x140007604  mov     rcx, [rsi]; lpFileName
0x140007607  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x14000760c  mov     ebx, eax
0x14000760e  test    eax, eax
0x140007610  js      loc_140007B19
0x140007616  mov     eax, 58h ; 'X'
0x14000761b  xor     r15b, r15b
0x14000761e  mov     ecx, eax; cb
0x140007620  mov     dword ptr [rbp+240h+Size], eax
0x140007623  xor     r12b, r12b
0x140007626  call    cs:__imp_CoTaskMemAlloc
0x14000762d  nop     dword ptr [rax+rax+00h]
0x140007632  mov     [rbp+240h+var_280], rax
0x140007636  test    rax, rax
0x140007639  jz      short loc_14000765F
0x14000763b  mov     r8d, dword ptr [rbp+240h+Size]; Size
0x14000763f  xor     edx, edx; Val
0x140007641  mov     rcx, rax; void *
0x140007644  call    memset_0
0x140007649  mov     rax, [rbp+240h+var_280]
0x14000764d  mov     ecx, dword ptr [rbp+240h+Size]
0x140007650  mov     [rax], ecx
0x140007652  mov     rax, [rbp+240h+var_280]
0x140007656  mov     dword ptr [rax+8], 1
0x14000765d  jmp     short loc_1400076D5
0x14000765f  mov     [rbp+240h+var_280], rdi
0x140007663  jmp     short loc_1400076D5
0x140007665  mov     r15b, 1
0x140007668  cmp     [r14+90h], edi
0x14000766f  jz      short loc_1400076D2
0x140007671  mov     rcx, [r14+98h]
0x140007678  mov     ebx, 80070005h
0x14000767d  test    rcx, rcx
0x140007680  jz      loc_140007B19
0x140007686  mov     rax, [rcx]
0x140007689  mov     r8, rsi
0x14000768c  mov     rdx, r12
0x14000768f  mov     rax, [rax+18h]
0x140007693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007698  mov     ebx, eax
0x14000769a  test    eax, eax
0x14000769c  js      loc_140007B19
0x1400076a2  mov     rcx, [rsi]; unsigned __int16 *
0x1400076a5  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x1400076aa  mov     ebx, eax
0x1400076ac  test    eax, eax
0x1400076ae  js      loc_140007B19
0x1400076b4  mov     rcx, [rsi]; lpFileName
0x1400076b7  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x1400076bc  mov     ebx, eax
0x1400076be  test    eax, eax
0x1400076c0  js      loc_140007B19
0x1400076c6  mov     [rbp+240h+var_268], 1
0x1400076cd  xor     r12b, r12b
0x1400076d0  jmp     short loc_1400076D5
0x1400076d2  mov     r12b, r15b
0x1400076d5  mov     ecx, 58h ; 'X'; cb
0x1400076da  mov     dword ptr [rbp+240h+Size], ecx
0x1400076dd  call    cs:__imp_CoTaskMemAlloc
0x1400076e4  nop     dword ptr [rax+rax+00h]
0x1400076e9  mov     [rbp+240h+var_280], rax
0x1400076ed  test    rax, rax
0x1400076f0  jz      short loc_140007716
0x1400076f2  mov     r8d, dword ptr [rbp+240h+Size]; Size
0x1400076f6  xor     edx, edx; Val
0x1400076f8  mov     rcx, rax; void *
0x1400076fb  call    memset_0
0x140007700  mov     rax, [rbp+240h+var_280]
0x140007704  mov     ecx, dword ptr [rbp+240h+Size]
0x140007707  mov     [rax], ecx
0x140007709  mov     rax, [rbp+240h+var_280]
0x14000770d  mov     dword ptr [rax+8], 1
0x140007714  jmp     short loc_140007725
0x140007716  mov     [rbp+240h+var_280], rdi
0x14000771a  mov     dword ptr [rbp+240h+Size], edi
0x14000771d  jmp     short loc_140007725
0x14000771f  mov     r15b, 1
0x140007722  mov     r12b, r15b
0x140007725  test    r12b, r12b
0x140007728  jz      loc_140007823
0x14000772e  lea     rdx, [rbp+240h+TemplateDirectory]
0x140007735  mov     [rbp+240h+MultiByteStr], dil
0x140007739  mov     ecx, 104h
0x14000773e  call    cs:__imp_GetTempPath2A
0x140007745  nop     dword ptr [rax+rax+00h]
0x14000774a  test    eax, eax
0x14000774c  jz      short loc_140007762
0x14000774e  lea     rdx, [rbp+240h+MultiByteStr]; char *
0x140007752  lea     rcx, [rbp+240h+TemplateDirectory]; lpTemplateDirectory
0x140007759  call    ?MakeRandomTempDirectory@@YAJPEBDPEADK@Z; MakeRandomTempDirectory(char const *,char *,ulong)
0x14000775e  mov     ebx, eax
0x140007760  jmp     short loc_14000777D
0x140007762  call    cs:__imp_GetLastError
0x140007769  nop     dword ptr [rax+rax+00h]
0x14000776e  mov     ebx, eax
0x140007770  test    eax, eax
0x140007772  jle     short loc_14000777D
0x140007774  movzx   ebx, ax
0x140007777  or      ebx, 80070000h
0x14000777d  test    ebx, ebx
0x14000777f  js      loc_140007B19
0x140007785  mov     rdx, [rsp+340h+ppSM]; lpsz
0x14000778a  lea     rcx, [rbp+240h+MultiByteStr]; lpMultiByteStr
0x14000778e  mov     r8, rsi; unsigned __int16 **
0x140007791  call    ?CopyFileToRandomDir@@YAJPEBDPEAGPEAPEAG@Z; CopyFileToRandomDir(char const *,ushort *,ushort * *)
0x140007796  mov     ebx, eax
0x140007798  test    eax, eax
0x14000779a  js      loc_140007B19
0x1400077a0  mov     rcx, [rsi]; unsigned __int16 *
0x1400077a3  call    ?AxiPreScanPathW@@YAJPEBG@Z; AxiPreScanPathW(ushort const *)
0x1400077a8  mov     ebx, eax
0x1400077aa  test    eax, eax
0x1400077ac  js      loc_140007B19
0x1400077b2  mov     rcx, [rsi]; lpFileName
0x1400077b5  call    ?VerifyFileHasExtensionW@@YAJPEBG@Z; VerifyFileHasExtensionW(ushort const *)
0x1400077ba  mov     ebx, eax
0x1400077bc  test    eax, eax
0x1400077be  js      loc_140007B19
0x1400077c4  mov     rcx, [rsi]; lpFileName
0x1400077c7  xor     r9d, r9d; lpSecurityAttributes
0x1400077ca  mov     [rsp+340h+hTemplateFile], rdi; hTemplateFile
0x1400077cf  mov     edx, 80000000h; dwDesiredAccess
0x1400077d4  mov     [rsp+340h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400077dc  mov     [rsp+340h+dwCreationDisposition], 3; dwCreationDisposition
0x1400077e4  lea     r8d, [r9+1]; dwShareMode
0x1400077e8  call    cs:__imp_CreateFileW
0x1400077ef  nop     dword ptr [rax+rax+00h]
0x1400077f4  mov     [rsp+340h+hObject], rax
0x1400077f9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400077fd  jnz     short loc_140007823
0x1400077ff  call    cs:__imp_GetLastError
0x140007806  nop     dword ptr [rax+rax+00h]
0x14000780b  mov     ebx, eax
0x14000780d  test    eax, eax
0x14000780f  jle     loc_140007B19
0x140007815  movzx   ebx, ax
0x140007818  or      ebx, 80070000h
0x14000781e  jmp     loc_140007B19
0x140007823  test    r15b, r15b
0x140007826  jz      loc_140007A23
0x14000782c  mov     ecx, 20h ; ' '; dwBytes
0x140007831  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007836  mov     rdi, rax
0x140007839  test    rax, rax
0x14000783c  jz      loc_140007AD0
0x140007842  lea     rax, ??_7CActiveXInstallSecurityManager@@6B@; const CActiveXInstallSecurityManager::`vftable'
0x140007849  mov     dword ptr [rdi+8], 1
0x140007850  mov     [rdi], rax
0x140007853  mov     rax, [rsp+340h+psz]
0x140007858  mov     qword ptr [rdi+18h], 0
0x140007860  mov     qword ptr [rdi+10h], 0
0x140007868  mov     [rsp+340h+ppSM], 0
0x140007871  test    rax, rax
0x140007874  jz      loc_140007AC9
0x14000787a  mov     rcx, rax; psz
0x14000787d  call    cs:__imp_SysAllocString
0x140007884  nop     dword ptr [rax+rax+00h]
0x140007889  mov     r15, rax
0x14000788c  test    rax, rax
0x14000788f  jz      short loc_1400078CD
0x140007891  xor     r8d, r8d; dwReserved
0x140007894  lea     rdx, [rsp+340h+ppSM]; ppSM
0x140007899  xor     ecx, ecx; pSP
0x14000789b  call    cs:__imp_CoInternetCreateSecurityManager
0x1400078a2  nop     dword ptr [rax+rax+00h]
0x1400078a7  mov     ebx, eax
0x1400078a9  test    eax, eax
0x1400078ab  js      short loc_1400078BC
0x1400078ad  mov     rcx, [rsp+340h+ppSM]
0x1400078b2  mov     [rdi+18h], rcx
0x1400078b6  mov     [rdi+10h], r15
0x1400078ba  jmp     short loc_1400078D2
0x1400078bc  mov     rcx, r15; bstrString
0x1400078bf  call    cs:__imp_SysFreeString
0x1400078c6  nop     dword ptr [rax+rax+00h]
0x1400078cb  jmp     short loc_1400078D2
0x1400078cd  mov     ebx, 8007000Eh
0x1400078d2  test    ebx, ebx
0x1400078d4  js      loc_140007B19
0x1400078da  mov     rax, [rdi]
0x1400078dd  lea     r8, [rbp+240h+var_2C0]
0x1400078e1  lea     rdx, IID_IInternetHostSecurityManager
0x1400078e8  mov     rcx, rdi
0x1400078eb  mov     rax, [rax]
0x1400078ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078f3  mov     ebx, eax
0x1400078f5  test    eax, eax
0x1400078f7  js      loc_140007B19
0x1400078fd  mov     rax, [rsp+340h+pbstr]
0x140007902  test    rax, rax
0x140007905  jz      loc_1400079B2
0x14000790b  mov     rcx, rax; pbstr
0x14000790e  call    cs:__imp_SysStringLen
0x140007915  nop     dword ptr [rax+rax+00h]
0x14000791a  test    eax, eax
0x14000791c  jz      loc_1400079B2
0x140007922  mov     ebx, [rbp+240h+arg_38]
0x140007928  lea     rax, [rbp+240h+var_2A0]
0x14000792c  mov     r15d, [rbp+240h+arg_30]
0x140007933  lea     rdx, [rsp+340h+ppSM]; struct _GUID *
0x140007938  mov     r9, [rsp+340h+hObject]; void *
0x14000793d  mov     r8, [rsp+340h+psz]; unsigned __int16 *
0x140007942  mov     rcx, [rsp+340h+var_2C8]; HWND
0x140007947  mov     [rsp+340h+var_300], rax; void *
0x14000794c  mov     rax, [rsp+340h+pbstr]
0x140007951  mov     [rsp+340h+var_308], ebx; unsigned int
0x140007955  mov     dword ptr [rsp+340h+hTemplateFile], r15d; unsigned int
0x14000795a  mov     qword ptr [rsp+340h+dwFlagsAndAttributes], rax; unsigned __int16 *
  ... truncated ...
```
