# DiscpInstanceNameToOsDeviceName

- ea: `0x1800187e4`
- end: `0x18001896b`
- name: `DiscpInstanceNameToOsDeviceName`
- size: `391`
- prototype: `__int64 __fastcall(__int64, STRSAFE_LPWSTR *, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800180ec`
- `0x18001827c`

## callees

- `0x180001410`
- `0x18000325c`
- `0x18000bdb0`
- `0x1800187e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800188cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800188cf`
- `ISCSIUM!DiscpAllocMemory` at `0x1800188f2`
- `ISCSIUM!DiscpAllocMemory` at `0x1800188f2`
- `WMICLNT!WmiCloseBlock` at `0x180018939`
- `WMICLNT!WmiCloseBlock` at `0x180018939`
- `WMICLNT!WmiFileHandleToInstanceNameW` at `0x1800188bb`
- `WMICLNT!WmiFileHandleToInstanceNameW` at `0x1800188bb`
- `WMICLNT!WmiOpenBlock` at `0x180018840`
- `WMICLNT!WmiOpenBlock` at `0x180018840`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001888c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001888c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018920`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018920`

## pseudocode

```c
__int64 __fastcall DiscpInstanceNameToOsDeviceName(__int64 a1, STRSAFE_LPWSTR *a2, unsigned int *a3)
{
  unsigned int v6; // edi
  unsigned int i; // ebx
  HANDLE FileW; // rax
  void *v9; // rsi
  __int64 v10; // rax
  unsigned int v11; // edi
  __int64 v12; // rax
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[1040]; // [rsp+260h] [rbp+160h] BYREF

  v15 = 0;
  v14 = 0;
  v6 = -268500924;
  if ( !(unsigned int)WmiOpenBlock(MSiSCSI_HBAInformation_GUID, 0x80000000LL, &v15) )
  {
    for ( i = 0; i < 0x100; ++i )
    {
      StringCchPrintfW(pszDest, 0x104u, L"\\\\.\\Scsi%d:", i);
      FileW = CreateFileW(pszDest, 0xC0000000, 0, 0, 3u, 0, 0);
      v9 = FileW;
      if ( FileW != (HANDLE)-1LL )
      {
        v14 = 520;
        if ( !(unsigned int)WmiFileHandleToInstanceNameW(v15, FileW, &v14, v17) && !(unsigned int)_o__wcsicmp(v17, a1) )
        {
          v10 = -1;
          do
            ++v10;
          while ( pszDest[v10] );
          v11 = v10 + 1;
          v12 = DiscpAllocMemory((unsigned int)(2 * (v10 + 1)));
          *a2 = (STRSAFE_LPWSTR)v12;
          if ( v12 )
          {
            *a3 = i;
            StringCchCopyW(*a2, v11, pszDest);
            v6 = 0;
          }
          else
          {
            v6 = 8;
          }
        }
        CloseHandle(v9);
      }
    }
    WmiCloseBlock(v15);
  }
  return v6;
}

```

## disassembly

