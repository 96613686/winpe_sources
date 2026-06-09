# PROXYPORT::SendRequest(uchar *,uchar *,ulong,bool)

- ea: `0x180040cb4`
- end: `0x180040faa`
- name: `?SendRequest@PROXYPORT@@QEAAJPEAE0K_N@Z`
- size: `758`
- prototype: `__int64 __fastcall(PROXYPORT *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned int, bool)`
- caller_count: `10`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x18003f05c`
- `0x180040950`
- `0x180040a94`
- `0x180040fb0`
- `0x18007eab0`
- `0x18007ec10`
- `0x18007ed70`
- `0x18007eefc`
- `0x18007f280`
- `0x18009b458`

## callees

- `0x180040cb4`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040f98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040f98`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180040e3c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180040e3c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f6c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f41`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180040f6c`
- `ntdll!RtlFreeHeap` at `0x180040ded`
- `ntdll!RtlFreeHeap` at `0x180040ded`
- `ntdll!RtlAllocateHeap` at `0x180040cfd`
- `ntdll!RtlAllocateHeap` at `0x180040cfd`
- `ntdll!TpSimpleTryPost` at `0x180040e61`
- `ntdll!TpSimpleTryPost` at `0x180040e61`
- `ntdll!NtRequestWaitReplyPort` at `0x180040d7f`
- `ntdll!NtRequestWaitReplyPort` at `0x180040d7f`
- `USER32!PostQuitMessage` at `0x180040f5a`
- `USER32!PostQuitMessage` at `0x180040f5a`
- `USER32!TranslateMessage` at `0x180040f1f`
- `USER32!TranslateMessage` at `0x180040f1f`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180040ea9`
- `USER32!MsgWaitForMultipleObjectsEx` at `0x180040ea9`
- `USER32!PeekMessageW` at `0x180040eff`
- `USER32!PeekMessageW` at `0x180040eff`
- `USER32!DispatchMessageW` at `0x180040f30`
- `USER32!DispatchMessageW` at `0x180040f30`

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
0x180040cb4  mov     [rsp+arg_8], rbx
0x180040cb9  mov     [rsp+arg_10], rbp
0x180040cbe  push    rsi
0x180040cbf  push    rdi
0x180040cc0  push    r13
0x180040cc2  push    r14
0x180040cc4  push    r15
0x180040cc6  sub     rsp, 60h
0x180040cca  mov     r15d, r9d
0x180040ccd  mov     rbp, r8
0x180040cd0  mov     rdi, rdx
0x180040cd3  mov     r14, rcx
0x180040cd6  mov     rax, [rcx]
0x180040cd9  mov     esi, 48h ; 'H'
0x180040cde  cmp     [rax+68h], esi
0x180040ce1  mov     r8d, esi
0x180040ce4  jb      short loc_180040CEA
0x180040ce6  mov     r8d, [rax+68h]
0x180040cea  add     r8, 60h ; '`'; Size
0x180040cee  mov     rcx, gs:60h
0x180040cf7  xor     edx, edx; Flags
0x180040cf9  mov     rcx, [rcx+30h]; HeapHandle
0x180040cfd  call    cs:__imp_RtlAllocateHeap
0x180040d04  nop     dword ptr [rax+rax+00h]
0x180040d09  mov     rbx, rax
0x180040d0c  mov     [rsp+88h+arg_0], rax
0x180040d14  test    rax, rax
0x180040d17  jz      loc_180040E16
0x180040d1d  xor     edx, edx; Val
0x180040d1f  mov     r8d, 0A8h; Size
0x180040d25  mov     rcx, rax; void *
0x180040d28  call    memset_0
0x180040d2d  mov     rax, [r14]
0x180040d30  mov     rcx, [rax]
0x180040d33  mov     [rbx+8], rcx
0x180040d37  mov     rax, [r14]
0x180040d3a  mov     ecx, [rax+58h]
0x180040d3d  lea     rdx, [rbx+18h]; LpcReply
0x180040d41  mov     dword ptr [rdx], 480020h
0x180040d47  mov     [rbx+40h], ecx
0x180040d4a  mov     [rbx+48h], rdi
0x180040d4e  mov     rax, rbp
0x180040d51  neg     rax
0x180040d54  sbb     ecx, ecx
0x180040d56  and     ecx, r15d
0x180040d59  mov     [rbx+50h], ecx
0x180040d5c  mov     [rbx+58h], rbp
0x180040d60  mov     r13d, 2
0x180040d66  cmp     [rsp+88h+arg_20], 0
0x180040d6e  jnz     loc_180040E1D
0x180040d74  lea     rsi, [rbx+60h]
0x180040d78  mov     r8, rsi; LpcRequest
0x180040d7b  mov     rcx, [rbx+8]; PortHandle
0x180040d7f  call    cs:__imp_NtRequestWaitReplyPort
0x180040d86  nop     dword ptr [rax+rax+00h]
0x180040d8b  mov     edi, eax
0x180040d8d  cmp     edi, 0C0000037h
0x180040d93  jz      loc_180040F82
0x180040d99  test    edi, edi
0x180040d9b  js      short loc_180040DCA
0x180040d9d  cmp     [rbx+64h], r13w
0x180040da2  jnz     loc_180040F8E
0x180040da8  mov     eax, 20h ; ' '
0x180040dad  cmp     [rsi], ax
0x180040db0  jnz     loc_180040F8E
0x180040db6  cmp     rbp, [rsi+40h]
0x180040dba  jnz     loc_180040F8E
0x180040dc0  cmp     r15d, [rsi+38h]
0x180040dc4  jnz     loc_180040F8E
0x180040dca  mov     rcx, [rbx]; hObject
0x180040dcd  test    rcx, rcx
0x180040dd0  jnz     loc_180040F98
0x180040dd6  test    rbx, rbx
0x180040dd9  jz      short loc_180040DFA
0x180040ddb  mov     rcx, gs:60h
0x180040de4  mov     r8, rbx; P
0x180040de7  xor     edx, edx; Flags
0x180040de9  mov     rcx, [rcx+30h]; HeapHandle
0x180040ded  call    cs:__imp_RtlFreeHeap
0x180040df4  nop     dword ptr [rax+rax+00h]
0x180040df9  nop
0x180040dfa  mov     eax, edi
0x180040dfc  lea     r11, [rsp+88h+var_28]
0x180040e01  mov     rbx, [r11+38h]
0x180040e05  mov     rbp, [r11+40h]
0x180040e09  mov     rsp, r11
0x180040e0c  pop     r15
0x180040e0e  pop     r14
0x180040e10  pop     r13
0x180040e12  pop     rdi
0x180040e13  pop     rsi
0x180040e14  retn
0x180040e16  mov     eax, 0C0000017h
0x180040e1b  jmp     short loc_180040DFC
0x180040e1d  mov     rcx, [r14]
0x180040e20  mov     eax, [rcx+6Ch]
0x180040e23  mov     esi, eax
0x180040e25  shr     esi, 2
0x180040e28  sbb     esi, esi
0x180040e2a  or      eax, r13d
0x180040e2d  mov     [rcx+6Ch], eax
0x180040e30  xor     r9d, r9d; lpName
0x180040e33  xor     r8d, r8d; bInitialState
0x180040e36  lea     edx, [r9+1]; bManualReset
0x180040e3a  xor     ecx, ecx; lpEventAttributes
0x180040e3c  call    cs:__imp_CreateEventA
0x180040e43  nop     dword ptr [rax+rax+00h]
0x180040e48  mov     [rbx], rax
0x180040e4b  test    rax, rax
0x180040e4e  jz      loc_180040EE3
0x180040e54  xor     r8d, r8d
0x180040e57  mov     rdx, rbx
0x180040e5a  lea     rcx, ?UmpdProxyRequest@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; UmpdProxyRequest(_TP_CALLBACK_INSTANCE *,void *)
0x180040e61  call    cs:__imp_TpSimpleTryPost
0x180040e68  nop     dword ptr [rax+rax+00h]
0x180040e6d  test    eax, eax
0x180040e6f  js      short loc_180040EE3
0x180040e71  xor     edi, edi
0x180040e73  xorps   xmm0, xmm0
0x180040e76  movups  xmmword ptr [rsp+88h+Msg.hwnd], xmm0
0x180040e7b  movups  xmmword ptr [rsp+88h+Msg.wParam], xmm0
0x180040e80  movups  xmmword ptr [rsp+88h+Msg.time], xmm0
0x180040e85  or      r13d, 0FFFFFFFFh
0x180040e89  cmp     [rsp+88h+Msg.message], 12h
0x180040e8e  jz      short loc_180040EC1
0x180040e90  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180040e98  mov     r9d, 1CFFh; dwWakeMask
0x180040e9e  mov     r8d, r13d; dwMilliseconds
0x180040ea1  mov     rdx, rbx; pHandles
0x180040ea4  mov     ecx, 1; nCount
0x180040ea9  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180040eb0  nop     dword ptr [rax+rax+00h]
0x180040eb5  cmp     eax, 1
0x180040eb8  jz      short loc_180040EEA
0x180040eba  test    eax, eax
0x180040ebc  jnz     short loc_180040E89
0x180040ebe  mov     edi, [rbx+10h]
0x180040ec1  mov     r13d, 2
0x180040ec7  lea     ecx, [rsi+rsi]
0x180040eca  mov     rdx, [r14]
0x180040ecd  mov     eax, ecx
0x180040ecf  xor     eax, [rdx+6Ch]
0x180040ed2  and     eax, 0FFFFFFFDh
0x180040ed5  xor     eax, ecx
0x180040ed7  mov     [rdx+6Ch], eax
0x180040eda  lea     rsi, [rbx+60h]
0x180040ede  jmp     loc_180040D8D
0x180040ee3  mov     edi, 0C0000001h
0x180040ee8  jmp     short loc_180040EC7
0x180040eea  mov     [rsp+88h+dwFlags], 1; wRemoveMsg
0x180040ef2  xor     r9d, r9d; wMsgFilterMax
0x180040ef5  xor     r8d, r8d; wMsgFilterMin
0x180040ef8  xor     edx, edx; hWnd
0x180040efa  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180040eff  call    cs:__imp_PeekMessageW
0x180040f06  nop     dword ptr [rax+rax+00h]
0x180040f0b  test    eax, eax
0x180040f0d  jz      loc_180040E89
0x180040f13  cmp     [rsp+88h+Msg.message], 12h
0x180040f18  jz      short loc_180040F56
0x180040f1a  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180040f1f  call    cs:__imp_TranslateMessage
0x180040f26  nop     dword ptr [rax+rax+00h]
0x180040f2b  lea     rcx, [rsp+88h+Msg]; lpMsg
0x180040f30  call    cs:__imp_DispatchMessageW
0x180040f37  nop     dword ptr [rax+rax+00h]
0x180040f3c  xor     edx, edx; dwMilliseconds
0x180040f3e  mov     rcx, [rbx]; hHandle
0x180040f41  call    cs:__imp_WaitForSingleObject
0x180040f48  nop     dword ptr [rax+rax+00h]
0x180040f4d  test    eax, eax
0x180040f4f  jnz     short loc_180040EEA
0x180040f51  jmp     loc_180040EBE
0x180040f56  mov     ecx, dword ptr [rsp+88h+Msg.wParam]; nExitCode
0x180040f5a  call    cs:__imp_PostQuitMessage
0x180040f61  nop     dword ptr [rax+rax+00h]
0x180040f66  mov     edx, r13d; dwMilliseconds
0x180040f69  mov     rcx, [rbx]; hHandle
0x180040f6c  call    cs:__imp_WaitForSingleObject
0x180040f73  nop     dword ptr [rax+rax+00h]
0x180040f78  mov     edi, 0C0000001h
0x180040f7d  jmp     loc_180040E89
0x180040f82  mov     rcx, [r14]
0x180040f85  and     dword ptr [rcx+6Ch], 0FFFFFFFEh
0x180040f89  jmp     loc_180040DCA
0x180040f8e  mov     edi, 0C0000001h
0x180040f93  jmp     loc_180040DCA
0x180040f98  call    cs:__imp_CloseHandle
0x180040f9f  nop     dword ptr [rax+rax+00h]
0x180040fa4  jmp     loc_180040DD6
```
