# CMapiPreviewer::GetMessageType(IMessage *)

- ea: `0x180025780`
- end: `0x180025866`
- name: `?GetMessageType@CMapiPreviewer@@AEAAJPEAUIMessage@@@Z`
- size: `230`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this, struct IMessage *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180025a90`

## callees

- `0x180004850`
- `0x1800048c0`
- `0x180025780`
- `0x180025948`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002580e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002580e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::GetMessageType(CMapiPreviewer *this, struct IMessage *a2)
{
  __int64 v4; // rcx
  int StringProp; // ebp
  unsigned int v6; // edi
  const WCHAR *v7; // rbx
  const WCHAR *lpString2; // rcx
  unsigned __int64 cchCount2; // r9
  unsigned int v10; // eax
  int v11; // ecx
  PCNZWCH lpString1; // [rsp+50h] [rbp+8h] BYREF

  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&lpString1);
  StringProp = CMapiPreviewer::GetStringProp(v4, a2, 1703967, &lpString1);
  *((_DWORD *)this + 56) = 11;
  if ( StringProp >= 0 )
  {
    v6 = 0;
    v7 = lpString1;
    while ( v6 < 0xB )
    {
      lpString2 = off_180040F10[v6];
      cchCount2 = -1;
      do
        ++cchCount2;
      while ( lpString2[cchCount2] );
      if ( *((unsigned int *)v7 - 4) >= cchCount2 && CompareStringW(0x7Fu, 1u, v7, cchCount2, lpString2, cchCount2) == 2 )
      {
        *((_DWORD *)this + 56) = v6;
        break;
      }
      ++v6;
    }
    v10 = *((_DWORD *)this + 56);
    if ( v10 > 7 || (v11 = 165, !_bittest(&v11, v10)) )
    {
      *((_DWORD *)this + 56) = 11;
      StringProp = -2147467259;
    }
  }
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(&lpString1);
  return (unsigned int)StringProp;
}

```

## disassembly

```asm
0x180025780  mov     [rsp+arg_8], rbx
0x180025785  mov     [rsp+arg_10], rbp
0x18002578a  push    rsi
0x18002578b  push    rdi
0x18002578c  push    r15
0x18002578e  sub     rsp, 30h
0x180025792  mov     rbx, rdx
0x180025795  mov     rsi, rcx
0x180025798  lea     rcx, [rsp+48h+lpString1]
0x18002579d  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x1800257a2  nop
0x1800257a3  lea     r9, [rsp+48h+lpString1]
0x1800257a8  mov     r8d, 1A001Fh
0x1800257ae  mov     rdx, rbx
0x1800257b1  call    ?GetStringProp@CMapiPreviewer@@AEAAJPEAUIMessage@@KAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z; CMapiPreviewer::GetStringProp(IMessage *,ulong,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x1800257b6  mov     ebp, eax
0x1800257b8  mov     dword ptr [rsi+0E0h], 0Bh
0x1800257c2  xor     r15d, r15d
0x1800257c5  test    eax, eax
0x1800257c7  js      short loc_180025847
0x1800257c9  mov     edi, r15d
0x1800257cc  mov     rbx, [rsp+48h+lpString1]
0x1800257d1  cmp     edi, 0Bh
0x1800257d4  jnb     short loc_180025823
0x1800257d6  mov     eax, edi
0x1800257d8  lea     rcx, off_180040F10; "IPM.Schedule.Meeting"
0x1800257df  mov     rcx, [rcx+rax*8]
0x1800257e3  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800257e7  inc     r9; cchCount1
0x1800257ea  cmp     [rcx+r9*2], r15w
0x1800257ef  jnz     short loc_1800257E7
0x1800257f1  mov     eax, [rbx-10h]
0x1800257f4  cmp     rax, r9
0x1800257f7  jb      short loc_180025819
0x1800257f9  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x1800257fe  mov     [rsp+48h+lpString2], rcx; lpString2
0x180025803  mov     r8, rbx; lpString1
0x180025806  mov     edx, 1; dwCmpFlags
0x18002580b  lea     ecx, [rdx+7Eh]; Locale
0x18002580e  call    cs:__imp_CompareStringW
0x180025814  cmp     eax, 2
0x180025817  jz      short loc_18002581D
0x180025819  inc     edi
0x18002581b  jmp     short loc_1800257D1
0x18002581d  mov     [rsi+0E0h], edi
0x180025823  mov     eax, [rsi+0E0h]
0x180025829  cmp     eax, 7
0x18002582c  ja      short loc_180025838
0x18002582e  mov     ecx, 0A5h
0x180025833  bt      ecx, eax
0x180025836  jb      short loc_180025847
0x180025838  mov     dword ptr [rsi+0E0h], 0Bh
0x180025842  mov     ebp, 80004005h
0x180025847  lea     rcx, [rsp+48h+lpString1]
0x18002584c  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x180025851  mov     eax, ebp
0x180025853  mov     rbx, [rsp+48h+arg_8]
0x180025858  mov     rbp, [rsp+48h+arg_10]
0x18002585d  add     rsp, 30h
0x180025861  pop     r15
0x180025863  pop     rdi
0x180025864  pop     rsi
0x180025865  retn
```
