# UxSslAllocateSendBuffer

- ea: `0x1c0134cc0`
- end: `0x1c0134efb`
- name: `UxSslAllocateSendBuffer`
- size: `571`
- prototype: `__int64 __fastcall(SIZE_T Length)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0135b90`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c0134cc0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1c0134cdd`
- `ntoskrnl!MmSizeOfMdl` at `0x1c0134cdd`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0134d6d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0134e67`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0134d6d`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0134e67`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0134d28`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0134df1`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0134d28`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0134df1`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0134ea1`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0134ea1`

## pseudocode

```c
PSLIST_ENTRY __fastcall UxSslAllocateSendBuffer(SIZE_T Length)
{
  unsigned int v1; // ebp
  unsigned int v2; // esi
  unsigned int v3; // eax
  __int64 v4; // rbx
  unsigned int v5; // r8d
  unsigned int v6; // eax
  __int64 v7; // rdi
  __int64 v8; // rcx
  char v9; // bl
  PSLIST_ENTRY v10; // rdx
  struct _SLIST_ENTRY *PoolWithTagPriority; // rax
  unsigned int v12; // r8d
  unsigned int v13; // eax
  _QWORD *v14; // rbx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  __int64 v17; // rdi
  PVOID v18; // rcx
  unsigned int v19; // r8d
  unsigned int v20; // eax
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 (__fastcall *v24)(__int64, __int64, __int64, __int64); // rax

  v1 = Length;
  v2 = (MmSizeOfMdl((PVOID)0xFFF, (unsigned int)Length) + 7) & 0xFFFFFFF8;
  if ( v1 >= 0xFFFFFFC8 )
    return 0;
  v3 = v2 + v1 + 56;
  if ( v3 < v2 )
    return 0;
  if ( v1 >= UxSslSmallSendBufferSize )
  {
    if ( v1 > UxSslSendBufferSize )
    {
      PoolWithTagPriority = (struct _SLIST_ENTRY *)ExAllocatePoolWithTagPriority(
                                                     (POOL_TYPE)512,
                                                     v3,
                                                     0x53537855u,
                                                     LowPoolPriority);
      v9 = 0;
      goto LABEL_30;
    }
    if ( UxCompactMode )
    {
      v14 = P;
      v15 = KeGetCurrentNodeNumber() + 1;
      v16 = *(_DWORD *)v14 - 1;
      if ( v15 < *(_DWORD *)v14 )
        v16 = v15;
      v17 = *(_QWORD *)(v14[4] + 8LL * v16);
      if ( *(_BYTE *)(v17 + 112) )
        goto LABEL_27;
      v18 = v14;
    }
    else
    {
      v18 = P;
      v19 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v20 = *(_DWORD *)P - 1;
      if ( v19 < *(_DWORD *)P )
        v20 = v19;
      v17 = *(_QWORD *)(*((_QWORD *)P + 4) + 8LL * v20);
      if ( *(_BYTE *)(v17 + 112) )
        goto LABEL_27;
    }
    PplpLazyInitializeLookasideList(v18, v17);
LABEL_27:
    v9 = 1;
    ++*(_DWORD *)(v17 + 20);
    v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v17);
    if ( v10 )
      goto LABEL_31;
    v21 = *(unsigned int *)(v17 + 40);
    v22 = *(unsigned int *)(v17 + 44);
    v23 = *(unsigned int *)(v17 + 36);
    v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v17 + 48);
    ++*(_DWORD *)(v17 + 24);
    PoolWithTagPriority = (struct _SLIST_ENTRY *)v24(v23, v22, v21, v17);
LABEL_30:
    v10 = PoolWithTagPriority;
    goto LABEL_31;
  }
  if ( UxCompactMode )
  {
    v4 = qword_1C0074600;
    v5 = KeGetCurrentNodeNumber() + 1;
    v6 = *(_DWORD *)v4 - 1;
    if ( v5 < *(_DWORD *)v4 )
      v6 = v5;
    v7 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 8LL * v6);
    if ( !*(_BYTE *)(v7 + 112) )
    {
      v8 = v4;
LABEL_9:
      PplpLazyInitializeLookasideList(v8, v7);
    }
  }
  else
  {
    v8 = qword_1C0074600;
    v12 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v13 = *(_DWORD *)qword_1C0074600 - 1;
    if ( v12 < *(_DWORD *)qword_1C0074600 )
      v13 = v12;
    v7 = *(_QWORD *)(*(_QWORD *)(qword_1C0074600 + 32) + 8LL * v13);
    if ( !*(_BYTE *)(v7 + 112) )
      goto LABEL_9;
  }
  v9 = 1;
  ++*(_DWORD *)(v7 + 20);
  v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v7);
  if ( !v10 )
  {
    ++*(_DWORD *)(v7 + 24);
    PoolWithTagPriority = (struct _SLIST_ENTRY *)(*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(v7 + 48))(
                                                   *(unsigned int *)(v7 + 36),
                                                   *(unsigned int *)(v7 + 44),
                                                   *(unsigned int *)(v7 + 40),
                                                   v7);
    goto LABEL_30;
  }
LABEL_31:
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    v10[2] = 0;
    v10[3].Next = (PSLIST_ENTRY)((char *)v10 + v2 + 56);
    LODWORD(v10->Next) = 1397979221;
    BYTE4(v10->Next) = v9;
    *((_DWORD *)&v10[2].Next + 3) = v1;
  }
  return v10;
}

```

