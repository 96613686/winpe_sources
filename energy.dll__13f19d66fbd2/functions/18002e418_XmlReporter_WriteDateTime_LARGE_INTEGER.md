# XmlReporter::WriteDateTime(_LARGE_INTEGER)

- ea: `0x18002e418`
- end: `0x18002e48f`
- name: `?WriteDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z`
- size: `119`
- prototype: `unsigned int __fastcall(XmlReporter *__hidden this, union _LARGE_INTEGER)`
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001000c`
- `0x180012ce4`
- `0x18002ca08`
- `0x18002d6fc`
- `0x18002dfdc`
- `0x18002e284`
- `0x180043fbc`
- `0x180056798`
- `0x1800843b4`
- `0x1800849e0`
- `0x180085570`
- `0x180085a68`
- `0x18008af14`

## callees

- `0x18002e418`
- `0x18002e498`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002e455`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002e455`

## pseudocode

```c
__int64 __fastcall XmlReporter::WriteDateTime(XmlReporter *this, union _LARGE_INTEGER a2)
{
  unsigned int v3; // ebx
  FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  FileTime = (FILETIME)a2.QuadPart;
  SystemTime = 0;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    v3 = 0;
    XmlReporter::WriteDateTime(this, &SystemTime);
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18002e418  mov     [rsp+arg_10], rbx
0x18002e41d  push    rdi
0x18002e41e  sub     rsp, 40h
0x18002e422  mov     rax, cs:__security_cookie
0x18002e429  xor     rax, rsp
0x18002e42c  mov     [rsp+48h+var_10], rax
0x18002e431  mov     rax, rdx
0x18002e434  mov     [rsp+48h+FileTime.dwLowDateTime], edx
0x18002e438  shr     rax, 20h
0x18002e43c  lea     rdx, [rsp+48h+SystemTime]; lpSystemTime
0x18002e441  mov     rdi, rcx
0x18002e444  mov     [rsp+48h+FileTime.dwHighDateTime], eax
0x18002e448  xorps   xmm0, xmm0
0x18002e44b  lea     rcx, [rsp+48h+FileTime]; lpFileTime
0x18002e450  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x18002e455  call    cs:__imp_FileTimeToSystemTime
0x18002e45b  test    eax, eax
0x18002e45d  jz      short loc_18002E488
0x18002e45f  xor     ebx, ebx
0x18002e461  lea     rdx, [rsp+48h+SystemTime]; struct _SYSTEMTIME *
0x18002e466  mov     rcx, rdi; this
0x18002e469  call    ?WriteDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteDateTime(_SYSTEMTIME &)
0x18002e46e  mov     eax, ebx
0x18002e470  mov     rcx, [rsp+48h+var_10]
0x18002e475  xor     rcx, rsp; StackCookie
0x18002e478  call    __security_check_cookie
0x18002e47d  mov     rbx, [rsp+48h+arg_10]
0x18002e482  add     rsp, 40h
0x18002e486  pop     rdi
0x18002e487  retn
0x18002e488  mov     ebx, 57h ; 'W'
0x18002e48d  jmp     short loc_18002E46E
```