```asm
0x1800187e4  mov     [rsp-8+arg_18], rbx
0x1800187e9  push    rbp
0x1800187ea  push    rsi
0x1800187eb  push    rdi
0x1800187ec  push    r12
0x1800187ee  push    r13
0x1800187f0  push    r14
0x1800187f2  push    r15
0x1800187f4  lea     rbp, [rsp-580h]
0x1800187fc  sub     rsp, 680h
0x180018803  mov     rax, cs:__security_cookie
0x18001880a  xor     rax, rsp
0x18001880d  mov     [rbp+5B0h+var_40], rax
0x180018814  mov     r12, r8
0x180018817  mov     r14, rdx
0x18001881a  mov     r15, rcx
0x18001881d  lea     r8, [rsp+6B0h+var_668]
0x180018822  xor     r13d, r13d
0x180018825  lea     rcx, MSiSCSI_HBAInformation_GUID
0x18001882c  mov     edx, 80000000h
0x180018831  mov     [rsp+6B0h+var_668], r13
0x180018836  mov     [rsp+6B0h+var_670], r13d
0x18001883b  mov     edi, 0EFFF0044h
0x180018840  call    cs:__imp_WmiOpenBlock
0x180018846  test    eax, eax
0x180018848  jnz     loc_18001893F
0x18001884e  mov     ebx, r13d
0x180018851  mov     r9d, ebx
0x180018854  lea     r8, aScsiD; "\\\\.\\Scsi%d:"
0x18001885b  mov     edx, 104h; cchDest
0x180018860  lea     rcx, [rsp+6B0h+pszDest]; pszDest
0x180018865  call    StringCchPrintfW
0x18001886a  mov     [rsp+6B0h+hTemplateFile], r13; hTemplateFile
0x18001886f  lea     rcx, [rsp+6B0h+pszDest]; lpFileName
0x180018874  mov     [rsp+6B0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180018879  xor     r9d, r9d; lpSecurityAttributes
0x18001887c  xor     r8d, r8d; dwShareMode
0x18001887f  mov     [rsp+6B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180018887  mov     edx, 0C0000000h; dwDesiredAccess
0x18001888c  call    cs:__imp_CreateFileW
0x180018892  mov     rsi, rax
0x180018895  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018899  jz      loc_180018926
0x18001889f  mov     rcx, [rsp+6B0h+var_668]
0x1800188a4  lea     r9, [rbp+5B0h+var_450]
0x1800188ab  lea     r8, [rsp+6B0h+var_670]
0x1800188b0  mov     [rsp+6B0h+var_670], 208h
0x1800188b8  mov     rdx, rax
0x1800188bb  call    cs:__imp_WmiFileHandleToInstanceNameW
0x1800188c1  test    eax, eax
0x1800188c3  jnz     short loc_18001891D
0x1800188c5  mov     rdx, r15
0x1800188c8  lea     rcx, [rbp+5B0h+var_450]
0x1800188cf  call    cs:__imp__o__wcsicmp
0x1800188d5  test    eax, eax
0x1800188d7  jnz     short loc_18001891D
0x1800188d9  lea     rcx, [rsp+6B0h+pszDest]
0x1800188de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800188e2  inc     rax
0x1800188e5  cmp     [rcx+rax*2], r13w
0x1800188ea  jnz     short loc_1800188E2
0x1800188ec  lea     edi, [rax+1]
0x1800188ef  lea     ecx, [rdi+rdi]
0x1800188f2  call    cs:__imp_DiscpAllocMemory
0x1800188f8  mov     [r14], rax
0x1800188fb  test    rax, rax
0x1800188fe  jz      short loc_180018918
0x180018900  mov     [r12], ebx
0x180018904  lea     r8, [rsp+6B0h+pszDest]; pszSrc
0x180018909  mov     rcx, [r14]; pszDest
0x18001890c  mov     edx, edi; cchDest
0x18001890e  call    StringCchCopyW
0x180018913  mov     edi, r13d
0x180018916  jmp     short loc_18001891D
0x180018918  mov     edi, 8
0x18001891d  mov     rcx, rsi; hObject
0x180018920  call    cs:__imp_CloseHandle
0x180018926  inc     ebx
0x180018928  cmp     ebx, 100h
0x18001892e  jb      loc_180018851
0x180018934  mov     rcx, [rsp+6B0h+var_668]
0x180018939  call    cs:__imp_WmiCloseBlock
0x18001893f  mov     eax, edi
0x180018941  mov     rcx, [rbp+5B0h+var_40]
0x180018948  xor     rcx, rsp; StackCookie
0x18001894b  call    __security_check_cookie
0x180018950  mov     rbx, [rsp+6B0h+arg_18]
0x180018958  add     rsp, 680h
0x18001895f  pop     r15
0x180018961  pop     r14
0x180018963  pop     r13
0x180018965  pop     r12
0x180018967  pop     rdi
0x180018968  pop     rsi
0x180018969  pop     rbp
0x18001896a  retn
```
