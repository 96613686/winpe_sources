# ResolveFirmwareMeasurementsFilePath(ushort const *,ushort * *)

- ea: `0x18005087c`
- end: `0x180050c36`
- name: `?ResolveFirmwareMeasurementsFilePath@@YAJPEBGPEAPEAG@Z`
- size: `954`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180009c44`
- `0x180009c64`
- `0x18000c6d0`
- `0x18000f0c8`
- `0x18000f8cc`
- `0x18001c48c`
- `0x18002a92c`
- `0x180036b48`
- `0x18005087c`
- `0x180051ca0`
- `0x1800570bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18005093c`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18005093c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800509e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050aad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180050b04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050b18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800509fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050ac1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180050b18`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800508cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800508cd`

## string_xrefs

- `0x1800508e5`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x1800509cf`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180050ae2`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`
- `0x180050bda`: `onecore\base\ngscb\pcrpf\fwupdate\fwupdate.cpp`

## pseudocode

```c
__int64 __fastcall ResolveFirmwareMeasurementsFilePath(unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v5; // r8
  const char *v6; // r9
  __int64 result; // rax
  _WORD *v8; // rsi
  char v9; // dl
  __int16 v10; // r8
  int v11; // r9d
  __int64 v12; // r8
  unsigned __int64 v13; // rdx
  void **v14; // rdi
  __int64 v15; // rbx
  HANDLE ProcessHeap; // rax
  const char *v17; // r9
  void **v18; // rdx
  __int64 v19; // rax
  const wchar_t *v20; // rcx
  HANDLE v21; // rax
  HANDLE v22; // rax
  unsigned __int64 v23; // rdx
  __int64 v24; // rbx
  void **v25; // rdx
  void *Src; // [rsp+20h] [rbp-2A8h] BYREF
  void *v27[2]; // [rsp+28h] [rbp-2A0h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-290h]
  unsigned __int64 v29; // [rsp+40h] [rbp-288h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-280h] BYREF
  size_t N; // [rsp+58h] [rbp-270h]
  unsigned __int64 v32; // [rsp+60h] [rbp-268h]
  wchar_t S2[12]; // [rsp+68h] [rbp-260h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+0h]

  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x2A,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
             v6);
  try
  {
    *(_OWORD *)v27 = 0;
    v28 = 0;
    v29 = 7;
    LOWORD(v27[0]) = 0;
    if ( *a1 == 92 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &Src,
        a1,
        -1);
      v8 = Src;
      o((wchar_t)Src, v9, v10, v11, (wchar_t)Src, *(long double *)v27);
      v13 = -1;
      do
        ++v13;
      while ( v8[v13] );
      if ( v13 > v29 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v27,
          v13,
          v12,
          v8);
      }
      else
      {
        v14 = v27;
        if ( v29 > 7 )
          v14 = (void **)v27[0];
        v28 = v13;
        v15 = 2 * v13;
        memmove_0(v14, v8, 2 * v13);
        *(_WORD *)((char *)v14 + v15) = 0;
      }
      wcscpy(S2, L"\\systemroot");
      if ( v28 < 0xB )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x38,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
          (const char *)0x80070057LL,
          (int)Src);
        if ( v8 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v8);
        }
LABEL_14:
        std::wstring::~wstring(v27);
        return 2147942487LL;
      }
      *(_OWORD *)S1 = 0;
      N = 0;
      v32 = 0;
      v18 = v27;
      if ( v29 > 7 )
        v18 = (void **)v27[0];
      std::wstring::_Construct<1,unsigned short const *>(S1, v18);
      v19 = -1;
      do
        ++v19;
      while ( S2[v19] );
      v20 = (const wchar_t *)S1;
      if ( v32 > 7 )
        v20 = S1[0];
      if ( N != v19 || N && wmemcmp(v20, S2, N) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
          (const char *)0x80070057LL,
          (int)Src);
        std::wstring::~wstring(S1);
        if ( v8 )
        {
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v8);
        }
        goto LABEL_14;
      }
      std::wstring::replace((int)v27);
      std::wstring::~wstring(S1);
      if ( v8 )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v8);
      }
    }
    else
    {
      v23 = -1;
      do
        ++v23;
      while ( Buffer[v23] );
      if ( v23 > 7 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          v27,
          v23,
          v5,
          Buffer);
      }
      else
      {
        v28 = v23;
        v24 = 2 * v23;
        memmove_0(v27, Buffer, 2 * v23);
        *(_WORD *)((char *)v27 + v24) = 0;
      }
      std::wstring::operator+=(v27, L"\\firmware\\");
      std::wstring::operator+=(v27, a1);
    }
    v25 = v27;
    if ( v29 > 7 )
      v25 = (void **)v27[0];
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Src,
      v25,
      -1);
    if ( Src )
    {
      *a2 = (unsigned __int16 *)Src;
      std::wstring::~wstring(v27);
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
        (const char *)0x8007000ELL,
        0);
      std::wstring::~wstring(v27);
      result = 2147942414LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4B,
                           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fwupdate.cpp",
                           v17);
  }
  return result;
}

```

