# CCorSvcMgr::GetRuntimeForConfiguration(Configuration *)

- ea: `0x180024700`
- end: `0x1800249a3`
- name: `?GetRuntimeForConfiguration@CCorSvcMgr@@AEAAXPEAVConfiguration@@@Z`
- size: `675`
- prototype: `void __fastcall(CCorSvcMgr *__hidden this, struct Configuration *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180006488`
- `0x180009f70`
- `0x18000d138`
- `0x180024700`
- `0x180028bdc`
- `0x18002c874`
- `0x180030d84`
- `0x180032654`
- `0x180034fd4`
- `0x18003dc30`

## import_xrefs

- `ucrtbase_clr0400!_wcsnicmp` at `0x18002488d`
- `ucrtbase_clr0400!_wcsnicmp` at `0x18002488d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247f5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247ad`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247cf`
- `OLEAUT32!__imp_SysAllocString` at `0x1800247f5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180024906`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800248f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180024906`

## string_xrefs

- `0x18002496f`: `Assembly %s requires runtime %s which is not supported by side-by-side NGen\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
void __fastcall CCorSvcMgr::GetRuntimeForConfiguration(CCorSvcMgr *this, struct Configuration *a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  const OLECHAR *v6; // r12
  BOOL v7; // ebx
  unsigned __int16 *v8; // r14
  BOOL v9; // r15d
  const OLECHAR **v10; // rdi
  const OLECHAR *v11; // rcx
  unsigned __int16 *v12; // rdi
  int v13; // eax
  const unsigned __int16 *Path; // rax
  wchar_t *String1; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h]
  int v17; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v18; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v20; // [rsp+58h] [rbp-A8h]
  BOOL v21; // [rsp+60h] [rbp-A0h]
  wchar_t **p_String1; // [rsp+68h] [rbp-98h]
  Image v23[16]; // [rsp+70h] [rbp-90h] BYREF
  __int16 *v24; // [rsp+80h] [rbp-80h]
  __int16 v25; // [rsp+88h] [rbp-78h] BYREF

  v17 = 0;
  v4 = *((_QWORD *)a2 + 1);
  v5 = *(_QWORD *)(v4 + 24);
  if ( v5 )
  {
    SString::ConvertToUnicode(*(SString **)(v4 + 24));
    v6 = *(const OLECHAR **)(v5 + 16);
  }
  else
  {
    v6 = 0;
  }
  v18 = 0;
  v7 = 0;
  v19 = 0;
  v8 = 0;
  v20 = 0;
  v9 = 0;
  v21 = 0;
  v10 = (const OLECHAR **)*((_QWORD *)a2 + 71);
  if ( v10 )
  {
    SString::ConvertToUnicode(*((SString **)a2 + 71));
    if ( (unsigned int)IsExe(v10[2]) )
    {
      SString::ConvertToUnicode((SString *)v10);
      v11 = v10[2];
    }
    else
    {
      SString::ConvertToUnicode((SString *)v10);
      v8 = SysAllocString(v10[2]);
      v20 = v8;
      v9 = v8 != 0;
      v21 = v9;
      v11 = v6;
    }
    v12 = SysAllocString(v11);
    v18 = v12;
    if ( v12 )
    {
      v7 = 1;
      v19 = 1;
    }
  }
  else
  {
    v12 = SysAllocString(v6);
    v18 = v12;
    v7 = v12 != 0;
    v19 = v7;
  }
  v16 = 0;
  p_String1 = &String1;
  String1 = 0;
  v17 = 1;
  CCorSvcMgr::GetRuntimeForAssembly(this, v12, v8, &String1, a2);
  v17 = 0;
  v13 = v16;
  if ( String1 )
    v13 = 1;
  v16 = v13;
  if ( *((_BYTE *)a2 + 640) || *((_DWORD *)a2 + 162) )
  {
    if ( v16 )
    {
      SysFreeString(String1);
      v16 = 0;
    }
    if ( v9 )
    {
      SysFreeString(v8);
      v21 = 0;
    }
  }
  else
  {
    if ( !_wcsnicmp(String1, L"v1.", 3u) )
    {
      *(_QWORD *)&v23[4] = 512;
      v24 = &v25;
      *(_DWORD *)v23 = 2;
      v25 = 0;
      SString::Printf(
        (SString *)v23,
        L"Assembly %s requires runtime %s which is not supported by side-by-side NGen\n",
        v12,
        String1);
      Path = Image::GetPath(v23);
      CCorSvcMgr::Log(this, Path, 2);
      ThrowHR(-2146230525);
    }
    Configuration::SetRuntimeVersion(a2, String1);
    if ( v16 )
    {
      SysFreeString(String1);
      v16 = 0;
    }
    if ( v9 )
    {
      SysFreeString(v8);
      v21 = 0;
    }
  }
  if ( v7 )
  {
    SysFreeString(v12);
    v19 = 0;
  }
}

```

