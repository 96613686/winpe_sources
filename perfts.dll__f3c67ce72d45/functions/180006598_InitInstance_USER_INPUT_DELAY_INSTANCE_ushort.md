# InitInstance(_USER_INPUT_DELAY_INSTANCE *,ushort *)

- ea: `0x180006598`
- end: `0x18000677c`
- name: `?InitInstance@@YAXPEAU_USER_INPUT_DELAY_INSTANCE@@PEAG@Z`
- size: `484`
- prototype: `void __fastcall(struct _USER_INPUT_DELAY_INSTANCE *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800047fc`

## callees

- `0x1800011e8`
- `0x180006598`
- `0x1800098f6`
- `0x180009930`

## string_xrefs

- `0x180006701`: `Failed to copy instance name`

## pseudocode

```c
void __fastcall InitInstance(struct _USER_INPUT_DELAY_INSTANCE *a1, unsigned __int16 *a2)
{
  __int64 v4; // r14
  int v5; // esi
  __int64 v6; // r8
  unsigned __int16 *v7; // rax
  unsigned int v8; // edx
  unsigned __int64 v9; // rax
  _WORD *v10; // rax
  __int64 v11; // rcx
  unsigned __int16 *v12; // r8
  __int64 v13; // rbp
  __int64 v14; // r10
  _WORD *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rdx
  struct _EVENT_DATA_DESCRIPTOR v18; // [rsp+30h] [rbp-88h] BYREF
  const char *v19; // [rsp+50h] [rbp-68h]
  __int64 v20; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v21; // [rsp+60h] [rbp-58h]
  int v22; // [rsp+68h] [rbp-50h]
  int v23; // [rsp+6Ch] [rbp-4Ch]

  memset_0(a1, 0, 0xB8u);
  v4 = -1;
  *((_DWORD *)a1 + 43) = 1;
  *((_DWORD *)a1 + 3) = -1;
  *((_DWORD *)a1 + 4) = 24;
  v5 = 2;
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_9:
    LODWORD(v9) = 0;
    goto LABEL_10;
  }
  v6 = 70;
  v7 = a2;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = v6 == 0 ? 0x80070057 : 0;
  v9 = (70 - v6) & -(__int64)(v6 != 0);
  if ( !v6 )
    goto LABEL_9;
  if ( v9 >= 0x46 )
  {
LABEL_11:
    LODWORD(v9) = 70;
    goto LABEL_12;
  }
LABEL_10:
  if ( v8 )
    goto LABEL_11;
LABEL_12:
  *((_DWORD *)a1 + 5) = 2 * v9 + 2;
  v10 = (_WORD *)((char *)a1 + 24);
  v11 = 2147483646;
  v12 = a2;
  v13 = 71;
  v14 = 0;
  do
  {
    if ( !v11 )
      break;
    if ( !*v12 )
      break;
    *v10++ = *v12++;
    --v11;
    ++v14;
    --v13;
  }
  while ( v13 );
  v15 = v10 - 1;
  v16 = v14 - 1;
  if ( v13 )
  {
    v15 = v10;
    v16 = v14;
  }
  *v15 = 0;
  if ( v13 )
  {
    v17 = 71 - v16;
    if ( v16 != 71 && v16 != 70 && (unsigned __int64)(2 * v17) > 2 )
      memset_0((char *)a1 + 2 * v16 + 26, 0, 2 * v17 - 2);
  }
  *((_WORD *)a1 + 83) = 0;
  if ( !v13 && (unsigned int)dword_180012020 > 2 )
  {
    if ( a2 )
    {
      do
        ++v4;
      while ( a2[v4] );
      v5 = 2 * v4 + 2;
    }
    else
    {
      a2 = (unsigned __int16 *)&unk_18000DE50;
    }
    v21 = a2;
    v19 = "Failed to copy instance name";
    v22 = v5;
    v23 = 0;
    v20 = 29;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180012020, byte_18000F095, 0, 0, 4u, &v18);
  }
  *(_DWORD *)a1 = 168;
  *((_DWORD *)a1 + 42) = 16;
}

```

## disassembly

