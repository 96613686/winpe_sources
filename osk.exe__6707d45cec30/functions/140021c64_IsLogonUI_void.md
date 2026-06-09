# IsLogonUI(void)

- ea: `0x140021c64`
- end: `0x140021d04`
- name: `?IsLogonUI@@YA_NXZ`
- size: `160`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140021c20`

## callees

- `0x140021c64`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140021c7b`
- `KERNEL32!GetCurrentThreadId` at `0x140021c7b`
- `USER32!GetThreadDesktop` at `0x140021c83`
- `USER32!GetThreadDesktop` at `0x140021c83`
- `USER32!GetUserObjectInformationW` at `0x140021cc1`
- `USER32!GetUserObjectInformationW` at `0x140021cc1`
- `msvcrt!_wcsicmp` at `0x140021cdc`
- `msvcrt!_wcsicmp` at `0x140021cdc`

## pseudocode

```c
char IsLogonUI(void)
{
  char v0; // bl
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  wchar_t String2[12]; // [rsp+30h] [rbp-48h] BYREF
  wchar_t pvInfo[12]; // [rsp+48h] [rbp-30h] BYREF

  v0 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop )
  {
    wcscpy(String2, L"Winlogon");
    if ( GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0) )
    {
      pvInfo[8] = 0;
      return _wcsicmp(pvInfo, String2) == 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x140021c64  push    rbx
0x140021c66  sub     rsp, 70h
0x140021c6a  mov     rax, cs:__security_cookie
0x140021c71  xor     rax, rsp
0x140021c74  mov     [rsp+78h+var_18], rax
0x140021c79  xor     bl, bl
0x140021c7b  call    cs:__imp_GetCurrentThreadId
0x140021c81  mov     ecx, eax; dwThreadId
0x140021c83  call    cs:__imp_GetThreadDesktop
0x140021c89  test    rax, rax
0x140021c8c  jz      short loc_140021CEF
0x140021c8e  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x140021c95  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x140021c9a  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x140021ca1  mov     r9d, 12h; nLength
0x140021ca7  mov     [rsp+78h+var_38], cx
0x140021cac  mov     rcx, rax; hObj
0x140021caf  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x140021cb8  movups  xmmword ptr [rsp+78h+String2], xmm0
0x140021cbd  lea     edx, [r9-10h]; nIndex
0x140021cc1  call    cs:__imp_GetUserObjectInformationW
0x140021cc7  test    eax, eax
0x140021cc9  jz      short loc_140021CEF
0x140021ccb  xor     ecx, ecx
0x140021ccd  lea     rdx, [rsp+78h+String2]; String2
0x140021cd2  mov     [rsp+78h+var_20], cx
0x140021cd7  lea     rcx, [rsp+78h+pvInfo]; String1
0x140021cdc  call    cs:__imp__wcsicmp
0x140021ce2  movzx   ebx, bl
0x140021ce5  mov     ecx, 1
0x140021cea  test    eax, eax
0x140021cec  cmovz   ebx, ecx
0x140021cef  mov     al, bl
0x140021cf1  mov     rcx, [rsp+78h+var_18]
0x140021cf6  xor     rcx, rsp; StackCookie
0x140021cf9  call    __security_check_cookie
0x140021cfe  add     rsp, 70h
0x140021d02  pop     rbx
0x140021d03  retn
```
