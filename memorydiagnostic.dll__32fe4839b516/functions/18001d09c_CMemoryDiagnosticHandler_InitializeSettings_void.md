# CMemoryDiagnosticHandler::InitializeSettings(void)

- ea: `0x18001d09c`
- end: `0x18001d2e2`
- name: `?InitializeSettings@CMemoryDiagnosticHandler@@AEAAXXZ`
- size: `582`
- prototype: `void __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ead0`

## callees

- `0x18001cfb8`
- `0x18001d09c`
- `0x18001f594`
- `0x18001f5dc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001d0d3`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d0d3`
- `ADVAPI32!RegCloseKey` at `0x18001d2c5`
- `ADVAPI32!RegCloseKey` at `0x18001d2c5`

## pseudocode

```c
void __fastcall CMemoryDiagnosticHandler::InitializeSettings(CMemoryDiagnosticHandler *this)
{
  unsigned int v2; // eax
  __int64 v3; // r8
  CMemoryDiagnosticHandler *v4; // rcx
  CMemoryDiagnosticHandler *v5; // rcx
  CMemoryDiagnosticHandler *v6; // rcx
  CMemoryDiagnosticHandler *v7; // rcx
  CMemoryDiagnosticHandler *v8; // rcx
  CMemoryDiagnosticHandler *v9; // rcx
  __int64 v10; // r8
  CMemoryDiagnosticHandler *v11; // rcx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MemoryDiagnostic", 0, 0x20019u, &hKey);
  if ( !v2 && hKey )
  {
    CMemoryDiagnosticHandler::InitializeSettingValue(
      (CMemoryDiagnosticHandler *)hKey,
      hKey,
      L"BugCheckThreshold",
      4u,
      (char *)this + 64);
    CMemoryDiagnosticHandler::InitializeSettingValue(v4, hKey, L"AppCrashThreshold", 4u, (char *)this + 56);
    CMemoryDiagnosticHandler::InitializeSettingValue(v5, hKey, L"PageNotZeroThreshold", 4u, (char *)this + 68);
    CMemoryDiagnosticHandler::InitializeSettingValue(v6, hKey, L"StoreCorruptionThreshold", 4u, (char *)this + 72);
    CMemoryDiagnosticHandler::InitializeSettingValue(v7, hKey, L"BadPageRemovalLimit", 4u, (char *)this + 60);
    CMemoryDiagnosticHandler::InitializeSettingValue(v8, hKey, L"LastScanTime", 0xBu, (char *)this + 96);
LABEL_7:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_8;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v3, v2);
    goto LABEL_7;
  }
