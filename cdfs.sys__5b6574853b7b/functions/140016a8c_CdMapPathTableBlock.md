# CdMapPathTableBlock

- ea: `0x140016a8c`
- end: `0x140016c4f`
- name: `CdMapPathTableBlock`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140016998`
- `0x140016a20`

## callees

- `0x140003000`
- `0x140003300`
- `0x140016a8c`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140016ae3`
- `ntoskrnl!CcUnpinData` at `0x140016bbb`
- `ntoskrnl!CcUnpinData` at `0x140016ae3`
- `ntoskrnl!CcUnpinData` at `0x140016bbb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bf5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140016bf5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016b31`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140016b31`
- `ntoskrnl!CcMapData` at `0x140016b94`
- `ntoskrnl!CcMapData` at `0x140016c2b`
- `ntoskrnl!CcMapData` at `0x140016b94`
- `ntoskrnl!CcMapData` at `0x140016c2b`

## pseudocode

```c
BOOLEAN __fastcall CdMapPathTableBlock(__int64 a1, __int64 a2, union _LARGE_INTEGER a3, __int64 a4)
{
  ULONG v4; // edi
  unsigned int v6; // eax
  PVOID *Bcb; // rsi
  void *v9; // rcx
  ULONG v10; // r12d
  PVOID PoolWithTag; // rax
  PVOID v12; // rbp
  __int64 v13; // r14
  ULONG v14; // edi
  int v15; // ebp
  BOOLEAN result; // al
  PVOID Src; // [rsp+60h] [rbp+8h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+70h] [rbp+18h] BYREF

  FileOffset = a3;
  Src = 0;
  v4 = 4096;
  v6 = *(_DWORD *)(a2 + 32) - a3.LowPart;
  if ( v6 <= 0x1000 )
  {
    *(_BYTE *)(a4 + 29) = 1;
    v4 = v6;
  }
  Bcb = (PVOID *)(a4 + 16);
  *(_DWORD *)(a4 + 8) = a3.LowPart;
  v9 = *(void **)(a4 + 16);
  *(_DWORD *)(a4 + 12) = v4;
  if ( v9 )
  {
    CcUnpinData(v9);
    a3.LowPart = FileOffset.LowPart;
    *Bcb = 0;
  }
  if ( v4 > 0x800 && (a3.LowPart & 0x3FFFF) == 0x3F800 )
  {
    v10 = 2048;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1041, v4, 0x70736443u);
    v12 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v4);
    v13 = 0;
    *(_QWORD *)a4 = v12;
    v14 = v4 - 2048;
    *(_BYTE *)(a4 + 28) = 1;
    v15 = 2;
    do
    {
      CcMapData(*(PFILE_OBJECT *)(a2 + 472), &FileOffset, v10, 1u, Bcb, &Src);
      memmove((void *)(v13 + *(_QWORD *)a4), Src, v10);
      if ( *Bcb )
      {
        CcUnpinData(*Bcb);
        *Bcb = 0;
      }
      result = 0;
      v10 = v14;
      FileOffset.QuadPart += 2048LL;
      v13 = 2048;
      --v15;
    }
    while ( v15 );
  }
  else
  {
    if ( *(_BYTE *)(a4 + 28) )
    {
      if ( *(_QWORD *)a4 )
      {
        ExFreePoolWithTag(*(PVOID *)a4, 0);
        *(_QWORD *)a4 = 0;
      }
      *(_BYTE *)(a4 + 28) = 0;
    }
    return CcMapData(*(PFILE_OBJECT *)(a2 + 472), &FileOffset, v4, 1u, Bcb, (PVOID *)a4);
  }
  return result;
}

