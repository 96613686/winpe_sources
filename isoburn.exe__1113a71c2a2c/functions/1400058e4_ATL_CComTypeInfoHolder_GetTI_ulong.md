# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1400058e4`
- end: `0x140005b99`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `693`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400052e0`
- `0x1400053f0`
- `0x140005574`
- `0x140005d50`
- `0x140005dc0`
- `0x140005e30`
- `0x140005ea0`
- `0x140006750`
- `0x140006800`

## callees

- `0x140001c08`
- `0x140001fa0`
- `0x140002c9c`
- `0x1400058e4`
- `0x140006a60`
- `0x140010010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000593c`
- `KERNEL32!EnterCriticalSection` at `0x140005acc`
- `KERNEL32!EnterCriticalSection` at `0x14000593c`
- `KERNEL32!EnterCriticalSection` at `0x140005acc`
- `KERNEL32!LeaveCriticalSection` at `0x140005ae2`
- `KERNEL32!LeaveCriticalSection` at `0x140005b66`
- `KERNEL32!LeaveCriticalSection` at `0x140005ae2`
- `KERNEL32!LeaveCriticalSection` at `0x140005b66`
- `KERNEL32!GetModuleFileNameW` at `0x1400059b2`
- `KERNEL32!GetModuleFileNameW` at `0x1400059b2`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400059d2`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400059d2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1400059f3`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1400059f3`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  struct ATL::CAtlModule *v5; // r12
  __int64 v6; // rcx
  WORD *v7; // rdx
  int NameCache; // esi
  DWORD ModuleFileNameW; // eax
  HRESULT v10; // eax
  __int64 v11; // rdx
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned __int64 v14; // r15
  _QWORD *v15; // r14
  struct ITypeInfo *v16; // rdx
  int (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_33;
  }
  v6 = *((_QWORD *)this + 1);
  pptlib = 0;
  if ( ATL::CAtlModule::m_libid.Data1 != *(_DWORD *)v6
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)(v6 + 4)
    || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)(v6 + 8)
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)(v6 + 12) )
  {
    v7 = (WORD *)((char *)this + 16);
LABEL_15:
    v10 = LoadRegTypeLib((const GUID *const)v6, *v7, *((_WORD *)this + 9), lcid, &pptlib);
LABEL_16:
    NameCache = v10;
    if ( v10 >= 0 )
    {
      v11 = *(_QWORD *)this;
      v19 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, __int64, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    v11,
                    &v19);
      if ( NameCache >= 0 )
      {
        v12 = v19;
        v17 = v19;
        if ( v19 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v19)[1])(v19);
          v12 = v19;
        }
        v20 = 0;
        if ( (**v12)(v12, &GUID_00020412_0000_0000_c000_000000000046, &v20) >= 0 )
          ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v17, &v20);
        v13 = 0;
        *((_QWORD *)this + 3) = v17;
        v17 = 0;
        v14 = ((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0);
        if ( v14 )
        {
          v15 = operator new(0x18u);
          if ( v15 )
          {
            v15[1] = this;
            *v15 = ATL::CComTypeInfoHolder::Cleanup;
            EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 16));
            v15[2] = *(_QWORD *)(v14 + 8);
            *(_QWORD *)(v14 + 8) = v15;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 16));
          }
          v13 = v17;
        }
        if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v13 = v17;
        }
        if ( v13 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v19 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v19)[2])(v19);
    }
    goto LABEL_33;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_15;
  NameCache = -2147467259;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( ModuleFileNameW && ModuleFileNameW != 260 )
  {
    v10 = LoadTypeLib(Filename, &pptlib);
    goto LABEL_16;
  }
