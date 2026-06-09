# FvepReleaseRemoveLockAndWait

- ea: `0x1400267dc`
- end: `0x140026942`
- name: `FvepReleaseRemoveLockAndWait`
- size: `358`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400701c4`

## callees

- `0x1400267dc`
- `0x140026948`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14002685d`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14002685d`
- `ntoskrnl!KeBugCheckEx` at `0x1400268a3`
- `ntoskrnl!KeBugCheckEx` at `0x1400268c4`
- `ntoskrnl!KeBugCheckEx` at `0x1400268ef`
- `ntoskrnl!KeBugCheckEx` at `0x140026914`
- `ntoskrnl!KeBugCheckEx` at `0x140026935`
- `ntoskrnl!KeBugCheckEx` at `0x1400268a3`
- `ntoskrnl!KeBugCheckEx` at `0x1400268c4`
- `ntoskrnl!KeBugCheckEx` at `0x1400268ef`
- `ntoskrnl!KeBugCheckEx` at `0x140026914`
- `ntoskrnl!KeBugCheckEx` at `0x140026935`

## pseudocode

```c
__int64 __fastcall FvepReleaseRemoveLockAndWait(ULONG_PTR BugCheckParameter2)
{
  __int64 result; // rax
  signed __int64 v3; // r8
  signed __int64 v4; // [rsp+48h] [rbp+10h]
  __int64 v5; // [rsp+48h] [rbp+10h]

  if ( *(_QWORD *)(BugCheckParameter2 + 48) )
    return FvepReleaseScalableRemoveLockAndWait(BugCheckParameter2);
  do
  {
    v3 = *(_QWORD *)(BugCheckParameter2 + 8);
    if ( !(_DWORD)v3 )
      KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, 0, 0);
    if ( WORD2(v3) )
      KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, WORD2(v3), (unsigned int)v3);
    if ( (v3 & 0xFF000000000000LL) != 0 )
      KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, BYTE6(v3), (unsigned int)v3);
    HIDWORD(v4) = HIDWORD(v3) & 0xFF00FFFF | 0x10000;
    LODWORD(v4) = v3 - 1;
  }
  while ( v3 != _InterlockedCompareExchange64((volatile signed __int64 *)(BugCheckParameter2 + 8), v4, v3) );
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)(BugCheckParameter2 + 16), *(PVOID *)BugCheckParameter2, 0x20u);
  v5 = *(_QWORD *)(BugCheckParameter2 + 8);
  if ( (_DWORD)v5 )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, 0, (unsigned int)v5);
  result = WORD2(v5);
  if ( WORD2(v5) )
    KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, WORD2(v5), 0);
  return result;
}

```

## disassembly

```asm
0x1400267dc  mov     [rsp+arg_8], rdx
0x1400267e1  push    rbx
0x1400267e2  sub     rsp, 30h
0x1400267e6  cmp     qword ptr [rcx+30h], 0
0x1400267eb  mov     rbx, rcx
0x1400267ee  jz      short loc_1400267FC
0x1400267f0  call    FvepReleaseScalableRemoveLockAndWait
0x1400267f5  add     rsp, 30h
0x1400267f9  pop     rbx
0x1400267fa  retn
0x1400267fc  mov     r8, [rbx+8]
0x140026800  mov     edx, r8d
0x140026803  mov     [rsp+38h+arg_8], r8
0x140026808  test    edx, edx
0x14002680a  jz      loc_140026921
0x140026810  mov     rcx, r8
0x140026813  shr     rcx, 20h
0x140026817  test    cx, cx
0x14002681a  jnz     loc_1400268FC
0x140026820  test    ecx, 0FF0000h
0x140026826  jnz     loc_1400268D1
0x14002682c  and     ecx, 0FF01FFFFh
0x140026832  mov     rax, r8
0x140026835  bts     ecx, 10h
0x140026839  dec     edx
0x14002683b  mov     dword ptr [rsp+38h+arg_8+4], ecx
0x14002683f  mov     dword ptr [rsp+38h+arg_8], edx
0x140026843  mov     rcx, [rsp+38h+arg_8]
0x140026848  lock cmpxchg [rbx+8], rcx
0x14002684e  jnz     short loc_1400267FC
0x140026850  mov     rdx, [rbx]; Tag
0x140026853  lea     rcx, [rbx+10h]; RemoveLock
0x140026857  mov     r8d, 20h ; ' '; RemlockSize
0x14002685d  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140026864  nop     dword ptr [rax+rax+00h]
0x140026869  mov     rax, [rbx+8]
0x14002686d  mov     [rsp+38h+arg_8], rax
0x140026872  mov     eax, eax
0x140026874  test    eax, eax
0x140026876  jnz     short loc_1400268B0
0x140026878  movzx   eax, word ptr [rsp+38h+arg_8+4]
0x14002687d  test    eax, eax
0x14002687f  jz      loc_1400267F5
0x140026885  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x140026889  mov     r8, rbx; BugCheckParameter2
0x14002688c  movzx   r9d, ax; BugCheckParameter3
0x140026890  mov     edx, 0Eh; BugCheckParameter1
0x140026895  mov     ecx, 120h; BugCheckCode
0x14002689a  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x1400268a3  call    cs:__imp_KeBugCheckEx
0x1400268b0  xor     r9d, r9d; BugCheckParameter3
0x1400268b3  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x1400268b8  mov     r8, rbx; BugCheckParameter2
0x1400268bb  mov     ecx, 120h; BugCheckCode
0x1400268c0  lea     edx, [r9+0Eh]; BugCheckParameter1
0x1400268c4  call    cs:__imp_KeBugCheckEx
0x1400268d1  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x1400268d5  mov     r8, rbx; BugCheckParameter2
0x1400268d8  shr     rax, 10h
0x1400268dc  mov     ecx, 120h; BugCheckCode
0x1400268e1  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x1400268e6  mov     edx, 0Eh; BugCheckParameter1
0x1400268eb  movzx   r9d, al; BugCheckParameter3
0x1400268ef  call    cs:__imp_KeBugCheckEx
0x1400268fc  movzx   r9d, word ptr [rsp+38h+arg_8+4]; BugCheckParameter3
0x140026902  mov     r8, rbx; BugCheckParameter2
0x140026905  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x14002690a  mov     ecx, 120h; BugCheckCode
0x14002690f  mov     edx, 0Eh; BugCheckParameter1
0x140026914  call    cs:__imp_KeBugCheckEx
0x140026921  xor     r9d, r9d; BugCheckParameter3
0x140026924  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x140026929  mov     r8, rbx; BugCheckParameter2
0x14002692c  mov     ecx, 120h; BugCheckCode
0x140026931  lea     edx, [r9+0Eh]; BugCheckParameter1
0x140026935  call    cs:__imp_KeBugCheckEx
```
