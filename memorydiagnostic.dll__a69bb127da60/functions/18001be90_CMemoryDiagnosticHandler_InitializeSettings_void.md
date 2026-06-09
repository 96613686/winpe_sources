# CMemoryDiagnosticHandler::InitializeSettings(void)

- ea: `0x18001be90`
- end: `0x18001c0cc`
- name: `?InitializeSettings@CMemoryDiagnosticHandler@@AEAAXXZ`
- size: `572`
- prototype: `void __fastcall(CMemoryDiagnosticHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d7a0`

## callees

- `0x18001bda8`
- `0x18001be90`
- `0x18001e24c`
- `0x18001e290`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18001beca`
- `ADVAPI32!RegOpenKeyExW` at `0x18001beca`
- `ADVAPI32!RegCloseKey` at `0x18001c0b6`
- `ADVAPI32!RegCloseKey` at `0x18001c0b6`

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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, v3, v2);
    goto LABEL_7;
  }
LABEL_8:
  if ( (*((_BYTE *)v9 + 28) & 4) != 0 && v9 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(*((_QWORD *)v9 + 2), 36, v3, *((unsigned int *)this + 16));
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, v10, *((unsigned int *)this + 14));
        v11 = WPP_GLOBAL_Control;
      }
      if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v11 + 2), 38, v10, *((unsigned int *)this + 17));
          v11 = WPP_GLOBAL_Control;
        }
        if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
          {
            WPP_SF_d(*((_QWORD *)v11 + 2), 39, v10, *((unsigned int *)this + 18));
            v11 = WPP_GLOBAL_Control;
          }
          if ( v11 != (CMemoryDiagnosticHandler *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v11 + 28) & 4) != 0 )
            {
              WPP_SF_d(*((_QWORD *)v11 + 2), 40, v10, *((unsigned int *)this + 15));
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
0x18001be90  mov     r11, rsp
0x18001be93  mov     [r11+8], rbx
0x18001be97  mov     [r11+18h], rsi
0x18001be9b  push    rdi
0x18001be9c  sub     rsp, 30h
0x18001bea0  mov     rbx, rcx
0x18001bea3  mov     qword ptr [r11+10h], 0
0x18001beab  lea     rax, [r11+10h]
0x18001beaf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001beb6  mov     r9d, 20019h; samDesired
0x18001bebc  mov     [r11-18h], rax
0x18001bec0  xor     r8d, r8d; ulOptions
0x18001bec3  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MemoryDiagnostic"
0x18001beca  call    cs:__imp_RegOpenKeyExW
0x18001bed0  lea     rdi, WPP_GLOBAL_Control
0x18001bed7  mov     esi, 4
0x18001bedc  test    eax, eax
0x18001bede  jnz     loc_18001BFA1
0x18001bee4  mov     rcx, [rsp+38h+hKey]; this
0x18001bee9  test    rcx, rcx
0x18001beec  jz      loc_18001BFA1
0x18001bef2  lea     rax, [rbx+40h]
0x18001bef6  mov     r9d, esi; unsigned int
0x18001bef9  lea     r8, aBugcheckthresh; "BugCheckThreshold"
0x18001bf00  mov     [rsp+38h+var_18], rax; void *
0x18001bf05  mov     rdx, rcx; HKEY
0x18001bf08  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf0d  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001bf12  lea     rax, [rbx+38h]
0x18001bf16  mov     r9d, esi; unsigned int
0x18001bf19  mov     [rsp+38h+var_18], rax; void *
0x18001bf1e  lea     r8, aAppcrashthresh; "AppCrashThreshold"
0x18001bf25  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf2a  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001bf2f  lea     rax, [rbx+44h]
0x18001bf33  mov     r9d, esi; unsigned int
0x18001bf36  mov     [rsp+38h+var_18], rax; void *
0x18001bf3b  lea     r8, aPagenotzerothr; "PageNotZeroThreshold"
0x18001bf42  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf47  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001bf4c  lea     rax, [rbx+48h]
0x18001bf50  mov     r9d, esi; unsigned int
0x18001bf53  mov     [rsp+38h+var_18], rax; void *
0x18001bf58  lea     r8, aStorecorruptio; "StoreCorruptionThreshold"
0x18001bf5f  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf64  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001bf69  lea     rax, [rbx+3Ch]
0x18001bf6d  mov     r9d, esi; unsigned int
0x18001bf70  mov     [rsp+38h+var_18], rax; void *
0x18001bf75  lea     r8, aBadpageremoval; "BadPageRemovalLimit"
0x18001bf7c  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf81  mov     rdx, [rsp+38h+hKey]; HKEY
0x18001bf86  lea     rax, [rbx+60h]
0x18001bf8a  lea     r9d, [rsi+7]; unsigned int
0x18001bf8e  mov     [rsp+38h+var_18], rax; void *
0x18001bf93  lea     r8, aLastscantime; "LastScanTime"
0x18001bf9a  call    ?InitializeSettingValue@CMemoryDiagnosticHandler@@AEAAXPEAUHKEY__@@PEBGKPEAX@Z; CMemoryDiagnosticHandler::InitializeSettingValue(HKEY__ *,ushort const *,ulong,void *)
0x18001bf9f  jmp     short loc_18001BFC4
0x18001bfa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfa8  cmp     rcx, rdi
0x18001bfab  jz      short loc_18001BFCB
0x18001bfad  test    byte ptr [rcx+1Ch], 2
0x18001bfb1  jz      short loc_18001BFCB
0x18001bfb3  mov     rcx, [rcx+10h]
0x18001bfb7  mov     edx, 23h ; '#'
0x18001bfbc  mov     r9d, eax
0x18001bfbf  call    WPP_SF_d
0x18001bfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfcb  test    [rcx+1Ch], sil
0x18001bfcf  jz      loc_18001C0AC
0x18001bfd5  cmp     rcx, rdi
0x18001bfd8  jz      loc_18001C0AC
0x18001bfde  mov     r9d, [rbx+40h]
0x18001bfe2  mov     edx, 24h ; '$'
0x18001bfe7  mov     rcx, [rcx+10h]
0x18001bfeb  call    WPP_SF_d
0x18001bff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bff7  cmp     rcx, rdi
0x18001bffa  jz      loc_18001C0AC
0x18001c000  test    [rcx+1Ch], sil
0x18001c004  jz      short loc_18001C01F
0x18001c006  mov     r9d, [rbx+38h]
0x18001c00a  mov     edx, 25h ; '%'
0x18001c00f  mov     rcx, [rcx+10h]
0x18001c013  call    WPP_SF_d
0x18001c018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c01f  cmp     rcx, rdi
0x18001c022  jz      loc_18001C0AC
0x18001c028  test    [rcx+1Ch], sil
0x18001c02c  jz      short loc_18001C047
0x18001c02e  mov     r9d, [rbx+44h]
0x18001c032  mov     edx, 26h ; '&'
0x18001c037  mov     rcx, [rcx+10h]
0x18001c03b  call    WPP_SF_d
0x18001c040  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c047  cmp     rcx, rdi
0x18001c04a  jz      short loc_18001C0AC
0x18001c04c  test    [rcx+1Ch], sil
0x18001c050  jz      short loc_18001C06B
0x18001c052  mov     r9d, [rbx+48h]
0x18001c056  mov     edx, 27h ; '''
0x18001c05b  mov     rcx, [rcx+10h]
0x18001c05f  call    WPP_SF_d
0x18001c064  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c06b  cmp     rcx, rdi
0x18001c06e  jz      short loc_18001C0AC
0x18001c070  test    [rcx+1Ch], sil
0x18001c074  jz      short loc_18001C08F
0x18001c076  mov     r9d, [rbx+3Ch]
0x18001c07a  mov     edx, 28h ; '('
0x18001c07f  mov     rcx, [rcx+10h]
0x18001c083  call    WPP_SF_d
0x18001c088  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c08f  cmp     rcx, rdi
0x18001c092  jz      short loc_18001C0AC
0x18001c094  test    [rcx+1Ch], sil
0x18001c098  jz      short loc_18001C0AC
0x18001c09a  mov     r9, [rbx+60h]
0x18001c09e  mov     edx, 29h ; ')'
0x18001c0a3  mov     rcx, [rcx+10h]
0x18001c0a7  call    WPP_SF_P
0x18001c0ac  mov     rcx, [rsp+38h+hKey]; hKey
0x18001c0b1  test    rcx, rcx
0x18001c0b4  jz      short loc_18001C0BC
0x18001c0b6  call    cs:__imp_RegCloseKey
0x18001c0bc  mov     rbx, [rsp+38h+arg_0]
0x18001c0c1  mov     rsi, [rsp+38h+arg_10]
0x18001c0c6  add     rsp, 30h
0x18001c0ca  pop     rdi
0x18001c0cb  retn
```
