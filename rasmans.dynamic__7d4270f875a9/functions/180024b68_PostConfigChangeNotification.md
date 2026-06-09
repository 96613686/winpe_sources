# PostConfigChangeNotification

- ea: `0x180024b68`
- end: `0x180024dd0`
- name: `PostConfigChangeNotification`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c940`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c424`
- `0x180024b68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024bd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024d35`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180024d25`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180024d25`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024c27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024bc1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024c27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024c4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024d86`

## pseudocode

```c
__int64 __fastcall PostConfigChangeNotification(_OWORD *a1)
{
  struct _OVERLAPPED *v2; // rdi
  DWORD v3; // eax
  DWORD v4; // ebx
  struct _LIST_ENTRY *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  HLOCAL v8; // rax
  void *v9; // rsi
  _OWORD *v10; // rcx
  _OWORD *v11; // rax
  __int64 v12; // rdx
  __int128 v13; // xmm1
  HANDLE v14; // rcx
  DWORD LastError; // eax

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1087, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids);
  }
  v2 = (struct _OVERLAPPED *)LocalAlloc(0x40u, 0x38u);
  if ( v2 )
  {
    v8 = LocalAlloc(0x40u, 0x1D8u);
    v9 = v8;
    if ( v8 )
    {
      v4 = 0;
      v10 = v8;
      v11 = a1;
      v12 = 3;
      do
      {
        *v10 = *v11;
        v10[1] = v11[1];
        v10[2] = v11[2];
        v10[3] = v11[3];
        v10[4] = v11[4];
        v10[5] = v11[5];
        v10[6] = v11[6];
        v13 = v11[7];
        v11 += 8;
        v10[7] = v13;
        v10 += 8;
        --v12;
      }
      while ( v12 );
      *v10 = *v11;
      v10[1] = v11[1];
      v10[2] = v11[2];
      v10[3] = v11[3];
      v10[4] = v11[4];
      *((_QWORD *)v10 + 10) = *((_QWORD *)v11 + 10);
      v14 = hIoCompletionPort;
      LODWORD(v2[1].Internal) = 10;
      v2[1].InternalHigh = (ULONG_PTR)v9;
      if ( !PostQueuedCompletionStatus(v14, 0, 0, v2) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control[1].Flink,
            1090,
            (unsigned int)WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids,
            (_DWORD)a1 + 85,
            LastError);
        }
        LocalFree(v2);
        LocalFree(v9);
      }
      goto LABEL_24;
    }
    v4 = GetLastError();
    LocalFree(v2);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return v4;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      goto LABEL_25;
    v6 = 1089;
    v7 = v4;
LABEL_10:
    WPP_SF_d(v5[1].Flink, v6, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v7);
LABEL_24:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_25;
  }
  v3 = GetLastError();
  v4 = v3;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v4;
  if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v6 = 1088;
    v7 = v3;
    goto LABEL_10;
  }
