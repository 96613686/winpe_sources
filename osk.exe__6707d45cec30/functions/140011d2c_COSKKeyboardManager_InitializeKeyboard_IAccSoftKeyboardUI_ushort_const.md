# COSKKeyboardManager::InitializeKeyboard(IAccSoftKeyboardUI *,ushort const *)

- ea: `0x140011d2c`
- end: `0x140011efb`
- name: `?InitializeKeyboard@COSKKeyboardManager@@AEAAJPEAUIAccSoftKeyboardUI@@PEBG@Z`
- size: `463`
- prototype: `__int64 __fastcall(COSKKeyboardManager *__hidden this, struct IAccSoftKeyboardUI *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000fe10`

## callees

- `0x140005a30`
- `0x14000f8f4`
- `0x140010c0c`
- `0x140011d2c`
- `0x140025d70`
- `0x140027010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140011e10`
- `KERNEL32!LoadLibraryExW` at `0x140011e24`
- `KERNEL32!LoadLibraryExW` at `0x140011e10`
- `KERNEL32!LoadLibraryExW` at `0x140011e24`
- `OLEAUT32!__imp_SysFreeString` at `0x140011eb7`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ec3`
- `OLEAUT32!__imp_SysFreeString` at `0x140011eb7`
- `OLEAUT32!__imp_SysFreeString` at `0x140011ec3`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140011d7e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x140011d7e`
- `DUI70!StrToID` at `0x140011d72`
- `DUI70!StrToID` at `0x140011d72`

## string_xrefs

- `0x140011dca`: `TabSKB.dll`
- `0x140011deb`: `TipResX.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall COSKKeyboardManager::InitializeKeyboard(
        COSKKeyboardManager *this,
        struct IAccSoftKeyboardUI *a2,
        const unsigned __int16 *a3)
{
  DirectUI::Element *v5; // rbx
  unsigned __int16 v6; // dx
  struct DirectUI::Element *Descendent; // r14
  COSKKeyboardManager *v8; // rcx
  int v9; // r8d
  int SKBFolderPath; // ebx
  HMODULE Library; // rbx
  HMODULE v12; // r8
  LPCWSTR v14; // [rsp+50h] [rbp-298h] BYREF
  LPCWSTR lpLibFileName; // [rsp+58h] [rbp-290h] BYREF
  __int128 v16; // [rsp+60h] [rbp-288h] BYREF
  int v17; // [rsp+70h] [rbp-278h] BYREF
  __int128 v18; // [rsp+74h] [rbp-274h]
  ATL::CAtlException *v19; // [rsp+90h] [rbp-258h] BYREF
  unsigned __int16 v20[264]; // [rsp+A0h] [rbp-248h] BYREF

  v18 = 0;
  v17 = 15;
  v5 = (DirectUI::Element *)*((_QWORD *)this + 15);
  v6 = StrToID(a3);
  Descendent = DirectUI::Element::FindDescendent(v5, v6);
  SKBFolderPath = COSKKeyboardManager::GetSKBFolderPath(v8, v20, v9);
  if ( SKBFolderPath >= 0 )
  {
    try
    {
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&lpLibFileName, v20);
      ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v14, v20);
      SKBFolderPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&lpLibFileName, L"TabSKB.dll", 10);
      if ( SKBFolderPath >= 0 )
      {
        SKBFolderPath = ATL::CComBSTR::Append((ATL::CComBSTR *)&v14, L"TipResX.dll", 11);
        if ( SKBFolderPath >= 0 )
        {
          Library = LoadLibraryExW(lpLibFileName, 0, 0);
          v12 = LoadLibraryExW(v14, 0, 2u);
          *((_QWORD *)this + 31) = v12;
          v16 = 0;
          *(_QWORD *)&v16 = *((_QWORD *)this + 19);
          WORD4(v16) = 30;
          HIDWORD(v18) = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12));
          SKBFolderPath = (*(__int64 (__fastcall **)(struct IAccSoftKeyboardUI *, _QWORD, _QWORD, struct DirectUI::Element *, HMODULE, HMODULE, int *, __int128 *))(*(_QWORD *)a2 + 216LL))(
                            a2,
                            *((_QWORD *)this + 10),
                            *((_QWORD *)this + 11),
                            Descendent,
                            Library,
                            v12,
                            &v17,
                            &v16);
        }
      }
      SysFreeString((BSTR)v14);
      SysFreeString((BSTR)lpLibFileName);
    }
    catch ( ATL::CAtlException *v19 )
    {
      return *(unsigned int *)v19;
    }
  }
  return (unsigned int)SKBFolderPath;
}

```

## disassembly

