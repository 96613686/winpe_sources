# LuafvIsTargetWRP

- ea: `0x1400208a0`
- end: `0x140020bdb`
- name: `LuafvIsTargetWRP`
- size: `827`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400258a0`

## callees

- `0x140001730`
- `0x140006080`
- `0x1400208a0`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140020b5b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140020b5b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020b15`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140020b15`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14002093a`
- `ntoskrnl!RtlCreateUnicodeString` at `0x14002093a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140020a73`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140020a73`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020a32`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020a32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020acd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020acd`
- `ntoskrnl!ExAllocatePool2` at `0x140020997`
- `ntoskrnl!ExAllocatePool2` at `0x140020997`
- `FLTMGR!FltReleaseContext` at `0x140020aee`
- `FLTMGR!FltReleaseContext` at `0x140020aee`
- `FLTMGR!FltGetInstanceContext` at `0x140020b97`
- `FLTMGR!FltGetInstanceContext` at `0x140020b97`
- `FLTMGR!FltReleasePushLockEx` at `0x1400209da`
- `FLTMGR!FltReleasePushLockEx` at `0x140020ab0`
- `FLTMGR!FltReleasePushLockEx` at `0x1400209da`
- `FLTMGR!FltReleasePushLockEx` at `0x140020ab0`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400209bf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020a92`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400209bf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140020a92`

## pseudocode

```c
__int64 __fastcall LuafvIsTargetWRP(__int64 a1, __int64 a2, _BYTE *a3)
{
  __int64 v3; // r9
  bool v6; // zf
  __int64 v7; // rbx
  _WORD *v8; // rax
  _WORD *v9; // rax
  unsigned __int16 v10; // dx
  const void *v11; // r13
  int v12; // ebp
  unsigned int v13; // r12d
  char v14; // di
  __int64 Pool2; // r15
  NTSTATUS InstanceContext; // edi
  PWSTR Buffer; // rbx
  unsigned int v19; // edi
  unsigned int v20; // eax
  PVOID v21; // rax
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  PFLT_CONTEXT Context; // [rsp+80h] [rbp+8h] BYREF
  PFLT_INSTANCE Instance; // [rsp+88h] [rbp+10h]

  v3 = *(_QWORD *)(a1 + 16);
  String2 = 0;
  Context = 0;
  DestinationString = 0;
  v6 = (*(_DWORD *)(v3 + 32) & 0x2000) == 0;
  *a3 = 0;
  if ( !v6 )
    goto LABEL_14;
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 80LL) & 0x800) != 0 )
    goto LABEL_14;
  v7 = *(_QWORD *)(v3 + 8);
  v8 = *(_WORD **)(v7 + 96);
  if ( !v8 || !*v8 )
    goto LABEL_14;
  Instance = *(PFLT_INSTANCE *)(a2 + 24);
  if ( !RtlCreateUnicodeString(&DestinationString, L"windows") )
  {
    InstanceContext = -1073741670;
    goto LABEL_15;
  }
  v9 = *(_WORD **)(v7 + 96);
  v10 = *(_WORD *)(v7 + 88);
  v11 = v9 + 1;
  if ( *v9 != 92 )
  {
    v11 = *(const void **)(v7 + 96);
    v10 += 2;
  }
  v12 = v10;
  v13 = v10 + 8;
  if ( v10 > 0xB8u )
  {
    v14 = -1;
LABEL_10:
    Pool2 = ExAllocatePool2(256, v13, 1717663052);
    goto LABEL_11;
  }
  v19 = 0;
  v20 = 56;
  do
  {
    if ( v10 <= v20 )
      break;
    ++v19;
    v20 += 32;
  }
  while ( v19 < 5 );
  v21 = ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)&StringLookaside[16 * (unsigned __int64)v19]);
  v14 = v19 + 2;
  Pool2 = (__int64)v21;
  if ( v14 == -1 )
    goto LABEL_10;
