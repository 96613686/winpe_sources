# CIPropertyStorageWrapper::CreateNewPropNodeWithName(ushort const *)

- ea: `0x1800110a8`
- end: `0x18001124d`
- name: `?CreateNewPropNodeWithName@CIPropertyStorageWrapper@@QEAAPEAU_propertyNodeDef@@PEBG@Z`
- size: `421`
- prototype: `struct _propertyNodeDef *__fastcall(CIPropertyStorageWrapper *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180011d00`

## callees

- `0x180001144`
- `0x18000115c`
- `0x18000119c`
- `0x180007bd4`
- `0x1800110a8`

## pseudocode

```c
struct _propertyNodeDef *__fastcall CIPropertyStorageWrapper::CreateNewPropNodeWithName(
        CIPropertyStorageWrapper *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // r14
  __int64 v3; // rsi
  _OWORD *v5; // rax
  _OWORD *v6; // rbx
  unsigned __int64 v7; // rsi
  void *v8; // rax
  __int64 *v9; // r8
  unsigned int v10; // ecx
  __int64 *i; // rax
  int v12; // edx
  _WORD *v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rax
  _WORD *v16; // rcx

  v2 = a2;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( !v3 )
    return 0;
  v5 = operator new(0x30u);
  v6 = v5;
  if ( !v5 )
    return 0;
  v7 = v3 + 1;
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  v8 = operator new[](saturated_mul(v7, 2u));
  *((_QWORD *)v6 + 3) = v8;
  if ( !v8 )
  {
LABEL_32:
    operator delete(v6);
    return 0;
  }
  *((_DWORD *)v6 + 4) = 0;
  v9 = (__int64 *)*((_QWORD *)this + 2);
  v10 = *((_DWORD *)this + 8);
  while ( 1 )
  {
    for ( i = v9; i; i = (__int64 *)*i )
    {
      if ( *((_DWORD *)i + 5) == v10 )
        break;
    }
    v12 = *((_DWORD *)this + 8);
    v10 = v12 + 1;
    *((_DWORD *)this + 8) = v12 + 1;
    if ( !i )
      break;
    if ( v10 >= 0x80000000 )
      goto LABEL_31;
  }
  *((_DWORD *)v6 + 5) = v12;
  v13 = (_WORD *)*((_QWORD *)v6 + 3);
  if ( !v7 )
  {
    v14 = 2147942487LL;
LABEL_28:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 11, WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids, v14);
LABEL_31:
    operator delete(*((void **)v6 + 3));
    goto LABEL_32;
  }
  if ( v7 > 0x7FFFFFFF )
  {
    v14 = 2147942487LL;
    *v13 = 0;
    goto LABEL_28;
  }
  v15 = 2147483646;
  do
  {
    if ( !v15 )
      break;
    if ( !*v2 )
      break;
    *v13++ = *v2++;
    --v15;
    --v7;
  }
  while ( v7 );
  v16 = v13 - 1;
  if ( v7 )
    v16 = v13;
  v14 = v7 == 0 ? 0x8007007A : 0;
  *v16 = 0;
  if ( !v7 )
    goto LABEL_28;
  *((_WORD *)v6 + 16) = 0;
  if ( *((_QWORD *)this + 2) )
  {
    *((_QWORD *)v6 + 1) = *((_QWORD *)this + 3);
    **((_QWORD **)this + 3) = v6;
  }
  else
  {
    *((_QWORD *)this + 2) = v6;
  }
  *((_QWORD *)this + 3) = v6;
  return (struct _propertyNodeDef *)v6;
}

```

## disassembly

