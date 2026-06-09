# NetpOpenConfigDataWithPathEx

- ea: `0x18000bb90`
- end: `0x18000bce3`
- name: `NetpOpenConfigDataWithPathEx`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18004ed98`

## callees

- `0x180003200`
- `0x18000bb90`
- `0x18000ed04`
- `0x18000ed10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bca6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcbd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bc18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bca6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcaf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bcbd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc8b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000bc8b`

## pseudocode

```c
__int64 __fastcall NetpOpenConfigDataWithPathEx(HKEY **a1, const wchar_t *a2, HKEY a3)
{
  HKEY *v5; // r14
  __int64 v7; // rax
  unsigned __int64 v9; // rdi
  wchar_t *v10; // rax
  wchar_t *v11; // rbp
  rsize_t v12; // rdi
  LSTATUS v13; // eax
  unsigned int v14; // ebx
  HKEY phkResult; // [rsp+60h] [rbp+18h] BYREF

  phkResult = a3;
  *a1 = 0;
  if ( !a2 || !*a2 )
    return 87;
  v5 = (HKEY *)NetpMemoryAllocate(16);
  if ( !v5 )
    return 8;
  v7 = -1;
  phkResult = 0;
  while ( a2[++v7] != 0 )
    ;
  v9 = (unsigned int)(2 * v7 + 24);
  v10 = (wchar_t *)NetpMemoryAllocate(v9);
  v11 = v10;
  if ( v10 )
  {
    v12 = v9 >> 1;
    wcscpy_s(v10, v12, a2);
    wcscat_s(v11, v12, L"\\");
    wcscat_s(v11, v12, L"Parameters");
    v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0x20019u, &phkResult);
    v14 = v13;
    if ( v13 == 2 )
    {
      v14 = 2146;
    }
    else if ( !v13 )
    {
      LocalFree(v11);
      v14 = 0;
      *v5 = phkResult;
      goto LABEL_15;
    }
    LocalFree(v11);
    LocalFree(v5);
    v5 = 0;
LABEL_15:
    *a1 = v5;
    return v14;
  }
  LocalFree(v5);
  return 8;
}

```

## disassembly

```asm
0x18000bb90  mov     [rsp+arg_10], r8
0x18000bb95  push    rbx
0x18000bb96  push    rsi
0x18000bb97  sub     rsp, 38h
0x18000bb9b  mov     qword ptr [rcx], 0
0x18000bba2  mov     rbx, rdx
0x18000bba5  mov     rsi, rcx
0x18000bba8  test    rdx, rdx
0x18000bbab  jz      loc_18000BCD7
0x18000bbb1  cmp     word ptr [rdx], 0
0x18000bbb5  jz      loc_18000BCD7
0x18000bbbb  mov     ecx, 10h
0x18000bbc0  mov     [rsp+48h+var_18], r14
0x18000bbc5  call    NetpMemoryAllocate
0x18000bbca  mov     r14, rax
0x18000bbcd  test    rax, rax
0x18000bbd0  jnz     short loc_18000BBD9
0x18000bbd2  mov     eax, 8
0x18000bbd7  jmp     short loc_18000BC2D
0x18000bbd9  mov     [rsp+48h+arg_0], rbp
0x18000bbde  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000bbe5  mov     [rsp+48h+arg_8], rdi
0x18000bbea  mov     [rsp+48h+arg_10], 0
0x18000bbf3  cmp     word ptr [rbx+rax*2+2], 0
0x18000bbf9  lea     rax, [rax+1]
0x18000bbfd  jnz     short loc_18000BBF3
0x18000bbff  lea     edi, ds:18h[rax*2]
0x18000bc06  mov     ecx, edi
0x18000bc08  call    NetpMemoryAllocate
0x18000bc0d  mov     rbp, rax
0x18000bc10  test    rax, rax
0x18000bc13  jnz     short loc_18000BC39
0x18000bc15  mov     rcx, r14; hMem
0x18000bc18  call    cs:__imp_LocalFree
0x18000bc1e  mov     eax, 8
0x18000bc23  mov     rdi, [rsp+48h+arg_8]
0x18000bc28  mov     rbp, [rsp+48h+arg_0]
0x18000bc2d  mov     r14, [rsp+48h+var_18]
0x18000bc32  add     rsp, 38h
0x18000bc36  pop     rsi
0x18000bc37  pop     rbx
0x18000bc38  retn
0x18000bc39  shr     rdi, 1
0x18000bc3c  mov     r8, rbx; Source
0x18000bc3f  mov     rdx, rdi; SizeInWords
0x18000bc42  mov     rcx, rbp; Destination
0x18000bc45  call    wcscpy_s
0x18000bc4a  lea     r8, SubStr; "\\"
0x18000bc51  mov     rdx, rdi; SizeInWords
0x18000bc54  mov     rcx, rbp; Destination
0x18000bc57  call    wcscat_s
0x18000bc5c  lea     r8, aParameters; "Parameters"
0x18000bc63  mov     rdx, rdi; SizeInWords
0x18000bc66  mov     rcx, rbp; Destination
0x18000bc69  call    wcscat_s
0x18000bc6e  lea     rax, [rsp+48h+arg_10]
0x18000bc73  mov     r9d, 20019h; samDesired
0x18000bc79  xor     r8d, r8d; ulOptions
0x18000bc7c  mov     [rsp+48h+phkResult], rax; phkResult
0x18000bc81  mov     rdx, rbp; lpSubKey
0x18000bc84  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000bc8b  call    cs:__imp_RegOpenKeyExW
0x18000bc91  mov     ebx, eax
0x18000bc93  cmp     eax, 2
0x18000bc96  jnz     short loc_18000BC9F
0x18000bc98  mov     ebx, 862h
0x18000bc9d  jmp     short loc_18000BCA3
0x18000bc9f  test    eax, eax
0x18000bca1  jz      short loc_18000BCBA
0x18000bca3  mov     rcx, rbp; hMem
0x18000bca6  call    cs:__imp_LocalFree
0x18000bcac  mov     rcx, r14; hMem
0x18000bcaf  call    cs:__imp_LocalFree
0x18000bcb5  xor     r14d, r14d
0x18000bcb8  jmp     short loc_18000BCCD
0x18000bcba  mov     rcx, rbp; hMem
0x18000bcbd  call    cs:__imp_LocalFree
0x18000bcc3  mov     rax, [rsp+48h+arg_10]
0x18000bcc8  xor     ebx, ebx
0x18000bcca  mov     [r14], rax
0x18000bccd  mov     [rsi], r14
0x18000bcd0  mov     eax, ebx
0x18000bcd2  jmp     loc_18000BC23
0x18000bcd7  mov     eax, 57h ; 'W'
0x18000bcdc  add     rsp, 38h
0x18000bce0  pop     rsi
0x18000bce1  pop     rbx
0x18000bce2  retn
```
