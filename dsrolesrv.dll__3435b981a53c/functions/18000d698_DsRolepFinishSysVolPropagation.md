# DsRolepFinishSysVolPropagation

- ea: `0x18000d698`
- end: `0x18000d780`
- name: `DsRolepFinishSysVolPropagation`
- size: `232`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cdfc`
- `0x1800100c0`
- `0x180011240`
- `0x180012460`

## callees

- `0x18000b7f0`
- `0x18000d698`
- `0x180020dbc`

## import_xrefs

- `DFSRAPI!DfsrAbortPromotionW` at `0x18000d70b`
- `DFSRAPI!DfsrAbortPromotionW` at `0x18000d70b`
- `DFSRAPI!DfsrWaitForPromotionW` at `0x18000d6c8`
- `DFSRAPI!DfsrWaitForPromotionW` at `0x18000d6c8`
- `DFSRAPI!DfsrWaitForDemotionW` at `0x18000d6e8`
- `DFSRAPI!DfsrWaitForDemotionW` at `0x18000d6e8`
- `DFSRAPI!DfsrCommitDemotionW` at `0x18000d6fe`
- `DFSRAPI!DfsrCommitDemotionW` at `0x18000d6fe`
- `DFSRAPI!DfsrAbortDemotionW` at `0x18000d713`
- `DFSRAPI!DfsrAbortDemotionW` at `0x18000d713`
- `DFSRAPI!DfsrCommitPromotionW` at `0x18000d6e0`
- `DFSRAPI!DfsrCommitPromotionW` at `0x18000d6e0`

## string_xrefs

- `0x18000d74d`: `Commit`

## pseudocode

```c
__int64 __fastcall DsRolepFinishSysVolPropagation(char a1, char a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  const char *v9; // r9
  const char *v10; // r8
  int v12; // [rsp+40h] [rbp+8h] BYREF

  v12 = 1;
  if ( !a1 )
  {
    if ( a2 )
    {
      v5 = DfsrAbortPromotionW();
    }
    else
    {
      v4 = DfsrAbortDemotionW();
      if ( v4 )
        goto LABEL_12;
      v5 = DsRolepSetRegistryVal(v7, v6, v8, (const BYTE *)&v12);
    }
    goto LABEL_11;
  }
  if ( !a2 )
  {
    v4 = DfsrWaitForDemotionW(0xFFFFFFFFLL, DsRolepDfsrStringErrorUpdateCallback);
    if ( v4 )
      goto LABEL_12;
    v5 = DfsrCommitDemotionW(0xFFFFFFFFLL, DsRolepDfsrStringErrorUpdateCallback);
LABEL_11:
    v4 = v5;
    if ( !v5 )
      return v4;
    goto LABEL_12;
  }
  v4 = DfsrWaitForPromotionW(0xFFFFFFFFLL, DsRolepDfsrStringErrorUpdateCallback);
  if ( !v4 )
  {
    v5 = DfsrCommitPromotionW(0, 0xFFFFFFFFLL, DsRolepDfsrStringErrorUpdateCallback);
    goto LABEL_11;
  }
LABEL_12:
  v9 = "Promote";
  if ( !a2 )
    v9 = "Demote";
  v10 = "Commit";
  if ( !a1 )
    v10 = "Abort";
  DsRolepLogPrintRoutine(1, "DsRolepFinishSysVolPropagation (%S %S) failed with %lu\n", v10, v9, v4);
  return v4;
}

```

## disassembly

```asm
0x18000d698  mov     [rsp+arg_8], rbx
0x18000d69d  mov     [rsp+arg_10], rbp
0x18000d6a2  push    rsi
0x18000d6a3  sub     rsp, 30h
0x18000d6a7  mov     [rsp+38h+arg_0], 1
0x18000d6af  mov     sil, dl
0x18000d6b2  mov     bpl, cl
0x18000d6b5  test    cl, cl
0x18000d6b7  jz      short loc_18000D706
0x18000d6b9  or      ecx, 0FFFFFFFFh
0x18000d6bc  lea     rdx, DsRolepDfsrStringErrorUpdateCallback
0x18000d6c3  test    sil, sil
0x18000d6c6  jz      short loc_18000D6E8
0x18000d6c8  call    cs:__imp_DfsrWaitForPromotionW
0x18000d6ce  mov     ebx, eax
0x18000d6d0  test    eax, eax
0x18000d6d2  jnz     short loc_18000D72F
0x18000d6d4  lea     r8, DsRolepDfsrStringErrorUpdateCallback
0x18000d6db  or      edx, 0FFFFFFFFh
0x18000d6de  xor     ecx, ecx
0x18000d6e0  call    cs:__imp_DfsrCommitPromotionW
0x18000d6e6  jmp     short loc_18000D729
0x18000d6e8  call    cs:__imp_DfsrWaitForDemotionW
0x18000d6ee  mov     ebx, eax
0x18000d6f0  test    eax, eax
0x18000d6f2  jnz     short loc_18000D72F
0x18000d6f4  lea     rdx, DsRolepDfsrStringErrorUpdateCallback
0x18000d6fb  or      ecx, 0FFFFFFFFh
0x18000d6fe  call    cs:__imp_DfsrCommitDemotionW
0x18000d704  jmp     short loc_18000D729
0x18000d706  test    sil, sil
0x18000d709  jz      short loc_18000D713
0x18000d70b  call    cs:__imp_DfsrAbortPromotionW
0x18000d711  jmp     short loc_18000D729
0x18000d713  call    cs:__imp_DfsrAbortDemotionW
0x18000d719  mov     ebx, eax
0x18000d71b  test    eax, eax
0x18000d71d  jnz     short loc_18000D72F
0x18000d71f  lea     r9, [rsp+38h+arg_0]
0x18000d724  call    DsRolepSetRegistryVal
0x18000d729  mov     ebx, eax
0x18000d72b  test    eax, eax
0x18000d72d  jz      short loc_18000D76E
0x18000d72f  test    sil, sil
0x18000d732  mov     [rsp+38h+var_18], ebx
0x18000d736  lea     rax, aDemote; "Demote"
0x18000d73d  mov     ecx, 1
0x18000d742  lea     r9, aPromote; "Promote"
0x18000d749  cmovz   r9, rax
0x18000d74d  lea     r8, aCommit; "Commit"
0x18000d754  test    bpl, bpl
0x18000d757  lea     rax, aAbort; "Abort"
0x18000d75e  lea     rdx, aDsrolepfinishs; "DsRolepFinishSysVolPropagation (%S %S) "...
0x18000d765  cmovz   r8, rax
0x18000d769  call    DsRolepLogPrintRoutine
0x18000d76e  mov     rbp, [rsp+38h+arg_10]
0x18000d773  mov     eax, ebx
0x18000d775  mov     rbx, [rsp+38h+arg_8]
0x18000d77a  add     rsp, 30h
0x18000d77e  pop     rsi
0x18000d77f  retn
```
