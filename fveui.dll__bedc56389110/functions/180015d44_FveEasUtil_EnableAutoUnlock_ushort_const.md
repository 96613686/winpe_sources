# FveEasUtil::EnableAutoUnlock(ushort const *)

- ea: `0x180015d44`
- end: `0x180015f7d`
- name: `?EnableAutoUnlock@FveEasUtil@@SAJPEBG@Z`
- size: `569`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002868c`

## callees

- `0x180001bb0`
- `0x1800037a0`
- `0x180005018`
- `0x180015600`
- `0x180015d44`
- `0x180015f84`
- `0x1800179bc`
- `0x180023340`

## import_xrefs

- `FVEAPI!FveBindDataVolume` at `0x180015ee6`
- `FVEAPI!FveBindDataVolume` at `0x180015ee6`
- `FVEAPI!FveCommitChanges` at `0x180015f20`
- `FVEAPI!FveCommitChanges` at `0x180015f20`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180015e3f`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180015e3f`

## pseudocode

```c
__int64 __fastcall FveEasUtil::EnableAutoUnlock(const unsigned __int16 *a1)
{
  unsigned int FVEVolumeHandle; // eax
  int v2; // ebx
  unsigned int v3; // eax
  unsigned int v4; // eax
  PVOID *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  void **v10; // [rsp+30h] [rbp-39h] BYREF
  __int64 v11; // [rsp+38h] [rbp-31h]
  _DWORD v12[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v13; // [rsp+48h] [rbp-21h]
  __int128 v14; // [rsp+50h] [rbp-19h]
  __int128 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+70h] [rbp+7h]
  __int64 v17[2]; // [rsp+78h] [rbp+Fh] BYREF

  v12[0] = 56;
  v12[1] = 1;
  v16 = 0;
  v11 = 0;
  v10 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v13 = 0x40000;
  v14 = 0;
  v15 = 0;
  *(_OWORD *)v17 = 0;
  FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(a1, &v10, 0);
  v2 = FVEVolumeHandle;
  if ( !FVEVolumeHandle )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      104,
      &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids,
      FVEVolumeHandle);
  if ( v2 >= 0 )
  {
LABEL_10:
    v3 = FveEasUtil::EnsureVolumeDEManaged(&v10);
    v2 = v3;
    if ( !v3 )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v3);
    if ( v2 >= 0 )
    {
LABEL_11:
      v4 = FveAddAuthMethodInformation(v11, v12, v17);
      v2 = v4;
      if ( !v4 )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
LABEL_18:
        if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
          WPP_SF_S_guid_((TRACEHANDLE)v5[2], (__int64)v17);
        v6 = FveEasUtil::AllowKeyExport();
        v2 = v6;
        if ( !v6 )
          goto LABEL_26;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v6);
        if ( v2 >= 0 )
        {
LABEL_26:
          v7 = FveBindDataVolume(v11, v17);
          v2 = v7;
          if ( !v7 )
            goto LABEL_31;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v7);
          if ( v2 >= 0 )
          {
LABEL_31:
            v8 = FveCommitChanges(v11);
            v2 = v8;
            if ( v8 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 110, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v8);
          }
        }
        goto LABEL_35;
      }
      v5 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v4);
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 >= 0 )
        goto LABEL_18;
    }
  }
LABEL_35:
  v10 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close((__int64)&v10);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180015d44  push    rbp
