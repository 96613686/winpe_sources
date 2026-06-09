# HrEnsureEventHandlerInitialized(void)

- ea: `0x18001f9c4`
- end: `0x18001fb61`
- name: `?HrEnsureEventHandlerInitialized@@YAJXZ`
- size: `413`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001bb00`

## callees

- `0x180002320`
- `0x18000538c`
- `0x180019200`
- `0x180019c68`
- `0x18001f9c4`
- `0x180023bd0`
- `0x18003060c`
- `0x180034de4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x18001fa41`
- `KERNEL32!CreateEventW` at `0x18001fa41`
- `KERNEL32!CloseHandle` at `0x18001fb14`
- `KERNEL32!CloseHandle` at `0x18001fb14`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x18001fab5`
- `RASDLG!RasSrvAllowConnectionsConfig` at `0x18001fab5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 HrEnsureEventHandlerInitialized(void)
{
  PVOID *v0; // rcx
  int Win32Error; // ebx
  HANDLE EventW; // rsi
  EventQueue *v3; // rax
  EventQueue *v4; // r14
  signed int v5; // eax
  bool v6; // sf
  int pExceptionObject; // [rsp+20h] [rbp-28h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  Win32Error = 1;
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 8) != 0 )
    WPP_SF_(v0[2], 38, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids);
  if ( !g_pEventQueue )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    if ( EventW )
    {
      v3 = (EventQueue *)MemAlloc(0x58u);
      v4 = v3;
      if ( v3 )
      {
        memset_0(v3, 0, 0x58u);
        v3 = EventQueue::EventQueue(v4, EventW);
      }
      g_pEventQueue = v3;
      if ( !v3 )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      v5 = RasSrvAllowConnectionsConfig(&g_fHandleIncomingEvents);
      v6 = v5 < 0;
      if ( v5 > 0 )
      {
        v5 = (unsigned __int16)v5 | 0x80070000;
        v6 = v5 < 0;
      }
      if ( v6 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          39,
          WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids,
          (unsigned int)v5);
      g_fDispatchEvents = 1;
      CloseHandle(EventW);
    }
    else
    {
      Win32Error = HrFromLastWin32Error();
    }
    if ( Win32Error < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids,
        (unsigned int)Win32Error);
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x18001f9c4  mov     [rsp+arg_10], rbx
0x18001f9c9  push    rsi
0x18001f9ca  push    rdi
0x18001f9cb  push    r14
0x18001f9cd  sub     rsp, 30h
0x18001f9d1  lea     rdi, WPP_GLOBAL_Control
0x18001f9d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9df  cmp     rcx, rdi
0x18001f9e2  jz      short loc_18001FA06
0x18001f9e4  test    byte ptr [rcx+1Ch], 8
0x18001f9e8  jz      short loc_18001FA06
0x18001f9ea  mov     edx, 25h ; '%'
0x18001f9ef  lea     r8, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids
0x18001f9f6  mov     rcx, [rcx+10h]
0x18001f9fa  call    WPP_SF_
0x18001f9ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa06  mov     ebx, 1
0x18001fa0b  cmp     rcx, rdi
0x18001fa0e  jz      short loc_18001FA29
0x18001fa10  test    byte ptr [rcx+1Ch], 8
0x18001fa14  jz      short loc_18001FA29
0x18001fa16  lea     edx, [rbx+25h]
0x18001fa19  lea     r8, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids
0x18001fa20  mov     rcx, [rcx+10h]
0x18001fa24  call    WPP_SF_
0x18001fa29  cmp     cs:?g_pEventQueue@@3PEAVEventQueue@@EA, 0; EventQueue * g_pEventQueue
0x18001fa31  jnz     loc_18001FB51
0x18001fa37  xor     r9d, r9d; lpName
0x18001fa3a  xor     r8d, r8d; bInitialState
0x18001fa3d  xor     edx, edx; bManualReset
0x18001fa3f  xor     ecx, ecx; lpEventAttributes
0x18001fa41  call    cs:__imp_CreateEventW
0x18001fa47  mov     rsi, rax
0x18001fa4a  mov     [rsp+48h+arg_8], rax
0x18001fa4f  test    rax, rax
0x18001fa52  jz      loc_18001FB1C
0x18001fa58  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001fa5d  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001fa62  mov     r14, rax
0x18001fa65  mov     [rsp+48h+arg_0], rax
0x18001fa6a  test    rax, rax
0x18001fa6d  jz      short loc_18001FA89
0x18001fa6f  xor     edx, edx; Val
0x18001fa71  lea     r8d, [rdx+58h]; Size
0x18001fa75  mov     rcx, rax; void *
0x18001fa78  call    memset_0
0x18001fa7d  mov     rdx, rsi; void *
0x18001fa80  mov     rcx, r14; this
0x18001fa83  call    ??0EventQueue@@QEAA@PEAX@Z; EventQueue::EventQueue(void *)
0x18001fa88  nop
0x18001fa89  mov     cs:?g_pEventQueue@@3PEAVEventQueue@@EA, rax; EventQueue * g_pEventQueue
0x18001fa90  test    rax, rax
0x18001fa93  jnz     short loc_18001FAAE
0x18001fa95  mov     [rsp+48h+pExceptionObject], 8007000Eh
0x18001fa9d  lea     rdx, _TI1J; pThrowInfo
0x18001faa4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001faa9  call    _CxxThrowException_0
0x18001faae  lea     rcx, ?g_fHandleIncomingEvents@@3HA; int g_fHandleIncomingEvents
0x18001fab5  call    cs:__imp_RasSrvAllowConnectionsConfig
0x18001fabb  test    eax, eax
0x18001fabd  jle     short loc_18001FAC9
0x18001fabf  movzx   eax, ax
0x18001fac2  or      eax, 80070000h
0x18001fac7  test    eax, eax
0x18001fac9  jns     short loc_18001FAF5
0x18001facb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fad2  cmp     rcx, rdi
0x18001fad5  jz      short loc_18001FAF5
0x18001fad7  test    byte ptr [rcx+1Ch], 1
0x18001fadb  jz      short loc_18001FAF5
0x18001fadd  mov     edx, 27h ; '''
0x18001fae2  mov     r9d, eax
0x18001fae5  lea     r8, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids
0x18001faec  mov     rcx, [rcx+10h]
0x18001faf0  call    WPP_SF_d
0x18001faf5  mov     cs:?g_fDispatchEvents@@3HA, 1; int g_fDispatchEvents
0x18001faff  jmp     short loc_18001FB11
0x18001fb01  lea     rdi, WPP_GLOBAL_Control
0x18001fb08  mov     rsi, [rsp+48h+arg_8]
0x18001fb0d  mov     ebx, dword ptr [rsp+48h+arg_0]
0x18001fb11  mov     rcx, rsi; hObject
0x18001fb14  call    cs:__imp_CloseHandle
0x18001fb1a  jmp     short loc_18001FB23
0x18001fb1c  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18001fb21  mov     ebx, eax
0x18001fb23  test    ebx, ebx
0x18001fb25  jns     short loc_18001FB51
0x18001fb27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb2e  cmp     rcx, rdi
0x18001fb31  jz      short loc_18001FB51
0x18001fb33  test    byte ptr [rcx+1Ch], 1
0x18001fb37  jz      short loc_18001FB51
0x18001fb39  mov     edx, 28h ; '('
0x18001fb3e  mov     r9d, ebx
0x18001fb41  lea     r8, WPP_7bd4eab9b76f3d42e97cbf4d22acd153_Traceguids
0x18001fb48  mov     rcx, [rcx+10h]
0x18001fb4c  call    WPP_SF_d
0x18001fb51  mov     eax, ebx
0x18001fb53  mov     rbx, [rsp+48h+arg_10]
0x18001fb58  add     rsp, 30h
0x18001fb5c  pop     r14
0x18001fb5e  pop     rdi
0x18001fb5f  pop     rsi
0x18001fb60  retn
```
