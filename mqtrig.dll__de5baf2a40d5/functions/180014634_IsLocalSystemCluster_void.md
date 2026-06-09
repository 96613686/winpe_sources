# IsLocalSystemCluster(void)

- ea: `0x180014634`
- end: `0x180014822`
- name: `?IsLocalSystemCluster@@YA_NXZ`
- size: `494`
- prototype: `char(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180014054`

## callees

- `0x180001ce6`
- `0x180005574`
- `0x18000c62c`
- `0x18000c654`
- `0x180014634`
- `0x180022010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800146e8`
- `KERNEL32!GetProcAddress` at `0x1800146e8`
- `KERNEL32!LoadLibraryW` at `0x180014641`
- `KERNEL32!LoadLibraryW` at `0x180014641`
- `KERNEL32!GetLastError` at `0x180014657`
- `KERNEL32!GetLastError` at `0x1800146f3`
- `KERNEL32!GetLastError` at `0x180014657`
- `KERNEL32!GetLastError` at `0x1800146f3`

## string_xrefs

- `0x18001463a`: `clusapi.dll`

## pseudocode

```c
char IsLocalSystemCluster(void)
{
  HMODULE LibraryW; // rax
  DWORD LastError; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  FARPROC ProcAddress; // rax
  DWORD v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  int v12; // [rsp+50h] [rbp+8h] BYREF

  LibraryW = LoadLibraryW(L"clusapi.dll");
  g_hLib = LibraryW;
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError != 126 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids, LastError);
      bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v2);
      throw (bad_win32_error *)pExceptionObject;
    }
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v4 = 15;
    goto LABEL_24;
  }
  ProcAddress = GetProcAddress(LibraryW, "GetNodeClusterState");
  if ( !ProcAddress )
  {
    v6 = GetLastError();
    v7 = v6;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids, v6);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v7);
    throw (bad_win32_error *)pExceptionObject;
  }
  v12 = 0;
  v8 = ((__int64 (__fastcall *)(_QWORD, int *))ProcAddress)(0, &v12);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids, v8);
    bad_win32_error::bad_win32_error((bad_win32_error *)pExceptionObject, v9);
    throw (bad_win32_error *)pExceptionObject;
  }
  if ( v12 != 19 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return 0;
    v4 = 18;
LABEL_24:
    WPP_SF_(v3[2], v4, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x180014634  push    rbx
0x180014636  sub     rsp, 40h
0x18001463a  lea     rcx, LibFileName; "clusapi.dll"
0x180014641  call    cs:__imp_LoadLibraryW
0x180014647  mov     cs:?g_hLib@@3VCAutoFreeLibrary@@A, rax; CAutoFreeLibrary g_hLib
0x18001464e  test    rax, rax
0x180014651  jnz     loc_1800146DE
0x180014657  call    cs:__imp_GetLastError
0x18001465d  mov     ebx, eax
0x18001465f  cmp     eax, 7Eh ; '~'
0x180014662  jz      short loc_1800146B3
0x180014664  mov     rcx, cs:WPP_GLOBAL_Control
0x18001466b  lea     rdx, WPP_GLOBAL_Control
0x180014672  cmp     rcx, rdx
0x180014675  jz      short loc_180014695
0x180014677  test    byte ptr [rcx+1Ch], 1
0x18001467b  jz      short loc_180014695
0x18001467d  mov     rcx, [rcx+10h]
0x180014681  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014688  mov     edx, 0Eh
0x18001468d  mov     r9d, eax
0x180014690  call    WPP_SF_d
0x180014695  mov     edx, ebx; unsigned int
0x180014697  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001469c  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800146a1  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800146a8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800146ad  call    _CxxThrowException_0
0x1800146b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146ba  lea     rdx, WPP_GLOBAL_Control
0x1800146c1  cmp     rcx, rdx
0x1800146c4  jz      loc_1800147E8
0x1800146ca  test    byte ptr [rcx+1Ch], 4
0x1800146ce  jz      loc_1800147E8
0x1800146d4  mov     edx, 0Fh
0x1800146d9  jmp     loc_1800147D8
0x1800146de  lea     rdx, aGetnodecluster; "GetNodeClusterState"
0x1800146e5  mov     rcx, rax; hModule
0x1800146e8  call    cs:__imp_GetProcAddress
0x1800146ee  test    rax, rax
0x1800146f1  jnz     short loc_18001474A
0x1800146f3  call    cs:__imp_GetLastError
0x1800146f9  mov     ebx, eax
0x1800146fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014702  lea     rdx, WPP_GLOBAL_Control
0x180014709  cmp     rcx, rdx
0x18001470c  jz      short loc_18001472C
0x18001470e  test    byte ptr [rcx+1Ch], 1
0x180014712  jz      short loc_18001472C
0x180014714  mov     rcx, [rcx+10h]
0x180014718  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x18001471f  mov     edx, 10h
0x180014724  mov     r9d, eax
0x180014727  call    WPP_SF_d
0x18001472c  mov     edx, ebx; unsigned int
0x18001472e  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180014733  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x180014738  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x18001473f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180014744  call    _CxxThrowException_0
0x18001474a  lea     rdx, [rsp+48h+arg_0]
0x18001474f  mov     [rsp+48h+arg_0], 0
0x180014757  xor     ecx, ecx
0x180014759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001475e  mov     ebx, eax
0x180014760  test    eax, eax
0x180014762  jz      short loc_1800147B3
0x180014764  mov     rcx, cs:WPP_GLOBAL_Control
0x18001476b  lea     rdx, WPP_GLOBAL_Control
0x180014772  cmp     rcx, rdx
0x180014775  jz      short loc_180014795
0x180014777  test    byte ptr [rcx+1Ch], 1
0x18001477b  jz      short loc_180014795
0x18001477d  mov     rcx, [rcx+10h]
0x180014781  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014788  mov     edx, 11h
0x18001478d  mov     r9d, eax
0x180014790  call    WPP_SF_d
0x180014795  mov     edx, ebx; unsigned int
0x180014797  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001479c  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800147a1  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800147a8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800147ad  call    _CxxThrowException_0
0x1800147b3  cmp     [rsp+48h+arg_0], 13h
0x1800147b8  jz      short loc_1800147EC
0x1800147ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147c1  lea     rdx, WPP_GLOBAL_Control
0x1800147c8  cmp     rcx, rdx
0x1800147cb  jz      short loc_1800147E8
0x1800147cd  test    byte ptr [rcx+1Ch], 4
0x1800147d1  jz      short loc_1800147E8
0x1800147d3  mov     edx, 12h
0x1800147d8  mov     rcx, [rcx+10h]
0x1800147dc  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x1800147e3  call    WPP_SF_
0x1800147e8  xor     al, al
0x1800147ea  jmp     short loc_18001481C
0x1800147ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147f3  lea     rdx, WPP_GLOBAL_Control
0x1800147fa  cmp     rcx, rdx
0x1800147fd  jz      short loc_18001481A
0x1800147ff  test    byte ptr [rcx+1Ch], 4
0x180014803  jz      short loc_18001481A
0x180014805  mov     rcx, [rcx+10h]
0x180014809  lea     r8, WPP_e6c45f08be9433bf899a63ba3aa38a01_Traceguids
0x180014810  mov     edx, 13h
0x180014815  call    WPP_SF_
0x18001481a  mov     al, 1
0x18001481c  add     rsp, 40h
0x180014820  pop     rbx
0x180014821  retn
```
