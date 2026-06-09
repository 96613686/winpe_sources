# ConnectCompleteRequest

- ea: `0x180015b10`
- end: `0x180015e89`
- name: `ConnectCompleteRequest`
- size: `889`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x180005cf8`
- `0x18000c424`
- `0x180015b10`
- `0x180020094`
- `0x18003a004`
- `0x18003de8c`
- `0x180041284`
- `0x1800499f0`
- `0x1800e8e96`
- `0x1800eb010`

## import_xrefs

- `msvcrt!_stricmp` at `0x180015bc3`
- `msvcrt!_stricmp` at `0x180015bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015cdd`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180015ccd`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180015ccd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180015c4b`

## pseudocode

```c
void __fastcall ConnectCompleteRequest(const char *a1, __int64 a2, unsigned int *a3)
{
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  DWORD LastError; // eax
  unsigned int v12; // eax
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // [rsp+60h] [rbp+8h] BYREF

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 498, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v16 = 0;
  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 6) != 2 )
    {
      if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(v5[1].Blink) & 0x2000) != 0
        && BYTE1(v5[1].Blink) >= 4u )
      {
        WPP_SF_q(v5[1].Flink, 503, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *(_QWORD *)a1);
      }
      if ( !_stricmp(a1 + 56, "NULL") )
      {
        SetPortConnState(v7, v6, a1, 2);
        *a3 = 0;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 504, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
        }
        return;
      }
      FreeDeviceList(a1);
      v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*((_QWORD *)a1 + 6) + 64LL))(
             *((_QWORD *)a1 + 27),
             0,
             &v16);
      if ( !v8 )
      {
        *((_DWORD *)a1 + 130) = GetTickCount();
        SetPortConnState(v10, v9, a1, 2);
        v8 = AllocBundle(a1);
        if ( !v8 )
        {
          MapCookieToEndpoint(a1, v16);
          memset_0((void *)(a1 + 732), 0, 0x9Cu);
          memset_0((void *)(a1 + 888), 0, 0x9Cu);
          if ( !*(_BYTE *)ReceiveBuffers && !PostQueuedCompletionStatus(hIoCompletionPort, 0, 0, &RO_PostRecvPkt) )
          {
            LastError = GetLastError();
            if ( LastError != 997
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 505, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, LastError);
            }
            v8 = 0;
          }
          if ( *(_WORD *)(*((_QWORD *)a1 + 154) + 96LL) == 9 )
          {
            v12 = DwSaveIpSecInfo((__int64)a1);
            if ( v12
              && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
              && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 506, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v12);
            }
            v8 = 0;
          }
        }
      }
      *a3 = v8;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control[1].Flink,
            507,
            (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
            (_DWORD)a1 + 8,
            v8);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(v13[1].Blink) & 0x2000) != 0
          && BYTE1(v13[1].Blink) >= 6u )
        {
          v14 = 508;
          v15 = v8;
LABEL_57:
          WPP_SF_d(v13[1].Flink, v14, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v15);
          return;
        }
      }
      return;
    }
    if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v5[1].Blink) & 0x2000) != 0
      && BYTE1(v5[1].Blink) >= 2u )
    {
      WPP_SF_q(v5[1].Flink, 499, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, *(_QWORD *)a1);
    }
  }
  else if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && (HIDWORD(v5[1].Blink) & 0x2000) != 0
         && BYTE1(v5[1].Blink) >= 2u )
  {
    WPP_SF_(v5[1].Flink, 500, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  *a3 = 615;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 501, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v13 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(v13[1].Blink) & 0x2000) != 0
      && BYTE1(v13[1].Blink) >= 6u )
    {
      v14 = 502;
      v15 = 615;
      goto LABEL_57;
    }
  }
}

