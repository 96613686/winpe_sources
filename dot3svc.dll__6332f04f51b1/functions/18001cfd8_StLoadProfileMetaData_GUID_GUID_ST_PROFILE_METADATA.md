# StLoadProfileMetaData(_GUID *,_GUID *,_ST_PROFILE_METADATA *)

- ea: `0x18001cfd8`
- end: `0x18001d162`
- name: `?StLoadProfileMetaData@@YAKPEAU_GUID@@0PEAU_ST_PROFILE_METADATA@@@Z`
- size: `394`
- prototype: `__int64 __fastcall(GUID *rguid, GUID *, struct _ST_PROFILE_METADATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000ddc8`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001cfd8`
- `0x18001e620`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d0a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d0a0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d0dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d0dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d10d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d10d`

## pseudocode

```c
__int64 __fastcall StLoadProfileMetaData(GUID *rguid, GUID *a2, struct _ST_PROFILE_METADATA *a3)
{
  unsigned int RegKeyPath; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  cbData = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 21, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  RegKeyPath = StpGetRegKeyPath(rguid, a2, 0, SubKey, 0x104u);
  if ( !RegKeyPath )
  {
    RegKeyPath = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey);
    if ( !RegKeyPath )
    {
      cbData = 4;
      RegKeyPath = RegQueryValueExW(hKey, L"Flags", 0, &Type, Data, &cbData);
      if ( !RegKeyPath )
      {
        if ( Type == 4 && cbData == 4 )
          *(_DWORD *)a3 = *(_DWORD *)Data;
        else
          RegKeyPath = 2;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids, RegKeyPath);
  }
  return RegKeyPath;
}

```

## disassembly

```asm
0x18001cfd8  push    rbp
0x18001cfda  push    rbx
0x18001cfdb  push    rsi
0x18001cfdc  push    rdi
0x18001cfdd  push    r12
0x18001cfdf  lea     rbp, [rsp-170h]
0x18001cfe7  sub     rsp, 270h
0x18001cfee  mov     rax, cs:__security_cookie
0x18001cff5  xor     rax, rsp
0x18001cff8  mov     [rbp+190h+var_30], rax
0x18001cfff  mov     rsi, r8
0x18001d002  mov     [rsp+290h+hKey], 0
0x18001d00b  mov     rdi, rdx
0x18001d00e  mov     dword ptr [rsp+290h+Data], 0
0x18001d016  mov     rbx, rcx
0x18001d019  mov     [rsp+290h+Type], 0
0x18001d021  mov     [rsp+290h+cbData], 0
0x18001d029  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d030  lea     r12, WPP_GLOBAL_Control
0x18001d037  cmp     rcx, r12
0x18001d03a  jz      short loc_18001D05D
0x18001d03c  cmp     byte ptr [rcx+19h], 4
0x18001d040  jb      short loc_18001D05D
0x18001d042  test    byte ptr [rcx+1Ch], 1
0x18001d046  jz      short loc_18001D05D
0x18001d048  mov     rcx, [rcx+10h]
0x18001d04c  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d053  mov     edx, 15h
0x18001d058  call    WPP_SF_
0x18001d05d  lea     r9, [rsp+290h+SubKey]; unsigned __int16 *
0x18001d062  mov     [rsp+290h+phkResult], 104h; unsigned __int64
0x18001d06b  xor     r8d, r8d; int
0x18001d06e  mov     rdx, rdi; GUID *
0x18001d071  mov     rcx, rbx; rguid
0x18001d074  call    ?StpGetRegKeyPath@@YAKPEBU_GUID@@0HPEAG_K@Z; StpGetRegKeyPath(_GUID const *,_GUID const *,int,ushort *,unsigned __int64)
0x18001d079  mov     ebx, eax
0x18001d07b  test    eax, eax
0x18001d07d  jnz     loc_18001D103
0x18001d083  lea     rax, [rsp+290h+hKey]
0x18001d088  xor     r8d, r8d; ulOptions
0x18001d08b  lea     r9d, [rbx+1]; samDesired
0x18001d08f  mov     [rsp+290h+phkResult], rax; phkResult
0x18001d094  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18001d099  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d0a0  call    cs:__imp_RegOpenKeyExW
0x18001d0a6  mov     ebx, eax
0x18001d0a8  test    eax, eax
0x18001d0aa  jnz     short loc_18001D103
0x18001d0ac  mov     rcx, [rsp+290h+hKey]; hKey
0x18001d0b1  lea     rax, [rsp+290h+cbData]
0x18001d0b6  mov     [rsp+290h+lpcbData], rax; lpcbData
0x18001d0bb  lea     r9, [rsp+290h+Type]; lpType
0x18001d0c0  lea     rax, [rsp+290h+Data]
0x18001d0c5  mov     [rsp+290h+cbData], 4
0x18001d0cd  xor     r8d, r8d; lpReserved
0x18001d0d0  mov     [rsp+290h+phkResult], rax; lpData
0x18001d0d5  lea     rdx, aFlags; "Flags"
0x18001d0dc  call    cs:__imp_RegQueryValueExW
0x18001d0e2  mov     ebx, eax
0x18001d0e4  test    eax, eax
0x18001d0e6  jnz     short loc_18001D103
0x18001d0e8  cmp     [rsp+290h+Type], 4
0x18001d0ed  jnz     short loc_18001D0FE
0x18001d0ef  cmp     [rsp+290h+cbData], 4
0x18001d0f4  jnz     short loc_18001D0FE
0x18001d0f6  mov     eax, dword ptr [rsp+290h+Data]
0x18001d0fa  mov     [rsi], eax
0x18001d0fc  jmp     short loc_18001D103
0x18001d0fe  mov     ebx, 2
0x18001d103  mov     rcx, [rsp+290h+hKey]; hKey
0x18001d108  test    rcx, rcx
0x18001d10b  jz      short loc_18001D113
0x18001d10d  call    cs:__imp_RegCloseKey
0x18001d113  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d11a  cmp     rcx, r12
0x18001d11d  jz      short loc_18001D143
0x18001d11f  cmp     byte ptr [rcx+19h], 4
0x18001d123  jb      short loc_18001D143
0x18001d125  test    byte ptr [rcx+1Ch], 1
0x18001d129  jz      short loc_18001D143
0x18001d12b  mov     rcx, [rcx+10h]
0x18001d12f  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001d136  mov     edx, 16h
0x18001d13b  mov     r9d, ebx
0x18001d13e  call    WPP_SF_d
0x18001d143  mov     eax, ebx
0x18001d145  mov     rcx, [rbp+190h+var_30]
0x18001d14c  xor     rcx, rsp; StackCookie
0x18001d14f  call    __security_check_cookie
0x18001d154  add     rsp, 270h
0x18001d15b  pop     r12
0x18001d15d  pop     rdi
0x18001d15e  pop     rsi
0x18001d15f  pop     rbx
0x18001d160  pop     rbp
0x18001d161  retn
```
