# TextFileLogger::ConstructSearchString(ushort *,ushort * *,ushort * *)

- ea: `0x180012a34`
- end: `0x180012b60`
- name: `?ConstructSearchString@TextFileLogger@@AEAA_NPEAGPEAPEAG1@Z`
- size: `300`
- prototype: `bool __fastcall(TextFileLogger *this, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180012b68`

## callees

- `0x180012a34`
- `0x18002e0b2`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180012a57`
- `KERNEL32!GetSystemDirectoryW` at `0x180012a57`
- `IisRTL!PuDbgPrint` at `0x180012b4b`
- `IisRTL!PuDbgPrint` at `0x180012b4b`

## string_xrefs

- `0x180012b3f`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x180012b24`: `Path of windows dir is larger than MAX_PATH\n`
- `0x180012a9b`: `Path + logfile exceeds MAX_PATH\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall TextFileLogger::ConstructSearchString(
        TextFileLogger *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  UINT SystemDirectoryW; // eax
  __int64 v9; // rdx
  unsigned __int16 *v10; // rdi
  __int64 v11; // rax
  const void *v12; // rdx
  unsigned __int16 *v13; // rdi
  __int64 v14; // rbx
  bool result; // al

  SystemDirectoryW = GetSystemDirectoryW(a2, 0x104u);
  if ( SystemDirectoryW - 1 > 0x103 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        809,
        "TextFileLogger::ConstructSearchString",
        "Path of windows dir is larger than MAX_PATH\n");
    return 0;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(*((_QWORD *)this + 2) + 2 * v9) );
  if ( (unsigned int)v9 + SystemDirectoryW + 24 >= 0x104 )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        826,
        "TextFileLogger::ConstructSearchString",
        "Path + logfile exceeds MAX_PATH\n");
    return 0;
  }
  v10 = &a2[SystemDirectoryW];
  if ( v10 != a2 && *(v10 - 1) != 92 )
    *v10++ = asc_1800334D0[0];
  v11 = (unsigned int)v9;
  *(_OWORD *)v10 = xmmword_180041578;
  v12 = (const void *)*((_QWORD *)this + 2);
  v13 = v10 + 8;
  v14 = v11;
  *a3 = v13;
  memcpy_0(v13, v12, 2 * v11);
  *(_OWORD *)&v13[v14] = xmmword_180041558;
  *a4 = &v13[v14 + 1];
  result = 1;
  *(_OWORD *)&v13[v14 + 7] = *(__int128 *)((char *)&xmmword_180041558 + 14);
  v13[v14 + 15] = 0;
  return result;
}

```

## disassembly

```asm
0x180012a34  push    rbx
0x180012a36  push    rbp
0x180012a37  push    rsi
0x180012a38  push    rdi
0x180012a39  push    r14
0x180012a3b  push    r15
0x180012a3d  sub     rsp, 38h
0x180012a41  mov     rbx, rdx
0x180012a44  mov     rsi, rcx
0x180012a47  mov     edi, 104h
0x180012a4c  mov     rcx, rbx; lpBuffer
0x180012a4f  mov     edx, edi; uSize
0x180012a51  mov     r14, r9
0x180012a54  mov     r15, r8
0x180012a57  call    cs:__imp_GetSystemDirectoryW
0x180012a5d  mov     r11d, eax
0x180012a60  lea     r10d, [r11-1]
0x180012a64  cmp     r10d, 103h
0x180012a6b  ja      loc_180012B1B
0x180012a71  mov     rax, [rsi+10h]
0x180012a75  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180012a79  xor     ebp, ebp
0x180012a7b  inc     rdx
0x180012a7e  cmp     [rax+rdx*2], bp
0x180012a82  jnz     short loc_180012A7B
0x180012a84  lea     eax, [r11+18h]
0x180012a88  add     eax, edx
0x180012a8a  cmp     eax, edi
0x180012a8c  jb      short loc_180012AAD
0x180012a8e  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012a95  jz      loc_180012B51
0x180012a9b  lea     rax, aPathLogfileExc; "Path + logfile exceeds MAX_PATH\n"
0x180012aa2  mov     r8d, 33Ah
0x180012aa8  jmp     loc_180012B31
0x180012aad  lea     rdi, [rbx+r11*2]
0x180012ab1  cmp     rdi, rbx
0x180012ab4  jz      short loc_180012ACA
0x180012ab6  cmp     word ptr [rdi-2], 5Ch ; '\'
0x180012abb  jz      short loc_180012ACA
0x180012abd  mov     eax, dword ptr cs:asc_1800334D0; "\\"
0x180012ac3  mov     [rdi], ax
0x180012ac6  add     rdi, 2
0x180012aca  movups  xmm0, cs:xmmword_180041578
0x180012ad1  mov     eax, edx
0x180012ad3  movdqu  xmmword ptr [rdi], xmm0
0x180012ad7  mov     rdx, [rsi+10h]; Src
0x180012adb  add     rdi, 10h
0x180012adf  lea     rbx, [rax+rax]
0x180012ae3  mov     [r15], rdi
0x180012ae6  mov     r8, rbx; Size
0x180012ae9  mov     rcx, rdi; void *
0x180012aec  call    memcpy_0
0x180012af1  movups  xmm0, cs:xmmword_180041558
0x180012af8  lea     rax, [rdi+2]
0x180012afc  add     rax, rbx
0x180012aff  movups  xmmword ptr [rbx+rdi], xmm0
0x180012b03  mov     [r14], rax
0x180012b06  mov     al, 1
0x180012b08  movups  xmm1, cs:xmmword_180041558+0Eh
0x180012b0f  movups  xmmword ptr [rbx+rdi+0Eh], xmm1
0x180012b14  mov     [rbx+rdi+1Eh], bp
0x180012b19  jmp     short loc_180012B53
0x180012b1b  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180012b22  jz      short loc_180012B51
0x180012b24  lea     rax, aPathOfWindowsD; "Path of windows dir is larger than MAX_"...
0x180012b2b  mov     r8d, 329h
0x180012b31  mov     rcx, cs:g_pDebug
0x180012b38  lea     r9, aTextfilelogger_2; "TextFileLogger::ConstructSearchString"
0x180012b3f  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x180012b46  mov     [rsp+68h+var_48], rax
0x180012b4b  call    cs:__imp_PuDbgPrint
0x180012b51  xor     al, al
0x180012b53  add     rsp, 38h
0x180012b57  pop     r15
0x180012b59  pop     r14
0x180012b5b  pop     rdi
0x180012b5c  pop     rsi
0x180012b5d  pop     rbp
0x180012b5e  pop     rbx
0x180012b5f  retn
```
