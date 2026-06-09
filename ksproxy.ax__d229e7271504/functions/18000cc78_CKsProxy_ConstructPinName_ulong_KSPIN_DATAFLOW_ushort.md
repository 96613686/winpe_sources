# CKsProxy::ConstructPinName(ulong,KSPIN_DATAFLOW,ushort * *)

- ea: `0x18000cc78`
- end: `0x18000d429`
- name: `?ConstructPinName@CKsProxy@@QEAAJKW4KSPIN_DATAFLOW@@PEAPEAG@Z`
- size: `1969`
- prototype: `__int64 __fastcall(CKsProxy *__hidden this, unsigned int, enum KSPIN_DATAFLOW, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000b6fc`

## callees

- `0x18000909c`
- `0x18000bde0`
- `0x18000c6f0`
- `0x18000cc78`
- `0x18001f1c4`
- `0x18001f210`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000cd60`
- `KERNEL32!GetLastError` at `0x18000ce5d`
- `KERNEL32!GetLastError` at `0x18000cfa0`
- `KERNEL32!GetLastError` at `0x18000cfc4`
- `KERNEL32!GetLastError` at `0x18000d00d`
- `KERNEL32!GetLastError` at `0x18000d056`
- `KERNEL32!GetLastError` at `0x18000d180`
- `KERNEL32!GetLastError` at `0x18000d28e`
- `KERNEL32!GetLastError` at `0x18000d2d7`
- `KERNEL32!GetLastError` at `0x18000cd60`
- `KERNEL32!GetLastError` at `0x18000ce5d`
- `KERNEL32!GetLastError` at `0x18000cfa0`
- `KERNEL32!GetLastError` at `0x18000cfc4`
- `KERNEL32!GetLastError` at `0x18000d00d`
- `KERNEL32!GetLastError` at `0x18000d056`
- `KERNEL32!GetLastError` at `0x18000d180`
- `KERNEL32!GetLastError` at `0x18000d28e`
- `KERNEL32!GetLastError` at `0x18000d2d7`
- `KERNEL32!CreateEventW` at `0x18000cd07`
- `KERNEL32!CreateEventW` at `0x18000ce03`
- `KERNEL32!CreateEventW` at `0x18000d11e`
- `KERNEL32!CreateEventW` at `0x18000cd07`
- `KERNEL32!CreateEventW` at `0x18000ce03`
- `KERNEL32!CreateEventW` at `0x18000d11e`
- `KERNEL32!CloseHandle` at `0x18000cd8b`
- `KERNEL32!CloseHandle` at `0x18000ce88`
- `KERNEL32!CloseHandle` at `0x18000d1ab`
- `KERNEL32!CloseHandle` at `0x18000cd8b`
- `KERNEL32!CloseHandle` at `0x18000ce88`
- `KERNEL32!CloseHandle` at `0x18000d1ab`
- `KERNEL32!GetOverlappedResult` at `0x18000cff9`
- `KERNEL32!GetOverlappedResult` at `0x18000d042`
- `KERNEL32!GetOverlappedResult` at `0x18000d2c3`
- `KERNEL32!GetOverlappedResult` at `0x18000cff9`
- `KERNEL32!GetOverlappedResult` at `0x18000d042`
- `KERNEL32!GetOverlappedResult` at `0x18000d2c3`
- `KERNEL32!DeviceIoControl` at `0x18000cd4c`
- `KERNEL32!DeviceIoControl` at `0x18000ce49`
- `KERNEL32!DeviceIoControl` at `0x18000d16c`
- `KERNEL32!DeviceIoControl` at `0x18000cd4c`
- `KERNEL32!DeviceIoControl` at `0x18000ce49`
- `KERNEL32!DeviceIoControl` at `0x18000d16c`

## pseudocode

```c
__int64 __fastcall CKsProxy::ConstructPinName(
        CKsProxy *this,
        unsigned int a2,
        enum KSPIN_DATAFLOW a3,
        unsigned __int16 **a4)
{
  unsigned int v4; // r15d
  unsigned int v7; // r14d
  CKsProxy *v8; // rsi
  char *m_FilterHandle; // rdi
  signed int LastError; // eax
  unsigned int v11; // ebx
  unsigned __int16 *v12; // rax
  unsigned __int64 v13; // rdx
  unsigned __int16 *lpOutBuffer; // rbx
  char *v15; // rdi
  DWORD nOutBufferSize; // esi
  signed int v17; // eax
  signed int v18; // ebx
  struct KSMULTIPLE_ITEM *v20; // r14
  unsigned __int64 Count; // rdx
  int v22; // ebx
  DWORD v23; // esi
  GUID v24; // xmm0
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  unsigned int Size; // ecx
  char *v30; // rdi
  signed int v31; // eax
  unsigned __int16 *v32; // rax
  unsigned __int64 v33; // rdx
  signed int v34; // eax
  signed int v35; // eax
  unsigned __int16 *v36; // rax
  int v37; // r12d
  struct KSMULTIPLE_ITEM *v38; // [rsp+48h] [rbp-49h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-41h] BYREF
  GUID InBuffer; // [rsp+70h] [rbp-21h] BYREF
  int v41; // [rsp+80h] [rbp-11h]
  int v42; // [rsp+84h] [rbp-Dh]
  unsigned int v43; // [rsp+88h] [rbp-9h]
  int v44; // [rsp+8Ch] [rbp-5h]
  GUID v45; // [rsp+90h] [rbp-1h] BYREF
  int v46; // [rsp+A0h] [rbp+Fh]
  int v47; // [rsp+A4h] [rbp+13h]
  unsigned int v48; // [rsp+A8h] [rbp+17h]
  int v49; // [rsp+ACh] [rbp+1Bh]
  DWORD BytesReturned; // [rsp+110h] [rbp+7Fh] BYREF

  v4 = 0;
  v38 = 0;
  BytesReturned = 0;
  v7 = a2;
  v8 = this;
  if ( !a4 )
    return 2147500035LL;
  m_FilterHandle = (char *)this->m_FilterHandle;
  v41 = 12;
  v42 = 1;
  v43 = a2;
  v44 = 0;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(m_FilterHandle - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    goto LABEL_24;
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(m_FilterHandle, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &BytesReturned, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v11 = -2147024875;
          goto LABEL_8;
        case 0x105uLL:
          v11 = -2147024662;
          goto LABEL_8;
        case 0x107uLL:
          v11 = -2147023595;
          goto LABEL_8;
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 != -2147023899 )
        goto LABEL_8;
      if ( !GetOverlappedResult(m_FilterHandle, &Overlapped, &BytesReturned, 1) )
      {
        v27 = GetLastError();
        v11 = v27;
        if ( v27 > 0 )
          v11 = (unsigned __int16)v27 | 0x80070000;
        goto LABEL_8;
      }
    }
    v11 = 0;
LABEL_8:
    CloseHandle(Overlapped.hEvent);
    goto LABEL_9;
  }
  v25 = GetLastError();
  v11 = v25;
  if ( v25 > 0 )
    v11 = (unsigned __int16)v25 | 0x80070000;
