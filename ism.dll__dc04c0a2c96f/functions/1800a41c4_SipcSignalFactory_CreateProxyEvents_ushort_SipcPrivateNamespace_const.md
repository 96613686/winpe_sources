# SipcSignalFactory::CreateProxyEvents(ushort,SipcPrivateNamespace const &)

- ea: `0x1800a41c4`
- end: `0x1800a43aa`
- name: `?CreateProxyEvents@SipcSignalFactory@@SAJGAEBVSipcPrivateNamespace@@@Z`
- size: `486`
- prototype: `__int64 __fastcall(unsigned __int16, const struct SipcPrivateNamespace *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801433e0`

## callees

- `0x1800a41c4`
- `0x1800a43b0`
- `0x1800f08d8`
- `0x1800f0990`
- `0x1800f0e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a42c6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a42bc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a4367`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a42bc`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800a4367`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a4224`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a4224`

## pseudocode

```c
__int64 __fastcall SipcSignalFactory::CreateProxyEvents(unsigned __int16 a1, const struct SipcPrivateNamespace *a2)
{
  unsigned int v2; // esi
  signed int LastError; // eax
  unsigned int v5; // ebx
  HANDLE v7[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v9; // [rsp+260h] [rbp+160h]
  wchar_t InBuffer[264]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v11; // [rsp+480h] [rbp+380h]

  v2 = a1;
  v7[0] = CreateFileW(L"\\\\.\\XVmCtrl", 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( v7[0] == (HANDLE)-1LL )
    goto LABEL_3;
  memset_0(Buffer, 0, 0x218u);
  swprintf_s(Buffer, 0x104u, L"%4.4X_%s", v2, L"ClientSignal");
  v9 = *(_QWORD *)a2;
  Buffer[260] = 3;
  if ( !DeviceIoControl(v7[0], 0x1501FCu, Buffer, 0x218u, 0, 0, 0, 0) )
    goto LABEL_3;
  memset_0(InBuffer, 0, 0x218u);
  swprintf_s(InBuffer, 0x104u, L"%4.4X_%s", v2, L"ServerSignal");
  v11 = *(_QWORD *)a2;
  InBuffer[260] = 259;
  if ( DeviceIoControl(v7[0], 0x1501FCu, InBuffer, 0x218u, 0, 0, 0, 0) )
  {
    v5 = 0;
  }
  else
  {
LABEL_3:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = -2147418113;
    if ( LastError < 0 )
      v5 = LastError;
  }
  SipcFileHandle::Reset((SipcFileHandle *)v7);
  return v5;
}

```

## disassembly

