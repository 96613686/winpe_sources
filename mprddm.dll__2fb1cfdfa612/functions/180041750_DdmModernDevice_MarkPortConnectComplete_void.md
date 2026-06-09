# DdmModernDevice::MarkPortConnectComplete(void)

- ea: `0x180041750`
- end: `0x180041a95`
- name: `?MarkPortConnectComplete@DdmModernDevice@@UEAAKXZ`
- size: `837`
- prototype: `unsigned int __fastcall(DdmModernDevice *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180007c50`
- `0x180041750`
- `0x1800441d8`
- `0x180071cec`
- `0x180086ad0`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `msvcrt!_itow_s` at `0x18004180f`
- `msvcrt!_itow_s` at `0x1800418d2`
- `msvcrt!_itow_s` at `0x1800419cf`
- `msvcrt!_itow_s` at `0x180041a47`
- `msvcrt!_itow_s` at `0x18004180f`
- `msvcrt!_itow_s` at `0x1800418d2`
- `msvcrt!_itow_s` at `0x1800419cf`
- `msvcrt!_itow_s` at `0x180041a47`
- `KERNEL32!DeviceIoControl` at `0x180041991`
- `KERNEL32!DeviceIoControl` at `0x180041991`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180041a0d`
- `KERNEL32!PostQueuedCompletionStatus` at `0x180041a0d`
- `KERNEL32!GetLastError` at `0x18004189e`
- `KERNEL32!GetLastError` at `0x18004199b`
- `KERNEL32!GetLastError` at `0x180041a17`
- `KERNEL32!GetLastError` at `0x18004189e`
- `KERNEL32!GetLastError` at `0x18004199b`
- `KERNEL32!GetLastError` at `0x180041a17`

## string_xrefs

- `0x18004182f`: `MarkPortConnectComplete`
- `0x180041a4d`: `IO completion for PostRecvPkt failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall DdmModernDevice::MarkPortConnectComplete(DdmModernDevice *this)
{
  char v2; // dl
  int v3; // ecx
  int v4; // r8d
  __int64 v5; // rcx
  DWORD ID; // edi
  int v7; // ecx
  __int128 v8; // xmm0
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // ecx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t Buffer[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v16; // [rsp+5Ch] [rbp-A4h]
  __int128 v17; // [rsp+6Ch] [rbp-94h]
  int v18; // [rsp+7Ch] [rbp-84h]
  _QWORD OutBuffer[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h]
  __int64 v21; // [rsp+A0h] [rbp-60h]
  int v22; // [rsp+A8h] [rbp-58h]
  __int128 v23; // [rsp+ACh] [rbp-54h]
  _DWORD v24[5]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v25; // [rsp+D4h] [rbp-2Ch]
  int v26; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v27[2044]; // [rsp+134h] [rbp+34h] BYREF

  BytesReturned = 0;
  memset_0(v24, 0, 0x64u);
  memset_0(OutBuffer, 0, 0x40u);
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v2 = byte_1800C8404;
  *(_DWORD *)Buffer = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  v14 = 0;
  if ( (byte_1800C8404 & 0x10) != 0 )
  {
    Buffer[0] = 0;
    if ( this )
    {
      v3 = *((_DWORD *)this + 24);
      if ( v3 != -1 )
      {
        _itow_s(v3, Buffer, 0x14u, 10);
        v2 = byte_1800C8404;
      }
    }
    if ( (v2 & 0x10) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceInfo,
        (unsigned int)L"MarkPortConnectComplete",
        (unsigned int)&v14,
        0,
        (__int64)Buffer);
  }
  v4 = *((_DWORD *)this + 299);
  v5 = 312LL * *((int *)this + 303);
  v24[0] = 100;
  ID = RasLineGetID(*(int *)((char *)&dword_1800C8FFC + v5), (int)&dword_1800C8FFC, v4, 4, (wchar_t *)L"NDIS", v24);
  if ( ID )
  {
    ID = GetLastError();
    if ( (byte_1800C8404 & 8) == 0 )
      return ID;
    v7 = *((_DWORD *)this + 24);
    LOWORD(v26) = 0;
    Buffer[0] = 0;
    if ( v7 != -1 )
      _itow_s(v7, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v26, L"RasLineGetID failed with error 0x%x", ID);
    goto LABEL_12;
  }
  v8 = *(_OWORD *)((char *)this + 714);
  v9 = *(_QWORD *)((char *)v24 + v25);
  v20 = *((_QWORD *)this + 12);
  v21 = v20;
  OutBuffer[2] = v9;
  v22 = 16;
  v23 = v8;
  if ( !DeviceIoControl(gblDdmDriverInfo, 0x120000u, OutBuffer, 0x40u, OutBuffer, 0x40u, &BytesReturned, 0) )
  {
    ID = GetLastError();
    if ( (byte_1800C8404 & 8) == 0 )
      return ID;
    v10 = *((_DWORD *)this + 24);
    LOWORD(v26) = 0;
    Buffer[0] = 0;
    if ( v10 != -1 )
      _itow_s(v10, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v26, L"IOCTL_NDISWAN_MAP_CONNECTION_ID failed with error 0x%x", ID);
    goto LABEL_12;
  }
  *((_QWORD *)this + 14) = OutBuffer[0];
  *((_QWORD *)this + 15) = OutBuffer[1];
  if ( !byte_1800C8998 && !PostQueuedCompletionStatus(CompletionPort, 0, 0, &stru_1800C88F8) )
  {
    ID = GetLastError();
    if ( (byte_1800C8404 & 8) == 0 )
      return ID;
    v11 = *((_DWORD *)this + 24);
    LOWORD(v26) = 0;
    Buffer[0] = 0;
    if ( v11 != -1 )
      _itow_s(v11, Buffer, 0x14u, 10);
    FormatRRASErrorString(&v26, L"IO completion for PostRecvPkt failed with error 0x%x", ID);
LABEL_12:
    if ( (byte_1800C8404 & 8) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDdmParamTraceError,
        (unsigned int)&v26,
        (unsigned int)&v14,
        0,
        (__int64)Buffer);
    return ID;
  }
  if ( *((_WORD *)this + 68) == 9 )
    DdmModernDevice::SaveIPSecInfo(this);
  return ID;
}

