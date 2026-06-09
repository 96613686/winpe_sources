# EapSetCachedUIRequest

- ea: `0x18001a5dc`
- end: `0x18001a6c6`
- name: `EapSetCachedUIRequest`
- size: `234`
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
- `0x18001a5dc`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x18001a63b`
- `MobileNetworking!SetBufferAndLength` at `0x18001a64c`
- `MobileNetworking!SetBufferAndLength` at `0x18001a63b`
- `MobileNetworking!SetBufferAndLength` at `0x18001a64c`

## pseudocode

```c
__int64 __fastcall EapSetCachedUIRequest(_DWORD *a1, unsigned int *a2, int a3)
{
  unsigned int v6; // ebp
  _DWORD *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  _QWORD *v10; // rcx

  v6 = *(_DWORD *)(*(_QWORD *)a1 + 20LL);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
  v7 = a1 + 34;
  if ( a2 )
  {
    v8 = SetBufferAndLength(v7, 0, a2, *a2);
  }
  else
  {
    v8 = SetBufferAndLength(v7, 0, 0, 0);
    a3 = -1;
  }
  a1[32] = a3;
  v9 = v8;
  if ( !v8 )
    goto LABEL_11;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v9;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6, v8);
LABEL_11:
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 17) & 0x800) != 0 )
    WPP_SF_D(v10[7], 30, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18001a5dc  push    rbx
0x18001a5de  push    rbp
0x18001a5df  push    rsi
0x18001a5e0  push    rdi
0x18001a5e1  push    r14
0x18001a5e3  sub     rsp, 30h
0x18001a5e7  mov     rax, [rcx]
0x18001a5ea  mov     esi, r8d
0x18001a5ed  mov     rbx, rdx
0x18001a5f0  mov     rdi, rcx
0x18001a5f3  mov     ebp, [rax+14h]
0x18001a5f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5fd  lea     r14, WPP_GLOBAL_Control
0x18001a604  cmp     rcx, r14
0x18001a607  jz      short loc_18001A627
0x18001a609  test    dword ptr [rcx+44h], 800h
0x18001a610  jz      short loc_18001A627
0x18001a612  mov     rcx, [rcx+38h]
0x18001a616  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001a61d  mov     edx, 1Ch
0x18001a622  call    WPP_SF_
0x18001a627  xor     edx, edx
0x18001a629  lea     rcx, [rdi+88h]
0x18001a630  test    rbx, rbx
0x18001a633  jnz     short loc_18001A646
0x18001a635  xor     r9d, r9d
0x18001a638  xor     r8d, r8d
0x18001a63b  call    cs:__imp_SetBufferAndLength
0x18001a641  or      esi, 0FFFFFFFFh
0x18001a644  jmp     short loc_18001A652
0x18001a646  mov     r9d, [rbx]
0x18001a649  mov     r8, rbx
0x18001a64c  call    cs:__imp_SetBufferAndLength
0x18001a652  mov     [rdi+80h], esi
0x18001a658  mov     ebx, eax
0x18001a65a  test    eax, eax
0x18001a65c  jz      short loc_18001A68C
0x18001a65e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a665  cmp     rcx, r14
0x18001a668  jz      short loc_18001A6B9
0x18001a66a  test    byte ptr [rcx+44h], 1
0x18001a66e  jz      short loc_18001A693
0x18001a670  mov     rcx, [rcx+38h]
0x18001a674  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001a67b  mov     edx, 1Dh
0x18001a680  mov     [rsp+58h+var_38], eax
0x18001a684  mov     r9d, ebp
0x18001a687  call    WPP_SF_dd
0x18001a68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a693  cmp     rcx, r14
0x18001a696  jz      short loc_18001A6B9
0x18001a698  test    dword ptr [rcx+44h], 800h
0x18001a69f  jz      short loc_18001A6B9
0x18001a6a1  mov     rcx, [rcx+38h]
0x18001a6a5  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x18001a6ac  mov     edx, 1Eh
0x18001a6b1  mov     r9d, ebx
0x18001a6b4  call    WPP_SF_D
0x18001a6b9  mov     eax, ebx
0x18001a6bb  add     rsp, 30h
0x18001a6bf  pop     r14
0x18001a6c1  pop     rdi
0x18001a6c2  pop     rsi
0x18001a6c3  pop     rbp
0x18001a6c4  pop     rbx
0x18001a6c5  retn
```
