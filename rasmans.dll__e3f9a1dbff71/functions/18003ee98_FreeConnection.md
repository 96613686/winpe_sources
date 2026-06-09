# FreeConnection

- ea: `0x18003ee98`
- end: `0x18003f2d7`
- name: `FreeConnection`
- size: `1087`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `6`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015c90`
- `0x180019184`
- `0x180019e90`
- `0x18001f83c`
- `0x18004563c`
- `0x180045f64`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180005f1c`
- `0x18003ea70`
- `0x18003ee98`
- `0x18003f3a8`
- `0x18003f458`
- `0x18004033c`
- `0x180049d94`
- `0x18009408c`
- `0x180098b18`
- `0x1800e3c88`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f0c1`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003f05b`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x18003f05b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f02c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003f02c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f09d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f157`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f19a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f27c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f09d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f157`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f19a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f1e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f21d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003f27c`

## string_xrefs

- `0x18003ef5a`: `SYSTEM\CurrentControlSet\Services\Tcpip\Linkage\`

## pseudocode

```c
double __fastcall FreeConnection(char *hMem)
{
  int v1; // ebx
  unsigned int v3; // eax
  double result; // xmm0_8
  void *v5; // rcx
  HLOCAL *Connection; // rax
  HLOCAL *v7; // rbx
  struct _OVERLAPPED *v8; // rax
  struct _OVERLAPPED *v9; // rsi
  struct _LIST_ENTRY *Flink; // rbx
  DWORD LastError; // eax
  struct _LIST_ENTRY *v12; // rbx
  DWORD v13; // eax
  void *v14; // rcx
  void *v15; // rcx
  __int64 UserData; // rax
  __int64 v17; // rsi
  __int64 v18; // rax
  __int64 v19; // r8
  _BYTE *v20; // rdx
  void *v21; // rcx
  _QWORD *v22; // rcx
  unsigned int v23; // edx
  __int64 v24; // r8
  void *v25; // rcx
  __int64 v26; // rcx
  _QWORD *v27; // rax
  void *v28; // rcx
  void *v29; // rcx
  __int64 v30; // rax
  _BYTE *v31; // rax
  BYTE *v32; // rcx
  BYTE *v33; // rcx
  void *v34; // rcx
  int v35[4]; // [rsp+30h] [rbp-98h] BYREF
  char v36[80]; // [rsp+40h] [rbp-88h] BYREF

  v1 = *((_DWORD *)hMem + 30);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_qc(WPP_GLOBAL_Control[1].Flink, 212, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, hMem, v1 != 0);
  }
  memset_0(v36, 0, 0x4Eu);
  v35[0] = 0;
  if ( (unsigned int)RegHelpStringFromGuid(hMem + 144, v36) )
  {
    v3 = DwRemoveLinkageKeys(
           v36,
           L"SYSTEM\\CurrentControlSet\\Services\\Tcpip\\Linkage\\",
           L"Bind",
           (__int64)L"\\Device\\",
           v35,
           TraceHandle);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        result = WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 213, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v3);
      }
    }
  }
  if ( v1 )
  {
    v5 = (void *)*((_QWORD *)hMem + 16);
    if ( v5 )
    {
      Connection = FindConnection(v5);
      v7 = Connection;
      if ( Connection )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 214, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, Connection[2]);
        }
        *((_DWORD *)v7 + 42) &= ~1u;
      }
      else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 215, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
      v8 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x38u);
      v9 = v8;
      if ( v8 )
      {
        LODWORD(v8[1].Internal) = 17;
        v8[1].Pointer = (PVOID)*((_QWORD *)hMem + 16);
        if ( !PostQueuedCompletionStatus(hIoCompletionPort, 0, 0, v8) )
        {
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            Flink = WPP_GLOBAL_Control[1].Flink;
            LastError = GetLastError();
            result = WPP_SF_d(Flink, 216, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, LastError);
          }
          LocalFree(v9);
        }
      }
      else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = WPP_GLOBAL_Control[1].Flink;
        v13 = GetLastError();
        result = WPP_SF_d(v12, 217, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v13);
      }
    }
  }
  v14 = (void *)*((_QWORD *)hMem + 10);
  if ( v14 )
  {
    CloseHandle(v14);
    *((_QWORD *)hMem + 10) = 0;
  }
  v15 = (void *)*((_QWORD *)hMem + 13);
  if ( v15 )
  {
    CloseHandle(v15);
    *((_QWORD *)hMem + 13) = 0;
  }
  UserData = GetUserData(hMem + 32, 6);
  v17 = 2048;
  if ( UserData )
  {
    if ( *(_DWORD *)(UserData + 20) >= 0xC28u )
    {
      v18 = UserData + 24;
      if ( v18 )
      {
        if ( *(_DWORD *)(v18 + 4) )
        {
          v19 = 2048;
          v20 = (_BYTE *)(v18 + 8);
          do
          {
            *v20++ = 0;
            --v19;
          }
          while ( v19 );
          *(_DWORD *)(v18 + 4) = 0;
        }
      }
    }
  }
  FreeUserData(hMem + 32);
  v21 = (void *)*((_QWORD *)hMem + 114);
  if ( v21 )
  {
    LocalFree(v21);
    *((_QWORD *)hMem + 114) = 0;
  }
  FreeNotifierList(hMem + 48);
  v22 = (_QWORD *)*((_QWORD *)hMem + 7);
  if ( v22 )
  {
    if ( *((_DWORD *)hMem + 16) )
    {
      v23 = 0;
      do
      {
        v24 = v22[v23];
        if ( v24 )
        {
          *(_QWORD *)(v24 + 1064) = 0;
          v22 = (_QWORD *)*((_QWORD *)hMem + 7);
        }
        ++v23;
      }
      while ( v23 < *((_DWORD *)hMem + 16) );
    }
    LocalFree(v22);
  }
  v25 = (void *)*((_QWORD *)hMem + 12);
  if ( v25 )
    LocalFree(v25);
  v26 = *(_QWORD *)hMem;
  if ( *(_QWORD *)hMem )
  {
    v27 = (_QWORD *)*((_QWORD *)hMem + 1);
    if ( v27 )
    {
      *v27 = v26;
      *(_QWORD *)(v26 + 8) = v27;
    }
  }
  v28 = (void *)*((_QWORD *)hMem + 109);
  if ( v28 )
    LocalFree(v28);
  v29 = (void *)*((_QWORD *)hMem + 111);
  if ( v29 )
    LocalFree(v29);
  v30 = *((_QWORD *)hMem + 115);
  if ( v30 )
  {
    if ( *(_DWORD *)(v30 + 4) )
    {
      v31 = (_BYTE *)(v30 + 8);
      do
      {
        *v31++ = 0;
        --v17;
      }
      while ( v17 );
      *(_DWORD *)(*((_QWORD *)hMem + 115) + 4LL) = 0;
    }
    LocalFree(*((HLOCAL *)hMem + 115));
    *((_QWORD *)hMem + 115) = 0;
  }
  v32 = (BYTE *)*((_QWORD *)hMem + 116);
  if ( v32 )
  {
    VpnFreeNgcTicketContext(v32);
    *((_QWORD *)hMem + 116) = 0;
  }
  v33 = (BYTE *)*((_QWORD *)hMem + 117);
  if ( v33 )
  {
    VpnFreeNgcTicketContext(v33);
    *((_QWORD *)hMem + 117) = 0;
  }
  v34 = (void *)*((_QWORD *)hMem + 118);
  if ( v34 )
  {
    LocalFree(v34);
    *((_QWORD *)hMem + 118) = 0;
    *((_DWORD *)hMem + 238) = 0;
  }
  LocalFree(hMem);
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    return WPP_SF_(WPP_GLOBAL_Control[1].Flink, 218, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x18003ee98  mov     [rsp+arg_8], rbx
0x18003ee9d  mov     [rsp+arg_10], rbp
0x18003eea2  push    rsi
0x18003eea3  push    rdi
0x18003eea4  push    r12
0x18003eea6  push    r13
0x18003eea8  push    r15
0x18003eeaa  sub     rsp, 0A0h
0x18003eeb1  mov     rax, cs:__security_cookie
0x18003eeb8  xor     rax, rsp
0x18003eebb  mov     [rsp+0C8h+var_38], rax
0x18003eec3  mov     ebx, [rcx+78h]
0x18003eec6  mov     rdi, rcx
0x18003eec9  mov     rcx, cs:WPP_GLOBAL_Control
0x18003eed0  lea     r12, WPP_GLOBAL_Control
0x18003eed7  xor     ebp, ebp
0x18003eed9  lea     r13, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003eee0  mov     r15d, 2000h
0x18003eee6  cmp     rcx, r12
0x18003eee9  jz      short loc_18003EF14
0x18003eeeb  test    [rcx+1Ch], r15d
0x18003eeef  jz      short loc_18003EF14
0x18003eef1  cmp     byte ptr [rcx+19h], 6
0x18003eef5  jb      short loc_18003EF14
0x18003eef7  mov     rcx, [rcx+10h]
0x18003eefb  test    ebx, ebx
0x18003eefd  mov     edx, 0D4h
0x18003ef02  mov     r9, rdi
0x18003ef05  setnz   al
0x18003ef08  mov     r8, r13
0x18003ef0b  mov     byte ptr [rsp+0C8h+var_A8], al
0x18003ef0f  call    WPP_SF_qc
0x18003ef14  xor     edx, edx; Val
0x18003ef16  lea     rcx, [rsp+0C8h+var_88]; void *
0x18003ef1b  lea     r8d, [rdx+4Eh]; Size
0x18003ef1f  call    memset_0
0x18003ef24  lea     rcx, [rdi+90h]
0x18003ef2b  mov     [rsp+0C8h+var_98], ebp
0x18003ef2f  lea     rdx, [rsp+0C8h+var_88]
0x18003ef34  call    RegHelpStringFromGuid
0x18003ef39  test    eax, eax
0x18003ef3b  jz      short loc_18003EFA0
0x18003ef3d  mov     eax, cs:TraceHandle
0x18003ef43  lea     r9, aDevice_1; "\\Device\\"
0x18003ef4a  mov     [rsp+0C8h+var_A0], eax
0x18003ef4e  lea     r8, aBind; "Bind"
0x18003ef55  lea     rax, [rsp+0C8h+var_98]
0x18003ef5a  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x18003ef61  mov     [rsp+0C8h+var_A8], rax
0x18003ef66  lea     rcx, [rsp+0C8h+var_88]
0x18003ef6b  call    DwRemoveLinkageKeys
0x18003ef70  test    eax, eax
0x18003ef72  jz      short loc_18003EFA0
0x18003ef74  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ef7b  cmp     rcx, r12
0x18003ef7e  jz      short loc_18003EFA0
0x18003ef80  test    [rcx+1Ch], r15d
0x18003ef84  jz      short loc_18003EFA0
0x18003ef86  cmp     byte ptr [rcx+19h], 2
0x18003ef8a  jb      short loc_18003EFA0
0x18003ef8c  mov     rcx, [rcx+10h]
0x18003ef90  mov     edx, 0D5h
0x18003ef95  mov     r9d, eax
0x18003ef98  mov     r8, r13
0x18003ef9b  call    WPP_SF_d
0x18003efa0  test    ebx, ebx
0x18003efa2  jz      loc_18003F0DA
0x18003efa8  mov     rcx, [rdi+80h]
0x18003efaf  test    rcx, rcx
0x18003efb2  jz      loc_18003F0DA
0x18003efb8  call    FindConnection
0x18003efbd  mov     rbx, rax
0x18003efc0  test    rax, rax
0x18003efc3  jz      short loc_18003EFFB
0x18003efc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003efcc  cmp     rcx, r12
0x18003efcf  jz      short loc_18003EFF2
0x18003efd1  test    [rcx+1Ch], r15d
0x18003efd5  jz      short loc_18003EFF2
0x18003efd7  cmp     byte ptr [rcx+19h], 5
0x18003efdb  jb      short loc_18003EFF2
0x18003efdd  mov     r9, [rax+10h]
0x18003efe1  mov     edx, 0D6h
0x18003efe6  mov     rcx, [rcx+10h]
0x18003efea  mov     r8, r13
0x18003efed  call    WPP_SF_q
0x18003eff2  and     dword ptr [rbx+0A8h], 0FFFFFFFEh
0x18003eff9  jmp     short loc_18003F024
0x18003effb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f002  cmp     rcx, r12
0x18003f005  jz      short loc_18003F024
0x18003f007  test    [rcx+1Ch], r15d
0x18003f00b  jz      short loc_18003F024
0x18003f00d  cmp     byte ptr [rcx+19h], 5
0x18003f011  jb      short loc_18003F024
0x18003f013  mov     rcx, [rcx+10h]
0x18003f017  mov     edx, 0D7h
0x18003f01c  mov     r8, r13
0x18003f01f  call    WPP_SF_
0x18003f024  mov     edx, 38h ; '8'; uBytes
0x18003f029  lea     ecx, [rdx+8]; uFlags
0x18003f02c  call    cs:__imp_LocalAlloc
0x18003f032  mov     rsi, rax
0x18003f035  test    rax, rax
0x18003f038  jz      short loc_18003F0A5
0x18003f03a  mov     dword ptr [rax+20h], 11h
0x18003f041  mov     r9, rax; lpOverlapped
0x18003f044  mov     rcx, [rdi+80h]
0x18003f04b  xor     r8d, r8d; dwCompletionKey
0x18003f04e  mov     [rax+30h], rcx
0x18003f052  xor     edx, edx; dwNumberOfBytesTransferred
0x18003f054  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x18003f05b  call    cs:__imp_PostQueuedCompletionStatus
0x18003f061  test    eax, eax
0x18003f063  jnz     short loc_18003F0DA
0x18003f065  mov     rbx, cs:WPP_GLOBAL_Control
0x18003f06c  cmp     rbx, r12
0x18003f06f  jz      short loc_18003F09A
0x18003f071  test    [rbx+1Ch], r15d
0x18003f075  jz      short loc_18003F09A
0x18003f077  cmp     byte ptr [rbx+19h], 2
0x18003f07b  jb      short loc_18003F09A
0x18003f07d  mov     rbx, [rbx+10h]
0x18003f081  call    cs:__imp_GetLastError
0x18003f087  mov     edx, 0D8h
0x18003f08c  mov     r8, r13
0x18003f08f  mov     r9d, eax
0x18003f092  mov     rcx, rbx
0x18003f095  call    WPP_SF_d
0x18003f09a  mov     rcx, rsi; hMem
0x18003f09d  call    cs:__imp_LocalFree
0x18003f0a3  jmp     short loc_18003F0DA
0x18003f0a5  mov     rbx, cs:WPP_GLOBAL_Control
0x18003f0ac  cmp     rbx, r12
0x18003f0af  jz      short loc_18003F0DA
0x18003f0b1  test    [rbx+1Ch], r15d
0x18003f0b5  jz      short loc_18003F0DA
0x18003f0b7  cmp     byte ptr [rbx+19h], 2
0x18003f0bb  jb      short loc_18003F0DA
0x18003f0bd  mov     rbx, [rbx+10h]
0x18003f0c1  call    cs:__imp_GetLastError
0x18003f0c7  mov     edx, 0D9h
0x18003f0cc  mov     r8, r13
0x18003f0cf  mov     r9d, eax
0x18003f0d2  mov     rcx, rbx
0x18003f0d5  call    WPP_SF_d
0x18003f0da  mov     rcx, [rdi+50h]; hObject
0x18003f0de  test    rcx, rcx
0x18003f0e1  jz      short loc_18003F0ED
0x18003f0e3  call    cs:__imp_CloseHandle
0x18003f0e9  mov     [rdi+50h], rbp
0x18003f0ed  mov     rcx, [rdi+68h]; hObject
0x18003f0f1  test    rcx, rcx
0x18003f0f4  jz      short loc_18003F100
0x18003f0f6  call    cs:__imp_CloseHandle
0x18003f0fc  mov     [rdi+68h], rbp
0x18003f100  mov     edx, 6
0x18003f105  lea     rcx, [rdi+20h]
0x18003f109  call    GetUserData
0x18003f10e  mov     esi, 800h
0x18003f113  test    rax, rax
0x18003f116  jz      short loc_18003F142
0x18003f118  cmp     dword ptr [rax+14h], 0C28h
0x18003f11f  jb      short loc_18003F142
0x18003f121  add     rax, 18h
0x18003f125  jz      short loc_18003F142
0x18003f127  cmp     [rax+4], ebp
0x18003f12a  jbe     short loc_18003F142
0x18003f12c  mov     r8d, esi
0x18003f12f  lea     rdx, [rax+8]
0x18003f133  mov     [rdx], bpl
0x18003f136  inc     rdx
0x18003f139  sub     r8, 1
0x18003f13d  jnz     short loc_18003F133
0x18003f13f  mov     [rax+4], ebp
0x18003f142  lea     rcx, [rdi+20h]
0x18003f146  call    FreeUserData
0x18003f14b  mov     rcx, [rdi+390h]; hMem
0x18003f152  test    rcx, rcx
0x18003f155  jz      short loc_18003F164
0x18003f157  call    cs:__imp_LocalFree
0x18003f15d  mov     [rdi+390h], rbp
0x18003f164  lea     rcx, [rdi+30h]
0x18003f168  call    FreeNotifierList
0x18003f16d  mov     rcx, [rdi+38h]
0x18003f171  test    rcx, rcx
0x18003f174  jz      short loc_18003F1A0
0x18003f176  cmp     [rdi+40h], ebp
0x18003f179  jbe     short loc_18003F19A
0x18003f17b  mov     edx, ebp
0x18003f17d  mov     eax, edx
0x18003f17f  mov     r8, [rcx+rax*8]
0x18003f183  test    r8, r8
0x18003f186  jz      short loc_18003F193
0x18003f188  mov     [r8+428h], rbp
0x18003f18f  mov     rcx, [rdi+38h]; hMem
0x18003f193  inc     edx
0x18003f195  cmp     edx, [rdi+40h]
0x18003f198  jb      short loc_18003F17D
0x18003f19a  call    cs:__imp_LocalFree
0x18003f1a0  mov     rcx, [rdi+60h]; hMem
0x18003f1a4  test    rcx, rcx
0x18003f1a7  jz      short loc_18003F1AF
0x18003f1a9  call    cs:__imp_LocalFree
0x18003f1af  mov     rcx, [rdi]
0x18003f1b2  test    rcx, rcx
0x18003f1b5  jz      short loc_18003F1C7
0x18003f1b7  mov     rax, [rdi+8]
0x18003f1bb  test    rax, rax
0x18003f1be  jz      short loc_18003F1C7
0x18003f1c0  mov     [rax], rcx
0x18003f1c3  mov     [rcx+8], rax
0x18003f1c7  mov     rcx, [rdi+368h]; hMem
0x18003f1ce  test    rcx, rcx
0x18003f1d1  jz      short loc_18003F1D9
0x18003f1d3  call    cs:__imp_LocalFree
0x18003f1d9  mov     rcx, [rdi+378h]; hMem
0x18003f1e0  test    rcx, rcx
0x18003f1e3  jz      short loc_18003F1EB
0x18003f1e5  call    cs:__imp_LocalFree
0x18003f1eb  mov     rax, [rdi+398h]
0x18003f1f2  test    rax, rax
0x18003f1f5  jz      short loc_18003F22A
0x18003f1f7  cmp     [rax+4], ebp
0x18003f1fa  jbe     short loc_18003F216
0x18003f1fc  add     rax, 8
0x18003f200  mov     [rax], bpl
0x18003f203  inc     rax
0x18003f206  sub     rsi, 1
0x18003f20a  jnz     short loc_18003F200
0x18003f20c  mov     rax, [rdi+398h]
0x18003f213  mov     [rax+4], ebp
0x18003f216  mov     rcx, [rdi+398h]; hMem
0x18003f21d  call    cs:__imp_LocalFree
0x18003f223  mov     [rdi+398h], rbp
0x18003f22a  mov     rcx, [rdi+3A0h]; pbInput
0x18003f231  test    rcx, rcx
0x18003f234  jz      short loc_18003F242
0x18003f236  call    VpnFreeNgcTicketContext
0x18003f23b  mov     [rdi+3A0h], rbp
0x18003f242  mov     rcx, [rdi+3A8h]; pbInput
0x18003f249  test    rcx, rcx
0x18003f24c  jz      short loc_18003F25A
0x18003f24e  call    VpnFreeNgcTicketContext
0x18003f253  mov     [rdi+3A8h], rbp
0x18003f25a  mov     rcx, [rdi+3B0h]; hMem
0x18003f261  test    rcx, rcx
0x18003f264  jz      short loc_18003F279
0x18003f266  call    cs:__imp_LocalFree
0x18003f26c  mov     [rdi+3B0h], rbp
0x18003f273  mov     [rdi+3B8h], ebp
0x18003f279  mov     rcx, rdi; hMem
0x18003f27c  call    cs:__imp_LocalFree
0x18003f282  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f289  cmp     rcx, r12
0x18003f28c  jz      short loc_18003F2AB
0x18003f28e  test    [rcx+1Ch], r15d
0x18003f292  jz      short loc_18003F2AB
0x18003f294  cmp     byte ptr [rcx+19h], 6
0x18003f298  jb      short loc_18003F2AB
0x18003f29a  mov     rcx, [rcx+10h]
0x18003f29e  mov     edx, 0DAh
0x18003f2a3  mov     r8, r13
0x18003f2a6  call    WPP_SF_
0x18003f2ab  mov     rcx, [rsp+0C8h+var_38]
0x18003f2b3  xor     rcx, rsp; StackCookie
0x18003f2b6  call    __security_check_cookie
0x18003f2bb  lea     r11, [rsp+0C8h+var_28]
0x18003f2c3  mov     rbx, [r11+38h]
0x18003f2c7  mov     rbp, [r11+40h]
0x18003f2cb  mov     rsp, r11
0x18003f2ce  pop     r15
0x18003f2d0  pop     r13
0x18003f2d2  pop     r12
0x18003f2d4  pop     rdi
0x18003f2d5  pop     rsi
0x18003f2d6  retn
```
