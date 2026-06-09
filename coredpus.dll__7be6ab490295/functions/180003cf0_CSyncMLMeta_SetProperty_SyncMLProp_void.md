# CSyncMLMeta::SetProperty(SyncMLProp,void *)

- ea: `0x180003cf0`
- end: `0x180003e01`
- name: `?SetProperty@CSyncMLMeta@@AEAAJW4SyncMLProp@@PEAX@Z`
- size: `273`
- prototype: `int __high(enum SyncMLProp, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a760`

## callees

- `0x180002550`
- `0x180003cf0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d67`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d67`
- `DMCmnUtils!CopyString` at `0x180003d85`
- `DMCmnUtils!CopyString` at `0x180003dbc`
- `DMCmnUtils!CopyString` at `0x180003d85`
- `DMCmnUtils!CopyString` at `0x180003dbc`

## pseudocode

```c
int __fastcall CSyncMLMeta::SetProperty(__int64 a1, int a2, const unsigned __int16 *a3)
{
  __int64 i; // rbx
  int v6; // ecx
  __int64 j; // rdx
  int result; // eax
  const unsigned __int16 **v9; // rdi
  unsigned __int16 *v10; // rcx
  unsigned __int64 v11; // [rsp+48h] [rbp+20h] BYREF

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 0x10 )
      return -2147024809;
    v6 = *((_DWORD *)&CSyncMLMeta::rgSupportedProps + i);
    if ( v6 == a2 )
      break;
  }
  for ( j = 0; (unsigned int)j < 3; j = (unsigned int)(j + 1) )
  {
    if ( *((_DWORD *)&CSyncMLMeta::rgUnimplementedProps + j) == v6 )
      return -2147467263;
  }
  v9 = (const unsigned __int16 **)(a1 + 8 * i);
  if ( (unsigned int)i > 4 )
  {
    result = 0;
    *v9 = a3;
LABEL_17:
    *(_DWORD *)(a1 + 128) |= 1 << i;
    return result;
  }
  v10 = (unsigned __int16 *)*v9;
  v11 = 0;
  LocalFree(v10);
  *v9 = 0;
  result = CopyString(a3, 0xFFFFFFFF, (unsigned __int16 **)(a1 + 8 * i));
  if ( a3 )
  {
    result = StringCchLengthW(a3, 0x7FFFFFFFu, &v11);
    if ( result >= 0 )
    {
      if ( v11 )
      {
        result = CopyString(a3, v11, (unsigned __int16 **)(a1 + 8 * i));
        if ( result >= 0 )
          goto LABEL_17;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003cf0  mov     [rsp+arg_8], rbx
0x180003cf5  mov     [rsp+arg_10], rsi
0x180003cfa  push    r14
0x180003cfc  sub     rsp, 20h
0x180003d00  mov     rsi, r8
0x180003d03  mov     r14, rcx
0x180003d06  lea     r8, __ImageBase
0x180003d0d  xor     ebx, ebx
0x180003d0f  nop
0x180003d10  cmp     ebx, 10h
0x180003d13  jnb     loc_180003DEA
0x180003d19  mov     ecx, ds:rva ?rgSupportedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B[r8+rbx*4]; SyncMLProp const near * const CSyncMLMeta::rgSupportedProps ...
0x180003d21  cmp     ecx, edx
0x180003d23  jz      short loc_180003D29
0x180003d25  inc     ebx
0x180003d27  jmp     short loc_180003D10
0x180003d29  xor     edx, edx
0x180003d2b  nop     dword ptr [rax+rax+00h]
0x180003d30  cmp     edx, 3
0x180003d33  jnb     short loc_180003D4D
0x180003d35  cmp     ds:rva ?rgUnimplementedProps@CSyncMLMeta@@0QBW4SyncMLProp@@B[r8+rdx*4], ecx; SyncMLProp const near * const CSyncMLMeta::rgUnimplementedProps ...
0x180003d3d  jz      short loc_180003D43
0x180003d3f  inc     edx
0x180003d41  jmp     short loc_180003D30
0x180003d43  mov     eax, 80004001h
0x180003d48  jmp     loc_180003DEF
0x180003d4d  mov     [rsp+28h+arg_0], rdi
0x180003d52  lea     rdi, [r14+rbx*8]
0x180003d56  cmp     ebx, 4
0x180003d59  ja      short loc_180003DCE
0x180003d5b  mov     rcx, [rdi]; hMem
0x180003d5e  mov     [rsp+28h+arg_18], 0
0x180003d67  call    cs:__imp_LocalFree
0x180003d6e  nop     dword ptr [rax+rax+00h]
0x180003d73  mov     r8, rdi
0x180003d76  mov     qword ptr [rdi], 0
0x180003d7d  mov     edx, 0FFFFFFFFh
0x180003d82  mov     rcx, rsi
0x180003d85  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180003d8c  nop     dword ptr [rax+rax+00h]
0x180003d91  test    rsi, rsi
0x180003d94  jz      short loc_180003DE3
0x180003d96  lea     r8, [rsp+28h+arg_18]; unsigned __int64 *
0x180003d9b  mov     edx, 7FFFFFFFh; unsigned __int64
0x180003da0  mov     rcx, rsi; unsigned __int16 *
0x180003da3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180003da8  test    eax, eax
0x180003daa  js      short loc_180003DE3
0x180003dac  mov     rdx, [rsp+28h+arg_18]
0x180003db1  test    rdx, rdx
0x180003db4  jz      short loc_180003DE3
0x180003db6  mov     r8, rdi
0x180003db9  mov     rcx, rsi
0x180003dbc  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180003dc3  nop     dword ptr [rax+rax+00h]
0x180003dc8  test    eax, eax
0x180003dca  jns     short loc_180003DD3
0x180003dcc  jmp     short loc_180003DE3
0x180003dce  xor     eax, eax
0x180003dd0  mov     [rdi], rsi
0x180003dd3  mov     ecx, ebx
0x180003dd5  mov     edx, 1
0x180003dda  shl     edx, cl
0x180003ddc  or      [r14+80h], edx
0x180003de3  mov     rdi, [rsp+28h+arg_0]
0x180003de8  jmp     short loc_180003DEF
0x180003dea  mov     eax, 80070057h
0x180003def  mov     rbx, [rsp+28h+arg_8]
0x180003df4  mov     rsi, [rsp+28h+arg_10]
0x180003df9  add     rsp, 20h
0x180003dfd  pop     r14
0x180003dff  retn
```
