# lEnumDirTree(void *,ushort const *,ushort const *,ushort *,_EDT_CALLBACK *,int *)

- ea: `0x1801a93d0`
- end: `0x1801a97bc`
- name: `?lEnumDirTree@@YAHPEAXPEBG1PEAGPEAU_EDT_CALLBACK@@PEAH@Z`
- size: `1004`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, struct _EDT_CALLBACK *, int *)`
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1801a93d0`
- `0x1801a97d0`
- `0x1801a9900`

## callees

- `0x18000aeec`
- `0x18000dfac`
- `0x18000f998`
- `0x180012e28`
- `0x180012e6c`
- `0x180012ed4`
- `0x180015f04`
- `0x180021374`
- `0x1801a8d6c`
- `0x1801a93d0`
- `0x1801aef0c`
- `0x1801af030`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a94cc`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1801a94cc`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1801a9538`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1801a9538`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801a9736`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1801a9736`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9606`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9627`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9636`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9606`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9627`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801a9636`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a95f9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a9779`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a95f9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1801a9779`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a956b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a96cb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a956b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801a96cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a964f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a964f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a9791`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801a9791`

## string_xrefs

- `0x1801a966a`: `%s - drive not ready\n`

## pseudocode

```c
__int64 __fastcall lEnumDirTree(
        void *a1,
        const unsigned __int16 *a2,
        wchar_t *a3,
        unsigned __int16 *a4,
        struct _EDT_CALLBACK *a5,
        int *a6)
{
  struct _PROCESS_ENTRY *ProcessEntry; // rdi
  __int64 v10; // rax
  __int64 v11; // r12
  HANDLE FirstFileW; // rbx
  unsigned __int16 *v13; // rdi
  int v14; // eax
  wchar_t *v16; // r14
  unsigned int v17; // [rsp+50h] [rbp-B0h]
  struct _PROCESS_ENTRY *v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch] BYREF
  wchar_t *FullPath; // [rsp+68h] [rbp-98h]
  void *v22; // [rsp+70h] [rbp-90h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v24[264]; // [rsp+290h] [rbp+190h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+4A0h] [rbp+3A0h] BYREF
  wchar_t Filename[264]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t Ext[264]; // [rsp+B40h] [rbp+A40h] BYREF

  FullPath = a3;
  v22 = a1;
  *a6 = 0;
  ProcessEntry = FindProcessEntry(a1);
  if ( (unsigned int)DoCallback(ProcessEntry, 7u, 0) )
    return 0;
  v18 = ProcessEntry;
  v20 = 0;
  v19 = MarkOperationStart(ProcessEntry, &v20);
  if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v18) )
    return 0;
  ToggleFailCriticalErrors(0);
  if ( !a2 || !a3 )
  {
    SetLastError(0x57u);
    return 0;
  }
  v17 = 1;
  _wsplitpath_s(a3, 0, 0, 0, 0, Filename, 0x105u, Ext, 0x101u);
  wcscat_s_ex(Filename, 0x105u, Ext);
  wcscpy_s_ex(FileName, 0x105u, a2);
  if ( *a2 && !(unsigned int)BackslashCat(FileName, 261) )
    goto LABEL_26;
  wcscpy_s_ex(v24, 0x105u, FileName);
  if ( (unsigned int)_o_wcsncat_s(FileName, 261, Filename, -1) == 80 )
    goto LABEL_26;
  v10 = -1;
  do
    ++v10;
  while ( v24[v10] );
  v11 = v10;
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    v13 = &v24[v11];
    while ( 1 )
    {
      if ( (unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v18) )
      {
        FindClose(FirstFileW);
LABEL_24:
        *a6 = 1;
LABEL_25:
        FindClose(FirstFileW);
        goto LABEL_26;
      }
      if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
      {
        wcscpy_s_ex(&v24[v11], 261 - ((v11 * 2) >> 1), FindFileData.cFileName);
        if ( a5 && *(_QWORD *)a5 )
        {
          v14 = EnumDirTreeCallback(a5, v24);
          *a6 = v14;
          if ( !v14 )
            goto LABEL_20;
        }
        else
        {
          *a6 = 1;
        }
        if ( a4 )
        {
          wcscpy_s_ex(a4, 0x105u, v24);
          goto LABEL_25;
        }
      }
LABEL_20:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        FindClose(FirstFileW);
        goto LABEL_31;
      }
    }
  }
  if ( GetLastError() == 21 )
  {
    if ( (unsigned int)spew() )
      _pwprint(ProcessEntry, L"%s - drive not ready\n", FileName);
  }
  else
  {
    v13 = &v24[v11];
LABEL_31:
    wcscpy_s_ex(FileName, 0x105u, a2);
    if ( !*a2 || (unsigned int)BackslashCat(FileName, 261) )
    {
      wcscat_s_ex(FileName, 0x105u, L"*.*");
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        v16 = FullPath;
        while ( !(unsigned int)CancellationCheck::IsCancelled((CancellationCheck *)&v18) )
        {
          if ( (FindFileData.dwFileAttributes & 0x10) != 0
            && (FindFileData.cFileName[0] != 46 || FindFileData.cFileName[1] && FindFileData.cFileName[1] != 46)
            && (unsigned int)_o_wcsncpy_s(v13, 261 - ((v11 * 2) >> 1), FindFileData.cFileName, -1) != 80 )
          {
            v17 = lEnumDirTree(v22, v24, v16, a4, a5, a6);
            if ( *a6 )
              goto LABEL_25;
          }
          if ( !FindNextFileW(FirstFileW, &FindFileData) )
            goto LABEL_25;
        }
        goto LABEL_24;
      }
    }
  }
LABEL_26:
  ToggleFailCriticalErrors(1);
  return v17;
}

```

