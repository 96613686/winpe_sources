# publicdm::FromBase64String(wchar_t *,uchar * *,int *)

- ea: `0x140044980`
- end: `0x140044ae6`
- name: `?FromBase64String@publicdm@@YAJPEA_WPEAPEAEPEAH@Z`
- size: `358`
- prototype: `__int64 __fastcall(publicdm *__hidden this, wchar_t *, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140044574`

## callees

- `0x140044980`
- `0x140044dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140044a02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140044a02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ac2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140044ac2`

## pseudocode

```c
__int64 __fastcall publicdm::FromBase64String(wchar_t *this, wchar_t *a2, unsigned __int8 **a3, int *a4)
{
  wchar_t *v6; // rdi
  __int64 v7; // rsi
  int v9; // edx
  int v10; // ebp
  LPVOID v11; // rax
  unsigned int v12; // ebx
  char v13; // al
  _BYTE *v14; // r8
  int v15; // eax
  _BYTE *v16; // r8
  char v17; // r9
  char v18; // dl
  int v19; // eax
  char v20; // r9
  int v21; // eax
  char v22; // dl
  __int64 v23; // r8

  v6 = this;
  if ( !this || !a2 || !a3 )
    return 2147942487LL;
  v7 = -1;
  do
    ++v7;
  while ( this[v7] );
  if ( (int)v7 % 4 )
    return 2147500037LL;
  v9 = 3 * ((int)v7 >> 2) - 1;
  if ( this[(int)v7 - 1] != 61 )
    v9 = 3 * ((int)v7 >> 2);
  v10 = v9 - 1;
  if ( this[(int)v7 - 2] != 61 )
    v10 = v9;
  v11 = CoTaskMemAlloc(v10);
  if ( v11 )
  {
    *(_QWORD *)a2 = v11;
    v12 = 0;
    *(_DWORD *)a3 = v10;
    while ( (int)v7 > 0 )
    {
      v13 = utBase64ToIndex(*v6);
      *v14 = 4 * v13;
      v15 = utBase64ToIndex(v6[1]);
      v18 = v15;
      if ( v15 == -1 )
        goto LABEL_24;
      *v16 = v17 + ((unsigned __int8)v15 >> 4);
      if ( v6[2] != 61 )
      {
        v16[1] = 16 * v15;
        v19 = utBase64ToIndex(v6[2]);
        v18 = v19;
        if ( v19 == -1 )
          goto LABEL_24;
        v16[1] = v20 + ((unsigned __int8)v19 >> 2);
      }
      if ( v6[3] != 61 )
      {
        v16[2] = v18 << 6;
        v21 = utBase64ToIndex(v6[3]);
        if ( v21 == -1 )
        {
LABEL_24:
          v12 = -2147467259;
          goto LABEL_25;
        }
        *(_BYTE *)(v23 + 2) = v22 + v21;
      }
      LODWORD(v7) = v7 - 4;
      v6 += 4;
    }
  }
  else
  {
    v12 = -2147024882;
LABEL_25:
    if ( *(_QWORD *)a2 )
      CoTaskMemFree(*(LPVOID *)a2);
    *(_QWORD *)a2 = 0;
    *(_DWORD *)a3 = 0;
  }
  return v12;
}

```

## disassembly

