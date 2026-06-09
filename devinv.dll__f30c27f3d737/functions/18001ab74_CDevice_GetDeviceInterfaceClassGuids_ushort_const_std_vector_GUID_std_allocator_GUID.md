# CDevice::GetDeviceInterfaceClassGuids(ushort const *,std::vector<_GUID,std::allocator<_GUID>> &)

- ea: `0x18001ab74`
- end: `0x18001ad9c`
- name: `?GetDeviceInterfaceClassGuids@CDevice@@SAXPEBGAEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@Z`
- size: `552`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b5e8`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x180018ac4`
- `0x18001ab74`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `DEVOBJ!DevObjGetClassDevs` at `0x18001ad1c`
- `DEVOBJ!DevObjGetClassDevs` at `0x18001ad1c`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001ad45`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18001ad45`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001abd6`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18001abd6`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001ad8f`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18001ad8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001abee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aca0`

## string_xrefs

- `0x18001abf8`: `DevObjCreateDeviceInfoList failed [%d]`

## pseudocode

```c
void __fastcall CDevice::GetDeviceInterfaceClassGuids(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r15
  unsigned int i; // ebx
  __int64 DeviceInfoList; // r14
  FILE *v6; // rax
  DWORD v7; // ebx
  FILE *v8; // rax
  FILE *v9; // rax
  DWORD v10; // eax
  DWORD v11; // eax
  _OWORD *v12; // rdx
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  DWORD LastError; // [rsp+20h] [rbp-88h]
  __int128 v19; // [rsp+50h] [rbp-58h] BYREF
  _OWORD v20[2]; // [rsp+60h] [rbp-48h] BYREF

  v2 = a2;
  v3 = a1;
  memset(v20, 0, sizeof(v20));
  for ( i = 0; i < 4; ++i )
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    if ( DeviceInfoList == -1 )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        2,
        "CDevice::GetDeviceInterfaceClassGuids",
        624,
        "DevObjCreateDeviceInfoList failed [%d]",
        LastError);
      if ( EnableDevInvStdErrLog )
      {
        v6 = o___acrt_iob_func_0(2u);
        fprintf(v6, "Error: %s, %u: ", "CDevice::GetDeviceInterfaceClassGuids", 624);
        v7 = GetLastError();
        v8 = o___acrt_iob_func_0(2u);
        fprintf(v8, "DevObjCreateDeviceInfoList failed [%d]", v7);
        v9 = o___acrt_iob_func_0(2u);
        fprintf(v9, "\n");
      }
      if ( g_DeviceMapLogFunction )
      {
        v10 = GetLastError();
        TraceMessageCallback(0x2000000, "DevObjCreateDeviceInfoList failed [%d]", v10);
      }
      v11 = GetLastError();
      AslLogCallPrintf(1, "CDevice::GetDeviceInterfaceClassGuids", 624, "DevObjCreateDeviceInfoList failed [%d]", v11);
      return;
    }
    v19 = *((_OWORD *)&CDevice::s_DeviceInterfaceClassGuids + (int)i);
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &v19, v3, 18, 0, 0) )
    {
      LODWORD(v20[0]) = 32;
      if ( (unsigned int)DevObjEnumDeviceInterfaces(DeviceInfoList, 0, &v19, 0, v20) )
      {
        try
        {
          v12 = *(_OWORD **)(v2 + 8);
          if ( v12 == *(_OWORD **)(v2 + 16) )
          {
            std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v2, v12, &v19);
          }
          else
          {
            *v12 = v19;
            *(_QWORD *)(v2 + 8) += 16LL;
          }
        }
        catch ( std::bad_alloc )
        {
          AslLogCallPrintf(2, "CDevice::GetDeviceInterfaceClassGuids", 658, "Out of memory");
          if ( EnableDevInvStdErrLog )
          {
            v13 = o___acrt_iob_func_0(2u);
            fprintf(v13, "Error: %s, %u: ", "CDevice::GetDeviceInterfaceClassGuids", 658);
            v14 = o___acrt_iob_func_0(2u);
            fprintf(v14, "Out of memory");
            v15 = o___acrt_iob_func_0(2u);
            fprintf(v15, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "Out of memory");
          v2 = a2;
          v3 = a1;
        }
      }
    }
    DevObjDestroyDeviceInfoList(DeviceInfoList);
  }
}

```

