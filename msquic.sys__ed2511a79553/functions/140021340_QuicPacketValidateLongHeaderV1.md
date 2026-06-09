# QuicPacketValidateLongHeaderV1

- ea: `0x140021340`
- end: `0x140021573`
- name: `QuicPacketValidateLongHeaderV1`
- size: `563`
- prototype: `char __fastcall(__int64, unsigned __int8, __int64, unsigned __int8 **, _WORD *, char)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140015b70`
- `0x14002924c`

## callees

- `0x14000ed10`
- `0x140021340`
- `0x140026a88`
- `0x140041d3c`

## string_xrefs

- `0x1400214b2`: `Long header has invalid token length`
- `0x1400214d6`: `Long header has token length larger than buffer length`

## pseudocode

```c
char __fastcall QuicPacketValidateLongHeaderV1(
        __int64 a1,
        unsigned __int8 a2,
        __int64 a3,
        unsigned __int8 **a4,
        _WORD *a5,
        char a6)
{
  __int64 v8; // rdi
  unsigned __int8 *v9; // r14
  __int64 v10; // rcx
  int v11; // r8d
  unsigned __int8 v12; // r9
  const char *v13; // r8
  const char *v14; // r8
  unsigned __int64 v15; // r9
  char v16; // al
  unsigned __int8 *v17; // rax
  unsigned __int64 v18; // r14
  __int64 v19; // rdx
  unsigned __int64 v20; // r15
  __int64 v21; // r9
  unsigned __int16 v22; // dx
  __int16 v23; // cx
  char result; // al
  _QWORD v25[2]; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int16 v26; // [rsp+70h] [rbp+40h] BYREF

  v8 = a1;
  if ( *(_BYTE *)(a3 + 86) > 0x14u || *(_BYTE *)(a3 + 87) > 0x14u )
  {
    v13 = "Greater than allowed max CID length";
    goto LABEL_32;
  }
  v9 = *(unsigned __int8 **)(a3 + 56);
  v10 = 4LL * a2;
  v11 = *(_DWORD *)(v9 + 1);
  if ( v11 == -817679509 )
  {
    v12 = *v9;
    if ( *((_BYTE *)&QUIC_HEADER_TYPE_ALLOWED_V2 + v10 + (((unsigned __int64)*v9 >> 4) & 3)) )
      goto LABEL_5;
LABEL_10:
    v14 = "Invalid client/server packet type";
    v15 = ((unsigned __int64)v12 >> 4) & 3;
    goto LABEL_11;
  }
  v12 = *v9;
  if ( !*((_BYTE *)&QUIC_HEADER_TYPE_ALLOWED_V1 + v10 + (((unsigned __int64)*v9 >> 4) & 3)) )
    goto LABEL_10;
LABEL_5:
  if ( !a6 && (*v9 & 0x40) == 0 )
  {
    v13 = "Invalid LH FixedBit bits values";
LABEL_8:
    a1 = v8;
LABEL_32:
    QuicPacketLogDrop(a1, a3, v13);
    return 0;
  }
  v26 = *(_WORD *)(a3 + 82);
  v16 = *v9 & 0x30;
  if ( v11 == -817679509 )
  {
    if ( v16 != 16 )
      goto LABEL_14;
LABEL_18:
    if ( a2 && *(_WORD *)(a3 + 80) < 0x4B0u )
    {
      v15 = *(unsigned __int16 *)(a3 + 80);
      v14 = "Client Long header Initial packet too short";
      goto LABEL_11;
    }
    v20 = *(unsigned __int16 *)(a3 + 80);
    v25[0] = 0;
    if ( !(unsigned __int8)QuicVarIntDecode((unsigned __int16)v20, v9, &v26, v25) )
    {
      v13 = "Long header has invalid token length";
      goto LABEL_8;
    }
    v21 = v26;
    if ( v20 < (unsigned __int64)v26 + v25[0] )
    {
      v15 = v25[0];
      v14 = "Long header has token length larger than buffer length";
      goto LABEL_11;
    }
    v26 += LOWORD(v25[0]);
    *a5 = v25[0];
    v17 = &v9[v21];
    goto LABEL_15;
  }
  if ( !v16 )
    goto LABEL_18;
LABEL_14:
  *a5 = 0;
  v17 = 0;
LABEL_15:
  *a4 = v17;
  v18 = *(unsigned __int16 *)(a3 + 80);
  v19 = *(_QWORD *)(a3 + 56);
  v25[0] = 0;
  if ( !(unsigned __int8)QuicVarIntDecode((unsigned __int16)v18, v19, &v26, v25) )
  {
    v13 = "Long header has invalid payload length";
    goto LABEL_8;
  }
  v22 = v26;
  v15 = v18;
  v23 = v25[0];
  if ( v18 >= (unsigned __int64)v26 + v25[0] )
  {
    if ( v18 >= (unsigned __int64)v26 + 4 )
    {
      *(_WORD *)(a3 + 84) = v25[0];
      result = 1;
      *(_WORD *)(a3 + 82) = v22;
      *(_BYTE *)(a3 + 92) |= 8u;
      *(_WORD *)(a3 + 80) = v22 + v23;
      return result;
    }
    v14 = "Long Header doesn't have enough room for packet number";
  }
  else
  {
    v15 = v25[0];
    v14 = "Long header has length larger than buffer length";
  }
LABEL_11:
  QuicPacketLogDropWithValue(v8, a3, v14, v15);
  return 0;
}

```

