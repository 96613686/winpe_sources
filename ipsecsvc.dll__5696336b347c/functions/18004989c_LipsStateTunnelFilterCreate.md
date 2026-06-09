# LipsStateTunnelFilterCreate

- ea: `0x18004989c`
- end: `0x1800499dc`
- name: `LipsStateTunnelFilterCreate`
- size: `320`
- prototype: `__int64 __fastcall(unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180049008`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x18004989c`
- `0x180049cb8`

## string_xrefs

- `0x1800499bd`: `LipsStateTunnelFilterCreate`

## pseudocode

```c
__int64 __fastcall LipsStateTunnelFilterCreate(unsigned int a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // rsi
  __int64 i; // rdi
  LPVOID v11; // rax
  _QWORD *v13; // [rsp+58h] [rbp+10h] BYREF
  SIZE_T v14; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  v14 = 0;
  v13 = 0;
  v4 = NsuSizeTMultiply(a1, 8, &v14);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_19;
    v7 = 33;
    v8 = v4;
    goto LABEL_5;
  }
  v13 = IpsecAllocMem(v14);
  v9 = v13;
  if ( !v13 )
  {
    v5 = 8;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_19;
    v7 = 34;
LABEL_10:
    v8 = 8;
LABEL_5:
    WPP_SF_d(v6[2], v7, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids, v8);
    goto LABEL_19;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a1 )
    {
      *a2 = v9;
      v13 = 0;
      goto LABEL_19;
    }
    v11 = IpsecAllocMem(0x44u);
    v9[i] = v11;
    if ( !v11 )
      break;
  }
  v5 = 8;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = 35;
    goto LABEL_10;
  }
LABEL_19:
  LipsStateTunnelFilterDestroy(a1, &v13);
  if ( v5 )
    return LipsReportError(v5, (int)"LipsStateTunnelFilterCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004989c  mov     rax, rsp
0x18004989f  mov     [rax+8], rbx
0x1800498a3  push    rbp
0x1800498a4  push    rsi
0x1800498a5  push    rdi
0x1800498a6  push    r12
0x1800498a8  push    r14
0x1800498aa  sub     rsp, 20h
0x1800498ae  mov     r14, rdx
0x1800498b1  mov     qword ptr [rdx], 0
0x1800498b8  mov     r12d, 8
0x1800498be  mov     ebp, ecx
0x1800498c0  mov     edx, r12d
0x1800498c3  mov     ecx, ecx
0x1800498c5  lea     r8, [rax+18h]
0x1800498c9  mov     qword ptr [rax+18h], 0
0x1800498d1  mov     qword ptr [rax+10h], 0
0x1800498d9  call    NsuSizeTMultiply
0x1800498de  mov     ebx, eax
0x1800498e0  test    eax, eax
0x1800498e2  jz      short loc_180049922
0x1800498e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800498eb  lea     rdx, WPP_GLOBAL_Control
0x1800498f2  cmp     rcx, rdx
0x1800498f5  jz      loc_1800499A9
0x1800498fb  test    byte ptr [rcx+1Ch], 10h
0x1800498ff  jz      loc_1800499A9
0x180049905  lea     edx, [r12+19h]
0x18004990a  mov     r9d, eax
0x18004990d  mov     rcx, [rcx+10h]
0x180049911  lea     r8, WPP_4259805821ae3eb6062dce0997567f8e_Traceguids
0x180049918  call    WPP_SF_d
0x18004991d  jmp     loc_1800499A9
0x180049922  mov     rcx, [rsp+48h+arg_10]
0x180049927  call    IpsecAllocMem
0x18004992c  mov     [rsp+48h+arg_8], rax
0x180049931  mov     rsi, rax
0x180049934  test    rax, rax
0x180049937  jnz     short loc_18004995D
0x180049939  mov     ebx, r12d
0x18004993c  mov     rcx, cs:WPP_GLOBAL_Control
0x180049943  lea     rdx, WPP_GLOBAL_Control
0x18004994a  cmp     rcx, rdx
0x18004994d  jz      short loc_1800499A9
0x18004994f  test    byte ptr [rcx+1Ch], 10h
0x180049953  jz      short loc_1800499A9
0x180049955  lea     edx, [rax+22h]
0x180049958  mov     r9d, r12d
0x18004995b  jmp     short loc_18004990D
0x18004995d  xor     edi, edi
0x18004995f  cmp     edi, ebp
0x180049961  jnb     short loc_18004999D
0x180049963  mov     ecx, 44h ; 'D'
0x180049968  call    IpsecAllocMem
0x18004996d  mov     [rsi+rdi*8], rax
0x180049971  test    rax, rax
0x180049974  jz      short loc_18004997A
0x180049976  inc     edi
0x180049978  jmp     short loc_18004995F
0x18004997a  mov     ebx, r12d
0x18004997d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049984  lea     rdx, WPP_GLOBAL_Control
0x18004998b  cmp     rcx, rdx
0x18004998e  jz      short loc_1800499A9
0x180049990  test    byte ptr [rcx+1Ch], 10h
0x180049994  jz      short loc_1800499A9
0x180049996  mov     edx, 23h ; '#'
0x18004999b  jmp     short loc_180049958
0x18004999d  mov     [r14], rsi
0x1800499a0  mov     [rsp+48h+arg_8], 0
0x1800499a9  lea     rdx, [rsp+48h+arg_8]
0x1800499ae  mov     ecx, ebp
0x1800499b0  call    LipsStateTunnelFilterDestroy
0x1800499b5  test    ebx, ebx
0x1800499b7  jnz     short loc_1800499BD
0x1800499b9  xor     eax, eax
0x1800499bb  jmp     short loc_1800499CB
0x1800499bd  lea     rdx, aLipsstatetunne_4; "LipsStateTunnelFilterCreate"
0x1800499c4  mov     ecx, ebx
0x1800499c6  call    LipsReportError
0x1800499cb  mov     rbx, [rsp+48h+arg_0]
0x1800499d0  add     rsp, 20h
0x1800499d4  pop     r14
0x1800499d6  pop     r12
0x1800499d8  pop     rdi
0x1800499d9  pop     rsi
0x1800499da  pop     rbp
0x1800499db  retn
```
