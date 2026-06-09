# MupiFindOrCreateNetworkOpenEcp

- ea: `0x14001d5b4`
- end: `0x14001d6ed`
- name: `MupiFindOrCreateNetworkOpenEcp`
- size: `313`
- prototype: `__int64 __fastcall(PECP_LIST EcpList)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001bb60`

## callees

- `0x14001d5b4`

## import_xrefs

- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001d6a5`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14001d6a5`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001d605`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14001d605`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001d679`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14001d679`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001d6b9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14001d6b9`

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
0x14001d5b4  mov     [rsp-18h+arg_0], rbx
0x14001d5b9  mov     [rsp-18h+arg_18], rsi
0x14001d5be  mov     qword ptr [rsp-18h+EcpContextSize], r8
0x14001d5c3  push    rbp
0x14001d5c4  push    rdi
0x14001d5c5  push    r14
0x14001d5c7  mov     rbp, rsp
0x14001d5ca  sub     rsp, 30h
0x14001d5ce  mov     [rbp+EcpContext], 0
0x14001d5d6  mov     rdi, r9
0x14001d5d9  mov     [rbp+EcpContextSize], 0
0x14001d5e0  mov     rsi, rdx
0x14001d5e3  mov     qword ptr [rdx], 0
0x14001d5ea  mov     r14, rcx
0x14001d5ed  test    r9, r9
0x14001d5f0  jz      short loc_14001D5F6
0x14001d5f2  mov     byte ptr [r9], 0
0x14001d5f6  lea     r9, [rbp+EcpContextSize]; EcpContextSize
0x14001d5fa  lea     r8, [rbp+EcpContext]; EcpContext
0x14001d5fe  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001d605  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14001d60c  nop     dword ptr [rax+rax+00h]
0x14001d611  cmp     eax, 0C0000225h
0x14001d616  jnz     short loc_14001D620
0x14001d618  xor     ecx, ecx
0x14001d61a  mov     [rbp+EcpContext], rcx
0x14001d61e  jmp     short loc_14001D62C
0x14001d620  test    eax, eax
0x14001d622  js      loc_14001D6D9
0x14001d628  mov     rcx, [rbp+EcpContext]
0x14001d62c  mov     ebx, 1Ch
0x14001d631  test    rcx, rcx
0x14001d634  jz      short loc_14001D656
0x14001d636  cmp     [rbp+EcpContextSize], ebx
0x14001d639  jnb     short loc_14001D642
0x14001d63b  mov     eax, 0C000000Dh
0x14001d640  jmp     short loc_14001D649
0x14001d642  cmp     [rcx], bx
0x14001d645  jnz     short loc_14001D63B
0x14001d647  xor     eax, eax
0x14001d649  test    eax, eax
0x14001d64b  jns     loc_14001D6D6
0x14001d651  jmp     loc_14001D6D9
0x14001d656  lea     rax, [rbp+EcpContext]
0x14001d65a  mov     [rbp+EcpContextSize], ebx
0x14001d65d  mov     [rsp+30h+var_8], rax; EcpContext
0x14001d662  lea     rcx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14001d669  xor     r9d, r9d; CleanupCallback
0x14001d66c  mov     [rsp+30h+PoolTag], 6345754Dh; PoolTag
0x14001d674  xor     r8d, r8d; Flags
0x14001d677  mov     edx, ebx; SizeOfContext
0x14001d679  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14001d680  nop     dword ptr [rax+rax+00h]
0x14001d685  test    eax, eax
0x14001d687  js      short loc_14001D6D9
0x14001d689  mov     rax, [rbp+EcpContext]
0x14001d68d  xorps   xmm0, xmm0
0x14001d690  mov     rcx, r14; EcpList
0x14001d693  movups  xmmword ptr [rax], xmm0
0x14001d696  movups  xmmword ptr [rax+0Ch], xmm0
0x14001d69a  mov     rax, [rbp+EcpContext]
0x14001d69e  mov     [rax], bx
0x14001d6a1  mov     rdx, [rbp+EcpContext]; EcpContext
0x14001d6a5  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14001d6ac  nop     dword ptr [rax+rax+00h]
0x14001d6b1  mov     rcx, [rbp+EcpContext]; EcpContext
0x14001d6b5  test    eax, eax
0x14001d6b7  jns     short loc_14001D6CC
0x14001d6b9  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14001d6c0  nop     dword ptr [rax+rax+00h]
0x14001d6c5  mov     eax, 0C00000E5h
0x14001d6ca  jmp     short loc_14001D6D9
0x14001d6cc  xor     eax, eax
0x14001d6ce  test    rdi, rdi
0x14001d6d1  jz      short loc_14001D6D6
0x14001d6d3  mov     byte ptr [rdi], 1
0x14001d6d6  mov     [rsi], rcx
0x14001d6d9  mov     rbx, [rsp+30h+arg_0]
0x14001d6de  mov     rsi, [rsp+30h+arg_18]
0x14001d6e3  add     rsp, 30h
0x14001d6e7  pop     r14
0x14001d6e9  pop     rdi
0x14001d6ea  pop     rbp
0x14001d6eb  retn
```
