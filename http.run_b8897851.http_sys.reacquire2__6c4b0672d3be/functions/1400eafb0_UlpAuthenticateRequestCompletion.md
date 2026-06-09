# UlpAuthenticateRequestCompletion

- ea: `0x1400eafb0`
- end: `0x1400eb309`
- name: `UlpAuthenticateRequestCompletion`
- size: `857`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x14000bfb0`
- `0x14000f480`
- `0x140013430`
- `0x14002dd70`
- `0x14008b7e0`
- `0x1400eaaac`
- `0x1400eafb0`
- `0x1400eba20`
- `0x1400ece74`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c4a18`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400eb26d`
- `ntoskrnl!IofCompleteRequest` at `0x1400eb26d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb069`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb1fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb069`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400eb1fa`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb05d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb1ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb05d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400eb1ee`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb026`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400eb026`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb00e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400eb00e`

## pseudocode

```c
void __fastcall UlpAuthenticateRequestCompletion(__int64 a1, int a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // r9
  ULONG_PTR v8; // rdx
  int v9; // eax
  int Request; // esi
  bool v11; // si
  bool v12; // cl
  char IsRequestFromProxy; // al
  _QWORD *v14; // rcx
  __int64 v15; // rax
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF

  v16[0] = v16;
  v16[1] = v16;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qdP(1032, 162, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, a1, a2, a3);
  v5 = *(_QWORD *)(a1 + 24);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v5 + 576, 0);
  *(_BYTE *)(a1 + 2440) = 0;
  if ( (*(_DWORD *)(v5 + 632) & 2) != 0 )
  {
    UlCleanupSecurityContext(*(_QWORD *)(v5 + 1096), 0, v5 + 792);
    ExReleasePushLockExclusiveEx(v5 + 576, 0);
    KeLeaveCriticalRegion();
    v8 = a1 + 48;
    v9 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
    if ( UxDebugCheckRefcount && v9 <= -1 )
      UlBugCheckEx(3u, v8, 0x20u, v9);
    goto LABEL_43;
  }
  Request = 0;
  if ( a2 < 0 )
  {
LABEL_15:
    if ( !*(_DWORD *)(a1 + 1868) )
      UlSetErrorCode(a1, 20, *(_QWORD *)(a1 + 1344));
    UlSendErrorResponse(v5);
LABEL_18:
    v12 = 0;
    if ( Request < 0 )
      goto LABEL_31;
    goto LABEL_19;
  }
  if ( a2 != 259 )
  {
    ++*(_DWORD *)(a1 + 2756);
    Request = UlpDeliverHttpRequest(v5, v16);
    if ( Request >= 0 )
    {
      Request = UlpParseNextRequest(v5, 0, v16);
      if ( Request >= 0 )
        goto LABEL_18;
    }
    goto LABEL_15;
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_qq(1032, 253, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v5, *(_QWORD *)(v5 + 48));
  UlpSendErrorResponse(v5, 9);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
  {
    WPP_SF_(1032, 254, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
    v11 = 1;
LABEL_20:
    if ( *(_BYTE *)(v5 + 821) && !*(_BYTE *)(a1 + 1466) || *(_BYTE *)(v5 + 822) && (*(_BYTE *)(a1 + 1467) & 1) != 0 )
    {
      IsRequestFromProxy = UlpIsRequestFromProxy(a1);
      v12 = v11;
      if ( !IsRequestFromProxy )
        v12 = 1;
    }
    else
    {
      v12 = v11;
    }
    if ( *(_BYTE *)(v5 + 823) )
      v12 = 1;
    goto LABEL_31;
  }
LABEL_19:
  v11 = a2 == 259;
  if ( a2 >= 0 )
    goto LABEL_20;
  v12 = a2 == 259;
LABEL_31:
  UlCleanupSecurityContext(*(_QWORD *)(v5 + 1096), v12, v5 + 792);
  ExReleasePushLockExclusiveEx(v5 + 576, 0);
  KeLeaveCriticalRegion();
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 289, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids, v16);
  while ( 1 )
  {
    v14 = (_QWORD *)v16[0];
    if ( (_QWORD *)v16[0] == v16 )
      break;
    if ( *(_QWORD **)(v16[0] + 8LL) != v16 || (v15 = *(_QWORD *)v16[0], *(_QWORD *)(*(_QWORD *)v16[0] + 8LL) != v16[0]) )
      __fastfail(3u);
    v16[0] = *(_QWORD *)v16[0];
    *(_QWORD *)(v15 + 8) = v16;
    *v14 = 0;
    v14[1] = 0;
    IofCompleteRequest((PIRP)(v14 - 21), 0);
  }
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 290, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
  v8 = a1 + 48;
  v9 = _InterlockedDecrement((volatile signed __int32 *)(a1 + 48));
  if ( UxDebugCheckRefcount && v9 <= -1 )
    UlBugCheckEx(3u, v8, 0x20u, v9);
LABEL_43:
  if ( !v9 )
    UlpQueueFreeHttpRequest(a1, v8, v6, v7);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_(1032, 163, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids);
}

