# GetConnectionSpecificDirectory(HKEY__ *,ushort *,ulong)

- ea: `0x1400585a4`
- end: `0x1400586a7`
- name: `?GetConnectionSpecificDirectory@@YAJPEAUHKEY__@@PEAGK@Z`
- size: `259`
- prototype: `__int64 __fastcall(HKEY hkey, BYTE *pszDest, size_t cchDest)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140057f18`
- `0x140059090`

## callees

- `0x1400576c8`
- `0x1400585a4`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14005866a`
- `ADVAPI32!RegGetValueW` at `0x14005866a`
- `KERNEL32!GetLastError` at `0x1400585eb`
- `KERNEL32!GetLastError` at `0x1400585eb`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1400585e1`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x1400585e1`

## pseudocode

```c
__int64 __fastcall GetConnectionSpecificDirectory(HKEY hkey, BYTE *pszDest, size_t cchDest)
{
  size_t v3; // rdi
  signed int LastError; // eax
  int v7; // ebx
  __int64 v8; // rax
  LSTATUS ValueW; // eax
  DWORD pdwType; // [rsp+70h] [rbp+18h] BYREF
  DWORD pcbData; // [rsp+78h] [rbp+20h] BYREF

  v3 = (unsigned int)cchDest;
  pdwType = 0;
  if ( GetPrinterDriverDirectoryW(0, 0, 1u, pszDest, 2 * cchDest, &pdwType) )
    goto LABEL_5;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_5:
    v7 = StringCchCatW((STRSAFE_LPWSTR)pszDest, v3, L"\\V4Connections\\");
    if ( v7 >= 0 )
    {
      pdwType = 0;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&pszDest[2 * v8] );
      pcbData = 2 * (v3 - v8);
      ValueW = RegGetValueW(hkey, 0, L"ConnectionGUID", 2u, &pdwType, &pszDest[2 * v8], &pcbData);
      if ( ValueW )
      {
        if ( ValueW > 0 )
          return (unsigned __int16)ValueW | 0x80070000;
        else
          return (unsigned int)ValueW;
      }
      else if ( pdwType != 1 )
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400585a4  mov     r11, rsp
0x1400585a7  mov     [r11+8], rbx
0x1400585ab  mov     [r11+10h], rbp
0x1400585af  push    rsi
0x1400585b0  push    rdi
0x1400585b1  push    r14
0x1400585b3  sub     rsp, 40h
0x1400585b7  mov     edi, r8d
0x1400585ba  mov     rbp, rcx
0x1400585bd  lea     rcx, [r11+18h]
0x1400585c1  xor     r14d, r14d
0x1400585c4  mov     [r11-30h], rcx
0x1400585c8  mov     rsi, rdx
0x1400585cb  mov     r9, rdx; pDriverDirectory
0x1400585ce  mov     [r11+18h], r14d
0x1400585d2  lea     eax, [rdi+rdi]
0x1400585d5  xor     edx, edx; pEnvironment
0x1400585d7  xor     ecx, ecx; pName
0x1400585d9  mov     [rsp+58h+cbBuf], eax; cbBuf
0x1400585dd  lea     r8d, [r14+1]; Level
0x1400585e1  call    cs:__imp_GetPrinterDriverDirectoryW
0x1400585e7  test    eax, eax
0x1400585e9  jnz     short loc_140058608
0x1400585eb  call    cs:__imp_GetLastError
0x1400585f1  mov     ebx, eax
0x1400585f3  test    eax, eax
0x1400585f5  jle     short loc_140058600
0x1400585f7  movzx   ebx, ax
0x1400585fa  or      ebx, 80070000h
0x140058600  test    ebx, ebx
0x140058602  js      loc_140058692
0x140058608  mov     rdx, rdi; cchDest
0x14005860b  lea     r8, aV4connections; "\\V4Connections\\"
0x140058612  mov     rcx, rsi; pszDest
0x140058615  call    StringCchCatW
0x14005861a  mov     ebx, eax
0x14005861c  test    eax, eax
0x14005861e  js      short loc_140058692
0x140058620  mov     [rsp+58h+pdwType], r14d
0x140058625  or      rax, 0FFFFFFFFFFFFFFFFh
0x140058629  inc     rax
0x14005862c  cmp     [rsi+rax*2], r14w
0x140058631  jnz     short loc_140058629
0x140058633  sub     edi, eax
0x140058635  lea     rcx, [rsp+58h+arg_18]
0x14005863a  mov     [rsp+58h+pcbData], rcx; pcbData
0x14005863f  lea     rax, [rsi+rax*2]
0x140058643  mov     [rsp+58h+pvData], rax; pvData
0x140058648  lea     r8, aConnectionguid; "ConnectionGUID"
0x14005864f  lea     rax, [rsp+58h+pdwType]
0x140058654  add     edi, edi
0x140058656  mov     r9d, 2; dwFlags
0x14005865c  mov     qword ptr [rsp+58h+cbBuf], rax; pdwType
0x140058661  xor     edx, edx; lpSubKey
0x140058663  mov     [rsp+58h+arg_18], edi
0x140058667  mov     rcx, rbp; hkey
0x14005866a  call    cs:__imp_RegGetValueW
0x140058670  test    eax, eax
0x140058672  jz      short loc_140058685
0x140058674  jg      short loc_14005867A
0x140058676  mov     ebx, eax
0x140058678  jmp     short loc_140058692
0x14005867a  movzx   ebx, ax
0x14005867d  or      ebx, 80070000h
0x140058683  jmp     short loc_140058692
0x140058685  cmp     [rsp+58h+pdwType], 1
0x14005868a  mov     eax, 8000FFFFh
0x14005868f  cmovnz  ebx, eax
0x140058692  mov     rbp, [rsp+58h+arg_8]
0x140058697  mov     eax, ebx
0x140058699  mov     rbx, [rsp+58h+arg_0]
0x14005869e  add     rsp, 40h
0x1400586a2  pop     r14
0x1400586a4  pop     rdi
0x1400586a5  pop     rsi
0x1400586a6  retn
```
