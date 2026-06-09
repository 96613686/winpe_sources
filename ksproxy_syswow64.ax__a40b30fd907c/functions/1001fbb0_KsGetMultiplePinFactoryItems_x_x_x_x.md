# KsGetMultiplePinFactoryItems(x,x,x,x)

- ea: `0x1001fbb0`
- end: `0x1001fcc0`
- name: `_KsGetMultiplePinFactoryItems@16`
- size: `272`
- prototype: `int __stdcall(HANDLE hDevice, int, int, LPVOID *)`
- caller_count: `10`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1000af42`
- `0x10011360`
- `0x100113a0`
- `0x10014e50`
- `0x10014e90`
- `0x10017be0`
- `0x1001e8ef`
- `0x1001ff00`
- `0x1001ffa0`
- `0x100202e2`

## callees

- `0x100063f1`
- `0x1001f3b0`
- `0x1001fbb0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1001fc6a`
- `ole32!CoTaskMemAlloc` at `0x1001fc6a`
- `ole32!CoTaskMemFree` at `0x1001fca3`
- `ole32!CoTaskMemFree` at `0x1001fca3`

## pseudocode

```c
int __stdcall KsGetMultiplePinFactoryItems(HANDLE hDevice, int a2, int a3, LPVOID *a4)
{
  int v4; // esi
  SIZE_T v5; // eax
  void *v6; // eax
  GUID InBuffer; // [esp+10h] [ebp-28h] BYREF
  int v9; // [esp+20h] [ebp-18h]
  int v10; // [esp+24h] [ebp-14h]
  int v11; // [esp+28h] [ebp-10h]
  int v12; // [esp+2Ch] [ebp-Ch]
  SIZE_T cb; // [esp+30h] [ebp-8h] BYREF
  DWORD BytesReturned; // [esp+34h] [ebp-4h] BYREF

  BytesReturned = 0;
  InBuffer = _GUID_8c134960_51ad_11cf_878a_94f801c10000;
  v9 = a3;
  v10 = 1;
  v11 = a2;
  v12 = 0;
  if ( a3 == 3 || a3 == 13 )
    v12 = 1;
  v4 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, &InBuffer, 0x20u, 0, 0, &BytesReturned);
  if ( v4 != -2147024774 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(0x16u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
  v4 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, &InBuffer, 0x20u, &cb, 4u, &BytesReturned);
  if ( v4 >= 0 )
  {
    v5 = cb;
    BytesReturned = cb;
  }
  else
  {
LABEL_10:
    if ( v4 != -2147024662 )
    {
      if ( v4 >= 0 )
        return -2147418113;
      return v4;
    }
    v5 = BytesReturned;
  }
  v6 = CoTaskMemAlloc(v5);
  *a4 = v6;
  if ( !v6 )
    return -2147024882;
  v4 = KsSynchronousDeviceControl(hDevice, 0x2F0003u, &InBuffer, 0x20u, v6, BytesReturned, &BytesReturned);
  if ( v4 < 0 )
  {
    CoTaskMemFree(*a4);
    *a4 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1001fbb0  mov     edi, edi
0x1001fbb2  push    ebp
0x1001fbb3  mov     ebp, esp
0x1001fbb5  sub     esp, 2Ch
0x1001fbb8  mov     ecx, [ebp+arg_8]
0x1001fbbb  xor     edx, edx
0x1001fbbd  mov     eax, [ebp+arg_4]
0x1001fbc0  inc     edx
0x1001fbc1  push    ebx
0x1001fbc2  push    esi
0x1001fbc3  push    edi
0x1001fbc4  mov     esi, offset __GUID_8c134960_51ad_11cf_878a_94f801c10000
0x1001fbc9  lea     edi, [ebp+InBuffer]
0x1001fbcc  xor     ebx, ebx
0x1001fbce  mov     [ebp+BytesReturned], ebx
0x1001fbd1  movsd
0x1001fbd2  movsd
0x1001fbd3  movsd
0x1001fbd4  movsd
0x1001fbd5  mov     [ebp+var_18], ecx
0x1001fbd8  mov     [ebp+var_14], edx
0x1001fbdb  mov     [ebp+var_10], eax
0x1001fbde  mov     [ebp+var_C], ebx
0x1001fbe1  cmp     ecx, 3
0x1001fbe4  jz      short loc_1001FBEB
0x1001fbe6  cmp     ecx, 0Dh
0x1001fbe9  jnz     short loc_1001FBEE
0x1001fbeb  mov     [ebp+var_C], edx
0x1001fbee  lea     eax, [ebp+BytesReturned]
0x1001fbf1  mov     edi, 2F0003h
0x1001fbf6  push    eax; lpBytesReturned
0x1001fbf7  push    ebx; nOutBufferSize
0x1001fbf8  push    ebx; lpOutBuffer
0x1001fbf9  push    20h ; ' '; nInBufferSize
0x1001fbfb  lea     eax, [ebp+InBuffer]
0x1001fbfe  push    eax; lpInBuffer
0x1001fbff  push    edi; dwIoControlCode
0x1001fc00  push    [ebp+hDevice]; hDevice
0x1001fc03  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001fc08  mov     esi, eax
0x1001fc0a  cmp     esi, 8007007Ah
0x1001fc10  jnz     short loc_1001FC5E
0x1001fc12  mov     eax, _WPP_GLOBAL_Control
0x1001fc17  cmp     eax, offset _WPP_GLOBAL_Control
0x1001fc1c  jz      short loc_1001FC37
0x1001fc1e  cmp     byte ptr [eax+19h], 2
0x1001fc22  jb      short loc_1001FC37
0x1001fc24  push    dword ptr [eax+14h]
0x1001fc27  mov     edx, offset _WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids; MessageGuid
0x1001fc2c  push    dword ptr [eax+10h]; LoggerHandle
0x1001fc2f  push    16h
0x1001fc31  pop     ecx; MessageNumber
0x1001fc32  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x1001fc37  lea     eax, [ebp+BytesReturned]
0x1001fc3a  push    eax; lpBytesReturned
0x1001fc3b  push    4; nOutBufferSize
0x1001fc3d  lea     eax, [ebp+cb]
0x1001fc40  push    eax; lpOutBuffer
0x1001fc41  push    20h ; ' '; nInBufferSize
0x1001fc43  lea     eax, [ebp+InBuffer]
0x1001fc46  push    eax; lpInBuffer
0x1001fc47  push    edi; dwIoControlCode
0x1001fc48  push    [ebp+hDevice]; hDevice
0x1001fc4b  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001fc50  mov     esi, eax
0x1001fc52  test    esi, esi
0x1001fc54  js      short loc_1001FC5E
0x1001fc56  mov     eax, [ebp+cb]
0x1001fc59  mov     [ebp+BytesReturned], eax
0x1001fc5c  jmp     short loc_1001FC69
0x1001fc5e  cmp     esi, 800700EAh
0x1001fc64  jnz     short loc_1001FCAD
0x1001fc66  mov     eax, [ebp+BytesReturned]
0x1001fc69  push    eax; cb
0x1001fc6a  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x1001fc70  mov     edi, [ebp+arg_C]
0x1001fc73  mov     [edi], eax
0x1001fc75  test    eax, eax
0x1001fc77  jnz     short loc_1001FC80
0x1001fc79  mov     eax, 8007000Eh
0x1001fc7e  jmp     short loc_1001FCB9
0x1001fc80  lea     ecx, [ebp+BytesReturned]
0x1001fc83  push    ecx; lpBytesReturned
0x1001fc84  push    [ebp+BytesReturned]; nOutBufferSize
0x1001fc87  push    eax; lpOutBuffer
0x1001fc88  push    20h ; ' '; nInBufferSize
0x1001fc8a  lea     eax, [ebp+InBuffer]
0x1001fc8d  push    eax; lpInBuffer
0x1001fc8e  push    2F0003h; dwIoControlCode
0x1001fc93  push    [ebp+hDevice]; hDevice
0x1001fc96  call    _KsSynchronousDeviceControl@28; KsSynchronousDeviceControl(x,x,x,x,x,x,x)
0x1001fc9b  mov     esi, eax
0x1001fc9d  test    esi, esi
0x1001fc9f  jns     short loc_1001FCB7
0x1001fca1  push    dword ptr [edi]; pv
0x1001fca3  call    ds:__imp__CoTaskMemFree@4; CoTaskMemFree(x)
0x1001fca9  mov     [edi], ebx
0x1001fcab  jmp     short loc_1001FCB7
0x1001fcad  test    esi, esi
0x1001fcaf  mov     eax, 8000FFFFh
0x1001fcb4  cmovns  esi, eax
0x1001fcb7  mov     eax, esi
0x1001fcb9  pop     edi
0x1001fcba  pop     esi
0x1001fcbb  pop     ebx
0x1001fcbc  leave
0x1001fcbd  retn    10h
```
