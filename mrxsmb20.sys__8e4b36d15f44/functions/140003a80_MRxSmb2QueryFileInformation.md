# MRxSmb2QueryFileInformation

- ea: `0x140003a80`
- end: `0x14000408f`
- name: `MRxSmb2QueryFileInformation`
- size: `1551`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140003a80`
- `0x1400040a0`
- `0x140004640`
- `0x1400054c0`
- `0x140005630`
- `0x140029764`
- `0x1400552e0`
- `0x140055650`
- `0x1400575a0`

## import_xrefs

- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140003bf9`
- `mrxsmb!MRxSmbGetInstanceConfigurationBlock` at `0x140003bf9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140003cf9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140003f33`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140003cf9`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140003f33`
- `mrxsmb!SmbCeInitiateExchange` at `0x140003cd4`
- `mrxsmb!SmbCeInitiateExchange` at `0x140003cd4`
- `mrxsmb!SmbCeInitializeExchange` at `0x140003c6f`
- `mrxsmb!SmbCeInitializeExchange` at `0x140003c6f`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140003e72`
- `mrxsmb!SmbCeCheckServerEntryDialect` at `0x140003e72`

## pseudocode

```c
__int64 __fastcall MRxSmb2QueryFileInformation(__int64 a1)
{
  __int64 v1; // rdx
  unsigned int *v2; // r15
  unsigned int v3; // r14d
  __int64 v4; // rdi
  __int64 v6; // rax
  _QWORD *v7; // r13
  __int64 v8; // rsi
  __int64 v9; // r12
  unsigned int FileInformationFromDirCache; // esi
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  bool v15; // r8
  __int64 v16; // r8
  int v17; // esi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 InstanceConfigurationBlock; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // r14d
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rcx
  PDEVICE_OBJECT v27; // rcx
  int FileInfoFromCache; // eax
  __int64 v29; // rdx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // [rsp+90h] [rbp+48h] BYREF
  unsigned int v33; // [rsp+98h] [rbp+50h] BYREF
  int v34; // [rsp+A0h] [rbp+58h] BYREF
  __int64 v35; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *(_QWORD *)(a1 + 72);
  v2 = (unsigned int *)(a1 + 472);
  v3 = *(_DWORD *)(a1 + 472);
  v4 = *(unsigned int *)(a1 + 448);
  v35 = 0;
  v6 = *(_QWORD *)(v1 + 40);
  v34 = 0;
  v33 = v3;
  LODWORD(v32) = v3;
  v7 = *(_QWORD **)(v6 + 40);
  v8 = v7[53];
  v9 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL);
  if ( (_DWORD)v4 == 0xFFFF )
  {
    __debugbreak();
LABEL_3:
    if ( *(_BYTE *)(v8 + 188) == 1 )
    {
      if ( (unsigned int)v4 >= 0x29
        || !*((_BYTE *)Smb2AllowedQueryInfoLevels_PIPE + v4)
        || (*(_DWORD *)(*(_QWORD *)(v1 + 48) + 8LL) & 1) != 0 )
      {
        return (unsigned int)-1073741637;
      }
    }
    else
    {
      if ( (unsigned int)v4 >= 0x3C || !*((_BYTE *)Smb2AllowedQueryInfoLevels_FILE + v4) )
        return (unsigned int)-1073741637;
      if ( (_DWORD)v4 == 48 )
      {
        if ( (unsigned __int8)SmbCeCheckServerEntryDialect(*(_QWORD *)(v7[52] + 384LL), 3, 0, 2)
          || (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 1314LL) & 4) != 0 )
        {
          if ( (*(_DWORD *)(v9 + 8) & 2) == 0 )
            goto LABEL_13;
          Smb2FetchVolumeFeatureSupportFromCache(v26, v7[53] + 928LL, *(_QWORD *)(v9 + 32), &v34);
          if ( (v34 & 1) == 0 )
            goto LABEL_13;
          FileInformationFromDirCache = -1073741637;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return FileInformationFromDirCache;
          }
          v31 = 14;
        }
        else
        {
          FileInformationFromDirCache = -1073741637;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || !BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            return FileInformationFromDirCache;
          }
          v31 = 13;
        }
        WPP_SF_d(v27->AttachedDevice, v31, WPP_df594d904eb23382f7a5bd2448918cda_Traceguids, 3221225659LL);
        return FileInformationFromDirCache;
      }
    }
    if ( (_DWORD)v4 == 6 )
    {
      v25 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL);
      if ( (*(_DWORD *)(v25 + 8) & 2) != 0 )
      {
        if ( v3 < 8 )
        {
          return (unsigned int)-1073741789;
        }
        else
        {
          FileInformationFromDirCache = 0;
          **(_QWORD **)(a1 + 456) = *(_QWORD *)(v25 + 24);
          *v2 = v3 - 8;
        }
        return FileInformationFromDirCache;
      }
    }
