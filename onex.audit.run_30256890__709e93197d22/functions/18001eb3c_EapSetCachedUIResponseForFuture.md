# EapSetCachedUIResponseForFuture

- ea: `0x18001eb3c`
- end: `0x18001ec10`
- name: `EapSetCachedUIResponseForFuture`
- size: `212`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180024860`
- `0x180024c40`
- `0x180026194`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18001eb3c`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18001eb9e`
- `MobileNetworking!SetBufferAndLength` at `0x18001eb9e`

## pseudocode

```c
__int64 __fastcall EapSetCachedUIResponseForFuture(__int64 a1, unsigned int *a2)
{
  unsigned int v4; // esi
  __int64 v5; // r9
  unsigned int *v6; // r8
  unsigned int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rcx

  v4 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 34, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
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
  v7 = SetBufferAndLength(a1 + 152, 0, v6, v5);
  v8 = v7;
  if ( !v7 )
    goto LABEL_11;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 35, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v4, v7);
LABEL_11:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 17) & 0x800) != 0 )
    WPP_SF_D(v9[7], 36, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18001eb3c  push    rbx
0x18001eb3e  push    rbp
0x18001eb3f  push    rsi
0x18001eb40  push    rdi
0x18001eb41  sub     rsp, 38h
0x18001eb45  mov     rax, [rcx]
0x18001eb48  mov     rbx, rdx
0x18001eb4b  mov     rdi, rcx
0x18001eb4e  mov     esi, [rax+14h]
0x18001eb51  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb58  lea     rbp, WPP_GLOBAL_Control
0x18001eb5f  cmp     rcx, rbp
0x18001eb62  jz      short loc_18001EB82
0x18001eb64  test    dword ptr [rcx+44h], 800h
0x18001eb6b  jz      short loc_18001EB82
0x18001eb6d  mov     rcx, [rcx+38h]
0x18001eb71  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001eb78  mov     edx, 22h ; '"'
0x18001eb7d  call    WPP_SF_
0x18001eb82  xor     edx, edx
0x18001eb84  lea     rcx, [rdi+98h]
0x18001eb8b  test    rbx, rbx
0x18001eb8e  jnz     short loc_18001EB98
0x18001eb90  xor     r9d, r9d
0x18001eb93  xor     r8d, r8d
0x18001eb96  jmp     short loc_18001EB9E
0x18001eb98  mov     r9d, [rbx]
0x18001eb9b  mov     r8, rbx
0x18001eb9e  call    cs:__imp_SetBufferAndLength
0x18001eba4  mov     ebx, eax
0x18001eba6  test    eax, eax
0x18001eba8  jz      short loc_18001EBD8
0x18001ebaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebb1  cmp     rcx, rbp
0x18001ebb4  jz      short loc_18001EC05
0x18001ebb6  test    byte ptr [rcx+44h], 1
0x18001ebba  jz      short loc_18001EBDF
0x18001ebbc  mov     rcx, [rcx+38h]
0x18001ebc0  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001ebc7  mov     edx, 23h ; '#'
0x18001ebcc  mov     [rsp+58h+var_38], eax
0x18001ebd0  mov     r9d, esi
0x18001ebd3  call    WPP_SF_dd
0x18001ebd8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebdf  cmp     rcx, rbp
0x18001ebe2  jz      short loc_18001EC05
0x18001ebe4  test    dword ptr [rcx+44h], 800h
0x18001ebeb  jz      short loc_18001EC05
0x18001ebed  mov     rcx, [rcx+38h]
0x18001ebf1  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001ebf8  mov     edx, 24h ; '$'
0x18001ebfd  mov     r9d, ebx
0x18001ec00  call    WPP_SF_D
0x18001ec05  mov     eax, ebx
0x18001ec07  add     rsp, 38h
0x18001ec0b  pop     rdi
0x18001ec0c  pop     rsi
0x18001ec0d  pop     rbp
0x18001ec0e  pop     rbx
0x18001ec0f  retn
```
