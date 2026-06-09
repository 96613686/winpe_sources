# DevUtilsGetCriticalDeviceIdList

- ea: `0x18000973c`
- end: `0x180009be9`
- name: `DevUtilsGetCriticalDeviceIdList`
- size: `1197`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001da8`

## callees

- `0x18000973c`
- `0x180009e08`
- `0x180009f1c`
- `0x18000a1a0`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1800097c2`
- `ntdll!NtQuerySystemInformation` at `0x1800097c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009bbd`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18000981d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_List_SizeW` at `0x18000981d`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18000987a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_ListW` at `0x18000987a`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000990c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009ae3`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x18000990c`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009ae3`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009b2a`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180009b2a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800098c6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x1800098c6`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009943`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009abc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009943`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180009abc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a15`
- `KERNEL32!CompareStringOrdinal` at `0x180009971`
- `KERNEL32!CompareStringOrdinal` at `0x180009971`
- `KERNEL32!HeapFree` at `0x18000983c`
- `KERNEL32!HeapFree` at `0x180009b84`
- `KERNEL32!HeapFree` at `0x180009b9e`
- `KERNEL32!HeapFree` at `0x180009bb5`
- `KERNEL32!HeapFree` at `0x18000983c`
- `KERNEL32!HeapFree` at `0x180009b84`
- `KERNEL32!HeapFree` at `0x180009b9e`
- `KERNEL32!HeapFree` at `0x180009bb5`
- `KERNEL32!HeapAlloc` at `0x180009853`
- `KERNEL32!HeapAlloc` at `0x180009853`
- `KERNEL32!DeviceIoControl` at `0x1800099f0`
- `KERNEL32!DeviceIoControl` at `0x1800099f0`
- `KERNEL32!CreateFileW` at `0x1800099a0`
- `KERNEL32!CreateFileW` at `0x1800099a0`

## pseudocode

