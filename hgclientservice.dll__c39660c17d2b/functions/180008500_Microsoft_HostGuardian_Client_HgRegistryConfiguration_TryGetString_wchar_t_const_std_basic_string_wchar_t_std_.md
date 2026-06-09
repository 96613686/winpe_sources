# Microsoft::HostGuardian::Client::HgRegistryConfiguration::TryGetString(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180008500`
- end: `0x180008687`
- name: `?TryGetString@HgRegistryConfiguration@Client@HostGuardian@Microsoft@@UEAAJPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `391`
- prototype: `int __fastcall(__int64, const WCHAR *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001770`
- `0x180001bb4`
- `0x180002abc`
- `0x180003d0c`
- `0x180004274`
- `0x1800064b4`
- `0x1800081e0`
- `0x180008498`
- `0x180008500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008558`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800085d4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180008558`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800085d4`

## string_xrefs

- `0x18000858d`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`
- `0x180008609`: `servercommon\base\securehostingservice\common\service\lib\hgregistryconfiguration.cpp`

## pseudocode

```c
int __fastcall Microsoft::HostGuardian::Client::HgRegistryConfiguration::TryGetString(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  unsigned int ValueW; // eax
  unsigned int v7; // r8d
  int v9; // ebx
  void *pvData; // rdi
  unsigned int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // r8
  unsigned int pdwType; // [rsp+20h] [rbp-50h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-50h]
  DWORD v16; // [rsp+40h] [rbp-30h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-2Ch] BYREF
  __int128 v18; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+58h] [rbp-18h]
  __int64 v20; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v16 = 0;
  pcbData = 0;
  ValueW = RegGetValueW(*(HKEY *)(a1 + 8), 0, a2, 6u, &v16, 0, &pcbData);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(retaddr, (void *)0x70, v7, (const char *)ValueW, pdwType);
  if ( v16 - 1 <= 1 )
  {
    pvData = operator new[](pcbData);
    v11 = RegGetValueW(*(HKEY *)(a1 + 8), 0, a2, 6u, &v16, pvData, &pcbData);
    if ( v11 )
    {
      v9 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x7C, v12, (const char *)v11, pdwTypea);
    }
    else if ( v16 - 1 <= 1 )
    {
      v18 = 0;
      v19 = 0;
      v20 = 0;
      v13 = -1;
      do
        ++v13;
      while ( *((_WORD *)pvData + v13) );
      std::wstring::_Construct<1,wchar_t const *>(&v18, pvData, v13);
      std::wstring::operator=(a3, &v18);
      std::wstring::~wstring(&v18);
      v9 = 0;
    }
    else
    {
      v9 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
        (const char *)0x8000FFFFLL,
        pdwTypea);
    }
    operator delete(pvData);
  }
  else
  {
    v9 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\hgregistryconfiguration.cpp",
      (const char *)0x8000FFFFLL,
      pdwType);
  }
  return v9;
}

```

## disassembly

```asm
0x180008500  mov     r11, rsp
0x180008503  mov     [r11+20h], rbx
0x180008507  push    rbp
0x180008508  push    rsi
0x180008509  push    rdi
0x18000850a  push    r14
0x18000850c  push    r15
0x18000850e  mov     rbp, rsp
0x180008511  sub     rsp, 70h
0x180008515  mov     rax, cs:__security_cookie
0x18000851c  xor     rax, rsp
0x18000851f  mov     [rbp+var_8], rax
0x180008523  mov     r14, r8
0x180008526  mov     rsi, rdx
0x180008529  mov     rbx, rcx
0x18000852c  xor     r15d, r15d
0x18000852f  mov     [rbp+var_30], r15d
0x180008533  mov     [rbp+var_2C], r15d
0x180008537  lea     rax, [rbp+var_2C]
0x18000853b  mov     [r11-68h], rax
0x18000853f  mov     [r11-70h], r15
0x180008543  lea     rax, [rbp+var_30]
0x180008547  mov     [r11-78h], rax
0x18000854b  lea     r9d, [r15+6]; dwFlags
0x18000854f  mov     r8, rdx; lpValue
0x180008552  xor     edx, edx; lpSubKey
0x180008554  mov     rcx, [rcx+8]; hkey
0x180008558  call    cs:__imp_RegGetValueW
0x18000855e  test    eax, eax
0x180008560  jz      short loc_180008577
0x180008562  mov     rcx, [rbp+28h]; this
0x180008566  mov     r9d, eax; char *
0x180008569  lea     edx, [r15+70h]; void *
0x18000856d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180008572  jmp     loc_180008667
0x180008577  mov     eax, [rbp+var_30]
0x18000857a  dec     eax
0x18000857c  cmp     eax, 1
0x18000857f  jbe     short loc_1800085A3
0x180008581  mov     rcx, [rbp+28h]; this
0x180008585  mov     ebx, 8000FFFFh
0x18000858a  mov     r9d, ebx; char *
0x18000858d  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x180008594  mov     edx, 71h ; 'q'; void *
0x180008599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000859e  jmp     loc_180008665
0x1800085a3  mov     ecx, [rbp+var_2C]; unsigned __int64
0x1800085a6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800085ab  mov     rdi, rax
0x1800085ae  lea     rax, [rbp+var_2C]
0x1800085b2  mov     [rsp+70h+pcbData], rax; pcbData
0x1800085b7  mov     [rsp+70h+pvData], rdi; pvData
0x1800085bc  lea     rax, [rbp+var_30]
0x1800085c0  mov     [rsp+70h+pdwType], rax; int
0x1800085c5  mov     r9d, 6; dwFlags
0x1800085cb  mov     r8, rsi; lpValue
0x1800085ce  xor     edx, edx; lpSubKey
0x1800085d0  mov     rcx, [rbx+8]; hkey
0x1800085d4  call    cs:__imp_RegGetValueW
0x1800085da  test    eax, eax
0x1800085dc  jz      short loc_1800085F3
0x1800085de  mov     rcx, [rbp+28h]; this
0x1800085e2  mov     r9d, eax; char *
0x1800085e5  mov     edx, 7Ch ; '|'; void *
0x1800085ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800085ef  mov     ebx, eax
0x1800085f1  jmp     short loc_18000865D
0x1800085f3  mov     eax, [rbp+var_30]
0x1800085f6  dec     eax
0x1800085f8  cmp     eax, 1
0x1800085fb  jbe     short loc_18000861C
0x1800085fd  mov     rcx, [rbp+28h]; this
0x180008601  mov     ebx, 8000FFFFh
0x180008606  mov     r9d, ebx; char *
0x180008609  lea     r8, aServercommonBa_9; "servercommon\\base\\securehostingservic"...
0x180008610  mov     edx, 7Dh ; '}'; void *
0x180008615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000861a  jmp     short loc_18000865D
0x18000861c  xorps   xmm0, xmm0
0x18000861f  movups  [rbp+var_28], xmm0
0x180008623  mov     [rbp+var_18], r15
0x180008627  mov     [rbp+var_10], r15
0x18000862b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000862f  inc     r8
0x180008632  cmp     [rdi+r8*2], r15w
0x180008637  jnz     short loc_18000862F
0x180008639  mov     rdx, rdi
0x18000863c  lea     rcx, [rbp+var_28]
0x180008640  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180008645  lea     rdx, [rbp+var_28]
0x180008649  mov     rcx, r14
0x18000864c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008651  lea     rcx, [rbp+var_28]
0x180008655  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000865a  mov     ebx, r15d
0x18000865d  mov     rcx, rdi; Block
0x180008660  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008665  mov     eax, ebx
0x180008667  mov     rcx, [rbp+var_8]
0x18000866b  xor     rcx, rsp; StackCookie
0x18000866e  call    __security_check_cookie
0x180008673  mov     rbx, [rsp+70h+arg_18]
0x18000867b  add     rsp, 70h
0x18000867f  pop     r15
0x180008681  pop     r14
0x180008683  pop     rdi
0x180008684  pop     rsi
0x180008685  pop     rbp
0x180008686  retn
```
