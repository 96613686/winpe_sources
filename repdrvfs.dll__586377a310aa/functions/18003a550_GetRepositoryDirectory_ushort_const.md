# GetRepositoryDirectory(ushort * const)

- ea: `0x18003a550`
- end: `0x18003a729`
- name: `?GetRepositoryDirectory@@YAJQEAG@Z`
- size: `473`
- prototype: `__int64 __fastcall(LPWSTR lpDst, __int64, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039c74`
- `0x18003c714`
- `0x18003c8a0`
- `0x1800406c4`
- `0x180041610`
- `0x1800422c0`

## callees

- `0x1800012b8`
- `0x180024ca0`
- `0x18003a550`
- `0x180043fa0`
- `0x180044170`
- `0x180044420`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003a5b3`
- `wbemcomn!GetMemLogObject` at `0x18003a651`
- `wbemcomn!GetMemLogObject` at `0x18003a6c0`
- `wbemcomn!GetMemLogObject` at `0x18003a5b3`
- `wbemcomn!GetMemLogObject` at `0x18003a651`
- `wbemcomn!GetMemLogObject` at `0x18003a6c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a5be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a65c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a6cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a5be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a65c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003a6cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a6a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003a69d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18003a69d`

## string_xrefs

- `0x18003a611`: `Repository Directory`

## pseudocode

```c
__int64 __fastcall GetRepositoryDirectory(LPWSTR lpDst, __int64 a2, int a3)
{
  int v4; // eax
  int v5; // r8d
  signed int Value; // ebx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v8; // rcx
  __int64 v9; // rdx
  bool v11; // sf
  CMemoryLog *v12; // rax
  signed int LastError; // eax
  CMemoryLog *v14; // rax
  int v15; // [rsp+30h] [rbp-238h] BYREF
  __int64 v16; // [rsp+38h] [rbp-230h] BYREF
  WCHAR Src[264]; // [rsp+40h] [rbp-228h] BYREF

  v16 = 0;
  v4 = DLRegOpenKeyExW(-2147483646, (unsigned int)L"SOFTWARE\\Microsoft\\WBEM\\CIMOM", a3, 131097, (__int64)&v16);
  Value = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      Value = (unsigned __int16)v4 | 0x80070000;
    if ( Value < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, Value);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)Value;
    }
    v9 = 14;
LABEL_10:
    WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, (unsigned int)Value);
    return (unsigned int)Value;
  }
  v15 = 522;
  Value = DLRegQueryValueExW(v16, (unsigned int)L"Repository Directory", v5, 0, (__int64)Src, (__int64)&v15);
  DLRegCloseKey(v16);
  v11 = Value < 0;
  if ( Value )
  {
    if ( Value > 0 )
    {
      Value = (unsigned __int16)Value | 0x80070000;
      v11 = Value < 0;
    }
    if ( v11 )
    {
      v12 = GetMemLogObject();
      CMemoryLog::Write(v12, Value);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)Value;
    }
    v9 = 15;
    goto LABEL_10;
  }
  if ( !ExpandEnvironmentStringsW(Src, lpDst, 0x105u) )
  {
    LastError = GetLastError();
    Value = LastError;
    if ( LastError > 0 )
      Value = (unsigned __int16)LastError | 0x80070000;
    if ( Value < 0 )
    {
      v14 = GetMemLogObject();
      CMemoryLog::Write(v14, Value);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)Value;
    }
    v9 = 16;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x18003a550  mov     [rsp+arg_8], rbx
