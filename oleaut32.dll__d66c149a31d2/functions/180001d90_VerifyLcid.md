# VerifyLcid

- ea: `0x180001d90`
- end: `0x180001e01`
- name: `VerifyLcid`
- size: `113`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a70`
- `0x180001d10`
- `0x180052920`
- `0x180055270`

## callees

- `0x180001d90`
- `0x18004d900`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ddf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180001ddf`

## pseudocode

```c
_BOOL8 __fastcall VerifyLcid(LCID a1)
{
  WCHAR String2[8]; // [rsp+30h] [rbp-28h] BYREF

  wcscpy(String2, L"Test");
  String2[5] = 0;
  return a1 && CompareStringW(a1, 3u, String2, -1, String2, -1) == 2;
}

```

## disassembly

```asm
0x180001d90  sub     rsp, 58h
0x180001d94  mov     rax, cs:__security_cookie
0x180001d9b  xor     rax, rsp
0x180001d9e  mov     [rsp+58h+var_18], rax
0x180001da3  movsd   xmm0, qword ptr cs:aTest; "Test"
0x180001dab  mov     eax, dword ptr cs:aTest+8; ""
0x180001db1  movsd   qword ptr [rsp+58h+String2], xmm0
0x180001db7  mov     [rsp+58h+var_20], eax
0x180001dbb  test    ecx, ecx
0x180001dbd  jnz     short loc_180001DC3
0x180001dbf  xor     eax, eax
0x180001dc1  jmp     short loc_180001DEF
0x180001dc3  or      r9d, 0FFFFFFFFh; cchCount1
0x180001dc7  lea     rax, [rsp+58h+String2]
0x180001dcc  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x180001dd1  lea     r8, [rsp+58h+String2]; lpString1
0x180001dd6  mov     [rsp+58h+lpString2], rax; lpString2
0x180001ddb  lea     edx, [r9+4]; dwCmpFlags
0x180001ddf  call    cs:__imp_CompareStringW
0x180001de5  xor     ecx, ecx
0x180001de7  cmp     eax, 2
0x180001dea  setz    cl
0x180001ded  mov     eax, ecx
0x180001def  mov     rcx, [rsp+58h+var_18]
0x180001df4  xor     rcx, rsp; StackCookie
0x180001df7  call    __security_check_cookie
0x180001dfc  add     rsp, 58h
0x180001e00  retn
```
