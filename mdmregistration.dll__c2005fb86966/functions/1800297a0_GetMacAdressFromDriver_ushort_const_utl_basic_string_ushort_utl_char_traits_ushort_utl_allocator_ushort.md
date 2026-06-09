# GetMacAdressFromDriver(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800297a0`
- end: `0x1800299ac`
- name: `?GetMacAdressFromDriver@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800294ac`

## callees

- `0x1800026d0`
- `0x18000bd7c`
- `0x18001e0b0`
- `0x1800297a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002989b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002995f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002997a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002989b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800298bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029926`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002995f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002997a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800297ea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800297ea`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029868`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180029868`

## pseudocode

```c
signed int __fastcall GetMacAdressFromDriver(const WCHAR *a1, __int64 a2)
{
  __int64 v3; // rdi
  HANDLE FileW; // rbx
  signed int result; // eax
  signed int LastError; // eax
  unsigned int v7; // edi
  int v8; // esi
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-39h]
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-31h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-29h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-21h]
  DWORD BytesReturned; // [rsp+50h] [rbp-9h] BYREF
  int InBuffer; // [rsp+54h] [rbp-5h] BYREF
  int OutBuffer; // [rsp+58h] [rbp-1h] BYREF
  __int16 v16; // [rsp+5Ch] [rbp+3h]
  unsigned __int16 v17[20]; // [rsp+60h] [rbp+7h] BYREF

  v3 = -1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    OutBuffer = 0;
    v16 = 0;
    BytesReturned = 0;
    InBuffer = 16843009;
    if ( DeviceIoControl(FileW, 0x170002u, &InBuffer, 4u, &OutBuffer, 6u, &BytesReturned, 0) )
    {
      if ( BytesReturned == 6 )
      {
        LODWORD(lpOverlapped) = (unsigned __int8)v16;
        LODWORD(hTemplateFile) = HIBYTE(OutBuffer);
        LODWORD(dwFlagsAndAttributes) = BYTE2(OutBuffer);
        dwCreationDisposition[0] = BYTE1(OutBuffer);
        v8 = StringCchPrintfW(
               v17,
               0x12u,
               L"%.2X-%.2X-%.2X-%.2X-%.2X-%.2X",
               (unsigned __int8)OutBuffer,
               *(_QWORD *)dwCreationDisposition,
               dwFlagsAndAttributes,
               hTemplateFile,
               lpOverlapped,
               HIBYTE(v16));
        if ( v8 >= 0 )
        {
          do
            ++v3;
          while ( v17[v3] );
          if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  a2,
                                  v17,
                                  v3) )
          {
            if ( FileW )
              CloseHandle(FileW);
            return 0;
          }
          else
          {
            if ( FileW )
              CloseHandle(FileW);
            return -2147024882;
          }
        }
        else
        {
          if ( FileW )
            CloseHandle(FileW);
          return v8;
        }
      }
      else
      {
        if ( FileW )
          CloseHandle(FileW);
        return -2147418113;
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( FileW )
        CloseHandle(FileW);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800297a0  mov     [rsp-8+arg_10], rbx
0x1800297a5  push    rbp
0x1800297a6  push    rsi
0x1800297a7  push    rdi
0x1800297a8  push    r14
0x1800297aa  push    r15
0x1800297ac  lea     rbp, [rsp-37h]
0x1800297b1  sub     rsp, 90h
0x1800297b8  mov     rax, cs:__security_cookie
0x1800297bf  xor     rax, rsp
0x1800297c2  mov     [rbp+57h+var_28], rax
0x1800297c6  xor     r15d, r15d
0x1800297c9  mov     r14, rdx
0x1800297cc  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x1800297d1  xor     r9d, r9d; lpSecurityAttributes
0x1800297d4  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800297d9  mov     edx, 80000000h; dwDesiredAccess
0x1800297de  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800297e6  lea     r8d, [r15+1]; dwShareMode
0x1800297ea  call    cs:__imp_CreateFileW
0x1800297f1  nop     dword ptr [rax+rax+00h]
0x1800297f6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800297fa  mov     rbx, rax
0x1800297fd  cmp     rax, rdi
0x180029800  jnz     short loc_180029823
0x180029802  call    cs:__imp_GetLastError
0x180029809  nop     dword ptr [rax+rax+00h]
0x18002980e  test    eax, eax
0x180029810  jle     loc_180029988
0x180029816  movzx   eax, ax
0x180029819  or      eax, 80070000h
0x18002981e  jmp     loc_180029988
0x180029823  xor     eax, eax
0x180029825  mov     [rsp+0B0h+lpOverlapped], r15; lpOverlapped
0x18002982a  mov     [rbp+57h+OutBuffer], eax
0x18002982d  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180029831  mov     [rbp+57h+var_54], ax
0x180029835  mov     r9d, 4; nInBufferSize
0x18002983b  lea     rax, [rbp+57h+BytesReturned]
0x18002983f  mov     [rbp+57h+BytesReturned], r15d
0x180029843  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x180029848  mov     edx, 170002h; dwIoControlCode
0x18002984d  lea     rax, [rbp+57h+OutBuffer]
0x180029851  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], 6; nOutBufferSize
0x180029859  mov     rcx, rbx; hDevice
0x18002985c  mov     qword ptr [rsp+0B0h+dwCreationDisposition], rax; lpOutBuffer
0x180029861  mov     [rbp+57h+InBuffer], 1010101h
0x180029868  call    cs:__imp_DeviceIoControl
0x18002986f  nop     dword ptr [rax+rax+00h]
0x180029874  test    eax, eax
0x180029876  jnz     short loc_1800298AE
0x180029878  call    cs:__imp_GetLastError
0x18002987f  nop     dword ptr [rax+rax+00h]
0x180029884  mov     edi, eax
0x180029886  test    eax, eax
0x180029888  jle     short loc_180029893
0x18002988a  movzx   edi, ax
0x18002988d  or      edi, 80070000h
0x180029893  test    rbx, rbx
0x180029896  jz      short loc_1800298A7
0x180029898  mov     rcx, rbx; hObject
0x18002989b  call    cs:__imp_CloseHandle
0x1800298a2  nop     dword ptr [rax+rax+00h]
0x1800298a7  mov     eax, edi
0x1800298a9  jmp     loc_180029988
0x1800298ae  cmp     [rbp+57h+BytesReturned], 6
0x1800298b2  jz      short loc_1800298D2
0x1800298b4  test    rbx, rbx
0x1800298b7  jz      short loc_1800298C8
0x1800298b9  mov     rcx, rbx; hObject
0x1800298bc  call    cs:__imp_CloseHandle
0x1800298c3  nop     dword ptr [rax+rax+00h]
0x1800298c8  mov     eax, 8000FFFFh
0x1800298cd  jmp     loc_180029988
0x1800298d2  movzx   ecx, byte ptr [rbp+57h+var_54]
0x1800298d6  movzx   edx, byte ptr [rbp+57h+OutBuffer+3]
0x1800298da  movzx   r8d, byte ptr [rbp+57h+OutBuffer+2]
0x1800298df  movzx   eax, byte ptr [rbp+57h+var_54+1]
0x1800298e3  movzx   r10d, byte ptr [rbp+57h+OutBuffer+1]
0x1800298e8  movzx   r9d, byte ptr [rbp+57h+OutBuffer]
0x1800298ed  mov     [rsp+0B0h+var_70], eax
0x1800298f1  mov     dword ptr [rsp+0B0h+lpOverlapped], ecx
0x1800298f5  lea     rcx, [rbp+57h+var_50]; unsigned __int16 *
0x1800298f9  mov     dword ptr [rsp+0B0h+hTemplateFile], edx
0x1800298fd  mov     edx, 12h; unsigned __int64
0x180029902  mov     dword ptr [rsp+0B0h+dwFlagsAndAttributes], r8d
0x180029907  lea     r8, a2x2x2x2x2x2x; "%.2X-%.2X-%.2X-%.2X-%.2X-%.2X"
0x18002990e  mov     [rsp+0B0h+dwCreationDisposition], r10d
0x180029913  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180029918  mov     esi, eax
0x18002991a  test    eax, eax
0x18002991c  jns     short loc_180029936
0x18002991e  test    rbx, rbx
0x180029921  jz      short loc_180029932
0x180029923  mov     rcx, rbx; hObject
0x180029926  call    cs:__imp_CloseHandle
0x18002992d  nop     dword ptr [rax+rax+00h]
0x180029932  mov     eax, esi
0x180029934  jmp     short loc_180029988
0x180029936  lea     rax, [rbp+57h+var_50]
0x18002993a  inc     rdi
0x18002993d  cmp     [rax+rdi*2], r15w
0x180029942  jnz     short loc_18002993A
0x180029944  mov     r8, rdi
0x180029947  lea     rdx, [rbp+57h+var_50]
0x18002994b  mov     rcx, r14
0x18002994e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180029953  test    al, al
0x180029955  jnz     short loc_180029972
0x180029957  test    rbx, rbx
0x18002995a  jz      short loc_18002996B
0x18002995c  mov     rcx, rbx; hObject
0x18002995f  call    cs:__imp_CloseHandle
0x180029966  nop     dword ptr [rax+rax+00h]
0x18002996b  mov     eax, 8007000Eh
0x180029970  jmp     short loc_180029988
0x180029972  test    rbx, rbx
0x180029975  jz      short loc_180029986
0x180029977  mov     rcx, rbx; hObject
0x18002997a  call    cs:__imp_CloseHandle
0x180029981  nop     dword ptr [rax+rax+00h]
0x180029986  xor     eax, eax
0x180029988  mov     rcx, [rbp+57h+var_28]
0x18002998c  xor     rcx, rsp; StackCookie
0x18002998f  call    __security_check_cookie
0x180029994  mov     rbx, [rsp+0B0h+arg_10]
0x18002999c  add     rsp, 90h
0x1800299a3  pop     r15
0x1800299a5  pop     r14
0x1800299a7  pop     rdi
0x1800299a8  pop     rsi
0x1800299a9  pop     rbp
0x1800299aa  retn
```
