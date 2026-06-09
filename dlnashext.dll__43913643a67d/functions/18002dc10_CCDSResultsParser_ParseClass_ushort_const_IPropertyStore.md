# CCDSResultsParser::ParseClass(ushort const *,IPropertyStore *)

- ea: `0x18002dc10`
- end: `0x18002deb7`
- name: `?ParseClass@CCDSResultsParser@@SAJPEBGPEAUIPropertyStore@@@Z`
- size: `679`
- prototype: `__int64 __fastcall(LPCWCH lpString1, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002dc10`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dcaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dcf0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dd3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ddda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002de55`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dcaa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dcf0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002dd3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ddda`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002de55`

## pseudocode

```c
__int64 __fastcall CCDSResultsParser::ParseClass(LPCWCH lpString1, struct IPropertyStore *a2)
{
  struct IPropertyStoreVtbl *lpVtbl; // rax
  unsigned int v5; // r12d
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // r14
  __int64 v10; // rdi
  __int64 v11; // rcx
  unsigned int i; // ebx
  unsigned int j; // ebx
  __int128 v15; // [rsp+30h] [rbp-49h] BYREF
  __int128 v16; // [rsp+40h] [rbp-39h] BYREF
  __int128 *v17; // [rsp+50h] [rbp-29h]
  __int128 v18; // [rsp+58h] [rbp-21h] BYREF
  __int64 v19; // [rsp+68h] [rbp-11h]
  __int128 v20; // [rsp+70h] [rbp-9h] BYREF
  __int64 v21; // [rsp+80h] [rbp+7h]

  v19 = 0;
  v18 = 0;
  LOWORD(v18) = 31;
  lpVtbl = a2->lpVtbl;
  *((_QWORD *)&v18 + 1) = lpString1;
  v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, __int128 *))lpVtbl->SetValue)(
         a2,
         &PKEY_ItemClass,
         &v18);
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  v6 = -1;
  v15 = 0;
  v7 = -1;
  do
    ++v7;
  while ( lpString1[v7] );
  if ( v7 >= 0x10 && CompareStringOrdinal(lpString1, 16, L"object.container", 16, 1) == 2 )
  {
    v8 = 1;
    *(_QWORD *)&v15 = L"folder";
    do
      ++v6;
    while ( lpString1[v6] );
    if ( v6 >= 0x22 && CompareStringOrdinal(lpString1, 34, L"object.container.playlistContainer", 34, 1) == 2 )
    {
      v8 = 2;
      *((_QWORD *)&v15 + 1) = L"playlist";
    }
LABEL_16:
    v16 = 0;
    DWORD2(v16) = v8;
    LOWORD(v16) = 4127;
    v17 = &v15;
    v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a2->lpVtbl->SetValue)(
           a2,
           &PKEY_Kind,
           &v16);
    goto LABEL_17;
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  do
  {
    if ( CompareStringOrdinal(lpString1, qword_1800389F8[v10], (&off_1800389F0)[v10], qword_1800389F8[v10], 1) == 2 )
    {
      v11 = v8++;
      *((_QWORD *)&v15 + v11) = off_180038A00[v10];
    }
    ++v9;
    v10 += 3;
  }
  while ( v9 != 5 );
  if ( v8 )
    goto LABEL_16;
LABEL_17:
  for ( i = 0; i < 4; ++i )
  {
    if ( CompareStringOrdinal(lpString1, dword_180038A78[6 * i], (&off_180038A70)[3 * i], dword_180038A78[6 * i], 1) == 2 )
    {
      v17 = 0;
      v16 = 0;
      LOWORD(v16) = 31;
      *((_QWORD *)&v16 + 1) = off_180038A80[3 * i];
      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a2->lpVtbl->SetValue)(
             a2,
             &PKEY_Media_ClassPrimaryID,
             &v16) >= 0 )
      {
        for ( j = 0; j < 4; ++j )
        {
          if ( CompareStringOrdinal(
                 lpString1,
                 dword_180038998[6 * j],
                 (&off_180038990)[3 * j],
                 dword_180038998[6 * j],
                 1) == 2 )
          {
            v21 = 0;
            v20 = 0;
            LOWORD(v20) = 31;
            *((_QWORD *)&v20 + 1) = off_1800389A0[3 * j];
            ((void (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int128 *))a2->lpVtbl->SetValue)(
              a2,
              &PKEY_Media_ClassSecondaryID,
              &v20);
            return v5;
          }
        }
      }
      return v5;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18002dc10  push    rbp
