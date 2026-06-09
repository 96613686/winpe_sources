# OpenTraceFile(void)

- ea: `0x18000d874`
- end: `0x18000d98f`
- name: `?OpenTraceFile@@YAPEAU_iobuf@@XZ`
- size: `283`
- prototype: `struct _iobuf *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d998`
- `0x18000da60`

## callees

- `0x180001ae8`
- `0x18000d874`
- `0x18001280a`
- `0x180012830`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryA` at `0x18000d8ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryA` at `0x18000d8ab`
- `msvcrt!fopen` at `0x18000d966`
- `msvcrt!fopen` at `0x18000d966`

## string_xrefs

- `0x18000d917`: `\DtcInstall.log`

## pseudocode

```c
struct _iobuf *OpenTraceFile(void)
{
  UINT SystemWindowsDirectoryA; // eax
  __int64 v1; // rdx
  __int64 v2; // r8
  __int64 v3; // rax
  __int64 v4; // rdx
  CHAR *v5; // rax
  __int64 v6; // r8
  __int64 v7; // rax
  CHAR *v8; // rcx
  const char *v9; // rdx
  __int64 v10; // rbx
  CHAR *v11; // rax
  CHAR Buffer[288]; // [rsp+20h] [rbp-138h] BYREF

  memset_0(Buffer, 0, 0x118u);
  SystemWindowsDirectoryA = GetSystemWindowsDirectoryA(Buffer, 0x104u);
  if ( SystemWindowsDirectoryA - 1 > 0x102 )
    return 0;
  v3 = SystemWindowsDirectoryA - 1;
  if ( Buffer[v3] == 92 )
  {
    if ( (unsigned int)v3 >= 0x118uLL )
      _report_rangecheckfailure((unsigned int)v3, v1, v2, 0);
    Buffer[v3] = 0;
  }
  v4 = 280;
  v5 = Buffer;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = (280 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    return 0;
  v7 = 16;
  v8 = &Buffer[v6];
  v9 = "\\DtcInstall.log";
  v10 = 280 - v6;
  if ( 280 != v6 )
  {
    do
    {
      if ( !v7 )
        break;
      if ( !*v9 )
        break;
      *v8++ = *v9++;
      --v7;
      --v10;
    }
    while ( v10 );
  }
  v11 = v8 - 1;
  if ( v10 )
    v11 = v8;
  *v11 = 0;
  if ( !v10 )
    return 0;
  Buffer[279] = 0;
  return fopen(Buffer, "a+");
}

```

## disassembly

```asm
0x18000d874  push    rbx
0x18000d876  sub     rsp, 150h
0x18000d87d  mov     rax, cs:__security_cookie
0x18000d884  xor     rax, rsp
0x18000d887  mov     [rsp+158h+var_18], rax
0x18000d88f  mov     ebx, 118h
0x18000d894  lea     rcx, [rsp+158h+Buffer]; void *
0x18000d899  mov     r8d, ebx; Size
0x18000d89c  xor     edx, edx; Val
0x18000d89e  call    memset_0
0x18000d8a3  lea     edx, [rbx-14h]; uSize
0x18000d8a6  lea     rcx, [rsp+158h+Buffer]; lpBuffer
0x18000d8ab  call    cs:__imp_GetSystemWindowsDirectoryA
0x18000d8b1  lea     ecx, [rax-1]
0x18000d8b4  cmp     ecx, 102h
0x18000d8ba  ja      loc_18000D96E
0x18000d8c0  dec     eax
0x18000d8c2  xor     r9d, r9d
0x18000d8c5  mov     ecx, eax
0x18000d8c7  cmp     [rsp+rax+158h+Buffer], 5Ch ; '\'
0x18000d8cc  jnz     short loc_18000D8DC
0x18000d8ce  cmp     rcx, rbx
0x18000d8d1  jnb     loc_18000D989
0x18000d8d7  mov     [rsp+rax+158h+Buffer], r9b
0x18000d8dc  mov     rdx, rbx
0x18000d8df  lea     rax, [rsp+158h+Buffer]
0x18000d8e4  cmp     [rax], r9b
0x18000d8e7  jz      short loc_18000D8F2
0x18000d8e9  inc     rax
0x18000d8ec  sub     rdx, 1
0x18000d8f0  jnz     short loc_18000D8E4
0x18000d8f2  mov     rcx, rbx
0x18000d8f5  mov     rax, rdx
0x18000d8f8  sub     rcx, rdx
0x18000d8fb  neg     rax
0x18000d8fe  sbb     r8, r8
0x18000d901  and     r8, rcx
0x18000d904  test    rdx, rdx
0x18000d907  jz      short loc_18000D96E
0x18000d909  lea     rcx, [rsp+158h+Buffer]
0x18000d90e  mov     eax, 10h
0x18000d913  lea     rcx, [rcx+r8]
0x18000d917  lea     rdx, aDtcinstallLog; "\\DtcInstall.log"
0x18000d91e  sub     rbx, r8
0x18000d921  jz      short loc_18000D942
0x18000d923  test    rax, rax
0x18000d926  jz      short loc_18000D942
0x18000d928  mov     r8b, [rdx]
0x18000d92b  test    r8b, r8b
0x18000d92e  jz      short loc_18000D942
0x18000d930  mov     [rcx], r8b
0x18000d933  inc     rdx
0x18000d936  inc     rcx
0x18000d939  dec     rax
0x18000d93c  sub     rbx, 1
0x18000d940  jnz     short loc_18000D923
0x18000d942  test    rbx, rbx
0x18000d945  lea     rax, [rcx-1]
0x18000d949  cmovnz  rax, rcx
0x18000d94d  mov     [rax], r9b
0x18000d950  jz      short loc_18000D96E
0x18000d952  lea     rdx, Mode; "a+"
0x18000d959  mov     [rsp+158h+var_21], r9b
0x18000d961  lea     rcx, [rsp+158h+Buffer]; FileName
0x18000d966  call    cs:__imp_fopen
0x18000d96c  jmp     short loc_18000D970
0x18000d96e  xor     eax, eax
0x18000d970  mov     rcx, [rsp+158h+var_18]
0x18000d978  xor     rcx, rsp; StackCookie
0x18000d97b  call    __security_check_cookie
0x18000d980  add     rsp, 150h
0x18000d987  pop     rbx
0x18000d988  retn
0x18000d989  call    __report_rangecheckfailure
```
