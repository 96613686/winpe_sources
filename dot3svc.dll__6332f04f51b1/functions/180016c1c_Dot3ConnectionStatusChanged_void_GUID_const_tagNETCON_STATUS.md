# Dot3ConnectionStatusChanged(void *,_GUID const *,tagNETCON_STATUS)

- ea: `0x180016c1c`
- end: `0x180016dc4`
- name: `?Dot3ConnectionStatusChanged@@YAJPEAXPEBU_GUID@@W4tagNETCON_STATUS@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(void *, const struct _GUID *, unsigned int)`
- caller_count: `7`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b4e4`
- `0x180023760`
- `0x180023ab0`
- `0x180023ce0`
- `0x180023f70`
- `0x180024170`
- `0x180024530`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180016c1c`
- `0x18001bb90`
- `0x180040010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cc9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cc9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016c9b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180016c9b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016d51`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180016d51`

## pseudocode

```c
__int64 __fastcall Dot3ConnectionStatusChanged(void *a1, const struct _GUID *a2, unsigned int a3)
{
  unsigned __int16 *v5; // rcx
  HRESULT v6; // ebx
  HRESULT v7; // eax
  struct _LIST_ENTRY *v8; // rcx
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  ppv = 0;
  v5 = (unsigned __int16 *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 113, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  }
  if ( !g_fHasNetmanBeenSeenStarted )
  {
    v6 = 0;
    g_fHasNetmanBeenSeenStarted = SvcRunning(v5);
    if ( !g_fHasNetmanBeenSeenStarted )
      goto LABEL_23;
  }
  v7 = CoInitializeEx(0, 0);
  v6 = v7;
  if ( v7 >= 0 )
  {
    v6 = CoCreateInstance(&CLSID_LegacyConnectionManager, 0, 0x17u, &IID_INetConnectionRefresh, &ppv);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 115, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 114, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
      }
      (*(void (__fastcall **)(LPVOID, const struct _GUID *, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, a2, a3);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    CoUninitialize();
    goto LABEL_23;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return (unsigned int)v6;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 116, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids, (unsigned int)v7);
LABEL_23:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v8[1].Blink) >= 4u && (BYTE4(v8[1].Blink) & 1) != 0 )
    WPP_SF_(v8[1].Flink, 117, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016c1c  mov     rax, rsp
0x180016c1f  mov     [rax+10h], rbx
0x180016c23  mov     [rax+18h], rsi
0x180016c27  mov     [rax+8], rcx
0x180016c2b  push    rdi
0x180016c2c  push    r12
0x180016c2e  push    r15
0x180016c30  sub     rsp, 30h
0x180016c34  mov     edi, r8d
0x180016c37  mov     qword ptr [rax+8], 0
0x180016c3f  mov     rsi, rdx
0x180016c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c49  lea     r15, WPP_GLOBAL_Control
0x180016c50  lea     r12, WPP_0eee27c7e0cd3271439d8d336f664c32_Traceguids
0x180016c57  cmp     rcx, r15
0x180016c5a  jz      short loc_180016C79
0x180016c5c  cmp     byte ptr [rcx+19h], 4
0x180016c60  jb      short loc_180016C79
0x180016c62  test    byte ptr [rcx+1Ch], 1
0x180016c66  jz      short loc_180016C79
0x180016c68  mov     rcx, [rcx+10h]
0x180016c6c  mov     edx, 71h ; 'q'
0x180016c71  mov     r8, r12
0x180016c74  call    WPP_SF_
0x180016c79  cmp     cs:?g_fHasNetmanBeenSeenStarted@@3HA, 0; int g_fHasNetmanBeenSeenStarted
0x180016c80  jnz     short loc_180016C97
0x180016c82  xor     ebx, ebx
0x180016c84  call    ?SvcRunning@@YAHPEAG@Z; SvcRunning(ushort *)
0x180016c89  mov     cs:?g_fHasNetmanBeenSeenStarted@@3HA, eax; int g_fHasNetmanBeenSeenStarted
0x180016c8f  test    eax, eax
0x180016c91  jz      loc_180016D85
0x180016c97  xor     edx, edx; dwCoInit
0x180016c99  xor     ecx, ecx; pvReserved
0x180016c9b  call    cs:__imp_CoInitializeEx
0x180016ca1  mov     ebx, eax
0x180016ca3  test    eax, eax
0x180016ca5  js      loc_180016D59
0x180016cab  xor     edx, edx; pUnkOuter
0x180016cad  lea     rax, [rsp+48h+arg_0]
0x180016cb2  lea     r9, IID_INetConnectionRefresh; riid
0x180016cb9  mov     [rsp+48h+ppv], rax; ppv
0x180016cbe  lea     rcx, CLSID_LegacyConnectionManager; rclsid
0x180016cc5  lea     r8d, [rdx+17h]; dwClsContext
0x180016cc9  call    cs:__imp_CoCreateInstance
0x180016ccf  mov     ebx, eax
0x180016cd1  test    eax, eax
0x180016cd3  js      short loc_180016D28
0x180016cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cdc  cmp     rcx, r15
0x180016cdf  jz      short loc_180016CFE
0x180016ce1  cmp     byte ptr [rcx+19h], 4
0x180016ce5  jb      short loc_180016CFE
0x180016ce7  test    byte ptr [rcx+1Ch], 1
0x180016ceb  jz      short loc_180016CFE
0x180016ced  mov     rcx, [rcx+10h]
0x180016cf1  mov     edx, 72h ; 'r'
0x180016cf6  mov     r8, r12
0x180016cf9  call    WPP_SF_
0x180016cfe  mov     rcx, [rsp+48h+arg_0]
0x180016d03  mov     r8d, edi
0x180016d06  mov     rdx, rsi
0x180016d09  mov     rax, [rcx]
0x180016d0c  mov     rax, [rax+40h]
0x180016d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d15  mov     rcx, [rsp+48h+arg_0]
0x180016d1a  mov     rax, [rcx]
0x180016d1d  mov     rax, [rax+10h]
0x180016d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d26  jmp     short loc_180016D51
0x180016d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d2f  cmp     rcx, r15
0x180016d32  jz      short loc_180016D51
0x180016d34  cmp     byte ptr [rcx+19h], 4
0x180016d38  jb      short loc_180016D51
0x180016d3a  test    byte ptr [rcx+1Ch], 1
0x180016d3e  jz      short loc_180016D51
0x180016d40  mov     rcx, [rcx+10h]
0x180016d44  mov     edx, 73h ; 's'
0x180016d49  mov     r8, r12
0x180016d4c  call    WPP_SF_
0x180016d51  call    cs:__imp_CoUninitialize
0x180016d57  jmp     short loc_180016D85
0x180016d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d60  cmp     rcx, r15
0x180016d63  jz      short loc_180016DAE
0x180016d65  cmp     byte ptr [rcx+19h], 4
0x180016d69  jb      short loc_180016D8C
0x180016d6b  test    byte ptr [rcx+1Ch], 1
0x180016d6f  jz      short loc_180016D8C
0x180016d71  mov     rcx, [rcx+10h]
0x180016d75  mov     edx, 74h ; 't'
0x180016d7a  mov     r9d, eax
0x180016d7d  mov     r8, r12
0x180016d80  call    WPP_SF_d
0x180016d85  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d8c  cmp     rcx, r15
0x180016d8f  jz      short loc_180016DAE
0x180016d91  cmp     byte ptr [rcx+19h], 4
0x180016d95  jb      short loc_180016DAE
0x180016d97  test    byte ptr [rcx+1Ch], 1
0x180016d9b  jz      short loc_180016DAE
0x180016d9d  mov     rcx, [rcx+10h]
0x180016da1  mov     edx, 75h ; 'u'
0x180016da6  mov     r8, r12
0x180016da9  call    WPP_SF_
0x180016dae  mov     rsi, [rsp+48h+arg_10]
0x180016db3  mov     eax, ebx
0x180016db5  mov     rbx, [rsp+48h+arg_8]
0x180016dba  add     rsp, 30h
0x180016dbe  pop     r15
0x180016dc0  pop     r12
0x180016dc2  pop     rdi
0x180016dc3  retn
```
