# CSetupAPIDevice::GetDriverDetails(_SP_DRVINFO_DETAIL_DATA_W * *)

- ea: `0x18002a454`
- end: `0x18002a57d`
- name: `?GetDriverDetails@CSetupAPIDevice@@QEAAJPEAPEAU_SP_DRVINFO_DETAIL_DATA_W@@@Z`
- size: `297`
- prototype: `__int64 __fastcall(CSetupAPIDevice *__hidden this, struct _SP_DRVINFO_DETAIL_DATA_W **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180027020`

## callees

- `0x18002a454`
- `0x18002ad14`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a521`
- `KERNEL32!GetLastError` at `0x18002a548`
- `KERNEL32!GetLastError` at `0x18002a521`
- `KERNEL32!GetLastError` at `0x18002a548`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18002a4ba`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18002a512`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18002a4ba`
- `SETUPAPI!SetupDiGetDriverInfoDetailW` at `0x18002a512`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a539`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a539`

## pseudocode

```c
__int64 __fastcall CSetupAPIDevice::GetDriverDetails(CSetupAPIDevice *this, struct _SP_DRVINFO_DETAIL_DATA_W **a2)
{
  __int64 result; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // rbp
  __int64 v8; // rcx
  struct _SP_DRVINFO_DETAIL_DATA_W *v9; // rax
  struct _SP_DRVINFO_DETAIL_DATA_W *v10; // rdi
  __int64 v11; // rax
  signed int LastError; // eax
  signed int v13; // eax
  DWORD RequiredSize; // [rsp+70h] [rbp+18h] BYREF

  result = CSetupAPIDevice::InitializeDriverInfo(this);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = *((_QWORD *)this + 1);
    v7 = -1;
    RequiredSize = 0;
    if ( v6 )
      v8 = *(_QWORD *)(v6 + 8);
    else
      v8 = -1;
    if ( SetupDiGetDriverInfoDetailW(
           (HDEVINFO)v8,
           (PSP_DEVINFO_DATA)((char *)this + 16),
           (PSP_DRVINFO_DATA_W)((char *)this + 64),
           0,
           0,
           &RequiredSize) )
    {
      return (unsigned int)-2147467260;
    }
    else if ( RequiredSize )
    {
      v9 = (struct _SP_DRVINFO_DETAIL_DATA_W *)CoTaskMemAlloc(RequiredSize);
      v10 = v9;
      if ( v9 )
      {
        v9->cbSize = 1584;
        v11 = *((_QWORD *)this + 1);
        if ( v11 )
          v7 = *(_QWORD *)(v11 + 8);
        if ( SetupDiGetDriverInfoDetailW(
               (HDEVINFO)v7,
               (PSP_DEVINFO_DATA)((char *)this + 16),
               (PSP_DRVINFO_DATA_W)((char *)this + 64),
               v10,
               RequiredSize,
               0) )
        {
          *a2 = v10;
        }
        else
        {
          LastError = GetLastError();
          v5 = LastError;
          if ( LastError > 0 )
            v5 = (unsigned __int16)LastError | 0x80070000;
          CoTaskMemFree(v10);
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        return (unsigned __int16)v13 | 0x80070000;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002a454  mov     [rsp+arg_0], rbx
0x18002a459  mov     [rsp+arg_8], rbp
0x18002a45e  push    rsi
0x18002a45f  push    rdi
0x18002a460  push    r12
0x18002a462  push    r14
0x18002a464  push    r15
0x18002a466  sub     rsp, 30h
0x18002a46a  mov     r14, rdx
0x18002a46d  mov     rsi, rcx
0x18002a470  call    ?InitializeDriverInfo@CSetupAPIDevice@@AEAAJXZ; CSetupAPIDevice::InitializeDriverInfo(void)
0x18002a475  mov     ebx, eax
0x18002a477  test    eax, eax
0x18002a479  js      loc_18002A566
0x18002a47f  mov     rax, [rsi+8]
0x18002a483  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18002a487  mov     [rsp+58h+arg_10], 0
0x18002a48f  test    rax, rax
0x18002a492  jz      short loc_18002A49A
0x18002a494  mov     rcx, [rax+8]
0x18002a498  jmp     short loc_18002A49D
0x18002a49a  mov     rcx, rbp; DeviceInfoSet
0x18002a49d  lea     rax, [rsp+58h+arg_10]
0x18002a4a2  xor     r9d, r9d; DriverInfoDetailData
0x18002a4a5  mov     [rsp+58h+RequiredSize], rax; RequiredSize
0x18002a4aa  lea     r8, [rsi+40h]; DriverInfoData
0x18002a4ae  lea     rdx, [rsi+10h]; DeviceInfoData
0x18002a4b2  mov     [rsp+58h+DriverInfoDetailDataSize], 0; DriverInfoDetailDataSize
0x18002a4ba  call    cs:__imp_SetupDiGetDriverInfoDetailW
0x18002a4c0  test    eax, eax
0x18002a4c2  jnz     loc_18002A55F
0x18002a4c8  mov     eax, [rsp+58h+arg_10]
0x18002a4cc  test    eax, eax
0x18002a4ce  jz      short loc_18002A548
0x18002a4d0  mov     ecx, eax; cb
0x18002a4d2  call    cs:__imp_CoTaskMemAlloc
0x18002a4d8  mov     rdi, rax
0x18002a4db  test    rax, rax
0x18002a4de  jz      short loc_18002A541
0x18002a4e0  mov     dword ptr [rax], 630h
0x18002a4e6  mov     rax, [rsi+8]
0x18002a4ea  mov     ecx, [rsp+58h+arg_10]
0x18002a4ee  test    rax, rax
0x18002a4f1  jz      short loc_18002A4F7
0x18002a4f3  mov     rbp, [rax+8]
0x18002a4f7  mov     [rsp+58h+RequiredSize], 0; RequiredSize
0x18002a500  lea     r8, [rsi+40h]; DriverInfoData
0x18002a504  mov     [rsp+58h+DriverInfoDetailDataSize], ecx; DriverInfoDetailDataSize
0x18002a508  lea     rdx, [rsi+10h]; DeviceInfoData
0x18002a50c  mov     rcx, rbp; DeviceInfoSet
0x18002a50f  mov     r9, rdi; DriverInfoDetailData
0x18002a512  call    cs:__imp_SetupDiGetDriverInfoDetailW
0x18002a518  test    eax, eax
0x18002a51a  jz      short loc_18002A521
0x18002a51c  mov     [r14], rdi
0x18002a51f  jmp     short loc_18002A564
0x18002a521  call    cs:__imp_GetLastError
0x18002a527  mov     ebx, eax
0x18002a529  test    eax, eax
0x18002a52b  jle     short loc_18002A536
0x18002a52d  movzx   ebx, ax
0x18002a530  or      ebx, 80070000h
0x18002a536  mov     rcx, rdi; pv
0x18002a539  call    cs:__imp_CoTaskMemFree
0x18002a53f  jmp     short loc_18002A564
0x18002a541  mov     ebx, 8007000Eh
0x18002a546  jmp     short loc_18002A564
0x18002a548  call    cs:__imp_GetLastError
0x18002a54e  mov     ebx, eax
0x18002a550  test    eax, eax
0x18002a552  jle     short loc_18002A564
0x18002a554  movzx   ebx, ax
0x18002a557  or      ebx, 80070000h
0x18002a55d  jmp     short loc_18002A564
0x18002a55f  mov     ebx, 80004004h
0x18002a564  mov     eax, ebx
0x18002a566  mov     rbx, [rsp+58h+arg_0]
0x18002a56b  mov     rbp, [rsp+58h+arg_8]
0x18002a570  add     rsp, 30h
0x18002a574  pop     r15
0x18002a576  pop     r14
0x18002a578  pop     r12
0x18002a57a  pop     rdi
0x18002a57b  pop     rsi
0x18002a57c  retn
```