LABEL_8:
  if ( (*((_BYTE *)v9 + 28) & 4) != 0 && v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
  {
    WPP_SF_D(*((_QWORD *)v9 + 2), 36, v3, *((unsigned int *)this + 16));
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v10, *((unsigned int *)this + 14));
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
        {
          WPP_SF_D(*((_QWORD *)v11 + 2), 38, v10, *((unsigned int *)this + 17));
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
          {
            WPP_SF_D(*((_QWORD *)v11 + 2), 39, v10, *((unsigned int *)this + 18));
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
            {
              WPP_SF_D(*((_QWORD *)v11 + 2), 40, v10, *((unsigned int *)this + 15));
              v11 = WPP_GLOBAL_Control;
            }
            if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
              WPP_SF_P(*((_QWORD *)v11 + 2), 41, v10, *((_QWORD *)this + 12));
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18001d09c  mov     r11, rsp
0x18001d09f  mov     [r11+8], rbx
0x18001d0a3  mov     [r11+18h], rsi
0x18001d0a7  push    rdi
0x18001d0a8  sub     rsp, 30h
0x18001d0ac  and     qword ptr [r11+10h], 0
0x18001d0b1  lea     rax, [r11+10h]
0x18001d0b5  mov     rbx, rcx
0x18001d0b8  mov     [r11-18h], rax
0x18001d0bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d0c3  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001d0ca  mov     r9d, 20019h; samDesired
0x18001d0d0  xor     r8d, r8d; ulOptions
0x18001d0d3  call    cs:__imp_RegOpenKeyExW
0x18001d0da  nop     dword ptr [rax+rax+00h]
0x18001d0df  lea     rdi, WPP_GLOBAL_Control
0x18001d0e6  mov     esi, 4
0x18001d0eb  test    eax, eax
0x18001d0ed  jnz     loc_18001D1B0
0x18001d0f3  mov     rcx, [rsp+38h+hKey]; this
0x18001d0f8  test    rcx, rcx
0x18001d0fb  jz      loc_18001D1B0
0x18001d101  lea     rax, [rbx+40h]
0x18001d105  mov     r9d, esi; unsigned int
0x18001d108  lea     r8, aBugcheckthresh; "BugCheckThreshold"
0x18001d10f  mov     [rsp+38h+var_18], rax; void *
0x18001d114  mov     rdx, rcx; HKEY
0x18001d117  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d11c  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001d121  lea     rax, [rbx+38h]
0x18001d125  mov     r9d, esi; unsigned int
0x18001d128  mov     [rsp+38h+var_18], rax; void *
0x18001d12d  lea     r8, aAppcrashthresh; "AppCrashThreshold"
0x18001d134  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d139  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001d13e  lea     rax, [rbx+44h]
0x18001d142  mov     r9d, esi; unsigned int
0x18001d145  mov     [rsp+38h+var_18], rax; void *
0x18001d14a  lea     r8, aPagenotzerothr; "PageNotZeroThreshold"
0x18001d151  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d156  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001d15b  lea     rax, [rbx+48h]
0x18001d15f  mov     r9d, esi; unsigned int
0x18001d162  mov     [rsp+38h+var_18], rax; void *
0x18001d167  lea     r8, aStorecorruptio; "StoreCorruptionThreshold"
0x18001d16e  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d173  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001d178  lea     rax, [rbx+3Ch]
0x18001d17c  mov     r9d, esi; unsigned int
0x18001d17f  mov     [rsp+38h+var_18], rax; void *
0x18001d184  lea     r8, aBadpageremoval; "BadPageRemovalLimit"
0x18001d18b  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d190  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001d195  lea     rax, [rbx+60h]
0x18001d199  lea     r9d, [rsi+7]; unsigned int
0x18001d19d  mov     [rsp+38h+var_18], rax; void *
0x18001d1a2  lea     r8, aLastscantime; "LastScanTime"
0x18001d1a9  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001d1ae  jmp     short loc_18001D1D3
0x18001d1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1b7  cmp     rcx, rdi
0x18001d1ba  jz      short loc_18001D1DA
0x18001d1bc  test    byte ptr [rcx+1Ch], 2
0x18001d1c0  jz      short loc_18001D1DA
0x18001d1c2  mov     rcx, [rcx+10h]
0x18001d1c6  mov     edx, 23h ; '#'
0x18001d1cb  mov     r9d, eax
0x18001d1ce  call    WPP_SF_D
0x18001d1d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d1da  test    [rcx+1Ch], sil
0x18001d1de  jz      loc_18001D2BB
0x18001d1e4  cmp     rcx, rdi
0x18001d1e7  jz      loc_18001D2BB
0x18001d1ed  mov     r9d, [rbx+40h]
0x18001d1f1  mov     edx, 24h ; '$'
0x18001d1f6  mov     rcx, [rcx+10h]
0x18001d1fa  call    WPP_SF_D
0x18001d1ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d206  cmp     rcx, rdi
0x18001d209  jz      loc_18001D2BB
0x18001d20f  test    [rcx+1Ch], sil
0x18001d213  jz      short loc_18001D22E
0x18001d215  mov     r9d, [rbx+38h]
0x18001d219  mov     edx, 25h ; '%'
0x18001d21e  mov     rcx, [rcx+10h]
0x18001d222  call    WPP_SF_D
0x18001d227  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d22e  cmp     rcx, rdi
0x18001d231  jz      loc_18001D2BB
0x18001d237  test    [rcx+1Ch], sil
0x18001d23b  jz      short loc_18001D256
0x18001d23d  mov     r9d, [rbx+44h]
0x18001d241  mov     edx, 26h ; '&'
0x18001d246  mov     rcx, [rcx+10h]
0x18001d24a  call    WPP_SF_D
0x18001d24f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d256  cmp     rcx, rdi
0x18001d259  jz      short loc_18001D2BB
0x18001d25b  test    [rcx+1Ch], sil
0x18001d25f  jz      short loc_18001D27A
0x18001d261  mov     r9d, [rbx+48h]
0x18001d265  mov     edx, 27h ; '''
0x18001d26a  mov     rcx, [rcx+10h]
0x18001d26e  call    WPP_SF_D
0x18001d273  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d27a  cmp     rcx, rdi
0x18001d27d  jz      short loc_18001D2BB
0x18001d27f  test    [rcx+1Ch], sil
0x18001d283  jz      short loc_18001D29E
0x18001d285  mov     r9d, [rbx+3Ch]
0x18001d289  mov     edx, 28h ; '('
0x18001d28e  mov     rcx, [rcx+10h]
0x18001d292  call    WPP_SF_D
0x18001d297  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d29e  cmp     rcx, rdi
0x18001d2a1  jz      short loc_18001D2BB
0x18001d2a3  test    [rcx+1Ch], sil
0x18001d2a7  jz      short loc_18001D2BB
0x18001d2a9  mov     r9, [rbx+60h]
0x18001d2ad  mov     edx, 29h ; ')'
0x18001d2b2  mov     rcx, [rcx+10h]
0x18001d2b6  call    WPP_SF_P
0x18001d2bb  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d2c0  test    rcx, rcx
0x18001d2c3  jz      short loc_18001D2D1
0x18001d2c5  call    cs:__imp_RegCloseKey
0x18001d2cc  nop     dword ptr [rax+rax+00h]
0x18001d2d1  mov     rbx, [rsp+38h+arg_0]
0x18001d2d6  mov     rsi, [rsp+38h+arg_10]
0x18001d2db  add     rsp, 30h
0x18001d2df  pop     rdi
0x18001d2e0  retn
```
