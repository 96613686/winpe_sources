# PropertyLoader::Load(IUnknown *)

- ea: `0x180046cc0`
- end: `0x1800470a5`
- name: `?Load@PropertyLoader@@UEAAJPEAUIUnknown@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(PropertyLoader *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800465b0`
- `0x180046cc0`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046f62`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046f9f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046fde`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046f62`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046f9f`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046fde`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046e0b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046e7b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046e0b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180046e7b`
- `OLEAUT32!__imp_SysAllocString` at `0x180046e27`
- `OLEAUT32!__imp_SysAllocString` at `0x180046e8d`
- `OLEAUT32!__imp_SysAllocString` at `0x180046e27`
- `OLEAUT32!__imp_SysAllocString` at `0x180046e8d`
- `OLEAUT32!__imp_SysFreeString` at `0x18004704c`
- `OLEAUT32!__imp_SysFreeString` at `0x180047057`
- `OLEAUT32!__imp_SysFreeString` at `0x180047062`
- `OLEAUT32!__imp_SysFreeString` at `0x18004706d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005670e`
- `OLEAUT32!__imp_SysFreeString` at `0x180056718`
- `OLEAUT32!__imp_SysFreeString` at `0x180056722`
- `OLEAUT32!__imp_SysFreeString` at `0x18005672c`
- `OLEAUT32!__imp_SysFreeString` at `0x18004704c`
- `OLEAUT32!__imp_SysFreeString` at `0x180047057`
- `OLEAUT32!__imp_SysFreeString` at `0x180047062`
- `OLEAUT32!__imp_SysFreeString` at `0x18004706d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005670e`
- `OLEAUT32!__imp_SysFreeString` at `0x180056718`
- `OLEAUT32!__imp_SysFreeString` at `0x180056722`
- `OLEAUT32!__imp_SysFreeString` at `0x18005672c`
- `OLEAUT32!__imp_VariantInit` at `0x180046d3f`
- `OLEAUT32!__imp_VariantInit` at `0x180046d3f`
- `OLEAUT32!__imp_VariantClear` at `0x180047078`
- `OLEAUT32!__imp_VariantClear` at `0x180056736`
- `OLEAUT32!__imp_VariantClear` at `0x180047078`
- `OLEAUT32!__imp_VariantClear` at `0x180056736`

## pseudocode

