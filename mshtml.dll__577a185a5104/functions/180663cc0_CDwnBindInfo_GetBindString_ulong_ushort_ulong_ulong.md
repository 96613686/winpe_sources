# CDwnBindInfo::GetBindString(ulong,ushort * *,ulong,ulong *)

- ea: `0x180663cc0`
- end: `0x180664008`
- name: `?GetBindString@CDwnBindInfo@@UEAAJKPEAPEAGKPEAK@Z`
- size: `840`
- prototype: `__int64 __fastcall(CDwnBindInfo *this, int, unsigned __int16 **, unsigned int, OLECHAR *pbstr)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x1803e41a0`
- `0x1803e41f0`
- `0x180402d68`
- `0x180663cc0`
- `0x180730a68`
- `0x180a3dbb0`
- `0x1810910f0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180663d7c`
- `msvcrt!memcpy_s` at `0x180663df2`
- `msvcrt!memcpy_s` at `0x180663e72`
- `msvcrt!memcpy_s` at `0x180663f03`
- `msvcrt!memcpy_s` at `0x180663d7c`
- `msvcrt!memcpy_s` at `0x180663df2`
- `msvcrt!memcpy_s` at `0x180663e72`
- `msvcrt!memcpy_s` at `0x180663f03`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663d5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663dca`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663e53`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663edb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663f71`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663d5d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663dca`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663e53`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663edb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180663f71`
- `OLEAUT32!__imp_SysFreeString` at `0x180663e8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180663e8f`
- `OLEAUT32!__imp_SysStringLen` at `0x180663e3c`
- `OLEAUT32!__imp_SysStringLen` at `0x180663e3c`

## pseudocode

