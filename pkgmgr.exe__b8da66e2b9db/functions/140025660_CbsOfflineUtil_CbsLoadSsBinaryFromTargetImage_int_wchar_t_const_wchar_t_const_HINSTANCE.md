# CbsOfflineUtil::CbsLoadSsBinaryFromTargetImage(int,wchar_t const *,wchar_t const *,HINSTANCE__ * *)

- ea: `0x140025660`
- end: `0x140025735`
- name: `?CbsLoadSsBinaryFromTargetImage@CbsOfflineUtil@@UEAAJHPEB_W0PEAPEAUHINSTANCE__@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(CbsOfflineUtil *this, __int64, const wchar_t *, const wchar_t *, HINSTANCE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x140002360`
- `0x140005684`
- `0x1400056ac`
- `0x140012a00`
- `0x140025660`
- `0x1400258f0`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400256c9`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1400256c9`

## pseudocode

```c
__int64 __fastcall CbsOfflineUtil::CbsLoadSsBinaryFromTargetImage(
        CbsOfflineUtil *this,
        __int64 a2,
        const wchar_t *a3,
        const wchar_t *a4,
        HINSTANCE *a5)
{
  __int64 v5; // rax
  int v6; // eax
  unsigned int LastError; // ebx
  HMODULE Library; // rax
  const char *v9; // r9
  HMODULE v11; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = *(_QWORD *)this;
  lpLibFileName = 0;
  v6 = (*(__int64 (__fastcall **)(CbsOfflineUtil *, __int64, const wchar_t *, const wchar_t *))(v5 + 56))(
         this,
         a2,
         a3,
         a4);
  LastError = v6;
  if ( v6 >= 0 )
  {
    Library = LoadLibraryExW(lpLibFileName, 0, 8u);
    v11 = Library;
    if ( Library )
    {
      v11 = 0;
      *a5 = Library;
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v11);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x128,
                    (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
                    v9);
      Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x125,
      (unsigned int)"onecore\\base\\cbs\\offlineutil\\cbsofflineimagestack.cpp",
      (const char *)(unsigned int)v6,
      (int)&lpLibFileName);
  }
  Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(&lpLibFileName);
  return LastError;
}

```

## disassembly

```asm
0x140025660  push    rbx
0x140025662  push    rdi
0x140025663  sub     rsp, 58h
0x140025667  mov     rax, cs:__security_cookie
0x14002566e  xor     rax, rsp
0x140025671  mov     [rsp+68h+var_28], rax
0x140025676  mov     rax, [rcx]
0x140025679  lea     r10, [rsp+68h+lpLibFileName]
0x14002567e  mov     rdi, [rsp+68h+arg_20]
0x140025686  mov     [rsp+68h+lpLibFileName], 0
0x14002568f  mov     qword ptr [rsp+68h+var_48], r10; int
0x140025694  mov     rax, [rax+38h]
0x140025698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002569d  mov     ebx, eax
0x14002569f  test    eax, eax
0x1400256a1  jns     short loc_1400256BE
0x1400256a3  mov     rcx, [rsp+68h]; this
0x1400256a8  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x1400256af  mov     r9d, eax; char *
0x1400256b2  mov     edx, 125h; void *
0x1400256b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400256bc  jmp     short loc_140025715
0x1400256be  mov     rcx, [rsp+68h+lpLibFileName]; lpLibFileName
0x1400256c3  xor     edx, edx; hFile
0x1400256c5  lea     r8d, [rdx+8]; dwFlags
0x1400256c9  call    cs:__imp_LoadLibraryExW
0x1400256cf  mov     [rsp+68h+var_38], rax
0x1400256d4  test    rax, rax
0x1400256d7  jnz     short loc_1400256FD
0x1400256d9  mov     rcx, [rsp+68h]; this
0x1400256de  lea     r8, aOnecoreBaseCbs_0; "onecore\\base\\cbs\\offlineutil\\cbsoff"...
0x1400256e5  mov     edx, 128h; void *
0x1400256ea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400256ef  lea     rcx, [rsp+68h+var_38]
0x1400256f4  mov     ebx, eax
0x1400256f6  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1400256fb  jmp     short loc_140025715
0x1400256fd  lea     rcx, [rsp+68h+var_38]
0x140025702  mov     [rsp+68h+var_38], 0
0x14002570b  mov     [rdi], rax
0x14002570e  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x140025713  xor     ebx, ebx
0x140025715  lea     rcx, [rsp+68h+lpLibFileName]
0x14002571a  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoHeapPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoHeapPtr<wchar_t>>::Close(void)
0x14002571f  mov     eax, ebx
0x140025721  mov     rcx, [rsp+68h+var_28]
0x140025726  xor     rcx, rsp; StackCookie
0x140025729  call    __security_check_cookie
0x14002572e  add     rsp, 58h
0x140025732  pop     rdi
0x140025733  pop     rbx
0x140025734  retn
```
