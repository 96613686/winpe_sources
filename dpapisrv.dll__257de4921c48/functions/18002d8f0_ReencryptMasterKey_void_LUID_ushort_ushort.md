# ReencryptMasterKey(void *,_LUID *,ushort *,ushort *)

- ea: `0x18002d8f0`
- end: `0x18002dd63`
- name: `?ReencryptMasterKey@@YAKPEAXPEAU_LUID@@PEAG2@Z`
- size: `1139`
- prototype: `__int64 __fastcall(void *, struct _LUID *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18002e310`

## callees

- `0x1800048a4`
- `0x180005a2c`
- `0x180007f10`
- `0x18000bc70`
- `0x180012258`
- `0x180013f2c`
- `0x18001866c`
- `0x18001b234`
- `0x18001c340`
- `0x18001c9c0`
- `0x18001d810`
- `0x18001e1b4`
- `0x1800244b8`
- `0x18002a57c`
- `0x18002a624`
- `0x18002d8f0`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18002daff`
- `RPCRT4!UuidFromStringW` at `0x18002daff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002daae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da14`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002da14`

## string_xrefs

- `0x18002da34`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002db26`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x18002dc3b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
__int64 __fastcall ReencryptMasterKey(void *a1, struct _LUID *a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  unsigned int v7; // r12d
  unsigned int v8; // r13d
  __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  SIZE_T v13; // r15
  HLOCAL v14; // rax
  unsigned int v15; // ebx
  DWORD LastError; // eax
  unsigned int v17; // eax
  unsigned __int8 *v18; // rax
  size_t v20; // [rsp+40h] [rbp-C0h]
  size_t v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v22; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v25[4]; // [rsp+90h] [rbp-70h] BYREF
  int v26; // [rsp+94h] [rbp-6Ch]
  HLOCAL v27; // [rsp+98h] [rbp-68h]
  unsigned __int16 StringUuid[40]; // [rsp+A0h] [rbp-60h] BYREF
  int v29; // [rsp+F0h] [rbp-10h]
  struct _GUID v30; // [rsp+130h] [rbp+30h] BYREF
  UUID Uuid; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int8 v32[24]; // [rsp+150h] [rbp+50h] BYREF

  *(_QWORD *)&v23.Data1 = a2;
  memset_0(v25, 0, 0xA0u);
  v22 = 0;
  v21 = 0;
  Uuid = 0;
  v30 = 0;
  if ( a1 )
  {
    v7 = *((_DWORD *)a1 + 13);
    v8 = *((_DWORD *)a1 + 14);
  }
  else
  {
    v7 = 26128;
    v8 = 32782;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_SS(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      15,
      (unsigned int)WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
      (_DWORD)a3,
      (__int64)a4);
  v9 = 20;
  if ( !a3 )
    goto LABEL_44;
  if ( !a4 )
    goto LABEL_44;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a4[v11] );
  if ( (unsigned __int64)(2 * v11 + 2) > 0x50 )
  {
LABEL_44:
    v15 = 87;
    goto LABEL_45;
  }
  memset_0(v25, 0, 0xA0u);
  v26 = 1;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v13 = (unsigned int)(2 * v12 + 2);
  v14 = LocalAlloc(0, v13);
  v27 = v14;
  if ( v14 )
  {
    memcpy_0(v14, a3, v13);
    do
      ++v10;
    while ( a4[v10] );
    memcpy_0(StringUuid, a4, 2 * v10 + 2);
    if ( !(unsigned int)ReadMasterKey(a1, (struct MASTERKEY_STORED *)v25) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids, LastError);
      }
LABEL_22:
      CloseMasterKey(a1, (struct MASTERKEY_STORED *)v25, 0);
      v15 = 1168;
LABEL_23:
      v9 = 20;
      goto LABEL_45;
    }
    v15 = UuidFromStringW(StringUuid, &Uuid);
    if ( v15 )
    {
      CloseMasterKey(a1, (struct MASTERKEY_STORED *)v25, 0);
      DebugTraceError(v15, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 842);
      goto LABEL_23;
    }
    v22 = 0;
    if ( !(unsigned int)SearchMasterKeyCache(*(struct _LUID **)&v23.Data1, a3, &Uuid, &v22, (unsigned int *)&v21) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_S(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          17,
          WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids,
          StringUuid);
      goto LABEL_22;
    }
    ScopedSecureSSFree::ScopedSecureSSFree((ScopedSecureSSFree *)v24, &v22, (unsigned int *)&v21);
    v30 = 0;
    if ( (unsigned int)GetMasterKeyUserEncryptionKey(a1, &v30, 0, 3u, v32, (unsigned int *)&v21 + 1) )
    {
      v29 |= 4u;
      LODWORD(v20) = v21;
      v17 = EncryptMasterKeyToStorage((struct MASTERKEY_STORED *)v25, 0, v7, v8, v32, 0x14u, HIDWORD(v21), v22, v20);
      v15 = v17;
      if ( v17 )
      {
        DebugTraceError(v17, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 907);
        CloseMasterKey(a1, (struct MASTERKEY_STORED *)v25, 0);
LABEL_43:
        ScopedSecureSSFree::~ScopedSecureSSFree((ScopedSecureSSFree *)v24);
        goto LABEL_23;
      }
      v23 = v30;
      LogMasterKeyDescription(StringUuid, &v23, v32, (unsigned __int16 *)a1 + 40);
      if ( CloseMasterKey(a1, (struct MASTERKEY_STORED *)v25, 1) )
      {
        ScopedSecureSSFree::~ScopedSecureSSFree((ScopedSecureSSFree *)v24);
        v15 = 0;
        goto LABEL_23;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids);
      CloseMasterKey(a1, (struct MASTERKEY_STORED *)v25, 0);
    }
    v15 = 1168;
    goto LABEL_43;
  }
  v15 = 1130;
  DebugTraceError(1130, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", 813);
  v9 = 20;
LABEL_45:
  v18 = v32;
  do
  {
    *v18++ = 0;
    --v9;
  }
  while ( v9 );
  return v15;
}

```

