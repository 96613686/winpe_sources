# HrQueryUserAndRemoveComponent(HWND__ *,INetCfg *,INetCfgComponent *)

- ea: `0x18002c6d4`
- end: `0x18002c920`
- name: `?HrQueryUserAndRemoveComponent@@YAJPEAUHWND__@@PEAUINetCfg@@PEAUINetCfgComponent@@@Z`
- size: `588`
- prototype: `__int64 __fastcall(HWND hWnd, struct INetCfg *, struct INetCfgComponent *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f6bc`
- `0x180030120`

## callees

- `0x180017b50`
- `0x18001e1e0`
- `0x18002b5e8`
- `0x18002b82c`
- `0x18002bf6c`
- `0x18002c0a8`
- `0x18002c6d4`
- `0x180031a78`
- `0x180031b08`
- `0x18003ffac`
- `0x180040648`
- `0x180065010`

## import_xrefs

- `USER32!IsWindow` at `0x18002c70a`
- `USER32!IsWindow` at `0x18002c70a`
- `ole32!CoTaskMemFree` at `0x18002c850`
- `ole32!CoTaskMemFree` at `0x18002c8f3`
- `ole32!CoTaskMemFree` at `0x18002c850`
- `ole32!CoTaskMemFree` at `0x18002c8f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrQueryUserAndRemoveComponent(HWND hWnd, struct INetCfg *a2, struct INetCfgComponent *a3)
{
  int v6; // ebx
  HICON v7; // r15
  int v8; // eax
  _WORD *i; // rsi
  __int64 v10; // r8
  __int64 v11; // rax
  const unsigned __int16 *v12; // r9
  int v13; // eax
  unsigned int v14; // ecx
  unsigned __int16 *v16; // [rsp+40h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-41h] BYREF
  tagOBO_TOKEN v18; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *Src[4]; // [rsp+80h] [rbp-9h] BYREF

  if ( hWnd && !IsWindow(hWnd) )
    return (unsigned int)-2147024809;
  if ( !a2 || !a3 )
    return (unsigned int)-2147467261;
  v16 = 0;
  v6 = ((__int64 (__fastcall *)(struct INetCfgComponent *, unsigned __int16 **))a3->lpVtbl->GetDisplayName)(a3, &v16);
  if ( v6 >= 0 )
  {
    if ( (unsigned int)NcMsgBoxWithVarCaption(hInst, hWnd, 0x3E99u, v16, 0x3E9Au, 0x124u, v16) != 6 )
    {
      v7 = 0;
      v6 = 1;
      goto LABEL_30;
    }
    memset(&v18, 0, sizeof(v18));
    v18.Type = OBO_USER;
    pv = 0;
    v7 = BeginWaitCursor();
    v8 = HrRemoveComponent(a2, a3, &v18, (unsigned __int16 **)&pv);
    v6 = v8;
    if ( v8 == 303139 )
    {
      std::wstring::wstring(Src, L"\r\n");
      for ( i = pv; *i; i += v11 + 1 )
      {
        std::wstring::_Append<unsigned short>(Src);
        v10 = -1;
        do
          ++v10;
        while ( i[v10] );
        std::wstring::_Append<unsigned short>(Src);
        v11 = -1;
        do
          ++v11;
        while ( i[v11] );
      }
      v12 = (const unsigned __int16 *)Src;
      if ( Src[3] > (unsigned __int16 *)7 )
        v12 = Src[0];
      LvReportError(0x3E8Du, hWnd, v16, v12);
      CoTaskMemFree(pv);
      std::wstring::_Tidy_deallocate((__int64)Src);
    }
    else if ( v8 < 0 )
    {
      goto LABEL_23;
    }
    dword_180089D50 = 1;
    v13 = ((__int64 (__fastcall *)(struct INetCfg *))a2->lpVtbl->Apply)(a2);
    dword_180089D50 = 0;
    if ( !v13 )
      goto LABEL_30;
    v6 = v13;
    if ( v13 >= 0 )
      goto LABEL_30;
    ((void (__fastcall *)(struct INetCfg *))a2->lpVtbl->Cancel)(a2);
LABEL_23:
    if ( v6 == -2147180506 )
    {
      v14 = 16044;
    }
    else
    {
      if ( v6 != -2147180507 )
      {
        LvReportErrorHr(v6, 16011, hWnd, v16);
        goto LABEL_30;
      }
      v14 = 16047;
    }
    LvReportError(v14, hWnd, v16, 0);
LABEL_30:
    EndWaitCursor(v7);
    CoTaskMemFree(v16);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c6d4  push    rbp
0x18002c6d6  push    rbx
0x18002c6d7  push    rsi
0x18002c6d8  push    rdi
0x18002c6d9  push    r12
0x18002c6db  push    r14
0x18002c6dd  push    r15
0x18002c6df  lea     rbp, [rsp-27h]
0x18002c6e4  sub     rsp, 0B0h
0x18002c6eb  mov     rax, cs:__security_cookie
0x18002c6f2  xor     rax, rsp
0x18002c6f5  mov     [rbp+57h+var_40], rax
0x18002c6f9  mov     rsi, r8
0x18002c6fc  mov     r14, rdx
0x18002c6ff  mov     rdi, rcx
0x18002c702  xor     r12d, r12d
0x18002c705  test    rcx, rcx
0x18002c708  jz      short loc_18002C71E
0x18002c70a  call    cs:__imp_IsWindow
0x18002c710  test    eax, eax
0x18002c712  jnz     short loc_18002C71E
0x18002c714  mov     ebx, 80070057h
0x18002c719  jmp     loc_18002C900
0x18002c71e  test    r14, r14
0x18002c721  jz      loc_18002C8FB
0x18002c727  test    rsi, rsi
0x18002c72a  jz      loc_18002C8FB
0x18002c730  mov     [rbp+57h+var_A0], r12
0x18002c734  mov     rax, [rsi]
0x18002c737  lea     rdx, [rbp+57h+var_A0]
0x18002c73b  mov     rcx, rsi
0x18002c73e  mov     rax, [rax+18h]
0x18002c742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c747  mov     ebx, eax
0x18002c749  test    eax, eax
0x18002c74b  js      loc_18002C900
0x18002c751  mov     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x18002c755  mov     [rsp+0E0h+var_B0], r9
0x18002c75a  mov     [rsp+0E0h+uType], 124h; uType
0x18002c762  mov     [rsp+0E0h+var_C0], 3E9Ah; unsigned int
0x18002c76a  mov     r8d, 3E99h; unsigned int
0x18002c770  mov     rdx, rdi; hWnd
0x18002c773  mov     rcx, cs:hInst; hModule
0x18002c77a  call    ?NcMsgBoxWithVarCaption@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IPEBGIIZZ; NcMsgBoxWithVarCaption(HINSTANCE__ *,HWND__ *,uint,ushort const *,uint,uint,...)
0x18002c77f  cmp     eax, 6
0x18002c782  jnz     loc_18002C8DF
0x18002c788  xorps   xmm0, xmm0
0x18002c78b  movups  xmmword ptr [rbp+57h+var_90.Type], xmm0
0x18002c78f  movups  xmmword ptr [rbp+57h+var_90.pszwManufacturer], xmm0
0x18002c793  movups  xmmword ptr [rbp+57h+var_90.pszwDisplayName], xmm0
0x18002c797  mov     [rbp+57h+var_90.Type], 1
0x18002c79e  mov     [rbp+57h+pv], r12
0x18002c7a2  call    ?BeginWaitCursor@@YAPEAUHICON__@@XZ; BeginWaitCursor(void)
0x18002c7a7  mov     r15, rax
0x18002c7aa  lea     r9, [rbp+57h+pv]; unsigned __int16 **
0x18002c7ae  lea     r8, [rbp+57h+var_90]; struct tagOBO_TOKEN *
0x18002c7b2  mov     rdx, rsi; struct INetCfgComponent *
0x18002c7b5  mov     rcx, r14; struct INetCfg *
0x18002c7b8  call    ?HrRemoveComponent@@YAJPEAUINetCfg@@PEAUINetCfgComponent@@PEAUtagOBO_TOKEN@@PEAPEAG@Z; HrRemoveComponent(INetCfg *,INetCfgComponent *,tagOBO_TOKEN *,ushort * *)
0x18002c7bd  mov     ebx, eax
0x18002c7bf  cmp     eax, 4A023h
0x18002c7c4  jnz     loc_18002C862
0x18002c7ca  lea     rdx, asc_1800796CC; "\r\n"
0x18002c7d1  lea     rcx, [rbp+57h+Src]
0x18002c7d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002c7da  nop
0x18002c7db  mov     rsi, [rbp+57h+pv]
0x18002c7df  jmp     short loc_18002C827
0x18002c7e1  mov     r8d, 2
0x18002c7e7  lea     rdx, asc_1800796CC; "\r\n"
0x18002c7ee  lea     rcx, [rbp+57h+Src]; Src
0x18002c7f2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002c7f7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002c7fb  inc     r8
0x18002c7fe  cmp     [rsi+r8*2], r12w
0x18002c803  jnz     short loc_18002C7FB
0x18002c805  mov     rdx, rsi
0x18002c808  lea     rcx, [rbp+57h+Src]; Src
0x18002c80c  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002c811  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c815  inc     rax
0x18002c818  cmp     [rsi+rax*2], r12w
0x18002c81d  jnz     short loc_18002C815
0x18002c81f  lea     rsi, [rsi+rax*2]
0x18002c823  add     rsi, 2
0x18002c827  cmp     [rsi], r12w
0x18002c82b  jnz     short loc_18002C7E1
0x18002c82d  lea     r9, [rbp+57h+Src]
0x18002c831  cmp     [rbp+57h+var_48], 7
0x18002c836  cmova   r9, [rbp+57h+Src]; unsigned __int16 *
0x18002c83b  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x18002c83f  mov     rdx, rdi; HWND
0x18002c842  mov     ecx, 3E8Dh; unsigned int
0x18002c847  call    ?LvReportError@@YAXHPEAUHWND__@@PEBG1@Z; LvReportError(int,HWND__ *,ushort const *,ushort const *)
0x18002c84c  mov     rcx, [rbp+57h+pv]; pv
0x18002c850  call    cs:__imp_CoTaskMemFree
0x18002c856  nop
0x18002c857  lea     rcx, [rbp+57h+Src]
0x18002c85b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002c860  jmp     short loc_18002C866
0x18002c862  test    eax, eax
0x18002c864  js      short loc_18002C89D
0x18002c866  mov     cs:dword_180089D50, 1
0x18002c870  mov     rax, [r14]
0x18002c873  mov     rcx, r14
0x18002c876  mov     rax, [rax+28h]
0x18002c87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c87f  mov     cs:dword_180089D50, r12d
0x18002c886  test    eax, eax
0x18002c888  jz      short loc_18002C8E7
0x18002c88a  mov     ebx, eax
0x18002c88c  jns     short loc_18002C8E7
0x18002c88e  mov     rax, [r14]
0x18002c891  mov     rcx, r14
0x18002c894  mov     rax, [rax+30h]
0x18002c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c89d  cmp     ebx, 8004A026h
0x18002c8a3  jnz     short loc_18002C8AC
0x18002c8a5  mov     ecx, 3EACh
0x18002c8aa  jmp     short loc_18002C8B9
0x18002c8ac  cmp     ebx, 8004A025h
0x18002c8b2  jnz     short loc_18002C8CA
0x18002c8b4  mov     ecx, 3EAFh; unsigned int
0x18002c8b9  mov     rdx, rdi; HWND
0x18002c8bc  mov     r8, [rbp+57h+var_A0]; unsigned __int16 *
0x18002c8c0  xor     r9d, r9d; unsigned __int16 *
0x18002c8c3  call    ?LvReportError@@YAXHPEAUHWND__@@PEBG1@Z; LvReportError(int,HWND__ *,ushort const *,ushort const *)
0x18002c8c8  jmp     short loc_18002C8E7
0x18002c8ca  mov     r9, [rbp+57h+var_A0]; unsigned __int16 *
0x18002c8ce  mov     r8, rdi; HWND
0x18002c8d1  mov     edx, 3E8Bh; int
0x18002c8d6  mov     ecx, ebx; int
0x18002c8d8  call    ?LvReportErrorHr@@YAXJHPEAUHWND__@@PEBG@Z; LvReportErrorHr(long,int,HWND__ *,ushort const *)
0x18002c8dd  jmp     short loc_18002C8E7
0x18002c8df  mov     r15, r12
0x18002c8e2  mov     ebx, 1
0x18002c8e7  mov     rcx, r15; HICON
0x18002c8ea  call    ?EndWaitCursor@@YAXPEAUHICON__@@@Z; EndWaitCursor(HICON__ *)
0x18002c8ef  mov     rcx, [rbp+57h+var_A0]; pv
0x18002c8f3  call    cs:__imp_CoTaskMemFree
0x18002c8f9  jmp     short loc_18002C900
0x18002c8fb  mov     ebx, 80004003h
0x18002c900  mov     eax, ebx
0x18002c902  mov     rcx, [rbp+57h+var_40]
0x18002c906  xor     rcx, rsp; StackCookie
0x18002c909  call    __security_check_cookie
0x18002c90e  add     rsp, 0B0h
0x18002c915  pop     r15
0x18002c917  pop     r14
0x18002c919  pop     r12
0x18002c91b  pop     rdi
0x18002c91c  pop     rsi
0x18002c91d  pop     rbx
0x18002c91e  pop     rbp
0x18002c91f  retn
```
