# Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)

- ea: `0x1800247d0`
- end: `0x180024a14`
- name: `?BluetoothFindFirstServiceInternal@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002478c`
- `0x180025648`
- `0x180026808`
- `0x180026dec`

## callees

- `0x1800247d0`
- `0x180024a8c`
- `0x180024ebc`
- `0x180026650`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024997`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024831`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024997`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800249ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024917`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800249ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024849`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800248cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002493d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800249b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800248e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800249e7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024953`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024953`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180024870`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180024870`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800248a7`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800248a7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800248f7`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800248f7`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BluetoothFindFirstServiceInternal(
        __int64 a1,
        _DWORD *a2,
        unsigned int a3)
{
  DWORD v6; // edi
  __int64 FirstService; // r15
  DWORD v8; // ecx
  Microsoft::Bluetooth::Services::BthServ *v9; // rbp
  HANDLE ProcessHeap; // rax
  _QWORD *v11; // rsi
  __int64 DeviceInfoList; // rax
  void **v13; // r8
  __int64 v14; // rcx
  DWORD LastError; // ebx
  void *v16; // rdx
  HANDLE v17; // rax
  DWORD v18; // eax
  void **v19; // r8
  DWORD v20; // eax
  void *v21; // rdx
  HANDLE v22; // rax
  HANDLE hObject; // [rsp+60h] [rbp+8h] BYREF

  v6 = 0;
  FirstService = 0;
  if ( *(_DWORD *)a1 != 32 || *a2 != 1480 )
  {
    v8 = 1306;
    goto LABEL_27;
  }
  if ( !*(_QWORD *)(a1 + 8) )
  {
    v8 = 87;
LABEL_27:
    SetLastError(v8);
    return FirstService;
  }
  if ( *(_QWORD *)(a1 + 16) )
    return Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(a1, a1, a2, a3);
  hObject = 0;
  v9 = 0;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( v11 )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v11[1] = DeviceInfoList;
    if ( DeviceInfoList == -1 )
    {
      v22 = GetProcessHeap();
      HeapFree(v22, 0, v11);
    }
    else
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_BTHPORT_DEVICE_INTERFACE, 0, 18, 0, 0) )
      {
        v9 = (Microsoft::Bluetooth::Services::BthServ *)v11;
        if ( !(unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(
                              (Microsoft::Bluetooth::Services::BthServ *)v11,
                              &hObject,
                              v13) )
        {
          LastError = GetLastError();
          Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(
            (Microsoft::Bluetooth::Services::BthServ *)v11,
            v16);
          v9 = 0;
          SetLastError(LastError);
        }
      }
      else
      {
        DevObjDestroyDeviceInfoList(v11[1]);
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v11);
      }
      if ( v9 )
      {
        do
        {
          FirstService = Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(v14, a1, a2, a3);
          v18 = GetLastError();
          if ( v18 )
            v6 = v18;
          CloseHandle(hObject);
        }
        while ( !FirstService
             && (unsigned int)Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(v9, &hObject, v19) );
        v20 = GetLastError();
        if ( v20 )
          v6 = v20;
        Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(v9, v21);
        if ( FirstService )
        {
          v8 = 0;
          goto LABEL_27;
        }
      }
    }
  }
  if ( !GetLastError() && v6 )
  {
    v8 = v6;
    goto LABEL_27;
  }
  return FirstService;
}

