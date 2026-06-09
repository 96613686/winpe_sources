# XVPReadAutoProcessRegistry(int,int &)

- ea: `0x180009724`
- end: `0x18000983f`
- name: `?XVPReadAutoProcessRegistry@@YAIHAEAH@Z`
- size: `283`
- prototype: `unsigned int __fastcall(int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a8c`
- `0x180060600`

## callees

- `0x180009724`
- `0x180009940`
- `0x1800bd8dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009834`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009834`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009790`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180009790`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009807`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800097cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180009807`

## string_xrefs

- `0x180009738`: `autoProcessDuringPlayback`
- `0x1800097c1`: `EnableAutoEnhanceDuringPlayback`

## pseudocode

```c
__int64 __fastcall XVPReadAutoProcessRegistry(int a1, int *a2)
{
  unsigned int v4; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  v4 = AccessRegistryInt(
         L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
         L"autoProcessDuringPlayback",
         0);
  *a2 = 0;
  hKey = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\VideoSettings", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"EnableAutoEnhanceDuringPlayback", 0, &Type, (LPBYTE)&Data, &cbData) )
      v4 = Data != 0;
    if ( !a1 && !RegQueryValueExW(hKey, L"DisableOtherEnhancementsOnBattery", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
    {
      v4 = v4 && !IsCurrentlyOnDC();
      *a2 = 1;
    }
    RegCloseKey(hKey);
  }
  return v4;
}

```

## disassembly

```asm
0x180009724  mov     [rsp-18h+arg_0], rbx
0x180009729  push    rbp
0x18000972a  push    rsi
0x18000972b  push    rdi
0x18000972c  mov     rbp, rsp
0x18000972f  sub     rsp, 40h
0x180009733  mov     rdi, rdx
0x180009736  mov     esi, ecx
0x180009738  lea     rdx, aAutoprocessdur; "autoProcessDuringPlayback"
0x18000973f  xor     r8d, r8d; int
0x180009742  lea     rcx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x180009749  call    ?AccessRegistryInt@@YAHPEBG0H@Z; AccessRegistryInt(ushort const *,ushort const *,int)
0x18000974e  mov     ebx, eax
0x180009750  mov     dword ptr [rdi], 0
0x180009756  mov     eax, 4
0x18000975b  mov     [rbp+hKey], 0
0x180009763  mov     [rbp+Type], eax
0x180009766  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000976d  mov     [rbp+cbData], eax
0x180009770  mov     r9d, 1; samDesired
0x180009776  lea     rax, [rbp+hKey]
0x18000977a  mov     [rbp+Data], 0
0x180009781  xor     r8d, r8d; ulOptions
0x180009784  mov     [rsp+40h+phkResult], rax; phkResult
0x180009789  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180009790  call    cs:__imp_RegOpenKeyExW
0x180009796  test    eax, eax
0x180009798  jz      short loc_1800097A9
0x18000979a  mov     eax, ebx
0x18000979c  mov     rbx, [rsp+40h+arg_0]
0x1800097a1  add     rsp, 40h
0x1800097a5  pop     rdi
0x1800097a6  pop     rsi
0x1800097a7  pop     rbp
0x1800097a8  retn
0x1800097a9  mov     rcx, [rbp+hKey]; hKey
0x1800097ad  lea     rax, [rbp+cbData]
0x1800097b1  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800097b6  lea     r9, [rbp+Type]; lpType
0x1800097ba  lea     rax, [rbp+Data]
0x1800097be  xor     r8d, r8d; lpReserved
0x1800097c1  lea     rdx, ValueName; "EnableAutoEnhanceDuringPlayback"
0x1800097c8  mov     [rsp+40h+phkResult], rax; lpData
0x1800097cd  call    cs:__imp_RegQueryValueExW
0x1800097d3  test    eax, eax
0x1800097d5  jnz     short loc_1800097DF
0x1800097d7  xor     ebx, ebx
0x1800097d9  cmp     [rbp+Data], ebx
0x1800097dc  setnz   bl
0x1800097df  test    esi, esi
0x1800097e1  jnz     short loc_180009830
0x1800097e3  mov     rcx, [rbp+hKey]; hKey
0x1800097e7  lea     rax, [rbp+cbData]
0x1800097eb  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800097f0  lea     r9, [rbp+Type]; lpType
0x1800097f4  lea     rax, [rbp+Data]
0x1800097f8  xor     r8d, r8d; lpReserved
0x1800097fb  lea     rdx, aDisableotheren; "DisableOtherEnhancementsOnBattery"
0x180009802  mov     [rsp+40h+phkResult], rax; lpData
0x180009807  call    cs:__imp_RegQueryValueExW
0x18000980d  test    eax, eax
0x18000980f  jnz     short loc_180009830
0x180009811  cmp     [rbp+Data], eax
0x180009814  jz      short loc_180009830
0x180009816  test    ebx, ebx
0x180009818  jz      short loc_180009828
0x18000981a  call    ?IsCurrentlyOnDC@@YA_NXZ; IsCurrentlyOnDC(void)
0x18000981f  test    al, al
0x180009821  jnz     short loc_180009828
0x180009823  lea     ebx, [rsi+1]
0x180009826  jmp     short loc_18000982A
0x180009828  xor     ebx, ebx
0x18000982a  mov     dword ptr [rdi], 1
0x180009830  mov     rcx, [rbp+hKey]; hKey
0x180009834  call    cs:__imp_RegCloseKey
0x18000983a  jmp     loc_18000979A
```
