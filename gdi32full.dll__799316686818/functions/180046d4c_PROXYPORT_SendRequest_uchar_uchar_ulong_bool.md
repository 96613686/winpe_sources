# PROXYPORT::SendRequest(uchar *,uchar *,ulong,bool)

- ea: `0x180046d4c`
- end: `0x180046fec`
- name: `?SendRequest@PROXYPORT@@QEAAJPEAE0K_N@Z`
- size: `672`
- prototype: `__int64 __fastcall(PROXYPORT *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned int, bool)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180045248`
- `0x180046a04`
- `0x180046b40`
- `0x180046ff4`
- `0x180079dec`
- `0x180079f30`
- `0x18007a074`
- `0x18007a1e8`
- `0x18007a538`
- `0x18009550c`

## callees

- `0x180046d4c`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046fe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046fe0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180046ec1`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180046ec1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046f9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046fba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046f9e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180046fba`
- `ntdll!RtlFreeHeap` at `0x180046e79`
- `ntdll!RtlFreeHeap` at `0x180046e79`
- `ntdll!RtlAllocateHeap` at `0x180046d95`
- `ntdll!RtlAllocateHeap` at `0x180046d95`
- `ntdll!TpSimpleTryPost` at `0x180046ee0`
- `ntdll!TpSimpleTryPost` at `0x180046ee0`
- `ntdll!NtRequestWaitReplyPort` at `0x180046e11`
- `ntdll!NtRequestWaitReplyPort` at `0x180046e11`
- `USER32!PostQuitMessage` at `0x180046fae`
- `USER32!PostQuitMessage` at `0x180046fae`
- `USER32!TranslateMessage` at `0x180046f88`
- `USER32!TranslateMessage` at `0x180046f88`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180046f22`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180046f22`
- `USER32!PeekMessageW` at `0x180046f72`
- `USER32!PeekMessageW` at `0x180046f72`
- `USER32!DispatchMessageW` at `0x180046f93`
- `USER32!DispatchMessageW` at `0x180046f93`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PROXYPORT::SendRequest(PROXYPORT *this, unsigned __int8 *a2, unsigned __int8 *a3, int a4, bool a5)
{
  __int64 v9; // r8
  char *Heap; // rax
  char *v11; // rbx
  int v12; // ecx
  unsigned __int8 **v13; // rsi
  NTSTATUS v14; // edi
  int v16; // esi
  HANDLE EventA; // rax
  DWORD v18; // eax
  tagMSG Msg; // [rsp+30h] [rbp-58h] BYREF

  v9 = 72;
  if ( *(_DWORD *)(*(_QWORD *)this + 104LL) >= 0x48u )
    v9 = *(unsigned int *)(*(_QWORD *)this + 104LL);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v9 + 96);
  v11 = Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, 0xA8u);
  *((_QWORD *)v11 + 1) = **(_QWORD **)this;
  v12 = *(_DWORD *)(*(_QWORD *)this + 88LL);
  *((_DWORD *)v11 + 6) = 4718624;
  *((_DWORD *)v11 + 16) = v12;
  *((_QWORD *)v11 + 9) = a2;
  *((_DWORD *)v11 + 20) = a3 != 0 ? a4 : 0;
  *((_QWORD *)v11 + 11) = a3;
  if ( a5 )
  {
    v16 = -__CFSHR__(*(_DWORD *)(*(_QWORD *)this + 108LL), 2);
    *(_DWORD *)(*(_QWORD *)this + 108LL) |= 2u;
    EventA = CreateEventA(0, 1, 0, 0);
    *(_QWORD *)v11 = EventA;
    if ( EventA && (int)TpSimpleTryPost(UmpdProxyRequest, v11, 0) >= 0 )
    {
      v14 = 0;
      memset(&Msg, 0, sizeof(Msg));
LABEL_21:
      while ( Msg.message != 18 )
      {
        v18 = MsgWaitForMultipleObjectsEx(1u, (const HANDLE *)v11, 0xFFFFFFFF, 0x1CFFu, 0);
        if ( v18 == 1 )
        {
          while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
          {
            if ( Msg.message == 18 )
            {
              PostQuitMessage(Msg.wParam);
              WaitForSingleObject(*(HANDLE *)v11, 0xFFFFFFFF);
              v14 = -1073741823;
              goto LABEL_21;
            }
            TranslateMessage(&Msg);
            DispatchMessageW(&Msg);
            if ( !WaitForSingleObject(*(HANDLE *)v11, 0) )
              goto LABEL_24;
          }
        }
        else if ( !v18 )
        {
LABEL_24:
          v14 = *((_DWORD *)v11 + 4);
          break;
        }
      }
    }
    else
    {
      v14 = -1073741823;
    }
    *(_DWORD *)(*(_QWORD *)this + 108LL) = (2 * v16) ^ (*(_DWORD *)(*(_QWORD *)this + 108LL) ^ (2 * v16)) & 0xFFFFFFFD;
    v13 = (unsigned __int8 **)(v11 + 96);
  }
  else
  {
    v13 = (unsigned __int8 **)(v11 + 96);
    v14 = NtRequestWaitReplyPort(*((HANDLE *)v11 + 1), (PPORT_MESSAGE)(v11 + 24), (PPORT_MESSAGE)(v11 + 96));
  }
  if ( v14 == -1073741769 )
  {
    *(_DWORD *)(*(_QWORD *)this + 108LL) &= ~1u;
  }
  else if ( v14 >= 0
         && (*((_WORD *)v11 + 50) != 2 || *(_WORD *)v13 != 32 || a3 != v13[8] || a4 != *((_DWORD *)v13 + 14)) )
  {
    v14 = -1073741823;
  }
  if ( *(_QWORD *)v11 )
    CloseHandle(*(HANDLE *)v11);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180046d4c  mov     [rsp+arg_8], rbx
