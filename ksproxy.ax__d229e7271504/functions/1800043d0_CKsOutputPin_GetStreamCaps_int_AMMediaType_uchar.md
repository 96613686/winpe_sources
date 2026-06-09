# CKsOutputPin::GetStreamCaps(int,_AMMediaType * *,uchar *)

- ea: `0x1800043d0`
- end: `0x180004f5b`
- name: `?GetStreamCaps@CKsOutputPin@@UEAAJHPEAPEAU_AMMediaType@@PEAE@Z`
- size: `2955`
- prototype: `__int64 __fastcall(CKsOutputPin *this, DWORD, struct _AMMediaType **, GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002dd70`
- `0x18002fa50`

## callees

- `0x1800043d0`
- `0x180004f70`
- `0x180005850`
- `0x18000bde0`
- `0x180025860`
- `0x18003e22c`
- `0x180045010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000458a`
- `KERNEL32!GetLastError` at `0x180004683`
- `KERNEL32!GetLastError` at `0x1800047ab`
- `KERNEL32!GetLastError` at `0x180004aaa`
- `KERNEL32!GetLastError` at `0x180004b6d`
- `KERNEL32!GetLastError` at `0x180004b91`
- `KERNEL32!GetLastError` at `0x180004bb5`
- `KERNEL32!GetLastError` at `0x180004bd8`
- `KERNEL32!GetLastError` at `0x180004d00`
- `KERNEL32!GetLastError` at `0x180004d24`
- `KERNEL32!GetLastError` at `0x180004d48`
- `KERNEL32!GetLastError` at `0x180004d6c`
- `KERNEL32!GetLastError` at `0x18000458a`
- `KERNEL32!GetLastError` at `0x180004683`
- `KERNEL32!GetLastError` at `0x1800047ab`
- `KERNEL32!GetLastError` at `0x180004aaa`
- `KERNEL32!GetLastError` at `0x180004b6d`
- `KERNEL32!GetLastError` at `0x180004b91`
- `KERNEL32!GetLastError` at `0x180004bb5`
- `KERNEL32!GetLastError` at `0x180004bd8`
- `KERNEL32!GetLastError` at `0x180004d00`
- `KERNEL32!GetLastError` at `0x180004d24`
- `KERNEL32!GetLastError` at `0x180004d48`
- `KERNEL32!GetLastError` at `0x180004d6c`
- `KERNEL32!CreateEventW` at `0x18000452f`
- `KERNEL32!CreateEventW` at `0x180004629`
- `KERNEL32!CreateEventW` at `0x180004750`
- `KERNEL32!CreateEventW` at `0x180004a54`
- `KERNEL32!CreateEventW` at `0x18000452f`
- `KERNEL32!CreateEventW` at `0x180004629`
- `KERNEL32!CreateEventW` at `0x180004750`
- `KERNEL32!CreateEventW` at `0x180004a54`
- `KERNEL32!CloseHandle` at `0x1800045b5`
- `KERNEL32!CloseHandle` at `0x1800046b1`
- `KERNEL32!CloseHandle` at `0x1800047d6`
- `KERNEL32!CloseHandle` at `0x180004ad5`
- `KERNEL32!CloseHandle` at `0x1800045b5`
- `KERNEL32!CloseHandle` at `0x1800046b1`
- `KERNEL32!CloseHandle` at `0x1800047d6`
- `KERNEL32!CloseHandle` at `0x180004ad5`
- `KERNEL32!GetOverlappedResult` at `0x180004c0d`
- `KERNEL32!GetOverlappedResult` at `0x180004c3a`
- `KERNEL32!GetOverlappedResult` at `0x180004c67`
- `KERNEL32!GetOverlappedResult` at `0x180004c97`
- `KERNEL32!GetOverlappedResult` at `0x180004c0d`
- `KERNEL32!GetOverlappedResult` at `0x180004c3a`
- `KERNEL32!GetOverlappedResult` at `0x180004c67`
- `KERNEL32!GetOverlappedResult` at `0x180004c97`
- `KERNEL32!DeviceIoControl` at `0x180004576`
- `KERNEL32!DeviceIoControl` at `0x18000466f`
- `KERNEL32!DeviceIoControl` at `0x180004797`
- `KERNEL32!DeviceIoControl` at `0x180004a9a`
- `KERNEL32!DeviceIoControl` at `0x180004576`
- `KERNEL32!DeviceIoControl` at `0x18000466f`
- `KERNEL32!DeviceIoControl` at `0x180004797`
- `KERNEL32!DeviceIoControl` at `0x180004a9a`
- `ole32!CoTaskMemAlloc` at `0x180004445`
- `ole32!CoTaskMemAlloc` at `0x1800045e8`
- `ole32!CoTaskMemAlloc` at `0x180004a13`
- `ole32!CoTaskMemAlloc` at `0x180004445`
- `ole32!CoTaskMemAlloc` at `0x1800045e8`
- `ole32!CoTaskMemAlloc` at `0x180004a13`
- `ole32!CoTaskMemFree` at `0x1800046c8`
- `ole32!CoTaskMemFree` at `0x1800048d5`
- `ole32!CoTaskMemFree` at `0x180004f35`
- `ole32!CoTaskMemFree` at `0x1800046c8`
- `ole32!CoTaskMemFree` at `0x1800048d5`
- `ole32!CoTaskMemFree` at `0x180004f35`

