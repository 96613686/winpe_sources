# CompactMaxpLocaTable

- ea: `0x1800075f4`
- end: `0x1800077fa`
- name: `CompactMaxpLocaTable`
- size: `518`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007fa4`

## callees

- `0x1800075f4`
- `0x18000e214`
- `0x180011538`
- `0x180011574`
- `0x180019a40`
- `0x180019ec0`
- `0x18001a808`
- `0x18001aa68`
- `0x18001aadc`
- `0x18001ac90`

## pseudocode

```c
__int16 __fastcall CompactMaxpLocaTable(_QWORD *a1, __int64 a2, unsigned __int16 a3, unsigned __int16 a4)
{
  int v4; // edi
  unsigned __int16 v5; // si
  int v6; // r12d
  __int16 result; // ax
  __int64 v9; // rax
  __int64 v10; // r15
  int Loca; // r13d
  unsigned __int16 v12; // bx
  __int64 v13; // rdx
  unsigned int v14; // ebx
  __int64 v15; // rdx
  unsigned int Generic; // eax
  __int16 v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h]
  _OWORD v19[2]; // [rsp+40h] [rbp-39h] BYREF
  _OWORD v20[3]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v21; // [rsp+90h] [rbp+17h]

  v4 = a4;
  v5 = 0;
  v6 = a3;
  result = 0;
  v18 = a2;
  v17 = 0;
  v21 = 0;
  memset(v19, 0, sizeof(v19));
  memset(v20, 0, sizeof(v20));
  if ( !a4 )
    return result;
  if ( !(unsigned int)GetGeneric(a1, v20, 0) )
    return 1032;
  v9 = Mem_Alloc(4LL * (unsigned int)(v6 + 1));
  v10 = v9;
  if ( !v9 )
    return 1005;
  Loca = GetLoca(a1, v9, (unsigned int)(v6 + 1));
  if ( !Loca )
  {
    Mem_Free(v10);
    return 1035;
  }
  v12 = 0;
  if ( WORD1(v21) )
  {
    while ( 1 )
    {
      if ( v5 > (unsigned __int16)v4 )
      {
LABEL_28:
        v14 = 4 * v4 + 4;
        goto LABEL_29;
      }
      if ( v5 == (_WORD)v4 )
        break;
      if ( v12 < (unsigned __int16)v6 )
      {
        v15 = v12;
        if ( *(_BYTE *)(v12 + v18) )
          goto LABEL_25;
      }
LABEL_27:
      if ( ++v12 > (unsigned __int16)v6 )
        goto LABEL_28;
    }
    v15 = v12;
LABEL_25:
    if ( (unsigned __int16)WriteLong(a1, *(unsigned int *)(v10 + 4 * v15), Loca + 4 * (unsigned int)v5) )
      goto LABEL_28;
    ++v5;
    goto LABEL_27;
  }
  while ( v5 <= (unsigned __int16)v4 )
  {
    if ( v5 == (_WORD)v4 )
    {
      v13 = v12;
LABEL_15:
      if ( (unsigned __int16)WriteWord(a1, *(_DWORD *)(v10 + 4 * v13) >> 1, Loca + 2 * (unsigned int)v5) )
        break;
      ++v5;
      goto LABEL_17;
    }
    if ( v12 < (unsigned __int16)v6 )
    {
      v13 = v12;
      if ( *(_BYTE *)(v12 + v18) )
        goto LABEL_15;
    }
LABEL_17:
    if ( ++v12 > (unsigned __int16)v6 )
      break;
  }
  v14 = 2 * v4 + 2;
