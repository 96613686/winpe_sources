# Smb2QueryInfo_Finalize

- ea: `0x140003570`
- end: `0x140003830`
- name: `Smb2QueryInfo_Finalize`
- size: `704`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003570`
- `0x140004b30`
- `0x140004d30`
- `0x140028950`

## import_xrefs

- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000378f`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x14000378f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003707`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003707`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400036e3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400036e3`
- `rdbss!RxCrackPathName` at `0x1400036a8`
- `rdbss!RxCrackPathName` at `0x1400036a8`
- `mrxsmb!FsRtlValidateVolumeInformationBuffer` at `0x140003811`
- `mrxsmb!FsRtlValidateVolumeInformationBuffer` at `0x140003811`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140003645`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140003645`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14000372e`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14000372e`

## pseudocode

```c
__int64 __fastcall Smb2QueryInfo_Finalize(__int64 a1)
{
  int v1; // ebx
  __int64 v2; // rsi
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // r13
  unsigned int *v7; // r9
  int v8; // eax
  int v9; // eax
  int v10; // ebp
  int v11; // eax
  _QWORD *v12; // rbp
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rsi
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int128 v23; // [rsp+40h] [rbp-38h] BYREF

  v1 = *(_DWORD *)(a1 + 16);
  v2 = *(_QWORD *)(a1 + 160);
  if ( v2 == a1 + 160 )
    return (unsigned int)v1;
  v4 = v2 - 8;
  if ( v2 != 8 )
  {
    v5 = *(_QWORD *)(a1 + 48);
    if ( v1 >= 0 )
      v1 = *(_DWORD *)(v2 + 40);
    if ( *(_DWORD *)(a1 + 2420) == 3 && v1 == -2147483643 )
    {
      v1 = -1073741629;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          10,
          WPP_df594d904eb23382f7a5bd2448918cda_Traceguids,
          v5,
          -2147483643,
          -1073741629);
      }
      goto LABEL_20;
    }
    v6 = *(_QWORD *)(a1 + 88);
    if ( !v1 || v1 == -2147483643 )
    {
      v7 = (unsigned int *)(v2 + 740);
      *(_DWORD *)(v5 + 472) = *(_DWORD *)(a1 + 2416) - *(_DWORD *)(v2 + 740);
    }
    else
    {
      v7 = (unsigned int *)(v2 + 740);
    }
    if ( v1 != -1073741789 )
    {
      if ( v1 < 0 && v1 != -2147483643 )
        goto LABEL_20;
      v8 = *(_DWORD *)(a1 + 2420);
      if ( v8 == 1 )
        goto LABEL_11;
      goto LABEL_22;
    }
    v7 = (unsigned int *)(v2 + 740);
    v20 = *(unsigned int *)(v2 + 740);
    if ( (unsigned int)v20 > *(_DWORD *)(a1 + 2416) )
    {
      if ( *(_DWORD *)(a1 + 2420) != 3 || (unsigned int)v20 >= 0x14 )
      {
        *(_QWORD *)(v5 + 184) = v20;
        if ( *(_DWORD *)(a1 + 2420) == 3 )
        {
          v8 = *(_DWORD *)(a1 + 2420);
          v1 = -2147483643;
LABEL_22:
          v10 = 0;
          v18 = v8 - 2;
          if ( !v18 )
          {
            v9 = FsRtlValidateVolumeInformationBuffer(
                   v5,
                   *(unsigned int *)(a1 + 2424),
                   *(_QWORD *)(v2 + 704),
                   *v7,
                   *(_DWORD *)(v2 + 40));
            goto LABEL_12;
          }
          v19 = v18 - 1;
          if ( !v19 )
          {
            if ( v1 >= 0
              && !RtlValidRelativeSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(v2 + 704), *(_DWORD *)(v2 + 740), 0) )
            {
              v10 = -1073741629;
            }
            goto LABEL_13;
          }
          if ( v19 != 1 )
          {
LABEL_13:
            v11 = v10;
            if ( v10 >= 0 )
              v11 = v1;
            v1 = v11;
            if ( v10 >= 0 && *(_DWORD *)(a1 + 2420) == 1 && *(_DWORD *)(a1 + 2424) == 59 )
            {
              v12 = *(_QWORD **)(v2 + 704);
              v13 = *(_QWORD *)(v6 + 424);
              v14 = *(_QWORD *)(v5 + 56) + 360LL;
              v23 = 0;
              RxCrackPathName(v14, &v23, 0, 0);
              v15 = Smb2FindOrCreateDirCacheObject(v5, v13 + 1112, &v23, 0, 0, 0);
              v16 = v15;
              if ( v15 )
              {
                ExAcquirePushLockExclusiveEx(v15 + 104, 0);
                *(_QWORD *)(v16 + 224) = *v12;
                *(_BYTE *)(v16 + 232) = 1;
                ExReleasePushLockExclusiveEx(v16 + 104, 0);
                Smb2DereferenceDirCacheObject((PVOID)v16);
              }
            }
            goto LABEL_20;
          }
LABEL_11:
          v9 = FsRtlValidateFileInformationBufferEx(
                 v5,
                 *(unsigned int *)(a1 + 2424),
                 *(_QWORD *)(v2 + 704),
                 *v7,
                 0,
                 0,
                 *(_DWORD *)(v2 + 40));
LABEL_12:
          v10 = v9;
          goto LABEL_13;
        }
LABEL_20:
        SmbCseFinalizeBufferContext(v4);
        return (unsigned int)v1;
      }
      v1 = -1073741629;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_20;
      }
      v22 = 12;
    }
    else
    {
      v1 = -1073741629;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_20;
      }
      v22 = 11;
    }
    WPP_SF_qDD(v21->AttachedDevice, v22, WPP_df594d904eb23382f7a5bd2448918cda_Traceguids, v5, -1073741789, -1073741629);
    goto LABEL_20;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140003570  push    rbx
