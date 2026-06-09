# CFvePolicyReader::ReadMultiString(eFveGpMultiStrSetting,MULTI_STRING_ARRAY *)

- ea: `0x18002ab90`
- end: `0x18002adc9`
- name: `?ReadMultiString@CFvePolicyReader@@UEBAJW4eFveGpMultiStrSetting@@PEAUMULTI_STRING_ARRAY@@@Z`
- size: `569`
- prototype: `__int64 __fastcall(__int64, int, _OWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x180002028`
- `0x1800022d8`
- `0x18000b978`
- `0x180029e18`
- `0x18002a984`
- `0x18002a99c`
- `0x18002a9ec`
- `0x18002ab90`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18002ac16`
- `ADVAPI32!RegGetValueW` at `0x18002aca2`
- `ADVAPI32!RegGetValueW` at `0x18002ac16`
- `ADVAPI32!RegGetValueW` at `0x18002aca2`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::ReadMultiString(__int64 a1, int a2, _OWORD *a3)
{
  unsigned __int64 v3; // r15
  __int64 v5; // rsi
  void *pvData; // rdi
  int v7; // edx
  int KeyForGpLocation; // ebx
  const WCHAR *v9; // rsi
  LSTATUS ValueW; // eax
  unsigned __int64 v11; // rax
  LSTATUS v12; // eax
  unsigned __int64 v13; // r14
  const unsigned __int16 *i; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // r12
  const unsigned __int16 *FirstMultiString; // rax
  __int16 v18; // r11
  const unsigned __int16 *v19; // rsi
  __int64 v20; // rax
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rax
  unsigned __int64 v23; // kr10_8
  unsigned __int16 *v24; // rax
  HKEY hkey; // [rsp+40h] [rbp-20h] BYREF
  __int128 v27; // [rsp+48h] [rbp-18h] BYREF
  DWORD pcbData; // [rsp+A8h] [rbp+48h] BYREF
  LPCWSTR lpSubKey; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  lpSubKey = 0;
  pcbData = 0;
  hkey = 0;
  v5 = 3LL * a2;
  pvData = 0;
  v7 = g_MultiStringSettingMap[3 * a2];
  v27 = 0;
  KeyForGpLocation = CFvePolicyReader::GetKeyForGpLocation(a1, v7, &hkey, &lpSubKey);
  if ( KeyForGpLocation >= 0 )
  {
    v9 = (const WCHAR *)g_MultiStringSettingMap[v5 + 1];
    ValueW = RegGetValueW(hkey, lpSubKey, v9, 0x20u, 0, 0, &pcbData);
    KeyForGpLocation = ValueW;
    if ( ValueW > 0 )
      KeyForGpLocation = (unsigned __int16)ValueW | 0x80070000;
    if ( KeyForGpLocation >= 0 )
    {
      if ( !pcbData )
      {
        KeyForGpLocation = -2147467259;
        goto LABEL_31;
      }
      v11 = 2 * ((unsigned __int64)pcbData >> 1);
      if ( !is_mul_ok((unsigned __int64)pcbData >> 1, 2u) )
        v11 = -1;
      pvData = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
      if ( !pvData )
        goto LABEL_10;
      v12 = RegGetValueW(hkey, lpSubKey, v9, 0x20u, 0, pvData, &pcbData);
      KeyForGpLocation = v12;
      if ( v12 > 0 )
        KeyForGpLocation = (unsigned __int16)v12 | 0x80070000;
      if ( KeyForGpLocation >= 0 )
      {
        v13 = 0;
        for ( i = CFvePolicyReader::GetFirstMultiString((const unsigned __int16 *)pvData);
              i;
              i = CFvePolicyReader::GetNextMultiString(i) )
        {
          ++v13;
        }
        *((_QWORD *)&v27 + 1) = v13;
        v15 = 8 * v13;
        if ( !is_mul_ok(v13, 8u) )
          v15 = -1;
        *(_QWORD *)&v27 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
        v16 = v27;
        if ( !(_QWORD)v27 )
        {
LABEL_10:
          KeyForGpLocation = -2147024882;
          goto LABEL_31;
        }
        FirstMultiString = CFvePolicyReader::GetFirstMultiString((const unsigned __int16 *)pvData);
        v18 = 0;
        while ( 1 )
        {
          v19 = FirstMultiString;
          if ( !FirstMultiString || v3 >= v13 )
            break;
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] != v18 );
          v21 = v20 + 1;
          v23 = v20 + 1;
          v22 = 2 * (v20 + 1);
          if ( !is_mul_ok(v23, 2u) )
            v22 = -1;
          v24 = (unsigned __int16 *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)(v16 + 8 * v3) = v24;
          if ( !v24 )
            goto LABEL_10;
          KeyForGpLocation = StringCchCopyW(v24, v21, v19);
          if ( KeyForGpLocation < 0 )
            goto LABEL_31;
          FirstMultiString = CFvePolicyReader::GetNextMultiString(v19);
          ++v3;
        }
        *a3 = v27;
        v27 = 0;
      }
    }
  }
LABEL_31:
  CFvePolicySettings::FreeMultiStringArray((struct MULTI_STRING_ARRAY *)&v27);
  if ( pvData )
    operator delete(pvData);
  return (unsigned int)KeyForGpLocation;
}

```

