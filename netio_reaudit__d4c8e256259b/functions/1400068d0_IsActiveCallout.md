# IsActiveCallout

- ea: `0x1400068d0`
- end: `0x140006c2e`
- name: `IsActiveCallout`
- size: `862`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140005a10`
- `0x140006240`
- `0x140035d10`
- `0x140039800`
- `0x140041180`

## callees

- `0x1400068d0`
- `0x140006c80`
- `0x140006d20`
- `0x1400070d0`
- `0x140007ad0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000695d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006a55`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006af2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000695d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006a55`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140006af2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006a17`
- `ntoskrnl!KeGetCurrentIrql` at `0x140006a17`
- `NDIS!NdisAcquireRWLockRead` at `0x140006a38`
- `NDIS!NdisAcquireRWLockRead` at `0x140006a38`
- `NDIS!NdisReleaseRWLock` at `0x140006995`
- `NDIS!NdisReleaseRWLock` at `0x140006b2b`
- `NDIS!NdisReleaseRWLock` at `0x140006995`
- `NDIS!NdisReleaseRWLock` at `0x140006b2b`

## pseudocode

```c
_BOOL8 __fastcall IsActiveCallout(__int64 a1, __int64 a2, int a3)
{
  __int64 v4; // r12
  int v5; // esi
  __int64 v6; // rbx
  void *v8; // rbx
  PNPAGED_LOOKASIDE_LIST v9; // rdi
  _DWORD *v10; // rdx
  struct _LIST_ENTRY *v11; // rbp
  __int64 v12; // rax
  PNPAGED_LOOKASIDE_LIST v13; // rsi
  unsigned __int16 **v14; // r15
  KIRQL CurrentIrql; // di
  __int64 v16; // rdx
  unsigned __int16 *v17; // r8
  unsigned int i; // edx
  __int64 v19; // r10
  PNPAGED_LOOKASIDE_LIST v20; // rdi
  _DWORD *v21; // r8
  int v22; // ecx
  BOOL v23; // edi
  int v25; // [rsp+20h] [rbp-58h]
  unsigned __int16 **v26; // [rsp+28h] [rbp-50h] BYREF
  __int16 v27; // [rsp+80h] [rbp+8h]
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+10h] BYREF
  int v29; // [rsp+90h] [rbp+18h]
  struct _LOCK_STATE_EX v30; // [rsp+98h] [rbp+20h] BYREF

  v29 = a3;
  v4 = 0;
  v5 = a3;
  v6 = *(unsigned int *)(*(_QWORD *)(a1 + 24) + 44LL);
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  WfpAcquireFastReadLock((PNDIS_RW_LOCK_EX *)&gWfpGlobal[1], &LockState);
  if ( (unsigned int)v6 >= gWfpGlobal[3].L.FreeMisses
    || (v8 = (void *)(*(_QWORD *)&gWfpGlobal[3].L.Tag + 144 * v6), !*((_DWORD *)v8 + 1)) )
  {
    v8 = gFeCallout;
  }
  _InterlockedIncrement((volatile signed __int32 *)v8 + 16);
  v9 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v10 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v10 == 4 )
      *v10 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v9[1].L.ListHead.Alignment, &LockState);
  if ( a2 && (*(_DWORD *)a2 & 2) != 0 )
  {
    v11 = *(struct _LIST_ENTRY **)(a2 + 32);
    if ( v11 )
    {
      v12 = *(_QWORD *)(a1 + 24);
      *(_WORD *)&v30.OldIrql = 0;
      v30.Flags = 0;
      v25 = *(_DWORD *)(v12 + 44);
      LOWORD(v12) = *(_WORD *)(a1 + 48);
      v26 = 0;
      v27 = v12;
      if ( !KfdAleGetTableFromHandle(v11, &v26) )
      {
        v13 = gWfpGlobal;
        v14 = v26;
        CurrentIrql = KeGetCurrentIrql();
        NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v13[3].L.AllocateEx, &v30, 0);
        if ( CurrentIrql != 2 && gWfpPerProContext )
        {
          v16 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          *(_QWORD *)(v16 + 8) = MEMORY[0xFFFFF78000000008];
          *(_DWORD *)v16 = 4;
        }
        v17 = *v14;
        if ( *v14 && v17 != (unsigned __int16 *)1 && (*((_DWORD *)v17 + 1) & 1) == 0 )
        {
          for ( i = 0; i < *v17; ++i )
          {
            v19 = *((_QWORD *)v17 + 1) + 32LL * i;
            if ( *(_DWORD *)(v19 + 12) == v25 && *(_WORD *)(v19 + 8) == v27 )
            {
              if ( (*(_DWORD *)v19 & 3) != 1 && *(_QWORD *)(v19 + 16) )
              {
                _InterlockedIncrement((volatile signed __int32 *)(v19 + 4));
                v4 = *(_QWORD *)(v19 + 16);
              }
              break;
            }
          }
        }
        v20 = gWfpGlobal;
        if ( gWfpPerProContext )
        {
          v21 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
          if ( *v21 == 4 )
            *v21 = 0;
        }
        NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v20[3].L.AllocateEx, &v30);
        if ( v14 != (unsigned __int16 **)112 )
          WfpAleDereferenceEndpoint(v14 - 14);
        v5 = v29;
      }
    }
  }
  else
  {
    v11 = 0;
  }
  v22 = *((_DWORD *)v8 + 14);
  v23 = ((v22 & 1) == 0 || v4)
     && ((v22 & 8) != 0 || !a2 || (*(_DWORD *)(a2 + 4) & 0x10) == 0)
     && ((v22 & 0x10) != 0 || !a2 || (*(_DWORD *)(a2 + 4) & 0x20) == 0);
  if ( v5 && (v22 & 2) != 0 )
    v23 = 0;
  if ( v11 && v4 )
    WfpFindAndDeRefFlowContext(v11, *(_WORD *)(a1 + 48), *(_DWORD *)(*(_QWORD *)(a1 + 24) + 44LL), 0);
  _InterlockedDecrement((volatile signed __int32 *)v8 + 16);
  return v23;
}