0x180015d46  push    rbx
0x180015d47  push    rsi
0x180015d48  push    rdi
0x180015d49  push    r12
0x180015d4b  push    r15
0x180015d4d  lea     rbp, [rsp-2Fh]
0x180015d52  sub     rsp, 98h
0x180015d59  mov     rax, cs:__security_cookie
0x180015d60  xor     rax, rsp
0x180015d63  mov     [rbp+57h+var_38], rax
0x180015d67  xorps   xmm0, xmm0
0x180015d6a  mov     [rbp+57h+var_80], 38h ; '8'
0x180015d71  xor     eax, eax
0x180015d73  mov     [rbp+57h+var_7C], 1
0x180015d7a  xorps   xmm1, xmm1
0x180015d7d  mov     [rbp+57h+var_50], rax
0x180015d81  lea     r12, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180015d88  mov     [rbp+57h+var_88], rax
0x180015d8c  xor     r8d, r8d
0x180015d8f  mov     [rbp+57h+var_90], r12
0x180015d93  lea     rdx, [rbp+57h+var_90]
0x180015d97  mov     [rbp+57h+var_78], 40000h
0x180015d9f  movdqu  [rbp+57h+var_70], xmm0
0x180015da4  mov     rdi, rcx
0x180015da7  movups  [rbp+57h+var_60], xmm1
0x180015dab  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180015daf  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x180015db4  lea     rsi, WPP_GLOBAL_Control
0x180015dbb  mov     ebx, eax
0x180015dbd  lea     r15, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180015dc4  test    eax, eax
0x180015dc6  jz      short loc_180015DF6
0x180015dc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180015dcf  cmp     rcx, rsi
0x180015dd2  jz      short loc_180015DEE
0x180015dd4  test    byte ptr [rcx+1Ch], 40h
0x180015dd8  jz      short loc_180015DEE
0x180015dda  mov     rcx, [rcx+10h]
0x180015dde  mov     edx, 68h ; 'h'
0x180015de3  mov     r9d, eax
0x180015de6  mov     r8, r15
0x180015de9  call    WPP_SF_d
0x180015dee  test    ebx, ebx
0x180015df0  js      loc_180015F52
0x180015df6  lea     rcx, [rbp+57h+var_90]
0x180015dfa  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x180015dff  mov     ebx, eax
0x180015e01  test    eax, eax
0x180015e03  jz      short loc_180015E33
0x180015e05  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e0c  cmp     rcx, rsi
0x180015e0f  jz      short loc_180015E2B
0x180015e11  test    byte ptr [rcx+1Ch], 40h
0x180015e15  jz      short loc_180015E2B
0x180015e17  mov     rcx, [rcx+10h]
0x180015e1b  mov     edx, 69h ; 'i'
0x180015e20  mov     r9d, eax
0x180015e23  mov     r8, r15
0x180015e26  call    WPP_SF_d
0x180015e2b  test    ebx, ebx
0x180015e2d  js      loc_180015F52
0x180015e33  mov     rcx, [rbp+57h+var_88]
0x180015e37  lea     r8, [rbp+57h+var_48]
0x180015e3b  lea     rdx, [rbp+57h+var_80]
0x180015e3f  call    cs:__imp_FveAddAuthMethodInformation
0x180015e45  mov     ebx, eax
0x180015e47  test    eax, eax
0x180015e49  jz      short loc_180015E82
0x180015e4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e52  cmp     rcx, rsi
0x180015e55  jz      short loc_180015E78
0x180015e57  test    byte ptr [rcx+1Ch], 40h
0x180015e5b  jz      short loc_180015E78
0x180015e5d  mov     rcx, [rcx+10h]
0x180015e61  mov     edx, 6Ah ; 'j'
0x180015e66  mov     r9d, eax
0x180015e69  mov     r8, r15
0x180015e6c  call    WPP_SF_d
0x180015e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e78  test    ebx, ebx
0x180015e7a  js      loc_180015F52
0x180015e80  jmp     short loc_180015E89
0x180015e82  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e89  cmp     rcx, rsi
0x180015e8c  jz      short loc_180015EA9
0x180015e8e  test    byte ptr [rcx+1Ch], 8
0x180015e92  jz      short loc_180015EA9
0x180015e94  mov     rcx, [rcx+10h]; LoggerHandle
0x180015e98  lea     rax, [rbp+57h+var_48]
0x180015e9c  mov     r9, rdi
0x180015e9f  mov     [rsp+0C0h+var_A0], rax; __int64
0x180015ea4  call    WPP_SF_S_guid_
0x180015ea9  call    ?AllowKeyExport@FveEasUtil@@CAJXZ; FveEasUtil::AllowKeyExport(void)
0x180015eae  mov     ebx, eax
0x180015eb0  test    eax, eax
0x180015eb2  jz      short loc_180015EDE
0x180015eb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ebb  cmp     rcx, rsi
0x180015ebe  jz      short loc_180015EDA
0x180015ec0  test    byte ptr [rcx+1Ch], 40h
0x180015ec4  jz      short loc_180015EDA
0x180015ec6  mov     rcx, [rcx+10h]
0x180015eca  mov     edx, 6Ch ; 'l'
0x180015ecf  mov     r9d, eax
0x180015ed2  mov     r8, r15
0x180015ed5  call    WPP_SF_d
0x180015eda  test    ebx, ebx
0x180015edc  js      short loc_180015F52
0x180015ede  mov     rcx, [rbp+57h+var_88]
0x180015ee2  lea     rdx, [rbp+57h+var_48]
0x180015ee6  call    cs:__imp_FveBindDataVolume
0x180015eec  mov     ebx, eax
0x180015eee  test    eax, eax
0x180015ef0  jz      short loc_180015F1C
0x180015ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ef9  cmp     rcx, rsi
0x180015efc  jz      short loc_180015F18
0x180015efe  test    byte ptr [rcx+1Ch], 40h
0x180015f02  jz      short loc_180015F18
0x180015f04  mov     rcx, [rcx+10h]
0x180015f08  mov     edx, 6Dh ; 'm'
0x180015f0d  mov     r9d, eax
0x180015f10  mov     r8, r15
0x180015f13  call    WPP_SF_d
0x180015f18  test    ebx, ebx
0x180015f1a  js      short loc_180015F52
0x180015f1c  mov     rcx, [rbp+57h+var_88]
0x180015f20  call    cs:__imp_FveCommitChanges
0x180015f26  mov     ebx, eax
0x180015f28  test    eax, eax
0x180015f2a  jz      short loc_180015F52
0x180015f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015f33  cmp     rcx, rsi
0x180015f36  jz      short loc_180015F52
0x180015f38  test    byte ptr [rcx+1Ch], 40h
0x180015f3c  jz      short loc_180015F52
0x180015f3e  mov     rcx, [rcx+10h]
0x180015f42  mov     edx, 6Eh ; 'n'
0x180015f47  mov     r9d, eax
0x180015f4a  mov     r8, r15
0x180015f4d  call    WPP_SF_d
0x180015f52  lea     rcx, [rbp+57h+var_90]
0x180015f56  mov     [rbp+57h+var_90], r12
0x180015f5a  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180015f5f  mov     eax, ebx
0x180015f61  mov     rcx, [rbp+57h+var_38]
0x180015f65  xor     rcx, rsp; StackCookie
0x180015f68  call    __security_check_cookie
0x180015f6d  add     rsp, 98h
0x180015f74  pop     r15
0x180015f76  pop     r12
0x180015f78  pop     rdi
0x180015f79  pop     rsi
0x180015f7a  pop     rbx
0x180015f7b  pop     rbp
0x180015f7c  retn
```
