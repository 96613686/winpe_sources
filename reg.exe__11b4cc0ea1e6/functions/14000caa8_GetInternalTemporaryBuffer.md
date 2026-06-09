# GetInternalTemporaryBuffer

- ea: `0x14000caa8`
- end: `0x14000ccbd`
- name: `GetInternalTemporaryBuffer`
- size: `533`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14000cd48`
- `0x14000cf88`
- `0x14000d010`
- `0x14000d6ec`
- `0x14000daa4`
- `0x14000e020`

## callees

- `0x140001cc6`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000caa8`
- `0x14000d114`
- `0x14000d7a8`
- `0x14000e3e0`
- `0x14000e450`
- `0x14000e6bc`
- `0x14000e838`
- `0x14000e87c`
- `0x14000e8c8`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000cc0c`
- `api-ms-win-crt-private-l1-1-0!_o__memicmp` at `0x14000cc0c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000cc22`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000cc22`

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
  __int64 v24; // rdx
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
    Item = _DynArrayGetItem(qword_140014218, v9, 0);
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
    v18 = _DynArrayGetItem(qword_140014218, 3, 0);
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
    if ( (unsigned int)v24 >= v23 )
      goto LABEL_36;
  }
  if ( v23 )
  {
    v26 = (unsigned int)ReallocateMemory(v16 + 16, v24) == 0;
  }
  else
  {
    v25 = AllocateMemory((unsigned int)v24);
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
0x14000caa8  mov     [rsp+arg_0], rbx
0x14000caad  mov     [rsp+arg_10], rbp
0x14000cab2  push    rsi
0x14000cab3  push    rdi
0x14000cab4  push    r14
0x14000cab6  sub     rsp, 20h
0x14000caba  mov     r14d, r9d
0x14000cabd  mov     edi, r8d
0x14000cac0  mov     rbp, rdx
0x14000cac3  mov     esi, ecx
0x14000cac5  test    rdx, rdx
0x14000cac8  jnz     short loc_14000CAD3
0x14000caca  test    r8d, r8d
0x14000cacd  jz      loc_14000CCA8
0x14000cad3  call    InitGlobals
0x14000cad8  test    eax, eax
0x14000cada  jz      loc_14000CCA8
0x14000cae0  mov     edx, 3
0x14000cae5  call    DynArrayGetCount2
0x14000caea  mov     r10d, eax
0x14000caed  cmp     eax, esi
0x14000caef  ja      short loc_14000CB41
0x14000caf1  mov     rcx, cs:qword_140014218
0x14000caf8  xor     r8d, r8d
0x14000cafb  call    __DynArrayGetItem
0x14000cb00  test    rax, rax
0x14000cb03  jz      loc_14000CCA8
0x14000cb09  cmp     dword ptr [rax+4], 10000h
0x14000cb10  jz      short loc_14000CB1F
0x14000cb12  cmp     dword ptr [rax+4], 80000h
0x14000cb19  jnz     loc_14000CCA8
0x14000cb1f  mov     rcx, [rax+10h]
0x14000cb23  test    rcx, rcx
0x14000cb26  jz      loc_14000CCA8
0x14000cb2c  mov     edx, esi
0x14000cb2e  sub     edx, r10d
0x14000cb31  inc     edx
0x14000cb33  call    DynArrayAddColumns
0x14000cb38  cmp     eax, 0FFFFFFFFh
0x14000cb3b  jz      loc_14000CCA8
0x14000cb41  mov     r8d, esi
0x14000cb44  call    DynArrayGetItemType2
0x14000cb49  test    eax, eax
0x14000cb4b  jz      short loc_14000CB66
0x14000cb4d  mov     r8d, esi
0x14000cb50  call    DynArrayItem2
0x14000cb55  mov     rbx, rax
0x14000cb58  test    rax, rax
0x14000cb5b  jz      loc_14000CCA8
0x14000cb61  jmp     loc_14000CBFC
0x14000cb66  mov     ecx, 18h; dwBytes
0x14000cb6b  call    AllocateMemory
0x14000cb70  mov     [rsp+38h+arg_8], rax
0x14000cb75  mov     rbx, rax
0x14000cb78  test    rax, rax
0x14000cb7b  jz      loc_14000CCA8
0x14000cb81  mov     dword ptr [rax+8], 0
0x14000cb88  mov     rcx, rax
0x14000cb8b  mov     qword ptr [rax+10h], 0
0x14000cb93  call    StringCopyA
0x14000cb98  mov     rcx, cs:qword_140014218
0x14000cb9f  xor     r8d, r8d
0x14000cba2  lea     edx, [r8+3]
0x14000cba6  call    __DynArrayGetItem
0x14000cbab  test    rax, rax
0x14000cbae  jz      loc_14000CC9E
0x14000cbb4  cmp     dword ptr [rax+4], 80000h
0x14000cbbb  jnz     loc_14000CC9E
0x14000cbc1  mov     rcx, [rax+10h]
0x14000cbc5  mov     edx, esi
0x14000cbc7  call    __DynArrayGetItem
0x14000cbcc  test    rax, rax
0x14000cbcf  jnz     short loc_14000CBD5
0x14000cbd1  xor     eax, eax
0x14000cbd3  jmp     short loc_14000CBF4
0x14000cbd5  cmp     dword ptr [rax+4], 10000h
0x14000cbdc  jz      short loc_14000CBEB
0x14000cbde  cmp     [rax+4], r8d
0x14000cbe2  jnz     short loc_14000CBD1
0x14000cbe4  mov     dword ptr [rax+4], 10000h
0x14000cbeb  mov     [rax+10h], rbx
0x14000cbef  mov     eax, 1
0x14000cbf4  test    eax, eax
0x14000cbf6  jz      loc_14000CC9E
0x14000cbfc  mov     r8d, 7
0x14000cc02  lea     rdx, cszSignature; "BUFFER"
0x14000cc09  mov     rcx, rbx
0x14000cc0c  call    cs:__imp__o__memicmp
0x14000cc12  test    eax, eax
0x14000cc14  jnz     loc_14000CCA8
0x14000cc1a  test    rbp, rbp
0x14000cc1d  jz      short loc_14000CC2B
0x14000cc1f  mov     rcx, rbp; lpString
0x14000cc22  call    cs:__imp_lstrlenW
0x14000cc28  lea     edi, [rax+1]
0x14000cc2b  mov     eax, [rbx+8]
0x14000cc2e  cmp     edi, eax
0x14000cc30  ja      short loc_14000CC43
0x14000cc32  cmp     edi, 100h
0x14000cc38  jbe     short loc_14000CC6A
0x14000cc3a  lea     edx, [rdi+rdi]
0x14000cc3d  cmp     edx, eax
0x14000cc3f  jnb     short loc_14000CC6A
0x14000cc41  jmp     short loc_14000CC46
0x14000cc43  lea     edx, [rdi+rdi]
0x14000cc46  test    eax, eax
0x14000cc48  jnz     short loc_14000CC5A
0x14000cc4a  mov     ecx, edx; dwBytes
0x14000cc4c  call    AllocateMemory
0x14000cc51  mov     [rbx+10h], rax
0x14000cc55  test    rax, rax
0x14000cc58  jmp     short loc_14000CC65
0x14000cc5a  lea     rcx, [rbx+10h]
0x14000cc5e  call    ReallocateMemory
0x14000cc63  test    eax, eax
0x14000cc65  jz      short loc_14000CCA8
0x14000cc67  mov     [rbx+8], edi
0x14000cc6a  mov     rcx, [rbx+10h]; void *
0x14000cc6e  test    rcx, rcx
0x14000cc71  jz      short loc_14000CCA8
0x14000cc73  test    rbp, rbp
0x14000cc76  jz      short loc_14000CC85
0x14000cc78  mov     r8d, edi
0x14000cc7b  mov     rdx, rbp
0x14000cc7e  call    StringCopyW
0x14000cc83  jmp     short loc_14000CC98
0x14000cc85  cmp     r14d, 1
0x14000cc89  jnz     short loc_14000CC98
0x14000cc8b  mov     r8d, edi
0x14000cc8e  xor     edx, edx; Val
0x14000cc90  add     r8, r8; Size
0x14000cc93  call    memset_0
0x14000cc98  mov     rax, [rbx+10h]
0x14000cc9c  jmp     short loc_14000CCAA
0x14000cc9e  lea     rcx, [rsp+38h+arg_8]
0x14000cca3  call    FreeMemory
0x14000cca8  xor     eax, eax
0x14000ccaa  mov     rbx, [rsp+38h+arg_0]
0x14000ccaf  mov     rbp, [rsp+38h+arg_10]
0x14000ccb4  add     rsp, 20h
0x14000ccb8  pop     r14
0x14000ccba  pop     rdi
0x14000ccbb  pop     rsi
0x14000ccbc  retn
```
