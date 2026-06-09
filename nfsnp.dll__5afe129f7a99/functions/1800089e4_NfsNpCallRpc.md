# NfsNpCallRpc

- ea: `0x1800089e4`
- end: `0x180008b21`
- name: `NfsNpCallRpc`
- size: `317`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180002a90`
- `0x180006b50`
- `0x180007860`

## callees

- `0x1800089e4`
- `0x18000b954`
- `0x18000c4d8`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180008ab4`
- `KERNEL32!GlobalFree` at `0x180008ab4`
- `KERNEL32!GlobalAlloc` at `0x180008a6b`
- `KERNEL32!GlobalAlloc` at `0x180008a6b`
- `WSOCK32!__imp_WSAStartup` at `0x180008a33`
- `WSOCK32!__imp_WSAStartup` at `0x180008a33`
- `WSOCK32!__imp_WSACleanup` at `0x180008ad2`
- `WSOCK32!__imp_WSACleanup` at `0x180008ad2`

## pseudocode

```c
__int64 __fastcall NfsNpCallRpc(__int64 a1, __int64 a2)
{
  int ExportList; // ebx
  unsigned int v5; // ecx
  unsigned int v6; // edi
  unsigned int v7; // ebp
  HGLOBAL v8; // rsi
  SIZE_T dwBytes[2]; // [rsp+20h] [rbp-1E8h] BYREF
  struct WSAData WSAData; // [rsp+30h] [rbp-1D8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  LODWORD(dwBytes[0]) = 4096;
  if ( !WSAStartup(0x101u, &WSAData) )
  {
    v5 = dwBytes[0];
    ExportList = 0;
    v6 = 0;
    while ( 1 )
    {
      if ( v6 >= 2 || v5 >= 0x8000000 )
      {
LABEL_15:
        WSACleanup();
        return (unsigned int)ExportList;
      }
      v7 = v5;
      v8 = GlobalAlloc(0x40u, v5);
      ExportList = GetExportList(a1, v8, dwBytes);
      if ( ExportList < 0 )
        break;
      v5 = dwBytes[0];
      if ( v7 >= LODWORD(dwBytes[0]) )
      {
        ExportList = UnpackExportEntry(a2, v8, LODWORD(dwBytes[0]));
LABEL_9:
        v5 = dwBytes[0];
      }
LABEL_10:
      if ( v8 )
      {
        GlobalFree(v8);
        v5 = dwBytes[0];
      }
      if ( ExportList < 0 || v7 < v5 )
      {
        ++v6;
        if ( ExportList >= 0 )
          continue;
      }
      goto LABEL_15;
    }
    if ( ExportList == -2147024785 )
    {
      v5 = dwBytes[0];
      if ( LODWORD(dwBytes[0]) < 0x8000000 )
        ExportList = 0;
      goto LABEL_10;
    }
    goto LABEL_9;
  }
  return 1222;
}

```

## disassembly

```asm
0x1800089e4  mov     [rsp+arg_10], rbx
0x1800089e9  push    rbp
0x1800089ea  push    rsi
0x1800089eb  push    rdi
0x1800089ec  push    r14
0x1800089ee  push    r15
0x1800089f0  sub     rsp, 1E0h
0x1800089f7  mov     rax, cs:__security_cookie
0x1800089fe  xor     rax, rsp
0x180008a01  mov     [rsp+208h+var_38], rax
0x180008a09  mov     r14, rdx
0x180008a0c  mov     r15, rcx
0x180008a0f  xor     edx, edx; Val
0x180008a11  lea     rcx, [rsp+208h+WSAData]; void *
0x180008a16  mov     r8d, 198h; Size
0x180008a1c  call    memset_0
0x180008a21  mov     ecx, 101h; wVersionRequested
0x180008a26  mov     dword ptr [rsp+208h+dwBytes], 1000h
0x180008a2e  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x180008a33  call    cs:__imp_WSAStartup
0x180008a3a  nop     dword ptr [rax+rax+00h]
0x180008a3f  test    eax, eax
0x180008a41  jz      short loc_180008A4D
0x180008a43  mov     ebx, 4C6h
0x180008a48  jmp     loc_180008ADE
0x180008a4d  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008a51  xor     ebx, ebx
0x180008a53  xor     edi, edi
0x180008a55  cmp     edi, 2
0x180008a58  jnb     short loc_180008AD2
0x180008a5a  cmp     ecx, 8000000h
0x180008a60  jnb     short loc_180008AD2
0x180008a62  mov     ebp, ecx
0x180008a64  mov     edx, ecx; dwBytes
0x180008a66  mov     ecx, 40h ; '@'; uFlags
0x180008a6b  call    cs:__imp_GlobalAlloc
0x180008a72  nop     dword ptr [rax+rax+00h]
0x180008a77  lea     r8, [rsp+208h+dwBytes]
0x180008a7c  mov     rcx, r15
0x180008a7f  mov     rdx, rax
0x180008a82  mov     rsi, rax
0x180008a85  call    GetExportList
0x180008a8a  mov     ebx, eax
0x180008a8c  test    eax, eax
0x180008a8e  js      short loc_180008B08
0x180008a90  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008a94  cmp     ebp, ecx
0x180008a96  jb      short loc_180008AAC
0x180008a98  mov     r8d, ecx
0x180008a9b  mov     rdx, rsi
0x180008a9e  mov     rcx, r14
0x180008aa1  call    UnpackExportEntry
0x180008aa6  mov     ebx, eax
0x180008aa8  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008aac  test    rsi, rsi
0x180008aaf  jz      short loc_180008AC4
0x180008ab1  mov     rcx, rsi; hMem
0x180008ab4  call    cs:__imp_GlobalFree
0x180008abb  nop     dword ptr [rax+rax+00h]
0x180008ac0  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008ac4  test    ebx, ebx
0x180008ac6  js      short loc_180008ACC
0x180008ac8  cmp     ebp, ecx
0x180008aca  jnb     short loc_180008AD2
0x180008acc  inc     edi
0x180008ace  test    ebx, ebx
0x180008ad0  jns     short loc_180008A55
0x180008ad2  call    cs:__imp_WSACleanup
0x180008ad9  nop     dword ptr [rax+rax+00h]
0x180008ade  mov     eax, ebx
0x180008ae0  mov     rcx, [rsp+208h+var_38]
0x180008ae8  xor     rcx, rsp; StackCookie
0x180008aeb  call    __security_check_cookie
0x180008af0  mov     rbx, [rsp+208h+arg_10]
0x180008af8  add     rsp, 1E0h
0x180008aff  pop     r15
0x180008b01  pop     r14
0x180008b03  pop     rdi
0x180008b04  pop     rsi
0x180008b05  pop     rbp
0x180008b06  retn
0x180008b08  cmp     ebx, 8007006Fh
0x180008b0e  jnz     short loc_180008AA8
0x180008b10  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008b14  xor     eax, eax
0x180008b16  cmp     ecx, 8000000h
0x180008b1c  cmovb   ebx, eax
0x180008b1f  jmp     short loc_180008AAC
```
