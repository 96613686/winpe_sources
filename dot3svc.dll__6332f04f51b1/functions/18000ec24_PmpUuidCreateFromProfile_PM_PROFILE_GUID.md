# PmpUuidCreateFromProfile(_PM_PROFILE *,_GUID *)

- ea: `0x18000ec24`
- end: `0x18000f0fa`
- name: `?PmpUuidCreateFromProfile@@YAKPEAU_PM_PROFILE@@PEAU_GUID@@@Z`
- size: `1238`
- prototype: `__int64 __fastcall(struct _PM_PROFILE *, struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cfc4`

## callees

- `0x18000a7ec`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x18000c460`
- `0x18000ec24`
- `0x180032e4c`
- `0x180032f7c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000ecf2`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed6a`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee35`
- `ntdll!RtlNtStatusToDosError` at `0x18000eeeb`
- `ntdll!RtlNtStatusToDosError` at `0x18000ef7b`
- `ntdll!RtlNtStatusToDosError` at `0x18000efde`
- `ntdll!RtlNtStatusToDosError` at `0x18000ecf2`
- `ntdll!RtlNtStatusToDosError` at `0x18000ed6a`
- `ntdll!RtlNtStatusToDosError` at `0x18000ee35`
- `ntdll!RtlNtStatusToDosError` at `0x18000eeeb`
- `ntdll!RtlNtStatusToDosError` at `0x18000ef7b`
- `ntdll!RtlNtStatusToDosError` at `0x18000efde`
- `bcrypt!BCryptFinishHash` at `0x18000ef99`
- `bcrypt!BCryptFinishHash` at `0x18000ef99`
- `bcrypt!BCryptHashData` at `0x18000ef36`
- `bcrypt!BCryptHashData` at `0x18000ef36`
- `bcrypt!BCryptCreateHash` at `0x18000eea6`
- `bcrypt!BCryptCreateHash` at `0x18000eea6`
- `bcrypt!BCryptGetProperty` at `0x18000ed25`
- `bcrypt!BCryptGetProperty` at `0x18000edf0`
- `bcrypt!BCryptGetProperty` at `0x18000ed25`
- `bcrypt!BCryptGetProperty` at `0x18000edf0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ecad`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000ecad`
- `bcrypt!BCryptDestroyHash` at `0x18000f042`
- `bcrypt!BCryptDestroyHash` at `0x18000f042`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000f05d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000f05d`

## pseudocode

```c
__int64 __fastcall PmpUuidCreateFromProfile(struct _PM_PROFILE *a1, struct _GUID *a2)
{
  UCHAR *v3; // r15
  UCHAR *v4; // r14
  int v6; // ebx
  ULONG v7; // ebx
  __int64 v8; // rdx
  int Property; // ebx
  __int64 v10; // r8
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // ebx
  __int64 v15; // r8
  int v16; // ebx
  ULONG v17; // eax
  UCHAR *v18; // rsi
  unsigned __int64 v19; // rcx
  ULONG v20; // eax
  int v21; // edi
  int v22; // edi
  unsigned int v23; // r8d
  __int64 v24; // rcx
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  PUCHAR pbInput; // [rsp+58h] [rbp-8h] BYREF
  ULONG v30; // [rsp+B0h] [rbp+50h] BYREF
  ULONG pbOutput; // [rsp+B8h] [rbp+58h] BYREF

  pbInput = 0;
  v3 = 0;
  phAlgorithm = 0;
  v4 = 0;
  phHash = 0;
  pcbResult = 0;
  v30 = 0;
  pbOutput = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 47, WPP_935883eb83d333df730e157613565e66_Traceguids);
  }
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( v6 >= 0 )
    goto LABEL_82;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink)
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 48, WPP_935883eb83d333df730e157613565e66_Traceguids, (unsigned int)v6);
  }
  v7 = RtlNtStatusToDosError(v6);
  if ( !v7 )
  {
LABEL_82:
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
      goto LABEL_17;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink)
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 49, WPP_935883eb83d333df730e157613565e66_Traceguids, (unsigned int)Property);
    }
    v7 = RtlNtStatusToDosError(Property);
    if ( !v7 )
    {
LABEL_17:
      v3 = (UCHAR *)Dot3Alloc(pbOutput, v8, v10);
      if ( !v3 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || !BYTE1(WPP_GLOBAL_Control[1].Blink)
          || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
        {
          goto LABEL_23;
        }
        v12 = 50;
LABEL_22:
        WPP_SF_(v11[1].Flink, v12, WPP_935883eb83d333df730e157613565e66_Traceguids);
        v11 = WPP_GLOBAL_Control;
LABEL_23:
        v7 = 8;
        goto LABEL_62;
      }
      v14 = BCryptGetProperty(phAlgorithm, L"HashDigestLength", (PUCHAR)&v30, 4u, &pcbResult, 0);
      if ( v14 >= 0 )
        goto LABEL_81;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 51, WPP_935883eb83d333df730e157613565e66_Traceguids, (unsigned int)v14);
      }
      v7 = RtlNtStatusToDosError(v14);
      if ( !v7 )
      {
LABEL_81:
        v4 = (UCHAR *)Dot3Alloc(v30, v13, v15);
        if ( !v4 )
        {
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || !BYTE1(WPP_GLOBAL_Control[1].Blink)
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
          {
            goto LABEL_23;
          }
          v12 = 52;
          goto LABEL_22;
        }
        v16 = BCryptCreateHash(phAlgorithm, &phHash, v3, pbOutput, 0, 0, 0);
        if ( v16 >= 0 )
          goto LABEL_41;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 53, WPP_935883eb83d333df730e157613565e66_Traceguids, (unsigned int)v16);
        }
        v7 = RtlNtStatusToDosError(v16);
        if ( !v7 )
        {
LABEL_41:
          v17 = LpGenerateProfileXml(a1, &pbInput);
          v18 = pbInput;
          v7 = v17;
          if ( !v17 )
          {
            if ( !pbInput )
            {
              v19 = 0;
LABEL_44:
              v20 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(2 * v19);
              v21 = BCryptHashData(phHash, v18, v20, 0);
              if ( v21 >= 0 )
                goto LABEL_50;
              if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                && BYTE1(WPP_GLOBAL_Control[1].Blink)
                && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control[1].Flink,
                  54,
                  WPP_935883eb83d333df730e157613565e66_Traceguids,
                  (unsigned int)v21);
              }
              v7 = RtlNtStatusToDosError(v21);
              if ( !v7 )
              {
LABEL_50:
                v22 = BCryptFinishHash(phHash, v4, v30, 0);
                if ( v22 >= 0 )
                  goto LABEL_56;
                if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
                  && BYTE1(WPP_GLOBAL_Control[1].Blink)
                  && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control[1].Flink,
                    55,
                    WPP_935883eb83d333df730e157613565e66_Traceguids,
                    (unsigned int)v22);
                }
                v7 = RtlNtStatusToDosError(v22);
                if ( !v7 )
                {
LABEL_56:
                  v23 = 0;
                  if ( v30 != 16 )
                  {
                    do
                    {
                      v24 = v23++;
                      v4[v24] ^= v4[v24 + 16];
                    }
                    while ( v23 < (unsigned __int64)v30 - 16 );
                  }
                  *a2 = *(struct _GUID *)v4;
                }
              }
              goto LABEL_59;
            }
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)&pbInput[2 * v19] );
            if ( v19 <= 0x7FFFFFFF )
              goto LABEL_44;
            v7 = 8;
          }
