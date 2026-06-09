# Smb2Fsctl_Finalize

- ea: `0x140024b10`
- end: `0x140024f0b`
- name: `Smb2Fsctl_Finalize`
- size: `1019`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000b940`
- `0x140014650`
- `0x140014a00`
- `0x140024b10`
- `0x140029840`
- `0x140035c40`
- `0x140050250`
- `0x140053880`
- `0x140055eb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140024c8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024c8e`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140024ca4`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140024ca4`
- `rdbss!RxLowIoCompletion` at `0x140024ee3`
- `rdbss!RxLowIoCompletion` at `0x140024ee3`
- `mrxsmb!FsRtlValidateFileRegionOutputBuffer` at `0x140024ecc`
- `mrxsmb!FsRtlValidateFileRegionOutputBuffer` at `0x140024ecc`
- `mrxsmb!FsRtlValidateReparsePointBufferEx` at `0x140024e90`
- `mrxsmb!FsRtlValidateReparsePointBufferEx` at `0x140024e90`
- `mrxsmb!SmbCeInitializeConnectionInfo` at `0x140024bf2`
- `mrxsmb!SmbCeInitializeConnectionInfo` at `0x140024bf2`
- `mrxsmb!RDR_PERF_ENTER` at `0x140024b36`
- `mrxsmb!RDR_PERF_ENTER` at `0x140024b36`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140024b88`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x140024b88`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140024c76`
- `mrxsmb!SmbCeDereferenceVNetRootContext` at `0x140024c76`

## pseudocode

