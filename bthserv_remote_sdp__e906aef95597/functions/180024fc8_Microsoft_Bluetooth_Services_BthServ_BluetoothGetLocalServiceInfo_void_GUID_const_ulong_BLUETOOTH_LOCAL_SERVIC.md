# Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO *)

- ea: `0x180024fc8`
- end: `0x1800252fc`
- name: `?BluetoothGetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEAU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z`
- size: `820`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _GUID *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024fc8`
- `0x180025648`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x180024a8c`
- `0x180024ebc`
- `0x180024fc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002515c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002522c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002515c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002522c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800252ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025240`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025240`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800252c2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025173`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002513a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002513a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800251f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002520e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002520e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180025283`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025053`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180025053`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002519a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18002519a`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800251cf`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800251cf`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025220`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025220`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3,
        __int64 a4)
{
  unsigned int v5; // r12d
  unsigned int v6; // r14d
  int v7; // eax
  _WORD *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _BYTE *v11; // r8
  __int16 v12; // ax
  bool v13; // zf
  _WORD *v14; // rax
  char *v15; // rcx
  signed __int64 v16; // r8
  __int16 v17; // ax
  char *v18; // rax
  Microsoft::Bluetooth::Services::BthServ *v19; // rsi
  HANDLE ProcessHeap; // rax
  _QWORD *v21; // rdi
  __int64 DeviceInfoList; // rax
  void **v23; // r8
  DWORD LastError; // ebx
  void *v25; // rdx
  HANDLE v26; // rax
  int v27; // ebx
  unsigned int LocalServiceInfo; // eax
  void *v29; // rdx
  void **v30; // r8
  HANDLE v31; // rax
  struct _BLUETOOTH_LOCAL_SERVICE_INFO *lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  int v36; // [rsp+60h] [rbp-A0h]
  int v37; // [rsp+64h] [rbp-9Ch]
  __int64 v38; // [rsp+68h] [rbp-98h]
  char v39; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v40[528]; // [rsp+270h] [rbp+170h] BYREF

  v5 = (unsigned int)a3;
  if ( this )
  {
    v36 = (int)a3;
    BytesReturned[0] = 0;
    v6 = 0;
    OutBuffer = SerialPortServiceClass_UUID;
    if ( DeviceIoControl(this, 0x411048u, &OutBuffer, 0x14u, &OutBuffer, 0x422u, BytesReturned, 0) )
    {
      v7 = v37;
      v8 = (_WORD *)(a4 + 16);
      *(_DWORD *)a4 = v37;
      if ( v7 )
      {
        v9 = 256;
        *(_QWORD *)(a4 + 8) = v38;
        v10 = 256;
        v11 = (_BYTE *)(v40 - (_BYTE *)v8);
        do
        {
          if ( v10 == -2147483390 )
            break;
          v12 = *(_WORD *)((char *)v8 + (_QWORD)v11);
          if ( !v12 )
            break;
          *v8++ = v12;
          --v10;
        }
        while ( v10 );
        v13 = v10 == 0;
        v14 = v8 - 1;
        v15 = (char *)(a4 + 528);
        if ( !v13 )
          v14 = v8;
        v16 = &v39 - v15;
        *v14 = 0;
        do
        {
          if ( v9 == -2147483390 )
            break;
          v17 = *(_WORD *)&v15[v16];
          if ( !v17 )
            break;
          *(_WORD *)v15 = v17;
          v15 += 2;
          --v9;
        }
        while ( v9 );
        v18 = v15 - 2;
        if ( v9 )
          v18 = v15;
        *(_WORD *)v18 = 0;
      }
      else
      {
        *(_QWORD *)(a4 + 8) = 0;
        memset_0((void *)(a4 + 528), 0, 0x200u);
        memset_0((void *)(a4 + 16), 0, 0x200u);
      }
    }
    else
    {
      return GetLastError();
    }
  }
  else
  {
    *(_QWORD *)BytesReturned = 0;
    v6 = 20;
    v19 = 0;
    ProcessHeap = GetProcessHeap();
    v21 = HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( v21 )
    {
      DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
      v21[1] = DeviceInfoList;
      if ( DeviceInfoList == -1 )
      {
        v31 = GetProcessHeap();
        HeapFree(v31, 0, v21);
      }
      else
      {
        if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
        {
          v19 = (Microsoft::Bluetooth::Services::BthServ *)v21;
          if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                                (Microsoft::Bluetooth::Services::BthServ *)v21,
                                BytesReturned,
                                v23) )
          {
            LastError = GetLastError();
            Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
              (Microsoft::Bluetooth::Services::BthServ *)v21,
              v25);
            v19 = 0;
            SetLastError(LastError);
          }
        }
        else
        {
          DevObjDestroyDeviceInfoList(v21[1]);
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v21);
        }
        if ( v19 )
        {
          v27 = 0;
          do
          {
            LocalServiceInfo = Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(
                                 *(Microsoft::Bluetooth::Services::BthServ **)BytesReturned,
                                 (void *)&SerialPortServiceClass_UUID,
                                 (const struct _GUID *)v5,
                                 a4,
                                 lpOutBuffer);
            v6 = LocalServiceInfo;
            if ( !LocalServiceInfo || LocalServiceInfo == 234 )
              v27 = 1;
            CloseHandle(*(HANDLE *)BytesReturned);
          }
          while ( !v27
               && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v19, BytesReturned, v30) );
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v19, v29);
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180024fc8  mov     [rsp-8+arg_8], rbx
0x180024fcd  push    rbp
0x180024fce  push    rsi
0x180024fcf  push    rdi
0x180024fd0  push    r12
0x180024fd2  push    r13
0x180024fd4  push    r14
0x180024fd6  push    r15
0x180024fd8  lea     rbp, [rsp-390h]
0x180024fe0  sub     rsp, 490h
0x180024fe7  mov     rax, cs:__security_cookie
0x180024fee  xor     rax, rsp
0x180024ff1  mov     [rbp+3C0h+var_40], rax
0x180024ff8  xor     r13d, r13d
0x180024ffb  mov     r15, r9
0x180024ffe  mov     r12d, r8d
0x180025001  test    rcx, rcx
0x180025004  jz      loc_18002514E
0x18002500a  movups  xmm0, xmmword ptr cs:SerialPortServiceClass_UUID.Data1
0x180025011  mov     [rsp+4C0h+lpOverlapped], r13; lpOverlapped
0x180025016  lea     rax, [rsp+4C0h+BytesReturned]
0x18002501b  mov     [rsp+4C0h+lpBytesReturned], rax; lpBytesReturned
0x180025020  lea     r9d, [r13+14h]; nInBufferSize
0x180025024  lea     rax, [rsp+4C0h+OutBuffer]
0x180025029  mov     [rsp+4C0h+var_460], r8d
0x18002502e  mov     [rsp+4C0h+nOutBufferSize], 422h; nOutBufferSize
0x180025036  lea     r8, [rsp+4C0h+OutBuffer]; lpInBuffer
0x18002503b  mov     edx, 411048h; dwIoControlCode
0x180025040  mov     [rsp+4C0h+lpOutBuffer], rax; lpOutBuffer
0x180025045  mov     [rsp+4C0h+BytesReturned], r13d
0x18002504a  mov     r14d, r13d
0x18002504d  movdqu  [rsp+4C0h+OutBuffer], xmm0
0x180025053  call    cs:__imp_DeviceIoControl
0x18002505a  nop     dword ptr [rax+rax+00h]
0x18002505f  test    eax, eax
0x180025061  jz      loc_18002513A
0x180025067  mov     eax, [rsp+4C0h+var_45C]
0x18002506b  lea     rbx, [r15+10h]
0x18002506f  mov     [r15], eax
0x180025072  test    eax, eax
0x180025074  jz      loc_18002510C
0x18002507a  mov     rax, [rsp+4C0h+var_458]
0x18002507f  lea     r8, [rbp+3C0h+var_250]
0x180025086  mov     edx, 100h
0x18002508b  mov     [r15+8], rax
0x18002508f  mov     ecx, edx
0x180025091  sub     r8, rbx
0x180025094  lea     rax, [rcx+7FFFFEFEh]
0x18002509b  test    rax, rax
0x18002509e  jz      short loc_1800250B7
0x1800250a0  movzx   eax, word ptr [r8+rbx]
0x1800250a5  test    ax, ax
0x1800250a8  jz      short loc_1800250B7
0x1800250aa  mov     [rbx], ax
0x1800250ad  add     rbx, 2
0x1800250b1  sub     rcx, 1
0x1800250b5  jnz     short loc_180025094
0x1800250b7  test    rcx, rcx
0x1800250ba  lea     rax, [rbx-2]
0x1800250be  lea     rcx, [r15+210h]
0x1800250c5  cmovnz  rax, rbx
0x1800250c9  lea     r8, [rsp+4C0h+var_450]
0x1800250ce  sub     r8, rcx
0x1800250d1  mov     [rax], r13w
0x1800250d5  lea     rax, [rdx+7FFFFEFEh]
0x1800250dc  test    rax, rax
0x1800250df  jz      short loc_1800250F8
0x1800250e1  movzx   eax, word ptr [r8+rcx]
0x1800250e6  test    ax, ax
0x1800250e9  jz      short loc_1800250F8
0x1800250eb  mov     [rcx], ax
0x1800250ee  add     rcx, 2
0x1800250f2  sub     rdx, 1
0x1800250f6  jnz     short loc_1800250D5
0x1800250f8  test    rdx, rdx
0x1800250fb  lea     rax, [rcx-2]
0x1800250ff  cmovnz  rax, rcx
0x180025103  mov     [rax], r13w
0x180025107  jmp     loc_1800252CE
0x18002510c  xor     eax, eax
0x18002510e  lea     rcx, [r15+210h]; void *
0x180025115  mov     edi, 200h
0x18002511a  mov     [r15+8], rax
0x18002511e  mov     r8d, edi; Size
0x180025121  xor     edx, edx; Val
0x180025123  call    memset_0
0x180025128  mov     r8d, edi; Size
0x18002512b  xor     edx, edx; Val
0x18002512d  mov     rcx, rbx; void *
0x180025130  call    memset_0
0x180025135  jmp     loc_1800252CE
0x18002513a  call    cs:__imp_GetLastError
0x180025141  nop     dword ptr [rax+rax+00h]
0x180025146  mov     r14d, eax
0x180025149  jmp     loc_1800252CE
0x18002514e  mov     qword ptr [rsp+4C0h+BytesReturned], r13
0x180025153  mov     r14d, 14h
0x180025159  mov     rsi, r13
0x18002515c  call    cs:__imp_GetProcessHeap
0x180025163  nop     dword ptr [rax+rax+00h]
0x180025168  mov     rcx, rax; hHeap
0x18002516b  lea     edx, [r14-0Ch]; dwFlags
0x18002516f  lea     r8d, [r14-4]; dwBytes
0x180025173  call    cs:__imp_HeapAlloc
0x18002517a  nop     dword ptr [rax+rax+00h]
0x18002517f  mov     rdi, rax
0x180025182  test    rax, rax
0x180025185  jz      loc_1800252CE
0x18002518b  xor     r9d, r9d
0x18002518e  mov     [rsp+4C0h+lpOutBuffer], r13
0x180025193  xor     r8d, r8d
0x180025196  xor     edx, edx
0x180025198  xor     ecx, ecx
0x18002519a  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800251a1  nop     dword ptr [rax+rax+00h]
0x1800251a6  mov     [rdi+8], rax
0x1800251aa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800251ae  jz      loc_1800252AE
0x1800251b4  mov     qword ptr [rsp+4C0h+nOutBufferSize], r13
0x1800251b9  lea     r9d, [r14-2]
0x1800251bd  xor     r8d, r8d
0x1800251c0  mov     [rsp+4C0h+lpOutBuffer], r13; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x1800251c5  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x1800251cc  mov     rcx, rax
0x1800251cf  call    cs:__imp_DevObjGetClassDevs
0x1800251d6  nop     dword ptr [rax+rax+00h]
0x1800251db  test    eax, eax
0x1800251dd  jz      short loc_18002521C
0x1800251df  lea     rdx, [rsp+4C0h+BytesReturned]; void *
0x1800251e4  mov     rcx, rdi; this
0x1800251e7  mov     rsi, rdi
0x1800251ea  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800251ef  test    eax, eax
0x1800251f1  jnz     short loc_18002524C
0x1800251f3  call    cs:__imp_GetLastError
0x1800251fa  nop     dword ptr [rax+rax+00h]
0x1800251ff  mov     rcx, rdi; this
0x180025202  mov     ebx, eax
0x180025204  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x180025209  mov     ecx, ebx; dwErrCode
0x18002520b  mov     rsi, r13
0x18002520e  call    cs:__imp_SetLastError
0x180025215  nop     dword ptr [rax+rax+00h]
0x18002521a  jmp     short loc_18002524C
0x18002521c  mov     rcx, [rdi+8]
0x180025220  call    cs:__imp_DevObjDestroyDeviceInfoList
0x180025227  nop     dword ptr [rax+rax+00h]
0x18002522c  call    cs:__imp_GetProcessHeap
0x180025233  nop     dword ptr [rax+rax+00h]
0x180025238  mov     r8, rdi; lpMem
0x18002523b  xor     edx, edx; dwFlags
0x18002523d  mov     rcx, rax; hHeap
0x180025240  call    cs:__imp_HeapFree
0x180025247  nop     dword ptr [rax+rax+00h]
0x18002524c  test    rsi, rsi
0x18002524f  jz      short loc_1800252CE
0x180025251  mov     ebx, r13d
0x180025254  mov     rcx, qword ptr [rsp+4C0h+BytesReturned]; this
0x180025259  lea     rdx, SerialPortServiceClass_UUID; void *
0x180025260  mov     r9, r15; unsigned int
0x180025263  mov     r8d, r12d; struct _GUID *
0x180025266  call    ?BluetoothGetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEAU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothGetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO *)
0x18002526b  mov     r14d, eax
0x18002526e  test    eax, eax
0x180025270  jz      short loc_180025279
0x180025272  cmp     eax, 0EAh
0x180025277  jnz     short loc_18002527E
0x180025279  mov     ebx, 1
0x18002527e  mov     rcx, qword ptr [rsp+4C0h+BytesReturned]; hObject
0x180025283  call    cs:__imp_CloseHandle
0x18002528a  nop     dword ptr [rax+rax+00h]
0x18002528f  test    ebx, ebx
0x180025291  jnz     short loc_1800252A4
0x180025293  lea     rdx, [rsp+4C0h+BytesReturned]; void *
0x180025298  mov     rcx, rsi; this
0x18002529b  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800252a0  test    eax, eax
0x1800252a2  jnz     short loc_180025254
0x1800252a4  mov     rcx, rsi; this
0x1800252a7  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x1800252ac  jmp     short loc_1800252CE
0x1800252ae  call    cs:__imp_GetProcessHeap
0x1800252b5  nop     dword ptr [rax+rax+00h]
0x1800252ba  mov     r8, rdi; lpMem
0x1800252bd  xor     edx, edx; dwFlags
0x1800252bf  mov     rcx, rax; hHeap
0x1800252c2  call    cs:__imp_HeapFree
0x1800252c9  nop     dword ptr [rax+rax+00h]
0x1800252ce  mov     eax, r14d
0x1800252d1  mov     rcx, [rbp+3C0h+var_40]
0x1800252d8  xor     rcx, rsp; StackCookie
0x1800252db  call    __security_check_cookie
0x1800252e0  mov     rbx, [rsp+4C0h+arg_8]
0x1800252e8  add     rsp, 490h
0x1800252ef  pop     r15
0x1800252f1  pop     r14
0x1800252f3  pop     r13
0x1800252f5  pop     r12
0x1800252f7  pop     rdi
0x1800252f8  pop     rsi
0x1800252f9  pop     rbp
0x1800252fa  retn
```
