# UlFlushResponseCacheIoctl

- ea: `0x1c00cefb0`
- end: `0x1c00cf2b8`
- name: `UlFlushResponseCacheIoctl`
- size: `776`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1c0001038`
- `0x1c001af84`
- `0x1c001b640`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f570`
- `0x1c008fd84`
- `0x1c0090c00`
- `0x1c0092a68`
- `0x1c00933b4`
- `0x1c00a153c`
- `0x1c00a1bfc`
- `0x1c00cefb0`
- `0x1c00cf2c0`

## import_xrefs

- `ntoskrnl!PsGetPermanentSiloContext` at `0x1c00cf022`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x1c00cf022`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00cf0f8`
- `ntoskrnl!IoIs32bitProcess` at `0x1c00cf0f8`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00cf009`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00cf0b9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00cf009`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1c00cf0b9`
- `ntoskrnl!IofCompleteRequest` at `0x1c00cf289`
- `ntoskrnl!IofCompleteRequest` at `0x1c00cf289`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f9119`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00f9119`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f9194`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00f9194`

## pseudocode

```c
__int64 __fastcall UlFlushResponseCacheIoctl(PIRP Irp, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  int v6; // ebx
  _QWORD *v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  BOOLEAN v12; // r14
  unsigned int v13; // edi
  struct _IRP *MasterIrp; // rdx
  int v15; // edi
  int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // xmm1_8
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r12
  size_t v22; // rbx
  const void *v23; // r15
  void *v24; // rsi
  __int64 v25; // rcx
  __int64 MdlAddress_low; // rax
  PVOID PoolWithTagPriority; // rax
  unsigned __int64 v29; // rax
  __int64 *v30; // [rsp+20h] [rbp-49h]
  __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  __int128 v32; // [rsp+48h] [rbp-21h] BYREF
  __int64 v33; // [rsp+58h] [rbp-11h]
  __int128 v34; // [rsp+60h] [rbp-9h] BYREF
  __int64 v35; // [rsp+70h] [rbp+7h]
  void *Src[2]; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v37; // [rsp+88h] [rbp+1Fh]
  __int64 v38; // [rsp+D8h] [rbp+6Fh] BYREF
  struct _IRP *v39; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v40; // [rsp+E8h] [rbp+7Fh]

  v38 = 0;
  v37 = 0;
  v35 = 0;
  *(_OWORD *)Src = 0;
  v39 = 0;
  v34 = 0;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qq(91, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2);
  v31 = 0;
  v4 = ((__int64 (*)(void))PsGetCurrentServerSilo)();
  PsGetPermanentSiloContext(v4, (unsigned int)UxPodMonitorSlot, &v31);
  v6 = 0;
  v7 = *(_QWORD **)(a2 + 48);
  v40 = v31;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
  {
    v30 = &v38;
    WPP_SF_qdP(12, WPP_18ca8755388c316524f95a91261e2540_Traceguids, v7, 1);
  }
  v8 = 0;
  v38 = 0;
  v9 = v7[1];
  if ( *(PDEVICE_OBJECT *)(v9 + 8) == UxDriverObject && v7[4] == 1347440705 )
  {
    v10 = v7[3];
    if ( v10
      && *(_DWORD *)(v10 + 24) == 1346464853
      && (v11 = *(_QWORD *)(v10 + 8)) != 0
      && *(_DWORD *)(v11 + 120) == 1329687637 )
    {
      if ( (*(_DWORD *)(v10 + 40) & 1) != 0 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v10 + 8) + 320LL) == PsGetCurrentServerSilo(v9, v5, 0) )
        {
          v8 = v10;
          v38 = v10;
        }
        else
        {
          v8 = v38;
          v6 = -1073740700;
        }
      }
      else
      {
        v6 = -1073741637;
      }
    }
    else
    {
      v6 = -1073741811;
    }
  }
  else
  {
    v6 = -1073741808;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_qD(13, WPP_18ca8755388c316524f95a91261e2540_Traceguids, v8, (unsigned int)v6);
  if ( v6 >= 0 )
  {
    v12 = IoIs32bitProcess(Irp);
    v6 = 0;
    v13 = v12 != 0 ? 12 : 24;
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
      WPP_SF_qilq(14, WPP_18ca8755388c316524f95a91261e2540_Traceguids, Irp, a2, v13, &v39);
    MasterIrp = 0;
    v39 = 0;
    if ( *(_DWORD *)(a2 + 16) < v13 )
    {
      v6 = -1073741789;
    }
    else if ( Irp->AssociatedIrp.MasterIrp )
    {
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      v39 = MasterIrp;
    }
    else
    {
      v6 = -1073741811;
    }
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    {
      WPP_SF_qD(15, WPP_18ca8755388c316524f95a91261e2540_Traceguids, MasterIrp, (unsigned int)v6);
      MasterIrp = v39;
    }
    if ( v6 >= 0 )
    {
      v15 = *(_DWORD *)&MasterIrp->Type;
      if ( v12 )
      {
        DWORD2(v34) = *(_DWORD *)(&MasterIrp->Size + 1);
        MdlAddress_low = LODWORD(MasterIrp->MdlAddress);
        MasterIrp = (struct _IRP *)&v34;
        v35 = MdlAddress_low;
        LODWORD(v34) = v15;
      }
      v16 = v15 & 1;
      if ( v15 != v16 )
        goto LABEL_47;
      v32 = 0;
      v33 = 0;
      v6 = RtlUnicodeStringValidate((PCUNICODE_STRING)&MasterIrp->MdlAddress);
      if ( v6 >= 0 )
      {
        v6 = UxCaptureWideString(*(void **)(v17 + 8));
        if ( v6 >= 0 )
        {
          v18 = v33;
          *(_OWORD *)Src = v32;
          v33 = 0;
          v37 = v18;
          v32 = 0;
        }
      }
      UxFreeCapturedUnicodeString(&v32);
      if ( v6 >= 0 )
      {
        if ( LOWORD(Src[0]) )
        {
          v21 = v38;
          v22 = LOWORD(Src[0]);
          v23 = Src[1];
          v24 = 0;
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
          {
            LODWORD(v30) = LOWORD(Src[0]);
            WPP_SF_qqLLq(v20, v19, v40, Src[1], v30, v15, v38);
          }
          v25 = v40;
          if ( !*(_BYTE *)(v40 + 1088) )
          {
            v6 = -1073741436;
            goto LABEL_40;
          }
          if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
          {
            WPP_SF_SdDdq(v40, v19, (_DWORD)v23, v22, v15, v15 & 1, v21);
            v25 = v40;
          }
          if ( !(_BYTE)v16 )
          {
            v6 = UlpFlushUri(v25, v23, (unsigned int)v22, v21, v30);
            if ( v6 >= 0 )
              goto LABEL_40;
LABEL_62:
            if ( v24 )
              ExFreePoolWithTag(v24, 0);
            goto LABEL_40;
          }
          if ( *((_WORD *)v23 + ((v22 - 2) >> 1)) != 47 )
          {
            if ( (int)v22 + 2 < (unsigned int)v22 || (unsigned int)(v22 + 4) < 2 )
            {
              v6 = -1073741675;
LABEL_40:
              if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80000) != 0 )
                WPP_SF_D(50, WPP_ede9639403cc3db159114586db5b30dd_Traceguids);
              goto LABEL_42;
            }
            PoolWithTagPriority = ExAllocatePoolWithTagPriority(PagedPool, v22 + 4, 0x53556C55u, LowPoolPriority);
            v24 = PoolWithTagPriority;
            if ( !PoolWithTagPriority )
            {
              v6 = -1073741670;
              goto LABEL_40;
            }
            memmove(PoolWithTagPriority, v23, v22);
            LODWORD(v23) = (_DWORD)v24;
            *((_WORD *)v24 + (v22 >> 1)) = 47;
            v29 = (v22 + 2) >> 1;
            LODWORD(v22) = v22 + 2;
            *((_WORD *)v24 + v29) = 0;
          }
          UlpFilteredFlushUriCache(v40, (unsigned int)UlpFlushFilterUriRecursive, v21, (_DWORD)v23, v22, 0);
          v6 = 0;
          goto LABEL_62;
        }
LABEL_47:
        v6 = -1073741811;
      }
    }
  }
