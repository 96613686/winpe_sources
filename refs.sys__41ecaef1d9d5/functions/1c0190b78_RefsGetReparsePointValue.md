# RefsGetReparsePointValue

- ea: `0x1c0190b78`
- end: `0x1c0191088`
- name: `RefsGetReparsePointValue`
- size: `1296`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `reparse_path`

## callers

- `0x1c0153d80`
- `0x1c015eb64`
- `0x1c0194f50`

## callees

- `0x1c000193c`
- `0x1c0003658`
- `0x1c000f770`
- `0x1c003af60`
- `0x1c003b21c`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00925e8`
- `0x1c00a29c4`
- `0x1c00ad610`
- `0x1c01632d4`
- `0x1c0190b78`
- `0x1c0191090`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0190f4f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0190f4f`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c0190e4f`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c0190e95`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c0190e4f`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c0190e95`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c0190da1`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x1c0190da1`

## string_xrefs

- `0x1c0190c30`: `Create.c`
- `0x1c0190cda`: `Create.c`
- `0x1c0190d7f`: `Create.c`
- `0x1c0190f24`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsGetReparsePointValue(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4, __int16 a5, char a6)
{
  unsigned int v9; // ebx
  int v10; // r8d
  char v11; // al
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // edx
  int v15; // ecx
  unsigned int v16; // eax
  ULONG v17; // r13d
  unsigned __int64 v18; // rcx
  NTSTATUS v19; // edi
  PREPARSE_DATA_BUFFER v20; // r15
  union _REPARSE_DATA_BUFFER::$EDE85F431271D6DB35F60DFE09C35EC8 *p_SymbolicLinkReparseBuffer; // rax
  _QWORD *v22; // r13
  __int64 v23; // rax
  __int64 v24; // r15
  char IsNonEmptyDirectoryReparsePointAllowed; // al
  ULONG v26; // ebx
  PVOID PoolWithTag; // rax
  int v28; // edx
  unsigned int v29; // edx
  __int64 v30; // rdx
  ULONG BufferLength; // [rsp+58h] [rbp-150h] BYREF
  __int64 v33; // [rsp+60h] [rbp-148h]
  PREPARSE_DATA_BUFFER ReparseBuffer; // [rsp+68h] [rbp-140h] BYREF
  _QWORD *v35; // [rsp+70h] [rbp-138h]
  __int64 v36; // [rsp+78h] [rbp-130h]
  __int128 v37; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v38[208]; // [rsp+90h] [rbp-118h] BYREF

  v33 = a4;
  v35 = a3;
  v36 = a1;
  memset(v38, 0, sizeof(v38));
  v37 = 0;
  ReparseBuffer = 0;
  BufferLength = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 192, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 260);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(260);
  v9 = 1;
  RefsInitializeAttributeContext(v38);
  v11 = RefsLookupInFileRecord(a1, a4, v10, 192, 0);
  v14 = a4;
  v15 = a1;
  if ( !v11 )
  {
    v16 = RefsQueueTriageForDeadFcb(a1, a4, v12, v13);
    v9 = v16;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 193, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, a4, v16);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(v9);
    RefsRaiseStatusInternal(a1, v9);
  }
  RefsMapAttributeValue(
    v15,
    v14,
    (unsigned int)&ReparseBuffer,
    (unsigned int)&BufferLength,
    (__int64)&v37,
    (__int64)v38);
  v17 = BufferLength;
  if ( BufferLength > 0x4000 )
  {
    v18 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v19 = -1073741192;
    }
    else
    {
      v19 = -1073741192;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 194, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221226104LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741192);
    goto LABEL_64;
  }
  v20 = ReparseBuffer;
  v19 = FsRtlValidateReparsePointBuffer(BufferLength, ReparseBuffer);
  if ( v19 < 0 )
  {
    if ( a6 )
    {
      v18 = *(_QWORD *)(a2 + 168);
      if ( (*(_DWORD *)(v18 + 16) & 0x200000) != 0 )
        v19 = 0;
    }
    goto LABEL_64;
  }
  p_SymbolicLinkReparseBuffer = (union _REPARSE_DATA_BUFFER::$EDE85F431271D6DB35F60DFE09C35EC8 *)&v20->SymbolicLinkReparseBuffer;
  if ( v17 < (unsigned int)v20->ReparseDataLength + 24 )
    p_SymbolicLinkReparseBuffer = 0;
  v22 = v35;
  RefsLookupOpenReparseEcp(v18, v35, a2, v20->ReparseTag, p_SymbolicLinkReparseBuffer);
  v23 = *(_QWORD *)(a2 + 192);
  if ( v23 )
  {
    *(_DWORD *)(v23 + 20) |= v9;
    if ( a6 )
    {
      v24 = v33;
      if ( (*(_DWORD *)(v33 + 160) & 0x10000000) == 0
        || !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(a2 + 184))
        || (v18 = *(unsigned int *)(*(_QWORD *)(a2 + 192) + 20LL), (v18 & 8) == 0) )
      {
        LOBYTE(v9) = 0;
      }
      goto LABEL_42;
    }
  }
  else if ( a6 )
  {
    v24 = v33;
    if ( (*(_DWORD *)(v33 + 160) & 0x10000000) != 0 )
    {
      IsNonEmptyDirectoryReparsePointAllowed = FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(a2 + 184));
      v18 = (unsigned __int8)v9;
      if ( IsNonEmptyDirectoryReparsePointAllowed )
        v18 = 0;
      LOBYTE(v9) = v18;
    }
    goto LABEL_42;
  }
  v24 = v33;
