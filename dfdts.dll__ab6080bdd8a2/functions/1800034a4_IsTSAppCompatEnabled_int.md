# IsTSAppCompatEnabled(int *)

- ea: `0x1800034a4`
- end: `0x180003575`
- name: `?IsTSAppCompatEnabled@@YAKPEAH@Z`
- size: `209`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180002790`

## callees

- `0x180002c90`
- `0x1800034a4`
- `0x18000833b`
- `0x180008370`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x1800034e5`
- `KERNEL32!GetVersionExW` at `0x1800034e5`
- `KERNEL32!GetLastError` at `0x1800034ef`
- `KERNEL32!GetLastError` at `0x1800034ef`

## pseudocode

```c
__int64 __fastcall IsTSAppCompatEnabled(int *a1)
{
  DWORD LastError; // ebx
  BOOL v3; // edx
  _OSVERSIONINFOW VersionInformation; // [rsp+20h] [rbp-138h] BYREF
  __int16 v6; // [rsp+138h] [rbp-20h]

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( GetVersionExW(&VersionInformation) )
  {
    LastError = 0;
    v3 = (v6 & 0x10) != 0 && (v6 & 0x100) == 0;
    *a1 = v3;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800034a4  mov     [rsp+arg_8], rbx
0x1800034a9  push    rdi
0x1800034aa  sub     rsp, 150h
0x1800034b1  mov     rax, cs:__security_cookie
0x1800034b8  xor     rax, rsp
0x1800034bb  mov     [rsp+158h+var_18], rax
0x1800034c3  mov     rdi, rcx
0x1800034c6  xor     edx, edx; Val
0x1800034c8  lea     rcx, [rsp+158h+VersionInformation.dwMajorVersion]; void *
0x1800034cd  mov     r8d, 118h; Size
0x1800034d3  call    memset_0
0x1800034d8  lea     rcx, [rsp+158h+VersionInformation]; lpVersionInformation
0x1800034dd  mov     [rsp+158h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800034e5  call    cs:__imp_GetVersionExW
0x1800034eb  test    eax, eax
0x1800034ed  jnz     short loc_18000352E
0x1800034ef  call    cs:__imp_GetLastError
0x1800034f5  mov     ebx, eax
0x1800034f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034fe  lea     rax, WPP_GLOBAL_Control
0x180003505  cmp     rcx, rax
0x180003508  jz      short loc_180003552
0x18000350a  mov     edx, 1
0x18000350f  test    [rcx+1Ch], dl
0x180003512  jz      short loc_180003552
0x180003514  mov     rcx, [rcx+10h]
0x180003518  lea     r8, WPP_0ae963c2f6a739e5a6734f4927a5ba0b_Traceguids
0x18000351f  mov     edx, 15h
0x180003524  mov     r9d, ebx
0x180003527  call    WPP_SF_d
0x18000352c  jmp     short loc_180003552
0x18000352e  xor     ebx, ebx
0x180003530  test    byte ptr [rsp+158h+var_20], 10h
0x180003538  jz      short loc_18000354E
0x18000353a  mov     eax, 100h
0x18000353f  test    [rsp+158h+var_20], ax
0x180003547  jnz     short loc_18000354E
0x180003549  lea     edx, [rbx+1]
0x18000354c  jmp     short loc_180003550
0x18000354e  xor     edx, edx
0x180003550  mov     [rdi], edx
0x180003552  mov     eax, ebx
0x180003554  mov     rcx, [rsp+158h+var_18]
0x18000355c  xor     rcx, rsp; StackCookie
0x18000355f  call    __security_check_cookie
0x180003564  mov     rbx, [rsp+158h+arg_8]
0x18000356c  add     rsp, 150h
0x180003573  pop     rdi
0x180003574  retn
```
