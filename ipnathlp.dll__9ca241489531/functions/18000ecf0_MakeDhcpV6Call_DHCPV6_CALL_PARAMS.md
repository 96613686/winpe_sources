# MakeDhcpV6Call(_DHCPV6_CALL_PARAMS *)

- ea: `0x18000ecf0`
- end: `0x18000f246`
- name: `?MakeDhcpV6Call@@YAKPEAU_DHCPV6_CALL_PARAMS@@@Z`
- size: `1366`
- prototype: `unsigned int __fastcall(PVOID Context)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d6a0`
- `0x18000ec28`
- `0x180068484`
- `0x180068558`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000ecf0`
- `0x18000f250`
- `0x180068634`

## import_xrefs

- `dhcpcsvc6!Dhcpv6CancelOperation` at `0x18000efc4`
- `dhcpcsvc6!Dhcpv6CancelOperation` at `0x18000efc4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ed5d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ed5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee0b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ef04`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000ef04`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000ee74`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000ee74`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ed80`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18000ed80`

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
0x18000ecf0  sub     rsp, 58h
0x18000ecf4  mov     [rsp+58h+arg_0], rbx
0x18000ecf9  mov     rbx, rcx
0x18000ecfc  mov     [rsp+58h+arg_8], rbp
0x18000ed01  mov     [rsp+58h+var_8], r12
0x18000ed06  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed0d  lea     r12, WPP_GLOBAL_Control
0x18000ed14  cmp     rcx, r12
0x18000ed17  jnz     loc_18000EFCF
0x18000ed1d  xor     eax, eax
0x18000ed1f  mov     [rsp+58h+var_18], r15
0x18000ed24  xorps   xmm0, xmm0
0x18000ed27  mov     ebp, 1
0x18000ed2c  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x18000ed31  mov     [rbx+10h], ebp
0x18000ed34  xchg    eax, [rbx+4]
0x18000ed37  mov     eax, [rbx+14h]
0x18000ed3a  test    eax, eax
0x18000ed3c  jnz     loc_18000EF36
0x18000ed42  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ed49  cmp     rcx, r12
0x18000ed4c  jnz     short loc_18000EDBF
0x18000ed4e  xor     r9d, r9d; lpName
0x18000ed51  mov     [rsp+58h+var_10], r14
0x18000ed56  xor     r8d, r8d; bInitialState
0x18000ed59  xor     edx, edx; bManualReset
0x18000ed5b  xor     ecx, ecx; lpEventAttributes
0x18000ed5d  call    cs:__imp_CreateEventW
0x18000ed63  mov     [rbx+8], rax
0x18000ed67  test    rax, rax
0x18000ed6a  jz      loc_18000F08B
0x18000ed70  mov     r8d, 10h; Flags
0x18000ed76  lea     rcx, ?DhcpV6CallWorkItem@@YAKPEAX@Z; Function
0x18000ed7d  mov     rdx, rbx; Context
0x18000ed80  call    cs:__imp_QueueUserWorkItem
0x18000ed86  test    eax, eax
0x18000ed88  jz      short loc_18000EDEC
0x18000ed8a  mov     rax, [rbx+8]
0x18000ed8e  xor     r15d, r15d
0x18000ed91  mov     [rsp+58h+Handles], rax
0x18000ed96  mov     rax, [rbx+18h]
0x18000ed9a  mov     [rsp+58h+Handles+8], rax
0x18000ed9f  mov     eax, [rbx+14h]
0x18000eda2  mov     [rsp+58h+arg_10], rsi
0x18000eda7  mov     [rsp+58h+arg_18], rdi
0x18000edac  cmp     eax, 2
0x18000edaf  jz      loc_18000EE4A
0x18000edb5  mov     esi, 0FFFFFFFFh
0x18000edba  jmp     loc_18000EE4D
0x18000edbf  test    byte ptr [rcx+1Ch], 80h
0x18000edc3  jz      short loc_18000ED4E
0x18000edc5  cmp     byte ptr [rcx+19h], 4
0x18000edc9  jb      short loc_18000ED4E
0x18000edcb  mov     edx, 14h
0x18000edd0  mov     rcx, [rcx+10h]
0x18000edd4  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000eddb  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000ede2  call    WPP_SF_s
0x18000ede7  jmp     loc_18000ED4E
0x18000edec  xor     ebp, ebp
0x18000edee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000edf5  cmp     rcx, r12
0x18000edf8  jnz     loc_18000F0CD
0x18000edfe  call    cs:__imp_GetLastError
0x18000ee04  mov     r15d, eax
0x18000ee07  mov     rcx, [rbx+8]; hObject
0x18000ee0b  call    cs:__imp_CloseHandle
0x18000ee11  test    ebp, ebp
0x18000ee13  jnz     loc_18000F20D
0x18000ee19  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee20  mov     r14, [rsp+58h+var_10]
0x18000ee25  mov     rbp, [rsp+58h+arg_8]
0x18000ee2a  cmp     rcx, r12
0x18000ee2d  mov     r12, [rsp+58h+var_8]
0x18000ee32  mov     rbx, [rsp+58h+arg_0]
0x18000ee37  jnz     loc_18000F215
0x18000ee3d  mov     eax, r15d
0x18000ee40  mov     r15, [rsp+58h+var_18]
0x18000ee45  add     rsp, 58h
0x18000ee49  retn
0x18000ee4a  mov     esi, [rbx+20h]
0x18000ee4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee54  xor     edi, edi
0x18000ee56  cmp     eax, 2
0x18000ee59  setnz   dil
0x18000ee5d  cmp     rcx, r12
0x18000ee60  jnz     loc_18000F102
0x18000ee66  mov     r9d, esi; dwMilliseconds
0x18000ee69  lea     rdx, [rsp+58h+Handles]; lpHandles
0x18000ee6e  xor     r8d, r8d; bWaitAll
0x18000ee71  lea     ecx, [rdi+1]; nCount
0x18000ee74  call    cs:__imp_WaitForMultipleObjects
0x18000ee7a  mov     rsi, [rsp+58h+arg_10]
0x18000ee7f  cmp     eax, 102h
0x18000ee84  jz      loc_18000F137
0x18000ee8a  test    eax, eax
0x18000ee8c  jz      loc_18000EF6D
0x18000ee92  cmp     eax, ebp
0x18000ee94  jnz     loc_18000F196
0x18000ee9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eea1  cmp     rcx, r12
0x18000eea4  jnz     loc_18000F180
0x18000eeaa  mov     edi, ebp
0x18000eeac  cmp     rcx, r12
0x18000eeaf  jz      short loc_18000EED9
0x18000eeb1  test    byte ptr [rcx+1Ch], 80h
0x18000eeb5  jz      short loc_18000EED9
0x18000eeb7  cmp     byte ptr [rcx+19h], 4
0x18000eebb  jb      short loc_18000EED9
0x18000eebd  mov     rcx, [rcx+10h]
0x18000eec1  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000eec8  mov     edx, 1Fh
0x18000eecd  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000eed4  call    WPP_SF_s
0x18000eed9  mov     [rbx+10h], r15d
0x18000eedd  nop     dword ptr [rax]
0x18000eee0  xor     eax, eax
0x18000eee2  lock xadd [rbx+4], eax
0x18000eee7  test    eax, eax
0x18000eee9  jnz     short loc_18000EF63
0x18000eeeb  test    edi, edi
0x18000eeed  jnz     loc_18000EFB4
0x18000eef3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eefa  cmp     rcx, r12
0x18000eefd  jnz     short loc_18000EF0C
0x18000eeff  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18000ef04  call    cs:__imp_Sleep
0x18000ef0a  jmp     short loc_18000EEE0
0x18000ef0c  test    byte ptr [rcx+1Ch], 80h
0x18000ef10  jz      short loc_18000EEFF
0x18000ef12  cmp     byte ptr [rcx+19h], 4
0x18000ef16  jb      short loc_18000EEFF
0x18000ef18  mov     rcx, [rcx+10h]
0x18000ef1c  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000ef23  mov     edx, 21h ; '!'
0x18000ef28  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000ef2f  call    WPP_SF_s
0x18000ef34  jmp     short loc_18000EEFF
0x18000ef36  mov     ecx, eax
0x18000ef38  sub     ecx, ebp
0x18000ef3a  jz      loc_18000F05D
0x18000ef40  cmp     ecx, ebp
0x18000ef42  jz      loc_18000F02F
0x18000ef48  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef4f  cmp     rcx, r12
0x18000ef52  jnz     loc_18000EFFD
0x18000ef58  mov     r15d, 57h ; 'W'
0x18000ef5e  jmp     loc_18000EE25
0x18000ef63  mov     rdi, [rsp+58h+arg_18]
0x18000ef68  jmp     loc_18000EE07
0x18000ef6d  xor     edi, edi
0x18000ef6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ef76  cmp     rcx, r12
0x18000ef79  jz      loc_18000EEE0
0x18000ef7f  test    byte ptr [rcx+1Ch], 80h
0x18000ef83  jz      loc_18000EEE0
0x18000ef89  cmp     byte ptr [rcx+19h], 4
0x18000ef8d  jb      loc_18000EEE0
0x18000ef93  mov     rcx, [rcx+10h]
0x18000ef97  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000ef9e  mov     edx, 1Ch
0x18000efa3  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000efaa  call    WPP_SF_s
0x18000efaf  jmp     loc_18000EEE0
0x18000efb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000efbb  cmp     rcx, r12
0x18000efbe  jnz     loc_18000F1D8
0x18000efc4  call    cs:__imp_Dhcpv6CancelOperation
0x18000efca  jmp     loc_18000EEF3
0x18000efcf  test    byte ptr [rcx+1Ch], 80h
0x18000efd3  jz      loc_18000ED1D
0x18000efd9  cmp     byte ptr [rcx+19h], 6
0x18000efdd  jb      loc_18000ED1D
0x18000efe3  mov     rcx, [rcx+10h]
0x18000efe7  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000efee  mov     edx, 13h
0x18000eff3  call    WPP_SF_
0x18000eff8  jmp     loc_18000ED1D
0x18000effd  test    byte ptr [rcx+1Ch], 80h
0x18000f001  jz      loc_18000EF58
0x18000f007  cmp     byte ptr [rcx+19h], 4
0x18000f00b  jb      loc_18000EF58
0x18000f011  mov     rcx, [rcx+10h]
0x18000f015  mov     edx, 17h
0x18000f01a  mov     [rsp+58h+var_38], eax
0x18000f01e  call    WPP_SF_sL
0x18000f023  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f02a  jmp     loc_18000EF58
0x18000f02f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f036  cmp     rcx, r12
0x18000f039  jz      loc_18000ED4E
0x18000f03f  test    byte ptr [rcx+1Ch], 80h
0x18000f043  jz      loc_18000ED4E
0x18000f049  cmp     byte ptr [rcx+19h], 4
0x18000f04d  jb      loc_18000ED4E
0x18000f053  mov     edx, 16h
0x18000f058  jmp     loc_18000EDD0
0x18000f05d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f064  cmp     rcx, r12
0x18000f067  jz      loc_18000ED4E
0x18000f06d  test    byte ptr [rcx+1Ch], 80h
0x18000f071  jz      loc_18000ED4E
0x18000f077  cmp     byte ptr [rcx+19h], 4
0x18000f07b  jb      loc_18000ED4E
0x18000f081  mov     edx, 15h
0x18000f086  jmp     loc_18000EDD0
0x18000f08b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f092  cmp     rcx, r12
0x18000f095  jz      short loc_18000F0BF
0x18000f097  test    byte ptr [rcx+1Ch], 80h
0x18000f09b  jz      short loc_18000F0BF
0x18000f09d  cmp     byte ptr [rcx+19h], 4
0x18000f0a1  jb      short loc_18000F0BF
0x18000f0a3  mov     rcx, [rcx+10h]
0x18000f0a7  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f0ae  mov     edx, 18h
0x18000f0b3  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f0ba  call    WPP_SF_s
0x18000f0bf  call    cs:__imp_GetLastError
0x18000f0c5  mov     r15d, eax
0x18000f0c8  jmp     loc_18000EE19
0x18000f0cd  test    byte ptr [rcx+1Ch], 80h
0x18000f0d1  jz      loc_18000EDFE
0x18000f0d7  cmp     byte ptr [rcx+19h], 4
0x18000f0db  jb      loc_18000EDFE
0x18000f0e1  mov     rcx, [rcx+10h]
0x18000f0e5  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f0ec  mov     edx, 19h
0x18000f0f1  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f0f8  call    WPP_SF_s
0x18000f0fd  jmp     loc_18000EDFE
0x18000f102  test    byte ptr [rcx+1Ch], 80h
0x18000f106  jz      loc_18000EE66
0x18000f10c  cmp     byte ptr [rcx+19h], 4
0x18000f110  jb      loc_18000EE66
0x18000f116  mov     rcx, [rcx+10h]
0x18000f11a  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f121  mov     edx, 1Ah
0x18000f126  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f12d  call    WPP_SF_s
0x18000f132  jmp     loc_18000EE66
0x18000f137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f13e  cmp     rcx, r12
0x18000f141  jz      loc_18000EEAA
0x18000f147  test    byte ptr [rcx+1Ch], 80h
0x18000f14b  jz      loc_18000EEAA
0x18000f151  cmp     byte ptr [rcx+19h], 4
0x18000f155  jb      loc_18000EEAA
0x18000f15b  mov     edx, 1Bh
0x18000f160  jmp     short loc_18000F167
0x18000f162  mov     edx, 1Dh
0x18000f167  mov     rcx, [rcx+10h]
0x18000f16b  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f172  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f179  call    WPP_SF_s
0x18000f17e  jmp     short loc_18000F1CC
0x18000f180  test    byte ptr [rcx+1Ch], 80h
0x18000f184  jz      loc_18000EEAA
0x18000f18a  cmp     byte ptr [rcx+19h], 4
0x18000f18e  jb      loc_18000EEAA
0x18000f194  jmp     short loc_18000F162
0x18000f196  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f19d  cmp     rcx, r12
0x18000f1a0  jz      loc_18000EEAA
0x18000f1a6  test    byte ptr [rcx+1Ch], 80h
0x18000f1aa  jz      loc_18000EEAA
0x18000f1b0  cmp     byte ptr [rcx+19h], 2
0x18000f1b4  jb      loc_18000EEAA
0x18000f1ba  mov     rcx, [rcx+10h]
0x18000f1be  mov     edx, 1Eh
0x18000f1c3  mov     [rsp+58h+var_38], eax
0x18000f1c7  call    WPP_SF_sL
0x18000f1cc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f1d3  jmp     loc_18000EEAA
0x18000f1d8  test    byte ptr [rcx+1Ch], 80h
0x18000f1dc  jz      loc_18000EFC4
0x18000f1e2  cmp     byte ptr [rcx+19h], 4
0x18000f1e6  jb      loc_18000EFC4
0x18000f1ec  mov     rcx, [rcx+10h]
0x18000f1f0  lea     r9, aMakedhcpv6call; "MakeDhcpV6Call"
0x18000f1f7  mov     edx, 20h ; ' '
0x18000f1fc  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f203  call    WPP_SF_s
0x18000f208  jmp     loc_18000EFC4
0x18000f20d  mov     r15d, [rbx]
0x18000f210  jmp     loc_18000EE19
0x18000f215  test    byte ptr [rcx+1Ch], 80h
0x18000f219  jz      loc_18000EE3D
0x18000f21f  cmp     byte ptr [rcx+19h], 6
0x18000f223  jb      loc_18000EE3D
0x18000f229  mov     rcx, [rcx+10h]
0x18000f22d  lea     r8, WPP_02f9d66c47ff394099e27486dbd70566_Traceguids
0x18000f234  mov     edx, 22h ; '"'
0x18000f239  mov     r9d, r15d
0x18000f23c  call    WPP_SF_d
0x18000f241  jmp     loc_18000EE3D
```
