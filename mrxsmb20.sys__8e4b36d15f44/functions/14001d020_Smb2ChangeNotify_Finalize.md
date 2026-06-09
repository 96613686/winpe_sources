# Smb2ChangeNotify_Finalize

- ea: `0x14001d020`
- end: `0x14001d41c`
- name: `Smb2ChangeNotify_Finalize`
- size: `1020`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14001d020`
- `0x140022700`
- `0x140029b0c`
- `0x140029c14`
- `0x1400375c0`
- `0x140055eb0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d219`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d29b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d219`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d29b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d177`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d26b`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d177`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d26b`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14001d1f4`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14001d286`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14001d1f4`
- `rdbss!RxNameCacheExpireEntriesWithPrefixEx` at `0x14001d286`
- `rdbss!RxNameCacheExpireEntry` at `0x14001d1bc`
- `rdbss!RxNameCacheExpireEntry` at `0x14001d1bc`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001d1a5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001d1d6`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001d1a5`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14001d1d6`
- `rdbss!RxCrackPathName` at `0x14001d162`
- `rdbss!RxCrackPathName` at `0x14001d162`
- `rdbss!RxLowIoCompletion` at `0x14001d2aa`
- `rdbss!RxLowIoCompletion` at `0x14001d2aa`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14001d256`
- `mrxsmb!MRxSmbIsStreamFile` at `0x14001d256`
- `mrxsmb!FsRtlValidateChangeNotifyBufferEx` at `0x14001d0b3`
- `mrxsmb!FsRtlValidateChangeNotifyBufferEx` at `0x14001d0b3`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001d0da`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001d0da`

## pseudocode

```c
__int64 __fastcall Smb2ChangeNotify_Finalize(__int64 a1)
{
  int v1; // edi
  __int64 v2; // rsi
  __int64 v4; // r14
  __int64 v5; // rcx
  __int64 v6; // rbx
  int v7; // ecx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rax
  char v12; // bl
  __int64 v13; // rcx
  struct _NAME_CACHE_CONTROL_ *v14; // rbp
  __int64 v15; // r8
  struct _NAME_CACHE *i; // rax
  __int64 v17; // rbx
  __int64 v18; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // rcx
  unsigned __int64 v22; // rax
  __int64 v23; // rcx
  _OWORD v24[13]; // [rsp+30h] [rbp-D8h] BYREF
  int v25; // [rsp+110h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 16);
  v2 = *(_QWORD *)(a1 + 48);
  v4 = *(_QWORD *)(a1 + 88);
  v25 = 0;
  if ( v1 < 0 && *(_BYTE *)(a1 + 2540) )
    Smb2UpdateDirInfoCacheLifeTime(v2, *(_QWORD *)(v4 + 424) + 1112LL, *(unsigned int *)(a1 + 2536));
  v5 = *(_QWORD *)(a1 + 160);
  *(_QWORD *)(v2 + 184) = 0;
  v6 = v5 - 8;
  if ( v5 == a1 + 160 )
    v6 = 0;
  if ( v6 )
  {
    if ( v1 >= 0 )
    {
      v1 = *(_DWORD *)(v6 + 48);
      if ( v1 >= 0 )
      {
        v7 = *(_DWORD *)(v6 + 748);
        if ( v7
          && (v8 = FsRtlValidateChangeNotifyBufferEx(
                     &v25,
                     0,
                     (unsigned int)v1,
                     *(_QWORD *)(v6 + 712),
                     v7,
                     *(_BYTE *)(a1 + 2506) & 1),
              v8 < 0) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_dD(WPP_GLOBAL_Control->AttachedDevice, v9, v10, (unsigned int)v8, v25);
          }
          v1 = -1073741629;
        }
        else
        {
          *(_QWORD *)(v2 + 184) = *(unsigned int *)(v6 + 748);
        }
      }
    }
    SmbCseFinalizeBufferContext(v6);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v4 + 424) + 176LL) & 0x80u) != 0 )
  {
    if ( (v20 = (unsigned int)(v1 + 1073741667), (unsigned int)v20 <= 0x2F)
      && (v21 = 0x900281000001LL, _bittest64(&v21, v20))
      || v1 == -1069481983
      || v1 == -1073740964
      || v1 == -1073740672
      || v1 == -1073741202
      || (v22 = (unsigned int)(v1 + 1073741309), (unsigned int)v22 <= 0x3E)
      && (v23 = 0x4208040000000601LL, _bittest64(&v23, v22))
      || v1 == -1073741507
      || v1 == -1073741073
      || (unsigned int)(v1 + 1073740698) <= 1
      || v1 == -1073741810
      || v1 == -2146893022
      || v1 == -2147483631 )
    {
      v1 = 268;
    }
  }
  v11 = *(_QWORD *)(v2 + 56);
  *(_DWORD *)(v2 + 176) = v1;
  if ( (*(_DWORD *)(v11 + 164) & 1) == 0 )
  {
    v12 = *(_BYTE *)(v2 + 536);
    Smb2InvalidateFileIdentityCacheEntryEx(v2, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 424) + 192LL), 0, 1);
    v13 = *(_QWORD *)(v2 + 56) + 360LL;
    v14 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v4 + 424) + 1112LL);
    v24[0] = 0;
    RxCrackPathName(v13, 0, v24, 0);
    ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
    if ( v12 )
    {
      LOBYTE(v15) = 1;
      RxNameCacheExpireEntriesWithPrefixEx(v14, v24, v15);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
          v2,
          (__int64)v24);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
          v2,
          (__int64)v24);
      }
      for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v14, v24, 0, 0);
            i;
            i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v14, v24, 0, 0) )
      {
        RxNameCacheExpireEntry(v14, i);
      }
    }
    ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
    v17 = *(_QWORD *)(v4 + 424);
    memset(v24, 0, 152);
    MRxSmbIsStreamFile(*(_QWORD *)(v2 + 56) + 360LL, v24);
    ExAcquirePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
    LOBYTE(v18) = 1;
    RxNameCacheExpireEntriesWithPrefixEx(v17 + 560, v24, v18);
    ExReleasePushLockExclusiveEx(&Smb2FileNotFoundCacheLock, 0);
  }
  RxLowIoCompletion((PRX_CONTEXT)v2);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14001d020  push    rbx
