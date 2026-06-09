# CCDSResultsParser::ParseTitle(ushort const *,IPropertyStore *)

- ea: `0x18002e990`
- end: `0x18002eba5`
- name: `?ParseTitle@CCDSResultsParser@@SAJPEBGPEAUIPropertyStore@@@Z`
- size: `533`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180011930`
- `0x1800125c4`
- `0x18001681c`
- `0x18001c5c4`
- `0x18002e990`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002eb73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002eb73`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ead3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002eb3b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002ead3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002eb3b`

## pseudocode

```c
__int64 __fastcall CCDSResultsParser::ParseTitle(unsigned __int16 *a1, struct IPropertyStore *a2)
{
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rax
  int v6; // ebx
  unsigned __int16 *v7; // r15
  struct IPropertyStoreVtbl *lpVtbl; // rax
  struct IPropertyStoreVtbl *v9; // rax
  const WCHAR *String; // rax
  unsigned __int64 v11; // rcx
  struct IPropertyStoreVtbl *v12; // rax
  const WCHAR *v13; // rax
  struct IPropertyStoreVtbl *v14; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v17; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v19[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(v19, 0, 0x20Au);
  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  if ( v5 <= 0x104 )
  {
    v6 = 0;
    v7 = a1;
  }
  else
  {
    v6 = StringCchCopyNW(v19, 0x105u, a1, 0x104u);
    v7 = v19;
  }
  if ( v6 >= 0 )
  {
    lpVtbl = a2->lpVtbl;
    pvar.hVal.QuadPart = (LONGLONG)v7;
    pvar.vt = 31;
    v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))lpVtbl->SetValue)(
           a2,
           &PKEY_ItemName,
           &pvar);
    if ( v6 >= 0 )
    {
      v9 = a2->lpVtbl;
      pvar.vt = 0;
      v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const struct _tagpropertykey *, PROPVARIANT *))v9->GetValue)(
             a2,
             &PKEY_ItemClass,
             &pvar);
      if ( v6 >= 0 && (pvar.vt == 31 && pvar.hVal.QuadPart || pvar.vt == 8) )
      {
        String = CPropVariant::GetString((CPropVariant *)&pvar);
        v11 = -1;
        do
          ++v11;
        while ( String[v11] );
        if ( v11 >= 0x10 && CompareStringOrdinal(String, 16, L"object.container", 16, 1) == 2 )
        {
          v12 = a2->lpVtbl;
          v17 = 31;
          v18 = v7;
          v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int16 *))v12->SetValue)(
                 a2,
                 &PKEY_FileName,
                 &v17);
        }
        v13 = CPropVariant::GetString((CPropVariant *)&pvar);
        do
          ++v4;
        while ( v13[v4] );
        if ( v4 >= 0x21 && CompareStringOrdinal(v13, 33, L"object.container.album.musicAlbum", 33, 1) == 2 )
        {
          v14 = a2->lpVtbl;
          v17 = 31;
          v18 = a1;
          v6 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, __int16 *))v14->SetValue)(
                 a2,
                 &PKEY_Music_AlbumTitle,
                 &v17);
        }
      }
      PropVariantClear(&pvar);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002e990  mov     [rsp-8+arg_10], rbx
