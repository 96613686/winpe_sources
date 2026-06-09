# CscService_SubmitTask(CServiceTask *,ulong)

- ea: `0x18001eb98`
- end: `0x18001ed7b`
- name: `?CscService_SubmitTask@@YAJPEAVCServiceTask@@K@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct CServiceTask *, unsigned int)`
- caller_count: `11`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18002fdd0`
- `0x18004b080`
- `0x1800555fc`
- `0x1800558d8`
- `0x180055fc8`
- `0x1800560b8`
- `0x1800585ac`
- `0x180058bd4`
- `0x180062420`
- `0x1800628bc`
- `0x180064b84`

## callees

- `0x18001eb98`
- `0x18001edf0`
- `0x18002f10c`
- `0x18003c488`
- `0x18003c4e8`
- `0x18003e928`
- `0x180056150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ecb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ed19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ed32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec37`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ed0a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001ed0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ec65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001ec65`
- `USER32!PostThreadMessageW` at `0x18001ecac`
- `USER32!PostThreadMessageW` at `0x18001ecac`

## pseudocode

```c
__int64 __fastcall CscService_SubmitTask(struct CServiceTask *a1, int a2)
{
  signed int LastError; // ebx
  signed int Error; // eax
  bool v7; // sf
  signed int v8; // eax
  struct CServiceTask *v9; // [rsp+30h] [rbp-38h] BYREF
  int v10; // [rsp+38h] [rbp-30h]
  int v11; // [rsp+3Ch] [rbp-2Ch]
  LPARAM lParam[2]; // [rsp+40h] [rbp-28h] BYREF
  HANDLE hHandle[3]; // [rsp+50h] [rbp-18h]

  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, (char *)a1 + 20);
  }
  v11 = 0;
  v9 = a1;
  v10 = a2;
  if ( (unsigned int)CscService_IsTerminating() )
  {
    LastError = -2147023834;
LABEL_6:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
        (_DWORD)a1 + 20,
        LastError);
    }
    return (unsigned int)LastError;
  }
  if ( GetCurrentThreadId() == g_idServiceMainThread )
  {
    Error = CscService_SubmitTaskCallback(&v9);
LABEL_14:
    LastError = Error;
    goto LABEL_27;
  }
  *(_OWORD *)lParam = 0;
  hHandle[0] = 0;
  hHandle[1] = CreateEventW(0, 0, 0, 0);
  if ( !hHandle[1] )
  {
    Error = ResultFromLastError();
    goto LABEL_14;
  }
  lParam[0] = (LPARAM)CscService_SubmitTaskCallback;
  LODWORD(hHandle[0]) = 0;
  lParam[1] = (LPARAM)&v9;
  if ( PostThreadMessageW(g_idServiceMainThread, 0xD26u, 0, (LPARAM)lParam) )
    goto LABEL_33;
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids,
      (unsigned int)LastError,
      g_idServiceMainThread);
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
    v7 = LastError < 0;
  }
  if ( !v7 )
  {
LABEL_33:
    if ( WaitForSingleObject(hHandle[1], 0xFFFFFFFF) )
    {
      v8 = GetLastError();
      LastError = v8;
      if ( v8 > 0 )
        LastError = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      LastError = (signed int)hHandle[0];
    }
  }
  CloseHandle(hHandle[1]);
LABEL_27:
  if ( LastError < 0 )
    goto LABEL_6;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids, (char *)a1 + 20);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18001eb98  push    rbp
0x18001eb9a  push    rbx
0x18001eb9b  push    rsi
0x18001eb9c  push    rdi
0x18001eb9d  mov     rbp, rsp
0x18001eba0  sub     rsp, 68h
0x18001eba4  mov     ebx, edx
0x18001eba6  mov     rdi, rcx
0x18001eba9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebb0  lea     rsi, WPP_GLOBAL_Control
0x18001ebb7  cmp     rcx, rsi
0x18001ebba  jz      short loc_18001EBDE
0x18001ebbc  test    dword ptr [rcx+1Ch], 400000h
0x18001ebc3  jz      short loc_18001EBDE
0x18001ebc5  mov     rcx, [rcx+10h]
0x18001ebc9  lea     r9, [rdi+14h]
0x18001ebcd  mov     edx, 0Dh
0x18001ebd2  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18001ebd9  call    WPP_SF_S
0x18001ebde  mov     [rbp+var_2C], 0
0x18001ebe5  mov     [rbp+var_38], rdi
0x18001ebe9  mov     [rbp+var_30], ebx
0x18001ebec  call    ?CscService_IsTerminating@@YAHXZ; CscService_IsTerminating(void)
0x18001ebf1  test    eax, eax
0x18001ebf3  jz      short loc_18001EC37
0x18001ebf5  mov     ebx, 80070426h
0x18001ebfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec01  cmp     rcx, rsi
0x18001ec04  jz      short loc_18001EC2C
0x18001ec06  test    dword ptr [rcx+1Ch], 400000h
0x18001ec0d  jz      short loc_18001EC2C
0x18001ec0f  mov     rcx, [rcx+10h]
0x18001ec13  lea     r9, [rdi+14h]
0x18001ec17  mov     edx, 0Fh
0x18001ec1c  mov     [rsp+68h+var_48], ebx
0x18001ec20  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18001ec27  call    WPP_SF_Sd
0x18001ec2c  mov     eax, ebx
0x18001ec2e  add     rsp, 68h
0x18001ec32  pop     rdi
0x18001ec33  pop     rsi
0x18001ec34  pop     rbx
0x18001ec35  pop     rbp
0x18001ec36  retn
0x18001ec37  call    cs:__imp_GetCurrentThreadId
0x18001ec3d  cmp     eax, cs:?g_idServiceMainThread@@3KA; ulong g_idServiceMainThread
0x18001ec43  jnz     short loc_18001EC50
0x18001ec45  lea     rcx, [rbp+var_38]; void *
0x18001ec49  call    ?CscService_SubmitTaskCallback@@YAJPEAX@Z; CscService_SubmitTaskCallback(void *)
0x18001ec4e  jmp     short loc_18001EC79
0x18001ec50  xorps   xmm0, xmm0
0x18001ec53  xor     r9d, r9d; lpName
0x18001ec56  xor     r8d, r8d; bInitialState
0x18001ec59  xor     edx, edx; bManualReset
0x18001ec5b  xor     ecx, ecx; lpEventAttributes
0x18001ec5d  movups  xmmword ptr [rbp+lParam], xmm0
0x18001ec61  movups  xmmword ptr [rbp+hHandle], xmm0
0x18001ec65  call    cs:__imp_CreateEventW
0x18001ec6b  mov     [rbp+hHandle+8], rax
0x18001ec6f  test    rax, rax
0x18001ec72  jnz     short loc_18001EC80
0x18001ec74  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001ec79  mov     ebx, eax
0x18001ec7b  jmp     loc_18001ED38
0x18001ec80  mov     ecx, cs:?g_idServiceMainThread@@3KA; idThread
0x18001ec86  lea     rax, ?CscService_SubmitTaskCallback@@YAJPEAX@Z; CscService_SubmitTaskCallback(void *)
0x18001ec8d  mov     [rbp+lParam], rax
0x18001ec91  lea     r9, [rbp+lParam]; lParam
0x18001ec95  lea     rax, [rbp+var_38]
0x18001ec99  mov     dword ptr [rbp+hHandle], 0
0x18001eca0  xor     r8d, r8d; wParam
0x18001eca3  mov     [rbp+lParam+8], rax
0x18001eca7  mov     edx, 0D26h; Msg
0x18001ecac  call    cs:__imp_PostThreadMessageW
0x18001ecb2  test    eax, eax
0x18001ecb4  jnz     short loc_18001ED03
0x18001ecb6  call    cs:__imp_GetLastError
0x18001ecbc  mov     ebx, eax
0x18001ecbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecc5  cmp     rcx, rsi
0x18001ecc8  jz      short loc_18001ECF2
0x18001ecca  test    byte ptr [rcx+1Ch], 2
0x18001ecce  jz      short loc_18001ECF2
0x18001ecd0  mov     eax, cs:?g_idServiceMainThread@@3KA; ulong g_idServiceMainThread
0x18001ecd6  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18001ecdd  mov     rcx, [rcx+10h]
0x18001ece1  mov     edx, 0Ch
0x18001ece6  mov     r9d, ebx
0x18001ece9  mov     [rsp+68h+var_48], eax
0x18001eced  call    WPP_SF_dd
0x18001ecf2  test    ebx, ebx
0x18001ecf4  jle     short loc_18001ED01
0x18001ecf6  movzx   ebx, bx
0x18001ecf9  or      ebx, 80070000h
0x18001ecff  test    ebx, ebx
0x18001ed01  js      short loc_18001ED2E
0x18001ed03  mov     rcx, [rbp+hHandle+8]; hHandle
0x18001ed07  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001ed0a  call    cs:__imp_WaitForSingleObject
0x18001ed10  test    eax, eax
0x18001ed12  jnz     short loc_18001ED19
0x18001ed14  mov     ebx, dword ptr [rbp+hHandle]
0x18001ed17  jmp     short loc_18001ED2E
0x18001ed19  call    cs:__imp_GetLastError
0x18001ed1f  mov     ebx, eax
0x18001ed21  test    eax, eax
0x18001ed23  jle     short loc_18001ED2E
0x18001ed25  movzx   ebx, ax
0x18001ed28  or      ebx, 80070000h
0x18001ed2e  mov     rcx, [rbp+hHandle+8]; hObject
0x18001ed32  call    cs:__imp_CloseHandle
0x18001ed38  test    ebx, ebx
0x18001ed3a  js      loc_18001EBFA
0x18001ed40  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed47  cmp     rcx, rsi
0x18001ed4a  jz      loc_18001EC2C
0x18001ed50  test    dword ptr [rcx+1Ch], 400000h
0x18001ed57  jz      loc_18001EC2C
0x18001ed5d  mov     rcx, [rcx+10h]
0x18001ed61  lea     r9, [rdi+14h]
0x18001ed65  mov     edx, 0Eh
0x18001ed6a  lea     r8, WPP_c1f26249b9153aeffc0e46a4a91f2203_Traceguids
0x18001ed71  call    WPP_SF_S
0x18001ed76  jmp     loc_18001EC2C
```
