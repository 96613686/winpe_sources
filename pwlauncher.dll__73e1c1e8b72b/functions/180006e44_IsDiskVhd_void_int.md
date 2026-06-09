# IsDiskVhd(void *,int *)

- ea: `0x180006e44`
- end: `0x1800070e6`
- name: `?IsDiskVhd@@YAHPEAXPEAH@Z`
- size: `674`
- prototype: `__int64 __fastcall(HANDLE hDevice, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180006814`

## callees

- `0x180005528`
- `0x180006e44`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fe10`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180006f75`
- `KERNEL32!GetProcessHeap` at `0x180007051`
- `KERNEL32!GetProcessHeap` at `0x180006f75`
- `KERNEL32!GetProcessHeap` at `0x180007051`
- `KERNEL32!HeapAlloc` at `0x180006f83`
- `KERNEL32!HeapAlloc` at `0x180006f83`
- `KERNEL32!GetLastError` at `0x180006f3a`
- `KERNEL32!GetLastError` at `0x180006ffc`
- `KERNEL32!GetLastError` at `0x18000707f`
- `KERNEL32!GetLastError` at `0x180006f3a`
- `KERNEL32!GetLastError` at `0x180006ffc`
- `KERNEL32!GetLastError` at `0x18000707f`
- `KERNEL32!HeapFree` at `0x18000705f`
- `KERNEL32!HeapFree` at `0x18000705f`
- `KERNEL32!SetLastError` at `0x180007067`
- `KERNEL32!SetLastError` at `0x180007067`
- `KERNEL32!DeviceIoControl` at `0x180006f30`
- `KERNEL32!DeviceIoControl` at `0x180006ff2`
- `KERNEL32!DeviceIoControl` at `0x180006f30`
- `KERNEL32!DeviceIoControl` at `0x180006ff2`

## string_xrefs

- `0x180006eee`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x18000701a`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall IsDiskVhd(HANDLE hDevice, int *a2)
{
  unsigned int v2; // esi
  _QWORD *v5; // rcx
  DWORD v6; // edi
  int v7; // edx
  DWORD v8; // eax
  unsigned int v9; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  DWORD LastError; // eax
  HANDLE v14; // rax
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rcx
  char lpOutBuffer; // [rsp+20h] [rbp-50h]
  char nOutBufferSize; // [rsp+28h] [rbp-48h]
  char lpBytesReturned; // [rsp+30h] [rbp-40h]
  DWORD BytesReturned; // [rsp+40h] [rbp-30h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-28h] BYREF
  __int64 InBuffer; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+58h] [rbp-18h]

  v2 = 0;
  OutBuffer = 0;
  InBuffer = 0;
  v25 = 0;
  BytesReturned = 0;
  v5 = WPP_GLOBAL_Control;
  v6 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a2 )
  {
    InBuffer = 0;
    if ( DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, &OutBuffer, 8u, &BytesReturned, 0) )
    {
      v9 = HIDWORD(OutBuffer);
      ProcessHeap = GetProcessHeap();
      v11 = HeapAlloc(ProcessHeap, 8u, v9);
      v12 = v11;
      if ( v11 )
      {
        if ( DeviceIoControl(hDevice, 0x2D1400u, &InBuffer, 0xCu, v11, HIDWORD(OutBuffer), &BytesReturned, 0) )
        {
          v6 = 0;
          *a2 = v12[7] == 15;
          v2 = 1;
        }
        else
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              65,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              57,
              LastError);
        }
        v14 = GetProcessHeap();
        HeapFree(v14, 0, v12);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          47,
          8);
      }
    }
    else
    {
      v8 = GetLastError();
      v6 = v8;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        nOutBufferSize = v8;
        v7 = 63;
        lpOutBuffer = 40;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v6 = 87;
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
    {
      nOutBufferSize = 87;
      v7 = 62;
      lpOutBuffer = 27;
LABEL_8:
      WPP_SF_sdD(
        v5[2],
        v7,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        lpOutBuffer,
        nOutBufferSize);
    }
  }
  SetLastError(v6);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    lpBytesReturned = GetLastError();
    v17 = "Success";
    if ( !v2 )
      v17 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, v15, v16, 72, (__int64)v17, lpBytesReturned);
  }
  return v2;
}

```

## disassembly

