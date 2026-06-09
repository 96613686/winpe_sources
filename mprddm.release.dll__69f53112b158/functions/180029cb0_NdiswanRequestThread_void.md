# NdiswanRequestThread(void *)

- ea: `0x180029cb0`
- end: `0x180029ff0`
- name: `?NdiswanRequestThread@@YAKPEAX@Z`
- size: `832`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002be6`
- `0x1800287b4`
- `0x180028e90`
- `0x180028f60`
- `0x180029cb0`
- `0x18002a6b8`
- `0x18003d100`
- `0x18003d278`
- `0x180047e94`
- `0x180048a4c`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180029fbd`
- `KERNEL32!DeleteCriticalSection` at `0x180029fbd`
- `KERNEL32!InitializeCriticalSection` at `0x180029cf3`
- `KERNEL32!InitializeCriticalSection` at `0x180029cf3`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180029f7b`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180029f7b`
- `KERNEL32!GetOverlappedResult` at `0x180029e45`
- `KERNEL32!GetOverlappedResult` at `0x180029e45`
- `KERNEL32!CloseHandle` at `0x180029fa2`
- `KERNEL32!CloseHandle` at `0x180029fa2`
- `KERNEL32!GetLastError` at `0x180029f04`
- `KERNEL32!GetLastError` at `0x180029f8f`
- `KERNEL32!GetLastError` at `0x180029f04`
- `KERNEL32!GetLastError` at `0x180029f8f`
- `KERNEL32!LeaveCriticalSection` at `0x180029f4d`
- `KERNEL32!LeaveCriticalSection` at `0x180029f4d`
- `KERNEL32!LocalAlloc` at `0x180029eb3`
- `KERNEL32!LocalAlloc` at `0x180029eb3`
- `KERNEL32!EnterCriticalSection` at `0x180029e0f`
- `KERNEL32!EnterCriticalSection` at `0x180029e0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NdiswanRequestThread(PVOID Parameter)
{
  int Internal; // edx
  int v2; // edx
  int v3; // edx
  char *v4; // rcx
  _OWORD *v5; // rax
  __int64 v6; // rdx
  struct DdmNotificationHandler *Instance; // rax
  volatile signed __int32 *v8; // rbx
  struct DdmDeviceTable *v9; // rax
  HLOCAL v10; // rax
  HLOCAL v11; // rdi
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v14; // [rsp+34h] [rbp-CCh] BYREF
  volatile signed __int32 *v15; // [rsp+38h] [rbp-C8h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 CompletionKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v19; // [rsp+58h] [rbp-A8h]
  _QWORD v20[2]; // [rsp+70h] [rbp-90h] BYREF
  char v21[8]; // [rsp+80h] [rbp-80h] BYREF
  char v22; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v23[272]; // [rsp+190h] [rbp+90h] BYREF

  v14 = 0;
  CompletionKey = 0;
  Overlapped = 0;
  InitializeCriticalSection(&stru_1800CF970);
  while ( GetQueuedCompletionStatus(CompletionPort, &v14, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
  {
    Internal = Overlapped[1].Internal;
    if ( !Internal )
      goto LABEL_27;
    v2 = Internal - 1;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        if ( v3 == 1 )
        {
          memset_0(v23, 0, 0x104u);
          if ( !DdmGetProtocolEvent((struct _NDISWAN_GET_PROTOCOL_EVENT *)v23) )
          {
            v20[0] = 9;
            v20[1] = 0;
            memset_0(v21, 0, 0x110u);
            v4 = &v22;
            v5 = v23;
            v6 = 2;
            do
            {
              *(_OWORD *)v4 = *v5;
              *((_OWORD *)v4 + 1) = v5[1];
              *((_OWORD *)v4 + 2) = v5[2];
              *((_OWORD *)v4 + 3) = v5[3];
              *((_OWORD *)v4 + 4) = v5[4];
              *((_OWORD *)v4 + 5) = v5[5];
              *((_OWORD *)v4 + 6) = v5[6];
              v4 += 128;
              *((_OWORD *)v4 - 1) = v5[7];
              v5 += 8;
              --v6;
            }
            while ( v6 );
            *(_DWORD *)v4 = *(_DWORD *)v5;
            v18 = v20;
            Instance = DdmNotificationHandler::GetInstance();
            DdmNotificationHandler::ProcessMessage(Instance, 2, &v18);
          }
          DdmSetProtocolEvent();
        }
      }
      else
      {
        EnterCriticalSection(&stru_1800CF970);
        NumberOfBytesTransferred = 0;
        v8 = 0;
        v15 = 0;
        v19 = 0;
        if ( !GetOverlappedResult(gblDdmDriverInfo, &stru_1800CF9A0, &NumberOfBytesTransferred, 0) )
          goto LABEL_17;
        byte_1800CF998 = 0;
        if ( NumberOfBytesTransferred )
        {
          ++dword_1800CF99C;
          if ( (_WORD)xmmword_1800CF9E8 != 0xABB2 )
          {
            v9 = DdmDeviceTable::GetInstance(0x11u);
            DdmDeviceTable::FindDevice(v9, *((_QWORD *)&xmmword_1800CF9D8 + 1), &v15);
            v8 = v15;
            if ( v15 )
            {
              v10 = LocalAlloc(0x40u, WORD2(xmmword_1800CF9E8));
              v11 = v10;
              if ( !v10 )
              {
LABEL_17:
                GetLastError();
                goto LABEL_18;
              }
              memcpy_0(v10, (char *)&xmmword_1800CF9E8 + 8, WORD2(xmmword_1800CF9E8));
              LODWORD(v19) = WORD2(xmmword_1800CF9E8);
              *((_QWORD *)&v19 + 1) = v11;
              DdmNotifyCaller(*((_QWORD *)v8 + 12), 0, 8);
            }
          }
        }
LABEL_18:
        if ( v8 && _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
          (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v15)(v15, 1);
        if ( !byte_1800CF998 )
          PostReceivePacketBuffer();
        LeaveCriticalSection(&stru_1800CF970);
      }
    }
    else
    {
      PostReceivePacketBuffer();
    }
  }
  GetLastError();
LABEL_27:
  CloseHandle(CompletionPort);
  CompletionPort = 0;
  DeleteCriticalSection(&stru_1800CF970);
  return 0;
}

```

