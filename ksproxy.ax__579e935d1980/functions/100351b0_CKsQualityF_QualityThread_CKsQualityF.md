# CKsQualityF::QualityThread(CKsQualityF *)

- ea: `0x100351b0`
- end: `0x100355ea`
- name: `?QualityThread@CKsQualityF@@CGJPAV1@@Z`
- size: `1082`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1002d510`
- `0x100351b0`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10035214`
- `KERNEL32!GetLastError` at `0x10035270`
- `KERNEL32!GetLastError` at `0x1003531d`
- `KERNEL32!GetLastError` at `0x10035384`
- `KERNEL32!GetLastError` at `0x10035461`
- `KERNEL32!GetLastError` at `0x100354a5`
- `KERNEL32!GetLastError` at `0x100355be`
- `KERNEL32!GetLastError` at `0x10035214`
- `KERNEL32!GetLastError` at `0x10035270`
- `KERNEL32!GetLastError` at `0x1003531d`
- `KERNEL32!GetLastError` at `0x10035384`
- `KERNEL32!GetLastError` at `0x10035461`
- `KERNEL32!GetLastError` at `0x100354a5`
- `KERNEL32!GetLastError` at `0x100355be`
- `KERNEL32!SetEvent` at `0x10035315`
- `KERNEL32!SetEvent` at `0x1003537c`
- `KERNEL32!SetEvent` at `0x100354db`
- `KERNEL32!SetEvent` at `0x10035315`
- `KERNEL32!SetEvent` at `0x1003537c`
- `KERNEL32!SetEvent` at `0x100354db`
- `KERNEL32!WaitForMultipleObjects` at `0x100353c3`
- `KERNEL32!WaitForMultipleObjects` at `0x100353c3`
- `KERNEL32!CancelIoEx` at `0x100353f6`
- `KERNEL32!CancelIoEx` at `0x10035404`
- `KERNEL32!CancelIoEx` at `0x100353f6`
- `KERNEL32!CancelIoEx` at `0x10035404`
- `KERNEL32!CreateEventW` at `0x10035205`
- `KERNEL32!CreateEventW` at `0x1003525f`
- `KERNEL32!CreateEventW` at `0x10035205`
- `KERNEL32!CreateEventW` at `0x1003525f`
- `KERNEL32!CloseHandle` at `0x1003527c`
- `KERNEL32!CloseHandle` at `0x1003540e`
- `KERNEL32!CloseHandle` at `0x10035418`
- `KERNEL32!CloseHandle` at `0x1003527c`
- `KERNEL32!CloseHandle` at `0x1003540e`
- `KERNEL32!CloseHandle` at `0x10035418`
- `KERNEL32!GetOverlappedResult` at `0x1003544e`
- `KERNEL32!GetOverlappedResult` at `0x10035492`
- `KERNEL32!GetOverlappedResult` at `0x100354f9`
- `KERNEL32!GetOverlappedResult` at `0x10035588`
- `KERNEL32!GetOverlappedResult` at `0x1003544e`
- `KERNEL32!GetOverlappedResult` at `0x10035492`
- `KERNEL32!GetOverlappedResult` at `0x100354f9`
- `KERNEL32!GetOverlappedResult` at `0x10035588`
- `KERNEL32!DeviceIoControl` at `0x10035307`
- `KERNEL32!DeviceIoControl` at `0x1003536e`
- `KERNEL32!DeviceIoControl` at `0x10035307`
- `KERNEL32!DeviceIoControl` at `0x1003536e`
- `ntdll!RtlNtStatusToDosError` at `0x10035540`
- `ntdll!RtlNtStatusToDosError` at `0x10035540`

## pseudocode

