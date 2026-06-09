# MakeDhcpV6Call(_DHCPV6_CALL_PARAMS *)

- ea: `0x18000f840`
- end: `0x18000fdcc`
- name: `?MakeDhcpV6Call@@YAKPEAU_DHCPV6_CALL_PARAMS@@@Z`
- size: `1420`
- prototype: `unsigned int __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e0b0`
- `0x18000f770`
- `0x18006d690`
- `0x18006d764`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18000f840`
- `0x18000fde0`
- `0x18006d840`

## import_xrefs

- `dhcpcsvc6!Dhcpv6CancelOperation` at `0x18000fb3e`
- `dhcpcsvc6!Dhcpv6CancelOperation` at `0x18000fb3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f8ad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f962`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc3f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f975`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f975`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fa78`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fa78`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000f9e5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000f9e5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000f8d6`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000f8d6`

## pseudocode

```c
__int64 __fastcall MakeDhcpV6Call(PVOID Context)
{
  int v2; // ebp
  int v3; // eax
  _QWORD *v4; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // r15d
  int v7; // eax
  DWORD v8; // esi
  __int64 v9; // rdx
  PVOID *v10; // rcx
  BOOL v12; // edi
  DWORD v13; // eax
  PVOID *v14; // rcx
  int v15; // edi
  __int64 v16; // rdx
  HANDLE Handles[2]; // [rsp+30h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids);
  }
  v2 = 1;
  *(_OWORD *)Handles = 0;
  *((_DWORD *)Context + 4) = 1;
  _InterlockedExchange((volatile __int32 *)Context + 1, 0);
  v3 = *((_DWORD *)Context + 5);
  switch ( v3 )
  {
    case 0:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v9 = 20;
LABEL_11:
        WPP_SF_s(v4[2], v9, &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids, "MakeDhcpV6Call");
        goto LABEL_4;
      }
      goto LABEL_4;
    case 1:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v9 = 21;
        goto LABEL_11;
      }
      goto LABEL_4;
    case 2:
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v9 = 22;
        goto LABEL_11;
      }
LABEL_4:
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)Context + 1) = EventW;
      if ( !EventW )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
            "MakeDhcpV6Call");
        }
        LastError = GetLastError();
        goto LABEL_16;
      }
      if ( !QueueUserWorkItem(DhcpV6CallWorkItem, Context, 0x10u) )
      {
        v2 = 0;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
            "MakeDhcpV6Call");
        }
        LastError = GetLastError();
        goto LABEL_14;
      }
      LastError = 0;
      Handles[0] = *((HANDLE *)Context + 1);
      Handles[1] = *((HANDLE *)Context + 3);
      v7 = *((_DWORD *)Context + 5);
      if ( v7 == 2 )
        v8 = *((_DWORD *)Context + 8);
      else
        v8 = -1;
      v12 = v7 != 2;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
          "MakeDhcpV6Call");
      }
      v13 = WaitForMultipleObjects(v12 + 1, Handles, 0, v8);
      switch ( v13 )
      {
        case 0x102u:
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_25;
          }
          v16 = 27;
          break;
        case 0u:
          v15 = 0;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              28,
              &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
              "MakeDhcpV6Call");
          }
          goto LABEL_30;
        case 1u:
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          {
            goto LABEL_25;
          }
          v16 = 29;
          break;
        default:
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || *((char *)WPP_GLOBAL_Control + 28) >= 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_25;
          }
          WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), 30);
          goto LABEL_85;
      }
      WPP_SF_s(v14[2], v16, &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids, "MakeDhcpV6Call");
LABEL_85:
      v14 = (PVOID *)WPP_GLOBAL_Control;
LABEL_25:
      v15 = 1;
      if ( v14 != &WPP_GLOBAL_Control && *((char *)v14 + 28) < 0 && *((_BYTE *)v14 + 25) >= 4u )
        WPP_SF_s(v14[2], 31, &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids, "MakeDhcpV6Call");
      *((_DWORD *)Context + 4) = 0;
