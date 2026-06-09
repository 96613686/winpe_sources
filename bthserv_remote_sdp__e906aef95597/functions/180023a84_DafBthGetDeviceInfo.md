# DafBthGetDeviceInfo

- ea: `0x180023a84`
- end: `0x180023d9f`
- name: `DafBthGetDeviceInfo`
- size: `795`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180022a74`

## callees

- `0x1800017a0`
- `0x18000270c`
- `0x18002354c`
- `0x180023628`
- `0x180023a84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023b39`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180023b39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023cb3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023be1`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180023be1`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023c18`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180023c18`

## pseudocode

```c
__int64 __fastcall DafBthGetDeviceInfo(HANDLE hFile, __int64 a2, int a3, _OWORD *a4)
{
  unsigned int v8; // ebx
  signed int v9; // eax
  int v10; // r9d
  _QWORD *v11; // rcx
  int v12; // edx
  signed int LastError; // eax
  signed int v14; // eax
  __int64 v15; // rcx
  char *v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  int v27; // eax
  bool v28; // cf
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+48h] [rbp-B8h] BYREF
  int OutBuffer; // [rsp+70h] [rbp-90h] BYREF
  int v33; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+80h] [rbp-80h]
  char v36; // [rsp+88h] [rbp-78h] BYREF

  v8 = 0;
  memset_0(&v33, 0, 0x354u);
  BytesReturned = 0;
  memset(&Overlapped, 0, 24);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids);
  v34 = a2;
  v33 = 3;
  v35 = 1;
  OutBuffer = a3;
  Overlapped.hEvent = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( Overlapped.hEvent )
  {
    if ( DeviceIoControl(hFile, 0x411058u, &OutBuffer, 0x18u, &OutBuffer, 0x358u, &BytesReturned, &Overlapped) )
      goto LABEL_25;
    LastError = GetLastError();
    if ( LastError == 997 )
    {
      if ( GetOverlappedResult(hFile, &Overlapped, &BytesReturned, 1) )
        goto LABEL_25;
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v12 = 23;
        goto LABEL_10;
      }
    }
    else
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      else
        v8 = LastError;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v12 = 24;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      v8 = (unsigned __int16)v9 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 22;
LABEL_10:
      WPP_SF_sd(v11[2], v12, (unsigned int)WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids, v10, v8);
