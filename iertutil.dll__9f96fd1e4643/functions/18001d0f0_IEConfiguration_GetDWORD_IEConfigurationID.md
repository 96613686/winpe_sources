# IEConfiguration_GetDWORD(IEConfigurationID)

- ea: `0x18001d0f0`
- end: `0x18001d4c6`
- name: `?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z`
- size: `982`
- prototype: ``
- caller_count: `26`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001ae48`
- `0x18001b510`
- `0x18001bd80`
- `0x18001c6e0`
- `0x18001e950`
- `0x18001fb24`
- `0x180020014`
- `0x180020a1c`
- `0x180020f60`
- `0x180023d98`
- `0x180024960`
- `0x18002fe60`
- `0x180031a0c`
- `0x180042430`
- `0x1800478b0`
- `0x180049850`
- `0x180049c98`
- `0x180049d40`
- `0x18004aec0`
- `0x18004b0dc`
- `0x180051f30`
- `0x180062260`
- `0x1800625b0`
- `0x180065f64`
- `0x180074bb0`
- `0x18007633c`

## callees

- `0x180018410`
- `0x180018d20`
- `0x18001d0f0`
- `0x1800248f8`
- `0x180031f00`
- `0x1800323f0`
- `0x180060830`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d30d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d30d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d1ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d1ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d350`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d411`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d258`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d411`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001d24b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001d404`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001d24b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18001d404`

## pseudocode

```c
__int64 __fastcall IEConfiguration_GetDWORD(int a1)
{
  unsigned int v1; // ebp
  char v2; // r14
  int v4; // esi
  char v5; // r12
  __int64 *v6; // r15
  signed __int32 v7; // eax
  DWORD v8; // ecx
  int v10; // eax
  signed __int32 v11; // edi
  const void *v12; // rax
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  unsigned __int8 Bool; // r12
  DWORD LastError; // r13d
  __int64 String; // r15
  __int64 v22; // r14
  struct IBrowsingEnvironment *CorrectBrowsingEnvironment; // rsi
  int (__fastcall *v24)(struct IBrowsingEnvironment *, _QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *); // rdi
  unsigned __int8 v25; // bl
  DWORD CurrentProcessId; // eax
  const void *v27; // rax
  int v28; // ebx
  int v29; // ebx
  unsigned int v30; // [rsp+70h] [rbp+8h] BYREF

  v1 = 0;
  v2 = 0;
  if ( a1 == 268435501 )
  {
    if ( byte_180299D11 )
    {
      v4 = 0;
LABEL_6:
      _InterlockedIncrement((volatile signed __int32 *)&g_IAS_SharedMemoryRefcount);
      if ( !g_fIAS_ShouldClearSharedMemory && _g_pvImmutableApplicationStateMappingBaseAddress )
      {
        v6 = (__int64 *)((char *)_g_pvImmutableApplicationStateMappingBaseAddress + 16);
        v5 = 1;
      }
      else
      {
        v5 = 0;
        v6 = qword_180298F20;
        v7 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_IAS_SharedMemoryRefcount, 0xFFFFFFFF);
        if ( g_fIAS_ShouldClearSharedMemory && v7 == 1 )
        {
          v27 = (const void *)_InterlockedCompareExchange64(
                                (volatile signed __int64 *)&_g_pvImmutableApplicationStateMappingBaseAddress,
                                0,
                                (signed __int64)_g_pvImmutableApplicationStateMappingBaseAddress);
          if ( v27 )
          {
            if ( hObject )
            {
              UnmapViewOfFile(v27);
              CloseHandle(hObject);
              hObject = 0;
            }
          }
        }
      }
      if ( a1 == 268435501 )
      {
        v1 = *((_DWORD *)v6 + 292);
        v2 = *((_BYTE *)v6 + 1172);
LABEL_11:
        if ( v5 )
        {
          v11 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_IAS_SharedMemoryRefcount, 0xFFFFFFFF);
          if ( g_fIAS_ShouldClearSharedMemory && v11 == 1 )
          {
            v12 = (const void *)_InterlockedCompareExchange64(
                                  (volatile signed __int64 *)&_g_pvImmutableApplicationStateMappingBaseAddress,
                                  0,
                                  (signed __int64)_g_pvImmutableApplicationStateMappingBaseAddress);
            if ( v12 )
            {
              if ( hObject )
              {
                UnmapViewOfFile(v12);
                CloseHandle(hObject);
                hObject = 0;
              }
            }
          }
        }
LABEL_12:
        v8 = 87;
        if ( v4 < 0 )
          goto LABEL_13;
        goto LABEL_20;
      }
      if ( a1 > 268435502 )
      {
        v16 = a1 - 268435516;
        if ( !v16 )
        {
          v1 = *((_DWORD *)v6 + 25);
          v2 = *((_BYTE *)v6 + 104);
          goto LABEL_11;
        }
        v17 = v16 - 22;
        if ( !v17 )
        {
          v1 = *((_DWORD *)v6 + 852);
          v2 = *((_BYTE *)v6 + 3412);
          goto LABEL_11;
        }
        v18 = v17 - 1;
        if ( !v18 )
        {
          v1 = *((_DWORD *)v6 + 854);
          v2 = *((_BYTE *)v6 + 3420);
          goto LABEL_11;
        }
        if ( v18 == 16777192 )
        {
          v1 = *((_DWORD *)v6 + 848);
          v2 = *((_BYTE *)v6 + 3396);
          goto LABEL_11;
        }
      }
      else
      {
        if ( a1 == 268435502 )
        {
          v1 = *((_DWORD *)v6 + 161);
          v2 = *((_BYTE *)v6 + 648);
          goto LABEL_11;
        }
        v13 = a1 - 268435469;
        if ( !v13 )
        {
          v1 = *((_DWORD *)v6 + 23);
          v2 = *((_BYTE *)v6 + 96);
          goto LABEL_11;
        }
        v14 = v13 - 1;
        if ( !v14 )
        {
          v1 = *((_DWORD *)v6 + 5);
          v2 = *((_BYTE *)v6 + 24);
          goto LABEL_11;
        }
        v28 = v14 - 20;
        if ( !v28 )
        {
          v1 = *((_DWORD *)v6 + 7);
          v2 = *((_BYTE *)v6 + 32);
          goto LABEL_11;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v1 = *((_DWORD *)v6 + 9);
          v2 = *((_BYTE *)v6 + 40);
          goto LABEL_11;
        }
        if ( v29 == 1 )
        {
          v1 = *((_DWORD *)v6 + 21);
          v2 = *((_BYTE *)v6 + 88);
          goto LABEL_11;
        }
      }
      v4 = -2147024809;
      goto LABEL_11;
    }
    v10 = IEConfiguration_SetBrowserAppProfileDefault();
  }
  else
  {
    v10 = IEConfiguration_Initialize(0);
  }
  v4 = v10;
  if ( v10 < 0 )
    goto LABEL_12;
  if ( (a1 & 0x20000000) == 0 )
  {
    if ( (a1 & 0x10000000) != 0 )
      goto LABEL_6;
LABEL_35:
    v8 = 87;
    goto LABEL_13;
  }
  v15 = a1 - 536870929;
  if ( v15 )
  {
    if ( v15 != 1 )
      goto LABEL_35;
    if ( byte_180299D3C )
    {
      v1 = dword_180299D38;
    }
    else
    {
      Bool = IEConfiguration_GetBool(268435519);
      LastError = GetLastError();
      String = IEConfiguration_GetString(268435506);
      v22 = IEConfiguration_GetString(268435507);
      v30 = 0;
      CorrectBrowsingEnvironment = GetCorrectBrowsingEnvironment();
      v24 = *(int (__fastcall **)(struct IBrowsingEnvironment *, _QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *))(*(_QWORD *)CorrectBrowsingEnvironment + 88LL);
      v25 = IEConfiguration_GetBool(268435520);
      CurrentProcessId = GetCurrentProcessId();
      if ( v24(CorrectBrowsingEnvironment, CurrentProcessId, Bool, v25, String, v22, &v30) >= 0 )
      {
        v1 = v30;
        if ( !LastError || !Bool && !String && !v22 )
          IEConfiguration_SetDWORD(536870930, v30);
      }
    }
    v2 = byte_180299D3C;
  }
  else
  {
    v1 = dword_180299D30;
    v2 = byte_180299D34;
  }
