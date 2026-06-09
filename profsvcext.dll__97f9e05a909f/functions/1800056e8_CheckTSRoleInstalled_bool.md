# CheckTSRoleInstalled(bool &)

- ea: `0x1800056e8`
- end: `0x18000577f`
- name: `?CheckTSRoleInstalled@@YAJAEA_N@Z`
- size: `151`
- prototype: `signed int __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180015f30`

## callees

- `0x1800056e8`
- `0x18000a520`
- `0x18000aef8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005754`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005754`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180005725`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180005725`

## pseudocode

```c
signed int __fastcall CheckTSRoleInstalled(bool *a1)
{
  signed int result; // eax
  bool v3; // cl
  struct _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF
  __int16 v5; // [rsp+138h] [rbp-20h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    result = 0;
    v3 = (v5 & 0x10) != 0 && (v5 & 0x100) == 0;
    *a1 = v3;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800056e8  push    rbx
0x1800056ea  sub     rsp, 150h
0x1800056f1  mov     rax, cs:__security_cookie
0x1800056f8  xor     rax, rsp
0x1800056fb  mov     [rsp+158h+var_18], rax
0x180005703  mov     rbx, rcx
0x180005706  xor     edx, edx; Val
0x180005708  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x18000570d  mov     r8d, 118h; Size
0x180005713  call    memset_0
0x180005718  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x18000571d  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180005725  call    cs:__imp_GetVersionExW
0x18000572b  test    eax, eax
0x18000572d  jz      short loc_180005754
0x18000572f  xor     eax, eax
0x180005731  test    byte ptr [rsp+158h+var_20], 10h
0x180005739  jz      short loc_18000574E
0x18000573b  mov     ecx, 100h
0x180005740  test    [rsp+158h+var_20], cx
0x180005748  jnz     short loc_18000574E
0x18000574a  mov     cl, 1
0x18000574c  jmp     short loc_180005750
0x18000574e  xor     cl, cl
0x180005750  mov     [rbx], cl
0x180005752  jmp     short loc_180005766
0x180005754  call    cs:__imp_GetLastError
0x18000575a  test    eax, eax
0x18000575c  jle     short loc_180005766
0x18000575e  movzx   eax, ax
0x180005761  or      eax, 80070000h
0x180005766  mov     rcx, [rsp+158h+var_18]
0x18000576e  xor     rcx, rsp; StackCookie
0x180005771  call    __security_check_cookie
0x180005776  add     rsp, 150h
0x18000577d  pop     rbx
0x18000577e  retn
```
