# InstallComponent(ushort *)

- ea: `0x1800018e0`
- end: `0x180001a0d`
- name: `?InstallComponent@@YAJPEAG@Z`
- size: `301`
- prototype: `__int64 __fastcall(wchar_t *String2)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800018e0`
- `0x180001ab0`
- `0x180002d14`
- `0x180002e64`
- `0x180002f84`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180001934`
- `msvcrt!_wcsicmp` at `0x180001934`
- `ADVAPI32!RegCloseKey` at `0x1800019bd`
- `ADVAPI32!RegCloseKey` at `0x1800019bd`
- `ADVAPI32!RegCreateKeyExW` at `0x18000199a`
- `ADVAPI32!RegCreateKeyExW` at `0x18000199a`

## pseudocode

```c
__int64 __fastcall InstallComponent(wchar_t *String2)
{
  signed int v2; // ebx
  int v3; // r14d
  __int64 v4; // rsi
  struct IIS_SETUP_REGISTRY_ENTRY (near **v5)[1]; // rdi
  HKEY v6; // rax
  LSTATUS v7; // eax
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  if ( String2 )
  {
    v2 = 0;
    v3 = Is64BitMachine();
    v4 = 0;
    do
    {
      v5 = &g_FileRegistrationList + 9 * v4;
      if ( (!*((_DWORD *)v5 + 16) || v3) && !_wcsicmp((const wchar_t *)*v5, String2) )
      {
        if ( v5[4] )
        {
          v2 = SetRegistryValue((struct IIS_SETUP_REGISTRY_ENTRY *)(&g_FileRegistrationList + 9 * v4));
        }
        else
        {
          hKey = 0;
          if ( v5 )
          {
            v2 = 0;
            v6 = ConvertStringToHKey((wchar_t *)v5[1]);
            v7 = RegCreateKeyExW(v6, (LPCWSTR)v5[2], 0, 0, 0, 4u, 0, &hKey, 0);
            if ( v7 )
            {
              if ( v7 > 0 )
                v2 = (unsigned __int16)v7 | 0x80070000;
              else
                v2 = v7;
            }
            if ( hKey )
            {
              RegCloseKey(hKey);
              hKey = 0;
            }
          }
          else
          {
            v2 = -2147024809;
          }
        }
        if ( v2 < 0 )
          break;
      }
      v4 = (unsigned int)(v4 + 1);
    }
    while ( (int)v4 < 598 );
  }
  else
  {
    v2 = -2147024809;
  }
  g_pDebug = (HGLOBAL)PuDeleteDebugPrintsObject();
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800018e0  mov     [rsp+arg_8], rbx
0x1800018e5  mov     [rsp+arg_10], rbp
0x1800018ea  push    rsi
0x1800018eb  push    rdi
0x1800018ec  push    r14
0x1800018ee  sub     rsp, 50h
0x1800018f2  mov     rbp, rcx
0x1800018f5  test    rcx, rcx
0x1800018f8  jnz     short loc_180001904
0x1800018fa  mov     ebx, 80070057h
0x1800018ff  jmp     loc_1800019EA
0x180001904  xor     ebx, ebx
0x180001906  call    ?Is64BitMachine@@YAHXZ; Is64BitMachine(void)
0x18000190b  mov     r14d, eax
0x18000190e  xor     esi, esi
0x180001910  lea     rcx, [rsi+rsi*8]
0x180001914  lea     rax, ?g_FileRegistrationList@@3PAY00UIIS_SETUP_REGISTRY_ENTRY@@A; IIS_SETUP_REGISTRY_ENTRY (near * g_FileRegistrationList)[1]
0x18000191b  lea     rdi, [rax+rcx*8]
0x18000191f  cmp     dword ptr [rdi+40h], 0
0x180001923  jz      short loc_18000192E
0x180001925  test    r14d, r14d
0x180001928  jz      loc_1800019DC
0x18000192e  mov     rcx, [rdi]; String1
0x180001931  mov     rdx, rbp; String2
0x180001934  call    cs:__imp__wcsicmp
0x18000193a  test    eax, eax
0x18000193c  jnz     loc_1800019DC
0x180001942  cmp     qword ptr [rdi+20h], 0
0x180001947  jnz     loc_1800019CE
0x18000194d  mov     [rsp+68h+hKey], 0
0x180001956  test    rdi, rdi
0x180001959  jnz     short loc_180001962
0x18000195b  mov     ebx, 80070057h
0x180001960  jmp     short loc_1800019D8
0x180001962  mov     rcx, [rdi+8]; String1
0x180001966  xor     ebx, ebx
0x180001968  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x18000196d  mov     rdx, [rdi+10h]; lpSubKey
0x180001971  lea     rcx, [rsp+68h+hKey]
0x180001976  mov     [rsp+68h+lpdwDisposition], rbx; lpdwDisposition
0x18000197b  xor     r9d, r9d; lpClass
0x18000197e  mov     [rsp+68h+phkResult], rcx; phkResult
0x180001983  xor     r8d, r8d; Reserved
0x180001986  mov     [rsp+68h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000198b  mov     rcx, rax; hKey
0x18000198e  mov     [rsp+68h+samDesired], 4; samDesired
0x180001996  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x18000199a  call    cs:__imp_RegCreateKeyExW
0x1800019a0  test    eax, eax
0x1800019a2  jz      short loc_1800019B3
0x1800019a4  jg      short loc_1800019AA
0x1800019a6  mov     ebx, eax
0x1800019a8  jmp     short loc_1800019B3
0x1800019aa  movzx   ebx, ax
0x1800019ad  or      ebx, 80070000h
0x1800019b3  mov     rcx, [rsp+68h+hKey]; hKey
0x1800019b8  test    rcx, rcx
0x1800019bb  jz      short loc_1800019D8
0x1800019bd  call    cs:__imp_RegCloseKey
0x1800019c3  mov     [rsp+68h+hKey], 0
0x1800019cc  jmp     short loc_1800019D8
0x1800019ce  mov     rcx, rdi; struct IIS_SETUP_REGISTRY_ENTRY *
0x1800019d1  call    ?SetRegistryValue@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z; SetRegistryValue(IIS_SETUP_REGISTRY_ENTRY *)
0x1800019d6  mov     ebx, eax
0x1800019d8  test    ebx, ebx
0x1800019da  js      short loc_1800019EA
0x1800019dc  inc     esi
0x1800019de  cmp     esi, 256h
0x1800019e4  jl      loc_180001910
0x1800019ea  call    PuDeleteDebugPrintsObject
0x1800019ef  lea     r11, [rsp+68h+var_18]
0x1800019f4  mov     cs:g_pDebug, rax
0x1800019fb  mov     rbp, [r11+30h]
0x1800019ff  mov     eax, ebx
0x180001a01  mov     rbx, [r11+28h]
0x180001a05  mov     rsp, r11
0x180001a08  pop     r14
0x180001a0a  pop     rdi
0x180001a0b  pop     rsi
0x180001a0c  retn
```
