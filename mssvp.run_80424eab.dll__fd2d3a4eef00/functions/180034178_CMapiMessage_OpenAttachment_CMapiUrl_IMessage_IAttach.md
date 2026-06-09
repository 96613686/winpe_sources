# CMapiMessage::OpenAttachment(CMapiUrl &,IMessage *,IAttach * *)

- ea: `0x180034178`
- end: `0x180034405`
- name: `?OpenAttachment@CMapiMessage@@SAJAEAVCMapiUrl@@PEAUIMessage@@PEAPEAUIAttach@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct CMapiUrl *, struct IMessage *, struct IAttach **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180028254`

## callees

- `0x1800048c0`
- `0x180006270`
- `0x180013d10`
- `0x180018758`
- `0x18002a1a8`
- `0x18002a7f4`
- `0x180034178`
- `0x180038b1c`
- `0x18003d010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800343a7`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_FreeProws` at `0x1800343a7`

## pseudocode

```c
__int64 __fastcall CMapiMessage::OpenAttachment(struct CMapiUrl *a1, struct IMessage *a2, struct IAttach **a3)
{
  int v4; // ebx
  int v5; // eax
  int v6; // r15d
  size_t v7; // r13
  LPSRowSet v8; // rsi
  ULONG i; // r14d
  LPSPropValue lpProps; // rdi
  int v12; // [rsp+30h] [rbp-39h] BYREF
  int v13; // [rsp+34h] [rbp-35h] BYREF
  __int64 v14; // [rsp+38h] [rbp-31h] BYREF
  LPSRowSet lpRows; // [rsp+40h] [rbp-29h] BYREF
  wchar_t *v16; // [rsp+48h] [rbp-21h] BYREF
  struct IAttach **v17; // [rsp+50h] [rbp-19h]
  size_t Size[2]; // [rsp+58h] [rbp-11h] BYREF
  _DWORD v19[8]; // [rsp+68h] [rbp-1h] BYREF

  v17 = a3;
  v13 = 0;
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
    &v16,
    (char *)a1 + 72);
  CEntryId::CEntryId((CEntryId *)Size, v16, &v13);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&v16);
  v12 = 0;
  v19[0] = 6;
  v19[1] = 237043715;
  v19[2] = 267976962;
  v19[3] = 923074563;
  v19[4] = 2147352587;
  v19[5] = 2147418123;
  v19[6] = 924057603;
  v14 = 0;
  v4 = v13;
  if ( v13 >= 0 )
  {
    v5 = ((__int64 (__fastcall *)(struct IMessage *, __int64, __int64 *))a2->lpVtbl->put_From)(a2, 0x80000000LL, &v14);
    v4 = v5;
    if ( v5 == -2147221245 )
    {
      v5 = ((__int64 (__fastcall *)(struct IMessage *, _QWORD, __int64 *))a2->lpVtbl->put_From)(a2, 0, &v14);
      v4 = v5;
    }
    if ( v5 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)v14 + 56LL))(v14, v19, 2);
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v14 + 72LL))(v14, 0, &v12);
    }
  }
  lpRows = 0;
  v6 = 0;
  if ( v4 >= 0 )
  {
    v7 = LODWORD(Size[0]);
    do
    {
      if ( !v12 )
        break;
      if ( v6 )
        break;
      v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPSRowSet *))(*(_QWORD *)v14 + 152LL))(
             v14,
             10,
             0,
             &lpRows);
      if ( v4 < 0 )
        break;
      v8 = lpRows;
      if ( !lpRows->cRows )
        goto LABEL_32;
      for ( i = 0; i < v8->cRows; ++i )
      {
        lpProps = v8->aRow[i].lpProps;
        if ( (lpProps[3].ulPropTag != 2147352587 || !lpProps[3].Value.i)
          && (lpProps[4].ulPropTag != 2147418123 || !lpProps[4].Value.i)
          && (lpProps[5].ulPropTag != 924057603 || (LOBYTE(lpProps[5].Value.flt) & 4) == 0)
          && lpProps[2].ulPropTag == 923074563
          && lpProps[2].Value.l == 1
          && lpProps->ulPropTag == 237043715
          && lpProps[1].ulPropTag == 267976962
          && lpProps[1].Value.l == (_DWORD)v7
          && !memcmp_0(lpProps[1].Value.bin.lpb, (const void *)Size[1], v7) )
        {
          v4 = ((__int64 (__fastcall *)(struct IMessage *, _QWORD, _QWORD, _QWORD, struct IAttach **))a2->lpVtbl->get_Keywords)(
                 a2,
                 lpProps->Value.ul,
                 0,
                 0,
                 v17);
          v6 = 1;
          v8 = lpRows;
          break;
        }
      }
      v12 -= v8->cRows;
      FreeProws(v8);
      lpRows = 0;
    }
    while ( v4 >= 0 );
    if ( v4 >= 0 && !v6 )