```asm
0x1800110a8  push    rbx
0x1800110aa  push    rbp
0x1800110ab  push    rsi
0x1800110ac  push    rdi
0x1800110ad  push    r14
0x1800110af  push    r15
0x1800110b1  sub     rsp, 28h
0x1800110b5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800110b9  mov     r14, rdx
0x1800110bc  mov     rsi, r15
0x1800110bf  xor     ebp, ebp
0x1800110c1  mov     rdi, rcx
0x1800110c4  inc     rsi
0x1800110c7  cmp     [rdx+rsi*2], bp
0x1800110cb  jnz     short loc_1800110C4
0x1800110cd  test    rsi, rsi
0x1800110d0  jz      loc_18001123E
0x1800110d6  mov     ecx, 30h ; '0'; Size
0x1800110db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800110e0  mov     rbx, rax
0x1800110e3  test    rax, rax
0x1800110e6  jz      loc_18001123E
0x1800110ec  xorps   xmm0, xmm0
0x1800110ef  inc     rsi
0x1800110f2  movups  xmmword ptr [rax], xmm0
0x1800110f5  movups  xmmword ptr [rax+10h], xmm0
0x1800110f9  movups  xmmword ptr [rax+20h], xmm0
0x1800110fd  mov     eax, 2
0x180011102  mul     rsi
0x180011105  cmovb   rax, r15
0x180011109  mov     rcx, rax; unsigned __int64
0x18001110c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180011111  mov     [rbx+18h], rax
0x180011115  test    rax, rax
0x180011118  jz      loc_180011236
0x18001111e  mov     [rbx+10h], ebp
0x180011121  mov     r8, [rdi+10h]
0x180011125  mov     ecx, [rdi+20h]
0x180011128  mov     rax, r8
0x18001112b  test    r8, r8
0x18001112e  jz      short loc_18001113D
0x180011130  cmp     [rax+14h], ecx
0x180011133  jz      short loc_18001113D
0x180011135  mov     rax, [rax]
0x180011138  test    rax, rax
0x18001113b  jnz     short loc_180011130
0x18001113d  mov     edx, [rdi+20h]
0x180011140  lea     ecx, [rdx+1]
0x180011143  mov     [rdi+20h], ecx
0x180011146  test    rax, rax
0x180011149  jz      short loc_180011158
0x18001114b  cmp     ecx, 80000000h
0x180011151  jb      short loc_180011128
0x180011153  jmp     loc_18001122D
0x180011158  mov     [rbx+14h], edx
0x18001115b  mov     rdx, [rbx+18h]
0x18001115f  test    rsi, rsi
0x180011162  jz      loc_1800111F1
0x180011168  cmp     rsi, 7FFFFFFFh
0x18001116f  jbe     short loc_18001117C
0x180011171  mov     r9d, 80070057h
0x180011177  jmp     loc_1800111FC
0x18001117c  mov     eax, 7FFFFFFEh
0x180011181  test    rax, rax
0x180011184  jz      short loc_1800111A3
0x180011186  movzx   ecx, word ptr [r14]
0x18001118a  test    cx, cx
0x18001118d  jz      short loc_1800111A3
0x18001118f  mov     [rdx], cx
0x180011192  add     r14, 2
0x180011196  add     rdx, 2
0x18001119a  dec     rax
0x18001119d  sub     rsi, 1
0x1800111a1  jnz     short loc_180011181
0x1800111a3  test    rsi, rsi
0x1800111a6  lea     rcx, [rdx-2]
0x1800111aa  mov     rax, rsi
0x1800111ad  cmovnz  rcx, rdx
0x1800111b1  neg     rax
0x1800111b4  sbb     r9d, r9d
0x1800111b7  not     r9d
0x1800111ba  and     r9d, 8007007Ah
0x1800111c1  mov     [rcx], bp
0x1800111c4  test    rsi, rsi
0x1800111c7  jz      short loc_1800111FF
0x1800111c9  mov     [rbx+20h], bp
0x1800111cd  cmp     [rdi+10h], rbp
0x1800111d1  jnz     short loc_1800111D9
0x1800111d3  mov     [rdi+10h], rbx
0x1800111d7  jmp     short loc_1800111E8
0x1800111d9  mov     rax, [rdi+18h]
0x1800111dd  mov     [rbx+8], rax
0x1800111e1  mov     rax, [rdi+18h]
0x1800111e5  mov     [rax], rbx
0x1800111e8  mov     [rdi+18h], rbx
0x1800111ec  mov     rax, rbx
0x1800111ef  jmp     short loc_180011240
0x1800111f1  mov     r9d, 80070057h
0x1800111f7  test    rsi, rsi
0x1800111fa  jz      short loc_1800111FF
0x1800111fc  mov     [rdx], bp
0x1800111ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180011206  lea     rax, WPP_GLOBAL_Control
0x18001120d  cmp     rcx, rax
0x180011210  jz      short loc_18001122D
0x180011212  test    byte ptr [rcx+44h], 1
0x180011216  jz      short loc_18001122D
0x180011218  mov     rcx, [rcx+38h]
0x18001121c  lea     r8, WPP_de07cdecc1bf34ac651f6376ad8c6e00_Traceguids
0x180011223  mov     edx, 0Bh
0x180011228  call    WPP_SF_d
0x18001122d  mov     rcx, [rbx+18h]; Block
0x180011231  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011236  mov     rcx, rbx; Block
0x180011239  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001123e  xor     eax, eax
0x180011240  add     rsp, 28h
0x180011244  pop     r15
0x180011246  pop     r14
0x180011248  pop     rdi
0x180011249  pop     rsi
0x18001124a  pop     rbp
0x18001124b  pop     rbx
0x18001124c  retn
```