0x18003a555  push    rdi
0x18003a556  sub     rsp, 260h
0x18003a55d  mov     rax, cs:__security_cookie
0x18003a564  xor     rax, rsp
0x18003a567  mov     [rsp+268h+var_18], rax
0x18003a56f  mov     rdi, rcx
0x18003a572  mov     [rsp+268h+var_230], 0
0x18003a57b  lea     rax, [rsp+268h+var_230]
0x18003a580  mov     rcx, 0FFFFFFFF80000002h
0x18003a587  mov     r9d, 20019h
0x18003a58d  mov     [rsp+268h+var_248], rax
0x18003a592  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WBEM\\CIMOM"
0x18003a599  call    DLRegOpenKeyExW
0x18003a59e  mov     ebx, eax
0x18003a5a0  test    eax, eax
0x18003a5a2  jz      short loc_18003A602
0x18003a5a4  jle     short loc_18003A5AF
0x18003a5a6  movzx   ebx, ax
0x18003a5a9  or      ebx, 80070000h
0x18003a5af  test    ebx, ebx
0x18003a5b1  jns     short loc_18003A5C4
0x18003a5b3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a5b9  mov     rcx, rax
0x18003a5bc  mov     edx, ebx
0x18003a5be  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a5c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a5cb  lea     rax, WPP_GLOBAL_Control
0x18003a5d2  cmp     rcx, rax
0x18003a5d5  jz      short loc_18003A5FB
0x18003a5d7  test    byte ptr [rcx+1Ch], 1
0x18003a5db  jz      short loc_18003A5FB
0x18003a5dd  cmp     byte ptr [rcx+19h], 2
0x18003a5e1  jb      short loc_18003A5FB
0x18003a5e3  mov     edx, 0Eh
0x18003a5e8  mov     rcx, [rcx+10h]
0x18003a5ec  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003a5f3  mov     r9d, ebx
0x18003a5f6  call    WPP_SF_d
0x18003a5fb  mov     eax, ebx
0x18003a5fd  jmp     loc_18003A708
0x18003a602  mov     rcx, [rsp+268h+var_230]
0x18003a607  lea     rax, [rsp+268h+var_238]
0x18003a60c  mov     [rsp+268h+var_240], rax
0x18003a611  lea     rdx, aRepositoryDire; "Repository Directory"
0x18003a618  lea     rax, [rsp+268h+Src]
0x18003a61d  mov     [rsp+268h+var_238], 20Ah
0x18003a625  xor     r9d, r9d
0x18003a628  mov     [rsp+268h+var_248], rax
0x18003a62d  call    DLRegQueryValueExW
0x18003a632  mov     rcx, [rsp+268h+var_230]
0x18003a637  mov     ebx, eax
0x18003a639  call    DLRegCloseKey
0x18003a63e  test    ebx, ebx
0x18003a640  jz      short loc_18003A68F
0x18003a642  jle     short loc_18003A64F
0x18003a644  movzx   ebx, bx
0x18003a647  or      ebx, 80070000h
0x18003a64d  test    ebx, ebx
0x18003a64f  jns     short loc_18003A662
0x18003a651  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a657  mov     rcx, rax
0x18003a65a  mov     edx, ebx
0x18003a65c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a662  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a669  lea     rax, WPP_GLOBAL_Control
0x18003a670  cmp     rcx, rax
0x18003a673  jz      short loc_18003A5FB
0x18003a675  test    byte ptr [rcx+1Ch], 1
0x18003a679  jz      short loc_18003A5FB
0x18003a67b  cmp     byte ptr [rcx+19h], 2
0x18003a67f  jb      loc_18003A5FB
0x18003a685  mov     edx, 0Fh
0x18003a68a  jmp     loc_18003A5E8
0x18003a68f  mov     r8d, 105h; nSize
0x18003a695  lea     rcx, [rsp+268h+Src]; lpSrc
0x18003a69a  mov     rdx, rdi; lpDst
0x18003a69d  call    cs:__imp_ExpandEnvironmentStringsW
0x18003a6a3  test    eax, eax
0x18003a6a5  jnz     short loc_18003A706
0x18003a6a7  call    cs:__imp_GetLastError
0x18003a6ad  mov     ebx, eax
0x18003a6af  test    eax, eax
0x18003a6b1  jle     short loc_18003A6BC
0x18003a6b3  movzx   ebx, ax
0x18003a6b6  or      ebx, 80070000h
0x18003a6bc  test    ebx, ebx
0x18003a6be  jns     short loc_18003A6D1
0x18003a6c0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003a6c6  mov     rcx, rax
0x18003a6c9  mov     edx, ebx
0x18003a6cb  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003a6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a6d8  lea     rax, WPP_GLOBAL_Control
0x18003a6df  cmp     rcx, rax
0x18003a6e2  jz      loc_18003A5FB
0x18003a6e8  test    byte ptr [rcx+1Ch], 1
0x18003a6ec  jz      loc_18003A5FB
0x18003a6f2  cmp     byte ptr [rcx+19h], 2
0x18003a6f6  jb      loc_18003A5FB
0x18003a6fc  mov     edx, 10h
0x18003a701  jmp     loc_18003A5E8
0x18003a706  xor     eax, eax
0x18003a708  mov     rcx, [rsp+268h+var_18]
0x18003a710  xor     rcx, rsp; StackCookie
0x18003a713  call    __security_check_cookie
0x18003a718  mov     rbx, [rsp+268h+arg_8]
0x18003a720  add     rsp, 260h
0x18003a727  pop     rdi
0x18003a728  retn
```
