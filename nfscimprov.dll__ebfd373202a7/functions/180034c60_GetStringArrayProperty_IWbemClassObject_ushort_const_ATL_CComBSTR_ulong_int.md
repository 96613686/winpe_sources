# GetStringArrayProperty(IWbemClassObject *,ushort const *,ATL::CComBSTR * *,ulong *,int *)

- ea: `0x180034c60`
- end: `0x180034dbf`
- name: `?GetStringArrayProperty@@YAJPEAUIWbemClassObject@@PEBGPEAPEAVCComBSTR@ATL@@PEAKPEAH@Z`
- size: `351`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, const unsigned __int16 *, struct ATL::CComBSTR **, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800355e0`

## callees

- `0x1800021f0`
- `0x180034a70`
- `0x180034acc`
- `0x180034c60`
- `0x180037010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180034c84`
- `OLEAUT32!__imp_VariantInit` at `0x180034c84`
- `OLEAUT32!__imp_VariantClear` at `0x180034da2`
- `OLEAUT32!__imp_VariantClear` at `0x180034da2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180034d35`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180034d35`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180034d74`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180034d74`

## pseudocode

```c
__int64 __fastcall GetStringArrayProperty(
        struct IWbemClassObject *a1,
        unsigned __int16 *a2,
        struct ATL::CComBSTR **a3,
        unsigned int *a4)
{
  HRESULT v7; // ebx
  unsigned int v8; // eax
  __int64 v9; // rsi
  __int64 v10; // rax
  unsigned __int64 v11; // kr00_8
  bool v12; // cf
  unsigned __int64 v13; // rax
  _QWORD *v14; // rax
  unsigned __int64 v15; // rdx
  void *(*v16)(void *); // r9
  struct ATL::CComBSTR *v17; // rbx
  unsigned int i; // esi
  VARIANTARG pvarg; // [rsp+40h] [rbp-38h] BYREF
  void *ppvData; // [rsp+88h] [rbp+10h] BYREF

  ppvData = a2;
  VariantInit(&pvarg);
  v7 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a1->lpVtbl->Get)(
         a1,
         L"UNMServers",
         0,
         &pvarg,
         0,
         0);
  if ( v7 < 0 )
    goto LABEL_19;
  if ( pvarg.vt == 8200 )
  {
    v8 = *(_DWORD *)(pvarg.llVal + 24);
    *a4 = v8;
    if ( !v8 )
    {
      *a3 = 0;
      goto LABEL_19;
    }
    v9 = v8;
    v11 = v8;
    v10 = 8LL * v8;
    if ( !is_mul_ok(v11, 8u) )
      v10 = -1;
    v12 = __CFADD__(v10, 8);
    v13 = v10 + 8;
    if ( v12 )
      v13 = -1;
    v14 = operator new[](v13);
    if ( v14 )
    {
      v17 = (struct ATL::CComBSTR *)(v14 + 1);
      *v14 = v9;
      `vector constructor iterator'((ATL::CComBSTR *)(v14 + 1), v15, (unsigned int)v9, v16);
      *a3 = v17;
      if ( v17 )
      {
        ppvData = 0;
        v7 = SafeArrayAccessData(pvarg.parray, &ppvData);
        if ( v7 >= 0 )
        {
          for ( i = 0; i < *a4; ++i )
            ATL::CComBSTR::operator=((char *)*a3 + 8 * i, *((_QWORD *)ppvData + i));
          SafeArrayUnaccessData(pvarg.parray);
        }
        goto LABEL_19;
      }
    }
    else
    {
      *a3 = 0;
    }
    v7 = -2147217402;
    goto LABEL_19;
  }
  if ( pvarg.vt != 1 )
    v7 = -2147217403;
LABEL_19:
  VariantClear(&pvarg);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180034c60  mov     rax, rsp