LABEL_32:
      v4 = -2147467259;
  }
  TComNoUnkPointer<CPinnedFilter>::~TComNoUnkPointer<CPinnedFilter>(&v14);
  CEntryId::FreeBuffer((CEntryId *)Size);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180034178  mov     [rsp-8+arg_18], rbx
0x18003417d  push    rbp
0x18003417e  push    rsi
0x18003417f  push    rdi
0x180034180  push    r12
0x180034182  push    r13
0x180034184  push    r14
0x180034186  push    r15
0x180034188  lea     rbp, [rsp-27h]
0x18003418d  sub     rsp, 90h
0x180034194  mov     rax, cs:__security_cookie
0x18003419b  xor     rax, rsp
0x18003419e  mov     [rbp+57h+var_38], rax
0x1800341a2  mov     [rbp+57h+var_70], r8
0x1800341a6  mov     r12, rdx
0x1800341a9  xor     edi, edi
0x1800341ab  mov     [rbp+57h+var_8C], edi
0x1800341ae  lea     rdx, [rcx+48h]
0x1800341b2  lea     rcx, [rbp+57h+var_78]
0x1800341b6  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x1800341bb  lea     r8, [rbp+57h+var_8C]; int *
0x1800341bf  mov     rdx, [rbp+57h+var_78]; wchar_t *
0x1800341c3  lea     rcx, [rbp+57h+Size]; this
0x1800341c7  call    ??0CEntryId@@QEAA@PEB_WPEAJ@Z; CEntryId::CEntryId(wchar_t const *,long *)
0x1800341cc  nop
0x1800341cd  lea     rcx, [rbp+57h+var_78]
0x1800341d1  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x1800341d6  mov     [rbp+57h+var_90], edi
0x1800341d9  mov     [rbp+57h+var_58], 6
0x1800341e0  mov     [rbp+57h+var_54], 0E210003h
0x1800341e7  mov     [rbp+57h+var_50], 0FF90102h
0x1800341ee  mov     [rbp+57h+var_4C], 37050003h
0x1800341f5  mov     [rbp+57h+var_48], 7FFE000Bh
0x1800341fc  mov     [rbp+57h+var_44], 7FFF000Bh
0x180034203  mov     [rbp+57h+var_40], 37140003h
0x18003420a  mov     [rbp+57h+var_88], rdi
0x18003420e  mov     ebx, [rbp+57h+var_8C]
0x180034211  test    ebx, ebx
0x180034213  js      short loc_18003428B
0x180034215  mov     rax, [r12]
0x180034219  lea     r8, [rbp+57h+var_88]
0x18003421d  mov     edx, 80000000h
0x180034222  mov     rcx, r12
0x180034225  mov     rax, [rax+70h]
0x180034229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003422e  mov     ebx, eax
0x180034230  cmp     eax, 80040103h
0x180034235  jnz     short loc_18003424F
0x180034237  mov     rax, [r12]
0x18003423b  lea     r8, [rbp+57h+var_88]
0x18003423f  xor     edx, edx
0x180034241  mov     rcx, r12
0x180034244  mov     rax, [rax+70h]
0x180034248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003424d  mov     ebx, eax
0x18003424f  test    eax, eax
0x180034251  js      short loc_18003428B
0x180034253  mov     rcx, [rbp+57h+var_88]
0x180034257  mov     rax, [rcx]
0x18003425a  mov     r8d, 2
0x180034260  lea     rdx, [rbp+57h+var_58]
0x180034264  mov     rax, [rax+38h]
0x180034268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003426d  mov     ebx, eax
0x18003426f  test    eax, eax
0x180034271  js      short loc_18003428B
0x180034273  mov     rcx, [rbp+57h+var_88]
0x180034277  mov     rax, [rcx]
0x18003427a  lea     r8, [rbp+57h+var_90]
0x18003427e  xor     edx, edx
0x180034280  mov     rax, [rax+48h]
0x180034284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034289  mov     ebx, eax
0x18003428b  mov     [rbp+57h+lpRows], rdi
0x18003428f  mov     r15d, edi
0x180034292  test    ebx, ebx
0x180034294  js      loc_1800343C9
0x18003429a  mov     r13d, dword ptr [rbp+57h+Size]
0x18003429e  cmp     [rbp+57h+var_90], edi
0x1800342a1  jbe     loc_1800343BB
0x1800342a7  test    r15d, r15d
0x1800342aa  jnz     loc_1800343BB
0x1800342b0  mov     rcx, [rbp+57h+var_88]
0x1800342b4  mov     rax, [rcx]
0x1800342b7  lea     r9, [rbp+57h+lpRows]
0x1800342bb  xor     r8d, r8d
0x1800342be  lea     edx, [r15+0Ah]
0x1800342c2  mov     rax, [rax+98h]
0x1800342c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342ce  mov     ebx, eax
0x1800342d0  test    eax, eax
0x1800342d2  js      loc_1800343BB
0x1800342d8  mov     rsi, [rbp+57h+lpRows]
0x1800342dc  cmp     [rsi], edi
0x1800342de  jz      loc_1800343C4
0x1800342e4  mov     r14d, edi
0x1800342e7  cmp     r14d, [rsi]
0x1800342ea  jnb     loc_18003439F
0x1800342f0  mov     eax, r14d
0x1800342f3  inc     rax
0x1800342f6  add     rax, rax
0x1800342f9  mov     rdi, [rsi+rax*8]
0x1800342fd  xor     eax, eax
0x1800342ff  cmp     dword ptr [rdi+48h], 7FFE000Bh
0x180034306  jnz     short loc_18003430E
0x180034308  cmp     [rdi+50h], ax
0x18003430c  jnz     short loc_180034369
0x18003430e  cmp     dword ptr [rdi+60h], 7FFF000Bh
0x180034315  jnz     short loc_18003431D
0x180034317  cmp     [rdi+68h], ax
0x18003431b  jnz     short loc_180034369
0x18003431d  cmp     dword ptr [rdi+78h], 37140003h
0x180034324  jnz     short loc_18003432F
0x180034326  test    byte ptr [rdi+80h], 4
0x18003432d  jnz     short loc_180034369
0x18003432f  cmp     dword ptr [rdi+30h], 37050003h
0x180034336  jnz     short loc_180034369
0x180034338  cmp     dword ptr [rdi+38h], 1
0x18003433c  jnz     short loc_180034369
0x18003433e  cmp     dword ptr [rdi], 0E210003h
0x180034344  jnz     short loc_180034369
0x180034346  cmp     dword ptr [rdi+18h], 0FF90102h
0x18003434d  jnz     short loc_180034369
0x18003434f  cmp     [rdi+20h], r13d
0x180034353  jnz     short loc_180034369
0x180034355  mov     r8, r13; Size
0x180034358  mov     rdx, [rbp+57h+Buf2]; Buf2
0x18003435c  mov     rcx, [rdi+28h]; Buf1
0x180034360  call    memcmp_0
0x180034365  test    eax, eax
0x180034367  jz      short loc_180034371
0x180034369  inc     r14d
0x18003436c  jmp     loc_1800342E7
0x180034371  mov     rax, [r12]
0x180034375  mov     rcx, [rbp+57h+var_70]
0x180034379  mov     [rsp+0C0h+var_A0], rcx
0x18003437e  xor     r9d, r9d
0x180034381  xor     r8d, r8d
0x180034384  mov     edx, [rdi+8]
0x180034387  mov     rcx, r12
0x18003438a  mov     rax, [rax+78h]
0x18003438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034393  mov     ebx, eax
0x180034395  mov     r15d, 1
0x18003439b  mov     rsi, [rbp+57h+lpRows]
0x18003439f  mov     eax, [rsi]
0x1800343a1  sub     [rbp+57h+var_90], eax
0x1800343a4  mov     rcx, rsi; lpRows
0x1800343a7  call    cs:__imp_FreeProws
0x1800343ad  xor     edi, edi
0x1800343af  mov     [rbp+57h+lpRows], rdi
0x1800343b3  test    ebx, ebx
0x1800343b5  jns     loc_18003429E
0x1800343bb  test    ebx, ebx
0x1800343bd  js      short loc_1800343C9
0x1800343bf  test    r15d, r15d
0x1800343c2  jnz     short loc_1800343C9
0x1800343c4  mov     ebx, 80004005h
0x1800343c9  lea     rcx, [rbp+57h+var_88]
0x1800343cd  call    ??1?$TComNoUnkPointer@VCPinnedFilter@@@@QEAA@XZ; TComNoUnkPointer<CPinnedFilter>::~TComNoUnkPointer<CPinnedFilter>(void)
0x1800343d2  nop
0x1800343d3  lea     rcx, [rbp+57h+Size]; this
0x1800343d7  call    ?FreeBuffer@CEntryId@@AEAAXXZ; CEntryId::FreeBuffer(void)
0x1800343dc  mov     eax, ebx
0x1800343de  mov     rcx, [rbp+57h+var_38]
0x1800343e2  xor     rcx, rsp; StackCookie
0x1800343e5  call    __security_check_cookie
0x1800343ea  mov     rbx, [rsp+0C0h+arg_18]
0x1800343f2  add     rsp, 90h
0x1800343f9  pop     r15
0x1800343fb  pop     r14
0x1800343fd  pop     r13
0x1800343ff  pop     r12
0x180034401  pop     rdi
0x180034402  pop     rsi
0x180034403  pop     rbp
0x180034404  retn
```
