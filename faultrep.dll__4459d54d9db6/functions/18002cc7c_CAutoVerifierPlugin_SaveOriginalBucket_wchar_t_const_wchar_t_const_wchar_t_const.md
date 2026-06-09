# CAutoVerifierPlugin::SaveOriginalBucket(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x18002cc7c`
- end: `0x18002ce0c`
- name: `?SaveOriginalBucket@CAutoVerifierPlugin@@AEAAJPEB_W00@Z`
- size: `400`
- prototype: `__int64 __fastcall(CAutoVerifierPlugin *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c3e0`

## callees

- `0x1800028b4`
- `0x180006b50`
- `0x180009f00`
- `0x18002cc7c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cd87`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18002cd87`

## pseudocode

```c
__int64 __fastcall CAutoVerifierPlugin::SaveOriginalBucket(
        CAutoVerifierPlugin *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v5; // r8
  int v8; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  LSTATUS v12; // eax
  LPCVOID lpData; // [rsp+30h] [rbp-40h] BYREF
  char *v15; // [rsp+38h] [rbp-38h]
  _WORD v16[8]; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+50h] [rbp-20h] BYREF
  _WORD v18[8]; // [rsp+60h] [rbp-10h] BYREF

  v5 = *((_QWORD *)this + 93);
  lpSubKey[0] = v18;
  lpSubKey[1] = v18;
  v18[0] = 0;
  lpData = v16;
  v15 = (char *)v16;
  v16[0] = 0;
  v8 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
         (__int64)lpSubKey,
         (__int64)L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Image File Execution Options\\%s\\Autoverifier",
         v5);
  if ( v8 >= 0 )
  {
    if ( a3 )
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              (__int64)&lpData,
              (__int64)L"%s:%s@%s",
              a2,
              a3,
              a4);
    else
      v11 = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
              (__int64)&lpData,
              (__int64)L"%s@%s",
              a2,
              a4);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v12 = RegSetKeyValueW(
              HKEY_CURRENT_USER,
              lpSubKey[0],
              L"OriginalBucket",
              1u,
              lpData,
              2 * ((v15 - (_BYTE *)lpData) >> 1) + 2);
      v8 = v12;
      if ( v12 )
      {
        if ( v12 > 0 )
          v8 = (unsigned __int16)v12 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v10 = 29;
          goto LABEL_5;
        }
      }
      else
      {
        v8 = 0;
      }
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 28;
LABEL_5:
      WPP_SF_d(v9[2], v10, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids, (unsigned int)v8);
    }
  }
  if ( lpData != v16 )
    operator delete((void *)lpData, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpSubKey[0] != v18 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002cc7c  push    rbp
0x18002cc7e  push    rbx
0x18002cc7f  push    rsi
0x18002cc80  push    rdi
0x18002cc81  push    r14
0x18002cc83  mov     rbp, rsp
0x18002cc86  sub     rsp, 70h
0x18002cc8a  lea     rax, [rbp+var_10]
0x18002cc8e  mov     rdi, r8
0x18002cc91  mov     r8, [rcx+2E8h]
0x18002cc98  mov     r14, rdx
0x18002cc9b  mov     [rbp+lpSubKey], rax
0x18002cc9f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002cca6  lea     rax, [rbp+var_10]
0x18002ccaa  mov     rsi, r9
0x18002ccad  mov     [rbp+var_18], rax
0x18002ccb1  lea     rcx, [rbp+lpSubKey]
0x18002ccb5  xor     eax, eax
0x18002ccb7  mov     [rbp+var_10], ax
0x18002ccbb  lea     rax, [rbp+var_30]
0x18002ccbf  mov     [rbp+var_40], rax
0x18002ccc3  lea     rax, [rbp+var_30]
0x18002ccc7  mov     [rbp+var_38], rax
0x18002cccb  xor     eax, eax
0x18002cccd  mov     [rbp+var_30], ax
0x18002ccd1  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002ccd6  mov     ebx, eax
0x18002ccd8  test    eax, eax
0x18002ccda  jns     short loc_18002CD1A
0x18002ccdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cce3  lea     rax, WPP_GLOBAL_Control
0x18002ccea  cmp     rcx, rax
0x18002cced  jz      loc_18002CDCD
0x18002ccf3  test    byte ptr [rcx+1Ch], 1
0x18002ccf7  jz      loc_18002CDCD
0x18002ccfd  mov     edx, 1Ch
0x18002cd02  mov     rcx, [rcx+10h]
0x18002cd06  lea     r8, WPP_4b9d8d51c5683cc1abc10789e478c3a6_Traceguids
0x18002cd0d  mov     r9d, ebx
0x18002cd10  call    WPP_SF_d
0x18002cd15  jmp     loc_18002CDCD
0x18002cd1a  lea     rcx, [rbp+var_40]
0x18002cd1e  mov     r8, r14
0x18002cd21  test    rdi, rdi
0x18002cd24  jz      short loc_18002CD3C
0x18002cd26  mov     r9, rdi
0x18002cd29  mov     [rsp+70h+lpData], rsi
0x18002cd2e  lea     rdx, aSSS_1; "%s:%s@%s"
0x18002cd35  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002cd3a  jmp     short loc_18002CD4B
0x18002cd3c  mov     r9, rsi
0x18002cd3f  lea     rdx, aSS; "%s@%s"
0x18002cd46  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18002cd4b  mov     ebx, eax
0x18002cd4d  test    eax, eax
0x18002cd4f  js      short loc_18002CDCD
0x18002cd51  mov     rcx, [rbp+var_40]
0x18002cd55  lea     r8, aOriginalbucket; "OriginalBucket"
0x18002cd5c  mov     rax, [rbp+var_38]
0x18002cd60  mov     r9d, 1; dwType
0x18002cd66  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002cd6a  sub     rax, rcx
0x18002cd6d  sar     rax, 1
0x18002cd70  lea     eax, ds:2[rax*2]
0x18002cd77  mov     [rsp+70h+cbData], eax; cbData
0x18002cd7b  mov     [rsp+70h+lpData], rcx; lpData
0x18002cd80  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002cd87  call    cs:__imp_RegSetKeyValueW
0x18002cd8d  mov     ebx, eax
0x18002cd8f  test    eax, eax
0x18002cd91  jz      short loc_18002CDCB
0x18002cd93  jle     short loc_18002CD9E
0x18002cd95  movzx   ebx, ax
0x18002cd98  or      ebx, 80070000h
0x18002cd9e  test    ebx, ebx
0x18002cda0  mov     eax, 80004005h
0x18002cda5  cmovns  ebx, eax
0x18002cda8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cdaf  lea     rax, WPP_GLOBAL_Control
0x18002cdb6  cmp     rcx, rax
0x18002cdb9  jz      short loc_18002CDCD
0x18002cdbb  test    byte ptr [rcx+1Ch], 1
0x18002cdbf  jz      short loc_18002CDCD
0x18002cdc1  mov     edx, 1Dh
0x18002cdc6  jmp     loc_18002CD02
0x18002cdcb  xor     ebx, ebx
0x18002cdcd  mov     rcx, [rbp+var_40]; void *
0x18002cdd1  lea     rax, [rbp+var_30]
0x18002cdd5  cmp     rcx, rax
0x18002cdd8  jz      short loc_18002CDE6
0x18002cdda  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cde1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cde6  mov     rcx, [rbp+lpSubKey]; void *
0x18002cdea  lea     rax, [rbp+var_10]
0x18002cdee  cmp     rcx, rax
0x18002cdf1  jz      short loc_18002CDFF
0x18002cdf3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002cdfa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002cdff  mov     eax, ebx
0x18002ce01  add     rsp, 70h
0x18002ce05  pop     r14
0x18002ce07  pop     rdi
0x18002ce08  pop     rsi
0x18002ce09  pop     rbx
0x18002ce0a  pop     rbp
0x18002ce0b  retn
```