LABEL_25:
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = 0;
    v11 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    v27 = 0;
    v28 = *((_BYTE *)v11 + 25) < 2u;
  }
  else
  {
    v15 = 6;
    v16 = &v36;
    do
    {
      v17 = *((_OWORD *)v16 + 1);
      *a4 = *(_OWORD *)v16;
      v18 = *((_OWORD *)v16 + 2);
      a4[1] = v17;
      v19 = *((_OWORD *)v16 + 3);
      a4[2] = v18;
      v20 = *((_OWORD *)v16 + 4);
      a4[3] = v19;
      v21 = *((_OWORD *)v16 + 5);
      a4[4] = v20;
      v22 = *((_OWORD *)v16 + 6);
      a4[5] = v21;
      v23 = *((_OWORD *)v16 + 7);
      v16 += 128;
      a4[6] = v22;
      a4 += 8;
      *(a4 - 1) = v23;
      --v15;
    }
    while ( v15 );
    v24 = *((_OWORD *)v16 + 1);
    *a4 = *(_OWORD *)v16;
    v25 = *((_OWORD *)v16 + 2);
    a4[1] = v24;
    v26 = *((_OWORD *)v16 + 3);
    v27 = 0;
    a4[2] = v25;
    a4[3] = v26;
    v11 = WPP_GLOBAL_Control;
    v28 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  }
  if ( v11 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v27) = !v28;
    if ( v27 )
      WPP_SF_sd(v11[2], 25, (unsigned int)WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids, v10, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180023a84  push    rbp
0x180023a86  push    rbx
0x180023a87  push    rsi
0x180023a88  push    rdi
0x180023a89  push    r13
0x180023a8b  push    r14
0x180023a8d  push    r15
0x180023a8f  lea     rbp, [rsp-2E0h]
0x180023a97  sub     rsp, 3E0h
0x180023a9e  mov     rax, cs:__security_cookie
0x180023aa5  xor     rax, rsp
0x180023aa8  mov     [rbp+310h+var_40], rax
0x180023aaf  mov     r15d, r8d
0x180023ab2  mov     r14, rdx
0x180023ab5  mov     rsi, rcx
0x180023ab8  xor     edx, edx; Val
0x180023aba  mov     r8d, 354h; Size
0x180023ac0  lea     rcx, [rsp+410h+var_39C]; void *
0x180023ac5  mov     rdi, r9
0x180023ac8  xor     ebx, ebx
0x180023aca  call    memset_0
0x180023acf  and     [rsp+410h+BytesReturned], ebx
0x180023ad3  xorps   xmm0, xmm0
0x180023ad6  and     [rsp+410h+Overlapped.Internal], rbx
0x180023adb  movdqu  xmmword ptr [rsp+410h+Overlapped.InternalHigh], xmm0
0x180023ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ae8  lea     rax, WPP_GLOBAL_Control
0x180023aef  lea     r13, WPP_b3a5891df4c637521e7337f4e390efd4_Traceguids
0x180023af6  cmp     rcx, rax
0x180023af9  jz      short loc_180023B10
0x180023afb  cmp     byte ptr [rcx+19h], 5
0x180023aff  jb      short loc_180023B10
0x180023b01  mov     rcx, [rcx+10h]
0x180023b05  lea     edx, [rbx+15h]
0x180023b08  mov     r8, r13
0x180023b0b  call    WPP_SF_s
0x180023b10  mov     [rsp+410h+var_398], r14
0x180023b15  mov     r9d, 1F0003h; dwDesiredAccess
0x180023b1b  mov     r14d, 1
0x180023b21  mov     [rsp+410h+var_39C], 3
0x180023b29  mov     r8d, r14d; dwFlags
0x180023b2c  mov     [rbp+310h+var_390], r14d
0x180023b30  xor     edx, edx; lpName
0x180023b32  mov     [rsp+410h+OutBuffer], r15d
0x180023b37  xor     ecx, ecx; lpEventAttributes
0x180023b39  call    cs:__imp_CreateEventExW
0x180023b40  nop     dword ptr [rax+rax+00h]
0x180023b45  mov     [rsp+410h+Overlapped.hEvent], rax
0x180023b4a  test    rax, rax
0x180023b4d  jnz     short loc_180023BA5
0x180023b4f  call    cs:__imp_GetLastError
0x180023b56  nop     dword ptr [rax+rax+00h]
0x180023b5b  mov     ebx, eax
0x180023b5d  test    eax, eax
0x180023b5f  jle     short loc_180023B6A
0x180023b61  movzx   ebx, ax
0x180023b64  or      ebx, 80070000h
0x180023b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b71  lea     rsi, WPP_GLOBAL_Control
0x180023b78  cmp     rcx, rsi
0x180023b7b  jz      loc_180023CA6
0x180023b81  cmp     byte ptr [rcx+19h], 2
0x180023b85  jb      loc_180023CA6
0x180023b8b  mov     edx, 16h
0x180023b90  mov     rcx, [rcx+10h]
0x180023b94  mov     r8, r13
0x180023b97  mov     dword ptr [rsp+410h+lpOutBuffer], ebx
0x180023b9b  call    WPP_SF_sd
0x180023ba0  jmp     loc_180023C9F
0x180023ba5  lea     rax, [rsp+410h+Overlapped]
0x180023baa  mov     r15d, 18h
0x180023bb0  mov     [rsp+410h+lpOverlapped], rax; lpOverlapped
0x180023bb5  lea     r8, [rsp+410h+OutBuffer]; lpInBuffer
0x180023bba  lea     rax, [rsp+410h+BytesReturned]
0x180023bbf  mov     r9d, r15d; nInBufferSize
0x180023bc2  mov     [rsp+410h+lpBytesReturned], rax; lpBytesReturned
0x180023bc7  mov     edx, 411058h; dwIoControlCode
0x180023bcc  lea     rax, [rsp+410h+OutBuffer]
0x180023bd1  mov     [rsp+410h+nOutBufferSize], 358h; nOutBufferSize
0x180023bd9  mov     rcx, rsi; hDevice
0x180023bdc  mov     [rsp+410h+lpOutBuffer], rax; lpOutBuffer
0x180023be1  call    cs:__imp_DeviceIoControl
0x180023be8  nop     dword ptr [rax+rax+00h]
0x180023bed  test    eax, eax
0x180023bef  jnz     loc_180023C98
0x180023bf5  call    cs:__imp_GetLastError
0x180023bfc  nop     dword ptr [rax+rax+00h]
0x180023c01  cmp     eax, 3E5h
0x180023c06  jnz     short loc_180023C66
0x180023c08  mov     r9d, r14d; bWait
0x180023c0b  lea     r8, [rsp+410h+BytesReturned]; lpNumberOfBytesTransferred
0x180023c10  lea     rdx, [rsp+410h+Overlapped]; lpOverlapped
0x180023c15  mov     rcx, rsi; hFile
0x180023c18  call    cs:__imp_GetOverlappedResult
0x180023c1f  nop     dword ptr [rax+rax+00h]
0x180023c24  test    eax, eax
0x180023c26  jnz     short loc_180023C98
0x180023c28  call    cs:__imp_GetLastError
0x180023c2f  nop     dword ptr [rax+rax+00h]
0x180023c34  mov     ebx, eax
0x180023c36  test    eax, eax
0x180023c38  jle     short loc_180023C43
0x180023c3a  movzx   ebx, ax
0x180023c3d  or      ebx, 80070000h
0x180023c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c4a  lea     rsi, WPP_GLOBAL_Control
0x180023c51  cmp     rcx, rsi
0x180023c54  jz      short loc_180023CA6
0x180023c56  cmp     byte ptr [rcx+19h], 3
0x180023c5a  jb      short loc_180023CA6
0x180023c5c  mov     edx, 17h
0x180023c61  jmp     loc_180023B90
0x180023c66  test    eax, eax
0x180023c68  jg      short loc_180023C6E
0x180023c6a  mov     ebx, eax
0x180023c6c  jmp     short loc_180023C77
0x180023c6e  movzx   ebx, ax
0x180023c71  or      ebx, 80070000h
0x180023c77  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c7e  lea     rsi, WPP_GLOBAL_Control
0x180023c85  cmp     rcx, rsi
0x180023c88  jz      short loc_180023CA6
0x180023c8a  cmp     byte ptr [rcx+19h], 3
0x180023c8e  jb      short loc_180023CA6
0x180023c90  mov     edx, r15d
0x180023c93  jmp     loc_180023B90
0x180023c98  lea     rsi, WPP_GLOBAL_Control
0x180023c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ca6  mov     rax, [rsp+410h+Overlapped.hEvent]
0x180023cab  test    rax, rax
0x180023cae  jz      short loc_180023CCC
0x180023cb0  mov     rcx, rax; hObject
0x180023cb3  call    cs:__imp_CloseHandle
0x180023cba  nop     dword ptr [rax+rax+00h]
0x180023cbf  and     [rsp+410h+Overlapped.hEvent], 0
0x180023cc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ccc  test    ebx, ebx
0x180023cce  jnz     loc_180023D54
0x180023cd4  lea     ecx, [rbx+6]
0x180023cd7  lea     edx, [rcx+7Ah]
0x180023cda  lea     rax, [rbp+310h+var_388]
0x180023cde  movups  xmm0, xmmword ptr [rax]
0x180023ce1  movups  xmm1, xmmword ptr [rax+10h]
0x180023ce5  movups  xmmword ptr [rdi], xmm0
0x180023ce8  movups  xmm0, xmmword ptr [rax+20h]
0x180023cec  movups  xmmword ptr [rdi+10h], xmm1
0x180023cf0  movups  xmm1, xmmword ptr [rax+30h]
0x180023cf4  movups  xmmword ptr [rdi+20h], xmm0
0x180023cf8  movups  xmm0, xmmword ptr [rax+40h]
0x180023cfc  movups  xmmword ptr [rdi+30h], xmm1
0x180023d00  movups  xmm1, xmmword ptr [rax+50h]
0x180023d04  movups  xmmword ptr [rdi+40h], xmm0
0x180023d08  movups  xmm0, xmmword ptr [rax+60h]
0x180023d0c  movups  xmmword ptr [rdi+50h], xmm1
0x180023d10  movups  xmm1, xmmword ptr [rax+70h]
0x180023d14  add     rax, rdx
0x180023d17  movups  xmmword ptr [rdi+60h], xmm0
0x180023d1b  add     rdi, rdx
0x180023d1e  movups  xmmword ptr [rdi-10h], xmm1
0x180023d22  sub     rcx, r14
0x180023d25  jnz     short loc_180023CDE
0x180023d27  movups  xmm0, xmmword ptr [rax]
0x180023d2a  movups  xmm1, xmmword ptr [rax+10h]
0x180023d2e  movups  xmmword ptr [rdi], xmm0
0x180023d31  movups  xmm0, xmmword ptr [rax+20h]
0x180023d35  movups  xmmword ptr [rdi+10h], xmm1
0x180023d39  movups  xmm1, xmmword ptr [rax+30h]
0x180023d3d  xor     eax, eax
0x180023d3f  movups  xmmword ptr [rdi+20h], xmm0
0x180023d43  movups  xmmword ptr [rdi+30h], xmm1
0x180023d47  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d4e  cmp     byte ptr [rcx+19h], 5
0x180023d52  jmp     short loc_180023D5A
0x180023d54  xor     eax, eax
0x180023d56  cmp     byte ptr [rcx+19h], 2
0x180023d5a  setnb   al
0x180023d5d  cmp     rcx, rsi
0x180023d60  jz      short loc_180023D7B
0x180023d62  test    eax, eax
0x180023d64  jz      short loc_180023D7B
0x180023d66  mov     rcx, [rcx+10h]
0x180023d6a  mov     edx, 19h
0x180023d6f  mov     r8, r13
0x180023d72  mov     dword ptr [rsp+410h+lpOutBuffer], ebx
0x180023d76  call    WPP_SF_sd
0x180023d7b  mov     eax, ebx
0x180023d7d  mov     rcx, [rbp+310h+var_40]
0x180023d84  xor     rcx, rsp; StackCookie
0x180023d87  call    __security_check_cookie
0x180023d8c  add     rsp, 3E0h
0x180023d93  pop     r15
0x180023d95  pop     r14
0x180023d97  pop     r13
0x180023d99  pop     rdi
0x180023d9a  pop     rsi
0x180023d9b  pop     rbx
0x180023d9c  pop     rbp
0x180023d9d  retn
```