## disassembly

```asm
0x18002d8f0  push    rbp
0x18002d8f2  push    rbx
0x18002d8f3  push    rsi
0x18002d8f4  push    rdi
0x18002d8f5  push    r12
0x18002d8f7  push    r13
0x18002d8f9  push    r14
0x18002d8fb  push    r15
0x18002d8fd  lea     rbp, [rsp-78h]
0x18002d902  sub     rsp, 178h
0x18002d909  mov     rax, cs:__security_cookie
0x18002d910  xor     rax, rsp
0x18002d913  mov     [rbp+0B0h+var_48], rax
0x18002d917  mov     rsi, r9
0x18002d91a  mov     r14, r8
0x18002d91d  mov     qword ptr [rsp+1B0h+var_150.Data1], rdx
0x18002d922  mov     rdi, rcx
0x18002d925  xor     edx, edx; Val
0x18002d927  mov     r8d, 0A0h; Size
0x18002d92d  lea     rcx, [rbp+0B0h+var_120]; void *
0x18002d931  call    memset_0
0x18002d936  xor     r15d, r15d
0x18002d939  mov     [rsp+1B0h+var_158], r15
0x18002d93e  mov     dword ptr [rsp+1B0h+var_160], r15d
0x18002d943  xorps   xmm0, xmm0
0x18002d946  movups  xmmword ptr [rbp+0B0h+Uuid.Data1], xmm0
0x18002d94a  mov     dword ptr [rsp+1B0h+var_160+4], r15d
0x18002d94f  xorps   xmm1, xmm1
0x18002d952  movups  xmmword ptr [rbp+0B0h+var_80.Data1], xmm1
0x18002d956  test    rdi, rdi
0x18002d959  jz      short loc_18002D965
0x18002d95b  mov     r12d, [rdi+34h]
0x18002d95f  mov     r13d, [rdi+38h]
0x18002d963  jmp     short loc_18002D971
0x18002d965  mov     r12d, 6610h
0x18002d96b  mov     r13d, 800Eh
0x18002d971  lea     rax, WPP_GLOBAL_Control
0x18002d978  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d97f  cmp     rcx, rax
0x18002d982  jz      short loc_18002D9A7
0x18002d984  test    byte ptr [rcx+1Ch], 4
0x18002d988  jz      short loc_18002D9A7
0x18002d98a  mov     edx, 0Fh
0x18002d98f  mov     [rsp+1B0h+var_190], rsi
0x18002d994  mov     r9, r14
0x18002d997  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002d99e  mov     rcx, [rcx+10h]
0x18002d9a2  call    WPP_SF_SS
0x18002d9a7  mov     ecx, 14h
0x18002d9ac  test    r14, r14
0x18002d9af  jz      loc_18002DD2B
0x18002d9b5  test    rsi, rsi
0x18002d9b8  jz      loc_18002DD2B
0x18002d9be  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d9c2  mov     rax, rbx
0x18002d9c5  inc     rax
0x18002d9c8  cmp     [rsi+rax*2], r15w
0x18002d9cd  jnz     short loc_18002D9C5
0x18002d9cf  lea     rax, ds:2[rax*2]
0x18002d9d7  cmp     rax, 50h ; 'P'
0x18002d9db  ja      loc_18002DD2B
0x18002d9e1  xor     edx, edx; Val
0x18002d9e3  mov     r8d, 0A0h; Size
0x18002d9e9  lea     rcx, [rbp+0B0h+var_120]; void *
0x18002d9ed  call    memset_0
0x18002d9f2  mov     [rbp+0B0h+var_11C], 1
0x18002d9f9  mov     rax, rbx
0x18002d9fc  inc     rax
0x18002d9ff  cmp     [r14+rax*2], r15w
0x18002da04  jnz     short loc_18002D9FC
0x18002da06  lea     eax, ds:2[rax*2]
0x18002da0d  mov     r15d, eax
0x18002da10  mov     edx, eax; uBytes
0x18002da12  xor     ecx, ecx; uFlags
0x18002da14  call    cs:__imp_LocalAlloc
0x18002da1b  nop     dword ptr [rax+rax+00h]
0x18002da20  mov     [rbp+0B0h+var_118], rax
0x18002da24  test    rax, rax
0x18002da27  jnz     short loc_18002DA56
0x18002da29  mov     ebx, 46Ah
0x18002da2e  mov     r9d, 32Dh
0x18002da34  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002da3b  lea     rdx, aDwlasterror; "dwLastError"
0x18002da42  mov     ecx, ebx
0x18002da44  call    DebugTraceError
0x18002da49  mov     ecx, 14h
0x18002da4e  xor     r15d, r15d
0x18002da51  jmp     loc_18002DD30
0x18002da56  mov     r8, r15; Size
0x18002da59  mov     rdx, r14; Src
0x18002da5c  mov     rcx, rax; void *
0x18002da5f  call    memcpy_0
0x18002da64  xor     r15d, r15d
0x18002da67  inc     rbx
0x18002da6a  cmp     [rsi+rbx*2], r15w
0x18002da6f  jnz     short loc_18002DA67
0x18002da71  lea     r8, ds:2[rbx*2]; Size
0x18002da79  mov     rdx, rsi; Src
0x18002da7c  lea     rcx, [rbp+0B0h+StringUuid]; void *
0x18002da80  call    memcpy_0
0x18002da85  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002da89  mov     rcx, rdi; void *
0x18002da8c  call    ?ReadMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@@Z; ReadMasterKey(void *,MASTERKEY_STORED *)
0x18002da91  test    eax, eax
0x18002da93  jnz     short loc_18002DAF7
0x18002da95  mov     rax, cs:WPP_GLOBAL_Control
0x18002da9c  lea     rdx, WPP_GLOBAL_Control
0x18002daa3  cmp     rax, rdx
0x18002daa6  jz      short loc_18002DAD9
0x18002daa8  test    byte ptr [rax+1Ch], 1
0x18002daac  jz      short loc_18002DAD9
0x18002daae  call    cs:__imp_GetLastError
0x18002dab5  nop     dword ptr [rax+rax+00h]
0x18002daba  mov     edx, 10h
0x18002dabf  mov     r9d, eax
0x18002dac2  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002dac9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dad0  mov     rcx, [rcx+10h]
0x18002dad4  call    WPP_SF_d
0x18002dad9  xor     r8d, r8d; int
0x18002dadc  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002dae0  mov     rcx, rdi; void *
0x18002dae3  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002dae8  mov     ebx, 490h
0x18002daed  mov     ecx, 14h
0x18002daf2  jmp     loc_18002DD30
0x18002daf7  lea     rdx, [rbp+0B0h+Uuid]; Uuid
0x18002dafb  lea     rcx, [rbp+0B0h+StringUuid]; StringUuid
0x18002daff  call    cs:__imp_UuidFromStringW
0x18002db06  nop     dword ptr [rax+rax+00h]
0x18002db0b  mov     ebx, eax
0x18002db0d  test    eax, eax
0x18002db0f  jz      short loc_18002DB3D
0x18002db11  xor     r8d, r8d; int
0x18002db14  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002db18  mov     rcx, rdi; void *
0x18002db1b  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002db20  mov     r9d, 34Ah
0x18002db26  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002db2d  lea     rdx, aDwlasterror; "dwLastError"
0x18002db34  mov     ecx, ebx
0x18002db36  call    DebugTraceError
0x18002db3b  jmp     short loc_18002DAED
0x18002db3d  mov     [rsp+1B0h+var_158], r15
0x18002db42  lea     rax, [rsp+1B0h+var_160]
0x18002db47  mov     [rsp+1B0h+var_190], rax; unsigned int *
0x18002db4c  lea     r9, [rsp+1B0h+var_158]; unsigned __int8 **
0x18002db51  lea     r8, [rbp+0B0h+Uuid]; struct _GUID *
0x18002db55  mov     rdx, r14; unsigned __int16 *
0x18002db58  mov     rcx, qword ptr [rsp+1B0h+var_150.Data1]; struct _LUID *
0x18002db5d  call    ?SearchMasterKeyCache@@YAHPEAU_LUID@@PEBGPEAU_GUID@@PEAPEAEPEAK@Z; SearchMasterKeyCache(_LUID *,ushort const *,_GUID *,uchar * *,ulong *)
0x18002db62  test    eax, eax
0x18002db64  jnz     short loc_18002DBA3
0x18002db66  mov     rcx, cs:WPP_GLOBAL_Control
0x18002db6d  lea     rdx, WPP_GLOBAL_Control
0x18002db74  cmp     rcx, rdx
0x18002db77  jz      loc_18002DAD9
0x18002db7d  test    byte ptr [rcx+1Ch], 1
0x18002db81  jz      loc_18002DAD9
0x18002db87  lea     edx, [rax+11h]
0x18002db8a  lea     r9, [rbp+0B0h+StringUuid]
0x18002db8e  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002db95  mov     rcx, [rcx+10h]
0x18002db99  call    WPP_SF_S
0x18002db9e  jmp     loc_18002DAD9
0x18002dba3  lea     r8, [rsp+1B0h+var_160]; unsigned int *
0x18002dba8  lea     rdx, [rsp+1B0h+var_158]; unsigned __int8 **
0x18002dbad  lea     rcx, [rsp+1B0h+var_140]; this
0x18002dbb2  call    ??0ScopedSecureSSFree@@QEAA@AEAPEAEAEAK@Z; ScopedSecureSSFree::ScopedSecureSSFree(uchar * &,ulong &)
0x18002dbb7  nop
0x18002dbb8  xorps   xmm0, xmm0
0x18002dbbb  movups  xmmword ptr [rbp+0B0h+var_80.Data1], xmm0
0x18002dbbf  lea     rax, [rsp+1B0h+var_160+4]
0x18002dbc4  mov     [rsp+1B0h+var_188], rax; unsigned int *
0x18002dbc9  lea     rax, [rbp+0B0h+var_60]
0x18002dbcd  mov     [rsp+1B0h+var_190], rax; unsigned __int8 *
0x18002dbd2  mov     r9d, 3; unsigned int
0x18002dbd8  xor     r8d, r8d; void *
0x18002dbdb  lea     rdx, [rbp+0B0h+var_80]; struct _GUID *
0x18002dbdf  mov     rcx, rdi; void *
0x18002dbe2  call    ?GetMasterKeyUserEncryptionKey@@YAHPEAXPEAU_GUID@@0KQEAEPEAK@Z; GetMasterKeyUserEncryptionKey(void *,_GUID *,void *,ulong,uchar * const,ulong *)
0x18002dbe7  test    eax, eax
0x18002dbe9  jz      loc_18002DCDA
0x18002dbef  or      [rbp+0B0h+var_C0], 4
0x18002dbf3  mov     eax, dword ptr [rsp+1B0h+var_160]
0x18002dbf7  mov     dword ptr [rsp+1B0h+var_170], eax; size_t
0x18002dbfb  mov     rax, [rsp+1B0h+var_158]
0x18002dc00  mov     [rsp+1B0h+var_178], rax; unsigned __int8 *
0x18002dc05  mov     eax, dword ptr [rsp+1B0h+var_160+4]
0x18002dc09  mov     [rsp+1B0h+var_180], eax; unsigned int
0x18002dc0d  mov     dword ptr [rsp+1B0h+var_188], 14h; unsigned int
0x18002dc15  lea     rax, [rbp+0B0h+var_60]
0x18002dc19  mov     [rsp+1B0h+var_190], rax; unsigned __int8 *
0x18002dc1e  mov     r9d, r13d; unsigned int
0x18002dc21  mov     r8d, r12d; unsigned int
0x18002dc24  xor     edx, edx; unsigned int
0x18002dc26  lea     rcx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002dc2a  call    ?EncryptMasterKeyToStorage@@YAKPEAUMASTERKEY_STORED@@KIIPEAEKK1K@Z; EncryptMasterKeyToStorage(MASTERKEY_STORED *,ulong,uint,uint,uchar *,ulong,ulong,uchar *,ulong)
0x18002dc2f  mov     ebx, eax
0x18002dc31  test    eax, eax
0x18002dc33  jz      short loc_18002DC64
0x18002dc35  mov     r9d, 38Bh
0x18002dc3b  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002dc42  lea     rdx, aDwlasterror; "dwLastError"
0x18002dc49  mov     ecx, eax
0x18002dc4b  call    DebugTraceError
0x18002dc50  xor     r8d, r8d; int
0x18002dc53  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002dc57  mov     rcx, rdi; void *
0x18002dc5a  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002dc5f  jmp     loc_18002DD1C
0x18002dc64  movaps  xmm0, xmmword ptr [rbp+0B0h+var_80.Data1]
0x18002dc68  movdqa  xmmword ptr [rsp+1B0h+var_150.Data1], xmm0
0x18002dc6e  lea     r9, [rdi+50h]; unsigned __int16 *
0x18002dc72  lea     r8, [rbp+0B0h+var_60]; unsigned __int8 *
0x18002dc76  lea     rdx, [rsp+1B0h+var_150]; struct _GUID
0x18002dc7b  lea     rcx, [rbp+0B0h+StringUuid]; StringUuid
0x18002dc7f  call    ?LogMasterKeyDescription@@YAJPEBGU_GUID@@PEAEPEAG@Z; LogMasterKeyDescription(ushort const *,_GUID,uchar *,ushort *)
0x18002dc84  mov     r8d, 1; int
0x18002dc8a  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002dc8e  mov     rcx, rdi; void *
0x18002dc91  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002dc96  test    eax, eax
0x18002dc98  jnz     short loc_18002DCC8
0x18002dc9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dca1  lea     rdx, WPP_GLOBAL_Control
0x18002dca8  cmp     rcx, rdx
0x18002dcab  jz      short loc_18002DD17
0x18002dcad  test    byte ptr [rcx+1Ch], 1
0x18002dcb1  jz      short loc_18002DD17
0x18002dcb3  lea     edx, [rax+13h]
0x18002dcb6  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002dcbd  mov     rcx, [rcx+10h]
0x18002dcc1  call    WPP_SF_
0x18002dcc6  jmp     short loc_18002DD17
0x18002dcc8  lea     rcx, [rsp+1B0h+var_140]; this
0x18002dccd  call    ??1ScopedSecureSSFree@@QEAA@XZ; ScopedSecureSSFree::~ScopedSecureSSFree(void)
0x18002dcd2  mov     ebx, r15d
0x18002dcd5  jmp     loc_18002DAED
0x18002dcda  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dce1  lea     rdx, WPP_GLOBAL_Control
0x18002dce8  cmp     rcx, rdx
0x18002dceb  jz      short loc_18002DD08
0x18002dced  test    byte ptr [rcx+1Ch], 1
0x18002dcf1  jz      short loc_18002DD08
0x18002dcf3  mov     edx, 12h
0x18002dcf8  lea     r8, WPP_f7e4c0cc1a8c3918616be824dd04d924_Traceguids
0x18002dcff  mov     rcx, [rcx+10h]
0x18002dd03  call    WPP_SF_
0x18002dd08  xor     r8d, r8d; int
0x18002dd0b  lea     rdx, [rbp+0B0h+var_120]; struct MASTERKEY_STORED *
0x18002dd0f  mov     rcx, rdi; void *
0x18002dd12  call    ?CloseMasterKey@@YAHPEAXPEAUMASTERKEY_STORED@@H@Z; CloseMasterKey(void *,MASTERKEY_STORED *,int)
0x18002dd17  mov     ebx, 490h
0x18002dd1c  lea     rcx, [rsp+1B0h+var_140]; this
0x18002dd21  call    ??1ScopedSecureSSFree@@QEAA@XZ; ScopedSecureSSFree::~ScopedSecureSSFree(void)
0x18002dd26  jmp     loc_18002DAED
0x18002dd2b  mov     ebx, 57h ; 'W'
0x18002dd30  lea     rax, [rbp+0B0h+var_60]
0x18002dd34  mov     [rax], r15b
0x18002dd37  inc     rax
0x18002dd3a  sub     rcx, 1
0x18002dd3e  jnz     short loc_18002DD34
0x18002dd40  mov     eax, ebx
0x18002dd42  mov     rcx, [rbp+0B0h+var_48]
0x18002dd46  xor     rcx, rsp; StackCookie
0x18002dd49  call    __security_check_cookie
0x18002dd4e  add     rsp, 178h
0x18002dd55  pop     r15
0x18002dd57  pop     r14
0x18002dd59  pop     r13
0x18002dd5b  pop     r12
0x18002dd5d  pop     rdi
0x18002dd5e  pop     rsi
0x18002dd5f  pop     rbx
0x18002dd60  pop     rbp
0x18002dd61  retn
```
