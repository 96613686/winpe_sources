# CTiBus::CreateSwDevice(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,_DEVPROPERTY *,ulong,int,HSWDEVICE__ * *,ushort *,ulong)

- ea: `0x18001b068`
- end: `0x18001b3a7`
- name: `?CreateSwDevice@CTiBus@@AEAAJPEBG0000PEAU_DEVPROPERTY@@KHPEAPEAUHSWDEVICE__@@PEAGK@Z`
- size: `831`
- prototype: `__int64 __fastcall(CTiBus *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _DEVPROPERTY *, unsigned int, int, struct HSWDEVICE__ **, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800abc78`

## callees

- `0x1800091a8`
- `0x18001b068`
- `0x18002e600`
- `0x180034970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b0d8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001b0d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b233`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b248`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b248`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b387`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b387`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18001b378`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceClose` at `0x18001b378`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18001b31b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x18001b31b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18001b1dd`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceCreate` at `0x18001b1dd`

## string_xrefs

- `0x18001b135`: `CreateEvent failed`
- `0x18001b21e`: `SwDeviceCreate failed`
- `0x18001b2e0`: `CreateSwDeviceCallback failed`

## pseudocode

```c
__int64 __fastcall CTiBus::CreateSwDevice(
        CTiBus *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct _DEVPROPERTY *a7,
        unsigned int a8,
        int a9,
        struct HSWDEVICE__ **a10,
        unsigned __int16 *a11)
{
  signed int LastError; // eax
  signed int v15; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // edx
  const char *v18; // rcx
  int v19; // eax
  int v20; // edi
  DWORD v21; // eax
  signed int v22; // eax
  struct HSWDEVICE__ *v23; // rax
  __int64 v25; // [rsp+30h] [rbp-81h]
  unsigned __int16 *v26; // [rsp+48h] [rbp-69h] BYREF
  int v27; // [rsp+50h] [rbp-61h]
  int hHandle; // [rsp+54h] [rbp-5Dh]
  HANDLE hHandle_4; // [rsp+58h] [rbp-59h]
  int v30; // [rsp+60h] [rbp-51h]
  int v31; // [rsp+64h] [rbp-4Dh]
  int v32; // [rsp+68h] [rbp-49h] BYREF
  const unsigned __int16 *v33; // [rsp+70h] [rbp-41h]
  const unsigned __int16 *v34; // [rsp+78h] [rbp-39h]
  const unsigned __int16 *v35; // [rsp+80h] [rbp-31h]
  int v36; // [rsp+90h] [rbp-21h]
  __int64 v37; // [rsp+98h] [rbp-19h]
  struct HSWDEVICE__ *v38; // [rsp+D8h] [rbp+27h] BYREF

  v38 = 0;
  hHandle = 0;
  v30 = 0;
  v31 = 0;
  memset_0(&v32, 0, 0x48u);
  v26 = a11;
  v27 = 260;
  hHandle_4 = CreateEventW(0, 1, 0, 0);
  if ( !hHandle_4 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( v15 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 39;
        v18 = "CreateEvent failed";
LABEL_9:
        LODWORD(v25) = v15;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v17,
          (unsigned int)&WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v18,
          v25);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
  }
  v35 = a5;
  v19 = 2;
  v34 = a4;
  v20 = a9;
  v32 = 72;
  v33 = a2;
  if ( !a9 )
    v19 = 10;
  v37 = 0;
  v36 = v19;
  if ( !a3 )
    a3 = L"HTREE\\ROOT\\0";
  v15 = ((__int64 (__fastcall *)(const wchar_t *, const unsigned __int16 *, int *, _QWORD, struct _DEVPROPERTY *, void (*)(struct HSWDEVICE__ *, int, void *, const unsigned __int16 *), unsigned __int16 **, struct HSWDEVICE__ **))SwDeviceCreate)(
          L"TS_INPT",
          a3,
          &v32,
          a8,
          a7,
          CTiBus::CreateSwDeviceCallback,
          &v26,
          &v38);
  if ( v15 >= 0 )
  {
    v21 = WaitForSingleObject(hHandle_4, 0xFFFFFFFF);
    if ( v21 )
    {
      if ( v21 != -1 )
      {
        v15 = -2147418113;
        goto LABEL_25;
      }
      v22 = GetLastError();
      v15 = v22;
      if ( v22 > 0 )
        v15 = (unsigned __int16)v22 | 0x80070000;
      if ( v15 < 0 )
      {
LABEL_25:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 41;
          v18 = "WaitForSingleObject failed";
          goto LABEL_9;
        }
        goto LABEL_41;
      }
    }
    if ( v30 >= 0 )
    {
      if ( v20 && (v15 = SwDeviceInterfaceRegister(v38, &GUID_DEVINTERFACE_TIBUS, 0, 0, 0, 1, 0), v15 < 0) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 43;
          v18 = "SwDeviceInterfaceRegister failed";
          goto LABEL_9;
        }
      }
      else
      {
        v23 = v38;
        v38 = 0;
        *a10 = v23;
      }
    }
    else
    {
      v15 = v30;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 42;
        v18 = "CreateSwDeviceCallback failed";
        goto LABEL_9;
      }
    }
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 40;
    v18 = "SwDeviceCreate failed";
    goto LABEL_9;
  }
LABEL_41:
  if ( v38 )
    SwDeviceClose();
  if ( hHandle_4 )
    CloseHandle(hHandle_4);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001b068  mov     rax, rsp
0x18001b06b  mov     [rax+10h], rbx
0x18001b06f  mov     [rax+18h], rsi
0x18001b073  mov     [rax+8], rcx
0x18001b077  push    rbp
0x18001b078  push    rdi
0x18001b079  push    r14
0x18001b07b  lea     rbp, [rax-1Fh]
0x18001b07f  sub     rsp, 0B0h
0x18001b086  mov     r14, rdx
0x18001b089  mov     [rbp+17h+arg_0], 0
0x18001b091  xor     edx, edx; Val
0x18001b093  mov     [rbp+17h+hHandle], 0
0x18001b09b  mov     rsi, r8
0x18001b09e  mov     [rbp+17h+var_6C], 0
0x18001b0a6  lea     rcx, [rbp+17h+var_60]; void *
0x18001b0aa  mov     [rbp+17h+var_64], 0
0x18001b0b1  mov     rdi, r9
0x18001b0b4  lea     r8d, [rdx+48h]; Size
0x18001b0b8  call    memset_0
0x18001b0bd  mov     rax, [rbp+17h+arg_50]
0x18001b0c1  xor     r9d, r9d; lpName
0x18001b0c4  xor     r8d, r8d; bInitialState
0x18001b0c7  mov     [rbp+17h+var_80], rax
0x18001b0cb  xor     ecx, ecx; lpEventAttributes
0x18001b0cd  mov     [rbp+17h+var_78], 104h
0x18001b0d4  lea     edx, [r9+1]; bManualReset
0x18001b0d8  call    cs:__imp_CreateEventW
0x18001b0de  mov     [rbp+17h+hHandle+4], rax
0x18001b0e2  test    rax, rax
0x18001b0e5  jnz     short loc_18001B164
0x18001b0e7  call    cs:__imp_GetLastError
0x18001b0ed  mov     ebx, eax
0x18001b0ef  test    eax, eax
0x18001b0f1  jle     short loc_18001B0FC
0x18001b0f3  movzx   ebx, ax
0x18001b0f6  or      ebx, 80070000h
0x18001b0fc  test    ebx, ebx
0x18001b0fe  jns     short loc_18001B164
0x18001b100  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b107  lea     rax, WPP_GLOBAL_Control
0x18001b10e  cmp     rcx, rax
0x18001b111  jz      loc_18001B36F
0x18001b117  test    byte ptr [rcx+1Ch], 8
0x18001b11b  jz      loc_18001B36F
0x18001b121  cmp     byte ptr [rcx+19h], 2
0x18001b125  jb      loc_18001B36F
0x18001b12b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001b130  mov     edx, 27h ; '''
0x18001b135  lea     rcx, aCreateeventFai; "CreateEvent failed"
0x18001b13c  mov     dword ptr [rsp+0C0h+var_98], ebx
0x18001b140  lea     r8, WPP_6d85d9d5bb873cabab3b37f14470c4c2_Traceguids
0x18001b147  mov     [rsp+0C0h+var_A0], rcx
0x18001b14c  mov     r9d, eax
0x18001b14f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b156  mov     rcx, [rcx+10h]
0x18001b15a  call    WPP_SF_DsD
0x18001b15f  jmp     loc_18001B36F
0x18001b164  mov     rax, [rbp+17h+arg_20]
0x18001b168  lea     r8, [rbp+17h+var_60]
0x18001b16c  mov     r9d, [rbp+17h+arg_38]
0x18001b170  mov     [rbp+17h+var_48], rax
0x18001b174  mov     eax, 2
0x18001b179  mov     [rbp+17h+var_50], rdi
0x18001b17d  mov     edi, [rbp+17h+arg_40]
0x18001b180  test    edi, edi
0x18001b182  mov     [rbp+17h+var_60], 48h ; 'H'
0x18001b189  lea     ecx, [rax+8]
0x18001b18c  mov     [rbp+17h+var_58], r14
0x18001b190  cmovz   eax, ecx
0x18001b193  mov     [rbp+17h+var_30], 0
0x18001b19b  mov     [rbp+17h+var_38], eax
0x18001b19e  lea     rcx, aTsInpt; "TS_INPT"
0x18001b1a5  lea     rax, aHtreeRoot0; "HTREE\\ROOT\\0"
0x18001b1ac  test    rsi, rsi
0x18001b1af  cmovz   rsi, rax
0x18001b1b3  lea     rax, [rbp+17h+arg_0]
0x18001b1b7  mov     [rsp+0C0h+var_88], rax
0x18001b1bc  mov     rdx, rsi
0x18001b1bf  lea     rax, [rbp+17h+var_80]
0x18001b1c3  mov     [rsp+0C0h+var_90], rax
0x18001b1c8  lea     rax, ?CreateSwDeviceCallback@CTiBus@@CAXPEAUHSWDEVICE__@@JPEAXPEBG@Z; CTiBus::CreateSwDeviceCallback(HSWDEVICE__ *,long,void *,ushort const *)
0x18001b1cf  mov     [rsp+0C0h+var_98], rax
0x18001b1d4  mov     rax, [rbp+17h+arg_30]
0x18001b1d8  mov     [rsp+0C0h+var_A0], rax
0x18001b1dd  call    cs:__imp_SwDeviceCreate
0x18001b1e3  mov     ebx, eax
0x18001b1e5  test    eax, eax
0x18001b1e7  jns     short loc_18001B22A
0x18001b1e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1f0  lea     rax, WPP_GLOBAL_Control
0x18001b1f7  cmp     rcx, rax
0x18001b1fa  jz      loc_18001B36F
0x18001b200  test    byte ptr [rcx+1Ch], 8
0x18001b204  jz      loc_18001B36F
0x18001b20a  cmp     byte ptr [rcx+19h], 2
0x18001b20e  jb      loc_18001B36F
0x18001b214  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001b219  mov     edx, 28h ; '('
0x18001b21e  lea     rcx, aSwdevicecreate_0; "SwDeviceCreate failed"
0x18001b225  jmp     loc_18001B13C
0x18001b22a  mov     rcx, [rbp+17h+hHandle+4]; hHandle
0x18001b22e  or      esi, 0FFFFFFFFh
0x18001b231  mov     edx, esi; dwMilliseconds
0x18001b233  call    cs:__imp_WaitForSingleObject
0x18001b239  test    eax, eax
0x18001b23b  jz      short loc_18001B2A2
0x18001b23d  cmp     eax, esi
0x18001b23f  jz      short loc_18001B248
0x18001b241  mov     ebx, 8000FFFFh
0x18001b246  jmp     short loc_18001B261
0x18001b248  call    cs:__imp_GetLastError
0x18001b24e  mov     ebx, eax
0x18001b250  test    eax, eax
0x18001b252  jle     short loc_18001B25D
0x18001b254  movzx   ebx, ax
0x18001b257  or      ebx, 80070000h
0x18001b25d  test    ebx, ebx
0x18001b25f  jns     short loc_18001B2A2
0x18001b261  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b268  lea     rax, WPP_GLOBAL_Control
0x18001b26f  cmp     rcx, rax
0x18001b272  jz      loc_18001B36F
0x18001b278  test    byte ptr [rcx+1Ch], 8
0x18001b27c  jz      loc_18001B36F
0x18001b282  cmp     byte ptr [rcx+19h], 2
0x18001b286  jb      loc_18001B36F
0x18001b28c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001b291  mov     edx, 29h ; ')'
0x18001b296  lea     rcx, aWaitforsingleo; "WaitForSingleObject failed"
0x18001b29d  jmp     loc_18001B13C
0x18001b2a2  mov     eax, dword ptr [rbp+17h+var_6C+4]
0x18001b2a5  test    eax, eax
0x18001b2a7  jns     short loc_18001B2EC
0x18001b2a9  mov     ebx, eax
0x18001b2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2b2  lea     rax, WPP_GLOBAL_Control
0x18001b2b9  cmp     rcx, rax
0x18001b2bc  jz      loc_18001B36F
0x18001b2c2  test    byte ptr [rcx+1Ch], 8
0x18001b2c6  jz      loc_18001B36F
0x18001b2cc  cmp     byte ptr [rcx+19h], 2
0x18001b2d0  jb      loc_18001B36F
0x18001b2d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001b2db  mov     edx, 2Ah ; '*'
0x18001b2e0  lea     rcx, aCreateswdevice_0; "CreateSwDeviceCallback failed"
0x18001b2e7  jmp     loc_18001B13C
0x18001b2ec  test    edi, edi
0x18001b2ee  jz      short loc_18001B35C
0x18001b2f0  mov     rcx, [rbp+17h+arg_0]
0x18001b2f4  lea     rdx, ?GUID_DEVINTERFACE_TIBUS@@3U_GUID@@B; _GUID const GUID_DEVINTERFACE_TIBUS
0x18001b2fb  mov     [rsp+0C0h+var_90], 0
0x18001b304  xor     r9d, r9d
0x18001b307  mov     dword ptr [rsp+0C0h+var_98], 1
0x18001b30f  xor     r8d, r8d
0x18001b312  mov     [rsp+0C0h+var_A0], 0
0x18001b31b  call    cs:__imp_SwDeviceInterfaceRegister
0x18001b321  mov     ebx, eax
0x18001b323  test    eax, eax
0x18001b325  jns     short loc_18001B35C
0x18001b327  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b32e  lea     rax, WPP_GLOBAL_Control
0x18001b335  cmp     rcx, rax
0x18001b338  jz      short loc_18001B36F
0x18001b33a  test    byte ptr [rcx+1Ch], 8
0x18001b33e  jz      short loc_18001B36F
0x18001b340  cmp     byte ptr [rcx+19h], 2
0x18001b344  jb      short loc_18001B36F
0x18001b346  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001b34b  mov     edx, 2Bh ; '+'
0x18001b350  lea     rcx, aSwdeviceinterf_0; "SwDeviceInterfaceRegister failed"
0x18001b357  jmp     loc_18001B13C
0x18001b35c  mov     rax, [rbp+17h+arg_0]
0x18001b360  mov     rcx, [rbp+17h+arg_48]
0x18001b364  mov     [rbp+17h+arg_0], 0
0x18001b36c  mov     [rcx], rax
0x18001b36f  mov     rcx, [rbp+17h+arg_0]
0x18001b373  test    rcx, rcx
0x18001b376  jz      short loc_18001B37E
0x18001b378  call    cs:__imp_SwDeviceClose
0x18001b37e  mov     rcx, [rbp+17h+hHandle+4]; hObject
0x18001b382  test    rcx, rcx
0x18001b385  jz      short loc_18001B38D
0x18001b387  call    cs:__imp_CloseHandle
0x18001b38d  lea     r11, [rsp+0C0h+var_10]
0x18001b395  mov     eax, ebx
0x18001b397  mov     rbx, [r11+28h]
0x18001b39b  mov     rsi, [r11+30h]
0x18001b39f  mov     rsp, r11
0x18001b3a2  pop     r14
0x18001b3a4  pop     rdi
0x18001b3a5  pop     rbp
0x18001b3a6  retn
```
