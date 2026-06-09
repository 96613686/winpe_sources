# CalloutInit

- ea: `0x18000601c`
- end: `0x18000622b`
- name: `CalloutInit`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180025144`

## callees

- `0x180003228`
- `0x180005924`
- `0x18000601c`
- `0x180006360`
- `0x180006430`
- `0x18001dde0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800060a3`
- `ADVAPI32!RegCloseKey` at `0x1800060d8`
- `ADVAPI32!RegCloseKey` at `0x1800060a3`
- `ADVAPI32!RegCloseKey` at `0x1800060d8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000606a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000606a`
- `KERNEL32!FreeLibrary` at `0x1800061a1`
- `KERNEL32!FreeLibrary` at `0x1800061a1`
- `KERNEL32!LocalFree` at `0x180006210`
- `KERNEL32!LocalFree` at `0x180006210`

## string_xrefs

- `0x18000605c`: `System\CurrentControlSet\Services\DHCPServer\Parameters`
- `0x1800060c6`: `CalloutDlls`

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
  if ( dword_1800FCE70 )
    return 0;
  dword_1800FCE74 = 0;
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
  ++dword_1800FCE70;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids);
LABEL_27:
  LocalFree(0);
  return 0;
}

```

## disassembly

```asm
0x18000601c  push    rbp
0x18000601e  push    rbx
0x18000601f  push    rdi
0x180006020  push    r12
0x180006022  push    r14
0x180006024  mov     rbp, rsp
0x180006027  sub     rsp, 40h
0x18000602b  xor     edi, edi
0x18000602d  cmp     cs:dword_1800FCE70, edi
0x180006033  mov     [rbp+hKey], rdi
0x180006037  mov     [rbp+var_10], rdi
0x18000603b  mov     [rbp+arg_0], edi
0x18000603e  jnz     loc_18000621C
0x180006044  lea     rax, [rbp+hKey]
0x180006048  mov     cs:dword_1800FCE74, edi
0x18000604e  mov     r9d, 20019h; samDesired
0x180006054  mov     [rsp+40h+phkResult], rax; phkResult
0x180006059  xor     r8d, r8d; ulOptions
0x18000605c  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\DH"...
0x180006063  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000606a  call    cs:__imp_RegOpenKeyExW
0x180006071  nop     dword ptr [rax+rax+00h]
0x180006076  test    eax, eax
0x180006078  jnz     loc_18000621C
0x18000607e  mov     rcx, [rbp+hKey]; hKey
0x180006082  lea     r9, [rbp+arg_0]
0x180006086  lea     r8d, [rdi+4]
0x18000608a  lea     rdx, aCalloutenabled; "CalloutEnabled"
0x180006091  call    DhcpRegGetValue
0x180006096  test    eax, eax
0x180006098  jnz     short loc_1800060B4
0x18000609a  cmp     [rbp+arg_0], edi
0x18000609d  jnz     short loc_1800060B4
0x18000609f  mov     rcx, [rbp+hKey]; hKey
0x1800060a3  call    cs:__imp_RegCloseKey
0x1800060aa  nop     dword ptr [rax+rax+00h]
0x1800060af  jmp     loc_18000621C
0x1800060b4  mov     rcx, [rbp+hKey]; hKey
0x1800060b8  lea     r9, [rbp+hMem]
0x1800060bc  mov     r8d, 7
0x1800060c2  mov     [rbp+hMem], rdi
0x1800060c6  lea     rdx, aCalloutdlls; "CalloutDlls"
0x1800060cd  call    DhcpRegGetValue
0x1800060d2  mov     rcx, [rbp+hKey]; hKey
0x1800060d6  mov     ebx, eax
0x1800060d8  call    cs:__imp_RegCloseKey
0x1800060df  nop     dword ptr [rax+rax+00h]
0x1800060e4  test    ebx, ebx
0x1800060e6  jnz     loc_18000621C
0x1800060ec  mov     rcx, [rbp+hMem]
0x1800060f0  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800060f4  mov     rbx, rcx
0x1800060f7  mov     rax, r12
0x1800060fa  inc     rax
0x1800060fd  cmp     [rcx+rax*2], di
0x180006101  jnz     short loc_1800060FA
0x180006103  test    rax, rax
0x180006106  jz      loc_18000620D
0x18000610c  lea     r14, WPP_GLOBAL_Control
0x180006113  lea     r8, [rbp+var_10]
0x180006117  mov     [rbp+hLibModule], rdi
0x18000611b  lea     rdx, [rbp+hLibModule]
0x18000611f  call    LoadDll
0x180006124  test    eax, eax
0x180006126  jz      short loc_180006159
0x180006128  mov     rcx, cs:WPP_GLOBAL_Control
0x18000612f  cmp     rcx, r14
0x180006132  jz      short loc_1800061AD
0x180006134  test    byte ptr [rcx+1Ch], 10h
0x180006138  jz      short loc_1800061AD
0x18000613a  mov     r9, [rbp+hMem]
0x18000613e  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x180006145  mov     rcx, [rcx+10h]
0x180006149  mov     edx, 0Ch
0x18000614e  mov     dword ptr [rsp+40h+phkResult], eax
0x180006152  call    WPP_SF_SD
0x180006157  jmp     short loc_1800061AD
0x180006159  mov     r8, [rbp+var_10]
0x18000615d  mov     rdx, [rbp+hMem]
0x180006161  mov     rcx, [rbp+hLibModule]
0x180006165  call    GetTable
0x18000616a  test    eax, eax
0x18000616c  jz      short loc_1800061E0
0x18000616e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006175  cmp     rcx, r14
0x180006178  jz      short loc_18000619D
0x18000617a  test    byte ptr [rcx+1Ch], 10h
0x18000617e  jz      short loc_18000619D
0x180006180  mov     r9, [rbp+hMem]
0x180006184  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x18000618b  mov     rcx, [rcx+10h]
0x18000618f  mov     edx, 0Dh
0x180006194  mov     dword ptr [rsp+40h+phkResult], eax
0x180006198  call    WPP_SF_SD
0x18000619d  mov     rcx, [rbp+hLibModule]; hLibModule
0x1800061a1  call    cs:__imp_FreeLibrary
0x1800061a8  nop     dword ptr [rax+rax+00h]
0x1800061ad  mov     rcx, [rbp+hMem]
0x1800061b1  mov     rax, r12
0x1800061b4  inc     rax
0x1800061b7  cmp     [rcx+rax*2], di
0x1800061bb  jnz     short loc_1800061B4
0x1800061bd  lea     rcx, [rcx+rax*2]
0x1800061c1  mov     rax, r12
0x1800061c4  add     rcx, 2
0x1800061c8  mov     [rbp+hMem], rcx
0x1800061cc  inc     rax
0x1800061cf  cmp     [rcx+rax*2], di
0x1800061d3  jnz     short loc_1800061CC
0x1800061d5  test    rax, rax
0x1800061d8  jnz     loc_180006113
0x1800061de  jmp     short loc_18000620D
0x1800061e0  inc     cs:dword_1800FCE70
0x1800061e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800061ed  cmp     rcx, r14
0x1800061f0  jz      short loc_18000620D
0x1800061f2  test    byte ptr [rcx+1Ch], 10h
0x1800061f6  jz      short loc_18000620D
0x1800061f8  mov     rcx, [rcx+10h]
0x1800061fc  lea     r8, WPP_f17105a4399c3abd2f916c713abfa5d8_Traceguids
0x180006203  mov     edx, 0Eh
0x180006208  call    WPP_SF_
0x18000620d  mov     rcx, rbx; hMem
0x180006210  call    cs:__imp_LocalFree
0x180006217  nop     dword ptr [rax+rax+00h]
0x18000621c  xor     eax, eax
0x18000621e  add     rsp, 40h
0x180006222  pop     r14
0x180006224  pop     r12
0x180006226  pop     rdi
0x180006227  pop     rbx
0x180006228  pop     rbp
0x180006229  retn
```
