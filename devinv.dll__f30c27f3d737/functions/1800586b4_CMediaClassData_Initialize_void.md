# CMediaClassData::Initialize(void)

- ea: `0x1800586b4`
- end: `0x1800589e1`
- name: `?Initialize@CMediaClassData@@QEAAJXZ`
- size: `813`
- prototype: `__int64 __fastcall(CMediaClassData *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ddc0`

## callees

- `0x180005e40`
- `0x180006eb8`
- `0x18000fa50`
- `0x1800103e0`
- `0x180016440`
- `0x18005823c`
- `0x1800586b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005870b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800587c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005870b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800587c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005879c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800589b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005879c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800589b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005877a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180058827`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005877a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180058827`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaClassData::Initialize(CMediaClassData *this)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  bool v4; // cc
  DWORD i; // r14d
  __int64 v6; // r8
  DWORD j; // r14d
  __int64 v8; // r8
  unsigned __int64 v9; // rdx
  void **v10; // rdi
  __int64 v11; // rbx
  void **v12; // r8
  unsigned __int64 v13; // rdx
  void **v14; // rdi
  __int64 v15; // rbx
  void **v16; // r8
  DWORD cchName; // [rsp+40h] [rbp-278h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-270h] BYREF
  int v20; // [rsp+50h] [rbp-268h]
  void *Src[2]; // [rsp+58h] [rbp-260h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp-250h]
  unsigned __int64 v23; // [rsp+70h] [rbp-248h]
  WCHAR Name[264]; // [rsp+80h] [rbp-238h] BYREF

  cchName = 0;
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\Audio\\Capture",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  v4 = v2 <= 0;
  if ( !v2 )
  {
    for ( i = 0; ; ++i )
    {
      *(_OWORD *)Src = 0;
      v22 = 0;
      v23 = 7;
      LOWORD(Src[0]) = 0;
      cchName = 259;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      v13 = -1;
      do
        ++v13;
      while ( Name[v13] );
      if ( v13 > v23 )
      {
        try
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
            Src,
            v13,
            v6,
            Name);
        }
        catch ( std::bad_alloc )
        {
          v20 = -2147024888;
          goto LABEL_30;
        }
      }
      else
      {
        v14 = Src;
        if ( v23 > 7 )
          v14 = (void **)Src[0];
        v22 = v13;
        v15 = 2 * v13;
        memmove_0(v14, Name, 2 * v13);
        *(_WORD *)((char *)v14 + v15) = 0;
      }
      std::wstring::append(Src, L"\\properties");
      v16 = Src;
      if ( v23 > 7 )
        v16 = (void **)Src[0];
      CMediaClassData::GetAudioDeviceInstance(this, hKey, v16, 0);
      std::wstring::~wstring(Src);
    }
    std::wstring::~wstring(Src);
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v2 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\MMDevices\\Audio\\Render",
           0,
           0x20019u,
           &hKey);
    v3 = v2;
    v4 = v2 <= 0;
    if ( !v2 )
    {
      for ( j = 0; ; ++j )
      {
        *(_OWORD *)Src = 0;
        v22 = 0;
        v23 = 7;
        LOWORD(Src[0]) = 0;
        cchName = 259;
        if ( RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0) )
        {
          std::wstring::~wstring(Src);
          v3 = 0;
          goto LABEL_31;
        }
        v9 = -1;
        do
          ++v9;
        while ( Name[v9] );
        if ( v9 > v23 )
        {
          try
          {
            std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
              Src,
              v9,
              v8,
              Name);
          }
          catch ( std::bad_alloc )
          {
            v20 = -2147024888;
LABEL_30:
            std::wstring::~wstring(Src);
            v3 = v20;
            goto LABEL_31;
          }
        }
        else
        {
          v10 = Src;
          if ( v23 > 7 )
            v10 = (void **)Src[0];
          v22 = v9;
          v11 = 2 * v9;
          memmove_0(v10, Name, 2 * v9);
          *(_WORD *)((char *)v10 + v11) = 0;
        }
        std::wstring::append(Src, L"\\properties");
        v12 = Src;
        if ( v23 > 7 )
          v12 = (void **)Src[0];
        CMediaClassData::GetAudioDeviceInstance(this, hKey, v12, 1);
        std::wstring::~wstring(Src);
      }
    }
  }
  if ( !v4 )
    v3 = (unsigned __int16)v2 | 0x80070000;
LABEL_31:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x1800586b4  mov     [rsp+arg_8], rbx
0x1800586b9  mov     [rsp+arg_10], rsi
0x1800586be  push    rdi
0x1800586bf  push    r14
0x1800586c1  push    r15
0x1800586c3  sub     rsp, 2A0h
0x1800586ca  mov     rax, cs:__security_cookie
0x1800586d1  xor     rax, rsp
0x1800586d4  mov     [rsp+2B8h+var_28], rax
0x1800586dc  mov     r15, rcx
0x1800586df  xor     esi, esi
0x1800586e1  mov     [rsp+2B8h+cchName], esi
0x1800586e5  mov     [rsp+2B8h+hKey], rsi
0x1800586ea  lea     rax, [rsp+2B8h+hKey]
0x1800586ef  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1800586f4  mov     r9d, 20019h; samDesired
0x1800586fa  xor     r8d, r8d; ulOptions
0x1800586fd  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180058704  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005870b  call    cs:__imp_RegOpenKeyExW
0x180058711  mov     ebx, eax
0x180058713  test    eax, eax
0x180058715  jz      short loc_18005872B
0x180058717  jle     loc_1800589A6
0x18005871d  movzx   ebx, ax
0x180058720  or      ebx, 80070000h
0x180058726  jmp     loc_1800589A6
0x18005872b  mov     r14d, esi
0x18005872e  xorps   xmm0, xmm0
0x180058731  movups  xmmword ptr [rsp+2B8h+Src], xmm0
0x180058736  mov     [rsp+2B8h+var_250], rsi
0x18005873b  mov     [rsp+2B8h+var_248], 7
0x180058744  mov     word ptr [rsp+2B8h+Src], si
0x180058749  mov     [rsp+2B8h+cchName], 103h
0x180058751  mov     [rsp+2B8h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180058756  mov     [rsp+2B8h+lpcchClass], rsi; lpcchClass
0x18005875b  mov     [rsp+2B8h+lpClass], rsi; lpClass
0x180058760  mov     [rsp+2B8h+phkResult], rsi; lpReserved
0x180058765  lea     r9, [rsp+2B8h+cchName]; lpcchName
0x18005876a  lea     r8, [rsp+2B8h+Name]; lpName
0x180058772  mov     edx, r14d; dwIndex
0x180058775  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18005877a  call    cs:__imp_RegEnumKeyExW
0x180058780  test    eax, eax
0x180058782  jz      loc_1800588F1
0x180058788  lea     rcx, [rsp+2B8h+Src]; void *
0x18005878d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058792  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180058797  test    rcx, rcx
0x18005879a  jz      short loc_1800587A7
0x18005879c  call    cs:__imp_RegCloseKey
0x1800587a2  mov     [rsp+2B8h+hKey], rsi
0x1800587a7  lea     rax, [rsp+2B8h+hKey]
0x1800587ac  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1800587b1  mov     r9d, 20019h; samDesired
0x1800587b7  xor     r8d, r8d; ulOptions
0x1800587ba  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800587c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800587c8  call    cs:__imp_RegOpenKeyExW
0x1800587ce  mov     ebx, eax
0x1800587d0  test    eax, eax
0x1800587d2  jnz     loc_180058717
0x1800587d8  mov     r14d, esi
0x1800587db  xorps   xmm0, xmm0
0x1800587de  movups  xmmword ptr [rsp+2B8h+Src], xmm0
0x1800587e3  mov     [rsp+2B8h+var_250], rsi
0x1800587e8  mov     [rsp+2B8h+var_248], 7
0x1800587f1  mov     word ptr [rsp+2B8h+Src], si
0x1800587f6  mov     [rsp+2B8h+cchName], 103h
0x1800587fe  mov     [rsp+2B8h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180058803  mov     [rsp+2B8h+lpcchClass], rsi; lpcchClass
0x180058808  mov     [rsp+2B8h+lpClass], rsi; lpClass
0x18005880d  mov     [rsp+2B8h+phkResult], rsi; lpReserved
0x180058812  lea     r9, [rsp+2B8h+cchName]; lpcchName
0x180058817  lea     r8, [rsp+2B8h+Name]; lpName
0x18005881f  mov     edx, r14d; dwIndex
0x180058822  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180058827  call    cs:__imp_RegEnumKeyExW
0x18005882d  test    eax, eax
0x18005882f  jz      short loc_180058842
0x180058831  lea     rcx, [rsp+2B8h+Src]; void *
0x180058836  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005883b  mov     ebx, esi
0x18005883d  jmp     loc_1800589A6
0x180058842  lea     rax, [rsp+2B8h+Name]
0x18005884a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005884e  inc     rdx
0x180058851  cmp     [rax+rdx*2], si
0x180058855  jnz     short loc_18005884E
0x180058857  cmp     rdx, [rsp+2B8h+var_248]
0x18005885c  ja      short loc_180058891
0x18005885e  lea     rdi, [rsp+2B8h+Src]
0x180058863  cmp     [rsp+2B8h+var_248], 7
0x180058869  cmova   rdi, [rsp+2B8h+Src]
0x18005886f  mov     [rsp+2B8h+var_250], rdx
0x180058874  lea     rbx, [rdx+rdx]
0x180058878  mov     r8, rbx; Size
0x18005887b  lea     rdx, [rsp+2B8h+Name]; Src
0x180058883  mov     rcx, rdi; void *
0x180058886  call    memmove_0
0x18005888b  mov     [rbx+rdi], si
0x18005888f  jmp     short loc_1800588A3
0x180058891  lea     r9, [rsp+2B8h+Name]
0x180058899  lea     rcx, [rsp+2B8h+Src]
0x18005889e  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800588a3  lea     rdx, aProperties; "\\properties"
0x1800588aa  lea     rcx, [rsp+2B8h+Src]; Src
0x1800588af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800588b4  nop
0x1800588b5  lea     r8, [rsp+2B8h+Src]
0x1800588ba  cmp     [rsp+2B8h+var_248], 7
0x1800588c0  cmova   r8, [rsp+2B8h+Src]
0x1800588c6  mov     r9d, 1
0x1800588cc  mov     rdx, [rsp+2B8h+hKey]
0x1800588d1  mov     rcx, r15
0x1800588d4  call    ?GetAudioDeviceInstance@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGW4MEDIA_AUDIO_DEVICE_TYPE@@@Z; CMediaClassData::GetAudioDeviceInstance(HKEY__ *,ushort const *,MEDIA_AUDIO_DEVICE_TYPE)
0x1800588d9  nop
0x1800588da  lea     rcx, [rsp+2B8h+Src]; void *
0x1800588df  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800588e4  inc     r14d
0x1800588e7  jmp     loc_1800587DB
0x1800588ec  jmp     loc_180058998
0x1800588f1  lea     rax, [rsp+2B8h+Name]
0x1800588f9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800588fd  inc     rdx
0x180058900  cmp     [rax+rdx*2], si
0x180058904  jnz     short loc_1800588FD
0x180058906  cmp     rdx, [rsp+2B8h+var_248]
0x18005890b  ja      short loc_180058940
0x18005890d  lea     rdi, [rsp+2B8h+Src]
0x180058912  cmp     [rsp+2B8h+var_248], 7
0x180058918  cmova   rdi, [rsp+2B8h+Src]
0x18005891e  mov     [rsp+2B8h+var_250], rdx
0x180058923  lea     rbx, [rdx+rdx]
0x180058927  mov     r8, rbx; Size
0x18005892a  lea     rdx, [rsp+2B8h+Name]; Src
0x180058932  mov     rcx, rdi; void *
0x180058935  call    memmove_0
0x18005893a  mov     [rbx+rdi], si
0x18005893e  jmp     short loc_180058952
0x180058940  lea     r9, [rsp+2B8h+Name]
0x180058948  lea     rcx, [rsp+2B8h+Src]
0x18005894d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180058952  lea     rdx, aProperties; "\\properties"
0x180058959  lea     rcx, [rsp+2B8h+Src]; Src
0x18005895e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180058963  nop
0x180058964  lea     r8, [rsp+2B8h+Src]
0x180058969  cmp     [rsp+2B8h+var_248], 7
0x18005896f  cmova   r8, [rsp+2B8h+Src]
0x180058975  xor     r9d, r9d
0x180058978  mov     rdx, [rsp+2B8h+hKey]
0x18005897d  mov     rcx, r15
0x180058980  call    ?GetAudioDeviceInstance@CMediaClassData@@AEAAJPEAUHKEY__@@PEBGW4MEDIA_AUDIO_DEVICE_TYPE@@@Z; CMediaClassData::GetAudioDeviceInstance(HKEY__ *,ushort const *,MEDIA_AUDIO_DEVICE_TYPE)
0x180058985  nop
0x180058986  lea     rcx, [rsp+2B8h+Src]; void *
0x18005898b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180058990  inc     r14d
0x180058993  jmp     loc_18005872E
0x180058998  lea     rcx, [rsp+2B8h+Src]; void *
0x18005899d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800589a2  mov     ebx, [rsp+2B8h+var_268]
0x1800589a6  mov     rcx, [rsp+2B8h+hKey]; hKey
0x1800589ab  test    rcx, rcx
0x1800589ae  jz      short loc_1800589B6
0x1800589b0  call    cs:__imp_RegCloseKey
0x1800589b6  mov     eax, ebx
0x1800589b8  mov     rcx, [rsp+2B8h+var_28]
0x1800589c0  xor     rcx, rsp; StackCookie
0x1800589c3  call    __security_check_cookie
0x1800589c8  lea     r11, [rsp+2B8h+var_18]
0x1800589d0  mov     rbx, [r11+28h]
0x1800589d4  mov     rsi, [r11+30h]
0x1800589d8  mov     rsp, r11
0x1800589db  pop     r15
0x1800589dd  pop     r14
0x1800589df  pop     rdi
0x1800589e0  retn
```
