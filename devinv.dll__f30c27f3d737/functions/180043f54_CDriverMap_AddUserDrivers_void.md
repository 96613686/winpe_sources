# CDriverMap::AddUserDrivers(void)

- ea: `0x180043f54`
- end: `0x1800443b3`
- name: `?AddUserDrivers@CDriverMap@@AEAAJXZ`
- size: `1119`
- prototype: `__int64 __fastcall(CDriverMap *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044f20`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18004255c`
- `0x180043f54`
- `0x1800460b8`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043fa9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043fa9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044303`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044303`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044158`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180044158`

## string_xrefs

- `0x180043f9f`: `Software\Microsoft\Windows Nt\CurrentVersion\WUDF\Services`
- `0x180043fd4`: `0x%08x Failed to open user mode service key`
- `0x18004401d`: `0x%08x Failed to open user mode service key`
- `0x18004404f`: `0x%08x Failed to open user mode service key`
- `0x18004432a`: `0x%08x Failed to get user mode driver path`
- `0x1800440b9`: `No user mode driver path found under the registry key.`
- `0x180044101`: `No user mode driver path found under the registry key.`
- `0x180044130`: `No user mode driver path found under the registry key.`
- `0x180044169`: `driver path longer than MAX_PATH-1 `
- `0x1800441b1`: `driver path longer than MAX_PATH-1 `
- `0x1800441e0`: `driver path longer than MAX_PATH-1 `

## pseudocode

```c
__int64 __fastcall CDriverMap::AddUserDrivers(CDriverMap *this)
{
  int v2; // r12d
  LSTATUS v3; // eax
  CDriverMap *v4; // rcx
  unsigned int v5; // r9d
  unsigned int UserModeDriverPath; // ebx
  FILE *v7; // rax
  FILE *v8; // rax
  FILE *v9; // rax
  CDriverMap *v10; // rcx
  unsigned int v11; // r9d
  FILE *v12; // rax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  int v18; // ebx
  FILE *v19; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  FILE *v25; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+28h] [rbp-D8h]
  WCHAR *v28; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Src[264]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v31[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Dst[264]; // [rsp+470h] [rbp+370h] BYREF

  v2 = 0;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Nt\\CurrentVersion\\WUDF\\Services",
         0,
         0x20119u,
         &hKey);
  UserModeDriverPath = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      UserModeDriverPath = (unsigned __int16)v3 | 0x80070000;
    AslLogCallPrintf(
      2,
      "CDriverMap::AddUserDrivers",
      1444,
      "0x%08x Failed to open user mode service key",
      UserModeDriverPath);
    if ( EnableDevInvStdErrLog )
    {
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Error: %s, %u: ", "CDriverMap::AddUserDrivers", 1444);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "0x%08x Failed to open user mode service key", UserModeDriverPath);
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "0x%08x Failed to open user mode service key", UserModeDriverPath);
  }
  else
  {
    UserModeDriverPath = CDriverMap::GetUserModeDriverPath(v4, hKey, 0, v5, v31, v27, Src);
    if ( UserModeDriverPath == -2147024637 )
    {
LABEL_26:
      UserModeDriverPath = 0;
    }
    else
    {
      while ( (UserModeDriverPath & 0x80000000) == 0 )
      {
        if ( Src[0] )
        {
          if ( ExpandEnvironmentStringsW(Src, Dst, 0x103u) < 0x103 )
          {
            v18 = CDriverMap::AddDriver(this, Dst, v31, 4u, 0);
            if ( v18 < 0 )
            {
              v28 = Src;
              LODWORD(phkResult) = v18;
              AslLogCallPrintf(
                2,
                "CDriverMap::AddUserDrivers",
                1486,
                "0x%08x Failed to add user mode driver [%ws]",
                phkResult);
              if ( EnableDevInvStdErrLog )
              {
                v19 = o___acrt_iob_func_0(2u);
                fprintf(v19, "Error: %s, %u: ", "CDriverMap::AddUserDrivers", 1486);
                v20 = o___acrt_iob_func_0(2u);
                fprintf(v20, "0x%08x Failed to add user mode driver [%ws]", (unsigned int)v18, Src);
                v21 = o___acrt_iob_func_0(2u);
                fprintf(v21, "\n");
              }
              if ( g_DeviceMapLogFunction )
                TraceMessageCallback(0x2000000, "0x%08x Failed to add user mode driver [%ws]", (unsigned int)v18, Src);
            }
          }
          else
          {
            AslLogCallPrintf(2, "CDriverMap::AddUserDrivers", 1478, "driver path longer than MAX_PATH-1 ");
            if ( EnableDevInvStdErrLog )
            {
              v15 = o___acrt_iob_func_0(2u);
              fprintf(v15, "Error: %s, %u: ", "CDriverMap::AddUserDrivers", 1478);
              v16 = o___acrt_iob_func_0(2u);
              fprintf(v16, "driver path longer than MAX_PATH-1 ");
              v17 = o___acrt_iob_func_0(2u);
              fprintf(v17, "\n");
            }
            if ( g_DeviceMapLogFunction )
              TraceMessageCallback(0x2000000, "driver path longer than MAX_PATH-1 ");
          }
        }
        else
        {
          AslLogCallPrintf(
            2,
            "CDriverMap::AddUserDrivers",
            1472,
            "No user mode driver path found under the registry key.");
          if ( EnableDevInvStdErrLog )
          {
            v12 = o___acrt_iob_func_0(2u);
            fprintf(v12, "Warning: %s, %u: ", "CDriverMap::AddUserDrivers", 1472);
            v13 = o___acrt_iob_func_0(2u);
            fprintf(v13, "No user mode driver path found under the registry key.");
            v14 = o___acrt_iob_func_0(2u);
            fprintf(v14, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(50331648, "No user mode driver path found under the registry key.");
        }
        UserModeDriverPath = CDriverMap::GetUserModeDriverPath(v10, hKey, ++v2, v11, v31, (unsigned int)v28, Src);
        if ( UserModeDriverPath == -2147024637 )
          goto LABEL_26;
      }
      AslLogCallPrintf(
        2,
        "CDriverMap::AddUserDrivers",
        1463,
        "0x%08x Failed to get user mode driver path",
        UserModeDriverPath);
      if ( EnableDevInvStdErrLog )
      {
        v23 = o___acrt_iob_func_0(2u);
        fprintf(v23, "Error: %s, %u: ", "CDriverMap::AddUserDrivers", 1463);
        v24 = o___acrt_iob_func_0(2u);
        fprintf(v24, "0x%08x Failed to get user mode driver path", UserModeDriverPath);
        v25 = o___acrt_iob_func_0(2u);
        fprintf(v25, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "0x%08x Failed to get user mode driver path", UserModeDriverPath);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return UserModeDriverPath;
}

```

## disassembly

```asm
0x180043f54  push    rbp
0x180043f56  push    rbx
0x180043f57  push    rsi
0x180043f58  push    rdi
0x180043f59  push    r12
0x180043f5b  push    r13
0x180043f5d  lea     rbp, [rsp-598h]
0x180043f65  sub     rsp, 698h
0x180043f6c  mov     rax, cs:__security_cookie
0x180043f73  xor     rax, rsp
0x180043f76  mov     [rbp+5C0h+var_40], rax
0x180043f7d  mov     r13, rcx
0x180043f80  lea     rax, [rsp+6C0h+hKey]
0x180043f85  xor     r12d, r12d
0x180043f88  mov     [rsp+6C0h+phkResult], rax; phkResult
0x180043f8d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043f94  mov     [rsp+6C0h+hKey], r12
0x180043f99  mov     r9d, 20119h; samDesired
0x180043f9f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows Nt\\Curren"...
0x180043fa6  xor     r8d, r8d; ulOptions
0x180043fa9  call    cs:__imp_RegOpenKeyExW
0x180043faf  mov     ebx, eax
0x180043fb1  test    eax, eax
0x180043fb3  jz      loc_180044068
0x180043fb9  jle     short loc_180043FC4
0x180043fbb  movzx   ebx, ax
0x180043fbe  or      ebx, 80070000h
0x180043fc4  lea     rsi, aCdrivermapAddu; "CDriverMap::AddUserDrivers"
0x180043fcb  mov     dword ptr [rsp+6C0h+phkResult], ebx
0x180043fcf  mov     edi, 2
0x180043fd4  lea     r9, a0x08xFailedToO; "0x%08x Failed to open user mode service"...
0x180043fdb  mov     rdx, rsi
0x180043fde  mov     ecx, edi
0x180043fe0  mov     r8d, 5A4h
0x180043fe6  call    AslLogCallPrintf
0x180043feb  cmp     cs:EnableDevInvStdErrLog, r12d
0x180043ff2  jz      short loc_180044042
0x180043ff4  mov     ecx, edi; Ix
0x180043ff6  call    _o___acrt_iob_func_0
0x180043ffb  mov     rcx, rax; Stream
0x180043ffe  lea     rdx, Format; "Error: %s, %u: "
0x180044005  mov     r9d, 5A4h
0x18004400b  mov     r8, rsi
0x18004400e  call    fprintf
0x180044013  mov     ecx, edi; Ix
0x180044015  call    _o___acrt_iob_func_0
0x18004401a  mov     rcx, rax; Stream
0x18004401d  lea     rdx, a0x08xFailedToO; "0x%08x Failed to open user mode service"...
0x180044024  mov     r8d, ebx
0x180044027  call    fprintf
0x18004402c  mov     ecx, edi; Ix
0x18004402e  call    _o___acrt_iob_func_0
0x180044033  mov     rcx, rax; Stream
0x180044036  lea     rdx, asc_18011EAD8; "\n"
0x18004403d  call    fprintf
0x180044042  cmp     cs:g_DeviceMapLogFunction, r12
0x180044049  jz      loc_1800442F9
0x18004404f  lea     rdx, a0x08xFailedToO; "0x%08x Failed to open user mode service"...
0x180044056  mov     r8d, ebx
0x180044059  mov     ecx, 2000000h
0x18004405e  call    TraceMessageCallback
0x180044063  jmp     loc_1800442F9
0x180044068  mov     rdx, [rsp+6C0h+hKey]; HKEY
0x18004406d  lea     rax, [rsp+6C0h+Src]
0x180044072  mov     [rsp+6C0h+var_690], rax; unsigned __int16 *
0x180044077  xor     r8d, r8d; unsigned int
0x18004407a  lea     rax, [rbp+5C0h+var_460]
0x180044081  mov     [rsp+6C0h+phkResult], rax; unsigned __int16 *
0x180044086  call    ?GetUserModeDriverPath@CDriverMap@@AEAAJPEAUHKEY__@@KKPEAGK1@Z; CDriverMap::GetUserModeDriverPath(HKEY__ *,ulong,ulong,ushort *,ulong,ushort *)
0x18004408b  mov     ebx, eax
0x18004408d  cmp     eax, 80070103h
0x180044092  jz      loc_1800442F3
0x180044098  lea     rsi, aCdrivermapAddu; "CDriverMap::AddUserDrivers"
0x18004409f  mov     edi, 2
0x1800440a4  test    ebx, ebx
0x1800440a6  js      loc_18004432A
0x1800440ac  xor     ebx, ebx
0x1800440ae  cmp     [rsp+6C0h+Src], bx
0x1800440b3  jnz     loc_180044146
0x1800440b9  lea     r9, aNoUserModeDriv; "No user mode driver path found under th"...
0x1800440c0  mov     r8d, 5C0h
0x1800440c6  mov     rdx, rsi
0x1800440c9  mov     ecx, edi
0x1800440cb  call    AslLogCallPrintf
0x1800440d0  cmp     cs:EnableDevInvStdErrLog, ebx
0x1800440d6  jz      short loc_180044123
0x1800440d8  mov     ecx, edi; Ix
0x1800440da  call    _o___acrt_iob_func_0
0x1800440df  mov     rcx, rax; Stream
0x1800440e2  lea     rdx, aWarningSU; "Warning: %s, %u: "
0x1800440e9  mov     r9d, 5C0h
0x1800440ef  mov     r8, rsi
0x1800440f2  call    fprintf
0x1800440f7  mov     ecx, edi; Ix
0x1800440f9  call    _o___acrt_iob_func_0
0x1800440fe  mov     rcx, rax; Stream
0x180044101  lea     rdx, aNoUserModeDriv; "No user mode driver path found under th"...
0x180044108  call    fprintf
0x18004410d  mov     ecx, edi; Ix
0x18004410f  call    _o___acrt_iob_func_0
0x180044114  mov     rcx, rax; Stream
0x180044117  lea     rdx, asc_18011EAD8; "\n"
0x18004411e  call    fprintf
0x180044123  cmp     cs:g_DeviceMapLogFunction, rbx
0x18004412a  jz      loc_1800442C0
0x180044130  lea     rdx, aNoUserModeDriv; "No user mode driver path found under th"...
0x180044137  mov     ecx, 3000000h
0x18004413c  call    TraceMessageCallback
0x180044141  jmp     loc_1800442C0
0x180044146  mov     r8d, 103h; nSize
0x18004414c  lea     rdx, [rbp+5C0h+Dst]; lpDst
0x180044153  lea     rcx, [rsp+6C0h+Src]; lpSrc
0x180044158  call    cs:__imp_ExpandEnvironmentStringsW
0x18004415e  cmp     eax, 103h
0x180044163  jb      loc_1800441F1
0x180044169  lea     r9, aDriverPathLong; "driver path longer than MAX_PATH-1 "
0x180044170  mov     r8d, 5C6h
0x180044176  mov     rdx, rsi
0x180044179  mov     ecx, edi
0x18004417b  call    AslLogCallPrintf
0x180044180  cmp     cs:EnableDevInvStdErrLog, ebx
0x180044186  jz      short loc_1800441D3
0x180044188  mov     ecx, edi; Ix
0x18004418a  call    _o___acrt_iob_func_0
0x18004418f  mov     rcx, rax; Stream
0x180044192  lea     rdx, Format; "Error: %s, %u: "
0x180044199  mov     r9d, 5C6h
0x18004419f  mov     r8, rsi
0x1800441a2  call    fprintf
0x1800441a7  mov     ecx, edi; Ix
0x1800441a9  call    _o___acrt_iob_func_0
0x1800441ae  mov     rcx, rax; Stream
0x1800441b1  lea     rdx, aDriverPathLong; "driver path longer than MAX_PATH-1 "
0x1800441b8  call    fprintf
0x1800441bd  mov     ecx, edi; Ix
0x1800441bf  call    _o___acrt_iob_func_0
0x1800441c4  mov     rcx, rax; Stream
0x1800441c7  lea     rdx, asc_18011EAD8; "\n"
0x1800441ce  call    fprintf
0x1800441d3  cmp     cs:g_DeviceMapLogFunction, rbx
0x1800441da  jz      loc_1800442C0
0x1800441e0  lea     rdx, aDriverPathLong; "driver path longer than MAX_PATH-1 "
0x1800441e7  mov     ecx, 2000000h
0x1800441ec  jmp     loc_18004413C
0x1800441f1  mov     r9d, 4; unsigned int
0x1800441f7  mov     [rsp+6C0h+phkResult], rbx; struct CDriver **
0x1800441fc  lea     r8, [rbp+5C0h+var_460]; unsigned __int16 *
0x180044203  mov     rcx, r13; this
0x180044206  lea     rdx, [rbp+5C0h+Dst]; lpSrc
0x18004420d  call    ?AddDriver@CDriverMap@@AEAAJPEBG0KPEAPEAVCDriver@@@Z; CDriverMap::AddDriver(ushort const *,ushort const *,ulong,CDriver * *)
0x180044212  mov     ebx, eax
0x180044214  test    eax, eax
0x180044216  jns     loc_1800442C0
0x18004421c  lea     rax, [rsp+6C0h+Src]
0x180044221  mov     r8d, 5CEh
0x180044227  mov     qword ptr [rsp+6C0h+var_698], rax; unsigned int
0x18004422c  lea     r9, a0x08xFailedToA_4; "0x%08x Failed to add user mode driver ["...
0x180044233  mov     rdx, rsi
0x180044236  mov     dword ptr [rsp+6C0h+phkResult], ebx
0x18004423a  mov     ecx, edi
0x18004423c  call    AslLogCallPrintf
0x180044241  cmp     cs:EnableDevInvStdErrLog, 0
0x180044248  jz      short loc_18004429D
0x18004424a  mov     ecx, edi; Ix
0x18004424c  call    _o___acrt_iob_func_0
0x180044251  mov     rcx, rax; Stream
0x180044254  lea     rdx, Format; "Error: %s, %u: "
0x18004425b  mov     r9d, 5CEh
0x180044261  mov     r8, rsi
0x180044264  call    fprintf
0x180044269  mov     ecx, edi; Ix
0x18004426b  call    _o___acrt_iob_func_0
0x180044270  mov     rcx, rax; Stream
0x180044273  lea     r9, [rsp+6C0h+Src]
0x180044278  mov     r8d, ebx
0x18004427b  lea     rdx, a0x08xFailedToA_4; "0x%08x Failed to add user mode driver ["...
0x180044282  call    fprintf
0x180044287  mov     ecx, edi; Ix
0x180044289  call    _o___acrt_iob_func_0
0x18004428e  mov     rcx, rax; Stream
0x180044291  lea     rdx, asc_18011EAD8; "\n"
0x180044298  call    fprintf
0x18004429d  cmp     cs:g_DeviceMapLogFunction, 0
0x1800442a5  jz      short loc_1800442C0
0x1800442a7  lea     r9, [rsp+6C0h+Src]
0x1800442ac  mov     r8d, ebx
0x1800442af  lea     rdx, a0x08xFailedToA_4; "0x%08x Failed to add user mode driver ["...
0x1800442b6  mov     ecx, 2000000h
0x1800442bb  call    TraceMessageCallback
0x1800442c0  mov     rdx, [rsp+6C0h+hKey]; HKEY
0x1800442c5  lea     rax, [rsp+6C0h+Src]
0x1800442ca  mov     [rsp+6C0h+var_690], rax; unsigned __int16 *
0x1800442cf  inc     r12d
0x1800442d2  lea     rax, [rbp+5C0h+var_460]
0x1800442d9  mov     r8d, r12d; unsigned int
0x1800442dc  mov     [rsp+6C0h+phkResult], rax; unsigned __int16 *
0x1800442e1  call    ?GetUserModeDriverPath@CDriverMap@@AEAAJPEAUHKEY__@@KKPEAGK1@Z; CDriverMap::GetUserModeDriverPath(HKEY__ *,ulong,ulong,ushort *,ulong,ushort *)
0x1800442e6  mov     ebx, eax
0x1800442e8  cmp     eax, 80070103h
0x1800442ed  jnz     loc_1800440A4
0x1800442f3  xor     r12d, r12d
0x1800442f6  mov     ebx, r12d
0x1800442f9  mov     rcx, [rsp+6C0h+hKey]; hKey
0x1800442fe  test    rcx, rcx
0x180044301  jz      short loc_180044309
0x180044303  call    cs:__imp_RegCloseKey
0x180044309  mov     eax, ebx
0x18004430b  mov     rcx, [rbp+5C0h+var_40]
0x180044312  xor     rcx, rsp; StackCookie
0x180044315  call    __security_check_cookie
0x18004431a  add     rsp, 698h
0x180044321  pop     r13
0x180044323  pop     r12
0x180044325  pop     rdi
0x180044326  pop     rsi
0x180044327  pop     rbx
0x180044328  pop     rbp
0x180044329  retn
0x18004432a  lea     r13, a0x08xFailedToG; "0x%08x Failed to get user mode driver p"...
0x180044331  mov     dword ptr [rsp+6C0h+phkResult], ebx
0x180044335  mov     r9, r13
0x180044338  mov     r8d, 5B7h
0x18004433e  mov     rdx, rsi
0x180044341  mov     ecx, edi
0x180044343  call    AslLogCallPrintf
0x180044348  xor     r12d, r12d
0x18004434b  cmp     cs:EnableDevInvStdErrLog, r12d
0x180044352  jz      short loc_18004439E
0x180044354  mov     ecx, edi; Ix
0x180044356  call    _o___acrt_iob_func_0
0x18004435b  mov     rcx, rax; Stream
0x18004435e  lea     rdx, Format; "Error: %s, %u: "
0x180044365  mov     r9d, 5B7h
0x18004436b  mov     r8, rsi
0x18004436e  call    fprintf
0x180044373  mov     ecx, edi; Ix
0x180044375  call    _o___acrt_iob_func_0
0x18004437a  mov     rcx, rax; Stream
0x18004437d  mov     r8d, ebx
0x180044380  mov     rdx, r13; Format
0x180044383  call    fprintf
0x180044388  mov     ecx, edi; Ix
0x18004438a  call    _o___acrt_iob_func_0
0x18004438f  mov     rcx, rax; Stream
0x180044392  lea     rdx, asc_18011EAD8; "\n"
0x180044399  call    fprintf
0x18004439e  cmp     cs:g_DeviceMapLogFunction, r12
0x1800443a5  jz      loc_1800442F9
0x1800443ab  mov     rdx, r13
0x1800443ae  jmp     loc_180044056
```
