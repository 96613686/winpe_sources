# InitiatePortDisconnection

- ea: `0x180012b00`
- end: `0x180012f1a`
- name: `InitiatePortDisconnection`
- size: `1050`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000cb80`
- `0x180013770`

## callees

- `0x18000d92c`
- `0x180012b00`
- `0x180023610`
- `0x180023a14`
- `0x180023e24`
- `0x18002619c`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180012bae`
- `msvcrt!_stricmp` at `0x180012bae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ebf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ebf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ed8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012c20`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180012c20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012c39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012c39`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012c9f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180012c9f`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180012e22`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180012e8e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180012e22`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDeallocateCall` at `0x180012e8e`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x180012d2a`
- `ext-ms-win-ras-tapi32-l1-1-1!lineSetStatusMessages` at `0x180012d2a`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x180012c8d`
- `ext-ms-win-ras-tapi32-l1-1-1!lineClose` at `0x180012c8d`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180012ce4`
- `ext-ms-win-ras-tapi32-l1-1-1!lineOpenA` at `0x180012ce4`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDrop` at `0x180012d6c`
- `ext-ms-win-ras-tapi32-l1-1-1!lineDrop` at `0x180012d6c`

## string_xrefs

- `0x180012d08`: `InitiatePortDisconnection: %s. lineOpen Failed. 0x%x`
- `0x180012e42`: `InitiatePortDisconnection: %s. linedrop completed sync.`

## pseudocode

```c
__int64 __fastcall InitiatePortDisconnection(__int64 a1)
{
  LONG *v2; // rsi
  int v3; // edx
  unsigned int **v4; // rdi
  unsigned int *v5; // rcx
  __int64 v6; // rax
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  void *v10; // rcx
  HCALL v11; // ecx
  __int64 v12; // rcx
  unsigned int *v13; // rcx
  unsigned int v14; // r8d
  int v15; // eax
  unsigned int v16; // edi
  int v17; // ebp
  unsigned int *v18; // rax
  __int64 v19; // rcx
  unsigned int *v20; // rax
  __int64 v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  _QWORD OutBuffer[2]; // [rsp+50h] [rbp-68h] BYREF
  DWORD BytesReturned; // [rsp+60h] [rbp-58h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-50h] BYREF

  v2 = (LONG *)(a1 + 252);
  *(_DWORD *)(a1 + 252) = -1;
  RasTapiTrace("InitiatePortDisconnection: %s");
  v3 = *(_DWORD *)(a1 + 1104);
  v4 = (unsigned int **)(a1 + 216);
  if ( (v3 & 2) != 0 )
  {
    v5 = *v4;
    v6 = *((_QWORD *)*v4 + 5);
    *(_DWORD *)(a1 + 1104) = v3 & 0xFFFFFFFD;
    if ( *((_QWORD *)v5 + 5) )
      --*(_DWORD *)(v6 + 16);
    --g_dwTotalDialIn;
    RasTapiTrace("%s InClients=%d, TotalDialInClients=%d");
  }
  if ( !_stricmp((const char *)(a1 + 64), "MODEM") )
  {
    if ( *(_QWORD *)(a1 + 880) != -1 )
    {
      OutBuffer[0] = *(_QWORD *)(a1 + 880);
      BytesReturned = 0;
      OutBuffer[1] = 0;
      memset(&Overlapped, 0, sizeof(Overlapped));
      DeviceIoControl(g_hAsyMac, 0x120004u, OutBuffer, 0x10u, OutBuffer, 0x10u, &BytesReturned, &Overlapped);
      *(_QWORD *)(a1 + 880) = -1;
    }
    v10 = *(void **)(a1 + 888);
    if ( v10 != (void *)-1LL )
    {
      CloseHandle(v10);
      *(_QWORD *)(a1 + 888) = -1;
    }
  }
  v11 = *(_DWORD *)(a1 + 232);
  if ( v11 == -1 )
  {
    RasTapiTrace("InitiatePortDisconnect: Invalid CallHandle - hIOPort %p, State 0x%x");
    if ( !(*v4)[9] )
    {
      RasTapiTrace("InitiatePortDisconnect: Hammering LineClosed!");
      v12 = (*v4)[3];
      if ( (*v4)[15] )
        RasLineClose(v12);
      else
        lineClose(v12);
      Sleep(0x1Eu);
      v13 = *v4;
      v14 = (*v4)[14];
      if ( (*v4)[15] )
        v15 = RasLineOpen(v13[2], 4, v14, (__int64)v13, (__int64)(*v4 + 3));
      else
        v15 = lineOpenA(RasLine, v13[2], *v4 + 3, v13[6], v13[7], (DWORD_PTR)v13, 4u, v14, 0);
      if ( v15 )
        RasTapiTrace("InitiatePortDisconnection: %s. lineOpen Failed. 0x%x");
      if ( !(*v4)[15] )
        lineSetStatusMessages((*v4)[3], 2u, 0);
      goto LABEL_22;
    }
    v16 = 0;
    RasTapiTrace("InitiatePortDisconnect: Possible lost port: %p");
    goto LABEL_43;
  }
  if ( (*v4)[15] )
  {
    v17 = RasLineDrop(v11, v7, v8, v9, (__int64)v2);
  }
  else
  {
    v17 = 0;
    *v2 = lineDrop(v11, 0, 0);
  }
  if ( (*v4)[15] )
  {
    if ( !v17 )
      goto LABEL_29;
LABEL_32:
    RasTapiTrace("InitiatePortDisconnection: Error issuing lineDrop for %s. RequestId = 0x%x, Status = 0x%x");
    RasTapiTrace("InitiatePortDisconnection: Changing state for %s from %d -> %d");
    v18 = *v4;
    v19 = *(unsigned int *)(a1 + 232);
    *(_DWORD *)(a1 + 56) = 1;
    *v2 = -1;
    if ( v18[15] )
      RasLineCloseCall(v19);
    else
      lineDeallocateCall(v19);
    RasTapiTrace(" ");
    v16 = 628;
    goto LABEL_43;
  }
  if ( (unsigned int)*v2 > 0x80000000 )
    goto LABEL_32;
LABEL_29:
  if ( *v2 )
  {
    RasTapiTrace("InitiatePortDisconnection: Changing state for %s from %d -> %d, id=0x%x");
    *(_DWORD *)(a1 + 1104) |= 4u;
    *(_DWORD *)(a1 + 56) = 5;
    RasTapiTrace(" ");
  }
  else
  {
    RasTapiTrace("InitiatePortDisconnection: %s. linedrop completed sync.");
    *v2 = -1;
    if ( *(_DWORD *)(a1 + 1100) )
    {
      RasTapiTrace("InitiatePortDisconnection: Changing state for %s from %d -> %d");
      v20 = *v4;
      v21 = *(unsigned int *)(a1 + 232);
      *(_DWORD *)(a1 + 1100) = 0;
      *(_DWORD *)(a1 + 56) = 1;
      if ( v20[15] )
        RasLineCloseCall(v21);
      else
        lineDeallocateCall(v21);
      *(_DWORD *)(a1 + 232) = -1;
LABEL_22:
      RasTapiTrace(" ");
      v16 = 0;
      goto LABEL_43;
    }
    *(_DWORD *)(a1 + 56) = 5;
  }
  v16 = 600;
LABEL_43:
  v22 = *(void **)(a1 + 1112);
  if ( v22 )
  {
    LocalFree(v22);
    *(_QWORD *)(a1 + 1112) = 0;
  }
  v23 = *(void **)(a1 + 864);
  if ( v23 )
  {
    LocalFree(v23);
    *(_QWORD *)(a1 + 864) = 0;
    *(_DWORD *)(a1 + 872) = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x180012b00  mov     [rsp+arg_8], rbx
0x180012b05  mov     [rsp+arg_10], rbp
0x180012b0a  push    rsi
0x180012b0b  push    rdi
0x180012b0c  push    r12
0x180012b0e  push    r14
0x180012b10  push    r15
0x180012b12  sub     rsp, 90h
0x180012b19  mov     rax, cs:__security_cookie
0x180012b20  xor     rax, rsp
0x180012b23  mov     [rsp+0B8h+var_30], rax
0x180012b2b  lea     r14, [rcx+18h]
0x180012b2f  mov     rbx, rcx
0x180012b32  lea     rsi, [rcx+0FCh]
0x180012b39  or      r12d, 0FFFFFFFFh
0x180012b3d  mov     rdx, r14
0x180012b40  mov     [rsi], r12d
0x180012b43  lea     rcx, aInitiateportdi_0; "InitiatePortDisconnection: %s"
0x180012b4a  call    RasTapiTrace
0x180012b4f  mov     edx, [rbx+450h]
0x180012b55  lea     rdi, [rbx+0D8h]
0x180012b5c  xor     r15d, r15d
0x180012b5f  test    dl, 2
0x180012b62  jz      short loc_180012BA3
0x180012b64  mov     rcx, [rdi]
0x180012b67  and     edx, 0FFFFFFFDh
0x180012b6a  mov     rax, [rcx+28h]
0x180012b6e  mov     [rbx+450h], edx
0x180012b74  cmp     [rcx+28h], r15
0x180012b78  jz      short loc_180012B7E
0x180012b7a  add     [rax+10h], r12d
0x180012b7e  mov     r9d, cs:g_dwTotalDialIn
0x180012b85  lea     rdx, [rbx+50h]
0x180012b89  mov     r8d, [rax+10h]
0x180012b8d  lea     rcx, aSInclientsDTot; "%s InClients=%d, TotalDialInClients=%d"
0x180012b94  add     r9d, r12d
0x180012b97  mov     cs:g_dwTotalDialIn, r9d
0x180012b9e  call    RasTapiTrace
0x180012ba3  lea     rcx, [rbx+40h]; String1
0x180012ba7  lea     rdx, aModem; "MODEM"
0x180012bae  call    cs:__imp__stricmp
0x180012bb4  test    eax, eax
0x180012bb6  jnz     loc_180012C46
0x180012bbc  mov     rax, [rbx+370h]
0x180012bc3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180012bc7  cmp     rax, rbp
0x180012bca  jz      short loc_180012C2D
0x180012bcc  mov     rcx, cs:g_hAsyMac; hDevice
0x180012bd3  lea     r9d, [rbp+11h]; nInBufferSize
0x180012bd7  mov     [rsp+0B8h+OutBuffer], rax
0x180012bdc  lea     r8, [rsp+0B8h+OutBuffer]; lpInBuffer
0x180012be1  xorps   xmm0, xmm0
0x180012be4  mov     [rsp+0B8h+BytesReturned], r15d
0x180012be9  lea     rax, [rsp+0B8h+Overlapped]
0x180012bee  mov     [rsp+0B8h+var_60], r15
0x180012bf3  mov     [rsp+0B8h+lpOverlapped], rax; lpOverlapped
0x180012bf8  mov     edx, 120004h; dwIoControlCode
0x180012bfd  lea     rax, [rsp+0B8h+BytesReturned]
0x180012c02  mov     [rsp+0B8h+lpBytesReturned], rax; lpBytesReturned
0x180012c07  lea     rax, [rsp+0B8h+OutBuffer]
0x180012c0c  mov     [rsp+0B8h+nOutBufferSize], r9d; nOutBufferSize
0x180012c11  mov     [rsp+0B8h+lpOutBuffer], rax; lpOutBuffer
0x180012c16  movups  xmmword ptr [rsp+0B8h+Overlapped.Internal], xmm0
0x180012c1b  movups  xmmword ptr [rsp+0B8h+Overlapped.10h], xmm0
0x180012c20  call    cs:__imp_DeviceIoControl
0x180012c26  mov     [rbx+370h], rbp
0x180012c2d  mov     rcx, [rbx+378h]; hObject
0x180012c34  cmp     rcx, rbp
0x180012c37  jz      short loc_180012C46
0x180012c39  call    cs:__imp_CloseHandle
0x180012c3f  mov     [rbx+378h], rbp
0x180012c46  mov     ecx, [rbx+0E8h]; hCall
0x180012c4c  cmp     ecx, r12d
0x180012c4f  jnz     loc_180012D5B
0x180012c55  mov     r8d, [rbx+38h]
0x180012c59  lea     rcx, aInitiateportdi_1; "InitiatePortDisconnect: Invalid CallHan"...
0x180012c60  mov     rdx, rbx
0x180012c63  call    RasTapiTrace
0x180012c68  mov     rax, [rdi]
0x180012c6b  cmp     [rax+24h], r15d
0x180012c6f  jnz     loc_180012D44
0x180012c75  lea     rcx, aInitiateportdi_6; "InitiatePortDisconnect: Hammering LineC"...
0x180012c7c  call    RasTapiTrace
0x180012c81  mov     rax, [rdi]
0x180012c84  mov     ecx, [rax+0Ch]; hLine
0x180012c87  cmp     [rax+3Ch], r15d
0x180012c8b  jnz     short loc_180012C95
0x180012c8d  call    cs:__imp_lineClose
0x180012c93  jmp     short loc_180012C9A
0x180012c95  call    RasLineClose
0x180012c9a  mov     ecx, 1Eh; dwMilliseconds
0x180012c9f  call    cs:__imp_Sleep
0x180012ca5  mov     rcx, [rdi]
0x180012ca8  lea     rdx, [rcx+0Ch]
0x180012cac  mov     r8d, [rcx+38h]
0x180012cb0  cmp     [rcx+3Ch], r15d
0x180012cb4  jnz     short loc_180012CEC
0x180012cb6  mov     eax, [rcx+1Ch]
0x180012cb9  mov     r9d, [rcx+18h]; dwAPIVersion
0x180012cbd  mov     [rsp+0B8h+lpCallParams], r15; lpCallParams
0x180012cc2  mov     dword ptr [rsp+0B8h+lpOverlapped], r8d; dwMediaModes
0x180012cc7  mov     r8, rdx; lphLine
0x180012cca  mov     edx, [rcx+8]; dwDeviceID
0x180012ccd  mov     dword ptr [rsp+0B8h+lpBytesReturned], 4; dwPrivileges
0x180012cd5  mov     qword ptr [rsp+0B8h+nOutBufferSize], rcx; dwCallbackInstance
0x180012cda  mov     ecx, cs:RasLine; hLineApp
0x180012ce0  mov     dword ptr [rsp+0B8h+lpOutBuffer], eax; dwExtVersion
0x180012ce4  call    cs:__imp_lineOpenA
0x180012cea  jmp     short loc_180012D01
0x180012cec  mov     [rsp+0B8h+lpOutBuffer], rdx
0x180012cf1  mov     r9, rcx
0x180012cf4  mov     ecx, [rcx+8]
0x180012cf7  mov     edx, 4
0x180012cfc  call    RasLineOpen
0x180012d01  test    eax, eax
0x180012d03  jz      short loc_180012D17
0x180012d05  mov     r8d, eax
0x180012d08  lea     rcx, aInitiateportdi; "InitiatePortDisconnection: %s. lineOpen"...
0x180012d0f  mov     rdx, r14
0x180012d12  call    RasTapiTrace
0x180012d17  mov     rcx, [rdi]
0x180012d1a  cmp     [rcx+3Ch], r15d
0x180012d1e  jnz     short loc_180012D30
0x180012d20  mov     ecx, [rcx+0Ch]; hLine
0x180012d23  xor     r8d, r8d; dwAddressStates
0x180012d26  lea     edx, [r8+2]; dwLineStates
0x180012d2a  call    cs:__imp_lineSetStatusMessages
0x180012d30  lea     rcx, asc_18002C0B8; " "
0x180012d37  call    RasTapiTrace
0x180012d3c  mov     edi, r15d
0x180012d3f  jmp     loc_180012EB3
0x180012d44  mov     rdx, rbx
0x180012d47  lea     rcx, aInitiateportdi_7; "InitiatePortDisconnect: Possible lost p"...
0x180012d4e  mov     edi, r15d
0x180012d51  call    RasTapiTrace
0x180012d56  jmp     loc_180012EB3
0x180012d5b  mov     rax, [rdi]
0x180012d5e  cmp     [rax+3Ch], r15d
0x180012d62  jnz     short loc_180012D76
0x180012d64  xor     r8d, r8d; dwSize
0x180012d67  xor     edx, edx; lpsUserUserInfo
0x180012d69  mov     ebp, r15d
0x180012d6c  call    cs:__imp_lineDrop
0x180012d72  mov     [rsi], eax
0x180012d74  jmp     short loc_180012D82
0x180012d76  mov     [rsp+0B8h+lpOutBuffer], rsi
0x180012d7b  call    RasLineDrop
0x180012d80  mov     ebp, eax
0x180012d82  mov     rcx, [rdi]
0x180012d85  cmp     [rcx+3Ch], r15d
0x180012d89  jnz     short loc_180012DD9
0x180012d8b  cmp     dword ptr [rsi], 80000000h
0x180012d91  ja      short loc_180012DDD
0x180012d93  mov     eax, [rsi]
0x180012d95  mov     rdx, r14
0x180012d98  test    eax, eax
0x180012d9a  jz      loc_180012E42
0x180012da0  mov     r8d, [rbx+38h]
0x180012da4  lea     rcx, aInitiateportdi_2; "InitiatePortDisconnection: Changing sta"...
0x180012dab  mov     r9d, 5
0x180012db1  mov     dword ptr [rsp+0B8h+lpOutBuffer], eax
0x180012db5  call    RasTapiTrace
0x180012dba  or      dword ptr [rbx+450h], 4
0x180012dc1  lea     rcx, asc_18002C0B8; " "
0x180012dc8  mov     dword ptr [rbx+38h], 5
0x180012dcf  call    RasTapiTrace
0x180012dd4  jmp     loc_180012EAE
0x180012dd9  test    ebp, ebp
0x180012ddb  jz      short loc_180012D93
0x180012ddd  mov     r8d, [rsi]
0x180012de0  lea     rcx, aInitiateportdi_3; "InitiatePortDisconnection: Error issuin"...
0x180012de7  mov     r9d, ebp
0x180012dea  mov     rdx, r14
0x180012ded  call    RasTapiTrace
0x180012df2  mov     r8d, [rbx+38h]
0x180012df6  lea     rcx, aInitiateportdi_5; "InitiatePortDisconnection: Changing sta"...
0x180012dfd  mov     ebp, 1
0x180012e02  mov     rdx, r14
0x180012e05  mov     r9d, ebp
0x180012e08  call    RasTapiTrace
0x180012e0d  mov     rax, [rdi]
0x180012e10  mov     ecx, [rbx+0E8h]; hCall
0x180012e16  mov     [rbx+38h], ebp
0x180012e19  mov     [rsi], r12d
0x180012e1c  cmp     [rax+3Ch], r15d
0x180012e20  jnz     short loc_180012E2A
0x180012e22  call    cs:__imp_lineDeallocateCall
0x180012e28  jmp     short loc_180012E2F
0x180012e2a  call    RasLineCloseCall
0x180012e2f  lea     rcx, asc_18002C0B8; " "
0x180012e36  call    RasTapiTrace
0x180012e3b  mov     edi, 274h
0x180012e40  jmp     short loc_180012EB3
0x180012e42  lea     rcx, aInitiateportdi_4; "InitiatePortDisconnection: %s. linedrop"...
0x180012e49  call    RasTapiTrace
0x180012e4e  mov     [rsi], r12d
0x180012e51  cmp     [rbx+44Ch], r15d
0x180012e58  jz      short loc_180012EA7
0x180012e5a  mov     r8d, [rbx+38h]
0x180012e5e  lea     rcx, aInitiateportdi_5; "InitiatePortDisconnection: Changing sta"...
0x180012e65  mov     ebp, 1
0x180012e6a  mov     rdx, r14
0x180012e6d  mov     r9d, ebp
0x180012e70  call    RasTapiTrace
0x180012e75  mov     rax, [rdi]
0x180012e78  mov     ecx, [rbx+0E8h]; hCall
0x180012e7e  mov     [rbx+44Ch], r15d
0x180012e85  mov     [rbx+38h], ebp
0x180012e88  cmp     [rax+3Ch], r15d
0x180012e8c  jnz     short loc_180012E96
0x180012e8e  call    cs:__imp_lineDeallocateCall
0x180012e94  jmp     short loc_180012E9B
0x180012e96  call    RasLineCloseCall
0x180012e9b  mov     [rbx+0E8h], r12d
0x180012ea2  jmp     loc_180012D30
0x180012ea7  mov     dword ptr [rbx+38h], 5
0x180012eae  mov     edi, 258h
0x180012eb3  mov     rcx, [rbx+458h]; hMem
0x180012eba  test    rcx, rcx
0x180012ebd  jz      short loc_180012ECC
0x180012ebf  call    cs:__imp_LocalFree
0x180012ec5  mov     [rbx+458h], r15
0x180012ecc  mov     rcx, [rbx+360h]; hMem
0x180012ed3  test    rcx, rcx
0x180012ed6  jz      short loc_180012EEC
0x180012ed8  call    cs:__imp_LocalFree
0x180012ede  mov     [rbx+360h], r15
0x180012ee5  mov     [rbx+368h], r15d
0x180012eec  mov     eax, edi
0x180012eee  mov     rcx, [rsp+0B8h+var_30]
0x180012ef6  xor     rcx, rsp; StackCookie
0x180012ef9  call    __security_check_cookie
0x180012efe  lea     r11, [rsp+0B8h+var_28]
0x180012f06  mov     rbx, [r11+38h]
0x180012f0a  mov     rbp, [r11+40h]
0x180012f0e  mov     rsp, r11
0x180012f11  pop     r15
0x180012f13  pop     r14
0x180012f15  pop     r12
0x180012f17  pop     rdi
0x180012f18  pop     rsi
0x180012f19  retn
```
