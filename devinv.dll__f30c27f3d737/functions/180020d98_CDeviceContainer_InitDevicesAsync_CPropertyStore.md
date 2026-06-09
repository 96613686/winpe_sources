# CDeviceContainer::InitDevicesAsync(CPropertyStore *)

- ea: `0x180020d98`
- end: `0x18002105e`
- name: `?InitDevicesAsync@CDeviceContainer@@AEAAJPEAVCPropertyStore@@@Z`
- size: `710`
- prototype: `__int64 __fastcall(CDeviceContainer *__hidden this, struct CPropertyStore *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021670`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x180020d98`
- `0x180034788`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020ede`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020ede`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021001`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180021001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ef7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002102b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002102b`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020e21`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180020e21`

## string_xrefs

- `0x180020f0c`: `Failed to create device event. 0x%08x`

## pseudocode

```c
__int64 __fastcall CDeviceContainer::InitDevicesAsync(CDeviceContainer *this, struct CPropertyStore *a2)
{
  __int64 v3; // rcx
  HRESULT v4; // eax
  signed int v5; // ebx
  FILE *v6; // rax
  FILE *v7; // rax
  FILE *v8; // rax
  HANDLE *v9; // rdi
  HANDLE EventW; // rax
  __int64 v11; // r8
  signed int LastError; // eax
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  void (__fastcall *v16)(__int64); // rax
  __int64 v18; // [rsp+50h] [rbp-19h] BYREF
  __int64 v19; // [rsp+58h] [rbp-11h] BYREF
  DEVPROPKEY v20; // [rsp+60h] [rbp-9h]
  int v21; // [rsp+74h] [rbp+Bh]
  __int64 v22; // [rsp+78h] [rbp+Fh]
  int v23; // [rsp+80h] [rbp+17h]
  int v24; // [rsp+84h] [rbp+1Bh]
  GUID *p_iid; // [rsp+88h] [rbp+1Fh]
  GUID iid; // [rsp+90h] [rbp+27h] BYREF

  iid = 0;
  v3 = *((_QWORD *)a2 + 2);
  v20 = DEVPKEY_Device_ContainerId;
  v21 = 0;
  v22 = 0;
  v19 = 2;
  v23 = 13;
  v24 = 16;
  p_iid = &iid;
  v18 = 0;
  v4 = IIDFromString(*(LPCOLESTR *)(v3 + 8), &iid);
  v5 = v4;
  if ( v4 >= 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    v9 = (HANDLE *)((char *)this + 720);
    *((_QWORD *)this + 90) = EventW;
    if ( EventW )
    {
      v5 = CDeviceMap::DevCreateObjectQuery(
             *((_QWORD *)this + 89),
             3,
             v11,
             32,
             &CDevice::s_PropertyKeys,
             1,
             &v19,
             CDeviceContainer::EnumerateDevicesCallback,
             this,
             &v18);
      if ( v5 >= 0 )
      {
        WaitForSingleObject(*v9, 0xFFFFFFFF);
        v16 = *(void (__fastcall **)(__int64))(*((_QWORD *)this + 89) + 688LL);
        if ( v16 )
          v16(v18);
      }
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      AslLogCallPrintf(2, "CDeviceContainer::InitDevicesAsync", 1415, "Failed to create device event. 0x%08x", v5);
      if ( EnableDevInvStdErrLog )
      {
        v13 = o___acrt_iob_func_0(2u);
        fprintf(v13, "Error: %s, %u: ", "CDeviceContainer::InitDevicesAsync", 1415);
        v14 = o___acrt_iob_func_0(2u);
        fprintf(v14, "Failed to create device event. 0x%08x", v5);
        v15 = o___acrt_iob_func_0(2u);
        fprintf(v15, "\n");
      }
      if ( g_DeviceMapLogFunction )
        TraceMessageCallback(0x2000000, "Failed to create device event. 0x%08x", v5);
    }
  }
  else
  {
    AslLogCallPrintf(
      2,
      "CDeviceContainer::InitDevicesAsync",
      1405,
      "Failed to convert container guid string to guid 0x%08x",
      v4);
    if ( EnableDevInvStdErrLog )
    {
      v6 = o___acrt_iob_func_0(2u);
      fprintf(v6, "Error: %s, %u: ", "CDeviceContainer::InitDevicesAsync", 1405);
      v7 = o___acrt_iob_func_0(2u);
      fprintf(v7, "Failed to convert container guid string to guid 0x%08x", v5);
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Failed to convert container guid string to guid 0x%08x", v5);
    v9 = (HANDLE *)((char *)this + 720);
  }
  if ( *v9 )
  {
    CloseHandle(*v9);
    *v9 = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020d98  mov     [rsp-8+arg_10], rbx
0x180020d9d  mov     [rsp-8+arg_18], rsi
0x180020da2  push    rbp
0x180020da3  push    rdi
0x180020da4  push    r15
0x180020da6  lea     rbp, [rsp-47h]
0x180020dab  sub     rsp, 0B0h
0x180020db2  mov     rax, cs:__security_cookie
0x180020db9  xor     rax, rsp
0x180020dbc  mov     [rbp+57h+var_20], rax
0x180020dc0  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x180020dc6  xorps   xmm0, xmm0
0x180020dc9  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x180020dcd  mov     rsi, rcx
0x180020dd0  mov     rcx, [rdx+10h]
0x180020dd4  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x180020ddb  mov     [rbp+57h+var_50], eax
0x180020dde  lea     rdx, [rbp+57h+iid]; lpiid
0x180020de2  lea     rax, [rbp+57h+iid]
0x180020de6  mov     [rbp+57h+var_4C], 0
0x180020ded  movups  [rbp+57h+var_60], xmm0
0x180020df1  mov     [rbp+57h+var_48], 0
0x180020df9  mov     r15d, 2
0x180020dff  mov     [rbp+57h+var_68], r15
0x180020e03  mov     [rbp+57h+var_40], 0Dh
0x180020e0a  mov     [rbp+57h+var_3C], 10h
0x180020e11  mov     [rbp+57h+var_38], rax
0x180020e15  mov     [rbp+57h+var_70], 0
0x180020e1d  mov     rcx, [rcx+8]; lpsz
0x180020e21  call    cs:__imp_IIDFromString
0x180020e27  mov     ebx, eax
0x180020e29  test    eax, eax
0x180020e2b  jns     loc_180020ED4
0x180020e31  lea     rdi, aFailedToConver_0; "Failed to convert container guid string"...
0x180020e38  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180020e3c  mov     r9, rdi
0x180020e3f  lea     rdx, aCdevicecontain_7; "CDeviceContainer::InitDevicesAsync"
0x180020e46  mov     r8d, 57Dh
0x180020e4c  mov     ecx, r15d
0x180020e4f  call    AslLogCallPrintf
0x180020e54  cmp     cs:EnableDevInvStdErrLog, 0
0x180020e5b  jz      short loc_180020EAE
0x180020e5d  mov     ecx, r15d; Ix
0x180020e60  call    _o___acrt_iob_func_0
0x180020e65  mov     rcx, rax; Stream
0x180020e68  lea     r8, aCdevicecontain_7; "CDeviceContainer::InitDevicesAsync"
0x180020e6f  mov     r9d, 57Dh
0x180020e75  lea     rdx, Format; "Error: %s, %u: "
0x180020e7c  call    fprintf
0x180020e81  mov     ecx, r15d; Ix
0x180020e84  call    _o___acrt_iob_func_0
0x180020e89  mov     rcx, rax; Stream
0x180020e8c  mov     r8d, ebx
0x180020e8f  mov     rdx, rdi; Format
0x180020e92  call    fprintf
0x180020e97  mov     ecx, r15d; Ix
0x180020e9a  call    _o___acrt_iob_func_0
0x180020e9f  mov     rcx, rax; Stream
0x180020ea2  lea     rdx, asc_18011EAD8; "\n"
0x180020ea9  call    fprintf
0x180020eae  cmp     cs:g_DeviceMapLogFunction, 0
0x180020eb6  jz      short loc_180020EC8
0x180020eb8  mov     r8d, ebx
0x180020ebb  mov     rdx, rdi
0x180020ebe  mov     ecx, 2000000h
0x180020ec3  call    TraceMessageCallback
0x180020ec8  lea     rdi, [rsi+2D0h]
0x180020ecf  jmp     loc_180021023
0x180020ed4  xor     r9d, r9d; lpName
0x180020ed7  xor     r8d, r8d; bInitialState
0x180020eda  xor     edx, edx; bManualReset
0x180020edc  xor     ecx, ecx; lpEventAttributes
0x180020ede  call    cs:__imp_CreateEventW
0x180020ee4  lea     rdi, [rsi+2D0h]
0x180020eeb  mov     [rdi], rax
0x180020eee  test    rax, rax
0x180020ef1  jnz     loc_180020FA9
0x180020ef7  call    cs:__imp_GetLastError
0x180020efd  mov     ebx, eax
0x180020eff  test    eax, eax
0x180020f01  jle     short loc_180020F0C
0x180020f03  movzx   ebx, ax
0x180020f06  or      ebx, 80070000h
0x180020f0c  lea     rsi, aFailedToCreate; "Failed to create device event. 0x%08x"
0x180020f13  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x180020f17  mov     r9, rsi
0x180020f1a  lea     rdx, aCdevicecontain_7; "CDeviceContainer::InitDevicesAsync"
0x180020f21  mov     r8d, 587h
0x180020f27  mov     ecx, r15d
0x180020f2a  call    AslLogCallPrintf
0x180020f2f  cmp     cs:EnableDevInvStdErrLog, 0
0x180020f36  jz      short loc_180020F89
0x180020f38  mov     ecx, r15d; Ix
0x180020f3b  call    _o___acrt_iob_func_0
0x180020f40  mov     rcx, rax; Stream
0x180020f43  lea     r8, aCdevicecontain_7; "CDeviceContainer::InitDevicesAsync"
0x180020f4a  mov     r9d, 587h
0x180020f50  lea     rdx, Format; "Error: %s, %u: "
0x180020f57  call    fprintf
0x180020f5c  mov     ecx, r15d; Ix
0x180020f5f  call    _o___acrt_iob_func_0
0x180020f64  mov     rcx, rax; Stream
0x180020f67  mov     r8d, ebx
0x180020f6a  mov     rdx, rsi; Format
0x180020f6d  call    fprintf
0x180020f72  mov     ecx, r15d; Ix
0x180020f75  call    _o___acrt_iob_func_0
0x180020f7a  mov     rcx, rax; Stream
0x180020f7d  lea     rdx, asc_18011EAD8; "\n"
0x180020f84  call    fprintf
0x180020f89  cmp     cs:g_DeviceMapLogFunction, 0
0x180020f91  jz      loc_180021023
0x180020f97  mov     r8d, ebx
0x180020f9a  mov     rdx, rsi
0x180020f9d  mov     ecx, 2000000h
0x180020fa2  call    TraceMessageCallback
0x180020fa7  jmp     short loc_180021023
0x180020fa9  mov     rcx, [rsi+2C8h]
0x180020fb0  lea     rax, [rbp+57h+var_70]
0x180020fb4  mov     [rsp+0C0h+var_78], rax
0x180020fb9  mov     edx, 3
0x180020fbe  mov     [rsp+0C0h+var_80], rsi
0x180020fc3  lea     rax, ?EnumerateDevicesCallback@CDeviceContainer@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceContainer::EnumerateDevicesCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180020fca  mov     [rsp+0C0h+var_88], rax
0x180020fcf  lea     rax, [rbp+57h+var_68]
0x180020fd3  mov     [rsp+0C0h+var_90], rax
0x180020fd8  lea     rax, ?s_PropertyKeys@CDevice@@0QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const CDevice::s_PropertyKeys
0x180020fdf  mov     [rsp+0C0h+var_98], 1
0x180020fe7  lea     r9d, [rdx+1Dh]
0x180020feb  mov     [rsp+0C0h+var_A0], rax
0x180020ff0  call    ?DevCreateObjectQuery@CDeviceMap@@QEAAJW4_DEV_OBJECT_TYPE@@KKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@P6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z4PEAPEAU5@@Z; CDeviceMap::DevCreateObjectQuery(_DEV_OBJECT_TYPE,ulong,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,HDEVQUERY__ * *)
0x180020ff5  mov     ebx, eax
0x180020ff7  test    eax, eax
0x180020ff9  js      short loc_180021023
0x180020ffb  mov     rcx, [rdi]; hHandle
0x180020ffe  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180021001  call    cs:__imp_WaitForSingleObject
0x180021007  mov     rax, [rsi+2C8h]
0x18002100e  mov     rax, [rax+2B0h]
0x180021015  test    rax, rax
0x180021018  jz      short loc_180021023
0x18002101a  mov     rcx, [rbp+57h+var_70]
0x18002101e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021023  mov     rcx, [rdi]; hObject
0x180021026  test    rcx, rcx
0x180021029  jz      short loc_180021038
0x18002102b  call    cs:__imp_CloseHandle
0x180021031  mov     qword ptr [rdi], 0
0x180021038  mov     eax, ebx
0x18002103a  mov     rcx, [rbp+57h+var_20]
0x18002103e  xor     rcx, rsp; StackCookie
0x180021041  call    __security_check_cookie
0x180021046  lea     r11, [rsp+0C0h+var_10]
0x18002104e  mov     rbx, [r11+30h]
0x180021052  mov     rsi, [r11+38h]
0x180021056  mov     rsp, r11
0x180021059  pop     r15
0x18002105b  pop     rdi
0x18002105c  pop     rbp
0x18002105d  retn
```
