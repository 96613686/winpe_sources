# CAppRecorderPlugin::RemoveAppCompatLayer(void)

- ea: `0x18002fb3c`
- end: `0x18002fe90`
- name: `?RemoveAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ`
- size: `852`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f330`

## callees

- `0x180002890`
- `0x180002e80`
- `0x180009f00`
- `0x18000a004`
- `0x18002fb3c`
- `0x180049310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002fc09`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18002fc09`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002fc21`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002fc35`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002fc21`
- `api-ms-win-crt-private-l1-1-0!_o_isspace` at `0x18002fc35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fcb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fd98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fdda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fe0f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fd8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002fd8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fe5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002fe5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fbb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002fbb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002fc86`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fcb2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002fcb2`

## string_xrefs

- `0x18002fb8c`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x18002fc78`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`
- `0x18002fd7a`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers`

## pseudocode

```c
__int64 __fastcall CAppRecorderPlugin::RemoveAppCompatLayer(CAppRecorderPlugin *this)
{
  const WCHAR *v1; // r8
  CAppRecorderPlugin *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // r14
  __int64 v7; // r12
  __int64 v8; // rdx
  HKEY *v9; // rax
  signed int v10; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  unsigned __int64 v15; // rcx
  unsigned int v16; // ebx
  BYTE *v17; // rcx
  _WORD *v18; // rdx
  size_t v19; // r8
  signed int v20; // eax
  signed int v21; // eax
  signed int LastError; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  CAppRecorderPlugin *v25; // [rsp+48h] [rbp-B8h]
  HKEY hKey[2]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v28[253]; // [rsp+76h] [rbp-8Ah] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 1);
  v25 = this;
  v2 = this;
  hKey[0] = 0;
  pcbData = 520;
  *(_WORD *)Data = 0;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
         v1,
         2u,
         0,
         Data,
         &pcbData)
    || pcbData < 2 )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 50;
      goto LABEL_49;
    }
  }
  else
  {
    v3 = -1;
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Data[2 * v4] );
    if ( (unsigned int)v4 >= 0xB )
    {
      v5 = 0;
      while ( 1 )
      {
        if ( !(unsigned int)_o__wcsnicmp(&Data[2 * v5], L"AppRecorder", 11) )
        {
          v6 = v5 - 1;
          if ( !v5 || (unsigned int)_o_isspace(*(unsigned __int16 *)&Data[2 * v6]) )
          {
            v7 = v5 + 11;
            if ( (unsigned int)_o_isspace(*(unsigned __int16 *)&Data[2 * v7]) || !*(_WORD *)&Data[2 * v7] )
              break;
          }
        }
        if ( ++v5 > (int)v4 - 11 )
          goto LABEL_13;
      }
      v14 = v5;
      if ( v5 )
        v14 = (unsigned int)v6;
      v15 = 2 * v14;
      if ( (unsigned int)v7 < (unsigned int)v4 )
      {
        v16 = v4 - v5 - 11;
        v17 = &Data[v15];
        v18 = &v28[v5];
        if ( (_DWORD)v14 )
        {
          v19 = 2LL * (v16 + 1);
        }
        else
        {
          v19 = 2LL * v16;
          ++v18;
        }
        memmove_0(v17, v18, v19);
      }
      else
      {
        if ( v15 >= 0x208 )
          _report_rangecheckfailure(v15, v8, (unsigned int)v14);
        *(_WORD *)&Data[2 * v14] = 0;
      }
LABEL_13:
      v2 = v25;
    }
    v9 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    if ( RegOpenKeyExW(
           HKEY_CURRENT_USER,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
           0,
           2u,
           v9)
      || !hKey[0] )
    {
      v21 = GetLastError();
      v11 = v21;
      if ( v21 > 0 )
        v11 = (unsigned __int16)v21 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 51;
        goto LABEL_49;
      }
    }
    else if ( *(_WORD *)Data )
    {
      do
        ++v3;
      while ( *(_WORD *)&Data[2 * v3] );
      if ( !RegSetValueExW(
              hKey[0],
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\Layers",
              0,
              1u,
              Data,
              2 * v3) )
      {
        v11 = 0;
        goto LABEL_50;
      }
      v20 = GetLastError();
      v11 = v20;
      if ( v20 > 0 )
        v11 = (unsigned __int16)v20 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 53;
        goto LABEL_49;
      }
    }
    else
    {
      RegDeleteValueW(hKey[0], *((LPCWSTR *)v2 + 1));
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v13 = 52;
LABEL_49:
        WPP_SF_d(v12[2], v13, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v11);
      }
    }
  }