0x18002dc12  push    rbx
0x18002dc13  push    rsi
0x18002dc14  push    rdi
0x18002dc15  push    r12
0x18002dc17  push    r13
0x18002dc19  push    r14
0x18002dc1b  push    r15
0x18002dc1d  lea     rbp, [rsp-1Fh]
0x18002dc22  sub     rsp, 98h
0x18002dc29  xor     eax, eax
0x18002dc2b  lea     r8, [rbp+57h+var_78]
0x18002dc2f  mov     [rbp+57h+var_68], rax
0x18002dc33  mov     r15, rdx
0x18002dc36  xorps   xmm0, xmm0
0x18002dc39  mov     eax, 1Fh
0x18002dc3e  movups  [rbp+57h+var_78], xmm0
0x18002dc42  mov     word ptr [rbp+57h+var_78], ax
0x18002dc46  mov     rsi, rcx
0x18002dc49  mov     rax, [rdx]
0x18002dc4c  lea     rdx, PKEY_ItemClass
0x18002dc53  mov     qword ptr [rbp+57h+var_78+8], rcx
0x18002dc57  mov     rcx, r15
0x18002dc5a  mov     rax, [rax+30h]
0x18002dc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dc63  xor     r13d, r13d
0x18002dc66  mov     r12d, eax
0x18002dc69  test    eax, eax
0x18002dc6b  js      loc_18002DEA0
0x18002dc71  xorps   xmm0, xmm0
0x18002dc74  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002dc78  movups  [rbp+57h+var_A0], xmm0
0x18002dc7c  mov     rcx, rdi
0x18002dc7f  inc     rcx
0x18002dc82  cmp     [rsi+rcx*2], r13w
0x18002dc87  jnz     short loc_18002DC7F
0x18002dc89  cmp     rcx, 10h
0x18002dc8d  jb      short loc_18002DD0D
0x18002dc8f  mov     r9d, 10h; cchCount2
0x18002dc95  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18002dc9d  mov     edx, r9d; cchCount1
0x18002dca0  lea     r8, aObjectContaine_4; "object.container"
0x18002dca7  mov     rcx, rsi; lpString1
0x18002dcaa  call    cs:__imp_CompareStringOrdinal
0x18002dcb0  cmp     eax, 2
0x18002dcb3  jnz     short loc_18002DD0D
0x18002dcb5  lea     rax, aFolder_0; "folder"
0x18002dcbc  mov     ebx, 1
0x18002dcc1  mov     qword ptr [rbp+57h+var_A0], rax
0x18002dcc5  inc     rdi
0x18002dcc8  cmp     [rsi+rdi*2], r13w
0x18002dccd  jnz     short loc_18002DCC5
0x18002dccf  cmp     rdi, 22h ; '"'
0x18002dcd3  jb      loc_18002DD6B
0x18002dcd9  mov     r9d, 22h ; '"'; cchCount2
0x18002dcdf  mov     [rsp+0D0h+bIgnoreCase], ebx; bIgnoreCase
0x18002dce3  mov     edx, r9d; cchCount1
0x18002dce6  lea     r8, aObjectContaine_0; "object.container.playlistContainer"
0x18002dced  mov     rcx, rsi; lpString1
0x18002dcf0  call    cs:__imp_CompareStringOrdinal
0x18002dcf6  cmp     eax, 2
0x18002dcf9  jnz     short loc_18002DD6B
0x18002dcfb  lea     rax, aPlaylist; "playlist"
0x18002dd02  mov     ebx, 2
0x18002dd07  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18002dd0b  jmp     short loc_18002DD6B
0x18002dd0d  mov     ebx, r13d
0x18002dd10  mov     r14, r13
0x18002dd13  mov     rdi, r13
0x18002dd16  lea     r13, __ImageBase
0x18002dd1d  mov     edx, [rdi+r13+389F8h]; cchCount1
0x18002dd25  mov     rcx, rsi; lpString1
0x18002dd28  mov     r8, [rdi+r13+389F0h]; lpString2
0x18002dd30  mov     r9d, edx; cchCount2
0x18002dd33  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18002dd3b  call    cs:__imp_CompareStringOrdinal
0x18002dd41  cmp     eax, 2
0x18002dd44  jnz     short loc_18002DD57
0x18002dd46  mov     rax, [rdi+r13+38A00h]
0x18002dd4e  mov     ecx, ebx
0x18002dd50  inc     ebx
0x18002dd52  mov     qword ptr [rbp+rcx*8+57h+var_A0], rax
0x18002dd57  inc     r14
0x18002dd5a  add     rdi, 18h
0x18002dd5e  cmp     r14, 5
0x18002dd62  jnz     short loc_18002DD1D
0x18002dd64  xor     r13d, r13d
0x18002dd67  test    ebx, ebx
0x18002dd69  jz      short loc_18002DDA3
0x18002dd6b  xorps   xmm0, xmm0
0x18002dd6e  lea     r8, [rbp+57h+var_90]
0x18002dd72  movups  [rbp+57h+var_90], xmm0
0x18002dd76  mov     eax, 101Fh
0x18002dd7b  mov     dword ptr [rbp+57h+var_90+8], ebx
0x18002dd7e  mov     word ptr [rbp+57h+var_90], ax
0x18002dd82  lea     rdx, PKEY_Kind
0x18002dd89  lea     rax, [rbp+57h+var_A0]
0x18002dd8d  mov     rcx, r15
0x18002dd90  mov     [rbp+57h+var_80], rax
0x18002dd94  mov     rax, [r15]
0x18002dd97  mov     rax, [rax+30h]
0x18002dd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dda0  mov     r12d, eax
0x18002dda3  mov     ebx, r13d
0x18002dda6  lea     r14, __ImageBase
0x18002ddad  cmp     ebx, 4
0x18002ddb0  jnb     loc_18002DEA0
0x18002ddb6  mov     eax, ebx
0x18002ddb8  mov     rcx, rsi; lpString1
0x18002ddbb  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18002ddc3  lea     rdi, [rax+rax*2]
0x18002ddc7  mov     edx, ds:rva dword_180038A78[r14+rdi*8]; cchCount1
0x18002ddcf  mov     r9d, edx; cchCount2
0x18002ddd2  mov     r8, ds:rva off_180038A70[r14+rdi*8]; lpString2
0x18002ddda  call    cs:__imp_CompareStringOrdinal
0x18002dde0  cmp     eax, 2
0x18002dde3  jz      short loc_18002DDE9
0x18002dde5  inc     ebx
0x18002dde7  jmp     short loc_18002DDAD
0x18002dde9  xor     eax, eax
0x18002ddeb  lea     r8, [rbp+57h+var_90]
0x18002ddef  mov     [rbp+57h+var_80], rax
0x18002ddf3  lea     rdx, PKEY_Media_ClassPrimaryID
0x18002ddfa  xorps   xmm0, xmm0
0x18002ddfd  mov     eax, 1Fh
0x18002de02  movups  [rbp+57h+var_90], xmm0
0x18002de06  mov     word ptr [rbp+57h+var_90], ax
0x18002de0a  mov     rcx, r15
0x18002de0d  mov     rax, ds:rva off_180038A80[r14+rdi*8]; "{D1607DBC-E323-4be2-86A1-48A42A28441E}" ...
0x18002de15  mov     qword ptr [rbp+57h+var_90+8], rax
0x18002de19  mov     rax, [r15]
0x18002de1c  mov     rax, [rax+30h]
0x18002de20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de25  test    eax, eax
0x18002de27  js      short loc_18002DEA0
0x18002de29  mov     ebx, r13d
0x18002de2c  cmp     ebx, 4
0x18002de2f  jnb     short loc_18002DEA0
0x18002de31  mov     eax, ebx
0x18002de33  mov     rcx, rsi; lpString1
0x18002de36  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x18002de3e  lea     rdi, [rax+rax*2]
0x18002de42  mov     edx, ds:rva dword_180038998[r14+rdi*8]; cchCount1
0x18002de4a  mov     r9d, edx; cchCount2
0x18002de4d  mov     r8, ds:rva off_180038990[r14+rdi*8]; lpString2
0x18002de55  call    cs:__imp_CompareStringOrdinal
0x18002de5b  cmp     eax, 2
0x18002de5e  jz      short loc_18002DE64
0x18002de60  inc     ebx
0x18002de62  jmp     short loc_18002DE2C
0x18002de64  xor     eax, eax
0x18002de66  lea     r8, [rbp+57h+var_60]
0x18002de6a  mov     [rbp+57h+var_50], rax
0x18002de6e  lea     rdx, PKEY_Media_ClassSecondaryID
0x18002de75  xorps   xmm0, xmm0
0x18002de78  mov     eax, 1Fh
0x18002de7d  movups  [rbp+57h+var_60], xmm0
0x18002de81  mov     word ptr [rbp+57h+var_60], ax
0x18002de85  mov     rcx, r15
0x18002de88  mov     rax, ds:rva off_1800389A0[r14+rdi*8]; "{E0236BEB-C281-4ede-A36D-7AF76A3D45B5}" ...
0x18002de90  mov     qword ptr [rbp+57h+var_60+8], rax
0x18002de94  mov     rax, [r15]
0x18002de97  mov     rax, [rax+30h]
0x18002de9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dea0  mov     eax, r12d
0x18002dea3  add     rsp, 98h
0x18002deaa  pop     r15
0x18002deac  pop     r14
0x18002deae  pop     r13
0x18002deb0  pop     r12
0x18002deb2  pop     rdi
0x18002deb3  pop     rsi
0x18002deb4  pop     rbx
0x18002deb5  pop     rbp
0x18002deb6  retn
```
