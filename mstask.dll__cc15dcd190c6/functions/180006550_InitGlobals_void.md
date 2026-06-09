# InitGlobals(void)

- ea: `0x180006550`
- end: `0x1800069df`
- name: `?InitGlobals@@YAJXZ`
- size: `1167`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800064f0`

## callees

- `0x180006550`
- `0x1800069e8`
- `0x180006ba0`
- `0x180009bb4`
- `0x180009ef8`
- `0x180009f38`
- `0x18001aac0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800069c5`
- `msvcrt!_wcsicmp` at `0x1800069c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006823`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006823`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006818`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180006818`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000674e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000674e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800066ed`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800066ed`

## string_xrefs

- `0x1800067ff`: `NotifyOnTaskMiss`
- `0x180006740`: `SOFTWARE\Microsoft\SchedulingAgent`

## pseudocode

```c
int InitGlobals(void)
{
  int result; // eax
  __int64 v1; // rsi
  __int64 v2; // rbx
  unsigned __int16 *v3; // rdi
  unsigned int v4; // r12d
  unsigned __int64 v5; // rbp
  _WORD *v6; // r14
  __int64 v7; // r13
  unsigned __int16 v8; // cx
  unsigned __int16 *i; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  _WORD *v12; // rax
  _WORD *v13; // rcx
  signed int LastError; // eax
  signed int v15; // ebx
  HKEY v16; // rcx
  unsigned __int16 *v17; // rcx
  __int64 v18; // rax
  WCHAR *v19; // r8
  __int64 v20; // r9
  WCHAR *v21; // rcx
  WCHAR *v22; // rax
  __int64 v23; // rcx
  const unsigned __int16 *v24; // rdx
  WCHAR *v25; // rax
  __int64 v26; // r10
  WCHAR *v27; // rcx
  _WORD *v28; // rax
  unsigned int v29; // ecx
  bool v30; // zf
  DWORD MaximumComponentLength; // [rsp+40h] [rbp-78h] BYREF
  DWORD FileSystemFlags[2]; // [rsp+48h] [rbp-70h] BYREF
  WCHAR FileSystemNameBuffer[24]; // [rsp+50h] [rbp-68h] BYREF

  result = GetTasksFolder(&g_TasksFolderInfo);
  if ( result < 0 )
    return result;
  result = EnsureTasksFolderExists(g_TasksFolderInfo);
  if ( result < 0 )
    return result;
  v1 = -1;
  v2 = -1;
  v3 = g_TasksFolderInfo;
  do
    ++v2;
  while ( g_TasksFolderInfo[v2] );
  v4 = 2;
  v5 = (unsigned int)(v2 + 2);
  v6 = operator new(saturated_mul(v5, 2u));
  if ( !v6 )
    return -2147024882;
  v7 = 2147483646;
  if ( (_DWORD)v2 && *v3 == 92 )
  {
    if ( (unsigned int)v2 <= 1 )
      goto LABEL_72;
    if ( v3[1] != 92 )
      goto LABEL_72;
    v28 = v3 + 2;
    v29 = 0;
    if ( (unsigned int)v2 <= 2 )
      goto LABEL_72;
    do
    {
      if ( !*v28 )
        break;
      v30 = v29 == 2;
      if ( v29 >= 2 )
        goto LABEL_66;
      for ( ; v4 < (unsigned int)v2; ++v28 )
      {
        if ( !*v28 )
          break;
        if ( *v28 == 92 )
          break;
        ++v4;
      }
      if ( !*v28 )
        goto LABEL_72;
      ++v29;
      ++v4;
      ++v28;
    }
    while ( v4 < (unsigned int)v2 );
    v30 = v29 == 2;
LABEL_66:
    if ( !v30 )
      goto LABEL_72;
    i = v28 - 1;
  }
  else
  {
    v8 = *v3;
    for ( i = v3; *i; v8 = *i )
    {
      if ( v8 == 92 )
        break;
      ++i;
    }
  }
  if ( *i == 92 )
  {
    v10 = (unsigned int)(i - v3) + 1;
    if ( (unsigned int)v10 <= (int)v2 + 1 )
    {
      if ( (_DWORD)v2 != -2 )
      {
        if ( v5 > 0x7FFFFFFF || (unsigned int)v10 > 0x7FFFFFFE )
        {
          *v6 = 0;
        }
        else
        {
          v11 = (unsigned int)v10;
          v12 = v6;
          do
          {
            if ( !v11 )
              break;
            if ( !*v3 )
              break;
            *v12++ = *v3++;
            --v11;
            --v5;
          }
          while ( v5 );
          v13 = v12 - 1;
          if ( v5 )
            v13 = v12;
          *v13 = 0;
        }
      }
      v6[v10] = 0;
      goto LABEL_21;
    }
  }
LABEL_72:
  if ( (unsigned int)(v2 + 2) < 2 )
  {
    if ( (_DWORD)v2 != -2 )
      *v6 = 0;
  }
  else
  {
    *(_DWORD *)v6 = 92;
  }
LABEL_21:
  MaximumComponentLength = 0;
  FileSystemFlags[0] = 0;
  if ( !GetVolumeInformationW(v6, 0, 0, 0, &MaximumComponentLength, FileSystemFlags, FileSystemNameBuffer, 0x14u) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    operator delete(v6);
    if ( v15 >= 0 )
      goto LABEL_25;
    return v15;
  }
  operator delete(v6);
  dword_180023EC8 = _wcsicmp(FileSystemNameBuffer, L"NTFS") == 0;
LABEL_25:
  *(_DWORD *)&g_fNotifyMiss = 0;
  *(_QWORD *)FileSystemFlags = 0;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SchedulingAgent", 0, 0x20019u, (PHKEY)FileSystemFlags);
  v16 = *(HKEY *)FileSystemFlags;
  if ( *(_QWORD *)FileSystemFlags )
  {
    MaximumComponentLength = 4;
    RegQueryValueExW(*(HKEY *)FileSystemFlags, L"NotifyOnTaskMiss", 0, 0, &g_fNotifyMiss, &MaximumComponentLength);
    RegCloseKey(*(HKEY *)FileSystemFlags);
  }
  result = GetViewHiddenTasks((int *)v16);
  if ( result >= 0 )
  {
    v17 = g_TasksFolderInfo;
    do
      v30 = g_TasksFolderInfo[++v1] == 0;
    while ( !v30 );
    if ( (unsigned int)(v1 + 9) <= 0x105 )
    {
      v18 = 2147483646;
      v19 = g_wszAtJobSearchPath;
      v20 = 261;
      do
      {
        if ( !v18 )
          break;
        if ( !*v17 )
          break;
        *v19++ = *v17++;
        --v18;
        --v20;
      }
      while ( v20 );
      v21 = v19 - 1;
      v22 = g_wszAtJobSearchPath;
      if ( v20 )
        v21 = v19;
      *v21 = 0;
      v23 = 261;
      do
      {
        if ( !*v22 )
          break;
        ++v22;
        --v23;
      }
      while ( v23 );
      if ( v23 )
      {
        v24 = L"\\At*.job";
        v25 = &g_wszAtJobSearchPath[261 - v23];
        v26 = v23;
        do
        {
          if ( !v7 )
            break;
          if ( !*v24 )
            break;
          *v25++ = *v24++;
          --v7;
          --v26;
        }
        while ( v26 );
        v27 = v25 - 1;
        if ( v26 )
          v27 = v25;
        *v27 = 0;
      }
      FILETIMES_PER_DAY = 864000000000LL;
      return 0;
    }
    else
    {
      return -2147467259;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006550  sub     rsp, 0B8h
0x180006557  mov     rax, cs:__security_cookie
0x18000655e  xor     rax, rsp
0x180006561  mov     [rsp+0B8h+var_38], rax
0x180006569  lea     rcx, ?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 **
0x180006570  call    ?GetTasksFolder@@YAJPEAPEAG@Z; GetTasksFolder(ushort * *)
0x180006575  test    eax, eax
0x180006577  js      loc_1800067D5
0x18000657d  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; unsigned __int16 *
0x180006584  call    ?EnsureTasksFolderExists@@YAJPEAGH@Z; EnsureTasksFolderExists(ushort *,int)
0x180006589  test    eax, eax
0x18000658b  js      loc_1800067D5
0x180006591  mov     [rsp+0B8h+arg_0], rbx
0x180006599  mov     [rsp+0B8h+arg_8], rbp
0x1800065a1  mov     [rsp+0B8h+arg_10], rsi
0x1800065a9  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800065b0  mov     [rsp+0B8h+var_8], rdi
0x1800065b8  mov     rbx, rsi
0x1800065bb  mov     rdi, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x1800065c2  mov     [rsp+0B8h+var_10], r12
0x1800065ca  mov     [rsp+0B8h+var_20], r14
0x1800065d2  mov     [rsp+0B8h+var_28], r15
0x1800065da  nop     word ptr [rax+rax+00h]
0x1800065e0  inc     rbx
0x1800065e3  cmp     word ptr [rdi+rbx*2], 0
0x1800065e8  jnz     short loc_1800065E0
0x1800065ea  lea     r15d, [rbx+2]
0x1800065ee  mov     [rsp+0B8h+var_18], r13
0x1800065f6  mov     r12d, 2
0x1800065fc  mov     ebp, r15d
0x1800065ff  mov     eax, r12d
0x180006602  mul     rbp
0x180006605  cmovb   rax, rsi
0x180006609  mov     rcx, rax; Size
0x18000660c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006611  mov     r14, rax
0x180006614  test    rax, rax
0x180006617  jz      loc_1800068EC
0x18000661d  xor     r9d, r9d; lpVolumeSerialNumber
0x180006620  mov     r13d, 7FFFFFFEh
0x180006626  test    ebx, ebx
0x180006628  jnz     loc_1800068F8
0x18000662e  movzx   ecx, word ptr [rdi]
0x180006631  mov     rax, rdi
0x180006634  test    cx, cx
0x180006637  jnz     loc_18000696A
0x18000663d  cmp     word ptr [rax], 5Ch ; '\'
0x180006641  jnz     loc_18000698D
0x180006647  sub     rax, rdi
0x18000664a  sar     rax, 1
0x18000664d  lea     r8d, [rax+1]
0x180006651  lea     eax, [r15-1]
0x180006655  cmp     r8d, eax
0x180006658  ja      loc_18000698D
0x18000665e  test    r15d, r15d
0x180006661  jz      short loc_1800066B0
0x180006663  cmp     rbp, 7FFFFFFFh
0x18000666a  ja      loc_180006984
0x180006670  cmp     r8d, r13d
0x180006673  ja      loc_180006984
0x180006679  mov     ecx, r8d
0x18000667c  mov     rax, r14
0x18000667f  nop
0x180006680  test    rcx, rcx
0x180006683  jz      short loc_1800066A1
0x180006685  movzx   edx, word ptr [rdi]
0x180006688  test    dx, dx
0x18000668b  jz      short loc_1800066A1
0x18000668d  mov     [rax], dx
0x180006690  add     rdi, 2
0x180006694  add     rax, 2
0x180006698  dec     rcx
0x18000669b  sub     rbp, 1
0x18000669f  jnz     short loc_180006680
0x1800066a1  test    rbp, rbp
0x1800066a4  lea     rcx, [rax-2]
0x1800066a8  cmovnz  rcx, rax
0x1800066ac  mov     [rcx], r9w
0x1800066b0  mov     [r14+r8*2], r9w
0x1800066b5  mov     [rsp+0B8h+nFileSystemNameSize], 14h; nFileSystemNameSize
0x1800066bd  lea     rax, [rsp+0B8h+FileSystemNameBuffer]
0x1800066c2  mov     [rsp+0B8h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x1800066c7  xor     r8d, r8d; nVolumeNameSize
0x1800066ca  lea     rax, [rsp+0B8h+FileSystemFlags]
0x1800066cf  mov     [rsp+0B8h+MaximumComponentLength], r9d
0x1800066d4  mov     [rsp+0B8h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800066d9  xor     edx, edx; lpVolumeNameBuffer
0x1800066db  lea     rax, [rsp+0B8h+MaximumComponentLength]
0x1800066e0  mov     [rsp+0B8h+FileSystemFlags], r9d
0x1800066e5  mov     rcx, r14; lpRootPathName
0x1800066e8  mov     [rsp+0B8h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x1800066ed  call    cs:__imp_GetVolumeInformationW
0x1800066f3  test    eax, eax
0x1800066f5  jnz     loc_1800069B1
0x1800066fb  call    cs:__imp_GetLastError
0x180006701  mov     ebx, eax
0x180006703  test    eax, eax
0x180006705  jle     short loc_180006710
0x180006707  movzx   ebx, ax
0x18000670a  or      ebx, 80070000h
0x180006710  mov     rcx, r14; Block
0x180006713  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006718  test    ebx, ebx
0x18000671a  js      loc_1800068F1
0x180006720  xor     ebx, ebx
0x180006722  lea     rax, [rsp+0B8h+FileSystemFlags]
0x180006727  mov     cs:?g_fNotifyMiss@@3HA, ebx; int g_fNotifyMiss
0x18000672d  mov     r9d, 20019h; samDesired
0x180006733  mov     [rsp+0B8h+lpMaximumComponentLength], rax; phkResult
0x180006738  xor     r8d, r8d; ulOptions
0x18000673b  mov     qword ptr [rsp+0B8h+FileSystemFlags], rbx
0x180006740  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\SchedulingAgent"
0x180006747  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000674e  call    cs:__imp_RegOpenKeyExW
0x180006754  mov     rcx, qword ptr [rsp+0B8h+FileSystemFlags]; int *
0x180006759  test    rcx, rcx
0x18000675c  jnz     loc_1800067ED
0x180006762  call    ?GetViewHiddenTasks@@YAJPEAH@Z; GetViewHiddenTasks(int *)
0x180006767  test    eax, eax
0x180006769  js      short loc_180006795
0x18000676b  mov     rcx, cs:?g_TasksFolderInfo@@3U_TasksFolderInfo@@A; _TasksFolderInfo g_TasksFolderInfo
0x180006772  cmp     word ptr [rcx+rsi*2+2], 0
0x180006778  lea     rsi, [rsi+1]
0x18000677c  jnz     short loc_180006772
0x18000677e  lea     eax, [rsi+9]
0x180006781  mov     r10d, 105h
0x180006787  cmp     eax, r10d
0x18000678a  jbe     loc_18000682E
0x180006790  mov     eax, 80004005h
0x180006795  mov     r13, [rsp+0B8h+var_18]
0x18000679d  mov     r14, [rsp+0B8h+var_20]
0x1800067a5  mov     r12, [rsp+0B8h+var_10]
0x1800067ad  mov     rdi, [rsp+0B8h+var_8]
0x1800067b5  mov     rsi, [rsp+0B8h+arg_10]
0x1800067bd  mov     rbp, [rsp+0B8h+arg_8]
0x1800067c5  mov     rbx, [rsp+0B8h+arg_0]
0x1800067cd  mov     r15, [rsp+0B8h+var_28]
0x1800067d5  mov     rcx, [rsp+0B8h+var_38]
0x1800067dd  xor     rcx, rsp; StackCookie
0x1800067e0  call    __security_check_cookie
0x1800067e5  add     rsp, 0B8h
0x1800067ec  retn
0x1800067ed  lea     rax, [rsp+0B8h+MaximumComponentLength]
0x1800067f2  mov     [rsp+0B8h+MaximumComponentLength], 4
0x1800067fa  mov     [rsp+0B8h+lpFileSystemFlags], rax; lpcbData
0x1800067ff  lea     rdx, ValueName; "NotifyOnTaskMiss"
0x180006806  lea     rax, ?g_fNotifyMiss@@3HA; int g_fNotifyMiss
0x18000680d  xor     r9d, r9d; lpType
0x180006810  xor     r8d, r8d; lpReserved
0x180006813  mov     [rsp+0B8h+lpMaximumComponentLength], rax; lpData
0x180006818  call    cs:__imp_RegQueryValueExW
0x18000681e  mov     rcx, qword ptr [rsp+0B8h+FileSystemFlags]; hKey
0x180006823  call    cs:__imp_RegCloseKey
0x180006829  jmp     loc_180006762
0x18000682e  lea     r11, ?g_wszAtJobSearchPath@@3PAGA; ushort near * g_wszAtJobSearchPath
0x180006835  mov     rax, r13
0x180006838  mov     r8, r11
0x18000683b  mov     r9, r10
0x18000683e  xchg    ax, ax
0x180006840  test    rax, rax
0x180006843  jz      short loc_180006862
0x180006845  movzx   edx, word ptr [rcx]
0x180006848  test    dx, dx
0x18000684b  jz      short loc_180006862
0x18000684d  mov     [r8], dx
0x180006851  add     rcx, 2
0x180006855  add     r8, 2
0x180006859  dec     rax
0x18000685c  sub     r9, 1
0x180006860  jnz     short loc_180006840
0x180006862  test    r9, r9
0x180006865  lea     rcx, [r8-2]
0x180006869  mov     rax, r11
0x18000686c  cmovnz  rcx, r8
0x180006870  mov     [rcx], bx
0x180006873  mov     rcx, r10
0x180006876  cmp     word ptr [rax], 0
0x18000687a  jz      short loc_180006886
0x18000687c  add     rax, 2
0x180006880  sub     rcx, 1
0x180006884  jnz     short loc_180006876
0x180006886  mov     r8, r10
0x180006889  sub     r8, rcx
0x18000688c  test    rcx, rcx
0x18000688f  cmovz   r8, rbx
0x180006893  jz      short loc_1800068D4
0x180006895  lea     rdx, aAtJob; "\\At*.job"
0x18000689c  lea     rax, [r11+r8*2]
0x1800068a0  sub     r10, r8
0x1800068a3  jz      short loc_1800068C6
0x1800068a5  test    r13, r13
0x1800068a8  jz      short loc_1800068C6
0x1800068aa  movzx   ecx, word ptr [rdx]
0x1800068ad  test    cx, cx
0x1800068b0  jz      short loc_1800068C6
0x1800068b2  mov     [rax], cx
0x1800068b5  add     rdx, 2
0x1800068b9  add     rax, 2
0x1800068bd  dec     r13
0x1800068c0  sub     r10, 1
0x1800068c4  jnz     short loc_1800068A5
0x1800068c6  test    r10, r10
0x1800068c9  lea     rcx, [rax-2]
0x1800068cd  cmovnz  rcx, rax
0x1800068d1  mov     [rcx], bx
0x1800068d4  mov     rax, 0C92A69C000h
0x1800068de  mov     cs:?FILETIMES_PER_DAY@@3_JA, rax; __int64 FILETIMES_PER_DAY
0x1800068e5  xor     eax, eax
0x1800068e7  jmp     loc_180006795
0x1800068ec  mov     ebx, 8007000Eh
0x1800068f1  mov     eax, ebx
0x1800068f3  jmp     loc_180006795
0x1800068f8  cmp     word ptr [rdi], 5Ch ; '\'
0x1800068fc  jnz     loc_18000662E
0x180006902  cmp     ebx, 1
0x180006905  jbe     loc_18000698D
0x18000690b  cmp     word ptr [rdi+2], 5Ch ; '\'
0x180006910  jnz     short loc_18000698D
0x180006912  lea     rax, [rdi+4]
0x180006916  mov     ecx, r9d
0x180006919  cmp     ebx, r12d
0x18000691c  jbe     short loc_18000698D
0x18000691e  cmp     [rax], r9w
0x180006922  jz      short loc_18000695C
0x180006924  cmp     ecx, 2
0x180006927  jnb     short loc_18000695F
0x180006929  cmp     r12d, ebx
0x18000692c  jnb     short loc_180006948
0x18000692e  movzx   edx, word ptr [rax]
0x180006931  test    dx, dx
0x180006934  jz      short loc_180006948
0x180006936  cmp     dx, 5Ch ; '\'
0x18000693a  jz      short loc_180006948
0x18000693c  inc     r12d
0x18000693f  add     rax, 2
0x180006943  cmp     r12d, ebx
0x180006946  jb      short loc_18000692E
0x180006948  cmp     [rax], r9w
0x18000694c  jz      short loc_18000698D
0x18000694e  inc     ecx
0x180006950  inc     r12d
0x180006953  add     rax, 2
0x180006957  cmp     r12d, ebx
0x18000695a  jb      short loc_18000691E
0x18000695c  cmp     ecx, 2
0x18000695f  jnz     short loc_18000698D
0x180006961  sub     rax, 2
0x180006965  jmp     loc_18000663D
0x18000696a  cmp     cx, 5Ch ; '\'
0x18000696e  jz      loc_18000663D
0x180006974  add     rax, r12
0x180006977  movzx   ecx, word ptr [rax]
0x18000697a  test    cx, cx
0x18000697d  jnz     short loc_18000696A
0x18000697f  jmp     loc_18000663D
0x180006984  mov     [r14], r9w
0x180006988  jmp     loc_1800066B0
0x18000698d  cmp     r15d, 2
0x180006991  jb      short loc_18000699F
0x180006993  mov     dword ptr [r14], 5Ch ; '\'
0x18000699a  jmp     loc_1800066B5
0x18000699f  test    r15d, r15d
0x1800069a2  jz      loc_1800066B5
0x1800069a8  mov     [r14], r9w
0x1800069ac  jmp     loc_1800066B5
0x1800069b1  mov     rcx, r14; Block
0x1800069b4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800069b9  lea     rdx, aNtfs; "NTFS"
0x1800069c0  lea     rcx, [rsp+0B8h+FileSystemNameBuffer]; String1
0x1800069c5  call    cs:__imp__wcsicmp
0x1800069cb  xor     ebx, ebx
0x1800069cd  mov     ecx, ebx
0x1800069cf  test    eax, eax
0x1800069d1  setz    cl
0x1800069d4  mov     cs:dword_180023EC8, ecx
0x1800069da  jmp     loc_180006722
```
