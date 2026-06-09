# DiskQuotaUIClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180011790`
- end: `0x1800118e1`
- name: `?CreateInstance@DiskQuotaUIClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `337`
- prototype: `int(DiskQuotaUIClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001510`
- `0x180006ec0`
- `0x180011790`
- `0x180016340`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800117d1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800117d1`

## pseudocode

```c
__int64 __fastcall DiskQuotaUIClassFactory::CreateInstance(
        DiskQuotaUIClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int Instance; // ebx
  _DWORD *v10; // rax
  _DWORD *v11; // rdi
  OLECHAR sz[264]; // [rsp+30h] [rbp-238h] BYREF

  StringFromGUID2(a3, sz, 260);
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  if ( !a2
    || *(_QWORD *)&IID_IUnknown.Data1 == *(_QWORD *)&a3->Data1 && *(_QWORD *)IID_IUnknown.Data4 == *(_QWORD *)a3->Data4 )
  {
    try
    {
      if ( *(_QWORD *)((char *)this + 12) == *(_QWORD *)&CLSID_DiskQuotaUI.Data1
        && *(_QWORD *)((char *)this + 20) == *(_QWORD *)CLSID_DiskQuotaUI.Data4 )
      {
        Instance = DiskQuotaPropSheetExt::CreateInstance(a3, a4);
      }
      else if ( *(_QWORD *)((char *)this + 12) == *(_QWORD *)&CLSID_QuotaUIHelper.Data1
             && *(_QWORD *)((char *)this + 20) == *(_QWORD *)CLSID_QuotaUIHelper.Data4 )
      {
        v10 = operator new(0x10u);
        v11 = v10;
        if ( v10 )
        {
          *(_QWORD *)v10 = &CElevatedUIHelper::`vftable';
          v10[2] = 1;
          _InterlockedIncrement(&g_cRefThisDll);
          Instance = (**(__int64 (__fastcall ***)(void *, const struct _GUID *, void **))v10)(v10, a3, a4);
          (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
        }
        else
        {
          Instance = -2147024882;
        }
      }
      else
      {
        Instance = -2147418113;
      }
    }
    catch ( CAllocException )
    {
      if ( *a4 )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 16LL))(*a4);
        *a4 = 0;
      }
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147221232;
  }
  return Instance;
}

```

## disassembly

```asm
0x180011790  mov     [rsp+arg_0], rbx
0x180011795  push    rsi
0x180011796  push    rdi
0x180011797  push    r14
0x180011799  sub     rsp, 250h
0x1800117a0  mov     rax, cs:__security_cookie
0x1800117a7  xor     rax, rsp
0x1800117aa  mov     [rsp+268h+var_28], rax
0x1800117b2  mov     r14, r9
0x1800117b5  mov     rsi, r8
0x1800117b8  mov     rdi, rdx
0x1800117bb  mov     rbx, rcx
0x1800117be  mov     [rsp+268h+var_248], r9
0x1800117c3  mov     r8d, 104h; cchMax
0x1800117c9  lea     rdx, [rsp+268h+sz]; lpsz
0x1800117ce  mov     rcx, rsi; rguid
0x1800117d1  call    cs:__imp_StringFromGUID2
0x1800117d7  test    r14, r14
0x1800117da  jnz     short loc_1800117E6
0x1800117dc  mov     eax, 80070057h
0x1800117e1  jmp     loc_1800118BD
0x1800117e6  mov     qword ptr [r14], 0
0x1800117ed  test    rdi, rdi
0x1800117f0  jz      short loc_180011815
0x1800117f2  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x1800117f9  cmp     rax, [rsi]
0x1800117fc  jnz     short loc_18001180B
0x1800117fe  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x180011805  cmp     rax, [rsi+8]
0x180011809  jz      short loc_180011815
0x18001180b  mov     ebx, 80040110h
0x180011810  jmp     loc_1800118B5
0x180011815  mov     rax, [rbx+0Ch]
0x180011819  cmp     rax, qword ptr cs:CLSID_DiskQuotaUI.Data1
0x180011820  jnz     short loc_18001183E
0x180011822  mov     rax, [rbx+14h]
0x180011826  cmp     rax, qword ptr cs:CLSID_DiskQuotaUI.Data4
0x18001182d  jnz     short loc_18001183E
0x18001182f  mov     rdx, r14; void **
0x180011832  mov     rcx, rsi; struct _GUID *
0x180011835  call    ?CreateInstance@DiskQuotaPropSheetExt@@SAJAEBU_GUID@@PEAPEAX@Z; DiskQuotaPropSheetExt::CreateInstance(_GUID const &,void * *)
0x18001183a  mov     ebx, eax
0x18001183c  jmp     short loc_1800118B5
0x18001183e  mov     rax, [rbx+0Ch]
0x180011842  cmp     rax, qword ptr cs:CLSID_QuotaUIHelper.Data1
0x180011849  jnz     short loc_1800118B0
0x18001184b  mov     rax, [rbx+14h]
0x18001184f  cmp     rax, qword ptr cs:CLSID_QuotaUIHelper.Data4
0x180011856  jnz     short loc_1800118B0
0x180011858  mov     ecx, 10h; uBytes
0x18001185d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011862  mov     rdi, rax
0x180011865  test    rax, rax
0x180011868  jz      short loc_1800118A9
0x18001186a  lea     rax, ??_7CElevatedUIHelper@@6B@; const CElevatedUIHelper::`vftable'
0x180011871  mov     [rdi], rax
0x180011874  mov     dword ptr [rdi+8], 1
0x18001187b  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180011882  mov     rax, [rdi]
0x180011885  mov     r8, r14
0x180011888  mov     rdx, rsi
0x18001188b  mov     rcx, rdi
0x18001188e  mov     rax, [rax]
0x180011891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011896  mov     ebx, eax
0x180011898  mov     rax, [rdi]
0x18001189b  mov     rcx, rdi
0x18001189e  mov     rax, [rax+10h]
0x1800118a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118a7  jmp     short loc_18001183C
0x1800118a9  mov     ebx, 8007000Eh
0x1800118ae  jmp     short loc_1800118B5
0x1800118b0  mov     ebx, 8000FFFFh
0x1800118b5  jmp     short loc_1800118BB
0x1800118b7  mov     ebx, dword ptr [rsp+268h+var_248]
0x1800118bb  mov     eax, ebx
0x1800118bd  mov     rcx, [rsp+268h+var_28]
0x1800118c5  xor     rcx, rsp; StackCookie
0x1800118c8  call    __security_check_cookie
0x1800118cd  mov     rbx, [rsp+268h+arg_0]
0x1800118d5  add     rsp, 250h
0x1800118dc  pop     r14
0x1800118de  pop     rdi
0x1800118df  pop     rsi
0x1800118e0  retn
```
