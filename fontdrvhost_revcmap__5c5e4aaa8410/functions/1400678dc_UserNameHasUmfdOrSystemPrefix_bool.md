# UserNameHasUmfdOrSystemPrefix(bool *)

- ea: `0x1400678dc`
- end: `0x140067a37`
- name: `?UserNameHasUmfdOrSystemPrefix@@YAJPEA_N@Z`
- size: `347`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140067a40`

## callees

- `0x1400678dc`
- `0x140075de0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400679d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400679f0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400679d8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1400679f0`
- `KERNEL32!GetProcessHeap` at `0x14006793b`
- `KERNEL32!GetProcessHeap` at `0x140067976`
- `KERNEL32!GetProcessHeap` at `0x140067a02`
- `KERNEL32!GetProcessHeap` at `0x14006793b`
- `KERNEL32!GetProcessHeap` at `0x140067976`
- `KERNEL32!GetProcessHeap` at `0x140067a02`
- `KERNEL32!HeapAlloc` at `0x140067949`
- `KERNEL32!HeapAlloc` at `0x140067949`
- `KERNEL32!GetEnvironmentVariableW` at `0x14006791f`
- `KERNEL32!GetEnvironmentVariableW` at `0x14006796c`
- `KERNEL32!GetEnvironmentVariableW` at `0x14006791f`
- `KERNEL32!GetEnvironmentVariableW` at `0x14006796c`
- `KERNEL32!HeapFree` at `0x140067984`
- `KERNEL32!HeapFree` at `0x140067a10`
- `KERNEL32!HeapFree` at `0x140067984`
- `KERNEL32!HeapFree` at `0x140067a10`

## pseudocode

```c
__int64 __fastcall UserNameHasUmfdOrSystemPrefix(bool *a1)
{
  DWORD EnvironmentVariableW; // eax
  __int64 v3; // rdi
  HANDLE ProcessHeap; // rax
  WCHAR *v6; // rax
  WCHAR *v7; // rbx
  HANDLE v8; // rax
  bool v9; // al
  HANDLE v10; // rax
  __int64 v11; // [rsp+20h] [rbp-48h] BYREF
  wchar_t v12; // [rsp+28h] [rbp-40h]
  __int64 v13; // [rsp+30h] [rbp-38h] BYREF
  int v14; // [rsp+38h] [rbp-30h]
  wchar_t v15; // [rsp+3Ch] [rbp-2Ch]
  WCHAR Name[12]; // [rsp+40h] [rbp-28h] BYREF

  wcscpy(Name, L"USERNAME");
  EnvironmentVariableW = GetEnvironmentVariableW(Name, 0, 0);
  v3 = EnvironmentVariableW;
  if ( !EnvironmentVariableW )
    return 3221225473LL;
  ProcessHeap = GetProcessHeap();
  v6 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 2 * v3);
  v7 = v6;
  if ( !v6 )
    return 3221225495LL;
  if ( GetEnvironmentVariableW(Name, v6, v3) >= (unsigned int)v3 )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, v7);
    return 3221225473LL;
  }
  v12 = aUmfd[4];
  v14 = *(_DWORD *)L"EM";
  v11 = *(_QWORD *)L"UMFD";
  v15 = aSystem[6];
  v13 = *(_QWORD *)L"SYSTEM";
  v9 = !(unsigned int)_o__wcsnicmp(v7, &v11, 4) || !(unsigned int)_o__wcsnicmp(v7, &v13, 6);
  *a1 = v9;
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v7);
  return 0;
}