LABEL_9:
  if ( v11 == -2147024662 )
  {
    v12 = (unsigned __int16 *)operator new[](saturated_mul((unsigned __int64)BytesReturned >> 1, 2u));
    *a4 = v12;
    lpOutBuffer = v12;
    if ( v12 )
    {
      v15 = (char *)v8->m_FilterHandle;
      if ( (unsigned __int64)(v15 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
LABEL_90:
        operator delete(*a4, v13);
        goto LABEL_24;
      }
      nOutBufferSize = BytesReturned;
      memset(&Overlapped, 0, sizeof(Overlapped));
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( !Overlapped.hEvent )
      {
        v26 = GetLastError();
        v18 = v26;
        if ( v26 > 0 )
          v18 = (unsigned __int16)v26 | 0x80070000;
        goto LABEL_18;
      }
      if ( DeviceIoControl(v15, 0x2F0003u, &InBuffer, 0x20u, lpOutBuffer, nOutBufferSize, &BytesReturned, &Overlapped) )
      {
        switch ( Overlapped.Internal )
        {
          case 0x101uLL:
            v18 = -2147024875;
            goto LABEL_17;
          case 0x105uLL:
            v18 = -2147024662;
            goto LABEL_17;
          case 0x107uLL:
            v18 = -2147023595;
            goto LABEL_17;
        }
      }
      else
      {
        v17 = GetLastError();
        v18 = v17;
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        if ( v18 != -2147023899 )
          goto LABEL_17;
        if ( !GetOverlappedResult(v15, &Overlapped, &BytesReturned, 1) )
        {
          v28 = GetLastError();
          v18 = v28;
          if ( v28 > 0 )
            v18 = (unsigned __int16)v28 | 0x80070000;
          goto LABEL_17;
        }
      }
      v18 = 0;
LABEL_17:
      CloseHandle(Overlapped.hEvent);
LABEL_18:
      if ( v18 >= 0 )
        return 0;
      v8 = this;
      goto LABEL_90;
    }
  }
LABEL_24:
  if ( (int)CKsProxy::QueryTopologyItems(v8, 2, &v38) >= 0 )
  {
    v20 = v38;
    if ( !v38 )
      return 2147549183LL;
    Count = v38->Count;
    v22 = -2147467259;
    if ( (_DWORD)Count )
    {
      v23 = BytesReturned;
      v24 = GUID_720d4ac0_7533_11d0_a5d6_28db04c10000;
      while ( 1 )
      {
        if ( v4 < (unsigned int)Count )
          goto LABEL_80;
        while ( 1 )
        {
          Count = v20->Count;
          if ( ++v4 >= (unsigned int)Count )
            goto LABEL_30;
LABEL_80:
          if ( a3 == KSPIN_DATAFLOW_IN )
            break;
          if ( a3 != KSPIN_DATAFLOW_OUT || v20[2 * v4 + 2].Size != -1 || v20[2 * v4 + 2].Count != a2 )
            goto LABEL_82;
          Size = v20[2 * v4 + 1].Size;
LABEL_56:
          if ( Size == -1 )
            goto LABEL_82;
          v45 = v24;
          v46 = 3;
          v47 = 1;
          v30 = (char *)this->m_FilterHandle;
          v48 = Size;
          v49 = 0;
          if ( (unsigned __int64)(v30 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            v22 = -2147024890;
            goto LABEL_65;
          }
          memset(&Overlapped, 0, sizeof(Overlapped));
          Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
          if ( !Overlapped.hEvent )
          {
            v34 = GetLastError();
            v22 = v34;
            if ( v34 > 0 )
              v22 = (unsigned __int16)v34 | 0x80070000;
            goto LABEL_64;
          }
          if ( DeviceIoControl(v30, 0x2F0003u, &v45, 0x20u, 0, 0, &BytesReturned, &Overlapped) )
          {
            switch ( Overlapped.Internal )
            {
              case 0x101uLL:
                v22 = -2147024875;
                goto LABEL_63;
              case 0x105uLL:
                v22 = -2147024662;
                goto LABEL_63;
              case 0x107uLL:
                v22 = -2147023595;
                goto LABEL_63;
            }
          }
          else
          {
            v31 = GetLastError();
            v22 = v31;
            if ( v31 > 0 )
              v22 = (unsigned __int16)v31 | 0x80070000;
            if ( v22 != -2147023899 )
              goto LABEL_63;
            if ( !GetOverlappedResult(v30, &Overlapped, &BytesReturned, 1) )
            {
              v35 = GetLastError();
              v22 = v35;
              if ( v35 > 0 )
                v22 = (unsigned __int16)v35 | 0x80070000;
              goto LABEL_63;
            }
          }
          v22 = 0;
LABEL_63:
          CloseHandle(Overlapped.hEvent);
LABEL_64:
          v23 = BytesReturned;
          v24 = GUID_720d4ac0_7533_11d0_a5d6_28db04c10000;
          if ( v22 < 0 )
          {
LABEL_65:
            if ( v23 < 2 )
            {
              v22 = -2147418113;
            }
            else if ( v22 == -2147024662 )
            {
              v32 = (unsigned __int16 *)operator new[](saturated_mul((unsigned __int64)v23 >> 1, 2u));
              v23 = BytesReturned & 0xFFFFFFFE;
              *a4 = v32;
              BytesReturned = v23;
              if ( v32 )
              {
                v22 = KsSynchronousDeviceControl(
                        (char *)this->m_FilterHandle,
                        0x2F0003u,
                        &v45,
                        0x20u,
                        v32,
                        v23,
                        &BytesReturned);
                if ( v22 >= 0 )
                {
                  if ( BytesReturned < 2 || BytesReturned > v23 )
                  {
                    operator delete(*a4, v33);
                    v22 = -2147418113;
                  }
                  else
                  {
                    Count = (unsigned __int64)BytesReturned >> 1;
                    (*a4)[Count - 1] = 0;
                  }
                }
                else
                {
                  operator delete(*a4, v33);
                }
                if ( v22 >= 0 )
                  goto LABEL_30;
                v23 = BytesReturned;
              }
              else
              {
                v22 = -2147024882;
              }
              v24 = GUID_720d4ac0_7533_11d0_a5d6_28db04c10000;
            }
          }
        }
        if ( v20[2 * v4 + 1].Size == -1 && v20[2 * v4 + 1].Count == a2 )
        {
          Size = v20[2 * v4 + 2].Size;
          goto LABEL_56;
        }
LABEL_82:
        ++v4;
      }
    }
LABEL_30:
    operator delete(v20, Count);
    if ( v22 >= 0 )
      return (unsigned int)v22;
    v7 = a2;
  }
  v36 = (unsigned __int16 *)operator new[](0x40u);
  *a4 = v36;
  if ( v36 )
  {
    v37 = a3 - 1;
    if ( v37 )
    {
      if ( v37 == 1 )
        StringCchPrintfW(v36, 0x20u, L"Output%u", v7);
    }
    else
    {
      StringCchPrintfW(v36, 0x20u, L"Input%u", v7);
    }
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000cc78  mov     rax, rsp
0x18000cc7b  mov     [rax+18h], rbx
0x18000cc7f  mov     [rax+10h], edx
0x18000cc82  mov     [rax+8], rcx
0x18000cc86  push    rbp
0x18000cc87  push    rsi
0x18000cc88  push    rdi
0x18000cc89  push    r12
0x18000cc8b  push    r13
0x18000cc8d  push    r14
0x18000cc8f  push    r15
0x18000cc91  lea     rbp, [rax-5Fh]
0x18000cc95  sub     rsp, 0B0h
0x18000cc9c  xor     r15d, r15d
0x18000cc9f  mov     r13, r9
0x18000cca2  mov     [rbp+57h+var_A0], r15
0x18000cca6  mov     r12d, r8d
0x18000cca9  mov     [rbp+57h+BytesReturned], r15d
0x18000ccad  mov     r14d, edx
0x18000ccb0  mov     rsi, rcx
0x18000ccb3  test    r9, r9
0x18000ccb6  jz      loc_18000CF8C
0x18000ccbc  mov     rdi, [rsi+170h]
0x18000ccc3  lea     ecx, [r15+1]
0x18000ccc7  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x18000ccce  mov     [rbp+57h+var_68], 0Ch
0x18000ccd5  mov     [rbp+57h+var_64], ecx
0x18000ccd8  lea     rax, [rdi-1]
0x18000ccdc  mov     [rbp+57h+var_60], edx
0x18000ccdf  mov     [rbp+57h+var_5C], r15d
0x18000cce3  movdqu  [rbp+57h+InBuffer], xmm0
0x18000cce8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ccec  ja      loc_18000CEE6
0x18000ccf2  xorps   xmm0, xmm0
0x18000ccf5  mov     edx, ecx; bManualReset
0x18000ccf7  xor     ecx, ecx; lpEventAttributes
0x18000ccf9  xor     r9d, r9d; lpName
0x18000ccfc  xor     r8d, r8d; bInitialState
0x18000ccff  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000cd03  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18000cd07  call    cs:__imp_CreateEventW
0x18000cd0e  nop     dword ptr [rax+rax+00h]
0x18000cd13  mov     [rbp+57h+Overlapped.hEvent], rax
0x18000cd17  test    rax, rax
0x18000cd1a  jz      loc_18000CFA0
0x18000cd20  lea     rax, [rbp+57h+Overlapped]
0x18000cd24  mov     edx, 2F0003h; dwIoControlCode
0x18000cd29  mov     [rsp+38h], rax; lpOverlapped
0x18000cd2e  lea     r9d, [r15+20h]; nInBufferSize
0x18000cd32  lea     rax, [rbp+57h+BytesReturned]
0x18000cd36  mov     rcx, rdi; hDevice
0x18000cd39  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000cd3e  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000cd42  mov     [rsp+0E0h+nOutBufferSize], r15d; nOutBufferSize
0x18000cd47  mov     [rsp+0E0h+lpOutBuffer], r15; lpOutBuffer
0x18000cd4c  call    cs:__imp_DeviceIoControl
0x18000cd53  nop     dword ptr [rax+rax+00h]
0x18000cd58  test    eax, eax
0x18000cd5a  jnz     loc_18000CEBA
0x18000cd60  call    cs:__imp_GetLastError
0x18000cd67  nop     dword ptr [rax+rax+00h]
0x18000cd6c  mov     ebx, eax
0x18000cd6e  test    eax, eax
0x18000cd70  jle     short loc_18000CD7B
0x18000cd72  movzx   ebx, ax
0x18000cd75  or      ebx, 80070000h
0x18000cd7b  cmp     ebx, 800703E5h
0x18000cd81  jz      loc_18000CFE8
0x18000cd87  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x18000cd8b  call    cs:__imp_CloseHandle
0x18000cd92  nop     dword ptr [rax+rax+00h]
0x18000cd97  cmp     ebx, 800700EAh
0x18000cd9d  jnz     loc_18000CEE6
0x18000cda3  mov     ecx, [rbp+57h+BytesReturned]
0x18000cda6  mov     eax, 2
0x18000cdab  shr     rcx, 1
0x18000cdae  mul     rcx
0x18000cdb1  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000cdb8  cmovb   rax, rcx
0x18000cdbc  mov     rcx, rax; unsigned __int64
0x18000cdbf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000cdc4  mov     [r13+0], rax
0x18000cdc8  mov     rbx, rax
0x18000cdcb  test    rax, rax
0x18000cdce  jz      loc_18000CEE6
0x18000cdd4  mov     rdi, [rsi+170h]
0x18000cddb  lea     rcx, [rdi-1]
0x18000cddf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000cde3  ja      loc_18000D35A
0x18000cde9  mov     esi, [rbp+57h+BytesReturned]
0x18000cdec  xorps   xmm0, xmm0
0x18000cdef  xor     r9d, r9d; lpName
0x18000cdf2  xor     r8d, r8d; bInitialState
0x18000cdf5  xor     ecx, ecx; lpEventAttributes
0x18000cdf7  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000cdfb  lea     edx, [r9+1]; bManualReset
0x18000cdff  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18000ce03  call    cs:__imp_CreateEventW
0x18000ce0a  nop     dword ptr [rax+rax+00h]
0x18000ce0f  mov     [rbp+57h+Overlapped.hEvent], rax
0x18000ce13  test    rax, rax
0x18000ce16  jz      loc_18000CFC4
0x18000ce1c  lea     rax, [rbp+57h+Overlapped]
0x18000ce20  mov     r9d, 20h ; ' '; nInBufferSize
0x18000ce26  mov     [rsp+38h], rax; lpOverlapped
0x18000ce2b  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000ce2f  lea     rax, [rbp+57h+BytesReturned]
0x18000ce33  mov     edx, 2F0003h; dwIoControlCode
0x18000ce38  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000ce3d  mov     rcx, rdi; hDevice
0x18000ce40  mov     [rsp+0E0h+nOutBufferSize], esi; nOutBufferSize
0x18000ce44  mov     [rsp+0E0h+lpOutBuffer], rbx; lpOutBuffer
0x18000ce49  call    cs:__imp_DeviceIoControl
0x18000ce50  nop     dword ptr [rax+rax+00h]
0x18000ce55  test    eax, eax
0x18000ce57  jnz     loc_18000CF60
0x18000ce5d  call    cs:__imp_GetLastError
0x18000ce64  nop     dword ptr [rax+rax+00h]
0x18000ce69  mov     ebx, eax
0x18000ce6b  test    eax, eax
0x18000ce6d  jle     short loc_18000CE78
0x18000ce6f  movzx   ebx, ax
0x18000ce72  or      ebx, 80070000h
0x18000ce78  cmp     ebx, 800703E5h
0x18000ce7e  jz      loc_18000D031
0x18000ce84  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x18000ce88  call    cs:__imp_CloseHandle
0x18000ce8f  nop     dword ptr [rax+rax+00h]
0x18000ce94  test    ebx, ebx
0x18000ce96  js      loc_18000D356
0x18000ce9c  xor     eax, eax
0x18000ce9e  mov     rbx, [rsp+0E0h+arg_10]
0x18000cea6  add     rsp, 0B0h
0x18000cead  pop     r15
0x18000ceaf  pop     r14
0x18000ceb1  pop     r13
0x18000ceb3  pop     r12
0x18000ceb5  pop     rdi
0x18000ceb6  pop     rsi
0x18000ceb7  pop     rbp
0x18000ceb8  retn
0x18000ceba  mov     rax, [rbp+57h+Overlapped.Internal]
0x18000cebe  sub     rax, 101h
0x18000cec4  jz      loc_18000D32E
0x18000ceca  sub     rax, 4
0x18000cece  jz      loc_18000D324
0x18000ced4  cmp     rax, 2
0x18000ced8  jz      loc_18000D31A
0x18000cede  mov     ebx, r15d
0x18000cee1  jmp     loc_18000CD87
0x18000cee6  lea     r8, [rbp+57h+var_A0]; struct KSMULTIPLE_ITEM **
0x18000ceea  mov     edx, 2; unsigned int
0x18000ceef  mov     rcx, rsi; this
0x18000cef2  call    ?QueryTopologyItems@CKsProxy@@QEAAJKPEAPEAUKSMULTIPLE_ITEM@@@Z; CKsProxy::QueryTopologyItems(ulong,KSMULTIPLE_ITEM * *)
0x18000cef7  test    eax, eax
0x18000cef9  js      loc_18000D3D8
0x18000ceff  mov     r14, [rbp+57h+var_A0]
0x18000cf03  test    r14, r14
0x18000cf06  jz      loc_18000CF96
0x18000cf0c  mov     edx, [r14+4]
0x18000cf10  mov     ebx, 80004005h
0x18000cf15  test    edx, edx
0x18000cf17  jz      short loc_18000CF46
0x18000cf19  mov     esi, [rbp+57h+BytesReturned]
0x18000cf1c  or      r8d, 0FFFFFFFFh
0x18000cf20  movups  xmm0, xmmword ptr cs:_GUID_720d4ac0_7533_11d0_a5d6_28db04c10000.Data1
0x18000cf27  cmp     r15d, edx
0x18000cf2a  jb      loc_18000D2FB
0x18000cf30  mov     edx, [r14+4]; unsigned __int64
0x18000cf34  inc     r15d
0x18000cf37  mov     r8d, 0FFFFFFFFh
0x18000cf3d  cmp     r15d, edx
0x18000cf40  jb      loc_18000D2FB
0x18000cf46  mov     rcx, r14; void *
0x18000cf49  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf4e  xor     r15d, r15d
0x18000cf51  test    ebx, ebx
0x18000cf53  js      loc_18000D3D4
0x18000cf59  mov     eax, ebx
0x18000cf5b  jmp     loc_18000CE9E
0x18000cf60  mov     rax, [rbp+57h+Overlapped.Internal]
0x18000cf64  sub     rax, 101h
0x18000cf6a  jz      loc_18000D34C
0x18000cf70  sub     rax, 4
0x18000cf74  jz      loc_18000D342
0x18000cf7a  cmp     rax, 2
0x18000cf7e  jz      loc_18000D338
0x18000cf84  mov     ebx, r15d
0x18000cf87  jmp     loc_18000CE84
0x18000cf8c  mov     eax, 80004003h
0x18000cf91  jmp     loc_18000CE9E
0x18000cf96  mov     eax, 8000FFFFh
0x18000cf9b  jmp     loc_18000CE9E
0x18000cfa0  call    cs:__imp_GetLastError
0x18000cfa7  nop     dword ptr [rax+rax+00h]
0x18000cfac  mov     ebx, eax
0x18000cfae  test    eax, eax
0x18000cfb0  jle     loc_18000CD97
0x18000cfb6  movzx   ebx, ax
0x18000cfb9  or      ebx, 80070000h
0x18000cfbf  jmp     loc_18000CD97
0x18000cfc4  call    cs:__imp_GetLastError
0x18000cfcb  nop     dword ptr [rax+rax+00h]
0x18000cfd0  mov     ebx, eax
0x18000cfd2  test    eax, eax
0x18000cfd4  jle     loc_18000CE94
0x18000cfda  movzx   ebx, ax
0x18000cfdd  or      ebx, 80070000h
0x18000cfe3  jmp     loc_18000CE94
0x18000cfe8  mov     r9d, 1; bWait
0x18000cfee  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x18000cff2  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18000cff6  mov     rcx, rdi; hFile
0x18000cff9  call    cs:__imp_GetOverlappedResult
0x18000d000  nop     dword ptr [rax+rax+00h]
0x18000d005  test    eax, eax
0x18000d007  jnz     loc_18000CEDE
0x18000d00d  call    cs:__imp_GetLastError
0x18000d014  nop     dword ptr [rax+rax+00h]
0x18000d019  mov     ebx, eax
0x18000d01b  test    eax, eax
0x18000d01d  jle     loc_18000CD87
0x18000d023  movzx   ebx, ax
0x18000d026  or      ebx, 80070000h
0x18000d02c  jmp     loc_18000CD87
0x18000d031  mov     r9d, 1; bWait
0x18000d037  lea     r8, [rbp+57h+BytesReturned]; lpNumberOfBytesTransferred
0x18000d03b  lea     rdx, [rbp+57h+Overlapped]; lpOverlapped
0x18000d03f  mov     rcx, rdi; hFile
0x18000d042  call    cs:__imp_GetOverlappedResult
0x18000d049  nop     dword ptr [rax+rax+00h]
0x18000d04e  test    eax, eax
0x18000d050  jnz     loc_18000CF84
0x18000d056  call    cs:__imp_GetLastError
0x18000d05d  nop     dword ptr [rax+rax+00h]
0x18000d062  mov     ebx, eax
0x18000d064  test    eax, eax
0x18000d066  jle     loc_18000CE84
0x18000d06c  movzx   ebx, ax
0x18000d06f  or      ebx, 80070000h
0x18000d075  jmp     loc_18000CE84
0x18000d07a  mov     eax, [rbp+57h+BytesReturned]
0x18000d07d  cmp     eax, 2
0x18000d080  jb      loc_18000D3C1
0x18000d086  cmp     eax, esi
0x18000d088  ja      loc_18000D3C1
0x18000d08e  mov     rcx, [r13+0]
0x18000d092  mov     edx, eax
0x18000d094  shr     rdx, 1
0x18000d097  xor     eax, eax
0x18000d099  mov     [rcx+rdx*2-2], ax
0x18000d09e  test    ebx, ebx
0x18000d0a0  jns     loc_18000CF46
0x18000d0a6  mov     esi, [rbp+57h+BytesReturned]
0x18000d0a9  movups  xmm0, xmmword ptr cs:_GUID_720d4ac0_7533_11d0_a5d6_28db04c10000.Data1
0x18000d0b0  jmp     loc_18000CF30
0x18000d0b5  mov     ecx, [rbp+57h+arg_8]
0x18000d0b8  cmp     [r14+rax*8+0Ch], ecx
0x18000d0bd  jnz     loc_18000D312
0x18000d0c3  mov     ecx, [r14+rax*8+10h]
0x18000d0c8  cmp     ecx, r8d
0x18000d0cb  jz      loc_18000D312
0x18000d0d1  mov     rax, [rbp+57h+arg_0]
0x18000d0d5  movdqu  [rbp+57h+var_58], xmm0
0x18000d0da  mov     [rbp+57h+var_48], 3
0x18000d0e1  mov     [rbp+57h+var_44], 1
0x18000d0e8  mov     rdi, [rax+170h]
0x18000d0ef  mov     [rbp+57h+var_40], ecx
0x18000d0f2  mov     [rbp+57h+var_3C], 0
0x18000d0f9  lea     rax, [rdi-1]
0x18000d0fd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d101  ja      loc_18000D3AD
0x18000d107  xorps   xmm0, xmm0
0x18000d10a  xor     r9d, r9d; lpName
0x18000d10d  xor     r8d, r8d; bInitialState
0x18000d110  xor     ecx, ecx; lpEventAttributes
0x18000d112  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000d116  lea     edx, [r9+1]; bManualReset
0x18000d11a  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18000d11e  call    cs:__imp_CreateEventW
0x18000d125  nop     dword ptr [rax+rax+00h]
0x18000d12a  mov     [rbp+57h+Overlapped.hEvent], rax
0x18000d12e  test    rax, rax
0x18000d131  jz      loc_18000D28E
0x18000d137  lea     rax, [rbp+57h+Overlapped]
0x18000d13b  mov     r9d, 20h ; ' '; nInBufferSize
0x18000d141  mov     [rsp+38h], rax; lpOverlapped
0x18000d146  lea     r8, [rbp+57h+var_58]; lpInBuffer
0x18000d14a  lea     rax, [rbp+57h+BytesReturned]
0x18000d14e  mov     edx, 2F0003h; dwIoControlCode
0x18000d153  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000d158  mov     rcx, rdi; hDevice
0x18000d15b  mov     [rsp+0E0h+nOutBufferSize], 0; nOutBufferSize
0x18000d163  mov     [rsp+0E0h+lpOutBuffer], 0; lpOutBuffer
0x18000d16c  call    cs:__imp_DeviceIoControl
0x18000d173  nop     dword ptr [rax+rax+00h]
0x18000d178  test    eax, eax
0x18000d17a  jnz     loc_18000D21A
0x18000d180  call    cs:__imp_GetLastError
0x18000d187  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
