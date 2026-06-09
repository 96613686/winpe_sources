# Dhcpv6CreateThreadAndRenew

- ea: `0x18000c884`
- end: `0x18000cab3`
- name: `Dhcpv6CreateThreadAndRenew`
- size: `559`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001cb0c`

## callees

- `0x180001ca4`
- `0x180001d04`
- `0x180004b30`
- `0x18000bb2c`
- `0x18000c884`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c915`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c915`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c8f9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000c8f9`

## pseudocode

```c
__int64 __fastcall Dhcpv6CreateThreadAndRenew(LPVOID lpParameter)
{
  DWORD v2; // edi
  int v3; // r14d
  char *v4; // rcx
  char v6; // al
  __int64 v7; // rcx
  DWORD LastError; // eax
  DWORD ThreadId; // [rsp+60h] [rbp+8h] BYREF

  ThreadId = 0;
  if ( !*((_QWORD *)lpParameter + 72) )
    return 0;
  if ( **(_DWORD **)&pDhcpv6GlobalIsShuttingDown )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 85, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *((_QWORD *)lpParameter + 7));
    return 0;
  }
  v2 = 0;
  _InterlockedAdd((volatile signed __int32 *)lpParameter + 4, 1u);
  v3 = _InterlockedIncrement((volatile signed __int32 *)lpParameter + 149);
  if ( v3 == 1 )
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 86, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *((_QWORD *)lpParameter + 7));
    v4 = (char *)CreateThread(0, 0, Dhcpv6RenewThread, lpParameter, 0, &ThreadId);
    if ( (unsigned __int64)(v4 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( (xmmword_1800423E0 & 2) != 0 )
        WPP_SF_D(1025, 87, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, LastError);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpParameter + 4, 0xFFFFFFFF) == 1 )
        Dhcpv6DestroyContextEx(lpParameter);
      if ( v2 )
      {
        if ( (xmmword_1800423E0 & 2) != 0 )
          WPP_SF_D(1025, 90, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, v2);
        if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
          McTemplateU0q_EtwEventWriteTransfer(v7, ErrorCreatingRenewalThread, v2);
        TraceLogErrorv6(0, v2, 23);
      }
    }
    else
    {
      CloseHandle(v4);
    }
  }
  else
  {
    v6 = xmmword_1800423E0;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      WPP_SF_(1028, 88, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids);
      v6 = xmmword_1800423E0;
    }
    if ( v3 < 0 )
    {
      if ( (v6 & 2) != 0 )
        WPP_SF_S(1025, 89, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids, *((_QWORD *)lpParameter + 7));
      if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
        McTemplateU0z_EtwEventWriteTransfer(lpParameter, ErrorCreatingRenewalThreadQueue, *((_QWORD *)lpParameter + 7));
      TraceLogErrorv6(lpParameter, 0, 23);
      _InterlockedExchange((volatile __int32 *)lpParameter + 149, 1);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpParameter + 4, 0xFFFFFFFF) == 1 )
      Dhcpv6DestroyContextEx(lpParameter);
  }
  return v2;
}

```

## disassembly