## disassembly

```asm
0x1801a93d0  push    rbp
0x1801a93d2  push    rbx
0x1801a93d3  push    rsi
0x1801a93d4  push    rdi
0x1801a93d5  push    r12
0x1801a93d7  push    r13
0x1801a93d9  push    r14
0x1801a93db  push    r15
0x1801a93dd  lea     rbp, [rsp-0C68h]
0x1801a93e5  sub     rsp, 0D68h
0x1801a93ec  mov     rax, cs:__security_cookie
0x1801a93f3  xor     rax, rsp
0x1801a93f6  mov     [rbp+0CA0h+var_50], rax
0x1801a93fd  mov     rsi, [rbp+0CA0h+arg_28]
0x1801a9404  mov     rbx, r8
0x1801a9407  mov     r13, [rbp+0CA0h+arg_20]
0x1801a940e  xor     r12d, r12d
0x1801a9411  mov     r15, r9
0x1801a9414  mov     [rsp+0DA0h+FullPath], rbx
0x1801a9419  mov     r14, rdx
0x1801a941c  mov     [rsp+0DA0h+var_D30], rcx
0x1801a9421  mov     [rsi], r12d
0x1801a9424  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x1801a9429  xor     r8d, r8d; void *
0x1801a942c  lea     edx, [r12+7]; unsigned int
0x1801a9431  mov     rcx, rax; struct _PROCESS_ENTRY *
0x1801a9434  mov     rdi, rax
0x1801a9437  call    ?DoCallback@@YAHPEAU_PROCESS_ENTRY@@KPEAX@Z; DoCallback(_PROCESS_ENTRY *,ulong,void *)
0x1801a943c  test    eax, eax
0x1801a943e  jnz     loc_1801A9797
0x1801a9444  lea     rdx, [rsp+0DA0h+var_D3C]
0x1801a9449  mov     [rsp+0DA0h+var_D48], rdi
0x1801a944e  mov     rcx, rdi
0x1801a9451  mov     [rsp+60h], r12
0x1801a9456  call    MarkOperationStart
0x1801a945b  lea     rcx, [rsp+0DA0h+var_D48]; this
0x1801a9460  mov     [rsp+0DA0h+var_D40], eax
0x1801a9464  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a9469  test    eax, eax
0x1801a946b  jnz     loc_1801A9797
0x1801a9471  xor     ecx, ecx; int
0x1801a9473  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x1801a9478  test    r14, r14
0x1801a947b  jz      loc_1801A978C
0x1801a9481  test    rbx, rbx
0x1801a9484  jz      loc_1801A978C
0x1801a948a  mov     [rsp+0DA0h+ExtCount], 101h; ExtCount
0x1801a9493  lea     rax, [rbp+0CA0h+var_260]
0x1801a949a  mov     [rsp+0DA0h+Ext], rax; Ext
0x1801a949f  xor     r9d, r9d; Dir
0x1801a94a2  lea     rax, [rbp+0CA0h+var_470]
0x1801a94a9  mov     [rsp+0DA0h+FilenameCount], 105h; FilenameCount
0x1801a94b2  mov     [rsp+0DA0h+Filename], rax; Filename
0x1801a94b7  xor     r8d, r8d; DriveCount
0x1801a94ba  xor     edx, edx; Drive
0x1801a94bc  mov     [rsp+0DA0h+DirCount], r12; DirCount
0x1801a94c1  mov     rcx, rbx; FullPath
0x1801a94c4  mov     [rsp+0DA0h+var_D50], 1
0x1801a94cc  call    cs:__imp__wsplitpath_s
0x1801a94d2  mov     ebx, 105h
0x1801a94d7  lea     r8, [rbp+0CA0h+var_260]; unsigned __int16 *
0x1801a94de  mov     edx, ebx; unsigned __int64
0x1801a94e0  lea     rcx, [rbp+0CA0h+var_470]; unsigned __int16 *
0x1801a94e7  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a94ec  mov     r8, r14; unsigned __int16 *
0x1801a94ef  lea     rcx, [rbp+0CA0h+FileName]; unsigned __int16 *
0x1801a94f3  mov     edx, ebx; unsigned __int64
0x1801a94f5  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a94fa  cmp     [r14], r12w
0x1801a94fe  jz      short loc_1801A9513
0x1801a9500  mov     edx, ebx
0x1801a9502  lea     rcx, [rbp+0CA0h+FileName]
0x1801a9506  call    BackslashCat
0x1801a950b  test    eax, eax
0x1801a950d  jz      loc_1801A963C
0x1801a9513  lea     r8, [rbp+0CA0h+FileName]; unsigned __int16 *
0x1801a9517  mov     rdx, rbx; unsigned __int64
0x1801a951a  lea     rcx, [rbp+0CA0h+var_B10]; unsigned __int16 *
0x1801a9521  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a9526  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801a952a  lea     r8, [rbp+0CA0h+var_470]
0x1801a9531  mov     rdx, rbx
0x1801a9534  lea     rcx, [rbp+0CA0h+FileName]
0x1801a9538  call    cs:__imp__o_wcsncat_s
0x1801a953e  cmp     eax, 50h ; 'P'
0x1801a9541  jz      loc_1801A963C
0x1801a9547  lea     rcx, [rbp+0CA0h+var_B10]
0x1801a954e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801a9552  inc     rax
0x1801a9555  cmp     [rcx+rax*2], r12w
0x1801a955a  jnz     short loc_1801A9552
0x1801a955c  lea     rdx, [rbp+0CA0h+FindFileData]; lpFindFileData
0x1801a9563  lea     rcx, [rbp+0CA0h+FileName]; lpFileName
0x1801a9567  lea     r12, [rax+rax]
0x1801a956b  call    cs:__imp_FindFirstFileW
0x1801a9571  mov     rbx, rax
0x1801a9574  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a9578  jz      loc_1801A964F
0x1801a957e  lea     rdi, [rbp+0CA0h+var_B10]
0x1801a9585  add     rdi, r12
0x1801a9588  lea     rcx, [rsp+0DA0h+var_D48]; this
0x1801a958d  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a9592  test    eax, eax
0x1801a9594  jnz     loc_1801A9624
0x1801a959a  test    byte ptr [rbp+0CA0h+FindFileData.dwFileAttributes], 10h
0x1801a95a1  jnz     short loc_1801A95EF
0x1801a95a3  mov     rax, r12
0x1801a95a6  lea     r8, [rbp+0CA0h+FindFileData.cFileName]; unsigned __int16 *
0x1801a95ad  sar     rax, 1
0x1801a95b0  mov     edx, 105h
0x1801a95b5  sub     rdx, rax; unsigned __int64
0x1801a95b8  mov     rcx, rdi; unsigned __int16 *
0x1801a95bb  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a95c0  xor     eax, eax
0x1801a95c2  test    r13, r13
0x1801a95c5  jz      short loc_1801A95E4
0x1801a95c7  cmp     [r13+0], rax
0x1801a95cb  jz      short loc_1801A95E4
0x1801a95cd  lea     rdx, [rbp+0CA0h+var_B10]; unsigned __int16 *
0x1801a95d4  mov     rcx, r13; struct _EDT_CALLBACK *
0x1801a95d7  call    ?EnumDirTreeCallback@@YAHPEAU_EDT_CALLBACK@@PEBG@Z; EnumDirTreeCallback(_EDT_CALLBACK *,ushort const *)
0x1801a95dc  mov     [rsi], eax
0x1801a95de  test    eax, eax
0x1801a95e0  jz      short loc_1801A95EF
0x1801a95e2  jmp     short loc_1801A95EA
0x1801a95e4  mov     dword ptr [rsi], 1
0x1801a95ea  test    r15, r15
0x1801a95ed  jnz     short loc_1801A960E
0x1801a95ef  lea     rdx, [rbp+0CA0h+FindFileData]; lpFindFileData
0x1801a95f6  mov     rcx, rbx; hFindFile
0x1801a95f9  call    cs:__imp_FindNextFileW
0x1801a95ff  test    eax, eax
0x1801a9601  jnz     short loc_1801A9588
0x1801a9603  mov     rcx, rbx; hFindFile
0x1801a9606  call    cs:__imp_FindClose
0x1801a960c  jmp     short loc_1801A9682
0x1801a960e  lea     r8, [rbp+0CA0h+var_B10]; unsigned __int16 *
0x1801a9615  mov     edx, 105h; unsigned __int64
0x1801a961a  mov     rcx, r15; unsigned __int16 *
0x1801a961d  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a9622  jmp     short loc_1801A9633
0x1801a9624  mov     rcx, rbx; hFindFile
0x1801a9627  call    cs:__imp_FindClose
0x1801a962d  mov     dword ptr [rsi], 1
0x1801a9633  mov     rcx, rbx; hFindFile
0x1801a9636  call    cs:__imp_FindClose
0x1801a963c  mov     ecx, 1; int
0x1801a9641  call    ?ToggleFailCriticalErrors@@YAHH@Z; ToggleFailCriticalErrors(int)
0x1801a9646  mov     eax, [rsp+0DA0h+var_D50]
0x1801a964a  jmp     loc_1801A9799
0x1801a964f  call    cs:__imp_GetLastError
0x1801a9655  cmp     eax, 15h
0x1801a9658  jnz     short loc_1801A9678
0x1801a965a  call    ?spew@@YAHXZ; spew(void)
0x1801a965f  test    eax, eax
0x1801a9661  jz      short loc_1801A963C
0x1801a9663  lea     r8, [rbp+0CA0h+FileName]
0x1801a9667  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1801a966a  lea     rdx, aSDriveNotReady; "%s - drive not ready\n"
0x1801a9671  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x1801a9676  jmp     short loc_1801A963C
0x1801a9678  lea     rdi, [rbp+0CA0h+var_B10]
0x1801a967f  add     rdi, r12
0x1801a9682  mov     ebx, 105h
0x1801a9687  lea     rcx, [rbp+0CA0h+FileName]; unsigned __int16 *
0x1801a968b  mov     edx, ebx; unsigned __int64
0x1801a968d  mov     r8, r14; unsigned __int16 *
0x1801a9690  call    ?wcscpy_s_ex@@YAHPEAG_KPEBG@Z; wcscpy_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a9695  xor     r11d, r11d
0x1801a9698  cmp     [r14], r11w
0x1801a969c  jz      short loc_1801A96AD
0x1801a969e  mov     edx, ebx
0x1801a96a0  lea     rcx, [rbp+0CA0h+FileName]
0x1801a96a4  call    BackslashCat
0x1801a96a9  test    eax, eax
0x1801a96ab  jz      short loc_1801A963C
0x1801a96ad  lea     r8, asc_180254678; "*.*"
0x1801a96b4  mov     rdx, rbx; unsigned __int64
0x1801a96b7  lea     rcx, [rbp+0CA0h+FileName]; unsigned __int16 *
0x1801a96bb  call    ?wcscat_s_ex@@YAHPEAG_KPEBG@Z; wcscat_s_ex(ushort *,unsigned __int64,ushort const *)
0x1801a96c0  lea     rdx, [rbp+0CA0h+FindFileData]; lpFindFileData
0x1801a96c7  lea     rcx, [rbp+0CA0h+FileName]; lpFileName
0x1801a96cb  call    cs:__imp_FindFirstFileW
0x1801a96d1  mov     rbx, rax
0x1801a96d4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a96d8  jz      loc_1801A963C
0x1801a96de  mov     r14, [rsp+0DA0h+FullPath]
0x1801a96e3  lea     rcx, [rsp+0DA0h+var_D48]; this
0x1801a96e8  call    ?IsCancelled@CancellationCheck@@QEBAHXZ; CancellationCheck::IsCancelled(void)
0x1801a96ed  test    eax, eax
0x1801a96ef  jnz     loc_1801A962D
0x1801a96f5  test    byte ptr [rbp+0CA0h+FindFileData.dwFileAttributes], 10h
0x1801a96fc  jz      short loc_1801A976F
0x1801a96fe  cmp     [rbp+0CA0h+FindFileData.cFileName], 2Eh ; '.'
0x1801a9706  jnz     short loc_1801A971A
0x1801a9708  movzx   eax, [rbp+0CA0h+FindFileData.cFileName+2]
0x1801a970f  test    ax, ax
0x1801a9712  jz      short loc_1801A976F
0x1801a9714  cmp     ax, 2Eh ; '.'
0x1801a9718  jz      short loc_1801A976F
0x1801a971a  mov     rax, r12
0x1801a971d  lea     r8, [rbp+0CA0h+FindFileData.cFileName]
0x1801a9724  sar     rax, 1
0x1801a9727  mov     edx, 105h
0x1801a972c  sub     rdx, rax
0x1801a972f  or      r9, 0FFFFFFFFFFFFFFFFh
0x1801a9733  mov     rcx, rdi
0x1801a9736  call    cs:__imp__o_wcsncpy_s
0x1801a973c  cmp     eax, 50h ; 'P'
0x1801a973f  jz      short loc_1801A976F
0x1801a9741  mov     rcx, [rsp+0DA0h+var_D30]; void *
0x1801a9746  lea     rdx, [rbp+0CA0h+var_B10]; unsigned __int16 *
0x1801a974d  mov     [rsp+0DA0h+Filename], rsi; int *
0x1801a9752  mov     r9, r15; unsigned __int16 *
0x1801a9755  mov     r8, r14; unsigned __int16 *
0x1801a9758  mov     [rsp+0DA0h+DirCount], r13; struct _EDT_CALLBACK *
0x1801a975d  call    ?lEnumDirTree@@YAHPEAXPEBG1PEAGPEAU_EDT_CALLBACK@@PEAH@Z; lEnumDirTree(void *,ushort const *,ushort const *,ushort *,_EDT_CALLBACK *,int *)
0x1801a9762  cmp     dword ptr [rsi], 0
0x1801a9765  mov     [rsp+0DA0h+var_D50], eax
0x1801a9769  jnz     loc_1801A9633
0x1801a976f  lea     rdx, [rbp+0CA0h+FindFileData]; lpFindFileData
0x1801a9776  mov     rcx, rbx; hFindFile
0x1801a9779  call    cs:__imp_FindNextFileW
0x1801a977f  test    eax, eax
0x1801a9781  jnz     loc_1801A96E3
0x1801a9787  jmp     loc_1801A9633
0x1801a978c  mov     ecx, 57h ; 'W'; dwErrCode
0x1801a9791  call    cs:__imp_SetLastError
0x1801a9797  xor     eax, eax
0x1801a9799  mov     rcx, [rbp+0CA0h+var_50]
0x1801a97a0  xor     rcx, rsp; StackCookie
0x1801a97a3  call    __security_check_cookie
0x1801a97a8  add     rsp, 0D68h
0x1801a97af  pop     r15
0x1801a97b1  pop     r14
0x1801a97b3  pop     r13
0x1801a97b5  pop     r12
0x1801a97b7  pop     rdi
0x1801a97b8  pop     rsi
0x1801a97b9  pop     rbx
0x1801a97ba  pop     rbp
0x1801a97bb  retn
```
