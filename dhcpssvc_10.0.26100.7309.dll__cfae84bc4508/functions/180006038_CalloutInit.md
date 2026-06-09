# CalloutInit

- ea: `0x180006038`
- end: `0x180006247`
- name: `CalloutInit`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180025bf4`

## callees

- `0x18000323c`
- `0x180005934`
- `0x180006038`
- `0x180006378`
- `0x180006448`
- `0x18001e828`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800060bf`
- `ADVAPI32!RegCloseKey` at `0x1800060f4`
- `ADVAPI32!RegCloseKey` at `0x1800060bf`
- `ADVAPI32!RegCloseKey` at `0x1800060f4`
- `ADVAPI32!RegOpenKeyExW` at `0x180006086`
- `ADVAPI32!RegOpenKeyExW` at `0x180006086`
- `KERNEL32!FreeLibrary` at `0x1800061bd`
- `KERNEL32!FreeLibrary` at `0x1800061bd`
- `KERNEL32!LocalFree` at `0x18000622c`
- `KERNEL32!LocalFree` at `0x18000622c`

## string_xrefs

- `0x180006078`: `System\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800060e2`: `CalloutDlls`

## pseudocode

```c
__int64 CalloutInit()
{
  int Value; // ebx
  _WORD *v1; // rcx
  __int64 v2; // rax
  int v3; // eax
  int Table; // eax
  __int64 v5; // rax
  char *v6; // rcx
  __int64 v7; // rax
  __int64 v9; // [rsp+30h] [rbp-10h] BYREF
  _WORD *hMem; // [rsp+78h] [rbp+38h]
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  HMODULE hLibModule; // [rsp+88h] [rbp+48h] BYREF

  hKey = 0;
  v9 = 0;
  if ( dword_1800FAE50 )
    return 0;
  dword_1800FAE54 = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\DHCPServer\\Parameters",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  if ( !(unsigned int)DhcpRegGetValue(hKey, L"CalloutEnabled") )
  {
    RegCloseKey(hKey);
    return 0;
  }
  hMem = 0;
  Value = DhcpRegGetValue(hKey, L"CalloutDlls");
  RegCloseKey(hKey);
  if ( Value )
    return 0;
  v1 = 0;
  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(2 * v2) );
  if ( !v2 )
    goto LABEL_27;
  while ( 1 )
  {
    hLibModule = 0;
    v3 = LoadDll(v1, &hLibModule, &v9);
    if ( !v3 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)&WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids,
        (_DWORD)hMem,
        v3);
LABEL_18:
    v5 = -1;
    do
      ++v5;
    while ( hMem[v5] );
    v6 = (char *)&hMem[v5];
    v7 = -1;
    v1 = v6 + 2;
    hMem = v1;
    do
      ++v7;
    while ( v1[v7] );
    if ( !v7 )
      goto LABEL_27;
  }
  Table = GetTable(hLibModule, hMem, v9);
  if ( Table )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)&WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids,
        (_DWORD)hMem,
        Table);
    FreeLibrary(hLibModule);
    goto LABEL_18;
  }
  ++dword_1800FAE50;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids);
LABEL_27:
  LocalFree(0);
  return 0;
}

```

## disassembly

