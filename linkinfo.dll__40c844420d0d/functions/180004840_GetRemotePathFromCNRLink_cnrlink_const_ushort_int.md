# GetRemotePathFromCNRLink(_cnrlink const *,ushort *,int)

- ea: `0x180004840`
- end: `0x1800048e5`
- name: `?GetRemotePathFromCNRLink@@YAXPEBU_cnrlink@@PEAGH@Z`
- size: `165`
- prototype: `void(const struct _cnrlink *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005110`

## callees

- `0x180001ae0`
- `0x180001bd0`
- `0x180004840`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004891`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004891`

## pseudocode

```c
void __fastcall GetRemotePathFromCNRLink(const struct _cnrlink *a1, unsigned __int16 *a2)
{
  const CHAR *v2; // r8
  unsigned __int16 *v4; // rbx
  WCHAR WideCharStr[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = (char *)a1 + *((unsigned int *)a1 + 2);
  if ( v2 == (char *)a1 + 20 )
  {
    v4 = WideCharStr;
    MultiByteToWideChar(0, 0, v2, -1, WideCharStr, 260);
  }
  else
  {
    v4 = (unsigned __int16 *)((char *)a1 + *((unsigned int *)a1 + 5));
  }
  StringCchCopyW(a2, 0x104u, v4);
  CatPath(a2, L"\\");
}

```

## disassembly

```asm
0x180004840  mov     [rsp+arg_10], rbx
0x180004845  push    rdi
0x180004846  sub     rsp, 250h
0x18000484d  mov     rax, cs:__security_cookie
0x180004854  xor     rax, rsp
0x180004857  mov     [rsp+258h+var_18], rax
0x18000485f  mov     r8d, [rcx+8]
0x180004863  lea     rax, [rcx+14h]
0x180004867  add     r8, rcx; lpMultiByteStr
0x18000486a  mov     rdi, rdx
0x18000486d  cmp     r8, rax
0x180004870  jnz     short loc_18000489F
0x180004872  lea     rax, [rsp+258h+WideCharStr]
0x180004877  mov     [rsp+258h+cchWideChar], 104h; cchWideChar
0x18000487f  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004883  mov     [rsp+258h+lpWideCharStr], rax; lpWideCharStr
0x180004888  xor     edx, edx; dwFlags
0x18000488a  lea     rbx, [rsp+258h+WideCharStr]
0x18000488f  xor     ecx, ecx; CodePage
0x180004891  call    cs:__imp_MultiByteToWideChar
0x180004898  nop     dword ptr [rax+rax+00h]
0x18000489d  jmp     short loc_1800048A4
0x18000489f  mov     ebx, [rax]
0x1800048a1  add     rbx, rcx
0x1800048a4  mov     r8, rbx; unsigned __int16 *
0x1800048a7  mov     edx, 104h; unsigned __int64
0x1800048ac  mov     rcx, rdi; unsigned __int16 *
0x1800048af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800048b4  lea     rdx, asc_180006504; "\\"
0x1800048bb  mov     rcx, rdi; unsigned __int16 *
0x1800048be  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x1800048c3  mov     rcx, [rsp+258h+var_18]
0x1800048cb  xor     rcx, rsp; StackCookie
0x1800048ce  call    __security_check_cookie
0x1800048d3  mov     rbx, [rsp+258h+arg_10]
0x1800048db  add     rsp, 250h
0x1800048e2  pop     rdi
0x1800048e3  retn
```