```c
__int64 DevUtilsGetCriticalDeviceIdList()
{
  int v0; // esi
  const WCHAR *v1; // r12
  WCHAR *v2; // r15
  __int64 v3; // r13
  int v4; // r14d
  GUID *v5; // rbx
  CONFIGRET Device_Interface_List_SizeW; // eax
  WCHAR *v7; // rax
  const WCHAR *v8; // rdi
  HANDLE FileW; // rax
  void *v10; // rbx
  __int64 v11; // rcx
  BYTE *v12; // r8
  __int64 v13; // rdx
  BYTE *v14; // rax
  BYTE *v15; // rcx
  DWORD v16; // eax
  DWORD v17; // ebx
  __int64 v18; // rax
  LPVOID *v19; // rdi
  unsigned int v20; // esi
  DWORD v21; // eax
  unsigned int i; // r14d
  ULONG PropertyBufferSize; // [rsp+40h] [rbp-C0h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-BCh] BYREF
  DEVNODE pdnDevInst; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pulLen; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ReturnLength; // [rsp+54h] [rbp-ACh] BYREF
  DWORD BytesReturned; // [rsp+58h] [rbp-A8h] BYREF
  int v31; // [rsp+5Ch] [rbp-A4h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-98h] BYREF
  __int128 OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+80h] [rbp-80h]
  WCHAR v36[200]; // [rsp+90h] [rbp-70h] BYREF
  _WORD SystemInformation[4]; // [rsp+220h] [rbp+120h] BYREF
  const WCHAR *v38; // [rsp+228h] [rbp+128h]
  WCHAR PropertyBuffer[200]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR v40[264]; // [rsp+5D0h] [rbp+4D0h] BYREF

  v0 = 0;
  pulLen = 0;
  pdnDevInst = 0;
  PropertyType = 0;
  PropertyBufferSize = 0;
  v35 = 0;
  v1 = 0;
  BytesReturned = 0;
  v2 = 0;
  lpMem = 0;
  OutBuffer = 0;
  v28 = 0;
  v3 = 0;
  v33 = 0;
  v31 = 0;
  ReturnLength = 536;
  if ( NtQuerySystemInformation(MaxSystemInfoClass, SystemInformation, 0x218u, &ReturnLength) >= 0
    && (unsigned __int64)SystemInformation[0] + 2 <= SystemInformation[1] )
  {
    v38[(unsigned __int64)SystemInformation[0] >> 1] = 0;
    v1 = v38;
  }
  v4 = 0;
LABEL_5:
  v5 = (GUID *)&qword_180011118[2 * v4];
  while ( 1 )
  {
    Device_Interface_List_SizeW = CM_Get_Device_Interface_List_SizeW(&pulLen, v5, 0, 1u);
    if ( Device_Interface_List_SizeW )
      goto LABEL_52;
    if ( v2 )
      HeapFree(hHeap, 0, v2);
    v7 = (WCHAR *)HeapAlloc(hHeap, 0, 2 * pulLen);
    v2 = v7;
    if ( !v7 )
      break;
    Device_Interface_List_SizeW = CM_Get_Device_Interface_ListW(v5, 0, v7, pulLen, 1u);
    if ( Device_Interface_List_SizeW != 26 )
    {
      if ( Device_Interface_List_SizeW )
        goto LABEL_52;
      v8 = v2;
      if ( *v2 )
      {
        while ( 2 )
        {
          PropertyBufferSize = 400;
          if ( !CM_Get_Device_Interface_PropertyW(
                  v8,
                  &DEVPKEY_Device_InstanceId,
                  &PropertyType,
                  (PBYTE)PropertyBuffer,
                  &PropertyBufferSize,
                  0)
            && PropertyType == 18
            && PropertyBufferSize >= 2 )
          {
            if ( v4 == 1
              && v1
              && !CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 1u)
              && (PropertyBufferSize = 520,
                  !CM_Get_DevNode_PropertyW(
                     pdnDevInst,
                     &DEVPKEY_Device_PDOName,
                     &PropertyType,
                     (PBYTE)v40,
                     &PropertyBufferSize,
                     0))
              && PropertyType == 18
              && PropertyBufferSize >= 2
              && CompareStringOrdinal(v40, -1, v1, -1, 1) == 2 )
            {
LABEL_31:
              v11 = 2147483646;
              v12 = (BYTE *)PropertyBuffer;
              v13 = 200;
              v14 = (BYTE *)v36;
              do
              {
                if ( !v11 )
                  break;
                if ( !*(_WORD *)v12 )
                  break;
                *(_WORD *)v14 = *(_WORD *)v12;
                v12 += 2;
                v14 += 2;
                --v11;
                --v13;
              }
              while ( v13 );
              v15 = v14 - 2;
              if ( v13 )
                v15 = v14;
              *(_WORD *)v15 = 0;
              while ( !CM_Locate_DevNodeW(&pdnDevInst, v36, 1u) )
              {
                v16 = pSetupAppendToStringArray(&lpMem, &v28, v36);
                v17 = v16;
                if ( v16 != 183 && v16 )
                  goto LABEL_54;
                PropertyBufferSize = 400;
                if ( CM_Get_DevNode_PropertyW(
                       pdnDevInst,
                       &DEVPKEY_Device_Parent,
                       &PropertyType,
                       (PBYTE)v36,
                       &PropertyBufferSize,
                       0)
                  || PropertyType != 18
                  || PropertyBufferSize < 2 )
                {
                  break;
                }
              }
            }
            else
            {
              FileW = CreateFileW(v8, 0x80000000, 3u, 0, 3u, 0, 0);
              v10 = FileW;
              if ( FileW != (HANDLE)-1LL )
              {
                v35 = 0;
                OutBuffer = 0;
                if ( DeviceIoControl(FileW, 0x700010u, 0, 0, &OutBuffer, 0x18u, &BytesReturned, 0)
                  && (SDWORD2(OutBuffer) > 0 || SHIDWORD(OutBuffer) > 0 || (int)v35 > 0) )
                {
                  v0 = 1;
                }
                CloseHandle(v10);
                if ( v0 )
                {
                  v0 = 0;
                  goto LABEL_31;
                }
                v0 = 0;
              }
            }
          }
          v18 = -1;
          do
            ++v18;
          while ( v8[v18] );
          v8 += v18 + 1;
          if ( !*v8 )
            break;
          continue;
        }
      }
      if ( (unsigned int)++v4 >= 2 )
        goto LABEL_53;
      goto LABEL_5;
    }
  }
  Device_Interface_List_SizeW = 2;
LABEL_52:
  v17 = CM_MapCrToWin32Err(Device_Interface_List_SizeW, 0xDu);
  if ( !v17 )
  {
LABEL_53:
    v19 = (LPVOID *)lpMem;
    v20 = v28;
    v21 = pSetupStringArrayToMultiSz(lpMem, v28, &v33, &v31);
    v3 = v33;
    v17 = v21;
    goto LABEL_55;
  }
LABEL_54:
  v19 = (LPVOID *)lpMem;
  v20 = v28;
LABEL_55:
  if ( v19 )
  {
    for ( i = 0; i < v20; ++i )
      HeapFree(hHeap, 0, v19[i]);
    HeapFree(hHeap, 0, v19);
  }
  if ( v2 )
    HeapFree(hHeap, 0, v2);
  SetLastError(v17);
  return v3;
}

```