```

## disassembly

```asm
0x1400eafb0  push    rbp
0x1400eafb2  push    rbx
0x1400eafb3  push    rsi
0x1400eafb4  push    rdi
0x1400eafb5  push    r13
0x1400eafb7  push    r14
0x1400eafb9  push    r15
0x1400eafbb  mov     rbp, rsp
0x1400eafbe  sub     rsp, 40h
0x1400eafc2  lea     rax, [rbp+var_10]
0x1400eafc6  mov     r14d, edx
0x1400eafc9  mov     [rbp+var_10], rax
0x1400eafcd  mov     rdi, rcx
0x1400eafd0  lea     rax, [rbp+var_10]
0x1400eafd4  mov     [rbp+var_8], rax
0x1400eafd8  mov     r13d, 1
0x1400eafde  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eafe5  jz      short loc_1400EB00A
0x1400eafe7  mov     [rsp+40h+var_18], r8
0x1400eafec  mov     edx, 0A2h
0x1400eaff1  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eaff8  mov     dword ptr [rsp+40h+var_20], r14d
0x1400eaffd  mov     ecx, 408h
0x1400eb002  mov     r9, rdi
0x1400eb005  call    WPP_SF_qdP
0x1400eb00a  mov     rbx, [rdi+18h]
0x1400eb00e  call    cs:__imp_KeEnterCriticalRegion
0x1400eb015  nop     dword ptr [rax+rax+00h]
0x1400eb01a  lea     r15, [rbx+240h]
0x1400eb021  xor     edx, edx
0x1400eb023  mov     rcx, r15
0x1400eb026  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400eb02d  nop     dword ptr [rax+rax+00h]
0x1400eb032  mov     byte ptr [rdi+988h], 0
0x1400eb039  mov     eax, [rbx+278h]
0x1400eb03f  test    al, 2
0x1400eb041  jz      short loc_1400EB0AA
0x1400eb043  mov     rcx, [rbx+448h]
0x1400eb04a  lea     r8, [rbx+318h]
0x1400eb051  xor     edx, edx
0x1400eb053  call    UlCleanupSecurityContext
0x1400eb058  xor     edx, edx
0x1400eb05a  mov     rcx, r15
0x1400eb05d  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400eb064  nop     dword ptr [rax+rax+00h]
0x1400eb069  call    cs:__imp_KeLeaveCriticalRegion
0x1400eb070  nop     dword ptr [rax+rax+00h]
0x1400eb075  lea     rdx, [rdi+30h]; BugCheckParameter2
0x1400eb079  or      eax, 0FFFFFFFFh
0x1400eb07c  lock xadd [rdx], eax
0x1400eb080  dec     eax
0x1400eb082  cmp     cs:UxDebugCheckRefcount, 0
0x1400eb089  jz      loc_1400EB2CE
0x1400eb08f  cmp     eax, 0FFFFFFFFh
0x1400eb092  jg      loc_1400EB2CE
0x1400eb098  mov     ecx, 3; BugCheckParameter1
0x1400eb09d  movsxd  r9, eax; BugCheckParameter4
0x1400eb0a0  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1400eb0a4  call    UlBugCheckEx
0x1400eb0aa  xor     esi, esi
0x1400eb0ac  test    r14d, r14d
0x1400eb0af  js      loc_1400EB148
0x1400eb0b5  cmp     r14d, 103h
0x1400eb0bc  jnz     short loc_1400EB11B
0x1400eb0be  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb0c5  jz      short loc_1400EB0E8
0x1400eb0c7  mov     rax, [rbx+30h]
0x1400eb0cb  lea     edx, [r14-6]
0x1400eb0cf  mov     ecx, 408h
0x1400eb0d4  mov     [rsp+40h+var_20], rax
0x1400eb0d9  mov     r9, rbx
0x1400eb0dc  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eb0e3  call    WPP_SF_qq
0x1400eb0e8  xor     r8d, r8d
0x1400eb0eb  mov     rcx, rbx
0x1400eb0ee  lea     edx, [r8+9]
0x1400eb0f2  call    UlpSendErrorResponse
0x1400eb0f7  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb0fe  jz      short loc_1400EB173
0x1400eb100  mov     edx, 0FEh
0x1400eb105  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eb10c  mov     ecx, 408h
0x1400eb111  call    WPP_SF_
0x1400eb116  mov     sil, r13b
0x1400eb119  jmp     short loc_1400EB183
0x1400eb11b  add     [rdi+0AC4h], r13d
0x1400eb122  lea     rdx, [rbp+var_10]
0x1400eb126  mov     rcx, rbx
0x1400eb129  call    UlpDeliverHttpRequest
0x1400eb12e  mov     esi, eax
0x1400eb130  test    eax, eax
0x1400eb132  js      short loc_1400EB148
0x1400eb134  lea     r8, [rbp+var_10]
0x1400eb138  xor     edx, edx
0x1400eb13a  mov     rcx, rbx
0x1400eb13d  call    UlpParseNextRequest
0x1400eb142  mov     esi, eax
0x1400eb144  test    eax, eax
0x1400eb146  jns     short loc_1400EB16D
0x1400eb148  cmp     dword ptr [rdi+74Ch], 0
0x1400eb14f  jnz     short loc_1400EB165
0x1400eb151  mov     r8, [rdi+540h]
0x1400eb158  mov     edx, 14h
0x1400eb15d  mov     rcx, rdi
0x1400eb160  call    UlSetErrorCode
0x1400eb165  mov     rcx, rbx
0x1400eb168  call    UlSendErrorResponse
0x1400eb16d  xor     cl, cl
0x1400eb16f  test    esi, esi
0x1400eb171  js      short loc_1400EB1CF
0x1400eb173  cmp     r14d, 103h
0x1400eb17a  setz    sil
0x1400eb17e  test    r14d, r14d
0x1400eb181  js      short loc_1400EB1CC
0x1400eb183  cmp     byte ptr [rbx+335h], 0
0x1400eb18a  jz      short loc_1400EB195
0x1400eb18c  cmp     byte ptr [rdi+5BAh], 0
0x1400eb193  jz      short loc_1400EB1A7
0x1400eb195  cmp     byte ptr [rbx+336h], 0
0x1400eb19c  jz      short loc_1400EB1BB
0x1400eb19e  test    [rdi+5BBh], r13b
0x1400eb1a5  jz      short loc_1400EB1BB
0x1400eb1a7  mov     rcx, rdi
0x1400eb1aa  call    UlpIsRequestFromProxy
0x1400eb1af  test    al, al
0x1400eb1b1  movzx   ecx, sil
0x1400eb1b5  cmovz   ecx, r13d
0x1400eb1b9  jmp     short loc_1400EB1BE
0x1400eb1bb  mov     cl, sil
0x1400eb1be  cmp     byte ptr [rbx+337h], 0
0x1400eb1c5  jz      short loc_1400EB1CF
0x1400eb1c7  mov     cl, r13b
0x1400eb1ca  jmp     short loc_1400EB1CF
0x1400eb1cc  mov     cl, sil
0x1400eb1cf  xor     edx, edx
0x1400eb1d1  lea     r8, [rbx+318h]
0x1400eb1d8  test    cl, cl
0x1400eb1da  mov     rcx, [rbx+448h]
0x1400eb1e1  setnz   dl
0x1400eb1e4  call    UlCleanupSecurityContext
0x1400eb1e9  xor     edx, edx
0x1400eb1eb  mov     rcx, r15
0x1400eb1ee  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400eb1f5  nop     dword ptr [rax+rax+00h]
0x1400eb1fa  call    cs:__imp_KeLeaveCriticalRegion
0x1400eb201  nop     dword ptr [rax+rax+00h]
0x1400eb206  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb20d  jz      short loc_1400EB229
0x1400eb20f  mov     edx, 121h
0x1400eb214  lea     r9, [rbp+var_10]
0x1400eb218  mov     ecx, 408h
0x1400eb21d  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eb224  call    WPP_SF_q
0x1400eb229  mov     rcx, [rbp+var_10]
0x1400eb22d  lea     rax, [rbp+var_10]
0x1400eb231  cmp     rcx, rax
0x1400eb234  jz      short loc_1400EB282
0x1400eb236  lea     rax, [rbp+var_10]
0x1400eb23a  cmp     [rcx+8], rax
0x1400eb23e  jnz     short loc_1400EB27B
0x1400eb240  mov     rax, [rcx]
0x1400eb243  cmp     [rax+8], rcx
0x1400eb247  jnz     short loc_1400EB27B
0x1400eb249  mov     [rbp+var_10], rax
0x1400eb24d  lea     rdx, [rbp+var_10]
0x1400eb251  mov     [rax+8], rdx
0x1400eb255  xor     edx, edx; PriorityBoost
0x1400eb257  mov     qword ptr [rcx], 0
0x1400eb25e  mov     qword ptr [rcx+8], 0
0x1400eb266  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1400eb26d  call    cs:__imp_IofCompleteRequest
0x1400eb274  nop     dword ptr [rax+rax+00h]
0x1400eb279  jmp     short loc_1400EB229
0x1400eb27b  mov     ecx, 3
0x1400eb280  int     29h; Win8: RtlFailFast(ecx)
0x1400eb282  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb289  jz      short loc_1400EB2A1
0x1400eb28b  mov     edx, 122h
0x1400eb290  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eb297  mov     ecx, 408h
0x1400eb29c  call    WPP_SF_
0x1400eb2a1  lea     rdx, [rdi+30h]; BugCheckParameter2
0x1400eb2a5  or      eax, 0FFFFFFFFh
0x1400eb2a8  lock xadd [rdx], eax
0x1400eb2ac  dec     eax
0x1400eb2ae  cmp     cs:UxDebugCheckRefcount, 0
0x1400eb2b5  jz      short loc_1400EB2CE
0x1400eb2b7  cmp     eax, 0FFFFFFFFh
0x1400eb2ba  jg      short loc_1400EB2CE
0x1400eb2bc  mov     ecx, 3; BugCheckParameter1
0x1400eb2c1  movsxd  r9, eax; BugCheckParameter4
0x1400eb2c4  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1400eb2c8  call    UlBugCheckEx
0x1400eb2ce  test    eax, eax
0x1400eb2d0  jnz     short loc_1400EB2DA
0x1400eb2d2  mov     rcx, rdi
0x1400eb2d5  call    UlpQueueFreeHttpRequest
0x1400eb2da  test    byte ptr cs:xmmword_1401A2CA0+1, r13b
0x1400eb2e1  jz      short loc_1400EB2F9
0x1400eb2e3  mov     edx, 0A3h
0x1400eb2e8  lea     r8, WPP_cb8ff99b1ccb3ab0665355982b063b25_Traceguids
0x1400eb2ef  mov     ecx, 408h
0x1400eb2f4  call    WPP_SF_
0x1400eb2f9  add     rsp, 40h
0x1400eb2fd  pop     r15
0x1400eb2ff  pop     r14
0x1400eb301  pop     r13
0x1400eb303  pop     rdi
0x1400eb304  pop     rsi
0x1400eb305  pop     rbx
0x1400eb306  pop     rbp
0x1400eb307  retn
```