```c
ULONG __stdcall CKsQualityF::QualityThread(HANDLE *Parameter)
{
  signed int v1; // ebx
  signed int LastError; // eax
  unsigned int v3; // ecx
  ULONG result; // eax
  HANDLE EventW; // eax
  signed int v6; // esi
  HANDLE *v7; // esi
  int v8; // ecx
  signed int v9; // eax
  int v10; // edi
  signed int v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v18; // ecx
  signed int v19; // eax
  int v20; // [esp+18h] [ebp-A4h]
  DWORD BytesReturned; // [esp+1Ch] [ebp-A0h] BYREF
  int v22; // [esp+20h] [ebp-9Ch]
  int v23; // [esp+24h] [ebp-98h]
  HANDLE *v24; // [esp+28h] [ebp-94h]
  int v25; // [esp+2Ch] [ebp-90h] BYREF
  struct _OVERLAPPED Overlapped; // [esp+30h] [ebp-8Ch] BYREF
  _DWORD **OutBuffer; // [esp+44h] [ebp-78h] BYREF
  int v28; // [esp+48h] [ebp-74h]
  int v29; // [esp+4Ch] [ebp-70h]
  int v30; // [esp+50h] [ebp-6Ch]
  struct _OVERLAPPED v31; // [esp+58h] [ebp-64h] BYREF
  NTSTATUS Status[2]; // [esp+6Ch] [ebp-50h] BYREF
  GUID InBuffer; // [esp+74h] [ebp-48h] BYREF
  int v34; // [esp+84h] [ebp-38h]
  int v35; // [esp+88h] [ebp-34h]
  GUID v36; // [esp+8Ch] [ebp-30h] BYREF
  int v37; // [esp+9Ch] [ebp-20h]
  int v38; // [esp+A0h] [ebp-1Ch]
  HANDLE Handles[4]; // [esp+A8h] [ebp-14h] BYREF

  v24 = Parameter;
  v1 = 0;
  InBuffer = _GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000;
  v34 = 0;
  memset(&Overlapped, 0, 16);
  v35 = 1;
  Overlapped.hEvent = CreateEventW(0, 1, 0, 0);
  if ( Overlapped.hEvent == (HANDLE)-1 )
  {
    LastError = GetLastError();
    v3 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return LastError;
    return v3;
  }
  v36 = _GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000;
  v37 = 1;
  memset(&v31, 0, 16);
  v38 = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  v31.hEvent = EventW;
  if ( EventW == (HANDLE)-1 )
  {
    v6 = GetLastError();
    CloseHandle(Overlapped.hEvent);
    result = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      return v6;
    return result;
  }
  v7 = v24;
  Handles[0] = Overlapped.hEvent;
  Handles[1] = EventW;
  v8 = 1;
  Handles[2] = v24[8];
  Handles[3] = v24[6];
  v20 = 1;
  v22 = 1;
  v23 = 0;
  while ( 1 )
  {
    OutBuffer = 0;
    *(_QWORD *)Status = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    if ( !v8 )
      goto LABEL_17;
    if ( !DeviceIoControl(v7[4], 0x2F0003u, &InBuffer, 0x18u, &OutBuffer, 0x10u, &BytesReturned, &Overlapped) )
      break;
    SetEvent(Overlapped.hEvent);
LABEL_16:
    v20 = 0;
LABEL_17:
    v10 = v22;
    if ( v22 )
    {
      if ( DeviceIoControl(v7[4], 0x2F0003u, &v36, 0x18u, Status, 8u, &BytesReturned, &v31) )
      {
        SetEvent(v31.hEvent);
      }
      else
      {
        v11 = GetLastError();
        v1 = (unsigned __int16)v11 | 0x80070000;
        if ( v11 <= 0 )
          v1 = v11;
        if ( v1 != -2147023899 )
          goto LABEL_59;
      }
      v10 = 0;
      v22 = 0;
    }
    if ( !v23 )
    {
      v12 = WaitForMultipleObjects(4u, Handles, 0, 0xFFFFFFFF);
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              v1 = -2147024637;
              goto LABEL_30;
            }
            goto LABEL_56;
          }
          v23 = 1;
          if ( GetOverlappedResult(v7[4], &Overlapped, &BytesReturned, 0) )
          {
            v20 = 1;
LABEL_37:
            if ( GetOverlappedResult(v7[4], &v31, &BytesReturned, 0) )
            {
              v10 = 1;
              v22 = 1;
            }
            else
            {
              v16 = GetLastError();
              v1 = (unsigned __int16)v16 | 0x80070000;
              if ( v16 <= 0 )
                v1 = v16;
              if ( v1 == -2147023900 )
                v1 = 0;
            }
            v8 = v20;
            if ( v20 || v10 )
              goto LABEL_57;
            SetEvent(v7[7]);
            v23 = 0;
            goto LABEL_56;
          }
          v15 = GetLastError();
          v1 = (unsigned __int16)v15 | 0x80070000;
          if ( v15 <= 0 )
            v1 = v15;
          if ( v1 == -2147023900 )
          {
            v1 = 0;
            goto LABEL_37;
          }
        }
        else if ( GetOverlappedResult(v7[4], &v31, &BytesReturned, 1) )
        {
          if ( ((int (__thiscall *)(_DWORD, _DWORD **, GUID *, int *))**OutBuffer)(
                 **OutBuffer,
                 OutBuffer,
                 &_GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770,
                 &v25) >= 0 )
          {
            (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v25 + 8))(*(_DWORD *)(*(_DWORD *)v25 + 8), v25);
            v17 = RtlNtStatusToDosError(Status[1]);
            v18 = (unsigned __int16)v17 | 0x80070000;
            if ( v17 <= 0 )
              v18 = v17;
            (*(void (__thiscall **)(_DWORD, int, int, unsigned int, _DWORD))(*(_DWORD *)v25 + 12))(
              *(_DWORD *)(*(_DWORD *)v25 + 12),
              v25,
              3,
              v18,
              0);
          }
          v7 = v24;
          v22 = 1;
        }
        else
        {
LABEL_54:
          v19 = GetLastError();
          v1 = (unsigned __int16)v19 | 0x80070000;
          if ( v19 <= 0 )
            v1 = v19;
        }
LABEL_56:
        v8 = v20;
        goto LABEL_57;
      }
    }
    if ( !GetOverlappedResult(v7[4], &Overlapped, &BytesReturned, 1) )
      goto LABEL_54;
    ((void (__thiscall *)(_DWORD, _DWORD **, int, int, int))(*OutBuffer)[15])(
      (*OutBuffer)[15],
      OutBuffer,
      v28,
      v29,
      v30);
    v7 = v24;
    v8 = 1;
    v20 = 1;
LABEL_57:
    if ( v1 < 0 )
      goto LABEL_30;
  }
  v9 = GetLastError();
  v1 = (unsigned __int16)v9 | 0x80070000;
  if ( v9 <= 0 )
    v1 = v9;
  if ( v1 == -2147023899 )
    goto LABEL_16;
LABEL_59:
  v1 = 0;
LABEL_30:
  CancelIoEx(v7[4], &Overlapped);
  CancelIoEx(v7[4], &v31);
  CloseHandle(Overlapped.hEvent);
  CloseHandle(v31.hEvent);
  return v1;
}

```

