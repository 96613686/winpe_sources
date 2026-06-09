# GmsapIsSameFileTime(_FILETIME const *,_FILETIME const *)

- ea: `0x180004318`
- end: `0x1800043ea`
- name: `?GmsapIsSameFileTime@@YAHPEBU_FILETIME@@0@Z`
- size: `210`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1, FILETIME *lpFileTime2)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e84`
- `0x180005018`

## callees

- `0x180001400`
- `0x180004318`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800043b8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800043b8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004350`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004367`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004350`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180004367`

## pseudocode

```c
_BOOL8 __fastcall GmsapIsSameFileTime(FILETIME *lpFileTime1, FILETIME *lpFileTime2)
{
  struct _SYSTEMTIME v5; // [rsp+20h] [rbp-30h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-20h] BYREF

  SystemTime = 0;
  v5 = 0;
  if ( !FileTimeToSystemTime(lpFileTime1, &SystemTime) || !FileTimeToSystemTime(lpFileTime2, &v5) )
    return CompareFileTime(lpFileTime1, lpFileTime2) == 0;
  if ( SystemTime.wYear == v5.wYear
    && SystemTime.wMonth == v5.wMonth
    && SystemTime.wDay == v5.wDay
    && SystemTime.wHour == v5.wHour )
  {
    return SystemTime.wMinute == v5.wMinute;
  }
  return 0;
}

```

## disassembly

```asm
0x180004318  mov     [rsp-8+arg_10], rbx
0x18000431d  mov     [rsp-8+arg_18], rdi
0x180004322  push    rbp
0x180004323  mov     rbp, rsp
0x180004326  sub     rsp, 50h
0x18000432a  mov     rax, cs:__security_cookie
0x180004331  xor     rax, rsp
0x180004334  mov     [rbp+var_10], rax
0x180004338  mov     rbx, rdx
0x18000433b  xorps   xmm0, xmm0
0x18000433e  xorps   xmm1, xmm1
0x180004341  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180004345  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180004349  mov     rdi, rcx
0x18000434c  movups  xmmword ptr [rbp+var_30.wYear], xmm1
0x180004350  call    cs:__imp_FileTimeToSystemTime
0x180004357  nop     dword ptr [rax+rax+00h]
0x18000435c  test    eax, eax
0x18000435e  jz      short loc_1800043B2
0x180004360  lea     rdx, [rbp+var_30]; lpSystemTime
0x180004364  mov     rcx, rbx; lpFileTime
0x180004367  call    cs:__imp_FileTimeToSystemTime
0x18000436e  nop     dword ptr [rax+rax+00h]
0x180004373  test    eax, eax
0x180004375  jz      short loc_1800043B2
0x180004377  movzx   eax, [rbp+var_30.wYear]
0x18000437b  cmp     [rbp+SystemTime.wYear], ax
0x18000437f  jnz     short loc_1800043AE
0x180004381  movzx   eax, [rbp+var_30.wMonth]
0x180004385  cmp     [rbp+SystemTime.wMonth], ax
0x180004389  jnz     short loc_1800043AE
0x18000438b  movzx   eax, [rbp+var_30.wDay]
0x18000438f  cmp     [rbp+SystemTime.wDay], ax
0x180004393  jnz     short loc_1800043AE
0x180004395  movzx   eax, [rbp+var_30.wHour]
0x180004399  cmp     [rbp+SystemTime.wHour], ax
0x18000439d  jnz     short loc_1800043AE
0x18000439f  movzx   ecx, [rbp+var_30.wMinute]
0x1800043a3  xor     eax, eax
0x1800043a5  cmp     [rbp+SystemTime.wMinute], cx
0x1800043a9  setz    al
0x1800043ac  jmp     short loc_1800043CD
0x1800043ae  xor     eax, eax
0x1800043b0  jmp     short loc_1800043CD
0x1800043b2  mov     rdx, rbx; lpFileTime2
0x1800043b5  mov     rcx, rdi; lpFileTime1
0x1800043b8  call    cs:__imp_CompareFileTime
0x1800043bf  nop     dword ptr [rax+rax+00h]
0x1800043c4  xor     ecx, ecx
0x1800043c6  test    eax, eax
0x1800043c8  setz    cl
0x1800043cb  mov     eax, ecx
0x1800043cd  mov     rcx, [rbp+var_10]
0x1800043d1  xor     rcx, rsp; StackCookie
0x1800043d4  call    __security_check_cookie
0x1800043d9  mov     rbx, [rsp+50h+arg_10]
0x1800043de  mov     rdi, [rsp+50h+arg_18]
0x1800043e3  add     rsp, 50h
0x1800043e7  pop     rbp
0x1800043e8  retn
```
