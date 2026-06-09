# SendToRDPIDD

- ea: `0x140031684`
- end: `0x1400318e2`
- name: `SendToRDPIDD`
- size: `606`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, DWORD nInBufferSize, LPVOID lpInBuffer)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000d4d8`
- `0x140038b60`

## callees

- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x140031040`
- `0x140031684`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400317fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031749`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400317fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400318bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400318bb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140031735`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140031735`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400317f2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1400317f2`

## string_xrefs

- `0x140031796`: `Fail to open instance of RDPIDD`

## pseudocode

```c
__int64 __fastcall SendToRDPIDD(__int64 dwIoControlCode, DWORD nInBufferSize, LPVOID lpInBuffer)
{
  DWORD v5; // esi
  __int64 FileW; // rdi
  signed int v7; // ebx
  signed int LastError; // eax
  signed int v9; // eax
  __int64 dwFlagsAndAttributes; // [rsp+28h] [rbp-270h]
  __int64 dwFlagsAndAttributesa; // [rsp+28h] [rbp-270h]
  DWORD BytesReturned[2]; // [rsp+40h] [rbp-258h] BYREF
  __int64 v14; // [rsp+48h] [rbp-250h]
  WCHAR FileName[264]; // [rsp+50h] [rbp-248h] BYREF

  v5 = dwIoControlCode;
  if ( (unsigned int)GetDxgkAdapter(dwIoControlCode, FileName) )
  {
    FileW = (__int64)CreateFileW(FileName, 0x10000000u, 3u, 0, 4u, 0x800080u, 0);
    v14 = FileW;
    if ( FileW != -1 )
      goto LABEL_14;
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(dwFlagsAndAttributes) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
          -1,
          (__int64)"Fail to open instance of RDPIDD",
          dwFlagsAndAttributes);
      }
    }
    else
    {
LABEL_14:
      BytesReturned[0] = 0;
      if ( DeviceIoControl((HANDLE)FileW, v5, lpInBuffer, nInBufferSize, 0, 0, BytesReturned, 0) )
        goto LABEL_23;
      v9 = GetLastError();
      v7 = v9;
      if ( v9 > 0 )
        v7 = (unsigned __int16)v9 | 0x80070000;
      BytesReturned[1] = v7;
      if ( v7 >= 0 )
      {
LABEL_23:
        v7 = 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(dwFlagsAndAttributesa) = v7;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          (unsigned int)&WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids,
          -1,
          (__int64)"I/O failed with RDPIDD",
          dwFlagsAndAttributesa);
      }
    }
  }
  else
  {
    FileW = -1;
    v7 = -2147467263;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids, 0xFFFFFFFFLL);
    }
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140031684  push    rbx
0x140031686  push    rsi
0x140031687  push    rdi
0x140031688  push    r14
0x14003168a  push    r15
0x14003168c  sub     rsp, 270h
0x140031693  mov     rax, cs:__security_cookie
0x14003169a  xor     rax, rsp
0x14003169d  mov     [rsp+298h+var_38], rax
0x1400316a5  mov     r15, r8
0x1400316a8  mov     r14d, edx
0x1400316ab  mov     esi, ecx
0x1400316ad  lea     rdx, [rsp+298h+FileName]
0x1400316b2  call    GetDxgkAdapter
0x1400316b7  test    eax, eax
0x1400316b9  jnz     short loc_14003170B
0x1400316bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400316bf  mov     ebx, 80004001h
0x1400316c4  lea     rax, WPP_GLOBAL_Control
0x1400316cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316d2  cmp     rcx, rax
0x1400316d5  jz      loc_1400318B2
0x1400316db  test    byte ptr [rcx+1Ch], 1
0x1400316df  jz      loc_1400318B2
0x1400316e5  cmp     byte ptr [rcx+19h], 2
0x1400316e9  jb      loc_1400318B2
0x1400316ef  lea     edx, [rdi+18h]
0x1400316f2  or      r9d, 0FFFFFFFFh
0x1400316f6  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400316fd  mov     rcx, [rcx+10h]
0x140031701  call    WPP_SF_d
0x140031706  jmp     loc_1400318B2
0x14003170b  mov     [rsp+298h+hTemplateFile], 0; hTemplateFile
0x140031714  mov     dword ptr [rsp+298h+dwFlagsAndAttributes], 800080h; dwFlagsAndAttributes
0x14003171c  mov     [rsp+298h+dwCreationDisposition], 4; dwCreationDisposition
0x140031724  xor     r9d, r9d; lpSecurityAttributes
0x140031727  mov     edx, 10000000h; dwDesiredAccess
0x14003172c  lea     r8d, [r9+3]; dwShareMode
0x140031730  lea     rcx, [rsp+298h+FileName]; lpFileName
0x140031735  call    cs:__imp_CreateFileW
0x14003173b  mov     rdi, rax
0x14003173e  mov     [rsp+298h+var_250], rax
0x140031743  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140031747  jnz     short loc_1400317BB
0x140031749  call    cs:__imp_GetLastError
0x14003174f  mov     ebx, eax
0x140031751  test    eax, eax
0x140031753  jle     short loc_14003175E
0x140031755  movzx   ebx, ax
0x140031758  or      ebx, 80070000h
0x14003175e  test    ebx, ebx
0x140031760  jns     short loc_1400317BB
0x140031762  lea     rax, WPP_GLOBAL_Control
0x140031769  mov     rcx, cs:WPP_GLOBAL_Control
0x140031770  cmp     rcx, rax
0x140031773  jz      loc_1400318B2
0x140031779  test    byte ptr [rcx+1Ch], 8
0x14003177d  jz      loc_1400318B2
0x140031783  cmp     byte ptr [rcx+19h], 2
0x140031787  jb      loc_1400318B2
0x14003178d  mov     edx, 18h
0x140031792  mov     dword ptr [rsp+298h+dwFlagsAndAttributes], ebx
0x140031796  lea     rax, aFailToOpenInst; "Fail to open instance of RDPIDD"
0x14003179d  mov     qword ptr [rsp+298h+dwCreationDisposition], rax
0x1400317a2  or      r9d, 0FFFFFFFFh
0x1400317a6  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400317ad  mov     rcx, [rcx+10h]
0x1400317b1  call    WPP_SF_DsD
0x1400317b6  jmp     loc_1400318B2
0x1400317bb  mov     [rsp+298h+BytesReturned], 0
0x1400317c3  mov     [rsp+298h+lpOverlapped], 0; lpOverlapped
0x1400317cc  lea     rax, [rsp+298h+BytesReturned]
0x1400317d1  mov     [rsp+298h+hTemplateFile], rax; lpBytesReturned
0x1400317d6  mov     dword ptr [rsp+298h+dwFlagsAndAttributes], 0; nOutBufferSize
0x1400317de  mov     qword ptr [rsp+298h+dwCreationDisposition], 0; lpOutBuffer
0x1400317e7  mov     r9d, r14d; nInBufferSize
0x1400317ea  mov     r8, r15; lpInBuffer
0x1400317ed  mov     edx, esi; dwIoControlCode
0x1400317ef  mov     rcx, rdi; hDevice
0x1400317f2  call    cs:__imp_DeviceIoControl
0x1400317f8  test    eax, eax
0x1400317fa  jnz     short loc_140031863
0x1400317fc  call    cs:__imp_GetLastError
0x140031802  mov     ebx, eax
0x140031804  test    eax, eax
0x140031806  jle     short loc_140031811
0x140031808  movzx   ebx, ax
0x14003180b  or      ebx, 80070000h
0x140031811  mov     [rsp+298h+var_254], ebx
0x140031815  test    ebx, ebx
0x140031817  jns     short loc_140031863
0x140031819  lea     rax, WPP_GLOBAL_Control
0x140031820  mov     rcx, cs:WPP_GLOBAL_Control
0x140031827  cmp     rcx, rax
0x14003182a  jz      short loc_140031861
0x14003182c  test    byte ptr [rcx+1Ch], 8
0x140031830  jz      short loc_140031861
0x140031832  cmp     byte ptr [rcx+19h], 2
0x140031836  jb      short loc_140031861
0x140031838  mov     edx, 19h
0x14003183d  mov     dword ptr [rsp+298h+dwFlagsAndAttributes], ebx
0x140031841  lea     rax, aIOFailedWithRd; "I/O failed with RDPIDD"
0x140031848  mov     qword ptr [rsp+298h+dwCreationDisposition], rax
0x14003184d  or      r9d, 0FFFFFFFFh
0x140031851  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x140031858  mov     rcx, [rcx+10h]
0x14003185c  call    WPP_SF_DsD
0x140031861  jmp     short loc_1400318B2
0x140031863  xor     ebx, ebx
0x140031865  jmp     short loc_1400318B2
0x140031867  mov     ebx, eax
0x140031869  bts     ebx, 1Ch
0x14003186d  mov     [rsp+298h+var_254], ebx
0x140031871  lea     rdx, WPP_GLOBAL_Control
0x140031878  mov     rcx, cs:WPP_GLOBAL_Control
0x14003187f  cmp     rcx, rdx
0x140031882  jz      short loc_1400318AD
0x140031884  test    byte ptr [rcx+1Ch], 1
0x140031888  jz      short loc_1400318AD
0x14003188a  cmp     byte ptr [rcx+19h], 2
0x14003188e  jb      short loc_1400318AD
0x140031890  mov     edx, 1Ah
0x140031895  mov     [rsp+298h+dwCreationDisposition], eax
0x140031899  or      r9d, 0FFFFFFFFh
0x14003189d  lea     r8, WPP_42a33f02ea92324bb459c59c3f9ce2d6_Traceguids
0x1400318a4  mov     rcx, [rcx+10h]
0x1400318a8  call    WPP_SF_Dd
0x1400318ad  mov     rdi, [rsp+298h+var_250]
0x1400318b2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400318b6  jz      short loc_1400318C1
0x1400318b8  mov     rcx, rdi; hObject
0x1400318bb  call    cs:__imp_CloseHandle
0x1400318c1  mov     eax, ebx
0x1400318c3  mov     rcx, [rsp+298h+var_38]
0x1400318cb  xor     rcx, rsp; StackCookie
0x1400318ce  call    __security_check_cookie
0x1400318d3  add     rsp, 270h
0x1400318da  pop     r15
0x1400318dc  pop     r14
0x1400318de  pop     rdi
0x1400318df  pop     rsi
0x1400318e0  pop     rbx
0x1400318e1  retn
0x14006a468  push    rbp
0x14006a46a  sub     rsp, 40h
0x14006a46e  mov     rbp, rdx
0x14006a471  mov     rax, [rcx]
0x14006a474  xor     ecx, ecx
0x14006a476  cmp     dword ptr [rax], 0C0000008h
0x14006a47c  setz    cl
0x14006a47f  mov     eax, ecx
0x14006a481  add     rsp, 40h
0x14006a485  pop     rbp
0x14006a486  retn
```
