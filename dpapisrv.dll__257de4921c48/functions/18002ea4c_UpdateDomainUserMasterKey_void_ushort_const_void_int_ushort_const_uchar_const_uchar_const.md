# UpdateDomainUserMasterKey(void *,ushort const *,void *,int,ushort * const,uchar * const,uchar * const)

- ea: `0x18002ea4c`
- end: `0x18002ef9a`
- name: `?UpdateDomainUserMasterKey@@YAKPEAXPEBG0HQEAGQEAE3@Z`
- size: `1358`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, void *, int, unsigned __int16 *const, unsigned __int8 *const, unsigned __int8 *const)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002e310`

## callees

- `0x180003908`
- `0x1800048a4`
- `0x180005a2c`
- `0x180006c60`
- `0x180007f10`
- `0x18000a7a0`
- `0x18000ab28`
- `0x18000abf0`
- `0x18000b5cc`
- `0x180012258`
- `0x180012da4`
- `0x18001866c`
- `0x18001b234`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x18002a794`
- `0x18002ac04`
- `0x18002ad50`
- `0x18002afc0`
- `0x18002ea4c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ed27`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002ed27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ebc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002edc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002ef51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eb4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002eb4b`

## string_xrefs

- `0x18002ebd7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002ec59`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002edd3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002ee3e`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002ee7c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall UpdateDomainUserMasterKey(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        void *a3,
        int a4,
        unsigned __int16 *const a5,
        unsigned __int8 *const a6,
        unsigned __int8 *const a7)
{
  unsigned __int16 *v10; // rsi
  unsigned int v11; // ebx
  unsigned int v12; // r15d
  __int64 v13; // rax
  HLOCAL v14; // rax
  void *v15; // rcx
  __int64 v16; // r14
  unsigned int v17; // ebx
  int v18; // eax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  DWORD LastError; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // r9
  DWORD v29; // eax
  unsigned int v30; // eax
  _BYTE *v31; // rax
  __int64 v32; // rcx
  UCHAR *v33; // rax
  size_t v35; // [rsp+40h] [rbp-C0h]
  size_t v36; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v37; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v38; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL v40; // [rsp+78h] [rbp-88h] BYREF
  int v41; // [rsp+80h] [rbp-80h] BYREF
  size_t Size; // [rsp+88h] [rbp-78h] BYREF
  struct _GUID v43; // [rsp+90h] [rbp-70h] BYREF
  void *Src; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v45; // [rsp+A8h] [rbp-58h]
  unsigned __int8 *v46; // [rsp+B0h] [rbp-50h]
  _BYTE v47[8]; // [rsp+C0h] [rbp-40h] BYREF
  HLOCAL hMem; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 StringUuid[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int128 v51; // [rsp+F0h] [rbp-10h]
  __int128 v52; // [rsp+100h] [rbp+0h]
  __int128 v53; // [rsp+110h] [rbp+10h]
  unsigned int v54; // [rsp+120h] [rbp+20h]
  struct _GUID v55; // [rsp+160h] [rbp+60h] BYREF
  UCHAR v56[24]; // [rsp+170h] [rbp+70h] BYREF

  v46 = a6;
  *(_QWORD *)&v43.Data1 = a3;
  Src = a2;
  v45 = a7;
  memset_0(v47, 0, 0xA0u);
  v38 = 0;
  v10 = 0;
  v39 = 0;
  v40 = 0;
  v36 = 0;
  v41 = 0;
  v37 = 0;
  v55 = 0;
  if ( a1 )
  {
    v11 = *((_DWORD *)a1 + 13);
    v12 = *((_DWORD *)a1 + 14);
  }
  else
  {
    v11 = 26128;
    v12 = 32782;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 99, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, a5);
  v13 = -1;
  do
    ++v13;
  while ( a2[v13] );
  Size = (unsigned int)(2 * v13 + 2);
  v14 = LocalAlloc(0, (unsigned int)Size);
  hMem = v14;
  v16 = 20;
  if ( !v14 )
  {
    v17 = 1130;
    v18 = 0;
LABEL_39:
    if ( a4 && v18 )
      DeleteMasterKey(v15, v10, StringUuid);
    goto LABEL_42;
  }
  memcpy_0(v14, Src, Size);
  v19 = *((_OWORD *)a5 + 1);
  *(_OWORD *)StringUuid = *(_OWORD *)a5;
  v20 = *((_OWORD *)a5 + 2);
  v50 = v19;
  v21 = *((_OWORD *)a5 + 3);
  v51 = v20;
  v22 = *((_OWORD *)a5 + 4);
  v52 = v21;
  v53 = v22;
  if ( !(unsigned int)ReadMasterKey(a1, (struct MASTERKEY_STORED *)v47) )
  {
    LastError = GetLastError();
    DebugTraceError(
      LastError,
      "GetLastError()",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
      3927);
    v17 = -2146893821;
LABEL_13:
    v18 = 0;
    goto LABEL_39;
  }
  GetReEncryptAlgorithms((struct MASTERKEY_STORED *)v47, v11, v12, &v37, (unsigned int *)&v36 + 1);
  if ( !(unsigned int)ComputeMasterKeyUserEncryptionKey(a1, *(void **)&v43.Data1, (v54 >> 2) & 1, v46, v45, v56) )
  {
    v17 = 87;
    v24 = 3951;
    v25 = 87;
LABEL_16:
    DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v24);
    goto LABEL_13;
  }
  v43 = v55;
  v26 = DecryptMasterKeyFromStorage(
          (struct MASTERKEY_STORED *)v47,
          0,
          v11,
          v12,
          v56,
          0x14u,
          (int *)&Size,
          (unsigned __int8 **)&v40,
          (unsigned int *)&v36,
          &v43,
          a1);
  v17 = v26;
  if ( v26 )
  {
    v24 = 3978;
    v25 = v26;
    goto LABEL_16;
  }
  if ( !a4 )
  {
LABEL_27:
    if ( (unsigned int)GetMasterKeyUserEncryptionKey(a1, &v55, 0, 2u, v56, &v38) )
    {
      LODWORD(v35) = v36;
      v30 = EncryptMasterKeyToStorage(
              (struct MASTERKEY_STORED *)v47,
              0,
              v37,
              HIDWORD(v36),
              v56,
              0x14u,
              v38,
              (unsigned __int8 *)v40,
              v35);
      v17 = v30;
      if ( !v30 )
      {
        if ( !a4 || (v27 = BuildLocalKey(a1, (struct MASTERKEY_STORED *)v47, v37, HIDWORD(v36)), (v17 = v27) == 0) )
        {
          v43 = v55;
          LogMasterKeyDescription(StringUuid, &v43, v56, a1 + 40);
          if ( (unsigned int)IsBackupMasterKeyRequired((struct MASTERKEY_STORED *)v47, &v39) )
            BackupMasterKey(a1, (struct MASTERKEY_STORED *)v47, (unsigned __int8 *)v40, v36, v39, 0);
          v17 = 0;
          v18 = WriteMasterKey(a1, (struct MASTERKEY_STORED *)v47);
          goto LABEL_39;
        }
        v28 = 4084;
LABEL_35:
        DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v28);
        goto LABEL_42;
      }
      DebugTraceError(v30, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4075);
    }
    else
    {
      v29 = GetLastError();
      DebugTraceError(v29, "GetLastError()", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 4049);
      v17 = -2146893821;
    }
    v18 = 0;
    goto LABEL_39;
  }
  v54 = 0;
  InitializeMasterKeyPolicy(a1, (struct MASTERKEY_STORED *)v47, &v41);
  v10 = (unsigned __int16 *)hMem;
  hMem = 0;
  v27 = CPSGetUserStorageArea(a1, 0, 1u, 1, (unsigned __int16 **)&hMem);
  v17 = v27;
  if ( v27 )
  {
    v28 = 4006;
    goto LABEL_35;
  }
  if ( (unsigned int)_o__wcsicmp(v10, hMem) )
  {
    PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v47, 3u, 0, 0);
    PersistMasterKeyToStorage((struct MASTERKEY_STORED *)v47, 2u, 0, 0);
    goto LABEL_27;
  }
  v17 = 87;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 102, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
