# CreateNewEventEntry

- ea: `0x18001b91c`
- end: `0x18001bb61`
- name: `CreateNewEventEntry`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001beb0`

## callees

- `0x18001b91c`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b9b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b9b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b9c8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001b9c8`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(__int128 *a1, unsigned __int8 a2, __int64 a3, char a4, int a5, char **a6)
{
  __int64 v6; // r10
  __int64 v7; // r11
  unsigned __int8 v8; // r12
  unsigned __int8 v9; // bl
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v15; // rdi
  SIZE_T v16; // rbx
  HANDLE ProcessHeap; // rax
  char *v18; // rax
  int v19; // edx
  char *v20; // rbp
  char *v21; // rsi
  unsigned __int8 v22; // r15
  bool v23; // zf
  unsigned __int8 v24; // r14
  __int64 v25; // r12
  size_t v26; // r8
  char *v27; // rax
  unsigned __int64 v28; // rcx
  char *v29; // rdi
  __int128 v30; // xmm0
  __int64 v31; // r15
  __int64 v32; // r14
  size_t v33; // r8
  char *v34; // rbp
  int v35; // edx
  int v36; // [rsp+20h] [rbp-48h]
  char *v37; // [rsp+28h] [rbp-40h]

  v6 = 0;
  v7 = 0;
  v8 = a2;
  v9 = 0;
  *a6 = 0;
  if ( a2 )
  {
    do
    {
      v12 = *(unsigned int *)(a3 + 16LL * v9 + 8);
      if ( v9 >= 2u )
        v6 += v12;
      v13 = v12 + v7;
      if ( v9 >= 2u )
        v13 = v7;
      ++v9;
      v7 = v13;
    }
    while ( v9 < a2 );
    if ( (unsigned __int64)(v6 + v13) > 0xFFFF )
      return 534;
  }
  v15 = 16LL * a2;
  v16 = v6 + v15 + 46;
  if ( !v16 )
    return 8;
  ProcessHeap = GetProcessHeap();
  v18 = (char *)HeapAlloc(ProcessHeap, 8u, v16);
  v20 = v18;
  if ( !v18 )
    return 8;
  if ( v15 && v16 >= v15 )
  {
    v21 = &v18[v15];
    v16 -= v15;
  }
  else
  {
    v21 = v18;
    v20 = 0;
  }
  v22 = 0;
  v23 = a4 == -2;
  v24 = a4 + 2;
  LOBYTE(v19) = v24;
  v36 = v19;
  if ( !v23 )
  {
    v25 = 0;
    do
    {
      if ( v22 >= 2u )
      {
        v26 = *(unsigned int *)(a3 + 16 * v25 + 8);
        if ( *(_DWORD *)(a3 + 16 * v25 + 8) && v16 >= v26 )
        {
          v27 = v21;
          v21 += v26;
          v16 -= v26;
        }
        else
        {
          v27 = 0;
        }
        v37 = v27;
        memcpy_0(v27, *(const void **)(a3 + 16 * v25), v26);
        *(_QWORD *)&v20[16 * v25] = v37;
        *(_DWORD *)&v20[16 * v25 + 12] = *(_DWORD *)(a3 + 16 * v25 + 12);
        *(_DWORD *)&v20[16 * v25 + 8] = *(_DWORD *)(a3 + 16 * v25 + 8);
      }
      else
      {
        *(_OWORD *)&v20[16 * v25] = *(_OWORD *)(a3 + 16 * v25);
      }
      ++v22;
      ++v25;
    }
    while ( v22 < v24 );
    v8 = a2;
    LOBYTE(v19) = v36;
  }
  v28 = v16;
  v29 = v21;
  if ( v16 >= 0x2E )
  {
    v21 += 46;
    v16 -= 46LL;
  }
  if ( v28 < 0x2E )
    v29 = 0;
  *((_QWORD *)v29 + 2) = v20;
  v30 = *a1;
  v29[45] = a4;
  *((_DWORD *)v29 + 10) = a5;
  v29[44] = v8;
  *(_OWORD *)v29 = v30;
  if ( (unsigned __int8)v19 < v8 )
  {
    v31 = v24;
    do
    {
      v32 = 2 * v31;
      v33 = *(unsigned int *)(a3 + 16 * v31 + 8);
      if ( *(_DWORD *)(a3 + 16 * v31 + 8) && v16 >= v33 )
      {
        v34 = v21;
        v21 += v33;
        v16 -= v33;
      }
      else
      {
        v34 = 0;
      }
      memcpy_0(v34, *(const void **)(a3 + 16 * v31++), v33);
      v35 = v36;
      LOBYTE(v35) = v36 + 1;
      v36 = v35;
      *(_QWORD *)(*((_QWORD *)v29 + 2) + 8 * v32) = v34;
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 12) = *(_DWORD *)(a3 + 8 * v32 + 12);
      *(_DWORD *)(*((_QWORD *)v29 + 2) + 8 * v32 + 8) = *(_DWORD *)(a3 + 8 * v32 + 8);
    }
    while ( (unsigned __int8)v35 < v8 );
  }
  *a6 = v29;
  return 0;
}

