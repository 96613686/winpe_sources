# DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)

- ea: `0x18000c040`
- end: `0x18000c0f8`
- name: `?LogInformation@DSLogger@@QEAAXPEBGK0ZZ`
- size: `184`
- prototype: `void(DSLogger *this, const unsigned __int16 *, int, const unsigned __int16 *, ...)`
- caller_count: `12`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800047f4`
- `0x180005508`
- `0x18000847c`
- `0x18000acb0`
- `0x18000d21c`
- `0x18000d860`
- `0x18000f740`
- `0x1800102d8`
- `0x180010844`
- `0x1800109d8`
- `0x180011548`
- `0x18001a498`

## callees

- `0x18000664c`
- `0x18000c040`
- `0x18000c46c`
- `0x18001b30a`
- `0x18001b340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c0b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c0b7`

## pseudocode

```c
void DSLogger::LogInformation(DSLogger *this, const unsigned __int16 *a2, int a3, const unsigned __int16 *a4, ...)
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
    if ( (Microsoft_WindowsPhone_DataSharingEnableBits & 8) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      McTemplateU0zqqz_EventWriteTransfer(
        (unsigned int)v8,
        (unsigned int)DSInformationEventLocationErrorMessage,
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
0x18000c040  mov     [rsp+arg_18], r9
0x18000c045  push    rbx
0x18000c046  push    rsi
0x18000c047  push    rdi
0x18000c048  sub     rsp, 450h
0x18000c04f  mov     rax, cs:__security_cookie
0x18000c056  xor     rax, rsp
0x18000c059  mov     [rsp+468h+var_28], rax
0x18000c061  cmp     dword ptr [rcx], 0
0x18000c064  mov     rbx, r9
0x18000c067  mov     esi, r8d
0x18000c06a  mov     rdi, rdx
0x18000c06d  jz      short loc_18000C0DD
0x18000c06f  xor     edx, edx; Val
0x18000c071  lea     rcx, [rsp+468h+var_428]; void *
0x18000c076  mov     r8d, 400h; Size
0x18000c07c  call    memset_0
0x18000c081  lea     r9, [rsp+468h+arg_20]; char *
0x18000c089  mov     [rsp+468h+var_438], 0
0x18000c092  mov     r8, rbx; unsigned __int16 *
0x18000c095  lea     rcx, [rsp+468h+var_428]; unsigned __int16 *
0x18000c09a  mov     edx, 200h; unsigned __int64
0x18000c09f  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000c0a4  xor     eax, eax
0x18000c0a6  test    cs:Microsoft_WindowsPhone_DataSharingEnableBits, 8
0x18000c0ad  mov     [rsp+468h+var_2A], ax
0x18000c0b5  jz      short loc_18000C0DD
0x18000c0b7  call    cs:__imp_GetCurrentThreadId
0x18000c0bd  lea     rcx, [rsp+468h+var_428]
0x18000c0c2  mov     r9d, esi
0x18000c0c5  mov     [rsp+468h+var_440], rcx
0x18000c0ca  lea     rdx, DSInformationEventLocationErrorMessage
0x18000c0d1  mov     r8, rdi
0x18000c0d4  mov     [rsp+468h+var_448], eax
0x18000c0d8  call    McTemplateU0zqqz_EventWriteTransfer
0x18000c0dd  mov     rcx, [rsp+468h+var_28]
0x18000c0e5  xor     rcx, rsp; StackCookie
0x18000c0e8  call    __security_check_cookie
0x18000c0ed  add     rsp, 450h
0x18000c0f4  pop     rdi
0x18000c0f5  pop     rsi
0x18000c0f6  pop     rbx
0x18000c0f7  retn
```
