# FatRemoveNames

- ea: `0x1400492a4`
- end: `0x140049377`
- name: `FatRemoveNames`
- size: `211`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1400034f0`
- `0x140024bd4`
- `0x1400268c0`
- `0x1400333d0`
- `0x14003a3e0`
- `0x14003bea4`
- `0x140048184`
- `0x1400491b4`

## callees

- `0x1400492a4`

## import_xrefs

- `ntoskrnl!RtlFreeOemString` at `0x140049314`
- `ntoskrnl!RtlFreeOemString` at `0x140049314`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004934d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004934d`
- `ntoskrnl!RtlDelete` at `0x1400492ce`
- `ntoskrnl!RtlDelete` at `0x1400492fe`
- `ntoskrnl!RtlDelete` at `0x140049337`
- `ntoskrnl!RtlDelete` at `0x1400492ce`
- `ntoskrnl!RtlDelete` at `0x1400492fe`
- `ntoskrnl!RtlDelete` at `0x140049337`

## pseudocode

```c
void __fastcall FatRemoveNames(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  unsigned int v4; // eax

  if ( (*(_DWORD *)(a2 + 192) & 0x100) != 0 )
  {
    v3 = *(_QWORD *)(a2 + 176);
    *(_QWORD *)(v3 + 384) = RtlDelete((PRTL_SPLAY_LINKS)(a2 + 504));
    v4 = *(_DWORD *)(a2 + 192);
    if ( (v4 & 0x200) != 0 )
    {
      *(_QWORD *)(v3 + 384) = RtlDelete((PRTL_SPLAY_LINKS)(a2 + 600));
      RtlFreeOemString((POEM_STRING)(a2 + 576));
      *(_DWORD *)(a2 + 192) &= ~0x200u;
      v4 = *(_DWORD *)(a2 + 192);
    }
    if ( (v4 & 0x400) != 0 )
    {
      *(_QWORD *)(v3 + 392) = RtlDelete((PRTL_SPLAY_LINKS)(a2 + 600));
      RtlFreeUnicodeString((PUNICODE_STRING)(a2 + 576));
      v4 = *(_DWORD *)(a2 + 192) & 0xFFFFFBFF;
    }
    *(_DWORD *)(a2 + 192) = v4 & 0xFFFFFEFF;
  }
}

```

## disassembly

```asm
0x1400492a4  push    rbx
0x1400492a6  push    rbp
0x1400492a7  push    rsi
0x1400492a8  push    rdi
0x1400492a9  sub     rsp, 28h
0x1400492ad  test    dword ptr [rdx+0C0h], 100h
0x1400492b7  mov     rbx, rdx
0x1400492ba  jz      loc_14004936D
0x1400492c0  mov     rdi, [rdx+0B0h]
0x1400492c7  lea     rcx, [rdx+1F8h]; Links
0x1400492ce  call    cs:__imp_RtlDelete
0x1400492d5  nop     dword ptr [rax+rax+00h]
0x1400492da  mov     [rdi+180h], rax
0x1400492e1  lea     rsi, [rbx+258h]
0x1400492e8  mov     eax, [rbx+0C0h]
0x1400492ee  lea     rbp, [rbx+240h]
0x1400492f5  bt      eax, 9
0x1400492f9  jnb     short loc_14004932E
0x1400492fb  mov     rcx, rsi; Links
0x1400492fe  call    cs:__imp_RtlDelete
0x140049305  nop     dword ptr [rax+rax+00h]
0x14004930a  mov     rcx, rbp; OemString
0x14004930d  mov     [rdi+180h], rax
0x140049314  call    cs:__imp_RtlFreeOemString
0x14004931b  nop     dword ptr [rax+rax+00h]
0x140049320  btr     dword ptr [rbx+0C0h], 9
0x140049328  mov     eax, [rbx+0C0h]
0x14004932e  bt      eax, 0Ah
0x140049332  jnb     short loc_140049363
0x140049334  mov     rcx, rsi; Links
0x140049337  call    cs:__imp_RtlDelete
0x14004933e  nop     dword ptr [rax+rax+00h]
0x140049343  mov     rcx, rbp; UnicodeString
0x140049346  mov     [rdi+188h], rax
0x14004934d  call    cs:__imp_RtlFreeUnicodeString
0x140049354  nop     dword ptr [rax+rax+00h]
0x140049359  mov     eax, [rbx+0C0h]
0x14004935f  btr     eax, 0Ah
0x140049363  btr     eax, 8
0x140049367  mov     [rbx+0C0h], eax
0x14004936d  add     rsp, 28h
0x140049371  pop     rdi
0x140049372  pop     rsi
0x140049373  pop     rbp
0x140049374  pop     rbx
0x140049375  retn
```
