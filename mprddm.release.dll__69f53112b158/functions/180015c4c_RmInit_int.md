# RmInit(int *)

- ea: `0x180015c4c`
- end: `0x180016123`
- name: `?RmInit@@YAKPEAH@Z`
- size: `1239`
- prototype: `unsigned int __fastcall(int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180015c4c`
- `0x180030684`
- `0x18003c4a0`
- `0x18003cc60`
- `0x18003d278`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180015ec9`
- `KERNEL32!MultiByteToWideChar` at `0x180015ec9`
- `KERNEL32!Sleep` at `0x180015d3b`
- `KERNEL32!Sleep` at `0x180015d3b`
- `KERNEL32!HeapAlloc` at `0x180015d21`
- `KERNEL32!HeapAlloc` at `0x180015d21`
- `KERNEL32!GetLastError` at `0x180015d7b`
- `KERNEL32!GetLastError` at `0x180015dc0`
- `KERNEL32!GetLastError` at `0x180015d7b`
- `KERNEL32!GetLastError` at `0x180015dc0`
- `KERNEL32!LeaveCriticalSection` at `0x180015fac`
- `KERNEL32!LeaveCriticalSection` at `0x180015fac`
- `KERNEL32!EnterCriticalSection` at `0x180015f7f`
- `KERNEL32!EnterCriticalSection` at `0x180015f7f`
- `KERNEL32!HeapFree` at `0x180015d04`
- `KERNEL32!HeapFree` at `0x1800160e4`
- `KERNEL32!HeapFree` at `0x180015d04`
- `KERNEL32!HeapFree` at `0x1800160e4`
- `rtutils!RouterLogEventW` at `0x180015daf`
- `rtutils!RouterLogEventW` at `0x180015df0`
- `rtutils!RouterLogEventW` at `0x1800160a1`
- `rtutils!RouterLogEventW` at `0x180015daf`
- `rtutils!RouterLogEventW` at `0x180015df0`
- `rtutils!RouterLogEventW` at `0x1800160a1`
- `rtutils!RouterLogEventStringW` at `0x180015e32`
- `rtutils!RouterLogEventStringW` at `0x180015f10`
- `rtutils!RouterLogEventStringW` at `0x180015e32`
- `rtutils!RouterLogEventStringW` at `0x180015f10`
- `rasman!RasPortOpen` at `0x180015e9b`
- `rasman!RasPortOpen` at `0x180015e9b`
- `rasman!RasPortEnum` at `0x180015cce`
- `rasman!RasPortEnum` at `0x180015cce`
- `sstpcfg!SetupSstpServerConfig` at `0x180015e7a`
- `sstpcfg!SetupSstpServerConfig` at `0x180015e7a`

## string_xrefs

- `0x180016014`: `DDMServiceInitialize: SetupSstpServerConfig failed. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RmInit(int *a1)
{
  char *v2; // r15
  int v3; // ebx
  DWORD v4; // esi
  DWORD v5; // edi
  unsigned int v6; // ecx
  DWORD LastError; // eax
  DWORD dwErrorCode; // eax
  unsigned int v9; // r12d
  char *v10; // r14
  __int64 v11; // rsi
  DWORD v12; // eax
  void (__fastcall ***v13)(_QWORD, __int64); // rbx
  __int64 v14; // rcx
  DdmDeviceTable *Instance; // rax
  __int64 v16; // r8
  SIZE_T dwBytes; // [rsp+48h] [rbp-C0h] BYREF
  void (__fastcall ***v19)(_QWORD, __int64); // [rsp+50h] [rbp-B8h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A8h] BYREF
  int *v22; // [rsp+68h] [rbp-A0h]
  char v23[16]; // [rsp+70h] [rbp-98h] BYREF
  int *v24; // [rsp+80h] [rbp-88h]
  int v25; // [rsp+88h] [rbp-80h]
  int v26; // [rsp+8Ch] [rbp-7Ch]
  WCHAR WideCharStr[20]; // [rsp+90h] [rbp-78h] BYREF
  int v28; // [rsp+B8h] [rbp-50h] BYREF
  char v29[2044]; // [rsp+BCh] [rbp-4Ch] BYREF

  v22 = a1;
  v21 = 0;
  v2 = 0;
  dwBytes = 0;
  v3 = 100;
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  *a1 = 0;
  v4 = 0;
  while ( 1 )
  {
    v5 = RasPortEnum(0, v2, (char *)&dwBytes + 4, &dwBytes);
    if ( v5 != 603 )
      break;
    if ( v2 )
      HeapFree(hHeap, 0, v2);
    v2 = (char *)HeapAlloc(hHeap, 8u, HIDWORD(dwBytes));
    if ( !v2 )
    {
      dwErrorCode = GetLastError();
      v5 = dwErrorCode;
      if ( dword_1800CF4E4 )
        RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, dwErrorCode);
      break;
    }
    Sleep(v4);
    v5 = 0;
    v4 += 100;
    if ( !--v3 )
      goto LABEL_7;
  }
  if ( v5 )
  {
    if ( dword_1800CF4E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E25u, 0, 0, v5, 0);
    goto LABEL_44;
  }