## disassembly

```asm
0x18005087c  mov     [rsp+arg_10], rbx
0x180050881  push    rsi
0x180050882  push    rdi
0x180050883  push    r12
0x180050885  push    r14
0x180050887  push    r15
0x180050889  sub     rsp, 2A0h
0x180050890  mov     rax, cs:__security_cookie
0x180050897  xor     rax, rsp
0x18005089a  mov     [rsp+2C8h+var_38], rax
0x1800508a2  mov     r15, rdx
0x1800508a5  mov     rdi, rcx
0x1800508a8  xor     r12d, r12d
0x1800508ab  xor     edx, edx; Val
0x1800508ad  mov     r8d, 208h; Size
0x1800508b3  lea     rcx, [rsp+2C8h+Buffer]; void *
0x1800508bb  call    memset_0
0x1800508c0  mov     edx, 104h; uSize
0x1800508c5  lea     rcx, [rsp+2C8h+Buffer]; lpBuffer
0x1800508cd  call    cs:__imp_GetWindowsDirectoryW
0x1800508d4  nop     dword ptr [rax+rax+00h]
0x1800508d9  test    eax, eax
0x1800508db  jnz     short loc_1800508F9
0x1800508dd  mov     rcx, [rsp+2C8h]; this
0x1800508e5  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800508ec  lea     edx, [rax+2Ah]; void *
0x1800508ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800508f4  jmp     loc_180050C0D
0x1800508f9  xorps   xmm0, xmm0
0x1800508fc  movups  xmmword ptr [rsp+2C8h+var_2A0], xmm0
0x180050901  mov     [rsp+2C8h+var_290], r12
0x180050906  mov     [rsp+2C8h+var_288], 7
0x18005090f  mov     word ptr [rsp+2C8h+var_2A0], r12w
0x180050915  or      r14, 0FFFFFFFFFFFFFFFFh
0x180050919  cmp     word ptr [rdi], 5Ch ; '\'
0x18005091d  jnz     loc_180050B36
0x180050923  mov     r8, r14
0x180050926  mov     rdx, rdi
0x180050929  lea     rcx, [rsp+2C8h+Src]
0x18005092e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180050933  nop
0x180050934  mov     rsi, [rsp+2C8h+Src]
0x180050939  mov     rcx, rsi
0x18005093c  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180050943  nop     dword ptr [rax+rax+00h]
0x180050948  mov     rdx, r14
0x18005094b  inc     rdx
0x18005094e  cmp     [rsi+rdx*2], r12w
0x180050953  jnz     short loc_18005094B
0x180050955  cmp     rdx, [rsp+2C8h+var_288]
0x18005095a  ja      short loc_18005098B
0x18005095c  lea     rdi, [rsp+2C8h+var_2A0]
0x180050961  cmp     [rsp+2C8h+var_288], 7
0x180050967  cmova   rdi, [rsp+2C8h+var_2A0]
0x18005096d  mov     [rsp+2C8h+var_290], rdx
0x180050972  lea     rbx, [rdx+rdx]
0x180050976  mov     r8, rbx; Size
0x180050979  mov     rdx, rsi; Src
0x18005097c  mov     rcx, rdi; void *
0x18005097f  call    memmove_0
0x180050984  mov     [rbx+rdi], r12w
0x180050989  jmp     short loc_180050998
0x18005098b  mov     r9, rsi
0x18005098e  lea     rcx, [rsp+2C8h+var_2A0]
0x180050993  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180050998  movups  xmm0, xmmword ptr cs:aSystemroot; "\\systemroot"
0x18005099f  movups  xmmword ptr [rsp+2C8h+S2], xmm0
0x1800509a4  movsd   xmm1, qword ptr cs:aSystemroot+10h; "oot"
0x1800509ac  movsd   [rsp+2C8h+var_250], xmm1
0x1800509b2  mov     r8d, 0Bh
0x1800509b8  cmp     [rsp+2C8h+var_290], r8
0x1800509bd  jnb     short loc_180050A18
0x1800509bf  mov     rcx, [rsp+2C8h]; this
0x1800509c7  mov     ebx, 80070057h
0x1800509cc  mov     r9d, ebx; char *
0x1800509cf  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800509d6  mov     edx, 38h ; '8'; void *
0x1800509db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800509e0  nop
0x1800509e1  test    rsi, rsi
0x1800509e4  jz      short loc_180050A07
0x1800509e6  call    cs:__imp_GetProcessHeap
0x1800509ed  nop     dword ptr [rax+rax+00h]
0x1800509f2  mov     rcx, rax; hHeap
0x1800509f5  mov     r8, rsi; lpMem
0x1800509f8  xor     edx, edx; dwFlags
0x1800509fa  call    cs:__imp_HeapFree
0x180050a01  nop     dword ptr [rax+rax+00h]
0x180050a06  nop
0x180050a07  lea     rcx, [rsp+2C8h+var_2A0]
0x180050a0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050a11  mov     eax, ebx
0x180050a13  jmp     loc_180050C0D
0x180050a18  xorps   xmm0, xmm0
0x180050a1b  movups  xmmword ptr [rsp+2C8h+S1], xmm0
0x180050a20  mov     [rsp+2C8h+N], r12
0x180050a25  mov     [rsp+2C8h+var_268], r12
0x180050a2a  lea     rdx, [rsp+2C8h+var_2A0]
0x180050a2f  cmp     [rsp+2C8h+var_288], 7
0x180050a35  cmova   rdx, [rsp+2C8h+var_2A0]
0x180050a3b  lea     rcx, [rsp+2C8h+S1]
0x180050a40  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180050a45  nop
0x180050a46  lea     rcx, [rsp+2C8h+S2]
0x180050a4b  mov     rax, r14
0x180050a4e  inc     rax
0x180050a51  cmp     [rcx+rax*2], r12w
0x180050a56  jnz     short loc_180050A4E
0x180050a58  mov     r8, [rsp+2C8h+N]; N
0x180050a5d  lea     rcx, [rsp+2C8h+S1]
0x180050a62  cmp     [rsp+2C8h+var_268], 7
0x180050a68  cmova   rcx, [rsp+2C8h+S1]; S1
0x180050a6e  cmp     r8, rax
0x180050a71  jnz     short loc_180050AD2
0x180050a73  test    r8, r8
0x180050a76  jz      short loc_180050A86
0x180050a78  lea     rdx, [rsp+2C8h+S2]; S2
0x180050a7d  call    wmemcmp
0x180050a82  test    eax, eax
0x180050a84  jnz     short loc_180050AD2
0x180050a86  lea     r9, [rsp+2C8h+Buffer]
0x180050a8e  lea     rcx, [rsp+2C8h+var_2A0]; int
0x180050a93  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0QEBG@Z; std::wstring::replace(unsigned __int64,unsigned __int64,ushort const * const)
0x180050a98  nop
0x180050a99  lea     rcx, [rsp+2C8h+S1]
0x180050a9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050aa3  nop
0x180050aa4  test    rsi, rsi
0x180050aa7  jz      loc_180050BA2
0x180050aad  call    cs:__imp_GetProcessHeap
0x180050ab4  nop     dword ptr [rax+rax+00h]
0x180050ab9  mov     rcx, rax; hHeap
0x180050abc  mov     r8, rsi; lpMem
0x180050abf  xor     edx, edx; dwFlags
0x180050ac1  call    cs:__imp_HeapFree
0x180050ac8  nop     dword ptr [rax+rax+00h]
0x180050acd  jmp     loc_180050BA2
0x180050ad2  mov     rcx, [rsp+2C8h]; this
0x180050ada  mov     ebx, 80070057h
0x180050adf  mov     r9d, ebx; char *
0x180050ae2  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180050ae9  mov     edx, 3Ah ; ':'; void *
0x180050aee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050af3  nop
0x180050af4  lea     rcx, [rsp+2C8h+S1]
0x180050af9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050afe  nop
0x180050aff  test    rsi, rsi
0x180050b02  jz      short loc_180050B25
0x180050b04  call    cs:__imp_GetProcessHeap
0x180050b0b  nop     dword ptr [rax+rax+00h]
0x180050b10  mov     rcx, rax; hHeap
0x180050b13  mov     r8, rsi; lpMem
0x180050b16  xor     edx, edx; dwFlags
0x180050b18  call    cs:__imp_HeapFree
0x180050b1f  nop     dword ptr [rax+rax+00h]
0x180050b24  nop
0x180050b25  lea     rcx, [rsp+2C8h+var_2A0]
0x180050b2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050b2f  mov     eax, ebx
0x180050b31  jmp     loc_180050C0D
0x180050b36  lea     rax, [rsp+2C8h+Buffer]
0x180050b3e  mov     rdx, r14
0x180050b41  inc     rdx
0x180050b44  cmp     [rax+rdx*2], r12w
0x180050b49  jnz     short loc_180050B41
0x180050b4b  lea     rcx, [rsp+2C8h+var_2A0]; void *
0x180050b50  cmp     rdx, 7
0x180050b54  ja      short loc_180050B77
0x180050b56  mov     [rsp+2C8h+var_290], rdx
0x180050b5b  lea     rbx, [rdx+rdx]
0x180050b5f  mov     r8, rbx; Size
0x180050b62  lea     rdx, [rsp+2C8h+Buffer]; Src
0x180050b6a  call    memmove_0
0x180050b6f  mov     word ptr [rsp+rbx+2C8h+var_2A0], r12w
0x180050b75  jmp     short loc_180050B84
0x180050b77  lea     r9, [rsp+2C8h+Buffer]
0x180050b7f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180050b84  lea     rdx, aFirmware; "\\firmware\\"
0x180050b8b  lea     rcx, [rsp+2C8h+var_2A0]; Src
0x180050b90  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180050b95  mov     rdx, rdi; void *
0x180050b98  lea     rcx, [rsp+2C8h+var_2A0]; Src
0x180050b9d  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180050ba2  lea     rdx, [rsp+2C8h+var_2A0]
0x180050ba7  cmp     [rsp+2C8h+var_288], 7
0x180050bad  cmova   rdx, [rsp+2C8h+var_2A0]
0x180050bb3  mov     r8, r14
0x180050bb6  lea     rcx, [rsp+2C8h+Src]
0x180050bbb  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180050bc0  mov     rax, [rsp+2C8h+Src]
0x180050bc5  test    rax, rax
0x180050bc8  jnz     short loc_180050BF8
0x180050bca  mov     rcx, [rsp+2C8h]; this
0x180050bd2  mov     ebx, 8007000Eh
0x180050bd7  mov     r9d, ebx; char *
0x180050bda  lea     r8, aOnecoreBaseNgs_3; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180050be1  lea     edx, [rax+46h]; void *
0x180050be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050be9  nop
0x180050bea  lea     rcx, [rsp+2C8h+var_2A0]
0x180050bef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050bf4  mov     eax, ebx
0x180050bf6  jmp     short loc_180050C0D
0x180050bf8  mov     [r15], rax
0x180050bfb  lea     rcx, [rsp+2C8h+var_2A0]
0x180050c00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050c05  xor     eax, eax
0x180050c07  jmp     short loc_180050C0D
0x180050c09  mov     eax, dword ptr [rsp+2C8h+Src]
0x180050c0d  mov     rcx, [rsp+2C8h+var_38]
0x180050c15  xor     rcx, rsp; StackCookie
0x180050c18  call    __security_check_cookie
0x180050c1d  mov     rbx, [rsp+2C8h+arg_10]
0x180050c25  add     rsp, 2A0h
0x180050c2c  pop     r15
0x180050c2e  pop     r14
0x180050c30  pop     r12
0x180050c32  pop     rdi
0x180050c33  pop     rsi
0x180050c34  retn
```
