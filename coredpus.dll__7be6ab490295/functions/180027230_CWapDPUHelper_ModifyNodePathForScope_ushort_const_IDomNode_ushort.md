# CWapDPUHelper::ModifyNodePathForScope(ushort const *,IDomNode *,ushort * *)

- ea: `0x180027230`
- end: `0x180027547`
- name: `?ModifyNodePathForScope@CWapDPUHelper@@AEAAJPEBGPEAUIDomNode@@PEAPEAG@Z`
- size: `791`
- prototype: `int(CWapDPUHelper *__hidden this, const unsigned __int16 *, struct IDomNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800278c0`

## callees

- `0x1800110bc`
- `0x180015b3c`
- `0x180023b0c`
- `0x180024308`
- `0x180027230`
- `0x18002e4d4`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027302`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002732c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180027302`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002732c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027434`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002752c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180027434`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18002752c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180027470`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002749a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800274c1`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180027470`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x18002749a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x1800274c1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800274ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800274ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800274ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1800274ff`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWapDPUHelper::ModifyNodePathForScope(
        CWapDPUHelper *this,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int16 **a4)
{
  struct IUnknown *v6; // rbx
  struct IUnknown *v7; // rax
  int v8; // r14d
  int v9; // r15d
  struct IUnknown *v10; // rdi
  int v11; // edi
  int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rsi
  __int64 v22; // r9
  const wchar_t *v23; // r8
  __int64 v24; // r9
  const unsigned __int16 *v25; // r8
  int v26; // eax
  struct IUnknown *v28; // [rsp+20h] [rbp-10h] BYREF
  wchar_t *String2; // [rsp+28h] [rbp-8h] BYREF
  struct IUnknown *v30; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+50h] BYREF

  bstrString = 0;
  String2 = 0;
  v6 = 0;
  v28 = 0;
  v30 = 0;
  if ( a3 && (ATL::AtlComPtrAssign(&v30, a3), (v7 = v30) != 0) )
  {
    v8 = 0;
    v9 = 0;
    v10 = 0;
    while ( 1 )
    {
      if ( v10 != v7 )
      {
        ATL::AtlComPtrAssign(&v28, v7);
        v6 = v28;
        v7 = v30;
      }
      v11 = ((__int64 (__fastcall *)(struct IUnknown *, wchar_t **))v7->lpVtbl[1].Release)(v7, &String2);
      if ( v11 < 0 )
        break;
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, const wchar_t *, BSTR *))v30->lpVtbl[3].Release)(
              v30,
              L"scope",
              &bstrString);
      v11 = v12;
      if ( v12 >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(bstrString, L"device") )
        {
          if ( !(unsigned int)_o__wcsicmp(bstrString, L"user") )
          {
            if ( v9 )
            {
LABEL_22:
              v11 = -2147024809;
              break;
            }
            v8 = 1;
          }
        }
        else
        {
          if ( v8 )
            goto LABEL_22;
          v9 = 1;
        }
      }
      else if ( v12 != -2147023728 )
      {
        break;
      }
      ATL::CComPtrBase<IDomNode>::Release(&v30);
      v10 = v6;
      ((void (__fastcall *)(struct IUnknown *, struct IUnknown **))v6->lpVtbl[6].QueryInterface)(v6, &v30);
      if ( wcscmp_0(L"wap-provisioningdoc", String2) )
      {
        v7 = v30;
        if ( v30 )
          continue;
      }
      v13 = -1;
      if ( v8 )
      {
        v14 = -1;
        do
          ++v14;
        while ( asc_180034A00[v14] );
        v15 = v14 + 4;
      }
      else
      {
        v15 = 0;
        if ( v9 )
        {
          v16 = -1;
          do
            ++v16;
          while ( asc_180034A00[v16] );
          v15 = v16 + 6;
        }
      }
      v17 = -1;
      do
        ++v17;
      while ( a2[v17] );
      v18 = v17 + v15 + 1;
      v19 = 2 * v18;
      if ( !is_mul_ok(v18, 2u) )
        v19 = -1;
      v20 = (unsigned __int16 *)operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
      v21 = v20;
      if ( !v20 )
      {
        v11 = -2147024882;
        break;
      }
      if ( (v8 || v9) && v18 >= 3 )
      {
        if ( (unsigned int)_o_wcscpy_s(v20, 3, L"./") )
          goto LABEL_48;
        if ( v8 )
        {
          v22 = 4;
          v23 = L"user";
        }
        else
        {
          v22 = 6;
          v23 = L"device";
        }
        if ( (unsigned int)_o_wcsncat_s(v21, v18, v23, v22) )
          goto LABEL_48;
        v24 = -1;
        do
          ++v24;
        while ( asc_180034A00[v24] );
        if ( (unsigned int)_o_wcsncat_s(v21, v18, L"/", v24) )
          goto LABEL_48;
        v25 = a2 + 2;
        do
          ++v13;
        while ( v25[v13] );
        v26 = _o_wcsncat_s(v21, v18, v25, v13);
      }
      else
      {
        v26 = _o_wcscpy_s(v20, v18, a2);
      }
      if ( v26 )
        goto LABEL_48;
      v11 = 0;
      *a4 = v21;
      break;
    }
  }
  else
  {
LABEL_48:
    v11 = -2147467259;
  }
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v30);
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)&v28);
  SysFreeString(String2);
  SysFreeString(bstrString);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180027230  mov     [rsp-38h+arg_8], rbx