```asm
0x180006598  push    rbx
0x18000659a  push    rbp
0x18000659b  push    rsi
0x18000659c  push    rdi
0x18000659d  push    r14
0x18000659f  push    r15
0x1800065a1  sub     rsp, 88h
0x1800065a8  mov     rax, cs:__security_cookie
0x1800065af  xor     rax, rsp
0x1800065b2  mov     [rsp+0B8h+var_48], rax
0x1800065b7  mov     rdi, rdx
0x1800065ba  mov     r8d, 0B8h; Size
0x1800065c0  xor     edx, edx; Val
0x1800065c2  mov     rbx, rcx
0x1800065c5  call    memset_0
0x1800065ca  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800065ce  mov     dword ptr [rbx+0ACh], 1
0x1800065d8  xor     r15d, r15d
0x1800065db  mov     [rbx+0Ch], r14d
0x1800065df  mov     dword ptr [rbx+10h], 18h
0x1800065e6  lea     esi, [r14+3]
0x1800065ea  lea     r9d, [r14+47h]
0x1800065ee  test    rdi, rdi
0x1800065f1  jz      short loc_180006636
0x1800065f3  mov     r8d, r9d
0x1800065f6  mov     rax, rdi
0x1800065f9  cmp     [rax], r15w
0x1800065fd  jz      short loc_180006608
0x1800065ff  add     rax, rsi
0x180006602  sub     r8, 1
0x180006606  jnz     short loc_1800065F9
0x180006608  mov     rax, r8
0x18000660b  mov     rcx, r9
0x18000660e  neg     rax
0x180006611  mov     rax, r8
0x180006614  sbb     edx, edx
0x180006616  sub     rcx, r8
0x180006619  not     edx
0x18000661b  and     edx, 80070057h
0x180006621  neg     rax
0x180006624  sbb     rax, rax
0x180006627  and     rax, rcx
0x18000662a  test    r8, r8
0x18000662d  jz      short loc_18000663B
0x18000662f  cmp     rax, r9
0x180006632  jnb     short loc_180006642
0x180006634  jmp     short loc_18000663E
0x180006636  mov     edx, 80070057h
0x18000663b  mov     rax, r15
0x18000663e  test    edx, edx
0x180006640  jz      short loc_180006645
0x180006642  mov     rax, r9
0x180006645  lea     eax, ds:2[rax*2]
0x18000664c  mov     edx, 47h ; 'G'
0x180006651  lea     r11, [rbx+18h]
0x180006655  mov     [rbx+14h], eax
0x180006658  mov     rax, r11
0x18000665b  mov     ecx, 7FFFFFFEh
0x180006660  mov     r8, rdi
0x180006663  mov     ebp, edx
0x180006665  mov     r10, r15
0x180006668  test    rcx, rcx
0x18000666b  jz      short loc_18000668D
0x18000666d  movzx   r9d, word ptr [r8]
0x180006671  test    r9w, r9w
0x180006675  jz      short loc_18000668D
0x180006677  mov     [rax], r9w
0x18000667b  add     r8, rsi
0x18000667e  add     rax, rsi
0x180006681  dec     rcx
0x180006684  inc     r10
0x180006687  sub     rbp, 1
0x18000668b  jnz     short loc_180006668
0x18000668d  test    rbp, rbp
0x180006690  lea     rcx, [rax-2]
0x180006694  lea     r9, [r10-1]
0x180006698  cmovnz  rcx, rax
0x18000669c  cmovnz  r9, r10
0x1800066a0  mov     [rcx], r15w
0x1800066a4  jz      short loc_1800066CA
0x1800066a6  sub     rdx, r9
0x1800066a9  cmp     rdx, 1
0x1800066ad  jbe     short loc_1800066CA
0x1800066af  lea     r8, [rdx+rdx]
0x1800066b3  cmp     r8, rsi
0x1800066b6  jbe     short loc_1800066CA
0x1800066b8  add     r11, rsi
0x1800066bb  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800066bf  xor     edx, edx; Val
0x1800066c1  lea     rcx, [r11+r9*2]; void *
0x1800066c5  call    memset_0
0x1800066ca  mov     [rbx+0A6h], r15w
0x1800066d2  test    rbp, rbp
0x1800066d5  jnz     short loc_18000674F
0x1800066d7  mov     eax, cs:dword_180012020
0x1800066dd  cmp     eax, esi
0x1800066df  jbe     short loc_18000674F
0x1800066e1  test    rdi, rdi
0x1800066e4  jz      short loc_1800066FA
0x1800066e6  inc     r14
0x1800066e9  cmp     [rdi+r14*2], r15w
0x1800066ee  jnz     short loc_1800066E6
0x1800066f0  lea     esi, ds:2[r14*2]
0x1800066f8  jmp     short loc_180006701
0x1800066fa  lea     rdi, unk_18000DE50
0x180006701  lea     rax, aFailedToCopyIn; "Failed to copy instance name"
0x180006708  mov     [rsp+0B8h+var_58], rdi
0x18000670d  mov     [rsp+0B8h+var_68], rax
0x180006712  lea     rdx, byte_18000F095
0x180006719  lea     rax, [rsp+0B8h+var_88]
0x18000671e  mov     [rsp+0B8h+var_50], esi
0x180006722  mov     [rsp+0B8h+var_90], rax
0x180006727  lea     rcx, dword_180012020
0x18000672e  xor     r9d, r9d
0x180006731  mov     [rsp+0B8h+var_98], 4
0x180006739  xor     r8d, r8d
0x18000673c  mov     [rsp+0B8h+var_4C], r15d
0x180006741  mov     [rsp+0B8h+var_60], 1Dh
0x18000674a  call    _tlgWriteTransfer_EventWriteTransfer
0x18000674f  mov     dword ptr [rbx], 0A8h
0x180006755  mov     dword ptr [rbx+0A8h], 10h
0x18000675f  mov     rcx, [rsp+0B8h+var_48]
0x180006764  xor     rcx, rsp; StackCookie
0x180006767  call    __security_check_cookie
0x18000676c  add     rsp, 88h
0x180006773  pop     r15
0x180006775  pop     r14
0x180006777  pop     rdi
0x180006778  pop     rsi
0x180006779  pop     rbp
0x18000677a  pop     rbx
0x18000677b  retn
```