```

## disassembly

```asm
0x180041750  mov     [rsp-8+arg_8], rbx
0x180041755  mov     [rsp-8+arg_10], rdi
0x18004175a  push    rbp
0x18004175b  push    r12
0x18004175d  push    r14
0x18004175f  lea     rbp, [rsp-840h]
0x180041767  sub     rsp, 940h
0x18004176e  mov     rax, cs:__security_cookie
0x180041775  xor     rax, rsp
0x180041778  mov     [rbp+850h+var_20], rax
0x18004177f  mov     rbx, rcx
0x180041782  mov     [rsp+950h+BytesReturned], 0
0x18004178a  mov     edi, 64h ; 'd'
0x18004178f  lea     rcx, [rbp+850h+var_890]; void *
0x180041793  mov     r8d, edi; Size
0x180041796  xor     edx, edx; Val
0x180041798  call    memset_0
0x18004179d  xor     edx, edx; Val
0x18004179f  lea     r8d, [rdi-24h]; Size
0x1800417a3  lea     rcx, [rbp+850h+OutBuffer]; void *
0x1800417a7  call    memset_0
0x1800417ac  xor     eax, eax
0x1800417ae  lea     rcx, [rbp+850h+var_81C]; void *
0x1800417b2  xor     edx, edx; Val
0x1800417b4  mov     [rbp+850h+var_820], eax
0x1800417b7  mov     r8d, 7FCh; Size
0x1800417bd  call    memset_0
0x1800417c2  mov     dl, cs:byte_1800C8404
0x1800417c8  lea     r12d, [rdi-50h]
0x1800417cc  xor     eax, eax
0x1800417ce  xorps   xmm0, xmm0
0x1800417d1  or      r14d, 0FFFFFFFFh
0x1800417d5  mov     dword ptr [rsp+950h+Buffer], eax
0x1800417d9  mov     [rsp+950h+var_8D4], eax
0x1800417dd  movups  [rsp+950h+var_8F4], xmm0
0x1800417e2  movups  [rsp+950h+var_8E4], xmm0
0x1800417e7  movups  [rsp+950h+var_908], xmm0
0x1800417ec  test    dl, 10h
0x1800417ef  jz      short loc_180041852
0x1800417f1  mov     [rsp+950h+Buffer], ax
0x1800417f6  test    rbx, rbx
0x1800417f9  jz      short loc_18004181B
0x1800417fb  mov     ecx, [rbx+60h]; Value
0x1800417fe  cmp     ecx, r14d
0x180041801  jz      short loc_18004181B
0x180041803  lea     r9d, [rdi-5Ah]; Radix
0x180041807  mov     r8d, r12d; BufferCount
0x18004180a  lea     rdx, [rsp+950h+Buffer]; Buffer
0x18004180f  call    cs:__imp__itow_s
0x180041815  mov     dl, cs:byte_1800C8404
0x18004181b  test    dl, 10h
0x18004181e  jz      short loc_180041852
0x180041820  lea     rax, [rsp+950h+Buffer]
0x180041825  mov     qword ptr [rsp+950h+nOutBufferSize], rax
0x18004182a  lea     r9, [rsp+950h+var_908]
0x18004182f  lea     r8, aMarkportconnec; "MarkPortConnectComplete"
0x180041836  mov     [rsp+950h+lpOutBuffer], 0
0x18004183f  lea     rdx, RasDdmParamTraceInfo
0x180041846  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004184d  call    McTemplateU0zjzz_EventWriteTransfer
0x180041852  movsxd  rax, dword ptr [rbx+4BCh]
0x180041859  lea     rdx, dword_1800C8FFC; int
0x180041860  mov     r8d, [rbx+4ACh]; int
0x180041867  mov     r9d, 4; int
0x18004186d  imul    rcx, rax, 138h
0x180041874  lea     rax, [rbp+850h+var_890]
0x180041878  mov     [rbp+850h+var_890], edi
0x18004187b  mov     qword ptr [rsp+950h+nOutBufferSize], rax; void *
0x180041880  lea     rax, aNdis; "NDIS"
0x180041887  mov     [rsp+950h+lpOutBuffer], rax; String1
0x18004188c  mov     ecx, [rcx+rdx]; int
0x18004188f  call    RasLineGetID
0x180041894  mov     edi, eax
0x180041896  test    eax, eax
0x180041898  jz      loc_18004192C
0x18004189e  call    cs:__imp_GetLastError
0x1800418a4  test    cs:byte_1800C8404, 8
0x1800418ab  mov     edi, eax
0x1800418ad  jz      loc_180041A6B
0x1800418b3  mov     ecx, [rbx+60h]; Value
0x1800418b6  xor     eax, eax
0x1800418b8  mov     word ptr [rbp+850h+var_820], ax
0x1800418bc  mov     [rsp+950h+Buffer], ax
0x1800418c1  cmp     ecx, r14d
0x1800418c4  jz      short loc_1800418D8
0x1800418c6  lea     r9d, [rax+0Ah]; Radix
0x1800418ca  mov     r8, r12; BufferCount
0x1800418cd  lea     rdx, [rsp+950h+Buffer]; Buffer
0x1800418d2  call    cs:__imp__itow_s
0x1800418d8  lea     rdx, aRaslinegetidFa; "RasLineGetID failed with error 0x%x"
0x1800418df  mov     r8d, edi
0x1800418e2  lea     rcx, [rbp+850h+var_820]
0x1800418e6  call    FormatRRASErrorString
0x1800418eb  test    cs:byte_1800C8404, 8
0x1800418f2  jz      loc_180041A6B
0x1800418f8  lea     rax, [rsp+950h+Buffer]
0x1800418fd  mov     qword ptr [rsp+950h+nOutBufferSize], rax
0x180041902  lea     r9, [rsp+950h+var_908]
0x180041907  lea     r8, [rbp+850h+var_820]
0x18004190b  mov     [rsp+950h+lpOutBuffer], 0
0x180041914  lea     rdx, RasDdmParamTraceError
0x18004191b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180041922  call    McTemplateU0zjzz_EventWriteTransfer
0x180041927  jmp     loc_180041A6B
0x18004192c  mov     eax, [rbp+850h+var_87C]
0x18004192f  lea     r8, [rbp+850h+OutBuffer]; lpInBuffer
0x180041933  movups  xmm0, xmmword ptr [rbx+2CAh]
0x18004193a  mov     [rsp+950h+lpOverlapped], 0; lpOverlapped
0x180041943  mov     r9d, 40h ; '@'; nInBufferSize
0x180041949  mov     edx, 120000h; dwIoControlCode
0x18004194e  mov     rcx, qword ptr [rbp+rax+850h+var_890]
0x180041953  mov     rax, [rbx+60h]
0x180041957  mov     [rbp+850h+var_8B8], rax
0x18004195b  mov     [rbp+850h+var_8B0], rax
0x18004195f  lea     rax, [rsp+950h+BytesReturned]
0x180041964  mov     [rsp+950h+lpBytesReturned], rax; lpBytesReturned
0x180041969  lea     rax, [rbp+850h+OutBuffer]
0x18004196d  mov     [rbp+850h+var_8C0], rcx
0x180041971  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180041978  mov     [rsp+950h+nOutBufferSize], 40h ; '@'; nOutBufferSize
0x180041980  mov     [rsp+950h+lpOutBuffer], rax; lpOutBuffer
0x180041985  mov     [rbp+850h+var_8A8], 10h
0x18004198c  movdqu  [rbp+850h+var_8A4], xmm0
0x180041991  call    cs:__imp_DeviceIoControl
0x180041997  test    eax, eax
0x180041999  jnz     short loc_1800419E1
0x18004199b  call    cs:__imp_GetLastError
0x1800419a1  test    cs:byte_1800C8404, 8
0x1800419a8  mov     edi, eax
0x1800419aa  jz      loc_180041A6B
0x1800419b0  mov     ecx, [rbx+60h]; Value
0x1800419b3  xor     eax, eax
0x1800419b5  mov     word ptr [rbp+850h+var_820], ax
0x1800419b9  mov     [rsp+950h+Buffer], ax
0x1800419be  cmp     ecx, r14d
0x1800419c1  jz      short loc_1800419D5
0x1800419c3  lea     r9d, [rax+0Ah]; Radix
0x1800419c7  mov     r8, r12; BufferCount
0x1800419ca  lea     rdx, [rsp+950h+Buffer]; Buffer
0x1800419cf  call    cs:__imp__itow_s
0x1800419d5  lea     rdx, aIoctlNdiswanMa; "IOCTL_NDISWAN_MAP_CONNECTION_ID failed "...
0x1800419dc  jmp     loc_1800418DF
0x1800419e1  mov     rax, [rbp+850h+OutBuffer]
0x1800419e5  mov     [rbx+70h], rax
0x1800419e9  mov     rax, [rbp+850h+var_8C8]
0x1800419ed  mov     [rbx+78h], rax
0x1800419f1  cmp     cs:byte_1800C8998, 0
0x1800419f8  jnz     short loc_180041A59
0x1800419fa  mov     rcx, cs:CompletionPort; CompletionPort
0x180041a01  lea     r9, stru_1800C88F8; lpOverlapped
0x180041a08  xor     r8d, r8d; dwCompletionKey
0x180041a0b  xor     edx, edx; dwNumberOfBytesTransferred
0x180041a0d  call    cs:__imp_PostQueuedCompletionStatus
0x180041a13  test    eax, eax
0x180041a15  jnz     short loc_180041A59
0x180041a17  call    cs:__imp_GetLastError
0x180041a1d  test    cs:byte_1800C8404, 8
0x180041a24  mov     edi, eax
0x180041a26  jz      short loc_180041A6B
0x180041a28  mov     ecx, [rbx+60h]; Value
0x180041a2b  xor     eax, eax
0x180041a2d  mov     word ptr [rbp+850h+var_820], ax
0x180041a31  mov     [rsp+950h+Buffer], ax
0x180041a36  cmp     ecx, r14d
0x180041a39  jz      short loc_180041A4D
0x180041a3b  lea     r9d, [rax+0Ah]; Radix
0x180041a3f  mov     r8, r12; BufferCount
0x180041a42  lea     rdx, [rsp+950h+Buffer]; Buffer
0x180041a47  call    cs:__imp__itow_s
0x180041a4d  lea     rdx, aIoCompletionFo; "IO completion for PostRecvPkt failed wi"...
0x180041a54  jmp     loc_1800418DF
0x180041a59  cmp     word ptr [rbx+88h], 9
0x180041a61  jnz     short loc_180041A6B
0x180041a63  mov     rcx, rbx; this
0x180041a66  call    ?SaveIPSecInfo@DdmModernDevice@@QEAAXXZ; DdmModernDevice::SaveIPSecInfo(void)
0x180041a6b  mov     eax, edi
0x180041a6d  mov     rcx, [rbp+850h+var_20]
0x180041a74  xor     rcx, rsp; StackCookie
0x180041a77  call    __security_check_cookie
0x180041a7c  lea     r11, [rsp+950h+var_10]
0x180041a84  mov     rbx, [r11+28h]
0x180041a88  mov     rdi, [r11+30h]
0x180041a8c  mov     rsp, r11
0x180041a8f  pop     r14
0x180041a91  pop     r12
0x180041a93  pop     rbp
0x180041a94  retn
```
