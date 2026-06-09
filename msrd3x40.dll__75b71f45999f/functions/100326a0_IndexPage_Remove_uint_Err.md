# IndexPage::Remove(uint,Err &)

- ea: `0x100326a0`
- end: `0x1003283d`
- name: `?Remove@IndexPage@@QAE?AW4IdxStatus@@IAAVErr@@@Z`
- size: `413`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10011540`
- `0x10012190`

## callees

- `0x1000f890`
- `0x10010290`
- `0x100326a0`
- `0x1005e7e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x100327c6`
- `api-ms-win-crt-private-l1-1-0!memcpy` at `0x100327c6`

## pseudocode

```c
int __thiscall IndexPage::Remove(_DWORD *this, unsigned int a2, int a3)
{
  int v3; // ebx
  int v4; // esi
  int v5; // eax
  unsigned int v6; // edx
  unsigned __int8 v7; // al
  unsigned int v9; // edi
  unsigned int v10; // ecx
  unsigned __int8 v11; // al
  int v13; // esi
  int v14; // ebx
  int v15; // eax
  unsigned int v16; // esi
  void *v18; // [esp-Ch] [ebp-48h]
  _DWORD v19[3]; // [esp+Ch] [ebp-30h] BYREF
  void *Block; // [esp+18h] [ebp-24h]
  void *v21; // [esp+1Ch] [ebp-20h]
  _DWORD v22[3]; // [esp+20h] [ebp-1Ch] BYREF
  _DWORD *v23; // [esp+2Ch] [ebp-10h]
  int v24; // [esp+30h] [ebp-Ch]
  _WORD *v25; // [esp+34h] [ebp-8h]
  int v26; // [esp+38h] [ebp-4h]

  v22[1] = 226;
  v23 = this;
  v3 = 0;
  v26 = this[1];
  v22[2] = 0;
  v4 = v26 + 22;
  v19[0] = 1;
  v5 = *(unsigned __int16 *)(v26 + 2);
  v22[0] = v26 + 22;
  v6 = (unsigned int)(1807 - v5) >> 3;
  v7 = *(_BYTE *)(v26 + 22 + v6) & byte_10003908[(1807 - v5) & 7];
  if ( v7 )
  {
LABEL_4:
    v9 = (unsigned __int8)byte_10003708[v7] + 8 * v6;
  }
  else
  {
    while ( v6-- )
    {
      v7 = *(_BYTE *)(v4 + v6);
      if ( v7 )
        goto LABEL_4;
    }
    v9 = -1;
  }
  v10 = a2 >> 3;
  v11 = *(_BYTE *)(v4 + (a2 >> 3)) & byte_10003908[a2 & 7];
  if ( v11 )
  {
LABEL_8:
    v13 = (unsigned __int8)byte_10003708[v11] + 8 * v10;
    v24 = v13;
    if ( v13 != -1 )
    {
      v25 = (_WORD *)(v26 + 2);
      if ( a2 == v9 )
        goto LABEL_14;
      v14 = v26;
LABEL_17:
      v18 = (void *)(v14 + v13 + 248);
      v16 = a2 - v13;
      _memcpy(v18, (const void *)(v14 + a2 + 248), v9 - a2);
      *(_WORD *)(v14 + 2) = *v25 + v16;
      Bitmap::DeleteBits((Bitmap *)v22, v24 + 1, v16, (struct Err *)v19);
      v3 = (unsigned __int8)(v19[0] & 8) >> 3;
      goto LABEL_18;
    }
  }
  else
  {
    while ( v10-- )
    {
      v11 = *(_BYTE *)(v4 + v10);
      if ( v11 )
        goto LABEL_8;
    }
  }
  if ( a2 != v9 )
  {
    v14 = v26;
    v13 = *(unsigned __int8 *)(v26 + 20);
    v24 = v13;
    v25 = (_WORD *)(v26 + 2);
    goto LABEL_17;
  }
  v13 = 0;
  v25 = (_WORD *)(v26 + 2);
LABEL_14:
  Bitmap::Clear((Bitmap *)v22, v9, (struct Err *)v19);
  v15 = v26;
  *(_WORD *)(v26 + 2) = *v25 + v9 - v13;
  if ( v13 )
    goto LABEL_20;
  v3 = 1;
  *(_WORD *)(v15 + 2) = 1800;
LABEL_18:
  if ( v3 == 1 )
    v3 = *(_DWORD *)(v23[1] + 16) == 0;
LABEL_20:
  if ( (v19[0] & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v21 )
      operator delete[](v21);
  }
  return v3;
}

