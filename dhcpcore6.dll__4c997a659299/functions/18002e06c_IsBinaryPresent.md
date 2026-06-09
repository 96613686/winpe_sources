# IsBinaryPresent

- ea: `0x18002e06c`
- end: `0x18002e19e`
- name: `IsBinaryPresent`
- size: `306`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001b808`

## callees

- `0x1800077e0`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18002e06c`
- `0x18002e1a4`
- `0x1800337d0`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e0dc`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e142`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002e142`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e0cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002e0cc`

## pseudocode

```c
__int64 __fastcall IsBinaryPresent(STRSAFE_LPCWSTR pszSrc)
{
  unsigned int v2; // ebx
  size_t v3; // rdx
  DWORD LastError; // eax
  HRESULT v5; // eax
  size_t v6; // rdx
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x208u);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 10, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, pszSrc);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_4;
  v5 = StringCchCatW(Buffer, v3, L"\\");
  if ( v5 < 0 || (v5 = StringCchCatW(Buffer, v6, pszSrc), v5 < 0) )
  {
    LastError = WX_WIN32_FROM_HR((unsigned int)v5);
  }
  else
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 11, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, Buffer);
    if ( GetFileAttributesW(Buffer) == -1 )
    {
LABEL_4:
      LastError = GetLastError();
      goto LABEL_12;
    }
    LastError = 0;
    v2 = 1;
  }
LABEL_12:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 12, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids, LastError);
  return v2;
}

```

## disassembly

```asm
0x18002e06c  mov     [rsp+arg_8], rbx
0x18002e071  push    rdi
0x18002e072  sub     rsp, 240h
0x18002e079  mov     rax, cs:__security_cookie
0x18002e080  xor     rax, rsp
0x18002e083  mov     [rsp+248h+var_18], rax
0x18002e08b  mov     rdi, rcx
0x18002e08e  xor     ebx, ebx
0x18002e090  lea     rcx, [rsp+248h+Buffer]; void *
0x18002e095  xor     edx, edx; Val
0x18002e097  mov     r8d, 208h; Size
0x18002e09d  call    memset_0
0x18002e0a2  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e0a9  jz      short loc_18002E0C2
0x18002e0ab  lea     edx, [rbx+0Ah]
0x18002e0ae  mov     ecx, 404h
0x18002e0b3  mov     r9, rdi
0x18002e0b6  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x18002e0bd  call    WPP_SF_S
0x18002e0c2  mov     edx, 104h; uSize
0x18002e0c7  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x18002e0cc  call    cs:__imp_GetSystemDirectoryW
0x18002e0d3  nop     dword ptr [rax+rax+00h]
0x18002e0d8  test    eax, eax
0x18002e0da  jnz     short loc_18002E0EA
0x18002e0dc  call    cs:__imp_GetLastError
0x18002e0e3  nop     dword ptr [rax+rax+00h]
0x18002e0e8  jmp     short loc_18002E158
0x18002e0ea  lea     r8, pszSrc; "\\"
0x18002e0f1  lea     rcx, [rsp+248h+Buffer]; pszDest
0x18002e0f6  call    StringCchCatW
0x18002e0fb  test    eax, eax
0x18002e0fd  jns     short loc_18002E108
0x18002e0ff  mov     ecx, eax
0x18002e101  call    WX_WIN32_FROM_HR
0x18002e106  jmp     short loc_18002E158
0x18002e108  mov     r8, rdi; pszSrc
0x18002e10b  lea     rcx, [rsp+248h+Buffer]; pszDest
0x18002e110  call    StringCchCatW
0x18002e115  test    eax, eax
0x18002e117  js      short loc_18002E0FF
0x18002e119  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e120  jz      short loc_18002E13D
0x18002e122  mov     edx, 0Bh
0x18002e127  lea     r9, [rsp+248h+Buffer]
0x18002e12c  mov     ecx, 404h
0x18002e131  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x18002e138  call    WPP_SF_S
0x18002e13d  lea     rcx, [rsp+248h+Buffer]; lpFileName
0x18002e142  call    cs:__imp_GetFileAttributesW
0x18002e149  nop     dword ptr [rax+rax+00h]
0x18002e14e  cmp     eax, 0FFFFFFFFh
0x18002e151  jz      short loc_18002E0DC
0x18002e153  xor     eax, eax
0x18002e155  lea     ebx, [rax+1]
0x18002e158  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e15f  jz      short loc_18002E17A
0x18002e161  mov     edx, 0Ch
0x18002e166  lea     r8, WPP_9c53ef35ceb23ce2918137816874c499_Traceguids
0x18002e16d  mov     ecx, 404h
0x18002e172  mov     r9d, eax
0x18002e175  call    WPP_SF_D
0x18002e17a  mov     eax, ebx
0x18002e17c  mov     rcx, [rsp+248h+var_18]
0x18002e184  xor     rcx, rsp; StackCookie
0x18002e187  call    __security_check_cookie
0x18002e18c  mov     rbx, [rsp+248h+arg_8]
0x18002e194  add     rsp, 240h
0x18002e19b  pop     rdi
0x18002e19c  retn
```
