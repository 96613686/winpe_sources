# CertificateStoreNodeHelper::GetVariantBinaryFromWString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,tagVARIANT *)

- ea: `0x18001da10`
- end: `0x18001db71`
- name: `?GetVariantBinaryFromWString@CertificateStoreNodeHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUtagVARIANT@@@Z`
- size: `353`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: `broker_com_uri`

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

- `0x180009cac`
- `0x18000d4d4`
- `0x18001da10`
- `0x18002031c`
- `0x1800f7280`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001db4e`
- `OLEAUT32!__imp_VariantInit` at `0x18001db4e`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001da80`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18001da80`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001db1f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18001db1f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001daa2`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001daa2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001dad6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001db10`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001dad6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001db10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001daf5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001daf5`
- `DMCmnUtils!DecodeBase64W` at `0x18001da55`
- `DMCmnUtils!DecodeBase64W` at `0x18001da55`

## pseudocode

```c
__int64 __fastcall CertificateStoreNodeHelper::GetVariantBinaryFromWString(__int64 a1, VARIANTARG *a2)
{
  SAFEARRAY *v3; // r14
  const unsigned __int16 *v4; // rax
  SAFEARRAY *v5; // rdi
  HRESULT v6; // ebx
  SAFEARRAY *v7; // rax
  void *v8; // rcx
  __int64 result; // rax
  void *Src; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  size_t Size; // [rsp+60h] [rbp+30h] BYREF
  void *ppvData; // [rsp+70h] [rbp+40h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+78h] [rbp+48h] BYREF

  v3 = 0;
  v4 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  v5 = 0;
  Src = 0;
  ppvData = 0;
  LODWORD(Size) = 0;
  rgsabound = 0;
  if ( v4 )
  {
    v6 = DecodeBase64W(v4, (unsigned __int8 **)&Src, (int *)&Size);
    if ( v6 >= 0 )
    {
      rgsabound.lLbound = 0;
      rgsabound.cElements = Size;
      v7 = SafeArrayCreate(0x11u, 1u, &rgsabound);
      v5 = v7;
      if ( v7 )
      {
        v6 = SafeArrayAccessData(v7, &ppvData);
        if ( v6 >= 0 )
        {
          v8 = ppvData;
          if ( !ppvData )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(0);
            v8 = ppvData;
          }
          memcpy_0(v8, Src, (unsigned int)Size);
          v6 = SafeArrayUnaccessData(v5);
          if ( v6 >= 0 )
          {
            ppvData = 0;
            v3 = v5;
            v5 = 0;
          }
        }
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  LocalFree(Src);
  if ( v5 )
  {
    if ( ppvData )
      SafeArrayUnaccessData(v5);
    SafeArrayDestroy(v5);
  }
  if ( v6 >= 0 )
  {
    VariantInit(a2);
    result = 0;
    a2->vt = 8209;
    a2->llVal = (LONGLONG)v3;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enterprisecsps\\v2\\CertificateCore\\CertificateStoreNodeHelper.h",
      (const char *)(unsigned int)v6,
      (int)Src);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x18001da10  push    rbp
0x18001da12  push    rbx
0x18001da13  push    rsi
0x18001da14  push    rdi
0x18001da15  push    r14
0x18001da17  mov     rbp, rsp
0x18001da1a  sub     rsp, 30h
0x18001da1e  mov     rsi, rdx
0x18001da21  xor     r14d, r14d
0x18001da24  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001da29  xor     edi, edi
0x18001da2b  mov     [rbp+Src], r14
0x18001da2f  mov     [rbp+ppvData], r14
0x18001da33  mov     dword ptr [rbp+Size], r14d
0x18001da37  mov     qword ptr [rbp+rgsabound.cElements], r14
0x18001da3b  test    rax, rax
0x18001da3e  jnz     short loc_18001DA4A
0x18001da40  mov     ebx, 80070057h
0x18001da45  jmp     loc_18001DAF1
0x18001da4a  lea     r8, [rbp+Size]
0x18001da4e  mov     rcx, rax
0x18001da51  lea     rdx, [rbp+Src]
0x18001da55  call    cs:__imp_?DecodeBase64W@@YAJQEBGPEAPEAEPEAH@Z; DecodeBase64W(ushort const * const,uchar * *,int *)
0x18001da5c  nop     dword ptr [rax+rax+00h]
0x18001da61  mov     ebx, eax
0x18001da63  test    eax, eax
0x18001da65  js      loc_18001DAF1
0x18001da6b  mov     eax, dword ptr [rbp+Size]
0x18001da6e  lea     r8, [rbp+rgsabound]; rgsabound
0x18001da72  mov     ecx, 11h; vt
0x18001da77  mov     [rbp+rgsabound.lLbound], edi
0x18001da7a  mov     [rbp+rgsabound.cElements], eax
0x18001da7d  lea     edx, [rcx-10h]; cDims
0x18001da80  call    cs:__imp_SafeArrayCreate
0x18001da87  nop     dword ptr [rax+rax+00h]
0x18001da8c  mov     rdi, rax
0x18001da8f  test    rax, rax
0x18001da92  jnz     short loc_18001DA9B
0x18001da94  mov     ebx, 8007000Eh
0x18001da99  jmp     short loc_18001DAF1
0x18001da9b  lea     rdx, [rbp+ppvData]; ppvData
0x18001da9f  mov     rcx, rdi; psa
0x18001daa2  call    cs:__imp_SafeArrayAccessData
0x18001daa9  nop     dword ptr [rax+rax+00h]
0x18001daae  mov     ebx, eax
0x18001dab0  test    eax, eax
0x18001dab2  js      short loc_18001DAF1
0x18001dab4  mov     rcx, [rbp+ppvData]
0x18001dab8  test    rcx, rcx
0x18001dabb  jnz     short loc_18001DAC6
0x18001dabd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL != pbSafeArray")
0x18001dac2  mov     rcx, [rbp+ppvData]; void *
0x18001dac6  mov     r8d, dword ptr [rbp+Size]; Size
0x18001daca  mov     rdx, [rbp+Src]; Src
0x18001dace  call    memcpy_0
0x18001dad3  mov     rcx, rdi; psa
0x18001dad6  call    cs:__imp_SafeArrayUnaccessData
0x18001dadd  nop     dword ptr [rax+rax+00h]
0x18001dae2  mov     ebx, eax
0x18001dae4  test    eax, eax
0x18001dae6  js      short loc_18001DAF1
0x18001dae8  mov     [rbp+ppvData], r14
0x18001daec  mov     r14, rdi
0x18001daef  xor     edi, edi
0x18001daf1  mov     rcx, [rbp+Src]; hMem
0x18001daf5  call    cs:__imp_LocalFree
0x18001dafc  nop     dword ptr [rax+rax+00h]
0x18001db01  test    rdi, rdi
0x18001db04  jz      short loc_18001DB2B
0x18001db06  cmp     [rbp+ppvData], 0
0x18001db0b  jz      short loc_18001DB1C
0x18001db0d  mov     rcx, rdi; psa
0x18001db10  call    cs:__imp_SafeArrayUnaccessData
0x18001db17  nop     dword ptr [rax+rax+00h]
0x18001db1c  mov     rcx, rdi; psa
0x18001db1f  call    cs:__imp_SafeArrayDestroy
0x18001db26  nop     dword ptr [rax+rax+00h]
0x18001db2b  test    ebx, ebx
0x18001db2d  jns     short loc_18001DB4B
0x18001db2f  mov     rcx, [rbp+28h]; this
0x18001db33  lea     r8, aOnecoreuapAdmi_71; "onecoreuap\\admin\\enterprisemgmt\\ente"...
0x18001db3a  mov     r9d, ebx; char *
0x18001db3d  mov     edx, 20h ; ' '; void *
0x18001db42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db47  mov     eax, ebx
0x18001db49  jmp     short loc_18001DB65
0x18001db4b  mov     rcx, rsi; pvarg
0x18001db4e  call    cs:__imp_VariantInit
0x18001db55  nop     dword ptr [rax+rax+00h]
0x18001db5a  xor     eax, eax
0x18001db5c  mov     word ptr [rsi], 2011h
0x18001db61  mov     [rsi+8], r14
0x18001db65  add     rsp, 30h
0x18001db69  pop     r14
0x18001db6b  pop     rdi
0x18001db6c  pop     rsi
0x18001db6d  pop     rbx
0x18001db6e  pop     rbp
0x18001db6f  retn
```
