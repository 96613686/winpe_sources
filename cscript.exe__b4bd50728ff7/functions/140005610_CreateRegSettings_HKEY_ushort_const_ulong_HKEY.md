# CreateRegSettings(HKEY__ *,ushort const *,ulong,HKEY__ * *)

- ea: `0x140005610`
- end: `0x140005759`
- name: `?CreateRegSettings@@YAJPEAUHKEY__@@PEBGKPEAPEAU1@@Z`
- size: `329`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005418`
- `0x14000d5d4`
- `0x14000f7d8`

## callees

- `0x140005610`
- `0x1400161d0`
- `0x140016200`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1400056a7`
- `KERNEL32!WideCharToMultiByte` at `0x140005703`
- `KERNEL32!WideCharToMultiByte` at `0x1400056a7`
- `KERNEL32!WideCharToMultiByte` at `0x140005703`
- `KERNEL32!GetLastError` at `0x1400056b4`
- `KERNEL32!GetLastError` at `0x1400056b4`
- `ADVAPI32!RegCreateKeyExA` at `0x140005731`
- `ADVAPI32!RegCreateKeyExA` at `0x140005731`
- `ADVAPI32!RegCreateKeyExW` at `0x140005667`
- `ADVAPI32!RegCreateKeyExW` at `0x140005667`

## pseudocode

