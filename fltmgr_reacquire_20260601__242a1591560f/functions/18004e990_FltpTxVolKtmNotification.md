# FltpTxVolKtmNotification

- ea: `0x18004e990`
- end: `0x18004eab7`
- name: `FltpTxVolKtmNotification`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004ff30`

## callees

- `0x180009f20`
- `0x18000d600`
- `0x18000ff70`
- `0x180010400`
- `0x18004e990`
- `0x18004eac0`
- `0x1800544b4`
- `0x180060cd0`
- `0x180060e10`

## import_xrefs

- `ntoskrnl!TmCommitComplete` at `0x18004ea5f`
- `ntoskrnl!TmCommitComplete` at `0x18004ea5f`
- `ntoskrnl!TmRollbackComplete` at `0x18004ea3e`
- `ntoskrnl!TmRollbackComplete` at `0x18004ea3e`

## pseudocode

```c
__int64 __fastcall FltpTxVolKtmNotification(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  void *v5; // rbp
  unsigned int v7; // eax
  unsigned int v8; // edi

  v5 = *(void **)(a3 + 8);
  if ( *(_QWORD *)(a3 + 24) == -3 )
    *(_QWORD *)(a3 + 24) = a1;
  v7 = FltObjectReference(v5);
  v8 = (unsigned int)FltpDbgStatus(v7, "minkernel\\fs\\filtermgr\\filter\\txvolcontextsup.c", 1583, 3223060491LL) >> 31;
  if ( a4 == 4 )
  {
    if ( !(_BYTE)v8 )
      FltpInvalidateNameCacheForTxRename(a3);
    TmCommitComplete(*(PKENLISTMENT *)(a3 + 24), 0);
    *(_WORD *)(a3 + 42) = 40;
    *(_WORD *)(a3 + 40) = -3804;
    *(_QWORD *)(a3 + 64) = FltpTxVolWaitForCommitFinalize;
    *(_QWORD *)(a3 + 72) = a3;
    *(_QWORD *)(a3 + 48) = 0;
    FltpQueueThrottledWorkItem(a3 + 40, 1);
  }
  else
  {
    if ( a4 == 8 )
    {
      if ( (*(_DWORD *)(a3 + 148) & 1) == 0 )
        _InterlockedOr((volatile signed __int32 *)(a3 + 148), 1u);
      TmRollbackComplete(*(PKENLISTMENT *)(a3 + 24), 0);
    }
    else
    {
      if ( a4 != 0x40000000 )
        goto LABEL_17;
      if ( (*(_DWORD *)(a3 + 148) & 1) == 0 )
        _InterlockedOr((volatile signed __int32 *)(a3 + 148), 1u);
      if ( !(_BYTE)v8 )
        FltpPurgeAndReinstateNameCacheForTxRename(a3);
    }
    FltpDeleteTxVolContext((PVOID)a3);
    FltpReleaseTxVolContext((PVOID)a3);
  }
LABEL_17:
  if ( !(_BYTE)v8 )
    FltObjectDereference(v5);
  return 259;
}

```

## disassembly

```asm
0x18004e990  push    rbx
0x18004e992  push    rbp
0x18004e993  push    rsi
0x18004e994  push    rdi
0x18004e995  sub     rsp, 38h
0x18004e999  cmp     qword ptr [r8+18h], 0FFFFFFFFFFFFFFFDh
0x18004e99e  mov     esi, r9d
0x18004e9a1  mov     rbp, [r8+8]
0x18004e9a5  mov     rbx, r8
0x18004e9a8  jnz     short loc_18004E9AE
0x18004e9aa  mov     [r8+18h], rcx
0x18004e9ae  mov     rcx, rbp; FltObject
0x18004e9b1  call    FltObjectReference
0x18004e9b6  mov     r8d, 62Fh
0x18004e9bc  mov     [rsp+58h+var_38], 0
0x18004e9c5  mov     r9d, 0C01C000Bh
0x18004e9cb  lea     rdx, aMinkernelFsFil_26; "minkernel\\fs\\filtermgr\\filter\\txvol"...
0x18004e9d2  mov     ecx, eax
0x18004e9d4  call    FltpDbgStatus
0x18004e9d9  mov     edi, eax
0x18004e9db  shr     edi, 1Fh
0x18004e9de  cmp     esi, 4
0x18004e9e1  jz      short loc_18004EA4C
0x18004e9e3  cmp     esi, 8
0x18004e9e6  jz      short loc_18004EA26
0x18004e9e8  cmp     esi, 40000000h
0x18004e9ee  jnz     loc_18004EA9B
0x18004e9f4  mov     ecx, [rbx+94h]
0x18004e9fa  test    cl, 1
0x18004e9fd  jnz     short loc_18004EA07
0x18004e9ff  lock or dword ptr [rbx+94h], 1
0x18004ea07  test    dil, dil
0x18004ea0a  jnz     short loc_18004EA14
0x18004ea0c  mov     rcx, rbx
0x18004ea0f  call    FltpPurgeAndReinstateNameCacheForTxRename
0x18004ea14  mov     rcx, rbx; Entry
0x18004ea17  call    FltpDeleteTxVolContext
0x18004ea1c  mov     rcx, rbx; Entry
0x18004ea1f  call    FltpReleaseTxVolContext
0x18004ea24  jmp     short loc_18004EA9B
0x18004ea26  mov     eax, [rbx+94h]
0x18004ea2c  test    al, 1
0x18004ea2e  jnz     short loc_18004EA38
0x18004ea30  lock or dword ptr [rbx+94h], 1
0x18004ea38  mov     rcx, [rbx+18h]; Enlistment
0x18004ea3c  xor     edx, edx; TmVirtualClock
0x18004ea3e  call    cs:__imp_TmRollbackComplete
0x18004ea45  nop     dword ptr [rax+rax+00h]
0x18004ea4a  jmp     short loc_18004EA14
0x18004ea4c  test    dil, dil
0x18004ea4f  jnz     short loc_18004EA59
0x18004ea51  mov     rcx, rbx
0x18004ea54  call    FltpInvalidateNameCacheForTxRename
0x18004ea59  mov     rcx, [rbx+18h]; Enlistment
0x18004ea5d  xor     edx, edx; TmVirtualClock
0x18004ea5f  call    cs:__imp_TmCommitComplete
0x18004ea66  nop     dword ptr [rax+rax+00h]
0x18004ea6b  mov     word ptr [rbx+2Ah], 28h ; '('
0x18004ea71  lea     rcx, [rbx+28h]
0x18004ea75  mov     word ptr [rcx], 0F124h
0x18004ea7a  lea     rax, FltpTxVolWaitForCommitFinalize
0x18004ea81  mov     edx, 1
0x18004ea86  mov     [rbx+40h], rax
0x18004ea8a  mov     [rbx+48h], rbx
0x18004ea8e  mov     qword ptr [rbx+30h], 0
0x18004ea96  call    FltpQueueThrottledWorkItem
0x18004ea9b  test    dil, dil
0x18004ea9e  jnz     short loc_18004EAA8
0x18004eaa0  mov     rcx, rbp; FltObject
0x18004eaa3  call    FltObjectDereference
0x18004eaa8  mov     eax, 103h
0x18004eaad  add     rsp, 38h
0x18004eab1  pop     rdi
0x18004eab2  pop     rsi
0x18004eab3  pop     rbp
0x18004eab4  pop     rbx
0x18004eab5  retn
```
