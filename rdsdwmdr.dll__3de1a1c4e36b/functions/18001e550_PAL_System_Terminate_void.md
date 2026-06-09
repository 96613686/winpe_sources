# PAL_System_Terminate(void)

- ea: `0x18001e550`
- end: `0x18001e6c0`
- name: `?PAL_System_Terminate@@YAJXZ`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001e40c`

## callees

- `0x18001d114`
- `0x18001e550`
- `0x18001ef44`
- `0x18002a888`
- `0x18002ab18`
- `0x18002ad68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18001e575`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x18001e575`

## string_xrefs

- `0x18001e60b`: `Failed to unregister the thread window class`

## pseudocode

```c
__int64 PAL_System_Terminate(void)
{
  __int64 v0; // rdx
  void *v1; // rcx
  int v2; // ebx
  __int64 v3; // r8
  __int64 v4; // r9
  int CurrentThreadActivityIdPrefix; // eax
  __int64 v6; // rdx
  void *v7; // rcx
  int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  int v11; // eax
  int v12; // ebx
  int v13; // eax
  __int64 v15; // [rsp+28h] [rbp-10h]
  int v16; // [rsp+28h] [rbp-10h]

  if ( (unsigned int)(g_PAL_SYS_initState - 1) > 1 )
    goto LABEL_20;
  if ( g_PAL_SYS_threadContextIndex )
  {
    TlsFree(g_PAL_SYS_threadContextIndex);
    g_PAL_SYS_threadContextIndex = 0;
  }
  v2 = PAL_Terminate_Timer_Globals();
  if ( v2 < 0 )
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = v2;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        (unsigned int)WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"Failed to terminate timer globals",
        v16);
    }
  }
  v8 = PAL_System_Win32_ThreadUnRegisterWindowClass((__int64)v1, v0, v3, v4);
  if ( v8 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(v15) = v8;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        (unsigned int)WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids,
        v11,
        (__int64)"Failed to unregister the thread window class",
        v15);
    }
  }
  v12 = PAL_System_Win32_TimerUnRegisterWindowClass((__int64)v7, v6, v9, v10);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v15) = v12;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      (unsigned int)WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids,
      v13,
      (__int64)"Failed to unregister the timer window class",
      v15);
  }
  g_PAL_SYS_dbgConfig = 0;
  dword_180044D58 = 0;
  if ( g_PAL_SYS_initState != 1 )
LABEL_20:
    g_PAL_SYS_initState = 3;
  return 0;
}

```

## disassembly

