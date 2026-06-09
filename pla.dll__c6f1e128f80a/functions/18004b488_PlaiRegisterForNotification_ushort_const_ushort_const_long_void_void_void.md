# PlaiRegisterForNotification(ushort const *,ushort const *,long,void *,void * *,void * *)

- ea: `0x18004b488`
- end: `0x18004b8e9`
- name: `?PlaiRegisterForNotification@@YAJPEBG0JPEAXPEAPEAX2@Z`
- size: `1121`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, int, void *, void **, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ae7d4`
- `0x1800fc514`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x18004b488`
- `0x18004b8f0`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b6a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b741`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b72d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004b72d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b82d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18004b82d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b8b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b8b7`
- `wevtapi!EvtSubscribe` at `0x18004b68e`
- `wevtapi!EvtSubscribe` at `0x18004b68e`
- `wevtapi!EvtClose` at `0x18004b86b`
- `wevtapi!EvtClose` at `0x18004b86b`
- `wevtapi!EvtNext` at `0x18004b850`
- `wevtapi!EvtNext` at `0x18004b88f`
- `wevtapi!EvtNext` at `0x18004b850`
- `wevtapi!EvtNext` at `0x18004b88f`

## pseudocode

```c
__int64 __fastcall PlaiRegisterForNotification(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        void *a4,
        void **a5,
        void **a6)
{
  HANDLE EventW; // rdi
  void *v8; // r15
  int IsChannelEnabled; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  int *v12; // r9
  __int64 v13; // rax
  EVT_HANDLE v14; // r14
  DWORD LastError; // eax
  __int64 v16; // rax
  DWORD v17; // eax
  __int64 v18; // rax
  int v20; // [rsp+70h] [rbp-90h] BYREF
  void *v21; // [rsp+78h] [rbp-88h] BYREF
  DWORD Returned; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Events; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v24[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v25[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v26[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v27[64]; // [rsp+210h] [rbp+110h] BYREF

  Events = 0;
  Returned = 0;
  EventW = 0;
  v20 = 0;
  v8 = a4;
  v21 = a4;
  IsChannelEnabled = PlaiIsChannelEnabled(a1, &v20);
  v10 = IsChannelEnabled;
  if ( IsChannelEnabled < 0 )
  {
    v20 = 0;
    LODWORD(v21) = IsChannelEnabled;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v24, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v24[v11] );
      v12 = (int *)&v21;
      goto LABEL_8;
    }
LABEL_39:
    if ( v8 && EventW )
      CloseHandle(EventW);
    return v10;
  }
  if ( !v20 )
  {
    v10 = -2144337648;
    v20 = -2144337648;
    LODWORD(v21) = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_39;
    }
    PlaiWhoAmI(v25, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v25[v13] );
    goto LABEL_15;
  }
  if ( v8 )
  {
    EventW = v8;
LABEL_18:
    v14 = EvtSubscribe(0, EventW, L"Microsoft-Windows-Diagnosis-PLA/Operational", a2, 0, 0, 0, 1u);
    if ( v14 )
    {
      ResetEvent(EventW);
      if ( EvtNext(v14, 1u, &Events, 0, 0, &Returned) )
      {
        do
        {
          if ( Returned != 1 )
            break;
          if ( Events )
          {
            EvtClose(Events);
            Events = 0;
          }
        }
        while ( EvtNext(v14, 1u, &Events, 0, 0, &Returned) );
        v8 = v21;
      }
      *a5 = EventW;
      EventW = 0;
      *a6 = v14;
      goto LABEL_39;
    }
    LastError = GetLastError();
    v10 = PlaiHResultFromWin32(LastError);
    LODWORD(v21) = 0;
    v20 = v10;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_39;
    }
    PlaiWhoAmI(v27, 0x4000000000000800uLL);
    v16 = -1;
    do
      ++v16;
    while ( v27[v16] );
LABEL_15:
    v12 = &v20;
LABEL_8:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v12);
    goto LABEL_39;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
    goto LABEL_18;
  v17 = GetLastError();
  v10 = PlaiHResultFromWin32(v17);
  LODWORD(v21) = 0;
  v20 = v10;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v26, 0x4000000000000800uLL);
    v18 = -1;
    do
      ++v18;
    while ( v26[v18] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v20);
  }
  return v10;
}

```

## disassembly

