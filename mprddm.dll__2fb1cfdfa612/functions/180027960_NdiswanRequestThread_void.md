# NdiswanRequestThread(void *)

- ea: `0x180027960`
- end: `0x180027d98`
- name: `?NdiswanRequestThread@@YAKPEAX@Z`
- size: `1080`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ba6`
- `0x180007b7c`
- `0x180026bf0`
- `0x180026cc0`
- `0x180027960`
- `0x180028490`
- `0x18003b7a8`
- `0x18003b8f4`
- `0x180046d6c`
- `0x1800478f8`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180027d75`
- `KERNEL32!DeleteCriticalSection` at `0x180027d75`
- `KERNEL32!DeviceIoControl` at `0x180027a85`
- `KERNEL32!DeviceIoControl` at `0x180027a85`
- `KERNEL32!InitializeCriticalSection` at `0x18002799c`
- `KERNEL32!InitializeCriticalSection` at `0x18002799c`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180027d46`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180027d46`
- `KERNEL32!GetOverlappedResult` at `0x180027c19`
- `KERNEL32!GetOverlappedResult` at `0x180027c19`
- `KERNEL32!CloseHandle` at `0x180027d61`
- `KERNEL32!CloseHandle` at `0x180027d61`
- `KERNEL32!GetLastError` at `0x180027a93`
- `KERNEL32!GetLastError` at `0x180027cd5`
- `KERNEL32!GetLastError` at `0x180027d54`
- `KERNEL32!GetLastError` at `0x180027a93`
- `KERNEL32!GetLastError` at `0x180027cd5`
- `KERNEL32!GetLastError` at `0x180027d54`
- `KERNEL32!LeaveCriticalSection` at `0x180027d1b`
- `KERNEL32!LeaveCriticalSection` at `0x180027d1b`
- `KERNEL32!LocalAlloc` at `0x180027c84`
- `KERNEL32!LocalAlloc` at `0x180027c84`
- `KERNEL32!EnterCriticalSection` at `0x180027be7`
- `KERNEL32!EnterCriticalSection` at `0x180027be7`

## string_xrefs

