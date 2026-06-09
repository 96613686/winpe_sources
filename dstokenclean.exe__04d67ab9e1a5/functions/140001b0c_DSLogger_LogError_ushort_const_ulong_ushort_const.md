# DSLogger::LogError(ushort const *,ulong,ushort const *,...)

- ea: `0x140001b0c`
- end: `0x140001bc5`
- name: `?LogError@DSLogger@@QEAAXPEBGK0ZZ`
- size: `185`
- prototype: `void(DSLogger *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400019b8`

## callees

- `0x140001b0c`
- `0x140001e5c`
- `0x140001fc9`
- `0x140001ff0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140001b6b`
- `msvcrt!_vsnwprintf` at `0x140001b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001b84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001b84`

## pseudocode

```c
void DSLogger::LogError(DSLogger *this, const unsigned __int16 *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  DWORD CurrentThreadId; // eax
  wchar_t Buffer[512]; // [rsp+40h] [rbp-428h] BYREF
  va_list Args; // [rsp+490h] [rbp+28h] BYREF

  va_start(Args, a4);
  if ( *(_DWORD *)this )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    _vsnwprintf(Buffer, 0x1FFu, a4, Args);
    Buffer[511] = 0;
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 2) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0zqqz_EventWriteTransfer(Buffer, DSErrorEventLocationErrorMessage, a2, a3, CurrentThreadId, Buffer, 0);
    }
  }
}

```

## disassembly

```asm
0x140001b0c  mov     [rsp+arg_18], r9
0x140001b11  push    rbx
0x140001b12  push    rsi
0x140001b13  push    rdi
0x140001b14  sub     rsp, 450h
0x140001b1b  mov     rax, cs:__security_cookie
0x140001b22  xor     rax, rsp
0x140001b25  mov     [rsp+468h+var_28], rax
0x140001b2d  cmp     dword ptr [rcx], 0
0x140001b30  mov     rbx, r9
0x140001b33  mov     esi, r8d
0x140001b36  mov     rdi, rdx
0x140001b39  jz      short loc_140001BAA
0x140001b3b  xor     edx, edx; Val
0x140001b3d  lea     rcx, [rsp+468h+Buffer]; void *
0x140001b42  mov     r8d, 400h; Size
0x140001b48  call    memset_0
0x140001b4d  lea     r9, [rsp+468h+Args]; Args
0x140001b55  mov     [rsp+468h+var_438], 0
0x140001b5e  mov     r8, rbx; Format
0x140001b61  lea     rcx, [rsp+468h+Buffer]; Buffer
0x140001b66  mov     edx, 1FFh; BufferCount
0x140001b6b  call    cs:__imp__vsnwprintf
0x140001b71  xor     eax, eax
0x140001b73  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 2
0x140001b7a  mov     [rsp+468h+var_2A], ax
0x140001b82  jz      short loc_140001BAA
0x140001b84  call    cs:__imp_GetCurrentThreadId
0x140001b8a  lea     rcx, [rsp+468h+Buffer]
0x140001b8f  mov     r9d, esi
0x140001b92  mov     [rsp+468h+var_440], rcx
0x140001b97  lea     rdx, DSErrorEventLocationErrorMessage
0x140001b9e  mov     r8, rdi
0x140001ba1  mov     [rsp+468h+var_448], eax
0x140001ba5  call    McTemplateU0zqqz_EventWriteTransfer
0x140001baa  mov     rcx, [rsp+468h+var_28]
0x140001bb2  xor     rcx, rsp; StackCookie
0x140001bb5  call    __security_check_cookie
0x140001bba  add     rsp, 450h
0x140001bc1  pop     rdi
0x140001bc2  pop     rsi
0x140001bc3  pop     rbx
0x140001bc4  retn
```
