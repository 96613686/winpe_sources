# GetDiskInfo(void *,_SP_DEVICE_INTERFACE_DATA *,_SP_DEVINFO_DATA *,_SP_DEVICE_INTERFACE_DETAIL_DATA_W * *)

- ea: `0x1800065bc`
- end: `0x18000680e`
- name: `?GetDiskInfo@@YAHPEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEAU_SP_DEVINFO_DATA@@PEAPEAU_SP_DEVICE_INTERFACE_DETAIL_DATA_W@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVICE_INTERFACE_DATA DeviceInterfaceData, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180005638`

## callees

- `0x180005528`
- `0x1800065bc`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800066cd`
- `KERNEL32!GetProcessHeap` at `0x1800066e8`
- `KERNEL32!GetProcessHeap` at `0x180006783`
- `KERNEL32!GetProcessHeap` at `0x1800066cd`
- `KERNEL32!GetProcessHeap` at `0x1800066e8`
- `KERNEL32!GetProcessHeap` at `0x180006783`
- `KERNEL32!HeapAlloc` at `0x1800066f6`
- `KERNEL32!HeapAlloc` at `0x1800066f6`
- `KERNEL32!GetLastError` at `0x1800066bd`
- `KERNEL32!GetLastError` at `0x18000673c`
- `KERNEL32!GetLastError` at `0x1800067bb`
- `KERNEL32!GetLastError` at `0x1800066bd`
- `KERNEL32!GetLastError` at `0x18000673c`
- `KERNEL32!GetLastError` at `0x1800067bb`
- `KERNEL32!HeapFree` at `0x1800066db`
- `KERNEL32!HeapFree` at `0x180006791`
- `KERNEL32!HeapFree` at `0x1800066db`
- `KERNEL32!HeapFree` at `0x180006791`
- `KERNEL32!SetLastError` at `0x1800067a3`
- `KERNEL32!SetLastError` at `0x1800067a3`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800066af`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1800066af`

## string_xrefs

- `0x180006644`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`
- `0x18000675a`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall GetDiskInfo(
        HDEVINFO DeviceInfoSet,
        PSP_DEVICE_INTERFACE_DATA DeviceInterfaceData,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W **a4)
{
  unsigned int v4; // ebp
  _QWORD *v9; // rcx
  DWORD v10; // edi
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v11; // rbx
  DWORD v12; // r9d
  HANDLE ProcessHeap; // rax
  DWORD v14; // ebx
  HANDLE v15; // rax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v16; // rax
  DWORD LastError; // eax
  HANDLE v18; // rax
  int v19; // r8d
  int v20; // r9d
  const char *v21; // rcx
  char v23; // [rsp+30h] [rbp-58h]
  DWORD RequiredSize; // [rsp+A0h] [rbp+18h] BYREF

  v4 = 0;
  RequiredSize = 0;
  v9 = WPP_GLOBAL_Control;
  v10 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
    v9 = WPP_GLOBAL_Control;
  }
  if ( DeviceInfoData )
  {
    if ( a4 )
    {
      v11 = 0;
      DeviceInfoData->cbSize = 32;
      v12 = 0;
      while ( 1 )
      {
        if ( SetupDiGetDeviceInterfaceDetailW(
               DeviceInfoSet,
               DeviceInterfaceData,
               v11,
               v12,
               &RequiredSize,
               DeviceInfoData) )
        {
          v10 = 0;
          *a4 = v11;
          v4 = 1;
          goto LABEL_29;
        }
        if ( GetLastError() != 122 )
          break;
        if ( v11 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v11);
        }
        v14 = RequiredSize;
        v15 = GetProcessHeap();
        v16 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)HeapAlloc(v15, 8u, v14);
        v11 = v16;
        if ( !v16 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              87,
              (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
              (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
              120,
              8);
          goto LABEL_29;
        }
        v12 = RequiredSize;
        v16->cbSize = 8;
      }
      LastError = GetLastError();
      v10 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          86,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          105,
          LastError);
      if ( v11 )
      {
        v18 = GetProcessHeap();
        HeapFree(v18, 0, v11);
      }
    }
    else
    {
      v10 = 87;
      if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
        WPP_SF_sdD(
          v9[2],
          85,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          90,
          87);
    }
  }
  else
  {
    v10 = 87;
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_sdD(
        v9[2],
        84,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        89,
        87);
  }
