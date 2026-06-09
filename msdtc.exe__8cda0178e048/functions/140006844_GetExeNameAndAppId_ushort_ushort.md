# GetExeNameAndAppId(ushort * *,ushort * *)

- ea: `0x140006844`
- end: `0x140006a73`
- name: `?GetExeNameAndAppId@@YAJPEAPEAG0@Z`
- size: `559`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140006a7c`

## callees

- `0x140002ed4`
- `0x140006774`
- `0x140006844`
- `0x140006f10`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x14000691c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x14000691c`
- `msvcrt!_wcsicmp` at `0x14000690e`
- `msvcrt!_wcsicmp` at `0x14000690e`
- `msvcrt!_stricmp` at `0x140006a34`
- `msvcrt!_stricmp` at `0x140006a34`
- `msvcrt!strchr` at `0x14000692a`
- `msvcrt!strchr` at `0x14000692a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400068a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400068a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400068c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400068c5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400068f8`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1400068f8`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1400068bb`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1400068bb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400069e8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400069e8`

## string_xrefs

- `0x140006907`: `dllhost.exe`
- `0x14000694f`: `/ProcessID`

## pseudocode

```c
__int64 __fastcall GetExeNameAndAppId(unsigned __int16 **a1, unsigned __int16 **a2)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v6; // ebx
  const char *CommandLineA; // rax
  char *v8; // rax
  char *v9; // rcx
  CHAR v10; // al
  CHAR *v11; // rcx
  CHAR *v12; // rbx
  CHAR *v13; // rax
  __int64 v14; // rcx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  char *v18; // [rsp+40h] [rbp-C0h] BYREF
  char String2[24]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR WideCharStr[48]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[272]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ExeName[264]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR Buffer[264]; // [rsp+3E0h] [rbp+2E0h] BYREF

  FilePart = 0;
  dwSize = 261;
  if ( a1 && a2 )
  {
    *a1 = 0;
    *a2 = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, &dwSize)
      || !GetFullPathNameW(ExeName, 0x105u, Buffer, &FilePart) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return v6;
    }
    if ( !_wcsicmp(L"dllhost.exe", FilePart) )
    {
      CommandLineA = GetCommandLineA();
      v8 = strchr(CommandLineA, 32);
      v9 = v8 + 1;
      if ( !v8 )
        v9 = 0;
      if ( v9 )
      {
        strcpy(String2, "/ProcessID");
        v18 = MultiByteStr;
        if ( (int)GetCommandLineArgumentsForTraceFileName(v9, &v18) >= 1 )
        {
          v10 = MultiByteStr[0];
          if ( MultiByteStr[0] )
          {
            v11 = MultiByteStr;
            while ( 1 )
            {
              v12 = v11 + 1;
              if ( v10 == 58 )
                break;
              v10 = *v12;
              ++v11;
              if ( !*v12 )
                goto LABEL_16;
            }
            *v11 = 0;
            v10 = *v12;
          }
          else
          {
            v12 = MultiByteStr;
          }
          if ( !v10 || _stricmp(MultiByteStr, String2) )
          {
LABEL_16:
            v12 = MultiByteStr;
LABEL_17:
            v13 = v12;
            v14 = 40;
            do
            {
              if ( !*v13 )
                break;
              ++v13;
              --v14;
            }
            while ( v14 );
            if ( v14 )
            {
              if ( MultiByteToWideChar(0, 0, v12, v14 != 0 ? 40 - v14 + 1 : 1, WideCharStr, 41) )
              {
                v6 = 0;
                if ( (int)DuplicateString(WideCharStr, a2) < 0 )
                  return v6;
              }
            }
            return (unsigned int)DuplicateString(FilePart, a1);
          }
          if ( v12 )
            goto LABEL_17;
        }
      }
    }
    return (unsigned int)DuplicateString(FilePart, a1);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140006844  mov     [rsp-8+arg_10], rbx
