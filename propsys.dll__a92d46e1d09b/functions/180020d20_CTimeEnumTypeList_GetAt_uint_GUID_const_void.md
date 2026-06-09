# CTimeEnumTypeList::GetAt(uint,_GUID const &,void * *)

- ea: `0x180020d20`
- end: `0x180020eba`
- name: `?GetAt@CTimeEnumTypeList@@UEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `410`
- prototype: `__int64 __fastcall(CTimeEnumTypeList *__hidden this, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020d20`
- `0x180021374`
- `0x1800231e8`
- `0x180052248`
- `0x18006ed20`
- `0x18006fb98`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020e0a`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180020e0a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e86`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e7c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180020e86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020e72`

## pseudocode

```c
__int64 __fastcall CTimeEnumTypeList::GetAt(CTimeEnumTypeList *this, __int64 a2, const struct _GUID *a3, void **a4)
{
  __int64 v5; // rax
  __int64 v7; // rsi
  HRESULT v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-69h] BYREF
  int v14; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v15[4]; // [rsp+44h] [rbp-55h] BYREF
  __int128 v16; // [rsp+48h] [rbp-51h]
  __int64 v17; // [rsp+58h] [rbp-41h]
  PROPVARIANT pvarSrc; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v19[16]; // [rsp+68h] [rbp-31h] BYREF
  PROPVARIANT pvarDest[3]; // [rsp+78h] [rbp-21h] BYREF
  LPVOID v21; // [rsp+90h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+98h] [rbp-1h] BYREF
  __int128 v23; // [rsp+A0h] [rbp+7h]

  *a4 = 0;
  v5 = *(_QWORD *)this;
  v7 = (unsigned int)a2;
  v13 = 0;
  v9 = (*(__int64 (__fastcall **)(CTimeEnumTypeList *, __int64, GUID *, __int64 *))(v5 + 40))(
         this,
         a2,
         &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
         &v13);
  if ( v9 >= 0 )
  {
    v9 = CTimeEnumTypeList::_EnsureTimePointComputed(this, v7);
    if ( v9 >= 0 )
    {
      memset_0(v15, 0, 0x6Cu);
      v14 = 1;
      v17 = 0;
      v10 = *((_QWORD *)this + 18);
      v16 = 0;
      v9 = SHConvertTime(v10 + 8 * v7, 0, v19, 0);
      if ( v9 >= 0 )
      {
        v11 = *((_QWORD *)this + 11);
        LOWORD(pvarSrc) = 64;
        v9 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *))(*(_QWORD *)v11 + 168LL))(v11, &pvarSrc);
        if ( v9 >= 0 )
        {
          v9 = PropVariantCopy(pvarDest, &pvarSrc);
          if ( v9 >= 0 )
          {
            (*(void (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v13 + 64LL))(v13, 1, &v21);
            v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v13 + 64LL))(v13, 0, &pv);
            if ( v9 >= 0 )
            {
              v23 = 0;
              v9 = CSchemaObject<IPropertyEnumType,CPropertyEnumType,PSFORMAT_ENUMINFO>::CreateInstance(a3, a4, &v14);
              CoTaskMemFree(pv);
            }
            CoTaskMemFree(v21);
            PropVariantClear(pvarDest);
          }
        }
        PropVariantClear(&pvarSrc);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180020d20  push    rbp
0x180020d22  push    rbx
0x180020d23  push    rsi
0x180020d24  push    rdi
0x180020d25  push    r14
0x180020d27  push    r15
0x180020d29  lea     rbp, [rsp-2Fh]
0x180020d2e  sub     rsp, 0C8h
0x180020d35  mov     rax, cs:__security_cookie
0x180020d3c  xor     rax, rsp
0x180020d3f  mov     [rbp+57h+var_40], rax
0x180020d43  mov     qword ptr [r9], 0
0x180020d4a  mov     r14, r9
0x180020d4d  mov     rax, [rcx]
0x180020d50  lea     r9, [rbp+57h+var_C0]
0x180020d54  mov     r15, r8
0x180020d57  mov     esi, edx
0x180020d59  lea     r8, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x180020d60  mov     [rbp+57h+var_C0], 0
0x180020d68  mov     rdi, rcx
0x180020d6b  mov     rax, [rax+28h]
0x180020d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d74  mov     ebx, eax
0x180020d76  test    eax, eax
0x180020d78  js      loc_180020E9C
0x180020d7e  mov     edx, esi; unsigned int
0x180020d80  mov     rcx, rdi; this
0x180020d83  call    ?_EnsureTimePointComputed@CTimeEnumTypeList@@AEAAJI@Z; CTimeEnumTypeList::_EnsureTimePointComputed(uint)
0x180020d88  mov     ebx, eax
0x180020d8a  test    eax, eax
0x180020d8c  js      loc_180020E8C
0x180020d92  xor     edx, edx; Val
0x180020d94  lea     rcx, [rbp+57h+var_AC]; void *
0x180020d98  lea     r8d, [rdx+6Ch]; Size
0x180020d9c  call    memset_0
0x180020da1  xor     eax, eax
0x180020da3  mov     [rbp+57h+var_B0], 1
0x180020daa  mov     [rbp+57h+var_98], rax
0x180020dae  lea     r8, [rbp+57h+var_88]
0x180020db2  mov     rax, [rdi+90h]
0x180020db9  xorps   xmm0, xmm0
0x180020dbc  xor     r9d, r9d
0x180020dbf  xor     edx, edx
0x180020dc1  movups  [rbp+57h+var_A8], xmm0
0x180020dc5  lea     rcx, [rax+rsi*8]
0x180020dc9  call    ?SHConvertTime@@YAJPEBU_FILETIME@@W4SHTIME_FLAGS@@PEAU1@1@Z; SHConvertTime(_FILETIME const *,SHTIME_FLAGS,_FILETIME *,SHTIME_FLAGS)
0x180020dce  mov     ebx, eax
0x180020dd0  test    eax, eax
0x180020dd2  js      loc_180020E8C
0x180020dd8  mov     rcx, [rdi+58h]
0x180020ddc  lea     rdx, [rbp+57h+pvarSrc]
0x180020de0  mov     eax, 40h ; '@'
0x180020de5  mov     word ptr [rbp+57h+pvarSrc], ax
0x180020de9  mov     rax, [rcx]
0x180020dec  mov     rax, [rax+0A8h]
0x180020df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020df8  mov     ebx, eax
0x180020dfa  test    eax, eax
0x180020dfc  js      loc_180020E82
0x180020e02  lea     rdx, [rbp+57h+pvarSrc]; pvarSrc
0x180020e06  lea     rcx, [rbp+57h+pvarDest]; pvarDest
0x180020e0a  call    cs:__imp_PropVariantCopy
0x180020e10  mov     ebx, eax
0x180020e12  test    eax, eax
0x180020e14  js      short loc_180020E82
0x180020e16  mov     rcx, [rbp+57h+var_C0]
0x180020e1a  lea     r8, [rbp+57h+var_60]
0x180020e1e  mov     edx, 1
0x180020e23  mov     rax, [rcx]
0x180020e26  mov     rax, [rax+40h]
0x180020e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2f  mov     rcx, [rbp+57h+var_C0]
0x180020e33  lea     r8, [rbp+57h+pv]
0x180020e37  xor     edx, edx
0x180020e39  mov     rax, [rcx]
0x180020e3c  mov     rax, [rax+40h]
0x180020e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e45  mov     ebx, eax
0x180020e47  test    eax, eax
0x180020e49  js      short loc_180020E6E
0x180020e4b  xorps   xmm0, xmm0
0x180020e4e  lea     r8, [rbp+57h+var_B0]
0x180020e52  mov     rdx, r14
0x180020e55  movdqa  [rbp+57h+var_50], xmm0
0x180020e5a  mov     rcx, r15
0x180020e5d  call    ?CreateInstance@?$CSchemaObject@UIPropertyEnumType@@VCPropertyEnumType@@UPSFORMAT_ENUMINFO@@@@SAJAEBU_GUID@@PEAPEAXPEBUPSFORMAT_ENUMINFO@@@Z; CSchemaObject<IPropertyEnumType,CPropertyEnumType,PSFORMAT_ENUMINFO>::CreateInstance(_GUID const &,void * *,PSFORMAT_ENUMINFO const *)
0x180020e62  mov     rcx, [rbp+57h+pv]; pv
0x180020e66  mov     ebx, eax
0x180020e68  call    cs:__imp_CoTaskMemFree
0x180020e6e  mov     rcx, [rbp+57h+var_60]; pv
0x180020e72  call    cs:__imp_CoTaskMemFree
0x180020e78  lea     rcx, [rbp+57h+pvarDest]; pvar
0x180020e7c  call    cs:__imp_PropVariantClear
0x180020e82  lea     rcx, [rbp+57h+pvarSrc]; pvar
0x180020e86  call    cs:__imp_PropVariantClear
0x180020e8c  mov     rcx, [rbp+57h+var_C0]
0x180020e90  mov     rax, [rcx]
0x180020e93  mov     rax, [rax+10h]
0x180020e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e9c  mov     eax, ebx
0x180020e9e  mov     rcx, [rbp+57h+var_40]
0x180020ea2  xor     rcx, rsp; StackCookie
0x180020ea5  call    __security_check_cookie
0x180020eaa  add     rsp, 0C8h
0x180020eb1  pop     r15
0x180020eb3  pop     r14
0x180020eb5  pop     rdi
0x180020eb6  pop     rsi
0x180020eb7  pop     rbx
0x180020eb8  pop     rbp
0x180020eb9  retn
```
