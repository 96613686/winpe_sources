# WaitForInterface

- ea: `0x18009a7ac`
- end: `0x18009a98a`
- name: `WaitForInterface`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180099f60`

## callees

- `0x18009a7ac`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a96a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a96a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a8b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009a8b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a92a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18009a92a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a8a5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009a8a5`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18009a916`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18009a916`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18009a95c`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18009a95c`

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
0x18009a7ac  push    rbp
0x18009a7ae  push    rbx
0x18009a7af  push    rsi
0x18009a7b0  push    rdi
0x18009a7b1  lea     rbp, [rsp-38h]
0x18009a7b6  sub     rsp, 138h
0x18009a7bd  mov     rax, cs:__security_cookie
0x18009a7c4  xor     rax, rsp
0x18009a7c7  mov     [rbp+50h+var_30], rax
0x18009a7cb  xor     eax, eax
0x18009a7cd  mov     [rsp+150h+var_E0], 20002h
0x18009a7d6  xor     esi, esi
0x18009a7d8  mov     [rbp+50h+var_A4], eax
0x18009a7db  xorps   xmm0, xmm0
0x18009a7de  mov     [rbp+50h+var_6C], eax
0x18009a7e1  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18009a7e7  movups  [rsp+150h+var_F8], xmm0
0x18009a7ec  mov     [rbp+50h+var_C8], eax
0x18009a7ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009a7f3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18009a7fa  mov     [rsp+150h+var_100], rsi
0x18009a7ff  mov     [rbp+50h+var_C4], esi
0x18009a802  movups  [rsp+150h+var_D8], xmm0
0x18009a807  mov     [rbp+50h+var_C0], rsi
0x18009a80b  mov     [rbp+50h+var_B8], 12h
0x18009a812  inc     rax
0x18009a815  cmp     [rcx+rax*2], si
0x18009a819  jnz     short loc_18009A812
0x18009a81b  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18009a822  lea     eax, ds:2[rax*2]
0x18009a829  mov     [rbp+50h+var_B0], rcx
0x18009a82d  mov     [rbp+50h+var_B4], eax
0x18009a830  mov     ecx, 2
0x18009a835  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18009a83b  xor     r9d, r9d; lpName
0x18009a83e  mov     [rbp+50h+var_90], eax
0x18009a841  xor     r8d, r8d; bInitialState
0x18009a844  lea     rax, s_fDevpropTrue
0x18009a84b  movaps  [rbp+50h+var_A0], xmm0
0x18009a84f  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18009a856  mov     [rbp+50h+var_78], rax
0x18009a85a  lea     ebx, [rcx-1]
0x18009a85d  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18009a863  xor     edx, edx; bManualReset
0x18009a865  mov     [rbp+50h+var_58], eax
0x18009a868  lea     rax, GUID_DEVINTERFACE_NET
0x18009a86f  mov     [rbp+50h+var_A8], ecx
0x18009a872  mov     [rbp+50h+var_70], ecx
0x18009a875  xor     ecx, ecx; lpEventAttributes
0x18009a877  mov     [rbp+50h+var_40], rax
0x18009a87b  mov     [rbp+50h+var_8C], esi
0x18009a87e  mov     [rbp+50h+var_88], rsi
0x18009a882  mov     [rbp+50h+var_80], 11h
0x18009a889  mov     [rbp+50h+var_7C], ebx
0x18009a88c  movups  [rbp+50h+var_68], xmm0
0x18009a890  mov     [rbp+50h+var_54], esi
0x18009a893  mov     [rbp+50h+var_50], rsi
0x18009a897  mov     [rbp+50h+var_48], 0Dh
0x18009a89e  mov     [rbp+50h+var_44], 10h
0x18009a8a5  call    cs:__imp_CreateEventW
0x18009a8ab  mov     rdi, rax
0x18009a8ae  test    rax, rax
0x18009a8b1  jnz     short loc_18009A8D1
0x18009a8b3  call    cs:__imp_GetLastError
0x18009a8b9  mov     ebx, eax
0x18009a8bb  test    eax, eax
0x18009a8bd  jle     loc_18009A952
0x18009a8c3  movzx   ebx, ax
0x18009a8c6  or      ebx, 80070000h
0x18009a8cc  jmp     loc_18009A952
0x18009a8d1  lea     rax, [rsp+150h+var_100]
0x18009a8d6  mov     qword ptr [rsp+150h+var_F8], rdi
0x18009a8db  mov     [rsp+150h+var_110], rax
0x18009a8e0  xor     r9d, r9d
0x18009a8e3  lea     rax, [rsp+150h+var_F8]
0x18009a8e8  mov     dword ptr [rsp+150h+var_F8+8], esi
0x18009a8ec  mov     [rsp+150h+var_118], rax
0x18009a8f1  xor     r8d, r8d
0x18009a8f4  lea     rax, DevQueryCallback
0x18009a8fb  mov     edx, ebx
0x18009a8fd  mov     [rsp+150h+var_120], rax
0x18009a902  mov     ecx, ebx
0x18009a904  lea     rax, [rsp+150h+var_E0]
0x18009a909  mov     [rsp+150h+var_128], rax
0x18009a90e  mov     [rsp+150h+var_130], 3
0x18009a916  call    cs:__imp_DevCreateObjectQuery
0x18009a91c  mov     ebx, eax
0x18009a91e  test    eax, eax
0x18009a920  js      short loc_18009A952
0x18009a922  mov     edx, 7530h; dwMilliseconds
0x18009a927  mov     rcx, rdi; hHandle
0x18009a92a  call    cs:__imp_WaitForSingleObject
0x18009a930  test    eax, eax
0x18009a932  jnz     short loc_18009A93A
0x18009a934  mov     ebx, dword ptr [rsp+150h+var_F8+8]
0x18009a938  jmp     short loc_18009A952
0x18009a93a  cmp     eax, 0FFFFFFFFh
0x18009a93d  jz      loc_18009A8B3
0x18009a943  cmp     eax, 102h
0x18009a948  mov     ebx, 8000FFFFh
0x18009a94d  cmovz   ebx, dword ptr [rsp+150h+var_F8+8]
0x18009a952  mov     rcx, [rsp+150h+var_100]
0x18009a957  test    rcx, rcx
0x18009a95a  jz      short loc_18009A962
0x18009a95c  call    cs:__imp_DevCloseObjectQuery
0x18009a962  test    rdi, rdi
0x18009a965  jz      short loc_18009A970
0x18009a967  mov     rcx, rdi; hObject
0x18009a96a  call    cs:__imp_CloseHandle
0x18009a970  mov     eax, ebx
0x18009a972  mov     rcx, [rbp+50h+var_30]
0x18009a976  xor     rcx, rsp; StackCookie
0x18009a979  call    __security_check_cookie
0x18009a97e  add     rsp, 138h
0x18009a985  pop     rdi
0x18009a986  pop     rsi
0x18009a987  pop     rbx
0x18009a988  pop     rbp
0x18009a989  retn
```
