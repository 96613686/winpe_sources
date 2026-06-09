# KsGetMultiplePinFactoryItems

- ea: `0x1800063a0`
- end: `0x1800067ed`
- name: `KsGetMultiplePinFactoryItems`
- size: `1101`
- prototype: `__int64 __fastcall(char *hFile, int, int, LPVOID *)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180005850`
- `0x180006800`
- `0x180006850`
- `0x180027c90`
- `0x18002ba70`
- `0x18002bac0`
- `0x180030188`
- `0x1800389a0`

## callees

- `0x1800063a0`
- `0x18000bde0`
- `0x180025860`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006477`
- `KERNEL32!GetLastError` at `0x1800065c7`
- `KERNEL32!GetLastError` at `0x180006642`
- `KERNEL32!GetLastError` at `0x180006666`
- `KERNEL32!GetLastError` at `0x1800066d8`
- `KERNEL32!GetLastError` at `0x1800066fc`
- `KERNEL32!GetLastError` at `0x180006477`
- `KERNEL32!GetLastError` at `0x1800065c7`
- `KERNEL32!GetLastError` at `0x180006642`
- `KERNEL32!GetLastError` at `0x180006666`
- `KERNEL32!GetLastError` at `0x1800066d8`
- `KERNEL32!GetLastError` at `0x1800066fc`
- `KERNEL32!CreateEventW` at `0x180006420`
- `KERNEL32!CreateEventW` at `0x180006570`
- `KERNEL32!CreateEventW` at `0x180006420`
- `KERNEL32!CreateEventW` at `0x180006570`
- `KERNEL32!CloseHandle` at `0x1800064a2`
- `KERNEL32!CloseHandle` at `0x1800065f2`
- `KERNEL32!CloseHandle` at `0x1800064a2`
- `KERNEL32!CloseHandle` at `0x1800065f2`
- `KERNEL32!GetOverlappedResult` at `0x180006697`
- `KERNEL32!GetOverlappedResult` at `0x1800066c0`
- `KERNEL32!GetOverlappedResult` at `0x180006697`
- `KERNEL32!GetOverlappedResult` at `0x1800066c0`
- `KERNEL32!DeviceIoControl` at `0x180006467`
- `KERNEL32!DeviceIoControl` at `0x1800065b7`
- `KERNEL32!DeviceIoControl` at `0x180006467`
- `KERNEL32!DeviceIoControl` at `0x1800065b7`
- `ole32!CoTaskMemAlloc` at `0x180006523`
- `ole32!CoTaskMemAlloc` at `0x180006523`
- `ole32!CoTaskMemFree` at `0x1800067d9`
- `ole32!CoTaskMemFree` at `0x1800067d9`

## pseudocode

```c
__int64 __fastcall KsGetMultiplePinFactoryItems(char *hFile, int a2, int a3, LPVOID *a4)
{
  unsigned int v6; // edi
  signed int LastError; // eax
  int v8; // ebx
  LPVOID v10; // rax
  void *lpOutBuffer; // rbx
  DWORD nOutBufferSize; // r14d
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  GUID InBuffer; // [rsp+40h] [rbp-40h] BYREF
  int v19; // [rsp+50h] [rbp-30h]
  int v20; // [rsp+54h] [rbp-2Ch]
  int v21; // [rsp+58h] [rbp-28h]
  int v22; // [rsp+5Ch] [rbp-24h]
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-20h] BYREF
  DWORD BytesReturned; // [rsp+B8h] [rbp+38h] BYREF
  DWORD v25; // [rsp+C0h] [rbp+40h] BYREF

  v19 = a3;
  BytesReturned = 0;
  v20 = 1;
  v21 = a2;
  v22 = 0;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( a3 == 3 || a3 == 13 )
    v22 = 1;
  v6 = -2147023595;
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
            v16 = GetLastError();
            v8 = v16;
            if ( v16 > 0 )
              v8 = (unsigned __int16)v16 | 0x80070000;
          }
        }
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
    }
    if ( v8 == -2147024774 )
    {
      v25 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
      v8 = KsSynchronousDeviceControl(hFile, 0x2F0003u, &InBuffer, 0x20u, &v25, 4u, &BytesReturned);
      if ( v8 >= 0 )
      {
        BytesReturned = v25;
        goto LABEL_22;
      }
    }
  }
  if ( v8 != -2147024662 )
  {
    v6 = v8;
    if ( v8 >= 0 )
      return (unsigned int)-2147418113;
    return v6;
  }
