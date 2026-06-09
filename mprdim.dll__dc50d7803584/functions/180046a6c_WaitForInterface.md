# WaitForInterface

- ea: `0x180046a6c`
- end: `0x180046c4a`
- name: `WaitForInterface`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180046254`

## callees

- `0x180046a6c`
- `0x180046e70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046c2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046b73`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046bea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046bea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180046b65`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046c1c`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x180046c1c`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180046bd6`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x180046bd6`

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
  __int64 *v24; // [rsp+D8h] [rbp-28h]
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
  v24 = s_fDevpropTrue;
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
0x180046a6c  push    rbp
0x180046a6e  push    rbx
0x180046a6f  push    rsi
0x180046a70  push    rdi
0x180046a71  lea     rbp, [rsp-38h]
0x180046a76  sub     rsp, 138h
0x180046a7d  mov     rax, cs:__security_cookie
0x180046a84  xor     rax, rsp
0x180046a87  mov     [rbp+50h+var_30], rax
0x180046a8b  xor     eax, eax
0x180046a8d  mov     [rsp+150h+var_E0], 20002h
0x180046a96  xor     esi, esi
0x180046a98  mov     [rbp+50h+var_A4], eax
0x180046a9b  xorps   xmm0, xmm0
0x180046a9e  mov     [rbp+50h+var_6C], eax
0x180046aa1  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180046aa7  movups  [rsp+150h+var_F8], xmm0
0x180046aac  mov     [rbp+50h+var_C8], eax
0x180046aaf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046ab3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180046aba  mov     [rsp+150h+var_100], rsi
0x180046abf  mov     [rbp+50h+var_C4], esi
0x180046ac2  movups  [rsp+150h+var_D8], xmm0
0x180046ac7  mov     [rbp+50h+var_C0], rsi
0x180046acb  mov     [rbp+50h+var_B8], 12h
0x180046ad2  inc     rax
0x180046ad5  cmp     [rcx+rax*2], si
0x180046ad9  jnz     short loc_180046AD2
0x180046adb  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x180046ae2  lea     eax, ds:2[rax*2]
0x180046ae9  mov     [rbp+50h+var_B0], rcx
0x180046aed  mov     [rbp+50h+var_B4], eax
0x180046af0  mov     ecx, 2
0x180046af5  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x180046afb  xor     r9d, r9d; lpName
0x180046afe  mov     [rbp+50h+var_90], eax
0x180046b01  xor     r8d, r8d; bInitialState
0x180046b04  lea     rax, s_fDevpropTrue
0x180046b0b  movaps  [rbp+50h+var_A0], xmm0
0x180046b0f  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180046b16  mov     [rbp+50h+var_78], rax
0x180046b1a  lea     ebx, [rcx-1]
0x180046b1d  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180046b23  xor     edx, edx; bManualReset
0x180046b25  mov     [rbp+50h+var_58], eax
0x180046b28  lea     rax, GUID_DEVINTERFACE_NET
0x180046b2f  mov     [rbp+50h+var_A8], ecx
0x180046b32  mov     [rbp+50h+var_70], ecx
0x180046b35  xor     ecx, ecx; lpEventAttributes
0x180046b37  mov     [rbp+50h+var_40], rax
0x180046b3b  mov     [rbp+50h+var_8C], esi
0x180046b3e  mov     [rbp+50h+var_88], rsi
0x180046b42  mov     [rbp+50h+var_80], 11h
0x180046b49  mov     [rbp+50h+var_7C], ebx
0x180046b4c  movups  [rbp+50h+var_68], xmm0
0x180046b50  mov     [rbp+50h+var_54], esi
0x180046b53  mov     [rbp+50h+var_50], rsi
0x180046b57  mov     [rbp+50h+var_48], 0Dh
0x180046b5e  mov     [rbp+50h+var_44], 10h
0x180046b65  call    cs:__imp_CreateEventW
0x180046b6b  mov     rdi, rax
0x180046b6e  test    rax, rax
0x180046b71  jnz     short loc_180046B91
0x180046b73  call    cs:__imp_GetLastError
0x180046b79  mov     ebx, eax
0x180046b7b  test    eax, eax
0x180046b7d  jle     loc_180046C12
0x180046b83  movzx   ebx, ax
0x180046b86  or      ebx, 80070000h
0x180046b8c  jmp     loc_180046C12
0x180046b91  lea     rax, [rsp+150h+var_100]
0x180046b96  mov     qword ptr [rsp+150h+var_F8], rdi
0x180046b9b  mov     [rsp+150h+var_110], rax
0x180046ba0  xor     r9d, r9d
0x180046ba3  lea     rax, [rsp+150h+var_F8]
0x180046ba8  mov     dword ptr [rsp+150h+var_F8+8], esi
0x180046bac  mov     [rsp+150h+var_118], rax
0x180046bb1  xor     r8d, r8d
0x180046bb4  lea     rax, DevQueryCallback
0x180046bbb  mov     edx, ebx
0x180046bbd  mov     [rsp+150h+var_120], rax
0x180046bc2  mov     ecx, ebx
0x180046bc4  lea     rax, [rsp+150h+var_E0]
0x180046bc9  mov     [rsp+150h+var_128], rax
0x180046bce  mov     [rsp+150h+var_130], 3
0x180046bd6  call    cs:__imp_DevCreateObjectQuery
0x180046bdc  mov     ebx, eax
0x180046bde  test    eax, eax
0x180046be0  js      short loc_180046C12
0x180046be2  mov     edx, 7530h; dwMilliseconds
0x180046be7  mov     rcx, rdi; hHandle
0x180046bea  call    cs:__imp_WaitForSingleObject
0x180046bf0  test    eax, eax
0x180046bf2  jnz     short loc_180046BFA
0x180046bf4  mov     ebx, dword ptr [rsp+150h+var_F8+8]
0x180046bf8  jmp     short loc_180046C12
0x180046bfa  cmp     eax, 0FFFFFFFFh
0x180046bfd  jz      loc_180046B73
0x180046c03  cmp     eax, 102h
0x180046c08  mov     ebx, 8000FFFFh
0x180046c0d  cmovz   ebx, dword ptr [rsp+150h+var_F8+8]
0x180046c12  mov     rcx, [rsp+150h+var_100]
0x180046c17  test    rcx, rcx
0x180046c1a  jz      short loc_180046C22
0x180046c1c  call    cs:__imp_DevCloseObjectQuery
0x180046c22  test    rdi, rdi
0x180046c25  jz      short loc_180046C30
0x180046c27  mov     rcx, rdi; hObject
0x180046c2a  call    cs:__imp_CloseHandle
0x180046c30  mov     eax, ebx
0x180046c32  mov     rcx, [rbp+50h+var_30]
0x180046c36  xor     rcx, rsp; StackCookie
0x180046c39  call    __security_check_cookie
0x180046c3e  add     rsp, 138h
0x180046c45  pop     rdi
0x180046c46  pop     rsi
0x180046c47  pop     rbx
0x180046c48  pop     rbp
0x180046c49  retn
```
