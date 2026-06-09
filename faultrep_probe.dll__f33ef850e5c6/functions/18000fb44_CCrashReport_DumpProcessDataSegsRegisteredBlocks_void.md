# CCrashReport::DumpProcessDataSegsRegisteredBlocks(void *)

- ea: `0x18000fb44`
- end: `0x18000fde5`
- name: `?DumpProcessDataSegsRegisteredBlocks@CCrashReport@@AEAAJPEAX@Z`
- size: `673`
- prototype: `__int64 __fastcall(CCrashReport *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014598`

## callees

- `0x180002890`
- `0x180009f00`
- `0x18000fb44`
- `0x1800169c4`
- `0x18003cc4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb87`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000fb7d`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x18000fb7d`
- `wer!WerpAuxmdMapFile` at `0x18000fd48`
- `wer!WerpAuxmdMapFile` at `0x18000fd48`
- `wer!WerpAuxmdHashVaRanges` at `0x18000fd0e`
- `wer!WerpAuxmdHashVaRanges` at `0x18000fd0e`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x18000fd00`
- `wer!WerpAuxmdFreeCopyBuffer` at `0x18000fd00`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x18000fcf5`
- `wer!WerpAuxmdDumpRegisteredBlocks` at `0x18000fcf5`
- `wer!WerpAuxmdDumpProcessImages` at `0x18000fcbb`
- `wer!WerpAuxmdDumpProcessImages` at `0x18000fcbb`
- `wer!WerpAuxmdInitialize` at `0x18000fc7c`
- `wer!WerpAuxmdInitialize` at `0x18000fc7c`

## pseudocode

```c
__int64 __fastcall CCrashReport::DumpProcessDataSegsRegisteredBlocks(wchar_t *this, void *a2)
{
  unsigned int TempPath2W; // eax
  signed int LastError; // eax
  int TempFile; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v10; // ebp
  int v11; // r8d
  __int64 v12; // [rsp+20h] [rbp-258h]
  WCHAR v13[264]; // [rsp+40h] [rbp-238h] BYREF

  TempPath2W = GetTempPath2W(260, v13);
  if ( !TempPath2W )
  {
    LastError = GetLastError();
    TempFile = LastError;
    if ( LastError > 0 )
      TempFile = (unsigned __int16)LastError | 0x80070000;
    if ( TempFile >= 0 )
      TempFile = -2147467259;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 132;
    goto LABEL_9;
  }
  if ( TempPath2W >= 0x104 )
  {
    v7 = WPP_GLOBAL_Control;
    TempFile = -2147024774;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 133;
LABEL_9:
    WPP_SF_d(v7[2], v8, &WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids, (unsigned int)TempFile);
    return (unsigned int)TempFile;
  }
  TempFile = UtilGetTempFile(0, v13, 0, this + 4804, v12, 0, 0, 0);
  if ( TempFile < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 134;
    goto LABEL_9;
  }
  TempFile = WerpAuxmdInitialize(this + 2572, this + 4804, a2, 0x10000);
  if ( TempFile < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 135;
    goto LABEL_9;
  }
  TempFile = WerpAuxmdDumpProcessImages(this + 2572, 3);
  if ( TempFile < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 136;
    goto LABEL_9;
  }
  v10 = WerpAuxmdDumpRegisteredBlocks(this + 2572);
  WerpAuxmdFreeCopyBuffer(this + 2572);
  TempFile = WerpAuxmdHashVaRanges(this + 2572, 4);
  if ( TempFile < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 137;
    goto LABEL_9;
  }
  TempFile = WerpAuxmdMapFile(this + 2572);
  if ( TempFile < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      return (unsigned int)TempFile;
    v8 = 138;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((_DWORD *)this + 1290) - v10,
      v11,
      (_DWORD)this + 9608,
      *((_DWORD *)this + 1290) - v10,
      v10,
      *((_DWORD *)this + 1290));
  return 0;
}

```

## disassembly