## disassembly

```asm
0x180024700  mov     [rsp-8+arg_10], rbx
0x180024705  push    rbp
0x180024706  push    rsi
0x180024707  push    rdi
0x180024708  push    r12
0x18002470a  push    r13
0x18002470c  push    r14
0x18002470e  push    r15
0x180024710  lea     rbp, [rsp-1A0h]
0x180024718  sub     rsp, 2A0h
0x18002471f  mov     rax, cs:__security_cookie
0x180024726  xor     rax, rsp
0x180024729  mov     [rbp+1D0h+var_40], rax
0x180024730  mov     rsi, rdx
0x180024733  mov     r13, rcx
0x180024736  and     [rsp+2D0h+var_290], 0
0x18002473b  mov     rax, [rdx+8]
0x18002473f  mov     rbx, [rax+18h]
0x180024743  test    rbx, rbx
0x180024746  jnz     short loc_18002474D
0x180024748  xor     r12d, r12d
0x18002474b  jmp     short loc_180024759
0x18002474d  mov     rcx, rbx; this
0x180024750  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180024755  mov     r12, [rbx+10h]
0x180024759  and     [rsp+2D0h+var_288], 0
0x18002475f  xor     ebx, ebx
0x180024761  mov     [rsp+2D0h+var_280], ebx
0x180024765  xor     r14d, r14d
0x180024768  mov     [rsp+2D0h+var_278], r14
0x18002476d  xor     r15d, r15d
0x180024770  mov     [rsp+2D0h+var_270], r15d
0x180024775  mov     rdi, [rsi+238h]
0x18002477c  test    rdi, rdi
0x18002477f  jz      short loc_1800247F2
0x180024781  mov     rcx, rdi; this
0x180024784  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180024789  mov     rcx, [rdi+10h]; unsigned __int16 *
0x18002478d  call    ?IsExe@@YAHPEBG@Z; IsExe(ushort const *)
0x180024792  mov     rcx, rdi; this
0x180024795  test    eax, eax
0x180024797  jz      short loc_1800247A4
0x180024799  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18002479e  mov     rcx, [rdi+10h]
0x1800247a2  jmp     short loc_1800247CF
0x1800247a4  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800247a9  mov     rcx, [rdi+10h]; psz
0x1800247ad  call    cs:__imp_SysAllocString
0x1800247b3  mov     r14, rax
0x1800247b6  mov     [rsp+2D0h+var_278], rax
0x1800247bb  test    rax, rax
0x1800247be  mov     eax, 1
0x1800247c3  cmovnz  r15d, eax
0x1800247c7  mov     [rsp+2D0h+var_270], r15d
0x1800247cc  mov     rcx, r12; psz
0x1800247cf  call    cs:__imp_SysAllocString
0x1800247d5  mov     rdi, rax
0x1800247d8  mov     [rsp+2D0h+var_288], rax
0x1800247dd  xor     r12d, r12d
0x1800247e0  test    rax, rax
0x1800247e3  jz      short loc_180024815
0x1800247e5  lea     eax, [r12+1]
0x1800247ea  mov     ebx, eax
0x1800247ec  mov     [rsp+2D0h+var_280], eax
0x1800247f0  jmp     short loc_180024815
0x1800247f2  mov     rcx, r12; psz
0x1800247f5  call    cs:__imp_SysAllocString
0x1800247fb  mov     rdi, rax
0x1800247fe  mov     [rsp+2D0h+var_288], rax
0x180024803  xor     r12d, r12d
0x180024806  test    rax, rax
0x180024809  lea     eax, [r12+1]
0x18002480e  cmovnz  ebx, eax
0x180024811  mov     [rsp+2D0h+var_280], ebx
0x180024815  mov     [rsp+2D0h+String1], r12
0x18002481a  mov     [rsp+2D0h+var_298], r12d
0x18002481f  lea     rax, [rsp+2D0h+String1]
0x180024824  mov     [rsp+2D0h+var_268], rax
0x180024829  mov     [rsp+2D0h+String1], r12
0x18002482e  mov     eax, 1
0x180024833  mov     [rsp+2D0h+var_290], eax
0x180024837  mov     [rsp+2D0h+var_2B0], rsi; struct Configuration *
0x18002483c  lea     r9, [rsp+2D0h+String1]; unsigned __int16 **
0x180024841  mov     r8, r14; unsigned __int16 *
0x180024844  mov     rdx, rdi; unsigned __int16 *
0x180024847  mov     rcx, r13; this
0x18002484a  call    ?GetRuntimeForAssembly@CCorSvcMgr@@AEAAXPEAG0PEAPEAGPEAVConfiguration@@@Z; CCorSvcMgr::GetRuntimeForAssembly(ushort *,ushort *,ushort * *,Configuration *)
0x18002484f  mov     edx, 1
0x180024854  mov     eax, edx
0x180024856  and     eax, 0FFFFFFFEh
0x180024859  mov     [rsp+2D0h+var_290], eax
0x18002485d  mov     eax, [rsp+2D0h+var_298]
0x180024861  mov     rcx, [rsp+2D0h+String1]; String1
0x180024866  test    rcx, rcx
0x180024869  cmovnz  eax, edx
0x18002486c  mov     [rsp+2D0h+var_298], eax
0x180024870  cmp     [rsi+280h], r12b
0x180024877  jnz     short loc_1800248D5
0x180024879  cmp     [rsi+288h], r12d
0x180024880  jnz     short loc_1800248D5
0x180024882  lea     r8d, [rdx+2]; MaxCount
0x180024886  lea     rdx, aV1; "v1."
0x18002488d  call    cs:__imp__wcsnicmp
0x180024893  test    eax, eax
0x180024895  jz      loc_18002493B
0x18002489b  mov     rdx, [rsp+2D0h+String1]; unsigned __int16 *
0x1800248a0  mov     rcx, rsi; this
0x1800248a3  call    ?SetRuntimeVersion@Configuration@@QEAAXPEBG@Z; Configuration::SetRuntimeVersion(ushort const *)
0x1800248a8  nop
0x1800248a9  cmp     [rsp+2D0h+var_298], r12d
0x1800248ae  jz      short loc_1800248C0
0x1800248b0  mov     rcx, [rsp+2D0h+String1]; bstrString
0x1800248b5  call    cs:__imp_SysFreeString
0x1800248bb  mov     [rsp+2D0h+var_298], r12d
0x1800248c0  test    r15d, r15d
0x1800248c3  jz      short loc_1800248D3
0x1800248c5  mov     rcx, r14; bstrString
0x1800248c8  call    cs:__imp_SysFreeString
0x1800248ce  mov     [rsp+2D0h+var_270], r12d
0x1800248d3  jmp     short loc_1800248FF
0x1800248d5  cmp     [rsp+2D0h+var_298], r12d
0x1800248da  jz      short loc_1800248EC
0x1800248dc  mov     rcx, [rsp+2D0h+String1]; bstrString
0x1800248e1  call    cs:__imp_SysFreeString
0x1800248e7  mov     [rsp+2D0h+var_298], r12d
0x1800248ec  test    r15d, r15d
0x1800248ef  jz      short loc_1800248FF
0x1800248f1  mov     rcx, r14; bstrString
0x1800248f4  call    cs:__imp_SysFreeString
0x1800248fa  mov     [rsp+2D0h+var_270], r12d
0x1800248ff  test    ebx, ebx
0x180024901  jz      short loc_180024911
0x180024903  mov     rcx, rdi; bstrString
0x180024906  call    cs:__imp_SysFreeString
0x18002490c  mov     [rsp+2D0h+var_280], r12d
0x180024911  mov     rcx, [rbp+1D0h+var_40]
0x180024918  xor     rcx, rsp; StackCookie
0x18002491b  call    __security_check_cookie
0x180024920  mov     rbx, [rsp+2D0h+arg_10]
0x180024928  add     rsp, 2A0h
0x18002492f  pop     r15
0x180024931  pop     r14
0x180024933  pop     r13
0x180024935  pop     r12
0x180024937  pop     rdi
0x180024938  pop     rsi
0x180024939  pop     rbp
0x18002493a  retn
0x18002493b  and     qword ptr [rsp+2D0h+var_260], 0
0x180024941  mov     qword ptr [rsp+2D0h+var_260+4], 200h
0x18002494a  mov     [rbp+1D0h+var_250], r12
0x18002494e  lea     rax, [rbp+1D0h+var_248]
0x180024952  mov     [rbp+1D0h+var_250], rax
0x180024956  mov     ebx, 2
0x18002495b  mov     dword ptr [rsp+2D0h+var_260], ebx
0x18002495f  mov     rax, [rbp+1D0h+var_250]
0x180024963  mov     [rax], r12w
0x180024967  mov     r9, [rsp+2D0h+String1]
0x18002496c  mov     r8, rdi
0x18002496f  lea     rdx, aAssemblySRequi_0; "Assembly %s requires runtime %s which i"...
0x180024976  lea     rcx, [rsp+2D0h+var_260]; this
0x18002497b  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180024980  lea     rcx, [rsp+2D0h+var_260]; this
0x180024985  call    ?GetPath@Image@@QEAAPEBGXZ; Image::GetPath(void)
0x18002498a  mov     rdx, rax
0x18002498d  mov     r8d, ebx
0x180024990  mov     rcx, r13
0x180024993  call    ?Log@CCorSvcMgr@@AEAAXPEBGW4CorSvcLogLevel@@@Z; CCorSvcMgr::Log(ushort const *,CorSvcLogLevel)
0x180024998  mov     ecx, 80131F03h; int
0x18002499d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
