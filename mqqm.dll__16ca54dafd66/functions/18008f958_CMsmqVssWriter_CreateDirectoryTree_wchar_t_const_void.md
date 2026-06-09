# CMsmqVssWriter::CreateDirectoryTree(wchar_t const *,void *)

- ea: `0x18008f958`
- end: `0x18008faf9`
- name: `?CreateDirectoryTree@CMsmqVssWriter@@AEAAJPEB_WPEAX@Z`
- size: `417`
- prototype: `int(CMsmqVssWriter *__hidden this, const wchar_t *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180091840`
- `0x180092180`

## callees

- `0x18000bab8`
- `0x18000cb80`
- `0x18002c61c`
- `0x18008f958`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18008fa00`
- `msvcrt!wcsrchr` at `0x18008fa00`
- `KERNEL32!GetLastError` at `0x18008f9e8`
- `KERNEL32!GetLastError` at `0x18008fa91`
- `KERNEL32!GetLastError` at `0x18008f9e8`
- `KERNEL32!GetLastError` at `0x18008fa91`
- `KERNEL32!GetFileAttributesW` at `0x18008f9dd`
- `KERNEL32!GetFileAttributesW` at `0x18008f9dd`
- `KERNEL32!CreateDirectoryW` at `0x18008fa37`
- `KERNEL32!CreateDirectoryW` at `0x18008fa37`
- `mqsec!MQSec_SetDirectorySecurityForService` at `0x18008fa46`
- `mqsec!MQSec_SetDirectorySecurityForService` at `0x18008fa46`

## string_xrefs

- `0x18008fa7f`: `writer/mqwriter`
- `0x18008fac1`: `writer/mqwriter`

## pseudocode

```c
__int64 __fastcall CMsmqVssWriter::CreateDirectoryTree(CMsmqVssWriter *this, const wchar_t *a2, void *a3)
{
  signed int v3; // ebx
  const wchar_t *v4; // r11
  unsigned __int16 v5; // r8
  WCHAR *v6; // rsi
  wchar_t *v7; // rbx
  DWORD FileAttributesW; // eax
  wchar_t *v9; // rax
  __int64 v10; // rbp
  int v11; // eax
  unsigned int v12; // edi
  bool v13; // sf
  signed int LastError; // eax
  wchar_t FileName[264]; // [rsp+20h] [rbp-238h] BYREF

  v3 = StringCchCopyW(FileName, 0x104u, a2);
  if ( v3 >= 0 )
  {
    v6 = &FileName[mqwcslen(v4)];
    v7 = v6;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( (char *)v7 - (char *)FileName < 0 || (((char *)v7 - (char *)FileName) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          v5 = 1800;
          goto LABEL_26;
        }
        FileAttributesW = GetFileAttributesW(FileName);
        if ( FileAttributesW == -1 )
          break;
        if ( (FileAttributesW & 0x10) != 0 )
        {
          while ( 1 )
          {
            if ( v7 >= v6 )
              return 0;
            *v7 = 92;
            v10 = mqwcslen(v7);
            if ( !CreateDirectoryW(FileName, 0) )
              break;
            v11 = MQSec_SetDirectorySecurityForService(FileName);
            v12 = v11;
            if ( v11 < 0 )
            {
              LogMsgHR(v11, (wchar_t *)L"writer/mqwriter", 0xFB5u);
              return v12;
            }
            v7 += v10;
          }
          LastError = GetLastError();
          v3 = LastError;
          if ( LastError > 0 )
            v3 = (unsigned __int16)LastError | 0x80070000;
          if ( v3 < 0 )
          {
            v5 = 1820;
            goto LABEL_27;
          }
          return (unsigned int)v3;
        }
      }
      v3 = GetLastError();
      if ( (unsigned int)(v3 - 2) > 1 )
        break;
      v9 = wcsrchr(FileName, 0x5Cu);
      v7 = v9;
      if ( !v9 )
      {
        v5 = 1760;
LABEL_26:
        v3 = -1072824314;
        goto LABEL_27;
      }
      *v9 = 0;
    }
    v13 = v3 < 0;
    if ( v3 > 0 )
    {
      v3 = (unsigned __int16)v3 | 0x80070000;
      v13 = v3 < 0;
    }
    if ( v13 )
    {
      v5 = 1780;
      goto LABEL_27;
    }
  }
  else
  {
    v5 = 1740;
LABEL_27:
    LogMsgHR(v3, (wchar_t *)L"writer/mqwriter", v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18008f958  mov     [rsp+arg_0], rbx
0x18008f95d  mov     [rsp+arg_10], rbp
0x18008f962  push    rsi
0x18008f963  push    rdi
0x18008f964  push    r14
0x18008f966  sub     rsp, 240h
0x18008f96d  mov     rax, cs:__security_cookie
0x18008f974  xor     rax, rsp
0x18008f977  mov     [rsp+258h+var_28], rax
0x18008f97f  mov     r11, rdx
0x18008f982  lea     rcx, [rsp+258h+FileName]; wchar_t *
0x18008f987  mov     r8, rdx; wchar_t *
0x18008f98a  mov     edx, 104h; unsigned __int64
0x18008f98f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18008f994  mov     ebx, eax
0x18008f996  test    eax, eax
0x18008f998  jns     short loc_18008F9A5
0x18008f99a  mov     r8d, 6CCh
0x18008f9a0  jmp     loc_18008FAC1
0x18008f9a5  mov     rcx, r11; wchar_t *
0x18008f9a8  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18008f9ad  mov     eax, eax
0x18008f9af  lea     rsi, [rsp+258h+FileName]
0x18008f9b4  mov     r14d, 5Ch ; '\'
0x18008f9ba  lea     rsi, [rsi+rax*2]
0x18008f9be  mov     rbx, rsi
0x18008f9c1  lea     rcx, [rsp+258h+FileName]
0x18008f9c6  mov     rax, rbx
0x18008f9c9  sub     rax, rcx
0x18008f9cc  test    rax, 0FFFFFFFFFFFFFFFEh
0x18008f9d2  jle     loc_18008FAB6
0x18008f9d8  lea     rcx, [rsp+258h+FileName]; lpFileName
0x18008f9dd  call    cs:__imp_GetFileAttributesW
0x18008f9e3  cmp     eax, 0FFFFFFFFh
0x18008f9e6  jnz     short loc_18008FA15
0x18008f9e8  call    cs:__imp_GetLastError
0x18008f9ee  mov     ebx, eax
0x18008f9f0  add     eax, 0FFFFFFFEh
0x18008f9f3  cmp     eax, 1
0x18008f9f6  ja      short loc_18008FA60
0x18008f9f8  mov     edx, r14d; Ch
0x18008f9fb  lea     rcx, [rsp+258h+FileName]; Str
0x18008fa00  call    cs:__imp_wcsrchr
0x18008fa06  mov     rbx, rax
0x18008fa09  test    rax, rax
0x18008fa0c  jz      short loc_18008FA58
0x18008fa0e  xor     ecx, ecx
0x18008fa10  mov     [rax], cx
0x18008fa13  jmp     short loc_18008F9C1
0x18008fa15  test    al, 10h
0x18008fa17  jz      short loc_18008F9C1
0x18008fa19  cmp     rbx, rsi
0x18008fa1c  jnb     loc_18008FAB2
0x18008fa22  mov     rcx, rbx; wchar_t *
0x18008fa25  mov     [rbx], r14w
0x18008fa29  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x18008fa2e  xor     edx, edx; lpSecurityAttributes
0x18008fa30  mov     ebp, eax
0x18008fa32  lea     rcx, [rsp+258h+FileName]; lpPathName
0x18008fa37  call    cs:__imp_CreateDirectoryW
0x18008fa3d  test    eax, eax
0x18008fa3f  jz      short loc_18008FA91
0x18008fa41  lea     rcx, [rsp+258h+FileName]
0x18008fa46  call    cs:__imp_?MQSec_SetDirectorySecurityForService@@YAJPEB_W@Z; MQSec_SetDirectorySecurityForService(wchar_t const *)
0x18008fa4c  mov     edi, eax
0x18008fa4e  test    eax, eax
0x18008fa50  js      short loc_18008FA79
0x18008fa52  lea     rbx, [rbx+rbp*2]
0x18008fa56  jmp     short loc_18008FA19
0x18008fa58  mov     r8d, 6E0h
0x18008fa5e  jmp     short loc_18008FABC
0x18008fa60  test    ebx, ebx
0x18008fa62  jle     short loc_18008FA6F
0x18008fa64  movzx   ebx, bx
0x18008fa67  or      ebx, 80070000h
0x18008fa6d  test    ebx, ebx
0x18008fa6f  jns     short loc_18008FACF
0x18008fa71  mov     r8d, 6F4h
0x18008fa77  jmp     short loc_18008FAC1
0x18008fa79  mov     r8d, 0FB5h; unsigned __int16
0x18008fa7f  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008fa86  mov     ecx, edi; int
0x18008fa88  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008fa8d  mov     eax, edi
0x18008fa8f  jmp     short loc_18008FAD1
0x18008fa91  call    cs:__imp_GetLastError
0x18008fa97  mov     ebx, eax
0x18008fa99  test    eax, eax
0x18008fa9b  jle     short loc_18008FAA6
0x18008fa9d  movzx   ebx, ax
0x18008faa0  or      ebx, 80070000h
0x18008faa6  test    ebx, ebx
0x18008faa8  jns     short loc_18008FACF
0x18008faaa  mov     r8d, 71Ch
0x18008fab0  jmp     short loc_18008FAC1
0x18008fab2  xor     eax, eax
0x18008fab4  jmp     short loc_18008FAD1
0x18008fab6  mov     r8d, 708h; unsigned __int16
0x18008fabc  mov     ebx, 0C00E0006h
0x18008fac1  lea     rdx, aWriterMqwriter; "writer/mqwriter"
0x18008fac8  mov     ecx, ebx; int
0x18008faca  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18008facf  mov     eax, ebx
0x18008fad1  mov     rcx, [rsp+258h+var_28]
0x18008fad9  xor     rcx, rsp; StackCookie
0x18008fadc  call    __security_check_cookie
0x18008fae1  lea     r11, [rsp+258h+var_18]
0x18008fae9  mov     rbx, [r11+20h]
0x18008faed  mov     rbp, [r11+30h]
0x18008faf1  mov     rsp, r11
0x18008faf4  pop     r14
0x18008faf6  pop     rdi
0x18008faf7  pop     rsi
0x18008faf8  retn
```
