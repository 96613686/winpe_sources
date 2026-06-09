# GetLibIdOfTypeLib

- ea: `0x180059b90`
- end: `0x180059d13`
- name: `GetLibIdOfTypeLib`
- size: `387`
- prototype: `__int64 __fastcall(struct ITypeLib *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051900`

## callees

- `0x180014840`
- `0x1800161b8`
- `0x18001a538`
- `0x18004d900`
- `0x18004e530`
- `0x180059278`
- `0x18005946c`
- `0x180059b90`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180059c1a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180059c1a`

## string_xrefs

- `0x180059be4`: `mincore\com\oleaut32\typelib\clutil.cpp`
- `0x180059ccd`: `mincore\com\oleaut32\typelib\clutil.cpp`

## pseudocode

```c
__int64 __fastcall GetLibIdOfTypeLib(struct ITypeLib *a1, unsigned __int16 **a2)
{
  struct ITypeLibVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 v7; // si
  unsigned __int16 v8; // r14
  unsigned int Data1; // r15d
  const unsigned __int16 *PathOfLoadedTypelib; // rax
  int RegTypeLibOfSzGuid_WithSyskind; // eax
  __int64 v12; // rdx
  int v14; // [rsp+20h] [rbp-69h]
  int v15; // [rsp+20h] [rbp-69h]
  unsigned __int16 *v16; // [rsp+28h] [rbp-61h]
  GUID *rguid; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 v18[4]; // [rsp+58h] [rbp-31h] BYREF
  ITypeLib sz[10]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  lpVtbl = a1->lpVtbl;
  rguid = 0;
  v5 = ((__int64 (__fastcall *)(struct ITypeLib *, GUID **))lpVtbl->GetLibAttr)(a1, &rguid);
  v6 = v5;
  if ( v5 >= 0 )
  {
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(rguid, (LPOLESTR)sz, 39);
    v7 = *(_WORD *)rguid[1].Data4;
    v8 = *(_WORD *)&rguid[1].Data4[2];
    Data1 = rguid[1].Data1;
    ((void (__fastcall *)(struct ITypeLib *))a1->lpVtbl->ReleaseTLibAttr)(a1);
    PathOfLoadedTypelib = OLE_TYPEMGR::GetPathOfLoadedTypelib(g_poletmgr, a1, 0);
    *(_QWORD *)v18 = 0;
    if ( !PathOfLoadedTypelib )
    {
      RegTypeLibOfSzGuid_WithSyskind = LoadRegTypeLibOfSzGuid_WithSyskind(sz, v7, v8, Data1, 0, (BSTR *)v18, 0, 0, 0);
      v6 = RegTypeLibOfSzGuid_WithSyskind;
      if ( RegTypeLibOfSzGuid_WithSyskind < 0 )
      {
        v12 = 1267;
        goto LABEL_9;
      }
      PathOfLoadedTypelib = *(const unsigned __int16 **)v18;
    }
    RegTypeLibOfSzGuid_WithSyskind = GetLibIdOfRegLib(
                                       (const unsigned __int16 *)sz,
                                       v7,
                                       v8,
                                       Data1,
                                       PathOfLoadedTypelib,
                                       v16,
                                       a2);
    v6 = RegTypeLibOfSzGuid_WithSyskind;
    if ( RegTypeLibOfSzGuid_WithSyskind >= 0 )
    {
      v6 = 0;
      goto LABEL_11;
    }
    v12 = 1281;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"mincore\\com\\oleaut32\\typelib\\clutil.cpp",
      (const char *)(unsigned int)RegTypeLibOfSzGuid_WithSyskind,
      v15);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v18);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4DA,
    (unsigned int)"mincore\\com\\oleaut32\\typelib\\clutil.cpp",
    (const char *)(unsigned int)v5,
    v14);
  return v6;
}

