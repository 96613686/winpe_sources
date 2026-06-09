# publicdm::FromBase64String(ushort *,uchar * *,int *)

- ea: `0x18000a0e0`
- end: `0x18000a24a`
- name: `?FromBase64String@publicdm@@YAJPEAGPEAPEAEPEAH@Z`
- size: `362`
- prototype: `__int64 __fastcall(publicdm *__hidden this, unsigned __int16 *, unsigned __int8 **, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c93c`

## callees

- `0x18000a0e0`
- `0x18000a250`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a22d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a16c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a16c`

## pseudocode

```c
__int64 __fastcall publicdm::FromBase64String(publicdm *this, unsigned __int16 *a2, unsigned __int8 **a3, int *a4)
{
  unsigned __int16 *v6; // rdi
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

  v6 = (unsigned __int16 *)this;
  if ( !this || !a2 || !a3 )
    return 2147942487LL;
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)this + v7) );
  if ( (int)v7 % 4 )
    return 2147500037LL;
  v9 = 3 * ((int)v7 >> 2) - 1;
  if ( *((_WORD *)this + (int)v7 - 1) != 61 )
    v9 = 3 * ((int)v7 >> 2);
  v10 = v9 - 1;
  if ( *((_WORD *)this + (int)v7 - 2) != 61 )
    v10 = v9;
  v11 = CoTaskMemAlloc(v10);
  if ( v11 )
  {
    v12 = 0;
    *(_QWORD *)a2 = v11;
    *(_DWORD *)a3 = v10;
    while ( (int)v7 > 0 )
    {
      v13 = utBase64ToIndex(*v6);
      *v14 = 4 * v13;
      v15 = utBase64ToIndex(v6[1]);
      v18 = v15;
      if ( v15 == -1 )
        goto LABEL_23;
      *v16 = v17 + ((unsigned __int8)v15 >> 4);
      if ( v6[2] != 61 )
      {
        v16[1] = 16 * v15;
        v19 = utBase64ToIndex(v6[2]);
        v18 = v19;
        if ( v19 == -1 )
          goto LABEL_23;
        v16[1] = v20 + ((unsigned __int8)v19 >> 2);
      }
      if ( v6[3] != 61 )
      {
        v16[2] = v18 << 6;
        v21 = utBase64ToIndex(v6[3]);
        if ( v21 == -1 )
        {
LABEL_23:
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
0x18000a0e0  push    rbx
0x18000a0e2  push    rbp
0x18000a0e3  push    rsi
0x18000a0e4  push    rdi
0x18000a0e5  push    r12
0x18000a0e7  push    r14
0x18000a0e9  push    r15
0x18000a0eb  sub     rsp, 20h
0x18000a0ef  xor     r12d, r12d
0x18000a0f2  mov     r15, r8
0x18000a0f5  mov     r14, rdx
0x18000a0f8  mov     rdi, rcx
0x18000a0fb  test    rcx, rcx
0x18000a0fe  jz      loc_18000A240
0x18000a104  test    rdx, rdx
0x18000a107  jz      loc_18000A240
0x18000a10d  test    r8, r8
0x18000a110  jz      loc_18000A240
0x18000a116  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a11a  inc     rsi
0x18000a11d  cmp     [rcx+rsi*2], r12w
0x18000a122  jnz     short loc_18000A11A
0x18000a124  mov     eax, esi
0x18000a126  mov     ecx, 4
0x18000a12b  cdq
0x18000a12c  idiv    ecx
0x18000a12e  test    edx, edx
0x18000a130  jz      short loc_18000A146
0x18000a132  mov     eax, 80004005h
0x18000a137  add     rsp, 20h
0x18000a13b  pop     r15
0x18000a13d  pop     r14
0x18000a13f  pop     r12
0x18000a141  pop     rdi
0x18000a142  pop     rsi
0x18000a143  pop     rbp
0x18000a144  pop     rbx
0x18000a145  retn
0x18000a146  mov     eax, esi
0x18000a148  sar     eax, 2
0x18000a14b  lea     ecx, [rax+rax*2]
0x18000a14e  movsxd  rax, esi
0x18000a151  lea     edx, [rcx-1]
0x18000a154  cmp     word ptr [rdi+rax*2-2], 3Dh ; '='
0x18000a15a  cmovnz  edx, ecx
0x18000a15d  cmp     word ptr [rdi+rax*2-4], 3Dh ; '='
0x18000a163  lea     ebp, [rdx-1]
0x18000a166  cmovnz  ebp, edx
0x18000a169  movsxd  rcx, ebp; cb
0x18000a16c  call    cs:__imp_CoTaskMemAlloc
0x18000a172  mov     r8, rax
0x18000a175  test    rax, rax
0x18000a178  jz      loc_18000A220
0x18000a17e  mov     ebx, r12d
0x18000a181  mov     [r14], rax
0x18000a184  mov     [r15], ebp
0x18000a187  test    esi, esi
0x18000a189  jle     loc_18000A239
0x18000a18f  movzx   ecx, word ptr [rdi]; unsigned __int16
0x18000a192  call    ?utBase64ToIndex@@YAHG@Z; utBase64ToIndex(ushort)
0x18000a197  mov     r9d, eax
0x18000a19a  shl     r9b, 2
0x18000a19e  mov     [r8], r9b
0x18000a1a1  movzx   ecx, word ptr [rdi+2]; unsigned __int16
0x18000a1a5  call    ?utBase64ToIndex@@YAHG@Z; utBase64ToIndex(ushort)
0x18000a1aa  mov     edx, eax
0x18000a1ac  cmp     eax, 0FFFFFFFFh
0x18000a1af  jz      short loc_18000A219
0x18000a1b1  mov     cl, dl
0x18000a1b3  shr     cl, 4
0x18000a1b6  add     cl, r9b
0x18000a1b9  mov     [r8], cl
0x18000a1bc  cmp     word ptr [rdi+4], 3Dh ; '='
0x18000a1c1  jz      short loc_18000A1E7
0x18000a1c3  shl     dl, 4
0x18000a1c6  mov     [r8+1], dl
0x18000a1ca  mov     r9b, dl
0x18000a1cd  movzx   ecx, word ptr [rdi+4]; unsigned __int16
0x18000a1d1  call    ?utBase64ToIndex@@YAHG@Z; utBase64ToIndex(ushort)
0x18000a1d6  mov     edx, eax
0x18000a1d8  cmp     eax, 0FFFFFFFFh
0x18000a1db  jz      short loc_18000A219
0x18000a1dd  shr     al, 2
0x18000a1e0  add     al, r9b
0x18000a1e3  mov     [r8+1], al
0x18000a1e7  cmp     word ptr [rdi+6], 3Dh ; '='
0x18000a1ec  jz      short loc_18000A209
0x18000a1ee  shl     dl, 6
0x18000a1f1  mov     [r8+2], dl
0x18000a1f5  movzx   ecx, word ptr [rdi+6]; unsigned __int16
0x18000a1f9  call    ?utBase64ToIndex@@YAHG@Z; utBase64ToIndex(ushort)
0x18000a1fe  cmp     eax, 0FFFFFFFFh
0x18000a201  jz      short loc_18000A219
0x18000a203  add     al, dl
0x18000a205  mov     [r8+2], al
0x18000a209  sub     esi, 4
0x18000a20c  add     rdi, 8
0x18000a210  add     r8, 3
0x18000a214  jmp     loc_18000A187
0x18000a219  mov     ebx, 80004005h
0x18000a21e  jmp     short loc_18000A225
0x18000a220  mov     ebx, 8007000Eh
0x18000a225  mov     rcx, [r14]; pv
0x18000a228  test    rcx, rcx
0x18000a22b  jz      short loc_18000A233
0x18000a22d  call    cs:__imp_CoTaskMemFree
0x18000a233  mov     [r14], r12
0x18000a236  mov     [r15], r12d
0x18000a239  mov     eax, ebx
0x18000a23b  jmp     loc_18000A137
0x18000a240  mov     eax, 80070057h
0x18000a245  jmp     loc_18000A137
```
