# EapSetCachedUIResponse

- ea: `0x180019d28`
- end: `0x180019dfc`
- name: `EapSetCachedUIResponse`
- size: `212`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180024620`
- `0x180024860`
- `0x180024c40`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180019d28`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x180019d8a`
- `MobileNetworking!SetBufferAndLength` at `0x180019d8a`

## pseudocode

```c
__int64 __fastcall EapSetCachedUIResponse(__int64 a1, unsigned int *a2)
{
  unsigned int v4; // esi
  __int64 v5; // r9
  unsigned int *v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx

  v4 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  if ( a2 )
  {
    v5 = *a2;
    v6 = a2;
  }
  else
  {
    v5 = 0;
    v6 = 0;
  }
  v7 = SetBufferAndLength(a1 + 144, 0, v6, v5);
  v8 = v7;
  if ( !v7 )
    goto LABEL_11;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v4, v7);
LABEL_11:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 33, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x180019d28  push    rbx
0x180019d2a  push    rbp
0x180019d2b  push    rsi
0x180019d2c  push    rdi
0x180019d2d  sub     rsp, 38h
0x180019d31  mov     rax, [rcx]
0x180019d34  mov     rbx, rdx
0x180019d37  mov     rdi, rcx
0x180019d3a  mov     esi, [rax+14h]
0x180019d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d44  lea     rbp, WPP_GLOBAL_Control
0x180019d4b  cmp     rcx, rbp
0x180019d4e  jz      short loc_180019D6E
0x180019d50  test    dword ptr [rcx+44h], 800h
0x180019d57  jz      short loc_180019D6E
0x180019d59  mov     rcx, [rcx+38h]
0x180019d5d  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180019d64  mov     edx, 1Fh
0x180019d69  call    WPP_SF_
0x180019d6e  xor     edx, edx
0x180019d70  lea     rcx, [rdi+90h]
0x180019d77  test    rbx, rbx
0x180019d7a  jnz     short loc_180019D84
0x180019d7c  xor     r9d, r9d
0x180019d7f  xor     r8d, r8d
0x180019d82  jmp     short loc_180019D8A
0x180019d84  mov     r9d, [rbx]
0x180019d87  mov     r8, rbx
0x180019d8a  call    cs:__imp_SetBufferAndLength
0x180019d90  mov     ebx, eax
0x180019d92  test    eax, eax
0x180019d94  jz      short loc_180019DC4
0x180019d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d9d  cmp     rcx, rbp
0x180019da0  jz      short loc_180019DF1
0x180019da2  test    byte ptr [rcx+44h], 1
0x180019da6  jz      short loc_180019DCB
0x180019da8  mov     rcx, [rcx+38h]
0x180019dac  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180019db3  mov     edx, 20h ; ' '
0x180019db8  mov     [rsp+58h+var_38], eax
0x180019dbc  mov     r9d, esi
0x180019dbf  call    WPP_SF_dd
0x180019dc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dcb  cmp     rcx, rbp
0x180019dce  jz      short loc_180019DF1
0x180019dd0  test    dword ptr [rcx+44h], 800h
0x180019dd7  jz      short loc_180019DF1
0x180019dd9  mov     rcx, [rcx+38h]
0x180019ddd  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180019de4  mov     edx, 21h ; '!'
0x180019de9  mov     r9d, ebx
0x180019dec  call    WPP_SF_D
0x180019df1  mov     eax, ebx
0x180019df3  add     rsp, 38h
0x180019df7  pop     rdi
0x180019df8  pop     rsi
0x180019df9  pop     rbp
0x180019dfa  pop     rbx
0x180019dfb  retn
```
