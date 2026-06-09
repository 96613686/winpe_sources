# MupiFindOrCreateNetworkOpenEcp

- ea: `0x14001d604`
- end: `0x14001d73d`
- name: `MupiFindOrCreateNetworkOpenEcp`
- size: `313`
- prototype: `NTSTATUS __fastcall(PECP_LIST EcpList, _QWORD *, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001bbb0`

## callees

- `0x14001d604`

## import_xrefs

- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001d6f5`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001d6f5`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001d655`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001d655`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001d6c9`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001d6c9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001d709`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001d709`

## pseudocode

```c
NTSTATUS __fastcall MupiFindOrCreateNetworkOpenEcp(PECP_LIST EcpList, _QWORD *a2, __int64 a3, _BYTE *a4)
{
  NTSTATUS result; // eax
  _WORD *v8; // rcx
  char *v9; // rax
  NTSTATUS Parameter; // eax
  PVOID EcpContext; // [rsp+58h] [rbp+28h] BYREF
  ULONG EcpContextSize; // [rsp+60h] [rbp+30h] BYREF
  int v13; // [rsp+64h] [rbp+34h]

  v13 = HIDWORD(a3);
  EcpContext = 0;
  EcpContextSize = 0;
  *a2 = 0;
  if ( a4 )
    *a4 = 0;
  result = FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_NETWORK_OPEN_CONTEXT, &EcpContext, &EcpContextSize);
  if ( result == -1073741275 )
  {
    v8 = 0;
    EcpContext = 0;
  }
  else
  {
    if ( result < 0 )
      return result;
    v8 = EcpContext;
  }
  if ( !v8 )
  {
    EcpContextSize = 28;
    result = FsRtlAllocateExtraCreateParameter(&GUID_ECP_NETWORK_OPEN_CONTEXT, 0x1Cu, 0, 0, 0x6345754Du, &EcpContext);
    if ( result < 0 )
      return result;
    v9 = (char *)EcpContext;
    *(_OWORD *)EcpContext = 0;
    *(_OWORD *)(v9 + 12) = 0;
    *(_WORD *)EcpContext = 28;
    Parameter = FsRtlInsertExtraCreateParameter(EcpList, EcpContext);
    v8 = EcpContext;
    if ( Parameter < 0 )
    {
      FsRtlFreeExtraCreateParameter(EcpContext);
      return -1073741595;
    }
    result = 0;
    if ( a4 )
      *a4 = 1;
    goto LABEL_19;
  }
  if ( EcpContextSize >= 0x1C && *v8 == 28 )
    result = 0;
  else
    result = -1073741811;
  if ( result >= 0 )
LABEL_19:
    *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x14001d604  mov     [rsp-18h+arg_0], rbx
0x14001d609  mov     [rsp-18h+arg_18], rsi
0x14001d60e  mov     qword ptr [rsp-18h+EcpContextSize], r8
0x14001d613  push    rbp
0x14001d614  push    rdi
0x14001d615  push    r14
0x14001d617  mov     rbp, rsp
0x14001d61a  sub     rsp, 30h
0x14001d61e  mov     [rbp+EcpContext], 0
0x14001d626  mov     rdi, r9
0x14001d629  mov     [rbp+EcpContextSize], 0
0x14001d630  mov     rsi, rdx
0x14001d633  mov     qword ptr [rdx], 0
0x14001d63a  mov     r14, rcx
0x14001d63d  test    r9, r9
0x14001d640  jz      short loc_14001D646
0x14001d642  mov     byte ptr [r9], 0
0x14001d646  lea     r9, [rbp+EcpContextSize]; EcpContextSize
0x14001d64a  lea     r8, [rbp+EcpContext]; EcpContext
0x14001d64e  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001d655  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001d65c  nop     dword ptr [rax+rax+00h]
0x14001d661  cmp     eax, 0C0000225h
0x14001d666  jnz     short loc_14001D670
0x14001d668  xor     ecx, ecx
0x14001d66a  mov     [rbp+EcpContext], rcx
0x14001d66e  jmp     short loc_14001D67C
0x14001d670  test    eax, eax
0x14001d672  js      loc_14001D729
0x14001d678  mov     rcx, [rbp+EcpContext]
0x14001d67c  mov     ebx, 1Ch
0x14001d681  test    rcx, rcx
0x14001d684  jz      short loc_14001D6A6
0x14001d686  cmp     [rbp+EcpContextSize], ebx
0x14001d689  jnb     short loc_14001D692
0x14001d68b  mov     eax, 0C000000Dh
0x14001d690  jmp     short loc_14001D699
0x14001d692  cmp     [rcx], bx
0x14001d695  jnz     short loc_14001D68B
0x14001d697  xor     eax, eax
0x14001d699  test    eax, eax
0x14001d69b  jns     loc_14001D726
0x14001d6a1  jmp     loc_14001D729
0x14001d6a6  lea     rax, [rbp+EcpContext]
0x14001d6aa  mov     [rbp+EcpContextSize], ebx
0x14001d6ad  mov     [rsp+30h+var_8], rax; EcpContext
0x14001d6b2  lea     rcx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001d6b9  xor     r9d, r9d; CleanupCallback
0x14001d6bc  mov     [rsp+30h+PoolTag], 6345754Dh; PoolTag
0x14001d6c4  xor     r8d, r8d; Flags
0x14001d6c7  mov     edx, ebx; SizeOfContext
0x14001d6c9  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14001d6d0  nop     dword ptr [rax+rax+00h]
0x14001d6d5  test    eax, eax
0x14001d6d7  js      short loc_14001D729
0x14001d6d9  mov     rax, [rbp+EcpContext]
0x14001d6dd  xorps   xmm0, xmm0
0x14001d6e0  mov     rcx, r14; EcpList
0x14001d6e3  movups  xmmword ptr [rax], xmm0
0x14001d6e6  movups  xmmword ptr [rax+0Ch], xmm0
0x14001d6ea  mov     rax, [rbp+EcpContext]
0x14001d6ee  mov     [rax], bx
0x14001d6f1  mov     rdx, [rbp+EcpContext]; EcpContext
0x14001d6f5  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14001d6fc  nop     dword ptr [rax+rax+00h]
0x14001d701  mov     rcx, [rbp+EcpContext]; EcpContext
0x14001d705  test    eax, eax
0x14001d707  jns     short loc_14001D71C
0x14001d709  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14001d710  nop     dword ptr [rax+rax+00h]
0x14001d715  mov     eax, 0C00000E5h
0x14001d71a  jmp     short loc_14001D729
0x14001d71c  xor     eax, eax
0x14001d71e  test    rdi, rdi
0x14001d721  jz      short loc_14001D726
0x14001d723  mov     byte ptr [rdi], 1
0x14001d726  mov     [rsi], rcx
0x14001d729  mov     rbx, [rsp+30h+arg_0]
0x14001d72e  mov     rsi, [rsp+30h+arg_18]
0x14001d733  add     rsp, 30h
0x14001d737  pop     r14
0x14001d739  pop     rdi
0x14001d73a  pop     rbp
0x14001d73b  retn
```