```asm
0x1800a41c4  mov     [rsp-8+arg_10], rbx
0x1800a41c9  mov     [rsp-8+arg_18], rsi
0x1800a41ce  push    rbp
0x1800a41cf  push    rdi
0x1800a41d0  push    r12
0x1800a41d2  lea     rbp, [rsp-3A0h]
0x1800a41da  sub     rsp, 4A0h
0x1800a41e1  mov     rax, cs:__security_cookie
0x1800a41e8  xor     rax, rsp
0x1800a41eb  mov     [rbp+3B0h+var_20], rax
0x1800a41f2  xor     r9d, r9d; lpSecurityAttributes
0x1800a41f5  movzx   esi, cx
0x1800a41f8  mov     rdi, rdx
0x1800a41fb  mov     [rsp+4B0h+hTemplateFile], 0; hTemplateFile
0x1800a4204  mov     [rsp+4B0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800a420c  lea     rcx, aXvmctrl; "\\\\.\\XVmCtrl"
0x1800a4213  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a4218  mov     [rsp+4B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800a4220  lea     r8d, [r9+3]; dwShareMode
0x1800a4224  call    cs:__imp_CreateFileW
0x1800a422a  mov     [rsp+4B0h+var_470], rax
0x1800a422f  mov     rbx, rax
0x1800a4232  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a4236  jz      loc_1800A42C6
0x1800a423c  mov     r12d, 218h
0x1800a4242  lea     rcx, [rsp+4B0h+Buffer]; void *
0x1800a4247  mov     r8d, r12d; Size
0x1800a424a  xor     edx, edx; Val
0x1800a424c  call    memset_0
0x1800a4251  lea     rax, ?ClientSignalName@SipcSignalFactory@@0QBGB; "ClientSignal"
0x1800a4258  mov     r9d, esi
0x1800a425b  lea     r8, a44xS; "%4.4X_%s"
0x1800a4262  mov     qword ptr [rsp+4B0h+dwCreationDisposition], rax
0x1800a4267  mov     edx, 104h; BufferCount
0x1800a426c  lea     rcx, [rsp+4B0h+Buffer]; Buffer
0x1800a4271  call    swprintf_s
0x1800a4276  mov     rax, [rdi]
0x1800a4279  lea     r8, [rsp+4B0h+Buffer]; lpInBuffer
0x1800a427e  mov     [rsp+4B0h+lpOverlapped], 0; lpOverlapped
0x1800a4287  mov     r9d, r12d; nInBufferSize
0x1800a428a  mov     [rsp+4B0h+hTemplateFile], 0; lpBytesReturned
0x1800a4293  mov     edx, 1501FCh; dwIoControlCode
0x1800a4298  mov     [rsp+4B0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800a42a0  mov     rcx, rbx; hDevice
0x1800a42a3  mov     [rbp+3B0h+var_250], rax
0x1800a42aa  mov     qword ptr [rsp+4B0h+dwCreationDisposition], 0; lpOutBuffer
0x1800a42b3  mov     [rbp+3B0h+var_258], 3
0x1800a42bc  call    cs:__imp_DeviceIoControl
0x1800a42c2  test    eax, eax
0x1800a42c4  jnz     short loc_1800A42E7
0x1800a42c6  call    cs:__imp_GetLastError
0x1800a42cc  test    eax, eax
0x1800a42ce  jle     short loc_1800A42D8
0x1800a42d0  movzx   eax, ax
0x1800a42d3  or      eax, 80070000h
0x1800a42d8  test    eax, eax
0x1800a42da  mov     ebx, 8000FFFFh
0x1800a42df  cmovs   ebx, eax
0x1800a42e2  jmp     loc_1800A4377
0x1800a42e7  mov     r8, r12; Size
0x1800a42ea  lea     rcx, [rbp+3B0h+InBuffer]; void *
0x1800a42f1  xor     edx, edx; Val
0x1800a42f3  call    memset_0
0x1800a42f8  lea     rax, ?ServerSignalName@SipcSignalFactory@@0QBGB; "ServerSignal"
0x1800a42ff  mov     r9d, esi
0x1800a4302  lea     r8, a44xS; "%4.4X_%s"
0x1800a4309  mov     qword ptr [rsp+4B0h+dwCreationDisposition], rax
0x1800a430e  mov     edx, 104h; BufferCount
0x1800a4313  lea     rcx, [rbp+3B0h+InBuffer]; Buffer
0x1800a431a  call    swprintf_s
0x1800a431f  mov     rax, [rdi]
0x1800a4322  lea     r8, [rbp+3B0h+InBuffer]; lpInBuffer
0x1800a4329  mov     [rsp+4B0h+lpOverlapped], 0; lpOverlapped
0x1800a4332  mov     r9d, r12d; nInBufferSize
0x1800a4335  mov     [rsp+4B0h+hTemplateFile], 0; lpBytesReturned
0x1800a433e  mov     edx, 1501FCh; dwIoControlCode
0x1800a4343  mov     [rsp+4B0h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1800a434b  mov     rcx, rbx; hDevice
0x1800a434e  mov     [rbp+3B0h+var_30], rax
0x1800a4355  mov     qword ptr [rsp+4B0h+dwCreationDisposition], 0; lpOutBuffer
0x1800a435e  mov     [rbp+3B0h+var_38], 103h
0x1800a4367  call    cs:__imp_DeviceIoControl
0x1800a436d  test    eax, eax
0x1800a436f  jz      loc_1800A42C6
0x1800a4375  xor     ebx, ebx
0x1800a4377  lea     rcx, [rsp+4B0h+var_470]; this
0x1800a437c  call    ?Reset@SipcFileHandle@@QEAAXXZ; SipcFileHandle::Reset(void)
0x1800a4381  mov     eax, ebx
0x1800a4383  mov     rcx, [rbp+3B0h+var_20]
0x1800a438a  xor     rcx, rsp; StackCookie
0x1800a438d  call    __security_check_cookie
0x1800a4392  lea     r11, [rsp+4B0h+var_10]
0x1800a439a  mov     rbx, [r11+30h]
0x1800a439e  mov     rsi, [r11+38h]
0x1800a43a2  mov     rsp, r11
0x1800a43a5  pop     r12
0x1800a43a7  pop     rdi
0x1800a43a8  pop     rbp
0x1800a43a9  retn
```