```asm
0x180006038  push    rbp
0x18000603a  push    rbx
0x18000603b  push    rdi
0x18000603c  push    r12
0x18000603e  push    r14
0x180006040  mov     rbp, rsp
0x180006043  sub     rsp, 40h
0x180006047  xor     edi, edi
0x180006049  cmp     cs:dword_1800FAE50, edi
0x18000604f  mov     [rbp+hKey], rdi
0x180006053  mov     [rbp+var_10], rdi
0x180006057  mov     [rbp+arg_0], edi
0x18000605a  jnz     loc_180006238
0x180006060  lea     rax, [rbp+hKey]
0x180006064  mov     cs:dword_1800FAE54, edi
0x18000606a  mov     r9d, 20019h; samDesired
0x180006070  mov     [rsp+40h+phkResult], rax; phkResult
0x180006075  xor     r8d, r8d; ulOptions
0x180006078  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\DH"...
0x18000607f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006086  call    cs:__imp_RegOpenKeyExW
0x18000608d  nop     dword ptr [rax+rax+00h]
0x180006092  test    eax, eax
0x180006094  jnz     loc_180006238
0x18000609a  mov     rcx, [rbp+hKey]; hKey
0x18000609e  lea     r9, [rbp+arg_0]
0x1800060a2  lea     r8d, [rdi+4]
0x1800060a6  lea     rdx, aCalloutenabled; "CalloutEnabled"
0x1800060ad  call    DhcpRegGetValue
0x1800060b2  test    eax, eax
0x1800060b4  jnz     short loc_1800060D0
0x1800060b6  cmp     [rbp+arg_0], edi
0x1800060b9  jnz     short loc_1800060D0
0x1800060bb  mov     rcx, [rbp+hKey]; hKey
0x1800060bf  call    cs:__imp_RegCloseKey
0x1800060c6  nop     dword ptr [rax+rax+00h]
0x1800060cb  jmp     loc_180006238
0x1800060d0  mov     rcx, [rbp+hKey]; hKey
0x1800060d4  lea     r9, [rbp+hMem]
0x1800060d8  mov     r8d, 7
0x1800060de  mov     [rbp+hMem], rdi
0x1800060e2  lea     rdx, aCalloutdlls; "CalloutDlls"
0x1800060e9  call    DhcpRegGetValue
0x1800060ee  mov     rcx, [rbp+hKey]; hKey
0x1800060f2  mov     ebx, eax
0x1800060f4  call    cs:__imp_RegCloseKey
0x1800060fb  nop     dword ptr [rax+rax+00h]
0x180006100  test    ebx, ebx
0x180006102  jnz     loc_180006238
0x180006108  mov     rcx, [rbp+hMem]
0x18000610c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180006110  mov     rbx, rcx
0x180006113  mov     rax, r12
0x180006116  inc     rax
0x180006119  cmp     [rcx+rax*2], di
0x18000611d  jnz     short loc_180006116
0x18000611f  test    rax, rax
0x180006122  jz      loc_180006229
0x180006128  lea     r14, WPP_GLOBAL_Control
0x18000612f  lea     r8, [rbp+var_10]
0x180006133  mov     [rbp+hLibModule], rdi
0x180006137  lea     rdx, [rbp+hLibModule]
0x18000613b  call    LoadDll
0x180006140  test    eax, eax
0x180006142  jz      short loc_180006175
0x180006144  mov     rcx, cs:WPP_GLOBAL_Control
0x18000614b  cmp     rcx, r14
0x18000614e  jz      short loc_1800061C9
0x180006150  test    byte ptr [rcx+1Ch], 10h
0x180006154  jz      short loc_1800061C9
0x180006156  mov     r9, [rbp+hMem]
0x18000615a  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x180006161  mov     rcx, [rcx+10h]
0x180006165  mov     edx, 0Ch
0x18000616a  mov     dword ptr [rsp+40h+phkResult], eax
0x18000616e  call    WPP_SF_SD
0x180006173  jmp     short loc_1800061C9
0x180006175  mov     r8, [rbp+var_10]
0x180006179  mov     rdx, [rbp+hMem]
0x18000617d  mov     rcx, [rbp+hLibModule]
0x180006181  call    GetTable
0x180006186  test    eax, eax
0x180006188  jz      short loc_1800061FC
0x18000618a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006191  cmp     rcx, r14
0x180006194  jz      short loc_1800061B9
0x180006196  test    byte ptr [rcx+1Ch], 10h
0x18000619a  jz      short loc_1800061B9
0x18000619c  mov     r9, [rbp+hMem]
0x1800061a0  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x1800061a7  mov     rcx, [rcx+10h]
0x1800061ab  mov     edx, 0Dh
0x1800061b0  mov     dword ptr [rsp+40h+phkResult], eax
0x1800061b4  call    WPP_SF_SD
0x1800061b9  mov     rcx, [rbp+hLibModule]; hLibModule
0x1800061bd  call    cs:__imp_FreeLibrary
0x1800061c4  nop     dword ptr [rax+rax+00h]
0x1800061c9  mov     rcx, [rbp+hMem]
0x1800061cd  mov     rax, r12
0x1800061d0  inc     rax
0x1800061d3  cmp     [rcx+rax*2], di
0x1800061d7  jnz     short loc_1800061D0
0x1800061d9  lea     rcx, [rcx+rax*2]
0x1800061dd  mov     rax, r12
0x1800061e0  add     rcx, 2
0x1800061e4  mov     [rbp+hMem], rcx
0x1800061e8  inc     rax
0x1800061eb  cmp     [rcx+rax*2], di
0x1800061ef  jnz     short loc_1800061E8
0x1800061f1  test    rax, rax
0x1800061f4  jnz     loc_18000612F
0x1800061fa  jmp     short loc_180006229
0x1800061fc  inc     cs:dword_1800FAE50
0x180006202  mov     rcx, cs:WPP_GLOBAL_Control
0x180006209  cmp     rcx, r14
0x18000620c  jz      short loc_180006229
0x18000620e  test    byte ptr [rcx+1Ch], 10h
0x180006212  jz      short loc_180006229
0x180006214  mov     rcx, [rcx+10h]
0x180006218  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x18000621f  mov     edx, 0Eh
0x180006224  call    WPP_SF_
0x180006229  mov     rcx, rbx; hMem
0x18000622c  call    cs:__imp_LocalFree
0x180006233  nop     dword ptr [rax+rax+00h]
0x180006238  xor     eax, eax
0x18000623a  add     rsp, 40h
0x18000623e  pop     r14
0x180006240  pop     r12
0x180006242  pop     rdi
0x180006243  pop     rbx
0x180006244  pop     rbp
0x180006245  retn
```
