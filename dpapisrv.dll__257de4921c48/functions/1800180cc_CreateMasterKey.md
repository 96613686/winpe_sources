# CreateMasterKey

- ea: `0x1800180cc`
- end: `0x180018663`
- name: `CreateMasterKey`
- size: `1431`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, unsigned __int16 *@<rdx>, struct _GUID *@<r8>, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018a20`
- `0x18002b0ec`

## callees

- `0x1800012fc`
- `0x1800048a4`
- `0x180007f10`
- `0x18000a7a0`
- `0x18000b5cc`
- `0x18000dcb0`
- `0x18000f910`
- `0x180012258`
- `0x180012da4`
- `0x18001467c`
- `0x1800180cc`
- `0x18001866c`
- `0x18001b234`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002a794`
- `0x18002ac04`
- `0x18002f234`
- `0x18002f5d4`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180018163`
- `RPCRT4!UuidCreate` at `0x180018163`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018211`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018211`
- `bcrypt!BCryptGenRandom` at `0x180018299`
- `bcrypt!BCryptGenRandom` at `0x1800183da`
- `bcrypt!BCryptGenRandom` at `0x180018299`
- `bcrypt!BCryptGenRandom` at `0x1800183da`
- `ntdll!RtlNtStatusToDosError` at `0x1800182c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800182c8`

## string_xrefs

- `0x180018189`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180018272`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800182b1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800184d9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18001856e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall CreateMasterKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int a4,
        __int64 a5)
{
  RPC_STATUS v8; // eax
  int v9; // edx
  int v10; // r8d
  ULONG v11; // ebx
  __int64 v12; // r9
  const char *v13; // rdx
  __int64 v14; // rax
  SIZE_T v15; // rbx
  HLOCAL v16; // rax
  int v17; // r13d
  __int64 v18; // rsi
  __int64 v19; // r14
  NTSTATUS v20; // eax
  NTSTATUS v21; // ebx
  int v22; // ebx
  int MasterKeyUserEncryptionKey; // esi
  struct _GUID *v24; // rdx
  __int64 v25; // r9
  __int64 v26; // rcx
  ULONG v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // r15d
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // r9
  UCHAR *v34; // rax
  UCHAR *v35; // rax
  size_t v37; // [rsp+40h] [rbp-C0h]
  int v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v39; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v41; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v42; // [rsp+60h] [rbp-A0h]
  struct _GUID v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v44[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v45; // [rsp+84h] [rbp-7Ch]
  _DWORD v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 StringUuid[40]; // [rsp+B0h] [rbp-50h] BYREF
  int v49; // [rsp+100h] [rbp+0h]
  struct _GUID v50; // [rsp+140h] [rbp+40h] BYREF
  UCHAR v51[32]; // [rsp+150h] [rbp+50h] BYREF
  UCHAR pbBuffer[64]; // [rsp+170h] [rbp+70h] BYREF

  *(_QWORD *)&v43.Data1 = a5;
  v40 = a4;
  memset_0(v46, 0, 0xA0u);
  v41 = 0;
  v38 = 0;
  if ( a1 )
  {
    v39 = *((_DWORD *)a1 + 13);
    v42 = *((_DWORD *)a1 + 14);
  }
  else
  {
    v39 = 26128;
    v42 = 32782;
  }
  v50 = 0;
  v8 = UuidCreate(a3);
  v11 = v8;
  if ( v8 && v8 != 1824 )
  {
    v12 = 2689;
    v13 = "dwLastError";
LABEL_7:
    DebugTraceError(v11, v13, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v12);
    return v11;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_S_guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v9, v10, (_DWORD)a2, (__int64)a3);
  memset_0(&v47, 0, 0x98u);
  v46[0] = 2;
  v46[1] = 1;
  InitializeMasterKeyPolicy(a1, (struct MASTERKEY_STORED *)v46, &v38);
  v14 = -1;
  do
    ++v14;
  while ( a2[v14] );
  v15 = (unsigned int)(2 * v14 + 2);
  v16 = LocalAlloc(0, v15);
  v47 = v16;
  if ( !v16 )
  {
    v12 = 2722;
    v13 = "ERROR_NOT_ENOUGH_SERVER_MEMORY";
    v11 = 1130;
    goto LABEL_7;
  }
  v17 = 0;
  memcpy_0(v16, a2, v15);
  v18 = 20;
  v19 = 64;
  if ( (unsigned int)MyGuidToStringW(a3, StringUuid) )
  {
    v11 = 13;
    DebugTraceError(13, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 2732);
    goto LABEL_59;
  }
  v20 = BCryptGenRandom(0, pbBuffer, 0x40u, 2u);
  v21 = v20;
  if ( v20 < 0 )
  {
    DebugTraceError(
      (unsigned int)v20,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      2746);
    v11 = RtlNtStatusToDosError(v21);
    goto LABEL_59;
  }
  v22 = v38;
  if ( v38 )
  {
    MasterKeyUserEncryptionKey = GetMasterKeyUserEncryptionKey(a1, &v50, 0, 3u, v51, &v41);
    if ( MasterKeyUserEncryptionKey )
    {
      v49 |= 4u;
      goto LABEL_37;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 75, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    v24 = &v50;
  }
  else
  {
    v24 = 0;
  }
  MasterKeyUserEncryptionKey = GetMasterKeyUserEncryptionKey(a1, v24, 0, 2u, v51, &v41);
  if ( !MasterKeyUserEncryptionKey )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        (unsigned int)(MasterKeyUserEncryptionKey + 78),
        WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    if ( v22 )
    {
      v25 = 2833;
LABEL_33:
      v11 = 5;
      v26 = 5;
      goto LABEL_47;
    }
    if ( (v49 & 2) != 0 )
    {
      v25 = 2840;
      goto LABEL_33;
    }
    BCryptGenRandom(0, v51, 0x14u, 2u);
  }
LABEL_37:
  if ( v22
    && (*(_DWORD *)v44 = 3,
        v45 = v50,
        v27 = PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v46, 2, v44, 0x14u),
        (v11 = v27) != 0) )
  {
    v25 = 2875;
  }
  else
  {
    if ( *(_QWORD *)&v43.Data1 )
      InsertMasterKeyCache(a1, *(struct _LUID **)&v43.Data1, a2, a3, pbBuffer, 0x40u);
    LODWORD(v37) = 64;
    v27 = EncryptMasterKeyToStorage((struct MASTERKEY_STORED *)v46, 0, v39, v42, v51, 0x14u, v41, pbBuffer, v37);
    v11 = v27;
    if ( v27 )
    {
      v25 = 2904;
    }
    else
    {
      v43 = v50;
      LogMasterKeyDescription(StringUuid, &v43, v51, a1 + 40);
      v27 = BuildLocalKey(a1, (struct MASTERKEY_STORED *)v46, v39, v42);
      v11 = v27;
      if ( !v27 )
      {
        v38 = 0;
        v17 = 1;
        if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 4) != 0 )
          McTemplateU0jz_EtwEventWriteTransfer(v29, v28, a3, a2);
        if ( (unsigned int)IsBackupMasterKeyRequired((struct MASTERKEY_STORED *)v46, &v38) )
        {
          if ( (unsigned int)BackupMasterKey(
                               a1,
                               (struct MASTERKEY_STORED *)v46,
                               pbBuffer,
                               0x40u,
                               v38,
                               MasterKeyUserEncryptionKey) )
          {
            v30 = v40;
            if ( !MasterKeyUserEncryptionKey || v40 && !*((_DWORD *)a1 + 4) )
            {
              v11 = -2146892987;
              DebugTraceError(
                2148074309LL,
                "dwLastError",
                "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
                2970);
              v17 = 0;
              if ( (unsigned int)dword_18004C260 > 5
                && (unsigned __int8)tlgKeywordOn(&dword_18004C260, 0x400000000000LL) )
              {
                v38 = *((_DWORD *)a1 + 4);
                v40 = MasterKeyUserEncryptionKey;
                v39 = v30;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  v31,
                  (int)&word_180044F4E,
                  v32,
                  v33,
                  (__int64)&v39,
                  (__int64)&v38,
                  (__int64)&v40);
              }
            }
          }
        }
        goto LABEL_58;
      }
      v25 = 2925;
    }
  }
  v26 = v27;
