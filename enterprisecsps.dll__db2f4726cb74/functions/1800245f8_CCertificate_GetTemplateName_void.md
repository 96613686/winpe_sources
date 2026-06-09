# CCertificate::GetTemplateName(void)

- ea: `0x1800245f8`
- end: `0x1800247ac`
- name: `?GetTemplateName@CCertificate@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `436`
- prototype: ``
- caller_count: `14`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180017428`
- `0x1800177f4`
- `0x180017bc0`
- `0x180017f8c`
- `0x180070bb0`
- `0x180070f7c`
- `0x180071348`
- `0x180071714`
- `0x180071ae0`
- `0x180071eac`
- `0x180072278`
- `0x180072644`
- `0x180072a10`
- `0x180072ddc`

## callees

- `0x1800091b0`
- `0x180009260`
- `0x18001a014`
- `0x180023874`
- `0x180023b70`
- `0x180023fa0`
- `0x1800245f8`
- `0x180024d8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002478c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002478c`
- `CRYPT32!CertRDNValueToStrW` at `0x1800246e6`
- `CRYPT32!CertRDNValueToStrW` at `0x18002475a`
- `CRYPT32!CertRDNValueToStrW` at `0x1800246e6`
- `CRYPT32!CertRDNValueToStrW` at `0x18002475a`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800246a4`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800246a4`
- `CRYPT32!CertFindExtension` at `0x180024644`
- `CRYPT32!CertFindExtension` at `0x180024644`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCertificate::GetTemplateName(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  PCERT_EXTENSION Extension; // rax
  const char *v5; // r9
  DWORD v6; // esi
  unsigned __int64 v7; // rax
  void *v8; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  DWORD pcbStructInfo; // [rsp+90h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp+30h] BYREF
  void *Block; // [rsp+A8h] [rbp+38h]

  v3 = a1 + 224;
  if ( *(_QWORD *)(a1 + 240) )
  {
    std::wstring::wstring(a2, a1 + 224);
  }
  else
  {
    Extension = CertFindExtension(
                  "1.3.6.1.4.1.311.20.2",
                  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 24LL) + 192LL),
                  *(CERT_EXTENSION **)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 24LL) + 200LL));
    if ( Extension )
    {
      hMem = 0;
      pcbStructInfo = 0;
      if ( !CryptDecodeObjectEx(
              1u,
              (LPCSTR)0x18,
              Extension->Value.pbData,
              Extension->Value.cbData,
              0x8000u,
              0,
              &hMem,
              &pcbStructInfo) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xCF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
          v5);
      v6 = CertRDNValueToStrW(*(_DWORD *)hMem, (PCERT_RDN_VALUE_BLOB)((char *)hMem + 8), 0, 0) + 1;
      v7 = 2LL * v6;
      if ( !is_mul_ok(v6, 2u) )
        v7 = -1;
      v8 = operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
      Block = v8;
      if ( !v8 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDA,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\certificatecore\\certificate.cpp",
          (const char *)0x8007000ELL,
          dwFlags);
      CertRDNValueToStrW(*(_DWORD *)hMem, (PCERT_RDN_VALUE_BLOB)((char *)hMem + 8), (LPWSTR)v8, v6);
      std::wstring::operator=(v3, Block);
      std::wstring::wstring(a2, v3);
      operator delete(Block);
      LocalFree(hMem);
    }
    else
    {
      std::wstring::wstring(a2);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800245f8  mov     [rsp-18h+arg_8], rbx
0x1800245fd  push    rbp
0x1800245fe  push    rsi
0x1800245ff  push    rdi
0x180024600  mov     rbp, rsp
0x180024603  sub     rsp, 70h
0x180024607  mov     rbx, rdx
0x18002460a  lea     rdi, [rcx+0E0h]
0x180024611  cmp     qword ptr [rdi+10h], 0
0x180024616  jbe     short loc_180024628
0x180024618  mov     rdx, rdi
0x18002461b  mov     rcx, rbx
0x18002461e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024623  jmp     loc_180024798
0x180024628  mov     rax, [rcx+58h]
0x18002462c  mov     rdx, [rax+18h]
0x180024630  mov     r8, [rdx+0C8h]; rgExtensions
0x180024637  mov     edx, [rdx+0C0h]; cExtensions
0x18002463d  lea     rcx, pszObjId; "1.3.6.1.4.1.311.20.2"
0x180024644  call    cs:__imp_CertFindExtension
0x18002464b  nop     dword ptr [rax+rax+00h]
0x180024650  test    rax, rax
0x180024653  jnz     short loc_180024662
0x180024655  mov     rcx, rbx
0x180024658  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002465d  jmp     loc_180024798
0x180024662  mov     [rbp+hMem], 0
0x18002466a  mov     [rbp+arg_0], 0
0x180024671  lea     rcx, [rbp+arg_0]
0x180024675  mov     [rsp+70h+pcbStructInfo], rcx; pcbStructInfo
0x18002467a  lea     rcx, [rbp+hMem]
0x18002467e  mov     [rsp+70h+pvStructInfo], rcx; pvStructInfo
0x180024683  mov     [rsp+70h+pDecodePara], 0; pDecodePara
0x18002468c  mov     [rsp+70h+dwFlags], 8000h; int
0x180024694  mov     r9d, [rax+10h]; cbEncoded
0x180024698  mov     r8, [rax+18h]; pbEncoded
0x18002469c  mov     edx, 18h; lpszStructType
0x1800246a1  lea     ecx, [rdx-17h]; dwCertEncodingType
0x1800246a4  call    cs:__imp_CryptDecodeObjectEx
0x1800246ab  nop     dword ptr [rax+rax+00h]
0x1800246b0  mov     rcx, [rbp+18h]; this
0x1800246b4  test    eax, eax
0x1800246b6  jnz     short loc_1800246CA
0x1800246b8  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x1800246bf  mov     edx, 0CFh; void *
0x1800246c4  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800246ca  lea     rax, [rbp+hMem]
0x1800246ce  mov     [rbp+var_28], rax
0x1800246d2  mov     [rbp+var_20], 1
0x1800246d6  mov     rcx, [rbp+hMem]
0x1800246da  lea     rdx, [rcx+8]; pValue
0x1800246de  xor     r9d, r9d; csz
0x1800246e1  xor     r8d, r8d; psz
0x1800246e4  mov     ecx, [rcx]; dwValueType
0x1800246e6  call    cs:__imp_CertRDNValueToStrW
0x1800246ed  nop     dword ptr [rax+rax+00h]
0x1800246f2  lea     esi, [rax+1]
0x1800246f5  mov     ecx, esi
0x1800246f7  mov     eax, 2
0x1800246fc  mul     rcx
0x1800246ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024706  cmovb   rax, rcx
0x18002470a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024711  mov     rcx, rax; unsigned __int64
0x180024714  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180024719  mov     [rbp+Block], rax
0x18002471d  mov     rcx, [rbp+18h]; this
0x180024721  test    rax, rax
0x180024724  jnz     short loc_18002473E
0x180024726  mov     r9d, 8007000Eh; char *
0x18002472c  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x180024733  mov     edx, 0DAh; void *
0x180024738  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002473e  lea     rcx, [rbp+Block]
0x180024742  mov     [rbp+var_18], rcx
0x180024746  mov     [rbp+var_10], 1
0x18002474a  mov     rcx, [rbp+hMem]
0x18002474e  lea     rdx, [rcx+8]; pValue
0x180024752  mov     r9d, esi; csz
0x180024755  mov     r8, rax; psz
0x180024758  mov     ecx, [rcx]; dwValueType
0x18002475a  call    cs:__imp_CertRDNValueToStrW
0x180024761  nop     dword ptr [rax+rax+00h]
0x180024766  mov     rdx, [rbp+Block]
0x18002476a  mov     rcx, rdi
0x18002476d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180024772  mov     rdx, rdi
0x180024775  mov     rcx, rbx
0x180024778  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002477d  nop
0x18002477e  mov     rcx, [rbp+Block]; Block
0x180024782  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024787  nop
0x180024788  mov     rcx, [rbp+hMem]; hMem
0x18002478c  call    cs:__imp_LocalFree
0x180024793  nop     dword ptr [rax+rax+00h]
0x180024798  mov     rax, rbx
0x18002479b  mov     rbx, [rsp+70h+arg_8]
0x1800247a3  add     rsp, 70h
0x1800247a7  pop     rdi
0x1800247a8  pop     rsi
0x1800247a9  pop     rbp
0x1800247aa  retn
```