0x140003572  push    rsi
0x140003573  push    rdi
0x140003574  sub     rsp, 60h
0x140003578  mov     ebx, [rcx+10h]
0x14000357b  lea     rax, [rcx+0A0h]
0x140003582  mov     rsi, [rax]
0x140003585  mov     rdi, rcx
0x140003588  cmp     rsi, rax
0x14000358b  jz      loc_140003757
0x140003591  mov     [rsp+78h+var_20], r14
0x140003596  lea     r14, [rsi-8]
0x14000359a  test    r14, r14
0x14000359d  jz      loc_1400037C5
0x1400035a3  mov     [rsp+78h+var_28], r15
0x1400035a8  mov     r15, [rcx+30h]
0x1400035ac  test    ebx, ebx
0x1400035ae  js      short loc_1400035B3
0x1400035b0  mov     ebx, [rsi+28h]
0x1400035b3  cmp     dword ptr [rcx+974h], 3
0x1400035ba  mov     [rsp+78h+arg_0], rbp
0x1400035c2  jz      loc_1400037D5
0x1400035c8  mov     [rsp+78h+arg_8], r12
0x1400035d0  mov     [rsp+78h+arg_10], r13
0x1400035d8  mov     r13, [rcx+58h]
0x1400035dc  test    ebx, ebx
0x1400035de  jnz     loc_1400037AD
0x1400035e4  mov     ecx, [rcx+970h]
0x1400035ea  lea     r9, [rsi+2E4h]
0x1400035f1  sub     ecx, [r9]
0x1400035f4  mov     [r15+1D8h], ecx
0x1400035fb  xor     r12d, r12d
0x1400035fe  cmp     ebx, 0C0000023h
0x140003604  jz      loc_140038249
0x14000360a  test    ebx, ebx
0x14000360c  js      loc_1400037E6
0x140003612  mov     eax, [rdi+974h]
0x140003618  cmp     eax, 1
0x14000361b  jnz     loc_140003762
0x140003621  mov     eax, [rsi+28h]
0x140003624  mov     rcx, r15
0x140003627  mov     r9d, [r9]
0x14000362a  mov     r8, [rsi+2C0h]
0x140003631  mov     edx, [rdi+978h]
0x140003637  mov     [rsp+78h+var_48], eax
0x14000363b  mov     [rsp+78h+var_50], r12
0x140003640  mov     [rsp+78h+var_58], r12
0x140003645  call    cs:__imp_FsRtlValidateFileInformationBufferEx
0x14000364c  nop     dword ptr [rax+rax+00h]
0x140003651  mov     ebp, eax
0x140003653  test    ebp, ebp
0x140003655  mov     eax, ebp
0x140003657  cmovns  eax, ebx
0x14000365a  mov     ebx, eax
0x14000365c  js      loc_14000371B
0x140003662  cmp     dword ptr [rdi+974h], 1
0x140003669  jnz     loc_14000371B
0x14000366f  cmp     dword ptr [rdi+978h], 3Bh ; ';'
0x140003676  jnz     loc_14000371B
0x14000367c  mov     rcx, [r15+38h]
0x140003680  lea     rdx, [rsp+78h+var_38]
0x140003685  mov     rbp, [rsi+2C0h]
0x14000368c  xorps   xmm0, xmm0
0x14000368f  mov     rdi, [r13+1A8h]
0x140003696  add     rcx, 168h
0x14000369d  xor     r9d, r9d
0x1400036a0  xor     r8d, r8d
0x1400036a3  movups  [rsp+78h+var_38], xmm0
0x1400036a8  call    cs:__imp_RxCrackPathName
0x1400036af  nop     dword ptr [rax+rax+00h]
0x1400036b4  xor     r9d, r9d
0x1400036b7  mov     [rsp+78h+var_50], r12
0x1400036bc  lea     r8, [rsp+78h+var_38]
0x1400036c1  mov     [rsp+78h+var_58], r12
0x1400036c6  lea     rdx, [rdi+458h]
0x1400036cd  mov     rcx, r15
0x1400036d0  call    Smb2FindOrCreateDirCacheObject
0x1400036d5  mov     rsi, rax
0x1400036d8  test    rax, rax
0x1400036db  jz      short loc_14000371B
0x1400036dd  xor     edx, edx
0x1400036df  lea     rcx, [rax+68h]
0x1400036e3  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400036ea  nop     dword ptr [rax+rax+00h]
0x1400036ef  mov     rax, [rbp+0]
0x1400036f3  lea     rcx, [rsi+68h]
0x1400036f7  xor     edx, edx
0x1400036f9  mov     [rsi+0E0h], rax
0x140003700  mov     byte ptr [rsi+0E8h], 1
0x140003707  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000370e  nop     dword ptr [rax+rax+00h]
0x140003713  mov     rcx, rsi; P
0x140003716  call    Smb2DereferenceDirCacheObject
0x14000371b  mov     r13, [rsp+78h+arg_10]
0x140003723  mov     r12, [rsp+78h+arg_8]
0x14000372b  mov     rcx, r14
0x14000372e  call    cs:__imp_SmbCseFinalizeBufferContext
0x140003735  nop     dword ptr [rax+rax+00h]
0x14000373a  mov     r15, [rsp+78h+var_28]
0x14000373f  mov     eax, ebx
0x140003741  mov     rbp, [rsp+78h+arg_0]
0x140003749  mov     r14, [rsp+78h+var_20]
0x14000374e  add     rsp, 60h
0x140003752  pop     rdi
0x140003753  pop     rsi
0x140003754  pop     rbx
0x140003755  retn
0x140003757  mov     eax, ebx
0x140003759  add     rsp, 60h
0x14000375d  pop     rdi
0x14000375e  pop     rsi
0x14000375f  pop     rbx
0x140003760  retn
0x140003762  mov     ebp, r12d
0x140003765  sub     eax, 2
0x140003768  jz      loc_1400037F7
0x14000376e  sub     eax, 1
0x140003771  jnz     loc_140003822
0x140003777  test    ebx, ebx
0x140003779  js      loc_140003653
0x14000377f  mov     edx, [rsi+2E4h]; SecurityDescriptorLength
0x140003785  xor     r8d, r8d; RequiredInformation
0x140003788  mov     rcx, [rsi+2C0h]; SecurityDescriptorInput
0x14000378f  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x140003796  nop     dword ptr [rax+rax+00h]
0x14000379b  test    al, al
0x14000379d  jnz     loc_140003653
0x1400037a3  mov     ebp, 0C00000C3h
0x1400037a8  jmp     loc_140003653
0x1400037ad  cmp     ebx, 80000005h
0x1400037b3  jz      loc_1400035E4
0x1400037b9  lea     r9, [rsi+2E4h]
0x1400037c0  jmp     loc_1400035FB
0x1400037c5  mov     r14, [rsp+78h+var_20]
0x1400037ca  mov     eax, ebx
0x1400037cc  add     rsp, 60h
0x1400037d0  pop     rdi
0x1400037d1  pop     rsi
0x1400037d2  pop     rbx
0x1400037d3  retn
0x1400037d5  cmp     ebx, 80000005h
0x1400037db  jnz     loc_1400035C8
0x1400037e1  jmp     loc_1400381EA
0x1400037e6  cmp     ebx, 80000005h
0x1400037ec  jz      loc_140003612
0x1400037f2  jmp     loc_14000371B
0x1400037f7  mov     eax, [rsi+28h]
0x1400037fa  mov     rcx, r15
0x1400037fd  mov     r9d, [r9]
0x140003800  mov     r8, [rsi+2C0h]
0x140003807  mov     edx, [rdi+978h]
0x14000380d  mov     dword ptr [rsp+78h+var_58], eax
0x140003811  call    cs:__imp_FsRtlValidateVolumeInformationBuffer
0x140003818  nop     dword ptr [rax+rax+00h]
0x14000381d  jmp     loc_140003651
0x140003822  cmp     eax, 1
0x140003825  jz      loc_140003621
0x14000382b  jmp     loc_140003653
0x1400381ea  mov     ebx, 0C00000C3h
0x1400381ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400381f6  lea     rax, WPP_GLOBAL_Control
0x1400381fd  cmp     rcx, rax
0x140038200  jz      loc_14000372B
0x140038206  mov     eax, [rcx+2Ch]
0x140038209  test    al, 1
0x14003820b  jz      loc_14000372B
0x140038211  cmp     byte ptr [rcx+29h], 1
0x140038215  jb      loc_14000372B
0x14003821b  mov     rcx, [rcx+18h]
0x14003821f  lea     r8, WPP_df594d904eb23382f7a5bd2448918cda_Traceguids
0x140038226  mov     edx, 0Ah
0x14003822b  mov     dword ptr [rsp+78h+var_50], 0C00000C3h
0x140038233  mov     r9, r15
0x140038236  mov     dword ptr [rsp+78h+var_58], 80000005h
0x14003823e  call    WPP_SF_qDD
0x140038243  nop
0x140038244  jmp     loc_14000372B
0x140038249  lea     r9, [rsi+2E4h]
0x140038250  mov     eax, [r9]
0x140038253  cmp     eax, [rdi+970h]
0x140038259  ja      short loc_140038293
0x14003825b  mov     ebx, 0C00000C3h
0x140038260  mov     rcx, cs:WPP_GLOBAL_Control
0x140038267  lea     rax, WPP_GLOBAL_Control
0x14003826e  cmp     rcx, rax
0x140038271  jz      loc_14000371B
0x140038277  mov     eax, [rcx+2Ch]
0x14003827a  test    al, 1
0x14003827c  jz      loc_14000371B
0x140038282  cmp     byte ptr [rcx+29h], 1
0x140038286  jb      loc_14000371B
0x14003828c  mov     edx, 0Bh
0x140038291  jmp     short loc_1400382D7
0x140038293  cmp     dword ptr [rdi+974h], 3
0x14003829a  jnz     short loc_140038300
0x14003829c  cmp     eax, 14h
0x14003829f  jnb     short loc_140038300
0x1400382a1  mov     ebx, 0C00000C3h
0x1400382a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400382ad  lea     rax, WPP_GLOBAL_Control
0x1400382b4  cmp     rcx, rax
0x1400382b7  jz      loc_14000371B
0x1400382bd  mov     eax, [rcx+2Ch]
0x1400382c0  test    al, 1
0x1400382c2  jz      loc_14000371B
0x1400382c8  cmp     byte ptr [rcx+29h], 1
0x1400382cc  jb      loc_14000371B
0x1400382d2  mov     edx, 0Ch
0x1400382d7  mov     rcx, [rcx+18h]
0x1400382db  lea     r8, WPP_df594d904eb23382f7a5bd2448918cda_Traceguids
0x1400382e2  mov     dword ptr [rsp+78h+var_50], 0C00000C3h
0x1400382ea  mov     r9, r15
0x1400382ed  mov     dword ptr [rsp+78h+var_58], 0C0000023h
0x1400382f5  call    WPP_SF_qDD
0x1400382fa  nop
0x1400382fb  jmp     loc_14000371B
0x140038300  mov     [r15+0B8h], rax
0x140038307  cmp     dword ptr [rdi+974h], 3
0x14003830e  jnz     loc_14000371B
0x140038314  mov     eax, [rdi+974h]
0x14003831a  mov     ebx, 80000005h
0x14003831f  jmp     loc_140003762
```
