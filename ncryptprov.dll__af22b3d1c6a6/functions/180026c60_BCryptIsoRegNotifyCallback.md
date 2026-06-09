# BCryptIsoRegNotifyCallback

- ea: `0x180026c60`
- end: `0x180026e01`
- name: `BCryptIsoRegNotifyCallback`
- size: `417`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000af80`
- `0x18001b41c`
- `0x18001b634`
- `0x180026c60`
- `0x180028114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180026d8c`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180026d8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026caa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026caa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026df5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180026d5f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180026d5f`

## string_xrefs

- `0x180026da4`: `onecore\ds\security\cryptoapi\ncrypt\ium\lib\bcryptisoutils.cpp`

## pseudocode

```c
void __fastcall BCryptIsoRegNotifyCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _DWORD *Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // ebx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids);
  AcquireSRWLockExclusive(&SRWLock);
  if ( phkResult )
  {
    if ( qword_18007A218 )
    {
      if ( hObject )
      {
        BCryptIsoReadKeyguardRegistryData(Context);
        SetThreadpoolWait(qword_18007A218, hObject, 0);
        v7 = RegNotifyChangeKeyValue(phkResult, 1, 0x10000004u, hObject, 1);
        v8 = v7;
        if ( v7 )
        {
          DebugTraceError(v7, "lStatus", "onecore\\ds\\security\\cryptoapi\\ncrypt\\ium\\lib\\bcryptisoutils.cpp", 163);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids, v8);
        }
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 14;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v6 = 13;
        goto LABEL_8;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 12;
LABEL_8:
      WPP_SF_(v5[2], v6, &WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids);
    }
  }
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x180026c60  mov     [rsp+arg_0], rbx
0x180026c65  mov     [rsp+arg_8], rsi
0x180026c6a  push    rdi
0x180026c6b  sub     rsp, 30h
0x180026c6f  mov     rbx, rdx
0x180026c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c79  lea     rdi, WPP_GLOBAL_Control
0x180026c80  lea     rsi, WPP_c399dbf5c8d0391a198b3f913468b97f_Traceguids
0x180026c87  cmp     rcx, rdi
0x180026c8a  jz      short loc_180026CA3
0x180026c8c  test    byte ptr [rcx+1Ch], 8
0x180026c90  jz      short loc_180026CA3
0x180026c92  mov     rcx, [rcx+10h]
0x180026c96  mov     edx, 0Bh
0x180026c9b  mov     r8, rsi
0x180026c9e  call    WPP_SF_
0x180026ca3  lea     rcx, SRWLock; SRWLock
0x180026caa  call    cs:__imp_AcquireSRWLockExclusive
0x180026cb1  nop     dword ptr [rax+rax+00h]
0x180026cb6  cmp     cs:phkResult, 0
0x180026cbe  jnz     short loc_180026CF0
0x180026cc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180026cc7  cmp     rcx, rdi
0x180026cca  jz      loc_180026DDF
0x180026cd0  test    byte ptr [rcx+1Ch], 1
0x180026cd4  jz      loc_180026DDF
0x180026cda  mov     edx, 0Ch
0x180026cdf  mov     rcx, [rcx+10h]
0x180026ce3  mov     r8, rsi
0x180026ce6  call    WPP_SF_
0x180026ceb  jmp     loc_180026DDF
0x180026cf0  cmp     cs:qword_18007A218, 0
0x180026cf8  jnz     short loc_180026D1B
0x180026cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d01  cmp     rcx, rdi
0x180026d04  jz      loc_180026DDF
0x180026d0a  test    byte ptr [rcx+1Ch], 1
0x180026d0e  jz      loc_180026DDF
0x180026d14  mov     edx, 0Dh
0x180026d19  jmp     short loc_180026CDF
0x180026d1b  cmp     cs:hObject, 0
0x180026d23  jnz     short loc_180026D46
0x180026d25  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d2c  cmp     rcx, rdi
0x180026d2f  jz      loc_180026DDF
0x180026d35  test    byte ptr [rcx+1Ch], 1
0x180026d39  jz      loc_180026DDF
0x180026d3f  mov     edx, 0Eh
0x180026d44  jmp     short loc_180026CDF
0x180026d46  mov     rcx, rbx
0x180026d49  call    BCryptIsoReadKeyguardRegistryData
0x180026d4e  mov     rdx, cs:hObject; h
0x180026d55  xor     r8d, r8d; pftTimeout
0x180026d58  mov     rcx, cs:qword_18007A218; pwa
0x180026d5f  call    cs:__imp_SetThreadpoolWait
0x180026d66  nop     dword ptr [rax+rax+00h]
0x180026d6b  mov     r9, cs:hObject; hEvent
0x180026d72  mov     edx, 1; bWatchSubtree
0x180026d77  mov     rcx, cs:phkResult; hKey
0x180026d7e  mov     r8d, 10000004h; dwNotifyFilter
0x180026d84  mov     [rsp+38h+fAsynchronous], 1; fAsynchronous
0x180026d8c  call    cs:__imp_RegNotifyChangeKeyValue
0x180026d93  nop     dword ptr [rax+rax+00h]
0x180026d98  mov     ebx, eax
0x180026d9a  test    eax, eax
0x180026d9c  jz      short loc_180026DDF
0x180026d9e  mov     r9d, 0A3h
0x180026da4  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180026dab  lea     rdx, aLstatus; "lStatus"
0x180026db2  mov     ecx, eax
0x180026db4  call    DebugTraceError
0x180026db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180026dc0  cmp     rcx, rdi
0x180026dc3  jz      short loc_180026DDF
0x180026dc5  test    byte ptr [rcx+1Ch], 1
0x180026dc9  jz      short loc_180026DDF
0x180026dcb  mov     rcx, [rcx+10h]
0x180026dcf  mov     edx, 0Fh
0x180026dd4  mov     r9d, ebx
0x180026dd7  mov     r8, rsi
0x180026dda  call    WPP_SF_D
0x180026ddf  lea     rcx, SRWLock
0x180026de6  mov     rbx, [rsp+38h+arg_0]
0x180026deb  mov     rsi, [rsp+38h+arg_8]
0x180026df0  add     rsp, 30h
0x180026df4  pop     rdi
0x180026df5  jmp     cs:__imp_ReleaseSRWLockExclusive
```
