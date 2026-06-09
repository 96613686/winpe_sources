# EapDeleteMasterUserData

- ea: `0x180009060`
- end: `0x1800091bd`
- name: `EapDeleteMasterUserData`
- size: `349`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800084a0`
- `0x180009be0`
- `0x180024860`

## callees

- `0x180005440`
- `0x180007f60`
- `0x180009060`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!SetBufferAndLength` at `0x1800090e8`
- `MobileNetworking!SetBufferAndLength` at `0x1800090e8`

## pseudocode

```c
__int64 __fastcall EapDeleteMasterUserData(__int64 *a1)
{
  __int64 v1; // rbx
  unsigned int v2; // esi
  _QWORD *v3; // rcx
  unsigned int v4; // edi
  unsigned int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx

  v1 = *a1;
  v2 = *(_DWORD *)(*a1 + 20);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids);
    v3 = WPP_GLOBAL_Control;
  }
  v4 = *(_DWORD *)(*(_QWORD *)(v1 + 2384) + 20LL);
  if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 17) & 0x800) != 0 )
    WPP_SF_(v3[7], 40, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids);
  v5 = SetBufferAndLength(v1 + 2760, v1 + 2752, 0, 0);
  v6 = v5;
  if ( !v5 )
    goto LABEL_11;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 41, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v4, v5);
LABEL_11:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
  {
    WPP_SF_D(v7[7], 42, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids, v6);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    if ( v7 == &WPP_GLOBAL_Control )
      return v6;
    if ( (*((_BYTE *)v7 + 68) & 1) != 0 )
    {
      WPP_SF_dd(v7[7], 45, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v2, v6);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 46, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x180009060  push    rbx
0x180009062  push    rbp
0x180009063  push    rsi
0x180009064  push    rdi
0x180009065  sub     rsp, 38h
0x180009069  mov     rbx, [rcx]
0x18000906c  mov     esi, [rbx+14h]
0x18000906f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009076  lea     rbp, WPP_GLOBAL_Control
0x18000907d  cmp     rcx, rbp
0x180009080  jz      short loc_1800090A7
0x180009082  test    dword ptr [rcx+44h], 800h
0x180009089  jz      short loc_1800090A7
0x18000908b  mov     rcx, [rcx+38h]
0x18000908f  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009096  mov     edx, 2Ch ; ','
0x18000909b  call    WPP_SF_
0x1800090a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a7  mov     rax, [rbx+950h]
0x1800090ae  mov     edi, [rax+14h]
0x1800090b1  cmp     rcx, rbp
0x1800090b4  jz      short loc_1800090D4
0x1800090b6  test    dword ptr [rcx+44h], 800h
0x1800090bd  jz      short loc_1800090D4
0x1800090bf  mov     rcx, [rcx+38h]
0x1800090c3  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x1800090ca  mov     edx, 28h ; '('
0x1800090cf  call    WPP_SF_
0x1800090d4  lea     rdx, [rbx+0AC0h]
0x1800090db  xor     r9d, r9d
0x1800090de  lea     rcx, [rbx+0AC8h]
0x1800090e5  xor     r8d, r8d
0x1800090e8  call    cs:__imp_SetBufferAndLength
0x1800090ee  mov     ebx, eax
0x1800090f0  test    eax, eax
0x1800090f2  jz      short loc_180009126
0x1800090f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090fb  cmp     rcx, rbp
0x1800090fe  jz      loc_1800091B2
0x180009104  test    byte ptr [rcx+44h], 1
0x180009108  jz      short loc_18000912D
0x18000910a  mov     rcx, [rcx+38h]
0x18000910e  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180009115  mov     edx, 29h ; ')'
0x18000911a  mov     [rsp+58h+var_38], eax
0x18000911e  mov     r9d, edi
0x180009121  call    WPP_SF_dd
0x180009126  mov     rcx, cs:WPP_GLOBAL_Control
0x18000912d  cmp     rcx, rbp
0x180009130  jz      short loc_18000915A
0x180009132  test    dword ptr [rcx+44h], 800h
0x180009139  jz      short loc_18000915A
0x18000913b  mov     rcx, [rcx+38h]
0x18000913f  lea     r8, WPP_5aa9b725e40135a9c26f3f5270650131_Traceguids
0x180009146  mov     edx, 2Ah ; '*'
0x18000914b  mov     r9d, ebx
0x18000914e  call    WPP_SF_D
0x180009153  mov     rcx, cs:WPP_GLOBAL_Control
0x18000915a  test    ebx, ebx
0x18000915c  jz      short loc_18000918C
0x18000915e  cmp     rcx, rbp
0x180009161  jz      short loc_1800091B2
0x180009163  test    byte ptr [rcx+44h], 1
0x180009167  jz      short loc_18000918C
0x180009169  mov     rcx, [rcx+38h]
0x18000916d  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x180009174  mov     edx, 2Dh ; '-'
0x180009179  mov     [rsp+58h+var_38], ebx
0x18000917d  mov     r9d, esi
0x180009180  call    WPP_SF_dd
0x180009185  mov     rcx, cs:WPP_GLOBAL_Control
0x18000918c  cmp     rcx, rbp
0x18000918f  jz      short loc_1800091B2
0x180009191  test    dword ptr [rcx+44h], 800h
0x180009198  jz      short loc_1800091B2
0x18000919a  mov     rcx, [rcx+38h]
0x18000919e  lea     r8, WPP_7a334571dc123d156aa3af8aa642e608_Traceguids
0x1800091a5  mov     edx, 2Eh ; '.'
0x1800091aa  mov     r9d, ebx
0x1800091ad  call    WPP_SF_D
0x1800091b2  mov     eax, ebx
0x1800091b4  add     rsp, 38h
0x1800091b8  pop     rdi
0x1800091b9  pop     rsi
0x1800091ba  pop     rbp
0x1800091bb  pop     rbx
0x1800091bc  retn
```
