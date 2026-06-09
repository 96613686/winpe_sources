# QueueBackupMasterKeyThreadFunc(void *)

- ea: `0x18002d330`
- end: `0x18002d7d9`
- name: `?QueueBackupMasterKeyThreadFunc@@YAKPEAX@Z`
- size: `1193`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001398`
- `0x1800048a4`
- `0x180007f10`
- `0x18000b680`
- `0x18000c4a0`
- `0x18001199c`
- `0x180012da4`
- `0x18001467c`
- `0x18001d810`
- `0x180024f38`
- `0x1800261e8`
- `0x18002d330`
- `0x18002f2c8`
- `0x18002f348`
- `0x180036778`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d4ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002d4ca`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d4a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d4f7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d4a9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d45a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d45a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002d443`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002d443`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d56f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d533`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d560`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d56f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4b8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d4df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d506`

## string_xrefs

- `0x18002d429`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d477`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002d66b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall QueueBackupMasterKeyThreadFunc(char *Parameter)
{
  int v2; // esi
  int v3; // ecx
  BOOL v4; // r14d
  void *v5; // r13
  ULONG v6; // ebx
  void *v7; // rax
  void *v8; // rcx
  int v9; // r15d
  ULONG v10; // eax
  int v11; // edx
  int v12; // ecx
  ULONG LastError; // eax
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // r14d
  int v17; // eax
  HANDLE v18; // rsi
  HANDLE v19; // rsi
  _BYTE *v20; // rcx
  __int64 v21; // rax
  _BYTE *v22; // rcx
  __int64 v23; // rax
  int v25; // r15d
  __int64 v26; // r14
  ULONG v27; // r13d
  UCHAR *v28; // rax
  ULONG v29; // eax
  int v30; // edx
  __int64 v31; // rcx
  __int64 v32; // r8
  size_t Size; // [rsp+30h] [rbp-89h]
  unsigned int v34; // [rsp+54h] [rbp-65h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-61h] BYREF
  int v36; // [rsp+5Ch] [rbp-5Dh] BYREF
  HLOCAL v37; // [rsp+60h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-51h] BYREF
  ULONG v39; // [rsp+70h] [rbp-49h] BYREF
  int v40; // [rsp+74h] [rbp-45h] BYREF
  ULONG v41; // [rsp+78h] [rbp-41h] BYREF
  int v42; // [rsp+7Ch] [rbp-3Dh] BYREF
  BOOL v43; // [rsp+80h] [rbp-39h]
  __int64 v44; // [rsp+88h] [rbp-31h] BYREF
  __int64 v45; // [rsp+90h] [rbp-29h] BYREF
  HANDLE hEvent; // [rsp+98h] [rbp-21h]
  HANDLE hObject; // [rsp+A0h] [rbp-19h]
  HANDLE v48; // [rsp+A8h] [rbp-11h]
  UCHAR v49[24]; // [rsp+B0h] [rbp-9h] BYREF

  hMem = 0;
  v35 = 0;
  v37 = 0;
  v34 = 0;
  v2 = FIsLegacyCompliant((int)Parameter);
  UpdateGlobals(v3);
  v4 = dword_18004C548 == 26625;
  if ( !Parameter || *(_DWORD *)Parameter != 224 )
    return 87;
  v5 = (void *)*((_QWORD *)Parameter + 21);
  v6 = 0;
  v7 = (void *)*((_QWORD *)Parameter + 26);
  v8 = (void *)*((_QWORD *)Parameter + 27);
  v9 = dword_18004CC98;
  hObject = v5;
  v48 = v7;
  hEvent = v8;
  if ( !v2 )
  {
    v10 = AttemptLocalBackup(
            1,
            v5,
            (struct MASTERKEY_STORED *)(Parameter + 8),
            *((unsigned __int8 **)Parameter + 24),
            *((_DWORD *)Parameter + 50),
            *((unsigned __int8 **)Parameter + 22),
            *((_DWORD *)Parameter + 46),
            (unsigned __int8 **)&v37,
            &v34);
    v6 = v10;
    if ( v10 )
      DebugTraceError(v10, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6112);
  }
  v43 = SetThreadToken(0, v5);
  if ( v43 )
  {
    if ( v6 || v2 )
    {
      v25 = v4 | v9;
      if ( v25 )
      {
        if ( !(unsigned int)FMyPrimitiveSHA(*((PUCHAR *)Parameter + 22), *((_DWORD *)Parameter + 46), v49) )
        {
          v6 = 13;
          v14 = 6142;
LABEL_38:
          v15 = v6;
          goto LABEL_9;
        }
        v26 = 20;
        LODWORD(Size) = *((_DWORD *)Parameter + 50);
        v27 = v6;
        v6 = EncryptMasterKeyToMemory(
               26625,
               32777,
               v49,
               0x14u,
               0,
               *((unsigned __int8 **)Parameter + 24),
               Size,
               (unsigned __int8 **)&hMem,
               &v35);
        v28 = v49;
        do
        {
          *v28++ = 0;
          --v26;
        }
        while ( v26 );
        if ( v6 )
        {
          v14 = 6169;
          goto LABEL_38;
        }
        v29 = BackupRestoreData(
                0,
                (struct MASTERKEY_STORED *)(Parameter + 8),
                (unsigned __int8 *)hMem,
                v35,
                (unsigned __int8 **)&v37,
                &v34,
                1);
        v6 = v29;
        if ( v29 )
          DebugTraceError(v29, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 6192);
        if ( (v2 || v27 != v6)
          && (unsigned int)dword_18004C260 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x800000000000LL) )
        {
          v39 = v6;
          v40 = 0;
          v41 = v27;
          v42 = v25;
          v36 = v2;
          v44 = 0x1000000;
          v45 = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v31,
            (int)byte_180044EBB,
            v32,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v36,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39);
        }
        LOBYTE(v36) = byte_18004CC41 & 0x10;
        if ( (byte_18004CC41 & 0x10) != 0 )
          McTemplateU0ttqqq_EtwEventWriteTransfer(v31, v30, v2, v25, v27, 0, v6);
      }
      else
      {
        LOBYTE(v36) = byte_18004CC41 & 0x20;
        if ( (byte_18004CC41 & 0x20) != 0 )
          McTemplateU0ttq_EtwEventWriteTransfer(v12, v11, v2, 0, v6);
      }
      if ( v6 )
        goto LABEL_10;
    }
    LastError = PersistMasterKeyToStorage((struct MASTERKEY_STORED *)(Parameter + 8), 3, (unsigned __int8 *)v37, v34);
    v6 = LastError;
    if ( !LastError )
    {
      PersistMasterKeyToStorage((struct MASTERKEY_STORED *)(Parameter + 8), 2, 0, 0);
      v16 = 1;
      goto LABEL_11;
    }
    v14 = 6238;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v6 = LastError;
  v14 = 6124;
