# PostEvent(_PROCESS_ENTRY *,ulong,_IMAGEHLP_CBA_EVENTW *)

- ea: `0x1801ac064`
- end: `0x1801ac217`
- name: `?PostEvent@@YAHPEAU_PROCESS_ENTRY@@KPEAU_IMAGEHLP_CBA_EVENTW@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(struct _PROCESS_ENTRY *, unsigned int, struct _IMAGEHLP_CBA_EVENTW *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1801acfd8`
- `0x1801ad080`

## callees

- `0x18000f998`
- `0x180023bdc`
- `0x180168f90`
- `0x1801abb28`
- `0x1801ac064`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801ac178`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801ac178`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801ac199`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801ac1c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801ac199`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1801ac1c5`

## pseudocode

```c
__int64 __fastcall PostEvent(struct _PROCESS_ENTRY *a1, int a2, struct _IMAGEHLP_CBA_EVENTW *a3)
{
  PCWSTR desc; // r9
  int v7; // ebx
  WCHAR v8; // ax
  unsigned __int64 i; // rcx
  bool v10; // zf
  __int64 v11; // r8
  unsigned int v13; // edx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR OutputString[4104]; // [rsp+40h] [rbp-C0h] BYREF
  char Buffer[4112]; // [rsp+2050h] [rbp+1F50h] BYREF

  desc = a3->desc;
  NumberOfBytesWritten = 0;
  if ( !*desc )
    return 1;
  OutputString[0] = 0;
  v7 = 0;
  v8 = *desc;
  for ( i = 0; *desc; v8 = *desc )
  {
    if ( i >= 0x1001 )
      break;
    if ( v8 == 10 )
    {
      if ( desc[1] != 13 )
      {
        if ( i >= 0x1000 )
        {
          v8 = 10;
        }
        else
        {
          OutputString[i++] = 13;
          v8 = *desc;
        }
      }
    }
    else if ( v8 == 8 )
    {
      break;
    }
    ++desc;
    OutputString[i++] = v8;
  }
  v10 = hFile == 0;
  OutputString[i] = 0;
  if ( !v10 && OutputString[0] )
  {
    wcs2ansi(OutputString, Buffer, 0x1002u);
    v11 = -1;
    do
      ++v11;
    while ( Buffer[v11] );
    WriteFile(hFile, Buffer, v11, &NumberOfBytesWritten, 0);
  }
  if ( dword_1802B09A8 && OutputString[0] )
  {
    v7 = 1;
    OutputDebugStringW(OutputString);
  }
  if ( !a3->severity && dword_1802AF9CC >= 0 )
    return 1;
  if ( !(unsigned int)IsCallback(a1) )
  {
    if ( !v7 )
      OutputDebugStringW(OutputString);
    return 1;
  }
  v13 = 0x40000000;
  if ( a2 != 0x20000000 )
    v13 = 16;
  return DoCallback(a1, v13, a3);
}

