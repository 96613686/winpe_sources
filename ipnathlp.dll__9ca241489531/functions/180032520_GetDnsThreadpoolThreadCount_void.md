# GetDnsThreadpoolThreadCount(void)

- ea: `0x180032520`
- end: `0x18003274d`
- name: `?GetDnsThreadpoolThreadCount@@YAKXZ`
- size: `557`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800323cc`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180032520`
- `0x18004e0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800326fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800326fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003261c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003261c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003269c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003269c`

## string_xrefs

- `0x180032566`: `System\CurrentControlSet\Services\SharedAccess\Parameters`
- `0x1800325b7`: `DnsThreadpoolThreadCount`

## pseudocode

```c
__int64 GetDnsThreadpoolThreadCount(void)
{
  unsigned int v0; // ebx
  PVOID *v1; // rcx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ValueName[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[64]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  }
  v0 = 128;
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  wcscpy(ValueName, L"DnsThreadpoolThreadCount");
  hKey = 0;
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData)
    && (unsigned int)(*(_DWORD *)Data - 1) <= 0x3FF )
  {
    v0 = *(_DWORD *)Data;
  }
  v1 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids, v0);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v1 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 0x10) != 0 && *((_BYTE *)v1 + 25) >= 6u )
    WPP_SF_(v1[2], 39, &WPP_6532b2ce8588302729379dde0e1b157e_Traceguids);
  return v0;
}

```

## disassembly