LABEL_42:
  if ( !(_BYTE)v9 || a6 && (*(_DWORD *)(*(_QWORD *)(a2 + 168) + 16LL) & 0x200000) != 0 )
  {
    v19 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 260);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(260);
    v19 = 260;
    v26 = BufferLength;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)528, BufferLength, 0x43466552u);
    v22[20] = PoolWithTag;
    memmove(PoolWithTag, ReparseBuffer, v26);
    if ( (*(_BYTE *)(v22[23] + 2LL) & 4) != 0 )
      a5 += *(_WORD *)(a2 + 84) - *(_WORD *)(a2 + 16);
    v18 = v22[20];
    *(_WORD *)(v18 + 6) = a5;
    if ( !*(_BYTE *)(a1 + 40) && *(_DWORD *)v18 == -1610612724 )
    {
      v28 = *(_DWORD *)(v18 + 16);
      if ( (*(_DWORD *)(v24 + 160) & 0x10000000) != 0 )
        v29 = v28 | 0x80000000;
      else
        v29 = v28 | 0x40000000;
      *(_DWORD *)(v18 + 16) = v29;
    }
    v30 = *(_QWORD *)(a2 + 192);
    if ( v30 && *(int *)(v30 + 20) < 0 )
      *(_WORD *)(v30 + 42) = a5;
    v22[7] = *(unsigned int *)v18;
  }
LABEL_64:
  RefsUnmapAttribute(v18, v38, &v37);
  RefsCleanupAttributeContext(a1, v38);
  RefsCheckpointCurrentTransaction(a1);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1c0190b78  push    rbx
