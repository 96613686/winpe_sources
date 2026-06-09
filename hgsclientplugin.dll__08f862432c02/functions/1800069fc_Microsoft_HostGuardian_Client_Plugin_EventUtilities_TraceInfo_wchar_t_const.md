# Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(wchar_t const *,...)

- ea: `0x1800069fc`
- end: `0x180006af7`
- name: `?TraceInfo@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ`
- size: `251`
- prototype: `void(wchar_t *Format, const wchar_t *, __int64, __int64, ...)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006060`
- `0x1800064cc`
- `0x180007a10`
- `0x1800082f0`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180001fb8`
- `0x1800068ec`
- `0x1800069fc`
- `0x180006d00`

## pseudocode

```c
void Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceInfo(
        wchar_t *Format,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        ...)
{
  unsigned int v5; // eax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t *p_Buffer; // [rsp+50h] [rbp-B8h]
  int v11; // [rsp+58h] [rbp-B0h]
  int v12; // [rsp+5Ch] [rbp-ACh]
  wchar_t Buffer; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v14[506]; // [rsp+6Ah] [rbp-9Eh] BYREF
  __int16 v15; // [rsp+264h] [rbp+15Ch]
  const wchar_t *Args; // [rsp+2A0h] [rbp+198h] BYREF

  Args = a2;
  Buffer = 0;
  memset_0(v14, 0, 0x1FCu);
  v5 = vsnwprintf(&Buffer, 0xFEu, Format, (va_list)&Args);
  if ( v5 > 0xFE )
  {
    v15 = 0;
    Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
      (wchar_t *)L"Event format failed. (ErrorCode: 0x%08x).",
      (const wchar_t *)0x8007007ALL,
      v6,
      v7);
  }
  else
  {
    if ( v5 == 254 )
      v15 = 0;
    if ( (Microsoft_Windows_HostGuardianService_ClientEnableBits & 1) != 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v14[2 * v8 - 2] );
      v12 = 0;
      v11 = 2 * v8 + 2;
      p_Buffer = &Buffer;
      McGenEventWrite_EventWriteTransfer((int)&Buffer, (int)&CommonDebugInfo, v6, v7, &v9);
    }
  }
}

```

## disassembly

```asm
0x1800069fc  mov     rax, rsp
0x1800069ff  mov     [rax+8], rcx
0x180006a03  mov     [rax+10h], rdx
0x180006a07  mov     [rax+18h], r8
0x180006a0b  mov     [rax+20h], r9
0x180006a0f  push    rbp
0x180006a10  push    rbx
0x180006a11  push    rdi
0x180006a12  lea     rbp, [rax-188h]
0x180006a19  sub     rsp, 270h
0x180006a20  mov     rax, cs:__security_cookie
0x180006a27  xor     rax, rsp
0x180006a2a  mov     [rbp+180h+var_20], rax
0x180006a31  mov     rbx, rcx
0x180006a34  xor     edi, edi
0x180006a36  lea     rcx, [rsp+280h+var_21E]; void *
0x180006a3b  mov     [rsp+280h+Buffer], di
0x180006a40  xor     edx, edx; Val
0x180006a42  mov     r8d, 1FCh; Size
0x180006a48  call    memset_0
0x180006a4d  mov     r8, rbx; Format
0x180006a50  lea     r9, [rbp+180h+Args]; Args
0x180006a57  mov     ebx, 0FEh
0x180006a5c  lea     rcx, [rsp+280h+Buffer]; Buffer
0x180006a61  mov     edx, ebx; BufferCount
0x180006a63  call    _vsnwprintf
0x180006a68  test    eax, eax
0x180006a6a  js      short loc_180006AC5
0x180006a6c  cmp     eax, ebx
0x180006a6e  ja      short loc_180006AC5
0x180006a70  jnz     short loc_180006A79
0x180006a72  mov     [rbp+180h+var_24], di
0x180006a79  test    cs:Microsoft_Windows_HostGuardianService_ClientEnableBits, 1
0x180006a80  jz      short loc_180006ADD
0x180006a82  lea     rcx, [rsp+280h+Buffer]
0x180006a87  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006a8b  inc     rax
0x180006a8e  cmp     [rcx+rax*2], di
0x180006a92  jnz     short loc_180006A8B
0x180006a94  lea     eax, ds:2[rax*2]
0x180006a9b  mov     [rsp+280h+var_22C], edi
0x180006a9f  mov     [rsp+280h+var_230], eax
0x180006aa3  lea     rcx, [rsp+280h+Buffer]; int
0x180006aa8  lea     rax, [rsp+280h+var_248]
0x180006aad  mov     qword ptr [rsp+280h+var_238], rcx
0x180006ab2  lea     rdx, CommonDebugInfo; int
0x180006ab9  mov     [rsp+20h], rax; PEVENT_DATA_DESCRIPTOR
0x180006abe  call    McGenEventWrite_EventWriteTransfer
0x180006ac3  jmp     short loc_180006ADD
0x180006ac5  mov     edx, 8007007Ah; wchar_t *
0x180006aca  mov     [rbp+180h+var_24], di
0x180006ad1  lea     rcx, aEventFormatFai; "Event format failed. (ErrorCode: 0x%08x"...
0x180006ad8  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x180006add  mov     rcx, [rbp+180h+var_20]
0x180006ae4  xor     rcx, rsp; StackCookie
0x180006ae7  call    __security_check_cookie
0x180006aec  add     rsp, 270h
0x180006af3  pop     rdi
0x180006af4  pop     rbx
0x180006af5  pop     rbp
0x180006af6  retn
```