LABEL_7:
  v6 = 5;
  if ( (unsigned int)dwBytes >= 5 )
  {
    v6 = dwBytes;
    if ( (unsigned int)dwBytes > 0x11 )
      v6 = 17;
  }
  if ( !DdmDeviceTable::GetInstance(v6) || !DdmConnectionTable::GetInstance() )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( dword_1800CF4E4 )
      goto LABEL_43;
    goto LABEL_44;
  }
  v9 = 0;
  if ( !(_DWORD)dwBytes )
    goto LABEL_44;
  v10 = v2 + 8;
  v11 = -1;
  while ( (v10[24] & 0x65) == 0 )
  {
LABEL_36:
    ++v9;
    v10 += 216;
    if ( v9 >= (unsigned int)dwBytes )
      goto LABEL_44;
  }
  if ( *((_WORD *)v10 + 10) == 14 )
  {
    v12 = SetupSstpServerConfig();
    v5 = v12;
    if ( v12 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"DDMServiceInitialize: SetupSstpServerConfig failed. Error %d", v12);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          do
            ++v11;
          while ( *(_WORD *)&v29[2 * v11 - 4] );
          v24 = &v28;
          v25 = 2 * v11 + 2;
          v26 = 0;
          McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v16, 2, v23);
        }
      }
      goto LABEL_44;
    }
  }
  v5 = RasPortOpen(v10, &v21, 0);
  if ( v5 )
  {
    plpszSubStringArray = 0;
    MultiByteToWideChar(0, 0, v10, -1, WideCharStr, 17);
    plpszSubStringArray = WideCharStr;
    if ( dword_1800CF4E4 )
      RouterLogEventStringW(hLogHandle, 1u, 0x4E8Cu, 1u, &plpszSubStringArray, v5, 1u);
    v5 = 0;
    goto LABEL_36;
  }
  v13 = 0;
  v19 = 0;
  if ( (v10[24] & 0x45) == 0 )
  {
LABEL_33:
    if ( v13 && !_InterlockedDecrement((volatile signed __int32 *)v13 + 2) )
      (**v19)(v19, 1);
    goto LABEL_36;
  }
  DdmDeviceTable::GetInstance(0x11u);
  LastError = DdmDeviceTable::CreateNewDevice(v14, v21, v10 - 8, &v19);
  v5 = LastError;
  v13 = v19;
  if ( v19 )
  {
    Instance = DdmDeviceTable::GetInstance(0x11u);
    DdmDeviceTable::AddDevice(Instance);
    EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 2));
    if ( ((_DWORD)v13[17] & 0xFFFF0000) != 0x20000 )
      *v22 = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 2));
    goto LABEL_33;
  }
  if ( !dword_1800CF4E4 )
    goto LABEL_44;
LABEL_43:
  RouterLogEventW(hLogHandle, 1u, 0x4E88u, 0, 0, LastError);
LABEL_44:
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  return v5;
}

