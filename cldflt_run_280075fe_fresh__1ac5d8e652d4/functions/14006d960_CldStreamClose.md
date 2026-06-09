# CldStreamClose

- ea: `0x14006d960`
- end: `0x14006db70`
- name: `CldStreamClose`
- size: `528`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14006d920`

## callees

- `0x14000d868`
- `0x14006d960`
- `0x14006db78`
- `0x14006dbe0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006d9f6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14006d9f6`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006da4d`
- `ntoskrnl!FsRtlUninitializeBaseMcb` at `0x14006da4d`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006d9b0`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x14006d9b0`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006da72`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14006da72`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da25`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db26`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da25`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006da3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006daf4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006db26`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d9dd`
- `FLTMGR!FltReleasePushLockEx` at `0x14006da83`
- `FLTMGR!FltReleasePushLockEx` at `0x14006d9dd`
- `FLTMGR!FltReleasePushLockEx` at `0x14006da83`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d998`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006da5e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006d998`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14006da5e`

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
  void *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
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
      v13 = (void *)v8[6];
      if ( v13 )
        ExFreePoolWithTag(v13, 0x73557348u);
    }
    else
    {
      v10 = (void *)v8[8];
      if ( v10 )
        ExFreePoolWithTag(v10, 0x6D726C43u);
      v11 = (void *)v8[10];
      if ( v11 )
        ExFreePoolWithTag(v11, 0x6D726C43u);
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
  CldiStreamCompleteProviderRequest(P);
  if ( (*(_DWORD *)(*(_QWORD *)*P + 28LL) & 2) == 0 )
    CldStreamPurgeCache(P);
  v12 = (void *)P[8];
  if ( v12 )
    ExFreePoolWithTag(v12, 0x68727343u);
  ExFreePoolWithTag(P, 0x74736C43u);
}