```asm
0x18000fb44  mov     [rsp+arg_10], rbx
0x18000fb49  mov     [rsp+arg_18], rbp
0x18000fb4e  push    rsi
0x18000fb4f  push    rdi
0x18000fb50  push    r14
0x18000fb52  sub     rsp, 260h
0x18000fb59  mov     rax, cs:__security_cookie
0x18000fb60  xor     rax, rsp
0x18000fb63  mov     [rsp+278h+var_28], rax
0x18000fb6b  mov     rbp, rdx
0x18000fb6e  mov     r14, rcx
0x18000fb71  mov     ebx, 104h
0x18000fb76  lea     rdx, [rsp+278h+var_238]
0x18000fb7b  mov     ecx, ebx
0x18000fb7d  call    cs:__imp_GetTempPath2W
0x18000fb83  test    eax, eax
0x18000fb85  jnz     short loc_18000FBDE
0x18000fb87  call    cs:__imp_GetLastError
0x18000fb8d  mov     ebx, eax
0x18000fb8f  test    eax, eax
0x18000fb91  jle     short loc_18000FB9C
0x18000fb93  movzx   ebx, ax
0x18000fb96  or      ebx, 80070000h
0x18000fb9c  test    ebx, ebx
0x18000fb9e  mov     eax, 80004005h
0x18000fba3  cmovns  ebx, eax
0x18000fba6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbad  lea     rax, WPP_GLOBAL_Control
0x18000fbb4  cmp     rcx, rax
0x18000fbb7  jz      short loc_18000FBD7
0x18000fbb9  test    byte ptr [rcx+1Ch], 2
0x18000fbbd  jz      short loc_18000FBD7
0x18000fbbf  mov     edx, 84h
0x18000fbc4  mov     rcx, [rcx+10h]
0x18000fbc8  lea     r8, WPP_81c54fc0bb413c1df4013ae372c383d0_Traceguids
0x18000fbcf  mov     r9d, ebx
0x18000fbd2  call    WPP_SF_d
0x18000fbd7  mov     eax, ebx
0x18000fbd9  jmp     loc_18000FDBD
0x18000fbde  cmp     eax, ebx
0x18000fbe0  jb      short loc_18000FC07
0x18000fbe2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbe9  lea     rax, WPP_GLOBAL_Control
0x18000fbf0  mov     ebx, 8007007Ah
0x18000fbf5  cmp     rcx, rax
0x18000fbf8  jz      short loc_18000FBD7
0x18000fbfa  test    byte ptr [rcx+1Ch], 2
0x18000fbfe  jz      short loc_18000FBD7
0x18000fc00  mov     edx, 85h
0x18000fc05  jmp     short loc_18000FBC4
0x18000fc07  mov     [rsp+278h+var_240], 0
0x18000fc0f  lea     rsi, [r14+2588h]
0x18000fc16  mov     r9, rsi
0x18000fc19  mov     [rsp+278h+var_248], 0
0x18000fc21  xor     r8d, r8d
0x18000fc24  mov     [rsp+278h+var_250], 0
0x18000fc2d  lea     rdx, [rsp+278h+var_238]
0x18000fc32  xor     ecx, ecx
0x18000fc34  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18000fc39  mov     ebx, eax
0x18000fc3b  test    eax, eax
0x18000fc3d  jns     short loc_18000FC66
0x18000fc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc46  lea     rax, WPP_GLOBAL_Control
0x18000fc4d  cmp     rcx, rax
0x18000fc50  jz      short loc_18000FBD7
0x18000fc52  test    byte ptr [rcx+1Ch], 2
0x18000fc56  jz      loc_18000FBD7
0x18000fc5c  mov     edx, 86h
0x18000fc61  jmp     loc_18000FBC4
0x18000fc66  lea     rdi, [r14+1418h]
0x18000fc6d  mov     r9d, 10000h
0x18000fc73  mov     rcx, rdi
0x18000fc76  mov     r8, rbp
0x18000fc79  mov     rdx, rsi
0x18000fc7c  call    cs:__imp_WerpAuxmdInitialize
0x18000fc82  mov     ebx, eax
0x18000fc84  test    eax, eax
0x18000fc86  jns     short loc_18000FCB3
0x18000fc88  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc8f  lea     rax, WPP_GLOBAL_Control
0x18000fc96  cmp     rcx, rax
0x18000fc99  jz      loc_18000FBD7
0x18000fc9f  test    byte ptr [rcx+1Ch], 2
0x18000fca3  jz      loc_18000FBD7
0x18000fca9  mov     edx, 87h
0x18000fcae  jmp     loc_18000FBC4
0x18000fcb3  mov     edx, 3
0x18000fcb8  mov     rcx, rdi
0x18000fcbb  call    cs:__imp_WerpAuxmdDumpProcessImages
0x18000fcc1  mov     ebx, eax
0x18000fcc3  test    eax, eax
0x18000fcc5  jns     short loc_18000FCF2
0x18000fcc7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcce  lea     rax, WPP_GLOBAL_Control
0x18000fcd5  cmp     rcx, rax
0x18000fcd8  jz      loc_18000FBD7
0x18000fcde  test    byte ptr [rcx+1Ch], 2
0x18000fce2  jz      loc_18000FBD7
0x18000fce8  mov     edx, 88h
0x18000fced  jmp     loc_18000FBC4
0x18000fcf2  mov     rcx, rdi
0x18000fcf5  call    cs:__imp_WerpAuxmdDumpRegisteredBlocks
0x18000fcfb  mov     rcx, rdi
0x18000fcfe  mov     ebp, eax
0x18000fd00  call    cs:__imp_WerpAuxmdFreeCopyBuffer
0x18000fd06  mov     edx, 4
0x18000fd0b  mov     rcx, rdi
0x18000fd0e  call    cs:__imp_WerpAuxmdHashVaRanges
0x18000fd14  mov     ebx, eax
0x18000fd16  test    eax, eax
0x18000fd18  jns     short loc_18000FD45
0x18000fd1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd21  lea     rax, WPP_GLOBAL_Control
0x18000fd28  cmp     rcx, rax
0x18000fd2b  jz      loc_18000FBD7
0x18000fd31  test    byte ptr [rcx+1Ch], 2
0x18000fd35  jz      loc_18000FBD7
0x18000fd3b  mov     edx, 89h
0x18000fd40  jmp     loc_18000FBC4
0x18000fd45  mov     rcx, rdi
0x18000fd48  call    cs:__imp_WerpAuxmdMapFile
0x18000fd4e  mov     ebx, eax
0x18000fd50  test    eax, eax
0x18000fd52  jns     short loc_18000FD7F
0x18000fd54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd5b  lea     rax, WPP_GLOBAL_Control
0x18000fd62  cmp     rcx, rax
0x18000fd65  jz      loc_18000FBD7
0x18000fd6b  test    byte ptr [rcx+1Ch], 2
0x18000fd6f  jz      loc_18000FBD7
0x18000fd75  mov     edx, 8Ah
0x18000fd7a  jmp     loc_18000FBC4
0x18000fd7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd86  lea     rax, WPP_GLOBAL_Control
0x18000fd8d  cmp     rcx, rax
0x18000fd90  jz      short loc_18000FDBB
0x18000fd92  test    byte ptr [rcx+1Ch], 8
0x18000fd96  jz      short loc_18000FDBB
0x18000fd98  mov     eax, [r14+1428h]
0x18000fd9f  mov     r9, rsi
0x18000fda2  mov     rcx, [rcx+10h]
0x18000fda6  mov     edx, eax
0x18000fda8  mov     [rsp+278h+var_248], eax
0x18000fdac  sub     edx, ebp
0x18000fdae  mov     dword ptr [rsp+278h+var_250], ebp
0x18000fdb2  mov     dword ptr [rsp+278h+var_258], edx
0x18000fdb6  call    WPP_SF_SDDD
0x18000fdbb  xor     eax, eax
0x18000fdbd  mov     rcx, [rsp+278h+var_28]
0x18000fdc5  xor     rcx, rsp; StackCookie
0x18000fdc8  call    __security_check_cookie
0x18000fdcd  lea     r11, [rsp+278h+var_18]
0x18000fdd5  mov     rbx, [r11+30h]
0x18000fdd9  mov     rbp, [r11+38h]
0x18000fddd  mov     rsp, r11
0x18000fde0  pop     r14
0x18000fde2  pop     rdi
0x18000fde3  pop     rsi
0x18000fde4  retn
```
