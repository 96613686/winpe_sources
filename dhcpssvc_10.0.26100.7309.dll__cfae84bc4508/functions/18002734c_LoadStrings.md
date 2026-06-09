# LoadStrings

- ea: `0x18002734c`
- end: `0x180027668`
- name: `LoadStrings`
- size: `796`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000f300`
- `0x18000f3d0`
- `0x180014600`
- `0x1800146b0`
- `0x180025bf4`

## callees

- `0x180002854`
- `0x180025b4c`
- `0x18002734c`
- `0x1800288c0`
- `0x1800cc99a`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x18002736c`
- `KERNEL32!LoadLibraryW` at `0x18002736c`
- `KERNEL32!FreeLibrary` at `0x180027625`
- `KERNEL32!FreeLibrary` at `0x180027625`
- `KERNEL32!FormatMessageW` at `0x1800273dc`
- `KERNEL32!FormatMessageW` at `0x1800274b4`
- `KERNEL32!FormatMessageW` at `0x180027593`
- `KERNEL32!FormatMessageW` at `0x1800273dc`
- `KERNEL32!FormatMessageW` at `0x1800274b4`
- `KERNEL32!FormatMessageW` at `0x180027593`
- `KERNEL32!GetLastError` at `0x18002742a`
- `KERNEL32!GetLastError` at `0x180027509`
- `KERNEL32!GetLastError` at `0x1800275ea`
- `KERNEL32!GetLastError` at `0x180027633`
- `KERNEL32!GetLastError` at `0x18002742a`
- `KERNEL32!GetLastError` at `0x180027509`
- `KERNEL32!GetLastError` at `0x1800275ea`
- `KERNEL32!GetLastError` at `0x180027633`

## string_xrefs