```asm
0x180006e44  mov     [rsp-28h+arg_10], rbx
0x180006e49  mov     [rsp-28h+arg_18], rsi
0x180006e4e  push    rbp
0x180006e4f  push    rdi
0x180006e50  push    r13
0x180006e52  push    r14
0x180006e54  push    r15
0x180006e56  mov     rbp, rsp
0x180006e59  sub     rsp, 70h
0x180006e5d  mov     rax, cs:__security_cookie
0x180006e64  xor     rax, rsp
0x180006e67  mov     [rbp+var_10], rax
0x180006e6b  xor     esi, esi
0x180006e6d  mov     r14, rdx
0x180006e70  xor     eax, eax
0x180006e72  mov     [rbp+OutBuffer], rsi
0x180006e76  mov     [rbp+InBuffer], rax
0x180006e7a  mov     r15, rcx
0x180006e7d  mov     [rbp+var_18], eax
0x180006e80  mov     [rbp+BytesReturned], esi
0x180006e83  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e8a  lea     r13, WPP_GLOBAL_Control
0x180006e91  lea     edi, [rsi+8]
0x180006e94  lea     rbx, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006e9b  cmp     rcx, r13
0x180006e9e  jz      short loc_180006EBC
0x180006ea0  test    [rcx+1Ch], dil
0x180006ea4  jz      short loc_180006EBC
0x180006ea6  mov     rcx, [rcx+10h]
0x180006eaa  lea     edx, [rsi+3Dh]
0x180006ead  mov     r8, rbx
0x180006eb0  call    WPP_SF_
0x180006eb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ebc  test    r14, r14
0x180006ebf  jnz     short loc_180006EFF
0x180006ec1  lea     edi, [r14+57h]
0x180006ec5  cmp     rcx, r13
0x180006ec8  jz      loc_180007065
0x180006ece  test    byte ptr [rcx+1Ch], 1
0x180006ed2  jz      loc_180007065
0x180006ed8  mov     [rsp+70h+nOutBufferSize], edi
0x180006edc  lea     edx, [rdi-19h]
0x180006edf  mov     dword ptr [rsp+70h+lpOutBuffer], 31Bh
0x180006ee7  mov     r8, rbx
0x180006eea  mov     rcx, [rcx+10h]
0x180006eee  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180006ef5  call    WPP_SF_sdD
0x180006efa  jmp     loc_180007065
0x180006eff  mov     [rsp+70h+lpOverlapped], rsi; lpOverlapped
0x180006f04  lea     rax, [rbp+BytesReturned]
0x180006f08  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180006f0d  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180006f11  lea     rax, [rbp+OutBuffer]
0x180006f15  mov     [rsp+70h+nOutBufferSize], edi; nOutBufferSize
0x180006f19  mov     r9d, 0Ch; nInBufferSize
0x180006f1f  mov     [rsp+70h+lpOutBuffer], rax; lpOutBuffer
0x180006f24  mov     edx, 2D1400h; dwIoControlCode
0x180006f29  mov     [rbp+InBuffer], rsi
0x180006f2d  mov     rcx, r15; hDevice
0x180006f30  call    cs:__imp_DeviceIoControl
0x180006f36  test    eax, eax
0x180006f38  jnz     short loc_180006F72
0x180006f3a  call    cs:__imp_GetLastError
0x180006f40  mov     edi, eax
0x180006f42  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f49  cmp     rcx, r13
0x180006f4c  jz      loc_180007065
0x180006f52  test    byte ptr [rcx+1Ch], 1
0x180006f56  jz      loc_180007065
0x180006f5c  mov     [rsp+70h+nOutBufferSize], eax
0x180006f60  mov     edx, 3Fh ; '?'
0x180006f65  mov     dword ptr [rsp+70h+lpOutBuffer], 328h
0x180006f6d  jmp     loc_180006EE7
0x180006f72  mov     ebx, dword ptr [rbp+OutBuffer+4]
0x180006f75  call    cs:__imp_GetProcessHeap
0x180006f7b  mov     r8d, ebx; dwBytes
0x180006f7e  mov     edx, edi; dwFlags
0x180006f80  mov     rcx, rax; hHeap
0x180006f83  call    cs:__imp_HeapAlloc
0x180006f89  mov     rbx, rax
0x180006f8c  test    rax, rax
0x180006f8f  jnz     short loc_180006FC6
0x180006f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f98  cmp     rcx, r13
0x180006f9b  jz      loc_180007065
0x180006fa1  test    byte ptr [rcx+1Ch], 1
0x180006fa5  jz      loc_180007065
0x180006fab  mov     [rsp+70h+nOutBufferSize], edi
0x180006faf  lea     edx, [rax+40h]
0x180006fb2  mov     dword ptr [rsp+70h+lpOutBuffer], 32Fh
0x180006fba  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006fc1  jmp     loc_180006EEA
0x180006fc6  lea     rax, [rbp+BytesReturned]
0x180006fca  mov     [rsp+70h+lpOverlapped], rsi; lpOverlapped
0x180006fcf  mov     [rsp+70h+lpBytesReturned], rax; lpBytesReturned
0x180006fd4  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180006fd8  mov     eax, dword ptr [rbp+OutBuffer+4]
0x180006fdb  mov     r9d, 0Ch; nInBufferSize
0x180006fe1  mov     [rsp+70h+nOutBufferSize], eax; nOutBufferSize
0x180006fe5  mov     edx, 2D1400h; dwIoControlCode
0x180006fea  mov     rcx, r15; hDevice
0x180006fed  mov     [rsp+70h+lpOutBuffer], rbx; lpOutBuffer
0x180006ff2  call    cs:__imp_DeviceIoControl
0x180006ff8  test    eax, eax
0x180006ffa  jnz     short loc_180007040
0x180006ffc  call    cs:__imp_GetLastError
0x180007002  mov     edi, eax
0x180007004  mov     rcx, cs:WPP_GLOBAL_Control
0x18000700b  cmp     rcx, r13
0x18000700e  jz      short loc_180007051
0x180007010  test    byte ptr [rcx+1Ch], 1
0x180007014  jz      short loc_180007051
0x180007016  mov     rcx, [rcx+10h]
0x18000701a  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180007021  mov     [rsp+70h+nOutBufferSize], eax
0x180007025  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000702c  mov     edx, 41h ; 'A'
0x180007031  mov     dword ptr [rsp+70h+lpOutBuffer], 339h
0x180007039  call    WPP_SF_sdD
0x18000703e  jmp     short loc_180007051
0x180007040  xor     eax, eax
0x180007042  xor     edi, edi
0x180007044  cmp     dword ptr [rbx+1Ch], 0Fh
0x180007048  setz    al
0x18000704b  mov     [r14], eax
0x18000704e  lea     esi, [rdi+1]
0x180007051  call    cs:__imp_GetProcessHeap
0x180007057  mov     r8, rbx; lpMem
0x18000705a  xor     edx, edx; dwFlags
0x18000705c  mov     rcx, rax; hHeap
0x18000705f  call    cs:__imp_HeapFree
0x180007065  mov     ecx, edi; dwErrCode
0x180007067  call    cs:__imp_SetLastError
0x18000706d  mov     rax, cs:WPP_GLOBAL_Control
0x180007074  cmp     rax, r13
0x180007077  jz      short loc_1800070BF
0x180007079  test    byte ptr [rax+1Ch], 4
0x18000707d  jz      short loc_1800070BF
0x18000707f  call    cs:__imp_GetLastError
0x180007085  lea     rdx, aFailure; "Failure"
0x18000708c  mov     dword ptr [rsp+70h+lpBytesReturned], eax
0x180007090  test    esi, esi
0x180007092  lea     rcx, aSuccess; "Success"
0x180007099  cmovz   rcx, rdx
0x18000709d  mov     edx, 42h ; 'B'
0x1800070a2  mov     qword ptr [rsp+70h+nOutBufferSize], rcx
0x1800070a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070ae  mov     dword ptr [rsp+70h+lpOutBuffer], 348h
0x1800070b6  mov     rcx, [rcx+10h]
0x1800070ba  call    WPP_SF_sdsd
0x1800070bf  mov     eax, esi
0x1800070c1  mov     rcx, [rbp+var_10]
0x1800070c5  xor     rcx, rsp; StackCookie
0x1800070c8  call    __security_check_cookie
0x1800070cd  lea     r11, [rsp+70h+var_s0]
0x1800070d2  mov     rbx, [r11+40h]
0x1800070d6  mov     rsi, [r11+48h]
0x1800070da  mov     rsp, r11
0x1800070dd  pop     r15
0x1800070df  pop     r14
0x1800070e1  pop     r13
0x1800070e3  pop     rdi
0x1800070e4  pop     rbp
0x1800070e5  retn
```
