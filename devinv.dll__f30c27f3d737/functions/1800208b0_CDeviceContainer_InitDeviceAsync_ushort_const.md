# CDeviceContainer::InitDeviceAsync(ushort const *)

- ea: `0x1800208b0`
- end: `0x180020abf`
- name: `?InitDeviceAsync@CDeviceContainer@@QEAAJPEBG@Z`
- size: `527`
- prototype: `__int64 __fastcall(CDeviceContainer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180031e30`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x1800208b0`
- `0x180034788`
- `0x18006041c`
- `0x180066c10`
- `0x180116010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020932`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180020932`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020a5e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180020a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020948`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a8c`

## string_xrefs

- `0x18002095d`: `Failed to create device event. 0x%08x`
- `0x1800209b4`: `Failed to create device event. 0x%08x`
- `0x1800209ea`: `Failed to create device event. 0x%08x`

## pseudocode

```c
__int64 __fastcall CDeviceContainer::InitDeviceAsync(CDeviceContainer *this, const unsigned __int16 *a2)
{
  __int64 v3; // rax
  HANDLE EventW; // rax
  __int64 v5; // r8
  signed int LastError; // eax
  signed int v7; // ebx
  FILE *v8; // rax
  FILE *v9; // rax
  FILE *v10; // rax
  void (__fastcall *v11)(__int64); // rax
  void *v12; // rcx
  __int64 v14; // [rsp+50h] [rbp-9h] BYREF
  __int64 v15; // [rsp+58h] [rbp-1h] BYREF
  DEVPROPKEY v16; // [rsp+60h] [rbp+7h]
  int v17; // [rsp+74h] [rbp+1Bh]
  __int64 v18; // [rsp+78h] [rbp+1Fh]
  int v19; // [rsp+80h] [rbp+27h]
  int v20; // [rsp+84h] [rbp+2Bh]
  const unsigned __int16 *v21; // [rsp+88h] [rbp+2Fh]

  v16 = DEVPKEY_Device_InstanceId;
  v15 = 2;
  v17 = 0;
  v3 = -1;
  v18 = 0;
  v19 = 18;
  do
    ++v3;
  while ( a2[v3] );
  v21 = a2;
  v20 = 2 * v3 + 2;
  v14 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 90) = EventW;
  if ( EventW )
  {
    v7 = CDeviceMap::DevCreateObjectQuery(
           *((_QWORD *)this + 89),
           3,
           v5,
           32,
           &CDevice::s_PropertyKeys,
           1,
           &v15,
           CDeviceContainer::EnumerateDevicesCallback,
           this,
           &v14);
    if ( v7 >= 0 )
    {
      WaitForSingleObject(*((HANDLE *)this + 90), 0xEA60u);
      v11 = *(void (__fastcall **)(__int64))(*((_QWORD *)this + 89) + 688LL);
      if ( v11 )
        v11(v14);
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    AslLogCallPrintf(2, "CDeviceContainer::InitDeviceAsync", 1327, "Failed to create device event. 0x%08x", v7);
    if ( EnableDevInvStdErrLog )
    {
      v8 = o___acrt_iob_func_0(2u);
      fprintf(v8, "Error: %s, %u: ", "CDeviceContainer::InitDeviceAsync", 1327);
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "Failed to create device event. 0x%08x", v7);
      v10 = o___acrt_iob_func_0(2u);
      fprintf(v10, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, "Failed to create device event. 0x%08x", v7);
  }
  v12 = (void *)*((_QWORD *)this + 90);
  if ( v12 )
  {
    CloseHandle(v12);
    *((_QWORD *)this + 90) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800208b0  mov     [rsp-8+arg_10], rbx
0x1800208b5  mov     [rsp-8+arg_18], rsi
0x1800208ba  push    rbp
0x1800208bb  push    rdi
0x1800208bc  push    r15
0x1800208be  lea     rbp, [rsp-47h]
0x1800208c3  sub     rsp, 0A0h
0x1800208ca  mov     rax, cs:__security_cookie
0x1800208d1  xor     rax, rsp
0x1800208d4  mov     [rbp+57h+var_20], rax
0x1800208d8  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x1800208de  xor     esi, esi
0x1800208e0  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x1800208e7  mov     r15d, 2
0x1800208ed  mov     [rbp+57h+var_40], eax
0x1800208f0  mov     rdi, rcx
0x1800208f3  mov     [rbp+57h+var_58], r15
0x1800208f7  movups  [rbp+57h+var_50], xmm0
0x1800208fb  mov     [rbp+57h+var_3C], esi
0x1800208fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020902  mov     [rbp+57h+var_38], rsi
0x180020906  mov     [rbp+57h+var_30], 12h
0x18002090d  inc     rax
0x180020910  cmp     [rdx+rax*2], si
0x180020914  jnz     short loc_18002090D
0x180020916  lea     eax, ds:2[rax*2]
0x18002091d  mov     [rbp+57h+var_28], rdx
0x180020921  xor     edx, edx; bManualReset
0x180020923  mov     [rbp+57h+var_2C], eax
0x180020926  xor     r9d, r9d; lpName
0x180020929  mov     [rbp+57h+var_60], rsi
0x18002092d  xor     r8d, r8d; bInitialState
0x180020930  xor     ecx, ecx; lpEventAttributes
0x180020932  call    cs:__imp_CreateEventW
0x180020938  mov     [rdi+2D0h], rax
0x18002093f  test    rax, rax
0x180020942  jnz     loc_180020A00
0x180020948  call    cs:__imp_GetLastError
0x18002094e  mov     ebx, eax
0x180020950  test    eax, eax
0x180020952  jle     short loc_18002095D
0x180020954  movzx   ebx, ax
0x180020957  or      ebx, 80070000h
0x18002095d  lea     r9, aFailedToCreate; "Failed to create device event. 0x%08x"
0x180020964  mov     dword ptr [rsp+0B0h+var_90], ebx
0x180020968  mov     r8d, 52Fh
0x18002096e  lea     rdx, aCdevicecontain_3; "CDeviceContainer::InitDeviceAsync"
0x180020975  mov     ecx, r15d
0x180020978  call    AslLogCallPrintf
0x18002097d  cmp     cs:EnableDevInvStdErrLog, esi
0x180020983  jz      short loc_1800209DA
0x180020985  mov     ecx, r15d; Ix
0x180020988  call    _o___acrt_iob_func_0
0x18002098d  mov     rcx, rax; Stream
0x180020990  lea     r8, aCdevicecontain_3; "CDeviceContainer::InitDeviceAsync"
0x180020997  mov     r9d, 52Fh
0x18002099d  lea     rdx, Format; "Error: %s, %u: "
0x1800209a4  call    fprintf
0x1800209a9  mov     ecx, r15d; Ix
0x1800209ac  call    _o___acrt_iob_func_0
0x1800209b1  mov     rcx, rax; Stream
0x1800209b4  lea     rdx, aFailedToCreate; "Failed to create device event. 0x%08x"
0x1800209bb  mov     r8d, ebx
0x1800209be  call    fprintf
0x1800209c3  mov     ecx, r15d; Ix
0x1800209c6  call    _o___acrt_iob_func_0
0x1800209cb  mov     rcx, rax; Stream
0x1800209ce  lea     rdx, asc_18011EAD8; "\n"
0x1800209d5  call    fprintf
0x1800209da  cmp     cs:g_DeviceMapLogFunction, rsi
0x1800209e1  jz      loc_180020A80
0x1800209e7  mov     r8d, ebx
0x1800209ea  lea     rdx, aFailedToCreate; "Failed to create device event. 0x%08x"
0x1800209f1  mov     ecx, 2000000h
0x1800209f6  call    TraceMessageCallback
0x1800209fb  jmp     loc_180020A80
0x180020a00  mov     rcx, [rdi+2C8h]
0x180020a07  lea     rax, [rbp+57h+var_60]
0x180020a0b  mov     [rsp+0B0h+var_68], rax
0x180020a10  mov     edx, 3
0x180020a15  mov     [rsp+0B0h+var_70], rdi
0x180020a1a  lea     rax, ?EnumerateDevicesCallback@CDeviceContainer@@CAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; CDeviceContainer::EnumerateDevicesCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x180020a21  mov     [rsp+0B0h+var_78], rax
0x180020a26  lea     rax, [rbp+57h+var_58]
0x180020a2a  mov     [rsp+0B0h+var_80], rax
0x180020a2f  lea     rax, ?s_PropertyKeys@CDevice@@0QBU_DEVPROPCOMPKEY@@B; _DEVPROPCOMPKEY const near * const CDevice::s_PropertyKeys
0x180020a36  mov     [rsp+0B0h+var_88], 1
0x180020a3e  lea     r9d, [rdx+1Dh]
0x180020a42  mov     [rsp+0B0h+var_90], rax
0x180020a47  call    ?DevCreateObjectQuery@CDeviceMap@@QEAAJW4_DEV_OBJECT_TYPE@@KKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@P6AXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z4PEAPEAU5@@Z; CDeviceMap::DevCreateObjectQuery(_DEV_OBJECT_TYPE,ulong,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,void (*)(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *),void *,HDEVQUERY__ * *)
0x180020a4c  mov     ebx, eax
0x180020a4e  test    eax, eax
0x180020a50  js      short loc_180020A80
0x180020a52  mov     rcx, [rdi+2D0h]; hHandle
0x180020a59  mov     edx, 0EA60h; dwMilliseconds
0x180020a5e  call    cs:__imp_WaitForSingleObject
0x180020a64  mov     rcx, [rdi+2C8h]
0x180020a6b  mov     rax, [rcx+2B0h]
0x180020a72  test    rax, rax
0x180020a75  jz      short loc_180020A80
0x180020a77  mov     rcx, [rbp+57h+var_60]
0x180020a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a80  mov     rcx, [rdi+2D0h]; hObject
0x180020a87  test    rcx, rcx
0x180020a8a  jz      short loc_180020A99
0x180020a8c  call    cs:__imp_CloseHandle
0x180020a92  mov     [rdi+2D0h], rsi
0x180020a99  mov     eax, ebx
0x180020a9b  mov     rcx, [rbp+57h+var_20]
0x180020a9f  xor     rcx, rsp; StackCookie
0x180020aa2  call    __security_check_cookie
0x180020aa7  lea     r11, [rsp+0B0h+var_10]
0x180020aaf  mov     rbx, [r11+30h]
0x180020ab3  mov     rsi, [r11+38h]
0x180020ab7  mov     rsp, r11
0x180020aba  pop     r15
0x180020abc  pop     rdi
0x180020abd  pop     rbp
0x180020abe  retn
```
