# NpUnlinkFcb

- ea: `0x1400107c0`
- end: `0x140010888`
- name: `NpUnlinkFcb`
- size: `200`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000d6dc`
- `0x14000e980`
- `0x14001399c`

## callees

- `0x140001010`
- `0x1400107c0`
- `0x140010d18`

## import_xrefs

- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001082a`
- `ntoskrnl!RtlRemoveUnicodePrefix` at `0x14001082a`

## pseudocode

```c
__int64 __fastcall NpUnlinkFcb(__int64 a1, __int64 a2, __int64 a3)
{
  const UNICODE_STRING *v3; // rdi
  __int64 result; // rax
  int v5; // ebp
  __int64 v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  _QWORD *v11; // rcx

  v3 = (const UNICODE_STRING *)(a2 + 160);
  result = 0;
  v5 = a3;
  if ( *(_WORD *)(a2 + 160) )
  {
    NpCancelWaiter((_QWORD *)(a1 + 144), v3, -1073741772, a3);
    v8 = *(_QWORD *)(a2 + 136);
    if ( *(_QWORD *)(v8 + 8) != a2 + 136
      || (v9 = *(_QWORD **)(a2 + 144), *v9 != a2 + 136)
      || (*v9 = v8,
          *(_QWORD *)(v8 + 8) = v9,
          RtlRemoveUnicodePrefix((PUNICODE_PREFIX_TABLE)(a1 + 216), (PUNICODE_PREFIX_TABLE_ENTRY)(a2 + 176)),
          v10 = *(_QWORD *)(a2 + 232),
          *(_QWORD *)(v10 + 8) != a2 + 232)
      || (v11 = *(_QWORD **)(a2 + 240), *v11 != a2 + 232) )
    {
      __fastfail(3u);
    }
    *v11 = v10;
    *(_QWORD *)(v10 + 8) = v11;
    NpCheckForNotifyWithFilter(a1, v5, 1, (_DWORD)v3, 2);
    result = 0;
    v3->Length = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400107c0  push    rbx
0x1400107c2  push    rbp
0x1400107c3  push    rsi
0x1400107c4  push    rdi
0x1400107c5  sub     rsp, 38h
0x1400107c9  lea     rdi, [rdx+0A0h]
0x1400107d0  xor     eax, eax
0x1400107d2  mov     rbp, r8
0x1400107d5  mov     rbx, rdx
0x1400107d8  mov     rsi, rcx
0x1400107db  cmp     ax, [rdi]
0x1400107de  jz      loc_140010877
0x1400107e4  mov     r9, r8
0x1400107e7  add     rcx, 90h
0x1400107ee  mov     r8d, 0C0000034h
0x1400107f4  mov     rdx, rdi
0x1400107f7  call    NpCancelWaiter
0x1400107fc  lea     rax, [rbx+88h]
0x140010803  mov     rdx, [rax]
0x140010806  cmp     [rdx+8], rax
0x14001080a  jnz     short loc_140010881
0x14001080c  mov     rcx, [rax+8]
0x140010810  cmp     [rcx], rax
0x140010813  jnz     short loc_140010881
0x140010815  mov     [rcx], rdx
0x140010818  mov     [rdx+8], rcx
0x14001081c  lea     rdx, [rbx+0B0h]; PrefixTableEntry
0x140010823  lea     rcx, [rsi+0D8h]; PrefixTable
0x14001082a  call    cs:__imp_RtlRemoveUnicodePrefix
0x140010831  nop     dword ptr [rax+rax+00h]
0x140010836  lea     rax, [rbx+0E8h]
0x14001083d  mov     rdx, [rax]
0x140010840  cmp     [rdx+8], rax
0x140010844  jnz     short loc_140010881
0x140010846  mov     rcx, [rax+8]
0x14001084a  cmp     [rcx], rax
0x14001084d  jnz     short loc_140010881
0x14001084f  mov     [rcx], rdx
0x140010852  mov     r9, rdi
0x140010855  mov     [rdx+8], rcx
0x140010859  mov     r8d, 1
0x14001085f  mov     rdx, rbp
0x140010862  mov     [rsp+58h+var_38], 2
0x14001086a  mov     rcx, rsi
0x14001086d  call    NpCheckForNotifyWithFilter
0x140010872  xor     eax, eax
0x140010874  mov     [rdi], ax
0x140010877  add     rsp, 38h
0x14001087b  pop     rdi
0x14001087c  pop     rsi
0x14001087d  pop     rbp
0x14001087e  pop     rbx
0x14001087f  retn
0x140010881  mov     ecx, 3
0x140010886  int     29h; Win8: RtlFailFast(ecx)
```