```asm
0x140044980  push    rbx
0x140044982  push    rbp
0x140044983  push    rsi
0x140044984  push    rdi
0x140044985  push    r12
0x140044987  push    r14
0x140044989  push    r15
0x14004498b  sub     rsp, 20h
0x14004498f  xor     r12d, r12d
0x140044992  mov     r15, r8
0x140044995  mov     r14, rdx
0x140044998  mov     rdi, rcx
0x14004499b  test    rcx, rcx
0x14004499e  jz      loc_140044AD2
0x1400449a4  test    rdx, rdx
0x1400449a7  jz      loc_140044AD2
0x1400449ad  test    r8, r8
0x1400449b0  jz      loc_140044AD2
0x1400449b6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400449ba  inc     rsi
0x1400449bd  cmp     [rcx+rsi*2], r12w
0x1400449c2  jnz     short loc_1400449BA
0x1400449c4  mov     eax, esi
0x1400449c6  mov     ecx, 4
0x1400449cb  cdq
0x1400449cc  idiv    ecx
0x1400449ce  test    edx, edx
0x1400449d0  jz      short loc_1400449DC
0x1400449d2  mov     eax, 80004005h
0x1400449d7  jmp     loc_140044AD7
0x1400449dc  mov     eax, esi
0x1400449de  sar     eax, 2
0x1400449e1  lea     ecx, [rax+rax*2]
0x1400449e4  movsxd  rax, esi
0x1400449e7  lea     edx, [rcx-1]
0x1400449ea  cmp     word ptr [rdi+rax*2-2], 3Dh ; '='
0x1400449f0  cmovnz  edx, ecx
0x1400449f3  cmp     word ptr [rdi+rax*2-4], 3Dh ; '='
0x1400449f9  lea     ebp, [rdx-1]
0x1400449fc  cmovnz  ebp, edx
0x1400449ff  movsxd  rcx, ebp; cb
0x140044a02  call    cs:__imp_CoTaskMemAlloc
0x140044a08  mov     r8, rax
0x140044a0b  test    rax, rax
0x140044a0e  jnz     short loc_140044A1A
0x140044a10  mov     ebx, 8007000Eh
0x140044a15  jmp     loc_140044ABA
0x140044a1a  mov     [r14], rax
0x140044a1d  mov     ebx, r12d
0x140044a20  mov     [r15], ebp
0x140044a23  test    esi, esi
0x140044a25  jle     loc_140044ACE
0x140044a2b  movzx   ecx, word ptr [rdi]; wchar_t
0x140044a2e  call    ?utBase64ToIndex@@YAH_W@Z; utBase64ToIndex(wchar_t)
0x140044a33  mov     r9d, eax
0x140044a36  shl     r9b, 2
0x140044a3a  mov     [r8], r9b
0x140044a3d  movzx   ecx, word ptr [rdi+2]; wchar_t
0x140044a41  call    ?utBase64ToIndex@@YAH_W@Z; utBase64ToIndex(wchar_t)
0x140044a46  mov     edx, eax
0x140044a48  cmp     eax, 0FFFFFFFFh
0x140044a4b  jz      short loc_140044AB5
0x140044a4d  mov     cl, dl
0x140044a4f  shr     cl, 4
0x140044a52  add     cl, r9b
0x140044a55  mov     [r8], cl
0x140044a58  cmp     word ptr [rdi+4], 3Dh ; '='
0x140044a5d  jz      short loc_140044A83
0x140044a5f  shl     dl, 4
0x140044a62  mov     [r8+1], dl
0x140044a66  mov     r9b, dl
0x140044a69  movzx   ecx, word ptr [rdi+4]; wchar_t
0x140044a6d  call    ?utBase64ToIndex@@YAH_W@Z; utBase64ToIndex(wchar_t)
0x140044a72  mov     edx, eax
0x140044a74  cmp     eax, 0FFFFFFFFh
0x140044a77  jz      short loc_140044AB5
0x140044a79  shr     al, 2
0x140044a7c  add     al, r9b
0x140044a7f  mov     [r8+1], al
0x140044a83  cmp     word ptr [rdi+6], 3Dh ; '='
0x140044a88  jz      short loc_140044AA5
0x140044a8a  shl     dl, 6
0x140044a8d  mov     [r8+2], dl
0x140044a91  movzx   ecx, word ptr [rdi+6]; wchar_t
0x140044a95  call    ?utBase64ToIndex@@YAH_W@Z; utBase64ToIndex(wchar_t)
0x140044a9a  cmp     eax, 0FFFFFFFFh
0x140044a9d  jz      short loc_140044AB5
0x140044a9f  add     al, dl
0x140044aa1  mov     [r8+2], al
0x140044aa5  sub     esi, 4
0x140044aa8  add     rdi, 8
0x140044aac  add     r8, 3
0x140044ab0  jmp     loc_140044A23
0x140044ab5  mov     ebx, 80004005h
0x140044aba  mov     rcx, [r14]; pv
0x140044abd  test    rcx, rcx
0x140044ac0  jz      short loc_140044AC8
0x140044ac2  call    cs:__imp_CoTaskMemFree
0x140044ac8  mov     [r14], r12
0x140044acb  mov     [r15], r12d
0x140044ace  mov     eax, ebx
0x140044ad0  jmp     short loc_140044AD7
0x140044ad2  mov     eax, 80070057h
0x140044ad7  add     rsp, 20h
0x140044adb  pop     r15
0x140044add  pop     r14
0x140044adf  pop     r12
0x140044ae1  pop     rdi
0x140044ae2  pop     rsi
0x140044ae3  pop     rbp
0x140044ae4  pop     rbx
0x140044ae5  retn
```