LABEL_29:
  SetLastError(v10);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v23 = GetLastError();
    v21 = "Success";
    if ( !v4 )
      v21 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v19, v20, 142, (__int64)v21, v23);
  }
  return v4;
}

```

## disassembly

```asm
0x1800065bc  mov     rax, rsp
0x1800065bf  push    rbx
0x1800065c0  push    rbp
0x1800065c1  push    rsi
0x1800065c2  push    rdi
0x1800065c3  push    r12
0x1800065c5  push    r13
0x1800065c7  push    r14
0x1800065c9  push    r15
0x1800065cb  sub     rsp, 48h
0x1800065cf  xor     ebp, ebp
0x1800065d1  mov     r14, r9
0x1800065d4  mov     [rax+18h], ebp
0x1800065d7  mov     rsi, r8
0x1800065da  mov     r15, rdx
0x1800065dd  mov     r12, rcx
0x1800065e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065e7  lea     r13, WPP_GLOBAL_Control
0x1800065ee  lea     edi, [rbp+8]
0x1800065f1  cmp     rcx, r13
0x1800065f4  jz      short loc_180006616
0x1800065f6  test    [rcx+1Ch], dil
0x1800065fa  jz      short loc_180006616
0x1800065fc  mov     rcx, [rcx+10h]
0x180006600  lea     edx, [rbp+53h]
0x180006603  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000660a  call    WPP_SF_
0x18000660f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006616  test    rsi, rsi
0x180006619  jnz     short loc_18000665C
0x18000661b  lea     edi, [rsi+57h]
0x18000661e  cmp     rcx, r13
0x180006621  jz      loc_1800067A1
0x180006627  test    byte ptr [rcx+1Ch], 1
0x18000662b  jz      loc_1800067A1
0x180006631  mov     dword ptr [rsp+88h+DeviceInfoData], edi
0x180006635  lea     edx, [rsi+54h]
0x180006638  mov     dword ptr [rsp+88h+RequiredSize], 459h
0x180006640  mov     rcx, [rcx+10h]
0x180006644  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x18000664b  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180006652  call    WPP_SF_sdD
0x180006657  jmp     loc_1800067A1
0x18000665c  test    r14, r14
0x18000665f  jnz     short loc_180006689
0x180006661  lea     edi, [r14+57h]
0x180006665  cmp     rcx, r13
0x180006668  jz      loc_1800067A1
0x18000666e  test    byte ptr [rcx+1Ch], 1
0x180006672  jz      loc_1800067A1
0x180006678  mov     dword ptr [rsp+88h+DeviceInfoData], edi
0x18000667c  lea     edx, [rdi-2]
0x18000667f  mov     dword ptr [rsp+88h+RequiredSize], 45Ah
0x180006687  jmp     short loc_180006640
0x180006689  xor     ebx, ebx
0x18000668b  mov     dword ptr [rsi], 20h ; ' '
0x180006691  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180006694  lea     rax, [rsp+88h+arg_10]
0x18000669c  mov     [rsp+88h+DeviceInfoData], rsi; DeviceInfoData
0x1800066a1  mov     r8, rbx; DeviceInterfaceDetailData
0x1800066a4  mov     [rsp+88h+RequiredSize], rax; RequiredSize
0x1800066a9  mov     rdx, r15; DeviceInterfaceData
0x1800066ac  mov     rcx, r12; DeviceInfoSet
0x1800066af  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1800066b5  test    eax, eax
0x1800066b7  jnz     loc_180006799
0x1800066bd  call    cs:__imp_GetLastError
0x1800066c3  cmp     eax, 7Ah ; 'z'
0x1800066c6  jnz     short loc_18000673C
0x1800066c8  test    rbx, rbx
0x1800066cb  jz      short loc_1800066E1
0x1800066cd  call    cs:__imp_GetProcessHeap
0x1800066d3  mov     r8, rbx; lpMem
0x1800066d6  xor     edx, edx; dwFlags
0x1800066d8  mov     rcx, rax; hHeap
0x1800066db  call    cs:__imp_HeapFree
0x1800066e1  mov     ebx, [rsp+88h+arg_10]
0x1800066e8  call    cs:__imp_GetProcessHeap
0x1800066ee  mov     r8d, ebx; dwBytes
0x1800066f1  mov     edx, edi; dwFlags
0x1800066f3  mov     rcx, rax; hHeap
0x1800066f6  call    cs:__imp_HeapAlloc
0x1800066fc  mov     rbx, rax
0x1800066ff  test    rax, rax
0x180006702  jz      short loc_180006710
0x180006704  mov     r9d, [rsp+88h+arg_10]
0x18000670c  mov     [rax], edi
0x18000670e  jmp     short loc_180006694
0x180006710  mov     rcx, cs:WPP_GLOBAL_Control
0x180006717  cmp     rcx, r13
0x18000671a  jz      loc_1800067A1
0x180006720  test    byte ptr [rcx+1Ch], 1
0x180006724  jz      short loc_1800067A1
0x180006726  mov     dword ptr [rsp+88h+DeviceInfoData], edi
0x18000672a  mov     edx, 57h ; 'W'
0x18000672f  mov     dword ptr [rsp+88h+RequiredSize], 478h
0x180006737  jmp     loc_180006640
0x18000673c  call    cs:__imp_GetLastError
0x180006742  mov     edi, eax
0x180006744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000674b  cmp     rcx, r13
0x18000674e  jz      short loc_18000677E
0x180006750  test    byte ptr [rcx+1Ch], 1
0x180006754  jz      short loc_18000677E
0x180006756  mov     rcx, [rcx+10h]
0x18000675a  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x180006761  mov     dword ptr [rsp+88h+DeviceInfoData], eax
0x180006765  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000676c  mov     edx, 56h ; 'V'
0x180006771  mov     dword ptr [rsp+88h+RequiredSize], 469h
0x180006779  call    WPP_SF_sdD
0x18000677e  test    rbx, rbx
0x180006781  jz      short loc_1800067A1
0x180006783  call    cs:__imp_GetProcessHeap
0x180006789  mov     r8, rbx; lpMem
0x18000678c  xor     edx, edx; dwFlags
0x18000678e  mov     rcx, rax; hHeap
0x180006791  call    cs:__imp_HeapFree
0x180006797  jmp     short loc_1800067A1
0x180006799  xor     edi, edi
0x18000679b  mov     [r14], rbx
0x18000679e  lea     ebp, [rdi+1]
0x1800067a1  mov     ecx, edi; dwErrCode
0x1800067a3  call    cs:__imp_SetLastError
0x1800067a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800067b0  cmp     rax, r13
0x1800067b3  jz      short loc_1800067FB
0x1800067b5  test    byte ptr [rax+1Ch], 4
0x1800067b9  jz      short loc_1800067FB
0x1800067bb  call    cs:__imp_GetLastError
0x1800067c1  lea     rdx, aFailure; "Failure"
0x1800067c8  mov     dword ptr [rsp+88h+var_58], eax
0x1800067cc  test    ebp, ebp
0x1800067ce  lea     rcx, aSuccess; "Success"
0x1800067d5  cmovz   rcx, rdx
0x1800067d9  mov     edx, 58h ; 'X'
0x1800067de  mov     [rsp+88h+DeviceInfoData], rcx
0x1800067e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067ea  mov     dword ptr [rsp+88h+RequiredSize], 48Eh
0x1800067f2  mov     rcx, [rcx+10h]
0x1800067f6  call    WPP_SF_sdsd
0x1800067fb  mov     eax, ebp
0x1800067fd  add     rsp, 48h
0x180006801  pop     r15
0x180006803  pop     r14
0x180006805  pop     r13
0x180006807  pop     r12
0x180006809  pop     rdi
0x18000680a  pop     rsi
0x18000680b  pop     rbp
0x18000680c  pop     rbx
0x18000680d  retn
```