```c
__int64 __fastcall CDwnBindInfo::GetBindString(
        CDwnBindInfo *this,
        int a2,
        unsigned __int16 **a3,
        unsigned int a4,
        BSTR pbstr)
{
  BSTR v5; // r14
  unsigned int AcceptHeadersForCategory; // ebx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  __int64 v15; // rdi
  _WORD *v16; // rdi
  __int64 v17; // rax
  SIZE_T v18; // rsi
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r15
  unsigned __int16 *v22; // rax
  rsize_t v23; // r9
  const wchar_t *v24; // r8
  rsize_t v25; // rdx
  __int64 v26; // rax
  CMarkup *v27; // rcx
  BSTR v28; // rdi
  SIZE_T v29; // rsi
  unsigned __int16 *v30; // rax
  unsigned __int16 *v31; // r15
  struct IUri *v32; // rdx
  SIZE_T v33; // rdi
  unsigned __int16 *v34; // rax
  unsigned __int16 *v35; // rsi
  __int64 v36; // rdi
  const wchar_t *v37; // rdi
  __int64 v38; // rax
  SIZE_T v39; // rsi
  CDwnPost *v40; // rcx
  _QWORD v41[5]; // [rsp+20h] [rbp-38h] BYREF
  int v42; // [rsp+48h] [rbp-10h]
  int v43; // [rsp+A8h] [rbp+50h] BYREF

  v5 = pbstr;
  AcceptHeadersForCategory = 0;
  v43 = 0;
  *(_DWORD *)pbstr = 0;
  v10 = a2 - 2;
  if ( !v10 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    if ( !(unsigned int)CFeatureControlKey::_CoInternetIsFeatureEnabledInternal((CFeatureControlKey *)&FCK::FEATURE_MIME_USE_BUILTIN_ACCEPT_HEADERS)
      && *(int *)(*((_QWORD *)this + 3) + 196LL) >= 9 )
    {
      AcceptHeadersForCategory = GetAcceptHeadersForCategory(*((unsigned int *)this + 30), a3, a4, v5);
      if ( (AcceptHeadersForCategory & 0x80000000) == 0 )
        return AcceptHeadersForCategory;
    }
    v22 = (unsigned __int16 *)CoTaskMemAlloc(8u);
    *a3 = v22;
    if ( v22 )
    {
      v23 = 8;
      v24 = L"*/*";
      v25 = 8;
LABEL_20:
      memcpy_s(v22, v25, v24, v23);
      goto LABEL_14;
    }
    return (unsigned int)-2147024882;
  }
  v11 = v10 - 10;
  if ( !v11 )
  {
    if ( a4 )
    {
      v40 = (CDwnPost *)*((_QWORD *)this + 4);
      if ( v40 )
      {
        AcceptHeadersForCategory = CDwnPost::GetHashString(v40, a3);
        *(_DWORD *)v5 = AcceptHeadersForCategory == 0;
      }
    }
    return AcceptHeadersForCategory;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    v36 = *((_QWORD *)this + 4);
    if ( !v36 )
      return AcceptHeadersForCategory;
    v37 = *(const wchar_t **)(v36 + 56);
    if ( !v37 )
      return (unsigned int)-2146697198;
    v38 = -1;
    do
      ++v38;
    while ( v37[v38] );
    v39 = (unsigned int)(2 * v38 + 2);
    v22 = (unsigned __int16 *)CoTaskMemAlloc(v39);
    *a3 = v22;
    if ( v22 )
    {
      v23 = (unsigned int)v39;
      v24 = v37;
      v25 = (unsigned int)v39;
      goto LABEL_20;
    }
    return (unsigned int)-2147024882;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    if ( !a4 )
      return AcceptHeadersForCategory;
    v32 = (struct IUri *)*((_QWORD *)this + 5);
    if ( v32 )
    {
      CUString::CUString((CUString *)v41, v32, Uri_PROPERTY_ABSOLUTE_URI, &v43);
      AcceptHeadersForCategory = v43;
      if ( !v43 )
      {
        v33 = (unsigned int)(2 * v42 + 2);
        v34 = (unsigned __int16 *)CoTaskMemAlloc(v33);
        v35 = v34;
        if ( v34 )
        {
          memcpy_s(v34, v33, (const void *const)v41[4], v33);
          *a3 = v35;
          *(_DWORD *)v5 = 1;
        }
        else
        {
          AcceptHeadersForCategory = -2147024882;
        }
      }
      v41[0] = &CUString::`vftable';
      CUString::Set((CUString *)v41, 0, Uri_PROPERTY_RAW_URI);
      return AcceptHeadersForCategory;
    }
    return (unsigned int)-2146697198;
  }
  v14 = v13 - 4;
  if ( v14 )
  {
    if ( v14 == 2 )
    {
      if ( a4 )
      {
        v15 = *((_QWORD *)this + 3);
        AcceptHeadersForCategory = -2146697198;
        if ( v15 )
        {
          v16 = *(_WORD **)(v15 + 680);
          if ( v16 )
          {
            AcceptHeadersForCategory = -2147024882;
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            v18 = (unsigned int)(2 * v17 + 2);
            v19 = (unsigned __int16 *)CoTaskMemAlloc(v18);
            v20 = v19;
            if ( v19 )
            {
              memcpy_s(v19, (unsigned int)v18, v16, (unsigned int)v18);
              *a3 = v20;
              AcceptHeadersForCategory = 0;
LABEL_14:
              *(_DWORD *)v5 = 1;
            }
          }
        }
      }
    }
  }
  else if ( a4 )
  {
    v26 = *((_QWORD *)this + 3);
    AcceptHeadersForCategory = -2146697198;
    pbstr = 0;
    v27 = *(CMarkup **)(v26 + 112);
    if ( v27 )
    {
      if ( CMarkup::GetRefererUrl(v27, &pbstr) >= 0 )
      {
        v28 = pbstr;
        AcceptHeadersForCategory = -2147024882;
        v29 = 2 * SysStringLen(pbstr) + 2;
        v30 = (unsigned __int16 *)CoTaskMemAlloc(v29);
        v31 = v30;
        if ( v30 )
        {
          memcpy_s(v30, (unsigned int)v29, v28, (unsigned int)v29);
          *a3 = v31;
          AcceptHeadersForCategory = 0;
          *(_DWORD *)v5 = 1;
        }
        SysFreeString(v28);
      }
    }
  }
  return AcceptHeadersForCategory;
}

