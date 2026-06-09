# StSetPlapKey(int)

- ea: `0x18001dff0`
- end: `0x18001e138`
- name: `?StSetPlapKey@@YAKH@Z`
- size: `328`
- prototype: `__int64 __fastcall(int)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000d638`
- `0x18000d920`

## callees

- `0x1800025f0`
- `0x18000a9c0`
- `0x18000c230`
- `0x18001bffc`
- `0x18001dff0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e08a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e08a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e0db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e0db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e0c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001e0c9`

## pseudocode

```c
__int64 __fastcall StSetPlapKey(int a1)
{
  struct _LIST_ENTRY *v2; // rcx
  unsigned int Dot3ServiceRootRegistryLocation; // ebx
  BYTE Data[8]; // [rsp+30h] [rbp-428h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-420h] BYREF
  WCHAR SubKey[512]; // [rsp+40h] [rbp-418h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 50, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids);
  }
  Dot3ServiceRootRegistryLocation = GetDot3ServiceRootRegistryLocation((__int64)v2, SubKey);
  if ( !Dot3ServiceRootRegistryLocation )
  {
    Dot3ServiceRootRegistryLocation = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
    if ( !Dot3ServiceRootRegistryLocation )
    {
      if ( a1 )
        *(_DWORD *)Data = 1;
      Dot3ServiceRootRegistryLocation = RegSetValueExW(hKey, L"L2NA8023Mode", 0, 4u, Data, 4u);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control[1].Flink,
      51,
      WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids,
      Dot3ServiceRootRegistryLocation);
  }
  return Dot3ServiceRootRegistryLocation;
}

```

## disassembly

```asm
0x18001dff0  mov     [rsp+arg_0], rbx
0x18001dff5  mov     [rsp+arg_8], rbp
0x18001dffa  push    rdi
0x18001dffb  sub     rsp, 450h
0x18001e002  mov     rax, cs:__security_cookie
0x18001e009  xor     rax, rsp
0x18001e00c  mov     [rsp+458h+var_18], rax
0x18001e014  mov     edi, ecx
0x18001e016  mov     [rsp+458h+hKey], 0
0x18001e01f  mov     dword ptr [rsp+458h+Data], 0
0x18001e027  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e02e  lea     rbp, WPP_GLOBAL_Control
0x18001e035  cmp     rcx, rbp
0x18001e038  jz      short loc_18001E05B
0x18001e03a  cmp     byte ptr [rcx+19h], 4
0x18001e03e  jb      short loc_18001E05B
0x18001e040  test    byte ptr [rcx+1Ch], 1
0x18001e044  jz      short loc_18001E05B
0x18001e046  mov     rcx, [rcx+10h]
0x18001e04a  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001e051  mov     edx, 32h ; '2'
0x18001e056  call    WPP_SF_
0x18001e05b  lea     rdx, [rsp+458h+SubKey]; unsigned __int16 *
0x18001e060  call    ?GetDot3ServiceRootRegistryLocation@@YAKKPEAG@Z; GetDot3ServiceRootRegistryLocation(ulong,ushort *)
0x18001e065  mov     ebx, eax
0x18001e067  test    eax, eax
0x18001e069  jnz     short loc_18001E0D1
0x18001e06b  lea     rax, [rsp+458h+hKey]
0x18001e070  mov     r9d, 20006h; samDesired
0x18001e076  xor     r8d, r8d; ulOptions
0x18001e079  mov     [rsp+458h+phkResult], rax; phkResult
0x18001e07e  lea     rdx, [rsp+458h+SubKey]; lpSubKey
0x18001e083  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e08a  call    cs:__imp_RegOpenKeyExW
0x18001e090  mov     ebx, eax
0x18001e092  test    eax, eax
0x18001e094  jnz     short loc_18001E0D1
0x18001e096  test    edi, edi
0x18001e098  jz      short loc_18001E0A2
0x18001e09a  mov     dword ptr [rsp+458h+Data], 1
0x18001e0a2  mov     rcx, [rsp+458h+hKey]; hKey
0x18001e0a7  lea     rax, [rsp+458h+Data]
0x18001e0ac  mov     [rsp+458h+cbData], 4; cbData
0x18001e0b4  lea     rdx, ValueName; "L2NA8023Mode"
0x18001e0bb  mov     r9d, 4; dwType
0x18001e0c1  mov     [rsp+458h+phkResult], rax; lpData
0x18001e0c6  xor     r8d, r8d; Reserved
0x18001e0c9  call    cs:__imp_RegSetValueExW
0x18001e0cf  mov     ebx, eax
0x18001e0d1  mov     rcx, [rsp+458h+hKey]; hKey
0x18001e0d6  test    rcx, rcx
0x18001e0d9  jz      short loc_18001E0E1
0x18001e0db  call    cs:__imp_RegCloseKey
0x18001e0e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e0e8  cmp     rcx, rbp
0x18001e0eb  jz      short loc_18001E111
0x18001e0ed  cmp     byte ptr [rcx+19h], 4
0x18001e0f1  jb      short loc_18001E111
0x18001e0f3  test    byte ptr [rcx+1Ch], 1
0x18001e0f7  jz      short loc_18001E111
0x18001e0f9  mov     rcx, [rcx+10h]
0x18001e0fd  lea     r8, WPP_8e5e49151a383bd98ed57de45d21f90a_Traceguids
0x18001e104  mov     edx, 33h ; '3'
0x18001e109  mov     r9d, ebx
0x18001e10c  call    WPP_SF_d
0x18001e111  mov     eax, ebx
0x18001e113  mov     rcx, [rsp+458h+var_18]
0x18001e11b  xor     rcx, rsp; StackCookie
0x18001e11e  call    __security_check_cookie
0x18001e123  lea     r11, [rsp+458h+var_8]
0x18001e12b  mov     rbx, [r11+10h]
0x18001e12f  mov     rbp, [r11+18h]
0x18001e133  mov     rsp, r11
0x18001e136  pop     rdi
0x18001e137  retn
```
