# IsCustomDLLTrusted

- ea: `0x18000da64`
- end: `0x18000de18`
- name: `IsCustomDLLTrusted`
- size: `948`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18001ffb0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000da64`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000dd18`
- `msvcrt!_wcsicmp` at `0x18000dd18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc25`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dafa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dafa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dbb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dbb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dd89`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000dc7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dc11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dd79`

## string_xrefs

- `0x18000dad3`: `SYSTEM\CurrentControlSet\Services\RasMan\Parameters`
- `0x18000dc75`: `CustomDLL`

## pseudocode

```c
__int64 __fastcall IsCustomDLLTrusted(wchar_t *String2)
{
  unsigned int v2; // eax
  struct _LIST_ENTRY *v3; // rcx
  __int64 v4; // rdx
  DWORD LastError; // eax
  int v6; // ebx
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  BYTE *v9; // rsi
  unsigned int v10; // eax
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  const wchar_t *v14; // rdi
  __int64 v15; // rax
  DWORD cValues; // [rsp+60h] [rbp-20h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-1Ch] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cbMaxValueLen; // [rsp+D0h] [rbp+50h] BYREF
  DWORD Type; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 45, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  hKey = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  Type = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Parameters",
         0,
         0x2000000u,
         &hKey);
  if ( v2 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return 0;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 46, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v2);
      v3 = WPP_GLOBAL_Control;
    }
    if ( v3 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(v3[1].Blink) & 0x2000) == 0
      || BYTE1(v3[1].Blink) < 6u )
    {
      return 0;
    }
    v4 = 47;
    goto LABEL_52;
  }
  LastError = RegQueryInfoKeyW(
                hKey,
                0,
                0,
                0,
                &cSubKeys,
                &cbMaxSubKeyLen,
                0,
                &cValues,
                &cbMaxValueNameLen,
                &cbMaxValueLen,
                0,
                0);
  v6 = LastError;
  if ( LastError )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 48;
LABEL_19:
      WPP_SF_d(v7[1].Flink, v8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, LastError);
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  ++cbMaxValueNameLen;
  v9 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( v9 )
  {
    v10 = RegQueryValueExW(hKey, L"CustomDLL", 0, &Type, v9, &cbMaxValueLen);
    v6 = v10;
    if ( v10 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_46;
      }
      v12 = 50;
      v13 = v10;
    }
    else
    {
      if ( Type == 7 )
      {
        v6 = 126;
        v14 = (const wchar_t *)v9;
        if ( *(_WORD *)v9 )
        {
          while ( _wcsicmp(v14, String2) )
          {
            v15 = -1;
            do
              ++v15;
            while ( v14[v15] );
            v14 += v15 + 1;
            if ( !*v14 )
              goto LABEL_46;
          }
          v6 = 0;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control[1].Flink, 52, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
          }
        }
        goto LABEL_46;
      }
      v6 = 1015;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_46:
        LocalFree(v9);
        goto LABEL_47;
      }
      v12 = 51;
      v13 = 1015;
    }
    WPP_SF_d(v11[1].Flink, v12, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids, v13);
    goto LABEL_46;
  }
  LastError = GetLastError();
  v6 = LastError;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v8 = 49;
    goto LABEL_19;
  }
LABEL_47:
  RegCloseKey(hKey);
  if ( v6 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 6u )
    {
      return 0;
    }
    v4 = 53;
LABEL_52:
    WPP_SF_(v3[1].Flink, v4, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 54, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids);
  }
  return 1;
}

```

## disassembly

