# PerflibciFindOutputInstance(PERFLIBCI_MULTI_INSTS *,_PERF_INSTANCE_HEADER *,_PERF_COUNTER_DATA *,ulong,int)

- ea: `0x180015b1c`
- end: `0x180015cec`
- name: `?PerflibciFindOutputInstance@@YAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAUPERFLIBCI_MULTI_INSTS@@PEAU_PERF_INSTANCE_HEADER@@PEAU_PERF_COUNTER_DATA@@KH@Z`
- size: `464`
- prototype: `struct PERFLIBCI_RED_BLACK_NODE *__fastcall(struct PERFLIBCI_MULTI_INSTS *, struct _PERF_INSTANCE_HEADER *, struct _PERF_COUNTER_DATA *, ULONG)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001520`

## callees

- `0x180005da0`
- `0x1800071b0`
- `0x180015b1c`
- `0x18001e431`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180015cce`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015b97`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015b97`

## pseudocode

```c
struct PERFLIBCI_RED_BLACK_NODE *__fastcall PerflibciFindOutputInstance(
        struct PERFLIBCI_MULTI_INSTS *a1,
        struct _PERF_INSTANCE_HEADER *a2,
        struct _PERF_COUNTER_DATA *a3,
        ULONG a4)
{
  struct PERFLIBCI_RED_BLACK_NODE **v6; // r12
  _QWORD *v7; // r14
  _QWORD *v8; // rdi
  const WCHAR *v9; // rcx
  __int64 v10; // rbx
  int v11; // eax
  int v12; // ebp
  ULONG InstanceId; // eax
  DWORD v14; // esi
  ULONG v15; // ecx
  ULONG v16; // eax
  _QWORD *v17; // rax
  char *v18; // rbx
  void *v19; // rcx
  unsigned int *v20; // rax
  unsigned int Size; // [rsp+88h] [rbp+20h]

  Size = a4;
  if ( !a1 || !a2 || !a3 )
  {
LABEL_32:
    v14 = 13;
    v8 = 0;
LABEL_33:
    SetLastError(v14);
    return (struct PERFLIBCI_RED_BLACK_NODE *)v8;
  }
  v6 = (struct PERFLIBCI_RED_BLACK_NODE **)((char *)a1 + 8);
  v7 = 0;
  v8 = (_QWORD *)*((_QWORD *)a1 + 1);
  v9 = (const WCHAR *)&a2[1];
  if ( v8 )
  {
    while ( 1 )
    {
      v10 = v8[4] + 8LL;
      if ( v8[4] == -8 )
        goto LABEL_32;
      v11 = CompareStringOrdinal(v9, -1, (LPCWCH)(v8[4] + 16LL), -1, 1);
      v12 = v11 - 2;
      if ( v11 == 2 )
      {
        InstanceId = a2->InstanceId;
        if ( InstanceId >= *(_DWORD *)(v10 + 4) )
        {
          if ( InstanceId <= *(_DWORD *)(v10 + 4) )
            return (struct PERFLIBCI_RED_BLACK_NODE *)v8;
          v12 = 1;
        }
        else
        {
          v12 = -1;
        }
      }
      v7 = v8;
      if ( v12 >= 0 )
        ++v8;
      v14 = 0;
      v8 = (_QWORD *)*v8;
      if ( !v8 )
      {
        a4 = Size;
        goto LABEL_17;
      }
      v9 = (const WCHAR *)&a2[1];
    }
  }
  v14 = 0;
  v12 = 0;
LABEL_17:
  v15 = a2->Size + 56;
  if ( a2->Size < v15 && (v16 = v15 + a4, v15 <= v15 + a4) && a4 <= v16 && (v17 = operator new(v16), (v8 = v17) != 0) )
  {
    v18 = (char *)(v17 + 7);
    v19 = v17 + 7;
    v17[4] = v17 + 6;
    v17[3] = *(_QWORD *)a1;
    *(_QWORD *)a1 = v17;
    v20 = (unsigned int *)v17[4];
    v8[2] = v7;
    *((_DWORD *)v8 + 10) = 1;
    *v20 = Size;
    memcpy_0(v19, a2, a2->Size);
    memcpy_0(&v18[a2->Size], a3, Size);
    if ( v7 )
    {
      if ( v12 >= 0 )
        v7[1] = v8;
      else
        *v7 = v8;
    }
    else
    {
      *v6 = (struct PERFLIBCI_RED_BLACK_NODE *)v8;
    }
    PerflibciInsertRedBlackNode(v6, (struct PERFLIBCI_RED_BLACK_NODE *)v8);
    *((_DWORD *)*v6 + 10) = 0;
  }
  else
  {
    v14 = 14;
    v8 = 0;
  }
  if ( !v8 )
  {
    if ( !v14 )
      v14 = 87;
    goto LABEL_33;
  }
  return (struct PERFLIBCI_RED_BLACK_NODE *)v8;
}