- `0x180027a12`: `DdmGetProtocolEvent`
- `0x180027ab2`: `IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed with error 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NdiswanRequestThread(PVOID Parameter)
{
  int Internal; // edx
  int v2; // edx
  int v3; // edx
  __int64 v4; // r8
  DWORD LastError; // eax
  DWORD v6; // ebx
  __int64 v7; // r8
  __int64 v8; // rax
  char *v9; // rcx
  _OWORD *v10; // rax
  __int64 v11; // rdx
  struct DdmNotificationHandler *Instance; // rax
  volatile signed __int32 *v13; // rbx
  struct DdmDeviceTable *v14; // rax
  HLOCAL v15; // rax
  HLOCAL v16; // rdi
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v19; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-B0h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  char v24[8]; // [rsp+80h] [rbp-80h] BYREF
  char v25; // [rsp+88h] [rbp-78h] BYREF
  _BYTE OutBuffer[272]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v27; // [rsp+2A0h] [rbp+1A0h] BYREF
  const wchar_t *v28; // [rsp+2B0h] [rbp+1B0h]
  __int64 v29; // [rsp+2B8h] [rbp+1B8h]
  int v30; // [rsp+2C0h] [rbp+1C0h] BYREF
  char v31[2044]; // [rsp+2C4h] [rbp+1C4h] BYREF

  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  InitializeCriticalSection(&stru_1800C8970);
  while ( GetQueuedCompletionStatus(CompletionPort, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
  {
    Internal = Overlapped[1].Internal;
    if ( !Internal )
      goto LABEL_35;
    v2 = Internal - 1;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        if ( v3 == 1 )
        {
          memset_0(OutBuffer, 0, 0x104u);
          BytesReturned = 0;
          v30 = 0;
          memset_0(v31, 0, sizeof(v31));
          LOBYTE(v19) = byte_1800C8404 & 0x10;
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            v28 = L"DdmGetProtocolEvent";
            v29 = 40;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v4, 2, &v27);
          }
          if ( DeviceIoControl(gblDdmDriverInfo, 0x1200A0u, 0, 0, OutBuffer, 0x104u, &BytesReturned, 0) )
            goto LABEL_15;
          LastError = GetLastError();
          v6 = LastError;
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v30) = 0;
            FormatRRASErrorString(&v30, L"IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed with error 0x%x", LastError);
            if ( (byte_1800C8404 & 8) != 0 )
            {
              v8 = -1;
              do
                ++v8;
              while ( *(_WORD *)&v31[2 * v8 - 4] );
              v28 = (const wchar_t *)&v30;
              v29 = (unsigned int)(2 * v8 + 2);
              McGenEventWrite_EventWriteTransfer(
                &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                RasDdmTraceError,
                v7,
                2,
                &v27);
            }
          }
          if ( !v6 )
          {
LABEL_15:
            v23[0] = 9;
            v23[1] = 0;
            memset_0(v24, 0, 0x110u);
            v9 = &v25;
            v10 = OutBuffer;
            v11 = 2;
            do
            {
              *(_OWORD *)v9 = *v10;
              *((_OWORD *)v9 + 1) = v10[1];
              *((_OWORD *)v9 + 2) = v10[2];
              *((_OWORD *)v9 + 3) = v10[3];
              *((_OWORD *)v9 + 4) = v10[4];
              *((_OWORD *)v9 + 5) = v10[5];
              *((_OWORD *)v9 + 6) = v10[6];
              *((_OWORD *)v9 + 7) = v10[7];
              v9 += 128;
              v10 += 8;
              --v11;
            }
            while ( v11 );
            *(_DWORD *)v9 = *(_DWORD *)v10;
            v19 = (volatile signed __int32 *)v23;
            Instance = DdmNotificationHandler::GetInstance();
            DdmNotificationHandler::ProcessMessage(Instance, 2, &v19);
          }
          DdmSetProtocolEvent();
        }
      }
      else
      {
        EnterCriticalSection(&stru_1800C8970);
        BytesReturned = 0;
        v13 = 0;
        v19 = 0;
        v27 = 0;
        if ( !GetOverlappedResult(gblDdmDriverInfo, &stru_1800C89A0, &BytesReturned, 0) )
          goto LABEL_25;
        byte_1800C8998 = 0;
        if ( BytesReturned )
        {
          ++dword_1800C899C;
          if ( (_WORD)xmmword_1800C89E8 != 0xABB2 )
          {
            v14 = DdmDeviceTable::GetInstance(0x11u);
            DdmDeviceTable::FindDevice(v14, *((_QWORD *)&xmmword_1800C89D8 + 1), &v19);
            v13 = v19;
            if ( v19 )
            {
              v15 = LocalAlloc(0x40u, WORD2(xmmword_1800C89E8));
              v16 = v15;
              if ( !v15 )
              {
LABEL_25:
                GetLastError();
                goto LABEL_26;
              }
              memcpy_0(v15, (char *)&xmmword_1800C89E8 + 8, WORD2(xmmword_1800C89E8));
              LODWORD(v27) = WORD2(xmmword_1800C89E8);
              *((_QWORD *)&v27 + 1) = v16;
              DdmNotifyCaller(*((_QWORD *)v13 + 12), 0, 8, &v27);
            }
          }
        }
LABEL_26:
        if ( v13 && _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v13)(v13, 1);
        if ( !byte_1800C8998 )
          PostReceivePacketBuffer();
        LeaveCriticalSection(&stru_1800C8970);
      }
    }
    else
    {
      PostReceivePacketBuffer();
    }
  }
  GetLastError();
LABEL_35:
  CloseHandle(CompletionPort);
  CompletionPort = 0;
  DeleteCriticalSection(&stru_1800C8970);
  return 0;
}

```

## disassembly