LABEL_42:
  CloseMasterKey(a1, (struct MASTERKEY_STORED *)v47, 0);
  if ( v10 )
    LocalFree(v10);
  v31 = v40;
  if ( v40 )
  {
    v32 = (unsigned int)v36;
    if ( (_DWORD)v36 )
    {
      do
      {
        *v31++ = 0;
        --v32;
      }
      while ( v32 );
    }
    LocalFree(v40);
  }
  v33 = v56;
  do
  {
    *v33++ = 0;
    --v16;
  }
  while ( v16 );
  return v17;
}

```

## disassembly

```asm
0x18002ea4c  mov     [rsp-8+arg_18], rbx
0x18002ea51  push    rbp
0x18002ea52  push    rsi
0x18002ea53  push    rdi
0x18002ea54  push    r12
0x18002ea56  push    r13
0x18002ea58  push    r14
0x18002ea5a  push    r15
0x18002ea5c  lea     rbp, [rsp-90h]
0x18002ea64  sub     rsp, 190h
0x18002ea6b  mov     rax, cs:__security_cookie
0x18002ea72  xor     rax, rsp
0x18002ea75  mov     [rbp+0C0h+var_38], rax
0x18002ea7c  mov     rax, [rbp+0C0h+arg_28]
0x18002ea83  mov     r14, rdx
0x18002ea86  mov     r13, [rbp+0C0h+arg_20]
0x18002ea8d  mov     rdi, rcx
0x18002ea90  mov     [rbp+0C0h+var_110], rax
0x18002ea94  lea     rcx, [rbp+0C0h+var_100]; void *
0x18002ea98  mov     rax, [rbp+0C0h+arg_30]
0x18002ea9f  mov     r12d, r9d
0x18002eaa2  mov     qword ptr [rbp+0C0h+var_130.Data1], r8
0x18002eaa6  mov     r8d, 0A0h; Size
0x18002eaac  mov     [rbp+0C0h+Src], rdx
0x18002eab0  xor     edx, edx; Val
0x18002eab2  mov     [rbp+0C0h+var_118], rax
0x18002eab6  call    memset_0
0x18002eabb  xor     edx, edx
0x18002eabd  xorps   xmm0, xmm0
0x18002eac0  mov     [rsp+1C0h+var_150], edx
0x18002eac4  mov     esi, edx
0x18002eac6  mov     [rsp+1C0h+var_14C], edx
0x18002eaca  mov     [rsp+1C0h+var_148], rdx
0x18002eacf  mov     dword ptr [rsp+1C0h+var_15C], edx
0x18002ead3  mov     [rbp+0C0h+var_140], edx
0x18002ead6  mov     [rsp+1C0h+var_154], edx
0x18002eada  mov     dword ptr [rsp+1C0h+var_15C+4], edx
0x18002eade  movups  xmmword ptr [rbp+0C0h+var_60.Data1], xmm0
0x18002eae2  test    rdi, rdi
0x18002eae5  jz      short loc_18002EAF0
0x18002eae7  mov     ebx, [rdi+34h]
0x18002eaea  mov     r15d, [rdi+38h]
0x18002eaee  jmp     short loc_18002EAFB
0x18002eaf0  mov     ebx, 6610h
0x18002eaf5  mov     r15d, 800Eh
0x18002eafb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb02  lea     rax, WPP_GLOBAL_Control
0x18002eb09  cmp     rcx, rax
0x18002eb0c  jz      short loc_18002EB2E
0x18002eb0e  test    byte ptr [rcx+1Ch], 4
0x18002eb12  jz      short loc_18002EB2E
0x18002eb14  mov     rcx, [rcx+10h]
0x18002eb18  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002eb1f  mov     edx, 63h ; 'c'
0x18002eb24  mov     r9, r13
0x18002eb27  call    WPP_SF_S
0x18002eb2c  xor     edx, edx
0x18002eb2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002eb32  inc     rax
0x18002eb35  cmp     [r14+rax*2], dx
0x18002eb3a  jnz     short loc_18002EB32
0x18002eb3c  lea     eax, ds:2[rax*2]
0x18002eb43  xor     ecx, ecx; uFlags
0x18002eb45  mov     edx, eax; uBytes
0x18002eb47  mov     [rbp+0C0h+Size], rax
0x18002eb4b  call    cs:__imp_LocalAlloc
0x18002eb52  nop     dword ptr [rax+rax+00h]
0x18002eb57  mov     [rbp+0C0h+hMem], rax
0x18002eb5b  mov     r14d, 14h
0x18002eb61  test    rax, rax
0x18002eb64  jnz     short loc_18002EB75
0x18002eb66  mov     ebx, 46Ah
0x18002eb6b  mov     eax, esi
0x18002eb6d  xor     r13d, r13d
0x18002eb70  jmp     loc_18002EEF5
0x18002eb75  mov     r8, [rbp+0C0h+Size]; Size
0x18002eb79  mov     rcx, rax; void *
0x18002eb7c  mov     rdx, [rbp+0C0h+Src]; Src
0x18002eb80  call    memcpy_0
0x18002eb85  movups  xmm0, xmmword ptr [r13+0]
0x18002eb8a  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002eb8e  mov     rcx, rdi; void *
0x18002eb91  movups  xmm1, xmmword ptr [r13+10h]
0x18002eb96  movaps  xmmword ptr [rbp+0C0h+StringUuid], xmm0
0x18002eb9a  movups  xmm0, xmmword ptr [r13+20h]
0x18002eb9f  movaps  [rbp+0C0h+var_E0], xmm1
0x18002eba3  movups  xmm1, xmmword ptr [r13+30h]
0x18002eba8  movaps  [rbp+0C0h+var_D0], xmm0
0x18002ebac  movups  xmm0, xmmword ptr [r13+40h]
0x18002ebb1  movaps  [rbp+0C0h+var_C0], xmm1
0x18002ebb5  movaps  [rbp+0C0h+var_B0], xmm0
0x18002ebb9  call    ?ReadMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z; ReadMasterKey(void *,MASTERKEY_STORED *)
0x18002ebbe  xor     r13d, r13d
0x18002ebc1  test    eax, eax
0x18002ebc3  jnz     short loc_18002EBF8
0x18002ebc5  call    cs:__imp_GetLastError
0x18002ebcc  nop     dword ptr [rax+rax+00h]
0x18002ebd1  mov     r9d, 0F57h
0x18002ebd7  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ebde  mov     ecx, eax
0x18002ebe0  lea     rdx, aGetlasterror; "GetLastError()"
0x18002ebe7  call    DebugTraceError
0x18002ebec  mov     ebx, 80090003h
0x18002ebf1  mov     eax, esi
0x18002ebf3  jmp     loc_18002EEF5
0x18002ebf8  lea     rax, [rsp+1C0h+var_15C+4]
0x18002ebfd  mov     r8d, r15d; unsigned int
0x18002ec00  lea     r9, [rsp+1C0h+var_154]; unsigned int *
0x18002ec05  mov     [rsp+1C0h+var_1A0], rax; unsigned int *
0x18002ec0a  mov     edx, ebx; unsigned int
0x18002ec0c  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ec10  call    ?GetReEncryptAlgorithms@@YAXPEAUMASTERKEY_STORED@@IIPEAI1@Z; GetReEncryptAlgorithms(MASTERKEY_STORED *,uint,uint,uint *,uint *)
0x18002ec15  mov     r8d, [rbp+0C0h+var_A0]
0x18002ec19  lea     rax, [rbp+0C0h+var_50]
0x18002ec1d  mov     r9, [rbp+0C0h+var_110]; unsigned __int8 *
0x18002ec21  mov     rcx, rdi; void *
0x18002ec24  mov     rdx, qword ptr [rbp+0C0h+var_130.Data1]; void *
0x18002ec28  mov     [rsp+1C0h+var_198], rax; PUCHAR
0x18002ec2d  mov     rax, [rbp+0C0h+var_118]
0x18002ec31  shr     r8d, 2
0x18002ec35  and     r8d, 1; unsigned int
0x18002ec39  mov     [rsp+1C0h+var_1A0], rax; Src
0x18002ec3e  call    ?ComputeMasterKeyUserEncryptionKey@@YAHPEAX0KQEAE11@Z; ComputeMasterKeyUserEncryptionKey(void *,void *,ulong,uchar * const,uchar * const,uchar * const)
0x18002ec43  test    eax, eax
0x18002ec45  jnz     short loc_18002EC67
0x18002ec47  lea     ebx, [rax+57h]
0x18002ec4a  mov     r9d, 0F6Fh
0x18002ec50  mov     ecx, ebx
0x18002ec52  lea     rdx, aStatus; "Status"
0x18002ec59  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ec60  call    DebugTraceError
0x18002ec65  jmp     short loc_18002EBF1
0x18002ec67  movaps  xmm0, xmmword ptr [rbp+0C0h+var_60.Data1]
0x18002ec6b  lea     rax, [rbp+0C0h+var_130]
0x18002ec6f  mov     [rsp+1C0h+var_170], rdi; void *
0x18002ec74  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ec78  mov     [rsp+1C0h+var_178], rax; struct _GUID
0x18002ec7d  mov     r9d, r15d; unsigned int
0x18002ec80  lea     rax, [rsp+1C0h+var_15C]
0x18002ec85  movdqa  xmmword ptr [rbp+0C0h+var_130.Data1], xmm0
0x18002ec8a  mov     [rsp+1C0h+var_180], rax; unsigned int *
0x18002ec8f  mov     r8d, ebx; unsigned int
0x18002ec92  lea     rax, [rsp+1C0h+var_148]
0x18002ec97  xor     edx, edx; unsigned int
0x18002ec99  mov     [rsp+1C0h+var_188], rax; unsigned __int8 **
0x18002ec9e  lea     rax, [rbp+0C0h+Size]
0x18002eca2  mov     [rsp+1C0h+var_190], rax; int *
0x18002eca7  lea     rax, [rbp+0C0h+var_50]
0x18002ecab  mov     dword ptr [rsp+1C0h+var_198], r14d; unsigned int
0x18002ecb0  mov     [rsp+1C0h+var_1A0], rax; unsigned __int8 *
0x18002ecb5  call    ?DecryptMasterKeyFromStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKPEAHPEAPEAEPEAKU_GUID@@PEAX@Z; DecryptMasterKeyFromStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,int *,uchar * *,ulong *,_GUID,void *)
0x18002ecba  mov     ebx, eax
0x18002ecbc  test    eax, eax
0x18002ecbe  jz      short loc_18002ECCA
0x18002ecc0  mov     r9d, 0F8Ah
0x18002ecc6  mov     ecx, eax
0x18002ecc8  jmp     short loc_18002EC52
0x18002ecca  mov     r15d, 2
0x18002ecd0  test    r12d, r12d
0x18002ecd3  jz      loc_18002ED98
0x18002ecd9  lea     r8, [rbp+0C0h+var_140]; int *
0x18002ecdd  mov     [rbp+0C0h+var_A0], r13d
0x18002ece1  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ece5  mov     rcx, rdi; void *
0x18002ece8  call    ?InitializeMasterKeyPolicy@@YAHPEAXPEAUMASTERKEY_STORED@@PEAH@Z; InitializeMasterKeyPolicy(void *,MASTERKEY_STORED *,int *)
0x18002eced  mov     rsi, [rbp+0C0h+hMem]
0x18002ecf1  lea     r9d, [r15-1]; int
0x18002ecf5  lea     rax, [rbp+0C0h+hMem]
0x18002ecf9  mov     [rbp+0C0h+hMem], r13
0x18002ecfd  mov     r8d, r9d; int
0x18002ed00  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 **
0x18002ed05  xor     edx, edx; void *
0x18002ed07  mov     rcx, rdi; void *
0x18002ed0a  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x18002ed0f  mov     ebx, eax
0x18002ed11  test    eax, eax
0x18002ed13  jz      short loc_18002ED20
0x18002ed15  mov     r9d, 0FA6h
0x18002ed1b  jmp     loc_18002EE7C
0x18002ed20  mov     rdx, [rbp+0C0h+hMem]
0x18002ed24  mov     rcx, rsi
0x18002ed27  call    cs:__imp__o__wcsicmp
0x18002ed2e  nop     dword ptr [rax+rax+00h]
0x18002ed33  test    eax, eax
0x18002ed35  jnz     short loc_18002ED73
0x18002ed37  lea     ebx, [rax+57h]
0x18002ed3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed41  lea     rax, WPP_GLOBAL_Control
0x18002ed48  cmp     rcx, rax
0x18002ed4b  jz      loc_18002EF0A
0x18002ed51  test    [rcx+1Ch], r15b
0x18002ed55  jz      loc_18002EF0A
0x18002ed5b  mov     rcx, [rcx+10h]
0x18002ed5f  lea     edx, [rbx+0Fh]
0x18002ed62  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002ed69  call    WPP_SF_
0x18002ed6e  jmp     loc_18002EF0A
0x18002ed73  xor     r9d, r9d; unsigned int
0x18002ed76  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ed7a  xor     r8d, r8d; unsigned __int8 *
0x18002ed7d  lea     edx, [r9+3]; unsigned int
0x18002ed81  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002ed86  xor     r9d, r9d; unsigned int
0x18002ed89  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ed8d  xor     r8d, r8d; unsigned __int8 *
0x18002ed90  mov     edx, r15d; unsigned int
0x18002ed93  call    ?PersistMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KPEAEK@Z; PersistMasterKeyToStorage(MASTERKEY_STORED *,ulong,uchar *,ulong)
0x18002ed98  lea     rax, [rsp+1C0h+var_150]
0x18002ed9d  mov     r9d, r15d; unsigned int
0x18002eda0  mov     [rsp+1C0h+var_198], rax; unsigned int *
0x18002eda5  lea     rdx, [rbp+0C0h+var_60]; struct _GUID *
0x18002eda9  lea     rax, [rbp+0C0h+var_50]
0x18002edad  xor     r8d, r8d; void *
0x18002edb0  mov     rcx, rdi; void *
0x18002edb3  mov     [rsp+1C0h+var_1A0], rax; unsigned __int8 *
0x18002edb8  call    ?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z; GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)
0x18002edbd  test    eax, eax
0x18002edbf  jnz     short loc_18002EDF5
0x18002edc1  call    cs:__imp_GetLastError
0x18002edc8  nop     dword ptr [rax+rax+00h]
0x18002edcd  mov     r9d, 0FD1h
0x18002edd3  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002edda  mov     ecx, eax
0x18002eddc  lea     rdx, aGetlasterror; "GetLastError()"
0x18002ede3  call    DebugTraceError
0x18002ede8  mov     ebx, 80090003h
0x18002eded  mov     eax, r13d
0x18002edf0  jmp     loc_18002EEF5
0x18002edf5  mov     eax, dword ptr [rsp+1C0h+var_15C]
0x18002edf9  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002edfd  mov     r9d, dword ptr [rsp+1C0h+var_15C+4]; unsigned int
0x18002ee02  xor     edx, edx; unsigned int
0x18002ee04  mov     r8d, [rsp+1C0h+var_154]; unsigned int
0x18002ee09  mov     dword ptr [rsp+1C0h+var_180], eax; size_t
0x18002ee0d  mov     rax, [rsp+1C0h+var_148]
0x18002ee12  mov     [rsp+1C0h+var_188], rax; unsigned __int8 *
0x18002ee17  mov     eax, [rsp+1C0h+var_150]
0x18002ee1b  mov     dword ptr [rsp+1C0h+var_190], eax; unsigned int
0x18002ee1f  lea     rax, [rbp+0C0h+var_50]
0x18002ee23  mov     dword ptr [rsp+1C0h+var_198], r14d; unsigned int
0x18002ee28  mov     [rsp+1C0h+var_1A0], rax; unsigned __int8 *
0x18002ee2d  call    ?EncryptMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKK1K@Z; EncryptMasterKeyToStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,ulong,uchar *,ulong)
0x18002ee32  mov     ebx, eax
0x18002ee34  test    eax, eax
0x18002ee36  jz      short loc_18002EE55
0x18002ee38  mov     r9d, 0FEBh
0x18002ee3e  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ee45  lea     rdx, aStatus; "Status"
0x18002ee4c  mov     ecx, eax
0x18002ee4e  call    DebugTraceError
0x18002ee53  jmp     short loc_18002EDED
0x18002ee55  test    r12d, r12d
0x18002ee58  jz      short loc_18002EE93
0x18002ee5a  mov     r9d, dword ptr [rsp+1C0h+var_15C+4]; unsigned int
0x18002ee5f  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002ee63  mov     r8d, [rsp+1C0h+var_154]; unsigned int
0x18002ee68  mov     rcx, rdi; void *
0x18002ee6b  call    ?BuildLocalKey@@YAKPEAXPEAUMASTERKEY_STORED@@II@Z; BuildLocalKey(void *,MASTERKEY_STORED *,uint,uint)
0x18002ee70  mov     ebx, eax
0x18002ee72  test    eax, eax
0x18002ee74  jz      short loc_18002EE93
0x18002ee76  mov     r9d, 0FF4h
0x18002ee7c  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002ee83  mov     ecx, eax
0x18002ee85  lea     rdx, aStatus; "Status"
0x18002ee8c  call    DebugTraceError
0x18002ee91  jmp     short loc_18002EF0A
0x18002ee93  movaps  xmm0, xmmword ptr [rbp+0C0h+var_60.Data1]
0x18002ee97  lea     r9, [rdi+50h]; unsigned __int16 *
0x18002ee9b  lea     r8, [rbp+0C0h+var_50]; unsigned __int8 *
0x18002ee9f  movdqa  xmmword ptr [rbp+0C0h+var_130.Data1], xmm0
0x18002eea4  lea     rdx, [rbp+0C0h+var_130]; struct _GUID
0x18002eea8  lea     rcx, [rbp+0C0h+StringUuid]; StringUuid
0x18002eeac  call    ?LogMasterKeyDescription@@YAJPEBGU_GUID@@PEAEPEAG@Z; LogMasterKeyDescription(ushort const *,_GUID,uchar *,ushort *)
0x18002eeb1  lea     rdx, [rsp+1C0h+var_14C]; int *
0x18002eeb6  lea     rcx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002eeba  call    ?IsBackupMasterKeyRequired@@YAHPEAUMASTERKEY_STORED@@PEAH@Z; IsBackupMasterKeyRequired(MASTERKEY_STORED *,int *)
0x18002eebf  test    eax, eax
0x18002eec1  jz      short loc_18002EEE6
0x18002eec3  mov     eax, [rsp+1C0h+var_14C]
0x18002eec7  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002eecb  mov     r9d, dword ptr [rsp+1C0h+var_15C]; unsigned int
0x18002eed0  mov     rcx, rdi; void *
0x18002eed3  mov     r8, [rsp+1C0h+var_148]; unsigned __int8 *
0x18002eed8  mov     dword ptr [rsp+1C0h+var_198], r13d; int
0x18002eedd  mov     dword ptr [rsp+1C0h+var_1A0], eax; int
0x18002eee1  call    ?BackupMasterKey@@YAKPEAXPEAUMASTERKEY_STORED@@PEAEKHH@Z; BackupMasterKey(void *,MASTERKEY_STORED *,uchar *,ulong,int,int)
0x18002eee6  mov     ebx, r13d
0x18002eee9  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
0x18002eeed  mov     rcx, rdi; void *
0x18002eef0  call    ?WriteMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z; WriteMasterKey(void *,MASTERKEY_STORED *)
0x18002eef5  test    r12d, r12d
0x18002eef8  jz      short loc_18002EF0A
0x18002eefa  test    eax, eax
0x18002eefc  jz      short loc_18002EF0A
0x18002eefe  lea     r8, [rbp+0C0h+StringUuid]; unsigned __int16 *
0x18002ef02  mov     rdx, rsi; unsigned __int16 *
0x18002ef05  call    ?DeleteMasterKey@@YAHPEAXPEBG1@Z; DeleteMasterKey(void *,ushort const *,ushort const *)
0x18002ef0a  xor     r8d, r8d; int
0x18002ef0d  lea     rdx, [rbp+0C0h+var_100]; struct MASTERKEY_STORED *
  ... truncated ...
```
