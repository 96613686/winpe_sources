# ScPolicyServiceHandlerEx

- ea: `0x18001b490`
- end: `0x18001b5b4`
- name: `ScPolicyServiceHandlerEx`
- size: `292`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004600`
- `0x1800154f4`
- `0x18001af6c`
- `0x18001b278`
- `0x18001b490`
- `0x18001be50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b5a1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b5a1`

## pseudocode

```c
__int64 __fastcall ScPolicyServiceHandlerEx(DWORD dwControl, int dwEventType, _DWORD *lpEventData, LPVOID lpContext)
{
  unsigned int v4; // edi
  DWORD v6; // ecx
  DWORD v7; // ecx
  __int64 v8; // rcx
  int v9; // r8d
  int v10; // r9d
  STRSAFE_LPSTR v11; // rcx
  int v12; // edx
  __int64 v13; // rcx

  v4 = 0;
  v6 = dwControl - 1;
  if ( !v6 || (v7 = v6 - 4) == 0 )
  {
    CommonReportServiceStatus(&g_ScPolicyStatus, g_hScPolicyStatus, 3u, 0, 0);
    SetEvent(g_hScPolicyStopEvent);
    return v4;
  }
  if ( v7 != 9 )
    return 120;
  if ( dwEventType == 1 )
  {
LABEL_13:
    ScPolicyCheckForSmartcardAuth((unsigned int)lpEventData[1], dwEventType);
    WppTraceIndent(v8, 2);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control[28] & 1) != 0
      && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
    {
      v12 = 23;
LABEL_17:
      WPP_SF_sdD(*((_QWORD *)v11 + 2), v12, v9, v10, lpEventData[1], 0);
      return v4;
    }
    return v4;
  }
  if ( dwEventType != 2 )
  {
    if ( dwEventType == 3 )
      goto LABEL_13;
    if ( dwEventType != 4 )
    {
      if ( dwEventType == 5 )
        goto LABEL_13;
      if ( dwEventType != 6 && dwEventType != 7 )
      {
        if ( dwEventType != 8 )
          return v4;
        goto LABEL_13;
      }
    }
  }
  ScPolicyDeleteSession((unsigned int)lpEventData[1], dwEventType);
  WppTraceIndent(v13, 2);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 4u )
  {
    v12 = 24;
    goto LABEL_17;
  }
  return v4;
}

```

## disassembly

```asm
0x18001b490  mov     [rsp+arg_0], rbx
0x18001b495  push    rdi
0x18001b496  sub     rsp, 30h
0x18001b49a  xor     edi, edi
0x18001b49c  mov     rbx, r8
0x18001b49f  sub     ecx, 1
0x18001b4a2  jz      loc_18001B57C
0x18001b4a8  sub     ecx, 4
0x18001b4ab  jz      loc_18001B57C
0x18001b4b1  cmp     ecx, 9
0x18001b4b4  jz      short loc_18001B4C0
0x18001b4b6  mov     edi, 78h ; 'x'
0x18001b4bb  jmp     loc_18001B5A7
0x18001b4c0  mov     eax, edx
0x18001b4c2  sub     eax, 1
0x18001b4c5  jz      short loc_18001B4EE
0x18001b4c7  sub     eax, 1
0x18001b4ca  jz      short loc_18001B543
0x18001b4cc  sub     eax, 1
0x18001b4cf  jz      short loc_18001B4EE
0x18001b4d1  sub     eax, 1
0x18001b4d4  jz      short loc_18001B543
0x18001b4d6  sub     eax, 1
0x18001b4d9  jz      short loc_18001B4EE
0x18001b4db  sub     eax, 1
0x18001b4de  jz      short loc_18001B543
0x18001b4e0  sub     eax, 1
0x18001b4e3  jz      short loc_18001B543
0x18001b4e5  cmp     eax, 1
0x18001b4e8  jnz     loc_18001B5A7
0x18001b4ee  mov     ecx, [r8+4]
0x18001b4f2  call    ScPolicyCheckForSmartcardAuth
0x18001b4f7  mov     edx, 2
0x18001b4fc  call    WppTraceIndent
0x18001b501  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b508  lea     rax, WPP_GLOBAL_Control
0x18001b50f  cmp     rcx, rax
0x18001b512  jz      loc_18001B5A7
0x18001b518  test    byte ptr [rcx+1Ch], 1
0x18001b51c  jz      loc_18001B5A7
0x18001b522  cmp     byte ptr [rcx+19h], 4
0x18001b526  jb      short loc_18001B5A7
0x18001b528  mov     edx, 17h
0x18001b52d  mov     eax, [rbx+4]
0x18001b530  mov     rcx, [rcx+10h]
0x18001b534  mov     [rsp+38h+var_10], edi
0x18001b538  mov     [rsp+38h+var_18], eax
0x18001b53c  call    WPP_SF_sdD
0x18001b541  jmp     short loc_18001B5A7
0x18001b543  mov     ecx, [r8+4]
0x18001b547  call    ScPolicyDeleteSession
0x18001b54c  mov     edx, 2
0x18001b551  call    WppTraceIndent
0x18001b556  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b55d  lea     rax, WPP_GLOBAL_Control
0x18001b564  cmp     rcx, rax
0x18001b567  jz      short loc_18001B5A7
0x18001b569  test    byte ptr [rcx+1Ch], 1
0x18001b56d  jz      short loc_18001B5A7
0x18001b56f  cmp     byte ptr [rcx+19h], 4
0x18001b573  jb      short loc_18001B5A7
0x18001b575  mov     edx, 18h
0x18001b57a  jmp     short loc_18001B52D
0x18001b57c  mov     rdx, cs:g_hScPolicyStatus; hServiceStatus
0x18001b583  lea     rcx, g_ScPolicyStatus; lpServiceStatus
0x18001b58a  xor     r9d, r9d
0x18001b58d  mov     [rsp+38h+var_18], edi; int
0x18001b591  lea     r8d, [r9+3]
0x18001b595  call    CommonReportServiceStatus
0x18001b59a  mov     rcx, cs:g_hScPolicyStopEvent; hEvent
0x18001b5a1  call    cs:__imp_SetEvent
0x18001b5a7  mov     rbx, [rsp+38h+arg_0]
0x18001b5ac  mov     eax, edi
0x18001b5ae  add     rsp, 30h
0x18001b5b2  pop     rdi
0x18001b5b3  retn
```
