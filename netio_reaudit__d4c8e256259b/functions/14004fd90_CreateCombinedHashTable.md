# CreateCombinedHashTable

- ea: `0x14004fd90`
- end: `0x14004fe1b`
- name: `CreateCombinedHashTable`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14004fd24`
- `0x140068a14`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14004fd90`

## import_xrefs

- `ntoskrnl!RtlCreateHashTable` at `0x14004fdc0`
- `ntoskrnl!RtlCreateHashTable` at `0x14004fdc0`

## string_xrefs

- `0x14004fdd6`: `RtlCreateHashTable`
- `0x14004fdf0`: `CreateCombinedHashTable`

## pseudocode

```c
__int64 __fastcall CreateCombinedHashTable(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  __int64 v3; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx

  v2 = (_QWORD *)(a1 + 8);
  v3 = 0;
  if ( *(_DWORD *)a1 )
  {
    ++*(_DWORD *)a1;
    *a2 = *v2;
  }
  else if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), 0, 0) )
  {
    v8 = *v2;
    *(_DWORD *)a1 = 1;
    *a2 = v8;
  }
  else
  {
    v7 = WfpReportSysErrorAsNtStatus(v6, "RtlCreateHashTable", 3221225473LL, 1);
    v3 = v7;
    if ( v7 )
      WfpReportError(v7, "CreateCombinedHashTable");
  }
  return v3;
}

```

## disassembly

```asm
0x14004fd90  push    rbx
0x14004fd92  push    rsi
0x14004fd93  push    rdi
0x14004fd94  push    r14
0x14004fd96  sub     rsp, 28h
0x14004fd9a  mov     eax, [rcx]
0x14004fd9c  lea     rsi, [rcx+8]
0x14004fda0  xor     ebx, ebx
0x14004fda2  mov     r14, rdx
0x14004fda5  mov     rdi, rcx
0x14004fda8  test    eax, eax
0x14004fdaa  jz      short loc_14004FDB8
0x14004fdac  inc     eax
0x14004fdae  mov     [rcx], eax
0x14004fdb0  mov     rax, [rsi]
0x14004fdb3  mov     [rdx], rax
0x14004fdb6  jmp     short loc_14004FE0D
0x14004fdb8  xor     r8d, r8d; Flags
0x14004fdbb  xor     edx, edx; Shift
0x14004fdbd  mov     rcx, rsi; HashTable
0x14004fdc0  call    cs:__imp_RtlCreateHashTable
0x14004fdc7  nop     dword ptr [rax+rax+00h]
0x14004fdcc  test    al, al
0x14004fdce  jnz     short loc_14004FE01
0x14004fdd0  mov     r9d, 1
0x14004fdd6  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x14004fddd  mov     r8d, 0C0000001h
0x14004fde3  call    WfpReportSysErrorAsNtStatus
0x14004fde8  mov     rbx, rax
0x14004fdeb  test    rax, rax
0x14004fdee  jz      short loc_14004FE0D
0x14004fdf0  lea     rdx, aCreatecombined; "CreateCombinedHashTable"
0x14004fdf7  mov     rcx, rax
0x14004fdfa  call    WfpReportError
0x14004fdff  jmp     short loc_14004FE0D
0x14004fe01  mov     rcx, [rsi]
0x14004fe04  mov     dword ptr [rdi], 1
0x14004fe0a  mov     [r14], rcx
0x14004fe0d  mov     rax, rbx
0x14004fe10  add     rsp, 28h
0x14004fe14  pop     r14
0x14004fe16  pop     rdi
0x14004fe17  pop     rsi
0x14004fe18  pop     rbx
0x14004fe19  retn
```
