# ScriptFileCallback(ushort const *,CAppExport *,_GUID const &,__MIDL___MIDL_itf_registrar_0000_0000_0001,_GUID const &,ushort * *,EFileType *)

- ea: `0x18004e140`
- end: `0x18004e3f4`
- name: `?ScriptFileCallback@@YAJPEBGPEAVCAppExport@@AEBU_GUID@@W4__MIDL___MIDL_itf_registrar_0000_0000_0001@@2PEAPEAGPEAW4EFileType@@@Z`
- size: `692`
- prototype: `int __high(const unsigned __int16 *, struct CAppExport *, const struct _GUID *, enum __MIDL___MIDL_itf_registrar_0000_0000_0001, const struct _GUID *, unsigned __int16 **, enum EFileType *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004a988`

## callees

- `0x18000be28`
- `0x1800241bc`
- `0x18004e140`
- `0x180052ee8`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e269`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e274`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e27f`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e269`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e274`
- `MfcSubs!??1CString@@QEAA@XZ` at `0x18004e27f`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18004e224`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18004e235`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18004e224`
- `MfcSubs!??0CString@@QEAA@PEBG@Z` at `0x18004e235`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18004e246`
- `MfcSubs!??H@YA?AVCString@@AEBV0@0@Z` at `0x18004e246`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e35e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e35e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e3bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e2ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004e2ff`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004e194`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004e194`

## string_xrefs

- `0x18004e1e3`: `SOFTWARE\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ScriptFileCallback(
        __int64 a1,
        __int64 a2,
        const GUID *a3,
        int a4,
        __int64 a5,
        unsigned __int16 **a6,
        _DWORD *a7)
{
  unsigned __int16 *v8; // rsi
  int RegNodeDispenser; // ebx
  struct IRegNodeDispenser *v10; // r15
  int v11; // ecx
  __int64 (__fastcall *v12)(__int64, _QWORD, const WCHAR *); // rdi
  CString *v13; // rbx
  CString *v14; // rax
  _QWORD *v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  int v18; // eax
  __int64 v20; // [rsp+40h] [rbp-61h] BYREF
  struct IRegNodeDispenser *v21; // [rsp+48h] [rbp-59h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-51h] BYREF
  SIZE_T cb; // [rsp+58h] [rbp-49h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-41h] BYREF

  v21 = 0;
  v20 = 0;
  v8 = 0;
  StringFromGUID2(a3, sz, 39);
  RegNodeDispenser = GetRegNodeDispenser(&v21);
  v10 = v21;
  if ( RegNodeDispenser >= 0 )
  {
    v11 = 512;
    if ( a4 != 1 )
      v11 = 256;
    RegNodeDispenser = (*(__int64 (__fastcall **)(struct IRegNodeDispenser *, const wchar_t *, __int64, const wchar_t *, const WCHAR *, unsigned int, __int64 *))(*(_QWORD *)v21 + 24LL))(
                         v21,
                         L"?",
                         -2147483646,
                         L"SOFTWARE\\Classes\\CLSID",
                         L"\\",
                         v11 | 0x20019u,
                         &v20);
    if ( RegNodeDispenser >= 0 )
    {
      v12 = *(__int64 (__fastcall **)(__int64, _QWORD, const WCHAR *))(*(_QWORD *)v20 + 112LL);
      v13 = CString::CString((CString *)&v22, L"\\ScriptletURL");
      v14 = CString::CString((CString *)&v21, sz);
      v15 = (_QWORD *)operator+(&cb, v14, v13);
      RegNodeDispenser = v12(v20, *v15, L"\\");
      CString::~CString((CString *)&cb);
      CString::~CString((CString *)&v21);
      CString::~CString((CString *)&v22);
      if ( RegNodeDispenser != 1 && RegNodeDispenser >= 0 )
      {
        LODWORD(v21) = 0;
        v22 = 0;
        (*(void (__fastcall **)(__int64, struct IRegNodeDispenser **))(*(_QWORD *)v20 + 64LL))(v20, &v21);
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 72LL))(v20, &v22);
        *a6 = 0;
        v16 = v22 + 1LL;
        if ( v16 < v22 )
        {
          RegNodeDispenser = -2147024362;
        }
        else
        {
          cb = v22 + 1LL;
          RegNodeDispenser = ULongLongMult(v16, 2u, &cb);
          if ( RegNodeDispenser >= 0 )
          {
            v17 = (unsigned __int16 *)CoTaskMemAlloc(cb);
            v8 = v17;
            if ( v17 )
            {
              RegNodeDispenser = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)v20 + 80LL))(
                                   v20,
                                   (unsigned int)v21,
                                   v22,
                                   v17);
              if ( RegNodeDispenser >= 0 )
              {
                *a7 = 6;
                v18 = IsLocalPath(v8, a6);
                RegNodeDispenser = v18;
                if ( v18 >= 0 )
                {
                  if ( v18 == 1 )
                  {
                    *a6 = v8;
                    v8 = 0;
                    RegNodeDispenser = 0;
                  }
                  else
                  {
                    CoTaskMemFree(v8);
                    v8 = 0;
                  }
                }
              }
            }
            else
            {
              RegNodeDispenser = -2147024882;
            }
          }
        }
      }
    }
  }
  if ( v10 )
    (*(void (__fastcall **)(struct IRegNodeDispenser *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  if ( RegNodeDispenser < 0 )
  {
    if ( *a6 )
    {
      CoTaskMemFree(*a6);
      *a6 = 0;
    }
    if ( v8 )
      CoTaskMemFree(v8);
    return 1;
  }
  return (unsigned int)RegNodeDispenser;
}

```