```

## disassembly

```asm
0x180015b10  mov     [rsp+arg_8], rbx
0x180015b15  mov     [rsp+arg_10], rbp
0x180015b1a  push    rsi
0x180015b1b  push    rdi
0x180015b1c  push    r13
0x180015b1e  push    r14
0x180015b20  push    r15
0x180015b22  sub     rsp, 30h
0x180015b26  mov     rsi, r8
0x180015b29  mov     rbx, rcx
0x180015b2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b33  lea     r15, WPP_GLOBAL_Control
0x180015b3a  lea     r13, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180015b41  mov     dil, 6
0x180015b44  mov     r14d, 2000h
0x180015b4a  cmp     rcx, r15
0x180015b4d  jz      short loc_180015B73
0x180015b4f  test    [rcx+1Ch], r14d
0x180015b53  jz      short loc_180015B73
0x180015b55  cmp     [rcx+19h], dil
0x180015b59  jb      short loc_180015B73
0x180015b5b  mov     rcx, [rcx+10h]
0x180015b5f  mov     edx, 1F2h
0x180015b64  mov     r8, r13
0x180015b67  call    WPP_SF_
0x180015b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b73  mov     [rsp+58h+arg_0], 0
0x180015b7c  mov     ebp, 2
0x180015b81  test    rbx, rbx
0x180015b84  jz      loc_180015DF5
0x180015b8a  cmp     [rbx+18h], ebp
0x180015b8d  jz      loc_180015DCE
0x180015b93  cmp     rcx, r15
0x180015b96  jz      short loc_180015BB8
0x180015b98  test    [rcx+1Ch], r14d
0x180015b9c  jz      short loc_180015BB8
0x180015b9e  cmp     byte ptr [rcx+19h], 4
0x180015ba2  jb      short loc_180015BB8
0x180015ba4  mov     r9, [rbx]
0x180015ba7  mov     edx, 1F7h
0x180015bac  mov     rcx, [rcx+10h]
0x180015bb0  mov     r8, r13
0x180015bb3  call    WPP_SF_q
0x180015bb8  lea     rcx, [rbx+38h]; String1
0x180015bbc  lea     rdx, aNull_1; "NULL"
0x180015bc3  call    cs:__imp__stricmp
0x180015bca  nop     dword ptr [rax+rax+00h]
0x180015bcf  test    eax, eax
0x180015bd1  jnz     short loc_180015C1E
0x180015bd3  mov     r9d, ebp
0x180015bd6  mov     r8, rbx
0x180015bd9  call    SetPortConnState
0x180015bde  mov     dword ptr [rsi], 0
0x180015be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180015beb  cmp     rcx, r15
0x180015bee  jz      loc_180015E71
0x180015bf4  test    [rcx+1Ch], r14d
0x180015bf8  jz      loc_180015E71
0x180015bfe  cmp     [rcx+19h], dil
0x180015c02  jb      loc_180015E71
0x180015c08  mov     rcx, [rcx+10h]
0x180015c0c  mov     edx, 1F8h
0x180015c11  mov     r8, r13
0x180015c14  call    WPP_SF_
0x180015c19  jmp     loc_180015E71
0x180015c1e  mov     rcx, rbx
0x180015c21  call    FreeDeviceList
0x180015c26  mov     rax, [rbx+30h]
0x180015c2a  lea     r8, [rsp+58h+arg_0]
0x180015c2f  mov     rcx, [rbx+0D8h]
0x180015c36  xor     edx, edx
0x180015c38  mov     rax, [rax+40h]
0x180015c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c41  mov     edi, eax
0x180015c43  test    eax, eax
0x180015c45  jnz     loc_180015D66
0x180015c4b  call    cs:__imp_GetTickCount
0x180015c52  nop     dword ptr [rax+rax+00h]
0x180015c57  mov     r9d, ebp
0x180015c5a  mov     r8, rbx
0x180015c5d  mov     [rbx+208h], eax
0x180015c63  call    SetPortConnState
0x180015c68  mov     rcx, rbx
0x180015c6b  call    AllocBundle
0x180015c70  mov     edi, eax
0x180015c72  test    eax, eax
0x180015c74  jnz     loc_180015D66
0x180015c7a  mov     rdx, [rsp+58h+arg_0]
0x180015c7f  mov     rcx, rbx
0x180015c82  call    MapCookieToEndpoint
0x180015c87  mov     ebp, 9Ch
0x180015c8c  lea     rcx, [rbx+2DCh]; void *
0x180015c93  mov     r8d, ebp; Size
0x180015c96  xor     edx, edx; Val
0x180015c98  call    memset_0
0x180015c9d  lea     rcx, [rbx+378h]; void *
0x180015ca4  mov     r8d, ebp; Size
0x180015ca7  xor     edx, edx; Val
0x180015ca9  call    memset_0
0x180015cae  mov     rax, cs:ReceiveBuffers
0x180015cb5  cmp     [rax], dil
0x180015cb8  jnz     short loc_180015D1E
0x180015cba  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180015cc1  lea     r9, RO_PostRecvPkt; lpOverlapped
0x180015cc8  xor     r8d, r8d; dwCompletionKey
0x180015ccb  xor     edx, edx; dwNumberOfBytesTransferred
0x180015ccd  call    cs:__imp_PostQueuedCompletionStatus
0x180015cd4  nop     dword ptr [rax+rax+00h]
0x180015cd9  test    eax, eax
0x180015cdb  jnz     short loc_180015D1E
0x180015cdd  call    cs:__imp_GetLastError
0x180015ce4  nop     dword ptr [rax+rax+00h]
0x180015ce9  cmp     eax, 3E5h
0x180015cee  jz      short loc_180015D1C
0x180015cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015cf7  cmp     rcx, r15
0x180015cfa  jz      short loc_180015D1C
0x180015cfc  test    [rcx+1Ch], r14d
0x180015d00  jz      short loc_180015D1C
0x180015d02  cmp     byte ptr [rcx+19h], 2
0x180015d06  jb      short loc_180015D1C
0x180015d08  mov     rcx, [rcx+10h]
0x180015d0c  mov     edx, 1F9h
0x180015d11  mov     r9d, eax
0x180015d14  mov     r8, r13
0x180015d17  call    WPP_SF_d
0x180015d1c  xor     edi, edi
0x180015d1e  mov     rax, [rbx+4D0h]
0x180015d25  cmp     word ptr [rax+60h], 9
0x180015d2a  jnz     short loc_180015D66
0x180015d2c  mov     rcx, rbx
0x180015d2f  call    DwSaveIpSecInfo
0x180015d34  test    eax, eax
0x180015d36  jz      short loc_180015D64
0x180015d38  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d3f  cmp     rcx, r15
0x180015d42  jz      short loc_180015D64
0x180015d44  test    [rcx+1Ch], r14d
0x180015d48  jz      short loc_180015D64
0x180015d4a  cmp     byte ptr [rcx+19h], 2
0x180015d4e  jb      short loc_180015D64
0x180015d50  mov     rcx, [rcx+10h]
0x180015d54  mov     edx, 1FAh
0x180015d59  mov     r9d, eax
0x180015d5c  mov     r8, r13
0x180015d5f  call    WPP_SF_d
0x180015d64  xor     edi, edi
0x180015d66  mov     [rsi], edi
0x180015d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d6f  cmp     rcx, r15
0x180015d72  jz      loc_180015E71
0x180015d78  test    [rcx+1Ch], r14d
0x180015d7c  jz      short loc_180015DA4
0x180015d7e  cmp     byte ptr [rcx+19h], 4
0x180015d82  jb      short loc_180015DA4
0x180015d84  mov     rcx, [rcx+10h]
0x180015d88  lea     r9, [rbx+8]
0x180015d8c  mov     edx, 1FBh
0x180015d91  mov     [rsp+58h+var_38], edi
0x180015d95  mov     r8, r13
0x180015d98  call    WPP_SF_sd
0x180015d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180015da4  cmp     rcx, r15
0x180015da7  jz      loc_180015E71
0x180015dad  test    [rcx+1Ch], r14d
0x180015db1  jz      loc_180015E71
0x180015db7  cmp     byte ptr [rcx+19h], 6
0x180015dbb  jb      loc_180015E71
0x180015dc1  mov     edx, 1FCh
0x180015dc6  mov     r9d, edi
0x180015dc9  jmp     loc_180015E65
0x180015dce  cmp     rcx, r15
0x180015dd1  jz      short loc_180015E17
0x180015dd3  test    [rcx+1Ch], r14d
0x180015dd7  jz      short loc_180015E17
0x180015dd9  cmp     [rcx+19h], bpl
0x180015ddd  jb      short loc_180015E17
0x180015ddf  mov     r9, [rbx]
0x180015de2  mov     edx, 1F3h
0x180015de7  mov     rcx, [rcx+10h]
0x180015deb  mov     r8, r13
0x180015dee  call    WPP_SF_q
0x180015df3  jmp     short loc_180015E17
0x180015df5  cmp     rcx, r15
0x180015df8  jz      short loc_180015E17
0x180015dfa  test    [rcx+1Ch], r14d
0x180015dfe  jz      short loc_180015E17
0x180015e00  cmp     [rcx+19h], bpl
0x180015e04  jb      short loc_180015E17
0x180015e06  mov     rcx, [rcx+10h]
0x180015e0a  mov     edx, 1F4h
0x180015e0f  mov     r8, r13
0x180015e12  call    WPP_SF_
0x180015e17  mov     ebx, 267h
0x180015e1c  mov     [rsi], ebx
0x180015e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e25  cmp     rcx, r15
0x180015e28  jz      short loc_180015E71
0x180015e2a  test    [rcx+1Ch], r14d
0x180015e2e  jz      short loc_180015E4C
0x180015e30  cmp     [rcx+19h], bpl
0x180015e34  jb      short loc_180015E4C
0x180015e36  mov     rcx, [rcx+10h]
0x180015e3a  lea     edx, [rbx-72h]
0x180015e3d  mov     r8, r13
0x180015e40  call    WPP_SF_
0x180015e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e4c  cmp     rcx, r15
0x180015e4f  jz      short loc_180015E71
0x180015e51  test    [rcx+1Ch], r14d
0x180015e55  jz      short loc_180015E71
0x180015e57  cmp     [rcx+19h], dil
0x180015e5b  jb      short loc_180015E71
0x180015e5d  mov     edx, 1F6h
0x180015e62  mov     r9d, ebx
0x180015e65  mov     rcx, [rcx+10h]
0x180015e69  mov     r8, r13
0x180015e6c  call    WPP_SF_d
0x180015e71  mov     rbx, [rsp+58h+arg_8]
0x180015e76  mov     rbp, [rsp+58h+arg_10]
0x180015e7b  add     rsp, 30h
0x180015e7f  pop     r15
0x180015e81  pop     r14
0x180015e83  pop     r13
0x180015e85  pop     rdi
0x180015e86  pop     rsi
0x180015e87  retn
```
