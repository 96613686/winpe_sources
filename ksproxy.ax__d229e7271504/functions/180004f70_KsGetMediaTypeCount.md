# KsGetMediaTypeCount

- ea: `0x180004f70`
- end: `0x180005849`
- name: `KsGetMediaTypeCount`
- size: `2265`
- prototype: `__int64 __fastcall(char *hFile, unsigned int, _DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180004250`
- `0x1800043d0`
- `0x18002dd70`
- `0x180038344`

## callees

- `0x180004f70`
- `0x18000bde0`
- `0x180025860`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005047`
- `KERNEL32!GetLastError` at `0x180005147`
- `KERNEL32!GetLastError` at `0x180005237`
- `KERNEL32!GetLastError` at `0x180005350`
- `KERNEL32!GetLastError` at `0x1800054b0`
- `KERNEL32!GetLastError` at `0x1800054d4`
- `KERNEL32!GetLastError` at `0x180005500`
- `KERNEL32!GetLastError` at `0x180005524`
- `KERNEL32!GetLastError` at `0x1800055f4`
- `KERNEL32!GetLastError` at `0x180005618`
- `KERNEL32!GetLastError` at `0x18000563c`
- `KERNEL32!GetLastError` at `0x180005660`
- `KERNEL32!GetLastError` at `0x180005047`
- `KERNEL32!GetLastError` at `0x180005147`
- `KERNEL32!GetLastError` at `0x180005237`
- `KERNEL32!GetLastError` at `0x180005350`
- `KERNEL32!GetLastError` at `0x1800054b0`
- `KERNEL32!GetLastError` at `0x1800054d4`
- `KERNEL32!GetLastError` at `0x180005500`
- `KERNEL32!GetLastError` at `0x180005524`
- `KERNEL32!GetLastError` at `0x1800055f4`
- `KERNEL32!GetLastError` at `0x180005618`
- `KERNEL32!GetLastError` at `0x18000563c`
- `KERNEL32!GetLastError` at `0x180005660`
- `KERNEL32!CreateEventW` at `0x180004fec`
- `KERNEL32!CreateEventW` at `0x1800050ed`
- `KERNEL32!CreateEventW` at `0x1800051dc`
- `KERNEL32!CreateEventW` at `0x1800052f6`
- `KERNEL32!CreateEventW` at `0x180004fec`
- `KERNEL32!CreateEventW` at `0x1800050ed`
- `KERNEL32!CreateEventW` at `0x1800051dc`
- `KERNEL32!CreateEventW` at `0x1800052f6`
- `KERNEL32!CloseHandle` at `0x180005072`
- `KERNEL32!CloseHandle` at `0x180005172`
- `KERNEL32!CloseHandle` at `0x180005262`
- `KERNEL32!CloseHandle` at `0x18000537b`
- `KERNEL32!CloseHandle` at `0x180005072`
- `KERNEL32!CloseHandle` at `0x180005172`
- `KERNEL32!CloseHandle` at `0x180005262`
- `KERNEL32!CloseHandle` at `0x18000537b`
- `KERNEL32!GetOverlappedResult` at `0x180005559`
- `KERNEL32!GetOverlappedResult` at `0x180005586`
- `KERNEL32!GetOverlappedResult` at `0x1800055b3`
- `KERNEL32!GetOverlappedResult` at `0x1800055dc`
- `KERNEL32!GetOverlappedResult` at `0x180005559`
- `KERNEL32!GetOverlappedResult` at `0x180005586`
- `KERNEL32!GetOverlappedResult` at `0x1800055b3`
- `KERNEL32!GetOverlappedResult` at `0x1800055dc`
- `KERNEL32!DeviceIoControl` at `0x180005033`
- `KERNEL32!DeviceIoControl` at `0x180005133`
- `KERNEL32!DeviceIoControl` at `0x180005223`
- `KERNEL32!DeviceIoControl` at `0x18000533c`
- `KERNEL32!DeviceIoControl` at `0x180005033`
- `KERNEL32!DeviceIoControl` at `0x180005133`
- `KERNEL32!DeviceIoControl` at `0x180005223`
- `KERNEL32!DeviceIoControl` at `0x18000533c`
- `ole32!CoTaskMemAlloc` at `0x1800050ac`
- `ole32!CoTaskMemAlloc` at `0x1800052b5`
- `ole32!CoTaskMemAlloc` at `0x1800050ac`
- `ole32!CoTaskMemAlloc` at `0x1800052b5`
- `ole32!CoTaskMemFree` at `0x1800053d9`
- `ole32!CoTaskMemFree` at `0x180005743`
- `ole32!CoTaskMemFree` at `0x18000581d`
- `ole32!CoTaskMemFree` at `0x1800053d9`
- `ole32!CoTaskMemFree` at `0x180005743`
- `ole32!CoTaskMemFree` at `0x18000581d`

## pseudocode

```c
__int64 __fastcall KsGetMediaTypeCount(char *hFile, unsigned int a2, _DWORD *a3)
{
  GUID v3; // xmm0
  signed int LastError; // eax
  int v8; // edi
  _DWORD *lpOutBuffer; // rbx
  DWORD nOutBufferSize; // edi
  signed int v11; // eax
  signed int v12; // eax
  DWORD v14; // edi
  signed int v15; // eax
  int v16; // ecx
  _DWORD *v17; // rax
  int v18; // ecx
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  GUID InBuffer; // [rsp+40h] [rbp-39h] BYREF
  int v28; // [rsp+50h] [rbp-29h]
  int v29; // [rsp+54h] [rbp-25h]
  unsigned int v30; // [rsp+58h] [rbp-21h]
  int v31; // [rsp+5Ch] [rbp-1Dh]
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-19h] BYREF
  struct _OVERLAPPED lpOverlapped; // [rsp+80h] [rbp+7h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+E0h] [rbp+67h] BYREF
  DWORD BytesReturned; // [rsp+E8h] [rbp+6Fh] BYREF
  DWORD v36; // [rsp+F8h] [rbp+7Fh] BYREF

  v3 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  v28 = 13;
  BytesReturned = 0;
  v29 = 1;
  v30 = a2;
  v31 = 1;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = -2147024890;
  }
  else
  {
    memset(&Overlapped, 0, 24);
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( DeviceIoControl(hFile, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &BytesReturned, &Overlapped) )
      {
        switch ( Overlapped.Internal )
        {
          case 0x101uLL:
            v8 = -2147024875;
            break;
          case 0x105uLL:
            v8 = -2147024662;
            break;
          case 0x107uLL:
            v8 = -2147023595;
            break;
          default:
            v8 = 0;
            break;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 == -2147023899 )
        {
          if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
          {
            v8 = 0;
          }
          else
          {
            v23 = GetLastError();
            v8 = v23;
            if ( v23 > 0 )
              v8 = (unsigned __int16)v23 | 0x80070000;
          }
        }
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      v19 = GetLastError();
      v8 = v19;
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
    }
    if ( v8 == -2147024774 )
    {
      NumberOfBytesTransferred = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
      v8 = KsSynchronousDeviceControl(hFile, 0x2F0003u, &InBuffer, 0x20u, &NumberOfBytesTransferred, 4u, &BytesReturned);
      if ( v8 >= 0 )
      {
        BytesReturned = NumberOfBytesTransferred;
        goto LABEL_13;
      }
    }
    v3 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  }
  if ( v8 != -2147024662 )
  {
    lpOutBuffer = 0;
    if ( v8 < 0 )
      goto LABEL_23;
LABEL_24:
    NumberOfBytesTransferred = 0;
    Overlapped.Pointer = (PVOID)0x100000003LL;
    Overlapped.hEvent = (HANDLE)(a2 | 0x100000000LL);
    *(GUID *)&Overlapped.Internal = v3;
    if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v8 = -2147024890;
    }
    else
    {
      memset(&lpOverlapped, 0, sizeof(lpOverlapped));
      lpOverlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( lpOverlapped.hEvent )
      {
        if ( DeviceIoControl(hFile, 0x2F0003u, &Overlapped, 0x20u, 0, 0, &NumberOfBytesTransferred, &lpOverlapped) )
        {
          switch ( lpOverlapped.Internal )
          {
            case 0x101uLL:
              v8 = -2147024875;
              break;
            case 0x105uLL:
              v8 = -2147024662;
              break;
            case 0x107uLL:
              v8 = -2147023595;
              break;
            default:
              v8 = 0;
              break;
          }
        }
        else
        {
          v12 = GetLastError();
          v8 = v12;
          if ( v12 > 0 )
            v8 = (unsigned __int16)v12 | 0x80070000;
          if ( v8 == -2147023899 )
          {
            if ( GetOverlappedResult(hFile, &lpOverlapped, &NumberOfBytesTransferred, 1) )
            {
              v8 = 0;
            }
            else
            {
              v25 = GetLastError();
              v8 = v25;
              if ( v25 > 0 )
                v8 = (unsigned __int16)v25 | 0x80070000;
            }
          }
        }
        CloseHandle(lpOverlapped.hEvent);
      }
      else
      {
        v20 = GetLastError();
        v8 = v20;
        if ( v20 > 0 )
          v8 = (unsigned __int16)v20 | 0x80070000;
      }
      if ( v8 == -2147024774 )
      {
        v36 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
        v8 = KsSynchronousDeviceControl(hFile, 0x2F0003u, &Overlapped, 0x20u, &v36, 4u, &NumberOfBytesTransferred);
        if ( v8 >= 0 )
        {
          NumberOfBytesTransferred = v36;
          goto LABEL_36;
        }
      }
    }
    if ( v8 != -2147024662 )
    {
      if ( v8 >= 0 )
        return (unsigned int)-2147418113;
      return (unsigned int)v8;
    }
