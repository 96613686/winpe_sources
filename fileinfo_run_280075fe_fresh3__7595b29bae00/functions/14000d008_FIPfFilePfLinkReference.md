# FIPfFilePfLinkReference

- ea: `0x14000d008`
- end: `0x14000d096`
- name: `FIPfFilePfLinkReference`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001606c`

## callees

- `0x140001da0`
- `0x140001f20`
- `0x14000d008`

## import_xrefs

- `FLTMGR!FltReferenceContext` at `0x14000d01b`
- `FLTMGR!FltReferenceContext` at `0x14000d01b`

## pseudocode

```c
__int64 __fastcall FIPfFilePfLinkReference(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  __int64 result; // rax
  __int64 v6; // rdi
  _QWORD *v7; // rcx

  FltReferenceContext(*(PFLT_CONTEXT *)(a1 + 56));
  v4 = *(_QWORD *)(a1 + 56);
  result = *(unsigned int *)(v4 + 56);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
  v6 = *(_QWORD *)(v4 + 24);
  if ( !a2 )
    result = FILockExclusiveAcquire(v6 + 136);
  if ( !*(_DWORD *)(a1 + 16) )
  {
    result = v6 + 144;
    v7 = *(_QWORD **)(v6 + 152);
    if ( *v7 != v6 + 144 )
      __fastfail(3u);
    *(_QWORD *)a1 = result;
    *(_QWORD *)(a1 + 8) = v7;
    *v7 = a1;
    *(_QWORD *)(v6 + 152) = a1;
    ++*(_DWORD *)(v6 + 208);
  }
  ++*(_DWORD *)(a1 + 16);
  if ( !a2 )
    return FILockExclusiveRelease(v6 + 136);
  return result;
}

```

## disassembly

```asm
0x14000d008  push    rbx
0x14000d00a  push    rbp
0x14000d00b  push    rsi
0x14000d00c  push    rdi
0x14000d00d  sub     rsp, 28h
0x14000d011  mov     rbx, rcx
0x14000d014  mov     rbp, rdx
0x14000d017  mov     rcx, [rcx+38h]; Context
0x14000d01b  call    cs:__imp_FltReferenceContext
0x14000d022  nop     dword ptr [rax+rax+00h]
0x14000d027  mov     r8, [rbx+38h]
0x14000d02b  mov     eax, [r8+38h]
0x14000d02f  lock inc dword ptr [rbx+14h]
0x14000d033  mov     rdi, [r8+18h]
0x14000d037  lea     rsi, [rdi+88h]
0x14000d03e  test    rbp, rbp
0x14000d041  jnz     short loc_14000D04B
0x14000d043  mov     rcx, rsi
0x14000d046  call    FILockExclusiveAcquire
0x14000d04b  cmp     dword ptr [rbx+10h], 0
0x14000d04f  jnz     short loc_14000D07C
0x14000d051  lea     rax, [rdi+90h]
0x14000d058  mov     rcx, [rax+8]
0x14000d05c  cmp     [rcx], rax
0x14000d05f  jz      short loc_14000D068
0x14000d061  mov     ecx, 3
0x14000d066  int     29h; Win8: RtlFailFast(ecx)
0x14000d068  mov     [rbx], rax
0x14000d06b  mov     [rbx+8], rcx
0x14000d06f  mov     [rcx], rbx
0x14000d072  mov     [rax+8], rbx
0x14000d076  inc     dword ptr [rdi+0D0h]
0x14000d07c  inc     dword ptr [rbx+10h]
0x14000d07f  test    rbp, rbp
0x14000d082  jnz     short loc_14000D08C
0x14000d084  mov     rcx, rsi
0x14000d087  call    FILockExclusiveRelease
0x14000d08c  add     rsp, 28h
0x14000d090  pop     rdi
0x14000d091  pop     rsi
0x14000d092  pop     rbp
0x14000d093  pop     rbx
0x14000d094  retn
```