```

## disassembly

```asm
0x140016a8c  mov     rax, rsp
0x140016a8f  mov     [rax+10h], rbx
0x140016a93  mov     [rax+20h], rbp
0x140016a97  mov     [rax+18h], r8
0x140016a9b  mov     [rax+8], rcx
0x140016a9f  push    rsi
0x140016aa0  push    rdi
0x140016aa1  push    r12
0x140016aa3  push    r14
0x140016aa5  push    r15
0x140016aa7  sub     rsp, 30h
0x140016aab  mov     qword ptr [rax+8], 0
0x140016ab3  mov     edi, 1000h
0x140016ab8  mov     eax, [rdx+20h]
0x140016abb  mov     rbx, r9
0x140016abe  sub     eax, r8d
0x140016ac1  mov     r15, rdx
0x140016ac4  cmp     eax, edi
0x140016ac6  ja      short loc_140016ACF
0x140016ac8  mov     byte ptr [r9+1Dh], 1
0x140016acd  mov     edi, eax
0x140016acf  lea     rsi, [r9+10h]
0x140016ad3  mov     [r9+8], r8d
0x140016ad7  mov     rcx, [rsi]; Bcb
0x140016ada  mov     [r9+0Ch], edi
0x140016ade  test    rcx, rcx
0x140016ae1  jz      short loc_140016AFB
0x140016ae3  call    cs:__imp_CcUnpinData
0x140016aea  nop     dword ptr [rax+rax+00h]
0x140016aef  mov     r8, qword ptr [rsp+58h+FileOffset]
0x140016af4  mov     qword ptr [rsi], 0
0x140016afb  cmp     edi, 800h
0x140016b01  jbe     loc_140016BE5
0x140016b07  and     r8d, 3FFFFh
0x140016b0e  cmp     r8d, 3F800h
0x140016b15  jnz     loc_140016BE5
0x140016b1b  mov     r8d, 70736443h; Tag
0x140016b21  mov     edx, edi; NumberOfBytes
0x140016b23  mov     ecx, 411h; PoolType
0x140016b28  mov     r14d, edi
0x140016b2b  mov     r12d, 800h
0x140016b31  call    cs:__imp_ExAllocatePoolWithTag
0x140016b38  nop     dword ptr [rax+rax+00h]
0x140016b3d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140016b44  mov     rbp, rax
0x140016b47  jnz     short loc_140016B5B
0x140016b49  test    rax, rax
0x140016b4c  jz      short loc_140016B5B
0x140016b4e  mov     r8d, r14d; Size
0x140016b51  xor     edx, edx; Val
0x140016b53  mov     rcx, rax; void *
0x140016b56  call    memset
0x140016b5b  xor     r14d, r14d
0x140016b5e  mov     [rbx], rbp
0x140016b61  add     edi, 0FFFFF800h
0x140016b67  mov     byte ptr [rbx+1Ch], 1
0x140016b6b  mov     ebp, 2
0x140016b70  mov     rcx, [r15+1D8h]; FileObject
0x140016b77  lea     rax, [rsp+58h+Src]
0x140016b7c  mov     [rsp+58h+Buffer], rax; Buffer
0x140016b81  lea     rdx, [rsp+58h+FileOffset]; FileOffset
0x140016b86  mov     r9d, 1; Flags
0x140016b8c  mov     [rsp+58h+Bcb], rsi; Bcb
0x140016b91  mov     r8d, r12d; Length
0x140016b94  call    cs:__imp_CcMapData
0x140016b9b  nop     dword ptr [rax+rax+00h]
0x140016ba0  mov     rcx, [rbx]
0x140016ba3  mov     rdx, [rsp+58h+Src]; Src
0x140016ba8  add     rcx, r14; void *
0x140016bab  mov     r8d, r12d; Size
0x140016bae  call    memmove
0x140016bb3  mov     rcx, [rsi]; Bcb
0x140016bb6  test    rcx, rcx
0x140016bb9  jz      short loc_140016BCE
0x140016bbb  call    cs:__imp_CcUnpinData
0x140016bc2  nop     dword ptr [rax+rax+00h]
0x140016bc7  mov     qword ptr [rsi], 0
0x140016bce  mov     eax, 800h
0x140016bd3  mov     r12d, edi
0x140016bd6  add     qword ptr [rsp+58h+FileOffset], rax
0x140016bdb  mov     r14d, eax
0x140016bde  add     ebp, 0FFFFFFFFh
0x140016be1  jnz     short loc_140016B70
0x140016be3  jmp     short loc_140016C37
0x140016be5  cmp     byte ptr [rbx+1Ch], 0
0x140016be9  jz      short loc_140016C0C
0x140016beb  mov     rcx, [rbx]; P
0x140016bee  test    rcx, rcx
0x140016bf1  jz      short loc_140016C08
0x140016bf3  xor     edx, edx; Tag
0x140016bf5  call    cs:__imp_ExFreePoolWithTag
0x140016bfc  nop     dword ptr [rax+rax+00h]
0x140016c01  mov     qword ptr [rbx], 0
0x140016c08  mov     byte ptr [rbx+1Ch], 0
0x140016c0c  mov     rcx, [r15+1D8h]; FileObject
0x140016c13  lea     rdx, [rsp+58h+FileOffset]; FileOffset
0x140016c18  mov     [rsp+58h+Buffer], rbx; Buffer
0x140016c1d  mov     r9d, 1; Flags
0x140016c23  mov     r8d, edi; Length
0x140016c26  mov     [rsp+58h+Bcb], rsi; Bcb
0x140016c2b  call    cs:__imp_CcMapData
0x140016c32  nop     dword ptr [rax+rax+00h]
0x140016c37  mov     rbx, [rsp+58h+arg_8]
0x140016c3c  mov     rbp, [rsp+58h+arg_18]
0x140016c41  add     rsp, 30h
0x140016c45  pop     r15
0x140016c47  pop     r14
0x140016c49  pop     r12
0x140016c4b  pop     rdi
0x140016c4c  pop     rsi
0x140016c4d  retn
```
