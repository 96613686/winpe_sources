# I_ReaderListReadDefaultContainer

- ea: `0x180020ff8`
- end: `0x1800210d8`
- name: `I_ReaderListReadDefaultContainer`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e4bc`

## callees

- `0x180004600`
- `0x180018b58`
- `0x180018bb4`
- `0x1800205c4`
- `0x180020ff8`

## pseudocode

```c
__int64 __fastcall I_ReaderListReadDefaultContainer(__int64 a1, __int64 a2, _DWORD *a3)
{
  STRSAFE_LPSTR v6; // rcx
  HCRYPTPROV v7; // r8
  _WORD *v8; // r9
  unsigned int ContainerDataPerKeyType; // ebx

  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  v7 = *(_QWORD *)(a2 + 128);
  *a3 = 0;
  if ( v7 && (v8 = *(_WORD **)(a2 + 96)) != 0 )
  {
    ContainerDataPerKeyType = I_ReaderListReadContainerDataPerKeyType(a1, a2, v7, v8, 1u);
    if ( !ContainerDataPerKeyType )
      ++*a3;
  }
  else
  {
    ContainerDataPerKeyType = -2146893802;
  }
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      93,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      ContainerDataPerKeyType);
  }
  return ContainerDataPerKeyType;
}

```

## disassembly

```asm
0x180020ff8  push    rbx
0x180020ffa  push    rsi
0x180020ffb  push    rdi
0x180020ffc  push    r14
0x180020ffe  sub     rsp, 38h
0x180021002  mov     rbx, rdx
0x180021005  mov     rdi, r8
0x180021008  xor     edx, edx
0x18002100a  mov     rsi, rcx
0x18002100d  call    WppTraceIndent
0x180021012  mov     rcx, cs:WPP_GLOBAL_Control
0x180021019  lea     r14, WPP_GLOBAL_Control
0x180021020  cmp     rcx, r14
0x180021023  jz      short loc_18002104D
0x180021025  test    byte ptr [rcx+1Ch], 2
0x180021029  jz      short loc_18002104D
0x18002102b  cmp     byte ptr [rcx+19h], 5
0x18002102f  jb      short loc_18002104D
0x180021031  mov     r9, cs:WPP_pszIndent
0x180021038  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18002103f  mov     rcx, [rcx+10h]
0x180021043  mov     edx, 5Ch ; '\'
0x180021048  call    WPP_SF_s
0x18002104d  mov     r8, [rbx+80h]
0x180021054  mov     dword ptr [rdi], 0
0x18002105a  test    r8, r8
0x18002105d  jz      short loc_180021085
0x18002105f  mov     r9, [rbx+60h]
0x180021063  test    r9, r9
0x180021066  jz      short loc_180021085
0x180021068  mov     rdx, rbx
0x18002106b  mov     [rsp+58h+var_38], 1
0x180021073  mov     rcx, rsi
0x180021076  call    I_ReaderListReadContainerDataPerKeyType
0x18002107b  mov     ebx, eax
0x18002107d  test    eax, eax
0x18002107f  jnz     short loc_18002108A
0x180021081  inc     dword ptr [rdi]
0x180021083  jmp     short loc_18002108A
0x180021085  mov     ebx, 80090016h
0x18002108a  mov     edx, 1
0x18002108f  call    WppTraceIndent
0x180021094  mov     rcx, cs:WPP_GLOBAL_Control
0x18002109b  cmp     rcx, r14
0x18002109e  jz      short loc_1800210CC
0x1800210a0  test    byte ptr [rcx+1Ch], 2
0x1800210a4  jz      short loc_1800210CC
0x1800210a6  cmp     byte ptr [rcx+19h], 5
0x1800210aa  jb      short loc_1800210CC
0x1800210ac  mov     r9, cs:WPP_pszIndent
0x1800210b3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800210ba  mov     rcx, [rcx+10h]
0x1800210be  mov     edx, 5Dh ; ']'
0x1800210c3  mov     [rsp+58h+var_38], ebx
0x1800210c7  call    WPP_SF_sD
0x1800210cc  mov     eax, ebx
0x1800210ce  add     rsp, 38h
0x1800210d2  pop     r14
0x1800210d4  pop     rdi
0x1800210d5  pop     rsi
0x1800210d6  pop     rbx
0x1800210d7  retn
```
