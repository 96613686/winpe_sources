# PostConfigChangeNotification

- ea: `0x180023d78`
- end: `0x180023fa9`
- name: `PostConfigChangeNotification`
- size: `561`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b6a0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000c00c`
- `0x180023d78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023ddf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f21`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180023f17`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x180023f17`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023dd1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023dd1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e2b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f66`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023e44`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023f66`

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
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 1087, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
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
            (unsigned int)WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
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
    WPP_SF_d(v5[1].Flink, v6, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v7);
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
    WPP_SF_d(v5[1].Flink, 1091, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180023d78  push    rbx
0x180023d7a  push    rbp
0x180023d7b  push    rsi
0x180023d7c  push    rdi
0x180023d7d  push    r12
0x180023d7f  push    r14
0x180023d81  push    r15
0x180023d83  sub     rsp, 30h
0x180023d87  mov     rbp, rcx
0x180023d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d91  lea     r15, WPP_GLOBAL_Control
0x180023d98  lea     r12, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180023d9f  mov     r14d, 2000h
0x180023da5  cmp     rcx, r15
0x180023da8  jz      short loc_180023DC7
0x180023daa  test    [rcx+1Ch], r14d
0x180023dae  jz      short loc_180023DC7
0x180023db0  cmp     byte ptr [rcx+19h], 6
0x180023db4  jb      short loc_180023DC7
0x180023db6  mov     rcx, [rcx+10h]
0x180023dba  mov     edx, 43Fh
0x180023dbf  mov     r8, r12
0x180023dc2  call    WPP_SF_
0x180023dc7  mov     edx, 38h ; '8'; uBytes
0x180023dcc  lea     ebx, [rdx+8]
0x180023dcf  mov     ecx, ebx; uFlags
0x180023dd1  call    cs:__imp_LocalAlloc
0x180023dd7  mov     rdi, rax
0x180023dda  test    rax, rax
0x180023ddd  jnz     short loc_180023E24
0x180023ddf  call    cs:__imp_GetLastError
0x180023de5  mov     ebx, eax
0x180023de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dee  cmp     rcx, r15
0x180023df1  jz      loc_180023F98
0x180023df7  test    [rcx+1Ch], r14d
0x180023dfb  jz      loc_180023F73
0x180023e01  cmp     byte ptr [rcx+19h], 2
0x180023e05  jb      loc_180023F73
0x180023e0b  mov     edx, 440h
0x180023e10  mov     r9d, eax
0x180023e13  mov     rcx, [rcx+10h]
0x180023e17  mov     r8, r12
0x180023e1a  call    WPP_SF_d
0x180023e1f  jmp     loc_180023F6C
0x180023e24  mov     edx, 1D8h; uBytes
0x180023e29  mov     ecx, ebx; uFlags
0x180023e2b  call    cs:__imp_LocalAlloc
0x180023e31  mov     rsi, rax
0x180023e34  test    rax, rax
0x180023e37  jnz     short loc_180023E78
0x180023e39  call    cs:__imp_GetLastError
0x180023e3f  mov     rcx, rdi; hMem
0x180023e42  mov     ebx, eax
0x180023e44  call    cs:__imp_LocalFree
0x180023e4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e51  cmp     rcx, r15
0x180023e54  jz      loc_180023F98
0x180023e5a  test    [rcx+1Ch], r14d
0x180023e5e  jz      loc_180023F73
0x180023e64  cmp     byte ptr [rcx+19h], 2
0x180023e68  jb      loc_180023F73
0x180023e6e  mov     edx, 441h
0x180023e73  mov     r9d, ebx
0x180023e76  jmp     short loc_180023E13
0x180023e78  xor     ebx, ebx
0x180023e7a  mov     rcx, rsi
0x180023e7d  mov     rax, rbp
0x180023e80  lea     edx, [rbx+3]
0x180023e83  lea     r8d, [rdx+7Dh]
0x180023e87  movups  xmm0, xmmword ptr [rax]
0x180023e8a  movups  xmmword ptr [rcx], xmm0
0x180023e8d  movups  xmm1, xmmword ptr [rax+10h]
0x180023e91  movups  xmmword ptr [rcx+10h], xmm1
0x180023e95  movups  xmm0, xmmword ptr [rax+20h]
0x180023e99  movups  xmmword ptr [rcx+20h], xmm0
0x180023e9d  movups  xmm1, xmmword ptr [rax+30h]
0x180023ea1  movups  xmmword ptr [rcx+30h], xmm1
0x180023ea5  movups  xmm0, xmmword ptr [rax+40h]
0x180023ea9  movups  xmmword ptr [rcx+40h], xmm0
0x180023ead  movups  xmm1, xmmword ptr [rax+50h]
0x180023eb1  movups  xmmword ptr [rcx+50h], xmm1
0x180023eb5  movups  xmm0, xmmword ptr [rax+60h]
0x180023eb9  movups  xmmword ptr [rcx+60h], xmm0
0x180023ebd  movups  xmm1, xmmword ptr [rax+70h]
0x180023ec1  add     rax, r8
0x180023ec4  movups  xmmword ptr [rcx+70h], xmm1
0x180023ec8  add     rcx, r8
0x180023ecb  sub     rdx, 1; dwNumberOfBytesTransferred
0x180023ecf  jnz     short loc_180023E87
0x180023ed1  movups  xmm0, xmmword ptr [rax]
0x180023ed4  mov     r9, rdi; lpOverlapped
0x180023ed7  xor     r8d, r8d; dwCompletionKey
0x180023eda  movups  xmmword ptr [rcx], xmm0
0x180023edd  movups  xmm1, xmmword ptr [rax+10h]
0x180023ee1  movups  xmmword ptr [rcx+10h], xmm1
0x180023ee5  movups  xmm0, xmmword ptr [rax+20h]
0x180023ee9  movups  xmmword ptr [rcx+20h], xmm0
0x180023eed  movups  xmm1, xmmword ptr [rax+30h]
0x180023ef1  movups  xmmword ptr [rcx+30h], xmm1
0x180023ef5  movups  xmm0, xmmword ptr [rax+40h]
0x180023ef9  movups  xmmword ptr [rcx+40h], xmm0
0x180023efd  mov     rax, [rax+50h]
0x180023f01  mov     [rcx+50h], rax
0x180023f05  mov     rcx, cs:hIoCompletionPort; CompletionPort
0x180023f0c  mov     dword ptr [rdi+20h], 0Ah
0x180023f13  mov     [rdi+28h], rsi
0x180023f17  call    cs:__imp_PostQueuedCompletionStatus
0x180023f1d  test    eax, eax
0x180023f1f  jnz     short loc_180023F6C
0x180023f21  call    cs:__imp_GetLastError
0x180023f27  mov     ebx, eax
0x180023f29  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f30  cmp     rcx, r15
0x180023f33  jz      short loc_180023F5A
0x180023f35  test    [rcx+1Ch], r14d
0x180023f39  jz      short loc_180023F5A
0x180023f3b  cmp     byte ptr [rcx+19h], 2
0x180023f3f  jb      short loc_180023F5A
0x180023f41  mov     rcx, [rcx+10h]
0x180023f45  lea     r9, [rbp+55h]
0x180023f49  mov     edx, 442h
0x180023f4e  mov     [rsp+68h+var_48], eax
0x180023f52  mov     r8, r12
0x180023f55  call    WPP_SF_sd
0x180023f5a  mov     rcx, rdi; hMem
0x180023f5d  call    cs:__imp_LocalFree
0x180023f63  mov     rcx, rsi; hMem
0x180023f66  call    cs:__imp_LocalFree
0x180023f6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f73  cmp     rcx, r15
0x180023f76  jz      short loc_180023F98
0x180023f78  test    [rcx+1Ch], r14d
0x180023f7c  jz      short loc_180023F98
0x180023f7e  cmp     byte ptr [rcx+19h], 6
0x180023f82  jb      short loc_180023F98
0x180023f84  mov     rcx, [rcx+10h]
0x180023f88  mov     edx, 443h
0x180023f8d  mov     r9d, ebx
0x180023f90  mov     r8, r12
0x180023f93  call    WPP_SF_d
0x180023f98  mov     eax, ebx
0x180023f9a  add     rsp, 30h
0x180023f9e  pop     r15
0x180023fa0  pop     r14
0x180023fa2  pop     r12
0x180023fa4  pop     rdi
0x180023fa5  pop     rsi
0x180023fa6  pop     rbp
0x180023fa7  pop     rbx
0x180023fa8  retn
```
