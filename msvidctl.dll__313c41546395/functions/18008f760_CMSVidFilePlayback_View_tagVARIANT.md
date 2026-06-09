# CMSVidFilePlayback::View(tagVARIANT *)

- ea: `0x18008f760`
- end: `0x18008f930`
- name: `?View@CMSVidFilePlayback@@UEAAJPEAUtagVARIANT@@@Z`
- size: `464`
- prototype: `__int64 __fastcall(CMSVidFilePlayback *__hidden this, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004640`
- `0x1800145ac`
- `0x180070aec`
- `0x18008e4ac`
- `0x18008f760`
- `0x1800f8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f7ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f824`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f84b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f7ea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f824`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18008f84b`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f88c`
- `OLEAUT32!__imp_SysAllocString` at `0x18008f88c`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f8fe`
- `OLEAUT32!__imp_SysFreeString` at `0x18008f8fe`
- `SHLWAPI!PathCreateFromUrlW` at `0x18008f8c4`
- `SHLWAPI!PathCreateFromUrlW` at `0x18008f8c4`
- `SHLWAPI!UrlIsW` at `0x18008f8a2`
- `SHLWAPI!UrlIsW` at `0x18008f8a2`

## pseudocode

```c
__int64 __fastcall CMSVidFilePlayback::View(CMSVidFilePlayback *this, struct tagVARIANT *a2)
{
  int v4; // r8d
  DWORD v5; // ecx
  LONGLONG llVal; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  OLECHAR *v10; // rbx
  HRESULT v11; // edi
  DWORD pcchPath; // [rsp+20h] [rbp-248h] BYREF
  OLECHAR *v13; // [rsp+28h] [rbp-240h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-238h] BYREF

  if ( !*((_BYTE *)this + *(int *)(*((_QWORD *)this - 1) + 4LL)) )
  {
    v4 = -2147221008;
    v5 = -1073478398;
    return ATL::CComCoClass<CMSVidFilePlayback,&__s_GUID const _GUID_37b0353c_a4c8_11d2_b634_00c04f79498e>::Error(
             v5,
             &GUID_37b03539_a4c8_11d2_b634_00c04f79498e,
             v4,
             hInstance);
  }
  if ( !a2 )
    return 2147500035LL;
  if ( a2->vt != 8 )
    return 2147942487LL;
  if ( (unsigned int)_o__wcsnicmp(a2->llVal, L"DVD:", 4) )
  {
    llVal = a2->llVal;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(llVal + 2 * v8) );
    if ( v8 < 7
      || (unsigned int)_o__wcsnicmp(llVal - 14 + 2 * v8, L".DVR-MS", 7)
      && (unsigned int)_o__wcsnicmp(a2->llVal - 14 + 2 * v8, L".TMPSBE", 7) )
    {
      v9 = *(int *)(*((_QWORD *)this - 1) + 4LL);
      if ( *(_QWORD *)((char *)this + v9 + 32) && !DSGraph::IsStopped((CMSVidFilePlayback *)((char *)this + v9 + 24)) )
      {
        v4 = -2147019873;
        v5 = -1073478396;
        return ATL::CComCoClass<CMSVidFilePlayback,&__s_GUID const _GUID_37b0353c_a4c8_11d2_b634_00c04f79498e>::Error(
                 v5,
                 &GUID_37b03539_a4c8_11d2_b634_00c04f79498e,
                 v4,
                 hInstance);
      }
      v13 = SysAllocString(a2->bstrVal);
      v10 = v13;
      if ( UrlIsW(v13, URLIS_FILEURL) )
      {
        pcchPath = 260;
        v11 = PathCreateFromUrlW(v13, pszPath, &pcchPath, 0);
        if ( v11 < 0 )
        {
LABEL_21:
          SysFreeString(v10);
          return (unsigned int)v11;
        }
        ATL::CComBSTR::operator=(&v13, pszPath);
        v10 = v13;
      }
      v11 = (*(__int64 (__fastcall **)(CMSVidFilePlayback *, OLECHAR *))(*(_QWORD *)this + 264LL))(this, v10);
      goto LABEL_21;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18008f760  mov     [rsp+arg_10], rbx
0x18008f765  push    rbp
0x18008f766  push    rsi
0x18008f767  push    rdi
0x18008f768  sub     rsp, 250h
0x18008f76f  mov     rax, cs:__security_cookie
0x18008f776  xor     rax, rsp
0x18008f779  mov     [rsp+268h+var_28], rax
0x18008f781  mov     rax, [rcx-8]
0x18008f785  mov     rsi, rcx
0x18008f788  xor     ebp, ebp
0x18008f78a  mov     rbx, rdx
0x18008f78d  movsxd  rcx, dword ptr [rax+4]
0x18008f791  cmp     [rcx+rsi], bpl
0x18008f795  jnz     short loc_18008F7BA
0x18008f797  mov     r8d, 800401F0h; int
0x18008f79d  mov     ecx, 0C0040502h; dwMessageId
0x18008f7a2  mov     r9, cs:hInstance; HINSTANCE
0x18008f7a9  lea     rdx, _GUID_37b03539_a4c8_11d2_b634_00c04f79498e; struct _GUID *
0x18008f7b0  call    ?Error@?$CComCoClass@VCMSVidFilePlayback@@$1?_GUID_37b0353c_a4c8_11d2_b634_00c04f79498e@@3U__s_GUID@@B@ATL@@SAJIAEBU_GUID@@JPEAUHINSTANCE__@@@Z; ATL::CComCoClass<CMSVidFilePlayback,&__s_GUID const _GUID_37b0353c_a4c8_11d2_b634_00c04f79498e>::Error(uint,_GUID const &,long,HINSTANCE__ *)
0x18008f7b5  jmp     loc_18008F90D
0x18008f7ba  test    rbx, rbx
0x18008f7bd  jnz     short loc_18008F7C9
0x18008f7bf  mov     eax, 80004003h
0x18008f7c4  jmp     loc_18008F90D
0x18008f7c9  cmp     word ptr [rdx], 8
0x18008f7cd  jz      short loc_18008F7D9
0x18008f7cf  mov     eax, 80070057h
0x18008f7d4  jmp     loc_18008F90D
0x18008f7d9  mov     rcx, [rbx+8]
0x18008f7dd  lea     rdx, aDvd_1; "DVD:"
0x18008f7e4  mov     r8d, 4
0x18008f7ea  call    cs:__imp__o__wcsnicmp
0x18008f7f0  test    eax, eax
0x18008f7f2  jz      loc_18008F908
0x18008f7f8  mov     rax, [rbx+8]
0x18008f7fc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008f800  inc     rdi
0x18008f803  cmp     [rax+rdi*2], bp
0x18008f807  jnz     short loc_18008F800
0x18008f809  cmp     rdi, 7
0x18008f80d  jb      short loc_18008F859
0x18008f80f  lea     rcx, [rax-0Eh]
0x18008f813  mov     r8d, 7
0x18008f819  lea     rcx, [rcx+rdi*2]
0x18008f81d  lea     rdx, aDvrMs; ".DVR-MS"
0x18008f824  call    cs:__imp__o__wcsnicmp
0x18008f82a  test    eax, eax
0x18008f82c  jz      loc_18008F908
0x18008f832  mov     rcx, [rbx+8]
0x18008f836  lea     rdx, aTmpsbe; ".TMPSBE"
0x18008f83d  add     rcx, 0FFFFFFFFFFFFFFF2h
0x18008f841  mov     r8d, 7
0x18008f847  lea     rcx, [rcx+rdi*2]
0x18008f84b  call    cs:__imp__o__wcsnicmp
0x18008f851  test    eax, eax
0x18008f853  jz      loc_18008F908
0x18008f859  mov     rax, [rsi-8]
0x18008f85d  movsxd  rcx, dword ptr [rax+4]
0x18008f861  cmp     [rcx+rsi+20h], rbp
0x18008f866  jz      short loc_18008F888
0x18008f868  add     rcx, 18h
0x18008f86c  add     rcx, rsi; this
0x18008f86f  call    ?IsStopped@DSGraph@@QEAA_NXZ; DSGraph::IsStopped(void)
0x18008f874  test    al, al
0x18008f876  jnz     short loc_18008F888
0x18008f878  mov     r8d, 8007139Fh
0x18008f87e  mov     ecx, 0C0040504h
0x18008f883  jmp     loc_18008F7A2
0x18008f888  mov     rcx, [rbx+8]; psz
0x18008f88c  call    cs:__imp_SysAllocString
0x18008f892  mov     rcx, rax; pszUrl
0x18008f895  mov     [rsp+268h+var_240], rax
0x18008f89a  mov     edx, 3; UrlIs
0x18008f89f  mov     rbx, rax
0x18008f8a2  call    cs:__imp_UrlIsW
0x18008f8a8  test    eax, eax
0x18008f8aa  jz      short loc_18008F8E4
0x18008f8ac  xor     r9d, r9d; dwFlags
0x18008f8af  mov     [rsp+268h+pcchPath], 104h
0x18008f8b7  lea     r8, [rsp+268h+pcchPath]; pcchPath
0x18008f8bc  mov     rcx, rbx; pszUrl
0x18008f8bf  lea     rdx, [rsp+268h+pszPath]; pszPath
0x18008f8c4  call    cs:__imp_PathCreateFromUrlW
0x18008f8ca  mov     edi, eax
0x18008f8cc  test    eax, eax
0x18008f8ce  js      short loc_18008F8FB
0x18008f8d0  lea     rdx, [rsp+268h+pszPath]
0x18008f8d5  lea     rcx, [rsp+268h+var_240]
0x18008f8da  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18008f8df  mov     rbx, [rsp+268h+var_240]
0x18008f8e4  mov     rax, [rsi]
0x18008f8e7  mov     rdx, rbx
0x18008f8ea  mov     rcx, rsi
0x18008f8ed  mov     rax, [rax+108h]
0x18008f8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f8f9  mov     edi, eax
0x18008f8fb  mov     rcx, rbx; bstrString
0x18008f8fe  call    cs:__imp_SysFreeString
0x18008f904  mov     eax, edi
0x18008f906  jmp     short loc_18008F90D
0x18008f908  mov     eax, 80004005h
0x18008f90d  mov     rcx, [rsp+268h+var_28]
0x18008f915  xor     rcx, rsp; StackCookie
0x18008f918  call    __security_check_cookie
0x18008f91d  mov     rbx, [rsp+268h+arg_10]
0x18008f925  add     rsp, 250h
0x18008f92c  pop     rdi
0x18008f92d  pop     rsi
0x18008f92e  pop     rbp
0x18008f92f  retn
```
