# MakeRandomTempDirectory(char const *,char *,ulong)

- ea: `0x14000a6b8`
- end: `0x14000a790`
- name: `?MakeRandomTempDirectory@@YAJPEBDPEADK@Z`
- size: `216`
- prototype: `__int64 __fastcall(LPCSTR lpTemplateDirectory, char *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000747c`

## callees

- `0x140009738`
- `0x14000a6b8`
- `0x14000ba00`
- `0x14000bc68`

## import_xrefs

- `KERNEL32!CreateDirectoryExA` at `0x14000a745`
- `KERNEL32!CreateDirectoryExA` at `0x14000a745`
- `KERNEL32!GetLastError` at `0x14000a755`
- `KERNEL32!GetLastError` at `0x14000a755`
- `ole32!CoTaskMemFree` at `0x14000a72c`
- `ole32!CoTaskMemFree` at `0x14000a72c`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a778`
- `OLEAUT32!__imp_SysFreeString` at `0x14000a778`

## pseudocode

```c
__int64 __fastcall MakeRandomTempDirectory(LPCSTR lpTemplateDirectory, char *a2)
{
  signed int v4; // edi
  unsigned int v5; // ecx
  void *v6; // rbx
  signed int LastError; // eax
  LPVOID pv; // [rsp+30h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp+20h] BYREF

  bstrString = 0;
  v4 = -2147467259;
  if ( (int)CreateUuidString(&bstrString) >= 0 )
  {
    pv = 0;
    if ( WSZtoSZ(v5, bstrString, (char **)&pv) >= 0 )
    {
      v6 = pv;
      v4 = StringCchPrintfA(a2, 0x104u, "%s%s", lpTemplateDirectory, (const char *)pv);
      CoTaskMemFree(v6);
      if ( v4 >= 0 && !CreateDirectoryExA(lpTemplateDirectory, a2, 0) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    SysFreeString(bstrString);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000a6b8  mov     rax, rsp
0x14000a6bb  push    rbx
0x14000a6bc  push    rbp
0x14000a6bd  push    rsi
0x14000a6be  push    rdi
0x14000a6bf  sub     rsp, 48h
0x14000a6c3  mov     rbp, rcx
0x14000a6c6  mov     qword ptr [rax+20h], 0
0x14000a6ce  lea     rcx, [rax+20h]; unsigned __int16 **
0x14000a6d2  mov     rsi, rdx
0x14000a6d5  mov     edi, 80004005h
0x14000a6da  call    ?CreateUuidString@@YAJPEAPEAG@Z; CreateUuidString(ushort * *)
0x14000a6df  test    eax, eax
0x14000a6e1  js      loc_14000A784
0x14000a6e7  mov     rdx, [rsp+68h+bstrString]; unsigned __int16 *
0x14000a6ef  lea     r8, [rsp+68h+pv]; char **
0x14000a6f4  mov     [rsp+68h+pv], 0
0x14000a6fd  call    ?WSZtoSZ@@YAJIPEBGPEAPEAD@Z; WSZtoSZ(uint,ushort const *,char * *)
0x14000a702  test    eax, eax
0x14000a704  js      short loc_14000A770
0x14000a706  mov     rbx, [rsp+68h+pv]
0x14000a70b  lea     r8, aSS_0; "%s%s"
0x14000a712  mov     r9, rbp
0x14000a715  mov     [rsp+68h+var_48], rbx
0x14000a71a  mov     edx, 104h; unsigned __int64
0x14000a71f  mov     rcx, rsi; char *
0x14000a722  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x14000a727  mov     rcx, rbx; pv
0x14000a72a  mov     edi, eax
0x14000a72c  call    cs:__imp_CoTaskMemFree
0x14000a733  nop     dword ptr [rax+rax+00h]
0x14000a738  test    edi, edi
0x14000a73a  js      short loc_14000A770
0x14000a73c  xor     r8d, r8d; lpSecurityAttributes
0x14000a73f  mov     rdx, rsi; lpNewDirectory
0x14000a742  mov     rcx, rbp; lpTemplateDirectory
0x14000a745  call    cs:__imp_CreateDirectoryExA
0x14000a74c  nop     dword ptr [rax+rax+00h]
0x14000a751  test    eax, eax
0x14000a753  jnz     short loc_14000A770
0x14000a755  call    cs:__imp_GetLastError
0x14000a75c  nop     dword ptr [rax+rax+00h]
0x14000a761  mov     edi, eax
0x14000a763  test    eax, eax
0x14000a765  jle     short loc_14000A770
0x14000a767  movzx   edi, ax
0x14000a76a  or      edi, 80070000h
0x14000a770  mov     rcx, [rsp+68h+bstrString]; bstrString
0x14000a778  call    cs:__imp_SysFreeString
0x14000a77f  nop     dword ptr [rax+rax+00h]
0x14000a784  mov     eax, edi
0x14000a786  add     rsp, 48h
0x14000a78a  pop     rdi
0x14000a78b  pop     rsi
0x14000a78c  pop     rbp
0x14000a78d  pop     rbx
0x14000a78e  retn
```
