# DSLogger::LogError(ushort const *,ulong,ushort const *,...)

- ea: `0x18000bf80`
- end: `0x18000c038`
- name: `?LogError@DSLogger@@QEAAXPEBGK0ZZ`
- size: `184`
- prototype: `void(DSLogger *this, const unsigned __int16 *, int, const unsigned __int16 *, ...)`
- caller_count: `90`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800047f4`
- `0x180005508`
- `0x180007220`
- `0x180007300`
- `0x180007440`
- `0x180007530`
- `0x1800075e0`
- `0x1800076f0`
- `0x180007800`
- `0x180007870`
- `0x1800083c0`
- `0x18000b700`
- `0x18000bc50`
- `0x18000ca4c`
- `0x18000ceb4`
- `0x18000cfcc`
- `0x18000d0d0`
- `0x18000d21c`
- `0x18000d3e4`
- `0x18000d68c`
- `0x18000d7b8`
- `0x18000da68`
- `0x18000e020`
- `0x18000e2b0`
- `0x18000e364`
- `0x18000f068`
- `0x18000f740`
- `0x18000fcd4`
- `0x18000fd9c`
- `0x180010220`
- `0x1800102d8`
- `0x180010500`
- `0x1800107c4`
- `0x1800109d8`
- `0x1800111c0`
- `0x18001182c`
- `0x180011914`
- `0x180011a78`
- `0x180011b38`
- `0x180011bdc`
- `0x180011c64`
- `0x180011d20`
- `0x180011fc0`
- `0x1800120ac`
- `0x180012274`
- `0x180012310`
- `0x1800124b0`
- `0x1800125c4`
- `0x180012748`
- `0x1800129fc`

## callees

- `0x18000664c`
- `0x18000bf80`
- `0x18000c46c`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bff7`

## pseudocode

```c
void DSLogger::LogError(DSLogger *this, const unsigned __int16 *a2, int a3, const unsigned __int16 *a4, ...)
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
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 2) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0zqqz_EventWriteTransfer(
        (unsigned int)v8,
        (unsigned int)DSErrorEventLocationErrorMessage,
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
0x18000bf80  mov     [rsp+arg_18], r9
0x18000bf85  push    rbx
0x18000bf86  push    rsi
0x18000bf87  push    rdi
0x18000bf88  sub     rsp, 450h
0x18000bf8f  mov     rax, cs:__security_cookie
0x18000bf96  xor     rax, rsp
0x18000bf99  mov     [rsp+468h+var_28], rax
0x18000bfa1  cmp     dword ptr [rcx], 0
0x18000bfa4  mov     rbx, r9
0x18000bfa7  mov     esi, r8d
0x18000bfaa  mov     rdi, rdx
0x18000bfad  jz      short loc_18000C01D
0x18000bfaf  xor     edx, edx; Val
0x18000bfb1  lea     rcx, [rsp+468h+var_428]; void *
0x18000bfb6  mov     r8d, 400h; Size
0x18000bfbc  call    memset_0
0x18000bfc1  lea     r9, [rsp+468h+arg_20]; char *
0x18000bfc9  mov     [rsp+468h+var_438], 0
0x18000bfd2  mov     r8, rbx; unsigned __int16 *
0x18000bfd5  lea     rcx, [rsp+468h+var_428]; unsigned __int16 *
0x18000bfda  mov     edx, 200h; unsigned __int64
0x18000bfdf  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000bfe4  xor     eax, eax
0x18000bfe6  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 2
0x18000bfed  mov     [rsp+468h+var_2A], ax
0x18000bff5  jz      short loc_18000C01D
0x18000bff7  call    cs:__imp_GetCurrentThreadId
0x18000bffd  lea     rcx, [rsp+468h+var_428]
0x18000c002  mov     r9d, esi
0x18000c005  mov     [rsp+468h+var_440], rcx
0x18000c00a  lea     rdx, DSErrorEventLocationErrorMessage
0x18000c011  mov     r8, rdi
0x18000c014  mov     [rsp+468h+var_448], eax
0x18000c018  call    McTemplateU0zqqz_EventWriteTransfer
0x18000c01d  mov     rcx, [rsp+468h+var_28]
0x18000c025  xor     rcx, rsp; StackCookie
0x18000c028  call    __security_check_cookie
0x18000c02d  add     rsp, 450h
0x18000c034  pop     rdi
0x18000c035  pop     rsi
0x18000c036  pop     rbx
0x18000c037  retn
```