LABEL_59:
          if ( v18 )
            LpFreeProfileXml(v18);
        }
      }
    }
  }
  v11 = WPP_GLOBAL_Control;
LABEL_62:
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    v11 = WPP_GLOBAL_Control;
  }
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v3 )
  {
    Dot3Free(v3);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    Dot3Free(v4);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v11[1].Blink) >= 4u && (BYTE4(v11[1].Blink) & 1) != 0 )
    WPP_SF_d(v11[1].Flink, 56, WPP_935883eb83d333df730e157613565e66_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000ec24  mov     [rsp-38h+arg_0], rbx
0x18000ec29  push    rbp
0x18000ec2a  push    rsi
0x18000ec2b  push    rdi
0x18000ec2c  push    r12
0x18000ec2e  push    r13
0x18000ec30  push    r14
0x18000ec32  push    r15
0x18000ec34  mov     rbp, rsp
0x18000ec37  sub     rsp, 60h
0x18000ec3b  xor     r13d, r13d
0x18000ec3e  mov     r12, rdx
0x18000ec41  mov     [rbp+pbInput], r13
0x18000ec45  mov     r15d, r13d
0x18000ec48  mov     [rbp+phAlgorithm], r13
0x18000ec4c  mov     r14d, r13d
0x18000ec4f  mov     [rbp+phHash], r13
0x18000ec53  mov     rdi, rcx
0x18000ec56  mov     [rbp+var_20], r13d
0x18000ec5a  mov     [rbp+arg_10], r13d
0x18000ec5e  mov     [rbp+pbOutput], r13d
0x18000ec62  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec69  lea     rax, WPP_GLOBAL_Control
0x18000ec70  lea     esi, [r13+1]
0x18000ec74  cmp     rcx, rax
0x18000ec77  jz      short loc_18000EC98
0x18000ec79  cmp     byte ptr [rcx+19h], 4
0x18000ec7d  jb      short loc_18000EC98
0x18000ec7f  test    [rcx+1Ch], sil
0x18000ec83  jz      short loc_18000EC98
0x18000ec85  mov     rcx, [rcx+10h]
0x18000ec89  lea     edx, [rsi+2Eh]
0x18000ec8c  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ec93  call    WPP_SF_
0x18000ec98  xor     r9d, r9d; dwFlags
0x18000ec9b  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000eca2  lea     rdx, pszAlgId; "SHA256"
0x18000eca9  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000ecad  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000ecb3  mov     ebx, eax
0x18000ecb5  test    eax, eax
0x18000ecb7  jns     short loc_18000ED02
0x18000ecb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ecc0  lea     rax, WPP_GLOBAL_Control
0x18000ecc7  cmp     rcx, rax
0x18000ecca  jz      short loc_18000ECF0
0x18000eccc  cmp     [rcx+19h], sil
0x18000ecd0  jb      short loc_18000ECF0
0x18000ecd2  test    [rcx+1Ch], sil
0x18000ecd6  jz      short loc_18000ECF0
0x18000ecd8  mov     rcx, [rcx+10h]
0x18000ecdc  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ece3  mov     edx, 30h ; '0'
0x18000ece8  mov     r9d, ebx
0x18000eceb  call    WPP_SF_d
0x18000ecf0  mov     ecx, ebx; Status
0x18000ecf2  call    cs:__imp_RtlNtStatusToDosError
0x18000ecf8  mov     ebx, eax
0x18000ecfa  test    eax, eax
0x18000ecfc  jnz     loc_18000F028
0x18000ed02  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000ed06  lea     rax, [rbp+var_20]
0x18000ed0a  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18000ed0f  lea     r8, [rbp+pbOutput]; pbOutput
0x18000ed13  mov     r9d, 4; cbOutput
0x18000ed19  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18000ed1e  lea     rdx, pszProperty; "ObjectLength"
0x18000ed25  call    cs:__imp_BCryptGetProperty
0x18000ed2b  mov     ebx, eax
0x18000ed2d  test    eax, eax
0x18000ed2f  jns     short loc_18000ED7A
0x18000ed31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed38  lea     rax, WPP_GLOBAL_Control
0x18000ed3f  cmp     rcx, rax
0x18000ed42  jz      short loc_18000ED68
0x18000ed44  cmp     [rcx+19h], sil
0x18000ed48  jb      short loc_18000ED68
0x18000ed4a  test    [rcx+1Ch], sil
0x18000ed4e  jz      short loc_18000ED68
0x18000ed50  mov     rcx, [rcx+10h]
0x18000ed54  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ed5b  mov     edx, 31h ; '1'
0x18000ed60  mov     r9d, ebx
0x18000ed63  call    WPP_SF_d
0x18000ed68  mov     ecx, ebx; Status
0x18000ed6a  call    cs:__imp_RtlNtStatusToDosError
0x18000ed70  mov     ebx, eax
0x18000ed72  test    eax, eax
0x18000ed74  jnz     loc_18000F028
0x18000ed7a  mov     ecx, [rbp+pbOutput]; dwBytes
0x18000ed7d  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18000ed82  mov     r15, rax
0x18000ed85  test    rax, rax
0x18000ed88  jnz     short loc_18000EDCD
0x18000ed8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed91  lea     rdi, WPP_GLOBAL_Control
0x18000ed98  cmp     rcx, rdi
0x18000ed9b  jz      short loc_18000EDC3
0x18000ed9d  cmp     [rcx+19h], sil
0x18000eda1  jb      short loc_18000EDC3
0x18000eda3  test    [rcx+1Ch], sil
0x18000eda7  jz      short loc_18000EDC3
0x18000eda9  lea     edx, [rax+32h]
0x18000edac  mov     rcx, [rcx+10h]
0x18000edb0  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000edb7  call    WPP_SF_
0x18000edbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edc3  mov     ebx, 8
0x18000edc8  jmp     loc_18000F036
0x18000edcd  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000edd1  lea     rax, [rbp+var_20]
0x18000edd5  mov     [rsp+60h+dwFlags], r13d; dwFlags
0x18000edda  lea     r8, [rbp+arg_10]; pbOutput
0x18000edde  mov     r9d, 4; cbOutput
0x18000ede4  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18000ede9  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000edf0  call    cs:__imp_BCryptGetProperty
0x18000edf6  mov     ebx, eax
0x18000edf8  test    eax, eax
0x18000edfa  jns     short loc_18000EE45
0x18000edfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee03  lea     rax, WPP_GLOBAL_Control
0x18000ee0a  cmp     rcx, rax
0x18000ee0d  jz      short loc_18000EE33
0x18000ee0f  cmp     [rcx+19h], sil
0x18000ee13  jb      short loc_18000EE33
0x18000ee15  test    [rcx+1Ch], sil
0x18000ee19  jz      short loc_18000EE33
0x18000ee1b  mov     rcx, [rcx+10h]
0x18000ee1f  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ee26  mov     edx, 33h ; '3'
0x18000ee2b  mov     r9d, ebx
0x18000ee2e  call    WPP_SF_d
0x18000ee33  mov     ecx, ebx; Status
0x18000ee35  call    cs:__imp_RtlNtStatusToDosError
0x18000ee3b  mov     ebx, eax
0x18000ee3d  test    eax, eax
0x18000ee3f  jnz     loc_18000F028
0x18000ee45  mov     ecx, [rbp+arg_10]; dwBytes
0x18000ee48  call    ?Dot3Alloc@@YAPEAX_K@Z; Dot3Alloc(unsigned __int64)
0x18000ee4d  mov     r14, rax
0x18000ee50  test    rax, rax
0x18000ee53  jnz     short loc_18000EE88
0x18000ee55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee5c  lea     rdi, WPP_GLOBAL_Control
0x18000ee63  cmp     rcx, rdi
0x18000ee66  jz      loc_18000EDC3
0x18000ee6c  cmp     [rcx+19h], sil
0x18000ee70  jb      loc_18000EDC3
0x18000ee76  test    [rcx+1Ch], sil
0x18000ee7a  jz      loc_18000EDC3
0x18000ee80  lea     edx, [rax+34h]
0x18000ee83  jmp     loc_18000EDAC
0x18000ee88  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18000ee8c  lea     rdx, [rbp+phHash]; phHash
0x18000ee90  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000ee94  mov     r8, r15; pbHashObject
0x18000ee97  mov     [rsp+60h+var_30], r13d; dwFlags
0x18000ee9c  mov     [rsp+60h+dwFlags], r13d; cbSecret
0x18000eea1  mov     [rsp+60h+pcbResult], r13; pbSecret
0x18000eea6  call    cs:__imp_BCryptCreateHash
0x18000eeac  mov     ebx, eax
0x18000eeae  test    eax, eax
0x18000eeb0  jns     short loc_18000EEFB
0x18000eeb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eeb9  lea     rax, WPP_GLOBAL_Control
0x18000eec0  cmp     rcx, rax
0x18000eec3  jz      short loc_18000EEE9
0x18000eec5  cmp     [rcx+19h], sil
0x18000eec9  jb      short loc_18000EEE9
0x18000eecb  test    [rcx+1Ch], sil
0x18000eecf  jz      short loc_18000EEE9
0x18000eed1  mov     rcx, [rcx+10h]
0x18000eed5  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000eedc  mov     edx, 35h ; '5'
0x18000eee1  mov     r9d, ebx
0x18000eee4  call    WPP_SF_d
0x18000eee9  mov     ecx, ebx; Status
0x18000eeeb  call    cs:__imp_RtlNtStatusToDosError
0x18000eef1  mov     ebx, eax
0x18000eef3  test    eax, eax
0x18000eef5  jnz     loc_18000F028
0x18000eefb  lea     rdx, [rbp+pbInput]
0x18000eeff  mov     rcx, rdi
0x18000ef02  call    LpGenerateProfileXml
0x18000ef07  mov     rsi, [rbp+pbInput]
0x18000ef0b  mov     ebx, eax
0x18000ef0d  test    eax, eax
0x18000ef0f  jnz     loc_18000F01B
0x18000ef15  test    rsi, rsi
0x18000ef18  jnz     loc_18000F0D5
0x18000ef1e  mov     rcx, r13
0x18000ef21  add     rcx, rcx
0x18000ef24  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000ef29  mov     rcx, [rbp+phHash]; hHash
0x18000ef2d  xor     r9d, r9d; dwFlags
0x18000ef30  mov     r8d, eax; cbInput
0x18000ef33  mov     rdx, rsi; pbInput
0x18000ef36  call    cs:__imp_BCryptHashData
0x18000ef3c  mov     edi, eax
0x18000ef3e  test    eax, eax
0x18000ef40  jns     short loc_18000EF8B
0x18000ef42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef49  lea     rax, WPP_GLOBAL_Control
0x18000ef50  cmp     rcx, rax
0x18000ef53  jz      short loc_18000EF79
0x18000ef55  cmp     byte ptr [rcx+19h], 1
0x18000ef59  jb      short loc_18000EF79
0x18000ef5b  test    byte ptr [rcx+1Ch], 1
0x18000ef5f  jz      short loc_18000EF79
0x18000ef61  mov     rcx, [rcx+10h]
0x18000ef65  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000ef6c  mov     edx, 36h ; '6'
0x18000ef71  mov     r9d, edi
0x18000ef74  call    WPP_SF_d
0x18000ef79  mov     ecx, edi; Status
0x18000ef7b  call    cs:__imp_RtlNtStatusToDosError
0x18000ef81  mov     ebx, eax
0x18000ef83  test    eax, eax
0x18000ef85  jnz     loc_18000F01B
0x18000ef8b  mov     r8d, [rbp+arg_10]; cbOutput
0x18000ef8f  xor     r9d, r9d; dwFlags
0x18000ef92  mov     rcx, [rbp+phHash]; hHash
0x18000ef96  mov     rdx, r14; pbOutput
0x18000ef99  call    cs:__imp_BCryptFinishHash
0x18000ef9f  mov     edi, eax
0x18000efa1  test    eax, eax
0x18000efa3  jns     short loc_18000EFEA
0x18000efa5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efac  lea     rax, WPP_GLOBAL_Control
0x18000efb3  cmp     rcx, rax
0x18000efb6  jz      short loc_18000EFDC
0x18000efb8  cmp     byte ptr [rcx+19h], 1
0x18000efbc  jb      short loc_18000EFDC
0x18000efbe  test    byte ptr [rcx+1Ch], 1
0x18000efc2  jz      short loc_18000EFDC
0x18000efc4  mov     rcx, [rcx+10h]
0x18000efc8  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000efcf  mov     edx, 37h ; '7'
0x18000efd4  mov     r9d, edi
0x18000efd7  call    WPP_SF_d
0x18000efdc  mov     ecx, edi; Status
0x18000efde  call    cs:__imp_RtlNtStatusToDosError
0x18000efe4  mov     ebx, eax
0x18000efe6  test    eax, eax
0x18000efe8  jnz     short loc_18000F01B
0x18000efea  cmp     [rbp+arg_10], 10h
0x18000efee  mov     r8d, r13d
0x18000eff1  jz      short loc_18000F011
0x18000eff3  mov     ecx, r8d
0x18000eff6  inc     r8d
0x18000eff9  mov     al, [rcx+r14+10h]
0x18000effe  xor     [rcx+r14], al
0x18000f002  mov     edx, [rbp+arg_10]
0x18000f005  sub     rdx, 10h
0x18000f009  mov     eax, r8d
0x18000f00c  cmp     rax, rdx
0x18000f00f  jb      short loc_18000EFF3
0x18000f011  movups  xmm0, xmmword ptr [r14]
0x18000f015  movdqu  xmmword ptr [r12], xmm0
0x18000f01b  test    rsi, rsi
0x18000f01e  jz      short loc_18000F028
0x18000f020  mov     rcx, rsi; lpMem
0x18000f023  call    LpFreeProfileXml
0x18000f028  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f02f  lea     rdi, WPP_GLOBAL_Control
0x18000f036  mov     rax, [rbp+phHash]
0x18000f03a  test    rax, rax
0x18000f03d  jz      short loc_18000F04F
0x18000f03f  mov     rcx, rax; hHash
0x18000f042  call    cs:__imp_BCryptDestroyHash
0x18000f048  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f04f  mov     rax, [rbp+phAlgorithm]
0x18000f053  test    rax, rax
0x18000f056  jz      short loc_18000F06A
0x18000f058  xor     edx, edx; dwFlags
0x18000f05a  mov     rcx, rax; hAlgorithm
0x18000f05d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000f063  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f06a  test    r15, r15
0x18000f06d  jz      short loc_18000F07E
0x18000f06f  mov     rcx, r15; lpMem
0x18000f072  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18000f077  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f07e  test    r14, r14
0x18000f081  jz      short loc_18000F092
0x18000f083  mov     rcx, r14; lpMem
0x18000f086  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18000f08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f092  cmp     rcx, rdi
0x18000f095  jz      short loc_18000F0BB
0x18000f097  cmp     byte ptr [rcx+19h], 4
0x18000f09b  jb      short loc_18000F0BB
0x18000f09d  test    byte ptr [rcx+1Ch], 1
0x18000f0a1  jz      short loc_18000F0BB
0x18000f0a3  mov     rcx, [rcx+10h]
0x18000f0a7  lea     r8, WPP_935883eb83d333df730e157613565e66_Traceguids
0x18000f0ae  mov     edx, 38h ; '8'
0x18000f0b3  mov     r9d, ebx
0x18000f0b6  call    WPP_SF_d
  ... truncated ...
```