## disassembly

```asm
0x140021340  mov     [rsp-28h+arg_0], rbx
0x140021345  mov     [rsp-28h+arg_8], rsi
0x14002134a  push    rbp
0x14002134b  push    rdi
0x14002134c  push    r12
0x14002134e  push    r14
0x140021350  push    r15
0x140021352  mov     rbp, rsp
0x140021355  sub     rsp, 30h
0x140021359  cmp     byte ptr [r8+56h], 14h
0x14002135e  mov     r12, r9
0x140021361  mov     rbx, r8
0x140021364  mov     rdi, rcx
0x140021367  ja      loc_14002154A
0x14002136d  cmp     byte ptr [r8+57h], 14h
0x140021372  ja      loc_14002154A
0x140021378  mov     r14, [r8+38h]
0x14002137c  mov     r10d, 0CF43336Bh
0x140021382  movzx   ecx, dl
0x140021385  xor     esi, esi
0x140021387  shl     rcx, 2
0x14002138b  mov     r8d, [r14+1]
0x14002138f  cmp     r8d, r10d
0x140021392  jz      short loc_1400213D1
0x140021394  movzx   r9d, byte ptr [r14]
0x140021398  mov     eax, r9d
0x14002139b  shr     rax, 4
0x14002139f  and     eax, 3
0x1400213a2  add     rax, rcx
0x1400213a5  lea     rcx, cs:140000000h
0x1400213ac  cmp     [rax+rcx+57410h], sil
0x1400213b4  jz      short loc_1400213F3
0x1400213b6  cmp     [rbp+arg_28], sil
0x1400213ba  jnz     short loc_140021416
0x1400213bc  test    byte ptr [r14], 40h
0x1400213c0  jnz     short loc_140021416
0x1400213c2  lea     r8, aInvalidLhFixed; "Invalid LH FixedBit bits values"
0x1400213c9  mov     rcx, rdi
0x1400213cc  jmp     loc_140021551
0x1400213d1  movzx   eax, byte ptr [r14]
0x1400213d5  mov     r9b, al
0x1400213d8  shr     rax, 4
0x1400213dc  and     eax, 3
0x1400213df  add     rax, rcx
0x1400213e2  lea     rcx, cs:140000000h
0x1400213e9  cmp     [rax+rcx+57418h], sil
0x1400213f1  jnz     short loc_1400213B6
0x1400213f3  movzx   r9d, r9b
0x1400213f7  lea     r8, aInvalidClientS; "Invalid client/server packet type"
0x1400213fe  shr     r9, 4
0x140021402  and     r9d, 3
0x140021406  mov     rdx, rbx
0x140021409  mov     rcx, rdi
0x14002140c  call    QuicPacketLogDropWithValue
0x140021411  jmp     loc_140021559
0x140021416  movzx   eax, word ptr [rbx+52h]
0x14002141a  mov     [rbp+arg_10], ax
0x14002141e  mov     al, [r14]
0x140021421  and     al, 30h
0x140021423  cmp     r8d, r10d
0x140021426  jz      short loc_14002146C
0x140021428  test    al, al
0x14002142a  jz      short loc_140021470
0x14002142c  mov     rax, [rbp+arg_20]
0x140021430  mov     [rax], si
0x140021433  mov     rax, rsi
0x140021436  mov     [r12], rax
0x14002143a  lea     r9, [rbp+var_10]
0x14002143e  movzx   r14d, word ptr [rbx+50h]
0x140021443  lea     r8, [rbp+arg_10]
0x140021447  mov     rdx, [rbx+38h]
0x14002144b  movzx   ecx, r14w
0x14002144f  mov     [rbp+var_10], rsi
0x140021453  call    QuicVarIntDecode
0x140021458  test    al, al
0x14002145a  jnz     loc_1400214FB
0x140021460  lea     r8, aLongHeaderHasI_0; "Long header has invalid payload length"
0x140021467  jmp     loc_1400213C9
0x14002146c  cmp     al, 10h
0x14002146e  jnz     short loc_14002142C
0x140021470  test    dl, dl
0x140021472  jz      short loc_140021491
0x140021474  movzx   eax, word ptr [rbx+50h]
0x140021478  mov     ecx, 4B0h
0x14002147d  cmp     ax, cx
0x140021480  jnb     short loc_140021491
0x140021482  mov     r9d, eax
0x140021485  lea     r8, aClientLongHead; "Client Long header Initial packet too s"...
0x14002148c  jmp     loc_140021406
0x140021491  movzx   r15d, word ptr [rbx+50h]
0x140021496  lea     r9, [rbp+var_10]
0x14002149a  movzx   ecx, r15w
0x14002149e  mov     [rbp+var_10], rsi
0x1400214a2  lea     r8, [rbp+arg_10]
0x1400214a6  mov     rdx, r14
0x1400214a9  call    QuicVarIntDecode
0x1400214ae  test    al, al
0x1400214b0  jnz     short loc_1400214BE
0x1400214b2  lea     r8, aLongHeaderHasI; "Long header has invalid token length"
0x1400214b9  jmp     loc_1400213C9
0x1400214be  movzx   r8d, [rbp+arg_10]
0x1400214c3  mov     rdx, [rbp+var_10]
0x1400214c7  mov     r9d, r8d
0x1400214ca  lea     rcx, [r8+rdx]
0x1400214ce  cmp     r15, rcx
0x1400214d1  jnb     short loc_1400214E2
0x1400214d3  mov     r9, rdx
0x1400214d6  lea     r8, aLongHeaderHasT; "Long header has token length larger tha"...
0x1400214dd  jmp     loc_140021406
0x1400214e2  mov     rax, [rbp+arg_20]
0x1400214e6  add     r8w, dx
0x1400214ea  mov     [rbp+arg_10], r8w
0x1400214ef  mov     [rax], dx
0x1400214f2  lea     rax, [r9+r14]
0x1400214f6  jmp     loc_140021436
0x1400214fb  movzx   edx, [rbp+arg_10]
0x1400214ff  mov     r9, r14
0x140021502  mov     rcx, [rbp+var_10]
0x140021506  lea     rax, [rdx+rcx]
0x14002150a  cmp     r14, rax
0x14002150d  jnb     short loc_14002151E
0x14002150f  mov     r9, rcx
0x140021512  lea     r8, aLongHeaderHasL; "Long header has length larger than buff"...
0x140021519  jmp     loc_140021406
0x14002151e  lea     rax, [rdx+4]
0x140021522  cmp     r9, rax
0x140021525  jnb     short loc_140021533
0x140021527  lea     r8, aLongHeaderDoes; "Long Header doesn't have enough room fo"...
0x14002152e  jmp     loc_140021406
0x140021533  mov     [rbx+54h], cx
0x140021537  mov     al, 1
0x140021539  add     cx, dx
0x14002153c  mov     [rbx+52h], dx
0x140021540  or      byte ptr [rbx+5Ch], 8
0x140021544  mov     [rbx+50h], cx
0x140021548  jmp     short loc_14002155B
0x14002154a  lea     r8, aGreaterThanAll; "Greater than allowed max CID length"
0x140021551  mov     rdx, rbx
0x140021554  call    QuicPacketLogDrop
0x140021559  xor     al, al
0x14002155b  mov     rbx, [rsp+30h+arg_0]
0x140021560  mov     rsi, [rsp+30h+arg_8]
0x140021565  add     rsp, 30h
0x140021569  pop     r15
0x14002156b  pop     r14
0x14002156d  pop     r12
0x14002156f  pop     rdi
0x140021570  pop     rbp
0x140021571  retn
```
