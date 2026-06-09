# DSLogger::LogError(ushort const *,ulong,ushort const *,...)

- ea: `0x180002350`
- end: `0x180002408`
- name: `?LogError@DSLogger@@QEAAXPEBGK0ZZ`
- size: `184`
- prototype: `void(DSLogger *this, const unsigned __int16 *, int, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001290`
- `0x1800015a0`
- `0x180001810`
- `0x180002060`
- `0x1800031d0`
- `0x1800032a0`
- `0x180003380`
- `0x180003460`
- `0x180003518`

## callees

- `0x180002350`
- `0x180003674`
- `0x1800038d4`
- `0x180009922`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023c7`

## pseudocode

```c
void DSLogger::LogError(DSLogger *this, const unsigned __int16 *a2, int a3, const unsigned __int16 *a4, ...)
{
  int v6; // esi
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
0x180002350  mov     [rsp+arg_18], r9
0x180002355  push    rbx
0x180002356  push    rsi
0x180002357  push    rdi
0x180002358  sub     rsp, 450h
0x18000235f  mov     rax, cs:__security_cookie
0x180002366  xor     rax, rsp
0x180002369  mov     [rsp+468h+var_28], rax
0x180002371  cmp     dword ptr [rcx], 0
0x180002374  mov     rdi, r9
0x180002377  mov     ebx, r8d
0x18000237a  mov     rsi, rdx
0x18000237d  jz      short loc_1800023ED
0x18000237f  xor     edx, edx; Val
0x180002381  lea     rcx, [rsp+468h+var_428]; void *
0x180002386  mov     r8d, 400h; Size
0x18000238c  call    memset_0
0x180002391  lea     r9, [rsp+468h+arg_20]; char *
0x180002399  mov     [rsp+468h+var_438], 0
0x1800023a2  mov     r8, rdi; unsigned __int16 *
0x1800023a5  lea     rcx, [rsp+468h+var_428]; unsigned __int16 *
0x1800023aa  mov     edx, 200h; unsigned __int64
0x1800023af  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x1800023b4  xor     eax, eax
0x1800023b6  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 2
0x1800023bd  mov     [rsp+468h+var_2A], ax
0x1800023c5  jz      short loc_1800023ED
0x1800023c7  call    cs:__imp_GetCurrentThreadId
0x1800023cd  lea     rcx, [rsp+468h+var_428]
0x1800023d2  mov     r9d, ebx
0x1800023d5  mov     [rsp+468h+var_440], rcx
0x1800023da  lea     rdx, DSErrorEventLocationErrorMessage
0x1800023e1  mov     r8, rsi
0x1800023e4  mov     [rsp+468h+var_448], eax
0x1800023e8  call    McTemplateU0zqqz_EventWriteTransfer
0x1800023ed  mov     rcx, [rsp+468h+var_28]
0x1800023f5  xor     rcx, rsp; StackCookie
0x1800023f8  call    __security_check_cookie
0x1800023fd  add     rsp, 450h
0x180002404  pop     rdi
0x180002405  pop     rsi
0x180002406  pop     rbx
0x180002407  retn
```
