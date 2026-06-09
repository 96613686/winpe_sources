# CombineCTAndAppId(ushort const *,ushort const *,ushort * *)

- ea: `0x180012674`
- end: `0x180012730`
- name: `?CombineCTAndAppId@@YAJPEBG0PEAPEAG@Z`
- size: `188`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180012860`
- `0x1800129e8`

## callees

- `0x180012674`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001270c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012717`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001270c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012717`
- `DMCmnUtils!BigStrcat` at `0x1800126f3`
- `DMCmnUtils!BigStrcat` at `0x1800126f3`
- `DMCmnUtils!CopyString` at `0x1800126ae`
- `DMCmnUtils!CopyString` at `0x1800126d1`
- `DMCmnUtils!CopyString` at `0x1800126ae`
- `DMCmnUtils!CopyString` at `0x1800126d1`

## pseudocode

```c
__int64 __fastcall CombineCTAndAppId(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v5; // ebx
  const unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // rax
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF
  HLOCAL v10; // [rsp+48h] [rbp+20h] BYREF

  hMem = 0;
  v10 = 0;
  if ( !a1 )
    a1 = &c_szUNKNOWN;
  v5 = CopyString(a1, 0xFFFFFFFF, (unsigned __int16 **)&hMem);
  if ( v5 >= 0 )
  {
    v6 = a2;
    if ( !a2 )
      v6 = &c_szUNKNOWN;
    v5 = CopyString(v6, 0xFFFFFFFF, (unsigned __int16 **)&v10);
    if ( v5 >= 0 )
    {
      v7 = BigStrcat(3u, hMem, L";", v10);
      *a3 = v7;
      if ( !v7 )
        v5 = -2147024882;
    }
  }
  LocalFree(hMem);
  LocalFree(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012674  mov     rax, rsp
0x180012677  mov     [rax+10h], rbx
0x18001267b  mov     [rax+18h], rsi
0x18001267f  push    r14
0x180012681  sub     rsp, 20h
0x180012685  mov     rsi, rdx
0x180012688  mov     qword ptr [rax+8], 0
0x180012690  or      edx, 0FFFFFFFFh
0x180012693  mov     qword ptr [rax+20h], 0
0x18001269b  mov     r14, r8
0x18001269e  lea     r8, [rax+8]
0x1800126a2  test    rcx, rcx
0x1800126a5  jnz     short loc_1800126AE
0x1800126a7  lea     rcx, ?c_szUNKNOWN@@3QBGB; ushort const near * const c_szUNKNOWN
0x1800126ae  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800126b4  mov     ebx, eax
0x1800126b6  test    eax, eax
0x1800126b8  js      short loc_180012707
0x1800126ba  or      edx, 0FFFFFFFFh
0x1800126bd  lea     r8, [rsp+28h+arg_18]
0x1800126c2  mov     rcx, rsi
0x1800126c5  test    rsi, rsi
0x1800126c8  jnz     short loc_1800126D1
0x1800126ca  lea     rcx, ?c_szUNKNOWN@@3QBGB; ushort const near * const c_szUNKNOWN
0x1800126d1  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x1800126d7  mov     ebx, eax
0x1800126d9  test    eax, eax
0x1800126db  js      short loc_180012707
0x1800126dd  mov     r9, [rsp+28h+arg_18]
0x1800126e2  lea     r8, ?c_szKeySeparator@@3QBGB; ";"
0x1800126e9  mov     rdx, [rsp+28h+hMem]
0x1800126ee  mov     ecx, 3
0x1800126f3  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1800126f9  test    rax, rax
0x1800126fc  mov     [r14], rax
0x1800126ff  mov     ecx, 8007000Eh
0x180012704  cmovz   ebx, ecx
0x180012707  mov     rcx, [rsp+28h+hMem]; hMem
0x18001270c  call    cs:__imp_LocalFree
0x180012712  mov     rcx, [rsp+28h+arg_18]; hMem
0x180012717  call    cs:__imp_LocalFree
0x18001271d  mov     rsi, [rsp+28h+arg_10]
0x180012722  mov     eax, ebx
0x180012724  mov     rbx, [rsp+28h+arg_8]
0x180012729  add     rsp, 20h
0x18001272d  pop     r14
0x18001272f  retn
```