```asm
0x140011d2c  mov     rax, rsp
0x140011d2f  mov     [rax+20h], rbx
0x140011d33  push    rsi
0x140011d34  push    rdi
0x140011d35  push    r14
0x140011d37  sub     rsp, 2D0h
0x140011d3e  movaps  xmmword ptr [rax-28h], xmm6
0x140011d42  mov     rax, cs:__security_cookie
0x140011d49  xor     rax, rsp
0x140011d4c  mov     [rsp+2E8h+var_38], rax
0x140011d54  mov     rsi, rdx
0x140011d57  mov     rdi, rcx
0x140011d5a  xorps   xmm6, xmm6
0x140011d5d  movdqu  [rsp+2E8h+var_278+4], xmm6
0x140011d63  mov     dword ptr [rsp+2E8h+var_278], 0Fh
0x140011d6b  mov     rbx, [rcx+78h]
0x140011d6f  mov     rcx, r8
0x140011d72  call    cs:__imp_StrToID
0x140011d78  movzx   edx, ax
0x140011d7b  mov     rcx, rbx
0x140011d7e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x140011d84  mov     r14, rax
0x140011d87  lea     rdx, [rsp+2E8h+var_248]; unsigned __int16 *
0x140011d8f  call    ?GetSKBFolderPath@COSKKeyboardManager@@AEAAJPEAGH@Z; COSKKeyboardManager::GetSKBFolderPath(ushort *,int)
0x140011d94  mov     ebx, eax
0x140011d96  test    eax, eax
0x140011d98  js      loc_140011ED0
0x140011d9e  lea     rdx, [rsp+2E8h+var_248]; unsigned __int16 *
0x140011da6  lea     rcx, [rsp+2E8h+lpLibFileName]; this
0x140011dab  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140011db0  nop
0x140011db1  lea     rdx, [rsp+2E8h+var_248]; unsigned __int16 *
0x140011db9  lea     rcx, [rsp+2E8h+var_298]; this
0x140011dbe  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140011dc3  nop
0x140011dc4  mov     r8d, 0Ah; int
0x140011dca  lea     rdx, aTabskbDll; "TabSKB.dll"
0x140011dd1  lea     rcx, [rsp+2E8h+lpLibFileName]; this
0x140011dd6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x140011ddb  mov     ebx, eax
0x140011ddd  test    eax, eax
0x140011ddf  js      loc_140011EB2
0x140011de5  mov     r8d, 0Bh; int
0x140011deb  lea     rdx, aTipresxDll; "TipResX.dll"
0x140011df2  lea     rcx, [rsp+2E8h+var_298]; this
0x140011df7  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x140011dfc  mov     ebx, eax
0x140011dfe  test    eax, eax
0x140011e00  js      loc_140011EB2
0x140011e06  xor     r8d, r8d; dwFlags
0x140011e09  xor     edx, edx; hFile
0x140011e0b  mov     rcx, [rsp+2E8h+lpLibFileName]; lpLibFileName
0x140011e10  call    cs:__imp_LoadLibraryExW
0x140011e16  mov     rbx, rax
0x140011e19  xor     edx, edx; hFile
0x140011e1b  lea     r8d, [rdx+2]; dwFlags
0x140011e1f  mov     rcx, [rsp+2E8h+var_298]; lpLibFileName
0x140011e24  call    cs:__imp_LoadLibraryExW
0x140011e2a  mov     r8, rax
0x140011e2d  mov     [rdi+0F8h], rax
0x140011e34  xorps   xmm0, xmm0
0x140011e37  movups  [rsp+2E8h+var_288], xmm0
0x140011e3c  mov     rcx, [rdi+98h]
0x140011e43  mov     qword ptr [rsp+2E8h+var_288], rcx
0x140011e48  mov     eax, 1Eh
0x140011e4d  mov     word ptr [rsp+2E8h+var_288+8], ax
0x140011e52  movaps  xmm0, [rsp+2E8h+var_288]
0x140011e57  movdqa  [rsp+2E8h+var_288], xmm0
0x140011e5d  movups  xmm1, [rsp+2E8h+var_278]
0x140011e62  movaps  [rsp+2E8h+var_278], xmm1
0x140011e67  psrldq  xmm6, 0Ch
0x140011e6c  movd    [rsp+2E8h+var_268], xmm6
0x140011e75  mov     rax, [rsi]
0x140011e78  lea     rcx, [rsp+2E8h+var_288]
0x140011e7d  mov     [rsp+2E8h+var_2B0], rcx
0x140011e82  lea     rcx, [rsp+2E8h+var_278]
0x140011e87  mov     [rsp+2E8h+var_2B8], rcx
0x140011e8c  mov     [rsp+2E8h+var_2C0], r8
0x140011e91  mov     [rsp+2E8h+var_2C8], rbx
0x140011e96  mov     r9, r14
0x140011e99  mov     r8, [rdi+58h]
0x140011e9d  mov     rdx, [rdi+50h]
0x140011ea1  mov     rcx, rsi
0x140011ea4  mov     rax, [rax+0D8h]
0x140011eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011eb0  mov     ebx, eax
0x140011eb2  mov     rcx, [rsp+2E8h+var_298]; bstrString
0x140011eb7  call    cs:__imp_SysFreeString
0x140011ebd  nop
0x140011ebe  mov     rcx, [rsp+2E8h+lpLibFileName]; bstrString
0x140011ec3  call    cs:__imp_SysFreeString
0x140011ec9  nop
0x140011eca  jmp     short loc_140011ED0
0x140011ecc  mov     ebx, dword ptr [rsp+2E8h+var_298]
0x140011ed0  mov     eax, ebx
0x140011ed2  mov     rcx, [rsp+2E8h+var_38]
0x140011eda  xor     rcx, rsp; StackCookie
0x140011edd  call    __security_check_cookie
0x140011ee2  lea     r11, [rsp+2E8h+var_18]
0x140011eea  mov     rbx, [r11+38h]
0x140011eee  movaps  xmm6, xmmword ptr [r11-10h]
0x140011ef3  mov     rsp, r11
0x140011ef6  pop     r14
0x140011ef8  pop     rdi
0x140011ef9  pop     rsi
0x140011efa  retn
```