## disassembly

```asm
0x18000973c  push    rbp
0x18000973e  push    rbx
0x18000973f  push    rsi
0x180009740  push    rdi
0x180009741  push    r12
0x180009743  push    r13
0x180009745  push    r14
0x180009747  push    r15
0x180009749  lea     rbp, [rsp-6F8h]
0x180009751  sub     rsp, 7F8h
0x180009758  mov     rax, cs:__security_cookie
0x18000975f  xor     rax, rsp
0x180009762  mov     [rbp+730h+var_50], rax
0x180009769  xor     esi, esi
0x18000976b  lea     r9, [rsp+830h+ReturnLength]; ReturnLength
0x180009770  xorps   xmm0, xmm0
0x180009773  mov     [rsp+830h+pulLen], esi
0x180009777  xor     eax, eax
0x180009779  mov     [rsp+830h+pdnDevInst], esi
0x18000977d  mov     r8d, 218h; SystemInformationLength
0x180009783  mov     [rsp+830h+PropertyType], esi
0x180009787  lea     ecx, [rsi+62h]; SystemInformationClass
0x18000978a  mov     [rsp+830h+PropertyBufferSize], esi
0x18000978e  lea     rdx, [rbp+730h+SystemInformation]; SystemInformation
0x180009795  mov     [rbp+730h+var_7B0], rax
0x180009799  mov     r12d, esi
0x18000979c  mov     [rsp+830h+BytesReturned], esi
0x1800097a0  mov     r15d, esi
0x1800097a3  mov     [rsp+830h+lpMem], rsi
0x1800097a8  movups  [rsp+830h+OutBuffer], xmm0
0x1800097ad  mov     [rsp+830h+var_7E0], esi
0x1800097b1  mov     r13d, esi
0x1800097b4  mov     [rsp+830h+var_7C8], rsi
0x1800097b9  mov     [rsp+830h+var_7D4], esi
0x1800097bd  mov     [rsp+830h+ReturnLength], r8d
0x1800097c2  call    cs:__imp_NtQuerySystemInformation
0x1800097c8  test    eax, eax
0x1800097ca  js      short loc_1800097F8
0x1800097cc  movzx   edx, [rbp+730h+SystemInformation]
0x1800097d3  movzx   eax, [rbp+730h+var_60E]
0x1800097da  lea     rcx, [rdx+2]
0x1800097de  cmp     rcx, rax
0x1800097e1  ja      short loc_1800097F8
0x1800097e3  mov     rax, [rbp+730h+var_608]
0x1800097ea  shr     rdx, 1
0x1800097ed  mov     [rax+rdx*2], si
0x1800097f1  mov     r12, [rbp+730h+var_608]
0x1800097f8  mov     r14d, esi
0x1800097fb  movsxd  rbx, r14d
0x1800097fe  lea     rax, qword_180011118
0x180009805  shl     rbx, 4
0x180009809  add     rbx, rax
0x18000980c  mov     r9d, 1; ulFlags
0x180009812  lea     rcx, [rsp+830h+pulLen]; pulLen
0x180009817  xor     r8d, r8d; pDeviceID
0x18000981a  mov     rdx, rbx; InterfaceClassGuid
0x18000981d  call    cs:__imp_CM_Get_Device_Interface_List_SizeW
0x180009823  test    eax, eax
0x180009825  jnz     loc_180009B23
0x18000982b  test    r15, r15
0x18000982e  jz      short loc_180009842
0x180009830  mov     rcx, cs:hHeap; hHeap
0x180009837  mov     r8, r15; lpMem
0x18000983a  xor     edx, edx; dwFlags
0x18000983c  call    cs:__imp_HeapFree
0x180009842  mov     eax, [rsp+830h+pulLen]
0x180009846  xor     edx, edx; dwFlags
0x180009848  mov     rcx, cs:hHeap; hHeap
0x18000984f  lea     r8d, [rax+rax]; dwBytes
0x180009853  call    cs:__imp_HeapAlloc
0x180009859  mov     r15, rax
0x18000985c  test    rax, rax
0x18000985f  jz      loc_180009B1E
0x180009865  mov     r9d, [rsp+830h+pulLen]; BufferLen
0x18000986a  mov     r8, rax; Buffer
0x18000986d  xor     edx, edx; pDeviceID
0x18000986f  mov     [rsp+830h+ulFlags], 1; ulFlags
0x180009877  mov     rcx, rbx; InterfaceClassGuid
0x18000987a  call    cs:__imp_CM_Get_Device_Interface_ListW
0x180009880  cmp     eax, 1Ah
0x180009883  jz      short loc_18000980C
0x180009885  test    eax, eax
0x180009887  jnz     loc_180009B23
0x18000988d  mov     rdi, r15
0x180009890  cmp     [r15], si
0x180009894  jz      loc_180009B0F
0x18000989a  lea     rax, [rsp+830h+PropertyBufferSize]
0x18000989f  mov     [rsp+830h+dwFlagsAndAttributes], esi; ulFlags
0x1800098a3  lea     r9, [rbp+730h+PropertyBuffer]; PropertyBuffer
0x1800098aa  mov     qword ptr [rsp+830h+ulFlags], rax; PropertyBufferSize
0x1800098af  lea     r8, [rsp+830h+PropertyType]; PropertyType
0x1800098b4  mov     [rsp+830h+PropertyBufferSize], 190h
0x1800098bc  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x1800098c3  mov     rcx, rdi; pszDeviceInterface
0x1800098c6  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x1800098cc  test    eax, eax
0x1800098ce  jnz     loc_180009AF1
0x1800098d4  cmp     [rsp+830h+PropertyType], 12h
0x1800098d9  jnz     loc_180009AF1
0x1800098df  cmp     [rsp+830h+PropertyBufferSize], 2
0x1800098e4  jb      loc_180009AF1
0x1800098ea  cmp     r14d, 1
0x1800098ee  jnz     loc_180009980
0x1800098f4  test    r12, r12
0x1800098f7  jz      loc_180009980
0x1800098fd  mov     r8d, r14d; ulFlags
0x180009900  lea     rdx, [rbp+730h+PropertyBuffer]; pDeviceID
0x180009907  lea     rcx, [rsp+830h+pdnDevInst]; pdnDevInst
0x18000990c  call    cs:__imp_CM_Locate_DevNodeW
0x180009912  test    eax, eax
0x180009914  jnz     short loc_180009980
0x180009916  mov     ecx, [rsp+830h+pdnDevInst]; dnDevInst
0x18000991a  lea     rax, [rsp+830h+PropertyBufferSize]
0x18000991f  mov     [rsp+830h+dwFlagsAndAttributes], esi; ulFlags
0x180009923  lea     r9, [rbp+730h+var_260]; PropertyBuffer
0x18000992a  lea     r8, [rsp+830h+PropertyType]; PropertyType
0x18000992f  mov     qword ptr [rsp+830h+ulFlags], rax; PropertyBufferSize
0x180009934  lea     rdx, DEVPKEY_Device_PDOName; PropertyKey
0x18000993b  mov     [rsp+830h+PropertyBufferSize], 208h
0x180009943  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180009949  test    eax, eax
0x18000994b  jnz     short loc_180009980
0x18000994d  cmp     [rsp+830h+PropertyType], 12h
0x180009952  jnz     short loc_180009980
0x180009954  cmp     [rsp+830h+PropertyBufferSize], 2
0x180009959  jb      short loc_180009980
0x18000995b  or      r9d, 0FFFFFFFFh; cchCount2
0x18000995f  mov     [rsp+830h+ulFlags], r14d; bIgnoreCase
0x180009964  or      edx, r9d; cchCount1
0x180009967  lea     rcx, [rbp+730h+var_260]; lpString1
0x18000996e  mov     r8, r12; lpString2
0x180009971  call    cs:__imp_CompareStringOrdinal
0x180009977  cmp     eax, 2
0x18000997a  jz      loc_180009A25
0x180009980  mov     eax, 3
0x180009985  mov     [rsp+830h+hTemplateFile], rsi; hTemplateFile
0x18000998a  mov     r8d, eax; dwShareMode
0x18000998d  mov     [rsp+830h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x180009991  xor     r9d, r9d; lpSecurityAttributes
0x180009994  mov     [rsp+830h+ulFlags], eax; dwCreationDisposition
0x180009998  mov     edx, 80000000h; dwDesiredAccess
0x18000999d  mov     rcx, rdi; lpFileName
0x1800099a0  call    cs:__imp_CreateFileW
0x1800099a6  mov     rbx, rax
0x1800099a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800099ad  jz      loc_180009AF1
0x1800099b3  xor     eax, eax
0x1800099b5  xorps   xmm0, xmm0
0x1800099b8  mov     [rsp+830h+lpOverlapped], rax; lpOverlapped
0x1800099bd  xor     r9d, r9d; nInBufferSize
0x1800099c0  mov     [rbp+730h+var_7B0], rax
0x1800099c4  xor     r8d, r8d; lpInBuffer
0x1800099c7  lea     rax, [rsp+830h+BytesReturned]
0x1800099cc  mov     edx, 700010h; dwIoControlCode
0x1800099d1  mov     [rsp+830h+hTemplateFile], rax; lpBytesReturned
0x1800099d6  mov     rcx, rbx; hDevice
0x1800099d9  lea     rax, [rsp+830h+OutBuffer]
0x1800099de  mov     [rsp+830h+dwFlagsAndAttributes], 18h; nOutBufferSize
0x1800099e6  mov     qword ptr [rsp+830h+ulFlags], rax; lpOutBuffer
0x1800099eb  movups  [rsp+830h+OutBuffer], xmm0
0x1800099f0  call    cs:__imp_DeviceIoControl
0x1800099f6  xor     ecx, ecx
0x1800099f8  test    eax, eax
0x1800099fa  jz      short loc_180009A12
0x1800099fc  cmp     dword ptr [rsp+830h+OutBuffer+8], ecx
0x180009a00  jg      short loc_180009A0D
0x180009a02  cmp     dword ptr [rsp+830h+OutBuffer+0Ch], ecx
0x180009a06  jg      short loc_180009A0D
0x180009a08  cmp     dword ptr [rbp+730h+var_7B0], ecx
0x180009a0b  jle     short loc_180009A12
0x180009a0d  mov     esi, 1
0x180009a12  mov     rcx, rbx; hObject
0x180009a15  call    cs:__imp_CloseHandle
0x180009a1b  test    esi, esi
0x180009a1d  jz      loc_180009AEF
0x180009a23  xor     esi, esi
0x180009a25  mov     ecx, 7FFFFFFEh
0x180009a2a  lea     r8, [rbp+730h+PropertyBuffer]
0x180009a31  mov     edx, 0C8h
0x180009a36  lea     rax, [rbp+730h+var_7A0]
0x180009a3a  test    rcx, rcx
0x180009a3d  jz      short loc_180009A5E
0x180009a3f  movzx   r9d, word ptr [r8]
0x180009a43  test    r9w, r9w
0x180009a47  jz      short loc_180009A5E
0x180009a49  mov     [rax], r9w
0x180009a4d  add     r8, 2
0x180009a51  add     rax, 2
0x180009a55  dec     rcx
0x180009a58  sub     rdx, 1
0x180009a5c  jnz     short loc_180009A3A
0x180009a5e  test    rdx, rdx
0x180009a61  lea     rcx, [rax-2]
0x180009a65  cmovnz  rcx, rax
0x180009a69  mov     [rcx], si
0x180009a6c  jmp     short loc_180009AD4
0x180009a6e  lea     r8, [rbp+730h+var_7A0]
0x180009a72  lea     rdx, [rsp+830h+var_7E0]
0x180009a77  lea     rcx, [rsp+830h+lpMem]
0x180009a7c  call    pSetupAppendToStringArray
0x180009a81  mov     ebx, eax
0x180009a83  cmp     eax, 0B7h
0x180009a88  jz      short loc_180009A92
0x180009a8a  test    eax, eax
0x180009a8c  jnz     loc_180009B5C
0x180009a92  mov     ecx, [rsp+830h+pdnDevInst]; dnDevInst
0x180009a96  lea     rax, [rsp+830h+PropertyBufferSize]
0x180009a9b  mov     [rsp+830h+dwFlagsAndAttributes], esi; ulFlags
0x180009a9f  lea     r9, [rbp+730h+var_7A0]; PropertyBuffer
0x180009aa3  lea     r8, [rsp+830h+PropertyType]; PropertyType
0x180009aa8  mov     qword ptr [rsp+830h+ulFlags], rax; PropertyBufferSize
0x180009aad  lea     rdx, DEVPKEY_Device_Parent; PropertyKey
0x180009ab4  mov     [rsp+830h+PropertyBufferSize], 190h
0x180009abc  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180009ac2  test    eax, eax
0x180009ac4  jnz     short loc_180009AF1
0x180009ac6  cmp     [rsp+830h+PropertyType], 12h
0x180009acb  jnz     short loc_180009AF1
0x180009acd  cmp     [rsp+830h+PropertyBufferSize], 2
0x180009ad2  jb      short loc_180009AF1
0x180009ad4  mov     r8d, 1; ulFlags
0x180009ada  lea     rdx, [rbp+730h+var_7A0]; pDeviceID
0x180009ade  lea     rcx, [rsp+830h+pdnDevInst]; pdnDevInst
0x180009ae3  call    cs:__imp_CM_Locate_DevNodeW
0x180009ae9  test    eax, eax
0x180009aeb  jz      short loc_180009A6E
0x180009aed  jmp     short loc_180009AF1
0x180009aef  xor     esi, esi
0x180009af1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009af5  inc     rax
0x180009af8  cmp     [rdi+rax*2], si
0x180009afc  jnz     short loc_180009AF5
0x180009afe  lea     rdi, [rdi+rax*2]
0x180009b02  add     rdi, 2
0x180009b06  cmp     [rdi], si
0x180009b09  jnz     loc_18000989A
0x180009b0f  inc     r14d
0x180009b12  cmp     r14d, 2
0x180009b16  jb      loc_1800097FB
0x180009b1c  jmp     short loc_180009B36
0x180009b1e  mov     eax, 2
0x180009b23  mov     edx, 0Dh; DefaultErr
0x180009b28  mov     ecx, eax; CmReturnCode
0x180009b2a  call    cs:__imp_CM_MapCrToWin32Err
0x180009b30  mov     ebx, eax
0x180009b32  test    eax, eax
0x180009b34  jnz     short loc_180009B5C
0x180009b36  mov     rdi, [rsp+830h+lpMem]
0x180009b3b  lea     r9, [rsp+830h+var_7D4]
0x180009b40  mov     esi, [rsp+830h+var_7E0]
0x180009b44  lea     r8, [rsp+830h+var_7C8]
0x180009b49  mov     rcx, rdi
0x180009b4c  mov     edx, esi
0x180009b4e  call    pSetupStringArrayToMultiSz
0x180009b53  mov     r13, [rsp+830h+var_7C8]
0x180009b58  mov     ebx, eax
0x180009b5a  jmp     short loc_180009B65
0x180009b5c  mov     rdi, [rsp+830h+lpMem]
0x180009b61  mov     esi, [rsp+830h+var_7E0]
0x180009b65  xor     r12d, r12d
0x180009b68  test    rdi, rdi
0x180009b6b  jz      short loc_180009BA4
0x180009b6d  mov     r14d, r12d
0x180009b70  test    esi, esi
0x180009b72  jz      short loc_180009B92
0x180009b74  mov     rcx, cs:hHeap; hHeap
0x180009b7b  xor     edx, edx; dwFlags
0x180009b7d  mov     r8d, r14d
0x180009b80  mov     r8, [rdi+r8*8]; lpMem
0x180009b84  call    cs:__imp_HeapFree
0x180009b8a  inc     r14d
0x180009b8d  cmp     r14d, esi
0x180009b90  jb      short loc_180009B74
0x180009b92  mov     rcx, cs:hHeap; hHeap
0x180009b99  mov     r8, rdi; lpMem
0x180009b9c  xor     edx, edx; dwFlags
0x180009b9e  call    cs:__imp_HeapFree
0x180009ba4  test    r15, r15
0x180009ba7  jz      short loc_180009BBB
0x180009ba9  mov     rcx, cs:hHeap; hHeap
0x180009bb0  mov     r8, r15; lpMem
0x180009bb3  xor     edx, edx; dwFlags
0x180009bb5  call    cs:__imp_HeapFree
0x180009bbb  mov     ecx, ebx; dwErrCode
0x180009bbd  call    cs:__imp_SetLastError
0x180009bc3  mov     rax, r13
0x180009bc6  mov     rcx, [rbp+730h+var_50]
0x180009bcd  xor     rcx, rsp; StackCookie
0x180009bd0  call    __security_check_cookie
0x180009bd5  add     rsp, 7F8h
0x180009bdc  pop     r15
0x180009bde  pop     r14
0x180009be0  pop     r13
0x180009be2  pop     r12
0x180009be4  pop     rdi
0x180009be5  pop     rsi
0x180009be6  pop     rbx
0x180009be7  pop     rbp
0x180009be8  retn
```
