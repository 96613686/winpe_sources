# Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO const *)

- ea: `0x180025304`
- end: `0x180025640`
- name: `?BluetoothSetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEBU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ *this, void *, const struct _GUID *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025304`
- `0x18002a4e4`

## callees

- `0x1800017a0`
- `0x180024a8c`
- `0x180024ebc`
- `0x180025304`
- `0x180027c48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800254a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800254a3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025586`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025607`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025586`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025607`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800254b9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800254b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025554`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800255c8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002546f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18002546f`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800254e0`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800254e0`
- `DEVOBJ!DevObjGetClassDevs` at `0x180025515`
- `DEVOBJ!DevObjGetClassDevs` at `0x180025515`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025566`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180025566`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(
        Microsoft::Bluetooth::Services::BthServ *this,
        void *a2,
        const struct _GUID *a3,
        int *a4)
{
  unsigned int v5; // r12d
  Microsoft::Bluetooth::Services::BthServ *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // r8
  __int16 v11; // ax
  Microsoft::Bluetooth::Services::BthServ *v12; // rax
  unsigned int v13; // edi
  __int64 v14; // r15
  __int16 v15; // ax
  Microsoft::Bluetooth::Services::BthServ *v16; // rax
  bool v17; // zf
  Microsoft::Bluetooth::Services::BthServ *v18; // r14
  HANDLE ProcessHeap; // rax
  _QWORD *v20; // rsi
  __int64 DeviceInfoList; // rax
  void **v22; // r8
  DWORD LastError; // ebx
  void *v24; // rdx
  HANDLE v25; // rax
  int v26; // ebx
  unsigned int v27; // eax
  void *v28; // rdx
  void **v29; // r8
  HANDLE v30; // rax
  const struct _BLUETOOTH_LOCAL_SERVICE_INFO *lpOutBuffer; // [rsp+20h] [rbp-E0h]
  HANDLE hDevice[2]; // [rsp+40h] [rbp-C0h] BYREF
  GUID InBuffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+64h] [rbp-9Ch]
  __int64 v37; // [rsp+68h] [rbp-98h]
  _BYTE v38[512]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v39[528]; // [rsp+270h] [rbp+170h] BYREF

  v5 = (unsigned int)a3;
  if ( this )
  {
    v7 = (Microsoft::Bluetooth::Services::BthServ *)v39;
    v36 = *a4;
    v8 = 256;
    v37 = *((_QWORD *)a4 + 1);
    v35 = (unsigned int)a3;
    v9 = (char *)a4 - v39;
    LODWORD(hDevice[0]) = 0;
    v10 = 256;
    InBuffer = SerialPortServiceClass_UUID;
    do
    {
      if ( v10 == -2147483390 )
        break;
      v11 = *(_WORD *)((char *)v7 + v9 + 16);
      if ( !v11 )
        break;
      *(_WORD *)v7 = v11;
      v7 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 + 2);
      --v10;
    }
    while ( v10 );
    v12 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 - 2);
    if ( v10 )
      v12 = v7;
    *(_WORD *)v12 = 0;
    v13 = v10 == 0 ? 0x8007007A : 0;
    if ( v10 )
    {
      v14 = (char *)a4 - v38;
      v7 = (Microsoft::Bluetooth::Services::BthServ *)v38;
      do
      {
        if ( v8 == -2147483390 )
          break;
        v15 = *(_WORD *)((char *)v7 + v14 + 528);
        if ( !v15 )
          break;
        *(_WORD *)v7 = v15;
        v7 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 + 2);
        --v8;
      }
      while ( v8 );
      v16 = (Microsoft::Bluetooth::Services::BthServ *)((char *)v7 - 2);
      if ( v8 )
        v16 = v7;
      v8 = -v8;
      v13 = v8 == 0 ? 0x8007007A : 0;
      *(_WORD *)v16 = 0;
    }
    if ( !v36 )
    {
      v17 = v13 == 0;
      if ( (v13 & 0x80000000) != 0 )
      {
LABEL_20:
        if ( v17 )
        {
          v13 = 0;
          if ( !DeviceIoControl(this, 0x41104Cu, &InBuffer, 0x422u, 0, 0, (LPDWORD)hDevice, 0) )
            return GetLastError();
        }
        return v13;
      }
      v13 = Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(
              v7,
              (void *)v8,
              (const struct _GUID *)v35,
              -2147024774);
    }
    v17 = v13 == 0;
    goto LABEL_20;
  }
  hDevice[0] = 0;
  v13 = 20;
  v18 = 0;
  ProcessHeap = GetProcessHeap();
  v20 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( v20 )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v20[1] = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v20);
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
      {
        v18 = (Microsoft::Bluetooth::Services::BthServ *)v20;
        if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                              (Microsoft::Bluetooth::Services::BthServ *)v20,
                              hDevice,
                              v22) )
        {
          LastError = GetLastError();
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
            (Microsoft::Bluetooth::Services::BthServ *)v20,
            v24);
          v18 = 0;
          SetLastError(LastError);
        }
      }
      else
      {
        DevObjDestroyDeviceInfoList(v20[1]);
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v20);
      }
      if ( v18 )
      {
        v26 = 0;
        do
        {
          v27 = Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(
                  (Microsoft::Bluetooth::Services::BthServ *)hDevice[0],
                  (void *)&SerialPortServiceClass_UUID,
                  (const struct _GUID *)v5,
                  (unsigned int)a4,
                  lpOutBuffer);
          v13 = v27;
          if ( !v27 || v27 == 234 )
            v26 = 1;
          CloseHandle(hDevice[0]);
        }
        while ( !v26 && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v18, hDevice, v29) );
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v18, v28);
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x180025304  mov     [rsp-8+arg_8], rbx
0x180025309  push    rbp
0x18002530a  push    rsi
0x18002530b  push    rdi
0x18002530c  push    r12
0x18002530e  push    r13
0x180025310  push    r14
0x180025312  push    r15
0x180025314  lea     rbp, [rsp-390h]
0x18002531c  sub     rsp, 490h
0x180025323  mov     rax, cs:__security_cookie
0x18002532a  xor     rax, rsp
0x18002532d  mov     [rbp+3C0h+var_40], rax
0x180025334  xor     r13d, r13d
0x180025337  mov     r15, r9
0x18002533a  mov     r12d, r8d
0x18002533d  mov     rbx, rcx
0x180025340  test    rcx, rcx
0x180025343  jz      loc_180025496
0x180025349  mov     eax, [r9]
0x18002534c  lea     rcx, [rbp+3C0h+var_250]
0x180025353  movups  xmm0, xmmword ptr cs:SerialPortServiceClass_UUID.Data1
0x18002535a  mov     dword ptr [rsp+4C0h+var_460+4], eax
0x18002535e  mov     edx, 100h
0x180025363  mov     rax, [r9+8]
0x180025367  mov     [rsp+4C0h+var_458], rax
0x18002536c  lea     rax, [rbp+3C0h+var_250]
0x180025373  mov     dword ptr [rsp+4C0h+var_460], r8d
0x180025378  sub     r9, rax
0x18002537b  mov     dword ptr [rsp+4C0h+hDevice], r13d
0x180025380  mov     r8d, edx
0x180025383  movdqu  [rsp+4C0h+InBuffer], xmm0
0x180025389  lea     rax, [r8+7FFFFEFEh]
0x180025390  test    rax, rax
0x180025393  jz      short loc_1800253AD
0x180025395  movzx   eax, word ptr [r9+rcx+10h]
0x18002539b  test    ax, ax
0x18002539e  jz      short loc_1800253AD
0x1800253a0  mov     [rcx], ax
0x1800253a3  add     rcx, 2
0x1800253a7  sub     r8, 1
0x1800253ab  jnz     short loc_180025389
0x1800253ad  test    r8, r8
0x1800253b0  lea     rax, [rcx-2]
0x1800253b4  mov     r9d, 8007007Ah; int
0x1800253ba  cmovnz  rax, rcx
0x1800253be  mov     [rax], r13w
0x1800253c2  mov     rax, r8
0x1800253c5  neg     rax
0x1800253c8  sbb     edi, edi
0x1800253ca  not     edi
0x1800253cc  and     edi, r9d
0x1800253cf  test    r8, r8
0x1800253d2  jz      short loc_180025421
0x1800253d4  lea     rax, [rsp+4C0h+var_450]
0x1800253d9  sub     r15, rax
0x1800253dc  lea     rcx, [rsp+4C0h+var_450]
0x1800253e1  lea     rax, [rdx+7FFFFEFEh]
0x1800253e8  test    rax, rax
0x1800253eb  jz      short loc_180025408
0x1800253ed  movzx   eax, word ptr [r15+rcx+210h]
0x1800253f6  test    ax, ax
0x1800253f9  jz      short loc_180025408
0x1800253fb  mov     [rcx], ax
0x1800253fe  add     rcx, 2; this
0x180025402  sub     rdx, 1
0x180025406  jnz     short loc_1800253E1
0x180025408  test    rdx, rdx
0x18002540b  lea     rax, [rcx-2]
0x18002540f  cmovnz  rax, rcx
0x180025413  neg     rdx; void *
0x180025416  sbb     edi, edi
0x180025418  not     edi
0x18002541a  and     edi, r9d
0x18002541d  mov     [rax], r13w
0x180025421  cmp     dword ptr [rsp+4C0h+var_460+4], r13d
0x180025426  jnz     short loc_180025438
0x180025428  test    edi, edi
0x18002542a  js      short loc_18002543A
0x18002542c  mov     r8d, dword ptr [rsp+4C0h+var_460]; struct _GUID *
0x180025431  call    ?BthpRemoveLocalDeviceInstance@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@H@Z; Microsoft::Bluetooth::Services::BthServ::BthpRemoveLocalDeviceInstance(void *,_GUID const *,int)
0x180025436  mov     edi, eax
0x180025438  test    edi, edi
0x18002543a  jnz     loc_180025613
0x180025440  mov     [rsp+4C0h+lpOverlapped], r13; lpOverlapped
0x180025445  lea     rax, [rsp+4C0h+hDevice]
0x18002544a  mov     [rsp+4C0h+lpBytesReturned], rax; lpBytesReturned
0x18002544f  lea     r8, [rsp+4C0h+InBuffer]; lpInBuffer
0x180025454  mov     [rsp+4C0h+nOutBufferSize], r13d; nOutBufferSize
0x180025459  mov     r9d, 422h; nInBufferSize
0x18002545f  mov     edx, 41104Ch; dwIoControlCode
0x180025464  mov     [rsp+4C0h+lpOutBuffer], r13; lpOutBuffer
0x180025469  mov     rcx, rbx; hDevice
0x18002546c  mov     edi, r13d
0x18002546f  call    cs:__imp_DeviceIoControl
0x180025476  nop     dword ptr [rax+rax+00h]
0x18002547b  test    eax, eax
0x18002547d  jnz     loc_180025613
0x180025483  call    cs:__imp_GetLastError
0x18002548a  nop     dword ptr [rax+rax+00h]
0x18002548f  mov     edi, eax
0x180025491  jmp     loc_180025613
0x180025496  mov     [rsp+4C0h+hDevice], r13
0x18002549b  mov     edi, 14h
0x1800254a0  mov     r14, r13
0x1800254a3  call    cs:__imp_GetProcessHeap
0x1800254aa  nop     dword ptr [rax+rax+00h]
0x1800254af  mov     rcx, rax; hHeap
0x1800254b2  lea     edx, [rdi-0Ch]; dwFlags
0x1800254b5  lea     r8d, [rdi-4]; dwBytes
0x1800254b9  call    cs:__imp_HeapAlloc
0x1800254c0  nop     dword ptr [rax+rax+00h]
0x1800254c5  mov     rsi, rax
0x1800254c8  test    rax, rax
0x1800254cb  jz      loc_180025613
0x1800254d1  xor     r9d, r9d
0x1800254d4  mov     [rsp+4C0h+lpOutBuffer], r13
0x1800254d9  xor     r8d, r8d
0x1800254dc  xor     edx, edx
0x1800254de  xor     ecx, ecx
0x1800254e0  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800254e7  nop     dword ptr [rax+rax+00h]
0x1800254ec  mov     [rsi+8], rax
0x1800254f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800254f4  jz      loc_1800255F3
0x1800254fa  mov     qword ptr [rsp+4C0h+nOutBufferSize], r13
0x1800254ff  lea     r9d, [rdi-2]
0x180025503  xor     r8d, r8d
0x180025506  mov     [rsp+4C0h+lpOutBuffer], r13; struct _BLUETOOTH_LOCAL_SERVICE_INFO *
0x18002550b  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x180025512  mov     rcx, rax
0x180025515  call    cs:__imp_DevObjGetClassDevs
0x18002551c  nop     dword ptr [rax+rax+00h]
0x180025521  test    eax, eax
0x180025523  jz      short loc_180025562
0x180025525  lea     rdx, [rsp+4C0h+hDevice]; void *
0x18002552a  mov     rcx, rsi; this
0x18002552d  mov     r14, rsi
0x180025530  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180025535  test    eax, eax
0x180025537  jnz     short loc_180025592
0x180025539  call    cs:__imp_GetLastError
0x180025540  nop     dword ptr [rax+rax+00h]
0x180025545  mov     rcx, rsi; this
0x180025548  mov     ebx, eax
0x18002554a  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x18002554f  mov     ecx, ebx; dwErrCode
0x180025551  mov     r14, r13
0x180025554  call    cs:__imp_SetLastError
0x18002555b  nop     dword ptr [rax+rax+00h]
0x180025560  jmp     short loc_180025592
0x180025562  mov     rcx, [rsi+8]
0x180025566  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18002556d  nop     dword ptr [rax+rax+00h]
0x180025572  call    cs:__imp_GetProcessHeap
0x180025579  nop     dword ptr [rax+rax+00h]
0x18002557e  mov     r8, rsi; lpMem
0x180025581  xor     edx, edx; dwFlags
0x180025583  mov     rcx, rax; hHeap
0x180025586  call    cs:__imp_HeapFree
0x18002558d  nop     dword ptr [rax+rax+00h]
0x180025592  test    r14, r14
0x180025595  jz      short loc_180025613
0x180025597  mov     ebx, r13d
0x18002559a  mov     rcx, [rsp+4C0h+hDevice]; this
0x18002559f  lea     rdx, SerialPortServiceClass_UUID; void *
0x1800255a6  mov     r9, r15; unsigned int
0x1800255a9  mov     r8d, r12d; struct _GUID *
0x1800255ac  call    ?BluetoothSetLocalServiceInfo@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_GUID@@KPEBU_BLUETOOTH_LOCAL_SERVICE_INFO@@@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothSetLocalServiceInfo(void *,_GUID const *,ulong,_BLUETOOTH_LOCAL_SERVICE_INFO const *)
0x1800255b1  mov     edi, eax
0x1800255b3  test    eax, eax
0x1800255b5  jz      short loc_1800255BE
0x1800255b7  cmp     eax, 0EAh
0x1800255bc  jnz     short loc_1800255C3
0x1800255be  mov     ebx, 1
0x1800255c3  mov     rcx, [rsp+4C0h+hDevice]; hObject
0x1800255c8  call    cs:__imp_CloseHandle
0x1800255cf  nop     dword ptr [rax+rax+00h]
0x1800255d4  test    ebx, ebx
0x1800255d6  jnz     short loc_1800255E9
0x1800255d8  lea     rdx, [rsp+4C0h+hDevice]; void *
0x1800255dd  mov     rcx, r14; this
0x1800255e0  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800255e5  test    eax, eax
0x1800255e7  jnz     short loc_18002559A
0x1800255e9  mov     rcx, r14; this
0x1800255ec  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x1800255f1  jmp     short loc_180025613
0x1800255f3  call    cs:__imp_GetProcessHeap
0x1800255fa  nop     dword ptr [rax+rax+00h]
0x1800255ff  mov     r8, rsi; lpMem
0x180025602  xor     edx, edx; dwFlags
0x180025604  mov     rcx, rax; hHeap
0x180025607  call    cs:__imp_HeapFree
0x18002560e  nop     dword ptr [rax+rax+00h]
0x180025613  mov     eax, edi
0x180025615  mov     rcx, [rbp+3C0h+var_40]
0x18002561c  xor     rcx, rsp; StackCookie
0x18002561f  call    __security_check_cookie
0x180025624  mov     rbx, [rsp+4C0h+arg_8]
0x18002562c  add     rsp, 490h
0x180025633  pop     r15
0x180025635  pop     r14
0x180025637  pop     r13
0x180025639  pop     r12
0x18002563b  pop     rdi
0x18002563c  pop     rsi
0x18002563d  pop     rbp
0x18002563e  retn
```
