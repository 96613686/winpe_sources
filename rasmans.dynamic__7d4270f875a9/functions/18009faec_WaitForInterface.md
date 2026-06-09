# WaitForInterface

- ea: `0x18009faec`
- end: `0x18009fcef`
- name: `WaitForInterface`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18009f1e8`

## callees

- `0x18009faec`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fcc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009fcc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fbf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fbf9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009fc7c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009fc7c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009fbe5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009fbe5`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18009fcb4`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18009fcb4`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18009fc62`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18009fc62`

## pseudocode

```c
__int64 __fastcall WaitForInterface(__int64 a1)
{
  __int64 v1; // rax
  HANDLE EventW; // rax
  void *v3; // rdi
  signed int LastError; // eax
  signed int v5; // ebx
  DWORD v6; // eax
  __int64 v8; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v9; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+70h] [rbp-90h] BYREF
  DEVPROPKEY v11; // [rsp+78h] [rbp-88h]
  int v12; // [rsp+8Ch] [rbp-74h]
  __int64 v13; // [rsp+90h] [rbp-70h]
  int v14; // [rsp+98h] [rbp-68h]
  int v15; // [rsp+9Ch] [rbp-64h]
  __int64 v16; // [rsp+A0h] [rbp-60h]
  int v17; // [rsp+A8h] [rbp-58h]
  int v18; // [rsp+ACh] [rbp-54h]
  DEVPROPKEY v19; // [rsp+B0h] [rbp-50h]
  int v20; // [rsp+C4h] [rbp-3Ch]
  __int64 v21; // [rsp+C8h] [rbp-38h]
  int v22; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+D4h] [rbp-2Ch]
  int *v24; // [rsp+D8h] [rbp-28h]
  int v25; // [rsp+E0h] [rbp-20h]
  int v26; // [rsp+E4h] [rbp-1Ch]
  DEVPROPKEY v27; // [rsp+E8h] [rbp-18h]
  int v28; // [rsp+FCh] [rbp-4h]
  __int64 v29; // [rsp+100h] [rbp+0h]
  int v30; // [rsp+108h] [rbp+8h]
  int v31; // [rsp+10Ch] [rbp+Ch]
  GUID *v32; // [rsp+110h] [rbp+10h]

  v10 = 131074;
  v18 = 0;
  v26 = 0;
  v9 = 0;
  v11 = DEVPKEY_Device_InstanceId;
  v1 = -1;
  v8 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 18;
  do
    ++v1;
  while ( *(_WORD *)(a1 + 2 * v1) );
  v16 = a1;
  v15 = 2 * v1 + 2;
  v19 = DEVPKEY_DeviceInterface_Enabled;
  v24 = &s_fDevpropTrue;
  v27 = DEVPKEY_DeviceInterface_ClassGuid;
  v17 = 2;
  v25 = 2;
  v32 = &GUID_DEVINTERFACE_NET;
  v20 = 0;
  v21 = 0;
  v22 = 17;
  v23 = 1;
  v28 = 0;
  v29 = 0;
  v30 = 13;
  v31 = 16;
  EventW = CreateEventW(0, 0, 0, 0);
  v3 = EventW;
  if ( !EventW )
    goto LABEL_4;
  *(_QWORD *)&v9 = EventW;
  DWORD2(v9) = 0;
  v5 = DevCreateObjectQuery(1, 1, 0, 0, 3, &v10, DevQueryCallback, &v9, &v8);
  if ( v5 < 0 )
    goto LABEL_12;
  v6 = WaitForSingleObject(v3, 0x7530u);
  if ( !v6 )
  {
    v5 = DWORD2(v9);
    goto LABEL_12;
  }
  if ( v6 == -1 )
  {
LABEL_4:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v5 = -2147418113;
    if ( v6 == 258 )
      v5 = DWORD2(v9);
  }
LABEL_12:
  if ( v8 )
    DevCloseObjectQuery();
  if ( v3 )
    CloseHandle(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18009faec  push    rbp
0x18009faee  push    rbx
0x18009faef  push    rsi
0x18009faf0  push    rdi
0x18009faf1  lea     rbp, [rsp-38h]
0x18009faf6  sub     rsp, 138h
0x18009fafd  mov     rax, cs:__security_cookie
0x18009fb04  xor     rax, rsp
0x18009fb07  mov     [rbp+50h+var_30], rax
0x18009fb0b  xor     eax, eax
0x18009fb0d  mov     [rsp+150h+var_E0], 20002h
0x18009fb16  xor     esi, esi
0x18009fb18  mov     [rbp+50h+var_A4], eax
0x18009fb1b  xorps   xmm0, xmm0
0x18009fb1e  mov     [rbp+50h+var_6C], eax
0x18009fb21  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18009fb27  movups  [rsp+150h+var_F8], xmm0
0x18009fb2c  mov     [rbp+50h+var_C8], eax
0x18009fb2f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009fb33  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18009fb3a  mov     [rsp+150h+var_100], rsi
0x18009fb3f  mov     [rbp+50h+var_C4], esi
0x18009fb42  movups  [rsp+150h+var_D8], xmm0
0x18009fb47  mov     [rbp+50h+var_C0], rsi
0x18009fb4b  mov     [rbp+50h+var_B8], 12h
0x18009fb52  inc     rax
0x18009fb55  cmp     [rcx+rax*2], si
0x18009fb59  jnz     short loc_18009FB52
0x18009fb5b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18009fb62  lea     eax, ds:2[rax*2]
0x18009fb69  mov     [rbp+50h+var_B0], rcx
0x18009fb6d  mov     [rbp+50h+var_B4], eax
0x18009fb70  mov     ecx, 2
0x18009fb75  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18009fb7b  xor     r9d, r9d; lpName
0x18009fb7e  mov     [rbp+50h+var_90], eax
0x18009fb81  xor     r8d, r8d; bInitialState
0x18009fb84  lea     rax, s_fDevpropTrue
0x18009fb8b  movaps  [rbp+50h+var_A0], xmm0
0x18009fb8f  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18009fb96  mov     [rbp+50h+var_78], rax
0x18009fb9a  lea     ebx, [rcx-1]
0x18009fb9d  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18009fba3  xor     edx, edx; bManualReset
0x18009fba5  mov     [rbp+50h+var_58], eax
0x18009fba8  lea     rax, GUID_DEVINTERFACE_NET
0x18009fbaf  mov     [rbp+50h+var_A8], ecx
0x18009fbb2  mov     [rbp+50h+var_70], ecx
0x18009fbb5  xor     ecx, ecx; lpEventAttributes
0x18009fbb7  mov     [rbp+50h+var_40], rax
0x18009fbbb  mov     [rbp+50h+var_8C], esi
0x18009fbbe  mov     [rbp+50h+var_88], rsi
0x18009fbc2  mov     [rbp+50h+var_80], 11h
0x18009fbc9  mov     [rbp+50h+var_7C], ebx
0x18009fbcc  movups  [rbp+50h+var_68], xmm0
0x18009fbd0  mov     [rbp+50h+var_54], esi
0x18009fbd3  mov     [rbp+50h+var_50], rsi
0x18009fbd7  mov     [rbp+50h+var_48], 0Dh
0x18009fbde  mov     [rbp+50h+var_44], 10h
0x18009fbe5  call    cs:__imp_CreateEventW
0x18009fbec  nop     dword ptr [rax+rax+00h]
0x18009fbf1  mov     rdi, rax
0x18009fbf4  test    rax, rax
0x18009fbf7  jnz     short loc_18009FC1D
0x18009fbf9  call    cs:__imp_GetLastError
0x18009fc00  nop     dword ptr [rax+rax+00h]
0x18009fc05  mov     ebx, eax
0x18009fc07  test    eax, eax
0x18009fc09  jle     loc_18009FCAA
0x18009fc0f  movzx   ebx, ax
0x18009fc12  or      ebx, 80070000h
0x18009fc18  jmp     loc_18009FCAA
0x18009fc1d  lea     rax, [rsp+150h+var_100]
0x18009fc22  mov     qword ptr [rsp+150h+var_F8], rdi
0x18009fc27  mov     [rsp+150h+var_110], rax
0x18009fc2c  xor     r9d, r9d
0x18009fc2f  lea     rax, [rsp+150h+var_F8]
0x18009fc34  mov     dword ptr [rsp+150h+var_F8+8], esi
0x18009fc38  mov     [rsp+150h+var_118], rax
0x18009fc3d  xor     r8d, r8d
0x18009fc40  lea     rax, DevQueryCallback
0x18009fc47  mov     edx, ebx
0x18009fc49  mov     [rsp+150h+var_120], rax
0x18009fc4e  mov     ecx, ebx
0x18009fc50  lea     rax, [rsp+150h+var_E0]
0x18009fc55  mov     [rsp+150h+var_128], rax
0x18009fc5a  mov     [rsp+150h+var_130], 3
0x18009fc62  call    cs:__imp_DevCreateObjectQuery
0x18009fc69  nop     dword ptr [rax+rax+00h]
0x18009fc6e  mov     ebx, eax
0x18009fc70  test    eax, eax
0x18009fc72  js      short loc_18009FCAA
0x18009fc74  mov     edx, 7530h; dwMilliseconds
0x18009fc79  mov     rcx, rdi; hHandle
0x18009fc7c  call    cs:__imp_WaitForSingleObject
0x18009fc83  nop     dword ptr [rax+rax+00h]
0x18009fc88  test    eax, eax
0x18009fc8a  jnz     short loc_18009FC92
0x18009fc8c  mov     ebx, dword ptr [rsp+150h+var_F8+8]
0x18009fc90  jmp     short loc_18009FCAA
0x18009fc92  cmp     eax, 0FFFFFFFFh
0x18009fc95  jz      loc_18009FBF9
0x18009fc9b  cmp     eax, 102h
0x18009fca0  mov     ebx, 8000FFFFh
0x18009fca5  cmovz   ebx, dword ptr [rsp+150h+var_F8+8]
0x18009fcaa  mov     rcx, [rsp+150h+var_100]
0x18009fcaf  test    rcx, rcx
0x18009fcb2  jz      short loc_18009FCC0
0x18009fcb4  call    cs:__imp_DevCloseObjectQuery
0x18009fcbb  nop     dword ptr [rax+rax+00h]
0x18009fcc0  test    rdi, rdi
0x18009fcc3  jz      short loc_18009FCD4
0x18009fcc5  mov     rcx, rdi; hObject
0x18009fcc8  call    cs:__imp_CloseHandle
0x18009fccf  nop     dword ptr [rax+rax+00h]
0x18009fcd4  mov     eax, ebx
0x18009fcd6  mov     rcx, [rbp+50h+var_30]
0x18009fcda  xor     rcx, rsp; StackCookie
0x18009fcdd  call    __security_check_cookie
0x18009fce2  add     rsp, 138h
0x18009fce9  pop     rdi
0x18009fcea  pop     rsi
0x18009fceb  pop     rbx
0x18009fcec  pop     rbp
0x18009fced  retn
```
