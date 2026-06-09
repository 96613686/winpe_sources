# EdpAadReauthToast::GetLaunchArgs(ushort * *)

- ea: `0x180009f20`
- end: `0x18000a0a3`
- name: `?GetLaunchArgs@EdpAadReauthToast@@UEAAJPEAPEAG@Z`
- size: `387`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180007cb4`
- `0x180008278`
- `0x180009f20`
- `0x180013410`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a047`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a066`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a07d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a047`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a066`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a07d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a033`

## string_xrefs

- `0x18000a017`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::GetLaunchArgs(EdpAadReauthToast *this, unsigned __int16 **a2)
{
  const unsigned __int16 *p_Src; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int pv; // [rsp+20h] [rbp-48h]
  LPVOID pva[3]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int16 *Src; // [rsp+38h] [rbp-30h] BYREF
  int v11; // [rsp+40h] [rbp-28h]
  __int16 v12; // [rsp+44h] [rbp-24h]
  __int64 v13; // [rsp+48h] [rbp-20h]
  unsigned __int64 v14; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*((_QWORD *)this + 2) )
    return 2147549183LL;
  v14 = 7;
  Src = (unsigned __int16 *)0x75004100650052LL;
  v11 = 6815860;
  v13 = 6;
  v12 = 0;
  try
  {
    std::wstring::operator+=(&Src, L" ");
    std::wstring::operator+=(&Src, (void *)(*((_QWORD *)this + 2) + 512LL));
    std::wstring::operator+=(&Src, L" ");
    std::wstring::operator+=(&Src, *((void **)this + 2));
  }
  catch ( ... )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28D,
      (unsigned int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)0x8007000ELL,
      pv);
    if ( v14 >= 8 )
      operator delete(Src);
    return 2147942414LL;
  }
  pva[0] = 0;
  pva[1] = (LPVOID)-1LL;
  pva[2] = (LPVOID)-1LL;
  p_Src = (const unsigned __int16 *)&Src;
  if ( v14 >= 8 )
    p_Src = Src;
  v6 = CoAllocString(p_Src, (unsigned __int16 **)pva);
  v7 = v6;
  if ( v6 >= 0 )
  {
    *a2 = (unsigned __int16 *)pva[0];
    if ( v14 >= 8 )
      operator delete(Src);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x291,
      (unsigned int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)v6,
      (int)pva[0]);
    if ( pva[0] )
      CoTaskMemFree(pva[0]);
    if ( v14 >= 8 )
      operator delete(Src);
    return v7;
  }
}

```

## disassembly

```asm
0x180009f20  mov     [rsp+arg_10], rbx
0x180009f25  push    rdi
0x180009f26  sub     rsp, 60h
0x180009f2a  mov     rax, cs:__security_cookie
0x180009f31  xor     rax, rsp
0x180009f34  mov     [rsp+68h+var_10], rax
0x180009f39  mov     rdi, rdx
0x180009f3c  mov     rbx, rcx
0x180009f3f  cmp     qword ptr [rcx+10h], 0
0x180009f44  jnz     short loc_180009F50
0x180009f46  mov     eax, 8000FFFFh
0x180009f4b  jmp     loc_18000A088
0x180009f50  mov     [rsp+68h+var_18], 7
0x180009f59  mov     [rsp+68h+var_20], 0
0x180009f62  xor     eax, eax
0x180009f64  mov     word ptr [rsp+68h+Src], ax
0x180009f69  movsd   xmm0, cs:qword_180018878
0x180009f71  movsd   [rsp+68h+Src], xmm0
0x180009f77  mov     eax, cs:dword_180018880
0x180009f7d  mov     [rsp+68h+var_28], eax
0x180009f81  mov     [rsp+68h+var_20], 6
0x180009f8a  xor     eax, eax
0x180009f8c  mov     [rsp+68h+var_24], ax
0x180009f91  lea     rdx, asc_1800182A8; " "
0x180009f98  lea     rcx, [rsp+68h+Src]; Src
0x180009f9d  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009fa2  mov     rdx, [rbx+10h]
0x180009fa6  add     rdx, 200h; void *
0x180009fad  lea     rcx, [rsp+68h+Src]; Src
0x180009fb2  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009fb7  lea     rdx, asc_1800182A8; " "
0x180009fbe  lea     rcx, [rsp+68h+Src]; Src
0x180009fc3  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009fc8  mov     rdx, [rbx+10h]; void *
0x180009fcc  lea     rcx, [rsp+68h+Src]; Src
0x180009fd1  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z; std::wstring::operator+=(ushort const *)
0x180009fd6  nop
0x180009fd7  mov     [rsp+68h+pv], 0; int
0x180009fe0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009fe4  mov     [rsp+68h+var_40], rax
0x180009fe9  mov     [rsp+68h+var_38], rax
0x180009fee  lea     rcx, [rsp+68h+Src]
0x180009ff3  cmp     [rsp+68h+var_18], 8
0x180009ff9  cmovnb  rcx, [rsp+68h+Src]; unsigned __int16 *
0x180009fff  lea     rdx, [rsp+68h+pv]; unsigned __int16 **
0x18000a004  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18000a009  mov     ebx, eax
0x18000a00b  test    eax, eax
0x18000a00d  jns     short loc_18000A051
0x18000a00f  mov     rcx, [rsp+68h]; this
0x18000a014  mov     r9d, eax; char *
0x18000a017  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18000a01e  mov     edx, 291h; void *
0x18000a023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a028  nop
0x18000a029  mov     rcx, [rsp+68h+pv]; pv
0x18000a02e  test    rcx, rcx
0x18000a031  jz      short loc_18000A03A
0x18000a033  call    cs:__imp_CoTaskMemFree
0x18000a039  nop
0x18000a03a  cmp     [rsp+68h+var_18], 8
0x18000a040  jb      short loc_18000A04D
0x18000a042  mov     rcx, [rsp+68h+Src]
0x18000a047  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a04d  mov     eax, ebx
0x18000a04f  jmp     short loc_18000A088
0x18000a051  mov     rax, [rsp+68h+pv]
0x18000a056  mov     [rdi], rax
0x18000a059  cmp     [rsp+68h+var_18], 8
0x18000a05f  jb      short loc_18000A06C
0x18000a061  mov     rcx, [rsp+68h+Src]
0x18000a066  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a06c  xor     eax, eax
0x18000a06e  jmp     short loc_18000A088
0x18000a070  cmp     [rsp+68h+var_18], 8
0x18000a076  jb      short loc_18000A083
0x18000a078  mov     rcx, [rsp+68h+Src]
0x18000a07d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a083  mov     eax, 8007000Eh
0x18000a088  mov     rcx, [rsp+68h+var_10]
0x18000a08d  xor     rcx, rsp; StackCookie
0x18000a090  call    __security_check_cookie
0x18000a095  mov     rbx, [rsp+68h+arg_10]
0x18000a09d  add     rsp, 60h
0x18000a0a1  pop     rdi
0x18000a0a2  retn
```