LABEL_13:
    v12 = *(_QWORD *)(a1 + 56);
    v13 = *(_QWORD *)(v12 + 120);
    v14 = *(_QWORD *)(v13 + 32);
    v15 = (*(_DWORD *)(v14 + 96) & 0x80u) == 0
       && (*(_BYTE *)(*(_QWORD *)(v14 + 32) + 764LL) & 2) != 0
       && (*(_DWORD *)(v12 + 156) & 0x4000000) == 0
       && (*(_DWORD *)(*(_QWORD *)(v12 + 136) + 8LL) & 1) == 0
       && !*(_BYTE *)(v13 + 77)
       && (*(_DWORD *)(a1 + 120) & 0x10000000) == 0;
    if ( (*(_WORD *)v12 != 0xEC22
       || (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 120LL) & 0x27) == 0
       || (*(_BYTE *)(v12 + 256) & 1) == 0 && (*(_DWORD *)(v12 + 164) & 1) != 0)
      && v15 )
    {
      FileInfoFromCache = Smb2FetchFileInfoFromCache(
                            a1,
                            v8 + 376,
                            1,
                            *(unsigned int *)(a1 + 448),
                            0,
                            *(_QWORD *)(a1 + 456),
                            &v33);
      FileInformationFromDirCache = FileInfoFromCache;
      if ( FileInfoFromCache != -1073741802 )
      {
        if ( FileInfoFromCache < 0 )
          return FileInformationFromDirCache;
        goto LABEL_67;
      }
      if ( (*(_DWORD *)(*(_QWORD *)(a1 + 72) + 120LL) & 0x27) == 0 )
      {
        FileInformationFromDirCache = Smb2QueryFileInformationFromDirCache(
                                        a1,
                                        v29,
                                        0,
                                        *(_DWORD *)(a1 + 448),
                                        *(_BYTE **)(a1 + 456),
                                        v2);
        if ( FileInformationFromDirCache != -1073741802 )
          return FileInformationFromDirCache;
      }
    }
    v16 = *(_QWORD *)(a1 + 56);
    v17 = *(_DWORD *)(a1 + 448);
    v18 = *(_QWORD *)(v16 + 120);
    v19 = *(_QWORD *)(v18 + 32);
    if ( (*(_DWORD *)(v19 + 96) & 0x80u) != 0
      || (*(_BYTE *)(*(_QWORD *)(v19 + 32) + 764LL) & 2) == 0
      || (*(_DWORD *)(*(_QWORD *)(v16 + 136) + 8LL) & 1) != 0
      || *(_BYTE *)(v18 + 77)
      || (v24 = *(_QWORD *)(a1 + 72),
          LOBYTE(v32) = 1,
          (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v24 + 40) + 40LL) + 424LL) + 184LL) & 0x800000) != 0) )
    {
      LOBYTE(v32) = 0;
    }
    InstanceConfigurationBlock = MRxSmbGetInstanceConfigurationBlock(*(_QWORD *)(a1 + 80));
    v21 = 0;
    if ( *(_DWORD *)(InstanceConfigurationBlock + 12) )
      v21 = (unsigned __int8)v32;
    if ( (unsigned int)(v17 - 4) > 1 && (unsigned int)(v17 - 34) > 1 || !(_BYTE)v21 )
    {
LABEL_27:
      v22 = *(_QWORD *)(a1 + 72);
      v23 = *(_DWORD *)(a1 + 448);
      v32 = 0;
      FileInformationFromDirCache = SmbCeInitializeExchange(
                                      &v32,
                                      a1,
                                      0,
                                      0,
                                      0,
                                      *(_QWORD *)(*(_QWORD *)(v22 + 40) + 40LL),
                                      2600,
                                      &QueryInfoDispatch);
      if ( !FileInformationFromDirCache )
      {
        *(_DWORD *)(v32 + 2424) = v23;
        *(_DWORD *)(v32 + 2420) = 1;
        *(_QWORD *)(v32 + 2408) = *(_QWORD *)(a1 + 456);
        *(_DWORD *)(v32 + 2416) = *v2;
        if ( v23 == 15 )
        {
          *(_DWORD *)(v32 + 2428) = 0;
          *(_QWORD *)(v32 + 2440) = *(_QWORD *)(a1 + 512);
          *(_DWORD *)(v32 + 2448) = *(_DWORD *)(a1 + 520);
          *(_DWORD *)(v32 + 2432) = *(_DWORD *)(a1 + 524);
        }
        _InterlockedOr((volatile signed __int32 *)(v32 + 68), 1u);
        FileInformationFromDirCache = SmbCeInitiateExchange(v32);
        if ( FileInformationFromDirCache == 259 )
          FileInformationFromDirCache = SmbCeWaitForCompletionAndFinalizeExchangeEx(v32, 0, 0, 0);
        else
          SmbCeWaitForCompletionAndFinalizeExchangeEx(v32, 0, 0, 0);
      }
      if ( (_DWORD)v4 == 48
        && (*(_DWORD *)(v9 + 8) & 2) != 0
        && (FileInformationFromDirCache == -1073741637 || FileInformationFromDirCache + 1073741822 <= 1) )
      {
        Smb2UpdateVolumeFeatureSupportCacheEntry(
          a1,
          (struct _NAME_CACHE_CONTROL_ *)(v7[53] + 928LL),
          *(_QWORD *)(v9 + 32),
          1,
          FileInformationFromDirCache);
      }
      return FileInformationFromDirCache;
    }
    FileInformationFromDirCache = Smb2StartPopulateFileInfoCache(a1, v21, &v35);
    if ( (FileInformationFromDirCache & 0x80000000) != 0 )
      return FileInformationFromDirCache;
    v30 = Smb2FinishPopulateFileInfoCache(a1, v35, *(_QWORD *)(a1 + 456), &v33);
    FileInformationFromDirCache = v30;
    if ( v30 < 0 )
    {
      if ( v30 != -1073741802 )
        return FileInformationFromDirCache;
      *v2 = v3;
      goto LABEL_27;
    }