LABEL_36:
    lpOutBuffer = CoTaskMemAlloc(NumberOfBytesTransferred);
    if ( !lpOutBuffer )
      return (unsigned int)-2147024882;
    if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v8 = -2147024890;
    }
    else
    {
      v14 = NumberOfBytesTransferred;
      memset(&lpOverlapped, 0, sizeof(lpOverlapped));
      lpOverlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( lpOverlapped.hEvent )
      {
        if ( DeviceIoControl(
               hFile,
               0x2F0003u,
               &Overlapped,
               0x20u,
               lpOutBuffer,
               v14,
               &NumberOfBytesTransferred,
               &lpOverlapped) )
        {
          switch ( lpOverlapped.Internal )
          {
            case 0x101uLL:
              v8 = -2147024875;
              break;
            case 0x105uLL:
              v8 = -2147024662;
              break;
            case 0x107uLL:
              v8 = -2147023595;
              break;
            default:
              v8 = 0;
              break;
          }
        }
        else
        {
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          if ( v8 == -2147023899 )
          {
            if ( GetOverlappedResult(hFile, &lpOverlapped, &NumberOfBytesTransferred, 1) )
            {
              v8 = 0;
            }
            else
            {
              v26 = GetLastError();
              v8 = v26;
              if ( v26 > 0 )
                v8 = (unsigned __int16)v26 | 0x80070000;
            }
          }
        }
        CloseHandle(lpOverlapped.hEvent);
      }
      else
      {
        v22 = GetLastError();
        v8 = v22;
        if ( v22 > 0 )
          v8 = (unsigned __int16)v22 | 0x80070000;
      }
      if ( v8 >= 0 )
        goto LABEL_45;
    }
    CoTaskMemFree(lpOutBuffer);
    return (unsigned int)v8;
  }