- `0x180027365`: `dhcpssvc.dll`

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
0x18002734c  mov     rax, rsp
0x18002734f  mov     [rax+8], rbx
0x180027353  mov     [rax+10h], rsi
0x180027357  mov     [rax+18h], rdi
0x18002735b  mov     [rax+20h], r12
0x18002735f  push    r15
0x180027361  sub     rsp, 40h
0x180027365  lea     rcx, LibFileName; "dhcpssvc.dll"
0x18002736c  call    cs:__imp_LoadLibraryW
0x180027373  nop     dword ptr [rax+rax+00h]
0x180027378  mov     rsi, rax
0x18002737b  test    rax, rax
0x18002737e  jz      loc_180027633
0x180027384  lea     r12, g_ppszStrings
0x18002738b  xor     edx, edx; Val
0x18002738d  mov     rcx, r12; void *
0x180027390  mov     r8d, 628h; Size
0x180027396  call    memset_0
0x18002739b  mov     ebx, 42Fh
0x1800273a0  lea     r15, WPP_GLOBAL_Control
0x1800273a7  mov     edi, 4B7h
0x1800273ac  and     [rsp+48h+var_18], 0
0x1800273b2  mov     r9d, 400h; dwLanguageId
0x1800273b8  mov     eax, ebx
0x1800273ba  mov     r8d, ebx; dwMessageId
0x1800273bd  add     rax, 0FFFFFFFFFFFFFBD1h
0x1800273c3  mov     [rsp+48h+nSize], 1; nSize
0x1800273cb  mov     rdx, rsi; lpSource
0x1800273ce  lea     rcx, [r12+rax*8]
0x1800273d2  mov     [rsp+48h+lpBuffer], rcx; lpBuffer
0x1800273d7  mov     ecx, 900h; dwFlags
0x1800273dc  call    cs:__imp_FormatMessageW
0x1800273e3  nop     dword ptr [rax+rax+00h]
0x1800273e8  test    eax, eax
0x1800273ea  jnz     short loc_1800273F0
0x1800273ec  cmp     ebx, edi
0x1800273ee  jb      short loc_18002742A
0x1800273f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800273f7  cmp     rcx, r15
0x1800273fa  jz      short loc_180027422
0x1800273fc  test    byte ptr [rcx+1Ch], 10h
0x180027400  jz      short loc_180027422
0x180027402  mov     rcx, [rcx+10h]
0x180027406  lea     eax, [rbx-42Fh]
0x18002740c  mov     rax, [r12+rax*8]
0x180027410  mov     edx, 0Ch
0x180027415  mov     r9d, ebx
0x180027418  mov     [rsp+48h+lpBuffer], rax
0x18002741d  call    WPP_SF_DS
0x180027422  inc     ebx
0x180027424  cmp     ebx, edi
0x180027426  jbe     short loc_1800273AC
0x180027428  jmp     short loc_18002746A
0x18002742a  call    cs:__imp_GetLastError
0x180027431  nop     dword ptr [rax+rax+00h]
0x180027436  mov     ebx, eax
0x180027438  mov     rcx, cs:WPP_GLOBAL_Control
0x18002743f  cmp     rcx, r15
0x180027442  jz      short loc_180027462
0x180027444  test    byte ptr [rcx+1Ch], 10h
0x180027448  jz      short loc_180027462
0x18002744a  mov     rcx, [rcx+10h]
0x18002744e  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180027455  mov     edx, 0Bh
0x18002745a  mov     r9d, eax
0x18002745d  call    WPP_SF_D
0x180027462  test    ebx, ebx
0x180027464  jnz     loc_180027622
0x18002746a  mov     ebx, 2AF8h
0x18002746f  lea     r12d, [rbx+1Ch]
0x180027473  and     [rsp+48h+var_18], 0
0x180027479  lea     edi, [rbx-2A6Fh]
0x18002747f  lea     ecx, [rdi-89h]
0x180027485  mov     [rsp+48h+nSize], 1; nSize
0x18002748d  lea     rax, g_ppszStrings
0x180027494  mov     r9d, 400h; dwLanguageId
0x18002749a  lea     rax, [rax+rcx*8]
0x18002749e  mov     r8d, ebx; dwMessageId
0x1800274a1  add     rax, 448h
0x1800274a7  mov     rdx, rsi; lpSource
0x1800274aa  mov     ecx, 900h; dwFlags
0x1800274af  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x1800274b4  call    cs:__imp_FormatMessageW
0x1800274bb  nop     dword ptr [rax+rax+00h]
0x1800274c0  test    eax, eax
0x1800274c2  jnz     short loc_1800274C9
0x1800274c4  cmp     ebx, r12d
0x1800274c7  jb      short loc_180027509
0x1800274c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274d0  cmp     rcx, r15
0x1800274d3  jz      short loc_1800274FC
0x1800274d5  test    byte ptr [rcx+1Ch], 10h
0x1800274d9  jz      short loc_1800274FC
0x1800274db  mov     rcx, [rcx+10h]
0x1800274df  lea     r8, g_ppszStrings
0x1800274e6  mov     rax, [r8+rdi*8]
0x1800274ea  mov     edx, 0Eh
0x1800274ef  mov     r9d, ebx
0x1800274f2  mov     [rsp+48h+lpBuffer], rax
0x1800274f7  call    WPP_SF_DS
0x1800274fc  inc     ebx
0x1800274fe  cmp     ebx, r12d
0x180027501  jbe     loc_180027473
0x180027507  jmp     short loc_180027549
0x180027509  call    cs:__imp_GetLastError
0x180027510  nop     dword ptr [rax+rax+00h]
0x180027515  mov     ebx, eax
0x180027517  mov     rcx, cs:WPP_GLOBAL_Control
0x18002751e  cmp     rcx, r15
0x180027521  jz      short loc_180027541
0x180027523  test    byte ptr [rcx+1Ch], 10h
0x180027527  jz      short loc_180027541
0x180027529  mov     rcx, [rcx+10h]
0x18002752d  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180027534  mov     edx, 0Dh
0x180027539  mov     r9d, eax
0x18002753c  call    WPP_SF_D
0x180027541  test    ebx, ebx
0x180027543  jnz     loc_180027622
0x180027549  mov     edi, 541h
0x18002754e  lea     r12d, [rdi+1Eh]
0x180027552  and     [rsp+48h+var_18], 0
0x180027558  lea     ebx, [rdi-49Bh]
0x18002755e  lea     ecx, [rbx-0A6h]
0x180027564  mov     [rsp+48h+nSize], 1; nSize
0x18002756c  lea     rax, g_ppszStrings
0x180027573  mov     r9d, 400h; dwLanguageId
0x180027579  lea     rax, [rax+rcx*8]
0x18002757d  mov     r8d, edi; dwMessageId
0x180027580  add     rax, 530h
0x180027586  mov     rdx, rsi; lpSource
0x180027589  mov     ecx, 900h; dwFlags
0x18002758e  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180027593  call    cs:__imp_FormatMessageW
0x18002759a  nop     dword ptr [rax+rax+00h]
0x18002759f  test    eax, eax
0x1800275a1  jnz     short loc_1800275A8
0x1800275a3  cmp     edi, r12d
0x1800275a6  jb      short loc_1800275EA
0x1800275a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275af  cmp     rcx, r15
0x1800275b2  jz      short loc_1800275DB
0x1800275b4  test    byte ptr [rcx+1Ch], 10h
0x1800275b8  jz      short loc_1800275DB
0x1800275ba  mov     rcx, [rcx+10h]
0x1800275be  lea     r8, g_ppszStrings
0x1800275c5  mov     rax, [r8+rbx*8]
0x1800275c9  mov     edx, 10h
0x1800275ce  mov     r9d, edi
0x1800275d1  mov     [rsp+48h+lpBuffer], rax
0x1800275d6  call    WPP_SF_DS
0x1800275db  xor     ebx, ebx
0x1800275dd  inc     edi
0x1800275df  cmp     edi, r12d
0x1800275e2  jbe     loc_180027552
0x1800275e8  jmp     short loc_180027622
0x1800275ea  call    cs:__imp_GetLastError
0x1800275f1  nop     dword ptr [rax+rax+00h]
0x1800275f6  mov     ebx, eax
0x1800275f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275ff  cmp     rcx, r15
0x180027602  jz      short loc_180027622
0x180027604  test    byte ptr [rcx+1Ch], 10h
0x180027608  jz      short loc_180027622
0x18002760a  mov     rcx, [rcx+10h]
0x18002760e  lea     r8, WPP_07851756b2233ff4beb410666ed8ea41_Traceguids
0x180027615  mov     edx, 0Fh
0x18002761a  mov     r9d, eax
0x18002761d  call    WPP_SF_D
0x180027622  mov     rcx, rsi; hLibModule
0x180027625  call    cs:__imp_FreeLibrary
0x18002762c  nop     dword ptr [rax+rax+00h]
0x180027631  jmp     short loc_180027641
0x180027633  call    cs:__imp_GetLastError
0x18002763a  nop     dword ptr [rax+rax+00h]
0x18002763f  mov     ebx, eax
0x180027641  test    ebx, ebx
0x180027643  jz      short loc_18002764A
0x180027645  call    FreeStrings
0x18002764a  mov     rsi, [rsp+48h+arg_8]
0x18002764f  mov     eax, ebx
0x180027651  mov     rbx, [rsp+48h+arg_0]
0x180027656  mov     rdi, [rsp+48h+arg_10]
0x18002765b  mov     r12, [rsp+48h+arg_18]
0x180027660  add     rsp, 40h
0x180027664  pop     r15
0x180027666  retn
```
