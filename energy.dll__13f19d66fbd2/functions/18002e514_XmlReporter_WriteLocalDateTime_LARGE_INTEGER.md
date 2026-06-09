# XmlReporter::WriteLocalDateTime(_LARGE_INTEGER)

- ea: `0x18002e514`
- end: `0x18002e58b`
- name: `?WriteLocalDateTime@XmlReporter@@IEAAKT_LARGE_INTEGER@@@Z`
- size: `119`
- prototype: `unsigned int __fastcall(XmlReporter *__hidden this, union _LARGE_INTEGER)`
- caller_count: `20`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001000c`
- `0x180012ac4`
- `0x180012ce4`
- `0x18002ca08`
- `0x18002d6fc`
- `0x18002dfdc`
- `0x18002e284`
- `0x180056798`
- `0x1800843b4`
- `0x1800849e0`
- `0x180085570`
- `0x180085a68`
- `0x18008abb4`
- `0x18008af14`
- `0x18008b2a4`
- `0x18008b588`
- `0x18008b8d4`
- `0x18008bcc4`
- `0x18008bf04`
- `0x18008c080`

## callees

- `0x18002e514`
- `0x18002e594`
- `0x18004ca90`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002e551`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18002e551`

## pseudocode

```c
__int64 __fastcall XmlReporter::WriteLocalDateTime(XmlReporter *this, union _LARGE_INTEGER a2)
{
  unsigned int v3; // ebx
  FILETIME FileTime; // [rsp+20h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+28h] [rbp-20h] BYREF

  FileTime = (FILETIME)a2.QuadPart;
  SystemTime = 0;
  if ( FileTimeToSystemTime(&FileTime, &SystemTime) )
  {
    v3 = 0;
    XmlReporter::WriteLocalDateTime(this, &SystemTime);
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
0x18002e514  mov     [rsp+arg_10], rbx
0x18002e519  push    rdi
0x18002e51a  sub     rsp, 40h
0x18002e51e  mov     rax, cs:__security_cookie
0x18002e525  xor     rax, rsp
0x18002e528  mov     [rsp+48h+var_10], rax
0x18002e52d  mov     rax, rdx
0x18002e530  mov     [rsp+48h+FileTime.dwLowDateTime], edx
0x18002e534  shr     rax, 20h
0x18002e538  lea     rdx, [rsp+48h+SystemTime]; lpSystemTime
0x18002e53d  mov     rdi, rcx
0x18002e540  mov     [rsp+48h+FileTime.dwHighDateTime], eax
0x18002e544  xorps   xmm0, xmm0
0x18002e547  lea     rcx, [rsp+48h+FileTime]; lpFileTime
0x18002e54c  movups  xmmword ptr [rsp+48h+SystemTime.wYear], xmm0
0x18002e551  call    cs:__imp_FileTimeToSystemTime
0x18002e557  test    eax, eax
0x18002e559  jz      short loc_18002E584
0x18002e55b  xor     ebx, ebx
0x18002e55d  lea     rdx, [rsp+48h+SystemTime]; struct _SYSTEMTIME *
0x18002e562  mov     rcx, rdi; this
0x18002e565  call    ?WriteLocalDateTime@XmlReporter@@IEAAKAEAU_SYSTEMTIME@@@Z; XmlReporter::WriteLocalDateTime(_SYSTEMTIME &)
0x18002e56a  mov     eax, ebx
0x18002e56c  mov     rcx, [rsp+48h+var_10]
0x18002e571  xor     rcx, rsp; StackCookie
0x18002e574  call    __security_check_cookie
0x18002e579  mov     rbx, [rsp+48h+arg_10]
0x18002e57e  add     rsp, 40h
0x18002e582  pop     rdi
0x18002e583  retn
0x18002e584  mov     ebx, 57h ; 'W'
0x18002e589  jmp     short loc_18002E56A
```