LABEL_13:
  lpOutBuffer = CoTaskMemAlloc(BytesReturned);
  if ( !lpOutBuffer )
  {
    v3 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    goto LABEL_24;
  }
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = -2147024890;
  }
  else
  {
    nOutBufferSize = BytesReturned;
    memset(&Overlapped, 0, sizeof(Overlapped));
    Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
    if ( Overlapped.hEvent )
    {
      if ( DeviceIoControl(hFile, 0x2F0003u, &InBuffer, 0x20u, lpOutBuffer, nOutBufferSize, &BytesReturned, &Overlapped) )
      {
        switch ( Overlapped.Internal )
        {
          case 0x101uLL:
            v8 = -2147024875;
            break;
          case 0x105uLL:
            v8 = -2147024662;
            break;
          case 0x107uLL:
            v8 = -2147023595;
            break;
          default:
            v8 = 0;
            break;
        }
      }
      else
      {
        v11 = GetLastError();
        v8 = v11;
        if ( v11 > 0 )
          v8 = (unsigned __int16)v11 | 0x80070000;
        if ( v8 == -2147023899 )
        {
          if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
          {
            v8 = 0;
          }
          else
          {
            v24 = GetLastError();
            v8 = v24;
            if ( v24 > 0 )
              v8 = (unsigned __int16)v24 | 0x80070000;
          }
        }
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      v21 = GetLastError();
      v8 = v21;
      if ( v21 > 0 )
        v8 = (unsigned __int16)v21 | 0x80070000;
    }
    if ( v8 >= 0 )
    {
      v3 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
      goto LABEL_23;
    }
  }
  CoTaskMemFree(lpOutBuffer);
  v3 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  lpOutBuffer = 0;
LABEL_23:
  if ( v8 < 0 )
    goto LABEL_24;
LABEL_45:
  *a3 = lpOutBuffer[1];
  v16 = lpOutBuffer[1];
  if ( v16 )
  {
    v17 = lpOutBuffer + 2;
    do
    {
      v18 = v16 - 1;
      lpOutBuffer[1] = v18;
      if ( (v17[1] & 2) != 0 )
      {
        lpOutBuffer[1] = v18 - 1;
        --*a3;
        v17 = (_DWORD *)((char *)v17 + ((*v17 + 7) & 0xFFFFFFF8));
      }
      v17 = (_DWORD *)((char *)v17 + ((*v17 + 7) & 0xFFFFFFF8));
      v16 = lpOutBuffer[1];
    }
    while ( v16 );
  }
  else
  {
    v16 = 0;
  }
  lpOutBuffer[1] = v16 - 1;
  CoTaskMemFree(lpOutBuffer);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180004f70  mov     [rsp-8+arg_10], rbx
0x180004f75  push    rbp
0x180004f76  push    rsi
0x180004f77  push    rdi
0x180004f78  push    r12
0x180004f7a  push    r13
0x180004f7c  push    r14
0x180004f7e  push    r15
0x180004f80  lea     rbp, [rsp-27h]
0x180004f85  sub     rsp, 0A0h
0x180004f8c  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180004f93  xor     r12d, r12d
0x180004f96  mov     [rbp+57h+var_80], 0Dh
0x180004f9d  lea     rax, [rcx-1]
0x180004fa1  mov     [rbp+57h+BytesReturned], r12d
0x180004fa5  mov     [rbp+57h+var_7C], 1
0x180004fac  mov     r15, r8
0x180004faf  mov     [rbp+57h+var_78], edx
0x180004fb2  mov     r14d, edx
0x180004fb5  mov     [rbp+57h+var_74], 1
0x180004fbc  mov     rsi, rcx
0x180004fbf  lea     r13, WPP_GLOBAL_Control
0x180004fc6  movups  [rbp+57h+InBuffer], xmm0
0x180004fca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180004fce  ja      loc_180005713
0x180004fd4  xorps   xmm0, xmm0
0x180004fd7  xor     r9d, r9d; lpName
0x180004fda  xor     r8d, r8d; bInitialState
0x180004fdd  mov     edx, 1; bManualReset
0x180004fe2  xor     ecx, ecx; lpEventAttributes
0x180004fe4  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180004fe8  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180004fec  call    cs:__imp_CreateEventW
0x180004ff3  nop     dword ptr [rax+rax+00h]
0x180004ff8  mov     [rbp+57h+Overlapped.hEvent], rax
0x180004ffc  test    rax, rax
0x180004fff  jz      loc_1800054B0
0x180005005  lea     rax, [rbp+57h+Overlapped]
0x180005009  mov     r9d, 20h ; ' '; nInBufferSize
0x18000500f  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x180005014  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180005018  lea     rax, [rbp+57h+BytesReturned]
0x18000501c  mov     edx, 2F0003h; dwIoControlCode
0x180005021  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005026  mov     rcx, rsi; hDevice
0x180005029  mov     [rsp+0D0h+nOutBufferSize], r12d; nOutBufferSize
0x18000502e  mov     [rsp+0D0h+lpOutBuffer], r12; lpOutBuffer
0x180005033  call    cs:__imp_DeviceIoControl
0x18000503a  nop     dword ptr [rax+rax+00h]
0x18000503f  test    eax, eax
0x180005041  jnz     loc_1800053EA
0x180005047  call    cs:__imp_GetLastError
0x18000504e  nop     dword ptr [rax+rax+00h]
0x180005053  mov     edi, eax
0x180005055  test    eax, eax
0x180005057  jle     short loc_180005062
0x180005059  movzx   edi, ax
0x18000505c  or      edi, 80070000h
0x180005062  cmp     edi, 800703E5h
0x180005068  jz      loc_180005548
0x18000506e  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180005072  call    cs:__imp_CloseHandle
0x180005079  nop     dword ptr [rax+rax+00h]
0x18000507e  cmp     edi, 8007007Ah
0x180005084  jz      loc_1800056A2
0x18000508a  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180005091  cmp     edi, 800700EAh
0x180005097  jz      short loc_1800050A9
0x180005099  mov     rbx, r12
0x18000509c  test    edi, edi
0x18000509e  js      loc_18000518D
0x1800050a4  jmp     loc_180005195
0x1800050a9  mov     ecx, [rbp+57h+BytesReturned]; cb
0x1800050ac  call    cs:__imp_CoTaskMemAlloc
0x1800050b3  nop     dword ptr [rax+rax+00h]
0x1800050b8  mov     rbx, rax
0x1800050bb  test    rax, rax
0x1800050be  jz      loc_18000549A
0x1800050c4  lea     rcx, [rsi-1]
0x1800050c8  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800050cc  ja      loc_18000573B
0x1800050d2  mov     edi, [rbp+57h+BytesReturned]
0x1800050d5  xorps   xmm0, xmm0
0x1800050d8  xor     r9d, r9d; lpName
0x1800050db  xor     r8d, r8d; bInitialState
0x1800050de  mov     edx, 1; bManualReset
0x1800050e3  xor     ecx, ecx; lpEventAttributes
0x1800050e5  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800050e9  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1800050ed  call    cs:__imp_CreateEventW
0x1800050f4  nop     dword ptr [rax+rax+00h]
0x1800050f9  mov     [rbp+57h+Overlapped.hEvent], rax
0x1800050fd  test    rax, rax
0x180005100  jz      loc_180005500
0x180005106  lea     rax, [rbp+57h+Overlapped]
0x18000510a  mov     r9d, 20h ; ' '; nInBufferSize
0x180005110  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x180005115  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180005119  lea     rax, [rbp+57h+BytesReturned]
0x18000511d  mov     edx, 2F0003h; dwIoControlCode
0x180005122  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005127  mov     rcx, rsi; hDevice
0x18000512a  mov     [rsp+0D0h+nOutBufferSize], edi; nOutBufferSize
0x18000512e  mov     [rsp+0D0h+lpOutBuffer], rbx; lpOutBuffer
0x180005133  call    cs:__imp_DeviceIoControl
0x18000513a  nop     dword ptr [rax+rax+00h]
0x18000513f  test    eax, eax
0x180005141  jnz     loc_180005442
0x180005147  call    cs:__imp_GetLastError
0x18000514e  nop     dword ptr [rax+rax+00h]
0x180005153  mov     edi, eax
0x180005155  test    eax, eax
0x180005157  jle     short loc_180005162
0x180005159  movzx   edi, ax
0x18000515c  or      edi, 80070000h
0x180005162  cmp     edi, 800703E5h
0x180005168  jz      loc_1800055A2
0x18000516e  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180005172  call    cs:__imp_CloseHandle
0x180005179  nop     dword ptr [rax+rax+00h]
0x18000517e  test    edi, edi
0x180005180  js      loc_180005740
0x180005186  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000518d  test    edi, edi
0x18000518f  jns     loc_18000538F
0x180005195  lea     rax, [rsi-1]
0x180005199  mov     [rbp+57h+NumberOfBytesTransferred], r12d
0x18000519d  mov     dword ptr [rbp+57h+Overlapped.10h], 3
0x1800051a4  mov     dword ptr [rbp+57h+Overlapped.10h+4], 1
0x1800051ab  mov     dword ptr [rbp+57h+Overlapped.hEvent], r14d
0x1800051af  mov     dword ptr [rbp+57h+Overlapped.hEvent+4], 1
0x1800051b6  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800051ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800051be  ja      loc_1800057ED
0x1800051c4  xorps   xmm0, xmm0
0x1800051c7  xor     r9d, r9d; lpName
0x1800051ca  xor     r8d, r8d; bInitialState
0x1800051cd  mov     edx, 1; bManualReset
0x1800051d2  xor     ecx, ecx; lpEventAttributes
0x1800051d4  movups  xmmword ptr [rbp+57h+var_50.Internal], xmm0
0x1800051d8  movups  xmmword ptr [rbp+57h+var_50.10h], xmm0
0x1800051dc  call    cs:__imp_CreateEventW
0x1800051e3  nop     dword ptr [rax+rax+00h]
0x1800051e8  mov     [rbp+57h+var_50.hEvent], rax
0x1800051ec  test    rax, rax
0x1800051ef  jz      loc_1800054D4
0x1800051f5  lea     rax, [rbp+57h+var_50]
0x1800051f9  mov     r9d, 20h ; ' '; nInBufferSize
0x1800051ff  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x180005204  lea     r8, [rbp+57h+Overlapped]; lpInBuffer
0x180005208  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x18000520c  mov     edx, 2F0003h; dwIoControlCode
0x180005211  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005216  mov     rcx, rsi; hDevice
0x180005219  mov     [rsp+0D0h+nOutBufferSize], r12d; nOutBufferSize
0x18000521e  mov     [rsp+0D0h+lpOutBuffer], r12; lpOutBuffer
0x180005223  call    cs:__imp_DeviceIoControl
0x18000522a  nop     dword ptr [rax+rax+00h]
0x18000522f  test    eax, eax
0x180005231  jnz     loc_180005416
0x180005237  call    cs:__imp_GetLastError
0x18000523e  nop     dword ptr [rax+rax+00h]
0x180005243  mov     edi, eax
0x180005245  test    eax, eax
0x180005247  jle     short loc_180005252
0x180005249  movzx   edi, ax
0x18000524c  or      edi, 80070000h
0x180005252  cmp     edi, 800703E5h
0x180005258  jz      loc_180005575
0x18000525e  mov     rcx, [rbp+57h+var_50.hEvent]; hObject
0x180005262  call    cs:__imp_CloseHandle
0x180005269  nop     dword ptr [rax+rax+00h]
0x18000526e  cmp     edi, 8007007Ah
0x180005274  jz      loc_18000577C
0x18000527a  cmp     edi, 800700EAh
0x180005280  jz      short loc_1800052B2
0x180005282  test    edi, edi
0x180005284  mov     eax, 8000FFFFh
0x180005289  cmovns  edi, eax
0x18000528c  test    edi, edi
0x18000528e  jns     loc_18000538F
0x180005294  mov     rbx, [rsp+0D0h+arg_10]
0x18000529c  mov     eax, edi
0x18000529e  add     rsp, 0A0h
0x1800052a5  pop     r15
0x1800052a7  pop     r14
0x1800052a9  pop     r13
0x1800052ab  pop     r12
0x1800052ad  pop     rdi
0x1800052ae  pop     rsi
0x1800052af  pop     rbp
0x1800052b0  retn
0x1800052b2  mov     ecx, [rbp+57h+NumberOfBytesTransferred]; cb
0x1800052b5  call    cs:__imp_CoTaskMemAlloc
0x1800052bc  nop     dword ptr [rax+rax+00h]
0x1800052c1  mov     rbx, rax
0x1800052c4  test    rax, rax
0x1800052c7  jz      loc_1800054A6
0x1800052cd  lea     rax, [rsi-1]
0x1800052d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800052d5  ja      loc_180005815
0x1800052db  mov     edi, [rbp+57h+NumberOfBytesTransferred]
0x1800052de  xorps   xmm0, xmm0
0x1800052e1  xor     r9d, r9d; lpName
0x1800052e4  xor     r8d, r8d; bInitialState
0x1800052e7  mov     edx, 1; bManualReset
0x1800052ec  xor     ecx, ecx; lpEventAttributes
0x1800052ee  movups  xmmword ptr [rbp+57h+var_50.Internal], xmm0
0x1800052f2  movups  xmmword ptr [rbp+57h+var_50.10h], xmm0
0x1800052f6  call    cs:__imp_CreateEventW
0x1800052fd  nop     dword ptr [rax+rax+00h]
0x180005302  mov     [rbp+57h+var_50.hEvent], rax
0x180005306  test    rax, rax
0x180005309  jz      loc_180005524
0x18000530f  lea     rax, [rbp+57h+var_50]
0x180005313  mov     r9d, 20h ; ' '; nInBufferSize
0x180005319  mov     [rsp+0D0h+lpOverlapped], rax; lpOverlapped
0x18000531e  lea     r8, [rbp+57h+Overlapped]; lpInBuffer
0x180005322  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180005326  mov     edx, 2F0003h; dwIoControlCode
0x18000532b  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005330  mov     rcx, rsi; hDevice
0x180005333  mov     [rsp+0D0h+nOutBufferSize], edi; nOutBufferSize
0x180005337  mov     [rsp+0D0h+lpOutBuffer], rbx; lpOutBuffer
0x18000533c  call    cs:__imp_DeviceIoControl
0x180005343  nop     dword ptr [rax+rax+00h]
0x180005348  test    eax, eax
0x18000534a  jnz     loc_18000546E
0x180005350  call    cs:__imp_GetLastError
0x180005357  nop     dword ptr [rax+rax+00h]
0x18000535c  mov     edi, eax
0x18000535e  test    eax, eax
0x180005360  jle     short loc_18000536B
0x180005362  movzx   edi, ax
0x180005365  or      edi, 80070000h
0x18000536b  cmp     edi, 800703E5h
0x180005371  jz      loc_1800055CB
0x180005377  mov     rcx, [rbp+57h+var_50.hEvent]; hObject
0x18000537b  call    cs:__imp_CloseHandle
0x180005382  nop     dword ptr [rax+rax+00h]
0x180005387  test    edi, edi
0x180005389  js      loc_18000581A
0x18000538f  mov     eax, [rbx+4]
0x180005392  mov     [r15], eax
0x180005395  mov     ecx, [rbx+4]
0x180005398  test    ecx, ecx
0x18000539a  jz      loc_1800054F8
0x1800053a0  lea     rax, [rbx+8]
0x1800053a4  mov     edx, 0FFFFFFF8h
0x1800053a9  nop     dword ptr [rax+00000000h]
0x1800053b0  dec     ecx
0x1800053b2  mov     [rbx+4], ecx
0x1800053b5  test    byte ptr [rax+4], 2
0x1800053b9  jnz     loc_180005831
0x1800053bf  mov     ecx, [rax]
0x1800053c1  add     ecx, 7
0x1800053c4  and     rcx, rdx
0x1800053c7  add     rax, rcx
0x1800053ca  mov     ecx, [rbx+4]
0x1800053cd  test    ecx, ecx
0x1800053cf  jnz     short loc_1800053B0
0x1800053d1  dec     ecx
0x1800053d3  mov     [rbx+4], ecx
0x1800053d6  mov     rcx, rbx; pv
0x1800053d9  call    cs:__imp_CoTaskMemFree
0x1800053e0  nop     dword ptr [rax+rax+00h]
0x1800053e5  jmp     loc_180005294
0x1800053ea  mov     rax, [rbp+57h+Overlapped.Internal]
0x1800053ee  sub     rax, 101h
0x1800053f4  jz      loc_180005698
0x1800053fa  sub     rax, 4
0x1800053fe  jz      loc_18000568E
0x180005404  cmp     rax, 2
0x180005408  jz      loc_180005684
0x18000540e  mov     edi, r12d
0x180005411  jmp     loc_18000506E
0x180005416  mov     rax, [rbp+57h+var_50.Internal]
0x18000541a  sub     rax, 101h
0x180005420  jz      loc_180005772
0x180005426  sub     rax, 4
0x18000542a  jz      loc_180005768
0x180005430  cmp     rax, 2
0x180005434  jz      loc_18000575E
0x18000543a  mov     edi, r12d
0x18000543d  jmp     loc_18000525E
0x180005442  mov     rax, [rbp+57h+Overlapped.Internal]
0x180005446  sub     rax, 101h
0x18000544c  jz      loc_180005731
0x180005452  sub     rax, 4
0x180005456  jz      loc_180005727
0x18000545c  cmp     rax, 2
0x180005460  jz      loc_18000571D
0x180005466  mov     edi, r12d
0x180005469  jmp     loc_18000516E
0x18000546e  mov     rax, [rbp+57h+var_50.Internal]
0x180005472  sub     rax, 101h
0x180005478  jz      loc_18000580B
0x18000547e  sub     rax, 4
0x180005482  jz      loc_180005801
0x180005488  cmp     rax, 2
  ... truncated ...
```