## disassembly

```asm
0x1c0134cc0  mov     [rsp+arg_0], rbx
0x1c0134cc5  mov     [rsp+arg_8], rbp
0x1c0134cca  mov     [rsp+arg_10], rsi
0x1c0134ccf  push    rdi
0x1c0134cd0  sub     rsp, 30h
0x1c0134cd4  mov     ebp, ecx
0x1c0134cd6  mov     edx, ecx; Length
0x1c0134cd8  mov     ecx, 0FFFh; Base
0x1c0134cdd  call    cs:__imp_MmSizeOfMdl
0x1c0134ce4  nop     dword ptr [rax+rax+00h]
0x1c0134ce9  lea     edx, [rbp+38h]
0x1c0134cec  lea     esi, [rax+7]
0x1c0134cef  and     esi, 0FFFFFFF8h
0x1c0134cf2  cmp     edx, 38h ; '8'
0x1c0134cf5  jb      loc_1C0134EE3
0x1c0134cfb  lea     eax, [rbp+38h]
0x1c0134cfe  add     eax, esi
0x1c0134d00  cmp     eax, esi
0x1c0134d02  jb      loc_1C0134EE3
0x1c0134d08  cmp     ebp, cs:UxSslSmallSendBufferSize
0x1c0134d0e  jnb     loc_1C0134DD5
0x1c0134d14  cmp     cs:UxCompactMode, 0
0x1c0134d1b  jz      loc_1C0134DA4
0x1c0134d21  mov     rbx, cs:qword_1C0074600
0x1c0134d28  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0134d2f  nop     dword ptr [rax+rax+00h]
0x1c0134d34  mov     edx, [rbx]
0x1c0134d36  movzx   r8d, ax
0x1c0134d3a  inc     r8d
0x1c0134d3d  cmp     r8d, edx
0x1c0134d40  lea     eax, [rdx-1]
0x1c0134d43  cmovb   eax, r8d
0x1c0134d47  mov     edx, eax
0x1c0134d49  mov     rax, [rbx+20h]
0x1c0134d4d  mov     rdi, [rax+rdx*8]
0x1c0134d51  cmp     byte ptr [rdi+70h], 0
0x1c0134d55  jnz     short loc_1C0134D62
0x1c0134d57  mov     rcx, rbx
0x1c0134d5a  mov     rdx, rdi
0x1c0134d5d  call    PplpLazyInitializeLookasideList
0x1c0134d62  mov     ebx, 1
0x1c0134d67  mov     rcx, rdi; ListHead
0x1c0134d6a  add     [rdi+14h], ebx
0x1c0134d6d  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0134d74  nop     dword ptr [rax+rax+00h]
0x1c0134d79  mov     rdx, rax
0x1c0134d7c  test    rax, rax
0x1c0134d7f  jnz     loc_1C0134EB2
0x1c0134d85  add     [rdi+18h], ebx
0x1c0134d88  mov     edx, [rdi+2Ch]
0x1c0134d8b  mov     rax, [rdi+30h]
0x1c0134d8f  mov     r8d, [rdi+28h]
0x1c0134d93  mov     ecx, [rdi+24h]
0x1c0134d96  mov     r9, rdi
0x1c0134d99  call    cs:__guard_dispatch_icall_fptr
0x1c0134d9f  jmp     loc_1C0134EAF
0x1c0134da4  mov     eax, gs:1A4h
0x1c0134dac  mov     rcx, cs:qword_1C0074600
0x1c0134db3  lea     r8d, [rax+1]
0x1c0134db7  mov     edx, [rcx]
0x1c0134db9  cmp     r8d, edx
0x1c0134dbc  lea     eax, [rdx-1]
0x1c0134dbf  cmovb   eax, r8d
0x1c0134dc3  mov     edx, eax
0x1c0134dc5  mov     rax, [rcx+20h]
0x1c0134dc9  mov     rdi, [rax+rdx*8]
0x1c0134dcd  cmp     byte ptr [rdi+70h], 0
0x1c0134dd1  jnz     short loc_1C0134D62
0x1c0134dd3  jmp     short loc_1C0134D5A
0x1c0134dd5  cmp     ebp, cs:UxSslSendBufferSize
0x1c0134ddb  ja      loc_1C0134E91
0x1c0134de1  cmp     cs:UxCompactMode, 0
0x1c0134de8  jz      short loc_1C0134E25
0x1c0134dea  mov     rbx, cs:P
0x1c0134df1  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0134df8  nop     dword ptr [rax+rax+00h]
0x1c0134dfd  mov     edx, [rbx]
0x1c0134dff  movzx   r8d, ax
0x1c0134e03  inc     r8d
0x1c0134e06  cmp     r8d, edx
0x1c0134e09  lea     eax, [rdx-1]
0x1c0134e0c  cmovb   eax, r8d
0x1c0134e10  mov     edx, eax
0x1c0134e12  mov     rax, [rbx+20h]
0x1c0134e16  mov     rdi, [rax+rdx*8]
0x1c0134e1a  cmp     byte ptr [rdi+70h], 0
0x1c0134e1e  jnz     short loc_1C0134E5C
0x1c0134e20  mov     rcx, rbx
0x1c0134e23  jmp     short loc_1C0134E54
0x1c0134e25  mov     eax, gs:1A4h
0x1c0134e2d  mov     rcx, cs:P
0x1c0134e34  lea     r8d, [rax+1]
0x1c0134e38  mov     edx, [rcx]
0x1c0134e3a  cmp     r8d, edx
0x1c0134e3d  lea     eax, [rdx-1]
0x1c0134e40  cmovb   eax, r8d
0x1c0134e44  mov     edx, eax
0x1c0134e46  mov     rax, [rcx+20h]
0x1c0134e4a  mov     rdi, [rax+rdx*8]
0x1c0134e4e  cmp     byte ptr [rdi+70h], 0
0x1c0134e52  jnz     short loc_1C0134E5C
0x1c0134e54  mov     rdx, rdi
0x1c0134e57  call    PplpLazyInitializeLookasideList
0x1c0134e5c  mov     ebx, 1
0x1c0134e61  mov     rcx, rdi; ListHead
0x1c0134e64  add     [rdi+14h], ebx
0x1c0134e67  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0134e6e  nop     dword ptr [rax+rax+00h]
0x1c0134e73  mov     rdx, rax
0x1c0134e76  test    rax, rax
0x1c0134e79  jnz     short loc_1C0134EB2
0x1c0134e7b  mov     r8d, [rdi+28h]
0x1c0134e7f  mov     edx, [rdi+2Ch]
0x1c0134e82  mov     ecx, [rdi+24h]
0x1c0134e85  mov     rax, [rdi+30h]
0x1c0134e89  add     [rdi+18h], ebx
0x1c0134e8c  jmp     loc_1C0134D96
0x1c0134e91  mov     edx, eax; NumberOfBytes
0x1c0134e93  xor     r9d, r9d; Priority
0x1c0134e96  mov     ecx, 200h; PoolType
0x1c0134e9b  mov     r8d, 53537855h; Tag
0x1c0134ea1  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0134ea8  nop     dword ptr [rax+rax+00h]
0x1c0134ead  xor     bl, bl
0x1c0134eaf  mov     rdx, rax
0x1c0134eb2  test    rdx, rdx
0x1c0134eb5  jz      short loc_1C0134EDE
0x1c0134eb7  xorps   xmm0, xmm0
0x1c0134eba  mov     ecx, esi
0x1c0134ebc  movups  xmmword ptr [rdx], xmm0
0x1c0134ebf  add     rcx, 38h ; '8'
0x1c0134ec3  movups  xmmword ptr [rdx+10h], xmm0
0x1c0134ec7  add     rcx, rdx
0x1c0134eca  movups  xmmword ptr [rdx+20h], xmm0
0x1c0134ece  mov     [rdx+30h], rcx
0x1c0134ed2  mov     dword ptr [rdx], 53537855h
0x1c0134ed8  mov     [rdx+4], bl
0x1c0134edb  mov     [rdx+2Ch], ebp
0x1c0134ede  mov     rax, rdx
0x1c0134ee1  jmp     short loc_1C0134EE5
0x1c0134ee3  xor     eax, eax
0x1c0134ee5  mov     rbx, [rsp+38h+arg_0]
0x1c0134eea  mov     rbp, [rsp+38h+arg_8]
0x1c0134eef  mov     rsi, [rsp+38h+arg_10]
0x1c0134ef4  add     rsp, 30h
0x1c0134ef8  pop     rdi
0x1c0134ef9  retn
```