LABEL_50:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return v11;
}

```

## disassembly

```asm
0x18002fb3c  push    rbp
0x18002fb3e  push    rbx
0x18002fb3f  push    rsi
0x18002fb40  push    rdi
0x18002fb41  push    r12
0x18002fb43  push    r13
0x18002fb45  push    r14
0x18002fb47  push    r15
0x18002fb49  lea     rbp, [rsp-188h]
0x18002fb51  sub     rsp, 288h
0x18002fb58  mov     rax, cs:__security_cookie
0x18002fb5f  xor     rax, rsp
0x18002fb62  mov     [rbp+1C0h+var_50], rax
0x18002fb69  mov     r8, [rcx+8]; lpValue
0x18002fb6d  lea     rax, [rsp+2C0h+var_280]
0x18002fb72  xor     r13d, r13d
0x18002fb75  mov     [rsp+2C0h+pcbData], rax; pcbData
0x18002fb7a  lea     rax, [rsp+2C0h+Data]
0x18002fb7f  mov     [rsp+2C0h+var_278], rcx
0x18002fb84  mov     rdi, rcx
0x18002fb87  mov     [rsp+2C0h+pvData], rax; pvData
0x18002fb8c  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002fb93  mov     [rsp+2C0h+pdwType], r13; pdwType
0x18002fb98  lea     r9d, [r13+2]; dwFlags
0x18002fb9c  mov     [rsp+2C0h+hKey], r13
0x18002fba1  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18002fba8  mov     [rsp+2C0h+var_280], 208h
0x18002fbb0  mov     word ptr [rsp+2C0h+Data], r13w
0x18002fbb6  call    cs:__imp_RegGetValueW
0x18002fbbc  test    eax, eax
0x18002fbbe  jnz     loc_18002FE0F
0x18002fbc4  cmp     [rsp+2C0h+var_280], 2
0x18002fbc9  jb      loc_18002FE0F
0x18002fbcf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002fbd3  lea     rax, [rsp+2C0h+Data]
0x18002fbd8  mov     rbx, rsi
0x18002fbdb  inc     rbx
0x18002fbde  cmp     [rax+rbx*2], r13w
0x18002fbe3  jnz     short loc_18002FBDB
0x18002fbe5  cmp     ebx, 0Bh
0x18002fbe8  jb      short loc_18002FC60
0x18002fbea  mov     edi, r13d
0x18002fbed  lea     r13d, [rbx-0Bh]
0x18002fbf1  mov     eax, edi
0x18002fbf3  lea     rcx, [rsp+2C0h+Data]
0x18002fbf8  mov     r8d, 0Bh
0x18002fbfe  lea     rdx, aApprecorder; "AppRecorder"
0x18002fc05  lea     rcx, [rcx+rax*2]
0x18002fc09  call    cs:__imp__o__wcsnicmp
0x18002fc0f  test    eax, eax
0x18002fc11  jnz     short loc_18002FC51
0x18002fc13  lea     r14d, [rdi-1]
0x18002fc17  test    edi, edi
0x18002fc19  jz      short loc_18002FC2B
0x18002fc1b  movzx   ecx, word ptr [rsp+r14*2+2C0h+Data]
0x18002fc21  call    cs:__imp__o_isspace
0x18002fc27  test    eax, eax
0x18002fc29  jz      short loc_18002FC51
0x18002fc2b  lea     r12d, [rdi+0Bh]
0x18002fc2f  movzx   ecx, word ptr [rsp+r12*2+2C0h+Data]
0x18002fc35  call    cs:__imp__o_isspace
0x18002fc3b  xor     ecx, ecx
0x18002fc3d  test    eax, eax
0x18002fc3f  jnz     loc_18002FCF8
0x18002fc45  cmp     word ptr [rsp+r12*2+2C0h+Data], cx
0x18002fc4b  jz      loc_18002FCF8
0x18002fc51  inc     edi
0x18002fc53  cmp     edi, r13d
0x18002fc56  jbe     short loc_18002FBF1
0x18002fc58  xor     r13d, r13d
0x18002fc5b  mov     rdi, [rsp+2C0h+var_278]
0x18002fc60  lea     rcx, [rsp+2C0h+hKey]
0x18002fc65  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002fc6a  mov     r9d, 2; samDesired
0x18002fc70  mov     [rsp+2C0h+pdwType], rax; phkResult
0x18002fc75  xor     r8d, r8d; ulOptions
0x18002fc78  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002fc7f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002fc86  call    cs:__imp_RegOpenKeyExW
0x18002fc8c  test    eax, eax
0x18002fc8e  jnz     loc_18002FDDA
0x18002fc94  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18002fc99  test    rcx, rcx
0x18002fc9c  jz      loc_18002FDDA
0x18002fca2  cmp     word ptr [rsp+2C0h+Data], r13w
0x18002fca8  jnz     loc_18002FD5E
0x18002fcae  mov     rdx, [rdi+8]; lpValueName
0x18002fcb2  call    cs:__imp_RegDeleteValueW
0x18002fcb8  call    cs:__imp_GetLastError
0x18002fcbe  mov     ebx, eax
0x18002fcc0  test    eax, eax
0x18002fcc2  jle     short loc_18002FCCD
0x18002fcc4  movzx   ebx, ax
0x18002fcc7  or      ebx, 80070000h
0x18002fccd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fcd4  lea     rax, WPP_GLOBAL_Control
0x18002fcdb  cmp     rcx, rax
0x18002fcde  jz      loc_18002FE55
0x18002fce4  test    byte ptr [rcx+1Ch], 1
0x18002fce8  jz      loc_18002FE55
0x18002fcee  mov     edx, 34h ; '4'
0x18002fcf3  jmp     loc_18002FE42
0x18002fcf8  xor     r13d, r13d
0x18002fcfb  mov     eax, edi
0x18002fcfd  test    edi, edi
0x18002fcff  cmovnz  eax, r14d
0x18002fd03  mov     r8d, eax
0x18002fd06  lea     rcx, [rax+rax]
0x18002fd0a  cmp     r12d, ebx
0x18002fd0d  jb      short loc_18002FD27
0x18002fd0f  cmp     rcx, 208h
0x18002fd16  jnb     loc_18002FE8A
0x18002fd1c  mov     word ptr [rsp+rcx+2C0h+Data], r13w
0x18002fd22  jmp     loc_18002FC5B
0x18002fd27  sub     ebx, edi
0x18002fd29  mov     eax, edi
0x18002fd2b  add     ebx, 0FFFFFFF5h
0x18002fd2e  lea     rdx, [rsp+2C0h+var_24A]
0x18002fd33  lea     rcx, [rsp+rcx+2C0h+Data]; void *
0x18002fd38  lea     rdx, [rdx+rax*2]; Src
0x18002fd3c  test    r8d, r8d
0x18002fd3f  jz      short loc_18002FD52
0x18002fd41  lea     r8d, [rbx+1]
0x18002fd45  add     r8, r8; Size
0x18002fd48  call    memmove_0
0x18002fd4d  jmp     loc_18002FC5B
0x18002fd52  mov     r8d, ebx
0x18002fd55  add     r8, r8
0x18002fd58  add     rdx, 2
0x18002fd5c  jmp     short loc_18002FD48
0x18002fd5e  lea     rax, [rsp+2C0h+Data]
0x18002fd63  inc     rsi
0x18002fd66  cmp     [rax+rsi*2], r13w
0x18002fd6b  jnz     short loc_18002FD63
0x18002fd6d  lea     eax, [rsi+rsi]
0x18002fd70  mov     r9d, 1; dwType
0x18002fd76  mov     dword ptr [rsp+2C0h+pvData], eax; cbData
0x18002fd7a  lea     rdx, aSoftwareMicros_11; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002fd81  lea     rax, [rsp+2C0h+Data]
0x18002fd86  xor     r8d, r8d; Reserved
0x18002fd89  mov     [rsp+2C0h+pdwType], rax; lpData
0x18002fd8e  call    cs:__imp_RegSetValueExW
0x18002fd94  test    eax, eax
0x18002fd96  jz      short loc_18002FDD5
0x18002fd98  call    cs:__imp_GetLastError
0x18002fd9e  mov     ebx, eax
0x18002fda0  test    eax, eax
0x18002fda2  jle     short loc_18002FDAD
0x18002fda4  movzx   ebx, ax
0x18002fda7  or      ebx, 80070000h
0x18002fdad  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdb4  lea     rax, WPP_GLOBAL_Control
0x18002fdbb  cmp     rcx, rax
0x18002fdbe  jz      loc_18002FE55
0x18002fdc4  test    byte ptr [rcx+1Ch], 1
0x18002fdc8  jz      loc_18002FE55
0x18002fdce  mov     edx, 35h ; '5'
0x18002fdd3  jmp     short loc_18002FE42
0x18002fdd5  mov     ebx, r13d
0x18002fdd8  jmp     short loc_18002FE55
0x18002fdda  call    cs:__imp_GetLastError
0x18002fde0  mov     ebx, eax
0x18002fde2  test    eax, eax
0x18002fde4  jle     short loc_18002FDEF
0x18002fde6  movzx   ebx, ax
0x18002fde9  or      ebx, 80070000h
0x18002fdef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fdf6  lea     rax, WPP_GLOBAL_Control
0x18002fdfd  cmp     rcx, rax
0x18002fe00  jz      short loc_18002FE55
0x18002fe02  test    byte ptr [rcx+1Ch], 1
0x18002fe06  jz      short loc_18002FE55
0x18002fe08  mov     edx, 33h ; '3'
0x18002fe0d  jmp     short loc_18002FE42
0x18002fe0f  call    cs:__imp_GetLastError
0x18002fe15  mov     ebx, eax
0x18002fe17  test    eax, eax
0x18002fe19  jle     short loc_18002FE24
0x18002fe1b  movzx   ebx, ax
0x18002fe1e  or      ebx, 80070000h
0x18002fe24  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fe2b  lea     rax, WPP_GLOBAL_Control
0x18002fe32  cmp     rcx, rax
0x18002fe35  jz      short loc_18002FE55
0x18002fe37  test    byte ptr [rcx+1Ch], 1
0x18002fe3b  jz      short loc_18002FE55
0x18002fe3d  mov     edx, 32h ; '2'
0x18002fe42  mov     rcx, [rcx+10h]
0x18002fe46  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x18002fe4d  mov     r9d, ebx
0x18002fe50  call    WPP_SF_d
0x18002fe55  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18002fe5a  test    rcx, rcx
0x18002fe5d  jz      short loc_18002FE65
0x18002fe5f  call    cs:__imp_RegCloseKey
0x18002fe65  mov     eax, ebx
0x18002fe67  mov     rcx, [rbp+1C0h+var_50]
0x18002fe6e  xor     rcx, rsp; StackCookie
0x18002fe71  call    __security_check_cookie
0x18002fe76  add     rsp, 288h
0x18002fe7d  pop     r15
0x18002fe7f  pop     r14
0x18002fe81  pop     r13
0x18002fe83  pop     r12
0x18002fe85  pop     rdi
0x18002fe86  pop     rsi
0x18002fe87  pop     rbx
0x18002fe88  pop     rbp
0x18002fe89  retn
0x18002fe8a  call    __report_rangecheckfailure
```
