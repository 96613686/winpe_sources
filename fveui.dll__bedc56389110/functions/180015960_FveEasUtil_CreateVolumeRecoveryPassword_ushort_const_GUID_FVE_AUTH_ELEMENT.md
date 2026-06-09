# FveEasUtil::CreateVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)

- ea: `0x180015960`
- end: `0x180015d3c`
- name: `?CreateVolumeRecoveryPassword@FveEasUtil@@QEBAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z`
- size: `988`
- prototype: `__int64 __fastcall(FveEasUtil *this, const unsigned __int16 *, struct _GUID *, struct _FVE_AUTH_ELEMENT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180023fe4`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x180005018`
- `0x18000e354`
- `0x180013b00`
- `0x180015960`
- `0x180015f84`
- `0x1800178e8`
- `0x1800179bc`
- `0x18002d010`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x180015b92`
- `FVEAPI!FveCommitChanges` at `0x180015b92`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180015b42`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180015b42`
- `FVEAPI!FveGetIdentity` at `0x180015c01`
- `FVEAPI!FveGetIdentity` at `0x180015c01`

## pseudocode

```c
__int64 __fastcall FveEasUtil::CreateVolumeRecoveryPassword(
        FveEasUtil *this,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        struct _FVE_AUTH_ELEMENT *a4)
{
  int VolumeRecoveryPassword; // eax
  int FVEVolumeHandle; // ebx
  PVOID *v10; // rcx
  __int64 v11; // rdx
  int StatusFlags; // eax
  __int64 (__fastcall ***v13)(_QWORD, __int64, __int128 *, struct _GUID *, _DWORD); // rcx
  __int64 v14; // rdx
  unsigned int v16; // [rsp+30h] [rbp-59h] BYREF
  void **v17; // [rsp+38h] [rbp-51h] BYREF
  void *v18; // [rsp+40h] [rbp-49h]
  _DWORD v19[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+50h] [rbp-39h]
  __int128 v21; // [rsp+58h] [rbp-31h]
  __int128 v22; // [rsp+68h] [rbp-21h]
  __int64 v23; // [rsp+78h] [rbp-11h]
  struct _GUID v24; // [rsp+80h] [rbp-9h] BYREF
  __int128 v25; // [rsp+90h] [rbp+7h] BYREF

  v19[0] = 56;
  v19[1] = 1;
  v20 = 0x80000;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v16 = 0;
  v24 = 0;
  v17 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v18 = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
  VolumeRecoveryPassword = FveEasUtil::GetVolumeRecoveryPassword(a2, a3, a4);
  FVEVolumeHandle = VolumeRecoveryPassword;
  if ( !VolumeRecoveryPassword )
    goto LABEL_54;
  if ( VolumeRecoveryPassword == -2147023728 )
  {
    FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(a2, &v17, 0);
    if ( FVEVolumeHandle )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle < 0 )
        goto LABEL_55;
    }
    FVEVolumeHandle = FveEasUtil::EnsureVolumeDEManaged(&v17);
    if ( FVEVolumeHandle )
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          80,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle < 0 )
        goto LABEL_55;
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_BYTE *)this + 48) )
    {
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
        WPP_SF_(v10[2], 81, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids);
      LODWORD(v20) = v20 | 8;
    }
    FVEVolumeHandle = FveAddAuthMethodInformation(v18, v19, &v24);
    if ( !FVEVolumeHandle )
      goto LABEL_35;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
        (unsigned int)FVEVolumeHandle);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( FVEVolumeHandle >= 0 )
    {
LABEL_35:
      FVEVolumeHandle = FveCommitChanges(v18);
      if ( !FVEVolumeHandle )
        goto LABEL_61;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
          (unsigned int)FVEVolumeHandle);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( FVEVolumeHandle >= 0 )
      {
LABEL_61:
        if ( *((_BYTE *)this + 48) )
        {
          if ( (StatusFlags = CFveApiWrapper::GetStatusFlags(v18, &v16), StatusFlags < 0)
            || (StatusFlags = FveGetIdentity(v18, &v25), StatusFlags < 0)
            || (v13 = (__int64 (__fastcall ***)(_QWORD, __int64, __int128 *, struct _GUID *, _DWORD))*((_QWORD *)this + 4)) != 0
            && ((v16 & 0x4000) == 0 ? (v14 = (unsigned int)((v16 & 0x400000) != 0) + 1) : (v14 = 0),
                StatusFlags = (**v13)(v13, v14, &v25, &v24, 0),
                StatusFlags < 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                84,
                &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
                (unsigned int)StatusFlags);
          }
        }
        if ( a4 )
        {
          FVEVolumeHandle = FveEasUtil::GetVolumeRecoveryPassword(a2, a3, a4);
          if ( FVEVolumeHandle )
          {
            v10 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              goto LABEL_58;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_55;
            v11 = 85;
            goto LABEL_53;
          }
        }
        else
        {
          *a3 = v24;
        }
LABEL_54:
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_58;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v11 = 78;
LABEL_53:
      WPP_SF_d(v10[2], v11, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)FVEVolumeHandle);
      goto LABEL_54;
    }
  }
LABEL_55:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x20) != 0 )
    WPP_SF_d(v10[2], 86, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, (unsigned int)FVEVolumeHandle);
LABEL_58:
  v17 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close((__int64)&v17);
  return (unsigned int)FVEVolumeHandle;
}

```

