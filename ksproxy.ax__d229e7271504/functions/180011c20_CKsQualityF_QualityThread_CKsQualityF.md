# CKsQualityF::QualityThread(CKsQualityF *)

- ea: `0x180011c20`
- end: `0x180012132`
- name: `?QualityThread@CKsQualityF@@CAJPEAV1@@Z`
- size: `1298`
- prototype: `signed int __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180011c20`
- `0x18001f620`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180011cb0`
- `KERNEL32!GetLastError` at `0x180011d12`
- `KERNEL32!GetLastError` at `0x180011df1`
- `KERNEL32!GetLastError` at `0x180011e79`
- `KERNEL32!GetLastError` at `0x180011f8f`
- `KERNEL32!GetLastError` at `0x180011fda`
- `KERNEL32!GetLastError` at `0x180012107`
- `KERNEL32!GetLastError` at `0x180011cb0`
- `KERNEL32!GetLastError` at `0x180011d12`
- `KERNEL32!GetLastError` at `0x180011df1`
- `KERNEL32!GetLastError` at `0x180011e79`
- `KERNEL32!GetLastError` at `0x180011f8f`
- `KERNEL32!GetLastError` at `0x180011fda`
- `KERNEL32!GetLastError` at `0x180012107`
- `KERNEL32!SetEvent` at `0x180011de3`
- `KERNEL32!SetEvent` at `0x180011e6b`
- `KERNEL32!SetEvent` at `0x180012012`
- `KERNEL32!SetEvent` at `0x180011de3`
- `KERNEL32!SetEvent` at `0x180011e6b`
- `KERNEL32!SetEvent` at `0x180012012`
- `KERNEL32!WaitForMultipleObjects` at `0x180011eb9`
- `KERNEL32!WaitForMultipleObjects` at `0x180011eb9`
- `KERNEL32!CancelIoEx` at `0x180011ef6`
- `KERNEL32!CancelIoEx` at `0x180011f0b`
- `KERNEL32!CancelIoEx` at `0x180011ef6`
- `KERNEL32!CancelIoEx` at `0x180011f0b`
- `KERNEL32!CreateEventW` at `0x180011c99`
- `KERNEL32!CreateEventW` at `0x180011cf9`
- `KERNEL32!CreateEventW` at `0x180011c99`
- `KERNEL32!CreateEventW` at `0x180011cf9`
- `KERNEL32!CloseHandle` at `0x180011d25`
- `KERNEL32!CloseHandle` at `0x180011f1c`
- `KERNEL32!CloseHandle` at `0x180011f2c`
- `KERNEL32!CloseHandle` at `0x180011d25`
- `KERNEL32!CloseHandle` at `0x180011f1c`
- `KERNEL32!CloseHandle` at `0x180011f2c`
- `KERNEL32!GetOverlappedResult` at `0x180011f7a`
- `KERNEL32!GetOverlappedResult` at `0x180011fc5`
- `KERNEL32!GetOverlappedResult` at `0x18001203a`
- `KERNEL32!GetOverlappedResult` at `0x1800120d8`
- `KERNEL32!GetOverlappedResult` at `0x180011f7a`
- `KERNEL32!GetOverlappedResult` at `0x180011fc5`
- `KERNEL32!GetOverlappedResult` at `0x18001203a`
- `KERNEL32!GetOverlappedResult` at `0x1800120d8`
- `KERNEL32!DeviceIoControl` at `0x180011dce`
- `KERNEL32!DeviceIoControl` at `0x180011e57`
- `KERNEL32!DeviceIoControl` at `0x180011dce`
- `KERNEL32!DeviceIoControl` at `0x180011e57`
- `ntdll!RtlNtStatusToDosError` at `0x18001208a`
- `ntdll!RtlNtStatusToDosError` at `0x18001208a`

## pseudocode

```c
signed int __fastcall CKsQualityF::QualityThread(PVOID Parameter)
{
  signed int result; // eax
  signed int LastError; // ebx
  int v4; // r12d
  int v5; // r15d
  int v6; // r14d
  signed int v7; // eax
  signed int v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // edx
  signed int v16; // eax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-B0h] BYREF
  struct _OVERLAPPED lpOverlapped; // [rsp+70h] [rbp-90h] BYREF
  __int128 OutBuffer; // [rsp+90h] [rbp-70h] BYREF
  __int64 v22; // [rsp+A0h] [rbp-60h]
  GUID v23; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+B8h] [rbp-48h]
  NTSTATUS Status[4]; // [rsp+C0h] [rbp-40h] BYREF
  GUID InBuffer; // [rsp+D0h] [rbp-30h] BYREF
  int v27; // [rsp+E0h] [rbp-20h]
  int v28; // [rsp+E4h] [rbp-1Ch]
  HANDLE Handles[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v30; // [rsp+F8h] [rbp-8h]

  v24 = 0;
  memset(&lpOverlapped, 0, sizeof(lpOverlapped));
  v27 = 0;
  v28 = 1;
  v23 = 0;
  *(_OWORD *)Handles = 0;
  v30 = 0;
  InBuffer = GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent == (HANDLE)-1LL )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v24 = 0x100000001LL;
  v23 = GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000;
  memset(&lpOverlapped, 0, 24);
  lpOverlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( lpOverlapped.hEvent == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CloseHandle(Overlapped.hEvent);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return LastError;
  }
  v4 = 0;
  Handles[0] = Overlapped.hEvent;
  v5 = 1;
  v6 = 1;
  *(_QWORD *)&v30 = *((_QWORD *)Parameter + 8);
  LastError = 0;
  *((_QWORD *)&v30 + 1) = *((_QWORD *)Parameter + 6);
  Handles[1] = lpOverlapped.hEvent;
  while ( 1 )
  {
    BytesReturned = 0;
    v22 = 0;
    OutBuffer = 0;
    *(_OWORD *)Status = 0;
    if ( !v5 )
      goto LABEL_16;
    if ( !DeviceIoControl(
            *((HANDLE *)Parameter + 4),
            0x2F0003u,
            &InBuffer,
            0x18u,
            &OutBuffer,
            0x18u,
            &BytesReturned,
            &Overlapped) )
      break;
    SetEvent(Overlapped.hEvent);
LABEL_15:
    v5 = 0;
LABEL_16:
    if ( v6 )
    {
      if ( DeviceIoControl(
             *((HANDLE *)Parameter + 4),
             0x2F0003u,
             &v23,
             0x18u,
             Status,
             0x10u,
             &BytesReturned,
             &lpOverlapped) )
      {
        SetEvent(lpOverlapped.hEvent);
      }
      else
      {
        v8 = GetLastError();
        if ( v8 > 0 )
          v8 = (unsigned __int16)v8 | 0x80070000;
        if ( v8 != -2147023899 )
          goto LABEL_60;
        LastError = -2147023899;
      }
      v6 = 0;
    }
    if ( v4 || (v9 = WaitForMultipleObjects(4u, Handles, 0, 0xFFFFFFFF)) == 0 )
    {
      if ( !GetOverlappedResult(*((HANDLE *)Parameter + 4), &Overlapped, &BytesReturned, 1) )
      {
LABEL_56:
        v16 = GetLastError();
        LastError = v16;
        if ( v16 > 0 )
          LastError = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_58;
      }
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)OutBuffer + 120LL))(
        OutBuffer,
        DWORD2(OutBuffer),
        v22);
      v5 = 1;
    }
    else
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 )
          {
            LastError = -2147024637;
            goto LABEL_30;
          }
        }
        else
        {
          v4 = 1;
          if ( GetOverlappedResult(*((HANDLE *)Parameter + 4), &Overlapped, &BytesReturned, 0) )
          {
            v5 = 1;
          }
          else
          {
            v12 = GetLastError();
            LastError = v12;
            if ( v12 > 0 )
              LastError = (unsigned __int16)v12 | 0x80070000;
            if ( LastError != -2147023900 )
              goto LABEL_58;
            LastError = 0;
          }
          if ( GetOverlappedResult(*((HANDLE *)Parameter + 4), &lpOverlapped, &BytesReturned, 0) )
          {
            v6 = 1;
          }
          else
          {
            v13 = GetLastError();
            LastError = v13;
            if ( v13 > 0 )
              LastError = (unsigned __int16)v13 | 0x80070000;
            if ( LastError == -2147023900 )
              LastError = 0;
          }
          if ( !v5 && !v6 )
          {
            SetEvent(*((HANDLE *)Parameter + 7));
            v4 = 0;
          }
        }
      }
      else
      {
        if ( !GetOverlappedResult(*((HANDLE *)Parameter + 4), &lpOverlapped, &BytesReturned, 1) )
          goto LABEL_56;
        v18 = 0;
        if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))OutBuffer)(
               OutBuffer,
               &GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770,
               &v18) >= 0 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          v14 = RtlNtStatusToDosError(Status[2]);
          v15 = v14;
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
          (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v18 + 24LL))(v18, 3, v15);
        }
        v6 = 1;
      }
    }
