# CCrashOnLaunch::NotifyPCA(wchar_t const *,ulong,unsigned __int64,unsigned __int64)

- ea: `0x180030aac`
- end: `0x180030b78`
- name: `?NotifyPCA@CCrashOnLaunch@@AEAAKPEB_WK_K1@Z`
- size: `204`
- prototype: `__int64(CCrashOnLaunch *this, const wchar_t *, int, __int64, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180030950`

## callees

- `0x180002890`
- `0x180030aac`

## import_xrefs

- `ntdll!EtwEventWriteNoRegistration` at `0x180030b39`
- `ntdll!EtwEventWriteNoRegistration` at `0x180030b39`
- `ntdll!DbgPrint` at `0x180030b4e`
- `ntdll!DbgPrint` at `0x180030b4e`

## pseudocode

```c
__int64 CCrashOnLaunch::NotifyPCA(CCrashOnLaunch *this, const wchar_t *a2, int a3, __int64 a4, ...)
{
  __int64 v4; // rax
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD v8[3]; // [rsp+20h] [rbp-50h] BYREF
  int v9; // [rsp+38h] [rbp-38h]
  int v10; // [rsp+3Ch] [rbp-34h]
  __int64 *v11; // [rsp+40h] [rbp-30h]
  __int64 v12; // [rsp+48h] [rbp-28h]
  va_list v13; // [rsp+50h] [rbp-20h]
  __int64 v14; // [rsp+58h] [rbp-18h]
  int v15; // [rsp+90h] [rbp+20h] BYREF
  __int64 v16; // [rsp+98h] [rbp+28h] BYREF
  va_list va; // [rsp+A0h] [rbp+30h] BYREF

  va_start(va, a4);
  v16 = a4;
  v15 = a3;
  v8[2] = a2;
  v8[0] = &v15;
  v8[1] = 4;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v10 = 0;
  v9 = 2 * v4 + 2;
  v12 = 8;
  v11 = &v16;
  v14 = 8;
  va_copy(v13, va);
  v5 = EtwEventWriteNoRegistration(S_MICROSOFT_WINDOWS_WER_DIAG, EVENT_CRASH_ON_LAUNCH, 4, v8);
  v6 = v5;
  if ( v5 )
    DbgPrint("Cannot log ETW event, Error %d", v5);
  else
    return 0;
  return v6;
}

```

## disassembly

```asm
0x180030aac  mov     rax, rsp
0x180030aaf  mov     [rax+8], rbx
0x180030ab3  mov     [rax+10h], rdi
0x180030ab7  mov     [rax+20h], r9
0x180030abb  mov     [rax+18h], r8d
0x180030abf  push    rbp
0x180030ac0  mov     rbp, rsp
0x180030ac3  sub     rsp, 70h
0x180030ac7  mov     rax, cs:__security_cookie
0x180030ace  xor     rax, rsp
0x180030ad1  mov     [rbp+var_10], rax
0x180030ad5  lea     rax, [rbp+arg_10]
0x180030ad9  mov     [rbp+var_40], rdx
0x180030add  mov     r8d, 4
0x180030ae3  mov     [rbp+var_50], rax
0x180030ae7  xor     edi, edi
0x180030ae9  mov     [rbp+var_48], r8
0x180030aed  or      rax, 0FFFFFFFFFFFFFFFFh
0x180030af1  inc     rax
0x180030af4  cmp     [rdx+rax*2], di
0x180030af8  jnz     short loc_180030AF1
0x180030afa  lea     eax, ds:2[rax*2]
0x180030b01  mov     [rbp+var_34], edi
0x180030b04  mov     [rbp+var_38], eax
0x180030b07  lea     r9, [rbp+var_50]
0x180030b0b  lea     rax, [rbp+arg_18]
0x180030b0f  mov     [rbp+var_28], 8
0x180030b17  mov     [rbp+var_30], rax
0x180030b1b  lea     rdx, EVENT_CRASH_ON_LAUNCH
0x180030b22  lea     rax, [rbp+arg_20]
0x180030b26  mov     [rbp+var_18], 8
0x180030b2e  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG
0x180030b35  mov     [rbp+var_20], rax
0x180030b39  call    cs:__imp_EtwEventWriteNoRegistration
0x180030b3f  mov     ebx, eax
0x180030b41  test    eax, eax
0x180030b43  jz      short loc_180030B56
0x180030b45  mov     edx, eax
0x180030b47  lea     rcx, aCannotLogEtwEv; "Cannot log ETW event, Error %d"
0x180030b4e  call    cs:__imp_DbgPrint
0x180030b54  jmp     short loc_180030B58
0x180030b56  mov     ebx, edi
0x180030b58  mov     eax, ebx
0x180030b5a  mov     rcx, [rbp+var_10]
0x180030b5e  xor     rcx, rsp; StackCookie
0x180030b61  call    __security_check_cookie
0x180030b66  lea     r11, [rsp+70h+var_s0]
0x180030b6b  mov     rbx, [r11+10h]
0x180030b6f  mov     rdi, [r11+18h]
0x180030b73  mov     rsp, r11
0x180030b76  pop     rbp
0x180030b77  retn
```