```asm
0x18000c884  push    rbx
0x18000c886  push    rsi
0x18000c887  push    rdi
0x18000c888  push    r14
0x18000c88a  sub     rsp, 38h
0x18000c88e  mov     [rsp+58h+ThreadId], 0
0x18000c896  mov     rbx, rcx
0x18000c899  cmp     qword ptr [rcx+240h], 0
0x18000c8a1  jz      loc_18000C984
0x18000c8a7  mov     rax, cs:pDhcpv6GlobalIsShuttingDown
0x18000c8ae  cmp     dword ptr [rax], 0
0x18000c8b1  jnz     loc_18000C977
0x18000c8b7  xor     edi, edi
0x18000c8b9  lea     esi, [rdi+1]
0x18000c8bc  lock add [rcx+10h], esi
0x18000c8c0  mov     r14d, esi
0x18000c8c3  lock xadd [rcx+254h], r14d
0x18000c8cc  add     r14d, esi
0x18000c8cf  cmp     r14d, esi
0x18000c8d2  jnz     short loc_18000C92E
0x18000c8d4  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000c8db  jnz     short loc_18000C958
0x18000c8dd  lea     rax, [rsp+58h+ThreadId]
0x18000c8e2  mov     r9, rbx; lpParameter
0x18000c8e5  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x18000c8ea  lea     r8, Dhcpv6RenewThread; lpStartAddress
0x18000c8f1  xor     edx, edx; dwStackSize
0x18000c8f3  mov     [rsp+58h+dwCreationFlags], edi; dwCreationFlags
0x18000c8f7  xor     ecx, ecx; lpThreadAttributes
0x18000c8f9  call    cs:__imp_CreateThread
0x18000c900  nop     dword ptr [rax+rax+00h]
0x18000c905  mov     rcx, rax; hObject
0x18000c908  dec     rax
0x18000c90b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c90f  ja      loc_18000CA31
0x18000c915  call    cs:__imp_CloseHandle
0x18000c91c  nop     dword ptr [rax+rax+00h]
0x18000c921  mov     eax, edi
0x18000c923  add     rsp, 38h
0x18000c927  pop     r14
0x18000c929  pop     rdi
0x18000c92a  pop     rsi
0x18000c92b  pop     rbx
0x18000c92c  retn
0x18000c92e  mov     al, byte ptr cs:xmmword_1800423E0
0x18000c934  test    al, 10h
0x18000c936  jnz     short loc_18000C988
0x18000c938  test    r14d, r14d
0x18000c93b  js      loc_18000CA63
0x18000c941  or      ecx, 0FFFFFFFFh
0x18000c944  lock xadd [rbx+10h], ecx
0x18000c949  cmp     ecx, 1
0x18000c94c  jnz     short loc_18000C921
0x18000c94e  mov     rcx, rbx
0x18000c951  call    Dhcpv6DestroyContextEx
0x18000c956  jmp     short loc_18000C921
0x18000c958  mov     r9, [rbx+38h]
0x18000c95c  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000c963  mov     edx, 56h ; 'V'
0x18000c968  mov     ecx, 404h
0x18000c96d  call    WPP_SF_S
0x18000c972  jmp     loc_18000C8DD
0x18000c977  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000c97e  jnz     loc_18000CA12
0x18000c984  xor     eax, eax
0x18000c986  jmp     short loc_18000C923
0x18000c988  mov     edx, 58h ; 'X'
0x18000c98d  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000c994  mov     ecx, 404h
0x18000c999  call    WPP_SF_
0x18000c99e  mov     al, byte ptr cs:xmmword_1800423E0
0x18000c9a4  jmp     short loc_18000C938
0x18000c9a6  test    edi, edi
0x18000c9a8  jz      loc_18000C921
0x18000c9ae  test    byte ptr cs:xmmword_1800423E0, 2
0x18000c9b5  jz      short loc_18000C9D0
0x18000c9b7  mov     edx, 5Ah ; 'Z'
0x18000c9bc  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000c9c3  mov     ecx, 401h
0x18000c9c8  mov     r9d, edi
0x18000c9cb  call    WPP_SF_D
0x18000c9d0  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, sil
0x18000c9d7  jz      short loc_18000C9E8
0x18000c9d9  mov     r8d, edi
0x18000c9dc  lea     rdx, ErrorCreatingRenewalThread
0x18000c9e3  call    McTemplateU0q_EtwEventWriteTransfer
0x18000c9e8  mov     r8d, 17h
0x18000c9ee  mov     edx, edi
0x18000c9f0  xor     ecx, ecx
0x18000c9f2  call    TraceLogErrorv6
0x18000c9f7  jmp     loc_18000C921
0x18000c9fc  or      eax, 0FFFFFFFFh
0x18000c9ff  lock xadd [rbx+10h], eax
0x18000ca04  cmp     eax, esi
0x18000ca06  jnz     short loc_18000C9A6
0x18000ca08  mov     rcx, rbx
0x18000ca0b  call    Dhcpv6DestroyContextEx
0x18000ca10  jmp     short loc_18000C9A6
0x18000ca12  mov     r9, [rbx+38h]
0x18000ca16  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000ca1d  mov     edx, 55h ; 'U'
0x18000ca22  mov     ecx, 404h
0x18000ca27  call    WPP_SF_S
0x18000ca2c  jmp     loc_18000C984
0x18000ca31  call    cs:__imp_GetLastError
0x18000ca38  nop     dword ptr [rax+rax+00h]
0x18000ca3d  mov     edi, eax
0x18000ca3f  test    byte ptr cs:xmmword_1800423E0, 2
0x18000ca46  jz      short loc_18000C9FC
0x18000ca48  mov     edx, 57h ; 'W'
0x18000ca4d  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000ca54  mov     ecx, 401h
0x18000ca59  mov     r9d, eax
0x18000ca5c  call    WPP_SF_D
0x18000ca61  jmp     short loc_18000C9FC
0x18000ca63  test    al, 2
0x18000ca65  jz      short loc_18000CA81
0x18000ca67  mov     r9, [rbx+38h]
0x18000ca6b  lea     r8, WPP_adff602ec73e393dc921a742cb89b1f2_Traceguids
0x18000ca72  mov     edx, 59h ; 'Y'
0x18000ca77  mov     ecx, 401h
0x18000ca7c  call    WPP_SF_S
0x18000ca81  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, sil
0x18000ca88  jz      short loc_18000CA9A
0x18000ca8a  mov     r8, [rbx+38h]
0x18000ca8e  lea     rdx, ErrorCreatingRenewalThreadQueue
0x18000ca95  call    McTemplateU0z_EtwEventWriteTransfer
0x18000ca9a  xor     edx, edx
0x18000ca9c  mov     rcx, rbx
0x18000ca9f  lea     r8d, [rdx+17h]
0x18000caa3  call    TraceLogErrorv6
0x18000caa8  xchg    esi, [rbx+254h]
0x18000caae  jmp     loc_18000C941
```
