# TMetabase_XMLtable::ParseXMLFile(IXMLDOMDocument *,bool)

- ea: `0x18000ce00`
- end: `0x18000d0ff`
- name: `?ParseXMLFile@TMetabase_XMLtable@@AEAAJPEAUIXMLDOMDocument@@_N@Z`
- size: `767`
- prototype: `__int64 __fastcall(TMetabase_XMLtable *__hidden this, struct IXMLDOMDocument *, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d110`

## callees

- `0x180002bc4`
- `0x18000584c`
- `0x18000c8e4`
- `0x18000ce00`
- `0x180011b38`
- `0x180012734`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000ced9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cee4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ceef`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ced9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cee4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ceef`

## string_xrefs

- `0x18000d0c1`: `inetsrv\iis\mb\config\src\stores\xmltable\metabase_xmltable.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TMetabase_XMLtable::ParseXMLFile(
        TMetabase_XMLtable *this,
        struct IXMLDOMDocument *a2,
        unsigned __int8 a3)
{
  __int64 result; // rax
  int v7; // ebx
  const wchar_t *v8; // rbx
  BSTR v9; // r10
  const wchar_t *v10; // r11
  __int64 v11; // [rsp+88h] [rbp-21h]
  __int64 v12; // [rsp+90h] [rbp-19h]
  int v13; // [rsp+B0h] [rbp+7h] BYREF
  int v14; // [rsp+B4h] [rbp+Bh] BYREF
  __int64 v15; // [rsp+B8h] [rbp+Fh] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp+17h] BYREF
  BSTR v17; // [rsp+C8h] [rbp+1Fh] BYREF
  BSTR v18; // [rsp+D0h] [rbp+27h] BYREF
  _BYTE v19[8]; // [rsp+D8h] [rbp+2Fh] BYREF
  __int64 v20; // [rsp+E0h] [rbp+37h]
  unsigned int v21; // [rsp+118h] [rbp+6Fh] BYREF
  int v22; // [rsp+128h] [rbp+7Fh] BYREF

  result = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))a2->lpVtbl->put_preserveWhiteSpace)(a2, 0);
  if ( (int)result >= 0 )
  {
    result = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, _QWORD))a2->lpVtbl->put_validateOnParse)(
               a2,
               (unsigned __int16)((a3 ^ 1) - 1));
    if ( (int)result >= 0 )
    {
      if ( (int)TMetabase_XMLtable::LoadDocumentFromURL(this, a2) >= 0 )
      {
        return 0;
      }
      else
      {
        v15 = 0;
        v21 = 0;
        v14 = 0;
        v13 = 0;
        v22 = 0;
        v18 = 0;
        v17 = 0;
        bstrString = 0;
        v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))a2->lpVtbl->get_parseError)(a2, &v15);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 56LL))(v15, &v21);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 104LL))(v15, &v14);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 88LL))(v15, &v13);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v15 + 96LL))(v15, &v22);
                if ( v7 >= 0 )
                {
                  v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 72LL))(v15, &v18);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 80LL))(v15, &v17);
                    if ( v7 >= 0 )
                    {
                      v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v15 + 64LL))(v15, &bstrString);
                      if ( v7 >= 0 )
                      {
                        if ( v21 + 2147024894 > 1 && v21 != -2147024864 )
                        {
                          v8 = &word_180034198;
                          v9 = (BSTR)&word_180034198;
                          if ( bstrString )
                            v9 = bstrString;
                          v10 = &word_180034198;
                          if ( v17 )
                            v10 = v17;
                          if ( v18 )
                            v8 = v18;
                          v20 = 0;
                          CErrorInterceptor::Init(
                            (CErrorInterceptor *)v19,
                            (_QWORD *)this + 225,
                            *((_QWORD *)this + 214),
                            v21,
                            2u,
                            -1073606477,
                            L" ",
                            v8,
                            v10,
                            0,
                            14,
                            (__int64)L"MBProperty",
                            1,
                            v13,
                            v22,
                            (__int64)v9,
                            0,
                            v11,
                            v12,
                            -1,
                            -1);
                          CErrorInterceptor::WriteToLog(
                            (CErrorInterceptor *)v19,
                            L"inetsrv\\iis\\mb\\config\\src\\stores\\xmltable\\metabase_xmltable.cpp",
                            1007,
                            *((_DWORD *)this + 415));
                          CErrorInterceptor::~CErrorInterceptor((CErrorInterceptor *)v19);
                        }
                        v7 = -2145318902;
                      }
                    }
                  }
                }
              }
            }
          }
        }
        SysFreeString(bstrString);
        SysFreeString(v17);
        SysFreeString(v18);
        ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(&v15);
        return (unsigned int)v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ce00  mov     [rsp-8+arg_0], rbx
0x18000ce05  mov     [rsp-8+arg_10], rsi
0x18000ce0a  push    rbp
0x18000ce0b  push    rdi
0x18000ce0c  push    r15
0x18000ce0e  lea     rbp, [rsp-47h]
0x18000ce13  sub     rsp, 0F0h
0x18000ce1a  mov     dil, r8b
0x18000ce1d  mov     rbx, rdx
0x18000ce20  mov     rsi, rcx
0x18000ce23  mov     rax, [rdx]
0x18000ce26  xor     edx, edx
0x18000ce28  mov     rcx, rbx
0x18000ce2b  mov     rax, [rax+240h]
0x18000ce32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce37  test    eax, eax
0x18000ce39  js      loc_18000D0E7
0x18000ce3f  mov     rax, [rbx]
0x18000ce42  mov     r15d, 1
0x18000ce48  xor     dil, r15b
0x18000ce4b  movzx   edx, dil
0x18000ce4f  sub     dx, r15w
0x18000ce53  mov     rcx, rbx
0x18000ce56  mov     rax, [rax+220h]
0x18000ce5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce62  test    eax, eax
0x18000ce64  js      loc_18000D0E7
0x18000ce6a  mov     rdx, rbx; struct IXMLDOMDocument *
0x18000ce6d  mov     rcx, rsi; this
0x18000ce70  call    ?LoadDocumentFromURL@TMetabase_XMLtable@@AEAAJPEAUIXMLDOMDocument@@@Z; TMetabase_XMLtable::LoadDocumentFromURL(IXMLDOMDocument *)
0x18000ce75  test    eax, eax
0x18000ce77  jns     loc_18000D0E5
0x18000ce7d  mov     [rbp+57h+var_48], 0
0x18000ce85  mov     [rbp+57h+arg_8], 0
0x18000ce8c  mov     [rbp+57h+var_4C], 0
0x18000ce93  mov     [rbp+57h+var_50], 0
0x18000ce9a  mov     [rbp+57h+arg_18], 0
0x18000cea1  mov     [rbp+57h+var_30], 0
0x18000cea9  mov     [rbp+57h+var_38], 0
0x18000ceb1  mov     [rbp+57h+bstrString], 0
0x18000ceb9  mov     rax, [rbx]
0x18000cebc  lea     rdx, [rbp+57h+var_48]
0x18000cec0  mov     rcx, rbx
0x18000cec3  mov     rax, [rax+1E0h]
0x18000ceca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cecf  mov     ebx, eax
0x18000ced1  test    eax, eax
0x18000ced3  jns     short loc_18000CF06
0x18000ced5  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000ced9  call    cs:__imp_SysFreeString
0x18000cedf  nop
0x18000cee0  mov     rcx, [rbp+57h+var_38]; bstrString
0x18000cee4  call    cs:__imp_SysFreeString
0x18000ceea  nop
0x18000ceeb  mov     rcx, [rbp+57h+var_30]; bstrString
0x18000ceef  call    cs:__imp_SysFreeString
0x18000cef5  nop
0x18000cef6  lea     rcx, [rbp+57h+var_48]
0x18000cefa  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x18000ceff  mov     eax, ebx
0x18000cf01  jmp     loc_18000D0E7
0x18000cf06  mov     rcx, [rbp+57h+var_48]
0x18000cf0a  mov     rax, [rcx]
0x18000cf0d  lea     rdx, [rbp+57h+arg_8]
0x18000cf11  mov     rax, [rax+38h]
0x18000cf15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf1a  mov     ebx, eax
0x18000cf1c  test    eax, eax
0x18000cf1e  js      short loc_18000CED5
0x18000cf20  mov     rcx, [rbp+57h+var_48]
0x18000cf24  mov     rax, [rcx]
0x18000cf27  lea     rdx, [rbp+57h+var_4C]
0x18000cf2b  mov     rax, [rax+68h]
0x18000cf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf34  mov     ebx, eax
0x18000cf36  test    eax, eax
0x18000cf38  js      short loc_18000CED5
0x18000cf3a  mov     rcx, [rbp+57h+var_48]
0x18000cf3e  mov     rax, [rcx]
0x18000cf41  lea     rdx, [rbp+57h+var_50]
0x18000cf45  mov     rax, [rax+58h]
0x18000cf49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf4e  mov     ebx, eax
0x18000cf50  test    eax, eax
0x18000cf52  js      short loc_18000CED5
0x18000cf54  mov     rcx, [rbp+57h+var_48]
0x18000cf58  mov     rax, [rcx]
0x18000cf5b  lea     rdx, [rbp+57h+arg_18]
0x18000cf5f  mov     rax, [rax+60h]
0x18000cf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf68  mov     ebx, eax
0x18000cf6a  test    eax, eax
0x18000cf6c  js      loc_18000CED5
0x18000cf72  mov     rcx, [rbp+57h+var_48]
0x18000cf76  mov     rax, [rcx]
0x18000cf79  lea     rdx, [rbp+57h+var_30]
0x18000cf7d  mov     rax, [rax+48h]
0x18000cf81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf86  mov     ebx, eax
0x18000cf88  test    eax, eax
0x18000cf8a  js      loc_18000CED5
0x18000cf90  mov     rcx, [rbp+57h+var_48]
0x18000cf94  mov     rax, [rcx]
0x18000cf97  lea     rdx, [rbp+57h+var_38]
0x18000cf9b  mov     rax, [rax+50h]
0x18000cf9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfa4  mov     ebx, eax
0x18000cfa6  test    eax, eax
0x18000cfa8  js      loc_18000CED5
0x18000cfae  mov     rcx, [rbp+57h+var_48]
0x18000cfb2  mov     rax, [rcx]
0x18000cfb5  lea     rdx, [rbp+57h+bstrString]
0x18000cfb9  mov     rax, [rax+40h]
0x18000cfbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfc2  mov     ebx, eax
0x18000cfc4  test    eax, eax
0x18000cfc6  js      loc_18000CED5
0x18000cfcc  mov     r9d, [rbp+57h+arg_8]
0x18000cfd0  lea     eax, [r9+7FF8FFFEh]
0x18000cfd7  cmp     eax, r15d
0x18000cfda  jbe     loc_18000D0DB
0x18000cfe0  cmp     r9d, 80070020h
0x18000cfe7  jz      loc_18000D0DB
0x18000cfed  lea     rbx, word_180034198
0x18000cff4  mov     r10, rbx
0x18000cff7  mov     rax, [rbp+57h+bstrString]
0x18000cffb  test    rax, rax
0x18000cffe  cmovnz  r10, rax
0x18000d002  mov     ecx, [rbp+57h+arg_18]
0x18000d005  mov     r8d, [rbp+57h+var_50]
0x18000d009  mov     r11, rbx
0x18000d00c  mov     rax, [rbp+57h+var_38]
0x18000d010  test    rax, rax
0x18000d013  cmovnz  r11, rax
0x18000d017  mov     rax, [rbp+57h+var_30]
0x18000d01b  test    rax, rax
0x18000d01e  cmovnz  rbx, rax
0x18000d022  mov     [rbp+57h+var_20], 0
0x18000d02a  lea     rdx, [rsi+708h]
0x18000d031  or      eax, 0FFFFFFFFh
0x18000d034  mov     [rsp+100h+var_60], eax
0x18000d03b  mov     [rsp+100h+var_68], eax
0x18000d042  mov     [rsp+100h+var_80], 0
0x18000d04d  mov     [rsp+100h+var_88], r10
0x18000d052  mov     [rsp+100h+var_90], ecx
0x18000d056  mov     [rsp+100h+var_98], r8d
0x18000d05b  mov     [rsp+100h+var_A0], r15d
0x18000d060  lea     rax, aMbproperty; "MBProperty"
0x18000d067  mov     [rsp+100h+var_A8], rax
0x18000d06c  mov     [rsp+100h+var_B0], 0Eh
0x18000d074  mov     [rsp+100h+var_B8], 0
0x18000d07d  mov     [rsp+100h+var_C0], r11
0x18000d082  mov     [rsp+100h+var_C8], rbx
0x18000d087  lea     rax, asc_1800340DC; " "
0x18000d08e  mov     [rsp+100h+var_D0], rax
0x18000d093  mov     [rsp+100h+var_D8], 0C00210B3h
0x18000d09b  mov     [rsp+100h+var_E0], 2
0x18000d0a3  mov     r8, [rsi+6B0h]
0x18000d0aa  lea     rcx, [rbp+57h+var_28]
0x18000d0ae  call    ?Init@CErrorInterceptor@@AEAAXPEAPEAUISimpleTableWrite2@@PEAUIAdvancedTableDispenser@@JKKPEBG222K2W4eDETAILEDERRORS_OperationType@@KK2W4eDETAILEDERRORS_Type@@PEAEKKK@Z; CErrorInterceptor::Init(ISimpleTableWrite2 * *,IAdvancedTableDispenser *,long,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,eDETAILEDERRORS_OperationType,ulong,ulong,ushort const *,eDETAILEDERRORS_Type,uchar *,ulong,ulong,ulong)
0x18000d0b3  nop
0x18000d0b4  mov     r9d, [rsi+67Ch]; unsigned int
0x18000d0bb  mov     r8d, 3EFh; unsigned int
0x18000d0c1  lea     rdx, aInetsrvIisMbCo_4; "inetsrv\\iis\\mb\\config\\src\\stores\\"...
0x18000d0c8  lea     rcx, [rbp+57h+var_28]; this
0x18000d0cc  call    ?WriteToLog@CErrorInterceptor@@QEAAJPEBGKK@Z; CErrorInterceptor::WriteToLog(ushort const *,ulong,ulong)
0x18000d0d1  nop
0x18000d0d2  lea     rcx, [rbp+57h+var_28]; this
0x18000d0d6  call    ??1CErrorInterceptor@@QEAA@XZ; CErrorInterceptor::~CErrorInterceptor(void)
0x18000d0db  mov     ebx, 8021080Ah
0x18000d0e0  jmp     loc_18000CED5
0x18000d0e5  xor     eax, eax
0x18000d0e7  lea     r11, [rsp+100h+var_10]
0x18000d0ef  mov     rbx, [r11+20h]
0x18000d0f3  mov     rsi, [r11+30h]
0x18000d0f7  mov     rsp, r11
0x18000d0fa  pop     r15
0x18000d0fc  pop     rdi
0x18000d0fd  pop     rbp
0x18000d0fe  retn
```