0x180046d51  mov     [rsp+arg_10], rbp
0x180046d56  push    rsi
0x180046d57  push    rdi
0x180046d58  push    r13
0x180046d5a  push    r14
0x180046d5c  push    r15
0x180046d5e  sub     rsp, 60h
0x180046d62  mov     r15d, r9d
0x180046d65  mov     rbp, r8
0x180046d68  mov     rdi, rdx
0x180046d6b  mov     r14, rcx
0x180046d6e  mov     rax, [rcx]
0x180046d71  mov     esi, 48h ; 'H'
0x180046d76  cmp     [rax+68h], esi
0x180046d79  mov     r8d, esi
0x180046d7c  jb      short loc_180046D82
0x180046d7e  mov     r8d, [rax+68h]
0x180046d82  add     r8, 60h ; '`'; Size
0x180046d86  mov     rcx, gs:60h
0x180046d8f  xor     edx, edx; Flags
0x180046d91  mov     rcx, [rcx+30h]; HeapHandle
0x180046d95  call    cs:__imp_RtlAllocateHeap
0x180046d9b  mov     rbx, rax
0x180046d9e  mov     [rsp+88h+arg_0], rax
0x180046da6  test    rax, rax
0x180046da9  jz      loc_180046E9B
0x180046daf  xor     edx, edx; Val
0x180046db1  mov     r8d, 0A8h; Size
0x180046db7  mov     rcx, rax; void *
0x180046dba  call    memset_0
0x180046dbf  mov     rax, [r14]
0x180046dc2  mov     rcx, [rax]
0x180046dc5  mov     [rbx+8], rcx
0x180046dc9  mov     rax, [r14]
0x180046dcc  mov     ecx, [rax+58h]
0x180046dcf  lea     rdx, [rbx+18h]; LpcReply
0x180046dd3  mov     dword ptr [rdx], 480020h
0x180046dd9  mov     [rbx+40h], ecx
0x180046ddc  mov     [rbx+48h], rdi
0x180046de0  mov     rax, rbp
0x180046de3  neg     rax
0x180046de6  sbb     ecx, ecx
0x180046de8  and     ecx, r15d
0x180046deb  mov     [rbx+50h], ecx
0x180046dee  mov     [rbx+58h], rbp
0x180046df2  mov     r13d, 2
0x180046df8  cmp     [rsp+88h+arg_20], 0
0x180046e00  jnz     loc_180046EA2
0x180046e06  lea     rsi, [rbx+60h]
0x180046e0a  mov     r8, rsi; LpcRequest
0x180046e0d  mov     rcx, [rbx+8]; PortHandle
0x180046e11  call    cs:__imp_NtRequestWaitReplyPort
0x180046e17  mov     edi, eax
0x180046e19  cmp     edi, 0C0000037h
0x180046e1f  jz      loc_180046FCA
0x180046e25  test    edi, edi
0x180046e27  js      short loc_180046E56
0x180046e29  cmp     [rbx+64h], r13w
0x180046e2e  jnz     loc_180046FD6
0x180046e34  mov     eax, 20h ; ' '
0x180046e39  cmp     [rsi], ax
0x180046e3c  jnz     loc_180046FD6
0x180046e42  cmp     rbp, [rsi+40h]
0x180046e46  jnz     loc_180046FD6
0x180046e4c  cmp     r15d, [rsi+38h]
0x180046e50  jnz     loc_180046FD6
0x180046e56  mov     rcx, [rbx]; hObject
0x180046e59  test    rcx, rcx
0x180046e5c  jnz     loc_180046FE0
0x180046e62  test    rbx, rbx
0x180046e65  jz      short loc_180046E80
0x180046e67  mov     rcx, gs:60h
0x180046e70  mov     r8, rbx; P
0x180046e73  xor     edx, edx; Flags
0x180046e75  mov     rcx, [rcx+30h]; HeapHandle
0x180046e79  call    cs:__imp_RtlFreeHeap
0x180046e7f  nop
0x180046e80  mov     eax, edi
0x180046e82  lea     r11, [rsp+88h+var_28]
0x180046e87  mov     rbx, [r11+38h]
0x180046e8b  mov     rbp, [r11+40h]
0x180046e8f  mov     rsp, r11
0x180046e92  pop     r15
0x180046e94  pop     r14
0x180046e96  pop     r13
0x180046e98  pop     rdi
0x180046e99  pop     rsi
0x180046e9a  retn
0x180046e9b  mov     eax, 0C0000017h
0x180046ea0  jmp     short loc_180046E82
0x180046ea2  mov     rcx, [r14]
0x180046ea5  mov     eax, [rcx+6Ch]
0x180046ea8  mov     esi, eax
0x180046eaa  shr     esi, 2
0x180046ead  sbb     esi, esi
0x180046eaf  or      eax, r13d
0x180046eb2  mov     [rcx+6Ch], eax
0x180046eb5  xor     r9d, r9d; lpName
0x180046eb8  xor     r8d, r8d; bInitialState
0x180046ebb  lea     edx, [r9+1]; bManualReset
0x180046ebf  xor     ecx, ecx; lpEventAttributes
0x180046ec1  call    cs:__imp_CreateEventA
0x180046ec7  mov     [rbx], rax
0x180046eca  test    rax, rax
0x180046ecd  jz      loc_180046F56
0x180046ed3  xor     r8d, r8d
0x180046ed6  mov     rdx, rbx
0x180046ed9  lea     rcx, ?UmpdProxyRequest@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; UmpdProxyRequest(_TP_CALLBACK_INSTANCE *,void *)
0x180046ee0  call    cs:__imp_TpSimpleTryPost
0x180046ee6  test    eax, eax
0x180046ee8  js      short loc_180046F56
0x180046eea  xor     edi, edi
0x180046eec  xorps   xmm0, xmm0
0x180046eef  movups  xmmword ptr [rsp+88h+Msg.hwnd], xmm0
0x180046ef4  movups  xmmword ptr [rsp+88h+Msg.wParam], xmm0
0x180046ef9  movups  xmmword ptr [rsp+88h+Msg.time], xmm0
0x180046efe  or      r13d, 0FFFFFFFFh
0x180046f02  cmp     [rsp+88h+Msg.message], 12h
0x180046f07  jz      short loc_180046F34
0x180046f09  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180046f11  mov     r9d, 1CFFh; dwWakeMask
0x180046f17  mov     r8d, r13d; dwMilliseconds
0x180046f1a  mov     rdx, rbx; pHandles
0x180046f1d  mov     ecx, 1; nCount
0x180046f22  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180046f28  cmp     eax, 1
0x180046f2b  jz      short loc_180046F5D
0x180046f2d  test    eax, eax
0x180046f2f  jnz     short loc_180046F02
0x180046f31  mov     edi, [rbx+10h]
0x180046f34  mov     r13d, 2
0x180046f3a  lea     ecx, [rsi+rsi]
0x180046f3d  mov     rdx, [r14]
0x180046f40  mov     eax, ecx
0x180046f42  xor     eax, [rdx+6Ch]
0x180046f45  and     eax, 0FFFFFFFDh
0x180046f48  xor     eax, ecx
0x180046f4a  mov     [rdx+6Ch], eax
0x180046f4d  lea     rsi, [rbx+60h]
0x180046f51  jmp     loc_180046E19
0x180046f56  mov     edi, 0C0000001h
0x180046f5b  jmp     short loc_180046F3A
0x180046f5d  mov     [rsp+88h+dwFlags], 1; wRemoveMsg
0x180046f65  xor     r9d, r9d; wMsgFilterMax
0x180046f68  xor     r8d, r8d; wMsgFilterMin
0x180046f6b  xor     edx, edx; hWnd
0x180046f6d  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180046f72  call    cs:__imp_PeekMessageW
0x180046f78  test    eax, eax
0x180046f7a  jz      short loc_180046F02
0x180046f7c  cmp     [rsp+88h+Msg.message], 12h
0x180046f81  jz      short loc_180046FAA
0x180046f83  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180046f88  call    cs:__imp_TranslateMessage
0x180046f8e  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180046f93  call    cs:__imp_DispatchMessageW
0x180046f99  xor     edx, edx; dwMilliseconds
0x180046f9b  mov     rcx, [rbx]; hHandle
0x180046f9e  call    cs:__imp_WaitForSingleObject
0x180046fa4  test    eax, eax
0x180046fa6  jnz     short loc_180046F5D
0x180046fa8  jmp     short loc_180046F31
0x180046faa  mov     ecx, dword ptr [rsp+88h+Msg.wParam]; nExitCode
0x180046fae  call    cs:__imp_PostQuitMessage
0x180046fb4  mov     edx, r13d; dwMilliseconds
0x180046fb7  mov     rcx, [rbx]; hHandle
0x180046fba  call    cs:__imp_WaitForSingleObject
0x180046fc0  mov     edi, 0C0000001h
0x180046fc5  jmp     loc_180046F02
0x180046fca  mov     rcx, [r14]
0x180046fcd  and     dword ptr [rcx+6Ch], 0FFFFFFFEh
0x180046fd1  jmp     loc_180046E56
0x180046fd6  mov     edi, 0C0000001h
0x180046fdb  jmp     loc_180046E56
0x180046fe0  call    cs:__imp_CloseHandle
0x180046fe6  jmp     loc_180046E62
```