```asm
0x180032520  mov     [rsp-8+arg_0], rbx
0x180032525  mov     [rsp-8+arg_8], rsi
0x18003252a  push    rbp
0x18003252b  lea     rbp, [rsp-10h]
0x180032530  sub     rsp, 110h
0x180032537  mov     rax, cs:__security_cookie
0x18003253e  xor     rax, rsp
0x180032541  mov     [rbp+10h+var_10], rax
0x180032545  mov     rcx, cs:WPP_GLOBAL_Control
0x18003254c  lea     rsi, WPP_GLOBAL_Control
0x180032553  cmp     rcx, rsi
0x180032556  jnz     loc_1800326AB
0x18003255c  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180032562  lea     rdx, [rbp+10h+SubKey]; lpSubKey
0x180032566  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18003256d  mov     ebx, 80h
0x180032572  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180032579  xor     r8d, r8d; ulOptions
0x18003257c  movaps  xmmword ptr [rbp+10h+SubKey], xmm0
0x180032580  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032587  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18003258e  movaps  [rbp+10h+var_70], xmm0
0x180032592  lea     r9d, [rbx-7Fh]; samDesired
0x180032596  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18003259d  movaps  [rbp+10h+var_50], xmm0
0x1800325a1  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x1800325a8  movaps  [rbp+10h+var_80], xmm1
0x1800325ac  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x1800325b3  movaps  [rbp+10h+var_30], xmm0
0x1800325b7  movups  xmm0, xmmword ptr cs:aDnsthreadpoolt; "DnsThreadpoolThreadCount"
0x1800325be  mov     [rbp+10h+var_20], eax
0x1800325c1  movzx   eax, word ptr cs:aDnsthreadpoolt+30h; ""
0x1800325c8  movaps  [rbp+10h+var_60], xmm1
0x1800325cc  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x1800325d3  movups  xmmword ptr [rsp+110h+ValueName], xmm0
0x1800325d8  mov     [rsp+110h+var_A0], ax
0x1800325dd  lea     rax, [rsp+110h+hKey]
0x1800325e2  movups  xmm0, xmmword ptr cs:aDnsthreadpoolt+20h; "eadCount"
0x1800325e9  mov     [rsp+110h+hKey], 0
0x1800325f2  movaps  [rbp+10h+var_40], xmm1
0x1800325f6  movups  xmm1, xmmword ptr cs:aDnsthreadpoolt+10h; "dpoolThreadCount"
0x1800325fd  mov     [rsp+110h+cbData], 4
0x180032605  movups  [rsp+110h+var_B0], xmm0
0x18003260a  mov     dword ptr [rsp+110h+Data], 0
0x180032612  movups  [rsp+110h+var_C0], xmm1
0x180032617  mov     [rsp+110h+phkResult], rax; phkResult
0x18003261c  call    cs:__imp_RegOpenKeyExW
0x180032622  test    eax, eax
0x180032624  jz      loc_1800326D9
0x18003262a  mov     rcx, cs:WPP_GLOBAL_Control
0x180032631  cmp     rcx, rsi
0x180032634  jz      short loc_18003263C
0x180032636  test    byte ptr [rcx+1Ch], 10h
0x18003263a  jnz     short loc_180032672
0x18003263c  mov     rax, [rsp+110h+hKey]
0x180032641  test    rax, rax
0x180032644  jnz     short loc_180032699
0x180032646  cmp     rcx, rsi
0x180032649  jnz     loc_18003271F
0x18003264f  mov     eax, ebx
0x180032651  mov     rcx, [rbp+10h+var_10]
0x180032655  xor     rcx, rsp; StackCookie
0x180032658  call    __security_check_cookie
0x18003265d  lea     r11, [rsp+110h+var_s0]
0x180032665  mov     rbx, [r11+10h]
0x180032669  mov     rsi, [r11+18h]
0x18003266d  mov     rsp, r11
0x180032670  pop     rbp
0x180032671  retn
0x180032672  cmp     byte ptr [rcx+19h], 4
0x180032676  jb      short loc_18003263C
0x180032678  mov     rcx, [rcx+10h]
0x18003267c  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x180032683  mov     edx, 26h ; '&'
0x180032688  mov     r9d, ebx
0x18003268b  call    WPP_SF_d
0x180032690  mov     rcx, cs:WPP_GLOBAL_Control
0x180032697  jmp     short loc_18003263C
0x180032699  mov     rcx, rax; hKey
0x18003269c  call    cs:__imp_RegCloseKey
0x1800326a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800326a9  jmp     short loc_180032646
0x1800326ab  test    byte ptr [rcx+1Ch], 10h
0x1800326af  jz      loc_18003255C
0x1800326b5  cmp     byte ptr [rcx+19h], 6
0x1800326b9  jb      loc_18003255C
0x1800326bf  mov     rcx, [rcx+10h]
0x1800326c3  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x1800326ca  mov     edx, 25h ; '%'
0x1800326cf  call    WPP_SF_
0x1800326d4  jmp     loc_18003255C
0x1800326d9  mov     rcx, [rsp+110h+hKey]; hKey
0x1800326de  lea     rax, [rsp+110h+cbData]
0x1800326e3  mov     [rsp+110h+lpcbData], rax; lpcbData
0x1800326e8  lea     rdx, [rsp+110h+ValueName]; lpValueName
0x1800326ed  lea     rax, [rsp+110h+Data]
0x1800326f2  xor     r9d, r9d; lpType
0x1800326f5  xor     r8d, r8d; lpReserved
0x1800326f8  mov     [rsp+110h+phkResult], rax; lpData
0x1800326fd  call    cs:__imp_RegQueryValueExW
0x180032703  test    eax, eax
0x180032705  jnz     loc_18003262A
0x18003270b  mov     ecx, dword ptr [rsp+110h+Data]
0x18003270f  lea     eax, [rcx-1]
0x180032712  cmp     eax, 3FFh
0x180032717  cmovbe  ebx, ecx
0x18003271a  jmp     loc_18003262A
0x18003271f  test    byte ptr [rcx+1Ch], 10h
0x180032723  jz      loc_18003264F
0x180032729  cmp     byte ptr [rcx+19h], 6
0x18003272d  jb      loc_18003264F
0x180032733  mov     rcx, [rcx+10h]
0x180032737  lea     r8, WPP_6532b2ce8588302729379dde0e1b157e_Traceguids
0x18003273e  mov     edx, 27h ; '''
0x180032743  call    WPP_SF_
0x180032748  jmp     loc_18003264F
```
