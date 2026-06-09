# CldStreamClose

- ea: `0x14006da80`
- end: `0x14006dc90`
- name: `CldStreamClose`
- size: `528`
- prototype: `void __fastcall(_QWORD *P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14006da40`

## callees

- `0x14000d868`
- `0x14006da80`
- `0x14006dc98`
- `0x14006dd00`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006db16`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006db16`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006db6d`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006db6d`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006dad0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006dad0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006db92`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006db92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc14`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc14`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc46`
- `FLTMGR!FltReleasePushLockEx` at `0x14006dafd`
- `FLTMGR!FltReleasePushLockEx` at `0x14006dba3`
- `FLTMGR!FltReleasePushLockEx` at `0x14006dafd`
- `FLTMGR!FltReleasePushLockEx` at `0x14006dba3`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006dab8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006db7e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006dab8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006db7e`

## pseudocode

```c
void __fastcall CldStreamClose(_QWORD *P)
{
  __int64 v2; // r14
  __int64 v3; // rax
  __int64 v4; // rbx
  __int64 v5; // rsi
  struct _RTL_AVL_TABLE *v6; // rbp
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  __int64 v9; // rax
  KIRQL *v10; // rdx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 Buffer; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  v3 = *(_QWORD *)(*P + 16LL);
  Buffer = *(_QWORD *)(*(_QWORD *)*P + 40LL);
  v4 = *(_QWORD *)(v3 + 32);
  v5 = v4 + 104;
  FltAcquirePushLockExclusiveEx(v4 + 104, 0);
  v6 = (struct _RTL_AVL_TABLE *)(v4 + 112);
  v7 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(v4 + 112), &Buffer);
  v8 = v7;
  if ( v7 )
  {
    v9 = v7[1];
    if ( v9 )
    {
      v2 = v9;
      v8[1] = 0;
    }
  }
  FltReleasePushLockEx(v5, 0);
  if ( v8 )
  {
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)v8 + 2);
    if ( (*(_DWORD *)(**(_QWORD **)v2 + 28LL) & 2) != 0 )
    {
      v14 = (void *)v8[6];
      if ( v14 )
        ExFreePoolWithTag(v14, 0x73557348u);
    }
    else
    {
      v11 = (void *)v8[8];
      if ( v11 )
        ExFreePoolWithTag(v11, 0x6D726C43u);
      v12 = (void *)v8[10];
      if ( v12 )
        ExFreePoolWithTag(v12, 0x6D726C43u);
      FsRtlUninitializeBaseMcb((PBASE_MCB)(v8 + 4));
    }
    FltAcquirePushLockExclusiveEx(v5, 0);
    RtlDeleteElementGenericTableAvl(v6, &Buffer);
    FltReleasePushLockEx(v5, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      36,
      WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids,
      P,
      *(_QWORD *)(*(_QWORD *)*P + 40LL),
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)*P + 16LL) + 32LL));
  }
  CldiStreamCompleteProviderRequest(P, v10);
  if ( (*(_DWORD *)(*(_QWORD *)*P + 28LL) & 2) == 0 )
    CldStreamPurgeCache(P);
  v13 = (void *)P[8];
  if ( v13 )
    ExFreePoolWithTag(v13, 0x68727343u);
  ExFreePoolWithTag(P, 0x74736C43u);
}

