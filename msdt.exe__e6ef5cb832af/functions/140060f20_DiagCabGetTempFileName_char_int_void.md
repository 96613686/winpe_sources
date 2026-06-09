# DiagCabGetTempFileName(char *,int,void *)

- ea: `0x140060f20`
- end: `0x1400610e8`
- name: `?DiagCabGetTempFileName@@YAHPEADHPEAX@Z`
- size: `456`
- prototype: `_BOOL8 __fastcall(char *pszTempName, int cbTempName, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140060f20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140060ff7`
- `KERNEL32!GetLastError` at `0x140061007`
- `KERNEL32!GetLastError` at `0x140061060`
- `KERNEL32!GetLastError` at `0x140061074`
- `KERNEL32!GetLastError` at `0x140060ff7`
- `KERNEL32!GetLastError` at `0x140061007`
- `KERNEL32!GetLastError` at `0x140061060`
- `KERNEL32!GetLastError` at `0x140061074`
- `KERNEL32!HeapAlloc` at `0x140060f4b`
- `KERNEL32!HeapAlloc` at `0x140060f7d`
- `KERNEL32!HeapAlloc` at `0x140060f4b`
- `KERNEL32!HeapAlloc` at `0x140060f7d`
- `KERNEL32!HeapFree` at `0x1400610a3`
- `KERNEL32!HeapFree` at `0x1400610c8`
- `KERNEL32!HeapFree` at `0x1400610a3`
- `KERNEL32!HeapFree` at `0x1400610c8`
- `KERNEL32!GetProcessHeap` at `0x140060f32`
- `KERNEL32!GetProcessHeap` at `0x140060f69`
- `KERNEL32!GetProcessHeap` at `0x14006108f`
- `KERNEL32!GetProcessHeap` at `0x1400610b4`
- `KERNEL32!GetProcessHeap` at `0x140060f32`
- `KERNEL32!GetProcessHeap` at `0x140060f69`
- `KERNEL32!GetProcessHeap` at `0x14006108f`
- `KERNEL32!GetProcessHeap` at `0x1400610b4`
- `KERNEL32!WideCharToMultiByte` at `0x140061050`
- `KERNEL32!WideCharToMultiByte` at `0x140061050`
- `KERNEL32!GetTempFileNameW` at `0x140060fe3`
- `KERNEL32!GetTempFileNameW` at `0x140060fe3`
- `KERNEL32!GetTempPath2W` at `0x140060fa5`
- `KERNEL32!GetTempPath2W` at `0x140060fa5`
- `msvcrt!rand` at `0x140060fc7`
- `msvcrt!rand` at `0x140060fc7`

## pseudocode

```c
_BOOL8 __fastcall DiagCabGetTempFileName(char *pszTempName, int cbTempName, void *pv)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rbp
  signed int v7; // ebx
  HANDLE v8; // rax
  WCHAR *v9; // rsi
  unsigned int TempPath2W; // eax
  UINT v11; // eax
  signed int LastError; // eax
  signed int v13; // eax
  HANDLE v14; // rax
  HANDLE v15; // rax

  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x208u);
  if ( !v6 )
  {
    v7 = -2147024882;
    return v7 >= 0;
  }
  v8 = GetProcessHeap();
  v9 = (WCHAR *)HeapAlloc(v8, 0, 0x208u);
  if ( !v9 )
  {
    v7 = -2147024882;
    goto LABEL_19;
  }
  TempPath2W = GetTempPath2W(260, v6);
  if ( !TempPath2W )
    goto LABEL_17;
  if ( TempPath2W >= 0x104 )
  {
    v7 = -2147024774;
    goto LABEL_19;
  }
  v11 = rand();
  if ( GetTempFileNameW(v6, L"PLA_", v11, v9) || !GetLastError() )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
      goto LABEL_19;
  }
  if ( !WideCharToMultiByte(0xFDE9u, 0, v9, -1, pszTempName, cbTempName, 0, 0) )
  {
    if ( !GetLastError() )
    {
      v7 = 0;
      goto LABEL_19;
    }
LABEL_17:
    v13 = GetLastError();
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
  }
LABEL_19:
  v14 = GetProcessHeap();
  HeapFree(v14, 0, v6);
  if ( v9 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v9);
  }
  return v7 >= 0;
}

```

## disassembly

