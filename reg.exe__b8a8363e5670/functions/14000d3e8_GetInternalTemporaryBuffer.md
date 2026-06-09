# GetInternalTemporaryBuffer

- ea: `0x14000d3e8`
- end: `0x14000d60a`
- name: `GetInternalTemporaryBuffer`
- size: `546`
- prototype: ``
- caller_count: `6`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000d694`
- `0x14000d900`
- `0x14000d990`
- `0x14000e190`
- `0x14000e600`
- `0x14000ec2c`

## callees

- `0x140001cc6`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d3e8`
- `0x14000dab0`
- `0x14000e268`
- `0x14000f04c`
- `0x14000f0c0`
- `0x14000f350`
- `0x14000f4d8`
- `0x14000f51c`
- `0x14000f568`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000d54c`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000d54c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d568`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000d568`

## pseudocode

```c
__int64 __fastcall GetInternalTemporaryBuffer(unsigned int a1, WCHAR *a2, unsigned int a3, int a4)
{
  unsigned int v5; // edi
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 Item; // rax
  int v12; // r10d
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  _DWORD *Memory; // rax
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 v20; // rax
  int v21; // r8d
  int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // edx
  LPVOID v25; // rax
  bool v26; // zf
  _WORD *v27; // rcx
  _DWORD *v29; // [rsp+48h] [rbp+10h] BYREF

  v5 = a3;
  if ( !a2 && !a3 )
    return 0;
  if ( !(unsigned int)InitGlobals() )
    return 0;
  if ( (unsigned int)DynArrayGetCount2(v8, 3) <= a1 )
  {
    Item = _DynArrayGetItem(qword_140015218, v9, 0);
    if ( !Item || *(_DWORD *)(Item + 4) != 0x10000 && *(_DWORD *)(Item + 4) != 0x80000 )
      return 0;
    v13 = *(_QWORD *)(Item + 16);
    if ( !v13 || (unsigned int)DynArrayAddColumns(v13, a1 - v12 + 1) == -1 )
      return 0;
  }
  if ( !(unsigned int)DynArrayGetItemType2(v10, v9, a1) )
  {
    Memory = AllocateMemory(0x18u);
    v29 = Memory;
    v16 = (__int64)Memory;
    if ( !Memory )
      return 0;
    Memory[2] = 0;
    *((_QWORD *)Memory + 2) = 0;
    StringCopyA(Memory);
    v18 = _DynArrayGetItem(qword_140015218, 3, 0);
    if ( !v18 || *(_DWORD *)(v18 + 4) != 0x80000 )
    {
LABEL_42:
      FreeMemory(&v29);
      return 0;
    }
    v20 = _DynArrayGetItem(*(_QWORD *)(v18 + 16), a1, v19);
    if ( !v20 )
      goto LABEL_17;
    if ( *(_DWORD *)(v20 + 4) != 0x10000 )
    {
      if ( *(_DWORD *)(v20 + 4) != v21 )
      {
LABEL_17:
        v22 = 0;
        goto LABEL_22;
      }
      *(_DWORD *)(v20 + 4) = 0x10000;
    }
    *(_QWORD *)(v20 + 16) = v16;
    v22 = 1;
LABEL_22:
    if ( v22 )
      goto LABEL_23;
    goto LABEL_42;
  }
  v16 = DynArrayItem2(v15, v14, a1);
  if ( !v16 )
    return 0;
LABEL_23:
  if ( (unsigned int)_o__memicmp(v16, "BUFFER", 7) )
    return 0;
  if ( a2 )
    v5 = lstrlenW(a2) + 1;
  v23 = *(_DWORD *)(v16 + 8);
  if ( v5 > v23 )
  {
    v24 = 2 * v5;
  }
  else
  {
    if ( v5 <= 0x100 )
      goto LABEL_36;
    v24 = 2 * v5;
    if ( 2 * v5 >= v23 )
      goto LABEL_36;
  }
  if ( v23 )
  {
    v26 = (unsigned int)ReallocateMemory((LPVOID *)(v16 + 16), v24) == 0;
  }
  else
  {
    v25 = AllocateMemory(v24);
    *(_QWORD *)(v16 + 16) = v25;
    v26 = v25 == 0;
  }
  if ( v26 )
    return 0;
  *(_DWORD *)(v16 + 8) = v5;
LABEL_36:
  v27 = *(_WORD **)(v16 + 16);
  if ( !v27 )
    return 0;
  if ( a2 )
  {
    StringCopyW(v27, a2, v5);
  }
  else if ( a4 == 1 )
  {
    memset_0(v27, 0, 2LL * v5);
  }
  return *(_QWORD *)(v16 + 16);
}

