# PuDeleteDataFromDisplayOrder(void *,_GUID const *)

- ea: `0x1801a6194`
- end: `0x1801a62fc`
- name: `?PuDeleteDataFromDisplayOrder@@YAJPEAXPEBU_GUID@@@Z`
- size: `360`
- prototype: `__int64 __fastcall(void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801a6014`

## callees

- `0x180007159`
- `0x1801a6194`
- `0x1801a64c8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a62d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a62d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a62bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a62bc`
- `bcd!BcdOpenObject` at `0x1801a61db`
- `bcd!BcdOpenObject` at `0x1801a61db`
- `bcd!BcdCloseObject` at `0x1801a62e3`
- `bcd!BcdCloseObject` at `0x1801a62e3`
- `bcd!BcdSetElementData` at `0x1801a6294`
- `bcd!BcdSetElementData` at `0x1801a6294`
- `bcd!BcdDeleteElement` at `0x1801a629e`
- `bcd!BcdDeleteElement` at `0x1801a629e`

## pseudocode

```c
__int64 __fastcall PuDeleteDataFromDisplayOrder(void *a1, const struct _GUID *a2)
{
  int v4; // ebx
  int BcdDisplayOrder; // eax
  __int64 v6; // r8
  void *v7; // rsi
  unsigned int v8; // edi
  unsigned int v9; // r15d
  _QWORD *v10; // r9
  unsigned int i; // eax
  __int64 v12; // rcx
  HANDLE ProcessHeap; // rax
  unsigned int v14; // [rsp+58h] [rbp+38h] BYREF
  void *v15; // [rsp+60h] [rbp+40h] BYREF
  void *lpMem; // [rsp+68h] [rbp+48h] BYREF

  v15 = 0;
  lpMem = 0;
  v14 = 0;
  if ( !a2 )
    return 3221225485LL;
  v4 = BcdOpenObject(a1, &GUID_WINDOWS_BOOTMGR, &v15);
  if ( v4 >= 0 )
  {
    BcdDisplayOrder = PuGetBcdDisplayOrder(v15, (struct _GUID **)&lpMem, &v14);
    v7 = lpMem;
    v4 = BcdDisplayOrder;
    if ( BcdDisplayOrder != -1073741275 )
    {
      if ( BcdDisplayOrder < 0 || (v8 = v14) == 0 )
      {
LABEL_24:
        if ( v7 )
        {
          ProcessHeap = GetProcessHeap();
          if ( ProcessHeap )
            HeapFree(ProcessHeap, 0, v7);
        }
        goto LABEL_27;
      }
      if ( !lpMem || (v9 = v14) == 0 )
      {
        v4 = -1073741811;
        goto LABEL_24;
      }
      v10 = lpMem;
      for ( i = 0; i < v14; ++i )
      {
        v12 = *v10 - *(_QWORD *)&a2->Data1;
        if ( *v10 == *(_QWORD *)&a2->Data1 )
          v12 = v10[1] - *(_QWORD *)a2->Data4;
        if ( !v12 )
        {
          v8 = v14 - 1;
          if ( i < v14 - 1 )
            memmove_0(v10, v10 + 2, 16LL * (v14 - i - 1));
          break;
        }
        v10 += 2;
      }
      v4 = 0;
      if ( v8 == v9 )
        goto LABEL_24;
      if ( v8 )
      {
        v4 = BcdSetElementData(v15, 603979777, v7, 16 * v8);
        goto LABEL_24;
      }
      v4 = BcdDeleteElement(v15, 603979777, v6, v10);
      if ( v4 != -1073741275 )
        goto LABEL_24;
    }
    v4 = 0;
    goto LABEL_24;
  }
LABEL_27:
  if ( v15 )
    BcdCloseObject();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1801a6194  mov     [rsp-28h+arg_0], rbx
0x1801a6199  push    rbp
0x1801a619a  push    rsi
0x1801a619b  push    rdi
0x1801a619c  push    r14
0x1801a619e  push    r15
0x1801a61a0  mov     rbp, rsp
0x1801a61a3  sub     rsp, 20h
0x1801a61a7  mov     [rbp+arg_10], 0
0x1801a61af  mov     r14, rdx
0x1801a61b2  mov     [rbp+lpMem], 0
0x1801a61ba  mov     [rbp+arg_8], 0
0x1801a61c1  test    rdx, rdx
0x1801a61c4  jnz     short loc_1801A61D0
0x1801a61c6  mov     eax, 0C000000Dh
0x1801a61cb  jmp     loc_1801A62EB
0x1801a61d0  lea     r8, [rbp+arg_10]
0x1801a61d4  lea     rdx, GUID_WINDOWS_BOOTMGR
0x1801a61db  call    cs:__imp_BcdOpenObject
0x1801a61e1  mov     ebx, eax
0x1801a61e3  test    eax, eax
0x1801a61e5  js      loc_1801A62DA
0x1801a61eb  mov     rcx, [rbp+arg_10]; void *
0x1801a61ef  lea     r8, [rbp+arg_8]; unsigned int *
0x1801a61f3  lea     rdx, [rbp+lpMem]; struct _GUID **
0x1801a61f7  call    ?PuGetBcdDisplayOrder@@YAJPEAXPEAPEAU_GUID@@PEAK@Z; PuGetBcdDisplayOrder(void *,_GUID * *,ulong *)
0x1801a61fc  mov     rsi, [rbp+lpMem]
0x1801a6200  mov     ebx, eax
0x1801a6202  cmp     eax, 0C0000225h
0x1801a6207  jnz     short loc_1801A6210
0x1801a6209  xor     ebx, ebx
0x1801a620b  jmp     loc_1801A62B7
0x1801a6210  test    eax, eax
0x1801a6212  js      loc_1801A62B7
0x1801a6218  mov     edi, [rbp+arg_8]
0x1801a621b  test    edi, edi
0x1801a621d  jz      loc_1801A62B7
0x1801a6223  test    rsi, rsi
0x1801a6226  jz      loc_1801A62B2
0x1801a622c  mov     r15d, edi
0x1801a622f  test    edi, edi
0x1801a6231  jz      short loc_1801A62B2
0x1801a6233  mov     r9, rsi
0x1801a6236  xor     eax, eax
0x1801a6238  cmp     eax, edi
0x1801a623a  jnb     short loc_1801A6277
0x1801a623c  mov     rcx, [r9]
0x1801a623f  sub     rcx, [r14]
0x1801a6242  jnz     short loc_1801A624C
0x1801a6244  mov     rcx, [r9+8]
0x1801a6248  sub     rcx, [r14+8]
0x1801a624c  test    rcx, rcx
0x1801a624f  jz      short loc_1801A6259
0x1801a6251  inc     eax
0x1801a6253  add     r9, 10h
0x1801a6257  jmp     short loc_1801A6238
0x1801a6259  mov     ecx, edi
0x1801a625b  dec     edi
0x1801a625d  cmp     eax, edi
0x1801a625f  jnb     short loc_1801A6277
0x1801a6261  sub     ecx, eax
0x1801a6263  lea     rdx, [r9+10h]; Src
0x1801a6267  lea     r8d, [rcx-1]
0x1801a626b  mov     rcx, r9; void *
0x1801a626e  shl     r8, 4; Size
0x1801a6272  call    memmove_0
0x1801a6277  xor     ebx, ebx
0x1801a6279  cmp     edi, r15d
0x1801a627c  jz      short loc_1801A62B7
0x1801a627e  mov     rcx, [rbp+arg_10]
0x1801a6282  mov     edx, 24000001h
0x1801a6287  test    edi, edi
0x1801a6289  jz      short loc_1801A629E
0x1801a628b  shl     edi, 4
0x1801a628e  mov     r8, rsi
0x1801a6291  mov     r9d, edi
0x1801a6294  call    cs:__imp_BcdSetElementData
0x1801a629a  mov     ebx, eax
0x1801a629c  jmp     short loc_1801A62B7
0x1801a629e  call    cs:__imp_BcdDeleteElement
0x1801a62a4  mov     ebx, eax
0x1801a62a6  cmp     eax, 0C0000225h
0x1801a62ab  jnz     short loc_1801A62B7
0x1801a62ad  jmp     loc_1801A6209
0x1801a62b2  mov     ebx, 0C000000Dh
0x1801a62b7  test    rsi, rsi
0x1801a62ba  jz      short loc_1801A62DA
0x1801a62bc  call    cs:__imp_GetProcessHeap
0x1801a62c2  test    rax, rax
0x1801a62c5  jz      short loc_1801A62DA
0x1801a62c7  test    rsi, rsi
0x1801a62ca  jz      short loc_1801A62DA
0x1801a62cc  mov     r8, rsi; lpMem
0x1801a62cf  xor     edx, edx; dwFlags
0x1801a62d1  mov     rcx, rax; hHeap
0x1801a62d4  call    cs:__imp_HeapFree
0x1801a62da  mov     rcx, [rbp+arg_10]
0x1801a62de  test    rcx, rcx
0x1801a62e1  jz      short loc_1801A62E9
0x1801a62e3  call    cs:__imp_BcdCloseObject
0x1801a62e9  mov     eax, ebx
0x1801a62eb  mov     rbx, [rsp+20h+arg_0]
0x1801a62f0  add     rsp, 20h
0x1801a62f4  pop     r15
0x1801a62f6  pop     r14
0x1801a62f8  pop     rdi
0x1801a62f9  pop     rsi
0x1801a62fa  pop     rbp
0x1801a62fb  retn
```
