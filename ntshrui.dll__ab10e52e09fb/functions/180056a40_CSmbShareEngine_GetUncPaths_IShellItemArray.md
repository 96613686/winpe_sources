# CSmbShareEngine::GetUncPaths(IShellItemArray * *)

- ea: `0x180056a40`
- end: `0x180056c04`
- name: `?GetUncPaths@CSmbShareEngine@@UEAAJPEAPEAUIShellItemArray@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(CSmbShareEngine *__hidden this, IShellItemArray **ppsiItemArray)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001aa00`
- `0x18001d1dc`
- `0x18001d9a0`
- `0x180056a40`
- `0x18005a934`
- `0x18005e024`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056bba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056bba`
- `SHELL32!SHParseDisplayName` at `0x180056b94`
- `SHELL32!SHParseDisplayName` at `0x180056b94`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180056be2`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180056be2`

## pseudocode

```c
__int64 __fastcall CSmbShareEngine::GetUncPaths(CSmbShareEngine *this, IShellItemArray **ppsiItemArray)
{
  __int64 v3; // rcx
  HRESULT ShareInfo; // ebx
  LPCITEMIDLIST *v6; // rsi
  void *v7; // rcx
  int v8; // eax
  __int64 v9; // rdi
  __int64 v10; // rcx
  LPVOID pv[3]; // [rsp+30h] [rbp-18h] BYREF
  UINT cidl; // [rsp+80h] [rbp+38h] BYREF
  struct IShellItem *v14; // [rsp+88h] [rbp+40h] BYREF
  PCWSTR pszName; // [rsp+90h] [rbp+48h] BYREF
  struct IShareInfo *v16; // [rsp+98h] [rbp+50h] BYREF

  *ppsiItemArray = 0;
  v3 = *((_QWORD *)this + 7);
  cidl = 0;
  ShareInfo = (*(__int64 (__fastcall **)(__int64, UINT *))(*(_QWORD *)v3 + 56LL))(v3, &cidl);
  if ( ShareInfo >= 0 )
  {
    if ( cidl )
    {
      v6 = 0;
      pszName = 0;
      v14 = 0;
      ShareInfo = ULongLongMult(cidl, 8u, (unsigned __int64 *)&v14);
      if ( ShareInfo >= 0 )
      {
        v8 = CTCoAllocPolicy::Alloc(v7, 1u, (unsigned __int64)v14, (void **)&pszName);
        v6 = (LPCITEMIDLIST *)pszName;
        ShareInfo = v8;
      }
      v9 = 0;
      while ( ShareInfo >= 0 )
      {
        if ( (unsigned int)v9 >= cidl )
        {
          ShareInfo = SHCreateShellItemArrayFromIDLists(cidl, v6, ppsiItemArray);
          break;
        }
        v10 = *((_QWORD *)this + 7);
        v14 = 0;
        ShareInfo = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IShellItem **))(*(_QWORD *)v10 + 64LL))(
                      v10,
                      (unsigned int)v9,
                      &v14);
        if ( ShareInfo >= 0 )
        {
          if ( (unsigned int)IsItemDirectory(v14) )
          {
            pv[0] = 0;
            ShareInfo = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPVOID *))v14->lpVtbl->GetDisplayName)(
                          v14,
                          2147844096LL,
                          pv);
            if ( ShareInfo >= 0 )
            {
              v16 = 0;
              ShareInfo = CSmbShareEngine::_GetShareInfo(this, (const unsigned __int16 *)pv[0], &v16);
              if ( ShareInfo >= 0 )
              {
                pszName = 0;
                ShareInfo = (*(__int64 (__fastcall **)(struct IShareInfo *, PCWSTR *))(*(_QWORD *)v16 + 104LL))(
                              v16,
                              &pszName);
                if ( ShareInfo >= 0 )
                {
                  ShareInfo = SHParseDisplayName(pszName, 0, (LPITEMIDLIST *)&v6[v9], 0, 0);
                  CoTaskMemFree((LPVOID)pszName);
                }
                (*(void (__fastcall **)(struct IShareInfo *))(*(_QWORD *)v16 + 16LL))(v16);
              }
              CoTaskMemFree(pv[0]);
            }
          }
          ((void (__fastcall *)(struct IShellItem *))v14->lpVtbl->Release)(v14);
        }
        v9 = (unsigned int)(v9 + 1);
      }
      FreeIDListArrayFull(v6, cidl);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)ShareInfo;
}