```asm
0x140060f20  push    rbx
0x140060f22  push    rbp
0x140060f23  push    rsi
0x140060f24  push    r14
0x140060f26  push    r15
0x140060f28  sub     rsp, 40h
0x140060f2c  mov     r14d, edx
0x140060f2f  mov     r15, rcx
0x140060f32  call    cs:__imp_GetProcessHeap
0x140060f39  nop     dword ptr [rax+rax+00h]
0x140060f3e  mov     ebx, 208h
0x140060f43  xor     edx, edx; dwFlags
0x140060f45  mov     rcx, rax; hHeap
0x140060f48  mov     r8d, ebx; dwBytes
0x140060f4b  call    cs:__imp_HeapAlloc
0x140060f52  nop     dword ptr [rax+rax+00h]
0x140060f57  mov     rbp, rax
0x140060f5a  test    rax, rax
0x140060f5d  jnz     short loc_140060F69
0x140060f5f  mov     ebx, 8007000Eh
0x140060f64  jmp     loc_1400610D4
0x140060f69  call    cs:__imp_GetProcessHeap
0x140060f70  nop     dword ptr [rax+rax+00h]
0x140060f75  mov     r8, rbx; dwBytes
0x140060f78  xor     edx, edx; dwFlags
0x140060f7a  mov     rcx, rax; hHeap
0x140060f7d  call    cs:__imp_HeapAlloc
0x140060f84  nop     dword ptr [rax+rax+00h]
0x140060f89  mov     rsi, rax
0x140060f8c  test    rax, rax
0x140060f8f  jnz     short loc_140060F9B
0x140060f91  mov     ebx, 8007000Eh
0x140060f96  jmp     loc_14006108F
0x140060f9b  mov     ebx, 104h
0x140060fa0  mov     rdx, rbp
0x140060fa3  mov     ecx, ebx
0x140060fa5  call    cs:__imp_GetTempPath2W
0x140060fac  nop     dword ptr [rax+rax+00h]
0x140060fb1  test    eax, eax
0x140060fb3  jz      loc_140061074
0x140060fb9  cmp     eax, ebx
0x140060fbb  jb      short loc_140060FC7
0x140060fbd  mov     ebx, 8007007Ah
0x140060fc2  jmp     loc_14006108F
0x140060fc7  call    cs:__imp_rand
0x140060fce  nop     dword ptr [rax+rax+00h]
0x140060fd3  mov     r9, rsi; lpTempFileName
0x140060fd6  lea     rdx, aPla; "PLA_"
0x140060fdd  mov     r8d, eax; uUnique
0x140060fe0  mov     rcx, rbp; lpPathName
0x140060fe3  call    cs:__imp_GetTempFileNameW
0x140060fea  nop     dword ptr [rax+rax+00h]
0x140060fef  test    eax, eax
0x140060ff1  jz      short loc_140060FF7
0x140060ff3  xor     ebx, ebx
0x140060ff5  jmp     short loc_140061026
0x140060ff7  call    cs:__imp_GetLastError
0x140060ffe  nop     dword ptr [rax+rax+00h]
0x140061003  test    eax, eax
0x140061005  jz      short loc_140060FF3
0x140061007  call    cs:__imp_GetLastError
0x14006100e  nop     dword ptr [rax+rax+00h]
0x140061013  mov     ebx, eax
0x140061015  test    eax, eax
0x140061017  jle     short loc_140061022
0x140061019  movzx   ebx, ax
0x14006101c  or      ebx, 80070000h
0x140061022  test    ebx, ebx
0x140061024  js      short loc_14006108F
0x140061026  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14006102f  or      r9d, 0FFFFFFFFh; cchWideChar
0x140061033  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x14006103c  mov     r8, rsi; lpWideCharStr
0x14006103f  mov     [rsp+68h+cbMultiByte], r14d; cbMultiByte
0x140061044  xor     edx, edx; dwFlags
0x140061046  mov     ecx, 0FDE9h; CodePage
0x14006104b  mov     [rsp+68h+lpMultiByteStr], r15; lpMultiByteStr
0x140061050  call    cs:__imp_WideCharToMultiByte
0x140061057  nop     dword ptr [rax+rax+00h]
0x14006105c  test    eax, eax
0x14006105e  jnz     short loc_14006108F
0x140061060  call    cs:__imp_GetLastError
0x140061067  nop     dword ptr [rax+rax+00h]
0x14006106c  test    eax, eax
0x14006106e  jnz     short loc_140061074
0x140061070  xor     ebx, ebx
0x140061072  jmp     short loc_14006108F
0x140061074  call    cs:__imp_GetLastError
0x14006107b  nop     dword ptr [rax+rax+00h]
0x140061080  mov     ebx, eax
0x140061082  test    eax, eax
0x140061084  jle     short loc_14006108F
0x140061086  movzx   ebx, ax
0x140061089  or      ebx, 80070000h
0x14006108f  call    cs:__imp_GetProcessHeap
0x140061096  nop     dword ptr [rax+rax+00h]
0x14006109b  mov     r8, rbp; lpMem
0x14006109e  xor     edx, edx; dwFlags
0x1400610a0  mov     rcx, rax; hHeap
0x1400610a3  call    cs:__imp_HeapFree
0x1400610aa  nop     dword ptr [rax+rax+00h]
0x1400610af  test    rsi, rsi
0x1400610b2  jz      short loc_1400610D4
0x1400610b4  call    cs:__imp_GetProcessHeap
0x1400610bb  nop     dword ptr [rax+rax+00h]
0x1400610c0  mov     r8, rsi; lpMem
0x1400610c3  xor     edx, edx; dwFlags
0x1400610c5  mov     rcx, rax; hHeap
0x1400610c8  call    cs:__imp_HeapFree
0x1400610cf  nop     dword ptr [rax+rax+00h]
0x1400610d4  not     ebx
0x1400610d6  shr     ebx, 1Fh
0x1400610d9  mov     eax, ebx
0x1400610db  add     rsp, 40h
0x1400610df  pop     r15
0x1400610e1  pop     r14
0x1400610e3  pop     rsi
0x1400610e4  pop     rbp
0x1400610e5  pop     rbx
0x1400610e6  retn
```