```asm
0x18001e550  mov     [rsp+arg_0], rbx
0x18001e555  push    rbp
0x18001e556  sub     rsp, 30h
0x18001e55a  mov     eax, cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A; PAL_SYS_STATE g_PAL_SYS_initState
0x18001e560  dec     eax
0x18001e562  cmp     eax, 1
0x18001e565  ja      loc_18001E6A9
0x18001e56b  mov     ecx, cs:?g_PAL_SYS_threadContextIndex@@3KA; dwTlsIndex
0x18001e571  test    ecx, ecx
0x18001e573  jz      short loc_18001E585
0x18001e575  call    cs:__imp_TlsFree
0x18001e57b  mov     cs:?g_PAL_SYS_threadContextIndex@@3KA, 0; ulong g_PAL_SYS_threadContextIndex
0x18001e585  call    ?PAL_Terminate_Timer_Globals@@YAJXZ; PAL_Terminate_Timer_Globals(void)
0x18001e58a  lea     rbp, WPP_GLOBAL_Control
0x18001e591  mov     ebx, eax
0x18001e593  test    eax, eax
0x18001e595  jns     short loc_18001E5E3
0x18001e597  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e59e  cmp     rcx, rbp
0x18001e5a1  jz      short loc_18001E5E3
0x18001e5a3  test    byte ptr [rcx+1Ch], 8
0x18001e5a7  jz      short loc_18001E5E3
0x18001e5a9  cmp     byte ptr [rcx+19h], 2
0x18001e5ad  jb      short loc_18001E5E3
0x18001e5af  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e5b4  lea     rcx, aFailedToTermin; "Failed to terminate timer globals"
0x18001e5bb  mov     [rsp+38h+var_10], ebx
0x18001e5bf  mov     [rsp+38h+var_18], rcx
0x18001e5c4  lea     r8, WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids
0x18001e5cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5d2  mov     edx, 0Ch
0x18001e5d7  mov     r9d, eax
0x18001e5da  mov     rcx, [rcx+10h]
0x18001e5de  call    WPP_SF_DsD
0x18001e5e3  call    ?PAL_System_Win32_ThreadUnRegisterWindowClass@@YAJXZ; PAL_System_Win32_ThreadUnRegisterWindowClass(void)
0x18001e5e8  mov     ebx, eax
0x18001e5ea  test    eax, eax
0x18001e5ec  jns     short loc_18001E63A
0x18001e5ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5f5  cmp     rcx, rbp
0x18001e5f8  jz      short loc_18001E63A
0x18001e5fa  test    byte ptr [rcx+1Ch], 8
0x18001e5fe  jz      short loc_18001E63A
0x18001e600  cmp     byte ptr [rcx+19h], 2
0x18001e604  jb      short loc_18001E63A
0x18001e606  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e60b  lea     rcx, aFailedToUnregi_0; "Failed to unregister the thread window "...
0x18001e612  mov     [rsp+38h+var_10], ebx
0x18001e616  mov     [rsp+38h+var_18], rcx
0x18001e61b  lea     r8, WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids
0x18001e622  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e629  mov     edx, 0Dh
0x18001e62e  mov     r9d, eax
0x18001e631  mov     rcx, [rcx+10h]
0x18001e635  call    WPP_SF_DsD
0x18001e63a  call    ?PAL_System_Win32_TimerUnRegisterWindowClass@@YAJXZ; PAL_System_Win32_TimerUnRegisterWindowClass(void)
0x18001e63f  mov     ebx, eax
0x18001e641  test    eax, eax
0x18001e643  jns     short loc_18001E691
0x18001e645  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e64c  cmp     rcx, rbp
0x18001e64f  jz      short loc_18001E691
0x18001e651  test    byte ptr [rcx+1Ch], 8
0x18001e655  jz      short loc_18001E691
0x18001e657  cmp     byte ptr [rcx+19h], 2
0x18001e65b  jb      short loc_18001E691
0x18001e65d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e662  lea     rcx, aFailedToUnregi; "Failed to unregister the timer window c"...
0x18001e669  mov     [rsp+38h+var_10], ebx
0x18001e66d  mov     [rsp+38h+var_18], rcx
0x18001e672  lea     r8, WPP_fa7f44a4abfa34436a622488f906f8c4_Traceguids
0x18001e679  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e680  mov     edx, 0Eh
0x18001e685  mov     r9d, eax
0x18001e688  mov     rcx, [rcx+10h]
0x18001e68c  call    WPP_SF_DsD
0x18001e691  xor     eax, eax
0x18001e693  cmp     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 1; PAL_SYS_STATE g_PAL_SYS_initState
0x18001e69a  mov     cs:?g_PAL_SYS_dbgConfig@@3UtagPAL_SYS_DBG_CONFIG@@A, rax; tagPAL_SYS_DBG_CONFIG g_PAL_SYS_dbgConfig
0x18001e6a1  mov     cs:dword_180044D58, eax
0x18001e6a7  jz      short loc_18001E6B3
0x18001e6a9  mov     cs:?g_PAL_SYS_initState@@3W4PAL_SYS_STATE@@A, 3; PAL_SYS_STATE g_PAL_SYS_initState
0x18001e6b3  mov     rbx, [rsp+38h+arg_0]
0x18001e6b8  xor     eax, eax
0x18001e6ba  add     rsp, 30h
0x18001e6be  pop     rbp
0x18001e6bf  retn
```