LABEL_22:
  v10 = CoTaskMemAlloc(BytesReturned);
  *a4 = v10;
  lpOutBuffer = v10;
  if ( !v10 )
    return 2147942414LL;
  if ( (unsigned __int64)(hFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = -2147024890;
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
        if ( Overlapped.Internal == 257 )
        {
          v6 = -2147024875;
        }
        else if ( Overlapped.Internal == 261 )
        {
          v6 = -2147024662;
        }
        else if ( Overlapped.Internal != 263 )
        {
          v6 = 0;
        }
      }
      else
      {
        v13 = GetLastError();
        v6 = v13;
        if ( v13 > 0 )
          v6 = (unsigned __int16)v13 | 0x80070000;
        if ( v6 == -2147023899 )
        {
          if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
          {
            v6 = 0;
          }
          else
          {
            v17 = GetLastError();
            v6 = v17;
            if ( v17 > 0 )
              v6 = (unsigned __int16)v17 | 0x80070000;
          }
        }
      }
      CloseHandle(Overlapped.hEvent);
    }
    else
    {
      v15 = GetLastError();
      v6 = v15;
      if ( v15 > 0 )
        v6 = (unsigned __int16)v15 | 0x80070000;
    }
    if ( (v6 & 0x80000000) == 0 )
      return v6;
  }
  CoTaskMemFree(*a4);
  *a4 = 0;
  return v6;
}

