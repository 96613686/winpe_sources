# CMemoryTable::InternalMatchValues(ulong,ulong,ulong,ulong,ulong,void *,void *)

- ea: `0x18000fa5c`
- end: `0x18000fb84`
- name: `?InternalMatchValues@CMemoryTable@@SAHKKKKKPEAX0@Z`
- size: `296`
- prototype: `static int(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, void *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f440`
- `0x18000fc24`

## callees

- `0x18000fa5c`
- `0x18000fdd4`
- `0x18002e0a6`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000fb1c`
- `msvcrt!_wcsicmp` at `0x18000fb1c`
- `KERNEL32!CompareStringW` at `0x18000fb04`
- `KERNEL32!CompareStringW` at `0x18000fb04`

## pseudocode

```c
char __fastcall CMemoryTable::InternalMatchValues(
        __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        WCHAR *lpString1,
        WCHAR *lpString2)
{
  WCHAR *v7; // r10
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  __int64 v12; // rdx
  int v16; // eax
  int v17; // edx

  v7 = lpString1;
  if ( !lpString1 )
    return lpString2 == 0;
  if ( !lpString2 )
    return 0;
  v8 = a2 - 19;
  if ( !v8 )
    return *(_DWORD *)lpString1 == *(_DWORD *)lpString2;
  v9 = v8 - 53;
  if ( !v9 )
  {
LABEL_8:
    v12 = *(_QWORD *)lpString1 - *(_QWORD *)lpString2;
    if ( *(_QWORD *)lpString1 == *(_QWORD *)lpString2 )
      v12 = *((_QWORD *)lpString1 + 1) - *((_QWORD *)lpString2 + 1);
    return v12 == 0;
  }
  v10 = v9 - 56;
  if ( !v10 )
  {
    if ( a4 == a5 )
      return memcmp_0(lpString1, lpString2, a4) == 0;
    return 0;
  }
  v11 = v10 - 2;
  if ( v11 )
  {
    if ( v11 == 5 )
      goto LABEL_8;
    return 0;
  }
  if ( (a3 & 0x2000000) != 0 )
    return CMemoryTable::MultiStringCompare(lpString1, lpString2, a3 & 0x20000000);
  if ( (a3 & 0x20000000) == 0 )
  {
    do
    {
      v16 = *(WCHAR *)((char *)v7 + (char *)lpString2 - (char *)lpString1);
      v17 = *v7 - v16;
      if ( v17 )
        break;
      ++v7;
    }
    while ( v16 );
    return v17 == 0;
  }
  if ( (a3 & 0x8000) != 0 )
    return CompareStringW(0x800u, 0x1001u, lpString1, -1, lpString2, -1) == 2;
  else
    return _wcsicmp(lpString1, lpString2) == 0;
}

```

## disassembly

```asm
0x18000fa5c  sub     rsp, 38h
0x18000fa60  mov     r10, [rsp+38h+lpString1]
0x18000fa65  test    r10, r10
0x18000fa68  jz      loc_18000FB6E
0x18000fa6e  mov     rcx, [rsp+38h+arg_30]
0x18000fa73  test    rcx, rcx
0x18000fa76  jz      loc_18000FB7D
0x18000fa7c  sub     edx, 13h
0x18000fa7f  jz      loc_18000FB62
0x18000fa85  sub     edx, 35h ; '5'
0x18000fa88  jz      short loc_18000FAA1
0x18000fa8a  sub     edx, 38h ; '8'
0x18000fa8d  jz      loc_18000FB49
0x18000fa93  sub     edx, 2
0x18000fa96  jz      short loc_18000FABE
0x18000fa98  cmp     edx, 5
0x18000fa9b  jnz     loc_18000FB7D
0x18000faa1  mov     rdx, [r10]
0x18000faa4  sub     rdx, [rcx]
0x18000faa7  jnz     short loc_18000FAB1
0x18000faa9  mov     rdx, [r10+8]
0x18000faad  sub     rdx, [rcx+8]
0x18000fab1  xor     eax, eax
0x18000fab3  test    rdx, rdx
0x18000fab6  setz    al
0x18000fab9  jmp     loc_18000FB7F
0x18000fabe  bt      r8d, 19h
0x18000fac3  jnb     short loc_18000FADB
0x18000fac5  mov     rdx, rcx; String2
0x18000fac8  and     r8d, 20000000h; int
0x18000facf  mov     rcx, r10; String1
0x18000fad2  add     rsp, 38h
0x18000fad6  jmp     ?MultiStringCompare@CMemoryTable@@CAHPEBG0H@Z; CMemoryTable::MultiStringCompare(ushort const *,ushort const *,int)
0x18000fadb  bt      r8d, 1Dh
0x18000fae0  jnb     short loc_18000FB28
0x18000fae2  bt      r8d, 0Fh
0x18000fae7  jnb     short loc_18000FB16
0x18000fae9  or      r9d, 0FFFFFFFFh; cchCount1
0x18000faed  mov     r8, r10; lpString1
0x18000faf0  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x18000faf5  mov     edx, 1001h; dwCmpFlags
0x18000fafa  mov     [rsp+38h+lpString2], rcx; lpString2
0x18000faff  mov     ecx, 800h; Locale
0x18000fb04  call    cs:__imp_CompareStringW
0x18000fb0a  xor     ecx, ecx
0x18000fb0c  cmp     eax, 2
0x18000fb0f  setz    cl
0x18000fb12  mov     eax, ecx
0x18000fb14  jmp     short loc_18000FB7F
0x18000fb16  mov     rdx, rcx; String2
0x18000fb19  mov     rcx, r10; String1
0x18000fb1c  call    cs:__imp__wcsicmp
0x18000fb22  xor     ecx, ecx
0x18000fb24  test    eax, eax
0x18000fb26  jmp     short loc_18000FB0F
0x18000fb28  sub     rcx, r10
0x18000fb2b  movzx   edx, word ptr [r10]
0x18000fb2f  movzx   eax, word ptr [r10+rcx]
0x18000fb34  sub     edx, eax
0x18000fb36  jnz     short loc_18000FB40
0x18000fb38  add     r10, 2
0x18000fb3c  test    eax, eax
0x18000fb3e  jnz     short loc_18000FB2B
0x18000fb40  xor     eax, eax
0x18000fb42  test    edx, edx
0x18000fb44  jmp     loc_18000FAB6
0x18000fb49  cmp     r9d, [rsp+38h+arg_20]
0x18000fb4e  jnz     short loc_18000FB7D
0x18000fb50  mov     rdx, rcx; Buf2
0x18000fb53  mov     r8d, r9d; Size
0x18000fb56  mov     rcx, r10; Buf1
0x18000fb59  call    memcmp_0
0x18000fb5e  test    eax, eax
0x18000fb60  jmp     short loc_18000FB74
0x18000fb62  mov     ecx, [rcx]
0x18000fb64  xor     eax, eax
0x18000fb66  cmp     [r10], ecx
0x18000fb69  jmp     loc_18000FAB6
0x18000fb6e  cmp     [rsp+38h+arg_30], 0
0x18000fb74  jnz     short loc_18000FB7D
0x18000fb76  mov     eax, 1
0x18000fb7b  jmp     short loc_18000FB7F
0x18000fb7d  xor     eax, eax
0x18000fb7f  add     rsp, 38h
0x18000fb83  retn
```