LABEL_20:
  v8 = 2;
  if ( v2 )
    v8 = 0;
LABEL_13:
  SetLastError(v8);
  return v1;
}

```

## disassembly

```asm
0x18001d0f0  mov     [rsp+arg_10], rbx
0x18001d0f5  mov     [rsp+arg_18], rbp
0x18001d0fa  push    rsi
0x18001d0fb  push    rdi
0x18001d0fc  push    r12
0x18001d0fe  push    r14
0x18001d100  push    r15
0x18001d102  sub     rsp, 40h
0x18001d106  xor     ebp, ebp
0x18001d108  xor     r14b, r14b
0x18001d10b  mov     ebx, ecx
0x18001d10d  cmp     ecx, 1000002Dh
0x18001d113  jnz     loc_18001D1CE
0x18001d119  cmp     cs:byte_180299D11, bpl
0x18001d120  jz      loc_18001D2F0
0x18001d126  xor     esi, esi
0x18001d128  jmp     short loc_18001D13E
0x18001d12a  bt      ebx, 1Dh
0x18001d12e  jb      loc_18001D29F
0x18001d134  bt      ebx, 1Ch
0x18001d138  jnb     loc_18001D2B4
0x18001d13e  lock inc cs:?g_IAS_SharedMemoryRefcount@@3KA; ulong g_IAS_SharedMemoryRefcount
0x18001d145  cmp     cs:?g_fIAS_ShouldClearSharedMemory@@3_NA, bpl; bool g_fIAS_ShouldClearSharedMemory
0x18001d14c  mov     edi, 0FFFFFFFFh
0x18001d151  jnz     short loc_18001D163
0x18001d153  mov     r15, cs:?_g_pvImmutableApplicationStateMappingBaseAddress@@3PEAXEA; void * _g_pvImmutableApplicationStateMappingBaseAddress
0x18001d15a  test    r15, r15
0x18001d15d  jnz     loc_18001D3C4
0x18001d163  xor     r12b, r12b
0x18001d166  lea     r15, qword_180298F20
0x18001d16d  mov     eax, edi
0x18001d16f  lock xadd cs:?g_IAS_SharedMemoryRefcount@@3KA, eax; ulong g_IAS_SharedMemoryRefcount
0x18001d177  cmp     cs:?g_fIAS_ShouldClearSharedMemory@@3_NA, bpl; bool g_fIAS_ShouldClearSharedMemory
0x18001d17e  jnz     loc_18001D3D0
0x18001d184  cmp     ebx, 1000002Dh
0x18001d18a  jnz     loc_18001D26E
0x18001d190  mov     ebp, [r15+490h]
0x18001d197  movzx   r14d, byte ptr [r15+494h]
0x18001d19f  test    r12b, r12b
0x18001d1a2  jnz     short loc_18001D20A
0x18001d1a4  mov     ecx, 57h ; 'W'; dwErrCode
0x18001d1a9  test    esi, esi
0x18001d1ab  jns     short loc_18001D1FB
0x18001d1ad  call    cs:__imp_SetLastError
0x18001d1b3  lea     r11, [rsp+68h+var_28]
0x18001d1b8  mov     eax, ebp
0x18001d1ba  mov     rbx, [r11+40h]
0x18001d1be  mov     rbp, [r11+48h]
0x18001d1c2  mov     rsp, r11
0x18001d1c5  pop     r15
0x18001d1c7  pop     r14
0x18001d1c9  pop     r12
0x18001d1cb  pop     rdi
0x18001d1cc  pop     rsi
0x18001d1cd  retn
0x18001d1ce  xor     ecx, ecx; unsigned int
0x18001d1d0  call    ?IEConfiguration_Initialize@@YAJK@Z; IEConfiguration_Initialize(ulong)
0x18001d1d5  mov     esi, eax
0x18001d1d7  test    eax, eax
0x18001d1d9  js      short loc_18001D1A4
0x18001d1db  jmp     loc_18001D12A
0x18001d1e0  cmp     cs:byte_180299D3C, bpl
0x18001d1e7  jz      loc_18001D2FA
0x18001d1ed  mov     ebp, cs:dword_180299D38
0x18001d1f3  movzx   r14d, cs:byte_180299D3C
0x18001d1fb  xor     edx, edx
0x18001d1fd  mov     ecx, 2
0x18001d202  test    r14b, r14b
0x18001d205  cmovnz  ecx, edx
0x18001d208  jmp     short loc_18001D1AD
0x18001d20a  lock xadd cs:?g_IAS_SharedMemoryRefcount@@3KA, edi; ulong g_IAS_SharedMemoryRefcount
0x18001d212  cmp     cs:?g_fIAS_ShouldClearSharedMemory@@3_NA, 0; bool g_fIAS_ShouldClearSharedMemory
0x18001d219  jz      short loc_18001D1A4
0x18001d21b  cmp     edi, 1
0x18001d21e  jnz     short loc_18001D1A4
0x18001d220  mov     rax, cs:?_g_pvImmutableApplicationStateMappingBaseAddress@@3PEAXEA; void * _g_pvImmutableApplicationStateMappingBaseAddress
0x18001d227  xor     ecx, ecx
0x18001d229  lock cmpxchg cs:?_g_pvImmutableApplicationStateMappingBaseAddress@@3PEAXEA, rcx; void * _g_pvImmutableApplicationStateMappingBaseAddress
0x18001d232  test    rax, rax
0x18001d235  jz      loc_18001D1A4
0x18001d23b  cmp     cs:hObject, rcx
0x18001d242  jz      loc_18001D1A4
0x18001d248  mov     rcx, rax; lpBaseAddress
0x18001d24b  call    cs:__imp_UnmapViewOfFile
0x18001d251  mov     rcx, cs:hObject; hObject
0x18001d258  call    cs:__imp_CloseHandle
0x18001d25e  mov     cs:hObject, 0
0x18001d269  jmp     loc_18001D1A4
0x18001d26e  cmp     ebx, 1000002Eh
0x18001d274  jg      short loc_18001D2BE
0x18001d276  jz      loc_18001D46A
0x18001d27c  sub     ebx, 1000000Dh
0x18001d282  jz      loc_18001D45C
0x18001d288  sub     ebx, 1
0x18001d28b  jnz     loc_18001D423
0x18001d291  mov     ebp, [r15+14h]
0x18001d295  movzx   r14d, byte ptr [r15+18h]
0x18001d29a  jmp     loc_18001D19F
0x18001d29f  sub     ebx, 20000011h
0x18001d2a5  jz      loc_18001D3B1
0x18001d2ab  cmp     ebx, 1
0x18001d2ae  jz      loc_18001D1E0
0x18001d2b4  mov     ecx, 57h ; 'W'
0x18001d2b9  jmp     loc_18001D1AD
0x18001d2be  sub     ebx, 1000003Ch
0x18001d2c4  jz      loc_18001D4B8
0x18001d2ca  sub     ebx, 16h
0x18001d2cd  jz      loc_18001D4A4
0x18001d2d3  sub     ebx, 1
0x18001d2d6  jnz     loc_18001D47E
0x18001d2dc  mov     ebp, [r15+0D58h]
0x18001d2e3  movzx   r14d, byte ptr [r15+0D5Ch]
0x18001d2eb  jmp     loc_18001D19F
0x18001d2f0  call    ?IEConfiguration_SetBrowserAppProfileDefault@@YAJXZ; IEConfiguration_SetBrowserAppProfileDefault(void)
0x18001d2f5  jmp     loc_18001D1D5
0x18001d2fa  mov     ecx, 1000003Fh
0x18001d2ff  mov     [rsp+68h+arg_8], r13
0x18001d304  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001d309  movzx   r12d, al
0x18001d30d  call    cs:__imp_GetLastError
0x18001d313  mov     ecx, 10000032h
0x18001d318  mov     r13d, eax
0x18001d31b  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18001d320  mov     ecx, 10000033h
0x18001d325  mov     r15, rax
0x18001d328  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x18001d32d  mov     r14, rax
0x18001d330  mov     [rsp+68h+arg_0], ebp
0x18001d334  call    ?GetCorrectBrowsingEnvironment@@YAPEAUIBrowsingEnvironment@@XZ; GetCorrectBrowsingEnvironment(void)
0x18001d339  mov     rsi, rax
0x18001d33c  mov     ecx, 10000040h
0x18001d341  mov     rax, [rax]
0x18001d344  mov     rdi, [rax+58h]
0x18001d348  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18001d34d  movzx   ebx, al
0x18001d350  call    cs:__imp_GetCurrentProcessId
0x18001d356  lea     rcx, [rsp+68h+arg_0]
0x18001d35b  movzx   r9d, bl
0x18001d35f  mov     [rsp+68h+var_38], rcx
0x18001d364  mov     edx, eax
0x18001d366  mov     [rsp+68h+var_40], r14
0x18001d36b  mov     rcx, rsi
0x18001d36e  movzx   r8d, r12b
0x18001d372  mov     [rsp+68h+var_48], r15
0x18001d377  mov     rax, rdi
0x18001d37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d37f  test    eax, eax
0x18001d381  js      short loc_18001D3A7
0x18001d383  mov     ebp, [rsp+68h+arg_0]
0x18001d387  test    r13d, r13d
0x18001d38a  jz      short loc_18001D39B
0x18001d38c  test    r12b, r12b
0x18001d38f  jnz     short loc_18001D3A7
0x18001d391  test    r15, r15
0x18001d394  jnz     short loc_18001D3A7
0x18001d396  test    r14, r14
0x18001d399  jnz     short loc_18001D3A7
0x18001d39b  mov     edx, ebp
0x18001d39d  mov     ecx, 20000012h
0x18001d3a2  call    ?IEConfiguration_SetDWORD@@YAJW4IEConfigurationID@@K@Z; IEConfiguration_SetDWORD(IEConfigurationID,ulong)
0x18001d3a7  mov     r13, [rsp+68h+arg_8]
0x18001d3ac  jmp     loc_18001D1F3
0x18001d3b1  mov     ebp, cs:dword_180299D30
0x18001d3b7  movzx   r14d, cs:byte_180299D34
0x18001d3bf  jmp     loc_18001D1FB
0x18001d3c4  add     r15, 10h
0x18001d3c8  mov     r12b, 1
0x18001d3cb  jmp     loc_18001D184
0x18001d3d0  cmp     eax, 1
0x18001d3d3  jnz     loc_18001D184
0x18001d3d9  mov     rax, cs:?_g_pvImmutableApplicationStateMappingBaseAddress@@3PEAXEA; void * _g_pvImmutableApplicationStateMappingBaseAddress
0x18001d3e0  xor     ecx, ecx
0x18001d3e2  lock cmpxchg cs:?_g_pvImmutableApplicationStateMappingBaseAddress@@3PEAXEA, rcx; void * _g_pvImmutableApplicationStateMappingBaseAddress
0x18001d3eb  test    rax, rax
0x18001d3ee  jz      loc_18001D184
0x18001d3f4  cmp     cs:hObject, rcx
0x18001d3fb  jz      loc_18001D184
0x18001d401  mov     rcx, rax; lpBaseAddress
0x18001d404  call    cs:__imp_UnmapViewOfFile
0x18001d40a  mov     rcx, cs:hObject; hObject
0x18001d411  call    cs:__imp_CloseHandle
0x18001d417  mov     cs:hObject, rbp
0x18001d41e  jmp     loc_18001D184
0x18001d423  sub     ebx, 14h
0x18001d426  jz      short loc_18001D44E
0x18001d428  sub     ebx, 1
0x18001d42b  jz      short loc_18001D440
0x18001d42d  cmp     ebx, 1
0x18001d430  jnz     short loc_18001D49A
0x18001d432  mov     ebp, [r15+54h]
0x18001d436  movzx   r14d, byte ptr [r15+58h]
0x18001d43b  jmp     loc_18001D19F
0x18001d440  mov     ebp, [r15+24h]
0x18001d444  movzx   r14d, byte ptr [r15+28h]
0x18001d449  jmp     loc_18001D19F
0x18001d44e  mov     ebp, [r15+1Ch]
0x18001d452  movzx   r14d, byte ptr [r15+20h]
0x18001d457  jmp     loc_18001D19F
0x18001d45c  mov     ebp, [r15+5Ch]
0x18001d460  movzx   r14d, byte ptr [r15+60h]
0x18001d465  jmp     loc_18001D19F
0x18001d46a  mov     ebp, [r15+284h]
0x18001d471  movzx   r14d, byte ptr [r15+288h]
0x18001d479  jmp     loc_18001D19F
0x18001d47e  cmp     ebx, 0FFFFE8h
0x18001d484  jnz     short loc_18001D49A
0x18001d486  mov     ebp, [r15+0D40h]
0x18001d48d  movzx   r14d, byte ptr [r15+0D44h]
0x18001d495  jmp     loc_18001D19F
0x18001d49a  mov     esi, 80070057h
0x18001d49f  jmp     loc_18001D19F
0x18001d4a4  mov     ebp, [r15+0D50h]
0x18001d4ab  movzx   r14d, byte ptr [r15+0D54h]
0x18001d4b3  jmp     loc_18001D19F
0x18001d4b8  mov     ebp, [r15+64h]
0x18001d4bc  movzx   r14d, byte ptr [r15+68h]
0x18001d4c1  jmp     loc_18001D19F
```