```

## disassembly

```asm
0x18001b91c  mov     rax, rsp
0x18001b91f  mov     [rax+18h], rbx
0x18001b923  mov     [rax+20h], r9b
0x18001b927  mov     [rax+10h], dl
0x18001b92a  mov     [rax+8], rcx
0x18001b92e  push    rbp
0x18001b92f  push    rsi
0x18001b930  push    rdi
0x18001b931  push    r12
0x18001b933  push    r13
0x18001b935  push    r14
0x18001b937  push    r15
0x18001b939  sub     rsp, 30h
0x18001b93d  mov     rax, [rsp+68h+arg_28]
0x18001b945  xor     r10d, r10d
0x18001b948  xor     r11d, r11d
0x18001b94b  movzx   r12d, dl
0x18001b94f  xor     bl, bl
0x18001b951  mov     r14b, r9b
0x18001b954  mov     r13, r8
0x18001b957  mov     [rax], r10
0x18001b95a  test    dl, dl
0x18001b95c  jz      short loc_18001B99B
0x18001b95e  movzx   eax, bl
0x18001b961  add     rax, rax
0x18001b964  cmp     bl, 2
0x18001b967  mov     ecx, [r8+rax*8+8]
0x18001b96c  lea     rax, [rcx+r10]
0x18001b970  cmovnb  r10, rax
0x18001b974  lea     rax, [rcx+r11]
0x18001b978  cmovnb  rax, r11
0x18001b97c  inc     bl
0x18001b97e  mov     r11, rax
0x18001b981  cmp     bl, r12b
0x18001b984  jb      short loc_18001B95E
0x18001b986  add     rax, r10
0x18001b989  cmp     rax, 0FFFFh
0x18001b98f  jbe     short loc_18001B99B
0x18001b991  mov     eax, 216h
0x18001b996  jmp     loc_18001BB48
0x18001b99b  mov     rdi, r12
0x18001b99e  mov     esi, 8
0x18001b9a3  shl     rdi, 4
0x18001b9a7  lea     rbx, [rdi+2Eh]
0x18001b9ab  add     rbx, r10
0x18001b9ae  jz      loc_18001BB46
0x18001b9b4  call    cs:__imp_GetProcessHeap
0x18001b9bb  nop     dword ptr [rax+rax+00h]
0x18001b9c0  mov     r8, rbx; dwBytes
0x18001b9c3  mov     edx, esi; dwFlags
0x18001b9c5  mov     rcx, rax; hHeap
0x18001b9c8  call    cs:__imp_HeapAlloc
0x18001b9cf  nop     dword ptr [rax+rax+00h]
0x18001b9d4  mov     rbp, rax
0x18001b9d7  test    rax, rax
0x18001b9da  jz      loc_18001BB46
0x18001b9e0  test    rdi, rdi
0x18001b9e3  jz      short loc_18001B9F3
0x18001b9e5  cmp     rbx, rdi
0x18001b9e8  jb      short loc_18001B9F3
0x18001b9ea  lea     rsi, [rdi+rax]
0x18001b9ee  sub     rbx, rdi
0x18001b9f1  jmp     short loc_18001B9F8
0x18001b9f3  mov     rsi, rax
0x18001b9f6  xor     ebp, ebp
0x18001b9f8  xor     r15b, r15b
0x18001b9fb  add     r14b, 2
0x18001b9ff  mov     dl, r14b
0x18001ba02  mov     [rsp+68h+var_48], edx
0x18001ba06  jz      short loc_18001BA83
0x18001ba08  xor     r12d, r12d
0x18001ba0b  mov     rdi, r12
0x18001ba0e  add     rdi, rdi
0x18001ba11  cmp     r15b, 2
0x18001ba15  jnb     short loc_18001BA25
0x18001ba17  movups  xmm0, xmmword ptr [r13+rdi*8+0]
0x18001ba1d  movdqu  xmmword ptr [rbp+rdi*8+0], xmm0
0x18001ba23  jmp     short loc_18001BA6F
0x18001ba25  mov     r8d, [r13+rdi*8+8]; Size
0x18001ba2a  test    r8, r8
0x18001ba2d  jz      short loc_18001BA3F
0x18001ba2f  cmp     rbx, r8
0x18001ba32  jb      short loc_18001BA3F
0x18001ba34  mov     rax, rsi
0x18001ba37  add     rsi, r8
0x18001ba3a  sub     rbx, r8
0x18001ba3d  jmp     short loc_18001BA41
0x18001ba3f  xor     eax, eax
0x18001ba41  mov     rdx, [r13+rdi*8+0]; Src
0x18001ba46  mov     rcx, rax; void *
0x18001ba49  mov     [rsp+68h+var_40], rax
0x18001ba4e  call    memcpy_0
0x18001ba53  mov     rax, [rsp+68h+var_40]
0x18001ba58  mov     [rbp+rdi*8+0], rax
0x18001ba5d  mov     eax, [r13+rdi*8+0Ch]
0x18001ba62  mov     [rbp+rdi*8+0Ch], eax
0x18001ba66  mov     eax, [r13+rdi*8+8]
0x18001ba6b  mov     [rbp+rdi*8+8], eax
0x18001ba6f  inc     r15b
0x18001ba72  inc     r12
0x18001ba75  cmp     r15b, r14b
0x18001ba78  jb      short loc_18001BA0B
0x18001ba7a  mov     r12b, [rsp+68h+arg_8]
0x18001ba7f  mov     edx, [rsp+68h+var_48]
0x18001ba83  mov     rcx, rbx
0x18001ba86  mov     rdi, rsi
0x18001ba89  cmp     rbx, 2Eh ; '.'
0x18001ba8d  jb      short loc_18001BA97
0x18001ba8f  add     rsi, 2Eh ; '.'
0x18001ba93  sub     rbx, 2Eh ; '.'
0x18001ba97  xor     eax, eax
0x18001ba99  cmp     rcx, 2Eh ; '.'
0x18001ba9d  cmovb   rdi, rax
0x18001baa1  mov     rax, [rsp+68h+arg_0]
0x18001baa6  mov     [rdi+10h], rbp
0x18001baaa  movups  xmm0, xmmword ptr [rax]
0x18001baad  mov     al, [rsp+68h+arg_18]
0x18001bab4  mov     [rdi+2Dh], al
0x18001bab7  mov     eax, [rsp+68h+arg_20]
0x18001babe  mov     [rdi+28h], eax
0x18001bac1  mov     [rdi+2Ch], r12b
0x18001bac5  movdqu  xmmword ptr [rdi], xmm0
0x18001bac9  cmp     dl, r12b
0x18001bacc  jnb     short loc_18001BB37
0x18001bace  movzx   r15d, r14b
0x18001bad2  mov     r14, r15
0x18001bad5  add     r14, r14
0x18001bad8  mov     r8d, [r13+r14*8+8]; Size
0x18001badd  test    r8, r8
0x18001bae0  jz      short loc_18001BAF2
0x18001bae2  cmp     rbx, r8
0x18001bae5  jb      short loc_18001BAF2
0x18001bae7  mov     rbp, rsi
0x18001baea  add     rsi, r8
0x18001baed  sub     rbx, r8
0x18001baf0  jmp     short loc_18001BAF4
0x18001baf2  xor     ebp, ebp
0x18001baf4  mov     rdx, [r13+r14*8+0]; Src
0x18001baf9  mov     rcx, rbp; void *
0x18001bafc  call    memcpy_0
0x18001bb01  mov     rax, [rdi+10h]
0x18001bb05  inc     r15
0x18001bb08  mov     edx, [rsp+68h+var_48]
0x18001bb0c  inc     dl
0x18001bb0e  mov     [rsp+68h+var_48], edx
0x18001bb12  mov     [rax+r14*8], rbp
0x18001bb16  mov     rcx, [rdi+10h]
0x18001bb1a  mov     eax, [r13+r14*8+0Ch]
0x18001bb1f  mov     [rcx+r14*8+0Ch], eax
0x18001bb24  mov     rcx, [rdi+10h]
0x18001bb28  mov     eax, [r13+r14*8+8]
0x18001bb2d  mov     [rcx+r14*8+8], eax
0x18001bb32  cmp     dl, r12b
0x18001bb35  jb      short loc_18001BAD2
0x18001bb37  mov     rax, [rsp+68h+arg_28]
0x18001bb3f  mov     [rax], rdi
0x18001bb42  xor     eax, eax
0x18001bb44  jmp     short loc_18001BB48
0x18001bb46  mov     eax, esi
0x18001bb48  mov     rbx, [rsp+68h+arg_10]
0x18001bb50  add     rsp, 30h
0x18001bb54  pop     r15
0x18001bb56  pop     r14
0x18001bb58  pop     r13
0x18001bb5a  pop     r12
0x18001bb5c  pop     rdi
0x18001bb5d  pop     rsi
0x18001bb5e  pop     rbp
0x18001bb5f  retn
```
