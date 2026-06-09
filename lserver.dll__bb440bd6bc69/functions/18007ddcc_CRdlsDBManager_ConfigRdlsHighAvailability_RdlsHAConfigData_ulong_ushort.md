# CRdlsDBManager::ConfigRdlsHighAvailability(_RdlsHAConfigData *,ulong *,ushort * *)

- ea: `0x18007ddcc`
- end: `0x18007e044`
- name: `?ConfigRdlsHighAvailability@CRdlsDBManager@@QEAAKPEAU_RdlsHAConfigData@@PEAKPEAPEAG@Z`
- size: `632`
- prototype: `unsigned int(CRdlsDBManager *__hidden this, struct _RdlsHAConfigData *, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180010dc0`

## callees

- `0x18007ddcc`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18007de4b`
- `ADVAPI32!RegSetValueExW` at `0x18007de80`
- `ADVAPI32!RegSetValueExW` at `0x18007df0f`
- `ADVAPI32!RegSetValueExW` at `0x18007df5f`
- `ADVAPI32!RegSetValueExW` at `0x18007dfaf`
- `ADVAPI32!RegSetValueExW` at `0x18007e01e`
- `ADVAPI32!RegSetValueExW` at `0x18007de4b`
- `ADVAPI32!RegSetValueExW` at `0x18007de80`
- `ADVAPI32!RegSetValueExW` at `0x18007df0f`
- `ADVAPI32!RegSetValueExW` at `0x18007df5f`
- `ADVAPI32!RegSetValueExW` at `0x18007dfaf`
- `ADVAPI32!RegSetValueExW` at `0x18007e01e`
- `ADVAPI32!RegOpenKeyExW` at `0x18007de0d`
- `ADVAPI32!RegOpenKeyExW` at `0x18007de0d`
- `tlscsp!__imp_LsCsp_StoreSecret` at `0x18007debf`
- `tlscsp!__imp_LsCsp_StoreSecret` at `0x18007dfe2`
- `tlscsp!__imp_LsCsp_StoreSecret` at `0x18007debf`
- `tlscsp!__imp_LsCsp_StoreSecret` at `0x18007dfe2`

## string_xrefs

- `0x18007ddfb`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x18007e002`: `RdlsSecretsCacheType`

## pseudocode