## pseudocode

```c
__int64 __fastcall CKsOutputPin::GetStreamCaps(CKsOutputPin *this, DWORD a2, struct _AMMediaType **a3, GUID *a4)
{
  unsigned int lSampleSize; // ebx
  __int64 v6; // rcx
  char *v9; // rax
  __int64 result; // rax
  struct _AMMediaType *v11; // rax
  unsigned int v12; // ebx
  char *v13; // rax
  int MediaType; // esi
  unsigned int v15; // ebx
  char *v16; // r15
  signed int LastError; // eax
  int v18; // ebx
  char *lpOutBuffer; // r13
  DWORD nOutBufferSize; // ebx
  signed int v21; // eax
  signed int v22; // ebx
  unsigned int v23; // ebx
  char *v24; // r14
  signed int v25; // eax
  char *i; // rax
  struct _AMMediaType *v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  GUID *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  DWORD v36; // ebx
  signed int v37; // eax
  signed int v38; // eax
  signed int v39; // eax
  signed int v40; // eax
  signed int v41; // eax
  GUID *v42; // rdx
  signed int v43; // eax
  signed int v44; // eax
  signed int v45; // eax
  signed int v46; // eax
  DWORD NumberOfBytesTransferred; // [rsp+40h] [rbp-49h] BYREF
  DWORD v48; // [rsp+44h] [rbp-45h] BYREF
  GUID InBuffer; // [rsp+48h] [rbp-41h] BYREF
  int v50; // [rsp+58h] [rbp-31h]
  int v51; // [rsp+5Ch] [rbp-2Dh]
  unsigned int v52; // [rsp+60h] [rbp-29h]
  int v53; // [rsp+64h] [rbp-25h]
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-21h] BYREF
  struct _OVERLAPPED lpOverlapped; // [rsp+88h] [rbp-1h] BYREF
  DWORD BytesReturned; // [rsp+F0h] [rbp+67h] BYREF
  GUID *v57; // [rsp+108h] [rbp+7Fh]

  v57 = a4;
  lSampleSize = this->m_mt.lSampleSize;
  v6 = *(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL;
  BytesReturned = 0;
  v9 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
  result = KsGetMediaTypeCount(v9, lSampleSize, &BytesReturned);
  if ( (int)result >= 0 )
  {
    if ( a2 >= BytesReturned )
      return 1;
    v11 = (struct _AMMediaType *)CoTaskMemAlloc(0x58u);
    *a3 = v11;
    if ( !v11 )
      return 2147942414LL;
    v11->majortype = 0;
    v11->subtype = 0;
    *(_OWORD *)&v11->bFixedSizeSamples = 0;
    *(_OWORD *)&v11->formattype.Data2 = 0;
    *(_OWORD *)&v11->pUnk = 0;
    v11->pbFormat = 0;
    v12 = this->m_mt.lSampleSize;
    v13 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL)
                                                     + 24LL))(*(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL);
    MediaType = KsGetMediaType(a2, (__int64)*a3, v13, v12);
    if ( MediaType < 0 )
      goto LABEL_92;
    v15 = this->m_mt.lSampleSize;
    v16 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL)
                                                     + 24LL))(*(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL);
    BytesReturned = 0;
    v50 = 13;
    v51 = 1;
    v52 = v15;
    v53 = 1;
    InBuffer = GUID_8c134960_51ad_11cf_878a_94f801c10000;
    if ( (unsigned __int64)(v16 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v18 = -2147024890;
    }
    else
    {
      memset(&Overlapped, 0, 24);
      Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
      if ( Overlapped.hEvent )
      {
        if ( DeviceIoControl(v16, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &BytesReturned, &Overlapped) )
        {
          switch ( Overlapped.Internal )
          {
            case 0x101uLL:
              v18 = -2147024875;
              break;
            case 0x105uLL:
              v18 = -2147024662;
              break;
            case 0x107uLL:
              v18 = -2147023595;
              break;
            default:
              v18 = 0;
              break;
          }
        }
        else
        {
          LastError = GetLastError();
          v18 = LastError;
          if ( LastError > 0 )
            v18 = (unsigned __int16)LastError | 0x80070000;
          if ( v18 == -2147023899 )
          {
            if ( GetOverlappedResult(v16, &Overlapped, &BytesReturned, 1) )
            {
              v18 = 0;
            }
            else
            {
              v43 = GetLastError();
              v18 = v43;
              if ( v43 > 0 )
                v18 = (unsigned __int16)v43 | 0x80070000;
            }
          }
        }
        CloseHandle(Overlapped.hEvent);
      }
      else
      {
        v38 = GetLastError();
        v18 = v38;
        if ( v38 > 0 )
          v18 = (unsigned __int16)v38 | 0x80070000;
      }
      if ( v18 == -2147024774 )
      {
        NumberOfBytesTransferred = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
        v18 = KsSynchronousDeviceControl(
                v16,
                0x2F0003u,
                &InBuffer,
                0x20u,
                &NumberOfBytesTransferred,
                4u,
                &BytesReturned);
        if ( v18 >= 0 )
        {
          BytesReturned = NumberOfBytesTransferred;
LABEL_14:
          lpOutBuffer = (char *)CoTaskMemAlloc(BytesReturned);
          if ( lpOutBuffer )
          {
            if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              nOutBufferSize = BytesReturned;
              memset(&Overlapped, 0, sizeof(Overlapped));
              Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
              if ( Overlapped.hEvent )
              {
                if ( DeviceIoControl(
                       v16,
                       0x2F0003u,
                       &InBuffer,
                       0x20u,
                       lpOutBuffer,
                       nOutBufferSize,
                       &BytesReturned,
                       &Overlapped) )
                {
                  if ( Overlapped.Internal == 257 )
                  {
                    v22 = -2147024875;
                  }
                  else if ( Overlapped.Internal == 261 )
                  {
                    v22 = -2147024662;
                  }
                  else
                  {
                    v22 = Overlapped.Internal == 263 ? -2147023595 : 0;
                  }
                }
                else
                {
                  v21 = GetLastError();
                  v22 = v21;
                  if ( v21 > 0 )
                    v22 = (unsigned __int16)v21 | 0x80070000;
                  if ( v22 == -2147023899 )
                  {
                    if ( GetOverlappedResult(v16, &Overlapped, &BytesReturned, 1) )
                    {
                      v22 = 0;
                    }
                    else
                    {
                      v44 = GetLastError();
                      v22 = v44;
                      if ( v44 > 0 )
                        v22 = (unsigned __int16)v44 | 0x80070000;
                    }
                  }
                }
                CloseHandle(Overlapped.hEvent);
              }
              else
              {
                v40 = GetLastError();
                v22 = v40;
                if ( v40 > 0 )
                  v22 = (unsigned __int16)v40 | 0x80070000;
              }
              if ( v22 >= 0 )
                goto LABEL_36;
            }
            CoTaskMemFree(lpOutBuffer);
          }
LABEL_24:
          v23 = this->m_mt.lSampleSize;
          v24 = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&this[-1].m_MarshalerList.m_Count
                                                                       + 168LL)
                                                           + 24LL))(*(_QWORD *)&this[-1].m_MarshalerList.m_Count + 168LL);
          NumberOfBytesTransferred = 0;
          Overlapped.Pointer = (PVOID)0x100000003LL;
          Overlapped.hEvent = (HANDLE)(v23 | 0x100000000LL);
          *(GUID *)&Overlapped.Internal = GUID_8c134960_51ad_11cf_878a_94f801c10000;
          if ( (unsigned __int64)(v24 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            MediaType = -2147024890;
          }
          else
          {
            memset(&lpOverlapped, 0, sizeof(lpOverlapped));
            lpOverlapped.hEvent = CreateEventW(0, 1, 0, 0);
            if ( lpOverlapped.hEvent )
            {
              if ( DeviceIoControl(v24, 0x2F0003u, &Overlapped, 0x20u, 0, 0, &NumberOfBytesTransferred, &lpOverlapped) )
              {
                switch ( lpOverlapped.Internal )
                {
                  case 0x101uLL:
                    MediaType = -2147024875;
                    break;
                  case 0x105uLL:
                    MediaType = -2147024662;
                    break;
                  case 0x107uLL:
                    MediaType = -2147023595;
                    break;
                  default:
                    MediaType = 0;
                    break;
                }
              }
              else
              {
                v25 = GetLastError();
                MediaType = v25;
                if ( v25 > 0 )
                  MediaType = (unsigned __int16)v25 | 0x80070000;
                if ( MediaType == -2147023899 )
                {
                  if ( GetOverlappedResult(v24, &lpOverlapped, &NumberOfBytesTransferred, 1) )
                  {
                    MediaType = 0;
                  }
                  else
                  {
                    v45 = GetLastError();
                    MediaType = v45;
                    if ( v45 > 0 )
                      MediaType = (unsigned __int16)v45 | 0x80070000;
                  }
                }
              }
              CloseHandle(lpOverlapped.hEvent);
            }
            else
            {
              v39 = GetLastError();
              MediaType = v39;
              if ( v39 > 0 )
                MediaType = (unsigned __int16)v39 | 0x80070000;
            }
            if ( MediaType == -2147024774 )
            {
              v48 = 0;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids);
              MediaType = KsSynchronousDeviceControl(
                            v24,
                            0x2F0003u,
                            &Overlapped,
                            0x20u,
                            &v48,
                            4u,
                            &NumberOfBytesTransferred);
              if ( MediaType >= 0 )
              {
                NumberOfBytesTransferred = v48;
LABEL_74:
                lpOutBuffer = (char *)CoTaskMemAlloc(NumberOfBytesTransferred);
                if ( !lpOutBuffer )
                {
                  MediaType = -2147024882;
LABEL_92:
                  DeleteMediaType(*a3);
                  *a3 = 0;
                  return (unsigned int)MediaType;
                }
                if ( (unsigned __int64)(v24 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
                {
                  MediaType = -2147024890;
LABEL_149:
                  CoTaskMemFree(lpOutBuffer);
                  goto LABEL_92;
                }
                v36 = NumberOfBytesTransferred;
                memset(&lpOverlapped, 0, sizeof(lpOverlapped));
                lpOverlapped.hEvent = CreateEventW(0, 1, 0, 0);
                if ( lpOverlapped.hEvent )
                {
                  if ( DeviceIoControl(
                         v24,
                         0x2F0003u,
                         &Overlapped,
                         0x20u,
                         lpOutBuffer,
                         v36,
                         &NumberOfBytesTransferred,
                         &lpOverlapped) )
                  {
                    switch ( lpOverlapped.Internal )
                    {
                      case 0x101uLL:
                        MediaType = -2147024875;
                        break;
                      case 0x105uLL:
                        MediaType = -2147024662;
                        break;
                      case 0x107uLL:
                        MediaType = -2147023595;
                        break;
                      default:
                        MediaType = 0;
                        break;
                    }
                  }
                  else
                  {
                    v37 = GetLastError();
                    MediaType = v37;
                    if ( v37 > 0 )
                      MediaType = (unsigned __int16)v37 | 0x80070000;
                    if ( MediaType == -2147023899 )
                    {
                      if ( GetOverlappedResult(v24, &lpOverlapped, &NumberOfBytesTransferred, 1) )
                      {
                        MediaType = 0;
                      }
                      else
                      {
                        v46 = GetLastError();
                        MediaType = v46;
                        if ( v46 > 0 )
                          MediaType = (unsigned __int16)v46 | 0x80070000;
                      }
                    }
                  }
                  CloseHandle(lpOverlapped.hEvent);
                }
                else
                {
                  v41 = GetLastError();
                  MediaType = v41;
                  if ( v41 > 0 )
                    MediaType = (unsigned __int16)v41 | 0x80070000;
                }
                if ( MediaType < 0 )
                  goto LABEL_149;
LABEL_36:
                for ( i = lpOutBuffer + 8; a2; i += (*(_DWORD *)i + 7) & 0xFFFFFFF8 )
                {
                  --a2;
                  if ( (i[4] & 2) != 0 )
                  {
                    --a2;
                    i += (*(_DWORD *)i + 7) & 0xFFFFFFF8;
                  }
                }
                v27 = *a3;
                v28 = *(_QWORD *)&(*a3)->majortype.Data1 - *(_QWORD *)&MEDIATYPE_Video.Data1;
                if ( !v28 )
                  v28 = *(_QWORD *)v27->majortype.Data4 - *(_QWORD *)MEDIATYPE_Video.Data4;
                if ( v28 )
                  goto LABEL_59;
                v29 = *(_QWORD *)&v27->formattype.Data1 - *(_QWORD *)&GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1;
                if ( !v29 )
                  v29 = *(_QWORD *)v27->formattype.Data4 - *(_QWORD *)GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4;
                if ( !v29 )
                  goto LABEL_46;
                v31 = *(_QWORD *)&v27->formattype.Data1 - *(_QWORD *)&GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data1;
                if ( !v31 )
                  v31 = *(_QWORD *)v27->formattype.Data4 - *(_QWORD *)GUID_f72a76a0_eb0a_11d0_ace4_0000c0cc16ba.Data4;
                if ( !v31 )
                  goto LABEL_46;
                v32 = *(_QWORD *)&v27->formattype.Data1 - *(_QWORD *)&GUID_05589f82_c356_11ce_bf01_00aa0055595a.Data1;
                if ( !v32 )
                  v32 = *(_QWORD *)v27->formattype.Data4 - *(_QWORD *)GUID_05589f82_c356_11ce_bf01_00aa0055595a.Data4;
                if ( !v32 )
                  goto LABEL_46;
                v33 = *(_QWORD *)&v27->formattype.Data1 - *(_QWORD *)&GUID_e06d80e3_db46_11cf_b4d1_00805f6cbbea.Data1;
                if ( !v33 )
                  v33 = *(_QWORD *)v27->formattype.Data4 - *(_QWORD *)GUID_e06d80e3_db46_11cf_b4d1_00805f6cbbea.Data4;
                if ( v33 )
                {
LABEL_59:
                  v34 = *(_QWORD *)&v27->majortype.Data1 - *(_QWORD *)&MEDIATYPE_Audio.Data1;
                  if ( *(_QWORD *)&v27->majortype.Data1 == *(_QWORD *)&MEDIATYPE_Audio.Data1 )
                    v34 = *(_QWORD *)v27->majortype.Data4 - *(_QWORD *)MEDIATYPE_Audio.Data4;
                  if ( v34 )
                    goto LABEL_65;
                  v35 = *(_QWORD *)&v27->formattype.Data1 - *(_QWORD *)&GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data1;
                  if ( !v35 )
                    v35 = *(_QWORD *)v27->formattype.Data4 - *(_QWORD *)GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data4;
                  if ( v35 )
                  {
LABEL_65:
                    *v57 = GUID_00000000_0000_0000_0000_000000000000;
                  }
                  else
                  {
                    v42 = v57;
                    *v57 = MEDIATYPE_Audio;
                    v42[1].Data1 = 1;
                    *(_DWORD *)&v42[1].Data2 = *((_DWORD *)i + 16);
                    *(_DWORD *)v42[1].Data4 = 1;
                    *(_DWORD *)&v42[1].Data4[4] = *((_DWORD *)i + 17);
                    v42[2].Data1 = *((_DWORD *)i + 18);
                    *(_DWORD *)&v42[2].Data2 = 1;
                    *(_DWORD *)v42[2].Data4 = *((_DWORD *)i + 19);
                    *(_DWORD *)&v42[2].Data4[4] = *((_DWORD *)i + 20);
                    v42[3].Data1 = 1;
                  }
                }
                else
                {
LABEL_46:
                  v30 = v57;
                  *v57 = *((GUID *)i + 5);
                  v30[1] = *((GUID *)i + 6);
                  v30[2] = *((GUID *)i + 7);
                  v30[3] = *((GUID *)i + 8);
                  v30[4] = *((GUID *)i + 9);
                  v30[5] = *((GUID *)i + 10);
                  v30[6] = *((GUID *)i + 11);
                  v30[7] = *((GUID *)i + 12);
                }
                CoTaskMemFree(lpOutBuffer);
                return (unsigned int)MediaType;
              }
            }
          }
          if ( MediaType != -2147024662 )
          {
            if ( MediaType >= 0 )
              MediaType = -2147418113;
            goto LABEL_92;
          }
          goto LABEL_74;
        }
      }
    }
    if ( v18 != -2147024662 )
      goto LABEL_24;
    goto LABEL_14;
  }
  return result;
}

```

