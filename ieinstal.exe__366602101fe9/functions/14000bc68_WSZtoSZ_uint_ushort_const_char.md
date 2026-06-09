# WSZtoSZ(uint,ushort const *,char * *)

- ea: `0x14000bc68`
- end: `0x14000bd65`
- name: `?WSZtoSZ@@YAJIPEBGPEAPEAD@Z`
- size: `253`
- prototype: `int(unsigned int, const unsigned __int16 *, char **)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140004a18`
- `0x1400088a8`
- `0x140008b44`
- `0x14000a6b8`

## callees

- `0x14000bc68`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000bd2a`
- `KERNEL32!GetLastError` at `0x14000bd2a`
- `KERNEL32!WideCharToMultiByte` at `0x14000bcac`
- `KERNEL32!WideCharToMultiByte` at `0x14000bd07`
- `KERNEL32!WideCharToMultiByte` at `0x14000bcac`
- `KERNEL32!WideCharToMultiByte` at `0x14000bd07`
- `ole32!CoTaskMemAlloc` at `0x14000bcc6`
- `ole32!CoTaskMemAlloc` at `0x14000bcc6`
- `ole32!CoTaskMemFree` at `0x14000bd4d`
- `ole32!CoTaskMemFree` at `0x14000bd4d`

## pseudocode

```c
__int64 __fastcall WSZtoSZ(__int64 a1, const unsigned __int16 *a2, char **a3)
{
  unsigned int v5; // ebx
  char *v6; // rdi
  unsigned int cbMultiByte; // ebx
  CHAR *lpMultiByteStr; // rax
  unsigned int v9; // eax
  signed int LastError; // eax

  v5 = -2147024809;
  if ( a2 && a3 )
  {
    v6 = 0;
    cbMultiByte = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
    if ( cbMultiByte - 1 <= 0x3FF )
    {
      lpMultiByteStr = (CHAR *)CoTaskMemAlloc(cbMultiByte);
      v6 = lpMultiByteStr;
      if ( !lpMultiByteStr )
        return (unsigned int)-2147024882;
      v9 = WideCharToMultiByte(0, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0);
      if ( v9 && v9 <= cbMultiByte && !v6[v9 - 1] )
      {
        v5 = 0;
        *a3 = v6;
        return v5;
      }
    }
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 )
      CoTaskMemFree(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x14000bc68  mov     rax, rsp
0x14000bc6b  push    rbx
0x14000bc6c  push    rbp
0x14000bc6d  push    rsi
0x14000bc6e  push    rdi
0x14000bc6f  sub     rsp, 48h
0x14000bc73  mov     rsi, r8
0x14000bc76  mov     rbp, rdx
0x14000bc79  mov     ebx, 80070057h
0x14000bc7e  test    rdx, rdx
0x14000bc81  jz      loc_14000BD59
0x14000bc87  test    r8, r8
0x14000bc8a  jz      loc_14000BD59
0x14000bc90  xor     edi, edi
0x14000bc92  mov     r8, rdx; lpWideCharStr
0x14000bc95  mov     [rax-30h], rdi
0x14000bc99  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bc9d  mov     [rax-38h], rdi
0x14000bca1  xor     edx, edx; dwFlags
0x14000bca3  mov     [rax-40h], edi
0x14000bca6  xor     ecx, ecx; CodePage
0x14000bca8  mov     [rax-48h], rdi
0x14000bcac  call    cs:__imp_WideCharToMultiByte
0x14000bcb3  nop     dword ptr [rax+rax+00h]
0x14000bcb8  mov     ebx, eax
0x14000bcba  lea     eax, [rbx-1]
0x14000bcbd  cmp     eax, 3FFh
0x14000bcc2  ja      short loc_14000BD2A
0x14000bcc4  mov     ecx, ebx; cb
0x14000bcc6  call    cs:__imp_CoTaskMemAlloc
0x14000bccd  nop     dword ptr [rax+rax+00h]
0x14000bcd2  mov     rdi, rax
0x14000bcd5  test    rax, rax
0x14000bcd8  jnz     short loc_14000BCE1
0x14000bcda  mov     ebx, 8007000Eh
0x14000bcdf  jmp     short loc_14000BD59
0x14000bce1  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14000bcea  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bcee  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x14000bcf7  mov     r8, rbp; lpWideCharStr
0x14000bcfa  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x14000bcfe  xor     edx, edx; dwFlags
0x14000bd00  xor     ecx, ecx; CodePage
0x14000bd02  mov     [rsp+68h+lpMultiByteStr], rdi; lpMultiByteStr
0x14000bd07  call    cs:__imp_WideCharToMultiByte
0x14000bd0e  nop     dword ptr [rax+rax+00h]
0x14000bd13  test    eax, eax
0x14000bd15  jz      short loc_14000BD2A
0x14000bd17  cmp     eax, ebx
0x14000bd19  ja      short loc_14000BD2A
0x14000bd1b  dec     eax
0x14000bd1d  cmp     byte ptr [rax+rdi], 0
0x14000bd21  jnz     short loc_14000BD2A
0x14000bd23  xor     ebx, ebx
0x14000bd25  mov     [rsi], rdi
0x14000bd28  jmp     short loc_14000BD59
0x14000bd2a  call    cs:__imp_GetLastError
0x14000bd31  nop     dword ptr [rax+rax+00h]
0x14000bd36  mov     ebx, eax
0x14000bd38  test    eax, eax
0x14000bd3a  jle     short loc_14000BD45
0x14000bd3c  movzx   ebx, ax
0x14000bd3f  or      ebx, 80070000h
0x14000bd45  test    rdi, rdi
0x14000bd48  jz      short loc_14000BD59
0x14000bd4a  mov     rcx, rdi; pv
0x14000bd4d  call    cs:__imp_CoTaskMemFree
0x14000bd54  nop     dword ptr [rax+rax+00h]
0x14000bd59  mov     eax, ebx
0x14000bd5b  add     rsp, 48h
0x14000bd5f  pop     rdi
0x14000bd60  pop     rsi
0x14000bd61  pop     rbp
0x14000bd62  pop     rbx
0x14000bd63  retn
```