```c
__int64 __fastcall Smb2Fsctl_Finalize(__int64 a1, __int64 a2)
{
  int RdmaMappingPost; // ebx
  __int64 v4; // rdi
  __int32 v5; // r15d
  __int64 v6; // rcx
  _QWORD *v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbp
  int v11; // eax
  int v12; // r8d
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // ecx
  __int64 v17; // r13
  __int64 v18; // rbp
  __int64 v19; // rax
  __int64 v20; // rcx

  RdmaMappingPost = *(_DWORD *)(a1 + 16);
  v4 = *(_QWORD *)(a1 + 48);
  LOBYTE(a2) = 18;
  RDR_PERF_ENTER(a1 + 512, a2);
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 160);
  v7 = (_QWORD *)(v4 + 184);
  *(_QWORD *)(v4 + 184) = 0;
  if ( v6 != a1 + 160 )
  {
    v8 = v6 - 8;
    if ( v8 )
    {
      if ( RdmaMappingPost < 0 || (RdmaMappingPost = *(_DWORD *)(v8 + 48), RdmaMappingPost < 0) )
      {
        if ( RdmaMappingPost != -2147483643 )
        {
LABEL_9:
          SmbCseFinalizeBufferContext(v8);
          goto LABEL_10;
        }
        v9 = *(unsigned int *)(a1 + 2444);
      }
      else
      {
        v9 = *(unsigned int *)(v8 + 748);
      }
      *v7 = v9;
      goto LABEL_9;
    }
  }
LABEL_10:
  if ( *(_DWORD *)(v4 + 540) == 1311188
    && RdmaMappingPost >= 0
    && (*(_DWORD *)(*(_QWORD *)(v4 + 64) + 72LL) & 0x200) == 0 )
  {
    RdmaMappingPost = Smb2RegisterResilientHandle(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL), *(_QWORD *)(v4 + 72));
  }
  if ( *(_DWORD *)(v4 + 540) != 1311228 )
    goto LABEL_26;
  if ( RdmaMappingPost >= 0 )
  {
    v10 = *(_QWORD *)(a1 + 72);
    v11 = SmbCeInitializeConnectionInfo(v10, *(_QWORD *)(a1 + 2432), *(unsigned int *)v7);
    if ( v11 < 0 )
    {
      if ( *(_DWORD *)v7 )
      {
        v13 = (int)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids, v10, v11);
        }
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x2000) != 0 )
          McTemplateK0hzr0_EtwWriteTransfer(
            v13,
            (unsigned int)ServerNetworkInterfaceInvalid,
            v12,
            *(_WORD *)(v10 + 80) >> 1,
            *(_QWORD *)(v10 + 88));
      }
    }
  }
  if ( *(int *)(v4 + 120) < 0 )
  {
    SmbCeDereferenceVNetRootContext(*(_QWORD *)(a1 + 88));
    ExFreePoolWithTag(*(PVOID *)(a1 + 2432), 0x63437852u);
    *(_QWORD *)(a1 + 2432) = 0;
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)v4);
  }
  else
  {
LABEL_26:
    v14 = *(_DWORD *)(v4 + 540);
    if ( v14 == 1311600 )
    {
      RdmaMappingPost = Smb2FsctlCreateRdmaMappingPost((unsigned int)RdmaMappingPost);
    }
    else if ( v14 == 1311604 )
    {
      Smb2FsctlReleaseRdmaMappingPost((unsigned int)RdmaMappingPost, a1);
    }
    if ( RdmaMappingPost >= 0 )
    {
      v15 = *(_QWORD *)(v4 + 56);
      if ( v15 )
      {
        if ( (unsigned __int16)(*(_WORD *)v15 + 5087) <= 1u )
        {
          v16 = *(_DWORD *)(a1 + 2408);
          v17 = *(_QWORD *)(*(_QWORD *)(a1 + 88) + 424LL);
          if ( (v16 & 0xC000) != 0x4000 )
          {
            if ( v16 > 0x903D3 )
            {
              if ( v16 != 590891 && v16 != 1114136 && v16 != 1310952 && v16 != 1311228 && v16 != 1311692 )
              {
LABEL_42:
                v18 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
                if ( (*(_BYTE *)(v18 + 2368) & 0xA) != 0 || *(_QWORD *)(v15 + 144) )
                  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v4 + 72) + 48LL) + 320LL) = 1;
                if ( (*(_BYTE *)(v18 + 2368) & 2) != 0 )
                  Smb2InvalidateFileInfoCacheEntry(v4, v17 + 376);
                if ( (*(_BYTE *)(v18 + 2368) & 8) != 0 )
                {
                  v19 = *(_QWORD *)(*(_QWORD *)(v4 + 56) + 288LL);
                  if ( v19 )
                  {
                    v20 = *(_QWORD *)(v19 + 136);
                    if ( v20 )
                      v5 = *(_DWORD *)(v20 + 88);
                  }
                  Smb2InvalidateSingleFileInDirInfoCache(v4, v17 + 1112);
                  _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*(_QWORD *)(v4 + 56) + 136LL) + 84LL), v5);
                }
              }
            }
            else if ( v16 != 590803 )
            {
              switch ( v16 )
              {
                case 0x90028u:
                case 0x9002Cu:
                case 0x9003Cu:
                case 0x90060u:
                case 0x90064u:
                case 0x90068u:
                case 0x9006Fu:
                case 0x90073u:
                case 0x90078u:
                case 0x90083u:
                case 0x9008Fu:
                case 0x9009Cu:
                case 0x900A8u:
                case 0x900B3u:
                case 0x900BBu:
                case 0x900E3u:
                case 0x900EBu:
                case 0x900F4u:
                  break;
                default:
                  goto LABEL_42;
              }
            }
          }
          if ( *(_DWORD *)(v4 + 540) == 589988 )
            Smb2InvalidateFileIdentityCacheEntryEx(v4, v17 + 192, 0, 0);
        }
      }
    }
    if ( *(_DWORD *)(v4 + 540) == 589992
      && (((RdmaMappingPost + 0x80000000) & 0x80000000) != 0 || RdmaMappingPost == -2147483643) )
    {
      RdmaMappingPost = FsRtlValidateReparsePointBufferEx(
                          *(unsigned int *)v7,
                          *(_QWORD *)(a1 + 2432),
                          (unsigned int)RdmaMappingPost);
    }
    if ( *(_DWORD *)(v4 + 540) == 590468
      && (((RdmaMappingPost + 0x80000000) & 0x80000000) != 0 || RdmaMappingPost == -2147483643) )
    {
      RdmaMappingPost = FsRtlValidateFileRegionOutputBuffer(
                          v4 + 184,
                          *(unsigned int *)(a1 + 2440),
                          *(_QWORD *)(a1 + 2432),
                          (unsigned int)RdmaMappingPost);
    }
    *(_DWORD *)(v4 + 176) = RdmaMappingPost;
    RxLowIoCompletion((PRX_CONTEXT)v4);
  }
  return (unsigned int)RdmaMappingPost;
}

```

## disassembly

