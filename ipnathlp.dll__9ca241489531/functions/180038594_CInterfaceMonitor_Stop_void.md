# CInterfaceMonitor::Stop(void)

- ea: `0x180038594`
- end: `0x180038746`
- name: `?Stop@CInterfaceMonitor@@QEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180024c90`
- `0x1800251f8`
- `0x180038500`

## callees

- `0x18000c110`
- `0x180038594`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800385c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800385c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800385d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800385d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180038655`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180038655`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003865f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003865f`
- `WINNSI!NsiDisconnectFromServer` at `0x180038702`
- `WINNSI!NsiDisconnectFromServer` at `0x180038702`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003863d`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003863d`

## pseudocode

```c
__int64 __fastcall CInterfaceMonitor::Stop(CInterfaceMonitor *this)
{
  struct _TP_WORK *v2; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( *((_QWORD *)this + 17) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    }
    NsiRpcDeregisterChangeNotification(*((_QWORD *)this + 16), &NPI_MS_NDIS_MODULEID, 1, *((_QWORD *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_QWORD *)this + 16) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
    }
    NsiDisconnectFromServer(*((_QWORD *)this + 16));
    *((_QWORD *)this + 16) = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180038594  mov     [rsp+arg_0], rbx
0x180038599  mov     [rsp+arg_8], rdi
0x18003859e  push    r14
0x1800385a0  sub     rsp, 20h
0x1800385a4  mov     rbx, rcx
0x1800385a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385ae  lea     r14, WPP_GLOBAL_Control
0x1800385b5  cmp     rcx, r14
0x1800385b8  jnz     loc_180038672
0x1800385be  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800385c2  call    cs:__imp_EnterCriticalSection
0x1800385c8  mov     rcx, [rbx+8]; pwk
0x1800385cc  test    rcx, rcx
0x1800385cf  jnz     short loc_180038650
0x1800385d1  lea     rcx, [rbx+58h]; lpCriticalSection
0x1800385d5  call    cs:__imp_LeaveCriticalSection
0x1800385db  cmp     qword ptr [rbx+88h], 0
0x1800385e3  jnz     short loc_180038616
0x1800385e5  cmp     qword ptr [rbx+80h], 0
0x1800385ed  jnz     loc_1800386CE
0x1800385f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800385fa  cmp     rcx, r14
0x1800385fd  jnz     loc_180038718
0x180038603  mov     rbx, [rsp+28h+arg_0]
0x180038608  xor     eax, eax
0x18003860a  mov     rdi, [rsp+28h+arg_8]
0x18003860f  add     rsp, 20h
0x180038613  pop     r14
0x180038615  retn
0x180038616  mov     rcx, cs:WPP_GLOBAL_Control
0x18003861d  cmp     rcx, r14
0x180038620  jnz     short loc_1800386A0
0x180038622  mov     r9, [rbx+88h]
0x180038629  lea     rdx, NPI_MS_NDIS_MODULEID
0x180038630  mov     rcx, [rbx+80h]
0x180038637  mov     r8d, 1
0x18003863d  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x180038643  mov     qword ptr [rbx+88h], 0
0x18003864e  jmp     short loc_1800385E5
0x180038650  mov     edx, 1; fCancelPendingCallbacks
0x180038655  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003865b  mov     rcx, [rbx+8]; pwk
0x18003865f  call    cs:__imp_CloseThreadpoolWork
0x180038665  mov     qword ptr [rbx+8], 0
0x18003866d  jmp     loc_1800385D1
0x180038672  test    byte ptr [rcx+1Ch], 10h
0x180038676  jz      loc_1800385BE
0x18003867c  cmp     byte ptr [rcx+19h], 6
0x180038680  jb      loc_1800385BE
0x180038686  mov     rcx, [rcx+10h]
0x18003868a  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x180038691  mov     edx, 17h
0x180038696  call    WPP_SF_
0x18003869b  jmp     loc_1800385BE
0x1800386a0  test    byte ptr [rcx+1Ch], 10h
0x1800386a4  jz      loc_180038622
0x1800386aa  cmp     byte ptr [rcx+19h], 5
0x1800386ae  jb      loc_180038622
0x1800386b4  mov     rcx, [rcx+10h]
0x1800386b8  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x1800386bf  mov     edx, 18h
0x1800386c4  call    WPP_SF_
0x1800386c9  jmp     loc_180038622
0x1800386ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386d5  cmp     rcx, r14
0x1800386d8  jz      short loc_1800386FB
0x1800386da  test    byte ptr [rcx+1Ch], 10h
0x1800386de  jz      short loc_1800386FB
0x1800386e0  cmp     byte ptr [rcx+19h], 5
0x1800386e4  jb      short loc_1800386FB
0x1800386e6  mov     rcx, [rcx+10h]
0x1800386ea  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x1800386f1  mov     edx, 19h
0x1800386f6  call    WPP_SF_
0x1800386fb  mov     rcx, [rbx+80h]
0x180038702  call    cs:__imp_NsiDisconnectFromServer
0x180038708  mov     qword ptr [rbx+80h], 0
0x180038713  jmp     loc_1800385F3
0x180038718  test    byte ptr [rcx+1Ch], 10h
0x18003871c  jz      loc_180038603
0x180038722  cmp     byte ptr [rcx+19h], 6
0x180038726  jb      loc_180038603
0x18003872c  mov     rcx, [rcx+10h]
0x180038730  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x180038737  mov     edx, 1Ah
0x18003873c  call    WPP_SF_
0x180038741  jmp     loc_180038603
```