## disassembly

```asm
0x1800043d0  mov     [rsp-8+arg_18], r9
0x1800043d5  push    rbp
0x1800043d6  push    rbx
0x1800043d7  push    rdi
0x1800043d8  push    r12
0x1800043da  push    r13
0x1800043dc  push    r14
0x1800043de  lea     rbp, [rsp-2Fh]
0x1800043e3  sub     rsp, 0B8h
0x1800043ea  mov     ebx, [rcx+90h]
0x1800043f0  mov     r14, rcx
0x1800043f3  mov     rcx, [rcx-168h]
0x1800043fa  xor     r13d, r13d
0x1800043fd  add     rcx, 0A8h
0x180004404  mov     [rbp+57h+BytesReturned], r13d
0x180004408  mov     r12, r8
0x18000440b  mov     edi, edx
0x18000440d  mov     rax, [rcx]
0x180004410  mov     rax, [rax+18h]
0x180004414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004419  lea     r8, [rbp+57h+BytesReturned]
0x18000441d  mov     edx, ebx
0x18000441f  mov     rcx, rax; hFile
0x180004422  call    KsGetMediaTypeCount
0x180004427  test    eax, eax
0x180004429  js      loc_1800048F3
0x18000442f  cmp     edi, [rbp+57h+BytesReturned]
0x180004432  jnb     loc_180004D90
0x180004438  mov     ecx, 58h ; 'X'; cb
0x18000443d  mov     [rsp+0E0h+arg_8], rsi
0x180004445  call    cs:__imp_CoTaskMemAlloc
0x18000444c  nop     dword ptr [rax+rax+00h]
0x180004451  mov     [r12], rax
0x180004455  test    rax, rax
0x180004458  jz      loc_180004D9A
0x18000445e  xorps   xmm0, xmm0
0x180004461  mov     [rsp+0E0h+var_30], r15
0x180004469  movups  xmmword ptr [rax], xmm0
0x18000446c  xor     ecx, ecx
0x18000446e  movups  xmmword ptr [rax+10h], xmm0
0x180004472  movups  xmmword ptr [rax+20h], xmm0
0x180004476  movups  xmmword ptr [rax+30h], xmm0
0x18000447a  movups  xmmword ptr [rax+40h], xmm0
0x18000447e  mov     [rax+50h], rcx
0x180004482  mov     rcx, [r14-168h]
0x180004489  mov     ebx, [r14+90h]
0x180004490  add     rcx, 0A8h
0x180004497  mov     rax, [rcx]
0x18000449a  mov     rax, [rax+18h]
0x18000449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a3  mov     rdx, [r12]
0x1800044a7  mov     r9d, ebx
0x1800044aa  mov     r8, rax
0x1800044ad  mov     ecx, edi
0x1800044af  call    KsGetMediaType
0x1800044b4  mov     esi, eax
0x1800044b6  test    eax, eax
0x1800044b8  js      loc_180004B49
0x1800044be  mov     rcx, [r14-168h]
0x1800044c5  mov     ebx, [r14+90h]
0x1800044cc  add     rcx, 0A8h
0x1800044d3  mov     rdx, [rcx]
0x1800044d6  mov     rax, [rdx+18h]
0x1800044da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044df  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x1800044e6  mov     r15, rax
0x1800044e9  mov     [rbp+57h+BytesReturned], r13d
0x1800044ed  mov     [rbp+57h+var_88], 0Dh
0x1800044f4  lea     rcx, [rax-1]
0x1800044f8  mov     [rbp+57h+var_84], 1
0x1800044ff  mov     [rbp+57h+var_80], ebx
0x180004502  mov     [rbp+57h+var_7C], 1
0x180004509  movups  [rbp+57h+InBuffer], xmm0
0x18000450d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180004511  ja      loc_180004E3A
0x180004517  xorps   xmm0, xmm0
0x18000451a  xor     r9d, r9d; lpName
0x18000451d  xor     r8d, r8d; bInitialState
0x180004520  mov     edx, 1; bManualReset
0x180004525  xor     ecx, ecx; lpEventAttributes
0x180004527  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000452b  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x18000452f  call    cs:__imp_CreateEventW
0x180004536  nop     dword ptr [rax+rax+00h]
0x18000453b  mov     [rbp+57h+Overlapped.hEvent], rax
0x18000453f  test    rax, rax
0x180004542  jz      loc_180004B6D
0x180004548  lea     rax, [rbp+57h+Overlapped]
0x18000454c  mov     r9d, 20h ; ' '; nInBufferSize
0x180004552  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x180004557  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x18000455b  lea     rax, [rbp+57h+BytesReturned]
0x18000455f  mov     edx, 2F0003h; dwIoControlCode
0x180004564  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x180004569  mov     rcx, r15; hDevice
0x18000456c  mov     [rsp+0E0h+nOutBufferSize], r13d; nOutBufferSize
0x180004571  mov     [rsp+0E0h+lpOutBuffer], r13; lpOutBuffer
0x180004576  call    cs:__imp_DeviceIoControl
0x18000457d  nop     dword ptr [rax+rax+00h]
0x180004582  test    eax, eax
0x180004584  jnz     loc_1800049B8
0x18000458a  call    cs:__imp_GetLastError
0x180004591  nop     dword ptr [rax+rax+00h]
0x180004596  mov     ebx, eax
0x180004598  test    eax, eax
0x18000459a  jle     short loc_1800045A5
0x18000459c  movzx   ebx, ax
0x18000459f  or      ebx, 80070000h
0x1800045a5  cmp     ebx, 800703E5h
0x1800045ab  jz      loc_180004BFC
0x1800045b1  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x1800045b5  call    cs:__imp_CloseHandle
0x1800045bc  nop     dword ptr [rax+rax+00h]
0x1800045c1  cmp     ebx, 8007007Ah
0x1800045c7  jz      loc_180004DC2
0x1800045cd  cmp     ebx, 800700EAh
0x1800045d3  jz      short loc_1800045E5
0x1800045d5  xor     r15d, r15d
0x1800045d8  test    ebx, ebx
0x1800045da  js      loc_1800046D7
0x1800045e0  jmp     loc_1800046DF
0x1800045e5  mov     ecx, [rbp+57h+BytesReturned]; cb
0x1800045e8  call    cs:__imp_CoTaskMemAlloc
0x1800045ef  nop     dword ptr [rax+rax+00h]
0x1800045f4  mov     r13, rax
0x1800045f7  test    rax, rax
0x1800045fa  jz      loc_180004B5B
0x180004600  lea     rcx, [r15-1]
0x180004604  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180004608  ja      loc_180004E62
0x18000460e  mov     ebx, [rbp+57h+BytesReturned]
0x180004611  xorps   xmm0, xmm0
0x180004614  xor     r9d, r9d; lpName
0x180004617  xor     r8d, r8d; bInitialState
0x18000461a  mov     edx, 1; bManualReset
0x18000461f  xor     ecx, ecx; lpEventAttributes
0x180004621  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x180004625  movups  xmmword ptr [rbp+57h+Overlapped.10h], xmm0
0x180004629  call    cs:__imp_CreateEventW
0x180004630  nop     dword ptr [rax+rax+00h]
0x180004635  mov     [rbp+57h+Overlapped.hEvent], rax
0x180004639  test    rax, rax
0x18000463c  jz      loc_180004BB5
0x180004642  lea     rax, [rbp+57h+Overlapped]
0x180004646  mov     r9d, 20h ; ' '; nInBufferSize
0x18000464c  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x180004651  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x180004655  lea     rax, [rbp+57h+BytesReturned]
0x180004659  mov     edx, 2F0003h; dwIoControlCode
0x18000465e  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x180004663  mov     rcx, r15; hDevice
0x180004666  mov     [rsp+0E0h+nOutBufferSize], ebx; nOutBufferSize
0x18000466a  mov     [rsp+0E0h+lpOutBuffer], r13; lpOutBuffer
0x18000466f  call    cs:__imp_DeviceIoControl
0x180004676  nop     dword ptr [rax+rax+00h]
0x18000467b  test    eax, eax
0x18000467d  jnz     loc_180004AEE
0x180004683  call    cs:__imp_GetLastError
0x18000468a  nop     dword ptr [rax+rax+00h]
0x18000468f  mov     ebx, eax
0x180004691  test    eax, eax
0x180004693  jle     short loc_18000469E
0x180004695  movzx   ebx, ax
0x180004698  or      ebx, 80070000h
0x18000469e  cmp     ebx, 800703E5h
0x1800046a4  jz      loc_180004C56
0x1800046aa  xor     r15d, r15d
0x1800046ad  mov     rcx, [rbp+57h+Overlapped.hEvent]; hObject
0x1800046b1  call    cs:__imp_CloseHandle
0x1800046b8  nop     dword ptr [rax+rax+00h]
0x1800046bd  test    ebx, ebx
0x1800046bf  jns     loc_18000480C
0x1800046c5  mov     rcx, r13; pv
0x1800046c8  call    cs:__imp_CoTaskMemFree
0x1800046cf  nop     dword ptr [rax+rax+00h]
0x1800046d4  mov     r13, r15
0x1800046d7  test    ebx, ebx
0x1800046d9  jns     loc_18000480C
0x1800046df  mov     rcx, [r14-168h]
0x1800046e6  mov     ebx, [r14+90h]
0x1800046ed  add     rcx, 0A8h
0x1800046f4  mov     rax, [rcx]
0x1800046f7  mov     rax, [rax+18h]
0x1800046fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004700  movups  xmm0, xmmword ptr cs:_GUID_8c134960_51ad_11cf_878a_94f801c10000.Data1
0x180004707  mov     r14, rax
0x18000470a  mov     [rbp+57h+NumberOfBytesTransferred], r15d
0x18000470e  mov     dword ptr [rbp+57h+Overlapped.10h], 3
0x180004715  lea     rcx, [rax-1]
0x180004719  mov     dword ptr [rbp+57h+Overlapped.10h+4], 1
0x180004720  mov     dword ptr [rbp+57h+Overlapped.hEvent], ebx
0x180004723  mov     dword ptr [rbp+57h+Overlapped.hEvent+4], 1
0x18000472a  movups  xmmword ptr [rbp+57h+Overlapped.Internal], xmm0
0x18000472e  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180004732  ja      loc_180004F05
0x180004738  xorps   xmm0, xmm0
0x18000473b  xor     r9d, r9d; lpName
0x18000473e  xor     r8d, r8d; bInitialState
0x180004741  mov     edx, 1; bManualReset
0x180004746  xor     ecx, ecx; lpEventAttributes
0x180004748  movups  xmmword ptr [rbp+57h+var_58.Internal], xmm0
0x18000474c  movups  xmmword ptr [rbp+57h+var_58.10h], xmm0
0x180004750  call    cs:__imp_CreateEventW
0x180004757  nop     dword ptr [rax+rax+00h]
0x18000475c  mov     [rbp+57h+var_58.hEvent], rax
0x180004760  test    rax, rax
0x180004763  jz      loc_180004B91
0x180004769  lea     rax, [rbp+57h+var_58]
0x18000476d  mov     r9d, 20h ; ' '; nInBufferSize
0x180004773  mov     [rsp+0E0h+lpOverlapped], rax; lpOverlapped
0x180004778  lea     r8, [rbp+57h+Overlapped]; lpInBuffer
0x18000477c  lea     rax, [rbp+57h+NumberOfBytesTransferred]
0x180004780  mov     edx, 2F0003h; dwIoControlCode
0x180004785  mov     [rsp+0E0h+lpBytesReturned], rax; lpBytesReturned
0x18000478a  mov     rcx, r14; hDevice
0x18000478d  mov     [rsp+0E0h+nOutBufferSize], r15d; nOutBufferSize
0x180004792  mov     [rsp+0E0h+lpOutBuffer], r15; lpOutBuffer
0x180004797  call    cs:__imp_DeviceIoControl
0x18000479e  nop     dword ptr [rax+rax+00h]
0x1800047a3  test    eax, eax
0x1800047a5  jnz     loc_1800049E4
0x1800047ab  call    cs:__imp_GetLastError
0x1800047b2  nop     dword ptr [rax+rax+00h]
0x1800047b7  mov     esi, eax
0x1800047b9  test    eax, eax
0x1800047bb  jle     short loc_1800047C6
0x1800047bd  movzx   esi, ax
0x1800047c0  or      esi, 80070000h
0x1800047c6  cmp     esi, 800703E5h
0x1800047cc  jz      loc_180004C29
0x1800047d2  mov     rcx, [rbp+57h+var_58.hEvent]; hObject
0x1800047d6  call    cs:__imp_CloseHandle
0x1800047dd  nop     dword ptr [rax+rax+00h]
0x1800047e2  cmp     esi, 8007007Ah
0x1800047e8  jz      loc_180004E8D
0x1800047ee  cmp     esi, 800700EAh
0x1800047f4  jz      loc_180004A10
0x1800047fa  test    esi, esi
0x1800047fc  mov     eax, 8000FFFFh
0x180004801  cmovns  esi, eax
0x180004804  test    esi, esi
0x180004806  js      loc_180004B46
0x18000480c  lea     rax, [r13+8]
0x180004810  test    edi, edi
0x180004812  jz      short loc_18000483B
0x180004814  mov     edx, 0FFFFFFF8h
0x180004819  nop     dword ptr [rax+00000000h]
0x180004820  dec     edi
0x180004822  test    byte ptr [rax+4], 2
0x180004826  jnz     loc_180004F49
0x18000482c  mov     ecx, [rax]
0x18000482e  add     ecx, 7
0x180004831  and     rcx, rdx
0x180004834  add     rax, rcx
0x180004837  test    edi, edi
0x180004839  jnz     short loc_180004820
0x18000483b  mov     rdx, [r12]
0x18000483f  mov     rcx, [rdx]
0x180004842  sub     rcx, qword ptr cs:MEDIATYPE_Video.Data1
0x180004849  jnz     short loc_180004856
0x18000484b  mov     rcx, [rdx+8]
0x18000484f  sub     rcx, qword ptr cs:MEDIATYPE_Video.Data4
0x180004856  test    rcx, rcx
0x180004859  jnz     loc_180004968
0x18000485f  mov     rcx, [rdx+2Ch]
0x180004863  sub     rcx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data1
0x18000486a  jnz     short loc_180004877
0x18000486c  mov     rcx, [rdx+34h]
0x180004870  sub     rcx, qword ptr cs:_GUID_05589f80_c356_11ce_bf01_00aa0055595a.Data4
0x180004877  test    rcx, rcx
0x18000487a  jnz     loc_180004905
0x180004880  movups  xmm0, xmmword ptr [rax+50h]
0x180004884  mov     rcx, [rbp+57h+arg_18]
0x180004888  movups  xmmword ptr [rcx], xmm0
0x18000488b  movups  xmm1, xmmword ptr [rax+60h]
0x18000488f  movups  xmmword ptr [rcx+10h], xmm1
0x180004893  movups  xmm0, xmmword ptr [rax+70h]
0x180004897  movups  xmmword ptr [rcx+20h], xmm0
0x18000489b  movups  xmm1, xmmword ptr [rax+80h]
0x1800048a2  movups  xmmword ptr [rcx+30h], xmm1
0x1800048a6  movups  xmm0, xmmword ptr [rax+90h]
0x1800048ad  movups  xmmword ptr [rcx+40h], xmm0
0x1800048b1  movups  xmm1, xmmword ptr [rax+0A0h]
0x1800048b8  movups  xmmword ptr [rcx+50h], xmm1
0x1800048bc  movups  xmm0, xmmword ptr [rax+0B0h]
0x1800048c3  movups  xmmword ptr [rcx+60h], xmm0
0x1800048c7  movups  xmm1, xmmword ptr [rax+0C0h]
0x1800048ce  movups  xmmword ptr [rcx+70h], xmm1
0x1800048d2  mov     rcx, r13; pv
0x1800048d5  call    cs:__imp_CoTaskMemFree
0x1800048dc  nop     dword ptr [rax+rax+00h]
0x1800048e1  mov     r15, [rsp+0E0h+var_30]
0x1800048e9  mov     eax, esi
0x1800048eb  mov     rsi, [rsp+0E0h+arg_8]
0x1800048f3  add     rsp, 0B8h
0x1800048fa  pop     r14
0x1800048fc  pop     r13
0x1800048fe  pop     r12
0x180004900  pop     rdi
0x180004901  pop     rbx
  ... truncated ...
```
