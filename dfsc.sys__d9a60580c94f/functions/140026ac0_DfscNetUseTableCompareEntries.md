# DfscNetUseTableCompareEntries

- ea: `0x140026ac0`
- end: `0x140026be8`
- name: `DfscNetUseTableCompareEntries`
- size: `296`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400035dc`
- `0x140017c68`
- `0x140026ac0`

## import_xrefs

- `ntoskrnl!towupper` at `0x140026b19`
- `ntoskrnl!towupper` at `0x140026b2f`
- `ntoskrnl!towupper` at `0x140026b19`
- `ntoskrnl!towupper` at `0x140026b2f`

## pseudocode

```c
__int64 __fastcall DfscNetUseTableCompareEntries(struct _RTL_AVL_TABLE *Table, __int64 FirstStruct, char *SecondStruct)
{
  unsigned int v3; // ecx
  unsigned int v7; // edx
  int v8; // esi
  LONG IsPathEqualString; // esi
  int v10; // eax

  v3 = *((_DWORD *)SecondStruct + 4);
  if ( *(_DWORD *)(FirstStruct + 16) > v3 )
    return 1;
  if ( *(_DWORD *)(FirstStruct + 16) < v3 )
    return 0;
  v7 = *(_DWORD *)(FirstStruct + 20);
  if ( __PAIR64__(*(_DWORD *)(FirstStruct + 24), v7) == *(_QWORD *)(SecondStruct + 20) )
  {
    if ( (*(_DWORD *)(FirstStruct + 40) & 1) != 0 )
    {
      v8 = towupper(**(_WORD **)(FirstStruct + 8));
      IsPathEqualString = v8 - towupper(**((_WORD **)SecondStruct + 1));
    }
    else
    {
      IsPathEqualString = DfscIsPathEqualString((__m128i *)FirstStruct, (UNICODE_STRING *)SecondStruct);
    }
    if ( IsPathEqualString > 0 )
      return 1;
    if ( IsPathEqualString < 0 )
      return 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_dDDZ(
        WPP_GLOBAL_Control->AttachedDevice,
        14,
        (unsigned int)WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids,
        *(_DWORD *)(FirstStruct + 16),
        *(_DWORD *)(FirstStruct + 24),
        *(_DWORD *)(FirstStruct + 20),
        FirstStruct);
    }
    return 2;
  }
  else
  {
    v10 = *((_DWORD *)SecondStruct + 6);
    if ( *(_DWORD *)(FirstStruct + 24) != v10 )
      return *(_DWORD *)(FirstStruct + 24) > v10;
    return v7 > *((_DWORD *)SecondStruct + 5);
  }
}

```

## disassembly

```asm
0x140026ac0  mov     [rsp+arg_0], rbx
0x140026ac5  mov     [rsp+arg_8], rsi
0x140026aca  push    rdi
0x140026acb  sub     rsp, 40h
0x140026acf  mov     ecx, [r8+10h]
0x140026ad3  mov     rdi, r8
0x140026ad6  mov     rbx, rdx
0x140026ad9  cmp     [rdx+10h], ecx
0x140026adc  ja      short loc_140026B44
0x140026ade  jnb     short loc_140026AF3
0x140026ae0  xor     eax, eax
0x140026ae2  mov     rbx, [rsp+48h+arg_0]
0x140026ae7  mov     rsi, [rsp+48h+arg_8]
0x140026aec  add     rsp, 40h
0x140026af0  pop     rdi
0x140026af1  retn
0x140026af3  mov     ecx, [r8+14h]
0x140026af7  mov     edx, [rdx+14h]
0x140026afa  cmp     edx, ecx
0x140026afc  jnz     short loc_140026B4B
0x140026afe  mov     eax, [r8+18h]
0x140026b02  cmp     [rbx+18h], eax
0x140026b05  jnz     short loc_140026B4B
0x140026b07  mov     eax, [rbx+28h]
0x140026b0a  test    al, 1
0x140026b0c  jz      loc_140026BAB
0x140026b12  mov     rcx, [rbx+8]
0x140026b16  movzx   ecx, word ptr [rcx]; C
0x140026b19  call    cs:__imp_towupper
0x140026b20  nop     dword ptr [rax+rax+00h]
0x140026b25  mov     rcx, [rdi+8]
0x140026b29  movzx   esi, ax
0x140026b2c  movzx   ecx, word ptr [rcx]; C
0x140026b2f  call    cs:__imp_towupper
0x140026b36  nop     dword ptr [rax+rax+00h]
0x140026b3b  movzx   eax, ax
0x140026b3e  sub     esi, eax
0x140026b40  test    esi, esi
0x140026b42  jle     short loc_140026B6C
0x140026b44  mov     eax, 1
0x140026b49  jmp     short loc_140026AE2
0x140026b4b  mov     eax, [r8+18h]
0x140026b4f  cmp     [rbx+18h], eax
0x140026b52  jnz     short loc_140026BA4
0x140026b54  xor     eax, eax
0x140026b56  cmp     edx, ecx
0x140026b58  setnbe  al
0x140026b5b  mov     rbx, [rsp+48h+arg_0]
0x140026b60  mov     rsi, [rsp+48h+arg_8]
0x140026b65  add     rsp, 40h
0x140026b69  pop     rdi
0x140026b6a  retn
0x140026b6c  js      loc_140026AE0
0x140026b72  mov     rcx, cs:WPP_GLOBAL_Control
0x140026b79  lea     rax, WPP_GLOBAL_Control
0x140026b80  cmp     rcx, rax
0x140026b83  jz      short loc_140026B8E
0x140026b85  test    dword ptr [rcx+2Ch], 400000h
0x140026b8c  jnz     short loc_140026BBA
0x140026b8e  mov     rbx, [rsp+48h+arg_0]
0x140026b93  mov     eax, 2
0x140026b98  mov     rsi, [rsp+48h+arg_8]
0x140026b9d  add     rsp, 40h
0x140026ba1  pop     rdi
0x140026ba2  retn
0x140026ba4  jg      short loc_140026B44
0x140026ba6  jmp     loc_140026AE0
0x140026bab  mov     rdx, rdi
0x140026bae  mov     rcx, rbx
0x140026bb1  call    DfscIsPathEqualString
0x140026bb6  mov     esi, eax
0x140026bb8  jmp     short loc_140026B40
0x140026bba  mov     eax, [rbx+14h]
0x140026bbd  lea     r8, WPP_4cbf8115eb6f3bebf2b1c99b588386c6_Traceguids
0x140026bc4  mov     r9d, [rbx+10h]
0x140026bc8  mov     edx, 0Eh
0x140026bcd  mov     rcx, [rcx+18h]
0x140026bd1  mov     [rsp+48h+var_18], rbx
0x140026bd6  mov     [rsp+48h+var_20], eax
0x140026bda  mov     eax, [rbx+18h]
0x140026bdd  mov     [rsp+48h+var_28], eax
0x140026be1  call    WPP_SF_dDDZ
0x140026be6  jmp     short loc_140026B8E
```
