# GetEnableRebootPersistConnection(void)

- ea: `0x180042114`
- end: `0x1800422d7`
- name: `?GetEnableRebootPersistConnection@@YAHXZ`
- size: `451`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021fb8`
- `0x180074c04`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000fde0`
- `0x180041d80`
- `0x180042114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042215`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180042215`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042193`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180042193`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042242`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042242`

## string_xrefs

- `0x18004217c`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`
- `0x1800421cf`: `Software\Microsoft\Windows\CurrentVersion\SharedAccess`

## pseudocode

```c
__int64 GetEnableRebootPersistConnection(void)
{
  unsigned int v0; // edi
  LSTATUS v1; // eax
  signed int v2; // ebx
  PVOID *v3; // rcx
  PVOID v4; // rcx
  const char *v5; // r9
  int Data; // [rsp+50h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 327, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  Data = 0;
  v0 = 0;
  cbData = 4;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess", 0, 1u, &hKey);
  v2 = v1;
  if ( !v1 )
  {
    v2 = 0;
    if ( !RegQueryValueExW(hKey, L"EnableRebootPersistConnection", 0, 0, (LPBYTE)&Data, &cbData) )
      LOBYTE(v0) = Data == 1;
    goto LABEL_15;
  }
  if ( v1 > 0 )
    v2 = (unsigned __int16)v1 | 0x80070000;
  if ( v2 >= 0 )
  {
LABEL_15:
    v3 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_16;
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      328,
      (unsigned int)&WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
      (unsigned int)L"Software\\Microsoft\\Windows\\CurrentVersion\\SharedAccess",
      v2);
    goto LABEL_15;
  }
LABEL_16:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v3 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( v3 != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 4u )
    {
      v4 = v3[2];
      v5 = "TRUE";
      if ( !v0 )
        v5 = "FALSE";
      WPP_SF_s(v4, 329, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
      v3 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 != &WPP_GLOBAL_Control && (*((_DWORD *)v3 + 7) & 0x200) != 0 && *((_BYTE *)v3 + 25) >= 6u )
      WPP_SF_d(v3[2], 330, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, (unsigned int)v2);
  }
  return v0;
}

```

## disassembly

```asm
0x180042114  mov     [rsp+arg_18], rbx
0x180042119  push    rbp
0x18004211a  push    rdi
0x18004211b  push    r14
0x18004211d  sub     rsp, 30h
0x180042121  mov     rcx, cs:WPP_GLOBAL_Control
0x180042128  lea     r14, WPP_GLOBAL_Control
0x18004212f  mov     ebp, 200h
0x180042134  cmp     rcx, r14
0x180042137  jz      short loc_180042159
0x180042139  test    [rcx+1Ch], ebp
0x18004213c  jz      short loc_180042159
0x18004213e  cmp     byte ptr [rcx+19h], 6
0x180042142  jb      short loc_180042159
0x180042144  mov     rcx, [rcx+10h]
0x180042148  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004214f  mov     edx, 147h
0x180042154  call    WPP_SF_
0x180042159  lea     rax, [rsp+48h+hKey]
0x18004215e  mov     [rsp+48h+Data], 0
0x180042166  xor     edi, edi
0x180042168  mov     [rsp+48h+cbData], 4
0x180042170  xor     r8d, r8d; ulOptions
0x180042173  mov     [rsp+48h+hKey], 0
0x18004217c  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180042183  mov     [rsp+48h+phkResult], rax; phkResult
0x180042188  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004218f  lea     r9d, [rdi+1]; samDesired
0x180042193  call    cs:__imp_RegOpenKeyExW
0x18004219a  nop     dword ptr [rax+rax+00h]
0x18004219f  mov     ebx, eax
0x1800421a1  test    eax, eax
0x1800421a3  jz      short loc_1800421ED
0x1800421a5  jle     short loc_1800421B0
0x1800421a7  movzx   ebx, ax
0x1800421aa  or      ebx, 80070000h
0x1800421b0  test    ebx, ebx
0x1800421b2  jns     short loc_18004222E
0x1800421b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421bb  cmp     rcx, r14
0x1800421be  jz      short loc_180042235
0x1800421c0  test    [rcx+1Ch], ebp
0x1800421c3  jz      short loc_180042235
0x1800421c5  cmp     byte ptr [rcx+19h], 2
0x1800421c9  jb      short loc_180042235
0x1800421cb  mov     rcx, [rcx+10h]
0x1800421cf  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800421d6  mov     edx, 148h
0x1800421db  mov     dword ptr [rsp+48h+phkResult], ebx
0x1800421df  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800421e6  call    WPP_SF_Sd
0x1800421eb  jmp     short loc_18004222E
0x1800421ed  mov     rcx, [rsp+48h+hKey]; hKey
0x1800421f2  lea     rax, [rsp+48h+cbData]
0x1800421f7  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800421fc  lea     rdx, aEnablerebootpe; "EnableRebootPersistConnection"
0x180042203  lea     rax, [rsp+48h+Data]
0x180042208  xor     r9d, r9d; lpType
0x18004220b  xor     r8d, r8d; lpReserved
0x18004220e  mov     [rsp+48h+phkResult], rax; lpData
0x180042213  xor     ebx, ebx
0x180042215  call    cs:__imp_RegQueryValueExW
0x18004221c  nop     dword ptr [rax+rax+00h]
0x180042221  test    eax, eax
0x180042223  jnz     short loc_18004222E
0x180042225  cmp     [rsp+48h+Data], 1
0x18004222a  setz    dil
0x18004222e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042235  mov     rax, [rsp+48h+hKey]
0x18004223a  test    rax, rax
0x18004223d  jz      short loc_18004225E
0x18004223f  mov     rcx, rax; hKey
0x180042242  call    cs:__imp_RegCloseKey
0x180042249  nop     dword ptr [rax+rax+00h]
0x18004224e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042255  mov     [rsp+48h+hKey], 0
0x18004225e  cmp     rcx, r14
0x180042261  jz      short loc_1800422C6
0x180042263  test    [rcx+1Ch], ebp
0x180042266  jz      short loc_18004229E
0x180042268  cmp     byte ptr [rcx+19h], 4
0x18004226c  jb      short loc_18004229E
0x18004226e  mov     rcx, [rcx+10h]
0x180042272  lea     rax, aFalse; "FALSE"
0x180042279  test    edi, edi
0x18004227b  lea     r9, aTrue; "TRUE"
0x180042282  mov     edx, 149h
0x180042287  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004228e  cmovz   r9, rax
0x180042292  call    WPP_SF_s
0x180042297  mov     rcx, cs:WPP_GLOBAL_Control
0x18004229e  cmp     rcx, r14
0x1800422a1  jz      short loc_1800422C6
0x1800422a3  test    [rcx+1Ch], ebp
0x1800422a6  jz      short loc_1800422C6
0x1800422a8  cmp     byte ptr [rcx+19h], 6
0x1800422ac  jb      short loc_1800422C6
0x1800422ae  mov     rcx, [rcx+10h]
0x1800422b2  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x1800422b9  mov     edx, 14Ah
0x1800422be  mov     r9d, ebx
0x1800422c1  call    WPP_SF_d
0x1800422c6  mov     rbx, [rsp+48h+arg_18]
0x1800422cb  mov     eax, edi
0x1800422cd  add     rsp, 30h
0x1800422d1  pop     r14
0x1800422d3  pop     rdi
0x1800422d4  pop     rbp
0x1800422d5  retn
```