```c
__int64 __fastcall PropertyLoader::Load(PropertyLoader *this, struct IUnknown *a2)
{
  int v4; // esi
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *VariantData; // rax
  unsigned int v10; // [rsp+30h] [rbp-D8h] BYREF
  int v11; // [rsp+34h] [rbp-D4h]
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C8h] BYREF
  LPCOLESTR v14; // [rsp+48h] [rbp-C0h] BYREF
  LPCOLESTR v15; // [rsp+50h] [rbp-B8h] BYREF
  LPCOLESTR lpsz; // [rsp+58h] [rbp-B0h] BYREF
  int vt; // [rsp+60h] [rbp-A8h] BYREF
  VARIANTARG pvarg; // [rsp+68h] [rbp-A0h] BYREF
  PropertyLoader *v19; // [rsp+80h] [rbp-88h]
  GUID pclsid; // [rsp+88h] [rbp-80h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-68h] BYREF

  v19 = this;
  v12 = 0;
  bstrString = 0;
  lpsz = 0;
  v14 = 0;
  v15 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  pclsid = 0;
  v4 = 0;
  v11 = 0;
  VariantInit(&pvarg);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IEventProperty,
         &v12);
  if ( !v12 )
    goto LABEL_26;
  v5 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v12 + 56LL))(v12, &bstrString);
  if ( !bstrString )
    goto LABEL_26;
  v5 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v12 + 72LL))(v12, &pvarg);
  if ( v5 < 0 )
    goto LABEL_26;
  v5 = (*(__int64 (__fastcall **)(_QWORD, LPCOLESTR *))(**((_QWORD **)this + 5) + 56LL))(*((_QWORD *)this + 5), &lpsz);
  if ( v5 )
    goto LABEL_26;
  v6 = *((_QWORD *)this + 6);
  if ( v6 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v6 + 392LL))(v6, &v14);
    if ( v5 )
      goto LABEL_26;
  }
  else
  {
    if ( !StringFromGUID2(&guidGlobalPartition, sz, 39) )
      goto LABEL_9;
    v14 = SysAllocString(sz);
    if ( !v14 )
      goto LABEL_9;
  }
  if ( !*((_DWORD *)this + 14) )
  {
    v7 = *((_QWORD *)this + 6);
    if ( v7 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, LPCOLESTR *))(*(_QWORD *)v7 + 408LL))(v7, &v15);
      if ( v5 )
        goto LABEL_26;
      goto LABEL_17;
    }
    if ( !StringFromGUID2(&GUID_NULL, sz, 39) || (v15 = SysAllocString(sz)) == 0 )
    {
LABEL_9:
      v5 = -2147024882;
      goto LABEL_26;
    }
  }
LABEL_17:
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 120LL))(*((_QWORD *)this + 1));
  if ( v5 >= 0 )
  {
    v4 = 1;
    v11 = 1;
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, BSTR))(**((_QWORD **)this + 1) + 160LL))(
           *((_QWORD *)this + 1),
           3,
           0,
           bstrString);
    if ( v5 >= 0 )
    {
      vt = pvarg.vt;
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 1) + 160LL))(
             *((_QWORD *)this + 1),
             4,
             0,
             &vt);
      if ( v5 >= 0 )
      {
        v10 = 0;
        VariantData = GetVariantData(&pvarg, &v10);
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, void *))(**((_QWORD **)this + 1) + 160LL))(
          *((_QWORD *)this + 1),
          5,
          v10,
          VariantData);
        CLSIDFromString(lpsz, &pclsid);
        v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
               *((_QWORD *)this + 1),
               0,
               0,
               &pclsid);
        if ( v5 >= 0 )
        {
          CLSIDFromString(v14, &pclsid);
          v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                 *((_QWORD *)this + 1),
                 1,
                 0,
                 &pclsid);
          if ( v5 >= 0 )
          {
            if ( *((_DWORD *)this + 14) )
              pclsid = GUID_NULL;
            else
              CLSIDFromString(v15, &pclsid);
            v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, GUID *))(**((_QWORD **)this + 1) + 160LL))(
                   *((_QWORD *)this + 1),
                   2,
                   0,
                   &pclsid);
          }
        }
      }
    }
  }
LABEL_26:
  if ( v4 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  SysFreeString(bstrString);
  SysFreeString((BSTR)lpsz);
  SysFreeString((BSTR)v14);
  SysFreeString((BSTR)v15);
  VariantClear(&pvarg);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046cc0  mov     r11, rsp
0x180046cc3  mov     [r11+18h], rbx
0x180046cc7  mov     [r11+20h], rsi
0x180046ccb  push    rdi
0x180046ccc  sub     rsp, 100h
0x180046cd3  mov     rax, cs:__security_cookie
0x180046cda  xor     rax, rsp
0x180046cdd  mov     [rsp+108h+var_18], rax
0x180046ce5  mov     rbx, rdx
0x180046ce8  mov     rdi, rcx
0x180046ceb  mov     [rsp+108h+var_88], rcx
0x180046cf3  mov     [rsp+108h+var_D0], 0
0x180046cfc  mov     [rsp+108h+bstrString], 0
0x180046d05  mov     [rsp+108h+lpsz], 0
0x180046d0e  mov     [rsp+108h+var_C0], 0
0x180046d17  mov     [rsp+108h+var_B8], 0
0x180046d20  xorps   xmm0, xmm0
0x180046d23  xor     eax, eax
0x180046d25  movups  xmmword ptr [rsp+108h+pvarg], xmm0
0x180046d2a  mov     qword ptr [rsp+108h+pvarg+10h], rax
0x180046d2f  movups  xmmword ptr [r11-80h], xmm0
0x180046d34  xor     esi, esi
0x180046d36  mov     [rsp+108h+var_D4], esi
0x180046d3a  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180046d3f  call    cs:__imp_VariantInit
0x180046d45  nop
0x180046d46  mov     rax, [rbx]
0x180046d49  lea     r8, [rsp+108h+var_D0]
0x180046d4e  lea     rdx, IID_IEventProperty
0x180046d55  mov     rcx, rbx
0x180046d58  mov     rax, [rax]
0x180046d5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d60  mov     ebx, eax
0x180046d62  mov     rcx, [rsp+108h+var_D0]
0x180046d67  test    rcx, rcx
0x180046d6a  jz      loc_18004701A
0x180046d70  mov     rax, [rcx]
0x180046d73  lea     rdx, [rsp+108h+bstrString]
0x180046d78  mov     rax, [rax+38h]
0x180046d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d81  mov     ebx, eax
0x180046d83  cmp     [rsp+108h+bstrString], rsi
0x180046d88  jz      loc_18004701A
0x180046d8e  mov     rcx, [rsp+108h+var_D0]
0x180046d93  mov     rax, [rcx]
0x180046d96  lea     rdx, [rsp+108h+pvarg]
0x180046d9b  mov     rax, [rax+48h]
0x180046d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046da4  mov     ebx, eax
0x180046da6  test    eax, eax
0x180046da8  js      loc_18004701A
0x180046dae  mov     rcx, [rdi+28h]
0x180046db2  mov     rax, [rcx]
0x180046db5  lea     rdx, [rsp+108h+lpsz]
0x180046dba  mov     rax, [rax+38h]
0x180046dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dc3  mov     ebx, eax
0x180046dc5  test    eax, eax
0x180046dc7  jnz     loc_18004701A
0x180046dcd  mov     rcx, [rdi+30h]
0x180046dd1  test    rcx, rcx
0x180046dd4  jz      short loc_180046DF6
0x180046dd6  mov     rax, [rcx]
0x180046dd9  lea     rdx, [rsp+108h+var_C0]
0x180046dde  mov     rax, [rax+188h]
0x180046de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dea  mov     ebx, eax
0x180046dec  test    eax, eax
0x180046dee  jnz     loc_18004701A
0x180046df4  jmp     short loc_180046E37
0x180046df6  mov     r8d, 27h ; '''; cchMax
0x180046dfc  lea     rdx, [rsp+108h+sz]; lpsz
0x180046e04  lea     rcx, guidGlobalPartition; rguid
0x180046e0b  call    cs:__imp_StringFromGUID2
0x180046e11  test    eax, eax
0x180046e13  jnz     short loc_180046E1F
0x180046e15  mov     ebx, 8007000Eh
0x180046e1a  jmp     loc_18004701A
0x180046e1f  lea     rcx, [rsp+108h+sz]; psz
0x180046e27  call    cs:__imp_SysAllocString
0x180046e2d  mov     [rsp+108h+var_C0], rax
0x180046e32  test    rax, rax
0x180046e35  jz      short loc_180046E15
0x180046e37  cmp     dword ptr [rdi+38h], 0
0x180046e3b  jnz     short loc_180046EA1
0x180046e3d  mov     rcx, [rdi+30h]
0x180046e41  test    rcx, rcx
0x180046e44  jz      short loc_180046E66
0x180046e46  mov     rax, [rcx]
0x180046e49  lea     rdx, [rsp+108h+var_B8]
0x180046e4e  mov     rax, [rax+198h]
0x180046e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046e5a  mov     ebx, eax
0x180046e5c  test    eax, eax
0x180046e5e  jnz     loc_18004701A
0x180046e64  jmp     short loc_180046EA1
0x180046e66  mov     r8d, 27h ; '''; cchMax
0x180046e6c  lea     rdx, [rsp+108h+sz]; lpsz
0x180046e74  lea     rcx, GUID_NULL; rguid
0x180046e7b  call    cs:__imp_StringFromGUID2
0x180046e81  test    eax, eax
0x180046e83  jz      short loc_180046E15
0x180046e85  lea     rcx, [rsp+108h+sz]; psz
0x180046e8d  call    cs:__imp_SysAllocString
0x180046e93  mov     [rsp+108h+var_B8], rax
0x180046e98  test    rax, rax
0x180046e9b  jz      loc_180046E15
0x180046ea1  mov     rcx, [rdi+8]
0x180046ea5  mov     rax, [rcx]
0x180046ea8  mov     rax, [rax+78h]
0x180046eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046eb1  mov     ebx, eax
0x180046eb3  test    eax, eax
0x180046eb5  js      loc_18004701A
0x180046ebb  mov     esi, 1
0x180046ec0  mov     [rsp+108h+var_D4], esi
0x180046ec4  mov     rcx, [rdi+8]
0x180046ec8  mov     rax, [rcx]
0x180046ecb  mov     r9, [rsp+108h+bstrString]
0x180046ed0  xor     r8d, r8d
0x180046ed3  lea     edx, [rsi+2]
0x180046ed6  mov     rax, [rax+0A0h]
0x180046edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046ee2  mov     ebx, eax
0x180046ee4  test    eax, eax
0x180046ee6  js      loc_18004701A
0x180046eec  movzx   eax, word ptr [rsp+108h+pvarg]
0x180046ef1  mov     [rsp+108h+var_A8], eax
0x180046ef5  mov     rcx, [rdi+8]
0x180046ef9  mov     rax, [rcx]
0x180046efc  lea     r9, [rsp+108h+var_A8]
0x180046f01  xor     r8d, r8d
0x180046f04  lea     edx, [rsi+3]
0x180046f07  mov     rax, [rax+0A0h]
0x180046f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f13  mov     ebx, eax
0x180046f15  test    eax, eax
0x180046f17  js      loc_18004701A
0x180046f1d  mov     [rsp+108h+var_D8], 0
0x180046f25  lea     rdx, [rsp+108h+var_D8]; unsigned int *
0x180046f2a  lea     rcx, [rsp+108h+pvarg]; struct tagVARIANT *
0x180046f2f  call    ?GetVariantData@@YAPEAXAEAUtagVARIANT@@PEAK@Z; GetVariantData(tagVARIANT &,ulong *)
0x180046f34  mov     rcx, [rdi+8]
0x180046f38  mov     rdx, [rcx]
0x180046f3b  mov     r10, [rdx+0A0h]
0x180046f42  mov     r9, rax
0x180046f45  mov     r8d, [rsp+108h+var_D8]
0x180046f4a  lea     edx, [rsi+4]
0x180046f4d  mov     rax, r10
0x180046f50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f55  lea     rdx, [rsp+108h+pclsid]; pclsid
0x180046f5d  mov     rcx, [rsp+108h+lpsz]; lpsz
0x180046f62  call    cs:__imp_CLSIDFromString
0x180046f68  mov     rcx, [rdi+8]
0x180046f6c  mov     rax, [rcx]
0x180046f6f  lea     r9, [rsp+108h+pclsid]
0x180046f77  xor     r8d, r8d
0x180046f7a  xor     edx, edx
0x180046f7c  mov     rax, [rax+0A0h]
0x180046f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046f88  mov     ebx, eax
0x180046f8a  test    eax, eax
0x180046f8c  js      loc_18004701A
0x180046f92  lea     rdx, [rsp+108h+pclsid]; pclsid
0x180046f9a  mov     rcx, [rsp+108h+var_C0]; lpsz
0x180046f9f  call    cs:__imp_CLSIDFromString
0x180046fa5  mov     rcx, [rdi+8]
0x180046fa9  mov     rax, [rcx]
0x180046fac  lea     r9, [rsp+108h+pclsid]
0x180046fb4  xor     r8d, r8d
0x180046fb7  mov     edx, esi
0x180046fb9  mov     rax, [rax+0A0h]
0x180046fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046fc5  mov     ebx, eax
0x180046fc7  test    eax, eax
0x180046fc9  js      short loc_18004701A
0x180046fcb  cmp     dword ptr [rdi+38h], 0
0x180046fcf  jnz     short loc_180046FE6
0x180046fd1  lea     rdx, [rsp+108h+pclsid]; pclsid
0x180046fd9  mov     rcx, [rsp+108h+var_B8]; lpsz
0x180046fde  call    cs:__imp_CLSIDFromString
0x180046fe4  jmp     short loc_180046FF6
0x180046fe6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180046fed  movdqu  xmmword ptr [rsp+108h+pclsid.Data1], xmm0
0x180046ff6  mov     rcx, [rdi+8]
0x180046ffa  mov     rax, [rcx]
0x180046ffd  lea     r9, [rsp+108h+pclsid]
0x180047005  xor     r8d, r8d
0x180047008  lea     edx, [r8+2]
0x18004700c  mov     rax, [rax+0A0h]
0x180047013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047018  mov     ebx, eax
0x18004701a  test    esi, esi
0x18004701c  jz      short loc_180047031
0x18004701e  mov     rcx, [rdi+8]
0x180047022  mov     rax, [rcx]
0x180047025  mov     rax, [rax+90h]
0x18004702c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047031  mov     rcx, [rsp+108h+var_D0]
0x180047036  test    rcx, rcx
0x180047039  jz      short loc_180047047
0x18004703b  mov     rax, [rcx]
0x18004703e  mov     rax, [rax+10h]
0x180047042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047047  mov     rcx, [rsp+108h+bstrString]; bstrString
0x18004704c  call    cs:__imp_SysFreeString
0x180047052  mov     rcx, [rsp+108h+lpsz]; bstrString
0x180047057  call    cs:__imp_SysFreeString
0x18004705d  mov     rcx, [rsp+108h+var_C0]; bstrString
0x180047062  call    cs:__imp_SysFreeString
0x180047068  mov     rcx, [rsp+108h+var_B8]; bstrString
0x18004706d  call    cs:__imp_SysFreeString
0x180047073  lea     rcx, [rsp+108h+pvarg]; pvarg
0x180047078  call    cs:__imp_VariantClear
0x18004707e  mov     eax, ebx
0x180047080  mov     rcx, [rsp+108h+var_18]
0x180047088  xor     rcx, rsp; StackCookie
0x18004708b  call    __security_check_cookie
0x180047090  lea     r11, [rsp+108h+var_8]
0x180047098  mov     rbx, [r11+20h]
0x18004709c  mov     rsi, [r11+28h]
0x1800470a0  mov     rsp, r11
0x1800470a3  pop     rdi
0x1800470a4  retn
0x1800566c7  push    rbp
0x1800566c9  sub     rsp, 30h
0x1800566cd  mov     rbp, rdx
0x1800566d0  cmp     dword ptr [rbp+34h], 0
0x1800566d4  jz      short loc_1800566F4
0x1800566d6  mov     rcx, [rbp+80h]
0x1800566dd  mov     rax, [rcx+8]
0x1800566e1  mov     rdx, [rax]
0x1800566e4  mov     rcx, rax
0x1800566e7  mov     rax, [rdx+90h]
0x1800566ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800566f3  nop
0x1800566f4  mov     rcx, [rbp+38h]
0x1800566f8  test    rcx, rcx
0x1800566fb  jz      short loc_18005670A
0x1800566fd  mov     rax, [rcx]
0x180056700  mov     rax, [rax+10h]
0x180056704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056709  nop
0x18005670a  mov     rcx, [rbp+40h]; bstrString
0x18005670e  call    cs:__imp_SysFreeString
0x180056714  mov     rcx, [rbp+58h]; bstrString
0x180056718  call    cs:__imp_SysFreeString
0x18005671e  mov     rcx, [rbp+48h]; bstrString
0x180056722  call    cs:__imp_SysFreeString
0x180056728  mov     rcx, [rbp+50h]; bstrString
0x18005672c  call    cs:__imp_SysFreeString
0x180056732  lea     rcx, [rbp+68h]; pvarg
0x180056736  call    cs:__imp_VariantClear
0x18005673c  nop
0x18005673d  add     rsp, 30h
0x180056741  pop     rbp
0x180056742  retn
```