```

## disassembly

```asm
0x1400678dc  mov     [rsp+arg_8], rbx
0x1400678e1  mov     [rsp+arg_10], rsi
0x1400678e6  push    rdi
0x1400678e7  sub     rsp, 60h
0x1400678eb  mov     rax, cs:__security_cookie
0x1400678f2  xor     rax, rsp
0x1400678f5  mov     [rsp+68h+var_10], rax
0x1400678fa  movups  xmm0, xmmword ptr cs:aUsername; "USERNAME"
0x140067901  movzx   eax, word ptr cs:aUsername+10h; ""
0x140067908  mov     rsi, rcx
0x14006790b  xor     r8d, r8d; nSize
0x14006790e  mov     [rsp+68h+var_18], ax
0x140067913  xor     edx, edx; lpBuffer
0x140067915  lea     rcx, [rsp+68h+Name]; lpName
0x14006791a  movups  xmmword ptr [rsp+68h+Name], xmm0
0x14006791f  call    cs:__imp_GetEnvironmentVariableW
0x140067925  mov     edi, eax
0x140067927  test    eax, eax
0x140067929  jnz     short loc_140067935
0x14006792b  mov     eax, 0C0000001h
0x140067930  jmp     loc_140067A18
0x140067935  mov     rbx, rdi
0x140067938  add     rbx, rbx
0x14006793b  call    cs:__imp_GetProcessHeap
0x140067941  mov     r8, rbx; dwBytes
0x140067944  xor     edx, edx; dwFlags
0x140067946  mov     rcx, rax; hHeap
0x140067949  call    cs:__imp_HeapAlloc
0x14006794f  mov     rbx, rax
0x140067952  test    rax, rax
0x140067955  jnz     short loc_140067961
0x140067957  mov     eax, 0C0000017h
0x14006795c  jmp     loc_140067A18
0x140067961  mov     r8d, edi; nSize
0x140067964  lea     rcx, [rsp+68h+Name]; lpName
0x140067969  mov     rdx, rbx; lpBuffer
0x14006796c  call    cs:__imp_GetEnvironmentVariableW
0x140067972  cmp     eax, edi
0x140067974  jb      short loc_14006798C
0x140067976  call    cs:__imp_GetProcessHeap
0x14006797c  mov     r8, rbx; lpMem
0x14006797f  xor     edx, edx; dwFlags
0x140067981  mov     rcx, rax; hHeap
0x140067984  call    cs:__imp_HeapFree
0x14006798a  jmp     short loc_14006792B
0x14006798c  movzx   eax, word ptr cs:aUmfd+8; ""
0x140067993  lea     rdx, [rsp+68h+var_48]
0x140067998  movsd   xmm0, qword ptr cs:aUmfd; "UMFD"
0x1400679a0  mov     r8d, 4
0x1400679a6  mov     [rsp+68h+var_40], ax
0x1400679ab  mov     rcx, rbx
0x1400679ae  mov     eax, dword ptr cs:aSystem+8; "EM"
0x1400679b4  mov     [rsp+68h+var_30], eax
0x1400679b8  movzx   eax, word ptr cs:aSystem+0Ch; ""
0x1400679bf  movsd   [rsp+68h+var_48], xmm0
0x1400679c5  movsd   xmm0, qword ptr cs:aSystem; "SYSTEM"
0x1400679cd  mov     [rsp+68h+var_2C], ax
0x1400679d2  movsd   [rsp+68h+var_38], xmm0
0x1400679d8  call    cs:__imp__o__wcsnicmp
0x1400679de  test    eax, eax
0x1400679e0  jz      short loc_1400679FE
0x1400679e2  mov     r8d, 6
0x1400679e8  lea     rdx, [rsp+68h+var_38]
0x1400679ed  mov     rcx, rbx
0x1400679f0  call    cs:__imp__o__wcsnicmp
0x1400679f6  test    eax, eax
0x1400679f8  jz      short loc_1400679FE
0x1400679fa  xor     al, al
0x1400679fc  jmp     short loc_140067A00
0x1400679fe  mov     al, 1
0x140067a00  mov     [rsi], al
0x140067a02  call    cs:__imp_GetProcessHeap
0x140067a08  mov     r8, rbx; lpMem
0x140067a0b  xor     edx, edx; dwFlags
0x140067a0d  mov     rcx, rax; hHeap
0x140067a10  call    cs:__imp_HeapFree
0x140067a16  xor     eax, eax
0x140067a18  mov     rcx, [rsp+68h+var_10]
0x140067a1d  xor     rcx, rsp; StackCookie
0x140067a20  call    __security_check_cookie
0x140067a25  lea     r11, [rsp+68h+var_8]
0x140067a2a  mov     rbx, [r11+18h]
0x140067a2e  mov     rsi, [r11+20h]
0x140067a32  mov     rsp, r11
0x140067a35  pop     rdi
0x140067a36  retn
```
