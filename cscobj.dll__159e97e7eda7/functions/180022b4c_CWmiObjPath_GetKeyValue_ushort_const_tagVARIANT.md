# CWmiObjPath::_GetKeyValue(ushort const *,tagVARIANT *)

- ea: `0x180022b4c`
- end: `0x180022cd5`
- name: `?_GetKeyValue@CWmiObjPath@@AEAAJPEBGPEAUtagVARIANT@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(CWmiObjPath *__hidden this, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800228d8`

## callees

- `0x18000b7c0`
- `0x180022b4c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022c74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180022c74`
- `OLEAUT32!__imp_VariantInit` at `0x180022c0d`
- `OLEAUT32!__imp_VariantInit` at `0x180022c0d`
- `OLEAUT32!__imp_VariantClear` at `0x180022c84`
- `OLEAUT32!__imp_VariantClear` at `0x180022c84`

## string_xrefs

- `0x180022c61`: `ItemPath`

## pseudocode

```c
__int64 __fastcall CWmiObjPath::_GetKeyValue(CWmiObjPath *this, const unsigned __int16 *a2, struct tagVARIANT *a3)
{
  int v3; // ebx
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  unsigned int i; // edi
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  int v12; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String2[264]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_DWORD *)this;
  if ( *(int *)this >= 0 )
  {
    v5 = (_QWORD *)((char *)this + 16);
    if ( *((_QWORD *)this + 2)
      || (v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 1) + 176LL))(
                 *((_QWORD *)this + 1),
                 v5),
          v3 >= 0) )
    {
      v6 = *v5;
      v10 = 0;
      v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v6 + 24LL))(v6, &v10);
      if ( v3 >= 0 )
      {
        for ( i = 0; i < v10 && v3 >= 0; ++i )
        {
          v12 = 260;
          v11 = 0;
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, int *, WCHAR *, VARIANTARG *, int *))(*(_QWORD *)*v5 + 56LL))(
                 *v5,
                 i,
                 0,
                 &v12,
                 String2,
                 &pvarg,
                 &v11);
          if ( v3 >= 0 && CompareStringW(0x7Fu, 1u, L"ItemPath", -1, String2, -1) == 2 )
          {
            pRecInfo = pvarg.pRecInfo;
            *(_OWORD *)&a3->vt = *(_OWORD *)&pvarg.vt;
            a3->pRecInfo = pRecInfo;
            return (unsigned int)v3;
          }
          VariantClear(&pvarg);
        }
        return (unsigned int)-2147217406;
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022b4c  mov     [rsp-8+arg_8], rbx
0x180022b51  push    rbp
0x180022b52  push    rsi
0x180022b53  push    rdi
0x180022b54  push    r14
0x180022b56  push    r15
0x180022b58  lea     rbp, [rsp-190h]
0x180022b60  sub     rsp, 290h
0x180022b67  mov     rax, cs:__security_cookie
0x180022b6e  xor     rax, rsp
0x180022b71  mov     [rbp+1B0h+var_30], rax
0x180022b78  mov     ebx, [rcx]
0x180022b7a  mov     r15, r8
0x180022b7d  test    ebx, ebx
0x180022b7f  js      loc_180022CAD
0x180022b85  lea     rsi, [rcx+10h]
0x180022b89  cmp     qword ptr [rsi], 0
0x180022b8d  jnz     short loc_180022BAF
0x180022b8f  mov     rcx, [rcx+8]
0x180022b93  mov     rdx, rsi
0x180022b96  mov     rax, [rcx]
0x180022b99  mov     rax, [rax+0B0h]
0x180022ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ba5  mov     ebx, eax
0x180022ba7  test    eax, eax
0x180022ba9  js      loc_180022CAD
0x180022baf  mov     rcx, [rsi]
0x180022bb2  lea     rdx, [rsp+2B0h+var_270]
0x180022bb7  mov     [rsp+2B0h+var_270], 0
0x180022bbf  mov     rax, [rcx]
0x180022bc2  mov     rax, [rax+18h]
0x180022bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bcb  mov     ebx, eax
0x180022bcd  test    eax, eax
0x180022bcf  js      loc_180022CAD
0x180022bd5  xor     edi, edi
0x180022bd7  cmp     edi, [rsp+2B0h+var_270]
0x180022bdb  jnb     loc_180022CA8
0x180022be1  test    ebx, ebx
0x180022be3  js      loc_180022CA8
0x180022be9  xorps   xmm0, xmm0
0x180022bec  mov     [rsp+2B0h+var_268], 104h
0x180022bf4  xor     eax, eax
0x180022bf6  mov     [rsp+2B0h+var_26C], 0
0x180022bfe  lea     rcx, [rsp+2B0h+pvarg]; pvarg
0x180022c03  mov     qword ptr [rsp+2B0h+pvarg+10h], rax
0x180022c08  movups  xmmword ptr [rsp+2B0h+pvarg], xmm0
0x180022c0d  call    cs:__imp_VariantInit
0x180022c13  mov     rcx, [rsi]
0x180022c16  lea     rdx, [rsp+2B0h+var_26C]
0x180022c1b  mov     [rsp+2B0h+var_280], rdx
0x180022c20  lea     r9, [rsp+2B0h+var_268]
0x180022c25  lea     rdx, [rsp+2B0h+pvarg]
0x180022c2a  xor     r8d, r8d
0x180022c2d  mov     qword ptr [rsp+2B0h+cchCount2], rdx
0x180022c32  lea     rdx, [rsp+2B0h+String2]
0x180022c37  mov     rax, [rcx]
0x180022c3a  mov     [rsp+2B0h+lpString2], rdx
0x180022c3f  mov     edx, edi
0x180022c41  mov     rax, [rax+38h]
0x180022c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c4a  mov     ebx, eax
0x180022c4c  test    eax, eax
0x180022c4e  js      short loc_180022C7F
0x180022c50  or      r9d, 0FFFFFFFFh; cchCount1
0x180022c54  mov     [rsp+2B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x180022c5c  lea     rax, [rsp+2B0h+String2]
0x180022c61  lea     r8, CSCWMI_STR_PROP_ITEMPATH; "ItemPath"
0x180022c68  mov     [rsp+2B0h+lpString2], rax; lpString2
0x180022c6d  lea     edx, [r9+2]; dwCmpFlags
0x180022c71  lea     ecx, [rdx+7Eh]; Locale
0x180022c74  call    cs:__imp_CompareStringW
0x180022c7a  cmp     eax, 2
0x180022c7d  jz      short loc_180022C91
0x180022c7f  lea     rcx, [rsp+2B0h+pvarg]; pvarg
0x180022c84  call    cs:__imp_VariantClear
0x180022c8a  inc     edi
0x180022c8c  jmp     loc_180022BD7
0x180022c91  movups  xmm0, xmmword ptr [rsp+2B0h+pvarg]
0x180022c96  movsd   xmm1, qword ptr [rsp+2B0h+pvarg+10h]
0x180022c9c  movups  xmmword ptr [r15], xmm0
0x180022ca0  movsd   qword ptr [r15+10h], xmm1
0x180022ca6  jmp     short loc_180022CAD
0x180022ca8  mov     ebx, 80041002h
0x180022cad  mov     eax, ebx
0x180022caf  mov     rcx, [rbp+1B0h+var_30]
0x180022cb6  xor     rcx, rsp; StackCookie
0x180022cb9  call    __security_check_cookie
0x180022cbe  mov     rbx, [rsp+2B0h+arg_8]
0x180022cc6  add     rsp, 290h
0x180022ccd  pop     r15
0x180022ccf  pop     r14
0x180022cd1  pop     rdi
0x180022cd2  pop     rsi
0x180022cd3  pop     rbp
0x180022cd4  retn
```