## disassembly

```asm
0x180015960  push    rbp
0x180015962  push    rbx
0x180015963  push    rsi
0x180015964  push    rdi
0x180015965  push    r12
0x180015967  push    r14
0x180015969  push    r15
0x18001596b  lea     rbp, [rsp-27h]
0x180015970  sub     rsp, 0B0h
0x180015977  mov     rax, cs:__security_cookie
0x18001597e  xor     rax, rsp
0x180015981  mov     [rbp+57h+var_40], rax
0x180015985  mov     r15, r9
0x180015988  mov     r14, r8
0x18001598b  mov     r12, rdx
0x18001598e  mov     rsi, rcx
0x180015991  mov     [rbp+57h+var_98], 38h ; '8'
0x180015998  mov     [rbp+57h+var_94], 1
0x18001599f  mov     [rbp+57h+var_90], 80000h
0x1800159a7  xorps   xmm0, xmm0
0x1800159aa  movdqu  [rbp+57h+var_88], xmm0
0x1800159af  xorps   xmm1, xmm1
0x1800159b2  xor     eax, eax
0x1800159b4  movups  [rbp+57h+var_78], xmm1
0x1800159b8  mov     [rbp+57h+var_68], rax
0x1800159bc  mov     [rbp+57h+var_B0], eax
0x1800159bf  movups  [rbp+57h+var_60], xmm0
0x1800159c3  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x1800159ca  mov     [rbp+57h+var_A8], rax
0x1800159ce  mov     [rbp+57h+var_A0], 0
0x1800159d6  movups  [rbp+57h+var_50], xmm0
0x1800159da  lea     rax, WPP_GLOBAL_Control
0x1800159e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800159e8  cmp     rcx, rax
0x1800159eb  jz      short loc_180015A08
0x1800159ed  test    byte ptr [rcx+1Ch], 20h
0x1800159f1  jz      short loc_180015A08
0x1800159f3  mov     edx, 4Dh ; 'M'
0x1800159f8  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800159ff  mov     rcx, [rcx+10h]
0x180015a03  call    WPP_SF_
0x180015a08  mov     r8, r15; struct _FVE_AUTH_ELEMENT *
0x180015a0b  mov     rdx, r14; struct _GUID *
0x180015a0e  mov     rcx, r12; unsigned __int16 *
0x180015a11  call    ?GetVolumeRecoveryPassword@FveEasUtil@@SAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z; FveEasUtil::GetVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)
0x180015a16  mov     ebx, eax
0x180015a18  test    eax, eax
0x180015a1a  jz      loc_180015CD6
0x180015a20  cmp     eax, 80070490h
0x180015a25  jz      short loc_180015A55
0x180015a27  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a2e  lea     rax, WPP_GLOBAL_Control
0x180015a35  cmp     rcx, rax
0x180015a38  jz      loc_180015D08
0x180015a3e  mov     dil, 40h ; '@'
0x180015a41  test    [rcx+1Ch], dil
0x180015a45  jz      loc_180015CDD
0x180015a4b  mov     edx, 4Eh ; 'N'
0x180015a50  jmp     loc_180015CC3
0x180015a55  xor     r8d, r8d
0x180015a58  lea     rdx, [rbp+57h+var_A8]
0x180015a5c  mov     rcx, r12
0x180015a5f  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x180015a64  mov     ebx, eax
0x180015a66  mov     dil, 40h ; '@'
0x180015a69  test    eax, eax
0x180015a6b  jz      short loc_180015AAD
0x180015a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015a74  lea     rax, WPP_GLOBAL_Control
0x180015a7b  cmp     rcx, rax
0x180015a7e  jz      short loc_180015AA5
0x180015a80  test    [rcx+1Ch], dil
0x180015a84  jz      short loc_180015AA5
0x180015a86  mov     edx, 4Fh ; 'O'
0x180015a8b  mov     r9d, ebx
0x180015a8e  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015a95  mov     rcx, [rcx+10h]
0x180015a99  call    WPP_SF_d
0x180015a9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aa5  test    ebx, ebx
0x180015aa7  js      loc_180015CDD
0x180015aad  lea     rcx, [rbp+57h+var_A8]
0x180015ab1  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x180015ab6  mov     ebx, eax
0x180015ab8  test    eax, eax
0x180015aba  jz      short loc_180015AFE
0x180015abc  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ac3  lea     rax, WPP_GLOBAL_Control
0x180015aca  cmp     rcx, rax
0x180015acd  jz      short loc_180015AF4
0x180015acf  test    [rcx+1Ch], dil
0x180015ad3  jz      short loc_180015AF4
0x180015ad5  mov     edx, 50h ; 'P'
0x180015ada  mov     r9d, ebx
0x180015add  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015ae4  mov     rcx, [rcx+10h]
0x180015ae8  call    WPP_SF_d
0x180015aed  mov     rcx, cs:WPP_GLOBAL_Control
0x180015af4  test    ebx, ebx
0x180015af6  js      loc_180015CDD
0x180015afc  jmp     short loc_180015B05
0x180015afe  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b05  cmp     byte ptr [rsi+30h], 0
0x180015b09  jz      short loc_180015B36
0x180015b0b  lea     rax, WPP_GLOBAL_Control
0x180015b12  cmp     rcx, rax
0x180015b15  jz      short loc_180015B32
0x180015b17  test    byte ptr [rcx+1Ch], 8
0x180015b1b  jz      short loc_180015B32
0x180015b1d  mov     edx, 51h ; 'Q'
0x180015b22  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015b29  mov     rcx, [rcx+10h]
0x180015b2d  call    WPP_SF_
0x180015b32  or      dword ptr [rbp+57h+var_90], 8
0x180015b36  lea     r8, [rbp+57h+var_60]
0x180015b3a  lea     rdx, [rbp+57h+var_98]
0x180015b3e  mov     rcx, [rbp+57h+var_A0]
0x180015b42  call    cs:__imp_FveAddAuthMethodInformation
0x180015b48  mov     ebx, eax
0x180015b4a  test    eax, eax
0x180015b4c  jz      short loc_180015B8E
0x180015b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b55  lea     rax, WPP_GLOBAL_Control
0x180015b5c  cmp     rcx, rax
0x180015b5f  jz      short loc_180015B86
0x180015b61  test    [rcx+1Ch], dil
0x180015b65  jz      short loc_180015B86
0x180015b67  mov     edx, 52h ; 'R'
0x180015b6c  mov     r9d, ebx
0x180015b6f  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015b76  mov     rcx, [rcx+10h]
0x180015b7a  call    WPP_SF_d
0x180015b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b86  test    ebx, ebx
0x180015b88  js      loc_180015CDD
0x180015b8e  mov     rcx, [rbp+57h+var_A0]
0x180015b92  call    cs:__imp_FveCommitChanges
0x180015b98  mov     ebx, eax
0x180015b9a  test    eax, eax
0x180015b9c  jz      short loc_180015BDE
0x180015b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ba5  lea     rax, WPP_GLOBAL_Control
0x180015bac  cmp     rcx, rax
0x180015baf  jz      short loc_180015BD6
0x180015bb1  test    [rcx+1Ch], dil
0x180015bb5  jz      short loc_180015BD6
0x180015bb7  mov     edx, 53h ; 'S'
0x180015bbc  mov     r9d, ebx
0x180015bbf  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015bc6  mov     rcx, [rcx+10h]
0x180015bca  call    WPP_SF_d
0x180015bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bd6  test    ebx, ebx
0x180015bd8  js      loc_180015CDD
0x180015bde  cmp     byte ptr [rsi+30h], 0
0x180015be2  jz      loc_180015C81
0x180015be8  lea     rdx, [rbp+57h+var_B0]; unsigned int *
0x180015bec  mov     rcx, [rbp+57h+var_A0]; void *
0x180015bf0  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x180015bf5  test    eax, eax
0x180015bf7  js      short loc_180015C50
0x180015bf9  lea     rdx, [rbp+57h+var_50]
0x180015bfd  mov     rcx, [rbp+57h+var_A0]
0x180015c01  call    cs:__imp_FveGetIdentity
0x180015c07  test    eax, eax
0x180015c09  js      short loc_180015C50
0x180015c0b  mov     rcx, [rsi+20h]
0x180015c0f  test    rcx, rcx
0x180015c12  jz      short loc_180015C81
0x180015c14  mov     rax, [rcx]
0x180015c17  mov     r10, [rax]
0x180015c1a  mov     eax, [rbp+57h+var_B0]
0x180015c1d  bt      eax, 0Eh
0x180015c21  jnb     short loc_180015C27
0x180015c23  xor     edx, edx
0x180015c25  jmp     short loc_180015C34
0x180015c27  and     eax, 400000h
0x180015c2c  neg     eax
0x180015c2e  sbb     edx, edx
0x180015c30  neg     edx
0x180015c32  inc     edx
0x180015c34  mov     [rsp+0E0h+var_C0], 0
0x180015c3c  lea     r9, [rbp+57h+var_60]
0x180015c40  lea     r8, [rbp+57h+var_50]
0x180015c44  mov     rax, r10
0x180015c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c4c  test    eax, eax
0x180015c4e  jns     short loc_180015C81
0x180015c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c57  lea     rdx, WPP_GLOBAL_Control
0x180015c5e  cmp     rcx, rdx
0x180015c61  jz      short loc_180015C81
0x180015c63  test    byte ptr [rcx+1Ch], 4
0x180015c67  jz      short loc_180015C81
0x180015c69  mov     edx, 54h ; 'T'
0x180015c6e  mov     r9d, eax
0x180015c71  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015c78  mov     rcx, [rcx+10h]
0x180015c7c  call    WPP_SF_d
0x180015c81  test    r15, r15
0x180015c84  jnz     short loc_180015C91
0x180015c86  movups  xmm0, [rbp+57h+var_60]
0x180015c8a  movdqu  xmmword ptr [r14], xmm0
0x180015c8f  jmp     short loc_180015CD6
0x180015c91  mov     r8, r15; struct _FVE_AUTH_ELEMENT *
0x180015c94  mov     rdx, r14; struct _GUID *
0x180015c97  mov     rcx, r12; unsigned __int16 *
0x180015c9a  call    ?GetVolumeRecoveryPassword@FveEasUtil@@SAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z; FveEasUtil::GetVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)
0x180015c9f  mov     ebx, eax
0x180015ca1  test    eax, eax
0x180015ca3  jz      short loc_180015CD6
0x180015ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cac  lea     rax, WPP_GLOBAL_Control
0x180015cb3  cmp     rcx, rax
0x180015cb6  jz      short loc_180015D08
0x180015cb8  test    [rcx+1Ch], dil
0x180015cbc  jz      short loc_180015CDD
0x180015cbe  mov     edx, 55h ; 'U'
0x180015cc3  mov     r9d, ebx
0x180015cc6  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015ccd  mov     rcx, [rcx+10h]
0x180015cd1  call    WPP_SF_d
0x180015cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cdd  lea     rdi, WPP_GLOBAL_Control
0x180015ce4  cmp     rcx, rdi
0x180015ce7  jz      short loc_180015D08
0x180015ce9  test    byte ptr [rcx+1Ch], 20h
0x180015ced  jz      short loc_180015D08
0x180015cef  mov     edx, 56h ; 'V'
0x180015cf4  mov     r9d, ebx
0x180015cf7  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015cfe  mov     rcx, [rcx+10h]
0x180015d02  call    WPP_SF_d
0x180015d07  nop
0x180015d08  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180015d0f  mov     [rbp+57h+var_A8], rax
0x180015d13  lea     rcx, [rbp+57h+var_A8]
0x180015d17  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180015d1c  mov     eax, ebx
0x180015d1e  mov     rcx, [rbp+57h+var_40]
0x180015d22  xor     rcx, rsp; StackCookie
0x180015d25  call    __security_check_cookie
0x180015d2a  add     rsp, 0B0h
0x180015d31  pop     r15
0x180015d33  pop     r14
0x180015d35  pop     r12
0x180015d37  pop     rdi
0x180015d38  pop     rsi
0x180015d39  pop     rbx
0x180015d3a  pop     rbp
0x180015d3b  retn
```
