# DsRolepDsGetDcForAccount

- ea: `0x18001f048`
- end: `0x18001f16c`
- name: `DsRolepDsGetDcForAccount`
- size: `292`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *, int, unsigned int, _QWORD **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005400`
- `0x1800100c0`
- `0x180012460`

## callees

- `0x180008f24`
- `0x180016374`
- `0x18001f048`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f09c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f09c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001f092`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18001f092`
- `logoncli!DsGetDcNameWithAccountW` at `0x18001f105`
- `logoncli!DsGetDcNameWithAccountW` at `0x18001f105`

## pseudocode

```c
__int64 __fastcall DsRolepDsGetDcForAccount(__int64 a1, __int64 a2, WCHAR *a3, int a4, unsigned int a5, _QWORD **a6)
{
  WCHAR *v7; // rsi
  DWORD LastError; // ebx
  DWORD DcNameWithAccountW; // eax
  DWORD nSize; // [rsp+40h] [rbp-78h] BYREF
  WCHAR Buffer[20]; // [rsp+48h] [rbp-70h] BYREF

  nSize = 16;
  v7 = a3;
  if ( !a3 )
  {
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      StringCchCatW(Buffer, 0x11u, L"$");
      v7 = Buffer;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError )
        return LastError;
    }
  }
  DsRolepSetCurrentOperationStatus(28720, a2, v7);
  DcNameWithAccountW = DsGetDcNameWithAccountW(a1, v7, a5, a2, 0, 0, a4, a6, nSize);
  LastError = DcNameWithAccountW;
  if ( DcNameWithAccountW == 1317 )
  {
    LastError = 1787;
  }
  else if ( !DcNameWithAccountW )
  {
    DsRolepSetCurrentOperationStatus(28673, **a6 + 4LL, a2);
    return LastError;
  }
  DsRolepLogPrintRoutine(1, "Failed to find a DC for domain %ws: %lu\n", a2, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18001f048  push    rbx
0x18001f04a  push    rbp
0x18001f04b  push    rsi
0x18001f04c  push    rdi
0x18001f04d  push    r14
0x18001f04f  push    r15
0x18001f051  sub     rsp, 88h
0x18001f058  mov     rax, cs:__security_cookie
0x18001f05f  xor     rax, rsp
0x18001f062  mov     [rsp+0B8h+var_48], rax
0x18001f067  mov     r14, [rsp+0B8h+arg_28]
0x18001f06f  mov     r15d, r9d
0x18001f072  mov     [rsp+0B8h+nSize], 10h
0x18001f07a  mov     rsi, r8
0x18001f07d  mov     rdi, rdx
0x18001f080  mov     rbp, rcx
0x18001f083  test    r8, r8
0x18001f086  jnz     short loc_18001F0C8
0x18001f088  lea     rdx, [rsp+0B8h+nSize]; nSize
0x18001f08d  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x18001f092  call    cs:__imp_GetComputerNameW
0x18001f098  test    eax, eax
0x18001f09a  jnz     short loc_18001F0AD
0x18001f09c  call    cs:__imp_GetLastError
0x18001f0a2  mov     ebx, eax
0x18001f0a4  test    eax, eax
0x18001f0a6  jz      short loc_18001F0C8
0x18001f0a8  jmp     loc_18001F130
0x18001f0ad  lea     r8, asc_18003AFD0; "$"
0x18001f0b4  mov     edx, 11h; cchDest
0x18001f0b9  lea     rcx, [rsp+0B8h+Buffer]; pszDest
0x18001f0be  call    StringCchCatW
0x18001f0c3  lea     rsi, [rsp+0B8h+Buffer]
0x18001f0c8  mov     r8, rsi
0x18001f0cb  mov     rdx, rdi
0x18001f0ce  mov     ecx, 7030h
0x18001f0d3  call    DsRolepSetCurrentOperationStatus
0x18001f0d8  mov     r8d, [rsp+0B8h+arg_20]
0x18001f0e0  mov     r9, rdi
0x18001f0e3  mov     [rsp+0B8h+var_80], r14
0x18001f0e8  mov     rdx, rsi
0x18001f0eb  mov     [rsp+0B8h+var_88], r15d
0x18001f0f0  mov     rcx, rbp
0x18001f0f3  mov     [rsp+0B8h+var_90], 0
0x18001f0fc  mov     [rsp+0B8h+var_98], 0
0x18001f105  call    cs:__imp_DsGetDcNameWithAccountW
0x18001f10b  mov     ebx, eax
0x18001f10d  cmp     eax, 525h
0x18001f112  jnz     short loc_18001F14F
0x18001f114  mov     ebx, 6FBh
0x18001f119  mov     r9d, ebx
0x18001f11c  lea     rdx, aFailedToFindAD_1; "Failed to find a DC for domain %ws: %lu"...
0x18001f123  mov     r8, rdi
0x18001f126  mov     ecx, 1
0x18001f12b  call    DsRolepLogPrintRoutine
0x18001f130  mov     eax, ebx
0x18001f132  mov     rcx, [rsp+0B8h+var_48]
0x18001f137  xor     rcx, rsp; StackCookie
0x18001f13a  call    __security_check_cookie
0x18001f13f  add     rsp, 88h
0x18001f146  pop     r15
0x18001f148  pop     r14
0x18001f14a  pop     rdi
0x18001f14b  pop     rsi
0x18001f14c  pop     rbp
0x18001f14d  pop     rbx
0x18001f14e  retn
0x18001f14f  test    eax, eax
0x18001f151  jnz     short loc_18001F119
0x18001f153  mov     rax, [r14]
0x18001f156  mov     r8, rdi
0x18001f159  mov     ecx, 7001h
0x18001f15e  mov     rdx, [rax]
0x18001f161  add     rdx, 4
0x18001f165  call    DsRolepSetCurrentOperationStatus
0x18001f16a  jmp     short loc_18001F130
```