```c
signed int __fastcall CreateRegSettings(HKEY hKey, LPCWCH lpWideCharStr, REGSAM samDesired, PHKEY phkResult)
{
  signed int result; // eax
  bool v9; // cc
  int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  void *v13; // rsp
  void *v14; // rsp
  CHAR MultiByteStr[64]; // [rsp+50h] [rbp+0h] BYREF

  if ( Global::g_fWindowsNT )
  {
    result = RegCreateKeyExW(hKey, lpWideCharStr, 0, 0, 0, samDesired, 0, phkResult, 0);
  }
  else
  {
    v10 = WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_7;
    v11 = v10 + 15LL;
    if ( v11 < v10 )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = v11 & 0xFFFFFFFFFFFFFFF0uLL;
    v13 = alloca(v12);
    v14 = alloca(v12);
    if ( !WideCharToMultiByte(0, 0, lpWideCharStr, -1, MultiByteStr, v10, 0, 0) )
    {
LABEL_7:
      result = GetLastError();
      v9 = result <= 0;
      goto LABEL_4;
    }
    result = RegCreateKeyExA(hKey, MultiByteStr, 0, 0, 0, samDesired, 0, phkResult, 0);
  }
  v9 = result <= 0;
  if ( !result )
    return 0;
LABEL_4:
  if ( !v9 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140005610  mov     r11, rsp
0x140005613  push    rbp
0x140005614  push    rbx
0x140005615  push    rsi
0x140005616  push    rdi
0x140005617  push    r12
0x140005619  push    r14
0x14000561b  push    r15
0x14000561d  sub     rsp, 60h
0x140005621  lea     rbp, [rsp+50h]
0x140005626  mov     rax, cs:__security_cookie
0x14000562d  xor     rax, rbp
0x140005630  mov     qword ptr [rbp+40h+MultiByteStr], rax
0x140005634  xor     r12d, r12d
0x140005637  mov     rdi, r9
0x14000563a  cmp     cs:?g_fWindowsNT@Global@@2_NA, r12b; bool Global::g_fWindowsNT
0x140005641  mov     esi, r8d
0x140005644  mov     rbx, rdx
0x140005647  mov     r14, rcx
0x14000564a  jz      short loc_140005688
0x14000564c  mov     [r11-58h], r12
0x140005650  mov     [r11-60h], r9
0x140005654  xor     r9d, r9d; lpClass
0x140005657  mov     [r11-68h], r12
0x14000565b  mov     [rsp+90h+samDesired], r8d; samDesired
0x140005660  xor     r8d, r8d; Reserved
0x140005663  mov     [r11-78h], r12d
0x140005667  call    cs:__imp_RegCreateKeyExW
0x14000566d  test    eax, eax
0x14000566f  jz      loc_14000573C
0x140005675  jle     loc_14000573E
0x14000567b  movzx   eax, ax
0x14000567e  or      eax, 80070000h
0x140005683  jmp     loc_14000573E
0x140005688  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x14000568d  or      r9d, 0FFFFFFFFh; cchWideChar
0x140005691  mov     [rsp+90h+lpDefaultChar], r12; lpDefaultChar
0x140005696  mov     r8, rbx; lpWideCharStr
0x140005699  mov     [rsp+90h+samDesired], r12d; cbMultiByte
0x14000569e  xor     edx, edx; dwFlags
0x1400056a0  xor     ecx, ecx; CodePage
0x1400056a2  mov     [rsp+90h+lpMultiByteStr], r12; lpMultiByteStr
0x1400056a7  call    cs:__imp_WideCharToMultiByte
0x1400056ad  movsxd  rdx, eax
0x1400056b0  test    eax, eax
0x1400056b2  jnz     short loc_1400056BE
0x1400056b4  call    cs:__imp_GetLastError
0x1400056ba  test    eax, eax
0x1400056bc  jmp     short loc_140005675
0x1400056be  lea     rcx, [rdx+0Fh]
0x1400056c2  cmp     rcx, rdx
0x1400056c5  ja      short loc_1400056D1
0x1400056c7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1400056d1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1400056d5  mov     rax, rcx
0x1400056d8  call    _alloca_probe
0x1400056dd  sub     rsp, rcx
0x1400056e0  or      r9d, 0FFFFFFFFh; cchWideChar
0x1400056e4  mov     r8, rbx; lpWideCharStr
0x1400056e7  xor     ecx, ecx; CodePage
0x1400056e9  mov     [rsp+90h+lpUsedDefaultChar], r12; lpUsedDefaultChar
0x1400056ee  lea     r15, [rsp+90h+MultiByteStr]
0x1400056f3  mov     [rsp+90h+lpDefaultChar], r12; lpDefaultChar
0x1400056f8  mov     [rsp+90h+samDesired], edx; cbMultiByte
0x1400056fc  xor     edx, edx; dwFlags
0x1400056fe  mov     [rsp+90h+lpMultiByteStr], r15; lpMultiByteStr
0x140005703  call    cs:__imp_WideCharToMultiByte
0x140005709  test    eax, eax
0x14000570b  jz      short loc_1400056B4
0x14000570d  mov     [rsp+90h+lpdwDisposition], r12; lpdwDisposition
0x140005712  xor     r9d, r9d; lpClass
0x140005715  mov     [rsp+90h+lpUsedDefaultChar], rdi; phkResult
0x14000571a  xor     r8d, r8d; Reserved
0x14000571d  mov     [rsp+90h+lpDefaultChar], r12; lpSecurityAttributes
0x140005722  mov     rdx, r15; lpSubKey
0x140005725  mov     [rsp+90h+samDesired], esi; samDesired
0x140005729  mov     rcx, r14; hKey
0x14000572c  mov     dword ptr [rsp+90h+lpMultiByteStr], r12d; dwOptions
0x140005731  call    cs:__imp_RegCreateKeyExA
0x140005737  jmp     loc_14000566D
0x14000573c  xor     eax, eax
0x14000573e  mov     rcx, qword ptr [rbp+40h+MultiByteStr]
0x140005742  xor     rcx, rbp; StackCookie
0x140005745  call    __security_check_cookie
0x14000574a  lea     rsp, [rbp+10h]
0x14000574e  pop     r15
0x140005750  pop     r14
0x140005752  pop     r12
0x140005754  pop     rdi
0x140005755  pop     rsi
0x140005756  pop     rbx
0x140005757  pop     rbp
0x140005758  retn
```