```asm
0x18004b488  mov     [rsp-8+arg_0], rbx
0x18004b48d  push    rbp
0x18004b48e  push    rsi
0x18004b48f  push    rdi
0x18004b490  push    r12
0x18004b492  push    r13
0x18004b494  push    r14
0x18004b496  push    r15
0x18004b498  lea     rbp, [rsp-1A0h]
0x18004b4a0  sub     rsp, 2A0h
0x18004b4a7  mov     rax, cs:__security_cookie
0x18004b4ae  xor     rax, rsp
0x18004b4b1  mov     [rbp+1D0h+var_40], rax
0x18004b4b8  mov     r12, [rbp+1D0h+arg_20]
0x18004b4bf  xor     esi, esi
0x18004b4c1  mov     r13, [rbp+1D0h+arg_28]
0x18004b4c8  mov     r14, rdx
0x18004b4cb  lea     rdx, [rsp+2D0h+var_260]; int *
0x18004b4d0  mov     [rbp+1D0h+Events], rsi
0x18004b4d4  mov     [rbp+1D0h+Returned], esi
0x18004b4d7  mov     edi, esi
0x18004b4d9  mov     [rsp+2D0h+var_260], esi
0x18004b4dd  mov     r15, r9
0x18004b4e0  mov     [rsp+2D0h+var_258], r9
0x18004b4e5  call    ?PlaiIsChannelEnabled@@YAJPEBGPEAH@Z; PlaiIsChannelEnabled(ushort const *,int *)
0x18004b4ea  mov     ebx, eax
0x18004b4ec  test    eax, eax
0x18004b4ee  jns     loc_18004B5CA
0x18004b4f4  cmp     dword ptr cs:xmmword_180169738, esi
0x18004b4fa  mov     [rsp+2D0h+var_260], esi
0x18004b4fe  mov     dword ptr [rsp+2D0h+var_258], eax
0x18004b502  jz      loc_18004B8AA
0x18004b508  mov     rdx, 4000000000000800h; unsigned __int64
0x18004b512  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004b519  jz      loc_18004B8AA
0x18004b51f  mov     rax, cs:qword_180169748
0x18004b526  and     rax, rdx
0x18004b529  cmp     cs:qword_180169748, rax
0x18004b530  jnz     loc_18004B8AA
0x18004b536  lea     rcx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18004b53a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004b53f  lea     rcx, [rbp+1D0h+var_240]
0x18004b543  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b547  inc     rax
0x18004b54a  cmp     [rcx+rax*2], si
0x18004b54e  jnz     short loc_18004B547
0x18004b550  lea     ecx, [rax+rax]
0x18004b553  mov     esi, 1
0x18004b558  add     rcx, 2
0x18004b55c  lea     rax, [rbp+1D0h+var_240]
0x18004b560  mov     [rsp+2D0h+var_270], rcx
0x18004b565  lea     r9, [rsp+2D0h+var_258]
0x18004b56a  lea     rcx, [rsp+2D0h+var_260]
0x18004b56f  mov     [rsp+2D0h+var_278], rax
0x18004b574  lea     rdx, PLA_EVENT_ERROR
0x18004b57b  mov     [rsp+2D0h+var_280], 1Ch
0x18004b584  lea     rax, aPlairegisterfo_0; "PlaiRegisterForNotification"
0x18004b58b  mov     [rsp+2D0h+var_288], rax
0x18004b590  mov     eax, 4
0x18004b595  mov     [rsp+2D0h+var_290], rax
0x18004b59a  mov     qword ptr [rsp+2D0h+Flags], rcx
0x18004b59f  lea     rcx, qword_180147320
0x18004b5a6  mov     [rsp+2D0h+Callback], rsi
0x18004b5ab  mov     [rsp+2D0h+Context], rcx
0x18004b5b0  lea     r8d, [rax+1]
0x18004b5b4  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004b5bb  mov     [rsp+2D0h+Bookmark], rax
0x18004b5c0  call    EventingWriteEvent
0x18004b5c5  jmp     loc_18004B8AA
0x18004b5ca  cmp     [rsp+2D0h+var_260], esi
0x18004b5ce  jnz     loc_18004B659
0x18004b5d4  cmp     dword ptr cs:xmmword_180169738, esi
0x18004b5da  mov     ebx, 80300110h
0x18004b5df  mov     [rsp+2D0h+var_260], ebx
0x18004b5e3  mov     dword ptr [rsp+2D0h+var_258], esi
0x18004b5e7  jz      loc_18004B8AA
0x18004b5ed  mov     rdx, 4000000000000800h; unsigned __int64
0x18004b5f7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004b5fe  jz      loc_18004B8AA
0x18004b604  mov     rax, cs:qword_180169748
0x18004b60b  and     rax, rdx
0x18004b60e  cmp     cs:qword_180169748, rax
0x18004b615  jnz     loc_18004B8AA
0x18004b61b  lea     rcx, [rbp+1D0h+var_1C0]; unsigned __int16 *
0x18004b61f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004b624  lea     rcx, [rbp+1D0h+var_1C0]
0x18004b628  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b62c  inc     rax
0x18004b62f  cmp     [rcx+rax*2], si
0x18004b633  jnz     short loc_18004B62C
0x18004b635  lea     ecx, [rax+rax]
0x18004b638  mov     esi, 1
0x18004b63d  lea     rax, [rbp+1D0h+var_1C0]
0x18004b641  add     rcx, 2
0x18004b645  lea     r9, [rsp+2D0h+var_260]
0x18004b64a  mov     [rsp+2D0h+var_270], rcx
0x18004b64f  lea     rcx, [rsp+2D0h+var_258]
0x18004b654  jmp     loc_18004B56F
0x18004b659  xor     eax, eax
0x18004b65b  mov     esi, 1
0x18004b660  test    r15, r15
0x18004b663  jz      loc_18004B723
0x18004b669  mov     rdi, r15
0x18004b66c  mov     [rsp+2D0h+Flags], esi; Flags
0x18004b670  lea     r8, ChannelPath; "Microsoft-Windows-Diagnosis-PLA/Operati"...
0x18004b677  mov     [rsp+2D0h+Callback], rax; Callback
0x18004b67c  mov     r9, r14; Query
0x18004b67f  mov     [rsp+2D0h+Context], rax; Context
0x18004b684  mov     rdx, rdi; SignalEvent
0x18004b687  xor     ecx, ecx; Session
0x18004b689  mov     [rsp+2D0h+Bookmark], rax; Bookmark
0x18004b68e  call    cs:__imp_EvtSubscribe
0x18004b694  mov     r14, rax
0x18004b697  test    rax, rax
0x18004b69a  jnz     loc_18004B82A
0x18004b6a0  call    cs:__imp_GetLastError
0x18004b6a6  mov     ecx, eax; unsigned int
0x18004b6a8  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004b6ad  cmp     dword ptr cs:xmmword_180169738, r14d
0x18004b6b4  mov     ebx, eax
0x18004b6b6  mov     dword ptr [rsp+2D0h+var_258], r14d
0x18004b6bb  mov     [rsp+2D0h+var_260], eax
0x18004b6bf  jz      loc_18004B8AA
0x18004b6c5  mov     rdx, 4000000000000800h; unsigned __int64
0x18004b6cf  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004b6d6  jz      loc_18004B8AA
0x18004b6dc  mov     rax, cs:qword_180169748
0x18004b6e3  and     rax, rdx
0x18004b6e6  cmp     cs:qword_180169748, rax
0x18004b6ed  jnz     loc_18004B8AA
0x18004b6f3  lea     rcx, [rbp+1D0h+var_C0]; unsigned __int16 *
0x18004b6fa  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004b6ff  lea     rcx, [rbp+1D0h+var_C0]
0x18004b706  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b70a  inc     rax
0x18004b70d  cmp     [rcx+rax*2], r14w
0x18004b712  jnz     short loc_18004B70A
0x18004b714  lea     ecx, [rax+rax]
0x18004b717  lea     rax, [rbp+1D0h+var_C0]
0x18004b71e  jmp     loc_18004B641
0x18004b723  xor     r9d, r9d; lpName
0x18004b726  xor     r8d, r8d; bInitialState
0x18004b729  mov     edx, esi; bManualReset
0x18004b72b  xor     ecx, ecx; lpEventAttributes
0x18004b72d  call    cs:__imp_CreateEventW
0x18004b733  mov     rdi, rax
0x18004b736  xor     eax, eax
0x18004b738  test    rdi, rdi
0x18004b73b  jnz     loc_18004B66C
0x18004b741  call    cs:__imp_GetLastError
0x18004b747  mov     ecx, eax; unsigned int
0x18004b749  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004b74e  cmp     dword ptr cs:xmmword_180169738, edi
0x18004b754  mov     ebx, eax
0x18004b756  mov     dword ptr [rsp+2D0h+var_258], edi
0x18004b75a  mov     [rsp+2D0h+var_260], eax
0x18004b75e  jz      loc_18004B8BD
0x18004b764  mov     rdx, 4000000000000800h; unsigned __int64
0x18004b76e  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004b775  jz      loc_18004B8BD
0x18004b77b  mov     rax, cs:qword_180169748
0x18004b782  and     rax, rdx
0x18004b785  cmp     cs:qword_180169748, rax
0x18004b78c  jnz     loc_18004B8BD
0x18004b792  lea     rcx, [rbp+1D0h+var_140]; unsigned __int16 *
0x18004b799  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004b79e  lea     rcx, [rbp+1D0h+var_140]
0x18004b7a5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004b7a9  inc     rax
0x18004b7ac  cmp     [rcx+rax*2], di
0x18004b7b0  jnz     short loc_18004B7A9
0x18004b7b2  lea     ecx, [rax+rax]
0x18004b7b5  add     rcx, 2
0x18004b7b9  lea     rax, [rbp+1D0h+var_140]
0x18004b7c0  mov     [rsp+2D0h+var_270], rcx
0x18004b7c5  lea     r9, [rsp+2D0h+var_260]
0x18004b7ca  mov     [rsp+2D0h+var_278], rax
0x18004b7cf  lea     rcx, [rsp+2D0h+var_258]
0x18004b7d4  mov     [rsp+2D0h+var_280], 1Ch
0x18004b7dd  lea     rax, aPlairegisterfo_0; "PlaiRegisterForNotification"
0x18004b7e4  mov     [rsp+2D0h+var_288], rax
0x18004b7e9  lea     rdx, PLA_EVENT_ERROR
0x18004b7f0  mov     eax, 4
0x18004b7f5  mov     [rsp+2D0h+var_290], rax
0x18004b7fa  mov     qword ptr [rsp+2D0h+Flags], rcx
0x18004b7ff  lea     rcx, qword_180147320
0x18004b806  mov     [rsp+2D0h+Callback], rsi
0x18004b80b  mov     [rsp+2D0h+Context], rcx
0x18004b810  lea     r8d, [rax+1]
0x18004b814  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004b81b  mov     [rsp+2D0h+Bookmark], rax
0x18004b820  call    EventingWriteEvent
0x18004b825  jmp     loc_18004B8BD
0x18004b82a  mov     rcx, rdi; hEvent
0x18004b82d  call    cs:__imp_ResetEvent
0x18004b833  lea     rax, [rbp+1D0h+Returned]
0x18004b837  xor     r9d, r9d; Timeout
0x18004b83a  mov     [rsp+2D0h+Context], rax; Returned
0x18004b83f  lea     r8, [rbp+1D0h+Events]; Events
0x18004b843  mov     edx, esi; EventsSize
0x18004b845  mov     dword ptr [rsp+2D0h+Bookmark], 0; Flags
0x18004b84d  mov     rcx, r14; ResultSet
0x18004b850  call    cs:__imp_EvtNext
0x18004b856  test    eax, eax
0x18004b858  jz      short loc_18004B89E
0x18004b85a  xor     r15d, r15d
0x18004b85d  cmp     [rbp+1D0h+Returned], esi
0x18004b860  jnz     short loc_18004B899
0x18004b862  mov     rcx, [rbp+1D0h+Events]; Object
0x18004b866  test    rcx, rcx
0x18004b869  jz      short loc_18004B875
0x18004b86b  call    cs:__imp_EvtClose
0x18004b871  mov     [rbp+1D0h+Events], r15
0x18004b875  lea     rax, [rbp+1D0h+Returned]
0x18004b879  xor     r9d, r9d; Timeout
0x18004b87c  mov     [rsp+2D0h+Context], rax; Returned
0x18004b881  lea     r8, [rbp+1D0h+Events]; Events
0x18004b885  mov     edx, esi; EventsSize
0x18004b887  mov     dword ptr [rsp+2D0h+Bookmark], r15d; Flags
0x18004b88c  mov     rcx, r14; ResultSet
0x18004b88f  call    cs:__imp_EvtNext
0x18004b895  test    eax, eax
0x18004b897  jnz     short loc_18004B85D
0x18004b899  mov     r15, [rsp+2D0h+var_258]
0x18004b89e  mov     [r12], rdi
0x18004b8a2  xor     esi, esi
0x18004b8a4  mov     edi, esi
0x18004b8a6  mov     [r13+0], r14
0x18004b8aa  test    r15, r15
0x18004b8ad  jz      short loc_18004B8BD
0x18004b8af  test    rdi, rdi
0x18004b8b2  jz      short loc_18004B8BD
0x18004b8b4  mov     rcx, rdi; hObject
0x18004b8b7  call    cs:__imp_CloseHandle
0x18004b8bd  mov     eax, ebx
0x18004b8bf  mov     rcx, [rbp+1D0h+var_40]
0x18004b8c6  xor     rcx, rsp; StackCookie
0x18004b8c9  call    __security_check_cookie
0x18004b8ce  mov     rbx, [rsp+2D0h+arg_0]
0x18004b8d6  add     rsp, 2A0h
0x18004b8dd  pop     r15
0x18004b8df  pop     r14
0x18004b8e1  pop     r13
0x18004b8e3  pop     r12
0x18004b8e5  pop     rdi
0x18004b8e6  pop     rsi
0x18004b8e7  pop     rbp
0x18004b8e8  retn
```