LABEL_29:
  Mem_Free(v10);
  result = UpdateDirEntry((__int64)a1, (__int64)"loca", v14);
  if ( !result )
  {
    Generic = GetGeneric(a1, v19, 3);
    if ( Generic )
    {
      WORD2(v19[0]) = v4;
      return WriteGeneric((__int64)a1, (__int64)v19, 0x20u, (unsigned __int8 *)MAXP_CONTROL, Generic, &v17);
    }
    else
    {
      return 1036;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800075f4  mov     [rsp-8+arg_8], rbx
0x1800075f9  push    rbp
0x1800075fa  push    rsi
0x1800075fb  push    rdi
0x1800075fc  push    r12
0x1800075fe  push    r13
0x180007600  push    r14
0x180007602  push    r15
0x180007604  lea     rbp, [rsp-27h]
0x180007609  sub     rsp, 0A0h
0x180007610  mov     rax, cs:__security_cookie
0x180007617  xor     rax, rsp
0x18000761a  mov     [rbp+57h+var_38], rax
0x18000761e  xorps   xmm1, xmm1
0x180007621  movzx   edi, r9w
0x180007625  xor     esi, esi
0x180007627  movzx   r12d, r8w
0x18000762b  xor     eax, eax
0x18000762d  mov     [rbp+57h+var_98], rdx
0x180007631  mov     [rbp+57h+var_A0], si
0x180007635  xorps   xmm0, xmm0
0x180007638  mov     [rbp+57h+var_40], rax
0x18000763c  mov     r14, rcx
0x18000763f  movups  [rbp+57h+var_90], xmm0
0x180007643  movups  [rbp+57h+var_80], xmm0
0x180007647  movups  [rbp+57h+var_70], xmm1
0x18000764b  movups  [rbp+57h+var_60], xmm1
0x18000764f  movups  [rbp+57h+var_50], xmm1
0x180007653  test    di, di
0x180007656  jz      loc_1800077D3
0x18000765c  xor     r8d, r8d
0x18000765f  lea     rdx, [rbp+57h+var_70]
0x180007663  call    GetGeneric
0x180007668  test    eax, eax
0x18000766a  jnz     short loc_180007676
0x18000766c  mov     eax, 408h
0x180007671  jmp     loc_1800077D3
0x180007676  lea     ebx, [r12+1]
0x18000767b  mov     ecx, ebx
0x18000767d  shl     rcx, 2; Size
0x180007681  call    Mem_Alloc
0x180007686  mov     r15, rax
0x180007689  test    rax, rax
0x18000768c  jnz     short loc_180007698
0x18000768e  mov     eax, 3EDh
0x180007693  jmp     loc_1800077D3
0x180007698  mov     r8d, ebx
0x18000769b  mov     rdx, r15
0x18000769e  mov     rcx, r14
0x1800076a1  call    GetLoca
0x1800076a6  mov     r13d, eax
0x1800076a9  test    eax, eax
0x1800076ab  jnz     short loc_1800076BF
0x1800076ad  mov     rcx, r15
0x1800076b0  call    Mem_Free
0x1800076b5  mov     eax, 40Bh
0x1800076ba  jmp     loc_1800077D3
0x1800076bf  mov     ebx, esi
0x1800076c1  cmp     word ptr [rbp+57h+var_40+2], si
0x1800076c5  jnz     short loc_18000771C
0x1800076c7  cmp     si, di
0x1800076ca  ja      short loc_180007713
0x1800076cc  jz      short loc_1800076E3
0x1800076ce  cmp     bx, r12w
0x1800076d2  jnb     short loc_18000770A
0x1800076d4  mov     rax, [rbp+57h+var_98]
0x1800076d8  movzx   edx, bx
0x1800076db  cmp     byte ptr [rdx+rax], 0
0x1800076df  jz      short loc_18000770A
0x1800076e1  jmp     short loc_1800076E6
0x1800076e3  movzx   edx, bx
0x1800076e6  mov     edx, [r15+rdx*4]
0x1800076ea  mov     rcx, r14
0x1800076ed  movzx   eax, si
0x1800076f0  shr     edx, 1
0x1800076f2  lea     r8d, ds:0[rax*2]
0x1800076fa  add     r8d, r13d
0x1800076fd  call    WriteWord
0x180007702  test    ax, ax
0x180007705  jnz     short loc_180007713
0x180007707  inc     si
0x18000770a  inc     bx
0x18000770d  cmp     bx, r12w
0x180007711  jbe     short loc_1800076C7
0x180007713  lea     ebx, ds:2[rdi*2]
0x18000771a  jmp     short loc_18000776D
0x18000771c  cmp     si, di
0x18000771f  ja      short loc_180007766
0x180007721  jz      short loc_180007738
0x180007723  cmp     bx, r12w
0x180007727  jnb     short loc_18000775D
0x180007729  mov     rax, [rbp+57h+var_98]
0x18000772d  movzx   edx, bx
0x180007730  cmp     byte ptr [rdx+rax], 0
0x180007734  jz      short loc_18000775D
0x180007736  jmp     short loc_18000773B
0x180007738  movzx   edx, bx
0x18000773b  mov     edx, [r15+rdx*4]
0x18000773f  mov     rcx, r14
0x180007742  movzx   eax, si
0x180007745  lea     r8d, ds:0[rax*4]
0x18000774d  add     r8d, r13d
0x180007750  call    WriteLong
0x180007755  test    ax, ax
0x180007758  jnz     short loc_180007766
0x18000775a  inc     si
0x18000775d  inc     bx
0x180007760  cmp     bx, r12w
0x180007764  jbe     short loc_18000771C
0x180007766  lea     ebx, ds:4[rdi*4]
0x18000776d  mov     rcx, r15
0x180007770  call    Mem_Free
0x180007775  mov     r8d, ebx
0x180007778  lea     rdx, aLoca; "loca"
0x18000777f  mov     rcx, r14
0x180007782  call    UpdateDirEntry
0x180007787  test    ax, ax
0x18000778a  jnz     short loc_1800077D3
0x18000778c  mov     r8d, 3
0x180007792  lea     rdx, [rbp+57h+var_90]
0x180007796  mov     rcx, r14
0x180007799  call    GetGeneric
0x18000779e  test    eax, eax
0x1800077a0  jnz     short loc_1800077A9
0x1800077a2  mov     eax, 40Ch
0x1800077a7  jmp     short loc_1800077D3
0x1800077a9  lea     rcx, [rbp+57h+var_A0]
0x1800077ad  mov     word ptr [rbp+57h+var_90+4], di
0x1800077b1  mov     [rsp+0D0h+var_A8], rcx
0x1800077b6  lea     r9, MAXP_CONTROL
0x1800077bd  mov     rcx, r14
0x1800077c0  mov     [rsp+0D0h+var_B0], eax
0x1800077c4  mov     r8d, 20h ; ' '
0x1800077ca  lea     rdx, [rbp+57h+var_90]
0x1800077ce  call    WriteGeneric
0x1800077d3  mov     rcx, [rbp+57h+var_38]
0x1800077d7  xor     rcx, rsp; StackCookie
0x1800077da  call    __security_check_cookie
0x1800077df  mov     rbx, [rsp+0D0h+arg_8]
0x1800077e7  add     rsp, 0A0h
0x1800077ee  pop     r15
0x1800077f0  pop     r14
0x1800077f2  pop     r13
0x1800077f4  pop     r12
0x1800077f6  pop     rdi
0x1800077f7  pop     rsi
0x1800077f8  pop     rbp
0x1800077f9  retn
```