LABEL_33:
  v16 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v16 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v16);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 24));
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1400058e4  mov     [rsp-8+arg_10], rbx
0x1400058e9  mov     [rsp-8+arg_18], rsi
0x1400058ee  push    rbp
0x1400058ef  push    rdi
0x1400058f0  push    r12
0x1400058f2  push    r14
0x1400058f4  push    r15
0x1400058f6  lea     rbp, [rsp-170h]
0x1400058fe  sub     rsp, 270h
0x140005905  mov     rax, cs:__security_cookie
0x14000590c  xor     rax, rsp
0x14000590f  mov     [rbp+190h+var_30], rax
0x140005916  cmp     qword ptr [rcx+18h], 0
0x14000591b  mov     ebx, edx
0x14000591d  mov     rdi, rcx
0x140005920  jz      short loc_140005930
0x140005922  cmp     qword ptr [rcx+28h], 0
0x140005927  jz      short loc_140005930
0x140005929  xor     eax, eax
0x14000592b  jmp     loc_140005B6E
0x140005930  mov     r12, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005937  lea     rcx, [r12+18h]; lpCriticalSection
0x14000593c  call    cs:__imp_EnterCriticalSection
0x140005942  cmp     qword ptr [rdi+18h], 0
0x140005947  jnz     loc_140005B45
0x14000594d  mov     rcx, [rdi+8]; rguid
0x140005951  mov     [rsp+290h+pptlib], 0
0x14000595a  mov     eax, [rcx]
0x14000595c  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x140005962  jnz     short loc_1400059DA
0x140005964  mov     eax, [rcx+4]
0x140005967  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x14000596d  jnz     short loc_1400059DA
0x14000596f  mov     eax, [rcx+8]
0x140005972  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x140005978  jnz     short loc_1400059DA
0x14000597a  mov     eax, [rcx+0Ch]
0x14000597d  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x140005983  jnz     short loc_1400059DA
0x140005985  lea     rdx, [rdi+10h]
0x140005989  mov     eax, 0FFFFh
0x14000598e  cmp     [rdx], ax
0x140005991  jnz     short loc_1400059DE
0x140005993  cmp     [rdi+12h], ax
0x140005997  jnz     short loc_1400059DE
0x140005999  mov     rcx, cs:hModule; hModule
0x1400059a0  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1400059a5  mov     ebx, 104h
0x1400059aa  mov     esi, 80004005h
0x1400059af  mov     r8d, ebx; nSize
0x1400059b2  call    cs:__imp_GetModuleFileNameW
0x1400059b8  test    eax, eax
0x1400059ba  jz      loc_140005B47
0x1400059c0  cmp     eax, ebx
0x1400059c2  jz      loc_140005B47
0x1400059c8  lea     rdx, [rsp+290h+pptlib]; pptlib
0x1400059cd  lea     rcx, [rsp+290h+Filename]; szFile
0x1400059d2  call    cs:__imp_LoadTypeLib
0x1400059d8  jmp     short loc_1400059F9
0x1400059da  lea     rdx, [rdi+10h]
0x1400059de  movzx   r8d, word ptr [rdi+12h]; wVerMinor
0x1400059e3  lea     rax, [rsp+290h+pptlib]
0x1400059e8  movzx   edx, word ptr [rdx]; wVerMajor
0x1400059eb  mov     r9d, ebx; lcid
0x1400059ee  mov     [rsp+290h+var_270], rax; pptlib
0x1400059f3  call    cs:__imp_LoadRegTypeLib
0x1400059f9  mov     esi, eax
0x1400059fb  test    eax, eax
0x1400059fd  js      loc_140005B47
0x140005a03  mov     rcx, [rsp+290h+pptlib]
0x140005a08  lea     r8, [rsp+290h+var_250]
0x140005a0d  mov     rdx, [rdi]
0x140005a10  mov     [rsp+290h+var_250], 0
0x140005a19  mov     rax, [rcx]
0x140005a1c  mov     rax, [rax+30h]
0x140005a20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a25  mov     esi, eax
0x140005a27  test    eax, eax
0x140005a29  js      loc_140005B1C
0x140005a2f  mov     rcx, [rsp+290h+var_250]
0x140005a34  mov     [rsp+290h+var_260], rcx
0x140005a39  test    rcx, rcx
0x140005a3c  jz      short loc_140005A4F
0x140005a3e  mov     rax, [rcx]
0x140005a41  mov     rax, [rax+8]
0x140005a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a4a  mov     rcx, [rsp+290h+var_250]
0x140005a4f  mov     [rsp+290h+var_248], 0
0x140005a58  lea     r8, [rsp+290h+var_248]
0x140005a5d  mov     rax, [rcx]
0x140005a60  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x140005a67  mov     rax, [rax]
0x140005a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a6f  test    eax, eax
0x140005a71  js      short loc_140005A82
0x140005a73  lea     rdx, [rsp+290h+var_248]
0x140005a78  lea     rcx, [rsp+290h+var_260]
0x140005a7d  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x140005a82  mov     rax, [rsp+290h+var_260]
0x140005a87  xor     ecx, ecx
0x140005a89  mov     [rdi+18h], rax
0x140005a8d  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140005a94  mov     [rsp+290h+var_260], rcx
0x140005a99  lea     rdx, [rax+8]
0x140005a9d  neg     rax
0x140005aa0  sbb     r15, r15
0x140005aa3  and     r15, rdx
0x140005aa6  jz      short loc_140005AED
0x140005aa8  mov     ecx, 18h; Size
0x140005aad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005ab2  mov     r14, rax
0x140005ab5  test    rax, rax
0x140005ab8  jz      short loc_140005AE8
0x140005aba  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x140005ac1  mov     [r14+8], rdi
0x140005ac5  lea     rcx, [r15+10h]; lpCriticalSection
0x140005ac9  mov     [r14], rax
0x140005acc  call    cs:__imp_EnterCriticalSection
0x140005ad2  mov     rcx, [r15+8]
0x140005ad6  mov     [r14+10h], rcx
0x140005ada  lea     rcx, [r15+10h]; lpCriticalSection
0x140005ade  mov     [r15+8], r14
0x140005ae2  call    cs:__imp_LeaveCriticalSection
0x140005ae8  mov     rcx, [rsp+290h+var_260]
0x140005aed  mov     rdx, [rsp+290h+var_248]
0x140005af2  test    rdx, rdx
0x140005af5  jz      short loc_140005B0B
0x140005af7  mov     rax, [rdx]
0x140005afa  mov     rcx, rdx
0x140005afd  mov     rax, [rax+10h]
0x140005b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b06  mov     rcx, [rsp+290h+var_260]
0x140005b0b  test    rcx, rcx
0x140005b0e  jz      short loc_140005B1C
0x140005b10  mov     rax, [rcx]
0x140005b13  mov     rax, [rax+10h]
0x140005b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b1c  mov     rcx, [rsp+290h+pptlib]
0x140005b21  mov     rax, [rcx]
0x140005b24  mov     rax, [rax+10h]
0x140005b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b2d  mov     rcx, [rsp+290h+var_250]
0x140005b32  test    rcx, rcx
0x140005b35  jz      short loc_140005B47
0x140005b37  mov     rax, [rcx]
0x140005b3a  mov     rax, [rax+10h]
0x140005b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b43  jmp     short loc_140005B47
0x140005b45  xor     esi, esi
0x140005b47  mov     rdx, [rdi+18h]; struct ITypeInfo *
0x140005b4b  test    rdx, rdx
0x140005b4e  jz      short loc_140005B61
0x140005b50  cmp     qword ptr [rdi+28h], 0
0x140005b55  jnz     short loc_140005B61
0x140005b57  mov     rcx, rdi; this
0x140005b5a  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x140005b5f  mov     esi, eax
0x140005b61  lea     rcx, [r12+18h]; lpCriticalSection
0x140005b66  call    cs:__imp_LeaveCriticalSection
0x140005b6c  mov     eax, esi
0x140005b6e  mov     rcx, [rbp+190h+var_30]
0x140005b75  xor     rcx, rsp; StackCookie
0x140005b78  call    __security_check_cookie
0x140005b7d  lea     r11, [rsp+290h+var_20]
0x140005b85  mov     rbx, [r11+40h]
0x140005b89  mov     rsi, [r11+48h]
0x140005b8d  mov     rsp, r11
0x140005b90  pop     r15
0x140005b92  pop     r14
0x140005b94  pop     r12
0x140005b96  pop     rdi
0x140005b97  pop     rbp
0x140005b98  retn
```
