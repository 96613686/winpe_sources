# Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(wchar_t const *)

- ea: `0x180006060`
- end: `0x1800061a9`
- name: `??0HgsClientData@Plugin@Client@HostGuardian@Microsoft@@QEAA@PEB_W@Z`
- size: `329`
- prototype: `Microsoft::HostGuardian::Client::Plugin::HgsClientData *__fastcall(Microsoft::HostGuardian::Client::Plugin::HgsClientData *this, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007c80`
- `0x180007f80`

## callees

- `0x180001520`
- `0x180005f34`
- `0x180006060`
- `0x180006260`
- `0x18000642c`
- `0x1800064cc`
- `0x1800065c0`
- `0x1800069fc`
- `0x180006d5c`
- `0x1800088cc`

## pseudocode

```c
Microsoft::HostGuardian::Client::Plugin::HgsClientData *__fastcall Microsoft::HostGuardian::Client::Plugin::HgsClientData::HgsClientData(
        Microsoft::HostGuardian::Client::Plugin::HgsClientData *this,
        const wchar_t *a2,
        __int64 a3)
{
  __int64 v4; // rax
  const wchar_t *v5; // rdx
  const wchar_t *v6; // rcx
  const wchar_t *v7; // rdx
  wchar_t *S1[4]; // [rsp+30h] [rbp-38h] BYREF

  *(_OWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 7;
  *(_WORD *)this = 0;
  *((_OWORD *)this + 2) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 7;
  *((_WORD *)this + 16) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *(_QWORD *)((char *)this + 116) = 2;
  *((_DWORD *)this + 31) = 0;
  *((_BYTE *)this + 128) = 1;
  if ( a2 && *a2 )
  {
    *((_DWORD *)this + 28) = 2;
    v4 = std::wstring::wstring(S1);
    std::wstring::operator=(this, v4);
  }
  else
  {
    Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(S1, a2, a3, L"Mode", this);
    v6 = (const wchar_t *)S1;
    if ( S1[3] > (wchar_t *)7 )
      v6 = S1[0];
    if ( S1[2] == (wchar_t *)3 && !wmemcmp(v6, v5, 3u) )
    {
      *((_DWORD *)this + 28) = 2;
      Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry(this);
    }
    else
    {
      *((_DWORD *)this + 28) = 1;
      Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetCACertSupportedFromRegistry(this);
    }
    v7 = L"TRUE";
    if ( !*((_BYTE *)this + 128) )
      v7 = L"FALSE";
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo((wchar_t *)L"CACertSupported is %ws.", v7);
  }
  std::wstring::~wstring(S1);
  return this;
}

```

## disassembly

```asm
0x180006060  mov     [rsp+arg_10], rbx
0x180006065  push    rdi
0x180006066  sub     rsp, 60h
0x18000606a  mov     rax, cs:__security_cookie
0x180006071  xor     rax, rsp
0x180006074  mov     [rsp+68h+var_18], rax
0x180006079  mov     rbx, rcx
0x18000607c  mov     [rsp+68h+var_48], rcx
0x180006081  xorps   xmm0, xmm0
0x180006084  movups  xmmword ptr [rcx], xmm0
0x180006087  xor     edi, edi
0x180006089  mov     [rcx+10h], rdi
0x18000608d  mov     qword ptr [rcx+18h], 7
0x180006095  mov     [rcx], di
0x180006098  movups  xmmword ptr [rcx+20h], xmm0
0x18000609c  mov     [rcx+30h], rdi
0x1800060a0  mov     qword ptr [rcx+38h], 7
0x1800060a8  mov     [rcx+20h], di
0x1800060ac  mov     [rcx+40h], rdi
0x1800060b0  mov     [rcx+48h], rdi
0x1800060b4  mov     [rcx+50h], rdi
0x1800060b8  mov     [rcx+58h], rdi
0x1800060bc  mov     [rcx+60h], rdi
0x1800060c0  mov     [rcx+68h], rdi
0x1800060c4  mov     [rcx+70h], edi
0x1800060c7  mov     qword ptr [rcx+74h], 2
0x1800060cf  mov     [rcx+7Ch], edi
0x1800060d2  mov     byte ptr [rcx+80h], 1
0x1800060d9  test    rdx, rdx
0x1800060dc  jz      short loc_180006101
0x1800060de  cmp     [rdx], di
0x1800060e1  jz      short loc_180006101
0x1800060e3  mov     dword ptr [rcx+70h], 2
0x1800060ea  lea     rcx, [rsp+68h+S1]
0x1800060ef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800060f4  mov     rdx, rax
0x1800060f7  mov     rcx, rbx
0x1800060fa  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800060ff  jmp     short loc_180006180
0x180006101  lea     r9, aMode; "Mode"
0x180006108  lea     rcx, [rsp+68h+S1]
0x18000610d  call    ?QueryRegistryKeyForString@RegistryUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAUHKEY__@@PEB_W1@Z; Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForString(HKEY__ * const,wchar_t const *,wchar_t const *)
0x180006112  nop
0x180006113  lea     rcx, [rsp+68h+S1]
0x180006118  cmp     [rsp+68h+var_20], 7
0x18000611e  cmova   rcx, [rsp+68h+S1]; S1
0x180006124  mov     r8d, 3; N
0x18000612a  cmp     [rsp+68h+var_28], r8
0x18000612f  jnz     short loc_18000614B
0x180006131  call    wmemcmp
0x180006136  test    eax, eax
0x180006138  jnz     short loc_18000614B
0x18000613a  mov     dword ptr [rbx+70h], 2
0x180006141  mov     rcx, rbx; this
0x180006144  call    ?SetShsValuesFromRegistry@HgsClientData@Plugin@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetShsValuesFromRegistry(void)
0x180006149  jmp     short loc_18000615A
0x18000614b  mov     dword ptr [rbx+70h], 1
0x180006152  mov     rcx, rbx; this
0x180006155  call    ?SetCACertSupportedFromRegistry@HgsClientData@Plugin@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::Plugin::HgsClientData::SetCACertSupportedFromRegistry(void)
0x18000615a  lea     rax, aFalse; "FALSE"
0x180006161  lea     rdx, aTrue; "TRUE"
0x180006168  cmp     [rbx+80h], dil
0x18000616f  cmovz   rdx, rax; wchar_t *
0x180006173  lea     rcx, aCacertsupporte; "CACertSupported is %ws."
0x18000617a  call    ?TraceInfo@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(wchar_t const *,...)
0x18000617f  nop
0x180006180  lea     rcx, [rsp+68h+S1]
0x180006185  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000618a  nop
0x18000618b  mov     rax, rbx
0x18000618e  mov     rcx, [rsp+68h+var_18]
0x180006193  xor     rcx, rsp; StackCookie
0x180006196  call    __security_check_cookie
0x18000619b  mov     rbx, [rsp+68h+arg_10]
0x1800061a3  add     rsp, 60h
0x1800061a7  pop     rdi
0x1800061a8  retn
```
