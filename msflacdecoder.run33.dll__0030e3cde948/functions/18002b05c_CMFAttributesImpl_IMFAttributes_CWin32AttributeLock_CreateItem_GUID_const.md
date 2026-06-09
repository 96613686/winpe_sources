# CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(_GUID const &)

- ea: `0x18002b05c`
- end: `0x18002b130`
- name: `?CreateItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@AEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z`
- size: `212`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002e640`
- `0x18002e6f0`
- `0x18002e9d0`
- `0x18002ea70`
- `0x18002ec00`
- `0x18002ece0`
- `0x18002ed40`
- `0x18002eda0`

## callees

- `0x180016b24`
- `0x18002b05c`
- `0x18002b39c`
- `0x18002f58c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b081`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b081`

## pseudocode

```c
__int64 __fastcall CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::CreateItem(__int64 a1, _DWORD *a2)
{
  PROPVARIANT *Item; // rax
  __int64 v5; // rbx
  int v6; // edx
  unsigned int v7; // edx
  __int64 i; // r10
  __int64 v9; // rbx

  Item = (PROPVARIANT *)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(a1, a2);
  v5 = (__int64)Item;
  if ( Item )
  {
    PropVariantClear(Item);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 56);
    if ( *(_DWORD *)(a1 + 60) == v6
      && (int)CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::ExtendStorage(a1, (unsigned int)(2 * v6 + 4)) < 0 )
    {
      return 0;
    }
    else
    {
      v7 = *(_DWORD *)(a1 + 60);
      for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
      {
        if ( *(_DWORD *)(*(_QWORD *)(a1 + 48) + 40 * i) >= *a2 )
          break;
      }
      v9 = 5 * i;
      memmove_0(
        (void *)(*(_QWORD *)(a1 + 48) + 40LL * (unsigned int)(i + 1)),
        (const void *)(*(_QWORD *)(a1 + 48) + 40 * i),
        40LL * (v7 - (unsigned int)i));
      *(_OWORD *)(*(_QWORD *)(a1 + 48) + 8 * v9) = *(_OWORD *)a2;
      v5 = *(_QWORD *)(a1 + 48) + 8 * (v9 + 2);
      *(_OWORD *)v5 = 0;
      *(_QWORD *)(v5 + 16) = 0;
      ++*(_DWORD *)(a1 + 60);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18002b05c  mov     [rsp+arg_0], rbx
0x18002b061  mov     [rsp+arg_8], rsi
0x18002b066  push    rdi
0x18002b067  sub     rsp, 20h
0x18002b06b  mov     rsi, rdx
0x18002b06e  mov     rdi, rcx
0x18002b071  call    ?_FindItem@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAPEAUtagPROPVARIANT@@AEBU_GUID@@@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::_FindItem(_GUID const &)
0x18002b076  mov     rbx, rax
0x18002b079  test    rax, rax
0x18002b07c  jz      short loc_18002B08C
0x18002b07e  mov     rcx, rax; pvar
0x18002b081  call    cs:__imp_PropVariantClear
0x18002b087  jmp     loc_18002B11D
0x18002b08c  mov     edx, [rdi+38h]
0x18002b08f  cmp     [rdi+3Ch], edx
0x18002b092  jnz     short loc_18002B0AB
0x18002b094  lea     edx, ds:4[rdx*2]
0x18002b09b  mov     rcx, rdi
0x18002b09e  call    ?ExtendStorage@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@IEAAJI@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::ExtendStorage(uint)
0x18002b0a3  test    eax, eax
0x18002b0a5  jns     short loc_18002B0AB
0x18002b0a7  xor     ebx, ebx
0x18002b0a9  jmp     short loc_18002B11D
0x18002b0ab  mov     edx, [rdi+3Ch]
0x18002b0ae  xor     r10d, r10d
0x18002b0b1  test    edx, edx
0x18002b0b3  jz      short loc_18002B0CE
0x18002b0b5  mov     r8d, [rsi]
0x18002b0b8  mov     r9, [rdi+30h]
0x18002b0bc  lea     rcx, [r10+r10*4]
0x18002b0c0  cmp     [r9+rcx*8], r8d
0x18002b0c4  jnb     short loc_18002B0CE
0x18002b0c6  inc     r10d
0x18002b0c9  cmp     r10d, edx
0x18002b0cc  jb      short loc_18002B0BC
0x18002b0ce  mov     r9, [rdi+30h]
0x18002b0d2  lea     eax, [r10+1]
0x18002b0d6  sub     edx, r10d
0x18002b0d9  lea     rbx, [r10+r10*4]
0x18002b0dd  lea     rax, [rax+rax*4]
0x18002b0e1  lea     rcx, [r9+rax*8]; void *
0x18002b0e5  lea     r8, [rdx+rdx*4]
0x18002b0e9  shl     r8, 3; Size
0x18002b0ed  lea     rdx, [r9+rbx*8]; Src
0x18002b0f1  call    memmove_0
0x18002b0f6  movups  xmm0, xmmword ptr [rsi]
0x18002b0f9  mov     rax, [rdi+30h]
0x18002b0fd  movdqu  xmmword ptr [rax+rbx*8], xmm0
0x18002b102  mov     rax, [rdi+30h]
0x18002b106  lea     rbx, [rbx+2]
0x18002b10a  xorps   xmm0, xmm0
0x18002b10d  lea     rbx, [rax+rbx*8]
0x18002b111  xor     eax, eax
0x18002b113  movups  xmmword ptr [rbx], xmm0
0x18002b116  mov     [rbx+10h], rax
0x18002b11a  inc     dword ptr [rdi+3Ch]
0x18002b11d  mov     rsi, [rsp+28h+arg_8]
0x18002b122  mov     rax, rbx
0x18002b125  mov     rbx, [rsp+28h+arg_0]
0x18002b12a  add     rsp, 20h
0x18002b12e  pop     rdi
0x18002b12f  retn
```