```asm
0x140024b10  mov     [rsp+arg_10], rbx
0x140024b15  mov     [rsp+arg_18], rsi
0x140024b1a  push    rdi
0x140024b1b  push    r14
0x140024b1d  push    r15
0x140024b1f  sub     rsp, 30h
0x140024b23  mov     ebx, [rcx+10h]
0x140024b26  mov     rsi, rcx
0x140024b29  mov     rdi, [rcx+30h]
0x140024b2d  mov     dl, 12h
0x140024b2f  add     rcx, 200h
0x140024b36  call    cs:__imp_RDR_PERF_ENTER
0x140024b3d  nop     dword ptr [rax+rax+00h]
0x140024b42  lea     rax, [rsi+0A0h]
0x140024b49  xor     r15d, r15d
0x140024b4c  mov     rcx, [rax]
0x140024b4f  lea     r14, [rdi+0B8h]
0x140024b56  mov     [r14], r15
0x140024b59  cmp     rcx, rax
0x140024b5c  jz      short loc_140024B94
0x140024b5e  add     rcx, 0FFFFFFFFFFFFFFF8h
0x140024b62  jz      short loc_140024B94
0x140024b64  test    ebx, ebx
0x140024b66  js      short loc_140024B77
0x140024b68  mov     ebx, [rcx+30h]
0x140024b6b  test    ebx, ebx
0x140024b6d  js      short loc_140024B77
0x140024b6f  mov     eax, [rcx+2ECh]
0x140024b75  jmp     short loc_140024B85
0x140024b77  cmp     ebx, 80000005h
0x140024b7d  jnz     short loc_140024B88
0x140024b7f  mov     eax, [rsi+98Ch]
0x140024b85  mov     [r14], rax
0x140024b88  call    cs:__imp_SmbCseFinalizeBufferContext
0x140024b8f  nop     dword ptr [rax+rax+00h]
0x140024b94  cmp     dword ptr [rdi+21Ch], 1401D4h
0x140024b9e  jnz     short loc_140024BC4
0x140024ba0  test    ebx, ebx
0x140024ba2  js      short loc_140024BC4
0x140024ba4  mov     rax, [rdi+40h]
0x140024ba8  test    dword ptr [rax+48h], 200h
0x140024baf  jnz     short loc_140024BC4
0x140024bb1  mov     rcx, [rsi+48h]
0x140024bb5  mov     rdx, [rdi+48h]
0x140024bb9  mov     rcx, [rcx+18h]
0x140024bbd  call    Smb2RegisterResilientHandle
0x140024bc2  mov     ebx, eax
0x140024bc4  cmp     dword ptr [rdi+21Ch], 1401FCh
0x140024bce  mov     [rsp+48h+arg_0], rbp
0x140024bd3  jnz     loc_140024CB5
0x140024bd9  test    ebx, ebx
0x140024bdb  js      loc_140024C6C
0x140024be1  mov     rbp, [rsi+48h]
0x140024be5  mov     r8d, [r14]
0x140024be8  mov     rcx, rbp
0x140024beb  mov     rdx, [rsi+980h]
0x140024bf2  call    cs:__imp_SmbCeInitializeConnectionInfo
0x140024bf9  nop     dword ptr [rax+rax+00h]
0x140024bfe  test    eax, eax
0x140024c00  jns     short loc_140024C6C
0x140024c02  cmp     dword ptr [r14], 0
0x140024c06  jz      short loc_140024C6C
0x140024c08  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140024c0f  lea     rdx, WPP_GLOBAL_Control
0x140024c16  cmp     rcx, rdx
0x140024c19  jz      short loc_140024C45
0x140024c1b  mov     edx, [rcx+2Ch]
0x140024c1e  test    dl, 1
0x140024c21  jz      short loc_140024C45
0x140024c23  cmp     byte ptr [rcx+29h], 1
0x140024c27  jb      short loc_140024C45
0x140024c29  mov     rcx, [rcx+18h]
0x140024c2d  lea     r8, WPP_65e9b76cb4683fb66828063337b9192b_Traceguids
0x140024c34  mov     edx, 0Dh
0x140024c39  mov     dword ptr [rsp+48h+var_28], eax
0x140024c3d  mov     r9, rbp
0x140024c40  call    WPP_SF_qD
0x140024c45  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 20h
0x140024c4c  jz      short loc_140024C6C
0x140024c4e  movzx   r9d, word ptr [rbp+50h]
0x140024c53  lea     rdx, ServerNetworkInterfaceInvalid
0x140024c5a  mov     rax, [rbp+58h]
0x140024c5e  shr     r9w, 1
0x140024c62  mov     [rsp+48h+var_28], rax
0x140024c67  call    McTemplateK0hzr0_EtwWriteTransfer
0x140024c6c  cmp     dword ptr [rdi+78h], 0
0x140024c70  jge     short loc_140024CB5
0x140024c72  mov     rcx, [rsi+58h]
0x140024c76  call    cs:__imp_SmbCeDereferenceVNetRootContext
0x140024c7d  nop     dword ptr [rax+rax+00h]
0x140024c82  mov     rcx, [rsi+980h]; P
0x140024c89  mov     edx, 63437852h; Tag
0x140024c8e  call    cs:__imp_ExFreePoolWithTag
0x140024c95  nop     dword ptr [rax+rax+00h]
0x140024c9a  mov     rcx, rdi; RxContext
0x140024c9d  mov     [rsi+980h], r15
0x140024ca4  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140024cab  nop     dword ptr [rax+rax+00h]
0x140024cb0  jmp     loc_140024EEF
0x140024cb5  mov     eax, [rdi+21Ch]
0x140024cbb  cmp     eax, 140370h
0x140024cc0  jnz     short loc_140024CCD
0x140024cc2  mov     ecx, ebx
0x140024cc4  call    Smb2FsctlCreateRdmaMappingPost
0x140024cc9  mov     ebx, eax
0x140024ccb  jmp     short loc_140024CDE
0x140024ccd  cmp     eax, 140374h
0x140024cd2  jnz     short loc_140024CDE
0x140024cd4  mov     rdx, rsi
0x140024cd7  mov     ecx, ebx
0x140024cd9  call    Smb2FsctlReleaseRdmaMappingPost
0x140024cde  test    ebx, ebx
0x140024ce0  js      loc_140024E63
0x140024ce6  mov     rdx, [rdi+38h]
0x140024cea  test    rdx, rdx
0x140024ced  jz      loc_140024E63
0x140024cf3  mov     eax, 13DFh
0x140024cf8  add     ax, [rdx]
0x140024cfb  cmp     ax, 1
0x140024cff  ja      loc_140024E63
0x140024d05  mov     rax, [rsi+58h]
0x140024d09  mov     ecx, [rsi+968h]
0x140024d0f  mov     [rsp+48h+arg_8], r13
0x140024d14  mov     r13, [rax+1A8h]
0x140024d1b  mov     eax, ecx
0x140024d1d  and     eax, 0C000h
0x140024d22  cmp     eax, 4000h
0x140024d27  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d2d  cmp     ecx, 903D3h
0x140024d33  ja      short loc_140024D6A
0x140024d35  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d3b  add     ecx, 0FFF6FFD8h; switch 205 cases
0x140024d41  cmp     ecx, 0CCh
0x140024d47  ja      short def_140024D64; jumptable 0000000140024D64 default case, cases 589865-589867,589869-589883,589885-589919,589921-589923,589925-589927,589929-589934,589936-589938,589940-589943,589945-589954,589956-589966,589968-589979,589981-589991,589993-590002,590004-590010,590012-590050,590052-590058,590060-590067
0x140024d49  lea     r8, cs:140000000h
0x140024d50  movzx   eax, ds:(byte_14003FD08 - 140000000h)[r8+rcx]
0x140024d59  mov     ecx, ds:(jpt_140024D64 - 140000000h)[r8+rax*4]
0x140024d61  add     rcx, r8
0x140024d64  jmp     rcx; switch jump
0x140024d6a  cmp     ecx, 9042Bh
0x140024d70  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d76  cmp     ecx, 110018h
0x140024d7c  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d82  cmp     ecx, 1400E8h
0x140024d88  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d8e  cmp     ecx, 1401FCh
0x140024d94  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024d9a  cmp     ecx, 1403CCh
0x140024da0  jz      loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024da6  mov     rax, [rsi+48h]; jumptable 0000000140024D64 default case, cases 589865-589867,589869-589883,589885-589919,589921-589923,589925-589927,589929-589934,589936-589938,589940-589943,589945-589954,589956-589966,589968-589979,589981-589991,589993-590002,590004-590010,590012-590050,590052-590058,590060-590067
0x140024daa  mov     rbp, [rax+18h]
0x140024dae  test    byte ptr [rbp+940h], 0Ah
0x140024db5  jnz     short loc_140024DC1
0x140024db7  cmp     qword ptr [rdx+90h], 0
0x140024dbf  jz      short loc_140024DD0
0x140024dc1  mov     rax, [rdi+48h]
0x140024dc5  mov     rcx, [rax+30h]
0x140024dc9  mov     byte ptr [rcx+140h], 1
0x140024dd0  test    byte ptr [rbp+940h], 2
0x140024dd7  jz      short loc_140024DE8
0x140024dd9  lea     rdx, [r13+178h]
0x140024de0  mov     rcx, rdi
0x140024de3  call    Smb2InvalidateFileInfoCacheEntry
0x140024de8  test    byte ptr [rbp+940h], 8
0x140024def  jz      short loc_140024E3D; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024df1  mov     rdx, [rdi+38h]
0x140024df5  mov     rax, [rdx+120h]
0x140024dfc  test    rax, rax
0x140024dff  jz      short loc_140024E1F
0x140024e01  mov     rcx, [rax+88h]
0x140024e08  test    rcx, rcx
0x140024e0b  jz      short loc_140024E1F
0x140024e0d  mov     rax, [rdx+88h]
0x140024e14  nop
0x140024e15  mov     r15d, [rcx+58h]
0x140024e19  nop
0x140024e1a  nop
0x140024e1b  mov     eax, [rax+54h]
0x140024e1e  nop
0x140024e1f  lea     rdx, [r13+458h]
0x140024e26  mov     rcx, rdi
0x140024e29  call    Smb2InvalidateSingleFileInDirInfoCache
0x140024e2e  mov     rax, [rdi+38h]
0x140024e32  mov     rcx, [rax+88h]
0x140024e39  xchg    r15d, [rcx+54h]
0x140024e3d  cmp     dword ptr [rdi+21Ch], 900A4h; jumptable 0000000140024D64 cases 589864,589868,589884,589920,589924,589928,589935,589939,589944,589955,589967,589980,589992,590003,590011,590051,590059,590068
0x140024e47  jnz     short loc_140024E5E
0x140024e49  lea     rdx, [r13+0C0h]
0x140024e50  xor     r9d, r9d
0x140024e53  xor     r8d, r8d
0x140024e56  mov     rcx, rdi
0x140024e59  call    Smb2InvalidateFileIdentityCacheEntryEx
0x140024e5e  mov     r13, [rsp+48h+arg_8]
0x140024e63  cmp     dword ptr [rdi+21Ch], 900A8h
0x140024e6d  mov     ebp, 80000000h
0x140024e72  jnz     short loc_140024E9E
0x140024e74  lea     eax, [rbx+rbp]
0x140024e77  test    ebp, eax
0x140024e79  jnz     short loc_140024E83
0x140024e7b  cmp     ebx, 80000005h
0x140024e81  jnz     short loc_140024E9E
0x140024e83  mov     rdx, [rsi+980h]
0x140024e8a  mov     r8d, ebx
0x140024e8d  mov     ecx, [r14]
0x140024e90  call    cs:__imp_FsRtlValidateReparsePointBufferEx
0x140024e97  nop     dword ptr [rax+rax+00h]
0x140024e9c  mov     ebx, eax
0x140024e9e  cmp     dword ptr [rdi+21Ch], 90284h
0x140024ea8  jnz     short loc_140024EDA
0x140024eaa  lea     eax, [rbx+rbp]
0x140024ead  test    ebp, eax
0x140024eaf  jnz     short loc_140024EB9
0x140024eb1  cmp     ebx, 80000005h
0x140024eb7  jnz     short loc_140024EDA
0x140024eb9  mov     r8, [rsi+980h]
0x140024ec0  mov     r9d, ebx
0x140024ec3  mov     edx, [rsi+988h]
0x140024ec9  mov     rcx, r14
0x140024ecc  call    cs:__imp_FsRtlValidateFileRegionOutputBuffer
0x140024ed3  nop     dword ptr [rax+rax+00h]
0x140024ed8  mov     ebx, eax
0x140024eda  mov     rcx, rdi; RxContext
0x140024edd  mov     [rdi+0B0h], ebx
0x140024ee3  call    cs:__imp_RxLowIoCompletion
0x140024eea  nop     dword ptr [rax+rax+00h]
0x140024eef  mov     eax, ebx
0x140024ef1  mov     rbp, [rsp+48h+arg_0]
0x140024ef6  mov     rbx, [rsp+48h+arg_10]
0x140024efb  mov     rsi, [rsp+48h+arg_18]
0x140024f00  add     rsp, 30h
0x140024f04  pop     r15
0x140024f06  pop     r14
0x140024f08  pop     rdi
0x140024f09  retn
```
