# AccessSetRouteState

- ea: `0x1800095b0`
- end: `0x18000968b`
- name: `AccessSetRouteState`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x1800095b0`
- `0x18000ac60`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000965a`
- `KERNEL32!LeaveCriticalSection` at `0x18000965a`
- `KERNEL32!EnterCriticalSection` at `0x180009644`
- `KERNEL32!EnterCriticalSection` at `0x180009644`

## string_xrefs

- `0x1800095d5`: `Leaving: AccessSetRouteState`
- `0x180009611`: `Leaving: AccessSetRouteState`
- `0x180009669`: `Leaving: AccessSetRouteState`

## pseudocode

```c
__int64 __fastcall AccessSetRouteState(int a1, __int64 a2, __int64 a3, unsigned int *a4, _DWORD *a5, int a6, int a7)
{
  unsigned int v8; // eax

  if ( a7 == 87 )
    return 50;
  if ( a1 == 1 )
  {
    v8 = *a4;
    *a4 = 12;
    if ( v8 >= 0xC )
    {
      *a5 = 34;
      EnterCriticalSection(&g_csFwdState);
      a5[2] = g_bSetRoutesToStack;
      LeaveCriticalSection(&g_csFwdState);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessSetRouteState");
      return 0;
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessSetRouteState");
      return 122;
    }
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessSetRouteState");
    return 87;
  }
}

```

## disassembly

```asm
0x1800095b0  push    rbx
0x1800095b2  sub     rsp, 20h
0x1800095b6  cmp     [rsp+28h+arg_30], 57h ; 'W'
0x1800095bb  jnz     short loc_1800095C7
0x1800095bd  mov     eax, 32h ; '2'
0x1800095c2  jmp     loc_180009685
0x1800095c7  cmp     ecx, 1
0x1800095ca  jz      short loc_1800095F9
0x1800095cc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800095d3  jz      short loc_1800095EF
0x1800095d5  lea     r8, aLeavingAccesss; "Leaving: AccessSetRouteState"
0x1800095dc  lea     rdx, RasRtrmgrTraceInfo
0x1800095e3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800095ea  call    McTemplateU0z_EventWriteTransfer
0x1800095ef  mov     eax, 57h ; 'W'
0x1800095f4  jmp     loc_180009685
0x1800095f9  mov     eax, [r9]
0x1800095fc  mov     dword ptr [r9], 0Ch
0x180009603  cmp     eax, 0Ch
0x180009606  jnb     short loc_180009632
0x180009608  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000960f  jz      short loc_18000962B
0x180009611  lea     r8, aLeavingAccesss; "Leaving: AccessSetRouteState"
0x180009618  lea     rdx, RasRtrmgrTraceInfo
0x18000961f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009626  call    McTemplateU0z_EventWriteTransfer
0x18000962b  mov     eax, 7Ah ; 'z'
0x180009630  jmp     short loc_180009685
0x180009632  mov     rbx, [rsp+28h+arg_20]
0x180009637  lea     rcx, g_csFwdState; lpCriticalSection
0x18000963e  mov     dword ptr [rbx], 22h ; '"'
0x180009644  call    cs:__imp_EnterCriticalSection
0x18000964a  mov     eax, cs:g_bSetRoutesToStack
0x180009650  lea     rcx, g_csFwdState; lpCriticalSection
0x180009657  mov     [rbx+8], eax
0x18000965a  call    cs:__imp_LeaveCriticalSection
0x180009660  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009667  jz      short loc_180009683
0x180009669  lea     r8, aLeavingAccesss; "Leaving: AccessSetRouteState"
0x180009670  lea     rdx, RasRtrmgrTraceInfo
0x180009677  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000967e  call    McTemplateU0z_EventWriteTransfer
0x180009683  xor     eax, eax
0x180009685  add     rsp, 20h
0x180009689  pop     rbx
0x18000968a  retn
```
