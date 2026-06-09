# NfsNpCallRpc

- ea: `0x180008420`
- end: `0x180008541`
- name: `NfsNpCallRpc`
- size: `289`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180002930`
- `0x1800066c0`
- `0x180007330`

## callees

- `0x180008420`
- `0x18000b134`
- `0x18000bc14`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x1800084e1`
- `KERNEL32!GlobalFree` at `0x1800084e1`
- `KERNEL32!GlobalAlloc` at `0x18000849e`
- `KERNEL32!GlobalAlloc` at `0x18000849e`
- `WSOCK32!__imp_WSAStartup` at `0x18000846f`
- `WSOCK32!__imp_WSAStartup` at `0x18000846f`
- `WSOCK32!__imp_WSACleanup` at `0x1800084f9`
- `WSOCK32!__imp_WSACleanup` at `0x1800084f9`

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
0x180008420  mov     [rsp+arg_10], rbx
0x180008425  push    rbp
0x180008426  push    rsi
0x180008427  push    rdi
0x180008428  push    r14
0x18000842a  push    r15
0x18000842c  sub     rsp, 1E0h
0x180008433  mov     rax, cs:__security_cookie
0x18000843a  xor     rax, rsp
0x18000843d  mov     [rsp+208h+var_38], rax
0x180008445  mov     r14, rdx
0x180008448  mov     r15, rcx
0x18000844b  xor     edx, edx; Val
0x18000844d  lea     rcx, [rsp+208h+WSAData]; void *
0x180008452  mov     r8d, 198h; Size
0x180008458  call    memset_0
0x18000845d  mov     ecx, 101h; wVersionRequested
0x180008462  mov     dword ptr [rsp+208h+dwBytes], 1000h
0x18000846a  lea     rdx, [rsp+208h+WSAData]; lpWSAData
0x18000846f  call    cs:__imp_WSAStartup
0x180008475  test    eax, eax
0x180008477  jz      short loc_180008480
0x180008479  mov     ebx, 4C6h
0x18000847e  jmp     short loc_1800084FF
0x180008480  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008484  xor     ebx, ebx
0x180008486  xor     edi, edi
0x180008488  cmp     edi, 2
0x18000848b  jnb     short loc_1800084F9
0x18000848d  cmp     ecx, 8000000h
0x180008493  jnb     short loc_1800084F9
0x180008495  mov     ebp, ecx
0x180008497  mov     edx, ecx; dwBytes
0x180008499  mov     ecx, 40h ; '@'; uFlags
0x18000849e  call    cs:__imp_GlobalAlloc
0x1800084a4  lea     r8, [rsp+208h+dwBytes]
0x1800084a9  mov     rcx, r15
0x1800084ac  mov     rdx, rax
0x1800084af  mov     rsi, rax
0x1800084b2  call    GetExportList
0x1800084b7  mov     ebx, eax
0x1800084b9  test    eax, eax
0x1800084bb  js      short loc_180008528
0x1800084bd  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x1800084c1  cmp     ebp, ecx
0x1800084c3  jb      short loc_1800084D9
0x1800084c5  mov     r8d, ecx
0x1800084c8  mov     rdx, rsi
0x1800084cb  mov     rcx, r14
0x1800084ce  call    UnpackExportEntry
0x1800084d3  mov     ebx, eax
0x1800084d5  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x1800084d9  test    rsi, rsi
0x1800084dc  jz      short loc_1800084EB
0x1800084de  mov     rcx, rsi; hMem
0x1800084e1  call    cs:__imp_GlobalFree
0x1800084e7  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x1800084eb  test    ebx, ebx
0x1800084ed  js      short loc_1800084F3
0x1800084ef  cmp     ebp, ecx
0x1800084f1  jnb     short loc_1800084F9
0x1800084f3  inc     edi
0x1800084f5  test    ebx, ebx
0x1800084f7  jns     short loc_180008488
0x1800084f9  call    cs:__imp_WSACleanup
0x1800084ff  mov     eax, ebx
0x180008501  mov     rcx, [rsp+208h+var_38]
0x180008509  xor     rcx, rsp; StackCookie
0x18000850c  call    __security_check_cookie
0x180008511  mov     rbx, [rsp+208h+arg_10]
0x180008519  add     rsp, 1E0h
0x180008520  pop     r15
0x180008522  pop     r14
0x180008524  pop     rdi
0x180008525  pop     rsi
0x180008526  pop     rbp
0x180008527  retn
0x180008528  cmp     ebx, 8007006Fh
0x18000852e  jnz     short loc_1800084D5
0x180008530  mov     ecx, dword ptr [rsp+208h+dwBytes]
0x180008534  xor     eax, eax
0x180008536  cmp     ecx, 8000000h
0x18000853c  cmovb   ebx, eax
0x18000853f  jmp     short loc_1800084D9
```
