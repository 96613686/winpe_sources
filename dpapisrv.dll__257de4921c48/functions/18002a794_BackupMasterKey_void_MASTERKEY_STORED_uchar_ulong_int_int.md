# BackupMasterKey(void *,MASTERKEY_STORED *,uchar *,ulong,int,int)

- ea: `0x18002a794`
- end: `0x18002abfc`
- name: `?BackupMasterKey@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKHH@Z`
- size: `1128`
- prototype: `__int64 __fastcall(void *, struct MASTERKEY_STORED *, unsigned __int8 *, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x1800180cc`
- `0x18002ea4c`

## callees

- `0x180007f10`
- `0x18000abf0`
- `0x18000b680`
- `0x18000c4a0`
- `0x180011014`
- `0x18001199c`
- `0x180012da4`
- `0x18001c9c0`
- `0x18001d810`
- `0x180024f38`
- `0x18002a794`
- `0x18002c738`
- `0x18002cf10`
- `0x180036778`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002abcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ab71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002abcd`

## string_xrefs

- `0x18002a84f`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002a8c2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002aa47`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002aaa5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002aae5`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002aaec`: `dwTempError`

## pseudocode

```c
__int64 __fastcall BackupMasterKey(
        void *a1,
        struct MASTERKEY_STORED *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        int a5,
        int a6)
{
  UCHAR *v6; // rsi
  ULONG v7; // r12d
  int v10; // r13d
  unsigned int v11; // r15d
  unsigned int v12; // ebx
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned int v16; // eax
  int v17; // ecx
  ULONG v18; // eax
  unsigned int v19; // eax
  __int64 v20; // r9
  unsigned int v21; // eax
  unsigned int v22; // edi
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned __int8 *v25; // rax
  UCHAR *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  UCHAR *v29; // rax
  _BYTE *v30; // rax
  __int64 v31; // rcx
  _BYTE *v32; // rcx
  __int64 v33; // rax
  size_t Size; // [rsp+30h] [rbp-D0h]
  ULONG cbInput; // [rsp+60h] [rbp-A0h] BYREF
  size_t v37; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v38; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v39; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v40; // [rsp+74h] [rbp-8Ch]
  HLOCAL hMem; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v42; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-78h] BYREF
  PUCHAR pbInput; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 *v45; // [rsp+98h] [rbp-68h]
  struct _GUID v46; // [rsp+A0h] [rbp-60h] BYREF
  UCHAR v47[32]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 v48[64]; // [rsp+D0h] [rbp-30h] BYREF

  v37 = a4;
  v43 = 0;
  v6 = 0;
  pbInput = 0;
  v7 = 0;
  cbInput = 0;
  hMem = 0;
  v42 = 0;
  v38 = 0;
  v45 = a3;
  v39 = 64;
  v10 = FIsLegacyCompliant();
  if ( a1 )
  {
    v11 = *((_DWORD *)a1 + 13);
    v12 = *((_DWORD *)a1 + 14);
  }
  else
  {
    v12 = 32782;
    v11 = 26128;
  }
  v40 = v12;
  if ( !(unsigned int)GetLocalKeyUserEncryptionKey(a1, a2, v48, &v39, &v43) )
  {
    v13 = -2146893821;
    v14 = 5603;
LABEL_6:
    v15 = v13;
LABEL_7:
    DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v14);
    goto LABEL_41;
  }
  v46 = GUID_NULL;
  v16 = DecryptMasterKeyFromStorage(a2, 1u, v11, v12, v48, v39, 0, &pbInput, &cbInput, &v46, a1);
  v13 = v16;
  if ( v16 )
  {
    DebugTraceError(v16, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5626);
    v6 = pbInput;
    v7 = cbInput;
    goto LABEL_41;
  }
  UpdateGlobals(v17);
  v6 = pbInput;
  v7 = cbInput;
  if ( dword_18004CC9C && (unsigned int)IsNT4Domain() )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 107, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    v10 = 1;
  }
  else if ( !v10 )
  {
    goto LABEL_21;
  }
  if ( !(unsigned int)FMyPrimitiveSHA(v6, v7, v47) )
  {
    v13 = 13;
    v14 = 5655;
    goto LABEL_6;
  }
  LODWORD(Size) = v37;
  v18 = EncryptMasterKeyToMemory(
          v11,
          v40,
          v47,
          0x14u,
          0,
          v45,
          Size,
          (unsigned __int8 **)&hMem,
          (unsigned int *)&v37 + 1);
  v13 = v18;
  if ( v18 )
  {
    v14 = 5679;
    v15 = v18;
    goto LABEL_7;
  }
LABEL_21:
  if ( !a5 )
    goto LABEL_31;
  if ( a6 && !v10 )
  {
    v19 = AttemptLocalBackup(0, *((void **)a1 + 3), a2, v45, v37, v6, v7, (unsigned __int8 **)&v42, &v38);
    if ( v19 )
    {
      v20 = 5724;
    }
    else
    {
      v19 = PersistMasterKeyToStorage(a2, 3, (unsigned __int8 *)v42, v38);
      v13 = v19;
      if ( !v19 )
      {
        PersistMasterKeyToStorage(a2, 2, 0, 0);
        goto LABEL_41;
      }
      v20 = 5738;
    }
    DebugTraceError(v19, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v20);
  }
  v21 = QueueBackupMasterKey(a1, a2, v6, v7, v45, v37, a6 != 0 ? 2000 : 20000);
  v13 = v21;
  if ( v21 )
  {
    DebugTraceError(v21, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5781);
LABEL_31:
    v22 = 0;
    if ( hMem )
    {
      v23 = PersistMasterKeyToStorage(a2, 2, (unsigned __int8 *)hMem, HIDWORD(v37));
      v22 = v23;
      if ( v23 )
        DebugTraceError(v23, "dwTempError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 5811);
    }
    if ( a6 && hMem )
    {
      v13 = v22;
    }
    else if ( !v13 && v22 )
    {
      v13 = v22;
    }
  }
LABEL_41:
  v24 = 64;
  v25 = v48;
  do
  {
    *v25++ = 0;
    --v24;
  }
  while ( v24 );
  v26 = v47;
  v27 = 20;
  do
  {
    *v26++ = 0;
    --v27;
  }
  while ( v27 );
  if ( v6 )
  {
    v28 = v7;
    v29 = v6;
    if ( v7 )
    {
      do
      {
        *v29++ = 0;
        --v28;
      }
      while ( v28 );
    }
    LocalFree(v6);
  }
  v30 = hMem;
  if ( hMem )
  {
    v31 = HIDWORD(v37);
    if ( HIDWORD(v37) )
    {
      do
      {
        *v30++ = 0;
        --v31;
      }
      while ( v31 );
    }
    LocalFree(hMem);
  }
  v32 = v42;
  if ( v42 )
  {
    v33 = v38;
    if ( v38 )
    {
      do
      {
        *v32++ = 0;
        --v33;
      }
      while ( v33 );
      v32 = v42;
    }
    LocalFree(v32);
  }
  return v13;
}

```