LABEL_8:
  v15 = LastError;
LABEL_9:
  DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v14);
LABEL_10:
  v16 = 0;
LABEL_11:
  v17 = CloseMasterKey(0, (struct MASTERKEY_STORED *)(Parameter + 8), v16);
  v18 = hEvent;
  if ( hEvent )
  {
    if ( v16 && v17 )
      SetEvent(hEvent);
    CloseHandle(v18);
  }
  if ( v43 )
    RevertToSelf();
  if ( hObject )
    CloseHandle(hObject);
  v19 = v48;
  if ( v48 )
  {
    SetEvent(v48);
    CloseHandle(v19);
  }
  v20 = hMem;
  if ( hMem )
  {
    v21 = v35;
    if ( v35 )
    {
      do
      {
        *v20++ = 0;
        --v21;
      }
      while ( v21 );
      v20 = hMem;
    }
    LocalFree(v20);
  }
  v22 = v37;
  if ( v37 )
  {
    v23 = v34;
    if ( v34 )
    {
      do
      {
        *v22++ = 0;
        --v23;
      }
      while ( v23 );
      v22 = v37;
    }
    LocalFree(v22);
  }
  LocalFree(Parameter);
  return v6;
}

```

## disassembly

```asm
0x18002d330  push    rbp
0x18002d332  push    rbx
0x18002d333  push    rsi
0x18002d334  push    rdi
0x18002d335  push    r12
0x18002d337  push    r13
0x18002d339  push    r14
0x18002d33b  push    r15
0x18002d33d  lea     rbp, [rsp-1Fh]
0x18002d342  sub     rsp, 0D8h
0x18002d349  mov     rax, cs:__security_cookie
0x18002d350  xor     rax, rsp
0x18002d353  mov     [rbp+57h+var_48], rax
0x18002d357  xor     r15d, r15d
0x18002d35a  mov     rdi, rcx
0x18002d35d  mov     [rbp+57h+hMem], r15
0x18002d361  mov     [rbp+57h+var_B8], r15d
0x18002d365  mov     [rbp+57h+var_B0], r15
0x18002d369  mov     [rbp+57h+var_BC], r15d
0x18002d36d  call    ?FIsLegacyCompliant@@YAHXZ; FIsLegacyCompliant(void)
0x18002d372  mov     esi, eax
0x18002d374  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x18002d379  cmp     cs:dword_18004C548, 6801h
0x18002d383  mov     r14d, r15d
0x18002d386  setz    r14b
0x18002d38a  test    rdi, rdi
0x18002d38d  jz      loc_18002D7B3
0x18002d393  cmp     dword ptr [rdi], 0E0h
0x18002d399  jnz     loc_18002D7B3
0x18002d39f  mov     r13, [rdi+0A8h]
0x18002d3a6  mov     ebx, r15d
0x18002d3a9  mov     rax, [rdi+0D0h]
0x18002d3b0  lea     r12, [rdi+8]
0x18002d3b4  mov     rcx, [rdi+0D8h]
0x18002d3bb  mov     [rbp+57h+var_C0], r15d
0x18002d3bf  mov     r15d, cs:dword_18004CC98
0x18002d3c6  mov     [rbp+57h+hObject], r13
0x18002d3ca  mov     [rbp+57h+var_68], rax
0x18002d3ce  mov     [rbp+57h+hEvent], rcx
0x18002d3d2  test    esi, esi
0x18002d3d4  jnz     short loc_18002D43E
0x18002d3d6  mov     r9, [rdi+0C0h]; unsigned __int8 *
0x18002d3dd  lea     rax, [rbp+57h+var_BC]
0x18002d3e1  mov     [rsp+110h+var_D0], rax; unsigned int *
0x18002d3e6  lea     ecx, [rsi+1]; int
0x18002d3e9  lea     rax, [rbp+57h+var_B0]
0x18002d3ed  mov     r8, r12; struct MASTERKEY_STORED *
0x18002d3f0  mov     [rsp+110h+var_D8], rax; unsigned __int8 **
0x18002d3f5  mov     rdx, r13; void *
0x18002d3f8  mov     eax, [rdi+0B8h]
0x18002d3fe  mov     dword ptr [rsp+110h+Size], eax; unsigned int
0x18002d402  mov     rax, [rdi+0B0h]
0x18002d409  mov     [rsp+110h+var_E8], rax; unsigned __int8 *
0x18002d40e  mov     eax, [rdi+0C8h]
0x18002d414  mov     dword ptr [rsp+110h+var_F0], eax; unsigned int
0x18002d418  call    ?AttemptLocalBackup@@YAKHPEAXPEAUMASTERKEY_STORED@@PEAEK2KPEAPEAEPEAK@Z; AttemptLocalBackup(int,void *,MASTERKEY_STORED *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18002d41d  mov     ebx, eax
0x18002d41f  test    eax, eax
0x18002d421  jz      short loc_18002D43E
0x18002d423  mov     r9d, 17E0h
0x18002d429  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d430  lea     rdx, aDwlasterror; "dwLastError"
0x18002d437  mov     ecx, eax
0x18002d439  call    DebugTraceError
0x18002d43e  mov     rdx, r13; Token
0x18002d441  xor     ecx, ecx; Thread
0x18002d443  call    cs:__imp_SetThreadToken
0x18002d44a  nop     dword ptr [rax+rax+00h]
0x18002d44f  mov     [rbp+57h+var_90], eax
0x18002d452  test    eax, eax
0x18002d454  jnz     loc_18002D582
0x18002d45a  call    cs:__imp_GetLastError
0x18002d461  nop     dword ptr [rax+rax+00h]
0x18002d466  mov     ebx, eax
0x18002d468  mov     r9d, 17ECh
0x18002d46e  mov     ecx, eax
0x18002d470  lea     rdx, aDwlasterror; "dwLastError"
0x18002d477  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d47e  call    DebugTraceError
0x18002d483  mov     r14d, [rbp+57h+var_C0]
0x18002d487  mov     r8d, r14d; int
0x18002d48a  mov     rdx, r12; struct MASTERKEY_STORED *
0x18002d48d  xor     ecx, ecx; void *
0x18002d48f  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002d494  mov     rsi, [rbp+57h+hEvent]
0x18002d498  test    rsi, rsi
0x18002d49b  jz      short loc_18002D4C4
0x18002d49d  test    r14d, r14d
0x18002d4a0  jz      short loc_18002D4B5
0x18002d4a2  test    eax, eax
0x18002d4a4  jz      short loc_18002D4B5
0x18002d4a6  mov     rcx, rsi; hEvent
0x18002d4a9  call    cs:__imp_SetEvent
0x18002d4b0  nop     dword ptr [rax+rax+00h]
0x18002d4b5  mov     rcx, rsi; hObject
0x18002d4b8  call    cs:__imp_CloseHandle
0x18002d4bf  nop     dword ptr [rax+rax+00h]
0x18002d4c4  cmp     [rbp+57h+var_90], 0
0x18002d4c8  jz      short loc_18002D4D6
0x18002d4ca  call    cs:__imp_RevertToSelf
0x18002d4d1  nop     dword ptr [rax+rax+00h]
0x18002d4d6  mov     rcx, [rbp+57h+hObject]; hObject
0x18002d4da  test    rcx, rcx
0x18002d4dd  jz      short loc_18002D4EB
0x18002d4df  call    cs:__imp_CloseHandle
0x18002d4e6  nop     dword ptr [rax+rax+00h]
0x18002d4eb  mov     rsi, [rbp+57h+var_68]
0x18002d4ef  test    rsi, rsi
0x18002d4f2  jz      short loc_18002D512
0x18002d4f4  mov     rcx, rsi; hEvent
0x18002d4f7  call    cs:__imp_SetEvent
0x18002d4fe  nop     dword ptr [rax+rax+00h]
0x18002d503  mov     rcx, rsi; hObject
0x18002d506  call    cs:__imp_CloseHandle
0x18002d50d  nop     dword ptr [rax+rax+00h]
0x18002d512  mov     rcx, [rbp+57h+hMem]
0x18002d516  test    rcx, rcx
0x18002d519  jz      short loc_18002D53F
0x18002d51b  mov     eax, [rbp+57h+var_B8]
0x18002d51e  test    rax, rax
0x18002d521  jz      short loc_18002D533
0x18002d523  mov     byte ptr [rcx], 0
0x18002d526  inc     rcx
0x18002d529  sub     rax, 1
0x18002d52d  jnz     short loc_18002D523
0x18002d52f  mov     rcx, [rbp+57h+hMem]; hMem
0x18002d533  call    cs:__imp_LocalFree
0x18002d53a  nop     dword ptr [rax+rax+00h]
0x18002d53f  mov     rcx, [rbp+57h+var_B0]
0x18002d543  test    rcx, rcx
0x18002d546  jz      short loc_18002D56C
0x18002d548  mov     eax, [rbp+57h+var_BC]
0x18002d54b  test    rax, rax
0x18002d54e  jz      short loc_18002D560
0x18002d550  mov     byte ptr [rcx], 0
0x18002d553  inc     rcx
0x18002d556  sub     rax, 1
0x18002d55a  jnz     short loc_18002D550
0x18002d55c  mov     rcx, [rbp+57h+var_B0]; hMem
0x18002d560  call    cs:__imp_LocalFree
0x18002d567  nop     dword ptr [rax+rax+00h]
0x18002d56c  mov     rcx, rdi; hMem
0x18002d56f  call    cs:__imp_LocalFree
0x18002d576  nop     dword ptr [rax+rax+00h]
0x18002d57b  mov     eax, ebx
0x18002d57d  jmp     loc_18002D7B8
0x18002d582  test    ebx, ebx
0x18002d584  jnz     short loc_18002D58E
0x18002d586  test    esi, esi
0x18002d588  jz      loc_18002D770
0x18002d58e  or      r15d, r14d
0x18002d591  jz      loc_18002D74C
0x18002d597  mov     edx, [rdi+0B8h]; cbInput
0x18002d59d  lea     rax, [rbp+57h+var_60]
0x18002d5a1  mov     rcx, [rdi+0B0h]; pbInput
0x18002d5a8  mov     [rsp+110h+var_F0], rax; PUCHAR
0x18002d5ad  call    FMyPrimitiveSHA
0x18002d5b2  test    eax, eax
0x18002d5b4  jnz     short loc_18002D5C6
0x18002d5b6  lea     ebx, [rax+0Dh]
0x18002d5b9  mov     r9d, 17FEh
0x18002d5bf  mov     ecx, ebx
0x18002d5c1  jmp     loc_18002D470
0x18002d5c6  lea     rax, [rbp+57h+var_B8]
0x18002d5ca  mov     r14d, 14h
0x18002d5d0  mov     [rsp+110h+var_D0], rax; unsigned int *
0x18002d5d5  lea     r8, [rbp+57h+var_60]; unsigned __int8 *
0x18002d5d9  lea     rax, [rbp+57h+hMem]
0x18002d5dd  mov     r9d, r14d; unsigned int
0x18002d5e0  mov     [rsp+110h+var_D8], rax; unsigned __int8 **
0x18002d5e5  mov     edx, 8009h; unsigned int
0x18002d5ea  mov     eax, [rdi+0C8h]
0x18002d5f0  mov     ecx, 6801h; unsigned int
0x18002d5f5  mov     dword ptr [rsp+110h+Size], eax; Size
0x18002d5f9  mov     r13d, ebx
0x18002d5fc  mov     rax, [rdi+0C0h]
0x18002d603  mov     [rsp+110h+var_E8], rax; unsigned __int8 *
0x18002d608  mov     dword ptr [rsp+110h+var_F0], 0; unsigned int
0x18002d610  call    ?EncryptMasterKeyToMemory@@YAKIIPEAEKK0KPEAPEAEPEAK@Z; EncryptMasterKeyToMemory(uint,uint,uchar *,ulong,ulong,uchar *,ulong,uchar * *,ulong *)
0x18002d615  mov     ebx, eax
0x18002d617  lea     rax, [rbp+57h+var_60]
0x18002d61b  mov     byte ptr [rax], 0
0x18002d61e  inc     rax
0x18002d621  sub     r14, 1
0x18002d625  jnz     short loc_18002D61B
0x18002d627  test    ebx, ebx
0x18002d629  jz      short loc_18002D633
0x18002d62b  mov     r9d, 1819h
0x18002d631  jmp     short loc_18002D5BF
0x18002d633  mov     r9d, [rbp+57h+var_B8]; unsigned int
0x18002d637  lea     rax, [rbp+57h+var_BC]
0x18002d63b  mov     r8, [rbp+57h+hMem]; unsigned __int8 *
0x18002d63f  mov     rdx, r12; struct MASTERKEY_STORED *
0x18002d642  mov     dword ptr [rsp+110h+Size], 1; int
0x18002d64a  xor     ecx, ecx; void *
0x18002d64c  mov     [rsp+110h+var_E8], rax; unsigned int *
0x18002d651  lea     rax, [rbp+57h+var_B0]
0x18002d655  mov     [rsp+110h+var_F0], rax; unsigned __int8 **
0x18002d65a  call    ?BackupRestoreData@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKPEAPEAEPEAKH@Z; BackupRestoreData(void *,MASTERKEY_STORED *,uchar *,ulong,uchar * *,ulong *,int)
0x18002d65f  mov     ebx, eax
0x18002d661  test    eax, eax
0x18002d663  jz      short loc_18002D680
0x18002d665  mov     r9d, 1830h
0x18002d66b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002d672  lea     rdx, aDwlasterror; "dwLastError"
0x18002d679  mov     ecx, eax
0x18002d67b  call    DebugTraceError
0x18002d680  test    esi, esi
0x18002d682  jnz     short loc_18002D68D
0x18002d684  cmp     r13d, ebx
0x18002d687  jz      loc_18002D721
0x18002d68d  mov     eax, cs:dword_18004C260
0x18002d693  cmp     eax, 5
0x18002d696  jbe     loc_18002D721
0x18002d69c  mov     rdx, 800000000000h
0x18002d6a6  lea     rcx, dword_18004C260
0x18002d6ad  call    _tlgKeywordOn
0x18002d6b2  test    al, al
0x18002d6b4  jz      short loc_18002D721
0x18002d6b6  lea     rax, [rbp+57h+var_A0]
0x18002d6ba  mov     [rbp+57h+var_A0], ebx
0x18002d6bd  mov     [rsp+110h+var_C8], rax
0x18002d6c2  lea     r9, [rbp+57h+var_80]
0x18002d6c6  lea     rax, [rbp+57h+var_9C]
0x18002d6ca  mov     [rbp+57h+var_9C], 0
0x18002d6d1  mov     [rsp+110h+var_D0], rax
0x18002d6d6  lea     rdx, byte_180044EBB
0x18002d6dd  lea     rax, [rbp+57h+var_98]
0x18002d6e1  mov     [rbp+57h+var_98], r13d
0x18002d6e5  mov     [rsp+110h+var_D8], rax
0x18002d6ea  lea     rax, [rbp+57h+var_94]
0x18002d6ee  mov     [rsp+110h+Size], rax
0x18002d6f3  lea     rax, [rbp+57h+var_B4]
0x18002d6f7  mov     [rsp+110h+var_E8], rax
0x18002d6fc  lea     rax, [rbp+57h+var_88]
0x18002d700  mov     [rsp+110h+var_F0], rax
0x18002d705  mov     [rbp+57h+var_94], r15d
0x18002d709  mov     [rbp+57h+var_B4], esi
0x18002d70c  mov     [rbp+57h+var_88], 1000000h
0x18002d714  mov     [rbp+57h+var_80], 1
0x18002d71c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapperByVal@$03@@3333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002d721  mov     al, cs:byte_18004CC41
0x18002d727  and     al, 10h
0x18002d729  mov     byte ptr [rbp+57h+var_B4], al
0x18002d72c  jz      short loc_18002D768
0x18002d72e  mov     dword ptr [rsp+110h+Size], ebx
0x18002d732  mov     r9d, r15d
0x18002d735  mov     dword ptr [rsp+110h+var_E8], 0
0x18002d73d  mov     r8d, esi
0x18002d740  mov     dword ptr [rsp+110h+var_F0], r13d
0x18002d745  call    McTemplateU0ttqqq_EtwEventWriteTransfer
0x18002d74a  jmp     short loc_18002D768
0x18002d74c  mov     al, cs:byte_18004CC41
0x18002d752  and     al, 20h
0x18002d754  mov     byte ptr [rbp+57h+var_B4], al
0x18002d757  jz      short loc_18002D768
0x18002d759  mov     r9d, r15d
0x18002d75c  mov     dword ptr [rsp+110h+var_F0], ebx
0x18002d760  mov     r8d, esi
0x18002d763  call    McTemplateU0ttq_EtwEventWriteTransfer
0x18002d768  test    ebx, ebx
0x18002d76a  jnz     loc_18002D483
0x18002d770  mov     r9d, [rbp+57h+var_BC]; unsigned int
0x18002d774  mov     edx, 3; unsigned int
0x18002d779  mov     r8, [rbp+57h+var_B0]; unsigned __int8 *
0x18002d77d  mov     rcx, r12; struct MASTERKEY_STORED *
0x18002d780  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002d785  mov     ebx, eax
0x18002d787  test    eax, eax
0x18002d789  jz      short loc_18002D796
0x18002d78b  mov     r9d, 185Eh
0x18002d791  jmp     loc_18002D46E
0x18002d796  xor     r9d, r9d; unsigned int
0x18002d799  xor     r8d, r8d; unsigned __int8 *
0x18002d79c  mov     rcx, r12; struct MASTERKEY_STORED *
0x18002d79f  lea     edx, [r9+2]; unsigned int
0x18002d7a3  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002d7a8  mov     r14d, 1
0x18002d7ae  jmp     loc_18002D487
0x18002d7b3  mov     eax, 57h ; 'W'
0x18002d7b8  mov     rcx, [rbp+57h+var_48]
0x18002d7bc  xor     rcx, rsp; StackCookie
0x18002d7bf  call    __security_check_cookie
0x18002d7c4  add     rsp, 0D8h
0x18002d7cb  pop     r15
0x18002d7cd  pop     r14
0x18002d7cf  pop     r13
0x18002d7d1  pop     r12
0x18002d7d3  pop     rdi
0x18002d7d4  pop     rsi
0x18002d7d5  pop     rbx
0x18002d7d6  pop     rbp
0x18002d7d7  retn
```