LABEL_11:
  if ( !Pool2 )
  {
    String2.Buffer = 0;
    goto LABEL_25;
  }
  *(_DWORD *)Pool2 = v12;
  *(_BYTE *)(Pool2 + 4) = v14;
  FltAcquirePushLockExclusiveEx(&PoolLock, 0);
  dword_14000F2FC += v12;
  FltReleasePushLockEx(&PoolLock, 0);
  String2.Buffer = (PWSTR)(Pool2 + 8);
  if ( Pool2 == -8 )
  {
LABEL_25:
    InstanceContext = -1073741670;
    goto LABEL_15;
  }
  String2.MaximumLength = v12;
  String2.Length = v12 - 2;
  memmove((void *)(Pool2 + 8), v11, (unsigned __int16)(v12 - 2));
  String2.Buffer[(unsigned __int64)String2.Length >> 1] = 0;
  if ( !RtlPrefixUnicodeString(&DestinationString, &String2, 1u) )
  {
LABEL_14:
    InstanceContext = 0;
    goto LABEL_15;
  }
  InstanceContext = FltGetInstanceContext(Instance, &Context);
  if ( InstanceContext >= 0 )
  {
    InstanceContext = LuafvIsFileWRP(v7 + 88, a2, *((_QWORD *)Context + 4), a3);
    if ( InstanceContext >= 0 )
      goto LABEL_14;
    *a3 = 0;
  }
