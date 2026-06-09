# CFDRPlugin::DeleteFDRLayer(void)

- ea: `0x180034df8`
- end: `0x18003515f`
- name: `?DeleteFDRLayer@CFDRPlugin@@AEAAJXZ`
- size: `871`
- prototype: `__int64 __fastcall(CFDRPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035168`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x18000a004`
- `0x180011d94`
- `0x1800121e4`
- `0x180034df8`
- `0x180035334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003505d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003505d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003513e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003513e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034eaa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034eaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800350aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800350ba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800350aa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800350ba`

## string_xrefs

- `0x180034e9c`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CFDRPlugin::DeleteFDRLayer(CFDRPlugin *this)
{
  BYTE *v2; // rdi
  HKEY *phkResult; // rax
  LSTATUS v4; // eax
  const struct std::nothrow_t *v5; // rdx
  int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  void *v12; // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  _WORD v16[2]; // [rsp+30h] [rbp-49h] BYREF
  int v17; // [rsp+34h] [rbp-45h]
  void *v18; // [rsp+38h] [rbp-41h]
  __m128i si128; // [rsp+40h] [rbp-39h]
  void *v20; // [rsp+50h] [rbp-29h]
  _WORD *v21; // [rsp+58h] [rbp-21h]
  _WORD v22[8]; // [rsp+60h] [rbp-19h] BYREF
  void *v23; // [rsp+70h] [rbp-9h]
  _WORD *v24; // [rsp+78h] [rbp-1h]
  _WORD v25[8]; // [rsp+80h] [rbp+7h] BYREF
  const struct std::nothrow_t *v26; // [rsp+90h] [rbp+17h]
  void *v27; // [rsp+A0h] [rbp+27h]
  _WORD *v28; // [rsp+A8h] [rbp+2Fh]
  _WORD v29[8]; // [rsp+B0h] [rbp+37h] BYREF
  HKEY hKey; // [rsp+E8h] [rbp+6Fh] BYREF
  BYTE *lpData; // [rsp+F0h] [rbp+77h] BYREF

  v20 = v22;
  hKey = 0;
  v21 = v22;
  v16[0] = 0;
  v23 = v25;
  v17 = 0;
  v24 = v25;
  v2 = 0;
  v18 = (void *)-1LL;
  v27 = v29;
  v28 = v29;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v22[0] = 0;
  v25[0] = 0;
  v26 = 0;
  lpData = 0;
  v29[0] = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  v4 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         0,
         0xF003Fu,
         phkResult);
  v6 = v4;
  if ( v4 )
  {
    if ( v4 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_928a4490cd403d1d5470036a68085293_Traceguids);
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( v6 >= 0 )
        v6 = -2147467259;
      goto LABEL_39;
    }
LABEL_42:
    v6 = 0;
    goto LABEL_43;
  }
  v6 = CRegSetting::Initialize(v16, 1, &dword_18004FE4C, *((_QWORD *)this + 1), 0);
  if ( v6 >= 0 )
  {
    v6 = CRegSetting::Load((CRegSetting *)v16, hKey, 0);
    if ( v6 >= 0 )
    {
      LOBYTE(v9) = v16[0];
      v5 = v26;
      v12 = v26;
      if ( LOBYTE(v16[0]) )
        v12 = v18;
      if ( v12 )
      {
        if ( LOBYTE(v16[0]) )
          LODWORD(v5) = (_DWORD)v18;
        v6 = CFDRPlugin::FDRRemoveAppCompatLayerFromList(v9, (_DWORD)v5, v10, v11, (__int64)&lpData);
        if ( v6 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              WPP_928a4490cd403d1d5470036a68085293_Traceguids,
              (unsigned int)v6);
          v2 = lpData;
          goto LABEL_39;
        }
        v2 = lpData;
        if ( lpData && *(_WORD *)lpData )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&lpData[2 * v13] );
          v14 = RegSetValueExW(hKey, *((LPCWSTR *)this + 1), 0, 1u, lpData, 2 * v13 + 2);
          if ( v14 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_928a4490cd403d1d5470036a68085293_Traceguids, v14);
            v6 = -2147467259;
            goto LABEL_39;
          }
        }
        else
        {
          RegDeleteValueW(hKey, *((LPCWSTR *)this + 1));
        }
      }
      goto LABEL_42;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 54;
      goto LABEL_15;
    }
  }
  else
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 53;
LABEL_15:
      WPP_SF_d(v7[2], v8, WPP_928a4490cd403d1d5470036a68085293_Traceguids, (unsigned int)v6);
    }
  }
LABEL_39:
  if ( hKey )
    RegDeleteValueW(hKey, *((LPCWSTR *)this + 1));
LABEL_43:
  if ( v27 != v29 )
    operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    operator delete(v2, v5);
  if ( v23 != v25 )
    operator delete(v23, (const struct std::nothrow_t *)&std::nothrow);
  if ( v20 != v22 )
    operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
  if ( v18 != (void *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)v18;
    operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180034df8  mov     [rsp-8+arg_0], rbx
0x180034dfd  mov     [rsp-8+arg_18], rdi
0x180034e02  push    rbp
0x180034e03  push    r14
0x180034e05  push    r15
0x180034e07  lea     rbp, [rsp-47h]
0x180034e0c  sub     rsp, 0C0h
0x180034e13  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180034e1b  lea     rax, [rbp+57h+var_70]
0x180034e1f  xor     r15d, r15d
0x180034e22  mov     [rbp+57h+var_80], rax
0x180034e26  lea     rax, [rbp+57h+var_70]
0x180034e2a  mov     [rbp+57h+hKey], r15
0x180034e2e  mov     [rbp+57h+var_78], rax
0x180034e32  mov     r14, rcx
0x180034e35  lea     rax, [rbp+57h+var_50]
0x180034e39  mov     [rbp+57h+var_A0], r15w
0x180034e3e  mov     [rbp+57h+var_60], rax
0x180034e42  lea     rcx, [rbp+57h+hKey]
0x180034e46  lea     rax, [rbp+57h+var_50]
0x180034e4a  mov     [rbp+57h+var_9C], r15d
0x180034e4e  mov     [rbp+57h+var_58], rax
0x180034e52  mov     edi, r15d
0x180034e55  lea     rax, [rbp+57h+var_20]
0x180034e59  mov     [rbp+57h+var_98], 0FFFFFFFFFFFFFFFFh
0x180034e61  mov     [rbp+57h+var_30], rax
0x180034e65  lea     rax, [rbp+57h+var_20]
0x180034e69  mov     [rbp+57h+var_28], rax
0x180034e6d  movdqa  [rbp+57h+var_90], xmm0
0x180034e72  mov     [rbp+57h+var_70], r15w
0x180034e77  mov     [rbp+57h+var_50], r15w
0x180034e7c  mov     [rbp+57h+var_40], r15
0x180034e80  mov     [rbp+57h+lpData], r15
0x180034e84  mov     [rbp+57h+var_20], r15w
0x180034e89  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180034e8e  mov     r9d, 0F003Fh; samDesired
0x180034e94  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180034e99  xor     r8d, r8d; ulOptions
0x180034e9c  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x180034ea3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180034eaa  call    cs:__imp_RegOpenKeyExW
0x180034eb0  mov     ebx, eax
0x180034eb2  test    eax, eax
0x180034eb4  jz      short loc_180034F08
0x180034eb6  cmp     eax, 2
0x180034eb9  jz      loc_1800350C0
0x180034ebf  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ec6  lea     rax, WPP_GLOBAL_Control
0x180034ecd  cmp     rcx, rax
0x180034ed0  jz      short loc_180034EEC
0x180034ed2  test    byte ptr [rcx+1Ch], 1
0x180034ed6  jz      short loc_180034EEC
0x180034ed8  mov     rcx, [rcx+10h]
0x180034edc  lea     edx, [r15+34h]
0x180034ee0  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180034ee7  call    WPP_SF_
0x180034eec  test    ebx, ebx
0x180034eee  jle     short loc_180034EF9
0x180034ef0  movzx   ebx, bx
0x180034ef3  or      ebx, 80070000h
0x180034ef9  test    ebx, ebx
0x180034efb  mov     eax, 80004005h
0x180034f00  cmovns  ebx, eax
0x180034f03  jmp     loc_18003509D
0x180034f08  mov     r9, [r14+8]
0x180034f0c  lea     r8, dword_18004FE4C
0x180034f13  mov     edx, 1
0x180034f18  mov     [rsp+0D0h+phkResult], r15
0x180034f1d  lea     rcx, [rbp+57h+var_A0]
0x180034f21  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x180034f26  mov     ebx, eax
0x180034f28  test    eax, eax
0x180034f2a  jns     short loc_180034F6A
0x180034f2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f33  lea     rax, WPP_GLOBAL_Control
0x180034f3a  cmp     rcx, rax
0x180034f3d  jz      loc_18003509D
0x180034f43  test    byte ptr [rcx+1Ch], 1
0x180034f47  jz      loc_18003509D
0x180034f4d  mov     edx, 35h ; '5'
0x180034f52  mov     rcx, [rcx+10h]
0x180034f56  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180034f5d  mov     r9d, ebx
0x180034f60  call    WPP_SF_d
0x180034f65  jmp     loc_18003509D
0x180034f6a  mov     rdx, [rbp+57h+hKey]; HKEY
0x180034f6e  lea     rcx, [rbp+57h+var_A0]; this
0x180034f72  xor     r8d, r8d; unsigned int
0x180034f75  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x180034f7a  mov     ebx, eax
0x180034f7c  test    eax, eax
0x180034f7e  jns     short loc_180034FA8
0x180034f80  mov     rcx, cs:WPP_GLOBAL_Control
0x180034f87  lea     rax, WPP_GLOBAL_Control
0x180034f8e  cmp     rcx, rax
0x180034f91  jz      loc_18003509D
0x180034f97  test    byte ptr [rcx+1Ch], 1
0x180034f9b  jz      loc_18003509D
0x180034fa1  mov     edx, 36h ; '6'
0x180034fa6  jmp     short loc_180034F52
0x180034fa8  mov     cl, byte ptr [rbp+57h+var_A0]
0x180034fab  mov     rdx, [rbp+57h+var_40]
0x180034faf  test    cl, cl
0x180034fb1  mov     rax, rdx
0x180034fb4  cmovnz  rax, [rbp+57h+var_98]
0x180034fb9  test    rax, rax
0x180034fbc  jz      loc_1800350C0
0x180034fc2  test    cl, cl
0x180034fc4  lea     rax, [rbp+57h+lpData]
0x180034fc8  mov     [rsp+0D0h+phkResult], rax
0x180034fcd  cmovnz  rdx, [rbp+57h+var_98]
0x180034fd2  call    ?FDRRemoveAppCompatLayerFromList@CFDRPlugin@@AEAAJPEB_WK0PEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@utl@@@Z; CFDRPlugin::FDRRemoveAppCompatLayerFromList(wchar_t const *,ulong,wchar_t const *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *)
0x180034fd7  mov     ebx, eax
0x180034fd9  test    eax, eax
0x180034fdb  jns     short loc_180035017
0x180034fdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180034fe4  lea     rax, WPP_GLOBAL_Control
0x180034feb  cmp     rcx, rax
0x180034fee  jz      short loc_18003500E
0x180034ff0  test    byte ptr [rcx+1Ch], 1
0x180034ff4  jz      short loc_18003500E
0x180034ff6  mov     rcx, [rcx+10h]
0x180034ffa  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x180035001  mov     edx, 37h ; '7'
0x180035006  mov     r9d, ebx
0x180035009  call    WPP_SF_d
0x18003500e  mov     rdi, [rbp+57h+lpData]
0x180035012  jmp     loc_18003509D
0x180035017  mov     rdi, [rbp+57h+lpData]
0x18003501b  test    rdi, rdi
0x18003501e  jz      loc_1800350B2
0x180035024  cmp     [rdi], r15w
0x180035028  jz      loc_1800350B2
0x18003502e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035032  inc     rax
0x180035035  cmp     [rdi+rax*2], r15w
0x18003503a  jnz     short loc_180035032
0x18003503c  mov     rdx, [r14+8]; lpValueName
0x180035040  lea     eax, ds:2[rax*2]
0x180035047  mov     rcx, [rbp+57h+hKey]; hKey
0x18003504b  mov     r9d, 1; dwType
0x180035051  mov     [rsp+0D0h+cbData], eax; cbData
0x180035055  xor     r8d, r8d; Reserved
0x180035058  mov     [rsp+0D0h+phkResult], rdi; lpData
0x18003505d  call    cs:__imp_RegSetValueExW
0x180035063  mov     r9d, eax
0x180035066  test    eax, eax
0x180035068  jz      short loc_1800350C0
0x18003506a  mov     rcx, cs:WPP_GLOBAL_Control
0x180035071  lea     rax, WPP_GLOBAL_Control
0x180035078  cmp     rcx, rax
0x18003507b  jz      short loc_180035098
0x18003507d  test    byte ptr [rcx+1Ch], 1
0x180035081  jz      short loc_180035098
0x180035083  mov     rcx, [rcx+10h]
0x180035087  lea     r8, WPP_928a4490cd403d1d5470036a68085293_Traceguids
0x18003508e  mov     edx, 38h ; '8'
0x180035093  call    WPP_SF_d
0x180035098  mov     ebx, 80004005h
0x18003509d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800350a1  test    rcx, rcx
0x1800350a4  jz      short loc_1800350C3
0x1800350a6  mov     rdx, [r14+8]; lpValueName
0x1800350aa  call    cs:__imp_RegDeleteValueW
0x1800350b0  jmp     short loc_1800350C3
0x1800350b2  mov     rdx, [r14+8]; lpValueName
0x1800350b6  mov     rcx, [rbp+57h+hKey]; hKey
0x1800350ba  call    cs:__imp_RegDeleteValueW
0x1800350c0  mov     ebx, r15d
0x1800350c3  mov     rcx, [rbp+57h+var_30]; void *
0x1800350c7  lea     rax, [rbp+57h+var_20]
0x1800350cb  cmp     rcx, rax
0x1800350ce  jz      short loc_1800350DC
0x1800350d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800350d7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800350dc  test    rdi, rdi
0x1800350df  jz      short loc_1800350E9
0x1800350e1  mov     rcx, rdi; void *
0x1800350e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800350e9  mov     rcx, [rbp+57h+var_60]; void *
0x1800350ed  lea     rax, [rbp+57h+var_50]
0x1800350f1  cmp     rcx, rax
0x1800350f4  jz      short loc_180035102
0x1800350f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800350fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035102  mov     rcx, [rbp+57h+var_80]; void *
0x180035106  lea     rax, [rbp+57h+var_70]
0x18003510a  cmp     rcx, rax
0x18003510d  jz      short loc_18003511B
0x18003510f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180035116  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003511b  mov     rcx, [rbp+57h+var_98]; void *
0x18003511f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180035123  jz      short loc_180035135
0x180035125  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003512c  mov     qword ptr [rbp+57h+var_90], rcx
0x180035130  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180035135  mov     rcx, [rbp+57h+hKey]; hKey
0x180035139  test    rcx, rcx
0x18003513c  jz      short loc_180035144
0x18003513e  call    cs:__imp_RegCloseKey
0x180035144  lea     r11, [rsp+0D0h+var_10]
0x18003514c  mov     eax, ebx
0x18003514e  mov     rbx, [r11+20h]
0x180035152  mov     rdi, [r11+38h]
0x180035156  mov     rsp, r11
0x180035159  pop     r15
0x18003515b  pop     r14
0x18003515d  pop     rbp
0x18003515e  retn
```