```c
__int64 __fastcall CRdlsDBManager::ConfigRdlsHighAvailability(
        CRdlsDBManager *this,
        BYTE *a2,
        unsigned int *a3,
        unsigned __int16 **a4)
{
  unsigned int v6; // ecx
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 v9; // r8
  const BYTE *v10; // rdx
  __int64 v11; // rax
  const BYTE *v12; // rdx
  __int64 v13; // rax
  const BYTE *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rdx
  HKEY v17; // rcx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
         0,
         2u,
         &hKey);
  if ( !v6 )
  {
    if ( a4 )
      *a4 = 0;
    v6 = RegSetValueExW(hKey, L"IsSQLDB", 0, 4u, a2, 4u);
    if ( !v6 )
    {
      v6 = RegSetValueExW(hKey, L"UseIntegratedAuth", 0, 4u, a2 + 4, 4u);
      if ( !v6 )
      {
        v7 = *((_QWORD *)a2 + 1);
        v8 = -1;
        if ( !v7 )
          goto LABEL_10;
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)(v7 + 2 * v9) );
        v6 = LsCsp_StoreSecret(L"SqlConnString", v7, (unsigned int)(2 * v9 + 2));
        if ( !v6 )
        {
LABEL_10:
          v10 = (const BYTE *)*((_QWORD *)a2 + 2);
          if ( !v10 )
            goto LABEL_30;
          v11 = -1;
          do
            ++v11;
          while ( *(_WORD *)&v10[2 * v11] );
          v6 = RegSetValueExW(hKey, L"SqlDriverName", 0, 1u, v10, 2 * v11 + 2);
          if ( !v6 )
          {
LABEL_30:
            v12 = (const BYTE *)*((_QWORD *)a2 + 3);
            if ( !v12 )
              goto LABEL_31;
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)&v12[2 * v13] );
            v6 = RegSetValueExW(hKey, L"SqlServerName", 0, 1u, v12, 2 * v13 + 2);
            if ( !v6 )
            {
LABEL_31:
              v14 = (const BYTE *)*((_QWORD *)a2 + 4);
              if ( !v14 )
                goto LABEL_32;
              v15 = -1;
              do
                ++v15;
              while ( *(_WORD *)&v14[2 * v15] );
              v6 = RegSetValueExW(hKey, L"SqlServerUserName", 0, 1u, v14, 2 * v15 + 2);
              if ( !v6 )
              {
LABEL_32:
                v16 = *((_QWORD *)a2 + 5);
                if ( !v16 )
                  goto LABEL_25;
                do
                  ++v8;
                while ( *(_WORD *)(v16 + 2 * v8) );
                v6 = LsCsp_StoreSecret(L"SqlServerUserPwd", v16, (unsigned int)(2 * v8 + 2));
                if ( !v6 )
                {
LABEL_25:
                  if ( (unsigned int)(*(_DWORD *)a2 - 1) <= 1 )
                  {
                    v17 = hKey;
                    *(_DWORD *)a2 = 3;
                    return (unsigned int)RegSetValueExW(v17, L"RdlsSecretsCacheType", 0, 4u, a2, 4u);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18007ddcc  mov     r11, rsp
0x18007ddcf  mov     [r11+8], rbx
0x18007ddd3  mov     [r11+10h], rbp
0x18007ddd7  mov     [r11+20h], rsi
0x18007dddb  mov     [r11+18h], r8
0x18007dddf  push    rdi
0x18007dde0  sub     rsp, 30h
0x18007dde4  xor     esi, esi
0x18007dde6  lea     rax, [r11+18h]
0x18007ddea  mov     rdi, r9
0x18007dded  mov     [r11+18h], rsi
0x18007ddf1  mov     rbx, rdx
0x18007ddf4  mov     [r11-18h], rax
0x18007ddf8  xor     r8d, r8d; ulOptions
0x18007ddfb  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x18007de02  lea     r9d, [rsi+2]; samDesired
0x18007de06  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007de0d  call    cs:__imp_RegOpenKeyExW
0x18007de14  nop     dword ptr [rax+rax+00h]
0x18007de19  mov     ecx, eax
0x18007de1b  test    eax, eax
0x18007de1d  jnz     loc_18007E02C
0x18007de23  test    rdi, rdi
0x18007de26  jz      short loc_18007DE2B
0x18007de28  mov     [rdi], rsi
0x18007de2b  mov     rcx, [rsp+38h+hKey]; hKey
0x18007de30  lea     rdx, aIssqldb; "IsSQLDB"
0x18007de37  mov     ebp, 4
0x18007de3c  xor     r8d, r8d; Reserved
0x18007de3f  mov     [rsp+38h+cbData], ebp; cbData
0x18007de43  mov     r9d, ebp; dwType
0x18007de46  mov     [rsp+38h+lpData], rbx; lpData
0x18007de4b  call    cs:__imp_RegSetValueExW
0x18007de52  nop     dword ptr [rax+rax+00h]
0x18007de57  mov     ecx, eax
0x18007de59  test    eax, eax
0x18007de5b  jnz     loc_18007E02C
0x18007de61  mov     rcx, [rsp+38h+hKey]; hKey
0x18007de66  lea     rax, [rbx+4]
0x18007de6a  mov     [rsp+38h+cbData], ebp; cbData
0x18007de6e  lea     rdx, aUseintegrateda; "UseIntegratedAuth"
0x18007de75  mov     r9d, ebp; dwType
0x18007de78  mov     [rsp+38h+lpData], rax; lpData
0x18007de7d  xor     r8d, r8d; Reserved
0x18007de80  call    cs:__imp_RegSetValueExW
0x18007de87  nop     dword ptr [rax+rax+00h]
0x18007de8c  mov     ecx, eax
0x18007de8e  test    eax, eax
0x18007de90  jnz     loc_18007E02C
0x18007de96  mov     rdx, [rbx+8]
0x18007de9a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007de9e  test    rdx, rdx
0x18007dea1  jz      short loc_18007DED5
0x18007dea3  mov     r8, rdi
0x18007dea6  inc     r8
0x18007dea9  cmp     [rdx+r8*2], si
0x18007deae  jnz     short loc_18007DEA6
0x18007deb0  lea     r8d, ds:2[r8*2]
0x18007deb8  lea     rcx, aSqlconnstring; "SqlConnString"
0x18007debf  call    cs:__imp_LsCsp_StoreSecret
0x18007dec6  nop     dword ptr [rax+rax+00h]
0x18007decb  mov     ecx, eax
0x18007decd  test    eax, eax
0x18007decf  jnz     loc_18007E02C
0x18007ded5  mov     rdx, [rbx+10h]
0x18007ded9  test    rdx, rdx
0x18007dedc  jz      short loc_18007DF25
0x18007dede  mov     rax, rdi
0x18007dee1  inc     rax
0x18007dee4  cmp     [rdx+rax*2], si
0x18007dee8  jnz     short loc_18007DEE1
0x18007deea  mov     rcx, [rsp+38h+hKey]; hKey
0x18007deef  lea     eax, ds:2[rax*2]
0x18007def6  mov     [rsp+38h+cbData], eax; cbData
0x18007defa  mov     r9d, 1; dwType
0x18007df00  mov     [rsp+38h+lpData], rdx; lpData
0x18007df05  xor     r8d, r8d; Reserved
0x18007df08  lea     rdx, aSqldrivername; "SqlDriverName"
0x18007df0f  call    cs:__imp_RegSetValueExW
0x18007df16  nop     dword ptr [rax+rax+00h]
0x18007df1b  mov     ecx, eax
0x18007df1d  test    eax, eax
0x18007df1f  jnz     loc_18007E02C
0x18007df25  mov     rdx, [rbx+18h]
0x18007df29  test    rdx, rdx
0x18007df2c  jz      short loc_18007DF75
0x18007df2e  mov     rax, rdi
0x18007df31  inc     rax
0x18007df34  cmp     [rdx+rax*2], si
0x18007df38  jnz     short loc_18007DF31
0x18007df3a  mov     rcx, [rsp+38h+hKey]; hKey
0x18007df3f  lea     eax, ds:2[rax*2]
0x18007df46  mov     [rsp+38h+cbData], eax; cbData
0x18007df4a  mov     r9d, 1; dwType
0x18007df50  mov     [rsp+38h+lpData], rdx; lpData
0x18007df55  xor     r8d, r8d; Reserved
0x18007df58  lea     rdx, aSqlservername; "SqlServerName"
0x18007df5f  call    cs:__imp_RegSetValueExW
0x18007df66  nop     dword ptr [rax+rax+00h]
0x18007df6b  mov     ecx, eax
0x18007df6d  test    eax, eax
0x18007df6f  jnz     loc_18007E02C
0x18007df75  mov     rdx, [rbx+20h]
0x18007df79  test    rdx, rdx
0x18007df7c  jz      short loc_18007DFC1
0x18007df7e  mov     rax, rdi
0x18007df81  inc     rax
0x18007df84  cmp     [rdx+rax*2], si
0x18007df88  jnz     short loc_18007DF81
0x18007df8a  mov     rcx, [rsp+38h+hKey]; hKey
0x18007df8f  lea     eax, ds:2[rax*2]
0x18007df96  mov     [rsp+38h+cbData], eax; cbData
0x18007df9a  mov     r9d, 1; dwType
0x18007dfa0  mov     [rsp+38h+lpData], rdx; lpData
0x18007dfa5  xor     r8d, r8d; Reserved
0x18007dfa8  lea     rdx, aSqlserverusern; "SqlServerUserName"
0x18007dfaf  call    cs:__imp_RegSetValueExW
0x18007dfb6  nop     dword ptr [rax+rax+00h]
0x18007dfbb  mov     ecx, eax
0x18007dfbd  test    eax, eax
0x18007dfbf  jnz     short loc_18007E02C
0x18007dfc1  mov     rdx, [rbx+28h]
0x18007dfc5  test    rdx, rdx
0x18007dfc8  jz      short loc_18007DFF4
0x18007dfca  inc     rdi
0x18007dfcd  cmp     [rdx+rdi*2], si
0x18007dfd1  jnz     short loc_18007DFCA
0x18007dfd3  lea     r8d, ds:2[rdi*2]
0x18007dfdb  lea     rcx, aSqlserveruserp; "SqlServerUserPwd"
0x18007dfe2  call    cs:__imp_LsCsp_StoreSecret
0x18007dfe9  nop     dword ptr [rax+rax+00h]
0x18007dfee  mov     ecx, eax
0x18007dff0  test    eax, eax
0x18007dff2  jnz     short loc_18007E02C
0x18007dff4  mov     eax, [rbx]
0x18007dff6  dec     eax
0x18007dff8  cmp     eax, 1
0x18007dffb  ja      short loc_18007E02C
0x18007dffd  mov     rcx, [rsp+38h+hKey]; hKey
0x18007e002  lea     rdx, aRdlssecretscac; "RdlsSecretsCacheType"
0x18007e009  mov     [rsp+38h+cbData], ebp; cbData
0x18007e00d  mov     r9d, ebp; dwType
0x18007e010  xor     r8d, r8d; Reserved
0x18007e013  mov     [rsp+38h+lpData], rbx; lpData
0x18007e018  mov     dword ptr [rbx], 3
0x18007e01e  call    cs:__imp_RegSetValueExW
0x18007e025  nop     dword ptr [rax+rax+00h]
0x18007e02a  mov     ecx, eax
0x18007e02c  mov     rbx, [rsp+38h+arg_0]
0x18007e031  mov     eax, ecx
0x18007e033  mov     rbp, [rsp+38h+arg_8]
0x18007e038  mov     rsi, [rsp+38h+arg_18]
0x18007e03d  add     rsp, 30h
0x18007e041  pop     rdi
0x18007e042  retn
```