0x180027235  mov     [rsp-38h+arg_0], rcx
0x18002723a  push    rbp
0x18002723b  push    rsi
0x18002723c  push    rdi
0x18002723d  push    r12
0x18002723f  push    r13
0x180027241  push    r14
0x180027243  push    r15
0x180027245  mov     rbp, rsp
0x180027248  sub     rsp, 30h
0x18002724c  mov     r12, r9
0x18002724f  mov     r13, rdx
0x180027252  xor     esi, esi
0x180027254  mov     [rbp+bstrString], rsi
0x180027258  mov     [rbp+String2], rsi
0x18002725c  mov     ebx, esi
0x18002725e  mov     [rbp+var_10], rbx
0x180027262  mov     [rbp+arg_0], rsi
0x180027266  test    r8, r8
0x180027269  jz      loc_1800274D1
0x18002726f  mov     rdx, r8; struct IUnknown *
0x180027272  lea     rcx, [rbp+arg_0]; struct IUnknown **
0x180027276  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18002727b  mov     rax, [rbp+arg_0]
0x18002727f  test    rax, rax
0x180027282  jz      loc_1800274D1
0x180027288  mov     r14d, esi
0x18002728b  mov     r15d, esi
0x18002728e  mov     edi, esi
0x180027290  cmp     rdi, rax
0x180027293  jz      short loc_1800272A9
0x180027295  mov     rdx, rax; struct IUnknown *
0x180027298  lea     rcx, [rbp+var_10]; struct IUnknown **
0x18002729c  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800272a1  mov     rbx, [rbp+var_10]
0x1800272a5  mov     rax, [rbp+arg_0]
0x1800272a9  mov     rcx, [rax]
0x1800272ac  mov     r8, [rcx+28h]
0x1800272b0  lea     rdx, [rbp+String2]
0x1800272b4  mov     rcx, rax
0x1800272b7  mov     rax, r8
0x1800272ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272bf  mov     edi, eax
0x1800272c1  test    eax, eax
0x1800272c3  js      loc_1800274D6
0x1800272c9  mov     rcx, [rbp+arg_0]
0x1800272cd  mov     rax, [rcx]
0x1800272d0  lea     r8, [rbp+bstrString]
0x1800272d4  lea     rdx, aScope; "scope"
0x1800272db  mov     rax, [rax+58h]
0x1800272df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272e4  mov     edi, eax
0x1800272e6  test    eax, eax
0x1800272e8  jns     short loc_1800272F7
0x1800272ea  cmp     eax, 80070490h
0x1800272ef  jnz     loc_1800274D6
0x1800272f5  jmp     short loc_180027345
0x1800272f7  lea     rdx, aDevice; "device"
0x1800272fe  mov     rcx, [rbp+bstrString]
0x180027302  call    cs:__imp__o__wcsicmp
0x180027309  nop     dword ptr [rax+rax+00h]
0x18002730e  test    eax, eax
0x180027310  jnz     short loc_180027321
0x180027312  test    r14d, r14d
0x180027315  jnz     loc_1800273AA
0x18002731b  lea     r15d, [rax+1]
0x18002731f  jmp     short loc_180027345
0x180027321  lea     rdx, aUser; "user"
0x180027328  mov     rcx, [rbp+bstrString]
0x18002732c  call    cs:__imp__o__wcsicmp
0x180027333  nop     dword ptr [rax+rax+00h]
0x180027338  test    eax, eax
0x18002733a  jnz     short loc_180027345
0x18002733c  test    r15d, r15d
0x18002733f  jnz     short loc_1800273AA
0x180027341  lea     r14d, [rax+1]
0x180027345  lea     rcx, [rbp+arg_0]
0x180027349  call    ?Release@?$CComPtrBase@UIDomNode@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDomNode>::Release(void)
0x18002734e  mov     rdi, rbx
0x180027351  mov     rax, [rbx]
0x180027354  lea     rdx, [rbp+arg_0]
0x180027358  mov     rcx, rbx
0x18002735b  mov     rax, [rax+90h]
0x180027362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027367  mov     rdx, [rbp+String2]; String2
0x18002736b  lea     rcx, aWapProvisionin_0; "wap-provisioningdoc"
0x180027372  call    wcscmp_0
0x180027377  test    eax, eax
0x180027379  jz      short loc_180027388
0x18002737b  mov     rax, [rbp+arg_0]
0x18002737f  test    rax, rax
0x180027382  jnz     loc_180027290
0x180027388  lea     rdx, asc_180034A00; "/"
0x18002738f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180027393  test    r14d, r14d
0x180027396  jz      short loc_1800273B4
0x180027398  mov     rax, rbx
0x18002739b  inc     rax
0x18002739e  cmp     [rdx+rax*2], si
0x1800273a2  jnz     short loc_18002739B
0x1800273a4  lea     rcx, [rax+4]
0x1800273a8  jmp     short loc_1800273CC
0x1800273aa  mov     edi, 80070057h
0x1800273af  jmp     loc_1800274D6
0x1800273b4  mov     rcx, rsi
0x1800273b7  test    r15d, r15d
0x1800273ba  jz      short loc_1800273CC
0x1800273bc  mov     rax, rbx
0x1800273bf  inc     rax
0x1800273c2  cmp     [rdx+rax*2], si
0x1800273c6  jnz     short loc_1800273BF
0x1800273c8  lea     rcx, [rax+6]
0x1800273cc  mov     rax, rbx
0x1800273cf  inc     rax
0x1800273d2  cmp     [r13+rax*2+0], si
0x1800273d8  jnz     short loc_1800273CF
0x1800273da  lea     rdi, [rcx+1]
0x1800273de  add     rdi, rax
0x1800273e1  mov     eax, 2
0x1800273e6  mul     rdi
0x1800273e9  cmovb   rax, rbx
0x1800273ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800273f4  mov     rcx, rax; unsigned __int64
0x1800273f7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800273fc  mov     rsi, rax
0x1800273ff  test    rax, rax
0x180027402  jnz     short loc_18002740E
0x180027404  mov     edi, 8007000Eh
0x180027409  jmp     loc_1800274D6
0x18002740e  test    r14d, r14d
0x180027411  jnz     short loc_18002741C
0x180027413  test    r15d, r15d
0x180027416  jz      loc_180027523
0x18002741c  mov     edx, 3
0x180027421  cmp     rdi, rdx
0x180027424  jb      loc_180027523
0x18002742a  lea     r8, asc_1800349F8; "./"
0x180027431  mov     rcx, rsi
0x180027434  call    cs:__imp__o_wcscpy_s
0x18002743b  nop     dword ptr [rax+rax+00h]
0x180027440  xor     r15d, r15d
0x180027443  test    eax, eax
0x180027445  jnz     loc_1800274D1
0x18002744b  mov     rdx, rdi
0x18002744e  mov     rcx, rsi
0x180027451  test    r14d, r14d
0x180027454  jz      short loc_180027463
0x180027456  lea     r9d, [r15+4]
0x18002745a  lea     r8, aUser; "user"
0x180027461  jmp     short loc_180027470
0x180027463  mov     r9d, 6
0x180027469  lea     r8, aDevice; "device"
0x180027470  call    cs:__imp__o_wcsncat_s
0x180027477  nop     dword ptr [rax+rax+00h]
0x18002747c  test    eax, eax
0x18002747e  jnz     short loc_1800274D1
0x180027480  mov     r9, rbx
0x180027483  lea     r8, asc_180034A00; "/"
0x18002748a  inc     r9
0x18002748d  cmp     [r8+r9*2], r15w
0x180027492  jnz     short loc_18002748A
0x180027494  mov     rdx, rdi
0x180027497  mov     rcx, rsi
0x18002749a  call    cs:__imp__o_wcsncat_s
0x1800274a1  nop     dword ptr [rax+rax+00h]
0x1800274a6  test    eax, eax
0x1800274a8  jnz     short loc_1800274D1
0x1800274aa  lea     r8, [r13+4]
0x1800274ae  inc     rbx
0x1800274b1  cmp     [r8+rbx*2], r15w
0x1800274b6  jnz     short loc_1800274AE
0x1800274b8  mov     r9, rbx
0x1800274bb  mov     rdx, rdi
0x1800274be  mov     rcx, rsi
0x1800274c1  call    cs:__imp__o_wcsncat_s
0x1800274c8  nop     dword ptr [rax+rax+00h]
0x1800274cd  test    eax, eax
0x1800274cf  jz      short loc_18002753D
0x1800274d1  mov     edi, 80004005h
0x1800274d6  lea     rcx, [rbp+arg_0]
0x1800274da  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800274df  nop
0x1800274e0  lea     rcx, [rbp+var_10]
0x1800274e4  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800274e9  nop
0x1800274ea  mov     rcx, [rbp+String2]; bstrString
0x1800274ee  call    cs:__imp_SysFreeString
0x1800274f5  nop     dword ptr [rax+rax+00h]
0x1800274fa  nop
0x1800274fb  mov     rcx, [rbp+bstrString]; bstrString
0x1800274ff  call    cs:__imp_SysFreeString
0x180027506  nop     dword ptr [rax+rax+00h]
0x18002750b  mov     eax, edi
0x18002750d  mov     rbx, [rsp+30h+arg_8]
0x180027512  add     rsp, 30h
0x180027516  pop     r15
0x180027518  pop     r14
0x18002751a  pop     r13
0x18002751c  pop     r12
0x18002751e  pop     rdi
0x18002751f  pop     rsi
0x180027520  pop     rbp
0x180027521  retn
0x180027523  mov     r8, r13
0x180027526  mov     rdx, rdi
0x180027529  mov     rcx, rsi
0x18002752c  call    cs:__imp__o_wcscpy_s
0x180027533  nop     dword ptr [rax+rax+00h]
0x180027538  xor     r15d, r15d
0x18002753b  jmp     short loc_1800274CD
0x18002753d  mov     edi, r15d
0x180027540  mov     [r12], rsi
0x180027544  jmp     short loc_1800274D6
```