```

## disassembly

```asm
0x180015b1c  mov     [rsp+arg_0], rbx
0x180015b21  mov     dword ptr [rsp+Size], r9d
0x180015b26  mov     [rsp+Src], r8
0x180015b2b  push    rbp
0x180015b2c  push    rsi
0x180015b2d  push    rdi
0x180015b2e  push    r12
0x180015b30  push    r13
0x180015b32  push    r14
0x180015b34  push    r15
0x180015b36  sub     rsp, 30h
0x180015b3a  mov     rax, r8
0x180015b3d  mov     r15, rdx
0x180015b40  mov     r13, rcx
0x180015b43  test    rcx, rcx
0x180015b46  jz      loc_180015CC5
0x180015b4c  test    rdx, rdx
0x180015b4f  jz      loc_180015CC5
0x180015b55  test    rax, rax
0x180015b58  jz      loc_180015CC5
0x180015b5e  lea     r12, [rcx+8]
0x180015b62  xor     r14d, r14d
0x180015b65  mov     rdi, [r12]
0x180015b69  lea     rcx, [rdx+8]; lpString1
0x180015b6d  test    rdi, rdi
0x180015b70  jz      loc_180015C85
0x180015b76  mov     rbx, [rdi+20h]
0x180015b7a  add     rbx, 8
0x180015b7e  jz      loc_180015CC5
0x180015b84  or      r9d, 0FFFFFFFFh; cchCount2
0x180015b88  mov     [rsp+68h+bIgnoreCase], 1; bIgnoreCase
0x180015b90  or      edx, r9d; cchCount1
0x180015b93  lea     r8, [rbx+8]; lpString2
0x180015b97  call    cs:__imp_CompareStringOrdinal
0x180015b9d  lea     ebp, [rax-2]
0x180015ba0  test    ebp, ebp
0x180015ba2  jnz     short loc_180015BB9
0x180015ba4  mov     eax, [r15+4]
0x180015ba8  cmp     eax, [rbx+4]
0x180015bab  jnb     short loc_180015BB2
0x180015bad  or      ebp, 0FFFFFFFFh
0x180015bb0  jmp     short loc_180015BB9
0x180015bb2  jbe     short loc_180015BD6
0x180015bb4  mov     ebp, 1
0x180015bb9  test    ebp, ebp
0x180015bbb  lea     rax, [rdi+8]
0x180015bbf  mov     r14, rdi
0x180015bc2  cmovns  rdi, rax
0x180015bc6  xor     esi, esi
0x180015bc8  mov     rdi, [rdi]
0x180015bcb  test    rdi, rdi
0x180015bce  jz      short loc_180015BE3
0x180015bd0  lea     rcx, [r15+8]
0x180015bd4  jmp     short loc_180015B76
0x180015bd6  xor     ebp, ebp
0x180015bd8  xor     esi, esi
0x180015bda  test    rdi, rdi
0x180015bdd  jnz     loc_180015CD4
0x180015be3  mov     r9d, dword ptr [rsp+68h+Size]
0x180015beb  mov     eax, [r15]
0x180015bee  lea     ecx, [rax+38h]
0x180015bf1  cmp     eax, ecx
0x180015bf3  jnb     loc_180015CB0
0x180015bf9  lea     eax, [rcx+r9]
0x180015bfd  cmp     ecx, eax
0x180015bff  ja      loc_180015CB0
0x180015c05  cmp     r9d, eax
0x180015c08  ja      loc_180015CB0
0x180015c0e  mov     ecx, eax
0x180015c10  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180015c15  mov     rdi, rax
0x180015c18  test    rax, rax
0x180015c1b  jz      loc_180015CB0
0x180015c21  lea     rbx, [rax+38h]
0x180015c25  mov     rdx, r15; Src
0x180015c28  add     rax, 30h ; '0'
0x180015c2c  mov     rcx, rbx; void *
0x180015c2f  mov     [rdi+20h], rax
0x180015c33  mov     rax, [r13+0]
0x180015c37  mov     [rdi+18h], rax
0x180015c3b  mov     [r13+0], rdi
0x180015c3f  mov     rax, [rdi+20h]
0x180015c43  mov     r13d, dword ptr [rsp+68h+Size]
0x180015c4b  mov     [rdi+10h], r14
0x180015c4f  mov     dword ptr [rdi+28h], 1
0x180015c56  mov     [rax], r13d
0x180015c59  mov     r8d, [r15]; Size
0x180015c5c  call    memcpy_0
0x180015c61  mov     ecx, [r15]
0x180015c64  mov     r8d, r13d; Size
0x180015c67  mov     rdx, [rsp+68h+Src]; Src
0x180015c6f  add     rcx, rbx; void *
0x180015c72  call    memcpy_0
0x180015c77  test    r14, r14
0x180015c7a  jz      short loc_180015C94
0x180015c7c  test    ebp, ebp
0x180015c7e  jns     short loc_180015C8E
0x180015c80  mov     [r14], rdi
0x180015c83  jmp     short loc_180015C98
0x180015c85  xor     esi, esi
0x180015c87  xor     ebp, ebp
0x180015c89  jmp     loc_180015BEB
0x180015c8e  mov     [r14+8], rdi
0x180015c92  jmp     short loc_180015C98
0x180015c94  mov     [r12], rdi
0x180015c98  mov     rdx, rdi; struct PERFLIBCI_RED_BLACK_NODE *
0x180015c9b  mov     rcx, r12; struct PERFLIBCI_RED_BLACK_NODE **
0x180015c9e  call    ?PerflibciInsertRedBlackNode@@YAXPEAPEAUPERFLIBCI_RED_BLACK_NODE@@PEAU1@@Z; PerflibciInsertRedBlackNode(PERFLIBCI_RED_BLACK_NODE * *,PERFLIBCI_RED_BLACK_NODE *)
0x180015ca3  mov     rax, [r12]
0x180015ca7  mov     dword ptr [rax+28h], 0
0x180015cae  jmp     short loc_180015CB7
0x180015cb0  mov     esi, 0Eh
0x180015cb5  xor     edi, edi
0x180015cb7  test    rdi, rdi
0x180015cba  jnz     short loc_180015CD4
0x180015cbc  test    esi, esi
0x180015cbe  jnz     short loc_180015CCC
0x180015cc0  lea     esi, [rdi+57h]
0x180015cc3  jmp     short loc_180015CCC
0x180015cc5  mov     esi, 0Dh
0x180015cca  xor     edi, edi
0x180015ccc  mov     ecx, esi; dwErrCode
0x180015cce  call    cs:__imp_SetLastError
0x180015cd4  mov     rbx, [rsp+68h+arg_0]
0x180015cd9  mov     rax, rdi
0x180015cdc  add     rsp, 30h
0x180015ce0  pop     r15
0x180015ce2  pop     r14
0x180015ce4  pop     r13
0x180015ce6  pop     r12
0x180015ce8  pop     rdi
0x180015ce9  pop     rsi
0x180015cea  pop     rbp
0x180015ceb  retn
```
