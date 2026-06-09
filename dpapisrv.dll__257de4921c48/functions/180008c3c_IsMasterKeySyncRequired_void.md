# IsMasterKeySyncRequired(void *)

- ea: `0x180008c3c`
- end: `0x1800090e0`
- name: `?IsMasterKeySyncRequired@@YAHPEAX@Z`
- size: `1188`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008af0`

## callees

- `0x180001e60`
- `0x180004d80`
- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180007f10`
- `0x180008498`
- `0x180008c3c`
- `0x18000dd40`
- `0x1800114b4`
- `0x180013bec`
- `0x180013f2c`
- `0x18001c0a4`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x180039be0`
- `0x180039fdc`
- `0x18003c620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009093`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008db4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009093`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008cb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008cb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008f71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ca0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ca0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008d78`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008e20`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008d78`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008e20`

## string_xrefs

- `0x180008ce5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x180008dc8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x1800090a5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall IsMasterKeySyncRequired(_QWORD *a1)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v5; // rax
  DWORD v6; // eax
  unsigned int v7; // edi
  DWORD v8; // eax
  __int64 v9; // r9
  unsigned int MasterKeySyncHash; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  void **p_hObject; // [rsp+38h] [rbp-C8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-B0h] BYREF
  struct _MK_LOCATION *v20; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID v21[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD Buffer[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Buf2[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 Buf1[64]; // [rsp+D0h] [rbp-30h] BYREF

  hObject = (HANDLE)-1LL;
  p_hObject = &hObject;
  Buffer[0] = 0;
  LODWORD(Buffer[1]) = 0;
  v21[0] = 0;
  NumberOfBytesRead = 0;
  hMem = 0;
  if ( (unsigned int)CPSImpersonateClient(a1) )
  {
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 1;
  }
  CurrentThread = GetCurrentThread();
  if ( !(unsigned int)GetThreadAuthenticationId(CurrentThread, v21) )
  {
    LastError = GetLastError();
    DebugTraceError(LastError, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", 361);
    CPSRevertToSelf(a1);
LABEL_7:
    ScopedCloseHandle::~ScopedCloseHandle(&p_hObject);
    return 1;
  }
  CPSRevertToSelf(a1);
  v5 = (void *)OpenSyncHistoryFile(a1, 0x80000000);
  hObject = v5;
  if ( v5 == (void *)-1LL )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
    goto LABEL_7;
  }
  if ( !ReadFile(v5, Buffer, 0xCu, &NumberOfBytesRead, 0) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
    v6 = GetLastError();
    DebugTraceError(v6, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", 390);
    goto LABEL_7;
  }
  v7 = 1;
  if ( LODWORD(Buffer[0]) != 1 || *(_QWORD *)((char *)Buffer + 4) != 0x400000800ELL )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
    v8 = GetLastError();
    v9 = 399;
    goto LABEL_56;
  }
  if ( !ReadFile(hObject, Buf2, 0x40u, &NumberOfBytesRead, 0) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids);
    v8 = GetLastError();
    v9 = 410;
LABEL_56:
    DebugTraceError(v8, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", v9);
    goto LABEL_57;
  }
  v20 = 0;
  v15 = 0;
  v22[0] = &v20;
  v22[1] = &v15;
  MasterKeySyncHash = EnumerateMasterKeys(a1, &v20, &v15);
  if ( MasterKeySyncHash )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_51;
    v12 = 19;
    goto LABEL_45;
  }
  MasterKeySyncHash = CPSGetUserStorageArea(a1, 0, 0, 0, (unsigned __int16 **)&hMem);
  if ( MasterKeySyncHash )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_51;
    v12 = 20;
    goto LABEL_45;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids, hMem);
  RemoveMasterKeyCache(v21, (const unsigned __int16 *)hMem);
  if ( hMem )
    LocalFree(hMem);
  MasterKeySyncHash = SynchronizeOneMasterKey(a1, v20, v15);
  if ( MasterKeySyncHash )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_51;
    v12 = 22;
    goto LABEL_45;
  }
  MasterKeySyncHash = GetMasterKeySyncHash(a1, v20, v15, HIDWORD(Buffer[0]), Buf1);
  if ( !MasterKeySyncHash )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
    {
      v21[1] = (struct _LUID)64LL;
      v21[0] = (struct _LUID)Buf2;
      WPP_SF__HEX_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v13, v14, v21);
    }
    if ( !memcmp_0(Buf1, Buf2, 0x40u) )
      v7 = 0;
    goto LABEL_51;
  }
  v11 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    v12 = 23;
LABEL_45:
    WPP_SF_d(*(_QWORD *)(v11 + 16), v12, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids, MasterKeySyncHash);
  }
LABEL_51:
  ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array((ScopedSSFreeMK_LOCATION_Array *)v22);
LABEL_57:
  ScopedCloseHandle::~ScopedCloseHandle(&p_hObject);
  return v7;
}

```

