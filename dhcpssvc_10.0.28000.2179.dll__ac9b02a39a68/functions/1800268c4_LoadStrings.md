# LoadStrings

- ea: `0x1800268c4`
- end: `0x180026be9`
- name: `LoadStrings`
- size: `805`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000e9d0`
- `0x18000eaa0`
- `0x180013d60`
- `0x180013e20`
- `0x180025144`

## callees

- `0x18000282c`
- `0x180025098`
- `0x1800268c4`
- `0x180027e48`
- `0x1800cda7a`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x1800268e4`
- `KERNEL32!LoadLibraryW` at `0x1800268e4`
- `KERNEL32!FreeLibrary` at `0x180026ba6`
- `KERNEL32!FreeLibrary` at `0x180026ba6`
- `KERNEL32!GetLastError` at `0x1800269a5`
- `KERNEL32!GetLastError` at `0x180026a87`
- `KERNEL32!GetLastError` at `0x180026b6b`
- `KERNEL32!GetLastError` at `0x180026bb4`
- `KERNEL32!GetLastError` at `0x1800269a5`
- `KERNEL32!GetLastError` at `0x180026a87`
- `KERNEL32!GetLastError` at `0x180026b6b`
- `KERNEL32!GetLastError` at `0x180026bb4`
- `KERNEL32!FormatMessageW` at `0x180026957`
- `KERNEL32!FormatMessageW` at `0x180026a32`
- `KERNEL32!FormatMessageW` at `0x180026b14`
- `KERNEL32!FormatMessageW` at `0x180026957`
- `KERNEL32!FormatMessageW` at `0x180026a32`
- `KERNEL32!FormatMessageW` at `0x180026b14`

## string_xrefs

- `0x1800268dd`: `dhcpssvc.dll`

## pseudocode

```c
__int64 LoadStrings()
{
  HMODULE LibraryW; // rsi
  DWORD v1; // ebx
  int v2; // r8d
  DWORD LastError; // eax
  DWORD v4; // ebx
  DWORD v5; // ebx
  DWORD v6; // eax
  DWORD v7; // edi
  DWORD v8; // eax

  LibraryW = LoadLibraryW(L"dhcpssvc.dll");
  if ( LibraryW )
  {
    memset_0(g_ppszStrings, 0, sizeof(g_ppszStrings));
    v1 = 1071;
    while ( FormatMessageW(0x900u, LibraryW, v1, 0x400u, &g_ppszStrings[4 * v1 - 4284], 1u, 0) || v1 >= 0x4B7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v2, v1, *(_QWORD *)&g_ppszStrings[4 * v1 - 4284]);
      if ( ++v1 > 0x4B7 )
        goto LABEL_14;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, LastError);
    if ( v4 )
      goto LABEL_37;
LABEL_14:
    v5 = 11000;
    while ( FormatMessageW(0x900u, LibraryW, v5, 0x400u, &g_ppszStrings[4 * v5 - 43452], 1u, 0) || v5 >= 0x2B14 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)g_ppszStrings,
          v5,
          *(_QWORD *)&g_ppszStrings[4 * v5 - 43452]);
      if ( ++v5 > 0x2B14 )
        goto LABEL_26;
    }
    v6 = GetLastError();
    v4 = v6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v6);
    if ( v4 )
      goto LABEL_37;
LABEL_26:
    v7 = 1345;
    while ( FormatMessageW(0x900u, LibraryW, v7, 0x400u, &g_ppszStrings[4 * v7 - 4716], 1u, 0) || v7 >= 0x55F )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)g_ppszStrings,
          v7,
          *(_QWORD *)&g_ppszStrings[4 * v7 - 4716]);
      v4 = 0;
      if ( ++v7 > 0x55F )
        goto LABEL_37;
    }
    v8 = GetLastError();
    v4 = v8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_07851756b2233ff4beb410666ed8ea41_Traceguids, v8);
LABEL_37:
    FreeLibrary(LibraryW);
  }
  else
  {
    v4 = GetLastError();
  }
  if ( v4 )
    FreeStrings();
  return v4;
}

```

## disassembly

