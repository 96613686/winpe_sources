# PuRescanAdapters(void)

- ea: `0x1801a7120`
- end: `0x1801a753d`
- name: `?PuRescanAdapters@@YAJXZ`
- size: `1053`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180116fa0`

## callees

- `0x180006350`
- `0x1800298d0`
- `0x1801a3394`
- `0x1801a59d0`
- `0x1801a7120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a71aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a71fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a72d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a738b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a73fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a745a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a748d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a71aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a71fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a7273`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a72d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a738b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a73fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a745a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a748d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a731b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a7502`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a731b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801a7502`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a7478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a7478`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a7445`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801a7445`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a73e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801a73e7`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a71ec`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a7304`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a71ec`
- `DEVOBJ!DevObjGetClassDevs` at `0x1801a7304`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a7195`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a72c1`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a7195`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1801a72c1`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801a7363`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x1801a7363`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801a722b`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1801a722b`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a7299`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a74f1`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a7299`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1801a74f1`
- `CFGMGR32!CM_Reenumerate_DevNode_Ex` at `0x1801a7252`
- `CFGMGR32!CM_Reenumerate_DevNode_Ex` at `0x1801a7252`

## pseudocode

```c
__int64 PuRescanAdapters(void)
{
  signed int v0; // ebx
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v1; // r14
  int v2; // r13d
  int v3; // r12d
  __int64 v4; // rdi
  __int64 DeviceInfoList; // rax
  __int64 v6; // r15
  signed int v7; // eax
  signed int LastError; // eax
  unsigned int i; // esi
  int IsWinPE; // eax
  ULONG v11; // edx
  __int64 v12; // rax
  char *v13; // rsi
  unsigned int v14; // edi
  HANDLE ProcessHeap; // rax
  unsigned int v16; // edx
  signed int v17; // eax
  HANDLE FileW; // r15
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  int v22; // edx
  __int64 j; // rcx
  unsigned int v24; // eax
  struct _DO_DEVICE_INTERFACE_DETAIL_DATA *v26; // [rsp+40h] [rbp-69h] BYREF
  DWORD BytesReturned; // [rsp+48h] [rbp-61h] BYREF
  int v28; // [rsp+4Ch] [rbp-5Dh]
  __int128 v29; // [rsp+50h] [rbp-59h]
  __int64 v30; // [rsp+60h] [rbp-49h]
  __int128 v31; // [rsp+68h] [rbp-41h] BYREF
  __int128 v32; // [rsp+78h] [rbp-31h]
  __int128 v33; // [rsp+88h] [rbp-21h] BYREF
  DEVINST dnDevInst[4]; // [rsp+98h] [rbp-11h]
  __int128 v35; // [rsp+A8h] [rbp-1h]

  v28 = 1;
  v0 = 0;
  v1 = 0;
  BytesReturned = 0;
  v2 = -2147467259;
  v26 = 0;
  v3 = -2147467259;
  v30 = 0;
  v33 = 0;
  v4 = 0;
  *(_OWORD *)dnDevInst = 0;
  v35 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
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
          v33 = 0;
          LODWORD(v33) = 48;
          *(_OWORD *)dnDevInst = 0;
          v35 = 0;
          if ( !(unsigned int)DevObjEnumDeviceInfo(v6, i, &v33) )
            break;
          IsWinPE = PuIsWinPE();
          v11 = 4;
          if ( !IsWinPE )
            v11 = 6;
          if ( CM_Reenumerate_DevNode_Ex(dnDevInst[1], v11, 0) )
            *((_DWORD *)&v29 + v4) = -2147418113;
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
      *((_DWORD *)&v29 + v4) = LastError;
LABEL_20:
      DevObjDestroyDeviceInfoList(v6);
      goto LABEL_21;
    }
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    *((_DWORD *)&v29 + v4) = v7;
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
        PmHeapFree(ProcessHeap, v16, v1);
        v26 = 0;
      }
      v31 = 0;
      LODWORD(v31) = 32;
      v32 = 0;
      if ( !(unsigned int)DevObjEnumDeviceInterfaces(v13, 0, &GUID_DEVINTERFACE_STORAGEPORT, v14, &v31) )
        break;
      if ( (unsigned int)PuGetInterfaceDetailData(v13, (struct _DO_DEVICE_INTERFACE_DATA *)&v31, &v26) )
      {
        v1 = v26;
        if ( v26 == (struct _DO_DEVICE_INTERFACE_DETAIL_DATA *)-4LL )
        {
          ++v14;
        }
        else
        {
          FileW = CreateFileW((LPCWSTR)v26 + 2, 0x80000000, 3u, 0, 3u, 0, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          if ( FileW == (HANDLE)-1LL )
          {
            v19 = GetLastError();
            v0 = v19;
            if ( v19 > 0 )
              v0 = (unsigned __int16)v19 | 0x80070000;
          }
          else
          {
            if ( DeviceIoControl(FileW, 0x4101Cu, 0, 0, 0, 0, &BytesReturned, 0) )
            {
              v3 = 0;
            }
            else
            {
              v20 = GetLastError();
              v0 = v20;
              if ( v20 > 0 )
                v0 = (unsigned __int16)v20 | 0x80070000;
            }
            CloseHandle(FileW);
          }
          ++v14;
        }
      }
      else
      {
        v17 = GetLastError();
        v0 = v17;
        if ( v17 > 0 )
          v0 = (unsigned __int16)v17 | 0x80070000;
        v1 = v26;
        ++v14;
      }
    }
    v21 = GetLastError();
    if ( v21 != 259 )
    {
      if ( v21 > 0 )
        v0 = (unsigned __int16)v21 | 0x80070000;
      else
        v0 = v21;
    }
  }
  LOBYTE(v22) = v28;
  if ( v0 >= 0 )
    v0 = 0;
  for ( j = 0; j != 6; ++j )
  {
    v24 = *((_DWORD *)&v29 + j);
    v22 &= v24 >> 31;
  }
  if ( v22 )
    v0 = v29;
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
0x1801a7120  push    rbp
0x1801a7122  push    rbx
0x1801a7123  push    rsi
0x1801a7124  push    rdi
0x1801a7125  push    r12
0x1801a7127  push    r13
0x1801a7129  push    r14
0x1801a712b  push    r15
0x1801a712d  lea     rbp, [rsp-1Fh]
0x1801a7132  sub     rsp, 0C8h
0x1801a7139  mov     rax, cs:__security_cookie
0x1801a7140  xor     rax, rsp
0x1801a7143  mov     [rbp+57h+var_48], rax
0x1801a7147  xorps   xmm0, xmm0
0x1801a714a  mov     [rbp+57h+var_B4], 1
0x1801a7151  xor     ebx, ebx
0x1801a7153  xor     r14d, r14d
0x1801a7156  xor     eax, eax
0x1801a7158  mov     [rbp+57h+BytesReturned], ebx
0x1801a715b  mov     r13d, 80004005h
0x1801a7161  mov     [rbp+57h+var_C0], r14
0x1801a7165  mov     r12d, r13d
0x1801a7168  mov     [rbp+57h+var_A0], rax
0x1801a716c  movups  [rbp+57h+var_78], xmm0
0x1801a7170  xor     edi, edi
0x1801a7172  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a7176  movups  [rbp+57h+var_58], xmm0
0x1801a717a  movups  [rbp+57h+var_98], xmm0
0x1801a717e  movups  [rbp+57h+var_88], xmm0
0x1801a7182  movups  [rbp+57h+var_B0], xmm0
0x1801a7186  xor     r9d, r9d
0x1801a7189  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a718e  xor     r8d, r8d
0x1801a7191  xor     edx, edx
0x1801a7193  xor     ecx, ecx
0x1801a7195  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a719c  nop     dword ptr [rax+rax+00h]
0x1801a71a1  mov     r15, rax
0x1801a71a4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a71a8  jnz     short loc_1801A71CB
0x1801a71aa  call    cs:__imp_GetLastError
0x1801a71b1  nop     dword ptr [rax+rax+00h]
0x1801a71b6  test    eax, eax
0x1801a71b8  jle     short loc_1801A71C2
0x1801a71ba  movzx   eax, ax
0x1801a71bd  or      eax, 80070000h
0x1801a71c2  mov     dword ptr [rbp+rdi*4+57h+var_B0], eax
0x1801a71c6  jmp     loc_1801A72A5
0x1801a71cb  lea     rdx, ?g_pAdaptorGuids@@3PAPEBU_GUID@@A; _GUID const * near * g_pAdaptorGuids
0x1801a71d2  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rbx
0x1801a71d7  mov     rdx, [rdx+rdi*8]
0x1801a71db  mov     r9d, 2
0x1801a71e1  xor     r8d, r8d
0x1801a71e4  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a71e9  mov     rcx, r15
0x1801a71ec  call    cs:__imp_DevObjGetClassDevs
0x1801a71f3  nop     dword ptr [rax+rax+00h]
0x1801a71f8  test    eax, eax
0x1801a71fa  jnz     short loc_1801A720A
0x1801a71fc  call    cs:__imp_GetLastError
0x1801a7203  nop     dword ptr [rax+rax+00h]
0x1801a7208  jmp     short loc_1801A7286
0x1801a720a  xor     esi, esi
0x1801a720c  xorps   xmm0, xmm0
0x1801a720f  lea     r8, [rbp+57h+var_78]
0x1801a7213  movups  [rbp+57h+var_78], xmm0
0x1801a7217  mov     edx, esi
0x1801a7219  mov     dword ptr [rbp+57h+var_78], 30h ; '0'
0x1801a7220  mov     rcx, r15
0x1801a7223  movups  xmmword ptr [rbp+57h+dnDevInst], xmm0
0x1801a7227  movups  [rbp+57h+var_58], xmm0
0x1801a722b  call    cs:__imp_DevObjEnumDeviceInfo
0x1801a7232  nop     dword ptr [rax+rax+00h]
0x1801a7237  test    eax, eax
0x1801a7239  jz      short loc_1801A7273
0x1801a723b  call    ?PuIsWinPE@@YAHXZ; PuIsWinPE(void)
0x1801a7240  mov     ecx, [rbp+57h+dnDevInst+4]; dnDevInst
0x1801a7243  xor     r8d, r8d; hMachine
0x1801a7246  lea     edx, [r8+4]
0x1801a724a  test    eax, eax
0x1801a724c  jnz     short loc_1801A7252
0x1801a724e  lea     edx, [r8+6]; ulFlags
0x1801a7252  call    cs:__imp_CM_Reenumerate_DevNode_Ex
0x1801a7259  nop     dword ptr [rax+rax+00h]
0x1801a725e  test    eax, eax
0x1801a7260  jz      short loc_1801A726E
0x1801a7262  mov     dword ptr [rbp+rdi*4+57h+var_B0], 8000FFFFh
0x1801a726a  inc     esi
0x1801a726c  jmp     short loc_1801A720C
0x1801a726e  xor     r13d, r13d
0x1801a7271  jmp     short loc_1801A726A
0x1801a7273  call    cs:__imp_GetLastError
0x1801a727a  nop     dword ptr [rax+rax+00h]
0x1801a727f  cmp     eax, 103h
0x1801a7284  jz      short loc_1801A7296
0x1801a7286  test    eax, eax
0x1801a7288  jle     short loc_1801A7292
0x1801a728a  movzx   eax, ax
0x1801a728d  or      eax, 80070000h
0x1801a7292  mov     dword ptr [rbp+rdi*4+57h+var_B0], eax
0x1801a7296  mov     rcx, r15
0x1801a7299  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a72a0  nop     dword ptr [rax+rax+00h]
0x1801a72a5  inc     rdi
0x1801a72a8  cmp     rdi, 6
0x1801a72ac  jnz     loc_1801A7186
0x1801a72b2  xor     r9d, r9d
0x1801a72b5  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a72ba  xor     r8d, r8d
0x1801a72bd  xor     edx, edx
0x1801a72bf  xor     ecx, ecx
0x1801a72c1  call    cs:__imp_DevObjCreateDeviceInfoList
0x1801a72c8  nop     dword ptr [rax+rax+00h]
0x1801a72cd  mov     rsi, rax
0x1801a72d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a72d4  jnz     short loc_1801A72E7
0x1801a72d6  call    cs:__imp_GetLastError
0x1801a72dd  nop     dword ptr [rax+rax+00h]
0x1801a72e2  jmp     loc_1801A74B1
0x1801a72e7  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], rbx
0x1801a72ec  lea     rdx, GUID_DEVINTERFACE_STORAGEPORT
0x1801a72f3  mov     r9d, 12h
0x1801a72f9  mov     qword ptr [rsp+100h+dwCreationDisposition], rbx
0x1801a72fe  xor     r8d, r8d
0x1801a7301  mov     rcx, rsi
0x1801a7304  call    cs:__imp_DevObjGetClassDevs
0x1801a730b  nop     dword ptr [rax+rax+00h]
0x1801a7310  test    eax, eax
0x1801a7312  jz      short loc_1801A72D6
0x1801a7314  xor     edi, edi
0x1801a7316  test    r14, r14
0x1801a7319  jz      short loc_1801A7339
0x1801a731b  call    cs:__imp_GetProcessHeap
0x1801a7322  nop     dword ptr [rax+rax+00h]
0x1801a7327  mov     rcx, rax; void *
0x1801a732a  mov     r8, r14; void *
0x1801a732d  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a7332  xor     r14d, r14d
0x1801a7335  mov     [rbp+57h+var_C0], r14
0x1801a7339  xorps   xmm0, xmm0
0x1801a733c  lea     rax, [rbp+57h+var_98]
0x1801a7340  movups  [rbp+57h+var_98], xmm0
0x1801a7344  mov     r9d, edi
0x1801a7347  mov     dword ptr [rbp+57h+var_98], 20h ; ' '
0x1801a734e  lea     r8, GUID_DEVINTERFACE_STORAGEPORT
0x1801a7355  mov     qword ptr [rsp+100h+dwCreationDisposition], rax
0x1801a735a  xor     edx, edx
0x1801a735c  mov     rcx, rsi
0x1801a735f  movups  [rbp+57h+var_88], xmm0
0x1801a7363  call    cs:__imp_DevObjEnumDeviceInterfaces
0x1801a736a  nop     dword ptr [rax+rax+00h]
0x1801a736f  test    eax, eax
0x1801a7371  jz      loc_1801A748D
0x1801a7377  lea     r8, [rbp+57h+var_C0]; struct _DO_DEVICE_INTERFACE_DETAIL_DATA **
0x1801a737b  mov     rcx, rsi; void *
0x1801a737e  lea     rdx, [rbp+57h+var_98]; struct _DO_DEVICE_INTERFACE_DATA *
0x1801a7382  call    ?PuGetInterfaceDetailData@@YAHPEAXPEAU_DO_DEVICE_INTERFACE_DATA@@PEAPEAU_DO_DEVICE_INTERFACE_DETAIL_DATA@@@Z; PuGetInterfaceDetailData(void *,_DO_DEVICE_INTERFACE_DATA *,_DO_DEVICE_INTERFACE_DETAIL_DATA * *)
0x1801a7387  test    eax, eax
0x1801a7389  jnz     short loc_1801A73B1
0x1801a738b  call    cs:__imp_GetLastError
0x1801a7392  nop     dword ptr [rax+rax+00h]
0x1801a7397  mov     ebx, eax
0x1801a7399  test    eax, eax
0x1801a739b  jle     short loc_1801A73A6
0x1801a739d  movzx   ebx, ax
0x1801a73a0  or      ebx, 80070000h
0x1801a73a6  mov     r14, [rbp+57h+var_C0]
0x1801a73aa  inc     edi
0x1801a73ac  jmp     loc_1801A7316
0x1801a73b1  mov     r14, [rbp+57h+var_C0]
0x1801a73b5  lea     rcx, [r14+4]; lpFileName
0x1801a73b9  test    rcx, rcx
0x1801a73bc  jz      loc_1801A7486
0x1801a73c2  xor     r9d, r9d; lpSecurityAttributes
0x1801a73c5  mov     [rsp+100h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1801a73ce  mov     [rsp+100h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801a73d6  mov     edx, 80000000h; dwDesiredAccess
0x1801a73db  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1801a73e3  lea     r8d, [r9+3]; dwShareMode
0x1801a73e7  call    cs:__imp_CreateFileW
0x1801a73ee  nop     dword ptr [rax+rax+00h]
0x1801a73f3  mov     r15, rax
0x1801a73f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801a73fa  jnz     short loc_1801A741E
0x1801a73fc  call    cs:__imp_GetLastError
0x1801a7403  nop     dword ptr [rax+rax+00h]
0x1801a7408  mov     ebx, eax
0x1801a740a  test    eax, eax
0x1801a740c  jle     short loc_1801A7417
0x1801a740e  movzx   ebx, ax
0x1801a7411  or      ebx, 80070000h
0x1801a7417  inc     edi
0x1801a7419  jmp     loc_1801A7316
0x1801a741e  xor     ecx, ecx
0x1801a7420  lea     rax, [rbp+57h+BytesReturned]
0x1801a7424  mov     [rsp+100h+lpOverlapped], rcx; lpOverlapped
0x1801a7429  xor     r9d, r9d; nInBufferSize
0x1801a742c  mov     [rsp+100h+hTemplateFile], rax; lpBytesReturned
0x1801a7431  xor     r8d, r8d; lpInBuffer
0x1801a7434  mov     [rsp+100h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1801a7438  mov     edx, 4101Ch; dwIoControlCode
0x1801a743d  mov     qword ptr [rsp+100h+dwCreationDisposition], rcx; lpOutBuffer
0x1801a7442  mov     rcx, r15; hDevice
0x1801a7445  call    cs:__imp_DeviceIoControl
0x1801a744c  nop     dword ptr [rax+rax+00h]
0x1801a7451  test    eax, eax
0x1801a7453  jz      short loc_1801A745A
0x1801a7455  xor     r12d, r12d
0x1801a7458  jmp     short loc_1801A7475
0x1801a745a  call    cs:__imp_GetLastError
0x1801a7461  nop     dword ptr [rax+rax+00h]
0x1801a7466  mov     ebx, eax
0x1801a7468  test    eax, eax
0x1801a746a  jle     short loc_1801A7475
0x1801a746c  movzx   ebx, ax
0x1801a746f  or      ebx, 80070000h
0x1801a7475  mov     rcx, r15; hObject
0x1801a7478  call    cs:__imp_CloseHandle
0x1801a747f  nop     dword ptr [rax+rax+00h]
0x1801a7484  jmp     short loc_1801A7417
0x1801a7486  inc     edi
0x1801a7488  jmp     loc_1801A7316
0x1801a748d  call    cs:__imp_GetLastError
0x1801a7494  nop     dword ptr [rax+rax+00h]
0x1801a7499  cmp     eax, 103h
0x1801a749e  jz      short loc_1801A74B1
0x1801a74a0  test    eax, eax
0x1801a74a2  jg      short loc_1801A74A8
0x1801a74a4  mov     ebx, eax
0x1801a74a6  jmp     short loc_1801A74B1
0x1801a74a8  movzx   ebx, ax
0x1801a74ab  or      ebx, 80070000h
0x1801a74b1  mov     edx, [rbp+57h+var_B4]
0x1801a74b4  xor     eax, eax
0x1801a74b6  test    ebx, ebx
0x1801a74b8  cmovns  ebx, eax
0x1801a74bb  xor     ecx, ecx
0x1801a74bd  mov     eax, dword ptr [rbp+rcx*4+57h+var_B0]
0x1801a74c1  inc     rcx
0x1801a74c4  shr     eax, 1Fh
0x1801a74c7  and     edx, eax
0x1801a74c9  cmp     rcx, 6
0x1801a74cd  jnz     short loc_1801A74BD
0x1801a74cf  test    edx, edx
0x1801a74d1  cmovnz  ebx, dword ptr [rbp+57h+var_B0]
0x1801a74d5  test    r12d, r12d
0x1801a74d8  jns     short loc_1801A74E4
0x1801a74da  test    r13d, r13d
0x1801a74dd  mov     r12d, ebx
0x1801a74e0  cmovns  r12d, r13d
0x1801a74e4  lea     rax, [rsi-1]
0x1801a74e8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801a74ec  ja      short loc_1801A74FD
0x1801a74ee  mov     rcx, rsi
0x1801a74f1  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1801a74f8  nop     dword ptr [rax+rax+00h]
0x1801a74fd  test    r14, r14
0x1801a7500  jz      short loc_1801A7519
0x1801a7502  call    cs:__imp_GetProcessHeap
0x1801a7509  nop     dword ptr [rax+rax+00h]
0x1801a750e  mov     rcx, rax; void *
0x1801a7511  mov     r8, r14; void *
0x1801a7514  call    ?PmHeapFree@@YAHPEAXK0@Z; PmHeapFree(void *,ulong,void *)
0x1801a7519  mov     eax, r12d
0x1801a751c  mov     rcx, [rbp+57h+var_48]
0x1801a7520  xor     rcx, rsp; StackCookie
0x1801a7523  call    __security_check_cookie
0x1801a7528  add     rsp, 0C8h
0x1801a752f  pop     r15
0x1801a7531  pop     r14
0x1801a7533  pop     r13
0x1801a7535  pop     r12
0x1801a7537  pop     rdi
0x1801a7538  pop     rsi
0x1801a7539  pop     rbx
0x1801a753a  pop     rbp
0x1801a753b  retn
```