```

## disassembly

```asm
0x14006da80  mov     [rsp+arg_8], rbx
0x14006da85  mov     [rsp+arg_10], rbp
0x14006da8a  push    rsi
0x14006da8b  push    rdi
0x14006da8c  push    r14
0x14006da8e  sub     rsp, 30h
0x14006da92  mov     r8, [rcx]
0x14006da95  mov     rdi, rcx
0x14006da98  xor     r14d, r14d
0x14006da9b  mov     rax, [r8]
0x14006da9e  mov     rdx, [rax+28h]
0x14006daa2  mov     rax, [r8+10h]
0x14006daa6  mov     [rsp+48h+Buffer], rdx
0x14006daab  xor     edx, edx
0x14006daad  mov     rbx, [rax+20h]
0x14006dab1  lea     rsi, [rbx+68h]
0x14006dab5  mov     rcx, rsi
0x14006dab8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006dabf  nop     dword ptr [rax+rax+00h]
0x14006dac4  lea     rbp, [rbx+70h]
0x14006dac8  mov     rcx, rbp; Table
0x14006dacb  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14006dad0  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14006dad7  nop     dword ptr [rax+rax+00h]
0x14006dadc  mov     rbx, rax
0x14006dadf  test    rax, rax
0x14006dae2  jz      short loc_14006DAF8
0x14006dae4  mov     rax, [rax+8]
0x14006dae8  test    rax, rax
0x14006daeb  jz      short loc_14006DAF8
0x14006daed  mov     r14, rax
0x14006daf0  mov     qword ptr [rbx+8], 0
0x14006daf8  xor     edx, edx
0x14006dafa  mov     rcx, rsi
0x14006dafd  call    cs:__imp_FltReleasePushLockEx
0x14006db04  nop     dword ptr [rax+rax+00h]
0x14006db09  test    rbx, rbx
0x14006db0c  jz      loc_14006DBAF
0x14006db12  lea     rcx, [rbx+10h]; RunRef
0x14006db16  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14006db1d  nop     dword ptr [rax+rax+00h]
0x14006db22  mov     rax, [r14]
0x14006db25  mov     rcx, [rax]
0x14006db28  mov     eax, [rcx+1Ch]
0x14006db2b  test    al, 2
0x14006db2d  jnz     loc_14006DC34
0x14006db33  mov     rcx, [rbx+40h]; P
0x14006db37  mov     r14d, 6D726C43h
0x14006db3d  test    rcx, rcx
0x14006db40  jz      short loc_14006DB51
0x14006db42  mov     edx, r14d; Tag
0x14006db45  call    cs:__imp_ExFreePoolWithTag
0x14006db4c  nop     dword ptr [rax+rax+00h]
0x14006db51  mov     rcx, [rbx+50h]; P
0x14006db55  test    rcx, rcx
0x14006db58  jz      short loc_14006DB69
0x14006db5a  mov     edx, r14d; Tag
0x14006db5d  call    cs:__imp_ExFreePoolWithTag
0x14006db64  nop     dword ptr [rax+rax+00h]
0x14006db69  lea     rcx, [rbx+20h]; Mcb
0x14006db6d  call    cs:__imp_FsRtlUninitializeBaseMcb
0x14006db74  nop     dword ptr [rax+rax+00h]
0x14006db79  xor     edx, edx
0x14006db7b  mov     rcx, rsi
0x14006db7e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006db85  nop     dword ptr [rax+rax+00h]
0x14006db8a  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14006db8f  mov     rcx, rbp; Table
0x14006db92  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14006db99  nop     dword ptr [rax+rax+00h]
0x14006db9e  xor     edx, edx
0x14006dba0  mov     rcx, rsi
0x14006dba3  call    cs:__imp_FltReleasePushLockEx
0x14006dbaa  nop     dword ptr [rax+rax+00h]
0x14006dbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dbb6  lea     rax, WPP_GLOBAL_Control
0x14006dbbd  cmp     rcx, rax
0x14006dbc0  jz      short loc_14006DBD5
0x14006dbc2  test    dword ptr [rcx+2Ch], 100h
0x14006dbc9  jz      short loc_14006DBD5
0x14006dbcb  cmp     byte ptr [rcx+29h], 5
0x14006dbcf  jnb     loc_14006DC57
0x14006dbd5  mov     rcx, rdi
0x14006dbd8  call    CldiStreamCompleteProviderRequest
0x14006dbdd  mov     rax, [rdi]
0x14006dbe0  mov     rcx, [rax]
0x14006dbe3  mov     eax, [rcx+1Ch]
0x14006dbe6  test    al, 2
0x14006dbe8  jnz     short loc_14006DBF2
0x14006dbea  mov     rcx, rdi
0x14006dbed  call    CldStreamPurgeCache
0x14006dbf2  mov     rcx, [rdi+40h]; P
0x14006dbf6  test    rcx, rcx
0x14006dbf9  jz      short loc_14006DC0C
0x14006dbfb  mov     edx, 68727343h; Tag
0x14006dc00  call    cs:__imp_ExFreePoolWithTag
0x14006dc07  nop     dword ptr [rax+rax+00h]
0x14006dc0c  mov     edx, 74736C43h; Tag
0x14006dc11  mov     rcx, rdi; P
0x14006dc14  call    cs:__imp_ExFreePoolWithTag
0x14006dc1b  nop     dword ptr [rax+rax+00h]
0x14006dc20  mov     rbx, [rsp+48h+arg_8]
0x14006dc25  mov     rbp, [rsp+48h+arg_10]
0x14006dc2a  add     rsp, 30h
0x14006dc2e  pop     r14
0x14006dc30  pop     rdi
0x14006dc31  pop     rsi
0x14006dc32  retn
0x14006dc34  mov     rcx, [rbx+30h]; P
0x14006dc38  test    rcx, rcx
0x14006dc3b  jz      loc_14006DB79
0x14006dc41  mov     edx, 73557348h; Tag
0x14006dc46  call    cs:__imp_ExFreePoolWithTag
0x14006dc4d  nop     dword ptr [rax+rax+00h]
0x14006dc52  jmp     loc_14006DB79
0x14006dc57  mov     rax, [rdi]
0x14006dc5a  mov     edx, 24h ; '$'
0x14006dc5f  mov     rcx, [rcx+18h]
0x14006dc63  mov     r9, rdi
0x14006dc66  mov     r8, [rax]
0x14006dc69  mov     rax, [r8+10h]
0x14006dc6d  mov     rax, [rax+20h]
0x14006dc71  mov     [rsp+48h+var_20], rax
0x14006dc76  mov     rax, [r8+28h]
0x14006dc7a  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006dc81  mov     [rsp+48h+var_28], rax
0x14006dc86  call    WPP_SF_qqq
0x14006dc8b  jmp     loc_14006DBD5
```
