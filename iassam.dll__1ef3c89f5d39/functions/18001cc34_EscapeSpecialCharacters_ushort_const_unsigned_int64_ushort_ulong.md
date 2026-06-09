# EscapeSpecialCharacters(ushort const *,unsigned __int64,ushort *,ulong)

- ea: `0x18001cc34`
- end: `0x18001cd88`
- name: `?EscapeSpecialCharacters@@YAKPEBG_KPEAGK@Z`
- size: `340`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001d04c`

## callees

- `0x18000e754`
- `0x18001cc34`
- `0x1800254a0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001ccf8`
- `msvcrt!wcscpy_s` at `0x18001ccf8`

## string_xrefs

- `0x18001cd45`: `Could not completely encode username %S.`

## pseudocode

```c
__int64 __fastcall EscapeSpecialCharacters(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v8; // r14
  __int64 v9; // rbx
  int v10; // eax
  const wchar_t *v11; // r8
  int v12; // r9d

  if ( !a2 || !a4 || a4 < a2 || !a1 || !a3 )
    return 87;
  v8 = 0;
  v9 = 0;
  while ( (unsigned int)v9 < a4 )
  {
    switch ( a1[v8] )
    {
      case '(':
        v11 = L"\\28";
        goto LABEL_19;
      case ')':
        v11 = L"\\29";
        goto LABEL_19;
      case '*':
        v11 = L"\\2a";
        goto LABEL_19;
      case '/':
        v11 = L"\\2f";
        goto LABEL_19;
      case '\\':
        v11 = L"\\5c";
LABEL_19:
        if ( a4 < (int)v9 + 3 )
          goto LABEL_22;
        wcscpy_s(&a3[v9], 4u, v11);
        v10 = 3;
        goto LABEL_21;
    }
    a3[v9] = a1[v8];
    v10 = 1;
LABEL_21:
    v8 = (unsigned int)(v8 + 1);
    v9 = (unsigned int)(v10 + v9);
    if ( (unsigned int)v8 >= a2 )
      break;
  }
LABEL_22:
  a3[v9] = 0;
  if ( (unsigned int)v8 == a2 )
    return 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Could not completely encode username %S.");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids,
      v12,
      (__int64)a1);
  }
  return 87;
}

```

## disassembly

```asm
0x18001cc34  push    rbx
0x18001cc36  push    rbp
0x18001cc37  push    rsi
0x18001cc38  push    rdi
0x18001cc39  push    r14
0x18001cc3b  push    r15
0x18001cc3d  sub     rsp, 38h
0x18001cc41  mov     esi, r9d
0x18001cc44  mov     r15, r8
0x18001cc47  mov     rdi, rdx
0x18001cc4a  mov     rbp, rcx
0x18001cc4d  test    rdx, rdx
0x18001cc50  jz      loc_18001CD72
0x18001cc56  test    r9d, r9d
0x18001cc59  jz      loc_18001CD72
0x18001cc5f  cmp     rsi, rdx
0x18001cc62  jb      loc_18001CD72
0x18001cc68  test    rcx, rcx
0x18001cc6b  jz      loc_18001CD72
0x18001cc71  test    r8, r8
0x18001cc74  jz      loc_18001CD72
0x18001cc7a  xor     r14d, r14d
0x18001cc7d  xor     ebx, ebx
0x18001cc7f  test    rdx, rdx
0x18001cc82  jz      loc_18001CD14
0x18001cc88  cmp     ebx, esi
0x18001cc8a  jnb     loc_18001CD14
0x18001cc90  movzx   edx, word ptr [rbp+r14*2+0]
0x18001cc96  mov     ecx, edx
0x18001cc98  sub     ecx, 28h ; '('
0x18001cc9b  jz      short loc_18001CCE1
0x18001cc9d  sub     ecx, 1
0x18001cca0  jz      short loc_18001CCD8
0x18001cca2  sub     ecx, 1
0x18001cca5  jz      short loc_18001CCCF
0x18001cca7  sub     ecx, 5
0x18001ccaa  jz      short loc_18001CCC6
0x18001ccac  cmp     ecx, 2Dh ; '-'
0x18001ccaf  jz      short loc_18001CCBD
0x18001ccb1  mov     [r15+rbx*2], dx
0x18001ccb6  mov     eax, 1
0x18001ccbb  jmp     short loc_18001CD03
0x18001ccbd  lea     r8, a5c; "\\5c"
0x18001ccc4  jmp     short loc_18001CCE8
0x18001ccc6  lea     r8, a2f; "\\2f"
0x18001cccd  jmp     short loc_18001CCE8
0x18001cccf  lea     r8, a2a; "\\2a"
0x18001ccd6  jmp     short loc_18001CCE8
0x18001ccd8  lea     r8, a29; "\\29"
0x18001ccdf  jmp     short loc_18001CCE8
0x18001cce1  lea     r8, a28; "\\28"
0x18001cce8  lea     eax, [rbx+3]
0x18001cceb  cmp     esi, eax
0x18001cced  jb      short loc_18001CD14
0x18001ccef  lea     rcx, [r15+rbx*2]; Destination
0x18001ccf3  mov     edx, 4; SizeInWords
0x18001ccf8  call    cs:__imp_wcscpy_s
0x18001ccfe  mov     eax, 3
0x18001cd03  inc     r14d
0x18001cd06  add     ebx, eax
0x18001cd08  mov     eax, r14d
0x18001cd0b  cmp     rax, rdi
0x18001cd0e  jb      loc_18001CC88
0x18001cd14  xor     eax, eax
0x18001cd16  mov     [r15+rbx*2], ax
0x18001cd1b  mov     eax, r14d
0x18001cd1e  cmp     rax, rdi
0x18001cd21  jz      short loc_18001CD84
0x18001cd23  mov     rax, cs:WPP_GLOBAL_Control
0x18001cd2a  lea     rcx, WPP_GLOBAL_Control
0x18001cd31  cmp     rax, rcx
0x18001cd34  jz      short loc_18001CD72
0x18001cd36  cmp     byte ptr [rax+19h], 4
0x18001cd3a  jb      short loc_18001CD72
0x18001cd3c  test    byte ptr [rax+1Ch], 4
0x18001cd40  jz      short loc_18001CD72
0x18001cd42  mov     rdx, rbp
0x18001cd45  lea     rcx, aCouldNotComple; "Could not completely encode username %S"...
0x18001cd4c  call    WppDbgPrint
0x18001cd51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd58  lea     r8, WPP_4c4937dd1ef3394d6e9963f59526f193_Traceguids
0x18001cd5f  mov     edx, 11h
0x18001cd64  mov     [rsp+68h+var_48], rbp
0x18001cd69  mov     rcx, [rcx+10h]
0x18001cd6d  call    WPP_SF_sS
0x18001cd72  mov     eax, 57h ; 'W'
0x18001cd77  add     rsp, 38h
0x18001cd7b  pop     r15
0x18001cd7d  pop     r14
0x18001cd7f  pop     rdi
0x18001cd80  pop     rsi
0x18001cd81  pop     rbp
0x18001cd82  pop     rbx
0x18001cd83  retn
0x18001cd84  xor     eax, eax
0x18001cd86  jmp     short loc_18001CD77
```
