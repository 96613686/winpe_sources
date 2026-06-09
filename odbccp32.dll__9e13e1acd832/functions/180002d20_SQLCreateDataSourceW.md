# SQLCreateDataSourceW

- ea: `0x180002d20`
- end: `0x180002e0b`
- name: `SQLCreateDataSourceW`
- size: `235`
- prototype: `BOOL __stdcall(HWND hwndParent, LPCWSTR lpszDSN)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000ee10`

## callees

- `0x180001740`
- `0x18000295c`
- `0x180002d20`
- `0x180002e14`
- `0x180014aae`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002de2`
- `KERNEL32!LeaveCriticalSection` at `0x180002de2`
- `KERNEL32!EnterCriticalSection` at `0x180002d64`
- `KERNEL32!EnterCriticalSection` at `0x180002d64`

## pseudocode

```c
BOOL __stdcall SQLCreateDataSourceW(HWND hwndParent, LPCWSTR lpszDSN)
{
  __int64 v4; // r11
  unsigned __int64 v5; // rax
  int v6; // ebx
  _DWORD v8[2]; // [rsp+20h] [rbp-248h] BYREF
  HWND v9; // [rsp+28h] [rbp-240h]
  __int64 v10; // [rsp+30h] [rbp-238h]
  int v11; // [rsp+38h] [rbp-230h]
  wchar_t pszDest[262]; // [rsp+3Ch] [rbp-22Ch] BYREF
  __int64 v13; // [rsp+248h] [rbp-20h]

  v8[1] = 0;
  memset_0(v8, 0, 0x22Cu);
  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  v4 = 0;
  v9 = hwndParent;
  if ( !lpszDSN )
  {
    pszDest[0] = 0;
    goto LABEL_8;
  }
  v5 = -1;
  do
    ++v5;
  while ( lpszDSN[v5] );
  if ( v5 < 0x105 )
  {
    StringCchCopyW(pszDest, 0x105u, lpszDSN);
LABEL_8:
    v8[0] = 560;
    v10 = 4;
    v11 = 1;
    v13 = v4;
    v6 = SQLCreateDataSourceCover((__int64)v8);
    goto LABEL_9;
  }
  v6 = 0;
LABEL_9:
  LeaveCriticalSection(&g_csInstaller);
  return v6;
}

```

## disassembly

```asm
0x180002d20  mov     [rsp+arg_10], rbx
0x180002d25  push    rdi
0x180002d26  sub     rsp, 260h
0x180002d2d  mov     rax, cs:__security_cookie
0x180002d34  xor     rax, rsp
0x180002d37  mov     [rsp+268h+var_18], rax
0x180002d3f  mov     rdi, rdx
0x180002d42  mov     rbx, rcx
0x180002d45  xor     eax, eax
0x180002d47  lea     rcx, [rsp+268h+var_248]; void *
0x180002d4c  xor     edx, edx; Val
0x180002d4e  mov     [rsp+268h+var_244], eax
0x180002d52  mov     r8d, 22Ch; Size
0x180002d58  call    memset_0
0x180002d5d  lea     rcx, g_csInstaller; lpCriticalSection
0x180002d64  call    cs:__imp_EnterCriticalSection
0x180002d6a  call    FreeErrorQueue
0x180002d6f  xor     r11d, r11d
0x180002d72  mov     [rsp+268h+var_240], rbx
0x180002d77  test    rdi, rdi
0x180002d7a  jz      short loc_180002DA8
0x180002d7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002d80  inc     rax
0x180002d83  cmp     [rdi+rax*2], r11w
0x180002d88  jnz     short loc_180002D80
0x180002d8a  mov     edx, 105h; cchDest
0x180002d8f  cmp     rax, rdx
0x180002d92  jb      short loc_180002D99
0x180002d94  mov     ebx, r11d
0x180002d97  jmp     short loc_180002DDB
0x180002d99  mov     r8, rdi; pszSrc
0x180002d9c  lea     rcx, [rsp+268h+pszDest]; pszDest
0x180002da1  call    StringCchCopyW
0x180002da6  jmp     short loc_180002DAE
0x180002da8  mov     [rsp+268h+pszDest], r11w
0x180002dae  lea     rcx, [rsp+268h+var_248]
0x180002db3  mov     [rsp+268h+var_248], 230h
0x180002dbb  mov     [rsp+268h+var_238], 4
0x180002dc4  mov     [rsp+268h+var_230], 1
0x180002dcc  mov     [rsp+268h+var_20], r11
0x180002dd4  call    SQLCreateDataSourceCover
0x180002dd9  mov     ebx, eax
0x180002ddb  lea     rcx, g_csInstaller; lpCriticalSection
0x180002de2  call    cs:__imp_LeaveCriticalSection
0x180002de8  mov     eax, ebx
0x180002dea  mov     rcx, [rsp+268h+var_18]
0x180002df2  xor     rcx, rsp; StackCookie
0x180002df5  call    __security_check_cookie
0x180002dfa  mov     rbx, [rsp+268h+arg_10]
0x180002e02  add     rsp, 260h
0x180002e09  pop     rdi
0x180002e0a  retn
```