```

## disassembly

```asm
0x1800063a0  push    rbp
0x1800063a2  push    rsi
0x1800063a3  push    rdi
0x1800063a4  push    r12
0x1800063a6  push    r15
0x1800063a8  mov     rbp, rsp
0x1800063ab  sub     rsp, 80h
0x1800063b2  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x1800063b9  xor     r12d, r12d
0x1800063bc  mov     [rbp+var_30], r8d
0x1800063c0  mov     [rbp+BytesReturned], r12d
0x1800063c4  mov     r15, r9
0x1800063c7  mov     [rbp+var_2C], 1
0x1800063ce  mov     rsi, rcx
0x1800063d1  mov     [rbp+var_28], edx
0x1800063d4  mov     [rbp+var_24], r12d
0x1800063d8  movups  [rbp+InBuffer], xmm0
0x1800063dc  cmp     r8d, 3
0x1800063e0  jnz     loc_180006511
0x1800063e6  mov     [rbp+var_24], 1
0x1800063ed  lea     rax, [rcx-1]
0x1800063f1  mov     [rsp+80h+arg_0], rbx
0x1800063f9  mov     edi, 80070515h
0x1800063fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006402  ja      loc_1800067B3
0x180006408  xorps   xmm0, xmm0
0x18000640b  xor     r9d, r9d; lpName
0x18000640e  xor     r8d, r8d; bInitialState
0x180006411  mov     edx, 1; bManualReset
0x180006416  xor     ecx, ecx; lpEventAttributes
0x180006418  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000641c  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180006420  call    cs:__imp_CreateEventW
0x180006427  nop     dword ptr [rax+rax+00h]
0x18000642c  mov     [rbp+Overlapped.hEvent], rax
0x180006430  test    rax, rax
0x180006433  jz      loc_180006642
0x180006439  lea     rax, [rbp+Overlapped]
0x18000643d  mov     r9d, 20h ; ' '; nInBufferSize
0x180006443  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x180006448  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000644c  lea     rax, [rbp+BytesReturned]
0x180006450  mov     edx, 2F0003h; dwIoControlCode
0x180006455  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x18000645a  mov     rcx, rsi; hDevice
0x18000645d  mov     [rsp+80h+nOutBufferSize], r12d; nOutBufferSize
0x180006462  mov     [rsp+80h+lpOutBuffer], r12; lpOutBuffer
0x180006467  call    cs:__imp_DeviceIoControl
0x18000646e  nop     dword ptr [rax+rax+00h]
0x180006473  test    eax, eax
0x180006475  jnz     short loc_1800064E8
0x180006477  call    cs:__imp_GetLastError
0x18000647e  nop     dword ptr [rax+rax+00h]
0x180006483  mov     ebx, eax
0x180006485  test    eax, eax
0x180006487  jle     short loc_180006492
0x180006489  movzx   ebx, ax
0x18000648c  or      ebx, 80070000h
0x180006492  cmp     ebx, 800703E5h
0x180006498  jz      loc_180006686
0x18000649e  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x1800064a2  call    cs:__imp_CloseHandle
0x1800064a9  nop     dword ptr [rax+rax+00h]
0x1800064ae  cmp     ebx, 8007007Ah
0x1800064b4  jz      loc_18000673B
0x1800064ba  cmp     ebx, 800700EAh
0x1800064c0  jz      short loc_180006520
0x1800064c2  test    ebx, ebx
0x1800064c4  mov     edi, ebx
0x1800064c6  mov     eax, 8000FFFFh
0x1800064cb  cmovns  edi, eax
0x1800064ce  mov     eax, edi
0x1800064d0  mov     rbx, [rsp+80h+arg_0]
0x1800064d8  add     rsp, 80h
0x1800064df  pop     r15
0x1800064e1  pop     r12
0x1800064e3  pop     rdi
0x1800064e4  pop     rsi
0x1800064e5  pop     rbp
0x1800064e6  retn
0x1800064e8  mov     rax, [rbp+Overlapped.Internal]
0x1800064ec  sub     rax, 101h
0x1800064f2  jz      loc_180006731
0x1800064f8  sub     rax, 4
0x1800064fc  jz      loc_180006727
0x180006502  cmp     rax, 2
0x180006506  jz      loc_180006720
0x18000650c  mov     ebx, r12d
0x18000650f  jmp     short loc_18000649E
0x180006511  cmp     r8d, 0Dh
0x180006515  jz      loc_1800063E6
0x18000651b  jmp     loc_1800063ED
0x180006520  mov     ecx, [rbp+BytesReturned]; cb
0x180006523  call    cs:__imp_CoTaskMemAlloc
0x18000652a  nop     dword ptr [rax+rax+00h]
0x18000652f  mov     [r15], rax
0x180006532  mov     rbx, rax
0x180006535  test    rax, rax
0x180006538  jz      loc_180006638
0x18000653e  lea     rax, [rsi-1]
0x180006542  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006546  ja      loc_1800067D1
0x18000654c  xorps   xmm0, xmm0
0x18000654f  mov     [rsp+80h+arg_18], r14
0x180006557  mov     r14d, [rbp+BytesReturned]
0x18000655b  xor     r9d, r9d; lpName
0x18000655e  xor     r8d, r8d; bInitialState
0x180006561  mov     edx, 1; bManualReset
0x180006566  xor     ecx, ecx; lpEventAttributes
0x180006568  movups  xmmword ptr [rbp+Overlapped.Internal], xmm0
0x18000656c  movups  xmmword ptr [rbp+Overlapped.10h], xmm0
0x180006570  call    cs:__imp_CreateEventW
0x180006577  nop     dword ptr [rax+rax+00h]
0x18000657c  mov     [rbp+Overlapped.hEvent], rax
0x180006580  test    rax, rax
0x180006583  jz      loc_180006666
0x180006589  lea     rax, [rbp+Overlapped]
0x18000658d  mov     r9d, 20h ; ' '; nInBufferSize
0x180006593  mov     [rsp+80h+lpOverlapped], rax; lpOverlapped
0x180006598  lea     r8, [rbp+InBuffer]; lpInBuffer
0x18000659c  lea     rax, [rbp+BytesReturned]
0x1800065a0  mov     edx, 2F0003h; dwIoControlCode
0x1800065a5  mov     [rsp+80h+lpBytesReturned], rax; lpBytesReturned
0x1800065aa  mov     rcx, rsi; hDevice
0x1800065ad  mov     [rsp+80h+nOutBufferSize], r14d; nOutBufferSize
0x1800065b2  mov     [rsp+80h+lpOutBuffer], rbx; lpOutBuffer
0x1800065b7  call    cs:__imp_DeviceIoControl
0x1800065be  nop     dword ptr [rax+rax+00h]
0x1800065c3  test    eax, eax
0x1800065c5  jnz     short loc_180006613
0x1800065c7  call    cs:__imp_GetLastError
0x1800065ce  nop     dword ptr [rax+rax+00h]
0x1800065d3  mov     edi, eax
0x1800065d5  test    eax, eax
0x1800065d7  jle     short loc_1800065E2
0x1800065d9  movzx   edi, ax
0x1800065dc  or      edi, 80070000h
0x1800065e2  cmp     edi, 800703E5h
0x1800065e8  jz      loc_1800066AF
0x1800065ee  mov     rcx, [rbp+Overlapped.hEvent]; hObject
0x1800065f2  call    cs:__imp_CloseHandle
0x1800065f9  nop     dword ptr [rax+rax+00h]
0x1800065fe  mov     r14, [rsp+80h+arg_18]
0x180006606  test    edi, edi
0x180006608  jns     loc_1800064CE
0x18000660e  jmp     loc_1800067D6
0x180006613  mov     rax, [rbp+Overlapped.Internal]
0x180006617  sub     rax, 101h
0x18000661d  jz      loc_1800067C7
0x180006623  sub     rax, 4
0x180006627  jz      loc_1800067BD
0x18000662d  cmp     rax, 2
0x180006631  jz      short loc_1800065EE
0x180006633  mov     edi, r12d
0x180006636  jmp     short loc_1800065EE
0x180006638  mov     eax, 8007000Eh
0x18000663d  jmp     loc_1800064D0
0x180006642  call    cs:__imp_GetLastError
0x180006649  nop     dword ptr [rax+rax+00h]
0x18000664e  mov     ebx, eax
0x180006650  test    eax, eax
0x180006652  jle     loc_1800064AE
0x180006658  movzx   ebx, ax
0x18000665b  or      ebx, 80070000h
0x180006661  jmp     loc_1800064AE
0x180006666  call    cs:__imp_GetLastError
0x18000666d  nop     dword ptr [rax+rax+00h]
0x180006672  mov     edi, eax
0x180006674  test    eax, eax
0x180006676  jle     short loc_1800065FE
0x180006678  movzx   edi, ax
0x18000667b  or      edi, 80070000h
0x180006681  jmp     loc_1800065FE
0x180006686  mov     r9d, 1; bWait
0x18000668c  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x180006690  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x180006694  mov     rcx, rsi; hFile
0x180006697  call    cs:__imp_GetOverlappedResult
0x18000669e  nop     dword ptr [rax+rax+00h]
0x1800066a3  test    eax, eax
0x1800066a5  jz      short loc_1800066D8
0x1800066a7  mov     ebx, r12d
0x1800066aa  jmp     loc_18000649E
0x1800066af  mov     r9d, 1; bWait
0x1800066b5  lea     r8, [rbp+BytesReturned]; lpNumberOfBytesTransferred
0x1800066b9  lea     rdx, [rbp+Overlapped]; lpOverlapped
0x1800066bd  mov     rcx, rsi; hFile
0x1800066c0  call    cs:__imp_GetOverlappedResult
0x1800066c7  nop     dword ptr [rax+rax+00h]
0x1800066cc  test    eax, eax
0x1800066ce  jz      short loc_1800066FC
0x1800066d0  mov     edi, r12d
0x1800066d3  jmp     loc_1800065EE
0x1800066d8  call    cs:__imp_GetLastError
0x1800066df  nop     dword ptr [rax+rax+00h]
0x1800066e4  mov     ebx, eax
0x1800066e6  test    eax, eax
0x1800066e8  jle     loc_18000649E
0x1800066ee  movzx   ebx, ax
0x1800066f1  or      ebx, 80070000h
0x1800066f7  jmp     loc_18000649E
0x1800066fc  call    cs:__imp_GetLastError
0x180006703  nop     dword ptr [rax+rax+00h]
0x180006708  mov     edi, eax
0x18000670a  test    eax, eax
0x18000670c  jle     loc_1800065EE
0x180006712  movzx   edi, ax
0x180006715  or      edi, 80070000h
0x18000671b  jmp     loc_1800065EE
0x180006720  mov     ebx, edi
0x180006722  jmp     loc_18000649E
0x180006727  mov     ebx, 800700EAh
0x18000672c  jmp     loc_18000649E
0x180006731  mov     ebx, 80070015h
0x180006736  jmp     loc_18000649E
0x18000673b  mov     [rbp+arg_10], r12d
0x18000673f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006746  lea     rax, WPP_GLOBAL_Control
0x18000674d  cmp     rcx, rax
0x180006750  jz      short loc_18000676D
0x180006752  cmp     byte ptr [rcx+19h], 2
0x180006756  jb      short loc_18000676D
0x180006758  mov     rcx, [rcx+10h]
0x18000675c  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180006763  mov     edx, 16h
0x180006768  call    WPP_SF_
0x18000676d  lea     rax, [rbp+BytesReturned]
0x180006771  mov     r9d, 20h ; ' '; nInBufferSize
0x180006777  mov     [rsp+80h+lpBytesReturned], rax; lpNumberOfBytesTransferred
0x18000677c  lea     r8, [rbp+InBuffer]; lpInBuffer
0x180006780  lea     rax, [rbp+arg_10]
0x180006784  mov     [rsp+80h+nOutBufferSize], 4; DWORD
0x18000678c  mov     edx, 2F0003h; dwIoControlCode
0x180006791  mov     [rsp+80h+lpOutBuffer], rax; LPVOID
0x180006796  mov     rcx, rsi; hFile
0x180006799  call    KsSynchronousDeviceControl
0x18000679e  mov     ebx, eax
0x1800067a0  test    eax, eax
0x1800067a2  js      loc_1800064BA
0x1800067a8  mov     eax, [rbp+arg_10]
0x1800067ab  mov     [rbp+BytesReturned], eax
0x1800067ae  jmp     loc_180006520
0x1800067b3  mov     ebx, 80070006h
0x1800067b8  jmp     loc_1800064BA
0x1800067bd  mov     edi, 800700EAh
0x1800067c2  jmp     loc_1800065EE
0x1800067c7  mov     edi, 80070015h
0x1800067cc  jmp     loc_1800065EE
0x1800067d1  mov     edi, 80070006h
0x1800067d6  mov     rcx, [r15]; pv
0x1800067d9  call    cs:__imp_CoTaskMemFree
0x1800067e0  nop     dword ptr [rax+rax+00h]
0x1800067e5  mov     [r15], r12
0x1800067e8  jmp     loc_1800064CE
```
