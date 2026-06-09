# KsGetMediaType

- ea: `0x180005850`
- end: `0x18000638e`
- name: `KsGetMediaType`
- size: `2878`
- prototype: `__int64 __fastcall(int, __int64, char *, int)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x1800042b0`
- `0x1800043d0`
- `0x1800273d0`
- `0x18002f8d0`
- `0x180038344`

## callees

- `0x180005850`
- `0x1800063a0`
- `0x18000bde0`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f210`
- `0x180025860`
- `0x180044850`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000593b`
- `KERNEL32!GetLastError` at `0x180005b1d`
- `KERNEL32!GetLastError` at `0x180005c11`
- `KERNEL32!GetLastError` at `0x180005e63`
- `KERNEL32!GetLastError` at `0x180005ef4`
- `KERNEL32!GetLastError` at `0x180005f18`
- `KERNEL32!GetLastError` at `0x180005f3c`
- `KERNEL32!GetLastError` at `0x180005f60`
- `KERNEL32!GetLastError` at `0x180006032`
- `KERNEL32!GetLastError` at `0x180006056`
- `KERNEL32!GetLastError` at `0x18000607a`
- `KERNEL32!GetLastError` at `0x18000609e`
- `KERNEL32!GetLastError` at `0x18000593b`
- `KERNEL32!GetLastError` at `0x180005b1d`
- `KERNEL32!GetLastError` at `0x180005c11`
- `KERNEL32!GetLastError` at `0x180005e63`
- `KERNEL32!GetLastError` at `0x180005ef4`
- `KERNEL32!GetLastError` at `0x180005f18`
- `KERNEL32!GetLastError` at `0x180005f3c`
- `KERNEL32!GetLastError` at `0x180005f60`
- `KERNEL32!GetLastError` at `0x180006032`
- `KERNEL32!GetLastError` at `0x180006056`
- `KERNEL32!GetLastError` at `0x18000607a`
- `KERNEL32!GetLastError` at `0x18000609e`
- `KERNEL32!CreateEventW` at `0x1800058e4`
- `KERNEL32!CreateEventW` at `0x180005ac5`
- `KERNEL32!CreateEventW` at `0x180005bb7`
- `KERNEL32!CreateEventW` at `0x180005e0d`
- `KERNEL32!CreateEventW` at `0x1800058e4`
- `KERNEL32!CreateEventW` at `0x180005ac5`
- `KERNEL32!CreateEventW` at `0x180005bb7`
- `KERNEL32!CreateEventW` at `0x180005e0d`
- `KERNEL32!CloseHandle` at `0x180005966`
- `KERNEL32!CloseHandle` at `0x180005b48`
- `KERNEL32!CloseHandle` at `0x180005c3c`
- `KERNEL32!CloseHandle` at `0x180005e8e`
- `KERNEL32!CloseHandle` at `0x180005966`
- `KERNEL32!CloseHandle` at `0x180005b48`
- `KERNEL32!CloseHandle` at `0x180005c3c`
- `KERNEL32!CloseHandle` at `0x180005e8e`
- `KERNEL32!GetOverlappedResult` at `0x180005f95`
- `KERNEL32!GetOverlappedResult` at `0x180005fc2`
- `KERNEL32!GetOverlappedResult` at `0x180005fee`
- `KERNEL32!GetOverlappedResult` at `0x18000601a`
- `KERNEL32!GetOverlappedResult` at `0x180005f95`
- `KERNEL32!GetOverlappedResult` at `0x180005fc2`
- `KERNEL32!GetOverlappedResult` at `0x180005fee`
- `KERNEL32!GetOverlappedResult` at `0x18000601a`
- `KERNEL32!DeviceIoControl` at `0x18000592b`
- `KERNEL32!DeviceIoControl` at `0x180005b09`
- `KERNEL32!DeviceIoControl` at `0x180005bfd`
- `KERNEL32!DeviceIoControl` at `0x180005e53`
- `KERNEL32!DeviceIoControl` at `0x18000592b`
- `KERNEL32!DeviceIoControl` at `0x180005b09`
- `KERNEL32!DeviceIoControl` at `0x180005bfd`
- `KERNEL32!DeviceIoControl` at `0x180005e53`
- `ole32!CoTaskMemAlloc` at `0x180005cb3`
- `ole32!CoTaskMemAlloc` at `0x180005dc8`
- `ole32!CoTaskMemAlloc` at `0x180005cb3`
- `ole32!CoTaskMemAlloc` at `0x180005dc8`
- `ole32!CoTaskMemFree` at `0x180005d42`
- `ole32!CoTaskMemFree` at `0x180006192`
- `ole32!CoTaskMemFree` at `0x1800061d0`
- `ole32!CoTaskMemFree` at `0x1800062b2`
- `ole32!CoTaskMemFree` at `0x180006308`
- `ole32!CoTaskMemFree` at `0x180005d42`
- `ole32!CoTaskMemFree` at `0x180006192`
- `ole32!CoTaskMemFree` at `0x1800061d0`
- `ole32!CoTaskMemFree` at `0x1800062b2`
- `ole32!CoTaskMemFree` at `0x180006308`