```

## disassembly

```asm
0x1400068d0  mov     r11, rsp
0x1400068d3  mov     [r11+18h], r8d
0x1400068d7  push    rbx
0x1400068d8  push    rbp
0x1400068d9  push    rdi
0x1400068da  push    r12
0x1400068dc  push    r13
0x1400068de  sub     rsp, 50h
0x1400068e2  mov     rax, [rcx+18h]
0x1400068e6  mov     r13, rcx
0x1400068e9  mov     rcx, cs:gWfpGlobal
0x1400068f0  xor     r12d, r12d
0x1400068f3  mov     [r11-30h], rsi
0x1400068f7  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400068fb  mov     [r11-38h], r14
0x1400068ff  mov     esi, r8d
0x140006902  mov     ebx, [rax+2Ch]
0x140006905  mov     r14, rdx
0x140006908  xor     eax, eax
0x14000690a  lea     rdx, [r11+10h]
0x14000690e  mov     [r11+10h], ax
0x140006913  mov     [r11+12h], al
0x140006917  call    WfpAcquireFastReadLock
0x14000691c  mov     rdx, cs:gWfpGlobal
0x140006923  cmp     ebx, [rdx+1A0h]
0x140006929  jnb     short loc_140006940
0x14000692b  lea     rbx, [rbx+rbx*8]
0x14000692f  shl     rbx, 4
0x140006933  add     rbx, [rdx+1A8h]
0x14000693a  cmp     [rbx+4], r12d
0x14000693e  jnz     short loc_140006947
0x140006940  mov     rbx, cs:gFeCallout
0x140006947  lock inc dword ptr [rbx+40h]
0x14000694b  cmp     cs:gWfpPerProContext, r12
0x140006952  mov     rdi, cs:gWfpGlobal
0x140006959  jz      short loc_140006986
0x14000695b  xor     ecx, ecx; ProcNumber
0x14000695d  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140006964  nop     dword ptr [rax+rax+00h]
0x140006969  imul    eax, cs:gWfpPerProContextSize
0x140006970  mov     ecx, eax
0x140006972  mov     rax, cs:gWfpPerProContext
0x140006979  mov     rdx, [rcx+rax]
0x14000697d  cmp     dword ptr [rdx], 4
0x140006980  jz      loc_140006C05
0x140006986  mov     rcx, [rdi+80h]; Lock
0x14000698d  lea     rdx, [rsp+78h+LockState]; LockState
0x140006995  call    cs:__imp_NdisReleaseRWLock
0x14000699c  nop     dword ptr [rax+rax+00h]
0x1400069a1  test    r14, r14
0x1400069a4  jz      loc_140006C19
0x1400069aa  mov     eax, [r14]
0x1400069ad  test    al, 2
0x1400069af  jz      loc_140006C19
0x1400069b5  mov     rbp, [r14+20h]
0x1400069b9  test    rbp, rbp
0x1400069bc  jz      loc_140006B54
0x1400069c2  mov     rax, [r13+18h]
0x1400069c6  lea     rdx, [rsp+78h+var_50]
0x1400069cb  xor     ecx, ecx
0x1400069cd  mov     word ptr [rsp+78h+arg_18.OldIrql], cx
0x1400069d5  mov     [rsp+78h+arg_18.Flags], cl
0x1400069dc  mov     eax, [rax+2Ch]
0x1400069df  mov     [rsp+78h+var_58], eax
0x1400069e3  movzx   eax, word ptr [r13+30h]
0x1400069e8  mov     [rsp+78h+var_50], rcx
0x1400069ed  mov     rcx, rbp
0x1400069f0  mov     [rsp+78h+arg_0], ax
0x1400069f8  call    KfdAleGetTableFromHandle
0x1400069fd  test    rax, rax
0x140006a00  jnz     loc_140006B54
0x140006a06  mov     rsi, cs:gWfpGlobal
0x140006a0d  mov     [rsp+78h+var_40], r15
0x140006a12  mov     r15, [rsp+78h+var_50]
0x140006a17  call    cs:__imp_KeGetCurrentIrql
0x140006a1e  nop     dword ptr [rax+rax+00h]
0x140006a23  mov     rcx, [rsi+1B0h]; Lock
0x140006a2a  lea     rdx, [rsp+78h+arg_18]; LockState
0x140006a32  xor     r8d, r8d; Flags
0x140006a35  movzx   edi, al
0x140006a38  call    cs:__imp_NdisAcquireRWLockRead
0x140006a3f  nop     dword ptr [rax+rax+00h]
0x140006a44  cmp     dil, 2
0x140006a48  jz      short loc_140006A89
0x140006a4a  cmp     cs:gWfpPerProContext, r12
0x140006a51  jz      short loc_140006A89
0x140006a53  xor     ecx, ecx; ProcNumber
0x140006a55  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140006a5c  nop     dword ptr [rax+rax+00h]
0x140006a61  imul    eax, cs:gWfpPerProContextSize
0x140006a68  mov     ecx, eax
0x140006a6a  mov     rax, cs:gWfpPerProContext
0x140006a71  mov     rdx, [rcx+rax]
0x140006a75  mov     rax, ds:0FFFFF78000000008h
0x140006a7f  mov     [rdx+8], rax
0x140006a83  mov     dword ptr [rdx], 4
0x140006a89  mov     r8, [r15]
0x140006a8c  test    r8, r8
0x140006a8f  jz      short loc_140006ADF
0x140006a91  cmp     r8, 1
0x140006a95  jz      short loc_140006ADF
0x140006a97  mov     eax, [r8+4]
0x140006a9b  test    al, 1
0x140006a9d  jnz     short loc_140006ADF
0x140006a9f  movzx   r9d, word ptr [r8]
0x140006aa3  xor     edx, edx
0x140006aa5  mov     r11d, [rsp+78h+var_58]
0x140006aaa  movzx   edi, [rsp+78h+arg_0]
0x140006ab2  cmp     edx, r9d
0x140006ab5  jnb     short loc_140006ADF
0x140006ab7  mov     r10d, edx
0x140006aba  shl     r10, 5
0x140006abe  add     r10, [r8+8]
0x140006ac2  cmp     [r10+0Ch], r11d
0x140006ac6  jz      loc_140006BAA
0x140006acc  inc     edx
0x140006ace  jmp     short loc_140006AB2
0x140006ad0  cmp     [r10+10h], r12
0x140006ad4  jz      short loc_140006ADF
0x140006ad6  lock inc dword ptr [r10+4]
0x140006adb  mov     r12, [r10+10h]
0x140006adf  cmp     cs:gWfpPerProContext, 0
0x140006ae7  mov     rdi, cs:gWfpGlobal
0x140006aee  jz      short loc_140006B1C
0x140006af0  xor     ecx, ecx; ProcNumber
0x140006af2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140006af9  nop     dword ptr [rax+rax+00h]
0x140006afe  imul    eax, cs:gWfpPerProContextSize
0x140006b05  mov     edx, eax
0x140006b07  mov     rax, cs:gWfpPerProContext
0x140006b0e  mov     r8, [rdx+rax]
0x140006b12  cmp     dword ptr [r8], 4
0x140006b16  jz      loc_140006C0D
0x140006b1c  mov     rcx, [rdi+1B0h]; Lock
0x140006b23  lea     rdx, [rsp+78h+arg_18]; LockState
0x140006b2b  call    cs:__imp_NdisReleaseRWLock
0x140006b32  nop     dword ptr [rax+rax+00h]
0x140006b37  lea     rax, [r15-70h]
0x140006b3b  mov     r15, [rsp+78h+var_40]
0x140006b40  test    rax, rax
0x140006b43  jz      short loc_140006B4D
0x140006b45  mov     rcx, rax
0x140006b48  call    WfpAleDereferenceEndpoint
0x140006b4d  mov     esi, [rsp+78h+arg_10]
0x140006b54  mov     ecx, [rbx+38h]
0x140006b57  test    cl, 1
0x140006b5a  jz      short loc_140006BC7
0x140006b5c  test    r12, r12
0x140006b5f  jnz     short loc_140006BC7
0x140006b61  xor     edi, edi
0x140006b63  mov     r14, [rsp+78h+var_38]
0x140006b68  test    esi, esi
0x140006b6a  mov     rsi, [rsp+78h+var_30]
0x140006b6f  jnz     loc_140006BF5
0x140006b75  test    rbp, rbp
0x140006b78  jz      short loc_140006B97
0x140006b7a  test    r12, r12
0x140006b7d  jz      short loc_140006B97
0x140006b7f  mov     r8, [r13+18h]
0x140006b83  xor     r9d, r9d
0x140006b86  movzx   edx, word ptr [r13+30h]
0x140006b8b  mov     rcx, rbp; int
0x140006b8e  mov     r8d, [r8+2Ch]
0x140006b92  call    WfpFindAndDeRefFlowContext
0x140006b97  lock dec dword ptr [rbx+40h]
0x140006b9b  mov     eax, edi
0x140006b9d  add     rsp, 50h
0x140006ba1  pop     r13
0x140006ba3  pop     r12
0x140006ba5  pop     rdi
0x140006ba6  pop     rbp
0x140006ba7  pop     rbx
0x140006ba8  retn
0x140006baa  cmp     [r10+8], di
0x140006baf  jnz     loc_140006ACC
0x140006bb5  mov     eax, [r10]
0x140006bb8  and     al, 3
0x140006bba  cmp     al, 1
0x140006bbc  jz      loc_140006ADF
0x140006bc2  jmp     loc_140006AD0
0x140006bc7  test    cl, 8
0x140006bca  jnz     short loc_140006BD9
0x140006bcc  test    r14, r14
0x140006bcf  jz      short loc_140006BD9
0x140006bd1  mov     eax, [r14+4]
0x140006bd5  test    al, 10h
0x140006bd7  jnz     short loc_140006C20
0x140006bd9  test    cl, 10h
0x140006bdc  jnz     short loc_140006BEB
0x140006bde  test    r14, r14
0x140006be1  jz      short loc_140006BEB
0x140006be3  mov     eax, [r14+4]
0x140006be7  test    al, 20h
0x140006be9  jnz     short loc_140006C27
0x140006beb  mov     edi, 1
0x140006bf0  jmp     loc_140006B63
0x140006bf5  test    cl, 2
0x140006bf8  mov     eax, 0
0x140006bfd  cmovnz  edi, eax
0x140006c00  jmp     loc_140006B75
0x140006c05  mov     [rdx], r12d
0x140006c08  jmp     loc_140006986
0x140006c0d  mov     dword ptr [r8], 0
0x140006c14  jmp     loc_140006B1C
0x140006c19  xor     ebp, ebp
0x140006c1b  jmp     loc_140006B54
0x140006c20  xor     edi, edi
0x140006c22  jmp     loc_140006B63
0x140006c27  xor     edi, edi
0x140006c29  jmp     loc_140006B63
```