0x1c0190b7a  push    rsi
0x1c0190b7b  push    rdi
0x1c0190b7c  push    r12
0x1c0190b7e  push    r13
0x1c0190b80  push    r15
0x1c0190b82  sub     rsp, 178h
0x1c0190b89  mov     rax, cs:__security_cookie
0x1c0190b90  xor     rax, rsp
0x1c0190b93  mov     [rsp+1A8h+var_48], rax
0x1c0190b9b  mov     rdi, r9
0x1c0190b9e  mov     [rsp+1A8h+var_148], r9
0x1c0190ba3  mov     [rsp+1A8h+var_138], r8
0x1c0190ba8  mov     rsi, rdx
0x1c0190bab  mov     r12, rcx
0x1c0190bae  mov     [rsp+1A8h+var_130], rcx
0x1c0190bb3  xor     edx, edx; Val
0x1c0190bb5  mov     r8d, 0D0h; Size
0x1c0190bbb  lea     rcx, [rsp+1A8h+var_118]; void *
0x1c0190bc3  call    memset
0x1c0190bc8  xorps   xmm0, xmm0
0x1c0190bcb  movups  [rsp+1A8h+var_128], xmm0
0x1c0190bd3  xor     r15d, r15d
0x1c0190bd6  mov     [rsp+1A8h+ReparseBuffer], r15
0x1c0190bdb  mov     [rsp+1A8h+BufferLength], r15d
0x1c0190be0  mov     [rsp+1A8h+var_157], r15b
0x1c0190be5  lea     r13, WPP_GLOBAL_Control
0x1c0190bec  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0190bf3  cmp     rcx, r13
0x1c0190bf6  jz      short loc_1C0190C20
0x1c0190bf8  mov     eax, [rcx+2Ch]
0x1c0190bfb  bt      eax, 8
0x1c0190bff  jnb     short loc_1C0190C20
0x1c0190c01  cmp     byte ptr [rcx+29h], 5
0x1c0190c05  jb      short loc_1C0190C20
0x1c0190c07  mov     edx, 0C0h
0x1c0190c0c  lea     r9d, [rdx+44h]
0x1c0190c10  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0190c17  mov     rcx, [rcx+18h]
0x1c0190c1b  call    WPP_SF_D
0x1c0190c20  mov     al, cs:RefsStatusDebugEnabled
0x1c0190c26  test    al, al
0x1c0190c28  jz      short loc_1C0190C42
0x1c0190c2a  mov     r8d, 4347h
0x1c0190c30  lea     rdx, aCreateC; "Create.c"
0x1c0190c37  mov     ecx, 104h; Status
0x1c0190c3c  call    RefsStatusDebug
0x1c0190c41  nop
0x1c0190c42  mov     ebx, 1
0x1c0190c47  mov     [rsp+1A8h+var_157], bl
0x1c0190c4b  lea     rcx, [rsp+1A8h+var_118]
0x1c0190c53  call    RefsInitializeAttributeContext
0x1c0190c58  lea     rax, [rsp+1A8h+var_118]
0x1c0190c60  mov     [rsp+1A8h+var_160], rax
0x1c0190c65  mov     [rsp+1A8h+var_178], r15b
0x1c0190c6a  mov     [rsp+1A8h+var_188], r15
0x1c0190c6f  mov     r9d, 0C0h
0x1c0190c75  mov     rdx, rdi
0x1c0190c78  mov     rcx, r12
0x1c0190c7b  call    RefsLookupInFileRecord
0x1c0190c80  mov     rdx, rdi
0x1c0190c83  mov     rcx, r12
0x1c0190c86  test    al, al
0x1c0190c88  jnz     short loc_1C0190CF2
0x1c0190c8a  call    RefsQueueTriageForDeadFcb
0x1c0190c8f  mov     ebx, eax
0x1c0190c91  mov     r10, cs:WPP_GLOBAL_Control
0x1c0190c98  cmp     r10, r13
0x1c0190c9b  jz      short loc_1C0190CCA
0x1c0190c9d  test    dword ptr [r10+2Ch], 100h
0x1c0190ca5  jz      short loc_1C0190CCA
0x1c0190ca7  cmp     byte ptr [r10+29h], 4
0x1c0190cac  jb      short loc_1C0190CCA
0x1c0190cae  mov     edx, 0C1h
0x1c0190cb3  mov     dword ptr [rsp+1A8h+var_188], eax
0x1c0190cb7  mov     r9, rdi
0x1c0190cba  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0190cc1  mov     rcx, [r10+18h]
0x1c0190cc5  call    WPP_SF_qd
0x1c0190cca  mov     al, cs:RefsStatusDebugEnabled
0x1c0190cd0  test    al, al
0x1c0190cd2  jz      short loc_1C0190CE8
0x1c0190cd4  mov     r8d, 4366h
0x1c0190cda  lea     rdx, aCreateC; "Create.c"
0x1c0190ce1  mov     ecx, ebx; Status
0x1c0190ce3  call    RefsStatusDebug
0x1c0190ce8  mov     edx, ebx
0x1c0190cea  mov     rcx, r12
0x1c0190ced  call    RefsRaiseStatusInternal
0x1c0190cf2  lea     rax, [rsp+1A8h+var_118]
0x1c0190cfa  mov     [rsp+1A8h+var_180], rax
0x1c0190cff  lea     rax, [rsp+1A8h+var_128]
0x1c0190d07  mov     [rsp+1A8h+var_188], rax
0x1c0190d0c  lea     r9, [rsp+1A8h+BufferLength]
0x1c0190d11  lea     r8, [rsp+1A8h+ReparseBuffer]
0x1c0190d16  call    RefsMapAttributeValue
0x1c0190d1b  mov     r13d, [rsp+1A8h+BufferLength]
0x1c0190d20  cmp     r13d, 4000h
0x1c0190d27  jbe     short loc_1C0190D96
0x1c0190d29  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0190d30  lea     rax, WPP_GLOBAL_Control
0x1c0190d37  cmp     rcx, rax
0x1c0190d3a  jz      short loc_1C0190D6A
0x1c0190d3c  mov     eax, [rcx+2Ch]
0x1c0190d3f  bt      eax, 8
0x1c0190d43  jnb     short loc_1C0190D6A
0x1c0190d45  cmp     byte ptr [rcx+29h], 4
0x1c0190d49  jb      short loc_1C0190D6A
0x1c0190d4b  mov     edx, 0C2h
0x1c0190d50  mov     edi, 0C0000278h
0x1c0190d55  mov     r9d, edi
0x1c0190d58  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0190d5f  mov     rcx, [rcx+18h]
0x1c0190d63  call    WPP_SF_D
0x1c0190d68  jmp     short loc_1C0190D6F
0x1c0190d6a  mov     edi, 0C0000278h
0x1c0190d6f  mov     al, cs:RefsStatusDebugEnabled
0x1c0190d75  test    al, al
0x1c0190d77  jz      short loc_1C0190D8D
0x1c0190d79  mov     r8d, 437Ah
0x1c0190d7f  lea     rdx, aCreateC; "Create.c"
0x1c0190d86  mov     ecx, edi; Status
0x1c0190d88  call    RefsStatusDebug
0x1c0190d8d  mov     [rsp+1A8h+var_154], edi
0x1c0190d91  jmp     loc_1C0190FFD
0x1c0190d96  mov     r15, [rsp+1A8h+ReparseBuffer]
0x1c0190d9b  mov     rdx, r15; ReparseBuffer
0x1c0190d9e  mov     ecx, r13d; BufferLength
0x1c0190da1  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x1c0190da8  nop     dword ptr [rax+rax+00h]
0x1c0190dad  mov     edi, eax
0x1c0190daf  mov     [rsp+1A8h+var_154], eax
0x1c0190db3  xor     r8d, r8d
0x1c0190db6  test    eax, eax
0x1c0190db8  jns     short loc_1C0190DE9
0x1c0190dba  cmp     [rsp+1A8h+arg_28], r8b
0x1c0190dc2  jz      loc_1C0190FFD
0x1c0190dc8  mov     rcx, [rsi+0A8h]
0x1c0190dcf  test    dword ptr [rcx+10h], 200000h
0x1c0190dd6  jz      loc_1C0190FFD
0x1c0190ddc  mov     edi, r8d
0x1c0190ddf  mov     [rsp+1A8h+var_154], r8d
0x1c0190de4  jmp     loc_1C0190FFD
0x1c0190de9  mov     [rsp+1A8h+var_158], bl
0x1c0190ded  movzx   eax, word ptr [r15+4]
0x1c0190df2  add     eax, 18h
0x1c0190df5  cmp     r13d, eax
0x1c0190df8  lea     rax, [r15+8]
0x1c0190dfc  jnb     short loc_1C0190E01
0x1c0190dfe  mov     rax, r8
0x1c0190e01  mov     [rsp+1A8h+var_188], rax
0x1c0190e06  mov     r9d, [r15]
0x1c0190e09  mov     r8, rsi
0x1c0190e0c  mov     r13, [rsp+1A8h+var_138]
0x1c0190e11  mov     rdx, r13
0x1c0190e14  call    RefsLookupOpenReparseEcp
0x1c0190e19  mov     rax, [rsi+0C0h]
0x1c0190e20  xor     edx, edx
0x1c0190e22  mov     dil, [rsp+1A8h+arg_28]
0x1c0190e2a  test    rax, rax
0x1c0190e2d  jz      short loc_1C0190E78
0x1c0190e2f  or      [rax+14h], ebx
0x1c0190e32  test    dil, dil
0x1c0190e35  jz      short loc_1C0190EB3
0x1c0190e37  mov     r15, [rsp+1A8h+var_148]
0x1c0190e3c  mov     eax, [r15+0A0h]
0x1c0190e43  bt      eax, 1Ch
0x1c0190e47  jnb     short loc_1C0190E70
0x1c0190e49  mov     ecx, [rsi+0B8h]
0x1c0190e4f  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1c0190e56  nop     dword ptr [rax+rax+00h]
0x1c0190e5b  xor     edx, edx
0x1c0190e5d  test    al, al
0x1c0190e5f  jz      short loc_1C0190E70
0x1c0190e61  mov     rax, [rsi+0C0h]
0x1c0190e68  mov     ecx, [rax+14h]
0x1c0190e6b  test    cl, 8
0x1c0190e6e  jnz     short loc_1C0190EB8
0x1c0190e70  mov     bl, dl
0x1c0190e72  mov     [rsp+1A8h+var_158], dl
0x1c0190e76  jmp     short loc_1C0190EB8
0x1c0190e78  test    dil, dil
0x1c0190e7b  jz      short loc_1C0190EB3
0x1c0190e7d  mov     r15, [rsp+1A8h+var_148]
0x1c0190e82  mov     eax, [r15+0A0h]
0x1c0190e89  bt      eax, 1Ch
0x1c0190e8d  jnb     short loc_1C0190EB8
0x1c0190e8f  mov     ecx, [rsi+0B8h]
0x1c0190e95  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x1c0190e9c  nop     dword ptr [rax+rax+00h]
0x1c0190ea1  movzx   ecx, bl
0x1c0190ea4  xor     edx, edx
0x1c0190ea6  test    al, al
0x1c0190ea8  cmovnz  ecx, edx
0x1c0190eab  mov     bl, cl
0x1c0190ead  mov     [rsp+1A8h+var_158], cl
0x1c0190eb1  jmp     short loc_1C0190EB8
0x1c0190eb3  mov     r15, [rsp+1A8h+var_148]
0x1c0190eb8  test    bl, bl
0x1c0190eba  jz      loc_1C0190FF7
0x1c0190ec0  test    dil, dil
0x1c0190ec3  jz      short loc_1C0190ED9
0x1c0190ec5  mov     rax, [rsi+0A8h]
0x1c0190ecc  test    dword ptr [rax+10h], 200000h
0x1c0190ed3  jnz     loc_1C0190FF7
0x1c0190ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0190ee0  lea     rax, WPP_GLOBAL_Control
0x1c0190ee7  cmp     rcx, rax
0x1c0190eea  jz      short loc_1C0190F14
0x1c0190eec  test    dword ptr [rcx+2Ch], 100h
0x1c0190ef3  jz      short loc_1C0190F14
0x1c0190ef5  cmp     byte ptr [rcx+29h], 5
0x1c0190ef9  jb      short loc_1C0190F14
0x1c0190efb  mov     edx, 0C3h
0x1c0190f00  lea     r9d, [rdx+41h]
0x1c0190f04  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0190f0b  mov     rcx, [rcx+18h]
0x1c0190f0f  call    WPP_SF_D
0x1c0190f14  mov     al, cs:RefsStatusDebugEnabled
0x1c0190f1a  test    al, al
0x1c0190f1c  jz      short loc_1C0190F35
0x1c0190f1e  mov     r8d, 43CEh
0x1c0190f24  lea     rdx, aCreateC; "Create.c"
0x1c0190f2b  mov     ecx, 104h; Status
0x1c0190f30  call    RefsStatusDebug
0x1c0190f35  mov     edi, 104h
0x1c0190f3a  mov     [rsp+1A8h+var_154], edi
0x1c0190f3e  mov     ebx, [rsp+1A8h+BufferLength]
0x1c0190f42  mov     r8d, 43466552h; Tag
0x1c0190f48  mov     edx, ebx; NumberOfBytes
0x1c0190f4a  mov     ecx, 210h; PoolType
0x1c0190f4f  call    cs:__imp_ExAllocatePoolWithTag
0x1c0190f56  nop     dword ptr [rax+rax+00h]
0x1c0190f5b  mov     [r13+0A0h], rax
0x1c0190f62  mov     r8d, ebx; Size
0x1c0190f65  mov     rdx, [rsp+1A8h+ReparseBuffer]; Src
0x1c0190f6a  mov     rcx, rax; void *
0x1c0190f6d  call    memmove
0x1c0190f72  mov     rax, [r13+0B8h]
0x1c0190f79  test    byte ptr [rax+2], 4
0x1c0190f7d  jz      short loc_1C0190F8F
0x1c0190f7f  movzx   ecx, word ptr [rsi+54h]
0x1c0190f83  sub     cx, [rsi+10h]
0x1c0190f87  add     [rsp+1A8h+arg_20], cx
0x1c0190f8f  mov     rcx, [r13+0A0h]
0x1c0190f96  movzx   eax, [rsp+1A8h+arg_20]
0x1c0190f9e  mov     [rcx+6], ax
0x1c0190fa2  xor     r8d, r8d
0x1c0190fa5  cmp     [r12+28h], r8b
0x1c0190faa  jnz     short loc_1C0190FD1
0x1c0190fac  cmp     dword ptr [rcx], 0A000000Ch
0x1c0190fb2  jnz     short loc_1C0190FD1
0x1c0190fb4  mov     edx, [rcx+10h]
0x1c0190fb7  test    dword ptr [r15+0A0h], 10000000h
0x1c0190fc2  jz      short loc_1C0190FCA
0x1c0190fc4  bts     edx, 1Fh
0x1c0190fc8  jmp     short loc_1C0190FCE
0x1c0190fca  bts     edx, 1Eh
0x1c0190fce  mov     [rcx+10h], edx
0x1c0190fd1  mov     rdx, [rsi+0C0h]
0x1c0190fd8  test    rdx, rdx
0x1c0190fdb  jz      short loc_1C0190FEF
0x1c0190fdd  cmp     [rdx+14h], r8d
0x1c0190fe1  jge     short loc_1C0190FEF
0x1c0190fe3  movzx   eax, [rsp+1A8h+arg_20]
0x1c0190feb  mov     [rdx+2Ah], ax
0x1c0190fef  mov     eax, [rcx]
0x1c0190ff1  mov     [r13+38h], rax
0x1c0190ff5  jmp     short loc_1C0190FFD
0x1c0190ff7  mov     edi, edx
0x1c0190ff9  mov     [rsp+1A8h+var_154], edx
0x1c0190ffd  lea     r8, [rsp+1A8h+var_128]
0x1c0191005  lea     rdx, [rsp+1A8h+var_118]
0x1c019100d  call    RefsUnmapAttribute
0x1c0191012  lea     rdx, [rsp+1A8h+var_118]
0x1c019101a  mov     rcx, r12
0x1c019101d  call    RefsCleanupAttributeContext
0x1c0191022  mov     rcx, r12
0x1c0191025  call    RefsCheckpointCurrentTransaction
0x1c019102a  mov     eax, edi
0x1c019102c  mov     rcx, [rsp+1A8h+var_48]
0x1c0191034  xor     rcx, rsp; StackCookie
0x1c0191037  call    __security_check_cookie
0x1c019103c  add     rsp, 178h
0x1c0191043  pop     r15
0x1c0191045  pop     r13
0x1c0191047  pop     r12
0x1c0191049  pop     rdi
0x1c019104a  pop     rsi
0x1c019104b  pop     rbx
0x1c019104c  retn
0x1c019104e  push    rbp
0x1c0191050  sub     rsp, 50h
0x1c0191054  mov     rbp, rdx
0x1c0191057  lea     r8, [rbp+80h]
0x1c019105e  lea     rdx, [rbp+90h]
0x1c0191065  call    RefsUnmapAttribute
0x1c019106a  cmp     byte ptr [rbp+51h], 0
0x1c019106e  jz      short loc_1C0191081
0x1c0191070  lea     rdx, [rbp+90h]
  ... truncated ...
```