## pseudocode

```c
__int64 __fastcall KsGetMediaType(int a1, __int64 a2, char *a3, int a4)
{
  _DWORD *v4; // r12
  __int64 v6; // r13
  unsigned int v7; // edi
  signed int LastError; // eax
  int v9; // ebx
  __int64 result; // rax
  unsigned int *v11; // rsi
  unsigned int v12; // ecx
  unsigned int *v13; // rbx
  DWORD v14; // r15d
  _DWORD *v15; // rax
  _DWORD *v16; // r14
  _DWORD *v17; // rdi
  void *v18; // rcx
  int v19; // eax
  unsigned __int64 v20; // rdx
  HANDLE v21; // rbx
  int v22; // edi
  signed int v23; // eax
  DWORD v24; // eax
  unsigned __int64 v25; // rdx
  int *lpOutBuffer; // rbx
  DWORD nOutBufferSize; // edi
  DWORD v28; // r9d
  HANDLE v29; // r15
  signed int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  unsigned int v34; // r13d
  size_t v35; // r12
  LPVOID v36; // rax
  __int64 v37; // rcx
  void *v38; // r15
  unsigned int v39; // eax
  DWORD v40; // ebx
  signed int v41; // eax
  signed int v42; // ebx
  signed int v43; // eax
  signed int v44; // eax
  signed int v45; // eax
  signed int v46; // eax
  signed int v47; // eax
  signed int v48; // eax
  signed int v49; // eax
  signed int v50; // eax
  __int64 v51; // rcx
  _QWORD *v52; // rax
  DWORD v53; // [rsp+48h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-31h]
  GUID InBuffer; // [rsp+58h] [rbp-29h] BYREF
  int v56; // [rsp+68h] [rbp-19h]
  int v57; // [rsp+6Ch] [rbp-15h]
  int v58; // [rsp+70h] [rbp-11h]
  int v59; // [rsp+74h] [rbp-Dh]
  struct _OVERLAPPED Overlapped; // [rsp+78h] [rbp-9h] BYREF
  DWORD BytesReturned; // [rsp+E8h] [rbp+67h] BYREF
  __int64 v62; // [rsp+F0h] [rbp+6Fh]
  HANDLE hDevice; // [rsp+F8h] [rbp+77h]
  int v64; // [rsp+100h] [rbp+7Fh]

  v64 = a4;
  hDevice = a3;
  v62 = a2;
  v4 = 0;
  pv = 0;
  v6 = a2;
  v7 = a1;
  if ( a1 < 0 )
    return 2147942487LL;
  BytesReturned = 0;
  v56 = 13;
  v57 = 1;
  v58 = a4;
  v59 = 1;
  InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v9 = -2147024890;
    goto LABEL_10;
  }
  memset(&Overlapped, 0, 24);
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(a3, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &BytesReturned, &Overlapped) )
    {
      switch ( Overlapped.Internal )
      {
        case 0x101uLL:
          v9 = -2147024875;
          break;
        case 0x105uLL:
          v9 = -2147024662;
          break;
        case 0x107uLL:
          v9 = -2147023595;
          break;
        default:
          v9 = 0;
          break;
      }
    }
    else
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 == -2147023899 )
      {
        if ( GetOverlappedResult(a3, &Overlapped, &BytesReturned, 1) )
        {
          v9 = 0;
        }
        else
        {
          v47 = GetLastError();
          v9 = v47;
          if ( v47 > 0 )
            v9 = (unsigned __int16)v47 | 0x80070000;
        }
      }
    }
    CloseHandle(Overlapped.hEvent);
  }
  else
  {
    v43 = GetLastError();
    v9 = v43;
    if ( v43 > 0 )
      v9 = (unsigned __int16)v43 | 0x80070000;
  }
  if ( v9 != -2147024774 )
    goto LABEL_10;
  v53 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
  v9 = KsSynchronousDeviceControl(a3, 0x2F0003u, &InBuffer, 0x20u, &v53, 4u, &BytesReturned);
  if ( v9 < 0 )
  {
LABEL_10:
    if ( v9 != -2147024662 )
      goto LABEL_11;
    goto LABEL_75;
  }
  BytesReturned = v53;
LABEL_75:
  pv = CoTaskMemAlloc(BytesReturned);
  v11 = (unsigned int *)pv;
  if ( pv )
  {
    if ( (unsigned __int64)(a3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v40 = BytesReturned;
      memset(&Overlapped, 0, sizeof(Overlapped));
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        if ( DeviceIoControl(a3, 0x2F0003u, &InBuffer, 0x20u, v11, v40, &BytesReturned, &Overlapped) )
        {
          if ( Overlapped.Internal == 257 )
          {
            v42 = -2147024875;
          }
          else if ( Overlapped.Internal == 261 )
          {
            v42 = -2147024662;
          }
          else
          {
            v42 = Overlapped.Internal == 263 ? -2147023595 : 0;
          }
        }
        else
        {
          v41 = GetLastError();
          v42 = v41;
          if ( v41 > 0 )
            v42 = (unsigned __int16)v41 | 0x80070000;
          if ( v42 == -2147023899 )
          {
            if ( GetOverlappedResult(a3, &Overlapped, &BytesReturned, 1) )
            {
              v42 = 0;
            }
            else
            {
              v48 = GetLastError();
              v42 = v48;
              if ( v48 > 0 )
                v42 = (unsigned __int16)v48 | 0x80070000;
            }
          }
        }
        CloseHandle(Overlapped.hEvent);
      }
      else
      {
        v46 = GetLastError();
        v42 = v46;
        if ( v46 > 0 )
          v42 = (unsigned __int16)v46 | 0x80070000;
      }
      if ( v42 >= 0 )
        goto LABEL_17;
    }
    CoTaskMemFree(v11);
    pv = 0;
  }
LABEL_11:
  result = KsGetMultiplePinFactoryItems(a3);
  if ( (int)result < 0 )
    return result;
  v11 = (unsigned int *)pv;
LABEL_17:
  if ( !v11 )
    return 2147549183LL;
  v12 = v11[1];
  if ( v7 < v12 )
  {
    BytesReturned = 0;
    v13 = v11 + 2;
    while ( v7 )
    {
      if ( (v13[1] & 2) != 0 )
      {
        v11[1] = --v12;
        if ( v7 >= v12 )
        {
          CoTaskMemFree(v11);
          return 262403;
        }
        v13 = (unsigned int *)((char *)v13 + ((*v13 + 7) & 0xFFFFFFF8));
      }
      v13 = (unsigned int *)((char *)v13 + ((*v13 + 7) & 0xFFFFFFF8));
      v11[1] = --v12;
      --v7;
    }
    v14 = *v13 + 40;
    if ( (v13[1] & 2) != 0 )
    {
      v4 = (unsigned int *)((char *)v13 + ((*v13 + 7) & 0xFFFFFFF8));
      v14 = *v4 + ((*v13 + 47) & 0xFFFFFFF8);
    }
    pv = v4;
    v15 = operator new[](v14);
    v16 = v15;
    if ( !v15 )
    {
LABEL_141:
      CoTaskMemFree(v11);
      return 2147942414LL;
    }
    v15[4] = 4;
    v17 = v15 + 8;
    v15[5] = 1;
    v18 = v15 + 10;
    *(GUID *)v15 = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    v15[6] = v64;
    v15[7] = 0;
    v19 = *v13 + 8;
    v16[9] = 1;
    v16[8] = v19;
    memcpy_0(v18, v13, *v13);
    if ( v4 )
    {
      v51 = *v4 + ((*v17 + 7) & 0xFFFFFFF8);
      ++v16[9];
      *v17 = v51;
      memcpy_0((char *)v17 + v51 - (unsigned int)*v4, v4, (unsigned int)*v4);
    }
    v21 = hDevice;
    if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v22 = -2147024890;
    }
    else
    {
      memset(&Overlapped, 0, sizeof(Overlapped));
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        v22 = 0;
        if ( DeviceIoControl(v21, 0x2F0003u, v16, v14, 0, 0, &BytesReturned, &Overlapped) )
        {
          switch ( Overlapped.Internal )
          {
            case 0x101uLL:
              v22 = -2147024875;
              break;
            case 0x105uLL:
              v22 = -2147024662;
              break;
            case 0x107uLL:
              v22 = -2147023595;
              break;
          }
        }
        else
        {
          v23 = GetLastError();
          v22 = v23;
          if ( v23 > 0 )
            v22 = (unsigned __int16)v23 | 0x80070000;
          if ( v22 == -2147023899 )
          {
            if ( GetOverlappedResult(v21, &Overlapped, &BytesReturned, 1) )
            {
              v22 = 0;
            }
            else
            {
              v49 = GetLastError();
              v22 = v49;
              if ( v49 > 0 )
                v22 = (unsigned __int16)v49 | 0x80070000;
            }
          }
        }
        CloseHandle(Overlapped.hEvent);
      }
      else
      {
        v44 = GetLastError();
        v22 = v44;
        if ( v44 > 0 )
          v22 = (unsigned __int16)v44 | 0x80070000;
      }
      if ( v22 == -2147024774 )
      {
        v53 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
        v22 = KsSynchronousDeviceControl((char *)v21, 0x2F0003u, v16, v14, &v53, 4u, &BytesReturned);
        if ( v22 >= 0 )
        {
          v24 = v53;
          BytesReturned = v53;
LABEL_38:
          if ( v24 < 0x40 )
          {
            v22 = -2147418113;
            goto LABEL_64;
          }
          lpOutBuffer = (int *)operator new[](v24);
          if ( lpOutBuffer )
          {
            if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
            {
              v22 = -2147024890;
            }
            else
            {
              nOutBufferSize = BytesReturned;
              memset(&Overlapped, 0, sizeof(Overlapped));
              Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
              if ( Overlapped.hEvent )
              {
                v28 = v14;
                v29 = hDevice;
                if ( DeviceIoControl(
                       hDevice,
                       0x2F0003u,
                       v16,
                       v28,
                       lpOutBuffer,
                       nOutBufferSize,
                       &BytesReturned,
                       &Overlapped) )
                {
                  switch ( Overlapped.Internal )
                  {
                    case 0x101uLL:
                      v22 = -2147024875;
                      break;
                    case 0x105uLL:
                      v22 = -2147024662;
                      break;
                    case 0x107uLL:
                      v22 = -2147023595;
                      break;
                    default:
                      v22 = 0;
                      break;
                  }
                }
                else
                {
                  v30 = GetLastError();
                  v22 = v30;
                  if ( v30 > 0 )
                    v22 = (unsigned __int16)v30 | 0x80070000;
                  if ( v22 == -2147023899 )
                  {
                    if ( GetOverlappedResult(v29, &Overlapped, &BytesReturned, 1) )
                    {
                      v22 = 0;
                    }
                    else
                    {
                      v50 = GetLastError();
                      v22 = v50;
                      if ( v50 > 0 )
                        v22 = (unsigned __int16)v50 | 0x80070000;
                    }
                  }
                }
                CloseHandle(Overlapped.hEvent);
              }
              else
              {
                v45 = GetLastError();
                v22 = v45;
                if ( v45 > 0 )
                  v22 = (unsigned __int16)v45 | 0x80070000;
              }
              if ( v22 < 0 )
                goto LABEL_63;
              if ( *lpOutBuffer == BytesReturned && (unsigned int)*lpOutBuffer >= 0x40 )
              {
                *(_OWORD *)v6 = *((_OWORD *)lpOutBuffer + 1);
                *(_OWORD *)(v6 + 16) = *((_OWORD *)lpOutBuffer + 2);
                *(_DWORD *)(v6 + 36) = lpOutBuffer[1] & 1;
                v31 = lpOutBuffer[2];
                if ( v31 )
                {
                  *(_DWORD *)(v6 + 40) = v31;
                  v32 = 1;
                }
                else
                {
                  v32 = 0;
                }
                *(_DWORD *)(v6 + 32) = v32;
                v33 = *lpOutBuffer;
                if ( (unsigned int)*lpOutBuffer <= 0x40 )
                  goto LABEL_62;
                v34 = v33 - 64;
                v35 = (unsigned int)(v33 - 64);
                if ( *(_DWORD *)(v62 + 72) == v33 - 64 )
                  goto LABEL_58;
                v36 = CoTaskMemAlloc(v34);
                v37 = v62;
                v38 = v36;
                v39 = *(_DWORD *)(v62 + 72);
                if ( v38 )
                {
                  if ( v39 )
                  {
                    CoTaskMemFree(*(LPVOID *)(v62 + 80));
                    v37 = v62;
                  }
                  *(_DWORD *)(v37 + 72) = v34;
                  v6 = v62;
                  *(_QWORD *)(v62 + 80) = v38;
                  goto LABEL_60;
                }
                if ( v34 <= v39 )
                {
LABEL_58:
                  v6 = v62;
                  v25 = 80;
                  if ( *(_QWORD *)(v62 + 80) )
                  {
                    v38 = *(void **)(v62 + 80);
LABEL_60:
                    memcpy_0(v38, lpOutBuffer + 16, v35);
LABEL_61:
                    v4 = pv;
LABEL_62:
                    *(_OWORD *)(v6 + 44) = *((_OWORD *)lpOutBuffer + 3);
                    if ( (lpOutBuffer[1] & 2) != 0 )
                    {
                      v52 = operator new(0x18u);
                      if ( v52 )
                      {
                        v52[1] = 0;
                        *v52 = &CMediaTypeAttributes::`vftable';
                        *((_DWORD *)v52 + 4) = 1;
                        *(_QWORD *)(v6 + 64) = v52;
                        v22 = (*(__int64 (__fastcall **)(_QWORD *, _DWORD *))(*v52 + 32LL))(v52, v4);
                      }
                      else
                      {
                        v22 = -2147024882;
                      }
                    }
                    goto LABEL_63;
                  }
                }
                else
                {
                  v6 = v62;
                }
                v22 = -2147024882;
                goto LABEL_61;
              }
              v22 = -2147418113;
            }
