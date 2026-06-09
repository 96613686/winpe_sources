# HashMasterKeyFile(void *,_MK_LOCATION *,void *)

- ea: `0x180001ff0`
- end: `0x180002304`
- name: `?HashMasterKeyFile@@YAKPEAXPEAU_MK_LOCATION@@0@Z`
- size: `788`
- prototype: `__int64 __fastcall(void *, struct _MK_LOCATION *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001e60`

## callees

- `0x180001ff0`
- `0x1800060e0`
- `0x180007f10`
- `0x180013bec`
- `0x180013f2c`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001eb8c`
- `0x180039bb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000224d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002176`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002157`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002176`
- `bcrypt!BCryptHashData` at `0x18000228f`
- `bcrypt!BCryptHashData` at `0x18000228f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002230`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180002230`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800021d0`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1800021d0`
- `ntdll!RtlNtStatusToDosError` at `0x1800022be`
- `ntdll!RtlNtStatusToDosError` at `0x1800022be`

## string_xrefs

- `0x180002121`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x180002197`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x180002261`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x1800022a7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall HashMasterKeyFile(void *a1, struct _MK_LOCATION *a2, void *a3)
{
  __int64 v6; // rcx
  int v7; // edx
  unsigned int LastError; // ebx
  HANDLE FileMappingW; // rax
  int v10; // edx
  UCHAR *v11; // rax
  NTSTATUS v12; // eax
  NTSTATUS v13; // ebx
  UCHAR **v15; // [rsp+40h] [rbp-20h] BYREF
  UCHAR *v16; // [rsp+48h] [rbp-18h] BYREF
  void **p_hObject; // [rsp+50h] [rbp-10h] BYREF
  void **p_hFile; // [rsp+58h] [rbp-8h] BYREF
  HANDLE hFile; // [rsp+88h] [rbp+28h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp+38h] BYREF

  hFile = (HANDLE)-1LL;
  p_hFile = &hFile;
  hObject = 0;
  p_hObject = &hObject;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 26, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(v6 + 28) & 4) != 0 )
      {
        WPP_SF_S(*(_QWORD *)(v6 + 16), 27, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids, *(_QWORD *)a2);
        v6 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(v6 + 28) & 4) != 0 )
        {
          WPP_SF_S(*(_QWORD *)(v6 + 16), 28, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids, *((_QWORD *)a2 + 1));
          v6 = WPP_GLOBAL_Control;
        }
        if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
          WPP_SF_d(*(_QWORD *)(v6 + 16), 29, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids, *((unsigned int *)a2 + 4));
      }
    }
  }
  LastError = OpenFileInStorageArea(
                a1,
                0x80000000,
                *(const unsigned __int16 **)a2,
                *((const unsigned __int16 **)a2 + 1),
                &hFile);
  if ( !LastError )
  {
    if ( hFile == (HANDLE)-1LL )
    {
      LastError = 1168;
      DebugTraceError(1168, "ERROR_NOT_FOUND", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", 601);
    }
    else
    {
      FileMappingW = CreateFileMappingW(hFile, 0, 2u, 0, 0, 0);
      hObject = FileMappingW;
      if ( !FileMappingW )
      {
        LastError = GetLastError();
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_sDsd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            v10,
            (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
            (unsigned int)"dwLastError",
            LastError,
            (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
            105);
        goto LABEL_17;
      }
      v11 = (UCHAR *)MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      v16 = v11;
      v15 = &v16;
      if ( v11 )
      {
        v12 = BCryptHashData(a3, v11, *((_DWORD *)a2 + 4), 0);
        v13 = v12;
        if ( v12 >= 0 )
        {
          ScopedUnMapView::~ScopedUnMapView((ScopedUnMapView *)&v15);
          LastError = 0;
          goto LABEL_33;
        }
        DebugTraceError(
          (unsigned int)v12,
          "ntStatus",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
          634);
        LastError = RtlNtStatusToDosError(v13);
      }
      else
      {
        LastError = GetLastError();
        DebugTraceError(
          LastError,
          "dwLastError",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
          627);
      }
      ScopedUnMapView::~ScopedUnMapView((ScopedUnMapView *)&v15);
    }
LABEL_33:
    ScopedCloseHandle::~ScopedCloseHandle(&p_hObject);
    ScopedCloseHandle::~ScopedCloseHandle(&p_hFile);
    return LastError;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_sDsd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v7,
      (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
      (unsigned int)"dwLastError",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
      83);
LABEL_17:
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hFile);
  return LastError;
}

```

## disassembly

```asm
0x180001ff0  mov     [rsp-18h+arg_0], rbx
0x180001ff5  mov     [rsp-18h+arg_10], rsi
0x180001ffa  push    rbp
0x180001ffb  push    rdi
0x180001ffc  push    r15
0x180001ffe  mov     rbp, rsp
0x180002001  sub     rsp, 60h
0x180002005  mov     rsi, r8
0x180002008  mov     rdi, rdx
0x18000200b  mov     rbx, rcx
0x18000200e  mov     [rbp+hFile], 0FFFFFFFFFFFFFFFFh
0x180002016  lea     rax, [rbp+hFile]
0x18000201a  mov     [rbp+var_8], rax
0x18000201e  mov     [rbp+hObject], 0
0x180002026  lea     rax, [rbp+hObject]
0x18000202a  mov     [rbp+var_10], rax
0x18000202e  lea     r15, WPP_GLOBAL_Control
0x180002035  mov     rcx, cs:WPP_GLOBAL_Control
0x18000203c  cmp     rcx, r15
0x18000203f  jz      loc_1800020E0
0x180002045  test    byte ptr [rcx+1Ch], 4
0x180002049  jz      short loc_180002067
0x18000204b  mov     edx, 1Ah
0x180002050  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180002057  mov     rcx, [rcx+10h]
0x18000205b  call    WPP_SF_
0x180002060  mov     rcx, cs:WPP_GLOBAL_Control
0x180002067  cmp     rcx, r15
0x18000206a  jz      short loc_1800020E0
0x18000206c  test    byte ptr [rcx+1Ch], 4
0x180002070  jz      short loc_180002091
0x180002072  mov     edx, 1Bh
0x180002077  mov     r9, [rdi]
0x18000207a  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180002081  mov     rcx, [rcx+10h]
0x180002085  call    WPP_SF_S
0x18000208a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002091  cmp     rcx, r15
0x180002094  jz      short loc_1800020E0
0x180002096  test    byte ptr [rcx+1Ch], 4
0x18000209a  jz      short loc_1800020BC
0x18000209c  mov     edx, 1Ch
0x1800020a1  mov     r9, [rdi+8]
0x1800020a5  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x1800020ac  mov     rcx, [rcx+10h]
0x1800020b0  call    WPP_SF_S
0x1800020b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020bc  cmp     rcx, r15
0x1800020bf  jz      short loc_1800020E0
0x1800020c1  test    byte ptr [rcx+1Ch], 4
0x1800020c5  jz      short loc_1800020E0
0x1800020c7  mov     edx, 1Dh
0x1800020cc  mov     r9d, [rdi+10h]
0x1800020d0  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x1800020d7  mov     rcx, [rcx+10h]
0x1800020db  call    WPP_SF_d
0x1800020e0  lea     rax, [rbp+hFile]
0x1800020e4  mov     qword ptr [rsp+60h+dwMaximumSizeLow], rax; void **
0x1800020e9  mov     r9, [rdi+8]; unsigned __int16 *
0x1800020ed  mov     r8, [rdi]; unsigned __int16 *
0x1800020f0  mov     edx, 80000000h; unsigned int
0x1800020f5  mov     rcx, rbx; void *
0x1800020f8  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x1800020fd  mov     ebx, eax
0x1800020ff  test    eax, eax
0x180002101  jz      loc_180002187
0x180002107  mov     rcx, cs:WPP_GLOBAL_Control
0x18000210e  cmp     rcx, r15
0x180002111  jz      short loc_180002149
0x180002113  test    byte ptr [rcx+1Ch], 1
0x180002117  jz      short loc_180002149
0x180002119  mov     [rsp+60h+var_30], 253h
0x180002121  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180002128  mov     [rsp+60h+lpName], r8
0x18000212d  mov     [rsp+60h+dwMaximumSizeLow], ebx
0x180002131  lea     r9, aDwlasterror; "dwLastError"
0x180002138  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000213f  mov     rcx, [rcx+10h]
0x180002143  call    WPP_SF_sDsd
0x180002148  nop
0x180002149  mov     rcx, [rbp+hObject]; hObject
0x18000214d  lea     rax, [rcx-1]
0x180002151  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002155  ja      short loc_180002164
0x180002157  call    cs:__imp_CloseHandle
0x18000215e  nop     dword ptr [rax+rax+00h]
0x180002163  nop
0x180002164  mov     rcx, [rbp+hFile]; hObject
0x180002168  lea     rax, [rcx-1]
0x18000216c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180002170  ja      loc_1800022EC
0x180002176  call    cs:__imp_CloseHandle
0x18000217d  nop     dword ptr [rax+rax+00h]
0x180002182  jmp     loc_1800022EC
0x180002187  mov     rcx, [rbp+hFile]; hFile
0x18000218b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000218f  jnz     short loc_1800021B6
0x180002191  mov     r9d, 259h
0x180002197  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000219e  lea     rdx, aErrorNotFound; "ERROR_NOT_FOUND"
0x1800021a5  mov     ebx, 490h
0x1800021aa  mov     ecx, ebx
0x1800021ac  call    DebugTraceError
0x1800021b1  jmp     loc_1800022D9
0x1800021b6  mov     [rsp+60h+lpName], 0; lpName
0x1800021bf  mov     [rsp+60h+dwMaximumSizeLow], 0; dwMaximumSizeLow
0x1800021c7  xor     r9d, r9d; dwMaximumSizeHigh
0x1800021ca  xor     edx, edx; lpFileMappingAttributes
0x1800021cc  lea     r8d, [r9+2]; flProtect
0x1800021d0  call    cs:__imp_CreateFileMappingW
0x1800021d7  nop     dword ptr [rax+rax+00h]
0x1800021dc  mov     [rbp+hObject], rax
0x1800021e0  test    rax, rax
0x1800021e3  jnz     short loc_18000221A
0x1800021e5  call    cs:__imp_GetLastError
0x1800021ec  nop     dword ptr [rax+rax+00h]
0x1800021f1  mov     ebx, eax
0x1800021f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021fa  cmp     rcx, r15
0x1800021fd  jz      loc_180002149
0x180002203  test    byte ptr [rcx+1Ch], 1
0x180002207  jz      loc_180002149
0x18000220d  mov     [rsp+60h+var_30], 269h
0x180002215  jmp     loc_180002121
0x18000221a  mov     qword ptr [rsp+60h+dwMaximumSizeLow], 0; dwNumberOfBytesToMap
0x180002223  xor     r9d, r9d; dwFileOffsetLow
0x180002226  xor     r8d, r8d; dwFileOffsetHigh
0x180002229  lea     edx, [r9+4]; dwDesiredAccess
0x18000222d  mov     rcx, rax; hFileMappingObject
0x180002230  call    cs:__imp_MapViewOfFile
0x180002237  nop     dword ptr [rax+rax+00h]
0x18000223c  mov     [rbp+var_18], rax
0x180002240  lea     rcx, [rbp+var_18]
0x180002244  mov     [rbp+var_20], rcx
0x180002248  test    rax, rax
0x18000224b  jnz     short loc_180002282
0x18000224d  call    cs:__imp_GetLastError
0x180002254  nop     dword ptr [rax+rax+00h]
0x180002259  mov     ebx, eax
0x18000225b  mov     r9d, 273h
0x180002261  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180002268  lea     rdx, aDwlasterror; "dwLastError"
0x18000226f  mov     ecx, eax
0x180002271  call    DebugTraceError
0x180002276  nop
0x180002277  lea     rcx, [rbp+var_20]; this
0x18000227b  call    ??1ScopedUnMapView@@QEAA@XZ; ScopedUnMapView::~ScopedUnMapView(void)
0x180002280  jmp     short loc_1800022D9
0x180002282  xor     r9d, r9d; dwFlags
0x180002285  mov     r8d, [rdi+10h]; cbInput
0x180002289  mov     rdx, rax; pbInput
0x18000228c  mov     rcx, rsi; hHash
0x18000228f  call    cs:__imp_BCryptHashData
0x180002296  nop     dword ptr [rax+rax+00h]
0x18000229b  mov     ebx, eax
0x18000229d  test    eax, eax
0x18000229f  jns     short loc_1800022CE
0x1800022a1  mov     r9d, 27Ah
0x1800022a7  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800022ae  lea     rdx, aNtstatus; "ntStatus"
0x1800022b5  mov     ecx, eax
0x1800022b7  call    DebugTraceError
0x1800022bc  mov     ecx, ebx; Status
0x1800022be  call    cs:__imp_RtlNtStatusToDosError
0x1800022c5  nop     dword ptr [rax+rax+00h]
0x1800022ca  mov     ebx, eax
0x1800022cc  jmp     short loc_180002277
0x1800022ce  lea     rcx, [rbp+var_20]; this
0x1800022d2  call    ??1ScopedUnMapView@@QEAA@XZ; ScopedUnMapView::~ScopedUnMapView(void)
0x1800022d7  xor     ebx, ebx
0x1800022d9  lea     rcx, [rbp+var_10]; this
0x1800022dd  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x1800022e2  nop
0x1800022e3  lea     rcx, [rbp+var_8]; this
0x1800022e7  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x1800022ec  mov     eax, ebx
0x1800022ee  lea     r11, [rsp+60h+var_s0]
0x1800022f3  mov     rbx, [r11+20h]
0x1800022f7  mov     rsi, [r11+30h]
0x1800022fb  mov     rsp, r11
0x1800022fe  pop     r15
0x180002300  pop     rdi
0x180002301  pop     rbp
0x180002302  retn
```
