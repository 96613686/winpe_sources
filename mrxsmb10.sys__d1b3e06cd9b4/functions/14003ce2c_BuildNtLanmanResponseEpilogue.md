# BuildNtLanmanResponseEpilogue

- ea: `0x14003ce2c`
- end: `0x14003ceb1`
- name: `BuildNtLanmanResponseEpilogue`
- size: `133`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140035df8`
- `0x14003ceb8`
- `0x140050ae0`

## callees

- `0x14000b120`
- `0x14003ce2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce90`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce90`
- `ksecdd!FreeContextBuffer` at `0x14003ce78`
- `ksecdd!FreeContextBuffer` at `0x14003ce78`
- `mrxsmb!MRxSmbUseKernelModeSecurity` at `0x14003ce6c`

## pseudocode

```c
__int64 __fastcall BuildNtLanmanResponseEpilogue(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 ExchangeSession; // rax
  __int64 *v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rbp
  unsigned int i; // edi
  void *v11; // rcx

  ExchangeSession = SmbCeGetExchangeSession(a1, a2, a3, a4);
  v7 = *v6;
  v8 = ExchangeSession;
  if ( *v6 )
  {
    v9 = *(_QWORD *)(v7 + 8);
    for ( i = 0; i < *(_DWORD *)(v7 + 4); ++i )
    {
      v11 = *(void **)(v9 + 16LL * i + 8);
      if ( v11 && (*(_DWORD *)(v8 + 8) & 8) == 0 && !MRxSmbUseKernelModeSecurity )
        FreeContextBuffer(v11);
    }
    ExFreePoolWithTag((PVOID)v7, 0);
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x14003ce2c  push    rbx
0x14003ce2e  push    rbp
0x14003ce2f  push    rsi
0x14003ce30  push    rdi
0x14003ce31  push    r14
0x14003ce33  sub     rsp, 20h
0x14003ce37  mov     rsi, rdx
0x14003ce3a  call    SmbCeGetExchangeSession
0x14003ce3f  mov     rbx, [rdx]
0x14003ce42  mov     r14, rax
0x14003ce45  test    rbx, rbx
0x14003ce48  jz      short loc_14003CEA3
0x14003ce4a  mov     rbp, [rbx+8]
0x14003ce4e  xor     edi, edi
0x14003ce50  cmp     [rbx+4], edi
0x14003ce53  jbe     short loc_14003CE8B
0x14003ce55  mov     eax, edi
0x14003ce57  add     rax, rax
0x14003ce5a  mov     rcx, [rbp+rax*8+8]; pvContextBuffer
0x14003ce5f  test    rcx, rcx
0x14003ce62  jz      short loc_14003CE84
0x14003ce64  mov     eax, [r14+8]
0x14003ce68  test    al, 8
0x14003ce6a  jnz     short loc_14003CE84
0x14003ce6c  mov     rax, cs:__imp_MRxSmbUseKernelModeSecurity
0x14003ce73  cmp     byte ptr [rax], 0
0x14003ce76  jnz     short loc_14003CE84
0x14003ce78  call    cs:__imp_FreeContextBuffer
0x14003ce7f  nop     dword ptr [rax+rax+00h]
0x14003ce84  inc     edi
0x14003ce86  cmp     edi, [rbx+4]
0x14003ce89  jb      short loc_14003CE55
0x14003ce8b  xor     edx, edx; Tag
0x14003ce8d  mov     rcx, rbx; P
0x14003ce90  call    cs:__imp_ExFreePoolWithTag
0x14003ce97  nop     dword ptr [rax+rax+00h]
0x14003ce9c  mov     qword ptr [rsi], 0
0x14003cea3  xor     eax, eax
0x14003cea5  add     rsp, 20h
0x14003cea9  pop     r14
0x14003ceab  pop     rdi
0x14003ceac  pop     rsi
0x14003cead  pop     rbp
0x14003ceae  pop     rbx
0x14003ceaf  retn
```
