# SecGetSessionsFilterMaskFromMatchEntries

- ea: `0x14003a4c4`
- end: `0x14003a5b7`
- name: `SecGetSessionsFilterMaskFromMatchEntries`
- size: `243`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140007db4`
- `0x140036860`
- `0x140036df4`
- `0x14003715c`
- `0x1400373fc`
- `0x1400376ec`
- `0x140037a04`
- `0x140037d30`
- `0x140038164`

## callees

- `0x14001042b`
- `0x1400104eb`
- `0x14003a4c4`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003a543`
- `ntoskrnl!RtlCompareMemory` at `0x14003a543`

## pseudocode

```c
_UNKNOWN **__fastcall SecGetSessionsFilterMaskFromMatchEntries(unsigned int a1, __int64 a2, __int64 *a3)
{
  _UNKNOWN **result; // rax
  __int64 v4; // rbx
  unsigned int i; // esi
  _QWORD *v9; // rdi
  __int64 v10; // rbx
  _UNKNOWN *retaddr; // [rsp+38h] [rbp+0h] BYREF

  result = &retaddr;
  v4 = 0;
  if ( a2 && a1 )
  {
    FltAcquirePushLockSharedEx_0((char *)SecData + 1240, 0);
    for ( i = 0; i < a1; ++i )
    {
      v9 = (_QWORD *)*((_QWORD *)SecData + 156);
      if ( v9 != (_QWORD *)((char *)SecData + 1248) )
      {
        while ( RtlCompareMemory((const void *)(a2 + 20LL * i), v9 + 2, 0x10u) != 16 )
        {
          v9 = (_QWORD *)*v9;
          if ( v9 == (_QWORD *)((char *)SecData + 1248) )
            goto LABEL_9;
        }
        v4 |= v9[4];
      }
LABEL_9:
      ;
    }
    result = (_UNKNOWN **)FltReleasePushLockEx_0((char *)SecData + 1240, 0);
    v10 = ~v4;
  }
  else
  {
    v10 = -1;
  }
  *a3 = v10;
  return result;
}

```

## disassembly

```asm
0x14003a4c4  mov     rax, rsp
0x14003a4c7  mov     [rax+8], rbx
0x14003a4cb  mov     [rax+10h], rbp
0x14003a4cf  mov     [rax+18h], rsi
0x14003a4d3  mov     [rax+20h], rdi
0x14003a4d7  push    r12
0x14003a4d9  push    r14
0x14003a4db  push    r15
0x14003a4dd  sub     rsp, 20h
0x14003a4e1  xor     ebx, ebx
0x14003a4e3  mov     r15, r8
0x14003a4e6  mov     r14, rdx
0x14003a4e9  mov     ebp, ecx
0x14003a4eb  test    rdx, rdx
0x14003a4ee  jz      loc_14003A590
0x14003a4f4  test    ecx, ecx
0x14003a4f6  jz      loc_14003A590
0x14003a4fc  mov     rcx, cs:SecData
0x14003a503  xor     edx, edx
0x14003a505  add     rcx, 4D8h
0x14003a50c  call    FltAcquirePushLockSharedEx_0
0x14003a511  mov     esi, ebx
0x14003a513  test    ebp, ebp
0x14003a515  jz      short loc_14003A576
0x14003a517  mov     rax, cs:SecData
0x14003a51e  add     rax, 4E0h
0x14003a524  mov     rdi, [rax]
0x14003a527  cmp     rdi, rax
0x14003a52a  jz      short loc_14003A570
0x14003a52c  mov     eax, esi
0x14003a52e  lea     rcx, [rax+rax*4]
0x14003a532  lea     r12, [r14+rcx*4]
0x14003a536  lea     rdx, [rdi+10h]; Source2
0x14003a53a  mov     r8d, 10h; Length
0x14003a540  mov     rcx, r12; Source1
0x14003a543  call    cs:__imp_RtlCompareMemory
0x14003a54a  nop     dword ptr [rax+rax+00h]
0x14003a54f  cmp     rax, 10h
0x14003a553  jz      short loc_14003A56C
0x14003a555  mov     rax, cs:SecData
0x14003a55c  mov     rdi, [rdi]
0x14003a55f  add     rax, 4E0h
0x14003a565  cmp     rdi, rax
0x14003a568  jnz     short loc_14003A536
0x14003a56a  jmp     short loc_14003A570
0x14003a56c  or      rbx, [rdi+20h]
0x14003a570  inc     esi
0x14003a572  cmp     esi, ebp
0x14003a574  jb      short loc_14003A517
0x14003a576  mov     rcx, cs:SecData
0x14003a57d  xor     edx, edx
0x14003a57f  add     rcx, 4D8h
0x14003a586  call    FltReleasePushLockEx_0
0x14003a58b  not     rbx
0x14003a58e  jmp     short loc_14003A594
0x14003a590  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003a594  mov     [r15], rbx
0x14003a597  mov     rbx, [rsp+38h+arg_0]
0x14003a59c  mov     rbp, [rsp+38h+arg_8]
0x14003a5a1  mov     rsi, [rsp+38h+arg_10]
0x14003a5a6  mov     rdi, [rsp+38h+arg_18]
0x14003a5ab  add     rsp, 20h
0x14003a5af  pop     r15
0x14003a5b1  pop     r14
0x14003a5b3  pop     r12
0x14003a5b5  retn
```