## disassembly

```asm
0x18002ab90  mov     [rsp-38h+arg_0], rbx
0x18002ab95  push    rbp
0x18002ab96  push    rsi
0x18002ab97  push    rdi
0x18002ab98  push    r12
0x18002ab9a  push    r13
0x18002ab9c  push    r14
0x18002ab9e  push    r15
0x18002aba0  mov     rbp, rsp
0x18002aba3  sub     rsp, 60h
0x18002aba7  xor     r15d, r15d
0x18002abaa  movsxd  rax, edx
0x18002abad  lea     r14, ?g_MultiStringSettingMap@@3QBU?$POLICY_REGISTRY_INFO@PEAPEBG@@B; POLICY_REGISTRY_INFO<ushort const * *> const near * const g_MultiStringSettingMap
0x18002abb4  mov     [rbp+lpSubKey], r15
0x18002abb8  mov     r13, r8
0x18002abbb  mov     [rbp+arg_8], r15d
0x18002abbf  xorps   xmm0, xmm0
0x18002abc2  mov     [rbp+hkey], r15
0x18002abc6  lea     rsi, [rax+rax*2]
0x18002abca  mov     edi, r15d
0x18002abcd  mov     edx, [r14+rsi*8]
0x18002abd1  lea     r9, [rbp+lpSubKey]
0x18002abd5  lea     r8, [rbp+hkey]
0x18002abd9  movups  [rbp+var_18], xmm0
0x18002abdd  call    ?GetKeyForGpLocation@CFvePolicyReader@@AEBAJW4eFveGpSettingsLocation@@PEAPEAUHKEY__@@PEAPEBG@Z; CFvePolicyReader::GetKeyForGpLocation(eFveGpSettingsLocation,HKEY__ * *,ushort const * *)
0x18002abe2  mov     ebx, eax
0x18002abe4  test    eax, eax
0x18002abe6  js      loc_18002AD99
0x18002abec  mov     rsi, [r14+rsi*8+8]
0x18002abf1  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002abf5  lea     rax, [rbp+arg_8]
0x18002abf9  mov     rcx, [rbp+hkey]; hkey
0x18002abfd  lea     r12d, [r15+20h]
0x18002ac01  mov     [rsp+60h+pcbData], rax; pcbData
0x18002ac06  mov     r9d, r12d; dwFlags
0x18002ac09  mov     [rsp+60h+pvData], r15; pvData
0x18002ac0e  mov     r8, rsi; lpValue
0x18002ac11  mov     [rsp+60h+pdwType], r15; pdwType
0x18002ac16  call    cs:__imp_RegGetValueW
0x18002ac1c  mov     ebx, eax
0x18002ac1e  mov     r14d, 80070000h
0x18002ac24  test    eax, eax
0x18002ac26  jle     short loc_18002AC2E
0x18002ac28  movzx   ebx, ax
0x18002ac2b  or      ebx, r14d
0x18002ac2e  test    ebx, ebx
0x18002ac30  js      loc_18002AD99
0x18002ac36  mov     eax, [rbp+arg_8]
0x18002ac39  test    eax, eax
0x18002ac3b  jnz     short loc_18002AC47
0x18002ac3d  mov     ebx, 80004005h
0x18002ac42  jmp     loc_18002AD99
0x18002ac47  mov     rcx, rax
0x18002ac4a  mov     eax, 2
0x18002ac4f  shr     rcx, 1
0x18002ac52  mul     rcx
0x18002ac55  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ac5c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ac63  cmovb   rax, rcx
0x18002ac67  mov     rcx, rax; unsigned __int64
0x18002ac6a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ac6f  mov     rdi, rax
0x18002ac72  test    rax, rax
0x18002ac75  jnz     short loc_18002AC81
0x18002ac77  mov     ebx, 8007000Eh
0x18002ac7c  jmp     loc_18002AD99
0x18002ac81  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002ac85  lea     rax, [rbp+arg_8]
0x18002ac89  mov     rcx, [rbp+hkey]; hkey
0x18002ac8d  mov     r9d, r12d; dwFlags
0x18002ac90  mov     [rsp+60h+pcbData], rax; pcbData
0x18002ac95  mov     r8, rsi; lpValue
0x18002ac98  mov     [rsp+60h+pvData], rdi; pvData
0x18002ac9d  mov     [rsp+60h+pdwType], r15; pdwType
0x18002aca2  call    cs:__imp_RegGetValueW
0x18002aca8  mov     ebx, eax
0x18002acaa  test    eax, eax
0x18002acac  jle     short loc_18002ACB4
0x18002acae  movzx   ebx, ax
0x18002acb1  or      ebx, r14d
0x18002acb4  test    ebx, ebx
0x18002acb6  js      loc_18002AD99
0x18002acbc  mov     rcx, rdi; unsigned __int16 *
0x18002acbf  mov     r14, r15
0x18002acc2  call    ?GetFirstMultiString@CFvePolicyReader@@CAPEBGPEBG@Z; CFvePolicyReader::GetFirstMultiString(ushort const *)
0x18002acc7  jmp     short loc_18002ACD4
0x18002acc9  inc     r14
0x18002accc  mov     rcx, rax; unsigned __int16 *
0x18002accf  call    ?GetNextMultiString@CFvePolicyReader@@CAPEBGPEBG@Z; CFvePolicyReader::GetNextMultiString(ushort const *)
0x18002acd4  test    rax, rax
0x18002acd7  jnz     short loc_18002ACC9
0x18002acd9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002ace0  mov     qword ptr [rbp+var_18+8], r14
0x18002ace4  mov     eax, 8
0x18002ace9  mul     r14
0x18002acec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002acf3  cmovb   rax, rcx
0x18002acf7  mov     rcx, rax; unsigned __int64
0x18002acfa  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002acff  mov     qword ptr [rbp+var_18], rax
0x18002ad03  mov     r12, rax
0x18002ad06  test    rax, rax
0x18002ad09  jz      loc_18002AC77
0x18002ad0f  mov     rcx, rdi; unsigned __int16 *
0x18002ad12  call    ?GetFirstMultiString@CFvePolicyReader@@CAPEBGPEBG@Z; CFvePolicyReader::GetFirstMultiString(ushort const *)
0x18002ad17  xor     r11d, r11d
0x18002ad1a  mov     rsi, rax
0x18002ad1d  test    rax, rax
0x18002ad20  jz      short loc_18002AD88
0x18002ad22  cmp     r15, r14
0x18002ad25  jnb     short loc_18002AD88
0x18002ad27  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002ad2b  mov     rax, rcx
0x18002ad2e  inc     rax
0x18002ad31  cmp     [rsi+rax*2], r11w
0x18002ad36  jnz     short loc_18002AD2E
0x18002ad38  lea     rbx, [rax+1]
0x18002ad3c  mov     eax, 2
0x18002ad41  mul     rbx
0x18002ad44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002ad4b  cmovb   rax, rcx
0x18002ad4f  mov     rcx, rax; unsigned __int64
0x18002ad52  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002ad57  xor     r11d, r11d
0x18002ad5a  mov     [r12+r15*8], rax
0x18002ad5e  test    rax, rax
0x18002ad61  jz      loc_18002AC77
0x18002ad67  mov     r8, rsi; unsigned __int16 *
0x18002ad6a  mov     rdx, rbx; unsigned __int64
0x18002ad6d  mov     rcx, rax; unsigned __int16 *
0x18002ad70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ad75  mov     ebx, eax
0x18002ad77  test    eax, eax
0x18002ad79  js      short loc_18002AD99
0x18002ad7b  mov     rcx, rsi; unsigned __int16 *
0x18002ad7e  call    ?GetNextMultiString@CFvePolicyReader@@CAPEBGPEBG@Z; CFvePolicyReader::GetNextMultiString(ushort const *)
0x18002ad83  inc     r15
0x18002ad86  jmp     short loc_18002AD1A
0x18002ad88  movups  xmm0, [rbp+var_18]
0x18002ad8c  xorps   xmm1, xmm1
0x18002ad8f  movdqu  xmmword ptr [r13+0], xmm0
0x18002ad95  movups  [rbp+var_18], xmm1
0x18002ad99  lea     rcx, [rbp+var_18]; struct MULTI_STRING_ARRAY *
0x18002ad9d  call    ?FreeMultiStringArray@CFvePolicySettings@@SAXPEAUMULTI_STRING_ARRAY@@@Z; CFvePolicySettings::FreeMultiStringArray(MULTI_STRING_ARRAY *)
0x18002ada2  test    rdi, rdi
0x18002ada5  jz      short loc_18002ADAF
0x18002ada7  mov     rcx, rdi; Block
0x18002adaa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002adaf  mov     eax, ebx
0x18002adb1  mov     rbx, [rsp+60h+arg_0]
0x18002adb9  add     rsp, 60h
0x18002adbd  pop     r15
0x18002adbf  pop     r14
0x18002adc1  pop     r13
0x18002adc3  pop     r12
0x18002adc5  pop     rdi
0x18002adc6  pop     rsi
0x18002adc7  pop     rbp
0x18002adc8  retn
```
