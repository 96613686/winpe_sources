# EapHost::ECPManager::Run(void)

- ea: `0x18000f184`
- end: `0x18000f2c0`
- name: `?Run@ECPManager@EapHost@@AEAAIXZ`
- size: `316`
- prototype: `__int64 __fastcall(EapHost::ECPManager *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180010520`

## callees

- `0x180001f60`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c39c`
- `0x18000f184`
- `0x18000f77c`
- `0x18001064c`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000f22f`
- `ntdll!EtwEventEnabled` at `0x18000f22f`

## string_xrefs

- `0x18000f239`: `Detected service shutdown. Exiting the wait/sync loop and the ECP thread`

## pseudocode

```c
__int64 __fastcall EapHost::ECPManager::Run(EapHost::ECPManager *this)
{
  EapHost::ECPManager *v1; // rbx
  int v2; // r8d
  int v3; // r9d
  __int64 v4; // rax
  __int64; // rax
  const Exception *v6; // rbx
  unsigned int v7; // eax
  int v8; // eax
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rax
  const Exception *v24; // [rsp+48h] [rbp-840h] BYREF
  _BYTE v25[16]; // [rsp+50h] [rbp-838h] BYREF
  char *v26; // [rsp+60h] [rbp-828h]
  int v27; // [rsp+68h] [rbp-820h]
  int v28; // [rsp+6Ch] [rbp-81Ch]
  char v29[2048]; // [rsp+70h] [rbp-818h] BYREF

  v1 = this;
  while ( !*(_BYTE *)this )
  {
    if ( __eh34_try(0, 1) )
    {
      __eh34_scope_strut(1);
      EapHost::ECPManager::WaitBeforeNextSync(v1);
      EapHost::ECPManager::SyncDeviceWithRegistry(v1);
    }
    if ( __eh34_catch(1) )
    {
      if ( __eh34_catch_type(1, &Exception `RTTI Type Descriptor', &v24) )
      {
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v6 = v24;
        }
        else
        {
          v6 = v24;
          v7 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v24 + 8LL))(v24);
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17u,
            (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids,
            v7);
        }
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent) )
        {
          v8 = (*(__int64 (__fastcall **)(const Exception *))(*(_QWORD *)v6 + 8LL))(v6);
          if ( (int)StringCchPrintfA(v29, 0x800u, "Caught foundation exception in wait/sync loop, 0x%x", v8) >= 0
            && (byte_180020AC1 & 8) != 0 )
          {
            v11 = -1;
            do
              ++v11;
            while ( v29[v11] );
            v26 = v29;
            v27 = v11 + 1;
            v28 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (_QWORD *)(unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v9,
              v10,
              (__int64)v25);
          }
        }
        if ( !*((_DWORD *)this + 15) )
        {
          if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
            && (int)StringCchPrintfA(v29, 0x800u, "Too many error happened.  Exiting ECP thread.") >= 0
            && (byte_180020AC1 & 8) != 0 )
          {
            v14 = -1;
            do
              ++v14;
            while ( v29[v14] );
            v26 = v29;
            v27 = v14 + 1;
            v28 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (_QWORD *)(unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v12,
              v13,
              (__int64)v25);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
           = 1;
          __eh34_try_continuation(1, &Exception `RTTI Type Descriptor', &loc_18000F1D8);
          return ;
        }
        v1 = this;
        __eh34_try_continuation(1, &Exception `RTTI Type Descriptor', &loc_18000F1EC);
        continue;
      }
      if ( __eh34_catch_type(1, &std::exception `RTTI Type Descriptor', 0) )
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
          && (int)StringCchPrintfA(v29, 0x800u, "Caught std::exception in wait/sync loop") >= 0
          && (byte_180020AC1 & 8) != 0 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v29[v17] );
          v26 = v29;
          v27 = v17 + 1;
          v28 = 0;
          McGenEventWrite_EtwEventWriteTransfer(
            (_QWORD *)(unsigned int)&eaphost_Context,
            (unsigned int)DebugErrorEvent,
            v15,
            v16,
            (__int64)v25);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
        if ( !*((_DWORD *)this + 15) )
        {
          if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
            && (int)StringCchPrintfA(v29, 0x800u, "Too many error happened.  Exiting ECP thread.") >= 0
            && (byte_180020AC1 & 8) != 0 )
          {
            v20 = -1;
            do
              ++v20;
            while ( v29[v20] );
            v26 = v29;
            v27 = v20 + 1;
            v28 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (_QWORD *)(unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v18,
              v19,
              (__int64)v25);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
           = 1;
          __eh34_try_continuation(1, &std::exception `RTTI Type Descriptor', &loc_18000F1E2);
          return ;
        }
        v1 = this;
        __eh34_try_continuation(1, &std::exception `RTTI Type Descriptor', &loc_18000F1EC);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21u, (__int64)WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v29, 0x800u, "Detected service shutdown. Exiting the wait/sync loop and the ECP thread") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v4 = -1;
    do
      ++v4;
    while ( v29[v4] );
    v26 = v29;
    v27 = v4 + 1;
    v28 = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (_QWORD *)(unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v2,
      v3,
      (__int64)v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f184  push    rbx
0x18000f186  sub     rsp, 880h
0x18000f18d  mov     rax, cs:__security_cookie
0x18000f194  xor     rax, rsp
0x18000f197  mov     [rsp+888h+var_18], rax
0x18000f19f  mov     rbx, rcx
0x18000f1a2  mov     [rsp+888h+var_848], rcx
0x18000f1a7  mov     [rsp+888h+var_850], rcx
0x18000f1ac  mov     [rsp+888h+var_858], 0
0x18000f1b4  mov     rax, [rsp+888h+var_848]
0x18000f1b9  cmp     byte ptr [rax], 0
0x18000f1bc  jnz     short loc_18000F1F3
0x18000f1be  mov     rcx, rbx; this
0x18000f1c1  call    ?WaitBeforeNextSync@ECPManager@EapHost@@AEAAXXZ; EapHost::ECPManager::WaitBeforeNextSync(void)
0x18000f1c6  mov     rcx, rbx; this
0x18000f1c9  call    ?SyncDeviceWithRegistry@ECPManager@EapHost@@AEAAXXZ; EapHost::ECPManager::SyncDeviceWithRegistry(void)
0x18000f1ce  mov     [rsp+888h+var_858], 0
0x18000f1d6  jmp     short loc_18000F1B4
0x18000f1d8  mov     eax, 1
0x18000f1dd  jmp     loc_18000F2A6
0x18000f1e2  mov     eax, 1
0x18000f1e7  jmp     loc_18000F2A6
0x18000f1ec  mov     rbx, [rsp+888h+var_850]
0x18000f1f1  jmp     short loc_18000F1B4
0x18000f1f3  lea     rax, WPP_GLOBAL_Control
0x18000f1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f201  cmp     rcx, rax
0x18000f204  jz      short loc_18000F221
0x18000f206  test    byte ptr [rcx+1Ch], 4
0x18000f20a  jz      short loc_18000F221
0x18000f20c  mov     edx, 15h
0x18000f211  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f218  mov     rcx, [rcx+10h]
0x18000f21c  call    WPP_SF_
0x18000f221  lea     rdx, DebugInfoEvent
0x18000f228  mov     rcx, cs:eaphost_Context
0x18000f22f  call    cs:__imp_EtwEventEnabled
0x18000f235  test    al, al
0x18000f237  jz      short loc_18000F2A4
0x18000f239  lea     r8, aDetectedServic; "Detected service shutdown. Exiting the "...
0x18000f240  mov     edx, 800h; unsigned __int64
0x18000f245  lea     rcx, [rsp+888h+var_818]; char *
0x18000f24a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f24f  test    eax, eax
0x18000f251  js      short loc_18000F2A4
0x18000f253  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18000f25a  jge     short loc_18000F2A4
0x18000f25c  lea     rcx, [rsp+888h+var_818]
0x18000f261  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f265  inc     rax
0x18000f268  cmp     byte ptr [rcx+rax], 0
0x18000f26c  jnz     short loc_18000F265
0x18000f26e  inc     eax
0x18000f270  lea     rcx, [rsp+888h+var_818]
0x18000f275  mov     [rsp+888h+var_828], rcx
0x18000f27a  mov     [rsp+888h+var_820], eax
0x18000f27e  mov     [rsp+888h+var_81C], 0
0x18000f286  lea     rax, [rsp+888h+var_838]
0x18000f28b  mov     [rsp+888h+var_868], rax
0x18000f290  lea     rdx, DebugInfoEvent
0x18000f297  lea     rcx, eaphost_Context
0x18000f29e  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f2a3  nop
0x18000f2a4  xor     eax, eax
0x18000f2a6  mov     rcx, [rsp+888h+var_18]
0x18000f2ae  xor     rcx, rsp; StackCookie
0x18000f2b1  call    __security_check_cookie
0x18000f2b6  add     rsp, 880h
0x18000f2bd  pop     rbx
0x18000f2be  retn
```