0x18002e995  push    rbp
0x18002e996  push    rsi
0x18002e997  push    rdi
0x18002e998  push    r12
0x18002e99a  push    r13
0x18002e99c  push    r14
0x18002e99e  push    r15
0x18002e9a0  lea     rbp, [rsp-180h]
0x18002e9a8  sub     rsp, 280h
0x18002e9af  mov     rax, cs:__security_cookie
0x18002e9b6  xor     rax, rsp
0x18002e9b9  mov     [rbp+1B0h+var_40], rax
0x18002e9c0  mov     rsi, rdx
0x18002e9c3  mov     r14, rcx
0x18002e9c6  xor     edx, edx; Val
0x18002e9c8  lea     rcx, [rsp+2B0h+var_250]; void *
0x18002e9cd  mov     r8d, 20Ah; Size
0x18002e9d3  call    memset_0
0x18002e9d8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002e9dc  mov     rax, rdi
0x18002e9df  xor     r12d, r12d
0x18002e9e2  inc     rax
0x18002e9e5  cmp     [r14+rax*2], r12w
0x18002e9ea  jnz     short loc_18002E9E2
0x18002e9ec  mov     r9d, 104h; unsigned __int64
0x18002e9f2  cmp     rax, r9
0x18002e9f5  jbe     short loc_18002EA11
0x18002e9f7  mov     r8, r14; unsigned __int16 *
0x18002e9fa  lea     edx, [r9+1]; unsigned __int64
0x18002e9fe  lea     rcx, [rsp+2B0h+var_250]; unsigned __int16 *
0x18002ea03  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002ea08  mov     ebx, eax
0x18002ea0a  lea     r15, [rsp+2B0h+var_250]
0x18002ea0f  jmp     short loc_18002EA17
0x18002ea11  mov     ebx, r12d
0x18002ea14  mov     r15, r14
0x18002ea17  test    ebx, ebx
0x18002ea19  js      loc_18002EB79
0x18002ea1f  mov     rax, [rsi]
0x18002ea22  lea     r8, [rsp+2B0h+pvar]
0x18002ea27  mov     r13d, 1Fh
0x18002ea2d  mov     qword ptr [rsp+2B0h+pvar+8], r15
0x18002ea32  lea     rdx, PKEY_ItemName
0x18002ea39  mov     word ptr [rsp+2B0h+pvar], r13w
0x18002ea3f  mov     rcx, rsi
0x18002ea42  mov     rax, [rax+30h]
0x18002ea46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea4b  mov     ebx, eax
0x18002ea4d  test    eax, eax
0x18002ea4f  js      loc_18002EB79
0x18002ea55  mov     rax, [rsi]
0x18002ea58  lea     r8, [rsp+2B0h+pvar]
0x18002ea5d  lea     rdx, PKEY_ItemClass
0x18002ea64  mov     word ptr [rsp+2B0h+pvar], r12w
0x18002ea6a  mov     rcx, rsi
0x18002ea6d  mov     rax, [rax+28h]
0x18002ea71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea76  mov     ebx, eax
0x18002ea78  test    eax, eax
0x18002ea7a  js      loc_18002EB6E
0x18002ea80  cmp     word ptr [rsp+2B0h+pvar], r13w
0x18002ea86  jnz     short loc_18002EA8F
0x18002ea88  cmp     qword ptr [rsp+2B0h+pvar+8], r12
0x18002ea8d  jnz     short loc_18002EA9B
0x18002ea8f  cmp     word ptr [rsp+2B0h+pvar], 8
0x18002ea95  jnz     loc_18002EB6E
0x18002ea9b  lea     rcx, [rsp+2B0h+pvar]; this
0x18002eaa0  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18002eaa5  mov     rcx, rdi
0x18002eaa8  inc     rcx
0x18002eaab  cmp     [rax+rcx*2], r12w
0x18002eab0  jnz     short loc_18002EAA8
0x18002eab2  cmp     rcx, 10h
0x18002eab6  jb      short loc_18002EB06
0x18002eab8  mov     r9d, 10h; cchCount2
0x18002eabe  mov     [rsp+2B0h+bIgnoreCase], 1; bIgnoreCase
0x18002eac6  mov     edx, r9d; cchCount1
0x18002eac9  lea     r8, aObjectContaine_4; "object.container"
0x18002ead0  mov     rcx, rax; lpString1
0x18002ead3  call    cs:__imp_CompareStringOrdinal
0x18002ead9  cmp     eax, 2
0x18002eadc  jnz     short loc_18002EB06
0x18002eade  mov     rax, [rsi]
0x18002eae1  lea     r8, [rsp+2B0h+var_268]
0x18002eae6  lea     rdx, PKEY_FileName
0x18002eaed  mov     [rsp+2B0h+var_268], r13w
0x18002eaf3  mov     rcx, rsi
0x18002eaf6  mov     [rsp+2B0h+var_260], r15
0x18002eafb  mov     rax, [rax+30h]
0x18002eaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb04  mov     ebx, eax
0x18002eb06  lea     rcx, [rsp+2B0h+pvar]; this
0x18002eb0b  call    ?GetString@CPropVariant@@QEBAPEBGXZ; CPropVariant::GetString(void)
0x18002eb10  inc     rdi
0x18002eb13  cmp     [rax+rdi*2], r12w
0x18002eb18  jnz     short loc_18002EB10
0x18002eb1a  cmp     rdi, 21h ; '!'
0x18002eb1e  jb      short loc_18002EB6E
0x18002eb20  mov     r9d, 21h ; '!'; cchCount2
0x18002eb26  mov     [rsp+2B0h+bIgnoreCase], 1; bIgnoreCase
0x18002eb2e  mov     edx, r9d; cchCount1
0x18002eb31  lea     r8, aObjectContaine_3; "object.container.album.musicAlbum"
0x18002eb38  mov     rcx, rax; lpString1
0x18002eb3b  call    cs:__imp_CompareStringOrdinal
0x18002eb41  cmp     eax, 2
0x18002eb44  jnz     short loc_18002EB6E
0x18002eb46  mov     rax, [rsi]
0x18002eb49  lea     r8, [rsp+2B0h+var_268]
0x18002eb4e  lea     rdx, PKEY_Music_AlbumTitle
0x18002eb55  mov     [rsp+2B0h+var_268], r13w
0x18002eb5b  mov     rcx, rsi
0x18002eb5e  mov     [rsp+2B0h+var_260], r14
0x18002eb63  mov     rax, [rax+30h]
0x18002eb67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb6c  mov     ebx, eax
0x18002eb6e  lea     rcx, [rsp+2B0h+pvar]; pvar
0x18002eb73  call    cs:__imp_PropVariantClear
0x18002eb79  mov     eax, ebx
0x18002eb7b  mov     rcx, [rbp+1B0h+var_40]
0x18002eb82  xor     rcx, rsp; StackCookie
0x18002eb85  call    __security_check_cookie
0x18002eb8a  mov     rbx, [rsp+2B0h+arg_10]
0x18002eb92  add     rsp, 280h
0x18002eb99  pop     r15
0x18002eb9b  pop     r14
0x18002eb9d  pop     r13
0x18002eb9f  pop     r12
0x18002eba1  pop     rdi
0x18002eba2  pop     rsi
0x18002eba3  pop     rbp
0x18002eba4  retn
```