LABEL_15:
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  Buffer = String2.Buffer;
  if ( String2.Buffer )
  {
    FltAcquirePushLockExclusiveEx(&PoolLock, 0);
    dword_14000F2FC -= *((_DWORD *)Buffer - 2);
    FltReleasePushLockEx(&PoolLock, 0);
    if ( *((_BYTE *)Buffer - 4) < 7u )
      ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)LookasideLists[*((unsigned __int8 *)Buffer - 4)], Buffer - 4);
    else
      ExFreePoolWithTag(Buffer - 4, 0x6661754Cu);
  }
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x1400208a0  mov     rax, rsp
0x1400208a3  push    rdi
0x1400208a4  sub     rsp, 70h
0x1400208a8  mov     r9, [rcx+10h]
0x1400208ac  xorps   xmm0, xmm0
0x1400208af  mov     [rax+18h], rbx
0x1400208b3  xorps   xmm1, xmm1
0x1400208b6  mov     [rax-10h], rbp
0x1400208ba  mov     [rax-18h], rsi
0x1400208be  mov     rsi, rdx
0x1400208c1  mov     [rax-20h], r12
0x1400208c5  mov     [rax-28h], r13
0x1400208c9  mov     [rax-30h], r14
0x1400208cd  mov     r14, r8
0x1400208d0  movups  xmmword ptr [rax-58h], xmm0
0x1400208d4  mov     qword ptr [rax+8], 0
0x1400208dc  movups  xmmword ptr [rax-48h], xmm1
0x1400208e0  test    dword ptr [r9+20h], 2000h
0x1400208e8  mov     [rax-38h], r15
0x1400208ec  mov     byte ptr [r8], 0
0x1400208f0  jnz     loc_140020A46
0x1400208f6  mov     rax, [rdx+20h]
0x1400208fa  test    dword ptr [rax+50h], 800h
0x140020901  jnz     loc_140020A46
0x140020907  mov     rbx, [r9+8]
0x14002090b  mov     rax, [rbx+60h]
0x14002090f  test    rax, rax
0x140020912  jz      loc_140020A46
0x140020918  cmp     word ptr [rax], 0
0x14002091c  jz      loc_140020A46
0x140020922  mov     rax, [rdx+18h]
0x140020926  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002092b  lea     rdx, SourceString; "windows"
0x140020932  mov     [rsp+78h+Instance], rax
0x14002093a  call    cs:__imp_RtlCreateUnicodeString
0x140020941  nop     dword ptr [rax+rax+00h]
0x140020946  test    al, al
0x140020948  jz      loc_140020B7D
0x14002094e  mov     rax, [rbx+60h]
0x140020952  movzx   edx, word ptr [rbx+58h]
0x140020956  cmp     word ptr [rax], 5Ch ; '\'
0x14002095a  lea     r13, [rax+2]
0x14002095e  cmovnz  r13, rax
0x140020962  lea     eax, [rdx+2]
0x140020965  cmovnz  dx, ax
0x140020969  movzx   ebp, dx
0x14002096c  lea     r12d, [rbp+8]
0x140020970  cmp     r12d, 8
0x140020974  jb      loc_140020B23
0x14002097a  cmp     ebp, 0B8h
0x140020980  jbe     loc_140020B36
0x140020986  mov     dil, 0FFh
0x140020989  mov     edx, r12d
0x14002098c  mov     ecx, 100h
0x140020991  mov     r8d, 6661754Ch
0x140020997  call    cs:__imp_ExAllocatePool2
0x14002099e  nop     dword ptr [rax+rax+00h]
0x1400209a3  mov     r15, rax
0x1400209a6  test    r15, r15
0x1400209a9  jz      loc_140020B23
0x1400209af  xor     edx, edx
0x1400209b1  mov     [r15], ebp
0x1400209b4  lea     rcx, PoolLock
0x1400209bb  mov     [r15+4], dil
0x1400209bf  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400209c6  nop     dword ptr [rax+rax+00h]
0x1400209cb  add     cs:dword_14000F2FC, ebp
0x1400209d1  lea     rcx, PoolLock
0x1400209d8  xor     edx, edx
0x1400209da  call    cs:__imp_FltReleasePushLockEx
0x1400209e1  nop     dword ptr [rax+rax+00h]
0x1400209e6  lea     rcx, [r15+8]; void *
0x1400209ea  mov     [rsp+78h+String2.Buffer], rcx
0x1400209ef  test    rcx, rcx
0x1400209f2  jz      loc_140020B2C
0x1400209f8  lea     eax, [rbp-2]
0x1400209fb  mov     [rsp+78h+String2.MaximumLength], bp
0x140020a00  movzx   r8d, ax; Size
0x140020a04  mov     rdx, r13; Src
0x140020a07  mov     [rsp+78h+String2.Length], r8w
0x140020a0d  call    memmove
0x140020a12  movzx   edx, [rsp+78h+String2.Length]
0x140020a17  xor     ecx, ecx
0x140020a19  mov     rax, [rsp+78h+String2.Buffer]
0x140020a1e  mov     r8b, 1; CaseInSensitive
0x140020a21  shr     rdx, 1
0x140020a24  mov     [rax+rdx*2], cx
0x140020a28  lea     rdx, [rsp+78h+String2]; String2
0x140020a2d  lea     rcx, [rsp+78h+DestinationString]; String1
0x140020a32  call    cs:__imp_RtlPrefixUnicodeString
0x140020a39  nop     dword ptr [rax+rax+00h]
0x140020a3e  test    al, al
0x140020a40  jnz     loc_140020B87
0x140020a46  xor     edi, edi
0x140020a48  cmp     [rsp+78h+DestinationString.Buffer], 0
0x140020a4e  mov     r15, [rsp+78h+var_38]
0x140020a53  mov     r14, [rsp+78h+var_30]
0x140020a58  mov     r13, [rsp+78h+var_28]
0x140020a5d  mov     r12, [rsp+78h+var_20]
0x140020a62  mov     rsi, [rsp+78h+var_18]
0x140020a67  mov     rbp, [rsp+78h+var_10]
0x140020a6c  jz      short loc_140020A7F
0x140020a6e  lea     rcx, [rsp+78h+DestinationString]; UnicodeString
0x140020a73  call    cs:__imp_RtlFreeUnicodeString
0x140020a7a  nop     dword ptr [rax+rax+00h]
0x140020a7f  mov     rbx, [rsp+78h+String2.Buffer]
0x140020a84  test    rbx, rbx
0x140020a87  jz      short loc_140020AD9
0x140020a89  xor     edx, edx
0x140020a8b  lea     rcx, PoolLock
0x140020a92  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140020a99  nop     dword ptr [rax+rax+00h]
0x140020a9e  mov     eax, [rbx-8]
0x140020aa1  lea     rcx, PoolLock
0x140020aa8  sub     cs:dword_14000F2FC, eax
0x140020aae  xor     edx, edx
0x140020ab0  call    cs:__imp_FltReleasePushLockEx
0x140020ab7  nop     dword ptr [rax+rax+00h]
0x140020abc  movzx   eax, byte ptr [rbx-4]
0x140020ac0  cmp     al, 7
0x140020ac2  jb      short loc_140020B03
0x140020ac4  mov     edx, 6661754Ch; Tag
0x140020ac9  lea     rcx, [rbx-8]; P
0x140020acd  call    cs:__imp_ExFreePoolWithTag
0x140020ad4  nop     dword ptr [rax+rax+00h]
0x140020ad9  mov     rcx, [rsp+78h+Context]; Context
0x140020ae1  mov     rbx, [rsp+78h+arg_10]
0x140020ae9  test    rcx, rcx
0x140020aec  jz      short loc_140020AFA
0x140020aee  call    cs:__imp_FltReleaseContext
0x140020af5  nop     dword ptr [rax+rax+00h]
0x140020afa  mov     eax, edi
0x140020afc  add     rsp, 70h
0x140020b00  pop     rdi
0x140020b01  retn
0x140020b03  mov     rcx, rax
0x140020b06  lea     rdx, [rbx-8]; Entry
0x140020b0a  lea     rax, LookasideLists
0x140020b11  mov     rcx, [rax+rcx*8]; Lookaside
0x140020b15  call    cs:__imp_ExFreeToPagedLookasideList
0x140020b1c  nop     dword ptr [rax+rax+00h]
0x140020b21  jmp     short loc_140020AD9
0x140020b23  mov     [rsp+78h+String2.Buffer], 0
0x140020b2c  mov     edi, 0C000009Ah
0x140020b31  jmp     loc_140020A48
0x140020b36  xor     edi, edi
0x140020b38  mov     eax, 38h ; '8'
0x140020b3d  cmp     ebp, eax
0x140020b3f  jbe     short loc_140020B4B
0x140020b41  inc     edi
0x140020b43  add     eax, 20h ; ' '
0x140020b46  cmp     edi, 5
0x140020b49  jb      short loc_140020B3D
0x140020b4b  lea     rax, StringLookaside
0x140020b52  mov     ecx, edi
0x140020b54  shl     rcx, 7
0x140020b58  add     rcx, rax; Lookaside
0x140020b5b  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140020b62  nop     dword ptr [rax+rax+00h]
0x140020b67  add     dil, 2
0x140020b6b  mov     r15, rax
0x140020b6e  cmp     dil, 0FFh
0x140020b72  jnz     loc_1400209A6
0x140020b78  jmp     loc_140020989
0x140020b7d  mov     edi, 0C000009Ah
0x140020b82  jmp     loc_140020A48
0x140020b87  mov     rcx, [rsp+78h+Instance]; Instance
0x140020b8f  lea     rdx, [rsp+78h+Context]; Context
0x140020b97  call    cs:__imp_FltGetInstanceContext
0x140020b9e  nop     dword ptr [rax+rax+00h]
0x140020ba3  mov     edi, eax
0x140020ba5  test    eax, eax
0x140020ba7  js      loc_140020A48
0x140020bad  mov     r8, [rsp+78h+Context]
0x140020bb5  lea     rcx, [rbx+58h]
0x140020bb9  mov     r9, r14
0x140020bbc  mov     rdx, rsi
0x140020bbf  mov     r8, [r8+20h]
0x140020bc3  call    LuafvIsFileWRP
0x140020bc8  mov     edi, eax
0x140020bca  test    eax, eax
0x140020bcc  jns     loc_140020A46
0x140020bd2  mov     byte ptr [r14], 0
0x140020bd6  jmp     loc_140020A48
```