LABEL_30:
      while ( !_InterlockedExchangeAdd((volatile signed __int32 *)Context + 1, 0) )
      {
        if ( v15 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((char *)WPP_GLOBAL_Control + 28) < 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
              "MakeDhcpV6Call");
          }
          Dhcpv6CancelOperation();
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            33,
            &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids,
            "MakeDhcpV6Call");
        }
        Sleep(0x64u);
      }
LABEL_14:
      CloseHandle(*((HANDLE *)Context + 1));
      if ( v2 )
        LastError = *(_DWORD *)Context;
LABEL_16:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_17;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((char *)WPP_GLOBAL_Control + 28) < 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sL(*((_QWORD *)WPP_GLOBAL_Control + 2), 23);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  LastError = 87;
LABEL_17:
  if ( v10 != &WPP_GLOBAL_Control && *((char *)v10 + 28) < 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 34, &WPP_02f9d66c47ff394099e27486dbd70566_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x18000f840  sub     rsp, 58h
0x18000f844  mov     [rsp+58h+arg_0], rbx
0x18000f849  mov     rbx, rcx
0x18000f84c  mov     [rsp+58h+arg_8], rbp
0x18000f851  mov     [rsp+58h+var_8], r12
0x18000f856  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f85d  lea     r12, WPP_GLOBAL_Control
0x18000f864  cmp     rcx, r12
0x18000f867  jnz     loc_18000FB4F
0x18000f86d  xor     eax, eax
0x18000f86f  mov     [rsp+58h+var_18], r15
0x18000f874  xorps   xmm0, xmm0
0x18000f877  mov     ebp, 1
0x18000f87c  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x18000f881  mov     [rbx+10h], ebp
0x18000f884  xchg    eax, [rbx+4]
0x18000f887  mov     eax, [rbx+14h]
0x18000f88a  test    eax, eax
0x18000f88c  jnz     loc_18000FAB0
0x18000f892  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f899  cmp     rcx, r12
0x18000f89c  jnz     short loc_18000F91B
0x18000f89e  xor     r9d, r9d; lpName
0x18000f8a1  mov     [rsp+58h+var_10], r14
0x18000f8a6  xor     r8d, r8d; bInitialState
0x18000f8a9  xor     edx, edx; bManualReset
0x18000f8ab  xor     ecx, ecx; lpEventAttributes
0x18000f8ad  call    cs:__imp_CreateEventW
0x18000f8b4  nop     dword ptr [rax+rax+00h]
0x18000f8b9  mov     [rbx+8], rax
0x18000f8bd  test    rax, rax
0x18000f8c0  jz      loc_18000FC0B
0x18000f8c6  mov     r8d, 10h; Flags
0x18000f8cc  lea     rcx, ?DhcpV6CallWorkItem@@YAKPEAX@Z; Function
0x18000f8d3  mov     rdx, rbx; Context
0x18000f8d6  call    cs:__imp_QueueUserWorkItem
0x18000f8dd  nop     dword ptr [rax+rax+00h]
0x18000f8e2  test    eax, eax
0x18000f8e4  jz      short loc_18000F950
0x18000f8e6  mov     rax, [rbx+8]
0x18000f8ea  xor     r15d, r15d
0x18000f8ed  mov     [rsp+58h+Handles], rax
0x18000f8f2  mov     rax, [rbx+18h]
0x18000f8f6  mov     [rsp+58h+Handles+8], rax
0x18000f8fb  mov     eax, [rbx+14h]
0x18000f8fe  mov     [rsp+58h+arg_10], rsi
0x18000f903  mov     [rsp+58h+arg_18], rdi
0x18000f908  cmp     eax, 2
0x18000f90b  jz      loc_18000F9BB
0x18000f911  mov     esi, 0FFFFFFFFh
0x18000f916  jmp     loc_18000F9BE
0x18000f91b  test    byte ptr [rcx+1Ch], 80h
0x18000f91f  jz      loc_18000F89E
0x18000f925  cmp     byte ptr [rcx+19h], 4
0x18000f929  jb      loc_18000F89E
0x18000f92f  mov     edx, 14h
0x18000f934  mov     rcx, [rcx+10h]
0x18000f938  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f93f  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f946  call    WPP_SF_s
0x18000f94b  jmp     loc_18000F89E
0x18000f950  xor     ebp, ebp
0x18000f952  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f959  cmp     rcx, r12
0x18000f95c  jnz     loc_18000FC53
0x18000f962  call    cs:__imp_GetLastError
0x18000f969  nop     dword ptr [rax+rax+00h]
0x18000f96e  mov     r15d, eax
0x18000f971  mov     rcx, [rbx+8]; hObject
0x18000f975  call    cs:__imp_CloseHandle
0x18000f97c  nop     dword ptr [rax+rax+00h]
0x18000f981  test    ebp, ebp
0x18000f983  jnz     loc_18000FD93
0x18000f989  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f990  mov     r14, [rsp+58h+var_10]
0x18000f995  mov     rbp, [rsp+58h+arg_8]
0x18000f99a  cmp     rcx, r12
0x18000f99d  mov     r12, [rsp+58h+var_8]
0x18000f9a2  mov     rbx, [rsp+58h+arg_0]
0x18000f9a7  jnz     loc_18000FD9B
0x18000f9ad  mov     eax, r15d
0x18000f9b0  mov     r15, [rsp+58h+var_18]
0x18000f9b5  add     rsp, 58h
0x18000f9b9  retn
0x18000f9bb  mov     esi, [rbx+20h]
0x18000f9be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9c5  xor     edi, edi
0x18000f9c7  cmp     eax, 2
0x18000f9ca  setnz   dil
0x18000f9ce  cmp     rcx, r12
0x18000f9d1  jnz     loc_18000FC88
0x18000f9d7  mov     r9d, esi; dwMilliseconds
0x18000f9da  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18000f9df  xor     r8d, r8d; bWaitAll
0x18000f9e2  lea     ecx, [rdi+1]; nCount
0x18000f9e5  call    cs:__imp_WaitForMultipleObjects
0x18000f9ec  nop     dword ptr [rax+rax+00h]
0x18000f9f1  mov     rsi, [rsp+58h+arg_10]
0x18000f9f6  cmp     eax, 102h
0x18000f9fb  jz      loc_18000FCBD
0x18000fa01  test    eax, eax
0x18000fa03  jz      loc_18000FAE7
0x18000fa09  cmp     eax, ebp
0x18000fa0b  jnz     loc_18000FD1C
0x18000fa11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa18  cmp     rcx, r12
0x18000fa1b  jnz     loc_18000FD06
0x18000fa21  mov     edi, ebp
0x18000fa23  cmp     rcx, r12
0x18000fa26  jz      short loc_18000FA50
0x18000fa28  test    byte ptr [rcx+1Ch], 80h
0x18000fa2c  jz      short loc_18000FA50
0x18000fa2e  cmp     byte ptr [rcx+19h], 4
0x18000fa32  jb      short loc_18000FA50
0x18000fa34  mov     rcx, [rcx+10h]
0x18000fa38  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fa3f  mov     edx, 1Fh
0x18000fa44  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fa4b  call    WPP_SF_s
0x18000fa50  mov     [rbx+10h], r15d
0x18000fa54  xor     eax, eax
0x18000fa56  lock xadd [rbx+4], eax
0x18000fa5b  test    eax, eax
0x18000fa5d  jnz     short loc_18000FADD
0x18000fa5f  test    edi, edi
0x18000fa61  jnz     loc_18000FB2E
0x18000fa67  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa6e  cmp     rcx, r12
0x18000fa71  jnz     short loc_18000FA86
0x18000fa73  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000fa78  call    cs:__imp_Sleep
0x18000fa7f  nop     dword ptr [rax+rax+00h]
0x18000fa84  jmp     short loc_18000FA54
0x18000fa86  test    byte ptr [rcx+1Ch], 80h
0x18000fa8a  jz      short loc_18000FA73
0x18000fa8c  cmp     byte ptr [rcx+19h], 4
0x18000fa90  jb      short loc_18000FA73
0x18000fa92  mov     rcx, [rcx+10h]
0x18000fa96  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fa9d  mov     edx, 21h ; '!'
0x18000faa2  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000faa9  call    WPP_SF_s
0x18000faae  jmp     short loc_18000FA73
0x18000fab0  mov     ecx, eax
0x18000fab2  sub     ecx, ebp
0x18000fab4  jz      loc_18000FBDD
0x18000faba  cmp     ecx, ebp
0x18000fabc  jz      loc_18000FBAF
0x18000fac2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fac9  cmp     rcx, r12
0x18000facc  jnz     loc_18000FB7D
0x18000fad2  mov     r15d, 57h ; 'W'
0x18000fad8  jmp     loc_18000F995
0x18000fadd  mov     rdi, [rsp+58h+arg_18]
0x18000fae2  jmp     loc_18000F971
0x18000fae7  xor     edi, edi
0x18000fae9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000faf0  cmp     rcx, r12
0x18000faf3  jz      loc_18000FA54
0x18000faf9  test    byte ptr [rcx+1Ch], 80h
0x18000fafd  jz      loc_18000FA54
0x18000fb03  cmp     byte ptr [rcx+19h], 4
0x18000fb07  jb      loc_18000FA54
0x18000fb0d  mov     rcx, [rcx+10h]
0x18000fb11  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fb18  mov     edx, 1Ch
0x18000fb1d  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fb24  call    WPP_SF_s
0x18000fb29  jmp     loc_18000FA54
0x18000fb2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb35  cmp     rcx, r12
0x18000fb38  jnz     loc_18000FD5E
0x18000fb3e  call    cs:__imp_Dhcpv6CancelOperation
0x18000fb45  nop     dword ptr [rax+rax+00h]
0x18000fb4a  jmp     loc_18000FA67
0x18000fb4f  test    byte ptr [rcx+1Ch], 80h
0x18000fb53  jz      loc_18000F86D
0x18000fb59  cmp     byte ptr [rcx+19h], 6
0x18000fb5d  jb      loc_18000F86D
0x18000fb63  mov     rcx, [rcx+10h]
0x18000fb67  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fb6e  mov     edx, 13h
0x18000fb73  call    WPP_SF_
0x18000fb78  jmp     loc_18000F86D
0x18000fb7d  test    byte ptr [rcx+1Ch], 80h
0x18000fb81  jz      loc_18000FAD2
0x18000fb87  cmp     byte ptr [rcx+19h], 4
0x18000fb8b  jb      loc_18000FAD2
0x18000fb91  mov     rcx, [rcx+10h]
0x18000fb95  mov     edx, 17h
0x18000fb9a  mov     [rsp+58h+var_38], eax
0x18000fb9e  call    WPP_SF_sL
0x18000fba3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbaa  jmp     loc_18000FAD2
0x18000fbaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbb6  cmp     rcx, r12
0x18000fbb9  jz      loc_18000F89E
0x18000fbbf  test    byte ptr [rcx+1Ch], 80h
0x18000fbc3  jz      loc_18000F89E
0x18000fbc9  cmp     byte ptr [rcx+19h], 4
0x18000fbcd  jb      loc_18000F89E
0x18000fbd3  mov     edx, 16h
0x18000fbd8  jmp     loc_18000F934
0x18000fbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fbe4  cmp     rcx, r12
0x18000fbe7  jz      loc_18000F89E
0x18000fbed  test    byte ptr [rcx+1Ch], 80h
0x18000fbf1  jz      loc_18000F89E
0x18000fbf7  cmp     byte ptr [rcx+19h], 4
0x18000fbfb  jb      loc_18000F89E
0x18000fc01  mov     edx, 15h
0x18000fc06  jmp     loc_18000F934
0x18000fc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc12  cmp     rcx, r12
0x18000fc15  jz      short loc_18000FC3F
0x18000fc17  test    byte ptr [rcx+1Ch], 80h
0x18000fc1b  jz      short loc_18000FC3F
0x18000fc1d  cmp     byte ptr [rcx+19h], 4
0x18000fc21  jb      short loc_18000FC3F
0x18000fc23  mov     rcx, [rcx+10h]
0x18000fc27  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fc2e  mov     edx, 18h
0x18000fc33  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fc3a  call    WPP_SF_s
0x18000fc3f  call    cs:__imp_GetLastError
0x18000fc46  nop     dword ptr [rax+rax+00h]
0x18000fc4b  mov     r15d, eax
0x18000fc4e  jmp     loc_18000F989
0x18000fc53  test    byte ptr [rcx+1Ch], 80h
0x18000fc57  jz      loc_18000F962
0x18000fc5d  cmp     byte ptr [rcx+19h], 4
0x18000fc61  jb      loc_18000F962
0x18000fc67  mov     rcx, [rcx+10h]
0x18000fc6b  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fc72  mov     edx, 19h
0x18000fc77  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fc7e  call    WPP_SF_s
0x18000fc83  jmp     loc_18000F962
0x18000fc88  test    byte ptr [rcx+1Ch], 80h
0x18000fc8c  jz      loc_18000F9D7
0x18000fc92  cmp     byte ptr [rcx+19h], 4
0x18000fc96  jb      loc_18000F9D7
0x18000fc9c  mov     rcx, [rcx+10h]
0x18000fca0  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fca7  mov     edx, 1Ah
0x18000fcac  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fcb3  call    WPP_SF_s
0x18000fcb8  jmp     loc_18000F9D7
0x18000fcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc4  cmp     rcx, r12
0x18000fcc7  jz      loc_18000FA21
0x18000fccd  test    byte ptr [rcx+1Ch], 80h
0x18000fcd1  jz      loc_18000FA21
0x18000fcd7  cmp     byte ptr [rcx+19h], 4
0x18000fcdb  jb      loc_18000FA21
0x18000fce1  mov     edx, 1Bh
0x18000fce6  jmp     short loc_18000FCED
0x18000fce8  mov     edx, 1Dh
0x18000fced  mov     rcx, [rcx+10h]
0x18000fcf1  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fcf8  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fcff  call    WPP_SF_s
0x18000fd04  jmp     short loc_18000FD52
0x18000fd06  test    byte ptr [rcx+1Ch], 80h
0x18000fd0a  jz      loc_18000FA21
0x18000fd10  cmp     byte ptr [rcx+19h], 4
0x18000fd14  jb      loc_18000FA21
0x18000fd1a  jmp     short loc_18000FCE8
0x18000fd1c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd23  cmp     rcx, r12
0x18000fd26  jz      loc_18000FA21
0x18000fd2c  test    byte ptr [rcx+1Ch], 80h
0x18000fd30  jz      loc_18000FA21
0x18000fd36  cmp     byte ptr [rcx+19h], 2
0x18000fd3a  jb      loc_18000FA21
0x18000fd40  mov     rcx, [rcx+10h]
0x18000fd44  mov     edx, 1Eh
0x18000fd49  mov     [rsp+58h+var_38], eax
0x18000fd4d  call    WPP_SF_sL
0x18000fd52  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd59  jmp     loc_18000FA21
0x18000fd5e  test    byte ptr [rcx+1Ch], 80h
0x18000fd62  jz      loc_18000FB3E
0x18000fd68  cmp     byte ptr [rcx+19h], 4
0x18000fd6c  jb      loc_18000FB3E
0x18000fd72  mov     rcx, [rcx+10h]
0x18000fd76  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000fd7d  mov     edx, 20h ; ' '
0x18000fd82  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fd89  call    WPP_SF_s
0x18000fd8e  jmp     loc_18000FB3E
0x18000fd93  mov     r15d, [rbx]
0x18000fd96  jmp     loc_18000F989
0x18000fd9b  test    byte ptr [rcx+1Ch], 80h
0x18000fd9f  jz      loc_18000F9AD
0x18000fda5  cmp     byte ptr [rcx+19h], 6
0x18000fda9  jb      loc_18000F9AD
0x18000fdaf  mov     rcx, [rcx+10h]
0x18000fdb3  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000fdba  mov     edx, 22h ; '"'
  ... truncated ...
```