```

## disassembly

```asm
0x180663cc0  push    rbp
0x180663cc2  push    rbx
0x180663cc3  push    rsi
0x180663cc4  push    rdi
0x180663cc5  push    r12
0x180663cc7  push    r13
0x180663cc9  push    r14
0x180663ccb  push    r15
0x180663ccd  mov     rbp, rsp
0x180663cd0  sub     rsp, 58h
0x180663cd4  mov     r14, [rbp+pbstr]
0x180663cd8  xor     r13d, r13d
0x180663cdb  mov     ebx, r13d
0x180663cde  mov     edi, r9d
0x180663ce1  mov     [rbp+arg_8], ebx
0x180663ce4  mov     r12, r8
0x180663ce7  mov     rsi, rcx
0x180663cea  mov     [r14], r13d
0x180663ced  sub     edx, 2
0x180663cf0  jz      loc_180663DAA
0x180663cf6  sub     edx, 0Ah
0x180663cf9  jz      loc_180663F9D
0x180663cff  sub     edx, 1
0x180663d02  jz      loc_180663F39
0x180663d08  sub     edx, 1
0x180663d0b  jz      loc_180663EA0
0x180663d11  sub     edx, 4
0x180663d14  jz      loc_180663E00
0x180663d1a  cmp     edx, 2
0x180663d1d  jnz     short loc_180663D96
0x180663d1f  cmp     r9d, 1
0x180663d23  jb      short loc_180663D96
0x180663d25  mov     rdi, [rcx+18h]
0x180663d29  mov     ebx, 800C0012h
0x180663d2e  test    rdi, rdi
0x180663d31  jz      short loc_180663D96
0x180663d33  mov     rdi, [rdi+2A8h]
0x180663d3a  test    rdi, rdi
0x180663d3d  jz      short loc_180663D96
0x180663d3f  mov     ebx, 8007000Eh
0x180663d44  or      rax, 0FFFFFFFFFFFFFFFFh
0x180663d48  inc     rax
0x180663d4b  cmp     [rdi+rax*2], r13w
0x180663d50  jnz     short loc_180663D48
0x180663d52  lea     eax, ds:2[rax*2]
0x180663d59  mov     ecx, eax; cb
0x180663d5b  mov     esi, eax
0x180663d5d  call    cs:__imp_CoTaskMemAlloc
0x180663d64  nop     dword ptr [rax+rax+00h]
0x180663d69  mov     r15, rax
0x180663d6c  test    rax, rax
0x180663d6f  jz      short loc_180663D96
0x180663d71  mov     r9d, esi; SourceSize
0x180663d74  mov     r8, rdi; Source
0x180663d77  mov     edx, esi; DestinationSize
0x180663d79  mov     rcx, rax; Destination
0x180663d7c  call    cs:__imp_memcpy_s
0x180663d83  nop     dword ptr [rax+rax+00h]
0x180663d88  mov     [r12], r15
0x180663d8c  mov     ebx, r13d
0x180663d8f  mov     dword ptr [r14], 1
0x180663d96  mov     eax, ebx
0x180663d98  add     rsp, 58h
0x180663d9c  pop     r15
0x180663d9e  pop     r14
0x180663da0  pop     r13
0x180663da2  pop     r12
0x180663da4  pop     rdi
0x180663da5  pop     rsi
0x180663da6  pop     rbx
0x180663da7  pop     rbp
0x180663da8  retn
0x180663daa  cmp     edi, 1
0x180663dad  jb      short loc_180663D96
0x180663daf  lea     rcx, ?FEATURE_MIME_USE_BUILTIN_ACCEPT_HEADERS@FCK@@3VCFeatureControlKey@@A; this
0x180663db6  call    ?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ; CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)
0x180663dbb  test    eax, eax
0x180663dbd  jz      loc_180663FCD
0x180663dc3  mov     edi, 8
0x180663dc8  mov     ecx, edi; cb
0x180663dca  call    cs:__imp_CoTaskMemAlloc
0x180663dd1  nop     dword ptr [rax+rax+00h]
0x180663dd6  mov     [r12], rax
0x180663dda  test    rax, rax
0x180663ddd  jz      loc_180663FFE
0x180663de3  mov     r9d, edi; SourceSize
0x180663de6  lea     r8, asc_181476858; "*/*"
0x180663ded  mov     edx, edi; DestinationSize
0x180663def  mov     rcx, rax; Destination
0x180663df2  call    cs:__imp_memcpy_s
0x180663df9  nop     dword ptr [rax+rax+00h]
0x180663dfe  jmp     short loc_180663D8F
0x180663e00  cmp     edi, 1
0x180663e03  jb      short loc_180663D96
0x180663e05  mov     rax, [rcx+18h]
0x180663e09  mov     ebx, 800C0012h
0x180663e0e  mov     [rbp+pbstr], r13
0x180663e12  mov     rcx, [rax+70h]; this
0x180663e16  test    rcx, rcx
0x180663e19  jz      loc_180663D96
0x180663e1f  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x180663e23  call    ?GetRefererUrl@CMarkup@@QEBAJPEAPEAG@Z; CMarkup::GetRefererUrl(ushort * *)
0x180663e28  test    eax, eax
0x180663e2a  js      loc_180663D96
0x180663e30  mov     rdi, [rbp+pbstr]
0x180663e34  mov     ebx, 8007000Eh
0x180663e39  mov     rcx, rdi; pbstr
0x180663e3c  call    cs:__imp_SysStringLen
0x180663e43  nop     dword ptr [rax+rax+00h]
0x180663e48  lea     eax, ds:2[rax*2]
0x180663e4f  mov     ecx, eax; cb
0x180663e51  mov     esi, eax
0x180663e53  call    cs:__imp_CoTaskMemAlloc
0x180663e5a  nop     dword ptr [rax+rax+00h]
0x180663e5f  mov     r15, rax
0x180663e62  test    rax, rax
0x180663e65  jz      short loc_180663E8C
0x180663e67  mov     r9d, esi; SourceSize
0x180663e6a  mov     r8, rdi; Source
0x180663e6d  mov     edx, esi; DestinationSize
0x180663e6f  mov     rcx, rax; Destination
0x180663e72  call    cs:__imp_memcpy_s
0x180663e79  nop     dword ptr [rax+rax+00h]
0x180663e7e  mov     [r12], r15
0x180663e82  mov     ebx, r13d
0x180663e85  mov     dword ptr [r14], 1
0x180663e8c  mov     rcx, rdi; bstrString
0x180663e8f  call    cs:__imp_SysFreeString
0x180663e96  nop     dword ptr [rax+rax+00h]
0x180663e9b  jmp     loc_180663D96
0x180663ea0  cmp     edi, 1
0x180663ea3  jb      loc_180663D96
0x180663ea9  mov     rdx, [rcx+28h]; struct IUri *
0x180663ead  test    rdx, rdx
0x180663eb0  jz      loc_180663F93
0x180663eb6  lea     r9, [rbp+arg_8]; int *
0x180663eba  xor     r8d, r8d; enum __MIDL_IUri_0001
0x180663ebd  lea     rcx, [rbp+var_38]; this
0x180663ec1  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180663ec6  mov     ebx, [rbp+arg_8]
0x180663ec9  test    ebx, ebx
0x180663ecb  jnz     short loc_180663F1A
0x180663ecd  mov     eax, [rbp+var_10]
0x180663ed0  lea     eax, ds:2[rax*2]
0x180663ed7  mov     ecx, eax; cb
0x180663ed9  mov     edi, eax
0x180663edb  call    cs:__imp_CoTaskMemAlloc
0x180663ee2  nop     dword ptr [rax+rax+00h]
0x180663ee7  mov     rsi, rax
0x180663eea  test    rax, rax
0x180663eed  jnz     short loc_180663EF6
0x180663eef  mov     ebx, 8007000Eh
0x180663ef4  jmp     short loc_180663F1A
0x180663ef6  mov     r8, [rbp+Source]; Source
0x180663efa  mov     r9, rdi; SourceSize
0x180663efd  mov     rdx, rdi; DestinationSize
0x180663f00  mov     rcx, rsi; Destination
0x180663f03  call    cs:__imp_memcpy_s
0x180663f0a  nop     dword ptr [rax+rax+00h]
0x180663f0f  mov     [r12], rsi
0x180663f13  mov     dword ptr [r14], 1
0x180663f1a  xor     edx, edx; struct IUri *
0x180663f1c  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180663f23  lea     rcx, [rbp+var_38]; this
0x180663f27  mov     [rbp+var_38], rax
0x180663f2b  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180663f2f  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180663f34  jmp     loc_180663D96
0x180663f39  cmp     edi, 1
0x180663f3c  jb      loc_180663D96
0x180663f42  mov     rdi, [rcx+20h]
0x180663f46  test    rdi, rdi
0x180663f49  jz      loc_180663D96
0x180663f4f  mov     rdi, [rdi+38h]
0x180663f53  test    rdi, rdi
0x180663f56  jz      short loc_180663F93
0x180663f58  or      rax, 0FFFFFFFFFFFFFFFFh
0x180663f5c  inc     rax
0x180663f5f  cmp     [rdi+rax*2], r13w
0x180663f64  jnz     short loc_180663F5C
0x180663f66  lea     eax, ds:2[rax*2]
0x180663f6d  mov     ecx, eax; cb
0x180663f6f  mov     esi, eax
0x180663f71  call    cs:__imp_CoTaskMemAlloc
0x180663f78  nop     dword ptr [rax+rax+00h]
0x180663f7d  mov     [r12], rax
0x180663f81  test    rax, rax
0x180663f84  jz      short loc_180663FFE
0x180663f86  mov     r9d, esi
0x180663f89  mov     r8, rdi
0x180663f8c  mov     edx, esi
0x180663f8e  jmp     loc_180663DEF
0x180663f93  mov     ebx, 800C0012h
0x180663f98  jmp     loc_180663D96
0x180663f9d  cmp     edi, 1
0x180663fa0  jb      loc_180663D96
0x180663fa6  mov     rcx, [rcx+20h]; this
0x180663faa  test    rcx, rcx
0x180663fad  jz      loc_180663D96
0x180663fb3  mov     rdx, r12; unsigned __int16 **
0x180663fb6  call    ?GetHashString@CDwnPost@@QEAAJPEAPEAG@Z; CDwnPost::GetHashString(ushort * *)
0x180663fbb  mov     ebx, eax
0x180663fbd  mov     eax, r13d
0x180663fc0  test    ebx, ebx
0x180663fc2  setz    al
0x180663fc5  mov     [r14], eax
0x180663fc8  jmp     loc_180663D96
0x180663fcd  mov     rax, [rsi+18h]
0x180663fd1  cmp     dword ptr [rax+0C4h], 9
0x180663fd8  jl      loc_180663DC3
0x180663fde  mov     ecx, [rsi+78h]
0x180663fe1  mov     r9, r14
0x180663fe4  mov     r8d, edi
0x180663fe7  mov     rdx, r12
0x180663fea  call    ?GetAcceptHeadersForCategory@@YAJW4__MIDL___MIDL_itf_urlmonp_0000_0019_0001@@PEAPEAGKPEAK@Z; GetAcceptHeadersForCategory(__MIDL___MIDL_itf_urlmonp_0000_0019_0001,ushort * *,ulong,ulong *)
0x180663fef  mov     ebx, eax
0x180663ff1  test    eax, eax
0x180663ff3  jns     loc_180663D96
0x180663ff9  jmp     loc_180663DC3
0x180663ffe  mov     ebx, 8007000Eh
0x180664003  jmp     loc_180663D96
```