LABEL_58:
    if ( LastError < 0 )
      goto LABEL_30;
  }
  v7 = GetLastError();
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v7 == -2147023899 )
  {
    LastError = -2147023899;
    goto LABEL_15;
  }
LABEL_60:
  LastError = 0;
LABEL_30:
  CancelIoEx(*((HANDLE *)Parameter + 4), &Overlapped);
  CancelIoEx(*((HANDLE *)Parameter + 4), &lpOverlapped);
  CloseHandle(Overlapped.hEvent);
  CloseHandle(lpOverlapped.hEvent);
  return LastError;
}

```

## disassembly

```asm
0x180011c20  mov     [rsp-8+arg_8], rbx
0x180011c25  mov     [rsp-8+arg_10], rsi
0x180011c2a  push    rbp
0x180011c2b  push    rdi
0x180011c2c  push    r12
0x180011c2e  push    r14
0x180011c30  push    r15
0x180011c32  lea     rbp, [rsp-10h]
0x180011c37  sub     rsp, 110h
0x180011c3e  mov     rax, cs:__security_cookie
0x180011c45  xor     rax, rsp
0x180011c48  mov     [rbp+30h+var_28], rax
0x180011c4c  xorps   xmm0, xmm0
0x180011c4f  xor     eax, eax
0x180011c51  xorps   xmm1, xmm1
0x180011c54  mov     [rbp+30h+var_78], rax
0x180011c58  movups  xmmword ptr [rsp+130h+var_C0.Internal], xmm1
0x180011c5d  mov     rsi, rcx
0x180011c60  xor     r9d, r9d; lpName
0x180011c63  lea     ebx, [rax+1]
0x180011c66  mov     [rbp+30h+var_50], eax
0x180011c69  movups  xmmword ptr [rbp+30h+var_C0.10h], xmm1
0x180011c6d  mov     edx, ebx; bManualReset
0x180011c6f  xor     r8d, r8d; bInitialState
0x180011c72  movups  xmm1, xmmword ptr cs:_GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000.Data1
0x180011c79  xor     ecx, ecx; lpEventAttributes
0x180011c7b  mov     [rbp+30h+var_4C], ebx
0x180011c7e  movups  [rbp+30h+var_88], xmm0
0x180011c82  movups  xmmword ptr [rbp+30h+Handles], xmm0
0x180011c86  movups  [rbp+30h+var_38], xmm0
0x180011c8a  movdqu  [rbp+30h+InBuffer], xmm1
0x180011c8f  movups  xmmword ptr [rsp+130h+Overlapped.Internal], xmm0
0x180011c94  movups  xmmword ptr [rsp+130h+Overlapped.10h], xmm0
0x180011c99  call    cs:__imp_CreateEventW
0x180011ca0  nop     dword ptr [rax+rax+00h]
0x180011ca5  mov     [rsp+130h+Overlapped.hEvent], rax
0x180011caa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011cae  jnz     short loc_180011CD1
0x180011cb0  call    cs:__imp_GetLastError
0x180011cb7  nop     dword ptr [rax+rax+00h]
0x180011cbc  test    eax, eax
0x180011cbe  jle     loc_180011F3A
0x180011cc4  movzx   eax, ax
0x180011cc7  or      eax, 80070000h
0x180011ccc  jmp     loc_180011F3A
0x180011cd1  movups  xmm0, xmmword ptr cs:_GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000.Data1
0x180011cd8  xor     r9d, r9d; lpName
0x180011cdb  mov     dword ptr [rbp+30h+var_78], ebx
0x180011cde  xor     r8d, r8d; bInitialState
0x180011ce1  mov     dword ptr [rbp+30h+var_78+4], ebx
0x180011ce4  movdqu  [rbp+30h+var_88], xmm0
0x180011ce9  mov     edx, ebx; bManualReset
0x180011ceb  xor     ecx, ecx; lpEventAttributes
0x180011ced  xorps   xmm0, xmm0
0x180011cf0  movups  xmmword ptr [rsp+130h+var_C0.Internal], xmm0
0x180011cf5  movups  xmmword ptr [rbp+30h+var_C0.10h], xmm0
0x180011cf9  call    cs:__imp_CreateEventW
0x180011d00  nop     dword ptr [rax+rax+00h]
0x180011d05  mov     [rbp+30h+var_C0.hEvent], rax
0x180011d09  mov     rcx, rax
0x180011d0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011d10  jnz     short loc_180011D47
0x180011d12  call    cs:__imp_GetLastError
0x180011d19  nop     dword ptr [rax+rax+00h]
0x180011d1e  mov     rcx, [rsp+130h+Overlapped.hEvent]; hObject
0x180011d23  mov     ebx, eax
0x180011d25  call    cs:__imp_CloseHandle
0x180011d2c  nop     dword ptr [rax+rax+00h]
0x180011d31  test    ebx, ebx
0x180011d33  jle     loc_180011F38
0x180011d39  movzx   ebx, bx
0x180011d3c  or      ebx, 80070000h
0x180011d42  jmp     loc_180011F38
0x180011d47  mov     rax, [rsp+130h+Overlapped.hEvent]
0x180011d4c  xor     r12d, r12d
0x180011d4f  mov     [rbp+30h+Handles], rax
0x180011d53  mov     r15d, ebx
0x180011d56  mov     rax, [rsi+40h]
0x180011d5a  mov     r14d, ebx
0x180011d5d  mov     qword ptr [rbp+30h+var_38], rax
0x180011d61  xor     ebx, ebx
0x180011d63  mov     rax, [rsi+30h]
0x180011d67  mov     edi, 80070000h
0x180011d6c  mov     qword ptr [rbp+30h+var_38+8], rax
0x180011d70  mov     [rbp+30h+Handles+8], rcx
0x180011d74  xor     eax, eax
0x180011d76  mov     [rsp+130h+BytesReturned], 0
0x180011d7e  mov     [rbp+30h+var_90], rax
0x180011d82  xorps   xmm0, xmm0
0x180011d85  movups  [rbp+30h+OutBuffer], xmm0
0x180011d89  movups  xmmword ptr [rbp+30h+Status], xmm0
0x180011d8d  test    r15d, r15d
0x180011d90  jz      loc_180011E16
0x180011d96  mov     rcx, [rsi+20h]; hDevice
0x180011d9a  lea     rax, [rsp+130h+Overlapped]
0x180011d9f  mov     [rsp+130h+lpOverlapped], rax; lpOverlapped
0x180011da4  lea     r8, [rbp+30h+InBuffer]; lpInBuffer
0x180011da8  lea     rax, [rsp+130h+BytesReturned]
0x180011dad  mov     r9d, 18h; nInBufferSize
0x180011db3  mov     [rsp+130h+lpBytesReturned], rax; lpBytesReturned
0x180011db8  mov     edx, 2F0003h; dwIoControlCode
0x180011dbd  lea     rax, [rbp+30h+OutBuffer]
0x180011dc1  mov     [rsp+130h+nOutBufferSize], 18h; nOutBufferSize
0x180011dc9  mov     [rsp+130h+lpOutBuffer], rax; lpOutBuffer
0x180011dce  call    cs:__imp_DeviceIoControl
0x180011dd5  nop     dword ptr [rax+rax+00h]
0x180011dda  test    eax, eax
0x180011ddc  jz      short loc_180011DF1
0x180011dde  mov     rcx, [rsp+130h+Overlapped.hEvent]; hEvent
0x180011de3  call    cs:__imp_SetEvent
0x180011dea  nop     dword ptr [rax+rax+00h]
0x180011def  jmp     short loc_180011E13
0x180011df1  call    cs:__imp_GetLastError
0x180011df8  nop     dword ptr [rax+rax+00h]
0x180011dfd  test    eax, eax
0x180011dff  jle     short loc_180011E06
0x180011e01  movzx   eax, ax
0x180011e04  or      eax, edi
0x180011e06  cmp     eax, 800703E5h
0x180011e0b  jnz     loc_18001212B
0x180011e11  mov     ebx, eax
0x180011e13  xor     r15d, r15d
0x180011e16  test    r14d, r14d
0x180011e19  jz      loc_180011EA0
0x180011e1f  mov     rcx, [rsi+20h]; hDevice
0x180011e23  lea     rax, [rsp+130h+var_C0]
0x180011e28  mov     [rsp+130h+lpOverlapped], rax; lpOverlapped
0x180011e2d  lea     r8, [rbp+30h+var_88]; lpInBuffer
0x180011e31  lea     rax, [rsp+130h+BytesReturned]
0x180011e36  mov     r9d, 18h; nInBufferSize
0x180011e3c  mov     [rsp+130h+lpBytesReturned], rax; lpBytesReturned
0x180011e41  mov     edx, 2F0003h; dwIoControlCode
0x180011e46  lea     rax, [rbp+30h+Status]
0x180011e4a  mov     [rsp+130h+nOutBufferSize], 10h; nOutBufferSize
0x180011e52  mov     [rsp+130h+lpOutBuffer], rax; lpOutBuffer
0x180011e57  call    cs:__imp_DeviceIoControl
0x180011e5e  nop     dword ptr [rax+rax+00h]
0x180011e63  test    eax, eax
0x180011e65  jz      short loc_180011E79
0x180011e67  mov     rcx, [rbp+30h+var_C0.hEvent]; hEvent
0x180011e6b  call    cs:__imp_SetEvent
0x180011e72  nop     dword ptr [rax+rax+00h]
0x180011e77  jmp     short loc_180011E9D
0x180011e79  call    cs:__imp_GetLastError
0x180011e80  nop     dword ptr [rax+rax+00h]
0x180011e85  test    eax, eax
0x180011e87  jle     short loc_180011E8E
0x180011e89  movzx   eax, ax
0x180011e8c  or      eax, edi
0x180011e8e  mov     ecx, 800703E5h
0x180011e93  cmp     eax, ecx
0x180011e95  jnz     loc_18001212B
0x180011e9b  mov     ebx, ecx
0x180011e9d  xor     r14d, r14d
0x180011ea0  test    r12d, r12d
0x180011ea3  jnz     loc_1800120C4
0x180011ea9  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180011ead  lea     rdx, [rbp+30h+Handles]; lpHandles
0x180011eb1  xor     r8d, r8d; bWaitAll
0x180011eb4  lea     ecx, [r12+4]; nCount
0x180011eb9  call    cs:__imp_WaitForMultipleObjects
0x180011ec0  nop     dword ptr [rax+rax+00h]
0x180011ec5  test    eax, eax
0x180011ec7  jz      loc_1800120C4
0x180011ecd  sub     eax, 1
0x180011ed0  jz      loc_180012026
0x180011ed6  sub     eax, 1
0x180011ed9  jz      loc_180011F63
0x180011edf  cmp     eax, 1
0x180011ee2  jnz     loc_18001211E
0x180011ee8  mov     ebx, 80070103h
0x180011eed  mov     rcx, [rsi+20h]; hFile
0x180011ef1  lea     rdx, [rsp+130h+Overlapped]; lpOverlapped
0x180011ef6  call    cs:__imp_CancelIoEx
0x180011efd  nop     dword ptr [rax+rax+00h]
0x180011f02  mov     rcx, [rsi+20h]; hFile
0x180011f06  lea     rdx, [rsp+130h+var_C0]; lpOverlapped
0x180011f0b  call    cs:__imp_CancelIoEx
0x180011f12  nop     dword ptr [rax+rax+00h]
0x180011f17  mov     rcx, [rsp+130h+Overlapped.hEvent]; hObject
0x180011f1c  call    cs:__imp_CloseHandle
0x180011f23  nop     dword ptr [rax+rax+00h]
0x180011f28  mov     rcx, [rbp+30h+var_C0.hEvent]; hObject
0x180011f2c  call    cs:__imp_CloseHandle
0x180011f33  nop     dword ptr [rax+rax+00h]
0x180011f38  mov     eax, ebx
0x180011f3a  mov     rcx, [rbp+30h+var_28]
0x180011f3e  xor     rcx, rsp; StackCookie
0x180011f41  call    __security_check_cookie
0x180011f46  lea     r11, [rsp+130h+var_20]
0x180011f4e  mov     rbx, [r11+38h]
0x180011f52  mov     rsi, [r11+40h]
0x180011f56  mov     rsp, r11
0x180011f59  pop     r15
0x180011f5b  pop     r14
0x180011f5d  pop     r12
0x180011f5f  pop     rdi
0x180011f60  pop     rbp
0x180011f61  retn
0x180011f63  mov     rcx, [rsi+20h]; hFile
0x180011f67  lea     r8, [rsp+130h+BytesReturned]; lpNumberOfBytesTransferred
0x180011f6c  xor     r9d, r9d; bWait
0x180011f6f  lea     rdx, [rsp+130h+Overlapped]; lpOverlapped
0x180011f74  mov     r12d, 1
0x180011f7a  call    cs:__imp_GetOverlappedResult
0x180011f81  nop     dword ptr [rax+rax+00h]
0x180011f86  test    eax, eax
0x180011f88  jz      short loc_180011F8F
0x180011f8a  mov     r15d, r12d
0x180011f8d  jmp     short loc_180011FB4
0x180011f8f  call    cs:__imp_GetLastError
0x180011f96  nop     dword ptr [rax+rax+00h]
0x180011f9b  mov     ebx, eax
0x180011f9d  test    eax, eax
0x180011f9f  jle     short loc_180011FA6
0x180011fa1  movzx   ebx, ax
0x180011fa4  or      ebx, edi
0x180011fa6  cmp     ebx, 800703E4h
0x180011fac  jnz     loc_18001211E
0x180011fb2  xor     ebx, ebx
0x180011fb4  mov     rcx, [rsi+20h]; hFile
0x180011fb8  lea     r8, [rsp+130h+BytesReturned]; lpNumberOfBytesTransferred
0x180011fbd  xor     r9d, r9d; bWait
0x180011fc0  lea     rdx, [rsp+130h+var_C0]; lpOverlapped
0x180011fc5  call    cs:__imp_GetOverlappedResult
0x180011fcc  nop     dword ptr [rax+rax+00h]
0x180011fd1  test    eax, eax
0x180011fd3  jz      short loc_180011FDA
0x180011fd5  mov     r14d, r12d
0x180011fd8  jmp     short loc_180011FFC
0x180011fda  call    cs:__imp_GetLastError
0x180011fe1  nop     dword ptr [rax+rax+00h]
0x180011fe6  mov     ebx, eax
0x180011fe8  test    eax, eax
0x180011fea  jle     short loc_180011FF1
0x180011fec  movzx   ebx, ax
0x180011fef  or      ebx, edi
0x180011ff1  xor     eax, eax
0x180011ff3  cmp     ebx, 800703E4h
0x180011ff9  cmovz   ebx, eax
0x180011ffc  test    r15d, r15d
0x180011fff  jnz     loc_18001211E
0x180012005  test    r14d, r14d
0x180012008  jnz     loc_18001211E
0x18001200e  mov     rcx, [rsi+38h]; hEvent
0x180012012  call    cs:__imp_SetEvent
0x180012019  nop     dword ptr [rax+rax+00h]
0x18001201e  xor     r12d, r12d
0x180012021  jmp     loc_18001211E
0x180012026  mov     rcx, [rsi+20h]; hFile
0x18001202a  lea     r8, [rsp+130h+BytesReturned]; lpNumberOfBytesTransferred
0x18001202f  mov     r9d, 1; bWait
0x180012035  lea     rdx, [rsp+130h+var_C0]; lpOverlapped
0x18001203a  call    cs:__imp_GetOverlappedResult
0x180012041  nop     dword ptr [rax+rax+00h]
0x180012046  test    eax, eax
0x180012048  jz      loc_180012107
0x18001204e  mov     rcx, qword ptr [rbp+30h+OutBuffer]
0x180012052  lea     r8, [rsp+130h+var_E8]
0x180012057  mov     [rsp+130h+var_E8], 0
0x180012060  lea     rdx, _GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770
0x180012067  mov     rax, [rcx]
0x18001206a  mov     rax, [rax]
0x18001206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012072  test    eax, eax
0x180012074  js      short loc_1800120BC
0x180012076  mov     rcx, [rsp+130h+var_E8]
0x18001207b  mov     rax, [rcx]
0x18001207e  mov     rax, [rax+10h]
0x180012082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012087  mov     ecx, [rbp+30h+Status+8]; Status
0x18001208a  call    cs:__imp_RtlNtStatusToDosError
0x180012091  nop     dword ptr [rax+rax+00h]
0x180012096  mov     edx, eax
0x180012098  test    eax, eax
0x18001209a  jle     short loc_1800120A1
0x18001209c  movzx   edx, ax
0x18001209f  or      edx, edi
0x1800120a1  mov     rcx, [rsp+130h+var_E8]
0x1800120a6  xor     r9d, r9d
0x1800120a9  movsxd  r8, edx
0x1800120ac  mov     rax, [rcx]
0x1800120af  lea     edx, [r9+3]
0x1800120b3  mov     rax, [rax+18h]
0x1800120b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120bc  mov     r14d, 1
0x1800120c2  jmp     short loc_18001211E
0x1800120c4  mov     rcx, [rsi+20h]; hFile
0x1800120c8  lea     r8, [rsp+130h+BytesReturned]; lpNumberOfBytesTransferred
0x1800120cd  mov     r9d, 1; bWait
0x1800120d3  lea     rdx, [rsp+130h+Overlapped]; lpOverlapped
0x1800120d8  call    cs:__imp_GetOverlappedResult
0x1800120df  nop     dword ptr [rax+rax+00h]
0x1800120e4  test    eax, eax
0x1800120e6  jz      short loc_180012107
0x1800120e8  mov     rcx, qword ptr [rbp+30h+OutBuffer]
0x1800120ec  mov     r8, [rbp+30h+var_90]
0x1800120f0  mov     edx, dword ptr [rbp+30h+OutBuffer+8]
0x1800120f3  mov     rax, [rcx]
0x1800120f6  mov     rax, [rax+78h]
  ... truncated ...
```