```

## disassembly

```asm
0x1801ac064  mov     [rsp-8+arg_8], rbx
0x1801ac069  push    rbp
0x1801ac06a  push    rsi
0x1801ac06b  push    rdi
0x1801ac06c  push    r14
0x1801ac06e  push    r15
0x1801ac070  lea     rbp, [rsp-2F70h]
0x1801ac078  mov     eax, 3070h
0x1801ac07d  call    _alloca_probe
0x1801ac082  sub     rsp, rax
0x1801ac085  mov     rax, cs:__security_cookie
0x1801ac08c  xor     rax, rsp
0x1801ac08f  mov     [rbp+2F90h+var_30], rax
0x1801ac096  mov     r9, [r8+8]
0x1801ac09a  xor     r15d, r15d
0x1801ac09d  mov     [rsp+3090h+NumberOfBytesWritten], r15d
0x1801ac0a2  mov     rdi, r8
0x1801ac0a5  mov     r14d, edx
0x1801ac0a8  mov     rsi, rcx
0x1801ac0ab  cmp     [r9], r15w
0x1801ac0af  jz      loc_1801AC1CB
0x1801ac0b5  mov     [rsp+3090h+OutputString], r15w
0x1801ac0bb  mov     ebx, r15d
0x1801ac0be  movzx   eax, word ptr [r9]
0x1801ac0c2  mov     ecx, r15d
0x1801ac0c5  test    ax, ax
0x1801ac0c8  jz      short loc_1801AC11E
0x1801ac0ca  lea     edx, [r15+0Ah]
0x1801ac0ce  lea     r8d, [r15+0Dh]
0x1801ac0d2  cmp     rcx, 1001h
0x1801ac0d9  jnb     short loc_1801AC11E
0x1801ac0db  cmp     ax, dx
0x1801ac0de  jnz     short loc_1801AC103
0x1801ac0e0  cmp     [r9+2], r8w
0x1801ac0e5  jz      short loc_1801AC109
0x1801ac0e7  cmp     rcx, 1000h
0x1801ac0ee  jnb     short loc_1801AC0FF
0x1801ac0f0  mov     [rsp+rcx*2+3090h+OutputString], r8w
0x1801ac0f6  inc     rcx
0x1801ac0f9  movzx   eax, word ptr [r9]
0x1801ac0fd  jmp     short loc_1801AC109
0x1801ac0ff  mov     eax, edx
0x1801ac101  jmp     short loc_1801AC109
0x1801ac103  cmp     ax, 8
0x1801ac107  jz      short loc_1801AC11E
0x1801ac109  add     r9, 2
0x1801ac10d  mov     [rsp+rcx*2+3090h+OutputString], ax
0x1801ac112  inc     rcx
0x1801ac115  movzx   eax, word ptr [r9]
0x1801ac119  test    ax, ax
0x1801ac11c  jnz     short loc_1801AC0D2
0x1801ac11e  cmp     cs:hFile, r15
0x1801ac125  mov     [rsp+rcx*2+3090h+OutputString], r15w
0x1801ac12b  jz      short loc_1801AC17E
0x1801ac12d  cmp     [rsp+3090h+OutputString], r15w
0x1801ac133  jz      short loc_1801AC17E
0x1801ac135  mov     r8d, 1002h; unsigned int
0x1801ac13b  lea     rdx, [rbp+2F90h+Buffer]; char *
0x1801ac142  lea     rcx, [rsp+3090h+OutputString]; lpWideCharStr
0x1801ac147  call    ?wcs2ansi@@YAHPEBGPEADK@Z; wcs2ansi(ushort const *,char *,ulong)
0x1801ac14c  lea     rax, [rbp+2F90h+Buffer]
0x1801ac153  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801ac157  inc     r8; nNumberOfBytesToWrite
0x1801ac15a  cmp     [rax+r8], r15b
0x1801ac15e  jnz     short loc_1801AC157
0x1801ac160  mov     rcx, cs:hFile; hFile
0x1801ac167  lea     r9, [rsp+3090h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1801ac16c  lea     rdx, [rbp+2F90h+Buffer]; lpBuffer
0x1801ac173  mov     [rsp+3090h+lpOverlapped], r15; lpOverlapped
0x1801ac178  call    cs:__imp_WriteFile
0x1801ac17e  cmp     cs:dword_1802B09A8, r15d
0x1801ac185  jz      short loc_1801AC19F
0x1801ac187  cmp     [rsp+3090h+OutputString], r15w
0x1801ac18d  jz      short loc_1801AC19F
0x1801ac18f  lea     rcx, [rsp+3090h+OutputString]; lpOutputString
0x1801ac194  mov     ebx, 1
0x1801ac199  call    cs:__imp_OutputDebugStringW
0x1801ac19f  cmp     [rdi], r15d
0x1801ac1a2  ja      short loc_1801AC1B0
0x1801ac1a4  test    cs:dword_1802AF9CC, 80000000h
0x1801ac1ae  jz      short loc_1801AC1CB
0x1801ac1b0  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x1801ac1b3  call    ?IsCallback@@YAHPEAU_PROCESS_ENTRY@@@Z; IsCallback(_PROCESS_ENTRY *)
0x1801ac1b8  test    eax, eax
0x1801ac1ba  jnz     short loc_1801AC1F6
0x1801ac1bc  test    ebx, ebx
0x1801ac1be  jnz     short loc_1801AC1CB
0x1801ac1c0  lea     rcx, [rsp+3090h+OutputString]; lpOutputString
0x1801ac1c5  call    cs:__imp_OutputDebugStringW
0x1801ac1cb  mov     eax, 1
0x1801ac1d0  mov     rcx, [rbp+2F90h+var_30]
0x1801ac1d7  xor     rcx, rsp; StackCookie
0x1801ac1da  call    __security_check_cookie
0x1801ac1df  mov     rbx, [rsp+3090h+arg_8]
0x1801ac1e7  add     rsp, 3070h
0x1801ac1ee  pop     r15
0x1801ac1f0  pop     r14
0x1801ac1f2  pop     rdi
0x1801ac1f3  pop     rsi
0x1801ac1f4  pop     rbp
0x1801ac1f5  retn
0x1801ac1f6  cmp     r14d, 20000000h
0x1801ac1fd  mov     edx, 40000000h
0x1801ac202  mov     eax, 10h
0x1801ac207  mov     r8, rdi; void *
0x1801ac20a  cmovnz  edx, eax; unsigned int
0x1801ac20d  mov     rcx, rsi; struct _PROCESS_ENTRY *
0x1801ac210  call    ?DoCallback@@YAHPEAU_PROCESS_ENTRY@@KPEAX@Z; DoCallback(_PROCESS_ENTRY *,ulong,void *)
0x1801ac215  jmp     short loc_1801AC1D0
```
