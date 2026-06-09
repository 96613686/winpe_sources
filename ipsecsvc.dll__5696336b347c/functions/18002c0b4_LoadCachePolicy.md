# LoadCachePolicy

- ea: `0x18002c0b4`
- end: `0x18002c1e3`
- name: `LoadCachePolicy`
- size: `303`
- prototype: `__int64 __fastcall(int, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002c5a0`

## callees

- `0x18000e510`
- `0x18000f638`
- `0x180019d80`
- `0x18002c0b4`
- `0x18003947c`
- `0x180039c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c1cd`

## string_xrefs

- `0x18002c10c`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Parameters\Cache`
- `0x18002c145`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Parameters\Cache`

## pseudocode

```c
__int64 __fastcall LoadCachePolicy(int a1, _QWORD *a2)
{
  void *v4; // rcx
  unsigned int PolicyObjectFromRegistry; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h]

  hKey = 0;
  v11 = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  PolicyObjectFromRegistry = OpenRegistryIPSECRootKey(
                               (__int64)v4,
                               L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent\\Parameters\\Cache",
                               &hKey);
  v6 = PolicyObjectFromRegistry;
  if ( PolicyObjectFromRegistry )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 56;
LABEL_12:
        WPP_SF_d(v7[2], v8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, PolicyObjectFromRegistry);
        v7 = WPP_GLOBAL_Control;
        goto LABEL_13;
      }
      goto LABEL_13;
    }
    goto LABEL_16;
  }
  PolicyObjectFromRegistry = ReadPolicyObjectFromRegistry(hKey);
  v6 = PolicyObjectFromRegistry;
  if ( PolicyObjectFromRegistry )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v8 = 57;
        goto LABEL_12;
      }
LABEL_13:
      if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
        WPP_SF_SD(v7[2], 58, (unsigned int)WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, a1, v6);
    }
LABEL_16:
    *a2 = 0;
    goto LABEL_18;
  }
  *a2 = v11;
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18002c0b4  mov     [rsp+arg_0], rbx
0x18002c0b9  push    rsi
0x18002c0ba  push    rdi
0x18002c0bb  push    r14
0x18002c0bd  sub     rsp, 30h
0x18002c0c1  mov     rdi, rdx
0x18002c0c4  mov     [rsp+48h+hKey], 0
0x18002c0cd  mov     rsi, rcx
0x18002c0d0  mov     [rsp+48h+arg_18], 0
0x18002c0d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0e0  lea     r14, WPP_GLOBAL_Control
0x18002c0e7  cmp     rcx, r14
0x18002c0ea  jz      short loc_18002C107
0x18002c0ec  test    byte ptr [rcx+1Ch], 4
0x18002c0f0  jz      short loc_18002C107
0x18002c0f2  mov     rcx, [rcx+10h]
0x18002c0f6  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c0fd  mov     edx, 37h ; '7'
0x18002c102  call    WPP_SF_
0x18002c107  lea     r8, [rsp+48h+hKey]
0x18002c10c  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x18002c113  call    OpenRegistryIPSECRootKey
0x18002c118  mov     ebx, eax
0x18002c11a  test    eax, eax
0x18002c11c  jz      short loc_18002C13B
0x18002c11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c125  cmp     rcx, r14
0x18002c128  jz      loc_18002C1B2
0x18002c12e  test    byte ptr [rcx+1Ch], 10h
0x18002c132  jz      short loc_18002C18B
0x18002c134  mov     edx, 38h ; '8'
0x18002c139  jmp     short loc_18002C171
0x18002c13b  mov     rcx, [rsp+48h+hKey]; hKey
0x18002c140  lea     r9, [rsp+48h+arg_18]
0x18002c145  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x18002c14c  mov     rdx, rsi
0x18002c14f  call    ReadPolicyObjectFromRegistry
0x18002c154  mov     ebx, eax
0x18002c156  test    eax, eax
0x18002c158  jz      short loc_18002C1BB
0x18002c15a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c161  cmp     rcx, r14
0x18002c164  jz      short loc_18002C1B2
0x18002c166  test    byte ptr [rcx+1Ch], 10h
0x18002c16a  jz      short loc_18002C18B
0x18002c16c  mov     edx, 39h ; '9'
0x18002c171  mov     rcx, [rcx+10h]
0x18002c175  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c17c  mov     r9d, eax
0x18002c17f  call    WPP_SF_d
0x18002c184  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c18b  cmp     rcx, r14
0x18002c18e  jz      short loc_18002C1B2
0x18002c190  test    byte ptr [rcx+1Ch], 10h
0x18002c194  jz      short loc_18002C1B2
0x18002c196  mov     rcx, [rcx+10h]
0x18002c19a  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x18002c1a1  mov     edx, 3Ah ; ':'
0x18002c1a6  mov     [rsp+48h+var_28], ebx
0x18002c1aa  mov     r9, rsi
0x18002c1ad  call    WPP_SF_SD
0x18002c1b2  mov     qword ptr [rdi], 0
0x18002c1b9  jmp     short loc_18002C1C3
0x18002c1bb  mov     rax, [rsp+48h+arg_18]
0x18002c1c0  mov     [rdi], rax
0x18002c1c3  mov     rcx, [rsp+48h+hKey]; hKey
0x18002c1c8  test    rcx, rcx
0x18002c1cb  jz      short loc_18002C1D3
0x18002c1cd  call    cs:__imp_RegCloseKey
0x18002c1d3  mov     eax, ebx
0x18002c1d5  mov     rbx, [rsp+48h+arg_0]
0x18002c1da  add     rsp, 30h
0x18002c1de  pop     r14
0x18002c1e0  pop     rdi
0x18002c1e1  pop     rsi
0x18002c1e2  retn
```
