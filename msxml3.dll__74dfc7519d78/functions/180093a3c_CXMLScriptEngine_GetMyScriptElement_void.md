# CXMLScriptEngine::GetMyScriptElement(void)

- ea: `0x180093a3c`
- end: `0x180093cee`
- name: `?GetMyScriptElement@CXMLScriptEngine@@AEAAPEAUIHTMLElement@@XZ`
- size: `690`
- prototype: `struct IHTMLElement *__fastcall(CXMLScriptEngine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180094070`

## callees

- `0x180064820`
- `0x180093a3c`
- `0x180094610`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180093a95`
- `OLEAUT32!__imp_SysAllocString` at `0x180093a95`
- `OLEAUT32!__imp_SysFreeString` at `0x180093c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180093cca`
- `OLEAUT32!__imp_SysFreeString` at `0x180093c90`
- `OLEAUT32!__imp_SysFreeString` at `0x180093cca`
- `OLEAUT32!__imp_VariantInit` at `0x180093b04`
- `OLEAUT32!__imp_VariantInit` at `0x180093b04`
- `OLEAUT32!__imp_VariantClear` at `0x180093c86`
- `OLEAUT32!__imp_VariantClear` at `0x180093c86`

## string_xrefs

- `0x180093a73`: `XMLDocument`
- `0x180093c21`: `text/XML`

## pseudocode

```c
OLECHAR *__fastcall CXMLScriptEngine::GetMyScriptElement(CXMLScriptEngine *this)
{
  OLECHAR *result; // rax
  OLECHAR *v3; // r15
  int v4; // esi
  int v5; // edi
  bool v6; // r14
  bool v7; // bl
  __int64 v8; // xmm6_8
  __int64 v9; // rax
  void *v10; // [rsp+38h] [rbp-79h] BYREF
  __int64 v11; // [rsp+40h] [rbp-71h] BYREF
  void *v12[2]; // [rsp+48h] [rbp-69h] BYREF
  VARIANTARG v13; // [rsp+58h] [rbp-59h] BYREF
  __int128 v14; // [rsp+78h] [rbp-39h]
  __int64 v15; // [rsp+88h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+90h] [rbp-21h] BYREF
  __int128 v17; // [rsp+A8h] [rbp-9h] BYREF
  __int64 v18; // [rsp+B8h] [rbp+7h]
  int v19; // [rsp+120h] [rbp+6Fh] BYREF
  void *v20; // [rsp+128h] [rbp+77h] BYREF
  BSTR bstrString; // [rsp+130h] [rbp+7Fh] BYREF

  v20 = 0;
  v15 = 0;
  v19 = 0;
  v12[0] = 0;
  v10 = 0;
  v14 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  result = SysAllocString(L"XMLDocument");
  v3 = result;
  if ( result )
  {
    if ( (*(int (__fastcall **)(_QWORD, void **))(**((_QWORD **)this + 5) + 144LL))(*((_QWORD *)this + 5), &v10) >= 0 )
    {
      if ( v10 )
      {
        v4 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v10 + 72LL))(v10, &v19);
        if ( v4 >= 0 )
        {
          v5 = 0;
          LOWORD(v14) = 3;
          DWORD2(v14) = 0;
          v6 = 0;
          v7 = 0;
          VariantInit(&pvarg);
          if ( v19 > 0 )
          {
            v8 = v15;
            do
            {
              if ( v4 < 0 || v6 )
                break;
              *(_OWORD *)&v13.vt = *(_OWORD *)&pvarg.vt;
              v9 = *(_QWORD *)v10;
              v13.pRecInfo = pvarg.pRecInfo;
              v17 = v14;
              v18 = v8;
              v4 = (*(__int64 (__fastcall **)(void *, __int128 *, VARIANTARG *, void **))(v9 + 88))(
                     v10,
                     &v17,
                     &v13,
                     v12);
              if ( v4 >= 0 && v12[0] )
              {
                if ( (**(int (__fastcall ***)(void *, GUID *, void **))v12[0])(v12[0], &IID_IHTMLElement, &v20) >= 0 )
                {
                  bstrString = 0;
                  (*(void (__fastcall **)(void *, BSTR *))(*(_QWORD *)v20 + 344LL))(v20, &bstrString);
                  if ( bstrString )
                  {
                    v7 = (unsigned int)fastcmpi(bstrString, L"XML") == 0;
                  }
                  else
                  {
                    v11 = 0;
                    v4 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v20)(
                           v20,
                           &IID_IHTMLScriptElement,
                           &v11);
                    if ( v11 )
                    {
                      (*(void (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v11 + 168LL))(v11, &bstrString);
                      v7 = bstrString && !(unsigned int)fastcmpi(bstrString, L"text/XML");
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                    }
                  }
                  if ( v7 )
                  {
                    memset(&v13, 0, sizeof(v13));
                    v4 = (*(__int64 (__fastcall **)(void *, OLECHAR *, __int64, VARIANTARG *))(*(_QWORD *)v20 + 64LL))(
                           v20,
                           v3,
                           1,
                           &v13);
                    if ( v4 >= 0 )
                    {
                      v6 = v13.vt == 1;
                      VariantClear(&v13);
                    }
                  }
                  SysFreeString(bstrString);
                }
                ReleaseInterface(v12);
                if ( !v6 )
                {
                  DWORD2(v14) = ++v5;
                  ReleaseInterface(&v20);
                  v7 = 0;
                }
              }
            }
            while ( v5 < v19 );
          }
        }
      }
    }
    ReleaseInterface(&v10);
    SysFreeString(v3);
    return (OLECHAR *)v20;
  }
  return result;
}