LABEL_42:
  UxFreeCapturedUnicodeString(Src);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x100) != 0 )
    WPP_SF_D(92, WPP_18ca8755388c316524f95a91261e2540_Traceguids);
  if ( v6 != 259 )
  {
    Irp->IoStatus.Status = v6;
    IofCompleteRequest(Irp, 0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1c00cefb0  mov     [rsp-8+arg_0], rbx
0x1c00cefb5  push    rbp
0x1c00cefb6  push    rsi
0x1c00cefb7  push    rdi
0x1c00cefb8  push    r12
0x1c00cefba  push    r13
0x1c00cefbc  push    r14
0x1c00cefbe  push    r15
0x1c00cefc0  lea     rbp, [rsp-27h]
0x1c00cefc5  sub     rsp, 90h
0x1c00cefcc  xor     r15d, r15d
0x1c00cefcf  xorps   xmm0, xmm0
0x1c00cefd2  xor     eax, eax
0x1c00cefd4  mov     [rbp+57h+arg_8], r15
0x1c00cefd8  mov     [rbp+57h+var_38], rax
0x1c00cefdc  mov     rsi, rdx
0x1c00cefdf  mov     [rbp+57h+var_50], rax
0x1c00cefe3  mov     r13, rcx
0x1c00cefe6  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1c00cefea  mov     [rbp+57h+arg_10], r15
0x1c00cefee  movups  [rbp+57h+var_60], xmm0
0x1c00ceff2  mov     r12d, 100h
0x1c00ceff8  test    dword ptr cs:WPP_MAIN_CB.Queue, r12d
0x1c00cefff  jnz     loc_1C00F8F8A
0x1c00cf005  mov     [rbp+57h+var_80], r15
0x1c00cf009  call    cs:__imp_PsGetCurrentServerSilo
0x1c00cf010  nop     dword ptr [rax+rax+00h]
0x1c00cf015  mov     edx, cs:UxPodMonitorSlot
0x1c00cf01b  lea     r8, [rbp+57h+var_80]
0x1c00cf01f  mov     rcx, rax
0x1c00cf022  call    cs:__imp_PsGetPermanentSiloContext
0x1c00cf029  nop     dword ptr [rax+rax+00h]
0x1c00cf02e  mov     rax, [rbp+57h+var_80]
0x1c00cf032  mov     ebx, r15d
0x1c00cf035  mov     rdi, [rsi+30h]
0x1c00cf039  mov     [rbp+57h+arg_18], rax
0x1c00cf03d  test    dword ptr cs:WPP_MAIN_CB.Queue, r12d
0x1c00cf044  jnz     loc_1C00F8FA7
0x1c00cf04a  mov     rax, cs:UxDriverObject
0x1c00cf051  mov     r8, r15
0x1c00cf054  mov     [rbp+57h+arg_8], r15
0x1c00cf058  mov     r12d, 0C000000Dh
0x1c00cf05e  mov     rcx, [rdi+8]
0x1c00cf062  cmp     [rcx+8], rax
0x1c00cf066  jnz     loc_1C00F8FEE
0x1c00cf06c  cmp     qword ptr [rdi+20h], 50505041h
0x1c00cf074  jnz     loc_1C00F8FEE
0x1c00cf07a  mov     rdi, [rdi+18h]
0x1c00cf07e  test    rdi, rdi
0x1c00cf081  jz      loc_1C00F8FE6
0x1c00cf087  cmp     dword ptr [rdi+18h], 50416C55h
0x1c00cf08e  jnz     loc_1C00F8FE6
0x1c00cf094  mov     rax, [rdi+8]
0x1c00cf098  test    rax, rax
0x1c00cf09b  jz      loc_1C00F8FE6
0x1c00cf0a1  cmp     dword ptr [rax+78h], 4F416C55h
0x1c00cf0a8  jnz     loc_1C00F8FE6
0x1c00cf0ae  mov     eax, [rdi+28h]
0x1c00cf0b1  test    al, 1
0x1c00cf0b3  jz      loc_1C00F8FCE
0x1c00cf0b9  call    cs:__imp_PsGetCurrentServerSilo
0x1c00cf0c0  nop     dword ptr [rax+rax+00h]
0x1c00cf0c5  mov     rcx, [rdi+8]
0x1c00cf0c9  cmp     [rcx+140h], rax
0x1c00cf0d0  jnz     loc_1C00F8FD8
0x1c00cf0d6  mov     r8, rdi
0x1c00cf0d9  mov     [rbp+57h+arg_8], rdi
0x1c00cf0dd  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cf0e7  jnz     loc_1C00F8FF8
0x1c00cf0ed  test    ebx, ebx
0x1c00cf0ef  js      loc_1C00CF25F
0x1c00cf0f5  mov     rcx, r13; Irp
0x1c00cf0f8  call    cs:__imp_IoIs32bitProcess
0x1c00cf0ff  nop     dword ptr [rax+rax+00h]
0x1c00cf104  mov     cl, al
0x1c00cf106  mov     r14b, al
0x1c00cf109  neg     cl
0x1c00cf10b  mov     ebx, r15d
0x1c00cf10e  sbb     edi, edi
0x1c00cf110  and     edi, 0FFFFFFF4h
0x1c00cf113  add     edi, 18h
0x1c00cf116  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cf120  jnz     loc_1C00F9012
0x1c00cf126  mov     rdx, r15
0x1c00cf129  mov     [rbp+57h+arg_10], rdx
0x1c00cf12d  cmp     [rsi+10h], edi
0x1c00cf130  jb      loc_1C00F903C
0x1c00cf136  mov     rax, [r13+18h]
0x1c00cf13a  test    rax, rax
0x1c00cf13d  jz      loc_1C00F9046
0x1c00cf143  mov     rdx, rax
0x1c00cf146  mov     [rbp+57h+arg_10], rax
0x1c00cf14a  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cf154  jnz     loc_1C00F904E
0x1c00cf15a  test    ebx, ebx
0x1c00cf15c  js      loc_1C00CF25F
0x1c00cf162  mov     edi, [rdx]
0x1c00cf164  test    r14b, r14b
0x1c00cf167  jnz     loc_1C00F906E
0x1c00cf16d  mov     r14d, edi
0x1c00cf170  and     r14d, 1
0x1c00cf174  cmp     edi, r14d
0x1c00cf177  jnz     loc_1C00CF2B3
0x1c00cf17d  mov     r10b, [r13+40h]
0x1c00cf181  lea     rcx, [rdx+8]; SourceString
0x1c00cf185  xor     eax, eax
0x1c00cf187  xorps   xmm0, xmm0
0x1c00cf18a  movups  [rbp+57h+var_78], xmm0
0x1c00cf18e  mov     [rbp+57h+var_68], rax
0x1c00cf192  call    RtlUnicodeStringValidate
0x1c00cf197  mov     ebx, eax
0x1c00cf199  test    eax, eax
0x1c00cf19b  js      short loc_1C00CF1D5
0x1c00cf19d  movzx   edx, word ptr [rcx]
0x1c00cf1a0  lea     r9, [rbp+57h+var_78]
0x1c00cf1a4  mov     rcx, [rcx+8]; Src
0x1c00cf1a8  mov     r8b, r10b
0x1c00cf1ab  call    UxCaptureWideString
0x1c00cf1b0  mov     ebx, eax
0x1c00cf1b2  test    eax, eax
0x1c00cf1b4  js      short loc_1C00CF1D5
0x1c00cf1b6  movups  xmm0, [rbp+57h+var_78]
0x1c00cf1ba  xor     eax, eax
0x1c00cf1bc  movsd   xmm1, [rbp+57h+var_68]
0x1c00cf1c1  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1c00cf1c5  mov     [rbp+57h+var_68], rax
0x1c00cf1c9  xorps   xmm0, xmm0
0x1c00cf1cc  movsd   [rbp+57h+var_38], xmm1
0x1c00cf1d1  movups  [rbp+57h+var_78], xmm0
0x1c00cf1d5  lea     rcx, [rbp+57h+var_78]
0x1c00cf1d9  call    UxFreeCapturedUnicodeString
0x1c00cf1de  test    ebx, ebx
0x1c00cf1e0  js      short loc_1C00CF25F
0x1c00cf1e2  movzx   eax, word ptr [rbp+57h+Src]
0x1c00cf1e6  test    ax, ax
0x1c00cf1e9  jz      loc_1C00CF2B3
0x1c00cf1ef  mov     r12, [rbp+57h+arg_8]
0x1c00cf1f3  mov     ebx, eax
0x1c00cf1f5  mov     r15, [rbp+57h+Src+8]
0x1c00cf1f9  xor     esi, esi
0x1c00cf1fb  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00cf205  jnz     loc_1C00F9091
0x1c00cf20b  mov     rcx, [rbp+57h+arg_18]
0x1c00cf20f  cmp     [rcx+440h], sil
0x1c00cf216  jz      loc_1C00F90B0
0x1c00cf21c  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00cf226  jnz     loc_1C00F90BA
0x1c00cf22c  xor     edi, edi
0x1c00cf22e  test    r14b, r14b
0x1c00cf231  jnz     loc_1C00F90DC
0x1c00cf237  mov     r9, r12
0x1c00cf23a  mov     r8d, ebx
0x1c00cf23d  mov     rdx, r15
0x1c00cf240  call    UlpFlushUri
0x1c00cf245  mov     ebx, eax
0x1c00cf247  test    eax, eax
0x1c00cf249  js      loc_1C00F9186
0x1c00cf24f  test    dword ptr cs:WPP_MAIN_CB.Queue, 80000h
0x1c00cf259  jnz     loc_1C00F91B0
0x1c00cf25f  lea     rcx, [rbp+57h+Src]
0x1c00cf263  call    UxFreeCapturedUnicodeString
0x1c00cf268  test    dword ptr cs:WPP_MAIN_CB.Queue, 100h
0x1c00cf272  jnz     loc_1C00F91CA
0x1c00cf278  cmp     ebx, 103h
0x1c00cf27e  jz      short loc_1C00CF295
0x1c00cf280  xor     edx, edx; PriorityBoost
0x1c00cf282  mov     [r13+30h], ebx
0x1c00cf286  mov     rcx, r13; Irp
0x1c00cf289  call    cs:__imp_IofCompleteRequest
0x1c00cf290  nop     dword ptr [rax+rax+00h]
0x1c00cf295  mov     eax, ebx
0x1c00cf297  mov     rbx, [rsp+0C0h+arg_0]
0x1c00cf29f  add     rsp, 90h
0x1c00cf2a6  pop     r15
0x1c00cf2a8  pop     r14
0x1c00cf2aa  pop     r13
0x1c00cf2ac  pop     r12
0x1c00cf2ae  pop     rdi
0x1c00cf2af  pop     rsi
0x1c00cf2b0  pop     rbp
0x1c00cf2b1  retn
0x1c00cf2b3  mov     ebx, r12d
0x1c00cf2b6  jmp     short loc_1C00CF25F
0x1c00f8f8a  mov     ecx, 5Bh ; '['
0x1c00f8f8f  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00f8f96  mov     r9, rsi
0x1c00f8f99  mov     r8, r13
0x1c00f8f9c  call    WPP_SF_qq
0x1c00f8fa1  nop
0x1c00f8fa2  jmp     loc_1C00CF005
0x1c00f8fa7  mov     ecx, 0Ch
0x1c00f8fac  lea     rax, [rbp+57h+arg_8]
0x1c00f8fb0  mov     r8, rdi
0x1c00f8fb3  mov     [rsp+0C0h+var_A0], rax
0x1c00f8fb8  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00f8fbf  lea     r9d, [rcx-0Bh]
0x1c00f8fc3  call    WPP_SF_qdP
0x1c00f8fc8  nop
0x1c00f8fc9  jmp     loc_1C00CF04A
0x1c00f8fce  mov     ebx, 0C00000BBh
0x1c00f8fd3  jmp     loc_1C00CF0DD
0x1c00f8fd8  mov     r8, [rbp+57h+arg_8]
0x1c00f8fdc  mov     ebx, 0C0000464h
0x1c00f8fe1  jmp     loc_1C00CF0DD
0x1c00f8fe6  mov     ebx, r12d
0x1c00f8fe9  jmp     loc_1C00CF0DD
0x1c00f8fee  mov     ebx, 0C0000010h
0x1c00f8ff3  jmp     loc_1C00CF0DD
0x1c00f8ff8  mov     ecx, 0Dh
0x1c00f8ffd  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00f9004  mov     r9d, ebx
0x1c00f9007  call    WPP_SF_qD
0x1c00f900c  nop
0x1c00f900d  jmp     loc_1C00CF0ED
0x1c00f9012  lea     rax, [rbp+57h+arg_10]
0x1c00f9016  mov     ecx, 0Eh
0x1c00f901b  mov     [rsp+0C0h+var_98], rax
0x1c00f9020  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00f9027  mov     r9, rsi
0x1c00f902a  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1c00f902e  mov     r8, r13
0x1c00f9031  call    WPP_SF_qilq
0x1c00f9036  nop
0x1c00f9037  jmp     loc_1C00CF126
0x1c00f903c  mov     ebx, 0C0000023h
0x1c00f9041  jmp     loc_1C00CF14A
0x1c00f9046  mov     ebx, r12d
0x1c00f9049  jmp     loc_1C00CF14A
0x1c00f904e  mov     r8, rdx
0x1c00f9051  mov     ecx, 0Fh
0x1c00f9056  lea     rdx, WPP_18ca8755388c316524f95a91261e2540_Traceguids
0x1c00f905d  mov     r9d, ebx
0x1c00f9060  call    WPP_SF_qD
0x1c00f9065  mov     rdx, [rbp+57h+arg_10]
0x1c00f9069  jmp     loc_1C00CF15A
0x1c00f906e  movzx   eax, word ptr [rdx+4]
0x1c00f9072  mov     word ptr [rbp+57h+var_60+8], ax
0x1c00f9076  movzx   eax, word ptr [rdx+6]
0x1c00f907a  mov     word ptr [rbp+57h+var_60+0Ah], ax
0x1c00f907e  mov     eax, [rdx+8]
0x1c00f9081  lea     rdx, [rbp+57h+var_60]
0x1c00f9085  mov     [rbp+57h+var_50], rax
0x1c00f9089  mov     dword ptr [rbp+57h+var_60], edi
0x1c00f908c  jmp     loc_1C00CF16D
0x1c00f9091  mov     r8, [rbp+57h+arg_18]
0x1c00f9095  mov     r9, r15
0x1c00f9098  mov     [rsp+0C0h+var_90], r12
0x1c00f909d  mov     dword ptr [rsp+0C0h+var_98], edi
0x1c00f90a1  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1c00f90a5  call    WPP_SF_qqLLq
0x1c00f90aa  nop
0x1c00f90ab  jmp     loc_1C00CF20B
0x1c00f90b0  mov     ebx, 0C0000184h
0x1c00f90b5  jmp     loc_1C00CF24F
0x1c00f90ba  mov     [rsp+0C0h+var_90], r12
0x1c00f90bf  mov     r9d, ebx
0x1c00f90c2  mov     dword ptr [rsp+0C0h+var_98], r14d
0x1c00f90c7  mov     r8, r15
0x1c00f90ca  mov     dword ptr [rsp+0C0h+var_A0], edi
0x1c00f90ce  call    WPP_SF_SdDdq
0x1c00f90d3  mov     rcx, [rbp+57h+arg_18]
0x1c00f90d7  jmp     loc_1C00CF22C
0x1c00f90dc  lea     rax, [rbx-2]
0x1c00f90e0  mov     ecx, 2Fh ; '/'
0x1c00f90e5  shr     rax, 1
0x1c00f90e8  cmp     [r15+rax*2], cx
0x1c00f90ed  jz      short loc_1C00F9165
0x1c00f90ef  lea     r14d, [rbx+2]
0x1c00f90f3  cmp     r14d, ebx
0x1c00f90f6  jb      loc_1C00F91A6
0x1c00f90fc  lea     eax, [rbx+4]
0x1c00f90ff  cmp     eax, 2
0x1c00f9102  jb      loc_1C00F91A6
0x1c00f9108  xor     r9d, r9d; Priority
0x1c00f910b  lea     rdx, [rbx+4]; NumberOfBytes
0x1c00f910f  mov     r8d, 53556C55h; Tag
0x1c00f9115  lea     ecx, [r9+1]; PoolType
0x1c00f9119  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00f9120  nop     dword ptr [rax+rax+00h]
0x1c00f9125  mov     rsi, rax
0x1c00f9128  test    rax, rax
0x1c00f912b  jnz     short loc_1C00F9137
0x1c00f912d  mov     ebx, 0C000009Ah
0x1c00f9132  jmp     loc_1C00CF24F
0x1c00f9137  mov     r8, rbx; Size
0x1c00f913a  mov     rdx, r15; Src
0x1c00f913d  mov     rcx, rsi; void *
0x1c00f9140  call    memmove
0x1c00f9145  mov     rax, rbx
0x1c00f9148  mov     ecx, 2Fh ; '/'
0x1c00f914d  shr     rax, 1
0x1c00f9150  mov     r15, rsi
0x1c00f9153  mov     [rsi+rax*2], cx
0x1c00f9157  lea     rax, [rbx+2]
0x1c00f915b  shr     rax, 1
0x1c00f915e  mov     ebx, r14d
0x1c00f9161  mov     [rsi+rax*2], di
0x1c00f9165  mov     rcx, [rbp+57h+arg_18]
0x1c00f9169  lea     rdx, UlpFlushFilterUriRecursive
0x1c00f9170  mov     byte ptr [rsp+0C0h+var_98], dil
  ... truncated ...
```