## disassembly

```asm
0x180029cb0  mov     [rsp-8+arg_0], rbx
0x180029cb5  mov     [rsp-8+arg_8], rdi
0x180029cba  push    rbp
0x180029cbb  lea     rbp, [rsp-1B0h]
0x180029cc3  sub     rsp, 2B0h
0x180029cca  mov     rax, cs:__security_cookie
0x180029cd1  xor     rax, rsp
0x180029cd4  mov     [rbp+1B0h+var_10], rax
0x180029cdb  and     [rsp+2B0h+var_27C], 0
0x180029ce0  and     [rsp+2B0h+CompletionKey], 0
0x180029ce6  and     [rsp+2B0h+Overlapped], 0
0x180029cec  lea     rcx, stru_1800CF970; lpCriticalSection
0x180029cf3  call    cs:__imp_InitializeCriticalSection
0x180029cfa  nop     dword ptr [rax+rax+00h]
0x180029cff  jmp     loc_180029F60
0x180029d04  mov     rcx, [rsp+2B0h+Overlapped]
0x180029d09  mov     edx, [rcx+20h]
0x180029d0c  test    edx, edx
0x180029d0e  jz      loc_180029F9B
0x180029d14  sub     edx, 1
0x180029d17  jz      loc_180029F5B
0x180029d1d  sub     edx, 1
0x180029d20  jz      loc_180029E08
0x180029d26  cmp     edx, 1
0x180029d29  jnz     loc_180029F60
0x180029d2f  xor     edx, edx; Val
0x180029d31  mov     r8d, 104h; Size
0x180029d37  lea     rcx, [rbp+1B0h+var_120]; void *
0x180029d3e  call    memset_0
0x180029d43  lea     rcx, [rbp+1B0h+var_120]; lpOutBuffer
0x180029d4a  call    ?DdmGetProtocolEvent@@YAKPEAU_NDISWAN_GET_PROTOCOL_EVENT@@@Z; DdmGetProtocolEvent(_NDISWAN_GET_PROTOCOL_EVENT *)
0x180029d4f  test    eax, eax
0x180029d51  jnz     loc_180029DFE
0x180029d57  mov     [rsp+2B0h+var_240], 9
0x180029d60  and     [rsp+2B0h+var_238], 0
0x180029d66  xor     edx, edx; Val
0x180029d68  mov     r8d, 110h; Size
0x180029d6e  lea     rcx, [rbp+1B0h+var_230]; void *
0x180029d72  call    memset_0
0x180029d77  lea     rcx, [rbp+1B0h+var_228]
0x180029d7b  lea     rax, [rbp+1B0h+var_120]
0x180029d82  mov     edx, 2
0x180029d87  movups  xmm0, xmmword ptr [rax]
0x180029d8a  movups  xmmword ptr [rcx], xmm0
0x180029d8d  movups  xmm1, xmmword ptr [rax+10h]
0x180029d91  movups  xmmword ptr [rcx+10h], xmm1
0x180029d95  movups  xmm0, xmmword ptr [rax+20h]
0x180029d99  movups  xmmword ptr [rcx+20h], xmm0
0x180029d9d  movups  xmm1, xmmword ptr [rax+30h]
0x180029da1  movups  xmmword ptr [rcx+30h], xmm1
0x180029da5  movups  xmm0, xmmword ptr [rax+40h]
0x180029da9  movups  xmmword ptr [rcx+40h], xmm0
0x180029dad  movups  xmm1, xmmword ptr [rax+50h]
0x180029db1  movups  xmmword ptr [rcx+50h], xmm1
0x180029db5  movups  xmm0, xmmword ptr [rax+60h]
0x180029db9  movups  xmmword ptr [rcx+60h], xmm0
0x180029dbd  lea     rcx, [rcx+80h]
0x180029dc4  movups  xmm1, xmmword ptr [rax+70h]
0x180029dc8  movups  xmmword ptr [rcx-10h], xmm1
0x180029dcc  lea     rax, [rax+80h]
0x180029dd3  sub     rdx, 1
0x180029dd7  jnz     short loc_180029D87
0x180029dd9  mov     eax, [rax]
0x180029ddb  mov     [rcx], eax
0x180029ddd  lea     rax, [rsp+2B0h+var_240]
0x180029de2  mov     [rsp+2B0h+var_260], rax
0x180029de7  call    ?GetInstance@DdmNotificationHandler@@SAPEAV1@XZ; DdmNotificationHandler::GetInstance(void)
0x180029dec  lea     r8, [rsp+2B0h+var_260]
0x180029df1  mov     edx, 2
0x180029df6  mov     rcx, rax
0x180029df9  call    ?ProcessMessage@DdmNotificationHandler@@QEAAKW4_MESSAGEQ_ID@@AEAT_MESSAGE@@@Z; DdmNotificationHandler::ProcessMessage(_MESSAGEQ_ID,_MESSAGE &)
0x180029dfe  call    ?DdmSetProtocolEvent@@YAKXZ; DdmSetProtocolEvent(void)
0x180029e03  jmp     loc_180029F60
0x180029e08  lea     rcx, stru_1800CF970; lpCriticalSection
0x180029e0f  call    cs:__imp_EnterCriticalSection
0x180029e16  nop     dword ptr [rax+rax+00h]
0x180029e1b  and     [rsp+2B0h+NumberOfBytesTransferred], 0
0x180029e20  xor     ebx, ebx
0x180029e22  mov     [rsp+2B0h+var_278], rbx
0x180029e27  xorps   xmm0, xmm0
0x180029e2a  movups  [rsp+2B0h+var_258], xmm0
0x180029e2f  xor     r9d, r9d; bWait
0x180029e32  lea     r8, [rsp+2B0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180029e37  lea     rdx, stru_1800CF9A0; lpOverlapped
0x180029e3e  mov     rcx, cs:?gblDdmDriverInfo@@3U_DDM_DRIVER_INFO@@A; hFile
0x180029e45  call    cs:__imp_GetOverlappedResult
0x180029e4c  nop     dword ptr [rax+rax+00h]
0x180029e51  test    eax, eax
0x180029e53  jz      loc_180029F04
0x180029e59  mov     cs:byte_1800CF998, bl
0x180029e5f  cmp     [rsp+2B0h+NumberOfBytesTransferred], ebx
0x180029e63  jz      loc_180029F11
0x180029e69  inc     cs:dword_1800CF99C
0x180029e6f  mov     eax, 0ABB2h
0x180029e74  cmp     ax, word ptr cs:xmmword_1800CF9E8
0x180029e7b  jz      loc_180029F11
0x180029e81  lea     ecx, [rbx+11h]; unsigned int
0x180029e84  call    ?GetInstance@DdmDeviceTable@@SAPEAV1@K@Z; DdmDeviceTable::GetInstance(ulong)
0x180029e89  lea     r8, [rsp+2B0h+var_278]
0x180029e8e  mov     rdx, qword ptr cs:xmmword_1800CF9D8+8
0x180029e95  mov     rcx, rax
0x180029e98  call    ?FindDevice@DdmDeviceTable@@QEAAXPEAXAEAV?$RasObjPtr@VDdmDevice@@@@@Z; DdmDeviceTable::FindDevice(void *,RasObjPtr<DdmDevice> &)
0x180029e9d  mov     rbx, [rsp+2B0h+var_278]
0x180029ea2  test    rbx, rbx
0x180029ea5  jz      short loc_180029F11
0x180029ea7  movzx   edx, word ptr cs:xmmword_1800CF9E8+4; uBytes
0x180029eae  mov     ecx, 40h ; '@'; uFlags
0x180029eb3  call    cs:__imp_LocalAlloc
0x180029eba  nop     dword ptr [rax+rax+00h]
0x180029ebf  mov     rdi, rax
0x180029ec2  test    rax, rax
0x180029ec5  jz      short loc_180029F04
0x180029ec7  movzx   r8d, word ptr cs:xmmword_1800CF9E8+4; Size
0x180029ecf  lea     rdx, xmmword_1800CF9E8+8; Src
0x180029ed6  mov     rcx, rax; void *
0x180029ed9  call    memcpy_0
0x180029ede  movzx   ecx, word ptr cs:xmmword_1800CF9E8+4
0x180029ee5  mov     dword ptr [rsp+2B0h+var_258], ecx
0x180029ee9  mov     qword ptr [rsp+2B0h+var_258+8], rdi
0x180029eee  lea     r9, [rsp+2B0h+var_258]
0x180029ef3  xor     edx, edx
0x180029ef5  lea     r8d, [rdx+8]
0x180029ef9  mov     rcx, [rbx+60h]
0x180029efd  call    ?DdmNotifyCaller@@YAXPEAXKW4_DDM_DRIVER_NOTIFICATION_MSG_ID@@0@Z; DdmNotifyCaller(void *,ulong,_DDM_DRIVER_NOTIFICATION_MSG_ID,void *)
0x180029f02  jmp     short loc_180029F11
0x180029f04  call    cs:__imp_GetLastError
0x180029f0b  nop     dword ptr [rax+rax+00h]
0x180029f10  nop
0x180029f11  test    rbx, rbx
0x180029f14  jz      short loc_180029F38
0x180029f16  or      eax, 0FFFFFFFFh
0x180029f19  lock xadd [rbx+8], eax
0x180029f1e  cmp     eax, 1
0x180029f21  jnz     short loc_180029F38
0x180029f23  mov     rcx, [rsp+2B0h+var_278]
0x180029f28  mov     rax, [rcx]
0x180029f2b  mov     edx, 1
0x180029f30  mov     rax, [rax]
0x180029f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f38  cmp     cs:byte_1800CF998, 0
0x180029f3f  jnz     short loc_180029F46
0x180029f41  call    ?PostReceivePacketBuffer@@YAKXZ; PostReceivePacketBuffer(void)
0x180029f46  lea     rcx, stru_1800CF970; lpCriticalSection
0x180029f4d  call    cs:__imp_LeaveCriticalSection
0x180029f54  nop     dword ptr [rax+rax+00h]
0x180029f59  jmp     short loc_180029F60
0x180029f5b  call    ?PostReceivePacketBuffer@@YAKXZ; PostReceivePacketBuffer(void)
0x180029f60  or      [rsp+2B0h+var_290], 0FFFFFFFFh
0x180029f65  lea     r9, [rsp+2B0h+Overlapped]; lpOverlapped
0x180029f6a  lea     r8, [rsp+2B0h+CompletionKey]; lpCompletionKey
0x180029f6f  lea     rdx, [rsp+2B0h+var_27C]; lpNumberOfBytesTransferred
0x180029f74  mov     rcx, cs:CompletionPort; CompletionPort
0x180029f7b  call    cs:__imp_GetQueuedCompletionStatus
0x180029f82  nop     dword ptr [rax+rax+00h]
0x180029f87  test    eax, eax
0x180029f89  jnz     loc_180029D04
0x180029f8f  call    cs:__imp_GetLastError
0x180029f96  nop     dword ptr [rax+rax+00h]
0x180029f9b  mov     rcx, cs:CompletionPort; hObject
0x180029fa2  call    cs:__imp_CloseHandle
0x180029fa9  nop     dword ptr [rax+rax+00h]
0x180029fae  and     cs:CompletionPort, 0
0x180029fb6  lea     rcx, stru_1800CF970; lpCriticalSection
0x180029fbd  call    cs:__imp_DeleteCriticalSection
0x180029fc4  nop     dword ptr [rax+rax+00h]
0x180029fc9  xor     eax, eax
0x180029fcb  mov     rcx, [rbp+1B0h+var_10]
0x180029fd2  xor     rcx, rsp; StackCookie
0x180029fd5  call    __security_check_cookie
0x180029fda  lea     r11, [rsp+2B0h+var_s0]
0x180029fe2  mov     rbx, [r11+10h]
0x180029fe6  mov     rdi, [r11+18h]
0x180029fea  mov     rsp, r11
0x180029fed  pop     rbp
0x180029fee  retn
```
