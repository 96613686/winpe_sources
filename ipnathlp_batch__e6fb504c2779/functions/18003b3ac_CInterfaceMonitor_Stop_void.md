# CInterfaceMonitor::Stop(void)

- ea: `0x18003b3ac`
- end: `0x18003b58b`
- name: `?Stop@CInterfaceMonitor@@QEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(CInterfaceMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800271d0`
- `0x18002776c`
- `0x18003b314`

## callees

- `0x18000ca20`
- `0x18003b3ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b3da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b3f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003b3f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003b488`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003b488`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003b498`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003b498`
- `WINNSI!NsiDisconnectFromServer` at `0x18003b541`
- `WINNSI!NsiDisconnectFromServer` at `0x18003b541`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003b46a`
- `WINNSI!NsiRpcDeregisterChangeNotification` at `0x18003b46a`

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
0x18003b3ac  mov     [rsp+arg_0], rbx
0x18003b3b1  mov     [rsp+arg_8], rdi
0x18003b3b6  push    r14
0x18003b3b8  sub     rsp, 20h
0x18003b3bc  mov     rbx, rcx
0x18003b3bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b3c6  lea     r14, WPP_GLOBAL_Control
0x18003b3cd  cmp     rcx, r14
0x18003b3d0  jnz     loc_18003B4B1
0x18003b3d6  lea     rcx, [rbx+58h]; lpCriticalSection
0x18003b3da  call    cs:__imp_EnterCriticalSection
0x18003b3e1  nop     dword ptr [rax+rax+00h]
0x18003b3e6  mov     rcx, [rbx+8]; pwk
0x18003b3ea  test    rcx, rcx
0x18003b3ed  jnz     loc_18003B483
0x18003b3f3  lea     rcx, [rbx+58h]; lpCriticalSection
0x18003b3f7  call    cs:__imp_LeaveCriticalSection
0x18003b3fe  nop     dword ptr [rax+rax+00h]
0x18003b403  cmp     qword ptr [rbx+88h], 0
0x18003b40b  jnz     short loc_18003B43F
0x18003b40d  cmp     qword ptr [rbx+80h], 0
0x18003b415  jnz     loc_18003B50D
0x18003b41b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b422  cmp     rcx, r14
0x18003b425  jnz     loc_18003B55D
0x18003b42b  mov     rbx, [rsp+28h+arg_0]
0x18003b430  xor     eax, eax
0x18003b432  mov     rdi, [rsp+28h+arg_8]
0x18003b437  add     rsp, 20h
0x18003b43b  pop     r14
0x18003b43d  retn
0x18003b43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b446  cmp     rcx, r14
0x18003b449  jnz     loc_18003B4DF
0x18003b44f  mov     r9, [rbx+88h]
0x18003b456  lea     rdx, NPI_MS_NDIS_MODULEID
0x18003b45d  mov     rcx, [rbx+80h]
0x18003b464  mov     r8d, 1
0x18003b46a  call    cs:__imp_NsiRpcDeregisterChangeNotification
0x18003b471  nop     dword ptr [rax+rax+00h]
0x18003b476  mov     qword ptr [rbx+88h], 0
0x18003b481  jmp     short loc_18003B40D
0x18003b483  mov     edx, 1; fCancelPendingCallbacks
0x18003b488  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003b48f  nop     dword ptr [rax+rax+00h]
0x18003b494  mov     rcx, [rbx+8]; pwk
0x18003b498  call    cs:__imp_CloseThreadpoolWork
0x18003b49f  nop     dword ptr [rax+rax+00h]
0x18003b4a4  mov     qword ptr [rbx+8], 0
0x18003b4ac  jmp     loc_18003B3F3
0x18003b4b1  test    byte ptr [rcx+1Ch], 10h
0x18003b4b5  jz      loc_18003B3D6
0x18003b4bb  cmp     byte ptr [rcx+19h], 6
0x18003b4bf  jb      loc_18003B3D6
0x18003b4c5  mov     rcx, [rcx+10h]
0x18003b4c9  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18003b4d0  mov     edx, 17h
0x18003b4d5  call    WPP_SF_
0x18003b4da  jmp     loc_18003B3D6
0x18003b4df  test    byte ptr [rcx+1Ch], 10h
0x18003b4e3  jz      loc_18003B44F
0x18003b4e9  cmp     byte ptr [rcx+19h], 5
0x18003b4ed  jb      loc_18003B44F
0x18003b4f3  mov     rcx, [rcx+10h]
0x18003b4f7  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18003b4fe  mov     edx, 18h
0x18003b503  call    WPP_SF_
0x18003b508  jmp     loc_18003B44F
0x18003b50d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b514  cmp     rcx, r14
0x18003b517  jz      short loc_18003B53A
0x18003b519  test    byte ptr [rcx+1Ch], 10h
0x18003b51d  jz      short loc_18003B53A
0x18003b51f  cmp     byte ptr [rcx+19h], 5
0x18003b523  jb      short loc_18003B53A
0x18003b525  mov     rcx, [rcx+10h]
0x18003b529  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18003b530  mov     edx, 19h
0x18003b535  call    WPP_SF_
0x18003b53a  mov     rcx, [rbx+80h]
0x18003b541  call    cs:__imp_NsiDisconnectFromServer
0x18003b548  nop     dword ptr [rax+rax+00h]
0x18003b54d  mov     qword ptr [rbx+80h], 0
0x18003b558  jmp     loc_18003B41B
0x18003b55d  test    byte ptr [rcx+1Ch], 10h
0x18003b561  jz      loc_18003B42B
0x18003b567  cmp     byte ptr [rcx+19h], 6
0x18003b56b  jb      loc_18003B42B
0x18003b571  mov     rcx, [rcx+10h]
0x18003b575  lea     r8, WPP_7d9c591b7bd93107528617e14d5ec105_Traceguids
0x18003b57c  mov     edx, 1Ah
0x18003b581  call    WPP_SF_
0x18003b586  jmp     loc_18003B42B
```
