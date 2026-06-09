# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x18000a730`
- end: `0x18000a890`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004fb0`

## callees

- `0x18000a730`
- `0x180028fa0`
- `0x180038010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::ConfigManagerNotification(__int64 a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // edx
  int v10; // eax
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx

  v3 = 0;
  if ( a2 > 5 )
  {
    v11 = a2 - 6;
    if ( !v11 )
    {
      if ( *(_DWORD *)(a1 + 24) == 5 )
      {
        *(_DWORD *)(a1 + 24) = 6;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      if ( (*(_DWORD *)(a1 + 24) & 0xFFFFFFF9) == 0 && *(_DWORD *)(a1 + 24) != 6 )
      {
        *(_DWORD *)(a1 + 24) = 7;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      if ( *(_DWORD *)(a1 + 24) == 7 )
      {
        *(_DWORD *)(a1 + 24) = 8;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
      {
        *(_DWORD *)(a1 + 24) = 9;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    if ( v14 == 1 )
    {
      if ( *(_DWORD *)(a1 + 24) == 9 )
      {
        *(_DWORD *)(a1 + 24) = 10;
        return v3;
      }
      return (unsigned int)-2147418113;
    }
    goto LABEL_30;
  }
  if ( a2 == 5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 2 )
    {
      *(_DWORD *)(a1 + 24) = 5;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  if ( !a2 )
  {
    if ( !*(_DWORD *)(a1 + 24) )
    {
      *(_DWORD *)(a1 + 24) = 0;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v4 = a2 - 1;
  if ( !v4 )
  {
    v9 = *(_DWORD *)(a1 + 24);
    if ( v9 <= 8 )
    {
      v10 = 337;
      if ( _bittest(&v10, v9) )
      {
        *(_DWORD *)(a1 + 24) = 1;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    if ( *(_DWORD *)(a1 + 24) == 1 || *(_DWORD *)(a1 + 24) == 10 )
    {
      *(_DWORD *)(a1 + 24) = 2;
      return v3;
    }
    return (unsigned int)-2147418113;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v7 = *(_DWORD *)(a1 + 24);
    if ( v7 <= 8 )
    {
      v8 = 337;
      if ( _bittest(&v8, v7) )
      {
        *(_DWORD *)(a1 + 24) = 3;
        return v3;
      }
    }
    return (unsigned int)-2147418113;
  }
  if ( v6 != 1 )
  {
LABEL_30:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return (unsigned int)-2147418113;
  }
  if ( *(_DWORD *)(a1 + 24) )
    return (unsigned int)-2147418113;
  *(_DWORD *)(a1 + 24) = 4;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 16) = a3;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000a730  push    rbx
0x18000a732  sub     rsp, 20h
0x18000a736  xor     r9d, r9d
0x18000a739  mov     ebx, r9d
0x18000a73c  lea     r10d, [r9+5]
0x18000a740  cmp     edx, r10d
0x18000a743  jg      loc_18000A80A
0x18000a749  jz      loc_18000A7FE
0x18000a74f  test    edx, edx
0x18000a751  jz      loc_18000A7F2
0x18000a757  sub     edx, 1
0x18000a75a  jz      short loc_18000A7D7
0x18000a75c  sub     edx, 1
0x18000a75f  jz      short loc_18000A7C2
0x18000a761  sub     edx, 1
0x18000a764  jz      short loc_18000A7A7
0x18000a766  cmp     edx, 1
0x18000a769  jnz     loc_18000A823
0x18000a76f  cmp     [rcx+18h], r9d
0x18000a773  jnz     loc_18000A828
0x18000a779  mov     dword ptr [rcx+18h], 4
0x18000a780  test    r8, r8
0x18000a783  jz      short loc_18000A79D
0x18000a785  mov     [rcx+10h], r8
0x18000a789  mov     rcx, r8
0x18000a78c  mov     rax, [r8]
0x18000a78f  mov     rax, [rax+8]
0x18000a793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a798  jmp     loc_18000A82D
0x18000a79d  mov     ebx, 80070057h
0x18000a7a2  jmp     loc_18000A82D
0x18000a7a7  mov     edx, [rcx+18h]
0x18000a7aa  cmp     edx, 8
0x18000a7ad  ja      short loc_18000A828
0x18000a7af  mov     eax, 151h
0x18000a7b4  bt      eax, edx
0x18000a7b7  jnb     short loc_18000A828
0x18000a7b9  mov     dword ptr [rcx+18h], 3
0x18000a7c0  jmp     short loc_18000A82D
0x18000a7c2  cmp     dword ptr [rcx+18h], 1
0x18000a7c6  jz      short loc_18000A7CE
0x18000a7c8  cmp     dword ptr [rcx+18h], 0Ah
0x18000a7cc  jnz     short loc_18000A828
0x18000a7ce  mov     dword ptr [rcx+18h], 2
0x18000a7d5  jmp     short loc_18000A82D
0x18000a7d7  mov     edx, [rcx+18h]
0x18000a7da  cmp     edx, 8
0x18000a7dd  ja      short loc_18000A828
0x18000a7df  mov     eax, 151h
0x18000a7e4  bt      eax, edx
0x18000a7e7  jnb     short loc_18000A828
0x18000a7e9  mov     dword ptr [rcx+18h], 1
0x18000a7f0  jmp     short loc_18000A82D
0x18000a7f2  cmp     [rcx+18h], r9d
0x18000a7f6  jnz     short loc_18000A828
0x18000a7f8  mov     [rcx+18h], r9d
0x18000a7fc  jmp     short loc_18000A82D
0x18000a7fe  cmp     dword ptr [rcx+18h], 2
0x18000a802  jnz     short loc_18000A828
0x18000a804  mov     [rcx+18h], r10d
0x18000a808  jmp     short loc_18000A82D
0x18000a80a  sub     edx, 6
0x18000a80d  jz      short loc_18000A881
0x18000a80f  sub     edx, 1
0x18000a812  jz      short loc_18000A869
0x18000a814  sub     edx, 1
0x18000a817  jz      short loc_18000A85A
0x18000a819  sub     edx, 1
0x18000a81c  jz      short loc_18000A845
0x18000a81e  cmp     edx, 1
0x18000a821  jz      short loc_18000A836
0x18000a823  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "0")
0x18000a828  mov     ebx, 8000FFFFh
0x18000a82d  mov     eax, ebx
0x18000a82f  add     rsp, 20h
0x18000a833  pop     rbx
0x18000a834  retn
0x18000a836  cmp     dword ptr [rcx+18h], 9
0x18000a83a  jnz     short loc_18000A828
0x18000a83c  mov     dword ptr [rcx+18h], 0Ah
0x18000a843  jmp     short loc_18000A82D
0x18000a845  cmp     dword ptr [rcx+18h], 1
0x18000a849  jz      short loc_18000A851
0x18000a84b  cmp     dword ptr [rcx+18h], 0Ah
0x18000a84f  jnz     short loc_18000A828
0x18000a851  mov     dword ptr [rcx+18h], 9
0x18000a858  jmp     short loc_18000A82D
0x18000a85a  cmp     dword ptr [rcx+18h], 7
0x18000a85e  jnz     short loc_18000A828
0x18000a860  mov     dword ptr [rcx+18h], 8
0x18000a867  jmp     short loc_18000A82D
0x18000a869  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x18000a870  jnz     short loc_18000A828
0x18000a872  cmp     dword ptr [rcx+18h], 6
0x18000a876  jz      short loc_18000A828
0x18000a878  mov     dword ptr [rcx+18h], 7
0x18000a87f  jmp     short loc_18000A82D
0x18000a881  cmp     [rcx+18h], r10d
0x18000a885  jnz     short loc_18000A828
0x18000a887  mov     dword ptr [rcx+18h], 6
0x18000a88e  jmp     short loc_18000A82D
```
