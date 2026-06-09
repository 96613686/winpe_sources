# CConfigServiceProvider2Impl::ConfigManagerNotification(ConfigManager2Notification,__int64)

- ea: `0x180007fa0`
- end: `0x1800080ff`
- name: `?ConfigManagerNotification@CConfigServiceProvider2Impl@@UEAAJW4ConfigManager2Notification@@_J@Z`
- size: `351`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800061e0`

## callees

- `0x180007fa0`
- `0x18000c408`
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
0x180007fa0  push    rbx
0x180007fa2  sub     rsp, 20h
0x180007fa6  xor     r9d, r9d
0x180007fa9  mov     ebx, r9d
0x180007fac  lea     r10d, [r9+5]
0x180007fb0  cmp     edx, r10d
0x180007fb3  jg      loc_18000807A
0x180007fb9  jz      loc_18000806E
0x180007fbf  test    edx, edx
0x180007fc1  jz      loc_180008062
0x180007fc7  sub     edx, 1
0x180007fca  jz      short loc_180008047
0x180007fcc  sub     edx, 1
0x180007fcf  jz      short loc_180008032
0x180007fd1  sub     edx, 1
0x180007fd4  jz      short loc_180008017
0x180007fd6  cmp     edx, 1
0x180007fd9  jnz     loc_180008093
0x180007fdf  cmp     [rcx+18h], r9d
0x180007fe3  jnz     loc_180008098
0x180007fe9  mov     dword ptr [rcx+18h], 4
0x180007ff0  test    r8, r8
0x180007ff3  jz      short loc_18000800D
0x180007ff5  mov     [rcx+10h], r8
0x180007ff9  mov     rcx, r8
0x180007ffc  mov     rax, [r8]
0x180007fff  mov     rax, [rax+8]
0x180008003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008008  jmp     loc_18000809D
0x18000800d  mov     ebx, 80070057h
0x180008012  jmp     loc_18000809D
0x180008017  mov     edx, [rcx+18h]
0x18000801a  cmp     edx, 8
0x18000801d  ja      short loc_180008098
0x18000801f  mov     eax, 151h
0x180008024  bt      eax, edx
0x180008027  jnb     short loc_180008098
0x180008029  mov     dword ptr [rcx+18h], 3
0x180008030  jmp     short loc_18000809D
0x180008032  cmp     dword ptr [rcx+18h], 1
0x180008036  jz      short loc_18000803E
0x180008038  cmp     dword ptr [rcx+18h], 0Ah
0x18000803c  jnz     short loc_180008098
0x18000803e  mov     dword ptr [rcx+18h], 2
0x180008045  jmp     short loc_18000809D
0x180008047  mov     edx, [rcx+18h]
0x18000804a  cmp     edx, 8
0x18000804d  ja      short loc_180008098
0x18000804f  mov     eax, 151h
0x180008054  bt      eax, edx
0x180008057  jnb     short loc_180008098
0x180008059  mov     dword ptr [rcx+18h], 1
0x180008060  jmp     short loc_18000809D
0x180008062  cmp     [rcx+18h], r9d
0x180008066  jnz     short loc_180008098
0x180008068  mov     [rcx+18h], r9d
0x18000806c  jmp     short loc_18000809D
0x18000806e  cmp     dword ptr [rcx+18h], 2
0x180008072  jnz     short loc_180008098
0x180008074  mov     [rcx+18h], r10d
0x180008078  jmp     short loc_18000809D
0x18000807a  sub     edx, 6
0x18000807d  jz      short loc_1800080F0
0x18000807f  sub     edx, 1
0x180008082  jz      short loc_1800080D8
0x180008084  sub     edx, 1
0x180008087  jz      short loc_1800080C9
0x180008089  sub     edx, 1
0x18000808c  jz      short loc_1800080B4
0x18000808e  cmp     edx, 1
0x180008091  jz      short loc_1800080A5
0x180008093  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008098  mov     ebx, 8000FFFFh
0x18000809d  mov     eax, ebx
0x18000809f  add     rsp, 20h
0x1800080a3  pop     rbx
0x1800080a4  retn
0x1800080a5  cmp     dword ptr [rcx+18h], 9
0x1800080a9  jnz     short loc_180008098
0x1800080ab  mov     dword ptr [rcx+18h], 0Ah
0x1800080b2  jmp     short loc_18000809D
0x1800080b4  cmp     dword ptr [rcx+18h], 1
0x1800080b8  jz      short loc_1800080C0
0x1800080ba  cmp     dword ptr [rcx+18h], 0Ah
0x1800080be  jnz     short loc_180008098
0x1800080c0  mov     dword ptr [rcx+18h], 9
0x1800080c7  jmp     short loc_18000809D
0x1800080c9  cmp     dword ptr [rcx+18h], 7
0x1800080cd  jnz     short loc_180008098
0x1800080cf  mov     dword ptr [rcx+18h], 8
0x1800080d6  jmp     short loc_18000809D
0x1800080d8  test    dword ptr [rcx+18h], 0FFFFFFF9h
0x1800080df  jnz     short loc_180008098
0x1800080e1  cmp     dword ptr [rcx+18h], 6
0x1800080e5  jz      short loc_180008098
0x1800080e7  mov     dword ptr [rcx+18h], 7
0x1800080ee  jmp     short loc_18000809D
0x1800080f0  cmp     [rcx+18h], r10d
0x1800080f4  jnz     short loc_180008098
0x1800080f6  mov     dword ptr [rcx+18h], 6
0x1800080fd  jmp     short loc_18000809D
```
