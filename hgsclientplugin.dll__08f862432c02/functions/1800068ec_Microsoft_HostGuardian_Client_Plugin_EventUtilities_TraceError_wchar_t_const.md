# Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(wchar_t const *,...)

- ea: `0x1800068ec`
- end: `0x1800069f4`
- name: `?TraceError@EventUtilities@Plugin@Client@HostGuardian@Microsoft@@YAXPEB_WZZ`
- size: `264`
- prototype: `void(wchar_t *Format, const wchar_t *, __int64, __int64, ...)`
- caller_count: `7`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800069fc`
- `0x180006b00`
- `0x180007a10`
- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`
- `0x18000a070`

## callees

- `0x180001520`
- `0x180001f9e`
- `0x180001fb8`
- `0x1800068ec`
- `0x180006d00`

## pseudocode

```c
void Microsoft::HostGuardian::Client::Plugin::EventUtilities::TraceError(
        wchar_t *Format,
        const wchar_t *a2,
        __int64 a3,
        __int64 a4,
        ...)
{
  unsigned int v5; // eax
  wchar_t *p_Buffer; // rcx
  int v7; // r8d
  int v8; // r9d
  __int64 v9; // rax
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t *v11; // [rsp+50h] [rbp-B8h]
  __int64 v12; // [rsp+58h] [rbp-B0h]
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
    if ( (Microsoft_Windows_HostGuardianService_ClientEnableBits & 4) == 0 )
      return;
    v12 = 42;
    v11 = L"Event format failed.";
    goto LABEL_10;
  }
  if ( v5 == 254 )
    v15 = 0;
  if ( (Microsoft_Windows_HostGuardianService_ClientEnableBits & 4) != 0 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)&v14[2 * v9 - 2] );
    p_Buffer = &Buffer;
    v12 = (unsigned int)(2 * v9 + 2);
    v11 = &Buffer;
LABEL_10:
    McGenEventWrite_EventWriteTransfer((int)p_Buffer, (int)&CommonDebugError, v7, v8, &v10);
  }
}

```

## disassembly

```asm
0x1800068ec  mov     rax, rsp
0x1800068ef  mov     [rax+8], rcx
0x1800068f3  mov     [rax+10h], rdx
0x1800068f7  mov     [rax+18h], r8
0x1800068fb  mov     [rax+20h], r9
0x1800068ff  push    rbp
0x180006900  push    rbx
0x180006901  push    rdi
0x180006902  lea     rbp, [rax-188h]
0x180006909  sub     rsp, 270h
0x180006910  mov     rax, cs:__security_cookie
0x180006917  xor     rax, rsp
0x18000691a  mov     [rbp+180h+var_20], rax
0x180006921  mov     rbx, rcx
0x180006924  xor     edi, edi
0x180006926  lea     rcx, [rsp+280h+var_21E]; void *
0x18000692b  mov     [rsp+280h+Buffer], di
0x180006930  xor     edx, edx; Val
0x180006932  mov     r8d, 1FCh; Size
0x180006938  call    memset_0
0x18000693d  mov     r8, rbx; Format
0x180006940  lea     r9, [rbp+180h+Args]; Args
0x180006947  mov     ebx, 0FEh
0x18000694c  lea     rcx, [rsp+280h+Buffer]; Buffer
0x180006951  mov     edx, ebx; BufferCount
0x180006953  call    _vsnwprintf
0x180006958  test    eax, eax
0x18000695a  js      short loc_18000699F
0x18000695c  cmp     eax, ebx
0x18000695e  ja      short loc_18000699F
0x180006960  jnz     short loc_180006969
0x180006962  mov     [rbp+180h+var_24], di
0x180006969  test    cs:Microsoft_Windows_HostGuardianService_ClientEnableBits, 4
0x180006970  jz      short loc_1800069DA
0x180006972  lea     rcx, [rsp+280h+Buffer]
0x180006977  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000697b  inc     rax
0x18000697e  cmp     [rcx+rax*2], di
0x180006982  jnz     short loc_18000697B
0x180006984  lea     eax, ds:2[rax*2]
0x18000698b  mov     dword ptr [rsp+280h+var_230+4], edi
0x18000698f  lea     rcx, [rsp+280h+Buffer]
0x180006994  mov     dword ptr [rsp+280h+var_230], eax
0x180006998  mov     [rsp+280h+var_238], rcx
0x18000699d  jmp     short loc_1800069C4
0x18000699f  test    cs:Microsoft_Windows_HostGuardianService_ClientEnableBits, 4
0x1800069a6  mov     [rbp+180h+var_24], di
0x1800069ad  jz      short loc_1800069DA
0x1800069af  lea     rax, aEventFormatFai_0; "Event format failed."
0x1800069b6  mov     [rsp+280h+var_230], 2Ah ; '*'
0x1800069bf  mov     [rsp+280h+var_238], rax
0x1800069c4  lea     rax, [rsp+280h+var_248]
0x1800069c9  lea     rdx, CommonDebugError; int
0x1800069d0  mov     [rsp+20h], rax; PEVENT_DATA_DESCRIPTOR
0x1800069d5  call    McGenEventWrite_EventWriteTransfer
0x1800069da  mov     rcx, [rbp+180h+var_20]
0x1800069e1  xor     rcx, rsp; StackCookie
0x1800069e4  call    __security_check_cookie
0x1800069e9  add     rsp, 270h
0x1800069f0  pop     rdi
0x1800069f1  pop     rbx
0x1800069f2  pop     rbp
0x1800069f3  retn
```
