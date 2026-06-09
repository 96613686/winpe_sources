# Smb2Lock_Finalize

- ea: `0x14001c080`
- end: `0x14001c17d`
- name: `Smb2Lock_Finalize`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14001c080`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c119`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001c119`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c0ed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001c0ed`
- `rdbss!RxLowIoCompletion` at `0x14001c14c`
- `rdbss!RxLowIoCompletion` at `0x14001c14c`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001c165`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14001c165`

## pseudocode

```c
__int64 __fastcall Smb2Lock_Finalize(__int64 a1)
{
  int v2; // r14d
  __int64 v3; // rbx
  struct _RX_CONTEXT *v4; // r15
  unsigned int v5; // r12d
  __int64 v6; // rdi

  v2 = *(_DWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 160) - 8LL;
  v4 = *(struct _RX_CONTEXT **)(a1 + 48);
  if ( *(_QWORD *)(a1 + 160) == a1 + 160 )
    v3 = 0;
  if ( v2 >= 0 && v3 )
    v2 = *(_DWORD *)(v3 + 48);
  v5 = *(unsigned __int16 *)(a1 + 1030);
  if ( (_WORD)v5 )
  {
    v6 = *(_QWORD *)&v4->pRelevantSrvOpen->Flags;
    ExAcquirePushLockExclusiveEx(v6 + 16, 0);
    *(_QWORD *)(v6 + 176) |= 1LL << ((unsigned __int8)(v5 >> 4) - 1);
    ExReleasePushLockExclusiveEx(v6 + 16, 0);
  }
  if ( !*(_BYTE *)(a1 + 1028) )
  {
    v4->StoredStatus = v2;
    RxLowIoCompletion(v4);
  }
  if ( v3 )
    SmbCseFinalizeBufferContext(v3);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14001c080  push    rbx
0x14001c082  push    r14
0x14001c084  sub     rsp, 28h
0x14001c088  lea     rdx, [rcx+0A0h]
0x14001c08f  mov     [rsp+38h+arg_0], rbp
0x14001c094  mov     rax, [rdx]
0x14001c097  mov     rbp, rcx
0x14001c09a  xor     ecx, ecx
0x14001c09c  mov     [rsp+38h+arg_18], r12
0x14001c0a1  cmp     rax, rdx
0x14001c0a4  mov     [rsp+38h+var_18], r15
0x14001c0a9  mov     r14d, [rbp+10h]
0x14001c0ad  lea     rbx, [rax-8]
0x14001c0b1  mov     r15, [rbp+30h]
0x14001c0b5  cmovz   rbx, rcx
0x14001c0b9  test    r14d, r14d
0x14001c0bc  js      short loc_14001C0C7
0x14001c0be  test    rbx, rbx
0x14001c0c1  jz      short loc_14001C0C7
0x14001c0c3  mov     r14d, [rbx+30h]
0x14001c0c7  movzx   r12d, word ptr [rbp+406h]
0x14001c0cf  test    r12w, r12w
0x14001c0d3  jz      short loc_14001C12F
0x14001c0d5  mov     rax, [r15+48h]
0x14001c0d9  xor     edx, edx
0x14001c0db  mov     [rsp+38h+arg_8], rsi
0x14001c0e0  mov     [rsp+38h+arg_10], rdi
0x14001c0e5  mov     rdi, [rax+30h]
0x14001c0e9  lea     rcx, [rdi+10h]
0x14001c0ed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001c0f4  nop     dword ptr [rax+rax+00h]
0x14001c0f9  mov     rdx, [rdi+0B0h]
0x14001c100  lea     rcx, [rdi+10h]
0x14001c104  mov     eax, r12d
0x14001c107  shr     eax, 4
0x14001c10a  dec     eax
0x14001c10c  bts     rdx, rax
0x14001c110  mov     [rdi+0B0h], rdx
0x14001c117  xor     edx, edx
0x14001c119  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001c120  nop     dword ptr [rax+rax+00h]
0x14001c125  mov     rdi, [rsp+38h+arg_10]
0x14001c12a  mov     rsi, [rsp+38h+arg_8]
0x14001c12f  cmp     byte ptr [rbp+404h], 0
0x14001c136  mov     rbp, [rsp+38h+arg_0]
0x14001c13b  mov     r12, [rsp+38h+arg_18]
0x14001c140  jnz     short loc_14001C158
0x14001c142  mov     rcx, r15; RxContext
0x14001c145  mov     [r15+0B0h], r14d
0x14001c14c  call    cs:__imp_RxLowIoCompletion
0x14001c153  nop     dword ptr [rax+rax+00h]
0x14001c158  mov     r15, [rsp+38h+var_18]
0x14001c15d  test    rbx, rbx
0x14001c160  jz      short loc_14001C171
0x14001c162  mov     rcx, rbx
0x14001c165  call    cs:__imp_SmbCseFinalizeBufferContext
0x14001c16c  nop     dword ptr [rax+rax+00h]
0x14001c171  mov     eax, r14d
0x14001c174  add     rsp, 28h
0x14001c178  pop     r14
0x14001c17a  pop     rbx
0x14001c17b  retn
```
