# LoadLibraryFromSystemDirectory

- ea: `0x14005757c`
- end: `0x1400576bf`
- name: `LoadLibraryFromSystemDirectory`
- size: `323`
- prototype: `__int64 __fastcall(__int64, HMODULE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x14005954c`

## callees

- `0x140002070`
- `0x140002c68`
- `0x14005757c`
- `0x1400576c8`
- `0x140057730`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14005767b`
- `KERNEL32!GetLastError` at `0x14005767b`
- `KERNEL32!LoadLibraryW` at `0x140057670`
- `KERNEL32!LoadLibraryW` at `0x140057670`
- `KERNEL32!GetSystemDirectoryW` at `0x140057621`
- `KERNEL32!GetSystemDirectoryW` at `0x140057621`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400575d9`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1400575d9`

## pseudocode

```c
__int64 __fastcall LoadLibraryFromSystemDirectory(__int64 a1, HMODULE *a2)
{
  HRESULT v3; // ebx
  wchar_t *v4; // rax
  __int64 SystemDirectoryW; // r9
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  wchar_t Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  pcchLength[0] = 0;
  if ( a2 )
  {
    v4 = wcsstr(L"winspool.drv", L"\\");
    *a2 = 0;
    if ( v4 )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      v3 = StringCchLengthW(L"winspool.drv", 0x103u, pcchLength);
      if ( v3 >= 0 )
      {
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
        if ( (unsigned __int64)(SystemDirectoryW - 1) > 0x101 || SystemDirectoryW + pcchLength[0] >= 0x103 )
        {
          return (unsigned int)-2147467259;
        }
        else
        {
          Buffer[SystemDirectoryW] = 92;
          v3 = StringCchCatW(Buffer, 0x104u, L"winspool.drv");
          if ( v3 >= 0 )
          {
            LibraryW = LoadLibraryW(Buffer);
            if ( LibraryW )
            {
              *a2 = LibraryW;
            }
            else
            {
              LastError = GetLastError();
              v3 = LastError;
              if ( LastError > 0 )
                return (unsigned __int16)LastError | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v3 = -2147024809;
    MEMORY[0] = 0;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14005757c  mov     [rsp+arg_0], rbx
0x140057581  push    rdi
0x140057582  sub     rsp, 250h
0x140057589  mov     rax, cs:__security_cookie
0x140057590  xor     rax, rsp
0x140057593  mov     [rsp+258h+var_18], rax
0x14005759b  mov     rdi, rdx
0x14005759e  lea     rcx, [rsp+258h+Buffer]; void *
0x1400575a3  xor     edx, edx; Val
0x1400575a5  mov     r8d, 208h; Size
0x1400575ab  call    memset_0
0x1400575b0  mov     [rsp+258h+pcchLength], 0
0x1400575b9  test    rdi, rdi
0x1400575bc  jnz     short loc_1400575CB
0x1400575be  mov     ebx, 80070057h
0x1400575c3  mov     [rdi], rdi
0x1400575c6  jmp     loc_14005769C
0x1400575cb  lea     rdx, asc_1400691D8; "\\"
0x1400575d2  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x1400575d9  call    cs:__imp_wcsstr
0x1400575df  mov     qword ptr [rdi], 0
0x1400575e6  test    rax, rax
0x1400575e9  jz      short loc_1400575F5
0x1400575eb  mov     ebx, 80070057h
0x1400575f0  jmp     loc_14005769C
0x1400575f5  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x1400575fa  mov     edx, 103h; cchMax
0x1400575ff  lea     rcx, aWinspoolDrv_0; "winspool.drv"
0x140057606  call    StringCchLengthW
0x14005760b  mov     ebx, eax
0x14005760d  test    eax, eax
0x14005760f  js      loc_14005769C
0x140057615  mov     ebx, 104h
0x14005761a  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x14005761f  mov     edx, ebx; uSize
0x140057621  call    cs:__imp_GetSystemDirectoryW
0x140057627  mov     r9d, eax
0x14005762a  lea     rax, [r9-1]
0x14005762e  cmp     rax, 101h
0x140057634  ja      short loc_140057697
0x140057636  mov     rcx, [rsp+258h+pcchLength]
0x14005763b  add     rcx, r9
0x14005763e  cmp     rcx, 103h
0x140057645  jnb     short loc_140057697
0x140057647  mov     eax, 5Ch ; '\'
0x14005764c  lea     r8, aWinspoolDrv_0; "winspool.drv"
0x140057653  mov     edx, ebx; cchDest
0x140057655  mov     [rsp+r9*2+258h+Buffer], ax
0x14005765b  lea     rcx, [rsp+258h+Buffer]; pszDest
0x140057660  call    StringCchCatW
0x140057665  mov     ebx, eax
0x140057667  test    eax, eax
0x140057669  js      short loc_14005769C
0x14005766b  lea     rcx, [rsp+258h+Buffer]; lpLibFileName
0x140057670  call    cs:__imp_LoadLibraryW
0x140057676  test    rax, rax
0x140057679  jnz     short loc_140057692
0x14005767b  call    cs:__imp_GetLastError
0x140057681  mov     ebx, eax
0x140057683  test    eax, eax
0x140057685  jle     short loc_14005769C
0x140057687  movzx   ebx, ax
0x14005768a  or      ebx, 80070000h
0x140057690  jmp     short loc_14005769C
0x140057692  mov     [rdi], rax
0x140057695  jmp     short loc_14005769C
0x140057697  mov     ebx, 80004005h
0x14005769c  mov     eax, ebx
0x14005769e  mov     rcx, [rsp+258h+var_18]
0x1400576a6  xor     rcx, rsp; StackCookie
0x1400576a9  call    __security_check_cookie
0x1400576ae  mov     rbx, [rsp+258h+arg_0]
0x1400576b6  add     rsp, 250h
0x1400576bd  pop     rdi
0x1400576be  retn
```