0x180034c63  mov     [rax+8], rbx
0x180034c67  mov     [rax+18h], rbp
0x180034c6b  mov     [rax+10h], rdx
0x180034c6f  push    rsi
0x180034c70  push    rdi
0x180034c71  push    r14
0x180034c73  sub     rsp, 60h
0x180034c77  mov     rbx, rcx
0x180034c7a  mov     r14, r9
0x180034c7d  lea     rcx, [rax-38h]; pvarg
0x180034c81  mov     rdi, r8
0x180034c84  call    cs:__imp_VariantInit
0x180034c8a  mov     rax, [rbx]
0x180034c8d  lea     r9, [rsp+78h+pvarg]
0x180034c92  xor     ebp, ebp
0x180034c94  lea     rdx, aUnmservers; "UNMServers"
0x180034c9b  mov     [rsp+78h+var_50], rbp
0x180034ca0  xor     r8d, r8d
0x180034ca3  mov     rcx, rbx
0x180034ca6  mov     [rsp+78h+var_58], rbp
0x180034cab  mov     rax, [rax+20h]
0x180034caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cb4  mov     ebx, eax
0x180034cb6  test    eax, eax
0x180034cb8  js      loc_180034D9D
0x180034cbe  mov     eax, 2008h
0x180034cc3  cmp     word ptr [rsp+78h+pvarg], ax
0x180034cc8  jnz     loc_180034D8B
0x180034cce  mov     rcx, qword ptr [rsp+78h+pvarg+8]
0x180034cd3  mov     eax, [rcx+18h]
0x180034cd6  mov     [r14], eax
0x180034cd9  test    eax, eax
0x180034cdb  jz      loc_180034D86
0x180034ce1  mov     esi, eax
0x180034ce3  lea     rcx, [rbp-1]
0x180034ce7  lea     eax, [rbp+8]
0x180034cea  mul     rsi
0x180034ced  cmovb   rax, rcx
0x180034cf1  add     rax, 8
0x180034cf5  cmovb   rax, rcx
0x180034cf9  mov     rcx, rax; unsigned __int64
0x180034cfc  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180034d01  test    rax, rax
0x180034d04  jz      short loc_180034D7C
0x180034d06  lea     rbx, [rax+8]
0x180034d0a  mov     [rax], rsi
0x180034d0d  mov     rcx, rbx; this
0x180034d10  mov     r8d, esi; unsigned __int64
0x180034d13  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180034d18  mov     [rdi], rbx
0x180034d1b  test    rbx, rbx
0x180034d1e  jz      short loc_180034D7F
0x180034d20  mov     rcx, qword ptr [rsp+78h+pvarg+8]; psa
0x180034d25  lea     rdx, [rsp+78h+ppvData]; ppvData
0x180034d2d  mov     [rsp+78h+ppvData], rbp
0x180034d35  call    cs:__imp_SafeArrayAccessData
0x180034d3b  mov     ebx, eax
0x180034d3d  test    eax, eax
0x180034d3f  js      short loc_180034D9D
0x180034d41  mov     esi, ebp
0x180034d43  cmp     [r14], ebp
0x180034d46  jbe     short loc_180034D6F
0x180034d48  mov     ebp, 1
0x180034d4d  mov     rax, [rdi]
0x180034d50  mov     rdx, [rsp+78h+ppvData]
0x180034d58  mov     r8d, esi
0x180034d5b  mov     rdx, [rdx+r8*8]
0x180034d5f  lea     rcx, [rax+r8*8]
0x180034d63  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180034d68  add     esi, ebp
0x180034d6a  cmp     esi, [r14]
0x180034d6d  jb      short loc_180034D4D
0x180034d6f  mov     rcx, qword ptr [rsp+78h+pvarg+8]; psa
0x180034d74  call    cs:__imp_SafeArrayUnaccessData
0x180034d7a  jmp     short loc_180034D9D
0x180034d7c  mov     [rdi], rbp
0x180034d7f  mov     ebx, 80041006h
0x180034d84  jmp     short loc_180034D9D
0x180034d86  mov     [rdi], rbp
0x180034d89  jmp     short loc_180034D9D
0x180034d8b  mov     ebp, 1
0x180034d90  mov     eax, 80041005h
0x180034d95  cmp     word ptr [rsp+78h+pvarg], bp
0x180034d9a  cmovnz  ebx, eax
0x180034d9d  lea     rcx, [rsp+78h+pvarg]; pvarg
0x180034da2  call    cs:__imp_VariantClear
0x180034da8  lea     r11, [rsp+78h+var_18]
0x180034dad  mov     eax, ebx
0x180034daf  mov     rbx, [r11+20h]
0x180034db3  mov     rbp, [r11+30h]
0x180034db7  mov     rsp, r11
0x180034dba  pop     r14
0x180034dbc  pop     rdi
0x180034dbd  pop     rsi
0x180034dbe  retn
```
