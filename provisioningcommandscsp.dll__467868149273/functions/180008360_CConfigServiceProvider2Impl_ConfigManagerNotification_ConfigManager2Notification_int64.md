# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180008360`
- end: `0x1800084c0`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800064d0`

## callees

- `0x180008360`
- `0x18000cab4`
- `0x18000e010`

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
0x180008360  push    rbx
0x180008362  sub     rsp, 20h
0x180008366  xor     r9d, r9d
0x180008369  mov     ebx, r9d
0x18000836c  lea     r10d, [r9+5]
0x180008370  cmp     edx, r10d
0x180008373  jg      loc_18000843A
0x180008379  jz      loc_18000842E
0x18000837f  test    edx, edx
0x180008381  jz      loc_180008422
0x180008387  sub     edx, 1
0x18000838a  jz      short loc_180008407
0x18000838c  sub     edx, 1
0x18000838f  jz      short loc_1800083F2
0x180008391  sub     edx, 1
0x180008394  jz      short loc_1800083D7
0x180008396  cmp     edx, 1
0x180008399  jnz     loc_180008453
0x18000839f  cmp     [rcx+18h], r9d
0x1800083a3  jnz     loc_180008458
0x1800083a9  mov     dword ptr [rcx+18h], 4
0x1800083b0  test    r8, r8
0x1800083b3  jz      short loc_1800083CD
0x1800083b5  mov     [rcx+10h], r8
0x1800083b9  mov     rcx, r8
0x1800083bc  mov     rax, [r8]
0x1800083bf  mov     rax, [rax+8]
0x1800083c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083c8  jmp     loc_18000845D
0x1800083cd  mov     ebx, 80070057h
0x1800083d2  jmp     loc_18000845D
0x1800083d7  mov     edx, [rcx+18h]
0x1800083da  cmp     edx, 8
0x1800083dd  ja      short loc_180008458
0x1800083df  mov     eax, 151h
0x1800083e4  bt      eax, edx
0x1800083e7  jnb     short loc_180008458
0x1800083e9  mov     dword ptr [rcx+18h], 3
0x1800083f0  jmp     short loc_18000845D
0x1800083f2  cmp     dword ptr [rcx+18h], 1
0x1800083f6  jz      short loc_1800083FE
0x1800083f8  cmp     dword ptr [rcx+18h], 0Ah
0x1800083fc  jnz     short loc_180008458
0x1800083fe  mov     dword ptr [rcx+18h], 2
0x180008405  jmp     short loc_18000845D
0x180008407  mov     edx, [rcx+18h]
0x18000840a  cmp     edx, 8
0x18000840d  ja      short loc_180008458
0x18000840f  mov     eax, 151h
0x180008414  bt      eax, edx
0x180008417  jnb     short loc_180008458
0x180008419  mov     dword ptr [rcx+18h], 1
0x180008420  jmp     short loc_18000845D
0x180008422  cmp     [rcx+18h], r9d
0x180008426  jnz     short loc_180008458
0x180008428  mov     [rcx+18h], r9d
0x18000842c  jmp     short loc_18000845D
0x18000842e  cmp     dword ptr [rcx+18h], 2
0x180008432  jnz     short loc_180008458
0x180008434  mov     [rcx+18h], r10d
0x180008438  jmp     short loc_18000845D
0x18000843a  sub     edx, 6
0x18000843d  jz      short loc_1800084B1
0x18000843f  sub     edx, 1
0x180008442  jz      short loc_180008499
0x180008444  sub     edx, 1
0x180008447  jz      short loc_18000848A
0x180008449  sub     edx, 1
0x18000844c  jz      short loc_180008475
0x18000844e  cmp     edx, 1
0x180008451  jz      short loc_180008466
0x180008453  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008458  mov     ebx, 8000FFFFh
0x18000845d  mov     eax, ebx
0x18000845f  add     rsp, 20h
0x180008463  pop     rbx
0x180008464  retn
0x180008466  cmp     dword ptr [rcx+18h], 9
0x18000846a  jnz     short loc_180008458
0x18000846c  mov     dword ptr [rcx+18h], 0Ah
0x180008473  jmp     short loc_18000845D
0x180008475  cmp     dword ptr [rcx+18h], 1
0x180008479  jz      short loc_180008481
0x18000847b  cmp     dword ptr [rcx+18h], 0Ah
0x18000847f  jnz     short loc_180008458
0x180008481  mov     dword ptr [rcx+18h], 9
0x180008488  jmp     short loc_18000845D
0x18000848a  cmp     dword ptr [rcx+18h], 7
0x18000848e  jnz     short loc_180008458
0x180008490  mov     dword ptr [rcx+18h], 8
0x180008497  jmp     short loc_18000845D
0x180008499  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x1800084a0  jnz     short loc_180008458
0x1800084a2  cmp     dword ptr [rcx+18h], 6
0x1800084a6  jz      short loc_180008458
0x1800084a8  mov     dword ptr [rcx+18h], 7
0x1800084af  jmp     short loc_18000845D
0x1800084b1  cmp     [rcx+18h], r10d
0x1800084b5  jnz     short loc_180008458
0x1800084b7  mov     dword ptr [rcx+18h], 6
0x1800084be  jmp     short loc_18000845D
```