```

## disassembly

```asm
0x180015c4c  mov     rax, rsp
0x180015c4f  mov     [rax+10h], rbx
0x180015c53  mov     [rax+18h], rsi
0x180015c57  mov     [rax+20h], rdi
0x180015c5b  push    rbp
0x180015c5c  push    r12
0x180015c5e  push    r13
0x180015c60  push    r14
0x180015c62  push    r15
0x180015c64  lea     rbp, [rax-7E8h]
0x180015c6b  sub     rsp, 8C0h
0x180015c72  mov     rax, cs:__security_cookie
0x180015c79  xor     rax, rsp
0x180015c7c  mov     [rbp+7E0h+var_30], rax
0x180015c83  mov     rdi, rcx
0x180015c86  mov     [rsp+8E0h+var_880], rcx
0x180015c8b  xor     r13d, r13d
0x180015c8e  mov     [rsp+8E0h+var_888], r13
0x180015c93  mov     r15d, r13d
0x180015c96  mov     dword ptr [rsp+8E0h+dwBytes+4], r13d
0x180015c9b  mov     dword ptr [rsp+8E0h+dwBytes], r13d
0x180015ca0  lea     ebx, [r13+64h]
0x180015ca4  mov     [rbp+7E0h+var_830], r13d
0x180015ca8  xor     edx, edx; Val
0x180015caa  mov     r8d, 7FCh; Size
0x180015cb0  lea     rcx, [rbp+7E0h+var_82C]; void *
0x180015cb4  call    memset_0
0x180015cb9  mov     [rdi], r13d
0x180015cbc  mov     esi, r13d
0x180015cbf  lea     r9, [rsp+8E0h+dwBytes]
0x180015cc4  lea     r8, [rsp+8E0h+dwBytes+4]
0x180015cc9  mov     rdx, r15
0x180015ccc  xor     ecx, ecx
0x180015cce  call    cs:__imp_RasPortEnum
0x180015cd5  nop     dword ptr [rax+rax+00h]
0x180015cda  mov     edi, eax
0x180015cdc  mov     r12d, 4E88h
0x180015ce2  mov     r14d, 1
0x180015ce8  cmp     eax, 25Bh
0x180015ced  jnz     loc_180015DFC
0x180015cf3  test    r15, r15
0x180015cf6  jz      short loc_180015D10
0x180015cf8  mov     r8, r15; lpMem
0x180015cfb  xor     edx, edx; dwFlags
0x180015cfd  mov     rcx, cs:hHeap; hHeap
0x180015d04  call    cs:__imp_HeapFree
0x180015d0b  nop     dword ptr [rax+rax+00h]
0x180015d10  mov     r8d, dword ptr [rsp+8E0h+dwBytes+4]; dwBytes
0x180015d15  mov     edx, 8; dwFlags
0x180015d1a  mov     rcx, cs:hHeap; hHeap
0x180015d21  call    cs:__imp_HeapAlloc
0x180015d28  nop     dword ptr [rax+rax+00h]
0x180015d2d  mov     r15, rax
0x180015d30  test    rax, rax
0x180015d33  jz      loc_180015DC0
0x180015d39  mov     ecx, esi; dwMilliseconds
0x180015d3b  call    cs:__imp_Sleep
0x180015d42  nop     dword ptr [rax+rax+00h]
0x180015d47  mov     edi, r13d
0x180015d4a  add     esi, 64h ; 'd'
0x180015d4d  add     ebx, 0FFFFFFFFh
0x180015d50  jnz     loc_180015CBF
0x180015d56  mov     ebx, 11h
0x180015d5b  mov     eax, dword ptr [rsp+8E0h+dwBytes]
0x180015d5f  lea     ecx, [rbx-0Ch]
0x180015d62  cmp     eax, ecx
0x180015d64  jb      short loc_180015D6D
0x180015d66  mov     ecx, eax
0x180015d68  cmp     eax, ebx
0x180015d6a  cmova   ecx, ebx; unsigned int
0x180015d6d  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180015d72  test    rax, rax
0x180015d75  jnz     loc_180015E43
0x180015d7b  call    cs:__imp_GetLastError
0x180015d82  nop     dword ptr [rax+rax+00h]
0x180015d87  mov     edi, eax
0x180015d89  cmp     cs:dword_1800CF4E4, r13d
0x180015d90  jbe     loc_1800160D3
0x180015d96  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x180015d9a  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x180015d9f  xor     r9d, r9d; dwSubStringCount
0x180015da2  mov     r8d, r12d; dwMessageId
0x180015da5  mov     edx, r14d; dwEventType
0x180015da8  mov     rcx, cs:hLogHandle; hLogHandle
0x180015daf  call    cs:__imp_RouterLogEventW
0x180015db6  nop     dword ptr [rax+rax+00h]
0x180015dbb  jmp     loc_1800160D3
0x180015dc0  call    cs:__imp_GetLastError
0x180015dc7  nop     dword ptr [rax+rax+00h]
0x180015dcc  mov     edi, eax
0x180015dce  cmp     cs:dword_1800CF4E4, r13d
0x180015dd5  jbe     short loc_180015DFC
0x180015dd7  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x180015ddb  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x180015de0  xor     r9d, r9d; dwSubStringCount
0x180015de3  mov     r8d, r12d; dwMessageId
0x180015de6  mov     edx, r14d; dwEventType
0x180015de9  mov     rcx, cs:hLogHandle; hLogHandle
0x180015df0  call    cs:__imp_RouterLogEventW
0x180015df7  nop     dword ptr [rax+rax+00h]
0x180015dfc  test    edi, edi
0x180015dfe  jz      loc_180015D56
0x180015e04  cmp     cs:dword_1800CF4E4, r13d
0x180015e0b  jbe     loc_1800160D3
0x180015e11  mov     [rsp+8E0h+dwErrorIndex], r13d; dwErrorIndex
0x180015e16  mov     [rsp+8E0h+dwErrorCode], edi; dwErrorCode
0x180015e1a  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x180015e1f  xor     r9d, r9d; dwSubStringCount
0x180015e22  mov     r8d, 4E25h; dwMessageId
0x180015e28  mov     edx, r14d; dwEventType
0x180015e2b  mov     rcx, cs:hLogHandle; hLogHandle
0x180015e32  call    cs:__imp_RouterLogEventStringW
0x180015e39  nop     dword ptr [rax+rax+00h]
0x180015e3e  jmp     loc_1800160D3
0x180015e43  call    ?GetInstance@DdmConnectionTable@@SAPEAV1@XZ; DdmConnectionTable::GetInstance(void)
0x180015e48  test    rax, rax
0x180015e4b  jz      loc_180015D7B
0x180015e51  mov     r12d, r13d
0x180015e54  cmp     dword ptr [rsp+8E0h+dwBytes], r13d
0x180015e59  jbe     loc_1800160D3
0x180015e5f  lea     r14, [r15+8]
0x180015e63  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180015e67  test    byte ptr [r14+18h], 65h
0x180015e6c  jz      loc_180015FE5
0x180015e72  cmp     word ptr [r14+14h], 0Eh
0x180015e78  jnz     short loc_180015E90
0x180015e7a  call    cs:__imp_SetupSstpServerConfig
0x180015e81  nop     dword ptr [rax+rax+00h]
0x180015e86  mov     edi, eax
0x180015e88  test    eax, eax
0x180015e8a  jnz     loc_180015FFF
0x180015e90  xor     r8d, r8d
0x180015e93  lea     rdx, [rsp+8E0h+var_888]
0x180015e98  mov     rcx, r14
0x180015e9b  call    cs:__imp_RasPortOpen
0x180015ea2  nop     dword ptr [rax+rax+00h]
0x180015ea7  mov     edi, eax
0x180015ea9  test    eax, eax
0x180015eab  jz      short loc_180015F24
0x180015ead  mov     [rsp+8E0h+var_890], r13
0x180015eb2  mov     [rsp+8E0h+dwErrorCode], ebx; cchWideChar
0x180015eb6  lea     rax, [rbp+7E0h+WideCharStr]
0x180015eba  mov     [rsp+8E0h+plpszSubStringArray], rax; lpWideCharStr
0x180015ebf  mov     r9d, esi; cbMultiByte
0x180015ec2  mov     r8, r14; lpMultiByteStr
0x180015ec5  xor     edx, edx; dwFlags
0x180015ec7  xor     ecx, ecx; CodePage
0x180015ec9  call    cs:__imp_MultiByteToWideChar
0x180015ed0  nop     dword ptr [rax+rax+00h]
0x180015ed5  lea     rax, [rbp+7E0h+WideCharStr]
0x180015ed9  mov     [rsp+8E0h+var_890], rax
0x180015ede  cmp     cs:dword_1800CF4E4, r13d
0x180015ee5  jbe     short loc_180015F1C
0x180015ee7  mov     ecx, 1
0x180015eec  mov     [rsp+8E0h+dwErrorIndex], ecx; dwErrorIndex
0x180015ef0  mov     [rsp+8E0h+dwErrorCode], edi; dwErrorCode
0x180015ef4  lea     rax, [rsp+8E0h+var_890]
0x180015ef9  mov     [rsp+8E0h+plpszSubStringArray], rax; plpszSubStringArray
0x180015efe  mov     r9d, ecx; dwSubStringCount
0x180015f01  mov     r8d, 4E8Ch; dwMessageId
0x180015f07  mov     edx, ecx; dwEventType
0x180015f09  mov     rcx, cs:hLogHandle; hLogHandle
0x180015f10  call    cs:__imp_RouterLogEventStringW
0x180015f17  nop     dword ptr [rax+rax+00h]
0x180015f1c  mov     edi, r13d
0x180015f1f  jmp     loc_180015FE5
0x180015f24  mov     rbx, r13
0x180015f27  mov     [rsp+8E0h+var_898], rbx
0x180015f2c  test    byte ptr [r14+18h], 45h
0x180015f31  jz      loc_180015FBB
0x180015f37  mov     ecx, 11h; unsigned int
0x180015f3c  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180015f41  lea     r8, [r14-8]
0x180015f45  lea     r9, [rsp+8E0h+var_898]
0x180015f4a  mov     rdx, [rsp+8E0h+var_888]
0x180015f4f  call    ?CreateNewDevice@DdmDeviceTable@@QEAAKPEAXPEAU_RASMAN_PORT@@AEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::CreateNewDevice(void *,_RASMAN_PORT *,RasObjPtr<DdmDevice> &)
0x180015f54  mov     edi, eax
0x180015f56  mov     rbx, [rsp+8E0h+var_898]
0x180015f5b  test    rbx, rbx
0x180015f5e  jz      loc_18001607B
0x180015f64  mov     ecx, 11h; unsigned int
0x180015f69  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180015f6e  lea     rdx, [rsp+8E0h+var_898]
0x180015f73  mov     rcx, rax; this
0x180015f76  call    ?AddDevice@DdmDeviceTable@@QEAAKAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::AddDevice(RasObjPtr<DdmDevice> &)
0x180015f7b  lea     rcx, [rbx+10h]; lpCriticalSection
0x180015f7f  call    cs:__imp_EnterCriticalSection
0x180015f86  nop     dword ptr [rax+rax+00h]
0x180015f8b  mov     eax, [rbx+88h]
0x180015f91  and     eax, 0FFFF0000h
0x180015f96  cmp     eax, 20000h
0x180015f9b  jz      short loc_180015FA8
0x180015f9d  mov     rax, [rsp+8E0h+var_880]
0x180015fa2  mov     dword ptr [rax], 1
0x180015fa8  lea     rcx, [rbx+10h]; lpCriticalSection
0x180015fac  call    cs:__imp_LeaveCriticalSection
0x180015fb3  nop     dword ptr [rax+rax+00h]
0x180015fb8  xor     r13d, r13d
0x180015fbb  test    rbx, rbx
0x180015fbe  jz      short loc_180015FE0
0x180015fc0  mov     eax, esi
0x180015fc2  lock xadd [rbx+8], eax
0x180015fc7  add     eax, esi
0x180015fc9  jnz     short loc_180015FE0
0x180015fcb  mov     rcx, [rsp+8E0h+var_898]
0x180015fd0  mov     rax, [rcx]
0x180015fd3  mov     edx, 1
0x180015fd8  mov     rax, [rax]
0x180015fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe0  mov     ebx, 11h
0x180015fe5  inc     r12d
0x180015fe8  add     r14, 0D8h
0x180015fef  cmp     r12d, dword ptr [rsp+8E0h+dwBytes]
0x180015ff4  jb      loc_180015E67
0x180015ffa  jmp     loc_1800160D3
0x180015fff  test    cs:byte_1800CF404, 8
0x180016006  jz      loc_1800160D3
0x18001600c  mov     word ptr [rbp+7E0h+var_830], r13w
0x180016011  mov     r8d, eax
0x180016014  lea     rdx, aDdmserviceinit_21; "DDMServiceInitialize: SetupSstpServerCo"...
0x18001601b  lea     rcx, [rbp+7E0h+var_830]
0x18001601f  call    FormatRRASErrorString
0x180016024  test    cs:byte_1800CF404, 8
0x18001602b  jz      loc_1800160D3
0x180016031  lea     rax, [rbp+7E0h+var_830]
0x180016035  inc     rsi
0x180016038  cmp     [rax+rsi*2], r13w
0x18001603d  jnz     short loc_180016035
0x18001603f  lea     eax, ds:2[rsi*2]
0x180016046  lea     rcx, [rbp+7E0h+var_830]
0x18001604a  mov     [rsp+8E0h+var_868], rcx
0x18001604f  mov     [rbp+7E0h+var_860], eax
0x180016052  mov     [rbp+7E0h+var_85C], r13d
0x180016056  lea     rax, [rsp+8E0h+var_878]
0x18001605b  mov     [rsp+8E0h+plpszSubStringArray], rax
0x180016060  mov     r9d, 2
0x180016066  lea     rdx, RasDdmTraceError
0x18001606d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016074  call    McGenEventWrite_EventWriteTransfer
0x180016079  jmp     short loc_1800160D3
0x18001607b  cmp     cs:dword_1800CF4E4, r13d
0x180016082  jbe     short loc_1800160AE
0x180016084  mov     [rsp+8E0h+dwErrorCode], eax; dwErrorCode
0x180016088  mov     [rsp+8E0h+plpszSubStringArray], r13; plpszSubStringArray
0x18001608d  xor     r9d, r9d; dwSubStringCount
0x180016090  lea     edx, [r9+1]; dwEventType
0x180016094  mov     r8d, 4E88h; dwMessageId
0x18001609a  mov     rcx, cs:hLogHandle; hLogHandle
0x1800160a1  call    cs:__imp_RouterLogEventW
0x1800160a8  nop     dword ptr [rax+rax+00h]
0x1800160ad  nop
0x1800160ae  test    rbx, rbx
0x1800160b1  jz      short loc_1800160D3
0x1800160b3  mov     eax, esi
0x1800160b5  lock xadd [rbx+8], eax
0x1800160ba  add     eax, esi
0x1800160bc  jnz     short loc_1800160D3
0x1800160be  mov     rcx, [rsp+8E0h+var_898]
0x1800160c3  mov     rax, [rcx]
0x1800160c6  mov     edx, 1
0x1800160cb  mov     rax, [rax]
0x1800160ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160d3  test    r15, r15
0x1800160d6  jz      short loc_1800160F0
0x1800160d8  mov     r8, r15; lpMem
0x1800160db  xor     edx, edx; dwFlags
0x1800160dd  mov     rcx, cs:hHeap; hHeap
0x1800160e4  call    cs:__imp_HeapFree
0x1800160eb  nop     dword ptr [rax+rax+00h]
0x1800160f0  mov     eax, edi
0x1800160f2  mov     rcx, [rbp+7E0h+var_30]
0x1800160f9  xor     rcx, rsp; StackCookie
0x1800160fc  call    __security_check_cookie
0x180016101  lea     r11, [rsp+8E0h+var_20]
0x180016109  mov     rbx, [r11+38h]
0x18001610d  mov     rsi, [r11+40h]
0x180016111  mov     rdi, [r11+48h]
0x180016115  mov     rsp, r11
0x180016118  pop     r15
0x18001611a  pop     r14
0x18001611c  pop     r13
0x18001611e  pop     r12
0x180016120  pop     rbp
0x180016121  retn
```
