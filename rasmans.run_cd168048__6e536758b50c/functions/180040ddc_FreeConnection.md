# FreeConnection

- ea: `0x180040ddc`
- end: `0x18004127e`
- name: `FreeConnection`
- size: `1186`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `6`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016500`
- `0x180019b58`
- `0x18001a8d0`
- `0x1800204d8`
- `0x180047954`
- `0x1800482c0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x180040998`
- `0x180040ddc`
- `0x180041354`
- `0x18004140c`
- `0x18004236c`
- `0x18004c19c`
- `0x180098bcc`
- `0x18009db94`
- `0x1800e577c`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004104d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041066`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004104d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041025`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180040fa9`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180040fa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040f70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040f70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ffb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800410cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041116`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004112b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004115b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041173`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800411b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004121c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040ffb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800410cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041116`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004112b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004115b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041173`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800411b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041200`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004121c`

## string_xrefs

- `0x180040e9e`: `SYSTEM\CurrentControlSet\Services\Tcpip\Linkage\`

## pseudocode

```c
double __fastcall FreeConnection(char *hMem)
{
  int v1; // ebx
  unsigned int v3; // eax
  __int64 v4; // rcx
  __int64 Connection; // rax
  __int64 v6; // rbx
  double result; // xmm0_8
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
    WPP_SF_qc(WPP_GLOBAL_Control[1].Flink, 212, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, hMem, v1 != 0);
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 213, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v3);
      }
    }
  }
  if ( v1 )
  {
    v4 = *((_QWORD *)hMem + 16);
    if ( v4 )
    {
      Connection = FindConnection(v4);
      v6 = Connection;
      if ( Connection )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control[1].Flink,
            214,
            WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids,
            *(_QWORD *)(Connection + 16));
        }
        *(_DWORD *)(v6 + 168) &= ~1u;
      }
      else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
             && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
      {
        result = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 215, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
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
            WPP_SF_d(Flink, 216, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, LastError);
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
        WPP_SF_d(v12, 217, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v13);
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
    return WPP_SF_(WPP_GLOBAL_Control[1].Flink, 218, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180040ddc  mov     [rsp+arg_8], rbx
0x180040de1  mov     [rsp+arg_10], rbp
0x180040de6  push    rsi
0x180040de7  push    rdi
0x180040de8  push    r12
0x180040dea  push    r13
0x180040dec  push    r15
0x180040dee  sub     rsp, 0A0h
0x180040df5  mov     rax, cs:__security_cookie
0x180040dfc  xor     rax, rsp
0x180040dff  mov     [rsp+0C8h+var_38], rax
0x180040e07  mov     ebx, [rcx+78h]
0x180040e0a  mov     rdi, rcx
0x180040e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e14  lea     r12, WPP_GLOBAL_Control
0x180040e1b  xor     ebp, ebp
0x180040e1d  lea     r13, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180040e24  mov     r15d, 2000h
0x180040e2a  cmp     rcx, r12
0x180040e2d  jz      short loc_180040E58
0x180040e2f  test    [rcx+1Ch], r15d
0x180040e33  jz      short loc_180040E58
0x180040e35  cmp     byte ptr [rcx+19h], 6
0x180040e39  jb      short loc_180040E58
0x180040e3b  mov     rcx, [rcx+10h]
0x180040e3f  test    ebx, ebx
0x180040e41  mov     edx, 0D4h
0x180040e46  mov     r9, rdi
0x180040e49  setnz   al
0x180040e4c  mov     r8, r13
0x180040e4f  mov     byte ptr [rsp+0C8h+var_A8], al
0x180040e53  call    WPP_SF_qc
0x180040e58  xor     edx, edx; Val
0x180040e5a  lea     rcx, [rsp+0C8h+var_88]; void *
0x180040e5f  lea     r8d, [rdx+4Eh]; Size
0x180040e63  call    memset_0
0x180040e68  lea     rcx, [rdi+90h]
0x180040e6f  mov     [rsp+0C8h+var_98], ebp
0x180040e73  lea     rdx, [rsp+0C8h+var_88]
0x180040e78  call    RegHelpStringFromGuid
0x180040e7d  test    eax, eax
0x180040e7f  jz      short loc_180040EE4
0x180040e81  mov     eax, cs:TraceHandle
0x180040e87  lea     r9, aDevice_1; "\\Device\\"
0x180040e8e  mov     [rsp+0C8h+var_A0], eax
0x180040e92  lea     r8, aBind; "Bind"
0x180040e99  lea     rax, [rsp+0C8h+var_98]
0x180040e9e  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Tc"...
0x180040ea5  mov     [rsp+0C8h+var_A8], rax
0x180040eaa  lea     rcx, [rsp+0C8h+var_88]
0x180040eaf  call    DwRemoveLinkageKeys
0x180040eb4  test    eax, eax
0x180040eb6  jz      short loc_180040EE4
0x180040eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ebf  cmp     rcx, r12
0x180040ec2  jz      short loc_180040EE4
0x180040ec4  test    [rcx+1Ch], r15d
0x180040ec8  jz      short loc_180040EE4
0x180040eca  cmp     byte ptr [rcx+19h], 2
0x180040ece  jb      short loc_180040EE4
0x180040ed0  mov     rcx, [rcx+10h]
0x180040ed4  mov     edx, 0D5h
0x180040ed9  mov     r9d, eax
0x180040edc  mov     r8, r13
0x180040edf  call    WPP_SF_d
0x180040ee4  test    ebx, ebx
0x180040ee6  jz      loc_180041044
0x180040eec  mov     rcx, [rdi+80h]
0x180040ef3  test    rcx, rcx
0x180040ef6  jz      loc_180041044
0x180040efc  call    FindConnection
0x180040f01  mov     rbx, rax
0x180040f04  test    rax, rax
0x180040f07  jz      short loc_180040F3F
0x180040f09  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f10  cmp     rcx, r12
0x180040f13  jz      short loc_180040F36
0x180040f15  test    [rcx+1Ch], r15d
0x180040f19  jz      short loc_180040F36
0x180040f1b  cmp     byte ptr [rcx+19h], 5
0x180040f1f  jb      short loc_180040F36
0x180040f21  mov     r9, [rax+10h]
0x180040f25  mov     edx, 0D6h
0x180040f2a  mov     rcx, [rcx+10h]
0x180040f2e  mov     r8, r13
0x180040f31  call    WPP_SF_q
0x180040f36  and     dword ptr [rbx+0A8h], 0FFFFFFFEh
0x180040f3d  jmp     short loc_180040F68
0x180040f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040f46  cmp     rcx, r12
0x180040f49  jz      short loc_180040F68
0x180040f4b  test    [rcx+1Ch], r15d
0x180040f4f  jz      short loc_180040F68
0x180040f51  cmp     byte ptr [rcx+19h], 5
0x180040f55  jb      short loc_180040F68
0x180040f57  mov     rcx, [rcx+10h]
0x180040f5b  mov     edx, 0D7h
0x180040f60  mov     r8, r13
0x180040f63  call    WPP_SF_
0x180040f68  mov     edx, 38h ; '8'; uBytes
0x180040f6d  lea     ecx, [rdx+8]; uFlags
0x180040f70  call    cs:__imp_LocalAlloc
0x180040f77  nop     dword ptr [rax+rax+00h]
0x180040f7c  mov     rsi, rax
0x180040f7f  test    rax, rax
0x180040f82  jz      loc_180041009
0x180040f88  mov     dword ptr [rax+20h], 11h
0x180040f8f  mov     r9, rax; lpOverlapped
0x180040f92  mov     rcx, [rdi+80h]
0x180040f99  xor     r8d, r8d; dwCompletionKey
0x180040f9c  mov     [rax+30h], rcx
0x180040fa0  xor     edx, edx; dwNumberOfBytesTransferred
0x180040fa2  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180040fa9  call    cs:__imp_PostQueuedCompletionStatus
0x180040fb0  nop     dword ptr [rax+rax+00h]
0x180040fb5  test    eax, eax
0x180040fb7  jnz     loc_180041044
0x180040fbd  mov     rbx, cs:WPP_GLOBAL_Control
0x180040fc4  cmp     rbx, r12
0x180040fc7  jz      short loc_180040FF8
0x180040fc9  test    [rbx+1Ch], r15d
0x180040fcd  jz      short loc_180040FF8
0x180040fcf  cmp     byte ptr [rbx+19h], 2
0x180040fd3  jb      short loc_180040FF8
0x180040fd5  mov     rbx, [rbx+10h]
0x180040fd9  call    cs:__imp_GetLastError
0x180040fe0  nop     dword ptr [rax+rax+00h]
0x180040fe5  mov     edx, 0D8h
0x180040fea  mov     r8, r13
0x180040fed  mov     r9d, eax
0x180040ff0  mov     rcx, rbx
0x180040ff3  call    WPP_SF_d
0x180040ff8  mov     rcx, rsi; hMem
0x180040ffb  call    cs:__imp_LocalFree
0x180041002  nop     dword ptr [rax+rax+00h]
0x180041007  jmp     short loc_180041044
0x180041009  mov     rbx, cs:WPP_GLOBAL_Control
0x180041010  cmp     rbx, r12
0x180041013  jz      short loc_180041044
0x180041015  test    [rbx+1Ch], r15d
0x180041019  jz      short loc_180041044
0x18004101b  cmp     byte ptr [rbx+19h], 2
0x18004101f  jb      short loc_180041044
0x180041021  mov     rbx, [rbx+10h]
0x180041025  call    cs:__imp_GetLastError
0x18004102c  nop     dword ptr [rax+rax+00h]
0x180041031  mov     edx, 0D9h
0x180041036  mov     r8, r13
0x180041039  mov     r9d, eax
0x18004103c  mov     rcx, rbx
0x18004103f  call    WPP_SF_d
0x180041044  mov     rcx, [rdi+50h]; hObject
0x180041048  test    rcx, rcx
0x18004104b  jz      short loc_18004105D
0x18004104d  call    cs:__imp_CloseHandle
0x180041054  nop     dword ptr [rax+rax+00h]
0x180041059  mov     [rdi+50h], rbp
0x18004105d  mov     rcx, [rdi+68h]; hObject
0x180041061  test    rcx, rcx
0x180041064  jz      short loc_180041076
0x180041066  call    cs:__imp_CloseHandle
0x18004106d  nop     dword ptr [rax+rax+00h]
0x180041072  mov     [rdi+68h], rbp
0x180041076  mov     edx, 6
0x18004107b  lea     rcx, [rdi+20h]
0x18004107f  call    GetUserData
0x180041084  mov     esi, 800h
0x180041089  test    rax, rax
0x18004108c  jz      short loc_1800410B8
0x18004108e  cmp     dword ptr [rax+14h], 0C28h
0x180041095  jb      short loc_1800410B8
0x180041097  add     rax, 18h
0x18004109b  jz      short loc_1800410B8
0x18004109d  cmp     [rax+4], ebp
0x1800410a0  jbe     short loc_1800410B8
0x1800410a2  mov     r8d, esi
0x1800410a5  lea     rdx, [rax+8]
0x1800410a9  mov     [rdx], bpl
0x1800410ac  inc     rdx
0x1800410af  sub     r8, 1
0x1800410b3  jnz     short loc_1800410A9
0x1800410b5  mov     [rax+4], ebp
0x1800410b8  lea     rcx, [rdi+20h]
0x1800410bc  call    FreeUserData
0x1800410c1  mov     rcx, [rdi+390h]; hMem
0x1800410c8  test    rcx, rcx
0x1800410cb  jz      short loc_1800410E0
0x1800410cd  call    cs:__imp_LocalFree
0x1800410d4  nop     dword ptr [rax+rax+00h]
0x1800410d9  mov     [rdi+390h], rbp
0x1800410e0  lea     rcx, [rdi+30h]
0x1800410e4  call    FreeNotifierList
0x1800410e9  mov     rcx, [rdi+38h]
0x1800410ed  test    rcx, rcx
0x1800410f0  jz      short loc_180041122
0x1800410f2  cmp     [rdi+40h], ebp
0x1800410f5  jbe     short loc_180041116
0x1800410f7  mov     edx, ebp
0x1800410f9  mov     eax, edx
0x1800410fb  mov     r8, [rcx+rax*8]
0x1800410ff  test    r8, r8
0x180041102  jz      short loc_18004110F
0x180041104  mov     [r8+428h], rbp
0x18004110b  mov     rcx, [rdi+38h]; hMem
0x18004110f  inc     edx
0x180041111  cmp     edx, [rdi+40h]
0x180041114  jb      short loc_1800410F9
0x180041116  call    cs:__imp_LocalFree
0x18004111d  nop     dword ptr [rax+rax+00h]
0x180041122  mov     rcx, [rdi+60h]; hMem
0x180041126  test    rcx, rcx
0x180041129  jz      short loc_180041137
0x18004112b  call    cs:__imp_LocalFree
0x180041132  nop     dword ptr [rax+rax+00h]
0x180041137  mov     rcx, [rdi]
0x18004113a  test    rcx, rcx
0x18004113d  jz      short loc_18004114F
0x18004113f  mov     rax, [rdi+8]
0x180041143  test    rax, rax
0x180041146  jz      short loc_18004114F
0x180041148  mov     [rax], rcx
0x18004114b  mov     [rcx+8], rax
0x18004114f  mov     rcx, [rdi+368h]; hMem
0x180041156  test    rcx, rcx
0x180041159  jz      short loc_180041167
0x18004115b  call    cs:__imp_LocalFree
0x180041162  nop     dword ptr [rax+rax+00h]
0x180041167  mov     rcx, [rdi+378h]; hMem
0x18004116e  test    rcx, rcx
0x180041171  jz      short loc_18004117F
0x180041173  call    cs:__imp_LocalFree
0x18004117a  nop     dword ptr [rax+rax+00h]
0x18004117f  mov     rax, [rdi+398h]
0x180041186  test    rax, rax
0x180041189  jz      short loc_1800411C4
0x18004118b  cmp     [rax+4], ebp
0x18004118e  jbe     short loc_1800411AA
0x180041190  add     rax, 8
0x180041194  mov     [rax], bpl
0x180041197  inc     rax
0x18004119a  sub     rsi, 1
0x18004119e  jnz     short loc_180041194
0x1800411a0  mov     rax, [rdi+398h]
0x1800411a7  mov     [rax+4], ebp
0x1800411aa  mov     rcx, [rdi+398h]; hMem
0x1800411b1  call    cs:__imp_LocalFree
0x1800411b8  nop     dword ptr [rax+rax+00h]
0x1800411bd  mov     [rdi+398h], rbp
0x1800411c4  mov     rcx, [rdi+3A0h]; pbInput
0x1800411cb  test    rcx, rcx
0x1800411ce  jz      short loc_1800411DC
0x1800411d0  call    VpnFreeNgcTicketContext
0x1800411d5  mov     [rdi+3A0h], rbp
0x1800411dc  mov     rcx, [rdi+3A8h]; pbInput
0x1800411e3  test    rcx, rcx
0x1800411e6  jz      short loc_1800411F4
0x1800411e8  call    VpnFreeNgcTicketContext
0x1800411ed  mov     [rdi+3A8h], rbp
0x1800411f4  mov     rcx, [rdi+3B0h]; hMem
0x1800411fb  test    rcx, rcx
0x1800411fe  jz      short loc_180041219
0x180041200  call    cs:__imp_LocalFree
0x180041207  nop     dword ptr [rax+rax+00h]
0x18004120c  mov     [rdi+3B0h], rbp
0x180041213  mov     [rdi+3B8h], ebp
0x180041219  mov     rcx, rdi; hMem
0x18004121c  call    cs:__imp_LocalFree
0x180041223  nop     dword ptr [rax+rax+00h]
0x180041228  mov     rcx, cs:WPP_GLOBAL_Control
0x18004122f  cmp     rcx, r12
0x180041232  jz      short loc_180041251
0x180041234  test    [rcx+1Ch], r15d
0x180041238  jz      short loc_180041251
0x18004123a  cmp     byte ptr [rcx+19h], 6
0x18004123e  jb      short loc_180041251
0x180041240  mov     rcx, [rcx+10h]
0x180041244  mov     edx, 0DAh
0x180041249  mov     r8, r13
0x18004124c  call    WPP_SF_
0x180041251  mov     rcx, [rsp+0C8h+var_38]
0x180041259  xor     rcx, rsp; StackCookie
0x18004125c  call    __security_check_cookie
0x180041261  lea     r11, [rsp+0C8h+var_28]
0x180041269  mov     rbx, [r11+38h]
0x18004126d  mov     rbp, [r11+40h]
0x180041271  mov     rsp, r11
0x180041274  pop     r15
0x180041276  pop     r13
0x180041278  pop     r12
0x18004127a  pop     rdi
0x18004127b  pop     rsi
0x18004127c  retn
```
