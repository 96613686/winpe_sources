# DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)

- ea: `0x140001bcc`
- end: `0x140001c85`
- name: `?LogInformation@DSLogger@@QEAAXPEBGK0ZZ`
- size: `185`
- prototype: `void(DSLogger *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400019b8`

## callees

- `0x140001bcc`
- `0x140001e5c`
- `0x140001fc9`
- `0x140001ff0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140001c2b`
- `msvcrt!_vsnwprintf` at `0x140001c2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001c44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001c44`

## pseudocode

```c
void DSLogger::LogInformation(
        DSLogger *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        ...)
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
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 8) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0zqqz_EventWriteTransfer(
        Buffer,
        DSInformationEventLocationErrorMessage,
        a2,
        a3,
        CurrentThreadId,
        Buffer,
        0);
    }
  }
}

```

## disassembly

```asm
0x140001bcc  mov     [rsp+arg_18], r9
0x140001bd1  push    rbx
0x140001bd2  push    rsi
0x140001bd3  push    rdi
0x140001bd4  sub     rsp, 450h
0x140001bdb  mov     rax, cs:__security_cookie
0x140001be2  xor     rax, rsp
0x140001be5  mov     [rsp+468h+var_28], rax
0x140001bed  cmp     dword ptr [rcx], 0
0x140001bf0  mov     rbx, r9
0x140001bf3  mov     esi, r8d
0x140001bf6  mov     rdi, rdx
0x140001bf9  jz      short loc_140001C6A
0x140001bfb  xor     edx, edx; Val
0x140001bfd  lea     rcx, [rsp+468h+Buffer]; void *
0x140001c02  mov     r8d, 400h; Size
0x140001c08  call    memset_0
0x140001c0d  lea     r9, [rsp+468h+Args]; Args
0x140001c15  mov     [rsp+468h+var_438], 0
0x140001c1e  mov     r8, rbx; Format
0x140001c21  lea     rcx, [rsp+468h+Buffer]; Buffer
0x140001c26  mov     edx, 1FFh; BufferCount
0x140001c2b  call    cs:__imp__vsnwprintf
0x140001c31  xor     eax, eax
0x140001c33  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 8
0x140001c3a  mov     [rsp+468h+var_2A], ax
0x140001c42  jz      short loc_140001C6A
0x140001c44  call    cs:__imp_GetCurrentThreadId
0x140001c4a  lea     rcx, [rsp+468h+Buffer]
0x140001c4f  mov     r9d, esi
0x140001c52  mov     [rsp+468h+var_440], rcx
0x140001c57  lea     rdx, DSInformationEventLocationErrorMessage
0x140001c5e  mov     r8, rdi
0x140001c61  mov     [rsp+468h+var_448], eax
0x140001c65  call    McTemplateU0zqqz_EventWriteTransfer
0x140001c6a  mov     rcx, [rsp+468h+var_28]
0x140001c72  xor     rcx, rsp; StackCookie
0x140001c75  call    __security_check_cookie
0x140001c7a  add     rsp, 450h
0x140001c81  pop     rdi
0x140001c82  pop     rsi
0x140001c83  pop     rbx
0x140001c84  retn
```
