# NGENService::HandleServiceManagerHR(long)

- ea: `0x180002f44`
- end: `0x18000305a`
- name: `?HandleServiceManagerHR@NGENService@@YAJJ@Z`
- size: `278`
- prototype: `__int64 __fastcall(NGENService *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180004cac`
- `0x1800053a0`

## callees

- `0x180002f44`
- `0x18001a790`
- `0x18002e1d0`
- `0x18002e418`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180002fe8`
- `KERNEL32!SetEvent` at `0x180003040`
- `KERNEL32!SetEvent` at `0x180002fe8`
- `KERNEL32!SetEvent` at `0x180003040`

## string_xrefs

- `0x180002ff7`: `Service Manager returned CLR_OPTSVC_E_CONTROLLER_INTERRUPT.\n`
- `0x180002f8b`: `Service Manager returned 0x%08x. Transient failures: %u\n`
- `0x18000300e`: `Service Manager returned a fatal error (0x%08x). Will stop service\n`
- `0x180002fb8`: `Service reached limit of transient errors. Will shut down. Last error returned from Service Manager: 0x%08x.\n`

## pseudocode

```c
__int64 __fastcall NGENService::HandleServiceManagerHR(NGENService *this, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned __int16 *v6; // [rsp+20h] [rbp-18h]

  v2 = (unsigned int)this;
  if ( (int)this < 0 )
  {
    if ( (unsigned int)((_DWORD)this + 2147467263) <= 1 || (_DWORD)this == -2147024784 )
    {
      if ( !byte_180070758 )
      {
        LODWORD(v6) = (_DWORD)this;
        NGENService::EventLog(
          0,
          (const unsigned __int16 *)1,
          0x456u,
          (unsigned int)L"Service Manager returned a fatal error (0x%08x). Will stop service\n",
          v6);
        NGENService::ServiceUpdateState((NGENService *)3, v4);
        NGENService::g_bStopRequested = 1;
        SetEvent(NGENService::g_hSCMRequestEvent);
        byte_180070758 = 1;
      }
    }
    else if ( (_DWORD)this == -2146230784 )
    {
      NGENService::DebugLog((NGENService *)L"Service Manager returned CLR_OPTSVC_E_CONTROLLER_INTERRUPT.\n", a2);
    }
    else
    {
      ++dword_180070754;
      NGENService::DebugLog(
        (NGENService *)L"Service Manager returned 0x%08x. Transient failures: %u\n",
        (const unsigned __int16 *)(unsigned int)this);
      if ( (unsigned int)dword_180070754 >= 0x14 && !byte_180070750 )
      {
        LODWORD(v6) = v2;
        NGENService::EventLog(
          0,
          (const unsigned __int16 *)1,
          0x457u,
          (unsigned int)L"Service reached limit of transient errors. Will shut down. Last error returned from Service Manager: 0x%08x.\n",
          v6);
        NGENService::ServiceUpdateState((NGENService *)3, v3);
        NGENService::g_bStopRequested = 1;
        SetEvent(NGENService::g_hSCMRequestEvent);
        byte_180070750 = 1;
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180002f44  mov     [rsp+arg_0], rbx
0x180002f49  push    rdi
0x180002f4a  sub     rsp, 30h
0x180002f4e  mov     ebx, ecx
0x180002f50  test    ecx, ecx
0x180002f52  jns     loc_18000304D
0x180002f58  lea     eax, [rcx+7FFFBFFFh]
0x180002f5e  mov     edi, 1
0x180002f63  cmp     eax, edi
0x180002f65  jbe     loc_180003005
0x180002f6b  cmp     ecx, 80070070h
0x180002f71  jz      loc_180003005
0x180002f77  cmp     ecx, 80131E00h
0x180002f7d  jz      short loc_180002FF7
0x180002f7f  mov     r8d, cs:dword_180070754
0x180002f86  mov     edx, ecx; unsigned __int16 *
0x180002f88  add     r8d, edi
0x180002f8b  lea     rcx, aServiceManager_0; "Service Manager returned 0x%08x. Transi"...
0x180002f92  mov     cs:dword_180070754, r8d
0x180002f99  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180002f9e  cmp     cs:dword_180070754, 14h
0x180002fa5  jb      loc_18000304D
0x180002fab  cmp     cs:byte_180070750, 0
0x180002fb2  jnz     loc_18000304D
0x180002fb8  lea     r9, aServiceReached; "Service reached limit of transient erro"...
0x180002fbf  mov     dword ptr [rsp+38h+var_18], ebx; unsigned __int16 *
0x180002fc3  mov     r8d, 457h; unsigned __int16
0x180002fc9  mov     edx, edi; unsigned __int16 *
0x180002fcb  xor     ecx, ecx; this
0x180002fcd  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180002fd2  lea     ecx, [rdi+2]; this
0x180002fd5  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x180002fda  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x180002fe1  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, dil; Volatile<bool> NGENService::g_bStopRequested
0x180002fe8  call    cs:__imp_SetEvent
0x180002fee  mov     cs:byte_180070750, dil
0x180002ff5  jmp     short loc_18000304D
0x180002ff7  lea     rcx, aServiceManager; "Service Manager returned CLR_OPTSVC_E_C"...
0x180002ffe  call    ?DebugLog@NGENService@@YAXPEBGZZ; NGENService::DebugLog(ushort const *,...)
0x180003003  jmp     short loc_18000304D
0x180003005  cmp     cs:byte_180070758, 0
0x18000300c  jnz     short loc_18000304D
0x18000300e  lea     r9, aServiceManager_2; "Service Manager returned a fatal error "...
0x180003015  mov     dword ptr [rsp+38h+var_18], ebx; unsigned __int16 *
0x180003019  mov     r8d, 456h; unsigned __int16
0x18000301f  mov     edx, edi; unsigned __int16 *
0x180003021  xor     ecx, ecx; this
0x180003023  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180003028  mov     ecx, 3; this
0x18000302d  call    ?ServiceUpdateState@NGENService@@YAXK@Z; NGENService::ServiceUpdateState(ulong)
0x180003032  mov     rcx, cs:?g_hSCMRequestEvent@NGENService@@3PEAXEA; hEvent
0x180003039  mov     cs:?g_bStopRequested@NGENService@@3V?$Volatile@_N@@A, dil; Volatile<bool> NGENService::g_bStopRequested
0x180003040  call    cs:__imp_SetEvent
0x180003046  mov     cs:byte_180070758, dil
0x18000304d  mov     eax, ebx
0x18000304f  mov     rbx, [rsp+38h+arg_0]
0x180003054  add     rsp, 30h
0x180003058  pop     rdi
0x180003059  retn
```