```asm
0x180027960  push    rbp
0x180027962  push    rbx
0x180027963  push    rsi
0x180027964  push    rdi
0x180027965  lea     rbp, [rsp-9D8h]
0x18002796d  sub     rsp, 0AD8h
0x180027974  mov     rax, cs:__security_cookie
0x18002797b  xor     rax, rsp
0x18002797e  mov     [rbp+9F0h+var_30], rax
0x180027985  xor     esi, esi
0x180027987  mov     [rsp+0AF0h+NumberOfBytesTransferred], esi
0x18002798b  mov     [rsp+0AF0h+CompletionKey], rsi
0x180027990  mov     [rsp+0AF0h+Overlapped], rsi
0x180027995  lea     rcx, stru_1800C8970; lpCriticalSection
0x18002799c  call    cs:__imp_InitializeCriticalSection
0x1800279a2  jmp     loc_180027D28
0x1800279a7  mov     rcx, [rsp+0AF0h+Overlapped]
0x1800279ac  mov     edx, [rcx+20h]
0x1800279af  test    edx, edx
0x1800279b1  jz      loc_180027D5A
0x1800279b7  sub     edx, 1
0x1800279ba  jz      loc_180027D23
0x1800279c0  sub     edx, 1
0x1800279c3  jz      loc_180027BE0
0x1800279c9  cmp     edx, 1
0x1800279cc  jnz     loc_180027D28
0x1800279d2  xor     edx, edx; Val
0x1800279d4  mov     r8d, 104h; Size
0x1800279da  lea     rcx, [rbp+9F0h+OutBuffer]; void *
0x1800279e1  call    memset_0
0x1800279e6  mov     [rsp+0AF0h+BytesReturned], esi
0x1800279ea  mov     [rbp+9F0h+var_830], esi
0x1800279f0  xor     edx, edx; Val
0x1800279f2  mov     r8d, 7FCh; Size
0x1800279f8  lea     rcx, [rbp+9F0h+var_82C]; void *
0x1800279ff  call    memset_0
0x180027a04  mov     al, cs:byte_1800C8404
0x180027a0a  and     al, 10h
0x180027a0c  mov     byte ptr [rsp+0AF0h+var_AA8], al
0x180027a10  jz      short loc_180027A50
0x180027a12  lea     rax, aDdmgetprotocol_1; "DdmGetProtocolEvent"
0x180027a19  mov     [rbp+9F0h+var_840], rax
0x180027a20  mov     [rbp+9F0h+var_838], 28h ; '('
0x180027a2b  lea     rax, [rbp+9F0h+var_850]
0x180027a32  mov     [rsp+0AF0h+lpOutBuffer], rax
0x180027a37  mov     r9d, 2
0x180027a3d  lea     rdx, RasDdmTraceInfo
0x180027a44  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180027a4b  call    McGenEventWrite_EventWriteTransfer
0x180027a50  mov     [rsp+0AF0h+lpOverlapped], rsi; lpOverlapped
0x180027a55  lea     rax, [rsp+0AF0h+BytesReturned]
0x180027a5a  mov     [rsp+0AF0h+lpBytesReturned], rax; lpBytesReturned
0x180027a5f  mov     [rsp+0AF0h+nOutBufferSize], 104h; nOutBufferSize
0x180027a67  lea     rax, [rbp+9F0h+OutBuffer]
0x180027a6e  mov     [rsp+0AF0h+lpOutBuffer], rax; lpOutBuffer
0x180027a73  xor     r9d, r9d; nInBufferSize
0x180027a76  xor     r8d, r8d; lpInBuffer
0x180027a79  mov     edx, 1200A0h; dwIoControlCode
0x180027a7e  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hDevice
0x180027a85  call    cs:__imp_DeviceIoControl
0x180027a8b  test    eax, eax
0x180027a8d  jnz     loc_180027B30
0x180027a93  call    cs:__imp_GetLastError
0x180027a99  mov     ebx, eax
0x180027a9b  test    cs:byte_1800C8404, 8
0x180027aa2  jz      loc_180027B28
0x180027aa8  mov     word ptr [rbp+9F0h+var_830], si
0x180027aaf  mov     r8d, eax
0x180027ab2  lea     rdx, aIoctlNdiswanGe_1; "IOCTL_NDISWAN_GET_PROTOCOL_EVENT failed"...
0x180027ab9  lea     rcx, [rbp+9F0h+var_830]
0x180027ac0  call    FormatRRASErrorString
0x180027ac5  test    cs:byte_1800C8404, 8
0x180027acc  jz      short loc_180027B28
0x180027ace  lea     rcx, [rbp+9F0h+var_830]
0x180027ad5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027ad9  inc     rax
0x180027adc  cmp     [rcx+rax*2], si
0x180027ae0  jnz     short loc_180027AD9
0x180027ae2  lea     eax, ds:2[rax*2]
0x180027ae9  lea     rcx, [rbp+9F0h+var_830]
0x180027af0  mov     [rbp+9F0h+var_840], rcx
0x180027af7  mov     dword ptr [rbp+9F0h+var_838], eax
0x180027afd  mov     dword ptr [rbp+9F0h+var_838+4], esi
0x180027b03  lea     rax, [rbp+9F0h+var_850]
0x180027b0a  mov     [rsp+0AF0h+lpOutBuffer], rax
0x180027b0f  mov     r9d, 2
0x180027b15  lea     rdx, RasDdmTraceError
0x180027b1c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180027b23  call    McGenEventWrite_EventWriteTransfer
0x180027b28  test    ebx, ebx
0x180027b2a  jnz     loc_180027BD6
0x180027b30  mov     [rsp+0AF0h+var_A80], 9
0x180027b39  mov     [rsp+0AF0h+var_A78], rsi
0x180027b3e  xor     edx, edx; Val
0x180027b40  mov     r8d, 110h; Size
0x180027b46  lea     rcx, [rbp+9F0h+var_A70]; void *
0x180027b4a  call    memset_0
0x180027b4f  lea     rcx, [rbp+9F0h+var_A68]
0x180027b53  lea     rax, [rbp+9F0h+OutBuffer]
0x180027b5a  mov     edx, 2
0x180027b5f  movups  xmm0, xmmword ptr [rax]
0x180027b62  movups  xmmword ptr [rcx], xmm0
0x180027b65  movups  xmm1, xmmword ptr [rax+10h]
0x180027b69  movups  xmmword ptr [rcx+10h], xmm1
0x180027b6d  movups  xmm0, xmmword ptr [rax+20h]
0x180027b71  movups  xmmword ptr [rcx+20h], xmm0
0x180027b75  movups  xmm1, xmmword ptr [rax+30h]
0x180027b79  movups  xmmword ptr [rcx+30h], xmm1
0x180027b7d  movups  xmm0, xmmword ptr [rax+40h]
0x180027b81  movups  xmmword ptr [rcx+40h], xmm0
0x180027b85  movups  xmm1, xmmword ptr [rax+50h]
0x180027b89  movups  xmmword ptr [rcx+50h], xmm1
0x180027b8d  movups  xmm0, xmmword ptr [rax+60h]
0x180027b91  movups  xmmword ptr [rcx+60h], xmm0
0x180027b95  movups  xmm1, xmmword ptr [rax+70h]
0x180027b99  movups  xmmword ptr [rcx+70h], xmm1
0x180027b9d  lea     rcx, [rcx+80h]
0x180027ba4  lea     rax, [rax+80h]
0x180027bab  sub     rdx, 1
0x180027baf  jnz     short loc_180027B5F
0x180027bb1  mov     eax, [rax]
0x180027bb3  mov     [rcx], eax
0x180027bb5  lea     rax, [rsp+0AF0h+var_A80]
0x180027bba  mov     [rsp+0AF0h+var_AA8], rax
0x180027bbf  call    ?GetInstance@DdmNotificationHandler@@SAPEAV1@XZ; DdmNotificationHandler::GetInstance(void)
0x180027bc4  lea     r8, [rsp+0AF0h+var_AA8]
0x180027bc9  mov     edx, 2
0x180027bce  mov     rcx, rax
0x180027bd1  call    ?ProcessMessage@DdmNotificationHandler@@QEAAKW4_MESSAGEQ_ID@@AEAT_MESSAGE@@@Z; DdmNotificationHandler::ProcessMessage(_MESSAGEQ_ID,_MESSAGE &)
0x180027bd6  call    ?DdmSetProtocolEvent@@YAKXZ; DdmSetProtocolEvent(void)
0x180027bdb  jmp     loc_180027D28
0x180027be0  lea     rcx, stru_1800C8970; lpCriticalSection
0x180027be7  call    cs:__imp_EnterCriticalSection
0x180027bed  mov     [rsp+0AF0h+BytesReturned], esi
0x180027bf1  mov     rbx, rsi
0x180027bf4  mov     [rsp+0AF0h+var_AA8], rbx
0x180027bf9  xorps   xmm0, xmm0
0x180027bfc  movups  [rbp+9F0h+var_850], xmm0
0x180027c03  xor     r9d, r9d; bWait
0x180027c06  lea     r8, [rsp+0AF0h+BytesReturned]; lpNumberOfBytesTransferred
0x180027c0b  lea     rdx, stru_1800C89A0; lpOverlapped
0x180027c12  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hFile
0x180027c19  call    cs:__imp_GetOverlappedResult
0x180027c1f  test    eax, eax
0x180027c21  jz      loc_180027CD5
0x180027c27  mov     cs:byte_1800C8998, sil
0x180027c2e  cmp     [rsp+0AF0h+BytesReturned], esi
0x180027c32  jz      loc_180027CDC
0x180027c38  inc     cs:dword_1800C899C
0x180027c3e  mov     eax, 0ABB2h
0x180027c43  cmp     ax, word ptr cs:xmmword_1800C89E8
0x180027c4a  jz      loc_180027CDC
0x180027c50  mov     ecx, 11h; unsigned int
0x180027c55  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180027c5a  lea     r8, [rsp+0AF0h+var_AA8]
0x180027c5f  mov     rdx, qword ptr cs:xmmword_1800C89D8+8
0x180027c66  mov     rcx, rax
0x180027c69  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180027c6e  mov     rbx, [rsp+0AF0h+var_AA8]
0x180027c73  test    rbx, rbx
0x180027c76  jz      short loc_180027CDC
0x180027c78  movzx   edx, word ptr cs:xmmword_1800C89E8+4; uBytes
0x180027c7f  mov     ecx, 40h ; '@'; uFlags
0x180027c84  call    cs:__imp_LocalAlloc
0x180027c8a  mov     rdi, rax
0x180027c8d  test    rax, rax
0x180027c90  jz      short loc_180027CD5
0x180027c92  movzx   r8d, word ptr cs:xmmword_1800C89E8+4; Size
0x180027c9a  lea     rdx, xmmword_1800C89E8+8; Src
0x180027ca1  mov     rcx, rax; void *
0x180027ca4  call    memcpy_0
0x180027ca9  movzx   ecx, word ptr cs:xmmword_1800C89E8+4
0x180027cb0  mov     dword ptr [rbp+9F0h+var_850], ecx
0x180027cb6  mov     qword ptr [rbp+9F0h+var_850+8], rdi
0x180027cbd  lea     r9, [rbp+9F0h+var_850]
0x180027cc4  xor     edx, edx
0x180027cc6  lea     r8d, [rdx+8]
0x180027cca  mov     rcx, [rbx+60h]
0x180027cce  call    ?DdmNotifyCaller@@YAXPEAXKW4_DDM_DRIVER_NOTIFICATION_MSG_ID@@0@Z; DdmNotifyCaller(void *,ulong,_DDM_DRIVER_NOTIFICATION_MSG_ID,void *)
0x180027cd3  jmp     short loc_180027CDC
0x180027cd5  call    cs:__imp_GetLastError
0x180027cdb  nop
0x180027cdc  test    rbx, rbx
0x180027cdf  jz      short loc_180027D06
0x180027ce1  or      eax, 0FFFFFFFFh
0x180027ce4  lock xadd [rbx+8], eax
0x180027ce9  cmp     eax, 1
0x180027cec  jnz     short loc_180027D06
0x180027cee  test    rbx, rbx
0x180027cf1  jz      short loc_180027D06
0x180027cf3  mov     rax, [rbx]
0x180027cf6  mov     edx, 1
0x180027cfb  mov     rcx, rbx
0x180027cfe  mov     rax, [rax]
0x180027d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d06  cmp     cs:byte_1800C8998, sil
0x180027d0d  jnz     short loc_180027D14
0x180027d0f  call    ?PostReceivePacketBuffer@@YAKXZ; PostReceivePacketBuffer(void)
0x180027d14  lea     rcx, stru_1800C8970; lpCriticalSection
0x180027d1b  call    cs:__imp_LeaveCriticalSection
0x180027d21  jmp     short loc_180027D28
0x180027d23  call    ?PostReceivePacketBuffer@@YAKXZ; PostReceivePacketBuffer(void)
0x180027d28  mov     dword ptr [rsp+0AF0h+lpOutBuffer], 0FFFFFFFFh; dwMilliseconds
0x180027d30  lea     r9, [rsp+0AF0h+Overlapped]; lpOverlapped
0x180027d35  lea     r8, [rsp+0AF0h+CompletionKey]; lpCompletionKey
0x180027d3a  lea     rdx, [rsp+0AF0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180027d3f  mov     rcx, cs:CompletionPort; CompletionPort
0x180027d46  call    cs:__imp_GetQueuedCompletionStatus
0x180027d4c  test    eax, eax
0x180027d4e  jnz     loc_1800279A7
0x180027d54  call    cs:__imp_GetLastError
0x180027d5a  mov     rcx, cs:CompletionPort; hObject
0x180027d61  call    cs:__imp_CloseHandle
0x180027d67  mov     cs:CompletionPort, rsi
0x180027d6e  lea     rcx, stru_1800C8970; lpCriticalSection
0x180027d75  call    cs:__imp_DeleteCriticalSection
0x180027d7b  xor     eax, eax
0x180027d7d  mov     rcx, [rbp+9F0h+var_30]
0x180027d84  xor     rcx, rsp; StackCookie
0x180027d87  call    __security_check_cookie
0x180027d8c  add     rsp, 0AD8h
0x180027d93  pop     rdi
0x180027d94  pop     rsi
0x180027d95  pop     rbx
0x180027d96  pop     rbp
0x180027d97  retn
```