0x140006849  push    rbp
0x14000684a  push    rsi
0x14000684b  push    rdi
0x14000684c  lea     rbp, [rsp-500h]
0x140006854  sub     rsp, 600h
0x14000685b  mov     rax, cs:__security_cookie
0x140006862  xor     rax, rsp
0x140006865  mov     [rbp+510h+var_20], rax
0x14000686c  mov     [rsp+610h+FilePart], 0
0x140006875  mov     ebx, 105h
0x14000687a  mov     [rsp+610h+dwSize], ebx
0x14000687e  mov     rdi, rdx
0x140006881  mov     rsi, rcx
0x140006884  test    rcx, rcx
0x140006887  jz      loc_140006A4C
0x14000688d  test    rdx, rdx
0x140006890  jz      loc_140006A4C
0x140006896  mov     qword ptr [rcx], 0
0x14000689d  mov     qword ptr [rdx], 0
0x1400068a4  call    cs:__imp_GetCurrentProcess
0x1400068aa  lea     r9, [rsp+610h+dwSize]; lpdwSize
0x1400068af  xor     edx, edx; dwFlags
0x1400068b1  mov     rcx, rax; hProcess
0x1400068b4  lea     r8, [rbp+510h+ExeName]; lpExeName
0x1400068bb  call    cs:__imp_QueryFullProcessImageNameW
0x1400068c1  test    eax, eax
0x1400068c3  jnz     short loc_1400068E3
0x1400068c5  call    cs:__imp_GetLastError
0x1400068cb  mov     ebx, eax
0x1400068cd  test    eax, eax
0x1400068cf  jle     loc_140006A14
0x1400068d5  movzx   ebx, ax
0x1400068d8  or      ebx, 80070000h
0x1400068de  jmp     loc_140006A14
0x1400068e3  lea     r9, [rsp+610h+FilePart]; lpFilePart
0x1400068e8  mov     edx, ebx; nBufferLength
0x1400068ea  lea     r8, [rbp+510h+Buffer]; lpBuffer
0x1400068f1  lea     rcx, [rbp+510h+ExeName]; lpFileName
0x1400068f8  call    cs:__imp_GetFullPathNameW
0x1400068fe  test    eax, eax
0x140006900  jz      short loc_1400068C5
0x140006902  mov     rdx, [rsp+610h+FilePart]; String2
0x140006907  lea     rcx, aDllhostExe; "dllhost.exe"
0x14000690e  call    cs:__imp__wcsicmp
0x140006914  test    eax, eax
0x140006916  jnz     loc_140006A05
0x14000691c  call    cs:__imp_GetCommandLineA
0x140006922  mov     rcx, rax; Str
0x140006925  mov     edx, 20h ; ' '; Val
0x14000692a  call    cs:__imp_strchr
0x140006930  test    rax, rax
0x140006933  lea     rcx, [rax+1]
0x140006937  cmovz   rcx, rax; char *
0x14000693b  test    rcx, rcx
0x14000693e  jz      loc_140006A05
0x140006944  mov     eax, dword ptr cs:aProcessid+7; "sID"
0x14000694a  lea     rdx, [rsp+610h+var_5D0]; char **
0x14000694f  movsd   xmm0, qword ptr cs:aProcessid; "/ProcessID"
0x140006957  movsd   qword ptr [rsp+610h+String2], xmm0
0x14000695d  mov     dword ptr [rsp+610h+String2+7], eax
0x140006961  lea     rax, [rbp+510h+MultiByteStr]
0x140006965  mov     [rsp+610h+var_5D0], rax
0x14000696a  call    ?GetCommandLineArgumentsForTraceFileName@@YAHPEADQEAPEADHH@Z; GetCommandLineArgumentsForTraceFileName(char *,char * * const,int,int)
0x14000696f  cmp     eax, 1
0x140006972  jl      loc_140006A05
0x140006978  mov     al, [rbp+510h+MultiByteStr]
0x14000697b  test    al, al
0x14000697d  jz      loc_140006A1F
0x140006983  lea     rcx, [rbp+510h+MultiByteStr]
0x140006987  lea     rbx, [rcx+1]
0x14000698b  cmp     al, 3Ah ; ':'
0x14000698d  jz      loc_140006A18
0x140006993  mov     al, [rbx]
0x140006995  mov     rcx, rbx
0x140006998  test    al, al
0x14000699a  jnz     short loc_140006987
0x14000699c  lea     rbx, [rbp+510h+MultiByteStr]
0x1400069a0  mov     edx, 28h ; '('
0x1400069a5  mov     rax, rbx
0x1400069a8  mov     ecx, edx
0x1400069aa  cmp     byte ptr [rax], 0
0x1400069ad  jz      short loc_1400069B8
0x1400069af  inc     rax
0x1400069b2  sub     rcx, 1
0x1400069b6  jnz     short loc_1400069AA
0x1400069b8  sub     rdx, rcx
0x1400069bb  mov     rax, rcx
0x1400069be  neg     rax
0x1400069c1  sbb     r9, r9
0x1400069c4  and     r9, rdx
0x1400069c7  test    rcx, rcx
0x1400069ca  jz      short loc_140006A05
0x1400069cc  lea     rax, [rsp+610h+WideCharStr]
0x1400069d1  mov     [rsp+610h+cchWideChar], 29h ; ')'; cchWideChar
0x1400069d9  inc     r9d; cbMultiByte
0x1400069dc  mov     [rsp+610h+lpWideCharStr], rax; lpWideCharStr
0x1400069e1  mov     r8, rbx; lpMultiByteStr
0x1400069e4  xor     edx, edx; dwFlags
0x1400069e6  xor     ecx, ecx; CodePage
0x1400069e8  call    cs:__imp_MultiByteToWideChar
0x1400069ee  test    eax, eax
0x1400069f0  jz      short loc_140006A05
0x1400069f2  mov     rdx, rdi; unsigned __int16 **
0x1400069f5  lea     rcx, [rsp+610h+WideCharStr]; unsigned __int16 *
0x1400069fa  xor     ebx, ebx
0x1400069fc  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x140006a01  test    eax, eax
0x140006a03  js      short loc_140006A14
0x140006a05  mov     rcx, [rsp+610h+FilePart]; unsigned __int16 *
0x140006a0a  mov     rdx, rsi; unsigned __int16 **
0x140006a0d  call    ?DuplicateString@@YAJPEBGPEAPEAG@Z; DuplicateString(ushort const *,ushort * *)
0x140006a12  mov     ebx, eax
0x140006a14  mov     eax, ebx
0x140006a16  jmp     short loc_140006A51
0x140006a18  mov     byte ptr [rcx], 0
0x140006a1b  mov     al, [rbx]
0x140006a1d  jmp     short loc_140006A23
0x140006a1f  lea     rbx, [rbp+510h+MultiByteStr]
0x140006a23  test    al, al
0x140006a25  jz      loc_14000699C
0x140006a2b  lea     rdx, [rsp+610h+String2]; String2
0x140006a30  lea     rcx, [rbp+510h+MultiByteStr]; String1
0x140006a34  call    cs:__imp__stricmp
0x140006a3a  test    eax, eax
0x140006a3c  jnz     loc_14000699C
0x140006a42  test    rbx, rbx
0x140006a45  jz      short loc_140006A05
0x140006a47  jmp     loc_1400069A0
0x140006a4c  mov     eax, 80070057h
0x140006a51  mov     rcx, [rbp+510h+var_20]
0x140006a58  xor     rcx, rsp; StackCookie
0x140006a5b  call    __security_check_cookie
0x140006a60  mov     rbx, [rsp+610h+arg_10]
0x140006a68  add     rsp, 600h
0x140006a6f  pop     rdi
0x140006a70  pop     rsi
0x140006a71  pop     rbp
0x140006a72  retn
```
