# GetRehydrationProgress(ushort *,unsigned __int64)

- ea: `0x180006f50`
- end: `0x180007100`
- name: `?GetRehydrationProgress@@YAJPEAG_K@Z`
- size: `432`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ba0`

## callees

- `0x1800067a0`
- `0x180006f50`
- `0x180008874`
- `0x180009464`
- `0x1800094cc`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180007046`
- `ADVAPI32!RegGetValueW` at `0x180007046`
- `ADVAPI32!RegCloseKey` at `0x1800070ef`
- `ADVAPI32!RegCloseKey` at `0x1800070ef`
- `ADVAPI32!RegCreateKeyExW` at `0x180006fb6`
- `ADVAPI32!RegCreateKeyExW` at `0x180006fb6`

## pseudocode

```c
__int64 __fastcall GetRehydrationProgress(unsigned __int16 *a1, __int64 a2)
{
  LSTATUS v3; // eax
  __int64 v4; // r8
  unsigned int v5; // ebx
  LSTATUS ValueW; // eax
  int v7; // r8d
  unsigned int pvData; // [rsp+78h] [rbp+10h] BYREF
  int v10; // [rsp+7Ch] [rbp+14h]
  DWORD pcbData; // [rsp+80h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+20h] BYREF

  v10 = HIDWORD(a2);
  hKey = 0;
  pcbData = 4;
  pvData = 0;
  v3 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  v5 = v3;
  if ( v3 )
  {
    if ( v3 > 0 )
      v5 = (unsigned __int16)v3 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        v4,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI");
  }
  else
  {
    ValueW = RegGetValueW(
               HKEY_CURRENT_USER,
               L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
               L"RehydrationProgress",
               0x18u,
               0,
               &pvData,
               &pcbData);
    v5 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v5 = (unsigned __int16)ValueW | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          v7,
          (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory\\RestoreUI",
          (__int64)L"RehydrationProgress");
    }
    else
    {
      v5 = StringCchPrintfW(a1, 6u, L"%d", pvData);
      if ( (v5 & 0x80000000) != 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, v5);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180006f50  mov     rax, rsp
0x180006f53  mov     [rax+10h], rdx
0x180006f57  push    rbx
0x180006f58  push    rdi
0x180006f59  push    r15
0x180006f5b  sub     rsp, 50h
0x180006f5f  mov     qword ptr [rax-28h], 0
0x180006f67  mov     rdi, rcx
0x180006f6a  mov     qword ptr [rax+20h], 0
0x180006f72  xor     r9d, r9d; lpClass
0x180006f75  mov     dword ptr [rax+18h], 4
0x180006f7c  xor     r8d, r8d; Reserved
0x180006f7f  mov     dword ptr [rax+10h], 0
0x180006f86  lea     rax, [rax+20h]
0x180006f8a  mov     [rsp+68h+phkResult], rax; phkResult
0x180006f8f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180006f96  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180006f9f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180006fa6  mov     [rsp+68h+samDesired], 20019h; samDesired
0x180006fae  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180006fb6  call    cs:__imp_RegCreateKeyExW
0x180006fbc  mov     ebx, eax
0x180006fbe  test    eax, eax
0x180006fc0  jz      short loc_180007008
0x180006fc2  jle     short loc_180006FCD
0x180006fc4  movzx   ebx, ax
0x180006fc7  or      ebx, 80070000h
0x180006fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd4  lea     rax, WPP_GLOBAL_Control
0x180006fdb  cmp     rcx, rax
0x180006fde  jz      loc_1800070E2
0x180006fe4  test    byte ptr [rcx+1Ch], 1
0x180006fe8  jz      loc_1800070E2
0x180006fee  mov     rcx, [rcx+10h]
0x180006ff2  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180006ff9  mov     edx, 0Eh
0x180006ffe  call    WPP_SF_S
0x180007003  jmp     loc_1800070E2
0x180007008  lea     rax, [rsp+68h+pcbData]
0x180007010  mov     r9d, 18h; dwFlags
0x180007016  mov     [rsp+68h+lpSecurityAttributes], rax; pcbData
0x18000701b  lea     r15, aRehydrationpro; "RehydrationProgress"
0x180007022  lea     rax, [rsp+68h+pvData]
0x180007027  mov     r8, r15; lpValue
0x18000702a  mov     qword ptr [rsp+68h+samDesired], rax; pvData
0x18000702f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007036  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18000703d  mov     qword ptr [rsp+68h+dwOptions], 0; pdwType
0x180007046  call    cs:__imp_RegGetValueW
0x18000704c  mov     ebx, eax
0x18000704e  test    eax, eax
0x180007050  jz      short loc_180007092
0x180007052  jle     short loc_18000705D
0x180007054  movzx   ebx, ax
0x180007057  or      ebx, 80070000h
0x18000705d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007064  lea     rax, WPP_GLOBAL_Control
0x18000706b  cmp     rcx, rax
0x18000706e  jz      short loc_1800070E2
0x180007070  test    byte ptr [rcx+1Ch], 1
0x180007074  jz      short loc_1800070E2
0x180007076  mov     rcx, [rcx+10h]
0x18000707a  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007081  mov     edx, 0Fh
0x180007086  mov     qword ptr [rsp+68h+dwOptions], r15
0x18000708b  call    WPP_SF_SS
0x180007090  jmp     short loc_1800070E2
0x180007092  mov     r9d, [rsp+68h+pvData]
0x180007097  lea     r8, aD; "%d"
0x18000709e  mov     edx, 6; unsigned __int64
0x1800070a3  mov     rcx, rdi; unsigned __int16 *
0x1800070a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800070ab  mov     ebx, eax
0x1800070ad  test    eax, eax
0x1800070af  jns     short loc_1800070E2
0x1800070b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070b8  lea     rax, WPP_GLOBAL_Control
0x1800070bf  cmp     rcx, rax
0x1800070c2  jz      short loc_1800070E2
0x1800070c4  test    byte ptr [rcx+1Ch], 1
0x1800070c8  jz      short loc_1800070E2
0x1800070ca  mov     rcx, [rcx+10h]
0x1800070ce  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x1800070d5  mov     edx, 10h
0x1800070da  mov     r9d, ebx
0x1800070dd  call    WPP_SF_d
0x1800070e2  mov     rcx, [rsp+68h+hKey]; hKey
0x1800070ea  test    rcx, rcx
0x1800070ed  jz      short loc_1800070F5
0x1800070ef  call    cs:__imp_RegCloseKey
0x1800070f5  mov     eax, ebx
0x1800070f7  add     rsp, 50h
0x1800070fb  pop     r15
0x1800070fd  pop     rdi
0x1800070fe  pop     rbx
0x1800070ff  retn
```