```asm
0x18000da64  mov     [rsp-38h+arg_0], rbx
0x18000da69  push    rbp
0x18000da6a  push    rsi
0x18000da6b  push    rdi
0x18000da6c  push    r12
0x18000da6e  push    r13
0x18000da70  push    r14
0x18000da72  push    r15
0x18000da74  mov     rbp, rsp
0x18000da77  sub     rsp, 80h
0x18000da7e  mov     r14, rcx
0x18000da81  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da88  lea     r13, WPP_GLOBAL_Control
0x18000da8f  mov     r12d, 2000h
0x18000da95  cmp     rcx, r13
0x18000da98  jz      short loc_18000DABB
0x18000da9a  test    [rcx+1Ch], r12d
0x18000da9e  jz      short loc_18000DABB
0x18000daa0  cmp     byte ptr [rcx+19h], 6
0x18000daa4  jb      short loc_18000DABB
0x18000daa6  mov     rcx, [rcx+10h]
0x18000daaa  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dab1  mov     edx, 2Dh ; '-'
0x18000dab6  call    WPP_SF_
0x18000dabb  xor     r15d, r15d
0x18000dabe  lea     rax, [rbp+hKey]
0x18000dac2  mov     r9d, 2000000h; samDesired
0x18000dac8  mov     [rbp+hKey], r15
0x18000dacc  xor     r8d, r8d; ulOptions
0x18000dacf  mov     [rbp+cSubKeys], r15d
0x18000dad3  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18000dada  mov     [rbp+cbMaxSubKeyLen], r15d
0x18000dade  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dae5  mov     [rbp+cbMaxValueNameLen], r15d
0x18000dae9  mov     [rbp+cValues], r15d
0x18000daed  mov     [rbp+cbMaxValueLen], r15d
0x18000daf1  mov     [rbp+Type], r15d
0x18000daf5  mov     [rsp+80h+phkResult], rax; phkResult
0x18000dafa  call    cs:__imp_RegOpenKeyExW
0x18000db01  nop     dword ptr [rax+rax+00h]
0x18000db06  test    eax, eax
0x18000db08  jz      short loc_18000DB6B
0x18000db0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db11  cmp     rcx, r13
0x18000db14  jz      loc_18000DDC6
0x18000db1a  test    [rcx+1Ch], r12d
0x18000db1e  jz      short loc_18000DB44
0x18000db20  cmp     byte ptr [rcx+19h], 2
0x18000db24  jb      short loc_18000DB44
0x18000db26  mov     rcx, [rcx+10h]
0x18000db2a  lea     edx, [r15+2Eh]
0x18000db2e  mov     r9d, eax
0x18000db31  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000db38  call    WPP_SF_d
0x18000db3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db44  cmp     rcx, r13
0x18000db47  jz      loc_18000DDC6
0x18000db4d  test    [rcx+1Ch], r12d
0x18000db51  jz      loc_18000DDC6
0x18000db57  cmp     byte ptr [rcx+19h], 6
0x18000db5b  jb      loc_18000DDC6
0x18000db61  mov     edx, 2Fh ; '/'
0x18000db66  jmp     loc_18000DDB6
0x18000db6b  mov     rcx, [rbp+hKey]; hKey
0x18000db6f  lea     rax, [rbp+cbMaxValueLen]
0x18000db73  mov     [rsp+80h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000db78  xor     r9d, r9d; lpReserved
0x18000db7b  mov     [rsp+80h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000db80  xor     r8d, r8d; lpcchClass
0x18000db83  mov     [rsp+80h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18000db88  xor     edx, edx; lpClass
0x18000db8a  lea     rax, [rbp+cbMaxValueNameLen]
0x18000db8e  mov     [rsp+80h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18000db93  lea     rax, [rbp+cValues]
0x18000db97  mov     [rsp+80h+lpcValues], rax; lpcValues
0x18000db9c  lea     rax, [rbp+cbMaxSubKeyLen]
0x18000dba0  mov     [rsp+80h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000dba5  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18000dbaa  lea     rax, [rbp+cSubKeys]
0x18000dbae  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18000dbb3  call    cs:__imp_RegQueryInfoKeyW
0x18000dbba  nop     dword ptr [rax+rax+00h]
0x18000dbbf  mov     ebx, eax
0x18000dbc1  test    eax, eax
0x18000dbc3  jz      short loc_18000DC06
0x18000dbc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbcc  cmp     rcx, r13
0x18000dbcf  jz      loc_18000DD85
0x18000dbd5  test    [rcx+1Ch], r12d
0x18000dbd9  jz      loc_18000DD85
0x18000dbdf  cmp     byte ptr [rcx+19h], 2
0x18000dbe3  jb      loc_18000DD85
0x18000dbe9  mov     edx, 30h ; '0'
0x18000dbee  mov     rcx, [rcx+10h]
0x18000dbf2  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dbf9  mov     r9d, eax
0x18000dbfc  call    WPP_SF_d
0x18000dc01  jmp     loc_18000DD85
0x18000dc06  mov     edx, [rbp+cbMaxValueLen]; uBytes
0x18000dc09  mov     ecx, 40h ; '@'; uFlags
0x18000dc0e  inc     [rbp+cbMaxValueNameLen]
0x18000dc11  call    cs:__imp_LocalAlloc
0x18000dc18  nop     dword ptr [rax+rax+00h]
0x18000dc1d  mov     rsi, rax
0x18000dc20  test    rax, rax
0x18000dc23  jnz     short loc_18000DC5C
0x18000dc25  call    cs:__imp_GetLastError
0x18000dc2c  nop     dword ptr [rax+rax+00h]
0x18000dc31  mov     ebx, eax
0x18000dc33  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc3a  cmp     rcx, r13
0x18000dc3d  jz      loc_18000DD85
0x18000dc43  test    [rcx+1Ch], r12d
0x18000dc47  jz      loc_18000DD85
0x18000dc4d  cmp     byte ptr [rcx+19h], 2
0x18000dc51  jb      loc_18000DD85
0x18000dc57  lea     edx, [rsi+31h]
0x18000dc5a  jmp     short loc_18000DBEE
0x18000dc5c  mov     rcx, [rbp+hKey]; hKey
0x18000dc60  lea     rax, [rbp+cbMaxValueLen]
0x18000dc64  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000dc69  lea     r9, [rbp+Type]; lpType
0x18000dc6d  xor     r8d, r8d; lpReserved
0x18000dc70  mov     [rsp+80h+phkResult], rsi; lpData
0x18000dc75  lea     rdx, aCustomdll; "CustomDLL"
0x18000dc7c  call    cs:__imp_RegQueryValueExW
0x18000dc83  nop     dword ptr [rax+rax+00h]
0x18000dc88  mov     ebx, eax
0x18000dc8a  test    eax, eax
0x18000dc8c  jz      short loc_18000DCCF
0x18000dc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc95  cmp     rcx, r13
0x18000dc98  jz      loc_18000DD76
0x18000dc9e  test    [rcx+1Ch], r12d
0x18000dca2  jz      loc_18000DD76
0x18000dca8  cmp     byte ptr [rcx+19h], 2
0x18000dcac  jb      loc_18000DD76
0x18000dcb2  mov     edx, 32h ; '2'
0x18000dcb7  mov     r9d, eax
0x18000dcba  mov     rcx, [rcx+10h]
0x18000dcbe  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dcc5  call    WPP_SF_d
0x18000dcca  jmp     loc_18000DD76
0x18000dccf  cmp     [rbp+Type], 7
0x18000dcd3  jz      short loc_18000DD04
0x18000dcd5  mov     ebx, 3F7h
0x18000dcda  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dce1  cmp     rcx, r13
0x18000dce4  jz      loc_18000DD76
0x18000dcea  test    [rcx+1Ch], r12d
0x18000dcee  jz      loc_18000DD76
0x18000dcf4  cmp     byte ptr [rcx+19h], 2
0x18000dcf8  jb      short loc_18000DD76
0x18000dcfa  mov     edx, 33h ; '3'
0x18000dcff  mov     r9d, ebx
0x18000dd02  jmp     short loc_18000DCBA
0x18000dd04  mov     ebx, 7Eh ; '~'
0x18000dd09  mov     rdi, rsi
0x18000dd0c  cmp     [rsi], r15w
0x18000dd10  jz      short loc_18000DD76
0x18000dd12  mov     rdx, r14; String2
0x18000dd15  mov     rcx, rdi; String1
0x18000dd18  call    cs:__imp__wcsicmp
0x18000dd1f  nop     dword ptr [rax+rax+00h]
0x18000dd24  test    eax, eax
0x18000dd26  jz      short loc_18000DD46
0x18000dd28  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dd2c  inc     rax
0x18000dd2f  cmp     [rdi+rax*2], r15w
0x18000dd34  jnz     short loc_18000DD2C
0x18000dd36  lea     rdi, [rdi+rax*2]
0x18000dd3a  add     rdi, 2
0x18000dd3e  cmp     [rdi], r15w
0x18000dd42  jnz     short loc_18000DD12
0x18000dd44  jmp     short loc_18000DD76
0x18000dd46  mov     ebx, r15d
0x18000dd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd50  cmp     rcx, r13
0x18000dd53  jz      short loc_18000DD76
0x18000dd55  test    [rcx+1Ch], r12d
0x18000dd59  jz      short loc_18000DD76
0x18000dd5b  cmp     byte ptr [rcx+19h], 4
0x18000dd5f  jb      short loc_18000DD76
0x18000dd61  mov     rcx, [rcx+10h]
0x18000dd65  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dd6c  mov     edx, 34h ; '4'
0x18000dd71  call    WPP_SF_
0x18000dd76  mov     rcx, rsi; hMem
0x18000dd79  call    cs:__imp_LocalFree
0x18000dd80  nop     dword ptr [rax+rax+00h]
0x18000dd85  mov     rcx, [rbp+hKey]; hKey
0x18000dd89  call    cs:__imp_RegCloseKey
0x18000dd90  nop     dword ptr [rax+rax+00h]
0x18000dd95  test    ebx, ebx
0x18000dd97  jz      short loc_18000DDCA
0x18000dd99  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dda0  cmp     rcx, r13
0x18000dda3  jz      short loc_18000DDC6
0x18000dda5  test    [rcx+1Ch], r12d
0x18000dda9  jz      short loc_18000DDC6
0x18000ddab  cmp     byte ptr [rcx+19h], 6
0x18000ddaf  jb      short loc_18000DDC6
0x18000ddb1  mov     edx, 35h ; '5'
0x18000ddb6  mov     rcx, [rcx+10h]
0x18000ddba  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000ddc1  call    WPP_SF_
0x18000ddc6  xor     eax, eax
0x18000ddc8  jmp     short loc_18000DDFC
0x18000ddca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddd1  cmp     rcx, r13
0x18000ddd4  jz      short loc_18000DDF7
0x18000ddd6  test    [rcx+1Ch], r12d
0x18000ddda  jz      short loc_18000DDF7
0x18000dddc  cmp     byte ptr [rcx+19h], 6
0x18000dde0  jb      short loc_18000DDF7
0x18000dde2  mov     rcx, [rcx+10h]
0x18000dde6  lea     r8, WPP_2e92e78aa7e03fb3a95ae56788dec76c_Traceguids
0x18000dded  mov     edx, 36h ; '6'
0x18000ddf2  call    WPP_SF_
0x18000ddf7  mov     eax, 1
0x18000ddfc  mov     rbx, [rsp+80h+arg_0]
0x18000de04  add     rsp, 80h
0x18000de0b  pop     r15
0x18000de0d  pop     r14
0x18000de0f  pop     r13
0x18000de11  pop     r12
0x18000de13  pop     rdi
0x18000de14  pop     rsi
0x18000de15  pop     rbp
0x18000de16  retn
```