```

## disassembly

```asm
0x180093a3c  mov     rax, rsp
0x180093a3f  push    rbp
0x180093a40  push    rbx
0x180093a41  push    rsi
0x180093a42  push    rdi
0x180093a43  push    r13
0x180093a45  push    r14
0x180093a47  push    r15
0x180093a49  lea     rbp, [rax-5Fh]
0x180093a4d  sub     rsp, 0D0h
0x180093a54  movaps  xmmword ptr [rax-48h], xmm6
0x180093a58  mov     rbx, rcx
0x180093a5b  xor     eax, eax
0x180093a5d  mov     [rbp+57h+arg_10], 0
0x180093a65  xorps   xmm0, xmm0
0x180093a68  mov     [rbp+57h+var_80], rax
0x180093a6c  xorps   xmm1, xmm1
0x180093a6f  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180093a73  lea     rcx, aXmldocument; "XMLDocument"
0x180093a7a  mov     [rbp+57h+arg_8], eax
0x180093a7d  mov     [rbp+57h+var_C0], 0
0x180093a85  mov     [rbp+57h+var_D0], 0
0x180093a8d  movups  [rbp+57h+var_90], xmm0
0x180093a91  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x180093a95  call    cs:__imp_SysAllocString
0x180093a9b  mov     r15, rax
0x180093a9e  test    rax, rax
0x180093aa1  jz      loc_180093CD4
0x180093aa7  mov     rcx, [rbx+28h]
0x180093aab  lea     rdx, [rbp+57h+var_D0]
0x180093aaf  mov     rax, [rcx]
0x180093ab2  mov     rax, [rax+90h]
0x180093ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093abe  test    eax, eax
0x180093ac0  js      loc_180093CBE
0x180093ac6  mov     rcx, [rbp+57h+var_D0]
0x180093aca  test    rcx, rcx
0x180093acd  jz      loc_180093CBE
0x180093ad3  mov     rax, [rcx]
0x180093ad6  lea     rdx, [rbp+57h+arg_8]
0x180093ada  mov     rax, [rax+48h]
0x180093ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ae3  mov     esi, eax
0x180093ae5  test    eax, eax
0x180093ae7  js      loc_180093CBE
0x180093aed  mov     eax, 3
0x180093af2  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180093af6  xor     edi, edi
0x180093af8  mov     word ptr [rbp+57h+var_90], ax
0x180093afc  mov     dword ptr [rbp+57h+var_90+8], edi
0x180093aff  xor     r14b, r14b
0x180093b02  xor     bl, bl
0x180093b04  call    cs:__imp_VariantInit
0x180093b0a  cmp     [rbp+57h+arg_8], edi
0x180093b0d  jle     loc_180093CBE
0x180093b13  movsd   xmm6, [rbp+57h+var_80]
0x180093b18  lea     r13d, [rdi+1]
0x180093b1c  test    esi, esi
0x180093b1e  js      loc_180093CBE
0x180093b24  test    r14b, r14b
0x180093b27  jnz     loc_180093CBE
0x180093b2d  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180093b31  mov     rcx, [rbp+57h+var_D0]
0x180093b35  lea     r9, [rbp+57h+var_C0]
0x180093b39  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180093b3e  lea     r8, [rbp+57h+var_B0]
0x180093b42  movaps  xmmword ptr [rbp+57h+var_B0], xmm0
0x180093b46  lea     rdx, [rbp+57h+var_60]
0x180093b4a  movups  xmm0, [rbp+57h+var_90]
0x180093b4e  mov     rax, [rcx]
0x180093b51  movsd   qword ptr [rbp+57h+var_B0+10h], xmm1
0x180093b56  movaps  [rbp+57h+var_60], xmm0
0x180093b5a  movsd   [rbp+57h+var_50], xmm6
0x180093b5f  mov     rax, [rax+58h]
0x180093b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b68  mov     esi, eax
0x180093b6a  test    eax, eax
0x180093b6c  js      loc_180093CB5
0x180093b72  mov     rcx, [rbp+57h+var_C0]
0x180093b76  test    rcx, rcx
0x180093b79  jz      loc_180093CB5
0x180093b7f  mov     rax, [rcx]
0x180093b82  lea     r8, [rbp+57h+arg_10]
0x180093b86  lea     rdx, IID_IHTMLElement
0x180093b8d  mov     rax, [rax]
0x180093b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b95  test    eax, eax
0x180093b97  js      loc_180093C96
0x180093b9d  mov     rcx, [rbp+57h+arg_10]
0x180093ba1  lea     rdx, [rbp+57h+bstrString]
0x180093ba5  mov     [rbp+57h+bstrString], 0
0x180093bad  mov     rax, [rcx]
0x180093bb0  mov     rax, [rax+158h]
0x180093bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bbc  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180093bc0  test    rcx, rcx
0x180093bc3  jz      short loc_180093BD8
0x180093bc5  lea     rdx, aXml_1; "XML"
0x180093bcc  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x180093bd1  test    eax, eax
0x180093bd3  setz    bl
0x180093bd6  jmp     short loc_180093C48
0x180093bd8  mov     rcx, [rbp+57h+arg_10]
0x180093bdc  lea     r8, [rbp+57h+var_C8]
0x180093be0  mov     [rbp+57h+var_C8], 0
0x180093be8  lea     rdx, IID_IHTMLScriptElement
0x180093bef  mov     rax, [rcx]
0x180093bf2  mov     rax, [rax]
0x180093bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bfa  mov     rcx, [rbp+57h+var_C8]
0x180093bfe  mov     esi, eax
0x180093c00  test    rcx, rcx
0x180093c03  jz      short loc_180093C48
0x180093c05  mov     rax, [rcx]
0x180093c08  lea     rdx, [rbp+57h+bstrString]
0x180093c0c  mov     rax, [rax+0A8h]
0x180093c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c18  mov     rcx, [rbp+57h+bstrString]; unsigned __int16 *
0x180093c1c  test    rcx, rcx
0x180093c1f  jz      short loc_180093C36
0x180093c21  lea     rdx, aTextXml; "text/XML"
0x180093c28  call    ?fastcmpi@@YAHPEBG0@Z; fastcmpi(ushort const *,ushort const *)
0x180093c2d  test    eax, eax
0x180093c2f  jnz     short loc_180093C36
0x180093c31  mov     bl, r13b
0x180093c34  jmp     short loc_180093C38
0x180093c36  xor     bl, bl
0x180093c38  mov     rcx, [rbp+57h+var_C8]
0x180093c3c  mov     rax, [rcx]
0x180093c3f  mov     rax, [rax+10h]
0x180093c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c48  test    bl, bl
0x180093c4a  jz      short loc_180093C8C
0x180093c4c  mov     rcx, [rbp+57h+arg_10]
0x180093c50  lea     r9, [rbp+57h+var_B0]
0x180093c54  xor     eax, eax
0x180093c56  xorps   xmm0, xmm0
0x180093c59  mov     qword ptr [rbp+57h+var_B0+10h], rax
0x180093c5d  mov     r8d, r13d
0x180093c60  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x180093c64  mov     rax, [rcx]
0x180093c67  mov     rdx, r15
0x180093c6a  mov     rax, [rax+40h]
0x180093c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c73  mov     esi, eax
0x180093c75  test    eax, eax
0x180093c77  js      short loc_180093C8C
0x180093c79  cmp     r13w, word ptr [rbp+57h+var_B0]
0x180093c7e  lea     rcx, [rbp+57h+var_B0]; pvarg
0x180093c82  setz    r14b
0x180093c86  call    cs:__imp_VariantClear
0x180093c8c  mov     rcx, [rbp+57h+bstrString]; bstrString
0x180093c90  call    cs:__imp_SysFreeString
0x180093c96  lea     rcx, [rbp+57h+var_C0]; void **
0x180093c9a  call    ?ReleaseInterface@@YAKPEAPEAX@Z; ReleaseInterface(void * *)
0x180093c9f  test    r14b, r14b
0x180093ca2  jnz     short loc_180093CB5
0x180093ca4  add     edi, r13d
0x180093ca7  lea     rcx, [rbp+57h+arg_10]; void **
0x180093cab  mov     dword ptr [rbp+57h+var_90+8], edi
0x180093cae  call    ?ReleaseInterface@@YAKPEAPEAX@Z; ReleaseInterface(void * *)
0x180093cb3  xor     bl, bl
0x180093cb5  cmp     edi, [rbp+57h+arg_8]
0x180093cb8  jl      loc_180093B1C
0x180093cbe  lea     rcx, [rbp+57h+var_D0]; void **
0x180093cc2  call    ?ReleaseInterface@@YAKPEAPEAX@Z; ReleaseInterface(void * *)
0x180093cc7  mov     rcx, r15; bstrString
0x180093cca  call    cs:__imp_SysFreeString
0x180093cd0  mov     rax, [rbp+57h+arg_10]
0x180093cd4  movaps  xmm6, [rsp+100h+var_48+8]
0x180093cdc  add     rsp, 0D0h
0x180093ce3  pop     r15
0x180093ce5  pop     r14
0x180093ce7  pop     r13
0x180093ce9  pop     rdi
0x180093cea  pop     rsi
0x180093ceb  pop     rbx
0x180093cec  pop     rbp
0x180093ced  retn
```
