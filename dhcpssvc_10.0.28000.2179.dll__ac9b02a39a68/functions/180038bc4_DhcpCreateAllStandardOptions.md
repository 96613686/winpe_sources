# DhcpCreateAllStandardOptions

- ea: `0x180038bc4`
- end: `0x180038d07`
- name: `DhcpCreateAllStandardOptions`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180045b6c`

## callees

- `0x18000282c`
- `0x180038bc4`
- `0x18003926c`
- `0x18003e044`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180038be8`
- `KERNEL32!LoadLibraryW` at `0x180038be8`
- `KERNEL32!FreeLibrary` at `0x180038cd9`
- `KERNEL32!FreeLibrary` at `0x180038cd9`
- `KERNEL32!LocalFree` at `0x180038c7e`
- `KERNEL32!LocalFree` at `0x180038c8d`
- `KERNEL32!LocalFree` at `0x180038c7e`
- `KERNEL32!LocalFree` at `0x180038c8d`

## string_xrefs

- `0x180038be1`: `dhcpssvc.dll`

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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_208b60ca2c083a2a88fa1ff76a8b9d92_Traceguids, 65);
  v2 = 0;
  v3 = (DWORD *)&unk_1800F9988;
  do
  {
    String = (void *)DhcpGetString(LibraryW, *(v3 - 1));
    v5 = (void *)DhcpGetString(LibraryW, *v3);
    StandardOption = DhcpCreateStandardOption(*(v3 - 2), String, v5, v3[1], v3[2]);
    LocalFree(String);
    LocalFree(v5);
    if ( StandardOption
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_208b60ca2c083a2a88fa1ff76a8b9d92_Traceguids, v2);
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
0x180038bc4  mov     rax, rsp
0x180038bc7  mov     [rax+8], rbx
0x180038bcb  mov     [rax+10h], rbp
0x180038bcf  mov     [rax+18h], rsi
0x180038bd3  mov     [rax+20h], rdi
0x180038bd7  push    r12
0x180038bd9  push    r14
0x180038bdb  push    r15
0x180038bdd  sub     rsp, 30h
0x180038be1  lea     rcx, LibFileName; "dhcpssvc.dll"
0x180038be8  call    cs:__imp_LoadLibraryW
0x180038bef  nop     dword ptr [rax+rax+00h]
0x180038bf4  mov     r15, rax
0x180038bf7  test    rax, rax
0x180038bfa  jnz     short loc_180038C06
0x180038bfc  mov     eax, 65Bh
0x180038c01  jmp     loc_180038CE7
0x180038c06  mov     rcx, cs:WPP_GLOBAL_Control
0x180038c0d  lea     r12, WPP_GLOBAL_Control
0x180038c14  cmp     rcx, r12
0x180038c17  jz      short loc_180038C38
0x180038c19  test    byte ptr [rcx+1Ch], 40h
0x180038c1d  jz      short loc_180038C38
0x180038c1f  mov     rcx, [rcx+10h]
0x180038c23  lea     r8, WPP_208b60ca2c083a2a88fa1ff76a8b9d92_Traceguids
0x180038c2a  mov     edx, 1Dh
0x180038c2f  lea     r9d, [rdx+24h]
0x180038c33  call    WPP_SF_D
0x180038c38  xor     ebp, ebp
0x180038c3a  lea     r14, unk_1800F9988
0x180038c41  mov     edx, [r14-4]; dwMessageId
0x180038c45  mov     rcx, r15; lpSource
0x180038c48  call    DhcpGetString
0x180038c4d  mov     edx, [r14]; dwMessageId
0x180038c50  mov     rcx, r15; lpSource
0x180038c53  mov     rsi, rax
0x180038c56  call    DhcpGetString
0x180038c5b  mov     ecx, [r14+8]
0x180038c5f  mov     r8, rax
0x180038c62  mov     r9d, [r14+4]
0x180038c66  mov     rdx, rsi
0x180038c69  mov     [rsp+48h+var_28], ecx
0x180038c6d  mov     rdi, rax
0x180038c70  mov     ecx, [r14-8]
0x180038c74  call    DhcpCreateStandardOption
0x180038c79  mov     rcx, rsi; hMem
0x180038c7c  mov     ebx, eax
0x180038c7e  call    cs:__imp_LocalFree
0x180038c85  nop     dword ptr [rax+rax+00h]
0x180038c8a  mov     rcx, rdi; hMem
0x180038c8d  call    cs:__imp_LocalFree
0x180038c94  nop     dword ptr [rax+rax+00h]
0x180038c99  test    ebx, ebx
0x180038c9b  jz      short loc_180038CC7
0x180038c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ca4  cmp     rcx, r12
0x180038ca7  jz      short loc_180038CC7
0x180038ca9  test    byte ptr [rcx+1Ch], 40h
0x180038cad  jz      short loc_180038CC7
0x180038caf  mov     rcx, [rcx+10h]
0x180038cb3  lea     r8, WPP_208b60ca2c083a2a88fa1ff76a8b9d92_Traceguids
0x180038cba  mov     edx, 1Eh
0x180038cbf  mov     r9d, ebp
0x180038cc2  call    WPP_SF_D
0x180038cc7  inc     ebp
0x180038cc9  add     r14, 14h
0x180038ccd  cmp     ebp, 41h ; 'A'
0x180038cd0  jb      loc_180038C41
0x180038cd6  mov     rcx, r15; hLibModule
0x180038cd9  call    cs:__imp_FreeLibrary
0x180038ce0  nop     dword ptr [rax+rax+00h]
0x180038ce5  xor     eax, eax
0x180038ce7  mov     rbx, [rsp+48h+arg_0]
0x180038cec  mov     rbp, [rsp+48h+arg_8]
0x180038cf1  mov     rsi, [rsp+48h+arg_10]
0x180038cf6  mov     rdi, [rsp+48h+arg_18]
0x180038cfb  add     rsp, 30h
0x180038cff  pop     r15
0x180038d01  pop     r14
0x180038d03  pop     r12
0x180038d05  retn
```
