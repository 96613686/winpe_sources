# Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(wchar_t const *,...)

- ea: `0x180006b00`
- end: `0x180006bfb`
- name: `?TraceWarning@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ`
- size: `251`
- prototype: `void(wchar_t *Format, const wchar_t *, __int64, __int64, ...)`
- caller_count: `5`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800064cc`
- `0x1800065c0`
- `0x1800085ec`
- `0x1800087e0`
- `0x1800088cc`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180001fb8`
- `0x1800068ec`
- `0x180006b00`
- `0x180006d00`

## pseudocode

```c
void Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceWarning(
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
    if ( (Microsoft_Windows_HostGuardianService_ClientEnableBits & 2) != 0 )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v14[2 * v8 - 2] );
      v12 = 0;
      v11 = 2 * v8 + 2;
      p_Buffer = &Buffer;
      McGenEventWrite_EventWriteTransfer((int)&Buffer, (int)&CommonDebugWarning, v6, v7, &v9);
    }
  }
}

```

## disassembly

```asm
0x180006b00  mov     rax, rsp
0x180006b03  mov     [rax+8], rcx
0x180006b07  mov     [rax+10h], rdx
0x180006b0b  mov     [rax+18h], r8
0x180006b0f  mov     [rax+20h], r9
0x180006b13  push    rbp
0x180006b14  push    rbx
0x180006b15  push    rdi
0x180006b16  lea     rbp, [rax-188h]
0x180006b1d  sub     rsp, 270h
0x180006b24  mov     rax, cs:__security_cookie
0x180006b2b  xor     rax, rsp
0x180006b2e  mov     [rbp+180h+var_20], rax
0x180006b35  mov     rbx, rcx
0x180006b38  xor     edi, edi
0x180006b3a  lea     rcx, [rsp+280h+var_21E]; void *
0x180006b3f  mov     [rsp+280h+Buffer], di
0x180006b44  xor     edx, edx; Val
0x180006b46  mov     r8d, 1FCh; Size
0x180006b4c  call    memset_0
0x180006b51  mov     r8, rbx; Format
0x180006b54  lea     r9, [rbp+180h+Args]; Args
0x180006b5b  mov     ebx, 0FEh
0x180006b60  lea     rcx, [rsp+280h+Buffer]; Buffer
0x180006b65  mov     edx, ebx; BufferCount
0x180006b67  call    _vsnwprintf
0x180006b6c  test    eax, eax
0x180006b6e  js      short loc_180006BC9
0x180006b70  cmp     eax, ebx
0x180006b72  ja      short loc_180006BC9
0x180006b74  jnz     short loc_180006B7D
0x180006b76  mov     [rbp+180h+var_24], di
0x180006b7d  test    cs:Microsoft_Windows_HostGuardianService_ClientEnableBits, 2
0x180006b84  jz      short loc_180006BE1
0x180006b86  lea     rcx, [rsp+280h+Buffer]
0x180006b8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006b8f  inc     rax
0x180006b92  cmp     [rcx+rax*2], di
0x180006b96  jnz     short loc_180006B8F
0x180006b98  lea     eax, ds:2[rax*2]
0x180006b9f  mov     [rsp+280h+var_22C], edi
0x180006ba3  mov     [rsp+280h+var_230], eax
0x180006ba7  lea     rcx, [rsp+280h+Buffer]; int
0x180006bac  lea     rax, [rsp+280h+var_248]
0x180006bb1  mov     qword ptr [rsp+280h+var_238], rcx
0x180006bb6  lea     rdx, CommonDebugWarning; int
0x180006bbd  mov     [rsp+20h], rax; PEVENT_DATA_DESCRIPTOR
0x180006bc2  call    McGenEventWrite_EventWriteTransfer
0x180006bc7  jmp     short loc_180006BE1
0x180006bc9  mov     edx, 8007007Ah; wchar_t *
0x180006bce  mov     [rbp+180h+var_24], di
0x180006bd5  lea     rcx, aEventFormatFai; "Event format failed. (ErrorCode: 0x%08x"...
0x180006bdc  call    ?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ; Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)
0x180006be1  mov     rcx, [rbp+180h+var_20]
0x180006be8  xor     rcx, rsp; StackCookie
0x180006beb  call    __security_check_cookie
0x180006bf0  add     rsp, 270h
0x180006bf7  pop     rdi
0x180006bf8  pop     rbx
0x180006bf9  pop     rbp
0x180006bfa  retn
```