## disassembly

```asm
0x180008c3c  push    rbp
0x180008c3e  push    rbx
0x180008c3f  push    rsi
0x180008c40  push    rdi
0x180008c41  lea     rbp, [rsp-28h]
0x180008c46  sub     rsp, 128h
0x180008c4d  mov     rax, cs:__security_cookie
0x180008c54  xor     rax, rsp
0x180008c57  mov     [rbp+40h+var_30], rax
0x180008c5b  mov     rsi, rcx
0x180008c5e  mov     [rsp+140h+hObject], 0FFFFFFFFFFFFFFFFh
0x180008c67  lea     rax, [rsp+140h+hObject]
0x180008c6c  mov     [rsp+140h+var_108], rax
0x180008c71  xor     eax, eax
0x180008c73  mov     qword ptr [rbp+40h+Buffer], rax
0x180008c77  mov     dword ptr [rbp+40h+Buffer+8], eax
0x180008c7a  mov     qword ptr [rsp+140h+var_E0.LowPart], rax
0x180008c7f  mov     [rsp+140h+NumberOfBytesRead], eax
0x180008c83  mov     [rsp+140h+hMem], rax
0x180008c88  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180008c8d  test    eax, eax
0x180008c8f  jz      short loc_180008CB6
0x180008c91  mov     rcx, [rsp+140h+hObject]; hObject
0x180008c96  lea     rax, [rcx-1]
0x180008c9a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008c9e  ja      short loc_180008CAC
0x180008ca0  call    cs:__imp_CloseHandle
0x180008ca7  nop     dword ptr [rax+rax+00h]
0x180008cac  mov     eax, 1
0x180008cb1  jmp     loc_1800090C7
0x180008cb6  call    cs:__imp_GetCurrentThread
0x180008cbd  nop     dword ptr [rax+rax+00h]
0x180008cc2  mov     rcx, rax
0x180008cc5  lea     rdx, [rsp+140h+var_E0]
0x180008cca  call    GetThreadAuthenticationId
0x180008ccf  test    eax, eax
0x180008cd1  jnz     short loc_180008D0F
0x180008cd3  call    cs:__imp_GetLastError
0x180008cda  nop     dword ptr [rax+rax+00h]
0x180008cdf  mov     r9d, 169h
0x180008ce5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180008cec  lea     rdx, aDwlasterror; "dwLastError"
0x180008cf3  mov     ecx, eax
0x180008cf5  call    DebugTraceError
0x180008cfa  mov     rcx, rsi; void *
0x180008cfd  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180008d02  nop
0x180008d03  lea     rcx, [rsp+140h+var_108]; this
0x180008d08  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x180008d0d  jmp     short loc_180008CAC
0x180008d0f  mov     rcx, rsi; void *
0x180008d12  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x180008d17  mov     edx, 80000000h; unsigned int
0x180008d1c  mov     rcx, rsi; void *
0x180008d1f  call    ?OpenSyncHistoryFile@@YAPEAXPEAXK@Z; OpenSyncHistoryFile(void *,ulong)
0x180008d24  mov     [rsp+140h+hObject], rax
0x180008d29  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008d2d  jnz     short loc_180008D5D
0x180008d2f  lea     rbx, WPP_GLOBAL_Control
0x180008d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d3d  cmp     rcx, rbx
0x180008d40  jz      short loc_180008D03
0x180008d42  test    byte ptr [rcx+1Ch], 2
0x180008d46  jz      short loc_180008D03
0x180008d48  lea     edx, [rax+10h]
0x180008d4b  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180008d52  mov     rcx, [rcx+10h]
0x180008d56  call    WPP_SF_
0x180008d5b  jmp     short loc_180008D03
0x180008d5d  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180008d66  lea     r9, [rsp+140h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008d6b  mov     r8d, 0Ch; nNumberOfBytesToRead
0x180008d71  lea     rdx, [rbp+40h+Buffer]; lpBuffer
0x180008d75  mov     rcx, rax; hFile
0x180008d78  call    cs:__imp_ReadFile
0x180008d7f  nop     dword ptr [rax+rax+00h]
0x180008d84  test    eax, eax
0x180008d86  jnz     short loc_180008DE0
0x180008d88  lea     rbx, WPP_GLOBAL_Control
0x180008d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d96  cmp     rcx, rbx
0x180008d99  jz      short loc_180008DB4
0x180008d9b  test    byte ptr [rcx+1Ch], 2
0x180008d9f  jz      short loc_180008DB4
0x180008da1  lea     edx, [rax+10h]
0x180008da4  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180008dab  mov     rcx, [rcx+10h]
0x180008daf  call    WPP_SF_
0x180008db4  call    cs:__imp_GetLastError
0x180008dbb  nop     dword ptr [rax+rax+00h]
0x180008dc0  mov     ecx, eax
0x180008dc2  mov     r9d, 186h
0x180008dc8  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180008dcf  lea     rdx, aGetlasterror; "GetLastError()"
0x180008dd6  call    DebugTraceError
0x180008ddb  jmp     loc_180008D03
0x180008de0  mov     edi, 1
0x180008de5  cmp     dword ptr [rbp+40h+Buffer], edi
0x180008de8  jnz     loc_180009065
0x180008dee  cmp     dword ptr [rbp+40h+Buffer+4], 800Eh
0x180008df5  jnz     loc_180009065
0x180008dfb  cmp     dword ptr [rbp+40h+Buffer+8], 40h ; '@'
0x180008dff  jnz     loc_180009065
0x180008e05  mov     [rsp+140h+lpOverlapped], 0; lpOverlapped
0x180008e0e  lea     r9, [rsp+140h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008e13  lea     r8d, [rdi+3Fh]; nNumberOfBytesToRead
0x180008e17  lea     rdx, [rbp+40h+Buf2]; lpBuffer
0x180008e1b  mov     rcx, [rsp+140h+hObject]; hFile
0x180008e20  call    cs:__imp_ReadFile
0x180008e27  nop     dword ptr [rax+rax+00h]
0x180008e2c  test    eax, eax
0x180008e2e  jnz     short loc_180008E73
0x180008e30  lea     rbx, WPP_GLOBAL_Control
0x180008e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e3e  cmp     rcx, rbx
0x180008e41  jz      short loc_180008E5C
0x180008e43  test    byte ptr [rcx+1Ch], 2
0x180008e47  jz      short loc_180008E5C
0x180008e49  lea     edx, [rdi+11h]
0x180008e4c  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180008e53  mov     rcx, [rcx+10h]
0x180008e57  call    WPP_SF_
0x180008e5c  call    cs:__imp_GetLastError
0x180008e63  nop     dword ptr [rax+rax+00h]
0x180008e68  mov     r9d, 19Ah
0x180008e6e  jmp     loc_1800090A5
0x180008e73  mov     [rsp+140h+var_E8], 0
0x180008e7c  mov     [rsp+140h+var_110], 0
0x180008e84  lea     rax, [rsp+140h+var_E8]
0x180008e89  mov     [rsp+140h+var_D0], rax
0x180008e8e  lea     rax, [rsp+140h+var_110]
0x180008e93  mov     [rsp+140h+var_C8], rax
0x180008e98  lea     r8, [rsp+140h+var_110]; unsigned int *
0x180008e9d  lea     rdx, [rsp+140h+var_E8]; struct _MK_LOCATION **
0x180008ea2  mov     rcx, rsi; void *
0x180008ea5  call    ?EnumerateMasterKeys@@YAKPEAXPEAPEAU_MK_LOCATION@@PEAK@Z; EnumerateMasterKeys(void *,_MK_LOCATION * *,ulong *)
0x180008eaa  test    eax, eax
0x180008eac  jz      short loc_180008ED9
0x180008eae  lea     rbx, WPP_GLOBAL_Control
0x180008eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ebc  cmp     rcx, rbx
0x180008ebf  jz      loc_180009059
0x180008ec5  test    byte ptr [rcx+1Ch], 2
0x180008ec9  jz      loc_180009059
0x180008ecf  mov     edx, 13h
0x180008ed4  jmp     loc_180008FEE
0x180008ed9  lea     rax, [rsp+140h+hMem]
0x180008ede  mov     [rsp+140h+lpOverlapped], rax; unsigned __int16 **
0x180008ee3  xor     r9d, r9d; int
0x180008ee6  xor     r8d, r8d; int
0x180008ee9  xor     edx, edx; void *
0x180008eeb  mov     rcx, rsi; void *
0x180008eee  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x180008ef3  test    eax, eax
0x180008ef5  jz      short loc_180008F22
0x180008ef7  lea     rbx, WPP_GLOBAL_Control
0x180008efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f05  cmp     rcx, rbx
0x180008f08  jz      loc_180009059
0x180008f0e  test    byte ptr [rcx+1Ch], 2
0x180008f12  jz      loc_180009059
0x180008f18  mov     edx, 14h
0x180008f1d  jmp     loc_180008FEE
0x180008f22  lea     rbx, WPP_GLOBAL_Control
0x180008f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f30  cmp     rcx, rbx
0x180008f33  jz      short loc_180008F55
0x180008f35  test    byte ptr [rcx+1Ch], 8
0x180008f39  jz      short loc_180008F55
0x180008f3b  mov     edx, 15h
0x180008f40  mov     r9, [rsp+140h+hMem]
0x180008f45  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180008f4c  mov     rcx, [rcx+10h]
0x180008f50  call    WPP_SF_S
0x180008f55  mov     rdx, [rsp+140h+hMem]; unsigned __int16 *
0x180008f5a  lea     rcx, [rsp+140h+var_E0]; struct _LUID *
0x180008f5f  call    ?RemoveMasterKeyCache@@YAHPEAU_LUID@@PEBG@Z; RemoveMasterKeyCache(_LUID *,ushort const *)
0x180008f64  cmp     [rsp+140h+hMem], 0
0x180008f6a  jz      short loc_180008F7D
0x180008f6c  mov     rcx, [rsp+140h+hMem]; hMem
0x180008f71  call    cs:__imp_LocalFree
0x180008f78  nop     dword ptr [rax+rax+00h]
0x180008f7d  mov     r8d, [rsp+140h+var_110]; unsigned int
0x180008f82  mov     rdx, [rsp+140h+var_E8]; struct _MK_LOCATION *
0x180008f87  mov     rcx, rsi; void *
0x180008f8a  call    ?SynchronizeOneMasterKey@@YAKPEAXPEAU_MK_LOCATION@@K@Z; SynchronizeOneMasterKey(void *,_MK_LOCATION *,ulong)
0x180008f8f  test    eax, eax
0x180008f91  jz      short loc_180008FB4
0x180008f93  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f9a  cmp     rcx, rbx
0x180008f9d  jz      loc_180009059
0x180008fa3  test    byte ptr [rcx+1Ch], 2
0x180008fa7  jz      loc_180009059
0x180008fad  mov     edx, 16h
0x180008fb2  jmp     short loc_180008FEE
0x180008fb4  lea     rax, [rbp+40h+Buf1]
0x180008fb8  mov     [rsp+140h+lpOverlapped], rax; unsigned __int8 *
0x180008fbd  mov     r9d, dword ptr [rbp+40h+Buffer+4]; unsigned int
0x180008fc1  mov     r8d, [rsp+140h+var_110]; unsigned int
0x180008fc6  mov     rdx, [rsp+140h+var_E8]; struct _MK_LOCATION *
0x180008fcb  mov     rcx, rsi; void *
0x180008fce  call    ?GetMasterKeySyncHash@@YAKPEAXPEAU_MK_LOCATION@@KKPEAEK@Z; GetMasterKeySyncHash(void *,_MK_LOCATION *,ulong,ulong,uchar *,ulong)
0x180008fd3  test    eax, eax
0x180008fd5  jz      short loc_180009003
0x180008fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fde  cmp     rcx, rbx
0x180008fe1  jz      short loc_180009059
0x180008fe3  test    byte ptr [rcx+1Ch], 2
0x180008fe7  jz      short loc_180009059
0x180008fe9  mov     edx, 17h
0x180008fee  mov     r9d, eax
0x180008ff1  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x180008ff8  mov     rcx, [rcx+10h]
0x180008ffc  call    WPP_SF_d
0x180009001  jmp     short loc_180009059
0x180009003  mov     rcx, cs:WPP_GLOBAL_Control
0x18000900a  cmp     rcx, rbx
0x18000900d  jz      short loc_180009040
0x18000900f  test    byte ptr [rcx+1Ch], 10h
0x180009013  jz      short loc_180009040
0x180009015  mov     qword ptr [rsp+140h+var_E0.LowPart+8], 40h ; '@'
0x18000901e  lea     rax, [rbp+40h+Buf2]
0x180009022  mov     qword ptr [rsp+140h+var_E0.LowPart], rax
0x180009027  movaps  xmm0, xmmword ptr [rsp+140h+var_E0.LowPart]
0x18000902c  movdqa  xmmword ptr [rsp+140h+var_E0.LowPart], xmm0
0x180009032  lea     r9, [rsp+140h+var_E0]
0x180009037  mov     rcx, [rcx+10h]
0x18000903b  call    WPP_SF__HEX_
0x180009040  mov     r8d, 40h ; '@'; Size
0x180009046  lea     rdx, [rbp+40h+Buf2]; Buf2
0x18000904a  lea     rcx, [rbp+40h+Buf1]; Buf1
0x18000904e  call    memcmp_0
0x180009053  test    eax, eax
0x180009055  jnz     short loc_180009059
0x180009057  xor     edi, edi
0x180009059  lea     rcx, [rsp+140h+var_D0]; this
0x18000905e  call    ??1ScopedSSFreeMK_LOCATION_Array@@QEAA@XZ; ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array(void)
0x180009063  jmp     short loc_1800090BB
0x180009065  lea     rbx, WPP_GLOBAL_Control
0x18000906c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009073  cmp     rcx, rbx
0x180009076  jz      short loc_180009093
0x180009078  test    byte ptr [rcx+1Ch], 2
0x18000907c  jz      short loc_180009093
0x18000907e  mov     edx, 11h
0x180009083  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x18000908a  mov     rcx, [rcx+10h]
0x18000908e  call    WPP_SF_
0x180009093  call    cs:__imp_GetLastError
0x18000909a  nop     dword ptr [rax+rax+00h]
0x18000909f  mov     r9d, 18Fh
0x1800090a5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800090ac  lea     rdx, aGetlasterror; "GetLastError()"
0x1800090b3  mov     ecx, eax
0x1800090b5  call    DebugTraceError
0x1800090ba  nop
0x1800090bb  lea     rcx, [rsp+140h+var_108]; this
0x1800090c0  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x1800090c5  mov     eax, edi
0x1800090c7  mov     rcx, [rbp+40h+var_30]
0x1800090cb  xor     rcx, rsp; StackCookie
0x1800090ce  call    __security_check_cookie
0x1800090d3  add     rsp, 128h
0x1800090da  pop     rdi
0x1800090db  pop     rsi
0x1800090dc  pop     rbx
0x1800090dd  pop     rbp
0x1800090de  retn
```