## disassembly

```asm
0x18004e140  mov     [rsp-8+arg_0], rbx
0x18004e145  mov     [rsp-8+arg_8], rsi
0x18004e14a  push    rbp
0x18004e14b  push    rdi
0x18004e14c  push    r12
0x18004e14e  push    r14
0x18004e150  push    r15
0x18004e152  lea     rbp, [rsp-1Fh]
0x18004e157  sub     rsp, 0C0h
0x18004e15e  mov     rax, cs:__security_cookie
0x18004e165  xor     rax, rsp
0x18004e168  mov     [rbp+3Fh+var_30], rax
0x18004e16c  mov     edi, r9d
0x18004e16f  mov     rcx, r8; rguid
0x18004e172  mov     r14, [rbp+3Fh+arg_28]
0x18004e176  mov     r12, [rbp+3Fh+arg_30]
0x18004e17a  mov     [rbp+3Fh+var_98], 0
0x18004e182  mov     [rbp+3Fh+var_A0], 0
0x18004e18a  xor     esi, esi
0x18004e18c  lea     r8d, [rsi+27h]; cchMax
0x18004e190  lea     rdx, [rbp+3Fh+sz]; lpsz
0x18004e194  call    cs:__imp_StringFromGUID2
0x18004e19a  lea     rcx, [rbp+3Fh+var_98]; struct IRegNodeDispenser **
0x18004e19e  call    ?GetRegNodeDispenser@@YAJPEAPEAUIRegNodeDispenser@@@Z; GetRegNodeDispenser(IRegNodeDispenser * *)
0x18004e1a3  mov     ebx, eax
0x18004e1a5  mov     r15, [rbp+3Fh+var_98]
0x18004e1a9  test    eax, eax
0x18004e1ab  js      loc_18004E36D
0x18004e1b1  mov     rax, [r15]
0x18004e1b4  mov     ecx, 200h
0x18004e1b9  mov     edx, 100h
0x18004e1be  cmp     edi, 1
0x18004e1c1  cmovnz  ecx, edx
0x18004e1c4  or      ecx, 20019h
0x18004e1ca  lea     rdx, [rbp+3Fh+var_A0]
0x18004e1ce  mov     [rsp+0E0h+var_B0], rdx
0x18004e1d3  mov     [rsp+0E0h+var_B8], ecx
0x18004e1d7  lea     rcx, asc_18005D30C; "\\"
0x18004e1de  mov     [rsp+0E0h+var_C0], rcx
0x18004e1e3  lea     r9, aSoftwareClasse; "SOFTWARE\\Classes\\CLSID"
0x18004e1ea  mov     r8, 0FFFFFFFF80000002h
0x18004e1f1  lea     rdx, asc_1800681B8; "?"
0x18004e1f8  mov     rcx, r15
0x18004e1fb  mov     rax, [rax+18h]
0x18004e1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e204  mov     ebx, eax
0x18004e206  test    eax, eax
0x18004e208  js      loc_18004E36D
0x18004e20e  mov     rax, [rbp+3Fh+var_A0]
0x18004e212  mov     rcx, [rax]
0x18004e215  mov     rdi, [rcx+70h]
0x18004e219  lea     rdx, aScriptleturl; "\\ScriptletURL"
0x18004e220  lea     rcx, [rbp+3Fh+var_90]
0x18004e224  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x18004e22a  mov     rbx, rax
0x18004e22d  lea     rdx, [rbp+3Fh+sz]
0x18004e231  lea     rcx, [rbp+3Fh+var_98]
0x18004e235  call    cs:__imp_??0CString@@QEAA@PEBG@Z; CString::CString(ushort const *)
0x18004e23b  nop
0x18004e23c  mov     r8, rbx
0x18004e23f  mov     rdx, rax
0x18004e242  lea     rcx, [rbp+3Fh+cb]
0x18004e246  call    cs:__imp_??H@YA?AVCString@@AEBV0@0@Z; operator+(CString const &,CString const &)
0x18004e24c  nop
0x18004e24d  lea     r8, asc_18005D30C; "\\"
0x18004e254  mov     rdx, [rax]
0x18004e257  mov     rcx, [rbp+3Fh+var_A0]
0x18004e25b  mov     rax, rdi
0x18004e25e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e263  mov     ebx, eax
0x18004e265  lea     rcx, [rbp+3Fh+cb]
0x18004e269  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18004e26f  nop
0x18004e270  lea     rcx, [rbp+3Fh+var_98]
0x18004e274  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18004e27a  nop
0x18004e27b  lea     rcx, [rbp+3Fh+var_90]
0x18004e27f  call    cs:__imp_??1CString@@QEAA@XZ; CString::~CString(void)
0x18004e285  cmp     ebx, 1
0x18004e288  jz      loc_18004E36D
0x18004e28e  test    ebx, ebx
0x18004e290  js      loc_18004E36D
0x18004e296  mov     dword ptr [rbp+3Fh+var_98], 0
0x18004e29d  mov     [rbp+3Fh+var_90], 0
0x18004e2a4  mov     rcx, [rbp+3Fh+var_A0]
0x18004e2a8  mov     rax, [rcx]
0x18004e2ab  lea     rdx, [rbp+3Fh+var_98]
0x18004e2af  mov     rax, [rax+40h]
0x18004e2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2b8  mov     rcx, [rbp+3Fh+var_A0]
0x18004e2bc  mov     rax, [rcx]
0x18004e2bf  lea     rdx, [rbp+3Fh+var_90]
0x18004e2c3  mov     rax, [rax+48h]
0x18004e2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e2cc  mov     qword ptr [r14], 0
0x18004e2d3  mov     eax, [rbp+3Fh+var_90]
0x18004e2d6  lea     rcx, [rax+1]; unsigned __int64
0x18004e2da  cmp     rcx, rax
0x18004e2dd  jb      loc_18004E368
0x18004e2e3  mov     [rbp+3Fh+cb], rcx
0x18004e2e7  lea     r8, [rbp+3Fh+cb]; unsigned __int64 *
0x18004e2eb  mov     edx, 2; unsigned __int64
0x18004e2f0  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004e2f5  mov     ebx, eax
0x18004e2f7  test    eax, eax
0x18004e2f9  js      short loc_18004E36D
0x18004e2fb  mov     rcx, [rbp+3Fh+cb]; cb
0x18004e2ff  call    cs:__imp_CoTaskMemAlloc
0x18004e305  mov     rsi, rax
0x18004e308  test    rax, rax
0x18004e30b  jnz     short loc_18004E314
0x18004e30d  mov     ebx, 8007000Eh
0x18004e312  jmp     short loc_18004E36D
0x18004e314  mov     rcx, [rbp+3Fh+var_A0]
0x18004e318  mov     rax, [rcx]
0x18004e31b  mov     r9, rsi
0x18004e31e  mov     r8d, [rbp+3Fh+var_90]
0x18004e322  mov     edx, dword ptr [rbp+3Fh+var_98]
0x18004e325  mov     rax, [rax+50h]
0x18004e329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e32e  mov     ebx, eax
0x18004e330  test    eax, eax
0x18004e332  js      short loc_18004E36D
0x18004e334  mov     dword ptr [r12], 6
0x18004e33c  mov     rdx, r14; unsigned __int16 **
0x18004e33f  mov     rcx, rsi; unsigned __int16 *
0x18004e342  call    ?IsLocalPath@@YAJPEBGPEAPEAG@Z; IsLocalPath(ushort const *,ushort * *)
0x18004e347  mov     ebx, eax
0x18004e349  test    eax, eax
0x18004e34b  js      short loc_18004E36D
0x18004e34d  cmp     eax, 1
0x18004e350  jnz     short loc_18004E35B
0x18004e352  mov     [r14], rsi
0x18004e355  xor     esi, esi
0x18004e357  xor     ebx, ebx
0x18004e359  jmp     short loc_18004E36D
0x18004e35b  mov     rcx, rsi; pv
0x18004e35e  call    cs:__imp_CoTaskMemFree
0x18004e364  xor     esi, esi
0x18004e366  jmp     short loc_18004E36D
0x18004e368  mov     ebx, 80070216h
0x18004e36d  test    r15, r15
0x18004e370  jz      short loc_18004E381
0x18004e372  mov     rax, [r15]
0x18004e375  mov     rcx, r15
0x18004e378  mov     rax, [rax+10h]
0x18004e37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e381  mov     rcx, [rbp+3Fh+var_A0]
0x18004e385  test    rcx, rcx
0x18004e388  jz      short loc_18004E39E
0x18004e38a  mov     rax, [rcx]
0x18004e38d  mov     rax, [rax+10h]
0x18004e391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e396  mov     [rbp+3Fh+var_A0], 0
0x18004e39e  test    ebx, ebx
0x18004e3a0  jns     short loc_18004E3CA
0x18004e3a2  mov     rcx, [r14]; pv
0x18004e3a5  test    rcx, rcx
0x18004e3a8  jz      short loc_18004E3B7
0x18004e3aa  call    cs:__imp_CoTaskMemFree
0x18004e3b0  mov     qword ptr [r14], 0
0x18004e3b7  test    rsi, rsi
0x18004e3ba  jz      short loc_18004E3C5
0x18004e3bc  mov     rcx, rsi; pv
0x18004e3bf  call    cs:__imp_CoTaskMemFree
0x18004e3c5  mov     ebx, 1
0x18004e3ca  mov     eax, ebx
0x18004e3cc  mov     rcx, [rbp+3Fh+var_30]
0x18004e3d0  xor     rcx, rsp; StackCookie
0x18004e3d3  call    __security_check_cookie
0x18004e3d8  lea     r11, [rsp+0E0h+var_20]
0x18004e3e0  mov     rbx, [r11+30h]
0x18004e3e4  mov     rsi, [r11+38h]
0x18004e3e8  mov     rsp, r11
0x18004e3eb  pop     r15
0x18004e3ed  pop     r14
0x18004e3ef  pop     r12
0x18004e3f1  pop     rdi
0x18004e3f2  pop     rbp
0x18004e3f3  retn
```
