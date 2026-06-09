# FvepReleaseRemoveLockAndWait

- ea: `0x1400277dc`
- end: `0x140027942`
- name: `FvepReleaseRemoveLockAndWait`
- size: `358`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140072194`

## callees

- `0x1400277dc`
- `0x140027948`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14002785d`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x14002785d`
- `ntoskrnl!KeBugCheckEx` at `0x1400278a3`
- `ntoskrnl!KeBugCheckEx` at `0x1400278c4`
- `ntoskrnl!KeBugCheckEx` at `0x1400278ef`
- `ntoskrnl!KeBugCheckEx` at `0x140027914`
- `ntoskrnl!KeBugCheckEx` at `0x140027935`
- `ntoskrnl!KeBugCheckEx` at `0x1400278a3`
- `ntoskrnl!KeBugCheckEx` at `0x1400278c4`
- `ntoskrnl!KeBugCheckEx` at `0x1400278ef`
- `ntoskrnl!KeBugCheckEx` at `0x140027914`
- `ntoskrnl!KeBugCheckEx` at `0x140027935`

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
0x1400277dc  mov     [rsp+arg_8], rdx
0x1400277e1  push    rbx
0x1400277e2  sub     rsp, 30h
0x1400277e6  cmp     qword ptr [rcx+30h], 0
0x1400277eb  mov     rbx, rcx
0x1400277ee  jz      short loc_1400277FC
0x1400277f0  call    FvepReleaseScalableRemoveLockAndWait
0x1400277f5  add     rsp, 30h
0x1400277f9  pop     rbx
0x1400277fa  retn
0x1400277fc  mov     r8, [rbx+8]
0x140027800  mov     edx, r8d
0x140027803  mov     [rsp+38h+arg_8], r8
0x140027808  test    edx, edx
0x14002780a  jz      loc_140027921
0x140027810  mov     rcx, r8
0x140027813  shr     rcx, 20h
0x140027817  test    cx, cx
0x14002781a  jnz     loc_1400278FC
0x140027820  test    ecx, 0FF0000h
0x140027826  jnz     loc_1400278D1
0x14002782c  and     ecx, 0FF01FFFFh
0x140027832  mov     rax, r8
0x140027835  bts     ecx, 10h
0x140027839  dec     edx
0x14002783b  mov     dword ptr [rsp+38h+arg_8+4], ecx
0x14002783f  mov     dword ptr [rsp+38h+arg_8], edx
0x140027843  mov     rcx, [rsp+38h+arg_8]
0x140027848  lock cmpxchg [rbx+8], rcx
0x14002784e  jnz     short loc_1400277FC
0x140027850  mov     rdx, [rbx]; Tag
0x140027853  lea     rcx, [rbx+10h]; RemoveLock
0x140027857  mov     r8d, 20h ; ' '; RemlockSize
0x14002785d  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x140027864  nop     dword ptr [rax+rax+00h]
0x140027869  mov     rax, [rbx+8]
0x14002786d  mov     [rsp+38h+arg_8], rax
0x140027872  mov     eax, eax
0x140027874  test    eax, eax
0x140027876  jnz     short loc_1400278B0
0x140027878  movzx   eax, word ptr [rsp+38h+arg_8+4]
0x14002787d  test    eax, eax
0x14002787f  jz      loc_1400277F5
0x140027885  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x140027889  mov     r8, rbx; BugCheckParameter2
0x14002788c  movzx   r9d, ax; BugCheckParameter3
0x140027890  mov     edx, 0Eh; BugCheckParameter1
0x140027895  mov     ecx, 120h; BugCheckCode
0x14002789a  mov     [rsp+38h+BugCheckParameter4], 0; BugCheckParameter4
0x1400278a3  call    cs:__imp_KeBugCheckEx
0x1400278b0  xor     r9d, r9d; BugCheckParameter3
0x1400278b3  mov     [rsp+38h+BugCheckParameter4], rax; BugCheckParameter4
0x1400278b8  mov     r8, rbx; BugCheckParameter2
0x1400278bb  mov     ecx, 120h; BugCheckCode
0x1400278c0  lea     edx, [r9+0Eh]; BugCheckParameter1
0x1400278c4  call    cs:__imp_KeBugCheckEx
0x1400278d1  mov     eax, dword ptr [rsp+38h+arg_8+4]
0x1400278d5  mov     r8, rbx; BugCheckParameter2
0x1400278d8  shr     rax, 10h
0x1400278dc  mov     ecx, 120h; BugCheckCode
0x1400278e1  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x1400278e6  mov     edx, 0Eh; BugCheckParameter1
0x1400278eb  movzx   r9d, al; BugCheckParameter3
0x1400278ef  call    cs:__imp_KeBugCheckEx
0x1400278fc  movzx   r9d, word ptr [rsp+38h+arg_8+4]; BugCheckParameter3
0x140027902  mov     r8, rbx; BugCheckParameter2
0x140027905  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x14002790a  mov     ecx, 120h; BugCheckCode
0x14002790f  mov     edx, 0Eh; BugCheckParameter1
0x140027914  call    cs:__imp_KeBugCheckEx
0x140027921  xor     r9d, r9d; BugCheckParameter3
0x140027924  mov     [rsp+38h+BugCheckParameter4], rdx; BugCheckParameter4
0x140027929  mov     r8, rbx; BugCheckParameter2
0x14002792c  mov     ecx, 120h; BugCheckCode
0x140027931  lea     edx, [r9+0Eh]; BugCheckParameter1
0x140027935  call    cs:__imp_KeBugCheckEx
```
