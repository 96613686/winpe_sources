# PuRescanAdapters(void)

- ea: `0x1801a1e94`
- end: `0x1801a2247`
- name: `?PuRescanAdapters@@YAJXZ`
- size: `947`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18011345c`

## callees

- `0x180006290`
- `0x18019e45c`
- `0x1801a0870`
- `0x1801a1e94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a20bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a219d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a1fc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a20bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a2176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a219d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a2067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a221e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a2067`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801a221e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a204f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2206`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a204f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a2206`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a218e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a218e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2167`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a2167`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a2115`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a2115`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a1f53`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a203e`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a1f53`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a203e`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a1f08`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a2007`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a1f08`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a2007`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801a209d`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801a209d`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801a1f88`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801a1f88`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a1fe5`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a21fb`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a1fe5`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a21fb`
- `CFGMGR32!CM_Reenumerate_DevNode_Ex` at `0x1801a1fa9`
- `CFGMGR32!CM_Reenumerate_DevNode_Ex` at `0x1801a1fa9`

## pseudocode

```c
__int64 PuRescanAdapters(void)
{
  signed int v0; // ebx
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v1; // rsi
  int v2; // r13d
  int v3; // r12d
  __int64 v4; // rdi
  __int64 DeviceInfoList; // rax
  __int64 v6; // r15
  signed int v7; // eax
  signed int LastError; // eax
  unsigned int i; // r14d
  int IsWinPE; // eax
  ULONG v11; // edx
  __int64 v12; // rax
  char *v13; // r14
  unsigned int v14; // edi
  HANDLE ProcessHeap; // rax
  signed int v16; // eax
  HANDLE FileW; // r15
  signed int v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  int v21; // edx
  __int64 j; // rcx
  unsigned int v23; // eax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v25; // [rsp+40h] [rbp-69h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-61h] BYREF
  int v27; // [rsp+4Ch] [rbp-5Dh]
  __int128 v28; // [rsp+50h] [rbp-59h]
  __int64 v29; // [rsp+60h] [rbp-49h]
  __int128 v30; // [rsp+68h] [rbp-41h] BYREF
  __int128 v31; // [rsp+78h] [rbp-31h]
  __int128 v32; // [rsp+88h] [rbp-21h] BYREF
  DEVINST dnDevInst[4]; // [rsp+98h] [rbp-11h]
  __int128 v34; // [rsp+A8h] [rbp-1h]

  v27 = 1;
  v0 = 0;
  v1 = 0;
  BytesReturned = 0;
  v2 = -2147467259;
  v25 = 0;
  v3 = -2147467259;
  v29 = 0;
  v32 = 0;
  v4 = 0;
  *(_OWORD *)dnDevInst = 0;
  v34 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  do
  {
    DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
    v6 = DeviceInfoList;
    if ( DeviceInfoList != -1 )
    {
      if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, *((_QWORD *)&g_pAdaptorGuids.Data1 + v4), 0, 2, 0, 0) )
      {
        for ( i = 0; ; ++i )
        {
          v32 = 0;
          LODWORD(v32) = 48;
          *(_OWORD *)dnDevInst = 0;
          v34 = 0;
          if ( !(unsigned int)DevObjEnumDeviceInfo(v6, i, &v32) )
            break;
          IsWinPE = PuIsWinPE();
          v11 = 4;
          if ( !IsWinPE )
            v11 = 6;
          if ( CM_Reenumerate_DevNode_Ex(dnDevInst[1], v11, 0) )
            *((_DWORD *)&v28 + v4) = -2147418113;
          else
            v2 = 0;
        }
        LastError = GetLastError();
        if ( LastError == 259 )
          goto LABEL_20;
      }
      else
      {
        LastError = GetLastError();
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *((_DWORD *)&v28 + v4) = LastError;
LABEL_20:
      DevObjDestroyDeviceInfoList(v6);
      goto LABEL_21;
    }
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    *((_DWORD *)&v28 + v4) = v7;
LABEL_21:
    ++v4;
  }
  while ( v4 != 6 );
  v12 = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v13 = (char *)v12;
  if ( v12 == -1 || !(unsigned int)DevObjGetClassDevs(v12, &GUID_DEVINTERFACE_STORAGEPORT, 0, 18, 0, 0) )
  {
    GetLastError();
  }
  else
  {
    v14 = 0;
    while ( 1 )
    {
      if ( v1 )
      {
        ProcessHeap = GetProcessHeap();
        if ( ProcessHeap )
          HeapFree(ProcessHeap, 0, v1);
        v25 = 0;
      }
      v30 = 0;
      LODWORD(v30) = 32;
      v31 = 0;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v13, 0, &GUID_DEVINTERFACE_STORAGEPORT, v14, &v30) )
        break;
      if ( (unsigned int)PuGetInterfaceDetailData(v13, (struct _DO_DEVICE_INTERFACE_DATA *)&v30, &v25) )
      {
        v1 = v25;
        if ( v25 == (struct _DO_DEVICE_INTERFACE_DETAIL_DATA *)-4LL )
        {
          ++v14;
        }
        else
        {
          FileW = CreateFileW((LPCWSTR)v25 + 2, 0x80000000, 3u, 0, 3u, 0, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          if ( FileW == (HANDLE)-1LL )
          {
            v18 = GetLastError();
            v0 = v18;
            if ( v18 > 0 )
              v0 = (unsigned __int16)v18 | 0x80070000;
          }
          else
          {
            if ( DeviceIoControl(FileW, 0x4101Cu, 0, 0, 0, 0, &BytesReturned, 0) )
            {
              v3 = 0;
            }
            else
            {
              v19 = GetLastError();
              v0 = v19;
              if ( v19 > 0 )
                v0 = (unsigned __int16)v19 | 0x80070000;
            }
            CloseHandle(FileW);
          }
          ++v14;
        }
      }
      else
      {
        v16 = GetLastError();
        v0 = v16;
        if ( v16 > 0 )
          v0 = (unsigned __int16)v16 | 0x80070000;
        v1 = v25;
        ++v14;
      }
    }
    v20 = GetLastError();
    if ( v20 != 259 )
    {
      if ( v20 > 0 )
        v0 = (unsigned __int16)v20 | 0x80070000;
      else
        v0 = v20;
    }
  }
  LOBYTE(v21) = v27;
  if ( v0 >= 0 )
    v0 = 0;
  for ( j = 0; j != 6; ++j )
  {
    v23 = *((_DWORD *)&v28 + j);
    v21 &= v23 >> 31;
  }
  if ( v21 )
    v0 = v28;
  if ( v3 < 0 )
  {
    v3 = v0;
    if ( v2 >= 0 )
      v3 = v2;
  }
  if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    DevObjDestroyDeviceInfoList(v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1801a1e94  push    rbp
0x1801a1e96  push    rbx
0x1801a1e97  push    rsi
0x1801a1e98  push    rdi
0x1801a1e99  push    r12
0x1801a1e9b  push    r13
0x1801a1e9d  push    r14
0x1801a1e9f  push    r15
0x1801a1ea1  lea     rbp, [rsp-1Fh]
0x1801a1ea6  sub     rsp, 0C8h
0x1801a1ead  mov     rax, cs:__security_cookie
0x1801a1eb4  xor     rax, rsp
0x1801a1eb7  mov     [rbp+57h+var_48], rax
0x1801a1ebb  xorps   xmm0, xmm0
0x1801a1ebe  mov     [rbp+57h+var_B4], 1
0x1801a1ec5  xor     ebx, ebx
0x1801a1ec7  xor     esi, esi
0x1801a1ec9  xor     eax, eax
0x1801a1ecb  mov     [rbp+57h+BytesReturned], ebx
0x1801a1ece  mov     r13d, 80004005h
0x1801a1ed4  mov     [rbp+57h+var_C0], rsi
0x1801a1ed8  mov     r12d, r13d
0x1801a1edb  mov     [rbp+57h+var_A0], rax
0x1801a1edf  movups  [rbp+57h+var_78], xmm0
0x1801a1ee3  xor     edi, edi
0x1801a1ee5  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a1ee9  movups  [rbp+57h+var_58], xmm0
0x1801a1eed  movups  [rbp+57h+var_98], xmm0
0x1801a1ef1  movups  [rbp+57h+var_88], xmm0
0x1801a1ef5  movups  [rbp+57h+var_B0], xmm0
0x1801a1ef9  xor     r9d, r9d
0x1801a1efc  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a1f01  xor     r8d, r8d
0x1801a1f04  xor     edx, edx
0x1801a1f06  xor     ecx, ecx
0x1801a1f08  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a1f0e  mov     r15, rax
0x1801a1f11  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a1f15  jnz     short loc_1801A1F32
0x1801a1f17  call    cs:__imp_GetLastError
0x1801a1f1d  test    eax, eax
0x1801a1f1f  jle     short loc_1801A1F29
0x1801a1f21  movzx   eax, ax
0x1801a1f24  or      eax, 80070000h
0x1801a1f29  mov     dword ptr [rbp+rdi*4+57h+var_B0], eax
0x1801a1f2d  jmp     loc_1801A1FEB
0x1801a1f32  lea     rdx, ?g_pAdaptorGuids@@3PAPEBU_GUID@@A; _GUID const * near * g_pAdaptorGuids
0x1801a1f39  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rbx
0x1801a1f3e  mov     rdx, [rdx+rdi*8]
0x1801a1f42  mov     r9d, 2
0x1801a1f48  xor     r8d, r8d
0x1801a1f4b  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a1f50  mov     rcx, r15
0x1801a1f53  call    cs:__imp_DevObjGetClassDevs
0x1801a1f59  test    eax, eax
0x1801a1f5b  jnz     short loc_1801A1F65
0x1801a1f5d  call    cs:__imp_GetLastError
0x1801a1f63  jmp     short loc_1801A1FD2
0x1801a1f65  xor     r14d, r14d
0x1801a1f68  xorps   xmm0, xmm0
0x1801a1f6b  lea     r8, [rbp+57h+var_78]
0x1801a1f6f  movups  [rbp+57h+var_78], xmm0
0x1801a1f73  mov     edx, r14d
0x1801a1f76  mov     dword ptr [rbp+57h+var_78], 30h ; '0'
0x1801a1f7d  mov     rcx, r15
0x1801a1f80  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a1f84  movups  [rbp+57h+var_58], xmm0
0x1801a1f88  call    cs:__imp_DevObjEnumDeviceInfo
0x1801a1f8e  test    eax, eax
0x1801a1f90  jz      short loc_1801A1FC5
0x1801a1f92  call    ?PuIsWinPE@@YAHXZ; PuIsWinPE(void)
0x1801a1f97  mov     ecx, [rbp+57h+dnDevInst+4]; dnDevInst
0x1801a1f9a  xor     r8d, r8d; hMachine
0x1801a1f9d  lea     edx, [r8+4]
0x1801a1fa1  test    eax, eax
0x1801a1fa3  jnz     short loc_1801A1FA9
0x1801a1fa5  lea     edx, [r8+6]; ulFlags
0x1801a1fa9  call    cs:__imp_CM_Reenumerate_DevNode_Ex
0x1801a1faf  test    eax, eax
0x1801a1fb1  jz      short loc_1801A1FC0
0x1801a1fb3  mov     dword ptr [rbp+rdi*4+57h+var_B0], 8000FFFFh
0x1801a1fbb  inc     r14d
0x1801a1fbe  jmp     short loc_1801A1F68
0x1801a1fc0  xor     r13d, r13d
0x1801a1fc3  jmp     short loc_1801A1FBB
0x1801a1fc5  call    cs:__imp_GetLastError
0x1801a1fcb  cmp     eax, 103h
0x1801a1fd0  jz      short loc_1801A1FE2
0x1801a1fd2  test    eax, eax
0x1801a1fd4  jle     short loc_1801A1FDE
0x1801a1fd6  movzx   eax, ax
0x1801a1fd9  or      eax, 80070000h
0x1801a1fde  mov     dword ptr [rbp+rdi*4+57h+var_B0], eax
0x1801a1fe2  mov     rcx, r15
0x1801a1fe5  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a1feb  inc     rdi
0x1801a1fee  cmp     rdi, 6
0x1801a1ff2  jnz     loc_1801A1EF9
0x1801a1ff8  xor     r9d, r9d
0x1801a1ffb  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a2000  xor     r8d, r8d
0x1801a2003  xor     edx, edx
0x1801a2005  xor     ecx, ecx
0x1801a2007  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a200d  mov     r14, rax
0x1801a2010  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a2014  jnz     short loc_1801A2021
0x1801a2016  call    cs:__imp_GetLastError
0x1801a201c  jmp     loc_1801A21BB
0x1801a2021  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rbx
0x1801a2026  lea     rdx, GUID_DEVINTERFACE_STORAGEPORT
0x1801a202d  mov     r9d, 12h
0x1801a2033  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a2038  xor     r8d, r8d
0x1801a203b  mov     rcx, r14
0x1801a203e  call    cs:__imp_DevObjGetClassDevs
0x1801a2044  test    eax, eax
0x1801a2046  jz      short loc_1801A2016
0x1801a2048  xor     edi, edi
0x1801a204a  test    rsi, rsi
0x1801a204d  jz      short loc_1801A2073
0x1801a204f  call    cs:__imp_GetProcessHeap
0x1801a2055  test    rax, rax
0x1801a2058  jz      short loc_1801A206D
0x1801a205a  test    rsi, rsi
0x1801a205d  jz      short loc_1801A206D
0x1801a205f  mov     r8, rsi; lpMem
0x1801a2062  xor     edx, edx; dwFlags
0x1801a2064  mov     rcx, rax; hHeap
0x1801a2067  call    cs:__imp_HeapFree
0x1801a206d  xor     esi, esi
0x1801a206f  mov     [rbp+57h+var_C0], rsi
0x1801a2073  xorps   xmm0, xmm0
0x1801a2076  lea     rax, [rbp+57h+var_98]
0x1801a207a  movups  [rbp+57h+var_98], xmm0
0x1801a207e  mov     r9d, edi
0x1801a2081  mov     dword ptr [rbp+57h+var_98], 20h ; ' '
0x1801a2088  lea     r8, GUID_DEVINTERFACE_STORAGEPORT
0x1801a208f  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1801a2094  xor     edx, edx
0x1801a2096  mov     rcx, r14
0x1801a2099  movups  [rbp+57h+var_88], xmm0
0x1801a209d  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1801a20a3  test    eax, eax
0x1801a20a5  jz      loc_1801A219D
0x1801a20ab  lea     r8, [rbp+57h+var_C0]; struct _DO_DEVICE_INTERFACE_DETAIL_DATA **
0x1801a20af  mov     rcx, r14; void *
0x1801a20b2  lea     rdx, [rbp+57h+var_98]; struct _DO_DEVICE_INTERFACE_DATA *
0x1801a20b6  call    ?PuGetInterfaceDetailData@@YAHPEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@@Z; PuGetInterfaceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *)
0x1801a20bb  test    eax, eax
0x1801a20bd  jnz     short loc_1801A20DF
0x1801a20bf  call    cs:__imp_GetLastError
0x1801a20c5  mov     ebx, eax
0x1801a20c7  test    eax, eax
0x1801a20c9  jle     short loc_1801A20D4
0x1801a20cb  movzx   ebx, ax
0x1801a20ce  or      ebx, 80070000h
0x1801a20d4  mov     rsi, [rbp+57h+var_C0]
0x1801a20d8  inc     edi
0x1801a20da  jmp     loc_1801A204A
0x1801a20df  mov     rsi, [rbp+57h+var_C0]
0x1801a20e3  lea     rcx, [rsi+4]; lpFileName
0x1801a20e7  test    rcx, rcx
0x1801a20ea  jz      loc_1801A2196
0x1801a20f0  xor     r9d, r9d; lpSecurityAttributes
0x1801a20f3  mov     [rsp+100h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1801a20fc  mov     [rsp+100h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801a2104  mov     edx, 80000000h; dwDesiredAccess
0x1801a2109  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1801a2111  lea     r8d, [r9+3]; dwShareMode
0x1801a2115  call    cs:__imp_CreateFileW
0x1801a211b  mov     r15, rax
0x1801a211e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a2122  jnz     short loc_1801A2140
0x1801a2124  call    cs:__imp_GetLastError
0x1801a212a  mov     ebx, eax
0x1801a212c  test    eax, eax
0x1801a212e  jle     short loc_1801A2139
0x1801a2130  movzx   ebx, ax
0x1801a2133  or      ebx, 80070000h
0x1801a2139  inc     edi
0x1801a213b  jmp     loc_1801A204A
0x1801a2140  xor     ecx, ecx
0x1801a2142  lea     rax, [rbp+57h+BytesReturned]
0x1801a2146  mov     [rsp+100h+lpOverlapped], rcx; lpOverlapped
0x1801a214b  xor     r9d, r9d; nInBufferSize
0x1801a214e  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x1801a2153  xor     r8d, r8d; lpInBuffer
0x1801a2156  mov     [rsp+100h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1801a215a  mov     edx, 4101Ch; dwIoControlCode
0x1801a215f  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx; lpOutBuffer
0x1801a2164  mov     rcx, r15; hDevice
0x1801a2167  call    cs:__imp_DeviceIoControl
0x1801a216d  test    eax, eax
0x1801a216f  jz      short loc_1801A2176
0x1801a2171  xor     r12d, r12d
0x1801a2174  jmp     short loc_1801A218B
0x1801a2176  call    cs:__imp_GetLastError
0x1801a217c  mov     ebx, eax
0x1801a217e  test    eax, eax
0x1801a2180  jle     short loc_1801A218B
0x1801a2182  movzx   ebx, ax
0x1801a2185  or      ebx, 80070000h
0x1801a218b  mov     rcx, r15; hObject
0x1801a218e  call    cs:__imp_CloseHandle
0x1801a2194  jmp     short loc_1801A2139
0x1801a2196  inc     edi
0x1801a2198  jmp     loc_1801A204A
0x1801a219d  call    cs:__imp_GetLastError
0x1801a21a3  cmp     eax, 103h
0x1801a21a8  jz      short loc_1801A21BB
0x1801a21aa  test    eax, eax
0x1801a21ac  jg      short loc_1801A21B2
0x1801a21ae  mov     ebx, eax
0x1801a21b0  jmp     short loc_1801A21BB
0x1801a21b2  movzx   ebx, ax
0x1801a21b5  or      ebx, 80070000h
0x1801a21bb  mov     edx, [rbp+57h+var_B4]
0x1801a21be  xor     eax, eax
0x1801a21c0  test    ebx, ebx
0x1801a21c2  cmovns  ebx, eax
0x1801a21c5  xor     ecx, ecx
0x1801a21c7  mov     eax, dword ptr [rbp+rcx*4+57h+var_B0]
0x1801a21cb  inc     rcx
0x1801a21ce  shr     eax, 1Fh
0x1801a21d1  and     edx, eax
0x1801a21d3  cmp     rcx, 6
0x1801a21d7  jnz     short loc_1801A21C7
0x1801a21d9  test    edx, edx
0x1801a21db  cmovnz  ebx, dword ptr [rbp+57h+var_B0]
0x1801a21df  test    r12d, r12d
0x1801a21e2  jns     short loc_1801A21EE
0x1801a21e4  test    r13d, r13d
0x1801a21e7  mov     r12d, ebx
0x1801a21ea  cmovns  r12d, r13d
0x1801a21ee  lea     rax, [r14-1]
0x1801a21f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801a21f6  ja      short loc_1801A2201
0x1801a21f8  mov     rcx, r14
0x1801a21fb  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a2201  test    rsi, rsi
0x1801a2204  jz      short loc_1801A2224
0x1801a2206  call    cs:__imp_GetProcessHeap
0x1801a220c  test    rax, rax
0x1801a220f  jz      short loc_1801A2224
0x1801a2211  test    rsi, rsi
0x1801a2214  jz      short loc_1801A2224
0x1801a2216  mov     r8, rsi; lpMem
0x1801a2219  xor     edx, edx; dwFlags
0x1801a221b  mov     rcx, rax; hHeap
0x1801a221e  call    cs:__imp_HeapFree
0x1801a2224  mov     eax, r12d
0x1801a2227  mov     rcx, [rbp+57h+var_48]
0x1801a222b  xor     rcx, rsp; StackCookie
0x1801a222e  call    __security_check_cookie
0x1801a2233  add     rsp, 0C8h
0x1801a223a  pop     r15
0x1801a223c  pop     r14
0x1801a223e  pop     r13
0x1801a2240  pop     r12
0x1801a2242  pop     rdi
0x1801a2243  pop     rsi
0x1801a2244  pop     rbx
0x1801a2245  pop     rbp
0x1801a2246  retn
```