LABEL_63:
            operator delete(lpOutBuffer, v25);
            goto LABEL_64;
          }
          operator delete(v16, v25);
          goto LABEL_141;
        }
      }
    }
    if ( v22 != -2147024662 )
    {
LABEL_64:
      operator delete(v16, v20);
      goto LABEL_65;
    }
    v24 = BytesReturned;
    goto LABEL_38;
  }
  v22 = 262403;
LABEL_65:
  CoTaskMemFree(v11);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x180005850  mov     rax, rsp
0x180005853  mov     [rax+20h], r9d
0x180005857  mov     [rax+18h], r8
0x18000585b  mov     [rax+10h], rdx
0x18000585f  push    rbp
0x180005860  push    rsi
0x180005861  push    rdi
0x180005862  push    r12
0x180005864  push    r13
0x180005866  push    r14
0x180005868  push    r15
0x18000586a  lea     rbp, [rax-5Fh]
0x18000586e  sub     rsp, 0A0h
0x180005875  xor     r12d, r12d
0x180005878  mov     r15d, r9d
0x18000587b  mov     [rbp+57h+pv], r12
0x18000587f  mov     r14, r8
0x180005882  mov     r13, rdx
0x180005885  mov     edi, ecx
0x180005887  mov     esi, r12d
0x18000588a  test    ecx, ecx
0x18000588c  js      loc_1800060C2
0x180005892  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180005899  mov     [rax-40h], rbx
0x18000589d  lea     rax, [r8-1]
0x1800058a1  mov     [rbp+57h+BytesReturned], r12d
0x1800058a5  mov     [rbp+57h+var_70], 0Dh
0x1800058ac  mov     [rbp+57h+var_6C], 1
0x1800058b3  mov     [rbp+57h+var_68], r9d
0x1800058b7  mov     [rbp+57h+var_64], 1
0x1800058be  movups  [rbp+57h+InBuffer], xmm0
0x1800058c2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800058c6  ja      loc_180006162
0x1800058cc  xorps   xmm0, xmm0
0x1800058cf  xor     r9d, r9d; lpName
0x1800058d2  xor     r8d, r8d; bInitialState
0x1800058d5  mov     edx, 1; bManualReset
0x1800058da  xor     ecx, ecx; lpEventAttributes
0x1800058dc  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x1800058e0  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x1800058e4  call    cs:__imp_CreateEventW
0x1800058eb  nop     dword ptr [rax+rax+00h]
0x1800058f0  mov     [rbp+57h+Overlapped.hEvent], rax
0x1800058f4  test    rax, rax
0x1800058f7  jz      loc_180005EF4
0x1800058fd  lea     rax, [rbp+57h+Overlapped]
0x180005901  mov     r9d, 20h ; ' '; nInBufferSize
0x180005907  mov     [rsp+38h], rax; lpOverlapped
0x18000590c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180005910  lea     rax, [rbp+57h+BytesReturned]
0x180005914  mov     edx, 2F0003h; dwIoControlCode
0x180005919  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x18000591e  mov     rcx, r14; hDevice
0x180005921  mov     [rsp+0D0h+nOutBufferSize], r12d; nOutBufferSize
0x180005926  mov     [rsp+0D0h+lpOutBuffer], r12; lpOutBuffer
0x18000592b  call    cs:__imp_DeviceIoControl
0x180005932  nop     dword ptr [rax+rax+00h]
0x180005937  test    eax, eax
0x180005939  jnz     short loc_1800059B1
0x18000593b  call    cs:__imp_GetLastError
0x180005942  nop     dword ptr [rax+rax+00h]
0x180005947  mov     ebx, eax
0x180005949  test    eax, eax
0x18000594b  jle     short loc_180005956
0x18000594d  movzx   ebx, ax
0x180005950  or      ebx, 80070000h
0x180005956  cmp     ebx, 800703E5h
0x18000595c  jz      loc_180005F84
0x180005962  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180005966  call    cs:__imp_CloseHandle
0x18000596d  nop     dword ptr [rax+rax+00h]
0x180005972  cmp     ebx, 8007007Ah
0x180005978  jz      loc_1800060EA
0x18000597e  cmp     ebx, 800700EAh
0x180005984  jz      loc_180005DC5
0x18000598a  test    ebx, ebx
0x18000598c  js      short loc_1800059DA
0x18000598e  lea     r9, [rbp+57h+pv]
0x180005992  mov     r8d, 3
0x180005998  mov     edx, r15d
0x18000599b  mov     rcx, r14; hFile
0x18000599e  call    KsGetMultiplePinFactoryItems
0x1800059a3  test    eax, eax
0x1800059a5  js      loc_180005D50
0x1800059ab  mov     rsi, [rbp+57h+pv]
0x1800059af  jmp     short loc_1800059DE
0x1800059b1  mov     rax, [rbp+57h+Overlapped.Internal]
0x1800059b5  sub     rax, 101h
0x1800059bb  jz      loc_1800060E0
0x1800059c1  sub     rax, 4
0x1800059c5  jz      loc_1800060D6
0x1800059cb  cmp     rax, 2
0x1800059cf  jz      loc_1800060CC
0x1800059d5  mov     ebx, r12d
0x1800059d8  jmp     short loc_180005962
0x1800059da  test    ebx, ebx
0x1800059dc  js      short loc_18000598E
0x1800059de  test    rsi, rsi
0x1800059e1  jz      loc_1800061AA
0x1800059e7  mov     ecx, [rsi+4]
0x1800059ea  cmp     edi, ecx
0x1800059ec  jnb     loc_180006384
0x1800059f2  mov     [rbp+57h+BytesReturned], r12d
0x1800059f6  lea     rbx, [rsi+8]
0x1800059fa  mov     edx, 0FFFFFFF8h
0x1800059ff  nop
0x180005a00  test    edi, edi
0x180005a02  jz      short loc_180005A22
0x180005a04  test    byte ptr [rbx+4], 2
0x180005a08  jnz     loc_1800061B4
0x180005a0e  mov     eax, [rbx]
0x180005a10  add     eax, 7
0x180005a13  and     rax, rdx
0x180005a16  add     rbx, rax
0x180005a19  dec     ecx
0x180005a1b  mov     [rsi+4], ecx
0x180005a1e  dec     edi
0x180005a20  jmp     short loc_180005A00
0x180005a22  test    byte ptr [rbx+4], 2
0x180005a26  mov     eax, [rbx]
0x180005a28  lea     r15d, [rax+28h]
0x180005a2c  jnz     loc_180005ED0
0x180005a32  mov     ecx, r15d; unsigned __int64
0x180005a35  mov     [rbp+57h+pv], r12
0x180005a39  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005a3e  mov     r14, rax
0x180005a41  test    rax, rax
0x180005a44  jz      loc_1800062AF
0x180005a4a  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180005a51  mov     dword ptr [rax+10h], 4
0x180005a58  lea     rdi, [r14+20h]
0x180005a5c  mov     dword ptr [rax+14h], 1
0x180005a63  lea     rcx, [rdi+8]; void *
0x180005a67  movups  xmmword ptr [rax], xmm0
0x180005a6a  mov     eax, [rbp+57h+arg_18]
0x180005a6d  mov     rdx, rbx; Src
0x180005a70  mov     [r14+18h], eax
0x180005a74  mov     dword ptr [r14+1Ch], 0
0x180005a7c  mov     eax, [rbx]
0x180005a7e  add     eax, 8
0x180005a81  mov     dword ptr [rdi+4], 1
0x180005a88  mov     [rdi], eax
0x180005a8a  mov     r8d, [rbx]; Size
0x180005a8d  call    memcpy_0
0x180005a92  test    r12, r12
0x180005a95  jnz     loc_1800061E6
0x180005a9b  mov     rbx, [rbp+57h+hDevice]
0x180005a9f  lea     rax, [rbx-1]
0x180005aa3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005aa7  ja      loc_18000629D
0x180005aad  xorps   xmm0, xmm0
0x180005ab0  xor     r9d, r9d; lpName
0x180005ab3  xor     r8d, r8d; bInitialState
0x180005ab6  mov     edx, 1; bManualReset
0x180005abb  xor     ecx, ecx; lpEventAttributes
0x180005abd  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180005ac1  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180005ac5  call    cs:__imp_CreateEventW
0x180005acc  nop     dword ptr [rax+rax+00h]
0x180005ad1  mov     [rbp+57h+Overlapped.hEvent], rax
0x180005ad5  test    rax, rax
0x180005ad8  jz      loc_180005F18
0x180005ade  lea     rax, [rbp+57h+Overlapped]
0x180005ae2  xor     edi, edi
0x180005ae4  mov     [rsp+38h], rax; lpOverlapped
0x180005ae9  mov     r9d, r15d; nInBufferSize
0x180005aec  lea     rax, [rbp+57h+BytesReturned]
0x180005af0  mov     r8, r14; lpInBuffer
0x180005af3  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005af8  mov     edx, 2F0003h; dwIoControlCode
0x180005afd  mov     [rsp+0D0h+nOutBufferSize], edi; nOutBufferSize
0x180005b01  mov     rcx, rbx; hDevice
0x180005b04  mov     [rsp+0D0h+lpOutBuffer], rdi; lpOutBuffer
0x180005b09  call    cs:__imp_DeviceIoControl
0x180005b10  nop     dword ptr [rax+rax+00h]
0x180005b15  test    eax, eax
0x180005b17  jnz     loc_180005D6C
0x180005b1d  call    cs:__imp_GetLastError
0x180005b24  nop     dword ptr [rax+rax+00h]
0x180005b29  mov     edi, eax
0x180005b2b  test    eax, eax
0x180005b2d  jle     short loc_180005B38
0x180005b2f  movzx   edi, ax
0x180005b32  or      edi, 80070000h
0x180005b38  cmp     edi, 800703E5h
0x180005b3e  jz      loc_180005FB1
0x180005b44  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180005b48  call    cs:__imp_CloseHandle
0x180005b4f  nop     dword ptr [rax+rax+00h]
0x180005b54  cmp     edi, 8007007Ah
0x180005b5a  jz      loc_180006226
0x180005b60  cmp     edi, 800700EAh
0x180005b66  jnz     loc_180005D37
0x180005b6c  mov     eax, [rbp+57h+BytesReturned]
0x180005b6f  cmp     eax, 40h ; '@'
0x180005b72  jb      loc_18000637A
0x180005b78  mov     ecx, eax; unsigned __int64
0x180005b7a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180005b7f  mov     rbx, rax
0x180005b82  test    rax, rax
0x180005b85  jz      loc_1800062A7
0x180005b8b  mov     rax, [rbp+57h+hDevice]
0x180005b8f  dec     rax
0x180005b92  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180005b96  ja      loc_180006370
0x180005b9c  mov     edi, [rbp+57h+BytesReturned]
0x180005b9f  xorps   xmm0, xmm0
0x180005ba2  xor     r9d, r9d; lpName
0x180005ba5  xor     r8d, r8d; bInitialState
0x180005ba8  mov     edx, 1; bManualReset
0x180005bad  xor     ecx, ecx; lpEventAttributes
0x180005baf  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180005bb3  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180005bb7  call    cs:__imp_CreateEventW
0x180005bbe  nop     dword ptr [rax+rax+00h]
0x180005bc3  mov     [rbp+57h+Overlapped.hEvent], rax
0x180005bc7  test    rax, rax
0x180005bca  jz      loc_180005F3C
0x180005bd0  lea     rax, [rbp+57h+Overlapped]
0x180005bd4  mov     r9d, r15d; nInBufferSize
0x180005bd7  mov     r15, [rbp+57h+hDevice]
0x180005bdb  mov     r8, r14; lpInBuffer
0x180005bde  mov     [rsp+38h], rax; lpOverlapped
0x180005be3  mov     edx, 2F0003h; dwIoControlCode
0x180005be8  lea     rax, [rbp+57h+BytesReturned]
0x180005bec  mov     rcx, r15; hDevice
0x180005bef  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x180005bf4  mov     [rsp+0D0h+nOutBufferSize], edi; nOutBufferSize
0x180005bf8  mov     [rsp+0D0h+lpOutBuffer], rbx; lpOutBuffer
0x180005bfd  call    cs:__imp_DeviceIoControl
0x180005c04  nop     dword ptr [rax+rax+00h]
0x180005c09  test    eax, eax
0x180005c0b  jnz     loc_180005D9A
0x180005c11  call    cs:__imp_GetLastError
0x180005c18  nop     dword ptr [rax+rax+00h]
0x180005c1d  mov     edi, eax
0x180005c1f  test    eax, eax
0x180005c21  jle     short loc_180005C2C
0x180005c23  movzx   edi, ax
0x180005c26  or      edi, 80070000h
0x180005c2c  cmp     edi, 800703E5h
0x180005c32  jz      loc_180005FDD
0x180005c38  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x180005c3c  call    cs:__imp_CloseHandle
0x180005c43  nop     dword ptr [rax+rax+00h]
0x180005c48  test    edi, edi
0x180005c4a  js      loc_180005D2F
0x180005c50  mov     eax, [rbx]
0x180005c52  cmp     eax, [rbp+57h+BytesReturned]
0x180005c55  jnz     loc_180005EEA
0x180005c5b  cmp     eax, 40h ; '@'
0x180005c5e  jb      loc_180005EEA
0x180005c64  movups  xmm0, xmmword ptr [rbx+10h]
0x180005c68  movups  xmmword ptr [r13+0], xmm0
0x180005c6d  movups  xmm0, xmmword ptr [rbx+20h]
0x180005c71  movups  xmmword ptr [r13+10h], xmm0
0x180005c76  mov     eax, [rbx+4]
0x180005c79  and     eax, 1
0x180005c7c  mov     [r13+24h], eax
0x180005c80  mov     eax, [rbx+8]
0x180005c83  test    eax, eax
0x180005c85  jz      loc_1800062E6
0x180005c8b  mov     [r13+28h], eax
0x180005c8f  mov     eax, 1
0x180005c94  mov     [r13+20h], eax
0x180005c98  mov     eax, [rbx]
0x180005c9a  cmp     eax, 40h ; '@'
0x180005c9d  jbe     short loc_180005D1C
0x180005c9f  lea     r13d, [rax-40h]
0x180005ca3  mov     rax, [rbp+57h+arg_8]
0x180005ca7  mov     r12d, r13d
0x180005caa  cmp     [rax+48h], r13d
0x180005cae  jz      short loc_180005CE8
0x180005cb0  mov     ecx, r12d; cb
0x180005cb3  call    cs:__imp_CoTaskMemAlloc
0x180005cba  nop     dword ptr [rax+rax+00h]
0x180005cbf  mov     rcx, [rbp+57h+arg_8]
0x180005cc3  mov     r15, rax
0x180005cc6  mov     eax, [rcx+48h]
0x180005cc9  test    r15, r15
0x180005ccc  jz      loc_1800062ED
0x180005cd2  test    eax, eax
0x180005cd4  jnz     loc_180006304
0x180005cda  mov     [rcx+48h], r13d
0x180005cde  mov     r13, [rbp+57h+arg_8]
0x180005ce2  mov     [r13+50h], r15
0x180005ce6  jmp     short loc_180005D09
0x180005ce8  mov     r13, [rbp+57h+arg_8]
0x180005cec  mov     eax, 50h ; 'P'
0x180005cf1  mov     rcx, r13
0x180005cf4  mov     edx, eax
0x180005cf6  mov     r15, r13
0x180005cf9  cmp     qword ptr [rax+rcx], 0
0x180005cfe  jz      loc_1800062FA
0x180005d04  mov     r15, [r13+rax+0]
0x180005d09  lea     rdx, [rbx+40h]; Src
0x180005d0d  mov     r8, r12; Size
0x180005d10  mov     rcx, r15; void *
0x180005d13  call    memcpy_0
0x180005d18  mov     r12, [rbp+57h+pv]
  ... truncated ...
```
