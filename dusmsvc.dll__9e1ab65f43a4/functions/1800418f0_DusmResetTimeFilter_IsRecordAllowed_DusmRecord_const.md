# DusmResetTimeFilter::IsRecordAllowed(DusmRecord const &)

- ea: `0x1800418f0`
- end: `0x180041935`
- name: `?IsRecordAllowed@DusmResetTimeFilter@@UEBAHAEBVDusmRecord@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(DusmResetTimeFilter *__hidden this, const struct DusmRecord *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007c90`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041914`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180041914`

## pseudocode

```c
_BOOL8 __fastcall DusmResetTimeFilter::IsRecordAllowed(const FILETIME *this, FILETIME *a2)
{
  FILETIME FileTime2; // [rsp+20h] [rbp-18h] BYREF

  FileTime2 = *a2;
  return CompareFileTime(this + 1, &FileTime2) <= 0;
}

```

## disassembly

```asm
0x1800418f0  sub     rsp, 38h
0x1800418f4  mov     rax, cs:__security_cookie
0x1800418fb  xor     rax, rsp
0x1800418fe  mov     [rsp+38h+var_10], rax
0x180041903  mov     rax, [rdx]
0x180041906  add     rcx, 8; lpFileTime1
0x18004190a  lea     rdx, [rsp+38h+FileTime2]; lpFileTime2
0x18004190f  mov     qword ptr [rsp+38h+FileTime2.dwLowDateTime], rax
0x180041914  call    cs:__imp_CompareFileTime
0x18004191a  xor     ecx, ecx
0x18004191c  test    eax, eax
0x18004191e  setle   cl
0x180041921  mov     eax, ecx
0x180041923  mov     rcx, [rsp+38h+var_10]
0x180041928  xor     rcx, rsp; StackCookie
0x18004192b  call    __security_check_cookie
0x180041930  add     rsp, 38h
0x180041934  retn
```
