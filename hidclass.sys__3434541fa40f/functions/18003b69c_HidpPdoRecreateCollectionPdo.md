# HidpPdoRecreateCollectionPdo

- ea: `0x18003b69c`
- end: `0x18003b742`
- name: `HidpPdoRecreateCollectionPdo`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180019694`

## callees

- `0x180019014`
- `0x18002432c`
- `0x18003b69c`
- `0x18003f8bc`
- `0x18003f980`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18003b6e0`

## pseudocode

```c
__int64 __fastcall HidpPdoRecreateCollectionPdo(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rdi
  _QWORD *v4; // rcx
  __int64 v5; // rdi
  __int64 v7; // r10
  unsigned int OneCollectionPdo; // ebx
  PVOID v9; // rcx
  PVOID v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8

  v2 = *(_QWORD *)(a1 + 64);
  v4 = *(_QWORD **)(v2 + 40);
  v5 = v2 + 32;
  v7 = RefDriverExt(*v4);
  if ( v7 )
  {
    v9 = *(PVOID *)(v5 + 152);
    if ( !v9 || v9 == MmBadPointer || (v10 = *(PVOID *)(v5 + 288)) == 0 || v10 == MmBadPointer )
    {
      TraceLoggingNoTopLevelCollection(v5);
      OneCollectionPdo = -1073741436;
    }
    else
    {
      OneCollectionPdo = CreateOneCollectionPdo(v7, v5, *(_DWORD *)(a1 + 12), a2);
    }
    DerefDriverExt(**(_QWORD **)(v5 + 8), v11, v12);
  }
  else
  {
    return (unsigned int)-1073741438;
  }
  return OneCollectionPdo;
}

```

## disassembly

```asm
0x18003b69c  mov     [rsp+arg_0], rbx
0x18003b6a1  mov     [rsp+arg_8], rsi
0x18003b6a6  push    rdi
0x18003b6a7  sub     rsp, 20h
0x18003b6ab  mov     rdi, [rcx+40h]
0x18003b6af  mov     rbx, rcx
0x18003b6b2  mov     rcx, [rdi+28h]
0x18003b6b6  add     rdi, 20h ; ' '
0x18003b6ba  mov     rsi, rdx
0x18003b6bd  mov     rcx, [rcx]
0x18003b6c0  call    RefDriverExt
0x18003b6c5  mov     r10, rax
0x18003b6c8  test    rax, rax
0x18003b6cb  jnz     short loc_18003B6D4
0x18003b6cd  mov     ebx, 0C0000182h
0x18003b6d2  jmp     short loc_18003B72F
0x18003b6d4  mov     rcx, [rdi+98h]
0x18003b6db  test    rcx, rcx
0x18003b6de  jz      short loc_18003B716
0x18003b6e0  mov     rax, cs:MmBadPointer
0x18003b6e7  mov     rdx, [rax]
0x18003b6ea  cmp     rcx, rdx
0x18003b6ed  jz      short loc_18003B716
0x18003b6ef  mov     rax, [rdi+120h]
0x18003b6f6  test    rax, rax
0x18003b6f9  jz      short loc_18003B716
0x18003b6fb  cmp     rax, rdx
0x18003b6fe  jz      short loc_18003B716
0x18003b700  mov     r8d, [rbx+0Ch]
0x18003b704  mov     r9, rsi
0x18003b707  mov     rdx, rdi
0x18003b70a  mov     rcx, r10
0x18003b70d  call    CreateOneCollectionPdo
0x18003b712  mov     ebx, eax
0x18003b714  jmp     short loc_18003B723
0x18003b716  mov     rcx, rdi
0x18003b719  call    TraceLoggingNoTopLevelCollection
0x18003b71e  mov     ebx, 0C0000184h
0x18003b723  mov     rcx, [rdi+8]
0x18003b727  mov     rcx, [rcx]
0x18003b72a  call    DerefDriverExt
0x18003b72f  mov     rsi, [rsp+28h+arg_8]
0x18003b734  mov     eax, ebx
0x18003b736  mov     rbx, [rsp+28h+arg_0]
0x18003b73b  add     rsp, 20h
0x18003b73f  pop     rdi
0x18003b740  retn
```