0x14001d022  push    rbp
0x14001d023  push    rsi
0x14001d024  push    rdi
0x14001d025  push    r14
0x14001d027  push    r15
0x14001d029  sub     rsp, 0D8h
0x14001d030  mov     edi, [rcx+10h]
0x14001d033  xor     r15d, r15d
0x14001d036  mov     rsi, [rcx+30h]
0x14001d03a  mov     rbp, rcx
0x14001d03d  mov     r14, [rcx+58h]
0x14001d041  mov     [rsp+108h+arg_0], r15d
0x14001d049  test    edi, edi
0x14001d04b  js      loc_14001D370
0x14001d051  lea     rdx, [rbp+0A0h]
0x14001d058  mov     rcx, [rdx]
0x14001d05b  cmp     rcx, rdx
0x14001d05e  mov     [rsi+0B8h], r15
0x14001d065  lea     rbx, [rcx-8]
0x14001d069  cmovz   rbx, r15
0x14001d06d  lea     r15, WPP_GLOBAL_Control
0x14001d074  test    rbx, rbx
0x14001d077  jz      short loc_14001D0E6
0x14001d079  test    edi, edi
0x14001d07b  js      short loc_14001D0D7
0x14001d07d  mov     edi, [rbx+30h]
0x14001d080  test    edi, edi
0x14001d082  js      short loc_14001D0D7
0x14001d084  mov     ecx, [rbx+2ECh]
0x14001d08a  test    ecx, ecx
0x14001d08c  jz      short loc_14001D0CA
0x14001d08e  movzx   eax, byte ptr [rbp+9CAh]
0x14001d095  mov     r8d, edi
0x14001d098  mov     r9, [rbx+2C8h]
0x14001d09f  and     al, 1
0x14001d0a1  mov     [rsp+108h+var_E0], al
0x14001d0a5  xor     edx, edx
0x14001d0a7  mov     dword ptr [rsp+108h+var_E8], ecx
0x14001d0ab  lea     rcx, [rsp+108h+arg_0]
0x14001d0b3  call    cs:__imp_FsRtlValidateChangeNotifyBufferEx
0x14001d0ba  nop     dword ptr [rax+rax+00h]
0x14001d0bf  mov     r9d, eax
0x14001d0c2  test    eax, eax
0x14001d0c4  js      loc_14001D39F
0x14001d0ca  mov     eax, [rbx+2ECh]
0x14001d0d0  mov     [rsi+0B8h], rax
0x14001d0d7  mov     rcx, rbx
0x14001d0da  call    cs:__imp_SmbCseFinalizeBufferContext
0x14001d0e1  nop     dword ptr [rax+rax+00h]
0x14001d0e6  mov     rax, [r14+1A8h]
0x14001d0ed  mov     ecx, [rax+0B0h]
0x14001d0f3  test    cl, cl
0x14001d0f5  js      loc_14001D307
0x14001d0fb  mov     rax, [rsi+38h]
0x14001d0ff  mov     [rsi+0B0h], edi
0x14001d105  mov     ecx, [rax+0A4h]
0x14001d10b  test    cl, 1
0x14001d10e  jnz     loc_14001D2A7
0x14001d114  mov     rdx, [r14+1A8h]
0x14001d11b  mov     r9b, 1
0x14001d11e  movzx   ebx, byte ptr [rsi+218h]
0x14001d125  add     rdx, 0C0h
0x14001d12c  xor     r8d, r8d
0x14001d12f  mov     rcx, rsi
0x14001d132  call    Smb2InvalidateFileIdentityCacheEntryEx
0x14001d137  mov     rcx, [rsi+38h]
0x14001d13b  lea     r8, [rsp+108h+var_D8]
0x14001d140  mov     rbp, [r14+1A8h]
0x14001d147  xorps   xmm0, xmm0
0x14001d14a  add     rcx, 168h
0x14001d151  xor     r9d, r9d
0x14001d154  xor     edx, edx
0x14001d156  add     rbp, 458h
0x14001d15d  movups  [rsp+108h+var_D8], xmm0
0x14001d162  call    cs:__imp_RxCrackPathName
0x14001d169  nop     dword ptr [rax+rax+00h]
0x14001d16e  xor     edx, edx
0x14001d170  lea     rcx, Smb2DirCacheLock
0x14001d177  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001d17e  nop     dword ptr [rax+rax+00h]
0x14001d183  test    bl, bl
0x14001d185  jnz     short loc_14001D1E9
0x14001d187  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d18e  cmp     rcx, r15
0x14001d191  jnz     loc_14001D3DE
0x14001d197  xor     r9d, r9d
0x14001d19a  lea     rdx, [rsp+108h+var_D8]
0x14001d19f  xor     r8d, r8d
0x14001d1a2  mov     rcx, rbp
0x14001d1a5  call    cs:__imp_RxNameCacheFetchEntryEx
0x14001d1ac  nop     dword ptr [rax+rax+00h]
0x14001d1b1  test    rax, rax
0x14001d1b4  jz      short loc_14001D210
0x14001d1b6  mov     rdx, rax; NameCache
0x14001d1b9  mov     rcx, rbp; NameCacheCtl
0x14001d1bc  call    cs:__imp_RxNameCacheExpireEntry
0x14001d1c3  nop     dword ptr [rax+rax+00h]
0x14001d1c8  xor     r9d, r9d
0x14001d1cb  lea     rdx, [rsp+108h+var_D8]
0x14001d1d0  xor     r8d, r8d
0x14001d1d3  mov     rcx, rbp
0x14001d1d6  call    cs:__imp_RxNameCacheFetchEntryEx
0x14001d1dd  nop     dword ptr [rax+rax+00h]
0x14001d1e2  test    rax, rax
0x14001d1e5  jnz     short loc_14001D1B6
0x14001d1e7  jmp     short loc_14001D210
0x14001d1e9  mov     r8b, 1
0x14001d1ec  lea     rdx, [rsp+108h+var_D8]
0x14001d1f1  mov     rcx, rbp
0x14001d1f4  call    cs:__imp_RxNameCacheExpireEntriesWithPrefixEx
0x14001d1fb  nop     dword ptr [rax+rax+00h]
0x14001d200  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d207  cmp     rcx, r15
0x14001d20a  jnz     loc_14001D2C9
0x14001d210  xor     edx, edx
0x14001d212  lea     rcx, Smb2DirCacheLock
0x14001d219  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001d220  nop     dword ptr [rax+rax+00h]
0x14001d225  mov     rbx, [r14+1A8h]
0x14001d22c  lea     rcx, [rsp+108h+var_C8]; void *
0x14001d231  xorps   xmm0, xmm0
0x14001d234  xor     edx, edx; Val
0x14001d236  mov     r8d, 88h; Size
0x14001d23c  movups  [rsp+108h+var_D8], xmm0
0x14001d241  call    memset
0x14001d246  mov     rcx, [rsi+38h]
0x14001d24a  lea     rdx, [rsp+108h+var_D8]
0x14001d24f  add     rcx, 168h
0x14001d256  call    cs:__imp_MRxSmbIsStreamFile
0x14001d25d  nop     dword ptr [rax+rax+00h]
0x14001d262  xor     edx, edx
0x14001d264  lea     rcx, Smb2FileNotFoundCacheLock
0x14001d26b  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001d272  nop     dword ptr [rax+rax+00h]
0x14001d277  mov     r8b, 1
0x14001d27a  lea     rdx, [rsp+108h+var_D8]
0x14001d27f  lea     rcx, [rbx+230h]
0x14001d286  call    cs:__imp_RxNameCacheExpireEntriesWithPrefixEx
0x14001d28d  nop     dword ptr [rax+rax+00h]
0x14001d292  xor     edx, edx
0x14001d294  lea     rcx, Smb2FileNotFoundCacheLock
0x14001d29b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001d2a2  nop     dword ptr [rax+rax+00h]
0x14001d2a7  mov     rcx, rsi; RxContext
0x14001d2aa  call    cs:__imp_RxLowIoCompletion
0x14001d2b1  nop     dword ptr [rax+rax+00h]
0x14001d2b6  mov     eax, edi
0x14001d2b8  add     rsp, 0D8h
0x14001d2bf  pop     r15
0x14001d2c1  pop     r14
0x14001d2c3  pop     rdi
0x14001d2c4  pop     rsi
0x14001d2c5  pop     rbp
0x14001d2c6  pop     rbx
0x14001d2c7  retn
0x14001d2c9  test    dword ptr [rcx+2Ch], 100h
0x14001d2d0  jz      loc_14001D210
0x14001d2d6  cmp     byte ptr [rcx+29h], 2
0x14001d2da  jb      loc_14001D210
0x14001d2e0  mov     rcx, [rcx+18h]
0x14001d2e4  lea     rax, [rsp+108h+var_D8]
0x14001d2e9  mov     edx, 0Fh
0x14001d2ee  mov     [rsp+108h+var_E8], rax
0x14001d2f3  mov     r9, rsi
0x14001d2f6  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x14001d2fd  call    WPP_SF_qZ
0x14001d302  jmp     loc_14001D210
0x14001d307  lea     eax, [rdi+3FFFFF63h]
0x14001d30d  cmp     eax, 2Fh ; '/'
0x14001d310  ja      short loc_14001D32C
0x14001d312  mov     rcx, 900281000001h
0x14001d31c  bt      rcx, rax
0x14001d320  jnb     short loc_14001D32C
0x14001d322  mov     edi, 10Ch
0x14001d327  jmp     loc_14001D0FB
0x14001d32c  cmp     edi, 0C0410001h
0x14001d332  jz      short loc_14001D322
0x14001d334  cmp     edi, 0C000035Ch
0x14001d33a  jz      short loc_14001D322
0x14001d33c  cmp     edi, 0C0000480h
0x14001d342  jz      short loc_14001D322
0x14001d344  cmp     edi, 0C000026Eh
0x14001d34a  jz      short loc_14001D322
0x14001d34c  lea     eax, [rdi+3FFFFDFDh]
0x14001d352  cmp     eax, 3Eh ; '>'
0x14001d355  ja      loc_14003BFD0
0x14001d35b  mov     rcx, 4208040000000601h
0x14001d365  bt      rcx, rax
0x14001d369  jb      short loc_14001D322
0x14001d36b  jmp     loc_14003BFD0
0x14001d370  cmp     [rcx+9ECh], r15b
0x14001d377  jz      loc_14001D051
0x14001d37d  mov     rdx, [r14+1A8h]
0x14001d384  mov     r8d, [rcx+9E8h]
0x14001d38b  add     rdx, 458h
0x14001d392  mov     rcx, rsi
0x14001d395  call    Smb2UpdateDirInfoCacheLifeTime
0x14001d39a  jmp     loc_14001D051
0x14001d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3a6  cmp     rcx, r15
0x14001d3a9  jz      loc_14003BFC6
0x14001d3af  mov     eax, [rcx+2Ch]
0x14001d3b2  test    al, 4
0x14001d3b4  jz      loc_14003BFC6
0x14001d3ba  cmp     byte ptr [rcx+29h], 1
0x14001d3be  jb      loc_14003BFC6
0x14001d3c4  mov     eax, [rsp+108h+arg_0]
0x14001d3cb  mov     rcx, [rcx+18h]
0x14001d3cf  mov     dword ptr [rsp+108h+var_E8], eax
0x14001d3d3  call    WPP_SF_dD
0x14001d3d8  nop
0x14001d3d9  jmp     loc_14003BFC6
0x14001d3de  test    dword ptr [rcx+2Ch], 100h
0x14001d3e5  jz      loc_14001D197
0x14001d3eb  cmp     byte ptr [rcx+29h], 2
0x14001d3ef  jb      loc_14001D197
0x14001d3f5  mov     rcx, [rcx+18h]
0x14001d3f9  lea     rax, [rsp+108h+var_D8]
0x14001d3fe  mov     edx, 10h
0x14001d403  mov     [rsp+108h+var_E8], rax
0x14001d408  mov     r9, rsi
0x14001d40b  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x14001d412  call    WPP_SF_qZ
0x14001d417  jmp     loc_14001D197
0x14003bfc6  mov     edi, 0C00000C3h
0x14003bfcb  jmp     loc_14001D0D7
0x14003bfd0  cmp     edi, 0C000013Dh
0x14003bfd6  jz      loc_14001D322
0x14003bfdc  cmp     edi, 0C00002EFh
0x14003bfe2  jz      loc_14001D322
0x14003bfe8  lea     eax, [rdi+3FFFFB9Ah]
0x14003bfee  cmp     eax, 1
0x14003bff1  jbe     loc_14001D322
0x14003bff7  cmp     edi, 0C000000Eh
0x14003bffd  jz      loc_14001D322
0x14003c003  cmp     edi, 80090322h
0x14003c009  jz      loc_14001D322
0x14003c00f  cmp     edi, 80000011h
0x14003c015  jnz     loc_14001D0FB
0x14003c01b  jmp     loc_14001D322
```