## disassembly

```asm
0x100351b0  mov     edi, edi
0x100351b2  push    ebp
0x100351b3  mov     ebp, esp
0x100351b5  and     esp, 0FFFFFFF8h
0x100351b8  sub     esp, 0A4h
0x100351be  mov     eax, ___security_cookie
0x100351c3  xor     eax, esp
0x100351c5  mov     [esp+0A4h+var_4], eax
0x100351cc  mov     eax, [ebp+Parameter]
0x100351cf  xor     ecx, ecx
0x100351d1  push    ebx
0x100351d2  push    esi
0x100351d3  push    edi
0x100351d4  mov     esi, offset __GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000
0x100351d9  mov     [esp+0B0h+var_94], eax
0x100351dd  lea     edi, [esp+0B0h+InBuffer]
0x100351e1  xor     eax, eax
0x100351e3  xor     ebx, ebx
0x100351e5  inc     ecx
0x100351e6  push    ebx; lpName
0x100351e7  movsd
0x100351e8  push    ebx; bInitialState
0x100351e9  push    ecx; bManualReset
0x100351ea  push    ebx; lpEventAttributes
0x100351eb  movsd
0x100351ec  movsd
0x100351ed  movsd
0x100351ee  lea     edi, [esp+0C0h+Overlapped]
0x100351f2  mov     [esp+0C0h+var_38], ebx
0x100351f9  stosd
0x100351fa  mov     [esp+0C0h+var_34], ecx
0x10035201  stosd
0x10035202  stosd
0x10035203  stosd
0x10035204  stosd
0x10035205  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x1003520b  mov     [esp+0B0h+Overlapped.hEvent], eax
0x1003520f  cmp     eax, 0FFFFFFFFh
0x10035212  jnz     short loc_1003522F
0x10035214  call    ds:__imp__GetLastError@0; GetLastError()
0x1003521a  movzx   ecx, ax
0x1003521d  or      ecx, 80070000h
0x10035223  test    eax, eax
0x10035225  cmovle  ecx, eax
0x10035228  mov     eax, ecx
0x1003522a  jmp     loc_10035420
0x1003522f  mov     esi, offset __GUID_d16ad380_ac1a_11cf_a5d6_28db04c10000
0x10035234  lea     edi, [esp+0B0h+var_30]
0x1003523b  xor     eax, eax
0x1003523d  xor     ecx, ecx
0x1003523f  push    ebx; lpName
0x10035240  inc     ecx
0x10035241  movsd
0x10035242  push    ebx; bInitialState
0x10035243  push    ecx; bManualReset
0x10035244  push    ebx; lpEventAttributes
0x10035245  movsd
0x10035246  movsd
0x10035247  movsd
0x10035248  lea     edi, [esp+0C0h+var_64]
0x1003524c  mov     [esp+0C0h+var_20], ecx
0x10035253  stosd
0x10035254  mov     [esp+0C0h+var_1C], ecx
0x1003525b  stosd
0x1003525c  stosd
0x1003525d  stosd
0x1003525e  stosd
0x1003525f  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10035265  mov     ecx, eax
0x10035267  mov     [esp+0B0h+var_64.hEvent], ecx
0x1003526b  cmp     ecx, 0FFFFFFFFh
0x1003526e  jnz     short loc_10035294
0x10035270  call    ds:__imp__GetLastError@0; GetLastError()
0x10035276  push    [esp+0B0h+Overlapped.hEvent]; hObject
0x1003527a  mov     esi, eax
0x1003527c  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10035282  movzx   eax, si
0x10035285  or      eax, 80070000h
0x1003528a  test    esi, esi
0x1003528c  cmovle  eax, esi
0x1003528f  jmp     loc_10035420
0x10035294  mov     esi, [esp+0B0h+var_94]
0x10035298  mov     eax, [esp+0B0h+Overlapped.hEvent]
0x1003529c  mov     [esp+0B0h+Handles], eax
0x100352a3  mov     [esp+0B0h+var_10], ecx
0x100352aa  xor     ecx, ecx
0x100352ac  mov     eax, [esi+20h]
0x100352af  inc     ecx
0x100352b0  mov     [esp+0B0h+var_C], eax
0x100352b7  mov     eax, [esi+18h]
0x100352ba  mov     [esp+0B0h+var_8], eax
0x100352c1  xor     eax, eax
0x100352c3  inc     eax
0x100352c4  mov     [esp+0B0h+var_A4], ecx
0x100352c8  mov     [esp+0B0h+var_9C], eax
0x100352cc  mov     [esp+0B0h+var_98], ebx
0x100352d0  xor     eax, eax
0x100352d2  lea     edi, [esp+0B0h+OutBuffer]
0x100352d6  stosd
0x100352d7  xorps   xmm0, xmm0
0x100352da  movlpd  qword ptr [esp+0B0h+Status], xmm0
0x100352e0  stosd
0x100352e1  stosd
0x100352e2  stosd
0x100352e3  test    ecx, ecx
0x100352e5  jz      short loc_10035343
0x100352e7  lea     eax, [esp+0B0h+Overlapped]
0x100352eb  push    eax; lpOverlapped
0x100352ec  lea     eax, [esp+0B4h+BytesReturned]
0x100352f0  push    eax; lpBytesReturned
0x100352f1  push    10h; nOutBufferSize
0x100352f3  lea     eax, [esp+0BCh+OutBuffer]
0x100352f7  push    eax; lpOutBuffer
0x100352f8  push    18h; nInBufferSize
0x100352fa  lea     eax, [esp+0C4h+InBuffer]
0x100352fe  push    eax; lpInBuffer
0x100352ff  push    2F0003h; dwIoControlCode
0x10035304  push    dword ptr [esi+10h]; hDevice
0x10035307  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x1003530d  test    eax, eax
0x1003530f  jz      short loc_1003531D
0x10035311  push    [esp+0B0h+Overlapped.hEvent]; hEvent
0x10035315  call    ds:__imp__SetEvent@4; SetEvent(x)
0x1003531b  jmp     short loc_1003533D
0x1003531d  call    ds:__imp__GetLastError@0; GetLastError()
0x10035323  movzx   ebx, ax
0x10035326  or      ebx, 80070000h
0x1003532c  test    eax, eax
0x1003532e  cmovle  ebx, eax
0x10035331  cmp     ebx, 800703E5h
0x10035337  jnz     loc_100355E3
0x1003533d  xor     eax, eax
0x1003533f  mov     [esp+0B0h+var_A4], eax
0x10035343  mov     edi, [esp+0B0h+var_9C]
0x10035347  test    edi, edi
0x10035349  jz      short loc_100353AA
0x1003534b  lea     eax, [esp+0B0h+var_64]
0x1003534f  push    eax; lpOverlapped
0x10035350  lea     eax, [esp+0B4h+BytesReturned]
0x10035354  push    eax; lpBytesReturned
0x10035355  push    8; nOutBufferSize
0x10035357  lea     eax, [esp+0BCh+Status]
0x1003535b  push    eax; lpOutBuffer
0x1003535c  push    18h; nInBufferSize
0x1003535e  lea     eax, [esp+0C4h+var_30]
0x10035365  push    eax; lpInBuffer
0x10035366  push    2F0003h; dwIoControlCode
0x1003536b  push    dword ptr [esi+10h]; hDevice
0x1003536e  call    ds:__imp__DeviceIoControl@32; DeviceIoControl(x,x,x,x,x,x,x,x)
0x10035374  test    eax, eax
0x10035376  jz      short loc_10035384
0x10035378  push    [esp+0B0h+var_64.hEvent]; hEvent
0x1003537c  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10035382  jmp     short loc_100353A4
0x10035384  call    ds:__imp__GetLastError@0; GetLastError()
0x1003538a  movzx   ebx, ax
0x1003538d  or      ebx, 80070000h
0x10035393  test    eax, eax
0x10035395  cmovle  ebx, eax
0x10035398  cmp     ebx, 800703E5h
0x1003539e  jnz     loc_100355E3
0x100353a4  xor     edi, edi
0x100353a6  mov     [esp+0B0h+var_9C], edi
0x100353aa  cmp     [esp+0B0h+var_98], 0
0x100353af  jnz     loc_10035579
0x100353b5  push    0FFFFFFFFh; dwMilliseconds
0x100353b7  push    0; bWaitAll
0x100353b9  lea     eax, [esp+0B8h+Handles]
0x100353c0  push    eax; lpHandles
0x100353c1  push    4; nCount
0x100353c3  call    ds:__imp__WaitForMultipleObjects@16; WaitForMultipleObjects(x,x,x,x)
0x100353c9  sub     eax, 0
0x100353cc  jz      loc_10035579
0x100353d2  sub     eax, 1
0x100353d5  jz      loc_100354EA
0x100353db  sub     eax, 1
0x100353de  jz      short loc_10035437
0x100353e0  sub     eax, 1
0x100353e3  jnz     loc_100355D2
0x100353e9  mov     ebx, 80070103h
0x100353ee  lea     eax, [esp+0B0h+Overlapped]
0x100353f2  push    eax; lpOverlapped
0x100353f3  push    dword ptr [esi+10h]; hFile
0x100353f6  call    ds:__imp__CancelIoEx@8; CancelIoEx(x,x)
0x100353fc  lea     eax, [esp+0B0h+var_64]
0x10035400  push    eax; lpOverlapped
0x10035401  push    dword ptr [esi+10h]; hFile
0x10035404  call    ds:__imp__CancelIoEx@8; CancelIoEx(x,x)
0x1003540a  push    [esp+0B0h+Overlapped.hEvent]; hObject
0x1003540e  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x10035414  push    [esp+0B0h+var_64.hEvent]; hObject
0x10035418  call    ds:__imp__CloseHandle@4; CloseHandle(x)
0x1003541e  mov     eax, ebx
0x10035420  mov     ecx, [esp+0B0h+var_4]
0x10035427  pop     edi
0x10035428  pop     esi
0x10035429  pop     ebx
0x1003542a  xor     ecx, esp; StackCookie
0x1003542c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10035431  mov     esp, ebp
0x10035433  pop     ebp
0x10035434  retn    4
0x10035437  push    0; bWait
0x10035439  lea     eax, [esp+0B4h+BytesReturned]
0x1003543d  mov     [esp+0B4h+var_98], 1
0x10035445  push    eax; lpNumberOfBytesTransferred
0x10035446  lea     eax, [esp+0B8h+Overlapped]
0x1003544a  push    eax; lpOverlapped
0x1003544b  push    dword ptr [esi+10h]; hFile
0x1003544e  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x10035454  test    eax, eax
0x10035456  jz      short loc_10035461
0x10035458  xor     eax, eax
0x1003545a  inc     eax
0x1003545b  mov     [esp+0B0h+var_A4], eax
0x1003545f  jmp     short loc_10035483
0x10035461  call    ds:__imp__GetLastError@0; GetLastError()
0x10035467  movzx   ebx, ax
0x1003546a  or      ebx, 80070000h
0x10035470  test    eax, eax
0x10035472  cmovle  ebx, eax
0x10035475  cmp     ebx, 800703E4h
0x1003547b  jnz     loc_100355D2
0x10035481  xor     ebx, ebx
0x10035483  push    0; bWait
0x10035485  lea     eax, [esp+0B4h+BytesReturned]
0x10035489  push    eax; lpNumberOfBytesTransferred
0x1003548a  lea     eax, [esp+0B8h+var_64]
0x1003548e  push    eax; lpOverlapped
0x1003548f  push    dword ptr [esi+10h]; hFile
0x10035492  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x10035498  test    eax, eax
0x1003549a  jz      short loc_100354A5
0x1003549c  xor     edi, edi
0x1003549e  inc     edi
0x1003549f  mov     [esp+0B0h+var_9C], edi
0x100354a3  jmp     short loc_100354C4
0x100354a5  call    ds:__imp__GetLastError@0; GetLastError()
0x100354ab  movzx   ebx, ax
0x100354ae  or      ebx, 80070000h
0x100354b4  test    eax, eax
0x100354b6  cmovle  ebx, eax
0x100354b9  xor     eax, eax
0x100354bb  cmp     ebx, 800703E4h
0x100354c1  cmovz   ebx, eax
0x100354c4  mov     ecx, [esp+0B0h+var_A4]
0x100354c8  test    ecx, ecx
0x100354ca  jnz     loc_100355D6
0x100354d0  test    edi, edi
0x100354d2  jnz     loc_100355D6
0x100354d8  push    dword ptr [esi+1Ch]; hEvent
0x100354db  call    ds:__imp__SetEvent@4; SetEvent(x)
0x100354e1  mov     [esp+0B0h+var_98], edi
0x100354e5  jmp     loc_100355D2
0x100354ea  push    1; bWait
0x100354ec  lea     eax, [esp+0B4h+BytesReturned]
0x100354f0  push    eax; lpNumberOfBytesTransferred
0x100354f1  lea     eax, [esp+0B8h+var_64]
0x100354f5  push    eax; lpOverlapped
0x100354f6  push    dword ptr [esi+10h]; hFile
0x100354f9  call    ds:__imp__GetOverlappedResult@16; GetOverlappedResult(x,x,x,x)
0x100354ff  test    eax, eax
0x10035501  jz      loc_100355BE
0x10035507  mov     ecx, [esp+0B0h+OutBuffer]
0x1003550b  mov     eax, [ecx]
0x1003550d  mov     esi, [eax]
0x1003550f  lea     eax, [esp+0B0h+var_90]
0x10035513  push    eax
0x10035514  push    offset __GUID_56a868a2_0ad4_11ce_b03a_0020af0ba770
0x10035519  push    ecx
0x1003551a  mov     ecx, esi; this
0x1003551c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10035522  call    esi
0x10035524  test    eax, eax
0x10035526  js      short loc_1003556C
0x10035528  mov     eax, [esp+0B0h+var_90]
0x1003552c  push    eax
0x1003552d  mov     ecx, [eax]
0x1003552f  mov     esi, [ecx+8]
0x10035532  mov     ecx, esi; this
0x10035534  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x1003553a  call    esi
0x1003553c  push    [esp+0B0h+Status+4]; Status
0x10035540  call    ds:__imp__RtlNtStatusToDosError@4; RtlNtStatusToDosError(x)
0x10035546  mov     edx, [esp+0B0h+var_90]
0x1003554a  movzx   ecx, ax
0x1003554d  or      ecx, 80070000h
0x10035553  test    eax, eax
0x10035555  push    0
0x10035557  mov     esi, [edx]
0x10035559  cmovle  ecx, eax
0x1003555c  push    ecx
0x1003555d  push    3
0x1003555f  push    edx
0x10035560  mov     ecx, [esi+0Ch]; this
0x10035563  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10035569  call    dword ptr [esi+0Ch]
0x1003556c  mov     esi, [esp+0B0h+var_94]
0x10035570  xor     eax, eax
0x10035572  inc     eax
  ... truncated ...
```