LABEL_47:
  DebugTraceError(v26, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v25);
LABEL_58:
  v18 = 20;
LABEL_59:
  v34 = pbBuffer;
  do
  {
    *v34++ = 0;
    --v19;
  }
  while ( v19 );
  v35 = v51;
  do
  {
    *v35++ = 0;
    --v18;
  }
  while ( v18 );
  if ( (unsigned int)CloseMasterKey(a1, (struct MASTERKEY_STORED *)v46, v17) && v17 )
    return 0;
  if ( !v11 )
    return 87;
  return v11;
}

```

## disassembly

```asm
0x1800180cc  mov     [rsp-8+arg_18], rbx
0x1800180d1  push    rbp
0x1800180d2  push    rsi
0x1800180d3  push    rdi
0x1800180d4  push    r12
0x1800180d6  push    r13
0x1800180d8  push    r14
0x1800180da  push    r15
0x1800180dc  lea     rbp, [rsp-0C0h]
0x1800180e4  sub     rsp, 1C0h
0x1800180eb  mov     rax, cs:__security_cookie
0x1800180f2  xor     rax, rsp
0x1800180f5  mov     [rbp+0F0h+var_40], rax
0x1800180fc  mov     rax, [rbp+0F0h+arg_20]
0x180018103  mov     r15, r8
0x180018106  mov     r12, rdx
0x180018109  mov     qword ptr [rsp+1F0h+var_180.Data1], rax
0x18001810e  mov     rdi, rcx
0x180018111  mov     [rsp+1F0h+var_198], r9d
0x180018116  xor     edx, edx; Val
0x180018118  lea     rcx, [rbp+0F0h+var_150]; void *
0x18001811c  mov     r8d, 0A0h; Size
0x180018122  call    memset_0
0x180018127  xor     r14d, r14d
0x18001812a  mov     [rsp+1F0h+var_194], r14d
0x18001812f  mov     [rsp+1F0h+var_1A0], r14d
0x180018134  test    rdi, rdi
0x180018137  jz      short loc_180018149
0x180018139  mov     esi, [rdi+34h]
0x18001813c  mov     [rsp+1F0h+var_19C], esi
0x180018140  mov     esi, [rdi+38h]
0x180018143  mov     [rsp+1F0h+var_190], esi
0x180018147  jmp     short loc_180018159
0x180018149  mov     [rsp+1F0h+var_19C], 6610h
0x180018151  mov     [rsp+1F0h+var_190], 800Eh
0x180018159  xorps   xmm0, xmm0
0x18001815c  mov     rcx, r15; Uuid
0x18001815f  movups  xmmword ptr [rbp+0F0h+var_B0.Data1], xmm0
0x180018163  call    cs:__imp_UuidCreate
0x18001816a  nop     dword ptr [rax+rax+00h]
0x18001816f  mov     ebx, eax
0x180018171  test    eax, eax
0x180018173  jz      short loc_18001819C
0x180018175  cmp     eax, 720h
0x18001817a  jz      short loc_18001819C
0x18001817c  mov     r9d, 0A81h
0x180018182  lea     rdx, aDwlasterror; "dwLastError"
0x180018189  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018190  mov     ecx, ebx
0x180018192  call    DebugTraceError
0x180018197  jmp     loc_180018636
0x18001819c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181a3  lea     rax, WPP_GLOBAL_Control
0x1800181aa  cmp     rcx, rax
0x1800181ad  jz      short loc_1800181C6
0x1800181af  test    byte ptr [rcx+1Ch], 8
0x1800181b3  jz      short loc_1800181C6
0x1800181b5  mov     rcx, [rcx+10h]
0x1800181b9  mov     r9, r12
0x1800181bc  mov     [rsp+1F0h+var_1D0], r15
0x1800181c1  call    WPP_SF_S_guid_
0x1800181c6  xor     edx, edx; Val
0x1800181c8  lea     rcx, [rbp+0F0h+var_148]; void *
0x1800181cc  mov     r8d, 98h; Size
0x1800181d2  call    memset_0
0x1800181d7  lea     r8, [rsp+1F0h+var_1A0]; int *
0x1800181dc  mov     [rbp+0F0h+var_150], 2
0x1800181e3  lea     rdx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x1800181e7  mov     [rbp+0F0h+var_14C], 1
0x1800181ee  mov     rcx, rdi; void *
0x1800181f1  call    ?InitializeMasterKeyPolicy@@YAHPEAXPEAUMASTERKEY_STORED@@PEAH@Z; InitializeMasterKeyPolicy(void *,MASTERKEY_STORED *,int *)
0x1800181f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800181fa  inc     rax
0x1800181fd  cmp     [r12+rax*2], r14w
0x180018202  jnz     short loc_1800181FA
0x180018204  lea     eax, ds:2[rax*2]
0x18001820b  xor     ecx, ecx; uFlags
0x18001820d  mov     edx, eax; uBytes
0x18001820f  mov     ebx, eax
0x180018211  call    cs:__imp_LocalAlloc
0x180018218  nop     dword ptr [rax+rax+00h]
0x18001821d  mov     [rbp+0F0h+var_148], rax
0x180018221  test    rax, rax
0x180018224  jnz     short loc_18001823D
0x180018226  mov     r9d, 0AA2h
0x18001822c  lea     rdx, aErrorNotEnough_0; "ERROR_NOT_ENOUGH_SERVER_MEMORY"
0x180018233  mov     ebx, 46Ah
0x180018238  jmp     loc_180018189
0x18001823d  mov     r8, rbx; Size
0x180018240  mov     rdx, r12; Src
0x180018243  mov     rcx, rax; void *
0x180018246  mov     r13d, r14d
0x180018249  call    memcpy_0
0x18001824e  lea     rdx, [rbp+0F0h+StringUuid]
0x180018252  mov     rcx, r15
0x180018255  call    MyGuidToStringW
0x18001825a  mov     esi, 14h
0x18001825f  lea     r14d, [rsi+2Ch]
0x180018263  test    eax, eax
0x180018265  jz      short loc_18001828A
0x180018267  lea     ebx, [rsi-7]
0x18001826a  mov     r9d, 0AACh
0x180018270  mov     ecx, ebx
0x180018272  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018279  lea     rdx, aDwlasterror; "dwLastError"
0x180018280  call    DebugTraceError
0x180018285  jmp     loc_1800185F0
0x18001828a  mov     r9d, 2; dwFlags
0x180018290  lea     rdx, [rbp+0F0h+pbBuffer]; pbBuffer
0x180018294  mov     r8d, r14d; cbBuffer
0x180018297  xor     ecx, ecx; hAlgorithm
0x180018299  call    cs:__imp_BCryptGenRandom
0x1800182a0  nop     dword ptr [rax+rax+00h]
0x1800182a5  mov     ebx, eax
0x1800182a7  test    eax, eax
0x1800182a9  jns     short loc_1800182DB
0x1800182ab  mov     r9d, 0ABAh
0x1800182b1  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800182b8  lea     rdx, aNtstatus; "ntStatus"
0x1800182bf  mov     ecx, eax
0x1800182c1  call    DebugTraceError
0x1800182c6  mov     ecx, ebx; Status
0x1800182c8  call    cs:__imp_RtlNtStatusToDosError
0x1800182cf  nop     dword ptr [rax+rax+00h]
0x1800182d4  mov     ebx, eax
0x1800182d6  jmp     loc_1800185F0
0x1800182db  mov     ebx, [rsp+1F0h+var_1A0]
0x1800182df  test    ebx, ebx
0x1800182e1  jz      short loc_18001834E
0x1800182e3  lea     rax, [rsp+1F0h+var_194]
0x1800182e8  mov     r9d, 3; unsigned int
0x1800182ee  mov     [rsp+1F0h+var_1C8], rax; unsigned int *
0x1800182f3  lea     rdx, [rbp+0F0h+var_B0]; struct _GUID *
0x1800182f7  lea     rax, [rbp+0F0h+var_A0]
0x1800182fb  xor     r8d, r8d; void *
0x1800182fe  mov     rcx, rdi; void *
0x180018301  mov     [rsp+1F0h+var_1D0], rax; unsigned __int8 *
0x180018306  call    ?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z; GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)
0x18001830b  mov     esi, eax
0x18001830d  test    eax, eax
0x18001830f  jz      short loc_18001831A
0x180018311  or      [rbp+0F0h+var_F0], 4
0x180018315  jmp     loc_1800183E6
0x18001831a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018321  lea     rax, WPP_GLOBAL_Control
0x180018328  cmp     rcx, rax
0x18001832b  jz      short loc_180018348
0x18001832d  test    byte ptr [rcx+1Ch], 2
0x180018331  jz      short loc_180018348
0x180018333  mov     rcx, [rcx+10h]
0x180018337  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18001833e  mov     edx, 4Bh ; 'K'
0x180018343  call    WPP_SF_
0x180018348  lea     rdx, [rbp+0F0h+var_B0]
0x18001834c  jmp     short loc_180018350
0x18001834e  xor     edx, edx; struct _GUID *
0x180018350  lea     rax, [rsp+1F0h+var_194]
0x180018355  mov     r9d, 2; unsigned int
0x18001835b  mov     [rsp+1F0h+var_1C8], rax; unsigned int *
0x180018360  xor     r8d, r8d; void *
0x180018363  lea     rax, [rbp+0F0h+var_A0]
0x180018367  mov     rcx, rdi; void *
0x18001836a  mov     [rsp+1F0h+var_1D0], rax; unsigned __int8 *
0x18001836f  call    ?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z; GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)
0x180018374  mov     esi, eax
0x180018376  test    eax, eax
0x180018378  jnz     short loc_1800183E6
0x18001837a  mov     rcx, cs:WPP_GLOBAL_Control
0x180018381  lea     rax, WPP_GLOBAL_Control
0x180018388  cmp     rcx, rax
0x18001838b  jz      short loc_1800183A6
0x18001838d  test    byte ptr [rcx+1Ch], 2
0x180018391  jz      short loc_1800183A6
0x180018393  mov     rcx, [rcx+10h]
0x180018397  lea     edx, [rsi+4Eh]
0x18001839a  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x1800183a1  call    WPP_SF_
0x1800183a6  test    ebx, ebx
0x1800183a8  jz      short loc_1800183BC
0x1800183aa  mov     r9d, 0B11h
0x1800183b0  mov     ebx, 5
0x1800183b5  mov     ecx, ebx
0x1800183b7  jmp     loc_1800184D9
0x1800183bc  test    byte ptr [rbp+0F0h+var_F0], 2
0x1800183c0  jz      short loc_1800183CA
0x1800183c2  mov     r9d, 0B18h
0x1800183c8  jmp     short loc_1800183B0
0x1800183ca  mov     r9d, 2; dwFlags
0x1800183d0  lea     rdx, [rbp+0F0h+var_A0]; pbBuffer
0x1800183d4  xor     ecx, ecx; hAlgorithm
0x1800183d6  lea     r8d, [r9+12h]; cbBuffer
0x1800183da  call    cs:__imp_BCryptGenRandom
0x1800183e1  nop     dword ptr [rax+rax+00h]
0x1800183e6  test    ebx, ebx
0x1800183e8  jz      short loc_180018422
0x1800183ea  movaps  xmm0, xmmword ptr [rbp+0F0h+var_B0.Data1]
0x1800183ee  lea     r8, [rbp+0F0h+var_170]; unsigned __int8 *
0x1800183f2  mov     r9d, 14h; unsigned int
0x1800183f8  mov     dword ptr [rbp+0F0h+var_170], 3
0x1800183ff  lea     rcx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x180018403  movdqu  [rbp+0F0h+var_16C], xmm0
0x180018408  lea     edx, [r9-12h]; unsigned int
0x18001840c  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x180018411  mov     ebx, eax
0x180018413  test    eax, eax
0x180018415  jz      short loc_180018422
0x180018417  mov     r9d, 0B3Bh
0x18001841d  jmp     loc_1800184D7
0x180018422  mov     rax, qword ptr [rsp+1F0h+var_180.Data1]
0x180018427  test    rax, rax
0x18001842a  jz      short loc_18001844B
0x18001842c  lea     rcx, [rbp+0F0h+pbBuffer]
0x180018430  mov     dword ptr [rsp+1F0h+var_1C8], r14d; unsigned int
0x180018435  mov     [rsp+1F0h+var_1D0], rcx; unsigned __int8 *
0x18001843a  mov     r9, r15; struct _GUID *
0x18001843d  mov     rcx, rdi; void *
0x180018440  mov     r8, r12; unsigned __int16 *
0x180018443  mov     rdx, rax; struct _LUID *
0x180018446  call    ?InsertMasterKeyCache@@YAHPEAXPEAU_LUID@@PEBGPEAU_GUID@@PEAEK@Z; InsertMasterKeyCache(void *,_LUID *,ushort const *,_GUID *,uchar *,ulong)
0x18001844b  mov     r9d, [rsp+1F0h+var_190]; unsigned int
0x180018450  lea     rax, [rbp+0F0h+pbBuffer]
0x180018454  mov     r8d, [rsp+1F0h+var_19C]; unsigned int
0x180018459  lea     rcx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x18001845d  mov     dword ptr [rsp+1F0h+var_1B0], r14d; size_t
0x180018462  xor     edx, edx; unsigned int
0x180018464  mov     [rsp+1F0h+var_1B8], rax; unsigned __int8 *
0x180018469  mov     eax, [rsp+1F0h+var_194]
0x18001846d  mov     [rsp+1F0h+var_1C0], eax; unsigned int
0x180018471  lea     rax, [rbp+0F0h+var_A0]
0x180018475  mov     dword ptr [rsp+1F0h+var_1C8], 14h; unsigned int
0x18001847d  mov     [rsp+1F0h+var_1D0], rax; unsigned __int8 *
0x180018482  call    ?EncryptMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKK1K@Z; EncryptMasterKeyToStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,ulong,uchar *,ulong)
0x180018487  mov     ebx, eax
0x180018489  test    eax, eax
0x18001848b  jz      short loc_180018495
0x18001848d  mov     r9d, 0B58h
0x180018493  jmp     short loc_1800184D7
0x180018495  movaps  xmm0, xmmword ptr [rbp+0F0h+var_B0.Data1]
0x180018499  lea     r9, [rdi+50h]; unsigned __int16 *
0x18001849d  lea     r8, [rbp+0F0h+var_A0]; unsigned __int8 *
0x1800184a1  movdqa  xmmword ptr [rsp+1F0h+var_180.Data1], xmm0
0x1800184a7  lea     rdx, [rsp+1F0h+var_180]; struct _GUID
0x1800184ac  lea     rcx, [rbp+0F0h+StringUuid]; StringUuid
0x1800184b0  call    ?LogMasterKeyDescription@@YAJPEBGU_GUID@@PEAEPEAG@Z; LogMasterKeyDescription(ushort const *,_GUID,uchar *,ushort *)
0x1800184b5  mov     r9d, [rsp+1F0h+var_190]; unsigned int
0x1800184ba  lea     rdx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x1800184be  mov     r8d, [rsp+1F0h+var_19C]; unsigned int
0x1800184c3  mov     rcx, rdi; void *
0x1800184c6  call    ?BuildLocalKey@@YAKPEAXPEAUMASTERKEY_STORED@@II@Z; BuildLocalKey(void *,MASTERKEY_STORED *,uint,uint)
0x1800184cb  mov     ebx, eax
0x1800184cd  test    eax, eax
0x1800184cf  jz      short loc_1800184F1
0x1800184d1  mov     r9d, 0B6Dh
0x1800184d7  mov     ecx, eax
0x1800184d9  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800184e0  lea     rdx, aDwlasterror; "dwLastError"
0x1800184e7  call    DebugTraceError
0x1800184ec  jmp     loc_1800185EB
0x1800184f1  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 4
0x1800184f8  mov     [rsp+1F0h+var_1A0], r13d
0x1800184fd  mov     r13d, 1
0x180018503  jz      short loc_180018510
0x180018505  mov     r9, r12
0x180018508  mov     r8, r15
0x18001850b  call    McTemplateU0jz_EtwEventWriteTransfer
0x180018510  lea     rdx, [rsp+1F0h+var_1A0]; int *
0x180018515  lea     rcx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x180018519  call    ?IsBackupMasterKeyRequired@@YAHPEAUMASTERKEY_STORED@@PEAH@Z; IsBackupMasterKeyRequired(MASTERKEY_STORED *,int *)
0x18001851e  test    eax, eax
0x180018520  jz      loc_1800185EB
0x180018526  mov     eax, [rsp+1F0h+var_1A0]
0x18001852a  lea     r8, [rbp+0F0h+pbBuffer]; unsigned __int8 *
0x18001852e  mov     dword ptr [rsp+1F0h+var_1C8], esi; int
0x180018532  lea     rdx, [rbp+0F0h+var_150]; struct MASTERKEY_STORED *
0x180018536  mov     r9d, r14d; unsigned int
0x180018539  mov     dword ptr [rsp+1F0h+var_1D0], eax; int
0x18001853d  mov     rcx, rdi; void *
0x180018540  call    ?BackupMasterKey@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKHH@Z; BackupMasterKey(void *,MASTERKEY_STORED *,uchar *,ulong,int,int)
0x180018545  test    eax, eax
0x180018547  jz      loc_1800185EB
0x18001854d  mov     r15d, [rsp+1F0h+var_198]
0x180018552  test    esi, esi
0x180018554  jz      short loc_180018569
0x180018556  test    r15d, r15d
0x180018559  jz      loc_1800185EB
0x18001855f  cmp     dword ptr [rdi+10h], 0
0x180018563  jnz     loc_1800185EB
0x180018569  mov     ebx, 80090345h
0x18001856e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180018575  mov     ecx, ebx
0x180018577  lea     rdx, aDwlasterror; "dwLastError"
0x18001857e  mov     r9d, 0B9Ah
0x180018584  call    DebugTraceError
0x180018589  mov     eax, cs:dword_18004C260
0x18001858f  xor     r13d, r13d
0x180018592  cmp     eax, 5
0x180018595  jbe     short loc_1800185EB
0x180018597  mov     rdx, 400000000000h
0x1800185a1  lea     rcx, dword_18004C260
0x1800185a8  call    _tlgKeywordOn
  ... truncated ...
```