```

## disassembly

```asm
0x180056a40  push    rbp
0x180056a42  push    rbx
0x180056a43  push    rsi
0x180056a44  push    rdi
0x180056a45  push    r14
0x180056a47  push    r15
0x180056a49  mov     rbp, rsp
0x180056a4c  sub     rsp, 48h
0x180056a50  mov     qword ptr [rdx], 0
0x180056a57  mov     r14, rcx
0x180056a5a  mov     rcx, [rcx+38h]
0x180056a5e  mov     r15, rdx
0x180056a61  mov     [rbp+cidl], 0
0x180056a68  lea     rdx, [rbp+cidl]
0x180056a6c  mov     rax, [rcx]
0x180056a6f  mov     rax, [rax+38h]
0x180056a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056a78  mov     ebx, eax
0x180056a7a  test    eax, eax
0x180056a7c  js      loc_180056BF5
0x180056a82  mov     eax, [rbp+cidl]
0x180056a85  test    eax, eax
0x180056a87  jnz     short loc_180056A93
0x180056a89  mov     ebx, 80070057h
0x180056a8e  jmp     loc_180056BF5
0x180056a93  xor     esi, esi
0x180056a95  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x180056a99  mov     rcx, rax; unsigned __int64
0x180056a9c  mov     [rbp+pszName], rsi
0x180056aa0  mov     [rbp+arg_8], rsi
0x180056aa4  lea     edx, [rsi+8]; unsigned __int64
0x180056aa7  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180056aac  mov     ebx, eax
0x180056aae  test    eax, eax
0x180056ab0  js      short loc_180056AC8
0x180056ab2  mov     r8, [rbp+arg_8]; unsigned __int64
0x180056ab6  lea     r9, [rbp+pszName]; void **
0x180056aba  lea     edx, [rsi+1]; unsigned int
0x180056abd  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180056ac2  mov     rsi, [rbp+pszName]
0x180056ac6  mov     ebx, eax
0x180056ac8  xor     edi, edi
0x180056aca  jmp     loc_180056BD2
0x180056acf  mov     ecx, [rbp+cidl]; cidl
0x180056ad2  cmp     edi, ecx
0x180056ad4  jnb     loc_180056BDC
0x180056ada  mov     rcx, [r14+38h]
0x180056ade  lea     r8, [rbp+arg_8]
0x180056ae2  mov     [rbp+arg_8], 0
0x180056aea  mov     edx, edi
0x180056aec  mov     rax, [rcx]
0x180056aef  mov     rax, [rax+40h]
0x180056af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056af8  mov     ebx, eax
0x180056afa  test    eax, eax
0x180056afc  js      loc_180056BD0
0x180056b02  mov     rcx, [rbp+arg_8]; struct IShellItem *
0x180056b06  call    ?IsItemDirectory@@YAHPEAUIShellItem@@@Z; IsItemDirectory(IShellItem *)
0x180056b0b  test    eax, eax
0x180056b0d  jz      loc_180056BC0
0x180056b13  mov     rcx, [rbp+arg_8]
0x180056b17  lea     r8, [rbp+pv]
0x180056b1b  mov     [rbp+pv], 0
0x180056b23  mov     edx, 80058000h
0x180056b28  mov     rax, [rcx]
0x180056b2b  mov     rax, [rax+28h]
0x180056b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b34  mov     ebx, eax
0x180056b36  test    eax, eax
0x180056b38  js      loc_180056BC0
0x180056b3e  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180056b42  lea     r8, [rbp+arg_18]; struct IShareInfo **
0x180056b46  mov     rcx, r14; this
0x180056b49  mov     [rbp+arg_18], 0
0x180056b51  call    ?_GetShareInfo@CSmbShareEngine@@AEAAJPEBGPEAPEAUIShareInfo@@@Z; CSmbShareEngine::_GetShareInfo(ushort const *,IShareInfo * *)
0x180056b56  mov     ebx, eax
0x180056b58  test    eax, eax
0x180056b5a  js      short loc_180056BB6
0x180056b5c  mov     rcx, [rbp+arg_18]
0x180056b60  lea     rdx, [rbp+pszName]
0x180056b64  mov     [rbp+pszName], 0
0x180056b6c  mov     rax, [rcx]
0x180056b6f  mov     rax, [rax+68h]
0x180056b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056b78  mov     ebx, eax
0x180056b7a  test    eax, eax
0x180056b7c  js      short loc_180056BA6
0x180056b7e  mov     rcx, [rbp+pszName]; pszName
0x180056b82  lea     r8, [rsi+rdi*8]; ppidl
0x180056b86  xor     r9d, r9d; sfgaoIn
0x180056b89  mov     [rsp+48h+psfgaoOut], 0; psfgaoOut
0x180056b92  xor     edx, edx; pbc
0x180056b94  call    cs:__imp_SHParseDisplayName
0x180056b9a  mov     rcx, [rbp+pszName]; pv
0x180056b9e  mov     ebx, eax
0x180056ba0  call    cs:__imp_CoTaskMemFree
0x180056ba6  mov     rcx, [rbp+arg_18]
0x180056baa  mov     rax, [rcx]
0x180056bad  mov     rax, [rax+10h]
0x180056bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bb6  mov     rcx, [rbp+pv]; pv
0x180056bba  call    cs:__imp_CoTaskMemFree
0x180056bc0  mov     rcx, [rbp+arg_8]
0x180056bc4  mov     rax, [rcx]
0x180056bc7  mov     rax, [rax+10h]
0x180056bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056bd0  inc     edi
0x180056bd2  test    ebx, ebx
0x180056bd4  jns     loc_180056ACF
0x180056bda  jmp     short loc_180056BEA
0x180056bdc  mov     r8, r15; ppsiItemArray
0x180056bdf  mov     rdx, rsi; rgpidl
0x180056be2  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180056be8  mov     ebx, eax
0x180056bea  mov     edx, [rbp+cidl]
0x180056bed  mov     rcx, rsi
0x180056bf0  call    FreeIDListArrayFull
0x180056bf5  mov     eax, ebx
0x180056bf7  add     rsp, 48h
0x180056bfb  pop     r15
0x180056bfd  pop     r14
0x180056bff  pop     rdi
0x180056c00  pop     rsi
0x180056c01  pop     rbx
0x180056c02  pop     rbp
0x180056c03  retn
```