```

## disassembly

```asm
0x14000d3e8  mov     [rsp+arg_0], rbx
0x14000d3ed  mov     [rsp+arg_10], rbp
0x14000d3f2  push    rsi
0x14000d3f3  push    rdi
0x14000d3f4  push    r14
0x14000d3f6  sub     rsp, 20h
0x14000d3fa  mov     r14d, r9d
0x14000d3fd  mov     edi, r8d
0x14000d400  mov     rbp, rdx
0x14000d403  mov     esi, ecx
0x14000d405  test    rdx, rdx
0x14000d408  jnz     short loc_14000D413
0x14000d40a  test    r8d, r8d
0x14000d40d  jz      loc_14000D5F4
0x14000d413  call    InitGlobals
0x14000d418  test    eax, eax
0x14000d41a  jz      loc_14000D5F4
0x14000d420  mov     edx, 3
0x14000d425  call    DynArrayGetCount2
0x14000d42a  mov     r10d, eax
0x14000d42d  cmp     eax, esi
0x14000d42f  ja      short loc_14000D481
0x14000d431  mov     rcx, cs:qword_140015218
0x14000d438  xor     r8d, r8d
0x14000d43b  call    __DynArrayGetItem
0x14000d440  test    rax, rax
0x14000d443  jz      loc_14000D5F4
0x14000d449  cmp     dword ptr [rax+4], 10000h
0x14000d450  jz      short loc_14000D45F
0x14000d452  cmp     dword ptr [rax+4], 80000h
0x14000d459  jnz     loc_14000D5F4
0x14000d45f  mov     rcx, [rax+10h]
0x14000d463  test    rcx, rcx
0x14000d466  jz      loc_14000D5F4
0x14000d46c  mov     edx, esi
0x14000d46e  sub     edx, r10d
0x14000d471  inc     edx
0x14000d473  call    DynArrayAddColumns
0x14000d478  cmp     eax, 0FFFFFFFFh
0x14000d47b  jz      loc_14000D5F4
0x14000d481  mov     r8d, esi
0x14000d484  call    DynArrayGetItemType2
0x14000d489  test    eax, eax
0x14000d48b  jz      short loc_14000D4A6
0x14000d48d  mov     r8d, esi
0x14000d490  call    DynArrayItem2
0x14000d495  mov     rbx, rax
0x14000d498  test    rax, rax
0x14000d49b  jz      loc_14000D5F4
0x14000d4a1  jmp     loc_14000D53C
0x14000d4a6  mov     ecx, 18h; dwBytes
0x14000d4ab  call    AllocateMemory
0x14000d4b0  mov     [rsp+38h+arg_8], rax
0x14000d4b5  mov     rbx, rax
0x14000d4b8  test    rax, rax
0x14000d4bb  jz      loc_14000D5F4
0x14000d4c1  mov     dword ptr [rax+8], 0
0x14000d4c8  mov     rcx, rax
0x14000d4cb  mov     qword ptr [rax+10h], 0
0x14000d4d3  call    StringCopyA
0x14000d4d8  mov     rcx, cs:qword_140015218
0x14000d4df  xor     r8d, r8d
0x14000d4e2  lea     edx, [r8+3]
0x14000d4e6  call    __DynArrayGetItem
0x14000d4eb  test    rax, rax
0x14000d4ee  jz      loc_14000D5EA
0x14000d4f4  cmp     dword ptr [rax+4], 80000h
0x14000d4fb  jnz     loc_14000D5EA
0x14000d501  mov     rcx, [rax+10h]
0x14000d505  mov     edx, esi
0x14000d507  call    __DynArrayGetItem
0x14000d50c  test    rax, rax
0x14000d50f  jnz     short loc_14000D515
0x14000d511  xor     eax, eax
0x14000d513  jmp     short loc_14000D534
0x14000d515  cmp     dword ptr [rax+4], 10000h
0x14000d51c  jz      short loc_14000D52B
0x14000d51e  cmp     [rax+4], r8d
0x14000d522  jnz     short loc_14000D511
0x14000d524  mov     dword ptr [rax+4], 10000h
0x14000d52b  mov     [rax+10h], rbx
0x14000d52f  mov     eax, 1
0x14000d534  test    eax, eax
0x14000d536  jz      loc_14000D5EA
0x14000d53c  mov     r8d, 7
0x14000d542  lea     rdx, cszSignature; "BUFFER"
0x14000d549  mov     rcx, rbx
0x14000d54c  call    cs:__imp__o__memicmp
0x14000d553  nop     dword ptr [rax+rax+00h]
0x14000d558  test    eax, eax
0x14000d55a  jnz     loc_14000D5F4
0x14000d560  test    rbp, rbp
0x14000d563  jz      short loc_14000D577
0x14000d565  mov     rcx, rbp; lpString
0x14000d568  call    cs:__imp_lstrlenW
0x14000d56f  nop     dword ptr [rax+rax+00h]
0x14000d574  lea     edi, [rax+1]
0x14000d577  mov     eax, [rbx+8]
0x14000d57a  cmp     edi, eax
0x14000d57c  ja      short loc_14000D58F
0x14000d57e  cmp     edi, 100h
0x14000d584  jbe     short loc_14000D5B6
0x14000d586  lea     edx, [rdi+rdi]
0x14000d589  cmp     edx, eax
0x14000d58b  jnb     short loc_14000D5B6
0x14000d58d  jmp     short loc_14000D592
0x14000d58f  lea     edx, [rdi+rdi]
0x14000d592  test    eax, eax
0x14000d594  jnz     short loc_14000D5A6
0x14000d596  mov     ecx, edx; dwBytes
0x14000d598  call    AllocateMemory
0x14000d59d  mov     [rbx+10h], rax
0x14000d5a1  test    rax, rax
0x14000d5a4  jmp     short loc_14000D5B1
0x14000d5a6  lea     rcx, [rbx+10h]
0x14000d5aa  call    ReallocateMemory
0x14000d5af  test    eax, eax
0x14000d5b1  jz      short loc_14000D5F4
0x14000d5b3  mov     [rbx+8], edi
0x14000d5b6  mov     rcx, [rbx+10h]; void *
0x14000d5ba  test    rcx, rcx
0x14000d5bd  jz      short loc_14000D5F4
0x14000d5bf  test    rbp, rbp
0x14000d5c2  jz      short loc_14000D5D1
0x14000d5c4  mov     r8d, edi
0x14000d5c7  mov     rdx, rbp
0x14000d5ca  call    StringCopyW
0x14000d5cf  jmp     short loc_14000D5E4
0x14000d5d1  cmp     r14d, 1
0x14000d5d5  jnz     short loc_14000D5E4
0x14000d5d7  mov     r8d, edi
0x14000d5da  xor     edx, edx; Val
0x14000d5dc  add     r8, r8; Size
0x14000d5df  call    memset_0
0x14000d5e4  mov     rax, [rbx+10h]
0x14000d5e8  jmp     short loc_14000D5F6
0x14000d5ea  lea     rcx, [rsp+38h+arg_8]
0x14000d5ef  call    FreeMemory
0x14000d5f4  xor     eax, eax
0x14000d5f6  mov     rbx, [rsp+38h+arg_0]
0x14000d5fb  mov     rbp, [rsp+38h+arg_10]
0x14000d600  add     rsp, 20h
0x14000d604  pop     r14
0x14000d606  pop     rdi
0x14000d607  pop     rsi
0x14000d608  retn
```
