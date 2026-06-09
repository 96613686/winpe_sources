# DSLogger::LogWarning(ushort const *,ulong,ushort const *,...)

- ea: `0x18000c158`
- end: `0x18000c210`
- name: `?LogWarning@DSLogger@@QEAAXPEBGK0ZZ`
- size: `184`
- prototype: `void(DSLogger *this, const unsigned __int16 *, int, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800105bc`
- `0x1800109d8`
- `0x180012f20`

## callees

- `0x18000664c`
- `0x18000c158`
- `0x18000c46c`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1cf`

## pseudocode

```c
void DSLogger::LogWarning(DSLogger *this, const unsigned __int16 *a2, int a3, const unsigned __int16 *a4, ...)
{
  int v6; // edi
  char CurrentThreadId; // al
  unsigned __int16 v8[512]; // [rsp+40h] [rbp-428h] BYREF
  va_list va; // [rsp+490h] [rbp+28h] BYREF

  va_start(va, a4);
  v6 = (int)a2;
  if ( *(_DWORD *)this )
  {
    memset_0(v8, 0, sizeof(v8));
    StringCchVPrintfW(v8, 0x200u, a4, va);
    v8[511] = 0;
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 4) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0zqqz_EventWriteTransfer(
        (unsigned int)v8,
        (unsigned int)DSWarningEventLocationErrorMessage,
        v6,
        a3,
        CurrentThreadId,
        (__int64)v8);
    }
  }
}

```

## disassembly

```asm
0x18000c158  mov     [rsp+arg_18], r9
0x18000c15d  push    rbx
0x18000c15e  push    rsi
0x18000c15f  push    rdi
0x18000c160  sub     rsp, 450h
0x18000c167  mov     rax, cs:__security_cookie
0x18000c16e  xor     rax, rsp
0x18000c171  mov     [rsp+468h+var_28], rax
0x18000c179  cmp     dword ptr [rcx], 0
0x18000c17c  mov     rbx, r9
0x18000c17f  mov     esi, r8d
0x18000c182  mov     rdi, rdx
0x18000c185  jz      short loc_18000C1F5
0x18000c187  xor     edx, edx; Val
0x18000c189  lea     rcx, [rsp+468h+var_428]; void *
0x18000c18e  mov     r8d, 400h; Size
0x18000c194  call    memset_0
0x18000c199  lea     r9, [rsp+468h+arg_20]; char *
0x18000c1a1  mov     [rsp+468h+var_438], 0
0x18000c1aa  mov     r8, rbx; unsigned __int16 *
0x18000c1ad  lea     rcx, [rsp+468h+var_428]; unsigned __int16 *
0x18000c1b2  mov     edx, 200h; unsigned __int64
0x18000c1b7  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000c1bc  xor     eax, eax
0x18000c1be  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 4
0x18000c1c5  mov     [rsp+468h+var_2A], ax
0x18000c1cd  jz      short loc_18000C1F5
0x18000c1cf  call    cs:__imp_GetCurrentThreadId
0x18000c1d5  lea     rcx, [rsp+468h+var_428]
0x18000c1da  mov     r9d, esi
0x18000c1dd  mov     [rsp+468h+var_440], rcx
0x18000c1e2  lea     rdx, DSWarningEventLocationErrorMessage
0x18000c1e9  mov     r8, rdi
0x18000c1ec  mov     [rsp+468h+var_448], eax
0x18000c1f0  call    McTemplateU0zqqz_EventWriteTransfer
0x18000c1f5  mov     rcx, [rsp+468h+var_28]
0x18000c1fd  xor     rcx, rsp; StackCookie
0x18000c200  call    __security_check_cookie
0x18000c205  add     rsp, 450h
0x18000c20c  pop     rdi
0x18000c20d  pop     rsi
0x18000c20e  pop     rbx
0x18000c20f  retn
```