```

## disassembly

```asm
0x14006d960  mov     [rsp+arg_8], rbx
0x14006d965  mov     [rsp+arg_10], rbp
0x14006d96a  push    rsi
0x14006d96b  push    rdi
0x14006d96c  push    r14
0x14006d96e  sub     rsp, 30h
0x14006d972  mov     r8, [rcx]
0x14006d975  mov     rdi, rcx
0x14006d978  xor     r14d, r14d
0x14006d97b  mov     rax, [r8]
0x14006d97e  mov     rdx, [rax+28h]
0x14006d982  mov     rax, [r8+10h]
0x14006d986  mov     [rsp+48h+Buffer], rdx
0x14006d98b  xor     edx, edx
0x14006d98d  mov     rbx, [rax+20h]
0x14006d991  lea     rsi, [rbx+68h]
0x14006d995  mov     rcx, rsi
0x14006d998  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006d99f  nop     dword ptr [rax+rax+00h]
0x14006d9a4  lea     rbp, [rbx+70h]
0x14006d9a8  mov     rcx, rbp; Table
0x14006d9ab  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14006d9b0  call    cs:__imp_RtlLookupElementGenericTableAvl
0x14006d9b7  nop     dword ptr [rax+rax+00h]
0x14006d9bc  mov     rbx, rax
0x14006d9bf  test    rax, rax
0x14006d9c2  jz      short loc_14006D9D8
0x14006d9c4  mov     rax, [rax+8]
0x14006d9c8  test    rax, rax
0x14006d9cb  jz      short loc_14006D9D8
0x14006d9cd  mov     r14, rax
0x14006d9d0  mov     qword ptr [rbx+8], 0
0x14006d9d8  xor     edx, edx
0x14006d9da  mov     rcx, rsi
0x14006d9dd  call    cs:__imp_FltReleasePushLockEx
0x14006d9e4  nop     dword ptr [rax+rax+00h]
0x14006d9e9  test    rbx, rbx
0x14006d9ec  jz      loc_14006DA8F
0x14006d9f2  lea     rcx, [rbx+10h]; RunRef
0x14006d9f6  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14006d9fd  nop     dword ptr [rax+rax+00h]
0x14006da02  mov     rax, [r14]
0x14006da05  mov     rcx, [rax]
0x14006da08  mov     eax, [rcx+1Ch]
0x14006da0b  test    al, 2
0x14006da0d  jnz     loc_14006DB14
0x14006da13  mov     rcx, [rbx+40h]; P
0x14006da17  mov     r14d, 6D726C43h
0x14006da1d  test    rcx, rcx
0x14006da20  jz      short loc_14006DA31
0x14006da22  mov     edx, r14d; Tag
0x14006da25  call    cs:__imp_ExFreePoolWithTag
0x14006da2c  nop     dword ptr [rax+rax+00h]
0x14006da31  mov     rcx, [rbx+50h]; P
0x14006da35  test    rcx, rcx
0x14006da38  jz      short loc_14006DA49
0x14006da3a  mov     edx, r14d; Tag
0x14006da3d  call    cs:__imp_ExFreePoolWithTag
0x14006da44  nop     dword ptr [rax+rax+00h]
0x14006da49  lea     rcx, [rbx+20h]; Mcb
0x14006da4d  call    cs:__imp_FsRtlUninitializeBaseMcb
0x14006da54  nop     dword ptr [rax+rax+00h]
0x14006da59  xor     edx, edx
0x14006da5b  mov     rcx, rsi
0x14006da5e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006da65  nop     dword ptr [rax+rax+00h]
0x14006da6a  lea     rdx, [rsp+48h+Buffer]; Buffer
0x14006da6f  mov     rcx, rbp; Table
0x14006da72  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14006da79  nop     dword ptr [rax+rax+00h]
0x14006da7e  xor     edx, edx
0x14006da80  mov     rcx, rsi
0x14006da83  call    cs:__imp_FltReleasePushLockEx
0x14006da8a  nop     dword ptr [rax+rax+00h]
0x14006da8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006da96  lea     rax, WPP_GLOBAL_Control
0x14006da9d  cmp     rcx, rax
0x14006daa0  jz      short loc_14006DAB5
0x14006daa2  test    dword ptr [rcx+2Ch], 100h
0x14006daa9  jz      short loc_14006DAB5
0x14006daab  cmp     byte ptr [rcx+29h], 5
0x14006daaf  jnb     loc_14006DB37
0x14006dab5  mov     rcx, rdi
0x14006dab8  call    CldiStreamCompleteProviderRequest
0x14006dabd  mov     rax, [rdi]
0x14006dac0  mov     rcx, [rax]
0x14006dac3  mov     eax, [rcx+1Ch]
0x14006dac6  test    al, 2
0x14006dac8  jnz     short loc_14006DAD2
0x14006daca  mov     rcx, rdi
0x14006dacd  call    CldStreamPurgeCache
0x14006dad2  mov     rcx, [rdi+40h]; P
0x14006dad6  test    rcx, rcx
0x14006dad9  jz      short loc_14006DAEC
0x14006dadb  mov     edx, 68727343h; Tag
0x14006dae0  call    cs:__imp_ExFreePoolWithTag
0x14006dae7  nop     dword ptr [rax+rax+00h]
0x14006daec  mov     edx, 74736C43h; Tag
0x14006daf1  mov     rcx, rdi; P
0x14006daf4  call    cs:__imp_ExFreePoolWithTag
0x14006dafb  nop     dword ptr [rax+rax+00h]
0x14006db00  mov     rbx, [rsp+48h+arg_8]
0x14006db05  mov     rbp, [rsp+48h+arg_10]
0x14006db0a  add     rsp, 30h
0x14006db0e  pop     r14
0x14006db10  pop     rdi
0x14006db11  pop     rsi
0x14006db12  retn
0x14006db14  mov     rcx, [rbx+30h]; P
0x14006db18  test    rcx, rcx
0x14006db1b  jz      loc_14006DA59
0x14006db21  mov     edx, 73557348h; Tag
0x14006db26  call    cs:__imp_ExFreePoolWithTag
0x14006db2d  nop     dword ptr [rax+rax+00h]
0x14006db32  jmp     loc_14006DA59
0x14006db37  mov     rax, [rdi]
0x14006db3a  mov     edx, 24h ; '$'
0x14006db3f  mov     rcx, [rcx+18h]
0x14006db43  mov     r9, rdi
0x14006db46  mov     r8, [rax]
0x14006db49  mov     rax, [r8+10h]
0x14006db4d  mov     rax, [rax+20h]
0x14006db51  mov     [rsp+48h+var_20], rax
0x14006db56  mov     rax, [r8+28h]
0x14006db5a  lea     r8, WPP_80e9beeee63631c5fe996ea78830fea1_Traceguids
0x14006db61  mov     [rsp+48h+var_28], rax
0x14006db66  call    WPP_SF_qqq
0x14006db6b  jmp     loc_14006DAB5
```