LABEL_25:
  if ( v5 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v5[1].Blink) & 0x2000) != 0
    && BYTE1(v5[1].Blink) >= 6u )
  {
    WPP_SF_d(v5[1].Flink, 1091, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180024b68  push    rbx
0x180024b6a  push    rbp
0x180024b6b  push    rsi
0x180024b6c  push    rdi
0x180024b6d  push    r12
0x180024b6f  push    r14
0x180024b71  push    r15
0x180024b73  sub     rsp, 30h
0x180024b77  mov     rbp, rcx
0x180024b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b81  lea     r15, WPP_GLOBAL_Control
0x180024b88  lea     r12, WPP_9f1cd3acacaf3b9ac42339ff7101d974_Traceguids
0x180024b8f  mov     r14d, 2000h
0x180024b95  cmp     rcx, r15
0x180024b98  jz      short loc_180024BB7
0x180024b9a  test    [rcx+1Ch], r14d
0x180024b9e  jz      short loc_180024BB7
0x180024ba0  cmp     byte ptr [rcx+19h], 6
0x180024ba4  jb      short loc_180024BB7
0x180024ba6  mov     rcx, [rcx+10h]
0x180024baa  mov     edx, 43Fh
0x180024baf  mov     r8, r12
0x180024bb2  call    WPP_SF_
0x180024bb7  mov     edx, 38h ; '8'; uBytes
0x180024bbc  lea     ebx, [rdx+8]
0x180024bbf  mov     ecx, ebx; uFlags
0x180024bc1  call    cs:__imp_LocalAlloc
0x180024bc8  nop     dword ptr [rax+rax+00h]
0x180024bcd  mov     rdi, rax
0x180024bd0  test    rax, rax
0x180024bd3  jnz     short loc_180024C20
0x180024bd5  call    cs:__imp_GetLastError
0x180024bdc  nop     dword ptr [rax+rax+00h]
0x180024be1  mov     ebx, eax
0x180024be3  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bea  cmp     rcx, r15
0x180024bed  jz      loc_180024DBE
0x180024bf3  test    [rcx+1Ch], r14d
0x180024bf7  jz      loc_180024D99
0x180024bfd  cmp     byte ptr [rcx+19h], 2
0x180024c01  jb      loc_180024D99
0x180024c07  mov     edx, 440h
0x180024c0c  mov     r9d, eax
0x180024c0f  mov     rcx, [rcx+10h]
0x180024c13  mov     r8, r12
0x180024c16  call    WPP_SF_d
0x180024c1b  jmp     loc_180024D92
0x180024c20  mov     edx, 1D8h; uBytes
0x180024c25  mov     ecx, ebx; uFlags
0x180024c27  call    cs:__imp_LocalAlloc
0x180024c2e  nop     dword ptr [rax+rax+00h]
0x180024c33  mov     rsi, rax
0x180024c36  test    rax, rax
0x180024c39  jnz     short loc_180024C86
0x180024c3b  call    cs:__imp_GetLastError
0x180024c42  nop     dword ptr [rax+rax+00h]
0x180024c47  mov     rcx, rdi; hMem
0x180024c4a  mov     ebx, eax
0x180024c4c  call    cs:__imp_LocalFree
0x180024c53  nop     dword ptr [rax+rax+00h]
0x180024c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c5f  cmp     rcx, r15
0x180024c62  jz      loc_180024DBE
0x180024c68  test    [rcx+1Ch], r14d
0x180024c6c  jz      loc_180024D99
0x180024c72  cmp     byte ptr [rcx+19h], 2
0x180024c76  jb      loc_180024D99
0x180024c7c  mov     edx, 441h
0x180024c81  mov     r9d, ebx
0x180024c84  jmp     short loc_180024C0F
0x180024c86  xor     ebx, ebx
0x180024c88  mov     rcx, rsi
0x180024c8b  mov     rax, rbp
0x180024c8e  lea     edx, [rbx+3]
0x180024c91  lea     r8d, [rdx+7Dh]
0x180024c95  movups  xmm0, xmmword ptr [rax]
0x180024c98  movups  xmmword ptr [rcx], xmm0
0x180024c9b  movups  xmm1, xmmword ptr [rax+10h]
0x180024c9f  movups  xmmword ptr [rcx+10h], xmm1
0x180024ca3  movups  xmm0, xmmword ptr [rax+20h]
0x180024ca7  movups  xmmword ptr [rcx+20h], xmm0
0x180024cab  movups  xmm1, xmmword ptr [rax+30h]
0x180024caf  movups  xmmword ptr [rcx+30h], xmm1
0x180024cb3  movups  xmm0, xmmword ptr [rax+40h]
0x180024cb7  movups  xmmword ptr [rcx+40h], xmm0
0x180024cbb  movups  xmm1, xmmword ptr [rax+50h]
0x180024cbf  movups  xmmword ptr [rcx+50h], xmm1
0x180024cc3  movups  xmm0, xmmword ptr [rax+60h]
0x180024cc7  movups  xmmword ptr [rcx+60h], xmm0
0x180024ccb  movups  xmm1, xmmword ptr [rax+70h]
0x180024ccf  add     rax, r8
0x180024cd2  movups  xmmword ptr [rcx+70h], xmm1
0x180024cd6  add     rcx, r8
0x180024cd9  sub     rdx, 1; dwNumberOfBytesTransferred
0x180024cdd  jnz     short loc_180024C95
0x180024cdf  movups  xmm0, xmmword ptr [rax]
0x180024ce2  mov     r9, rdi; lpOverlapped
0x180024ce5  xor     r8d, r8d; dwCompletionKey
0x180024ce8  movups  xmmword ptr [rcx], xmm0
0x180024ceb  movups  xmm1, xmmword ptr [rax+10h]
0x180024cef  movups  xmmword ptr [rcx+10h], xmm1
0x180024cf3  movups  xmm0, xmmword ptr [rax+20h]
0x180024cf7  movups  xmmword ptr [rcx+20h], xmm0
0x180024cfb  movups  xmm1, xmmword ptr [rax+30h]
0x180024cff  movups  xmmword ptr [rcx+30h], xmm1
0x180024d03  movups  xmm0, xmmword ptr [rax+40h]
0x180024d07  movups  xmmword ptr [rcx+40h], xmm0
0x180024d0b  mov     rax, [rax+50h]
0x180024d0f  mov     [rcx+50h], rax
0x180024d13  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180024d1a  mov     dword ptr [rdi+20h], 0Ah
0x180024d21  mov     [rdi+28h], rsi
0x180024d25  call    cs:__imp_PostQueuedCompletionStatus
0x180024d2c  nop     dword ptr [rax+rax+00h]
0x180024d31  test    eax, eax
0x180024d33  jnz     short loc_180024D92
0x180024d35  call    cs:__imp_GetLastError
0x180024d3c  nop     dword ptr [rax+rax+00h]
0x180024d41  mov     ebx, eax
0x180024d43  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d4a  cmp     rcx, r15
0x180024d4d  jz      short loc_180024D74
0x180024d4f  test    [rcx+1Ch], r14d
0x180024d53  jz      short loc_180024D74
0x180024d55  cmp     byte ptr [rcx+19h], 2
0x180024d59  jb      short loc_180024D74
0x180024d5b  mov     rcx, [rcx+10h]
0x180024d5f  lea     r9, [rbp+55h]
0x180024d63  mov     edx, 442h
0x180024d68  mov     [rsp+68h+var_48], eax
0x180024d6c  mov     r8, r12
0x180024d6f  call    WPP_SF_sd
0x180024d74  mov     rcx, rdi; hMem
0x180024d77  call    cs:__imp_LocalFree
0x180024d7e  nop     dword ptr [rax+rax+00h]
0x180024d83  mov     rcx, rsi; hMem
0x180024d86  call    cs:__imp_LocalFree
0x180024d8d  nop     dword ptr [rax+rax+00h]
0x180024d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d99  cmp     rcx, r15
0x180024d9c  jz      short loc_180024DBE
0x180024d9e  test    [rcx+1Ch], r14d
0x180024da2  jz      short loc_180024DBE
0x180024da4  cmp     byte ptr [rcx+19h], 6
0x180024da8  jb      short loc_180024DBE
0x180024daa  mov     rcx, [rcx+10h]
0x180024dae  mov     edx, 443h
0x180024db3  mov     r9d, ebx
0x180024db6  mov     r8, r12
0x180024db9  call    WPP_SF_d
0x180024dbe  mov     eax, ebx
0x180024dc0  add     rsp, 30h
0x180024dc4  pop     r15
0x180024dc6  pop     r14
0x180024dc8  pop     r12
0x180024dca  pop     rdi
0x180024dcb  pop     rsi
0x180024dcc  pop     rbp
0x180024dcd  pop     rbx
0x180024dce  retn
```