## disassembly

```asm
0x18001ab74  mov     [rsp+arg_10], rbx
0x18001ab79  push    rsi
0x18001ab7a  push    r14
0x18001ab7c  push    r15
0x18001ab7e  sub     rsp, 90h
0x18001ab85  mov     rax, cs:__security_cookie
0x18001ab8c  xor     rax, rsp
0x18001ab8f  mov     [rsp+0A8h+var_28], rax
0x18001ab97  mov     rsi, rdx
0x18001ab9a  mov     r15, rcx
0x18001ab9d  mov     [rsp+0A8h+var_60], rcx
0x18001aba2  mov     [rsp+0A8h+var_68], rdx
0x18001aba7  xorps   xmm0, xmm0
0x18001abaa  movups  [rsp+0A8h+var_48], xmm0
0x18001abaf  movups  [rsp+0A8h+var_38], xmm0
0x18001abb4  xor     ebx, ebx
0x18001abb6  mov     [rsp+0A8h+var_78], ebx
0x18001abba  cmp     ebx, 4
0x18001abbd  jnb     loc_18001ACBD
0x18001abc3  mov     [rsp+0A8h+var_88], 0
0x18001abcc  xor     r9d, r9d
0x18001abcf  xor     r8d, r8d
0x18001abd2  xor     edx, edx
0x18001abd4  xor     ecx, ecx
0x18001abd6  call    cs:__imp_DevObjCreateDeviceInfoList
0x18001abdc  mov     r14, rax
0x18001abdf  mov     [rsp+0A8h+var_70], rax
0x18001abe4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001abe8  jnz     loc_18001ACE2
0x18001abee  call    cs:__imp_GetLastError
0x18001abf4  mov     dword ptr [rsp+0A8h+var_88], eax
0x18001abf8  lea     rsi, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed [%d]"
0x18001abff  mov     r9, rsi
0x18001ac02  mov     r14d, 270h
0x18001ac08  mov     r8d, r14d
0x18001ac0b  lea     r15, aCdeviceGetdevi; "CDevice::GetDeviceInterfaceClassGuids"
0x18001ac12  mov     rdx, r15
0x18001ac15  mov     ecx, 2
0x18001ac1a  call    AslLogCallPrintf
0x18001ac1f  cmp     cs:EnableDevInvStdErrLog, 0
0x18001ac26  jz      short loc_18001AC80
0x18001ac28  mov     ecx, 2; Ix
0x18001ac2d  call    _o___acrt_iob_func_0
0x18001ac32  mov     rcx, rax; Stream
0x18001ac35  mov     r9d, r14d
0x18001ac38  mov     r8, r15
0x18001ac3b  lea     rdx, Format; "Error: %s, %u: "
0x18001ac42  call    fprintf
0x18001ac47  call    cs:__imp_GetLastError
0x18001ac4d  mov     ebx, eax
0x18001ac4f  mov     ecx, 2; Ix
0x18001ac54  call    _o___acrt_iob_func_0
0x18001ac59  mov     r8d, ebx
0x18001ac5c  mov     rdx, rsi; Format
0x18001ac5f  mov     rcx, rax; Stream
0x18001ac62  call    fprintf
0x18001ac67  mov     ecx, 2; Ix
0x18001ac6c  call    _o___acrt_iob_func_0
0x18001ac71  mov     rcx, rax; Stream
0x18001ac74  lea     rdx, asc_18011EAD8; "\n"
0x18001ac7b  call    fprintf
0x18001ac80  cmp     cs:g_DeviceMapLogFunction, 0
0x18001ac88  jz      short loc_18001ACA0
0x18001ac8a  call    cs:__imp_GetLastError
0x18001ac90  mov     r8d, eax
0x18001ac93  mov     rdx, rsi
0x18001ac96  mov     ecx, 2000000h
0x18001ac9b  call    TraceMessageCallback
0x18001aca0  call    cs:__imp_GetLastError
0x18001aca6  mov     dword ptr [rsp+0A8h+var_88], eax
0x18001acaa  mov     r9, rsi
0x18001acad  mov     r8, r14
0x18001acb0  mov     rdx, r15
0x18001acb3  mov     ecx, 1
0x18001acb8  call    AslLogCallPrintf
0x18001acbd  mov     rcx, [rsp+0A8h+var_28]
0x18001acc5  xor     rcx, rsp; StackCookie
0x18001acc8  call    __security_check_cookie
0x18001accd  mov     rbx, [rsp+0A8h+arg_10]
0x18001acd5  add     rsp, 90h
0x18001acdc  pop     r15
0x18001acde  pop     r14
0x18001ace0  pop     rsi
0x18001ace1  retn
0x18001ace2  movsxd  rax, ebx
0x18001ace5  add     rax, rax
0x18001ace8  lea     rcx, ?s_DeviceInterfaceClassGuids@CDevice@@2QBU_GUID@@B; _GUID const near * const CDevice::s_DeviceInterfaceClassGuids
0x18001acef  movups  xmm0, xmmword ptr [rcx+rax*8]
0x18001acf3  movdqu  [rsp+0A8h+var_58], xmm0
0x18001acf9  mov     [rsp+0A8h+var_80], 0
0x18001ad02  mov     [rsp+0A8h+var_88], 0
0x18001ad0b  mov     r9d, 12h
0x18001ad11  mov     r8, r15
0x18001ad14  lea     rdx, [rsp+0A8h+var_58]
0x18001ad19  mov     rcx, r14
0x18001ad1c  call    cs:__imp_DevObjGetClassDevs
0x18001ad22  test    eax, eax
0x18001ad24  jz      short loc_18001AD8C
0x18001ad26  mov     dword ptr [rsp+0A8h+var_48], 20h ; ' '
0x18001ad2e  lea     rax, [rsp+0A8h+var_48]
0x18001ad33  mov     [rsp+0A8h+var_88], rax
0x18001ad38  xor     r9d, r9d
0x18001ad3b  lea     r8, [rsp+0A8h+var_58]
0x18001ad40  xor     edx, edx
0x18001ad42  mov     rcx, r14
0x18001ad45  call    cs:__imp_DevObjEnumDeviceInterfaces
0x18001ad4b  test    eax, eax
0x18001ad4d  jz      short loc_18001AD8C
0x18001ad4f  mov     rdx, [rsi+8]
0x18001ad53  cmp     rdx, [rsi+10h]
0x18001ad57  jz      short loc_18001AD69
0x18001ad59  movups  xmm0, [rsp+0A8h+var_58]
0x18001ad5e  movdqu  xmmword ptr [rdx], xmm0
0x18001ad62  add     qword ptr [rsi+8], 10h
0x18001ad67  jmp     short loc_18001AD77
0x18001ad69  lea     r8, [rsp+0A8h+var_58]
0x18001ad6e  mov     rcx, rsi
0x18001ad71  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x18001ad76  nop
0x18001ad77  jmp     short loc_18001AD8C
0x18001ad79  mov     r14, [rsp+0A8h+var_70]
0x18001ad7e  mov     ebx, [rsp+0A8h+var_78]
0x18001ad82  mov     rsi, [rsp+0A8h+var_68]
0x18001ad87  mov     r15, [rsp+0A8h+var_60]
0x18001ad8c  mov     rcx, r14
0x18001ad8f  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18001ad95  inc     ebx
0x18001ad97  jmp     loc_18001ABB6
```