```

## disassembly

```asm
0x180059b90  mov     [rsp-8+arg_10], rbx
0x180059b95  mov     [rsp-8+arg_18], rsi
0x180059b9a  push    rbp
0x180059b9b  push    rdi
0x180059b9c  push    r12
0x180059b9e  push    r14
0x180059ba0  push    r15
0x180059ba2  lea     rbp, [rsp-37h]
0x180059ba7  sub     rsp, 0C0h
0x180059bae  mov     rax, cs:__security_cookie
0x180059bb5  xor     rax, rsp
0x180059bb8  mov     [rbp+57h+var_30], rax
0x180059bbc  mov     rax, [rcx]
0x180059bbf  mov     r12, rdx
0x180059bc2  lea     rdx, [rbp+57h+rguid]
0x180059bc6  mov     [rbp+57h+rguid], 0
0x180059bce  mov     rdi, rcx
0x180059bd1  mov     rax, [rax+38h]
0x180059bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059bda  mov     ebx, eax
0x180059bdc  test    eax, eax
0x180059bde  jns     short loc_180059BFD
0x180059be0  mov     rcx, [rbp+5Fh]; this
0x180059be4  lea     r8, aMincoreComOlea_1; "mincore\\com\\oleaut32\\typelib\\clutil"...
0x180059beb  mov     r9d, eax; char *
0x180059bee  mov     edx, 4DAh; void *
0x180059bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059bf8  jmp     loc_180059CE9
0x180059bfd  xor     edx, edx; Val
0x180059bff  lea     rcx, [rbp+57h+sz]; void *
0x180059c03  lea     r8d, [rdx+4Eh]; Size
0x180059c07  call    memset_0
0x180059c0c  mov     rcx, [rbp+57h+rguid]; rguid
0x180059c10  lea     rdx, [rbp+57h+sz]; lpsz
0x180059c14  mov     r8d, 27h ; '''; cchMax
0x180059c1a  call    cs:__imp_StringFromGUID2
0x180059c20  mov     rdx, [rbp+57h+rguid]
0x180059c24  mov     rcx, rdi
0x180059c27  mov     rax, [rdi]
0x180059c2a  movzx   esi, word ptr [rdx+18h]
0x180059c2e  mov     rax, [rax+60h]
0x180059c32  movzx   r14d, word ptr [rdx+1Ah]
0x180059c37  mov     r15d, [rdx+10h]
0x180059c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059c40  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x180059c47  xor     r8d, r8d; int
0x180059c4a  mov     rdx, rdi; struct ITypeLib *
0x180059c4d  call    ?GetPathOfLoadedTypelib@OLE_TYPEMGR@@QEAAPEBGPEAUITypeLib@@H@Z; OLE_TYPEMGR::GetPathOfLoadedTypelib(ITypeLib *,int)
0x180059c52  mov     qword ptr [rbp+57h+var_88], 0
0x180059c5a  test    rax, rax
0x180059c5d  jnz     short loc_180059CA1
0x180059c5f  mov     [rsp+0E0h+var_A0], al
0x180059c63  lea     rcx, [rbp+57h+sz]
0x180059c67  mov     [rsp+0E0h+var_A8], rax
0x180059c6c  mov     r9d, r15d
0x180059c6f  mov     dword ptr [rsp+0E0h+var_B0], eax
0x180059c73  movzx   r8d, r14w
0x180059c77  lea     rax, [rbp+57h+var_88]
0x180059c7b  movzx   edx, si
0x180059c7e  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x180059c83  mov     dword ptr [rsp+0E0h+var_C0], 0
0x180059c8b  call    LoadRegTypeLibOfSzGuid_WithSyskind
0x180059c90  mov     ebx, eax
0x180059c92  test    eax, eax
0x180059c94  jns     short loc_180059C9D
0x180059c96  mov     edx, 4F3h
0x180059c9b  jmp     short loc_180059CC9
0x180059c9d  mov     rax, qword ptr [rbp+57h+var_88]
0x180059ca1  mov     [rsp+0E0h+var_B0], r12; unsigned __int16 **
0x180059ca6  lea     rcx, [rbp+57h+sz]; unsigned __int16 *
0x180059caa  mov     r9d, r15d; unsigned int
0x180059cad  mov     [rsp+0E0h+var_C0], rax; int
0x180059cb2  movzx   r8d, r14w; unsigned __int16
0x180059cb6  movzx   edx, si; unsigned __int16
0x180059cb9  call    ?GetLibIdOfRegLib@@YAJPEBGGGK00PEAPEAG@Z; GetLibIdOfRegLib(ushort const *,ushort,ushort,ulong,ushort const *,ushort const *,ushort * *)
0x180059cbe  mov     ebx, eax
0x180059cc0  test    eax, eax
0x180059cc2  jns     short loc_180059CDE
0x180059cc4  mov     edx, 501h; void *
0x180059cc9  mov     rcx, [rbp+5Fh]; this
0x180059ccd  lea     r8, aMincoreComOlea_1; "mincore\\com\\oleaut32\\typelib\\clutil"...
0x180059cd4  mov     r9d, eax; char *
0x180059cd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059cdc  jmp     short loc_180059CE0
0x180059cde  xor     ebx, ebx
0x180059ce0  lea     rcx, [rbp+57h+var_88]
0x180059ce4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180059ce9  mov     eax, ebx
0x180059ceb  mov     rcx, [rbp+57h+var_30]
0x180059cef  xor     rcx, rsp; StackCookie
0x180059cf2  call    __security_check_cookie
0x180059cf7  lea     r11, [rsp+0E0h+var_20]
0x180059cff  mov     rbx, [r11+40h]
0x180059d03  mov     rsi, [r11+48h]
0x180059d07  mov     rsp, r11
0x180059d0a  pop     r15
0x180059d0c  pop     r14
0x180059d0e  pop     r12
0x180059d10  pop     rdi
0x180059d11  pop     rbp
0x180059d12  retn
```
