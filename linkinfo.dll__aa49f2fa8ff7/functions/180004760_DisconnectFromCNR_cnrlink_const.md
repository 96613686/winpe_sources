# DisconnectFromCNR(_cnrlink const *)

- ea: `0x180004760`
- end: `0x1800047f6`
- name: `?DisconnectFromCNR@@YAHPEBU_cnrlink@@@Z`
- size: `150`
- prototype: `_BOOL8 __fastcall(const struct _cnrlink *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005550`

## callees

- `0x180004760`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800047aa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800047aa`
- `MPR!WNetCancelConnection2W` at `0x1800047c7`
- `MPR!WNetCancelConnection2W` at `0x1800047c7`

## pseudocode

```c
_BOOL8 __fastcall DisconnectFromCNR(const struct _cnrlink *a1)
{
  const CHAR *v1; // r8
  WCHAR *v2; // rbx
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-228h] BYREF

  v1 = (char *)a1 + *((unsigned int *)a1 + 2);
  if ( v1 == (char *)a1 + 20 )
  {
    v2 = WideCharStr;
    MultiByteToWideChar(0, 0, v1, -1, WideCharStr, 260);
  }
  else
  {
    v2 = (WCHAR *)((char *)a1 + *((unsigned int *)a1 + 5));
  }
  return WNetCancelConnection2W(v2, 0x40u, 0) == 0;
}

```

## disassembly

```asm
0x180004760  push    rbx
0x180004762  sub     rsp, 250h
0x180004769  mov     rax, cs:__security_cookie
0x180004770  xor     rax, rsp
0x180004773  mov     [rsp+258h+var_18], rax
0x18000477b  mov     r8d, [rcx+8]
0x18000477f  lea     rax, [rcx+14h]
0x180004783  add     r8, rcx; lpMultiByteStr
0x180004786  cmp     r8, rax
0x180004789  jnz     short loc_1800047B8
0x18000478b  lea     rax, [rsp+258h+WideCharStr]
0x180004790  mov     [rsp+258h+cchWideChar], 104h; cchWideChar
0x180004798  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18000479c  mov     [rsp+258h+lpWideCharStr], rax; lpWideCharStr
0x1800047a1  xor     edx, edx; dwFlags
0x1800047a3  lea     rbx, [rsp+258h+WideCharStr]
0x1800047a8  xor     ecx, ecx; CodePage
0x1800047aa  call    cs:__imp_MultiByteToWideChar
0x1800047b1  nop     dword ptr [rax+rax+00h]
0x1800047b6  jmp     short loc_1800047BD
0x1800047b8  mov     ebx, [rax]
0x1800047ba  add     rbx, rcx
0x1800047bd  xor     r8d, r8d; fForce
0x1800047c0  mov     rcx, rbx; lpName
0x1800047c3  lea     edx, [r8+40h]; dwFlags
0x1800047c7  call    cs:__imp_WNetCancelConnection2W
0x1800047ce  nop     dword ptr [rax+rax+00h]
0x1800047d3  xor     ecx, ecx
0x1800047d5  test    eax, eax
0x1800047d7  setz    cl
0x1800047da  mov     eax, ecx
0x1800047dc  mov     rcx, [rsp+258h+var_18]
0x1800047e4  xor     rcx, rsp; StackCookie
0x1800047e7  call    __security_check_cookie
0x1800047ec  add     rsp, 250h
0x1800047f3  pop     rbx
0x1800047f4  retn
```