```

## disassembly

```asm
0x1800247d0  mov     [rsp+arg_8], rbx
0x1800247d5  mov     [rsp+arg_10], rbp
0x1800247da  mov     [rsp+arg_18], rsi
0x1800247df  push    rdi
0x1800247e0  push    r12
0x1800247e2  push    r13
0x1800247e4  push    r14
0x1800247e6  push    r15
0x1800247e8  sub     rsp, 30h
0x1800247ec  xor     ebx, ebx
0x1800247ee  mov     r13d, r8d
0x1800247f1  cmp     dword ptr [rcx], 20h ; ' '
0x1800247f4  mov     r12, rdx
0x1800247f7  mov     r14, rcx
0x1800247fa  mov     edi, ebx
0x1800247fc  mov     r15d, ebx
0x1800247ff  jnz     loc_1800249E2
0x180024805  cmp     dword ptr [rdx], 5C8h
0x18002480b  jnz     loc_1800249E2
0x180024811  cmp     [rcx+8], rbx
0x180024815  jnz     short loc_18002481F
0x180024817  lea     ecx, [rbx+57h]
0x18002481a  jmp     loc_1800249E7
0x18002481f  cmp     [rcx+10h], rbx
0x180024823  jnz     loc_1800249CF
0x180024829  mov     [rsp+58h+hObject], rbx
0x18002482e  mov     rbp, rbx
0x180024831  call    cs:__imp_GetProcessHeap
0x180024838  nop     dword ptr [rax+rax+00h]
0x18002483d  mov     edx, 8; dwFlags
0x180024842  mov     rcx, rax; hHeap
0x180024845  lea     r8d, [rdx+8]; dwBytes
0x180024849  call    cs:__imp_HeapAlloc
0x180024850  nop     dword ptr [rax+rax+00h]
0x180024855  mov     rsi, rax
0x180024858  test    rax, rax
0x18002485b  jz      loc_1800249B7
0x180024861  xor     r9d, r9d
0x180024864  mov     [rsp+58h+var_38], rbx
0x180024869  xor     r8d, r8d
0x18002486c  xor     edx, edx
0x18002486e  xor     ecx, ecx
0x180024870  call    cs:__imp_DevObjCreateDeviceInfoList
0x180024877  nop     dword ptr [rax+rax+00h]
0x18002487c  mov     [rsi+8], rax
0x180024880  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024884  jz      loc_180024997
0x18002488a  mov     [rsp+58h+var_30], rbx
0x18002488f  lea     rdx, GUID_BTHPORT_DEVICE_INTERFACE
0x180024896  mov     r9d, 12h
0x18002489c  mov     [rsp+58h+var_38], rbx
0x1800248a1  xor     r8d, r8d
0x1800248a4  mov     rcx, rax
0x1800248a7  call    cs:__imp_DevObjGetClassDevs
0x1800248ae  nop     dword ptr [rax+rax+00h]
0x1800248b3  test    eax, eax
0x1800248b5  jz      short loc_1800248F3
0x1800248b7  lea     rdx, [rsp+58h+hObject]; void *
0x1800248bc  mov     rcx, rsi; this
0x1800248bf  mov     rbp, rsi
0x1800248c2  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x1800248c7  test    eax, eax
0x1800248c9  jnz     short loc_180024923
0x1800248cb  call    cs:__imp_GetLastError
0x1800248d2  nop     dword ptr [rax+rax+00h]
0x1800248d7  mov     rcx, rsi; this
0x1800248da  mov     ebx, eax
0x1800248dc  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x1800248e1  mov     ecx, ebx; dwErrCode
0x1800248e3  xor     ebp, ebp
0x1800248e5  call    cs:__imp_SetLastError
0x1800248ec  nop     dword ptr [rax+rax+00h]
0x1800248f1  jmp     short loc_180024923
0x1800248f3  mov     rcx, [rsi+8]
0x1800248f7  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800248fe  nop     dword ptr [rax+rax+00h]
0x180024903  call    cs:__imp_GetProcessHeap
0x18002490a  nop     dword ptr [rax+rax+00h]
0x18002490f  mov     r8, rsi; lpMem
0x180024912  xor     edx, edx; dwFlags
0x180024914  mov     rcx, rax; hHeap
0x180024917  call    cs:__imp_HeapFree
0x18002491e  nop     dword ptr [rax+rax+00h]
0x180024923  test    rbp, rbp
0x180024926  jz      loc_1800249B7
0x18002492c  mov     r9d, r13d
0x18002492f  mov     r8, r12
0x180024932  mov     rdx, r14
0x180024935  call    ?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x18002493a  mov     r15, rax
0x18002493d  call    cs:__imp_GetLastError
0x180024944  nop     dword ptr [rax+rax+00h]
0x180024949  mov     rcx, [rsp+58h+hObject]; hObject
0x18002494e  test    eax, eax
0x180024950  cmovnz  edi, eax
0x180024953  call    cs:__imp_CloseHandle
0x18002495a  nop     dword ptr [rax+rax+00h]
0x18002495f  test    r15, r15
0x180024962  jnz     short loc_180024975
0x180024964  lea     rdx, [rsp+58h+hObject]; void *
0x180024969  mov     rcx, rbp; this
0x18002496c  call    ?BluetoothFindNextRadio@BthServ@Services@Bluetooth@Microsoft@@YAHPEAXPEAPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindNextRadio(void *,void * *)
0x180024971  test    eax, eax
0x180024973  jnz     short loc_18002492C
0x180024975  call    cs:__imp_GetLastError
0x18002497c  nop     dword ptr [rax+rax+00h]
0x180024981  test    eax, eax
0x180024983  mov     rcx, rbp; this
0x180024986  cmovnz  edi, eax
0x180024989  call    ?BluetoothFindRadioClose@BthServ@Services@Bluetooth@Microsoft@@YAHPEAX@Z; Microsoft::Bluetooth::Services::BthServ::BluetoothFindRadioClose(void *)
0x18002498e  test    r15, r15
0x180024991  jz      short loc_1800249B7
0x180024993  xor     ecx, ecx
0x180024995  jmp     short loc_1800249E7
0x180024997  call    cs:__imp_GetProcessHeap
0x18002499e  nop     dword ptr [rax+rax+00h]
0x1800249a3  mov     r8, rsi; lpMem
0x1800249a6  xor     edx, edx; dwFlags
0x1800249a8  mov     rcx, rax; hHeap
0x1800249ab  call    cs:__imp_HeapFree
0x1800249b2  nop     dword ptr [rax+rax+00h]
0x1800249b7  call    cs:__imp_GetLastError
0x1800249be  nop     dword ptr [rax+rax+00h]
0x1800249c3  test    eax, eax
0x1800249c5  jnz     short loc_1800249F3
0x1800249c7  test    edi, edi
0x1800249c9  jz      short loc_1800249F3
0x1800249cb  mov     ecx, edi
0x1800249cd  jmp     short loc_1800249E7
0x1800249cf  mov     r9d, r13d
0x1800249d2  mov     r8, r12
0x1800249d5  mov     rdx, r14
0x1800249d8  call    ?BthpFindFirstService@BthServ@Services@Bluetooth@Microsoft@@YAPEAXPEAXPEBU_BLUETOOTH_SDP_SEARCH_PARAMS@@PEAU_BLUETOOTH_SERVICE_RECORD@@W4_BTHSERV_QUERY_TYPE@@@Z; Microsoft::Bluetooth::Services::BthServ::BthpFindFirstService(void *,_BLUETOOTH_SDP_SEARCH_PARAMS const *,_BLUETOOTH_SERVICE_RECORD *,_BTHSERV_QUERY_TYPE)
0x1800249dd  mov     r15, rax
0x1800249e0  jmp     short loc_1800249F3
0x1800249e2  mov     ecx, 51Ah; dwErrCode
0x1800249e7  call    cs:__imp_SetLastError
0x1800249ee  nop     dword ptr [rax+rax+00h]
0x1800249f3  mov     rbx, [rsp+58h+arg_8]
0x1800249f8  mov     rax, r15
0x1800249fb  mov     rbp, [rsp+58h+arg_10]
0x180024a00  mov     rsi, [rsp+58h+arg_18]
0x180024a05  add     rsp, 30h
0x180024a09  pop     r15
0x180024a0b  pop     r14
0x180024a0d  pop     r13
0x180024a0f  pop     r12
0x180024a11  pop     rdi
0x180024a12  retn
```