```asm
0x1800268c4  mov     rax, rsp
0x1800268c7  mov     [rax+8], rbx
0x1800268cb  mov     [rax+10h], rsi
0x1800268cf  mov     [rax+18h], rdi
0x1800268d3  mov     [rax+20h], r12
0x1800268d7  push    r15
0x1800268d9  sub     rsp, 40h
0x1800268dd  lea     rcx, LibFileName; "dhcpssvc.dll"
0x1800268e4  call    cs:__imp_LoadLibraryW
0x1800268eb  nop     dword ptr [rax+rax+00h]
0x1800268f0  mov     rsi, rax
0x1800268f3  test    rax, rax
0x1800268f6  jz      loc_180026BB4
0x1800268fc  lea     r12, g_ppszStrings
0x180026903  xor     edx, edx; Val
0x180026905  mov     rcx, r12; void *
0x180026908  mov     r8d, 628h; Size
0x18002690e  call    memset_0
0x180026913  mov     ebx, 42Fh
0x180026918  lea     r15, WPP_GLOBAL_Control
0x18002691f  mov     edi, 4B7h
0x180026924  mov     [rsp+48h+Arguments], 0; Arguments
0x18002692d  mov     r9d, 400h; dwLanguageId
0x180026933  mov     eax, ebx
0x180026935  mov     r8d, ebx; dwMessageId
0x180026938  add     rax, 0FFFFFFFFFFFFFBD1h
0x18002693e  mov     [rsp+48h+nSize], 1; nSize
0x180026946  mov     rdx, rsi; lpSource
0x180026949  lea     rcx, [r12+rax*8]
0x18002694d  mov     [rsp+48h+lpBuffer], rcx; lpBuffer
0x180026952  mov     ecx, 900h; dwFlags
0x180026957  call    cs:__imp_FormatMessageW
0x18002695e  nop     dword ptr [rax+rax+00h]
0x180026963  test    eax, eax
0x180026965  jnz     short loc_18002696B
0x180026967  cmp     ebx, edi
0x180026969  jb      short loc_1800269A5
0x18002696b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026972  cmp     rcx, r15
0x180026975  jz      short loc_18002699D
0x180026977  test    byte ptr [rcx+1Ch], 10h
0x18002697b  jz      short loc_18002699D
0x18002697d  mov     rcx, [rcx+10h]
0x180026981  lea     eax, [rbx-42Fh]
0x180026987  mov     rax, [r12+rax*8]
0x18002698b  mov     edx, 0Ch
0x180026990  mov     r9d, ebx
0x180026993  mov     [rsp+48h+lpBuffer], rax
0x180026998  call    WPP_SF_DS
0x18002699d  inc     ebx
0x18002699f  cmp     ebx, edi
0x1800269a1  jbe     short loc_180026924
0x1800269a3  jmp     short loc_1800269E5
0x1800269a5  call    cs:__imp_GetLastError
0x1800269ac  nop     dword ptr [rax+rax+00h]
0x1800269b1  mov     ebx, eax
0x1800269b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269ba  cmp     rcx, r15
0x1800269bd  jz      short loc_1800269DD
0x1800269bf  test    byte ptr [rcx+1Ch], 10h
0x1800269c3  jz      short loc_1800269DD
0x1800269c5  mov     rcx, [rcx+10h]
0x1800269c9  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x1800269d0  mov     edx, 0Bh
0x1800269d5  mov     r9d, eax
0x1800269d8  call    WPP_SF_D
0x1800269dd  test    ebx, ebx
0x1800269df  jnz     loc_180026BA3
0x1800269e5  mov     ebx, 2AF8h
0x1800269ea  lea     r12d, [rbx+1Ch]
0x1800269ee  mov     [rsp+48h+Arguments], 0; Arguments
0x1800269f7  lea     edi, [rbx-2A6Fh]
0x1800269fd  lea     ecx, [rdi-89h]
0x180026a03  mov     [rsp+48h+nSize], 1; nSize
0x180026a0b  lea     rax, g_ppszStrings
0x180026a12  mov     r9d, 400h; dwLanguageId
0x180026a18  lea     rax, [rax+rcx*8]
0x180026a1c  mov     r8d, ebx; dwMessageId
0x180026a1f  add     rax, 448h
0x180026a25  mov     rdx, rsi; lpSource
0x180026a28  mov     ecx, 900h; dwFlags
0x180026a2d  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180026a32  call    cs:__imp_FormatMessageW
0x180026a39  nop     dword ptr [rax+rax+00h]
0x180026a3e  test    eax, eax
0x180026a40  jnz     short loc_180026A47
0x180026a42  cmp     ebx, r12d
0x180026a45  jb      short loc_180026A87
0x180026a47  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a4e  cmp     rcx, r15
0x180026a51  jz      short loc_180026A7A
0x180026a53  test    byte ptr [rcx+1Ch], 10h
0x180026a57  jz      short loc_180026A7A
0x180026a59  mov     rcx, [rcx+10h]
0x180026a5d  lea     r8, g_ppszStrings
0x180026a64  mov     rax, [r8+rdi*8]
0x180026a68  mov     edx, 0Eh
0x180026a6d  mov     r9d, ebx
0x180026a70  mov     [rsp+48h+lpBuffer], rax
0x180026a75  call    WPP_SF_DS
0x180026a7a  inc     ebx
0x180026a7c  cmp     ebx, r12d
0x180026a7f  jbe     loc_1800269EE
0x180026a85  jmp     short loc_180026AC7
0x180026a87  call    cs:__imp_GetLastError
0x180026a8e  nop     dword ptr [rax+rax+00h]
0x180026a93  mov     ebx, eax
0x180026a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180026a9c  cmp     rcx, r15
0x180026a9f  jz      short loc_180026ABF
0x180026aa1  test    byte ptr [rcx+1Ch], 10h
0x180026aa5  jz      short loc_180026ABF
0x180026aa7  mov     rcx, [rcx+10h]
0x180026aab  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180026ab2  mov     edx, 0Dh
0x180026ab7  mov     r9d, eax
0x180026aba  call    WPP_SF_D
0x180026abf  test    ebx, ebx
0x180026ac1  jnz     loc_180026BA3
0x180026ac7  mov     edi, 541h
0x180026acc  lea     r12d, [rdi+1Eh]
0x180026ad0  mov     [rsp+48h+Arguments], 0; Arguments
0x180026ad9  lea     ebx, [rdi-49Bh]
0x180026adf  lea     ecx, [rbx-0A6h]
0x180026ae5  mov     [rsp+48h+nSize], 1; nSize
0x180026aed  lea     rax, g_ppszStrings
0x180026af4  mov     r9d, 400h; dwLanguageId
0x180026afa  lea     rax, [rax+rcx*8]
0x180026afe  mov     r8d, edi; dwMessageId
0x180026b01  add     rax, 530h
0x180026b07  mov     rdx, rsi; lpSource
0x180026b0a  mov     ecx, 900h; dwFlags
0x180026b0f  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180026b14  call    cs:__imp_FormatMessageW
0x180026b1b  nop     dword ptr [rax+rax+00h]
0x180026b20  test    eax, eax
0x180026b22  jnz     short loc_180026B29
0x180026b24  cmp     edi, r12d
0x180026b27  jb      short loc_180026B6B
0x180026b29  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b30  cmp     rcx, r15
0x180026b33  jz      short loc_180026B5C
0x180026b35  test    byte ptr [rcx+1Ch], 10h
0x180026b39  jz      short loc_180026B5C
0x180026b3b  mov     rcx, [rcx+10h]
0x180026b3f  lea     r8, g_ppszStrings
0x180026b46  mov     rax, [r8+rbx*8]
0x180026b4a  mov     edx, 10h
0x180026b4f  mov     r9d, edi
0x180026b52  mov     [rsp+48h+lpBuffer], rax
0x180026b57  call    WPP_SF_DS
0x180026b5c  xor     ebx, ebx
0x180026b5e  inc     edi
0x180026b60  cmp     edi, r12d
0x180026b63  jbe     loc_180026AD0
0x180026b69  jmp     short loc_180026BA3
0x180026b6b  call    cs:__imp_GetLastError
0x180026b72  nop     dword ptr [rax+rax+00h]
0x180026b77  mov     ebx, eax
0x180026b79  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b80  cmp     rcx, r15
0x180026b83  jz      short loc_180026BA3
0x180026b85  test    byte ptr [rcx+1Ch], 10h
0x180026b89  jz      short loc_180026BA3
0x180026b8b  mov     rcx, [rcx+10h]
0x180026b8f  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180026b96  mov     edx, 0Fh
0x180026b9b  mov     r9d, eax
0x180026b9e  call    WPP_SF_D
0x180026ba3  mov     rcx, rsi; hLibModule
0x180026ba6  call    cs:__imp_FreeLibrary
0x180026bad  nop     dword ptr [rax+rax+00h]
0x180026bb2  jmp     short loc_180026BC2
0x180026bb4  call    cs:__imp_GetLastError
0x180026bbb  nop     dword ptr [rax+rax+00h]
0x180026bc0  mov     ebx, eax
0x180026bc2  test    ebx, ebx
0x180026bc4  jz      short loc_180026BCB
0x180026bc6  call    FreeStrings
0x180026bcb  mov     rsi, [rsp+48h+arg_8]
0x180026bd0  mov     eax, ebx
0x180026bd2  mov     rbx, [rsp+48h+arg_0]
0x180026bd7  mov     rdi, [rsp+48h+arg_10]
0x180026bdc  mov     r12, [rsp+48h+arg_18]
0x180026be1  add     rsp, 40h
0x180026be5  pop     r15
0x180026be7  retn
```
