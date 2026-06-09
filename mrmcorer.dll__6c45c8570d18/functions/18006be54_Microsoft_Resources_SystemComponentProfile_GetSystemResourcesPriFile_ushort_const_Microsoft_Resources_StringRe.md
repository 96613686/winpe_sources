# Microsoft::Resources::SystemComponentProfile::GetSystemResourcesPriFile(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x18006be54`
- end: `0x18006bf5c`
- name: `?GetSystemResourcesPriFile@SystemComponentProfile@Resources@Microsoft@@SAJPEBGPEAVStringResult@23@@Z`
- size: `264`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006bc80`
- `0x18006bcd0`
- `0x18006bdb0`

## callees

- `0x180028510`
- `0x18002c8d0`
- `0x18002eb8c`
- `0x18006be54`
- `0x1800862f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006bf3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006be88`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18006be88`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::SystemComponentProfile::GetSystemResourcesPriFile(
        const unsigned __int16 *a1,
        struct Microsoft::Resources::StringResult *a2)
{
  UINT SystemWindowsDirectoryW; // eax
  signed int v5; // ebx
  __int64 v7; // rdx
  signed int LastError; // eax
  int v9; // [rsp+20h] [rbp-448h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-438h] BYREF
  unsigned __int16 v11[264]; // [rsp+240h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+468h] [rbp+0h]

  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW <= 0x104 )
      goto LABEL_3;
    v5 = -2147024774;
LABEL_7:
    v7 = 2642;
    goto LABEL_8;
  }
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_7;
LABEL_3:
  v5 = StringCchPrintfW(v11, 0x104u, L"%s\\SystemResources\\%s\\%s.pri", Buffer, a1, a1);
  if ( v5 < 0 )
  {
    v7 = 2650;
  }
  else
  {
    v5 = DefStringResult_SetCopy(*(_QWORD *)a2, v11);
    if ( v5 >= 0 )
      return 0;
    v7 = 2652;
  }
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
    (const char *)(unsigned int)v5,
    v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006be54  mov     [rsp+arg_10], rbx
0x18006be59  mov     [rsp+arg_18], rsi
0x18006be5e  push    rdi
0x18006be5f  sub     rsp, 460h
0x18006be66  mov     rax, cs:__security_cookie
0x18006be6d  xor     rax, rsp
0x18006be70  mov     [rsp+468h+var_18], rax
0x18006be78  mov     rsi, rdx
0x18006be7b  mov     rdi, rcx
0x18006be7e  mov     edx, 104h; uSize
0x18006be83  lea     rcx, [rsp+468h+Buffer]; lpBuffer
0x18006be88  call    cs:__imp_GetSystemWindowsDirectoryW
0x18006be8e  test    eax, eax
0x18006be90  jz      loc_18006BF3E
0x18006be96  cmp     eax, 104h
0x18006be9b  ja      short loc_18006BF08
0x18006be9d  mov     [rsp+468h+var_440], rdi
0x18006bea2  lea     r9, [rsp+468h+Buffer]
0x18006bea7  lea     r8, aSSystemresourc_0; "%s\\SystemResources\\%s\\%s.pri"
0x18006beae  mov     [rsp+468h+var_448], rdi
0x18006beb3  mov     edx, 104h; unsigned __int64
0x18006beb8  lea     rcx, [rsp+468h+var_228]; unsigned __int16 *
0x18006bec0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006bec5  mov     ebx, eax
0x18006bec7  test    eax, eax
0x18006bec9  js      short loc_18006BF2D
0x18006becb  mov     rcx, [rsi]
0x18006bece  lea     rdx, [rsp+468h+var_228]
0x18006bed6  call    DefStringResult_SetCopy
0x18006bedb  mov     ebx, eax
0x18006bedd  test    eax, eax
0x18006bedf  js      short loc_18006BF55
0x18006bee1  xor     eax, eax
0x18006bee3  mov     rcx, [rsp+468h+var_18]
0x18006beeb  xor     rcx, rsp; StackCookie
0x18006beee  call    __security_check_cookie
0x18006bef3  lea     r11, [rsp+468h+var_8]
0x18006befb  mov     rbx, [r11+20h]
0x18006beff  mov     rsi, [r11+28h]
0x18006bf03  mov     rsp, r11
0x18006bf06  pop     rdi
0x18006bf07  retn
0x18006bf08  mov     ebx, 8007007Ah
0x18006bf0d  mov     edx, 0A52h; void *
0x18006bf12  mov     rcx, [rsp+468h]; this
0x18006bf1a  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18006bf21  mov     r9d, ebx; char *
0x18006bf24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf29  mov     eax, ebx
0x18006bf2b  jmp     short loc_18006BEE3
0x18006bf2d  mov     edx, 0A5Ah
0x18006bf32  jmp     short loc_18006BF12
0x18006bf34  test    ebx, ebx
0x18006bf36  jns     loc_18006BE9D
0x18006bf3c  jmp     short loc_18006BF0D
0x18006bf3e  call    cs:__imp_GetLastError
0x18006bf44  mov     ebx, eax
0x18006bf46  test    eax, eax
0x18006bf48  jle     short loc_18006BF34
0x18006bf4a  movzx   ebx, ax
0x18006bf4d  or      ebx, 80070000h
0x18006bf53  jmp     short loc_18006BF34
0x18006bf55  mov     edx, 0A5Ch
0x18006bf5a  jmp     short loc_18006BF12
```
