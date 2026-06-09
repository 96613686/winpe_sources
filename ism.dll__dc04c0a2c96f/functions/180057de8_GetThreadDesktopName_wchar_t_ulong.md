# GetThreadDesktopName(wchar_t *,ulong)

- ea: `0x180057de8`
- end: `0x180057ecc`
- name: `?GetThreadDesktopName@@YAHPEA_WK@Z`
- size: `228`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180057cac`

## callees

- `0x180057de8`
- `0x180058020`
- `0x1800f0990`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057e10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057e10`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180057eaa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x180057eaa`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180057e18`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180057e18`

## pseudocode

```c
__int64 __fastcall GetThreadDesktopName(wchar_t *a1)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  __int64 v4; // rcx
  const WCHAR *v5; // r8
  __int64 v6; // rdx
  wchar_t *v7; // rcx
  __int64 result; // rax
  unsigned __int64 v9; // rdx
  DWORD nLengthNeeded[4]; // [rsp+30h] [rbp-238h] BYREF
  wchar_t pvInfo[264]; // [rsp+40h] [rbp-228h] BYREF

  nLengthNeeded[0] = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop && GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x208u, nLengthNeeded) )
  {
    StringCchCopyW(a1, v9, pvInfo);
    return 1;
  }
  else
  {
    v4 = 2147483646;
    v5 = &WindowName;
    v6 = 260;
    do
    {
      if ( !v4 )
        break;
      if ( !*v5 )
        break;
      *a1++ = *v5++;
      --v4;
      --v6;
    }
    while ( v6 );
    v7 = a1 - 1;
    result = 0;
    if ( v6 )
      v7 = a1;
    *v7 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180057de8  mov     [rsp+arg_8], rbx
0x180057ded  push    rdi
0x180057dee  sub     rsp, 260h
0x180057df5  mov     rax, cs:__security_cookie
0x180057dfc  xor     rax, rsp
0x180057dff  mov     [rsp+268h+var_18], rax
0x180057e07  xor     edi, edi
0x180057e09  mov     rbx, rcx
0x180057e0c  mov     [rsp+268h+nLengthNeeded], edi
0x180057e10  call    cs:__imp_GetCurrentThreadId
0x180057e16  mov     ecx, eax; dwThreadId
0x180057e18  call    cs:__imp_GetThreadDesktop
0x180057e1e  test    rax, rax
0x180057e21  jnz     short loc_180057E8D
0x180057e23  mov     ecx, 7FFFFFFEh
0x180057e28  lea     r8, WindowName
0x180057e2f  mov     edx, 104h
0x180057e34  mov     eax, 1
0x180057e39  test    rcx, rcx
0x180057e3c  jz      short loc_180057E5C
0x180057e3e  movzx   r9d, word ptr [r8]
0x180057e42  test    r9w, r9w
0x180057e46  jz      short loc_180057E5C
0x180057e48  mov     [rbx], r9w
0x180057e4c  add     r8, 2
0x180057e50  add     rbx, 2
0x180057e54  sub     rcx, rax
0x180057e57  sub     rdx, rax
0x180057e5a  jnz     short loc_180057E39
0x180057e5c  test    rdx, rdx
0x180057e5f  lea     rcx, [rbx-2]
0x180057e63  mov     eax, edi
0x180057e65  cmovnz  rcx, rbx
0x180057e69  mov     [rcx], di
0x180057e6c  mov     rcx, [rsp+268h+var_18]
0x180057e74  xor     rcx, rsp; StackCookie
0x180057e77  call    __security_check_cookie
0x180057e7c  mov     rbx, [rsp+268h+arg_8]
0x180057e84  add     rsp, 260h
0x180057e8b  pop     rdi
0x180057e8c  retn
0x180057e8d  lea     rcx, [rsp+268h+nLengthNeeded]
0x180057e92  mov     r9d, 208h; nLength
0x180057e98  mov     [rsp+268h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180057e9d  lea     r8, [rsp+268h+pvInfo]; pvInfo
0x180057ea2  mov     rcx, rax; hObj
0x180057ea5  mov     edx, 2; nIndex
0x180057eaa  call    cs:__imp_GetUserObjectInformationW
0x180057eb0  test    eax, eax
0x180057eb2  jz      loc_180057E23
0x180057eb8  lea     r8, [rsp+268h+pvInfo]; wchar_t *
0x180057ebd  mov     rcx, rbx; wchar_t *
0x180057ec0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180057ec5  mov     eax, 1
0x180057eca  jmp     short loc_180057E6C
```
