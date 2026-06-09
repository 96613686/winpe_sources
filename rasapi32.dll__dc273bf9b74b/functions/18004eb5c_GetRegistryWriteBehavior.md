# GetRegistryWriteBehavior

- ea: `0x18004eb5c`
- end: `0x18004ec6b`
- name: `GetRegistryWriteBehavior`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180005af0`

## callees

- `0x18003e50c`
- `0x18004e580`
- `0x18004eb5c`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004eb9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004eb9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ec50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ec50`

## string_xrefs

- `0x18004eb8d`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x18004ebf5`: `RegWrite`

## pseudocode

```c
__int64 GetRegistryWriteBehavior()
{
  unsigned int v0; // eax
  unsigned int StringValue; // eax
  unsigned int v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  _BYTE pvData[16]; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config", 0, 0x20219u, &hKey);
  if ( v0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((char *)WPP_GLOBAL_Control + 28) < 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids, v0);
    }
    return 0;
  }
  else
  {
    StringValue = RegReadStringValue(hKey, "RegWrite", pvData, 0, 0xAu);
    v3 = 0;
    if ( StringValue != 2 )
    {
      LOBYTE(v3) = pvData[0] != 48;
      if ( StringValue )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids,
            StringValue);
        }
      }
    }
    RegCloseKey(hKey);
    return v3;
  }
}

```

## disassembly

```asm
0x18004eb5c  push    rbx
0x18004eb5e  sub     rsp, 50h
0x18004eb62  mov     rax, cs:__security_cookie
0x18004eb69  xor     rax, rsp
0x18004eb6c  mov     [rsp+58h+var_10], rax
0x18004eb71  lea     rax, [rsp+58h+hKey]
0x18004eb76  mov     [rsp+58h+hKey], 0
0x18004eb7f  mov     r9d, 20219h; samDesired
0x18004eb85  mov     [rsp+58h+phkResult], rax; phkResult
0x18004eb8a  xor     r8d, r8d; ulOptions
0x18004eb8d  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18004eb94  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004eb9b  call    cs:__imp_RegOpenKeyExA
0x18004eba1  test    eax, eax
0x18004eba3  jz      short loc_18004EBE0
0x18004eba5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ebac  lea     rdx, WPP_GLOBAL_Control
0x18004ebb3  cmp     rcx, rdx
0x18004ebb6  jz      short loc_18004EBDC
0x18004ebb8  test    byte ptr [rcx+1Ch], 80h
0x18004ebbc  jz      short loc_18004EBDC
0x18004ebbe  cmp     byte ptr [rcx+19h], 2
0x18004ebc2  jb      short loc_18004EBDC
0x18004ebc4  mov     rcx, [rcx+10h]
0x18004ebc8  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18004ebcf  mov     edx, 1Dh
0x18004ebd4  mov     r9d, eax
0x18004ebd7  call    WPP_SF_d
0x18004ebdc  xor     eax, eax
0x18004ebde  jmp     short loc_18004EC58
0x18004ebe0  mov     rcx, [rsp+58h+hKey]; hkey
0x18004ebe5  lea     r8, [rsp+58h+pvData]; pvData
0x18004ebea  xor     r9d, r9d; lpSubKey
0x18004ebed  mov     dword ptr [rsp+58h+phkResult], 0Ah; DWORD
0x18004ebf5  lea     rdx, aRegwrite; "RegWrite"
0x18004ebfc  call    RegReadStringValue
0x18004ec01  xor     ebx, ebx
0x18004ec03  cmp     eax, 2
0x18004ec06  jz      short loc_18004EC4B
0x18004ec08  cmp     [rsp+58h+pvData], 30h ; '0'
0x18004ec0d  setnz   bl
0x18004ec10  test    eax, eax
0x18004ec12  jz      short loc_18004EC4B
0x18004ec14  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ec1b  lea     rdx, WPP_GLOBAL_Control
0x18004ec22  cmp     rcx, rdx
0x18004ec25  jz      short loc_18004EC4B
0x18004ec27  test    byte ptr [rcx+1Ch], 80h
0x18004ec2b  jz      short loc_18004EC4B
0x18004ec2d  cmp     byte ptr [rcx+19h], 2
0x18004ec31  jb      short loc_18004EC4B
0x18004ec33  mov     rcx, [rcx+10h]
0x18004ec37  lea     r8, WPP_aa3d3933af4637b2ab2179f602a86832_Traceguids
0x18004ec3e  mov     edx, 1Eh
0x18004ec43  mov     r9d, eax
0x18004ec46  call    WPP_SF_d
0x18004ec4b  mov     rcx, [rsp+58h+hKey]; hKey
0x18004ec50  call    cs:__imp_RegCloseKey
0x18004ec56  mov     eax, ebx
0x18004ec58  mov     rcx, [rsp+58h+var_10]
0x18004ec5d  xor     rcx, rsp; StackCookie
0x18004ec60  call    __security_check_cookie
0x18004ec65  add     rsp, 50h
0x18004ec69  pop     rbx
0x18004ec6a  retn
```