## disassembly

```asm
0x18002a794  push    rbp
0x18002a796  push    rbx
0x18002a797  push    rsi
0x18002a798  push    rdi
0x18002a799  push    r12
0x18002a79b  push    r13
0x18002a79d  push    r14
0x18002a79f  push    r15
0x18002a7a1  lea     rbp, [rsp-28h]
0x18002a7a6  sub     rsp, 128h
0x18002a7ad  mov     rax, cs:__security_cookie
0x18002a7b4  xor     rax, rsp
0x18002a7b7  mov     [rbp+60h+var_50], rax
0x18002a7bb  xor     ebx, ebx
0x18002a7bd  mov     dword ptr [rsp+160h+var_FC], r9d
0x18002a7c2  mov     [rbp+60h+var_D8], ebx
0x18002a7c5  mov     esi, ebx
0x18002a7c7  mov     [rbp+60h+pbInput], rbx
0x18002a7cb  mov     r12d, ebx
0x18002a7ce  mov     [rsp+160h+cbInput], ebx
0x18002a7d2  mov     r14, rdx
0x18002a7d5  mov     [rsp+160h+hMem], rbx
0x18002a7da  mov     rdi, rcx
0x18002a7dd  mov     dword ptr [rsp+160h+var_FC+4], ebx
0x18002a7e1  mov     [rbp+60h+var_E0], rbx
0x18002a7e5  mov     [rsp+160h+var_F4], ebx
0x18002a7e9  mov     [rbp+60h+var_C8], r8
0x18002a7ed  mov     [rsp+160h+var_F0], 40h ; '@'
0x18002a7f5  call    ?FIsLegacyCompliant@@YAHXZ; FIsLegacyCompliant(void)
0x18002a7fa  mov     r13d, eax
0x18002a7fd  test    rdi, rdi
0x18002a800  jz      short loc_18002A80B
0x18002a802  mov     r15d, [rdi+34h]
0x18002a806  mov     ebx, [rdi+38h]
0x18002a809  jmp     short loc_18002A816
0x18002a80b  mov     ebx, 800Eh
0x18002a810  mov     r15d, 6610h
0x18002a816  lea     rax, [rbp+60h+var_D8]
0x18002a81a  mov     [rsp+160h+var_EC], ebx
0x18002a81e  lea     r9, [rsp+160h+var_F0]; unsigned int *
0x18002a823  mov     [rsp+160h+var_140], rax; unsigned int *
0x18002a828  lea     r8, [rbp+60h+var_90]; unsigned __int8 *
0x18002a82c  mov     rdx, r14; struct MASTERKEY_STORED *
0x18002a82f  mov     rcx, rdi; void *
0x18002a832  call    ?GetLocalKeyUserEncryptionKey@@YAHPEAXPEAUMASTERKEY_STORED@@PEAEPEAK3@Z; GetLocalKeyUserEncryptionKey(void *,MASTERKEY_STORED *,uchar *,ulong *,ulong *)
0x18002a837  test    eax, eax
0x18002a839  jnz     short loc_18002A860
0x18002a83b  mov     ebx, 80090003h
0x18002a840  mov     r9d, 15E3h
0x18002a846  mov     ecx, ebx
0x18002a848  lea     rdx, aDwlasterror; "dwLastError"
0x18002a84f  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a856  call    DebugTraceError
0x18002a85b  jmp     loc_18002AB28
0x18002a860  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002a867  mov     [rsp+160h+var_110], rdi; void *
0x18002a86c  lea     rax, [rbp+60h+var_C0]
0x18002a870  mov     [rsp+160h+var_118], rax; struct _GUID
0x18002a875  mov     r9d, ebx; unsigned int
0x18002a878  lea     rax, [rsp+160h+cbInput]
0x18002a87d  mov     r8d, r15d; unsigned int
0x18002a880  mov     [rsp+160h+var_120], rax; unsigned int *
0x18002a885  mov     edx, 1; unsigned int
0x18002a88a  lea     rax, [rbp+60h+pbInput]
0x18002a88e  mov     rcx, r14; struct MASTERKEY_STORED *
0x18002a891  mov     [rsp+160h+var_128], rax; unsigned __int8 **
0x18002a896  mov     eax, [rsp+160h+var_F0]
0x18002a89a  mov     [rsp+160h+Size], rsi; int *
0x18002a89f  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x18002a8a3  lea     rax, [rbp+60h+var_90]
0x18002a8a7  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x18002a8ac  movdqu  xmmword ptr [rbp+60h+var_C0.Data1], xmm0
0x18002a8b1  call    ?DecryptMasterKeyFromStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKPEAHPEAPEAEPEAKU_GUID@@PEAX@Z; DecryptMasterKeyFromStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,int *,uchar * *,ulong *,_GUID,void *)
0x18002a8b6  mov     ebx, eax
0x18002a8b8  test    eax, eax
0x18002a8ba  jz      short loc_18002A8E5
0x18002a8bc  mov     r9d, 15FAh
0x18002a8c2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002a8c9  lea     rdx, aDwlasterror; "dwLastError"
0x18002a8d0  mov     ecx, eax
0x18002a8d2  call    DebugTraceError
0x18002a8d7  mov     rsi, [rbp+60h+pbInput]
0x18002a8db  mov     r12d, [rsp+160h+cbInput]
0x18002a8e0  jmp     loc_18002AB28
0x18002a8e5  call    ?UpdateGlobals@@YAKH@Z; UpdateGlobals(int)
0x18002a8ea  cmp     cs:dword_18004CC9C, 0
0x18002a8f1  mov     rsi, [rbp+60h+pbInput]
0x18002a8f5  mov     r12d, [rsp+160h+cbInput]
0x18002a8fa  jz      short loc_18002A93B
0x18002a8fc  call    ?IsNT4Domain@@YAHXZ; IsNT4Domain(void)
0x18002a901  test    eax, eax
0x18002a903  jz      short loc_18002A93B
0x18002a905  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a90c  lea     rax, WPP_GLOBAL_Control
0x18002a913  cmp     rcx, rax
0x18002a916  jz      short loc_18002A933
0x18002a918  test    byte ptr [rcx+1Ch], 2
0x18002a91c  jz      short loc_18002A933
0x18002a91e  mov     rcx, [rcx+10h]
0x18002a922  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002a929  mov     edx, 6Bh ; 'k'
0x18002a92e  call    WPP_SF_
0x18002a933  mov     r13d, 1
0x18002a939  jmp     short loc_18002A940
0x18002a93b  test    r13d, r13d
0x18002a93e  jz      short loc_18002A9BC
0x18002a940  lea     rax, [rbp+60h+var_B0]
0x18002a944  mov     edx, r12d; cbInput
0x18002a947  mov     rcx, rsi; pbInput
0x18002a94a  mov     [rsp+160h+var_140], rax; PUCHAR
0x18002a94f  call    FMyPrimitiveSHA
0x18002a954  test    eax, eax
0x18002a956  jnz     short loc_18002A966
0x18002a958  lea     ebx, [rax+0Dh]
0x18002a95b  mov     r9d, 1617h
0x18002a961  jmp     loc_18002A846
0x18002a966  mov     edx, [rsp+160h+var_EC]; unsigned int
0x18002a96a  lea     rax, [rsp+160h+var_FC+4]
0x18002a96f  mov     [rsp+160h+var_120], rax; unsigned int *
0x18002a974  lea     r8, [rbp+60h+var_B0]; unsigned __int8 *
0x18002a978  lea     rax, [rsp+160h+hMem]
0x18002a97d  mov     r9d, 14h; unsigned int
0x18002a983  mov     [rsp+160h+var_128], rax; unsigned __int8 **
0x18002a988  mov     ecx, r15d; unsigned int
0x18002a98b  mov     eax, dword ptr [rsp+160h+var_FC]
0x18002a98f  mov     dword ptr [rsp+160h+Size], eax; Size
0x18002a993  mov     rax, [rbp+60h+var_C8]
0x18002a997  mov     [rsp+160h+var_138], rax; unsigned __int8 *
0x18002a99c  mov     dword ptr [rsp+160h+var_140], 0; unsigned int
0x18002a9a4  call    ?EncryptMasterKeyToMemory@@YAKIIPEAEKK0KPEAPEAEPEAK@Z; EncryptMasterKeyToMemory(uint,uint,uchar *,ulong,ulong,uchar *,ulong,uchar * *,ulong *)
0x18002a9a9  mov     ebx, eax
0x18002a9ab  test    eax, eax
0x18002a9ad  jz      short loc_18002A9BC
0x18002a9af  mov     r9d, 162Fh
0x18002a9b5  mov     ecx, eax
0x18002a9b7  jmp     loc_18002A848
0x18002a9bc  cmp     [rbp+60h+arg_20], 0
0x18002a9c3  mov     r15d, [rbp+60h+arg_28]
0x18002a9ca  jz      loc_18002AABA
0x18002a9d0  test    r15d, r15d
0x18002a9d3  jz      loc_18002AA5C
0x18002a9d9  test    r13d, r13d
0x18002a9dc  jnz     short loc_18002AA5C
0x18002a9de  mov     r9, [rbp+60h+var_C8]; unsigned __int8 *
0x18002a9e2  lea     rax, [rsp+160h+var_F4]
0x18002a9e7  mov     rdx, [rdi+18h]; void *
0x18002a9eb  mov     r8, r14; struct MASTERKEY_STORED *
0x18002a9ee  mov     [rsp+160h+var_120], rax; unsigned int *
0x18002a9f3  xor     ecx, ecx; int
0x18002a9f5  lea     rax, [rbp+60h+var_E0]
0x18002a9f9  mov     [rsp+160h+var_128], rax; unsigned __int8 **
0x18002a9fe  mov     eax, dword ptr [rsp+160h+var_FC]
0x18002aa02  mov     dword ptr [rsp+160h+Size], r12d; unsigned int
0x18002aa07  mov     [rsp+160h+var_138], rsi; unsigned __int8 *
0x18002aa0c  mov     dword ptr [rsp+160h+var_140], eax; unsigned int
0x18002aa10  call    ?AttemptLocalBackup@@YAKHPEAXPEAUMASTERKEY_STORED@@PEAEK2KPEAPEAEPEAK@Z; AttemptLocalBackup(int,void *,MASTERKEY_STORED *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18002aa15  test    eax, eax
0x18002aa17  jz      short loc_18002AA21
0x18002aa19  mov     r9d, 165Ch
0x18002aa1f  jmp     short loc_18002AA47
0x18002aa21  mov     r9d, [rsp+160h+var_F4]; unsigned int
0x18002aa26  mov     edx, 3; unsigned int
0x18002aa2b  mov     r8, [rbp+60h+var_E0]; unsigned __int8 *
0x18002aa2f  mov     rcx, r14; struct MASTERKEY_STORED *
0x18002aa32  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002aa37  mov     ebx, eax
0x18002aa39  test    eax, eax
0x18002aa3b  jz      loc_18002AB0B
0x18002aa41  mov     r9d, 166Ah
0x18002aa47  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002aa4e  mov     ecx, eax
0x18002aa50  lea     rdx, aDwlasterror; "dwLastError"
0x18002aa57  call    DebugTraceError
0x18002aa5c  mov     eax, r15d
0x18002aa5f  mov     r9d, r12d; unsigned int
0x18002aa62  neg     eax
0x18002aa64  mov     r8, rsi; unsigned __int8 *
0x18002aa67  mov     eax, dword ptr [rsp+160h+var_FC]
0x18002aa6b  mov     rcx, rdi; void *
0x18002aa6e  sbb     edx, edx
0x18002aa70  and     edx, 0FFFFB9B0h
0x18002aa76  add     edx, 4E20h
0x18002aa7c  mov     dword ptr [rsp+160h+Size], edx; unsigned int
0x18002aa80  mov     rdx, r14; struct MASTERKEY_STORED *
0x18002aa83  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x18002aa87  mov     rax, [rbp+60h+var_C8]
0x18002aa8b  mov     [rsp+160h+var_140], rax; unsigned __int8 *
0x18002aa90  call    ?QueueBackupMasterKey@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEK2KK@Z; QueueBackupMasterKey(void *,MASTERKEY_STORED *,uchar *,ulong,uchar *,ulong,ulong)
0x18002aa95  mov     ebx, eax
0x18002aa97  test    eax, eax
0x18002aa99  jz      loc_18002AB28
0x18002aa9f  mov     r9d, 1695h
0x18002aaa5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002aaac  lea     rdx, aDwlasterror; "dwLastError"
0x18002aab3  mov     ecx, eax
0x18002aab5  call    DebugTraceError
0x18002aaba  mov     rax, [rsp+160h+hMem]
0x18002aabf  xor     edi, edi
0x18002aac1  test    rax, rax
0x18002aac4  jz      short loc_18002AAFA
0x18002aac6  mov     r9d, dword ptr [rsp+160h+var_FC+4]; unsigned int
0x18002aacb  lea     edx, [rdi+2]; unsigned int
0x18002aace  mov     r8, rax; unsigned __int8 *
0x18002aad1  mov     rcx, r14; struct MASTERKEY_STORED *
0x18002aad4  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002aad9  mov     edi, eax
0x18002aadb  test    eax, eax
0x18002aadd  jz      short loc_18002AAFA
0x18002aadf  mov     r9d, 16B3h
0x18002aae5  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002aaec  lea     rdx, aDwtemperror; "dwTempError"
0x18002aaf3  mov     ecx, eax
0x18002aaf5  call    DebugTraceError
0x18002aafa  test    r15d, r15d
0x18002aafd  jz      short loc_18002AB1F
0x18002aaff  cmp     [rsp+160h+hMem], 0
0x18002ab05  jz      short loc_18002AB1F
0x18002ab07  mov     ebx, edi
0x18002ab09  jmp     short loc_18002AB28
0x18002ab0b  xor     r9d, r9d; unsigned int
0x18002ab0e  xor     r8d, r8d; unsigned __int8 *
0x18002ab11  mov     rcx, r14; struct MASTERKEY_STORED *
0x18002ab14  lea     edx, [r9+2]; unsigned int
0x18002ab18  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002ab1d  jmp     short loc_18002AB28
0x18002ab1f  test    ebx, ebx
0x18002ab21  jnz     short loc_18002AB28
0x18002ab23  test    edi, edi
0x18002ab25  cmovnz  ebx, edi
0x18002ab28  mov     ecx, 40h ; '@'
0x18002ab2d  lea     rax, [rbp+60h+var_90]
0x18002ab31  lea     edi, [rcx-3Fh]
0x18002ab34  mov     byte ptr [rax], 0
0x18002ab37  add     rax, rdi
0x18002ab3a  sub     rcx, rdi
0x18002ab3d  jnz     short loc_18002AB34
0x18002ab3f  lea     rax, [rbp+60h+var_B0]
0x18002ab43  mov     ecx, 14h
0x18002ab48  mov     byte ptr [rax], 0
0x18002ab4b  add     rax, rdi
0x18002ab4e  sub     rcx, rdi
0x18002ab51  jnz     short loc_18002AB48
0x18002ab53  test    rsi, rsi
0x18002ab56  jz      short loc_18002AB7D
0x18002ab58  mov     edx, r12d
0x18002ab5b  mov     rax, rsi
0x18002ab5e  test    r12d, r12d
0x18002ab61  jz      short loc_18002AB6E
0x18002ab63  mov     byte ptr [rax], 0
0x18002ab66  add     rax, rdi
0x18002ab69  sub     rdx, rdi
0x18002ab6c  jnz     short loc_18002AB63
0x18002ab6e  mov     rcx, rsi; hMem
0x18002ab71  call    cs:__imp_LocalFree
0x18002ab78  nop     dword ptr [rax+rax+00h]
0x18002ab7d  mov     rax, [rsp+160h+hMem]
0x18002ab82  test    rax, rax
0x18002ab85  jz      short loc_18002ABAC
0x18002ab87  mov     ecx, dword ptr [rsp+160h+var_FC+4]
0x18002ab8b  test    rcx, rcx
0x18002ab8e  jz      short loc_18002AB9B
0x18002ab90  mov     byte ptr [rax], 0
0x18002ab93  add     rax, rdi
0x18002ab96  sub     rcx, rdi
0x18002ab99  jnz     short loc_18002AB90
0x18002ab9b  mov     rcx, [rsp+160h+hMem]; hMem
0x18002aba0  call    cs:__imp_LocalFree
0x18002aba7  nop     dword ptr [rax+rax+00h]
0x18002abac  mov     rcx, [rbp+60h+var_E0]
0x18002abb0  test    rcx, rcx
0x18002abb3  jz      short loc_18002ABD9
0x18002abb5  mov     eax, [rsp+160h+var_F4]
0x18002abb9  test    rax, rax
0x18002abbc  jz      short loc_18002ABCD
0x18002abbe  mov     byte ptr [rcx], 0
0x18002abc1  add     rcx, rdi
0x18002abc4  sub     rax, rdi
0x18002abc7  jnz     short loc_18002ABBE
0x18002abc9  mov     rcx, [rbp+60h+var_E0]; hMem
0x18002abcd  call    cs:__imp_LocalFree
0x18002abd4  nop     dword ptr [rax+rax+00h]
0x18002abd9  mov     eax, ebx
0x18002abdb  mov     rcx, [rbp+60h+var_50]
0x18002abdf  xor     rcx, rsp; StackCookie
0x18002abe2  call    __security_check_cookie
0x18002abe7  add     rsp, 128h
0x18002abee  pop     r15
0x18002abf0  pop     r14
0x18002abf2  pop     r13
0x18002abf4  pop     r12
0x18002abf6  pop     rdi
0x18002abf7  pop     rsi
0x18002abf8  pop     rbx
0x18002abf9  pop     rbp
0x18002abfa  retn
```
