# DhcpCreateAllStandardOptions

- ea: `0x180039484`
- end: `0x1800395c7`
- name: `DhcpCreateAllStandardOptions`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180046060`

## callees

- `0x180002854`
- `0x180039484`
- `0x180039b14`
- `0x18003e610`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800394a8`
- `KERNEL32!LoadLibraryW` at `0x1800394a8`
- `KERNEL32!FreeLibrary` at `0x180039599`
- `KERNEL32!FreeLibrary` at `0x180039599`
- `KERNEL32!LocalFree` at `0x18003953e`
- `KERNEL32!LocalFree` at `0x18003954d`
- `KERNEL32!LocalFree` at `0x18003953e`
- `KERNEL32!LocalFree` at `0x18003954d`

## string_xrefs

- `0x1800394a1`: `dhcpssvc.dll`

## pseudocode

```c
__int64 DhcpCreateAllStandardOptions()
{
  HMODULE LibraryW; // r15
  unsigned int v2; // ebp
  DWORD *v3; // r14
  void *String; // rsi
  void *v5; // rdi
  int StandardOption; // ebx

  LibraryW = LoadLibraryW(L"dhcpssvc.dll");
  if ( !LibraryW )
    return 1627;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_eee6c4c18a23342c2c59cb8fb72e4310_Traceguids, 65);
  v2 = 0;
  v3 = (DWORD *)&unk_1800F7988;
  do
  {
    String = (void *)DhcpGetString(LibraryW, *(v3 - 1));
    v5 = (void *)DhcpGetString(LibraryW, *v3);
    StandardOption = DhcpCreateStandardOption(*(v3 - 2), (_DWORD)String, (_DWORD)v5, v3[1], v3[2]);
    LocalFree(String);
    LocalFree(v5);
    if ( StandardOption
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_eee6c4c18a23342c2c59cb8fb72e4310_Traceguids, v2);
    }
    ++v2;
    v3 += 5;
  }
  while ( v2 < 0x41 );
  FreeLibrary(LibraryW);
  return 0;
}

```

## disassembly

```asm
0x180039484  mov     rax, rsp
0x180039487  mov     [rax+8], rbx
0x18003948b  mov     [rax+10h], rbp
0x18003948f  mov     [rax+18h], rsi
0x180039493  mov     [rax+20h], rdi
0x180039497  push    r12
0x180039499  push    r14
0x18003949b  push    r15
0x18003949d  sub     rsp, 30h
0x1800394a1  lea     rcx, LibFileName; "dhcpssvc.dll"
0x1800394a8  call    cs:__imp_LoadLibraryW
0x1800394af  nop     dword ptr [rax+rax+00h]
0x1800394b4  mov     r15, rax
0x1800394b7  test    rax, rax
0x1800394ba  jnz     short loc_1800394C6
0x1800394bc  mov     eax, 65Bh
0x1800394c1  jmp     loc_1800395A7
0x1800394c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800394cd  lea     r12, WPP_GLOBAL_Control
0x1800394d4  cmp     rcx, r12
0x1800394d7  jz      short loc_1800394F8
0x1800394d9  test    byte ptr [rcx+1Ch], 40h
0x1800394dd  jz      short loc_1800394F8
0x1800394df  mov     rcx, [rcx+10h]
0x1800394e3  lea     r8, WPP_eee6c4c18a23342c2c59cb8fb72e4310_Traceguids
0x1800394ea  mov     edx, 1Dh
0x1800394ef  lea     r9d, [rdx+24h]
0x1800394f3  call    WPP_SF_D
0x1800394f8  xor     ebp, ebp
0x1800394fa  lea     r14, unk_1800F7988
0x180039501  mov     edx, [r14-4]; dwMessageId
0x180039505  mov     rcx, r15; lpSource
0x180039508  call    DhcpGetString
0x18003950d  mov     edx, [r14]; dwMessageId
0x180039510  mov     rcx, r15; lpSource
0x180039513  mov     rsi, rax
0x180039516  call    DhcpGetString
0x18003951b  mov     ecx, [r14+8]
0x18003951f  mov     r8, rax
0x180039522  mov     r9d, [r14+4]
0x180039526  mov     rdx, rsi
0x180039529  mov     [rsp+48h+var_28], ecx
0x18003952d  mov     rdi, rax
0x180039530  mov     ecx, [r14-8]
0x180039534  call    DhcpCreateStandardOption
0x180039539  mov     rcx, rsi; hMem
0x18003953c  mov     ebx, eax
0x18003953e  call    cs:__imp_LocalFree
0x180039545  nop     dword ptr [rax+rax+00h]
0x18003954a  mov     rcx, rdi; hMem
0x18003954d  call    cs:__imp_LocalFree
0x180039554  nop     dword ptr [rax+rax+00h]
0x180039559  test    ebx, ebx
0x18003955b  jz      short loc_180039587
0x18003955d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039564  cmp     rcx, r12
0x180039567  jz      short loc_180039587
0x180039569  test    byte ptr [rcx+1Ch], 40h
0x18003956d  jz      short loc_180039587
0x18003956f  mov     rcx, [rcx+10h]
0x180039573  lea     r8, WPP_eee6c4c18a23342c2c59cb8fb72e4310_Traceguids
0x18003957a  mov     edx, 1Eh
0x18003957f  mov     r9d, ebp
0x180039582  call    WPP_SF_D
0x180039587  inc     ebp
0x180039589  add     r14, 14h
0x18003958d  cmp     ebp, 41h ; 'A'
0x180039590  jb      loc_180039501
0x180039596  mov     rcx, r15; hLibModule
0x180039599  call    cs:__imp_FreeLibrary
0x1800395a0  nop     dword ptr [rax+rax+00h]
0x1800395a5  xor     eax, eax
0x1800395a7  mov     rbx, [rsp+48h+arg_0]
0x1800395ac  mov     rbp, [rsp+48h+arg_8]
0x1800395b1  mov     rsi, [rsp+48h+arg_10]
0x1800395b6  mov     rdi, [rsp+48h+arg_18]
0x1800395bb  add     rsp, 30h
0x1800395bf  pop     r15
0x1800395c1  pop     r14
0x1800395c3  pop     r12
0x1800395c5  retn
```
