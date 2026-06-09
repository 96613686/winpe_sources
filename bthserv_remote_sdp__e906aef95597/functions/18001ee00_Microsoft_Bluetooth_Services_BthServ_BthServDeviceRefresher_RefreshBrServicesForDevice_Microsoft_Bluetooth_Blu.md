# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(Microsoft::Bluetooth::BluetoothBRAddress const &)

- ea: `0x18001ee00`
- end: `0x18001f1c6`
- name: `?RefreshBrServicesForDevice@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@AEAAJAEBVBluetoothBRAddress@45@@Z`
- size: `966`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *__hidden this, const struct Microsoft::Bluetooth::BluetoothBRAddress *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ebf8`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x18000dfcc`
- `0x180010128`
- `0x180012004`
- `0x180012384`
- `0x18001ee00`
- `0x18001f268`
- `0x18001f394`
- `0x180025648`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ef3d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001ef3d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesForDevice(
        Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *this,
        const struct Microsoft::Bluetooth::BluetoothBRAddress *a2)
{
  const struct Microsoft::Bluetooth::BluetoothBRAddress *v2; // r14
  char v3; // bl
  const struct _BLUETOOTH_DEVICE_INFO *v4; // r8
  Microsoft::Bluetooth::Services::BthServ **v5; // rdi
  __int64 v6; // rdx
  __int64 v7; // r8
  const struct _BLUETOOTH_DEVICE_INFO *v8; // r8
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  signed int v12; // esi
  volatile signed __int32 *v13; // rbx
  bool v15; // dl
  _BYTE *v16; // rcx
  bool v17; // r10
  unsigned int v18; // edx
  volatile signed __int32 *v19; // rbx
  Microsoft::Bluetooth::Services::BthServ **v20; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v21; // [rsp+68h] [rbp-98h]
  __int64 InBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v24[69]; // [rsp+88h] [rbp-78h] BYREF

  v2 = a2;
  v3 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v23 = 560;
  memset_0(v24, 0, sizeof(v24));
  v24[0] = *((_QWORD *)v2 + 1);
  BthServGlobals::GetSafeRadioHandle(&Globals, &v20);
  v5 = v20;
  if ( v20 && (((unsigned __int64)*v20 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( (unsigned int)Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(*v20, &v23, v4) )
    {
      LOBYTE(v6) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, *((_QWORD *)WPP_GLOBAL_Control + 5));
      }
      Sleep(0x12Cu);
      v9 = Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(*v5, &v23, v8);
      v12 = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          v12 = (unsigned __int16)v9 | 0x80070000;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          v3 = 0;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v10) = v3;
          WPP_RECORDER_AND_TRACE_SF_sid(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v10,
            v11,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        }
LABEL_27:
        if ( v21 && _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
        {
          v13 = v21;
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64, __int64))v21)(v21, v10, v11);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
        return (unsigned int)v12;
      }
    }
    v15 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
    if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    InBuffer = *((_QWORD *)v2 + 1);
    v12 = BthServOverlappedIoctl(*v5, 0x411220u, &InBuffer, 8u, 0, 0, 0);
    if ( v12 )
    {
      v16 = WPP_GLOBAL_Control;
      v17 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      if ( !v17 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_51;
      if ( v12 > 0 )
        v18 = (unsigned __int16)v12 | 0x80070000;
      else
        v18 = v12;
      LOBYTE(v18) = v17;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sid(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v11, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    v16 = WPP_GLOBAL_Control;
LABEL_51:
    if ( v16 == (_BYTE *)&WPP_GLOBAL_Control || v16[25] < 5u )
      v3 = 0;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = v3;
      WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v16 + 2), v10, (_BYTE)v11, *((_QWORD *)v16 + 5));
    }
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_27;
  }
  if ( v21 )
  {
    if ( _InterlockedExchangeAdd(v21 + 2, 0xFFFFFFFF) == 1 )
    {
      v19 = v21;
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  return 6;
}

```

## disassembly

```asm
0x18001ee00  mov     [rsp-8+arg_0], rbx
0x18001ee05  mov     [rsp-8+arg_10], rsi
0x18001ee0a  push    rbp
0x18001ee0b  push    rdi
0x18001ee0c  push    r12
0x18001ee0e  push    r13
0x18001ee10  push    r14
0x18001ee12  lea     rbp, [rsp-1C0h]
0x18001ee1a  sub     rsp, 2C0h
0x18001ee21  mov     rax, cs:__security_cookie
0x18001ee28  xor     rax, rsp
0x18001ee2b  mov     [rbp+1E0h+var_30], rax
0x18001ee32  mov     r14, rdx
0x18001ee35  lea     r12, WPP_GLOBAL_Control
0x18001ee3c  mov     bl, 1
0x18001ee3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ee45  cmp     rcx, r12
0x18001ee48  jz      short loc_18001EE54
0x18001ee4a  cmp     byte ptr [rcx+19h], 5
0x18001ee4e  jb      short loc_18001EE54
0x18001ee50  mov     dl, bl
0x18001ee52  jmp     short loc_18001EE56
0x18001ee54  xor     dl, dl
0x18001ee56  lea     r13, WPP_RECORDER_INITIALIZED
0x18001ee5d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ee64  setnz   r8b
0x18001ee68  lea     rsi, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001ee6f  test    dl, dl
0x18001ee71  jnz     short loc_18001EE78
0x18001ee73  test    r8b, r8b
0x18001ee76  jz      short loc_18001EE9A
0x18001ee78  mov     rax, [r14+8]
0x18001ee7c  mov     [rsp+2E0h+var_298], rax
0x18001ee81  mov     [rsp+2E0h+var_2A8], rsi
0x18001ee86  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 0Dh
0x18001ee8d  mov     r9, [rcx+28h]
0x18001ee91  mov     rcx, [rcx+10h]
0x18001ee95  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001ee9a  mov     [rbp+1E0h+var_260], 230h
0x18001eea2  xor     edx, edx; Val
0x18001eea4  mov     r8d, 228h; Size
0x18001eeaa  lea     rcx, [rbp+1E0h+var_258]; void *
0x18001eeae  call    memset_0
0x18001eeb3  mov     rax, [r14+8]
0x18001eeb7  mov     [rbp+1E0h+var_258], rax
0x18001eebb  lea     rdx, [rsp+2E0h+var_280]
0x18001eec0  lea     rcx, ?Globals@@3VBthServGlobals@@A; BthServGlobals Globals
0x18001eec7  call    ?GetSafeRadioHandle@BthServGlobals@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ; BthServGlobals::GetSafeRadioHandle(void)
0x18001eecc  nop
0x18001eecd  mov     rdi, [rsp+2E0h+var_280]
0x18001eed2  test    rdi, rdi
0x18001eed5  jz      loc_18001F14E
0x18001eedb  mov     rcx, [rdi]; this
0x18001eede  lea     rax, [rcx+1]
0x18001eee2  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001eee8  jz      loc_18001F14E
0x18001eeee  lea     rdx, [rbp+1E0h+var_260]; void *
0x18001eef2  call    ?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z; Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)
0x18001eef7  test    eax, eax
0x18001eef9  jz      loc_18001F00B
0x18001eeff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef06  cmp     rcx, r12
0x18001ef09  jz      short loc_18001EF15
0x18001ef0b  cmp     byte ptr [rcx+19h], 3
0x18001ef0f  jb      short loc_18001EF15
0x18001ef11  mov     dl, bl
0x18001ef13  jmp     short loc_18001EF17
0x18001ef15  xor     dl, dl
0x18001ef17  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ef1e  setnz   r8b
0x18001ef22  test    dl, dl
0x18001ef24  jnz     short loc_18001EF2B
0x18001ef26  test    r8b, r8b
0x18001ef29  jz      short loc_18001EF38
0x18001ef2b  mov     r9, [rcx+28h]
0x18001ef2f  mov     rcx, [rcx+10h]
0x18001ef33  call    WPP_RECORDER_AND_TRACE_SF_sddd
0x18001ef38  mov     ecx, 12Ch; dwMilliseconds
0x18001ef3d  call    cs:__imp_Sleep
0x18001ef44  nop     dword ptr [rax+rax+00h]
0x18001ef49  lea     rdx, [rbp+1E0h+var_260]; void *
0x18001ef4d  mov     rcx, [rdi]; this
0x18001ef50  call    ?BthpEnableAllServices@BthServ@Services@Bluetooth@Microsoft@@YAKPEAXPEBU_BLUETOOTH_DEVICE_INFO@@E@Z; Microsoft::Bluetooth::Services::BthServ::BthpEnableAllServices(void *,_BLUETOOTH_DEVICE_INFO const *,uchar)
0x18001ef55  mov     esi, eax
0x18001ef57  test    eax, eax
0x18001ef59  jz      loc_18001F004
0x18001ef5f  jle     short loc_18001EF6A
0x18001ef61  movzx   esi, ax
0x18001ef64  or      esi, 80070000h
0x18001ef6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef71  cmp     rcx, r12
0x18001ef74  jz      short loc_18001EF7C
0x18001ef76  cmp     byte ptr [rcx+19h], 3
0x18001ef7a  jnb     short loc_18001EF7E
0x18001ef7c  xor     bl, bl
0x18001ef7e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ef85  setnz   r8b
0x18001ef89  test    bl, bl
0x18001ef8b  jnz     short loc_18001EF92
0x18001ef8d  test    r8b, r8b
0x18001ef90  jz      short loc_18001EFB6
0x18001ef92  mov     rax, [r14+8]
0x18001ef96  mov     [rsp+2E0h+var_290], esi
0x18001ef9a  mov     [rsp+2E0h+var_298], rax
0x18001ef9f  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 0Fh
0x18001efa6  mov     r9, [rcx+28h]
0x18001efaa  mov     dl, bl
0x18001efac  mov     rcx, [rcx+10h]
0x18001efb0  call    WPP_RECORDER_AND_TRACE_SF_sid
0x18001efb5  nop
0x18001efb6  mov     rcx, [rsp+2E0h+var_278]
0x18001efbb  test    rcx, rcx
0x18001efbe  jz      short loc_18001EFFD
0x18001efc0  or      edi, 0FFFFFFFFh
0x18001efc3  mov     eax, edi
0x18001efc5  lock xadd [rcx+8], eax
0x18001efca  add     eax, edi
0x18001efcc  jnz     short loc_18001EFFD
0x18001efce  mov     rbx, [rsp+2E0h+var_278]
0x18001efd3  mov     rax, [rbx]
0x18001efd6  mov     rcx, rbx
0x18001efd9  mov     rax, [rax]
0x18001efdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe1  mov     ecx, edi
0x18001efe3  lock xadd [rbx+0Ch], ecx
0x18001efe8  add     ecx, edi
0x18001efea  jnz     short loc_18001EFFD
0x18001efec  mov     rcx, [rsp+2E0h+var_278]
0x18001eff1  mov     rdx, [rcx]
0x18001eff4  mov     rax, [rdx+8]
0x18001eff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001effd  mov     eax, esi
0x18001efff  jmp     loc_18001F19A
0x18001f004  lea     rsi, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001f00b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f012  cmp     rcx, r12
0x18001f015  jz      short loc_18001F021
0x18001f017  cmp     byte ptr [rcx+19h], 5
0x18001f01b  jb      short loc_18001F021
0x18001f01d  mov     dl, bl
0x18001f01f  jmp     short loc_18001F023
0x18001f021  xor     dl, dl
0x18001f023  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001f02a  setnz   r8b
0x18001f02e  test    dl, dl
0x18001f030  jnz     short loc_18001F037
0x18001f032  test    r8b, r8b
0x18001f035  jz      short loc_18001F050
0x18001f037  mov     [rsp+2E0h+var_2A8], rsi
0x18001f03c  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 10h; lpNumberOfBytesTransferred
0x18001f043  mov     r9, [rcx+28h]
0x18001f047  mov     rcx, [rcx+10h]
0x18001f04b  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001f050  mov     rax, [r14+8]
0x18001f054  mov     [rsp+2E0h+InBuffer], rax
0x18001f059  and     [rsp+2E0h+lpNumberOfBytesTransferred], 0
0x18001f05f  and     [rsp+2E0h+var_2B8], 0
0x18001f064  and     [rsp+2E0h+var_2C0], 0
0x18001f06a  mov     r9d, 8; nInBufferSize
0x18001f070  lea     r8, [rsp+2E0h+InBuffer]; lpInBuffer
0x18001f075  mov     edx, 411220h; dwIoControlCode
0x18001f07a  mov     rcx, [rdi]; hFile
0x18001f07d  call    ?BthServOverlappedIoctl@@YAKPEAXK0K0KPEAK@Z; BthServOverlappedIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001f082  mov     esi, eax
0x18001f084  mov     edi, 80070000h
0x18001f089  test    eax, eax
0x18001f08b  jz      short loc_18001F0ED
0x18001f08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f094  cmp     rcx, r12
0x18001f097  jz      short loc_18001F0A4
0x18001f099  cmp     byte ptr [rcx+19h], 3
0x18001f09d  jb      short loc_18001F0A4
0x18001f09f  mov     r10b, bl
0x18001f0a2  jmp     short loc_18001F0A7
0x18001f0a4  xor     r10b, r10b
0x18001f0a7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001f0ae  setnz   r8b
0x18001f0b2  test    r10b, r10b
0x18001f0b5  jnz     short loc_18001F0BC
0x18001f0b7  test    r8b, r8b
0x18001f0ba  jz      short loc_18001F0F4
0x18001f0bc  test    esi, esi
0x18001f0be  jg      short loc_18001F0C4
0x18001f0c0  mov     edx, esi
0x18001f0c2  jmp     short loc_18001F0C9
0x18001f0c4  movzx   edx, si
0x18001f0c7  or      edx, edi
0x18001f0c9  mov     rax, [r14+8]
0x18001f0cd  mov     [rsp+2E0h+var_290], edx
0x18001f0d1  mov     [rsp+2E0h+var_298], rax
0x18001f0d6  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 11h
0x18001f0dd  mov     r9, [rcx+28h]
0x18001f0e1  mov     dl, r10b
0x18001f0e4  mov     rcx, [rcx+10h]
0x18001f0e8  call    WPP_RECORDER_AND_TRACE_SF_sid
0x18001f0ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0f4  cmp     rcx, r12
0x18001f0f7  jz      short loc_18001F0FF
0x18001f0f9  cmp     byte ptr [rcx+19h], 5
0x18001f0fd  jnb     short loc_18001F101
0x18001f0ff  xor     bl, bl
0x18001f101  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001f108  setnz   r8b
0x18001f10c  test    bl, bl
0x18001f10e  jnz     short loc_18001F115
0x18001f110  test    r8b, r8b
0x18001f113  jz      short loc_18001F13C
0x18001f115  mov     [rsp+2E0h+var_298], rsi
0x18001f11a  lea     rax, WPP_21eeecb372ac35bdc1c1ea9e0d2ef949_Traceguids
0x18001f121  mov     [rsp+2E0h+var_2A8], rax
0x18001f126  mov     word ptr [rsp+2E0h+lpNumberOfBytesTransferred], 12h
0x18001f12d  mov     r9, [rcx+28h]
0x18001f131  mov     dl, bl
0x18001f133  mov     rcx, [rcx+10h]
0x18001f137  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001f13c  test    esi, esi
0x18001f13e  jle     loc_18001EFB6
0x18001f144  movzx   esi, si
0x18001f147  or      esi, edi
0x18001f149  jmp     loc_18001EFB6
0x18001f14e  mov     rcx, [rsp+2E0h+var_278]
0x18001f153  test    rcx, rcx
0x18001f156  jz      short loc_18001F195
0x18001f158  or      edi, 0FFFFFFFFh
0x18001f15b  mov     eax, edi
0x18001f15d  lock xadd [rcx+8], eax
0x18001f162  add     eax, edi
0x18001f164  jnz     short loc_18001F195
0x18001f166  mov     rbx, [rsp+2E0h+var_278]
0x18001f16b  mov     rax, [rbx]
0x18001f16e  mov     rcx, rbx
0x18001f171  mov     rax, [rax]
0x18001f174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f179  mov     eax, edi
0x18001f17b  lock xadd [rbx+0Ch], eax
0x18001f180  add     eax, edi
0x18001f182  jnz     short loc_18001F195
0x18001f184  mov     rcx, [rsp+2E0h+var_278]
0x18001f189  mov     rax, [rcx]
0x18001f18c  mov     rax, [rax+8]
0x18001f190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f195  mov     eax, 6
0x18001f19a  mov     rcx, [rbp+1E0h+var_30]
0x18001f1a1  xor     rcx, rsp; StackCookie
0x18001f1a4  call    __security_check_cookie
0x18001f1a9  lea     r11, [rsp+2E0h+var_20]
0x18001f1b1  mov     rbx, [r11+30h]
0x18001f1b5  mov     rsi, [r11+40h]
0x18001f1b9  mov     rsp, r11
0x18001f1bc  pop     r14
0x18001f1be  pop     r13
0x18001f1c0  pop     r12
0x18001f1c2  pop     rdi
0x18001f1c3  pop     rbp
0x18001f1c4  retn
```