LABEL_67:
    *v2 = v3 - v33;
    return FileInformationFromDirCache;
  }
  if ( (_DWORD)v4 != 55 )
    goto LABEL_3;
  FileInformationFromDirCache = Smb2QueryProtocolInformation(v7, *(_QWORD *)(v1 + 48), *(_QWORD *)(a1 + 456), &v32);
  if ( (FileInformationFromDirCache & 0x80000000) == 0 )
    *v2 -= v32;
  return FileInformationFromDirCache;
}

```

## disassembly

```asm
0x140003a80  push    rbp
0x140003a82  push    rbx
0x140003a83  push    rsi
0x140003a84  push    rdi
0x140003a85  push    r12
0x140003a87  push    r13
0x140003a89  push    r14
0x140003a8b  push    r15
0x140003a8d  mov     rbp, rsp
0x140003a90  sub     rsp, 48h
0x140003a94  mov     rdx, [rcx+48h]
0x140003a98  lea     r15, [rcx+1D8h]
0x140003a9f  mov     r14d, [r15]
0x140003aa2  xor     r8d, r8d
0x140003aa5  mov     edi, [rcx+1C0h]
0x140003aab  mov     rbx, rcx
0x140003aae  mov     [rbp+arg_18], r8
0x140003ab2  mov     rax, [rdx+28h]
0x140003ab6  mov     [rbp+arg_10], r8d
0x140003aba  mov     [rbp+arg_8], r14d
0x140003abe  mov     dword ptr [rbp+arg_0], r14d
0x140003ac2  mov     r13, [rax+28h]
0x140003ac6  mov     rax, [rcx+38h]
0x140003aca  mov     rsi, [r13+1A8h]
0x140003ad1  mov     r12, [rax+88h]
0x140003ad8  cmp     edi, 0FFFFh
0x140003ade  jz      loc_140004029
0x140003ae4  cmp     edi, 37h ; '7'
0x140003ae7  jz      loc_140003D5E
0x140003aed  cmp     byte ptr [rsi+0BCh], 1
0x140003af4  jnz     short loc_140003B30
0x140003af6  cmp     edi, 29h ; ')'
0x140003af9  jnb     short loc_140003B17
0x140003afb  lea     rcx, cs:140000000h
0x140003b02  cmp     [rdi+rcx+3F618h], r8b
0x140003b0a  jz      short loc_140003B17
0x140003b0c  mov     rcx, [rdx+30h]
0x140003b10  mov     eax, [rcx+8]
0x140003b13  test    al, 1
0x140003b15  jz      short loc_140003B4F
0x140003b17  mov     esi, 0C00000BBh
0x140003b1c  mov     eax, esi
0x140003b1e  add     rsp, 48h
0x140003b22  pop     r15
0x140003b24  pop     r14
0x140003b26  pop     r13
0x140003b28  pop     r12
0x140003b2a  pop     rdi
0x140003b2b  pop     rsi
0x140003b2c  pop     rbx
0x140003b2d  pop     rbp
0x140003b2e  retn
0x140003b30  cmp     edi, 3Ch ; '<'
0x140003b33  jnb     short loc_140003B17
0x140003b35  lea     rcx, cs:140000000h
0x140003b3c  cmp     [rdi+rcx+3F648h], r8b
0x140003b44  jz      short loc_140003B17
0x140003b46  cmp     edi, 30h ; '0'
0x140003b49  jz      loc_140003E59
0x140003b4f  cmp     edi, 6
0x140003b52  jz      loc_140003E1C
0x140003b58  mov     rdx, [rbx+38h]
0x140003b5c  mov     r8, [rdx+78h]
0x140003b60  mov     rcx, [r8+20h]
0x140003b64  mov     eax, [rcx+60h]
0x140003b67  test    al, al
0x140003b69  js      loc_140003D8A
0x140003b6f  mov     rax, [rcx+20h]
0x140003b73  test    byte ptr [rax+2FCh], 2
0x140003b7a  jz      loc_140003D8A
0x140003b80  test    dword ptr [rdx+9Ch], 4000000h
0x140003b8a  jnz     loc_140003D8A
0x140003b90  mov     rax, [rdx+88h]
0x140003b97  mov     ecx, [rax+8]
0x140003b9a  test    cl, 1
0x140003b9d  jnz     loc_140003D8A
0x140003ba3  cmp     byte ptr [r8+4Dh], 0
0x140003ba8  jnz     loc_140003D8A
0x140003bae  mov     r8d, [rbx+78h]
0x140003bb2  shr     r8d, 1Ch
0x140003bb6  not     r8b
0x140003bb9  and     r8b, 1
0x140003bbd  mov     eax, 0EC22h
0x140003bc2  cmp     [rdx], ax
0x140003bc5  jz      loc_140003D92
0x140003bcb  test    r8b, r8b
0x140003bce  jnz     loc_140003F44
0x140003bd4  mov     r8, [rbx+38h]
0x140003bd8  mov     esi, [rbx+1C0h]
0x140003bde  mov     rdx, [r8+78h]
0x140003be2  mov     rcx, [rdx+20h]
0x140003be6  mov     eax, [rcx+60h]
0x140003be9  test    al, al
0x140003beb  jns     loc_140003DC2
0x140003bf1  mov     byte ptr [rbp+arg_0], 0
0x140003bf5  mov     rcx, [rbx+50h]
0x140003bf9  call    cs:__imp_MRxSmbGetInstanceConfigurationBlock
0x140003c00  nop     dword ptr [rax+rax+00h]
0x140003c05  movzx   ecx, byte ptr [rbp+arg_0]
0x140003c09  xor     edx, edx
0x140003c0b  cmp     [rax+0Ch], edx
0x140003c0e  lea     eax, [rsi-4]
0x140003c11  cmovnz  edx, ecx
0x140003c14  cmp     eax, 1
0x140003c17  ja      loc_140004039
0x140003c1d  test    dl, dl
0x140003c1f  jnz     loc_140003FDF
0x140003c25  mov     rax, [rbx+48h]
0x140003c29  lea     rcx, QueryInfoDispatch
0x140003c30  mov     r14d, [rbx+1C0h]
0x140003c37  xor     r9d, r9d
0x140003c3a  mov     [rsp+48h+var_10], rcx
0x140003c3f  xor     r8d, r8d
0x140003c42  mov     [rbp+arg_0], 0
0x140003c4a  lea     rcx, [rbp+arg_0]
0x140003c4e  mov     rax, [rax+28h]
0x140003c52  mov     rdx, rbx
0x140003c55  mov     dword ptr [rsp+48h+var_18], 0A28h
0x140003c5d  mov     rax, [rax+28h]
0x140003c61  mov     [rsp+48h+var_20], rax
0x140003c66  mov     [rsp+48h+var_28], 0
0x140003c6f  call    cs:__imp_SmbCeInitializeExchange
0x140003c76  nop     dword ptr [rax+rax+00h]
0x140003c7b  mov     esi, eax
0x140003c7d  test    eax, eax
0x140003c7f  jnz     loc_140003D07
0x140003c85  mov     rax, [rbp+arg_0]
0x140003c89  mov     [rax+978h], r14d
0x140003c90  mov     rax, [rbp+arg_0]
0x140003c94  mov     dword ptr [rax+974h], 1
0x140003c9e  mov     rax, [rbp+arg_0]
0x140003ca2  mov     rcx, [rbx+1C8h]
0x140003ca9  mov     [rax+968h], rcx
0x140003cb0  mov     rax, [rbp+arg_0]
0x140003cb4  mov     ecx, [r15]
0x140003cb7  mov     [rax+970h], ecx
0x140003cbd  cmp     r14d, 0Fh
0x140003cc1  jz      loc_14000404A
0x140003cc7  mov     rax, [rbp+arg_0]
0x140003ccb  lock or dword ptr [rax+44h], 1
0x140003cd0  mov     rcx, [rbp+arg_0]
0x140003cd4  call    cs:__imp_SmbCeInitiateExchange
0x140003cdb  nop     dword ptr [rax+rax+00h]
0x140003ce0  mov     rcx, [rbp+arg_0]
0x140003ce4  xor     r9d, r9d
0x140003ce7  xor     r8d, r8d
0x140003cea  xor     edx, edx
0x140003cec  mov     esi, eax
0x140003cee  cmp     eax, 103h
0x140003cf3  jnz     loc_140003F33
0x140003cf9  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140003d00  nop     dword ptr [rax+rax+00h]
0x140003d05  mov     esi, eax
0x140003d07  cmp     edi, 30h ; '0'
0x140003d0a  jnz     loc_140003B1C
0x140003d10  mov     eax, [r12+8]
0x140003d15  test    al, 2
0x140003d17  jz      loc_140003B1C
0x140003d1d  cmp     esi, 0C00000BBh
0x140003d23  jz      short loc_140003D34
0x140003d25  lea     eax, [rsi+3FFFFFFEh]
0x140003d2b  cmp     eax, 1
0x140003d2e  ja      loc_140003B1C
0x140003d34  mov     rdx, [r13+1A8h]
0x140003d3b  mov     r9d, 1
0x140003d41  mov     r8, [r12+20h]
0x140003d46  add     rdx, 3A0h
0x140003d4d  mov     rcx, rbx
0x140003d50  mov     dword ptr [rsp+48h+var_28], esi
0x140003d54  call    Smb2UpdateVolumeFeatureSupportCacheEntry
0x140003d59  jmp     loc_140003B1C
0x140003d5e  mov     r8, [rcx+1C8h]
0x140003d65  lea     r9, [rbp+arg_0]
0x140003d69  mov     rdx, [rdx+30h]
0x140003d6d  mov     rcx, r13
0x140003d70  call    Smb2QueryProtocolInformation
0x140003d75  mov     esi, eax
0x140003d77  test    eax, eax
0x140003d79  js      loc_140003B1C
0x140003d7f  mov     ecx, dword ptr [rbp+arg_0]
0x140003d82  sub     [r15], ecx
0x140003d85  jmp     loc_140003B1C
0x140003d8a  xor     r8b, r8b
0x140003d8d  jmp     loc_140003BBD
0x140003d92  mov     rax, [rbx+48h]
0x140003d96  mov     ecx, [rax+78h]
0x140003d99  test    cl, 27h
0x140003d9c  jz      loc_140003BCB
0x140003da2  test    byte ptr [rdx+100h], 1
0x140003da9  jnz     loc_140003BD4
0x140003daf  mov     eax, [rdx+0A4h]
0x140003db5  test    al, 1
0x140003db7  jnz     loc_140003BCB
0x140003dbd  jmp     loc_140003BD4
0x140003dc2  mov     rax, [rcx+20h]
0x140003dc6  test    byte ptr [rax+2FCh], 2
0x140003dcd  jz      loc_140003BF1
0x140003dd3  mov     rax, [r8+88h]
0x140003dda  mov     ecx, [rax+8]
0x140003ddd  test    cl, 1
0x140003de0  jnz     loc_140003BF1
0x140003de6  cmp     byte ptr [rdx+4Dh], 0
0x140003dea  jnz     loc_140003BF1
0x140003df0  mov     rax, [rbx+48h]
0x140003df4  mov     byte ptr [rbp+arg_0], 1
0x140003df8  mov     rcx, [rax+28h]
0x140003dfc  mov     rax, [rcx+28h]
0x140003e00  mov     rcx, [rax+1A8h]
0x140003e07  test    dword ptr [rcx+0B8h], 800000h
0x140003e11  jnz     loc_140003BF1
0x140003e17  jmp     loc_140003BF5
0x140003e1c  mov     rax, [rbx+38h]
0x140003e20  mov     rdx, [rax+88h]
0x140003e27  mov     eax, [rdx+8]
0x140003e2a  test    al, 2
0x140003e2c  jz      loc_140003B58
0x140003e32  cmp     r14d, 8
0x140003e36  jb      loc_14000402F
0x140003e3c  mov     rax, [rdx+18h]
0x140003e40  mov     esi, r8d
0x140003e43  mov     rcx, [rbx+1C8h]
0x140003e4a  mov     [rcx], rax
0x140003e4d  lea     eax, [r14-8]
0x140003e51  mov     [r15], eax
0x140003e54  jmp     loc_140003B1C
0x140003e59  mov     rcx, [r13+1A0h]
0x140003e60  mov     r9d, 2
0x140003e66  mov     edx, 3
0x140003e6b  mov     rcx, [rcx+180h]
0x140003e72  call    cs:__imp_SmbCeCheckServerEntryDialect
0x140003e79  nop     dword ptr [rax+rax+00h]
0x140003e7e  test    al, al
0x140003e80  jz      short loc_140003EEB
0x140003e82  mov     eax, [r12+8]
0x140003e87  test    al, 2
0x140003e89  jz      loc_140003B58
0x140003e8f  mov     rdx, [r13+1A8h]
0x140003e96  lea     r9, [rbp+arg_10]
0x140003e9a  mov     r8, [r12+20h]
0x140003e9f  add     rdx, 3A0h
0x140003ea6  call    Smb2FetchVolumeFeatureSupportFromCache
0x140003eab  test    byte ptr [rbp+arg_10], 1
0x140003eaf  jz      loc_140003B58
0x140003eb5  mov     esi, 0C00000BBh
0x140003eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140003ec1  lea     rax, WPP_GLOBAL_Control
0x140003ec8  cmp     rcx, rax
0x140003ecb  jz      loc_140003B1C
0x140003ed1  mov     eax, [rcx+2Ch]
0x140003ed4  test    al, 1
0x140003ed6  jz      loc_140003B1C
0x140003edc  cmp     byte ptr [rcx+29h], 1
0x140003ee0  jb      loc_140003B1C
0x140003ee6  jmp     loc_140038324
0x140003eeb  mov     rax, [rbx+50h]
0x140003eef  test    byte ptr [rax+522h], 4
0x140003ef6  jnz     short loc_140003E82
0x140003ef8  mov     esi, 0C00000BBh
0x140003efd  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f04  lea     rax, WPP_GLOBAL_Control
0x140003f0b  cmp     rcx, rax
0x140003f0e  jz      loc_140003B1C
0x140003f14  mov     eax, [rcx+2Ch]
0x140003f17  test    al, 1
0x140003f19  jz      loc_140003B1C
0x140003f1f  cmp     byte ptr [rcx+29h], 1
0x140003f23  jb      loc_140003B1C
0x140003f29  mov     edx, 0Dh
0x140003f2e  jmp     loc_140038329
0x140003f33  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140003f3a  nop     dword ptr [rax+rax+00h]
0x140003f3f  jmp     loc_140003D07
0x140003f44  mov     r9d, [rbx+1C0h]
0x140003f4b  lea     rax, [rbp+arg_8]
0x140003f4f  mov     [rsp+48h+var_18], rax
0x140003f54  lea     rdx, [rsi+178h]
0x140003f5b  mov     rax, [rbx+1C8h]
0x140003f62  mov     r8d, 1
0x140003f68  mov     [rsp+48h+var_20], rax
0x140003f6d  mov     rcx, rbx
0x140003f70  mov     dword ptr [rsp+48h+var_28], 0
0x140003f78  call    Smb2FetchFileInfoFromCache
0x140003f7d  mov     esi, eax
0x140003f7f  cmp     eax, 0C0000016h
0x140003f84  jz      short loc_140003F9A
0x140003f86  test    eax, eax
0x140003f88  js      loc_140003B1C
0x140003f8e  sub     r14d, [rbp+arg_8]
0x140003f92  mov     [r15], r14d
0x140003f95  jmp     loc_140003B1C
0x140003f9a  mov     rax, [rbx+48h]
0x140003f9e  mov     ecx, [rax+78h]
0x140003fa1  test    cl, 27h
0x140003fa4  jnz     loc_140003BD4
0x140003faa  mov     rax, [rbx+1C8h]
0x140003fb1  xor     r8d, r8d
0x140003fb4  mov     r9d, [rbx+1C0h]
0x140003fbb  mov     rcx, rbx
0x140003fbe  mov     [rsp+48h+var_20], r15
0x140003fc3  mov     [rsp+48h+var_28], rax
  ... truncated ...
```