```

## disassembly

```asm
0x100326a0  mov     edi, edi
0x100326a2  push    ebp
0x100326a3  mov     ebp, esp
0x100326a5  sub     esp, 30h
0x100326a8  mov     eax, ecx
0x100326aa  mov     [ebp+var_18], 0E2h
0x100326b1  mov     [ebp+var_10], eax
0x100326b4  mov     ecx, 70Fh
0x100326b9  push    ebx
0x100326ba  push    esi
0x100326bb  mov     eax, [eax+4]
0x100326be  xor     ebx, ebx
0x100326c0  mov     [ebp+var_4], eax
0x100326c3  push    edi
0x100326c4  mov     [ebp+var_14], 0
0x100326cb  lea     esi, [eax+16h]
0x100326ce  mov     [ebp+var_30], 1
0x100326d5  movzx   eax, word ptr [eax+2]
0x100326d9  sub     ecx, eax
0x100326db  mov     [ebp+var_1C], esi
0x100326de  mov     edx, ecx
0x100326e0  and     ecx, 7
0x100326e3  shr     edx, 3
0x100326e6  mov     al, ds:byte_10003908[ecx]
0x100326ec  and     al, [esi+edx]
0x100326ef  jnz     short loc_100326FF
0x100326f1  mov     eax, edx
0x100326f3  dec     edx
0x100326f4  test    eax, eax
0x100326f6  jz      short loc_10032758
0x100326f8  mov     al, [esi+edx]
0x100326fb  test    al, al
0x100326fd  jz      short loc_100326F1
0x100326ff  movzx   eax, al
0x10032702  movzx   eax, ds:byte_10003708[eax]
0x10032709  lea     edi, [eax+edx*8]
0x1003270c  mov     edx, [ebp+arg_0]
0x1003270f  mov     eax, edx
0x10032711  and     eax, 7
0x10032714  mov     ecx, edx
0x10032716  shr     ecx, 3
0x10032719  mov     al, ds:byte_10003908[eax]
0x1003271f  and     al, [esi+ecx]
0x10032722  jnz     short loc_10032732
0x10032724  mov     eax, ecx
0x10032726  dec     ecx
0x10032727  test    eax, eax
0x10032729  jz      short loc_10032747
0x1003272b  mov     al, [esi+ecx]
0x1003272e  test    al, al
0x10032730  jz      short loc_10032724
0x10032732  movzx   eax, al
0x10032735  movzx   eax, ds:byte_10003708[eax]
0x1003273c  lea     esi, [eax+ecx*8]
0x1003273f  mov     [ebp+var_C], esi
0x10032742  cmp     esi, 0FFFFFFFFh
0x10032745  jnz     short loc_1003276F
0x10032747  cmp     edx, edi
0x10032749  jnz     short loc_1003275D
0x1003274b  mov     ecx, [ebp+var_4]
0x1003274e  xor     esi, esi
0x10032750  add     ecx, 2
0x10032753  mov     [ebp+var_8], ecx
0x10032756  jmp     short loc_1003277C
0x10032758  or      edi, 0FFFFFFFFh
0x1003275b  jmp     short loc_1003270C
0x1003275d  mov     ebx, [ebp+var_4]
0x10032760  movzx   esi, byte ptr [ebx+14h]
0x10032764  lea     eax, [ebx+2]
0x10032767  mov     [ebp+var_C], esi
0x1003276a  mov     [ebp+var_8], eax
0x1003276d  jmp     short loc_100327AD
0x1003276f  mov     eax, [ebp+var_4]
0x10032772  add     eax, 2
0x10032775  mov     [ebp+var_8], eax
0x10032778  cmp     edx, edi
0x1003277a  jnz     short loc_100327AA
0x1003277c  lea     eax, [ebp+var_30]
0x1003277f  push    eax; struct Err *
0x10032780  push    edi; unsigned int
0x10032781  lea     ecx, [ebp+var_1C]; this
0x10032784  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x10032789  mov     ecx, [ebp+var_8]
0x1003278c  sub     edi, esi
0x1003278e  mov     eax, [ebp+var_4]
0x10032791  add     di, [ecx]
0x10032794  mov     [eax+2], di
0x10032798  test    esi, esi
0x1003279a  jnz     short loc_10032809
0x1003279c  mov     ecx, 708h
0x100327a1  lea     ebx, [esi+1]
0x100327a4  mov     [eax+2], cx
0x100327a8  jmp     short loc_100327F6
0x100327aa  mov     ebx, [ebp+var_4]
0x100327ad  lea     eax, [edx+0F8h]
0x100327b3  sub     edi, edx
0x100327b5  lea     ecx, [esi+0F8h]
0x100327bb  add     eax, ebx
0x100327bd  push    edi; Size
0x100327be  add     ecx, ebx
0x100327c0  mov     esi, eax
0x100327c2  push    eax; Src
0x100327c3  push    ecx; void *
0x100327c4  sub     esi, ecx
0x100327c6  call    ds:__imp__memcpy
0x100327cc  mov     ecx, [ebp+var_8]
0x100327cf  add     esp, 0Ch
0x100327d2  mov     eax, esi
0x100327d4  add     ax, [ecx]
0x100327d7  lea     ecx, [ebp+var_1C]; this
0x100327da  mov     [ebx+2], ax
0x100327de  lea     eax, [ebp+var_30]
0x100327e1  push    eax; struct Err *
0x100327e2  mov     eax, [ebp+var_C]
0x100327e5  push    esi; unsigned int
0x100327e6  inc     eax
0x100327e7  push    eax; unsigned int
0x100327e8  call    ?DeleteBits@Bitmap@@QAEXKKAAVErr@@@Z; Bitmap::DeleteBits(ulong,ulong,Err &)
0x100327ed  mov     ebx, [ebp+var_30]
0x100327f0  and     ebx, 8
0x100327f3  shr     ebx, 3
0x100327f6  cmp     ebx, 1
0x100327f9  jnz     short loc_10032809
0x100327fb  mov     eax, [ebp+var_10]
0x100327fe  xor     ebx, ebx
0x10032800  mov     eax, [eax+4]
0x10032803  cmp     [eax+10h], ebx
0x10032806  setz    bl
0x10032809  test    [ebp+var_30], 0FFFFFFFEh
0x10032810  jz      short loc_10032832
0x10032812  mov     eax, [ebp+Block]
0x10032815  test    eax, eax
0x10032817  jz      short loc_10032822
0x10032819  push    eax; Block
0x1003281a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003281f  add     esp, 4
0x10032822  mov     eax, [ebp+var_20]
0x10032825  test    eax, eax
0x10032827  jz      short loc_10032832
0x10032829  push    eax; Block
0x1003282a  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1003282f  add     esp, 4
0x10032832  pop     edi
0x10032833  pop     esi
0x10032834  mov     eax, ebx
0x10032836  pop     ebx
0x10032837  mov     esp, ebp
0x10032839  pop     ebp
0x1003283a  retn    8
```
