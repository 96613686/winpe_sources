# SyncImportExport(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,ulong,uchar *,ushort const *,ushort * *,ulong *,uchar * *)

- ea: `0x180009fa4`
- end: `0x18000a289`
- name: `?SyncImportExport@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@KPEAEPEBGPEAPEAGPEAKPEAPEAE@Z`
- size: `741`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a290`
- `0x18000a330`

## callees

- `0x180001d38`
- `0x180002168`
- `0x180002f10`
- `0x180009fa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a211`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a211`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a114`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000a114`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000a1e5`
- `RPCRT4!Ndr64AsyncClientCall` at `0x18000a1e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a25c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a124`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a25c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a252`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a252`

## pseudocode

```c
__int64 __fastcall SyncImportExport(
        struct _DAC_CLIENT_CONTEXT *a1,
        int a2,
        int a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7,
        _QWORD *a8)
{
  _DWORD *v12; // r15
  _QWORD *v13; // rsi
  signed int LastError; // eax
  int v15; // edi
  signed int v16; // eax
  __int64 v18; // [rsp+28h] [rbp-60h]
  struct _DAC_ASYNC_USER_CONTEXT *v19; // [rsp+40h] [rbp-48h] BYREF
  __int128 hHandle; // [rsp+48h] [rbp-40h] BYREF
  int v22; // [rsp+A0h] [rbp+18h] BYREF

  v19 = 0;
  v22 = 0;
  hHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_1937730dad33375cdddf08c541dbf4f4_Traceguids);
  if ( a3 )
  {
    if ( !a4 )
      goto LABEL_42;
    goto LABEL_9;
  }
  if ( a4 )
    goto LABEL_42;
  if ( a6 )
  {
LABEL_9:
    if ( a2 == 10 )
      goto LABEL_42;
  }
  if ( (!a3 || !a4 || !a6) && a2 == 8 )
    goto LABEL_42;
  v12 = a7;
  v13 = a8;
  if ( a7 )
  {
    if ( a8 )
      goto LABEL_19;
LABEL_42:
    v15 = -2147024809;
    goto LABEL_43;
  }
  if ( a8 )
    goto LABEL_42;
  if ( !a5 )
    goto LABEL_20;
LABEL_19:
  if ( a2 == 8 )
    goto LABEL_42;
LABEL_20:
  if ( (!a7 || !a8 || !a5) && a2 == 10 )
    goto LABEL_42;
  if ( a2 == 10 && a7 && a8 )
  {
    *a7 = 0;
    *v13 = 0;
  }
  else if ( a2 == 8 && a6 )
  {
    *a6 = 0;
  }
  *(_QWORD *)&hHandle = CreateEventW(0, 1, 0, 0);
  if ( !(_QWORD)hHandle )
    goto LABEL_32;
  v15 = CreateAsyncUserContext((__int64)a1, 0xAu, 0, &hHandle, &v22, (struct _RPC_ASYNC_STATE **)&v19);
  if ( v15 < 0 )
  {
    CleanupAsyncUserContext(a1, v22, &v19);
    goto LABEL_43;
  }
  if ( a2 == 8 )
  {
    LODWORD(v18) = a3;
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
      0xDu,
      0,
      v19,
      (char *)a1 + 56,
      v18,
      a4,
      a6);
  }
  else if ( a2 == 10 )
  {
    Ndr64AsyncClientCall(
      (MIDL_STUBLESS_PROXY_INFO *)&DeviceAssociation_ProxyInfo,
      0xEu,
      0,
      v19,
      (char *)a1 + 56,
      a5,
      v12,
      v13);
  }
  if ( WaitForSingleObject((HANDLE)hHandle, 0xFFFFFFFF) )
  {
LABEL_32:
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v15 = DWORD2(hHandle);
  }
LABEL_43:
  if ( (_QWORD)hHandle )
  {
    if ( !CloseHandle((HANDLE)hHandle) )
    {
      v16 = GetLastError();
      v15 = v16;
      if ( v16 > 0 )
        return (unsigned __int16)v16 | 0x80070000;
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180009fa4  mov     rax, rsp
0x180009fa7  mov     [rax+10h], rsi
0x180009fab  mov     [rax+8], rcx
0x180009faf  push    rdi
0x180009fb0  push    r12
0x180009fb2  push    r13
0x180009fb4  push    r14
0x180009fb6  push    r15
0x180009fb8  sub     rsp, 60h
0x180009fbc  mov     r12, r9
0x180009fbf  mov     r13d, r8d
0x180009fc2  mov     r14d, edx
0x180009fc5  mov     rdi, rcx
0x180009fc8  mov     qword ptr [rax-48h], 0
0x180009fd0  mov     dword ptr [rax+18h], 0
0x180009fd7  xorps   xmm0, xmm0
0x180009fda  movups  xmmword ptr [rax-40h], xmm0
0x180009fde  lea     rax, WPP_GLOBAL_Control
0x180009fe5  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fec  cmp     rcx, rax
0x180009fef  jz      short loc_18000A00C
0x180009ff1  cmp     byte ptr [rcx+19h], 4
0x180009ff5  jb      short loc_18000A00C
0x180009ff7  mov     edx, 0Ch
0x180009ffc  lea     r8, WPP_1937730dad33375cdddf08c541dbf4f4_Traceguids
0x18000a003  mov     rcx, [rcx+10h]
0x18000a007  call    WPP_SF_s
0x18000a00c  test    r13d, r13d
0x18000a00f  jz      short loc_18000A01F
0x18000a011  test    r12, r12
0x18000a014  jz      loc_18000A243
0x18000a01a  test    r13d, r13d
0x18000a01d  jnz     short loc_18000A03C
0x18000a01f  test    r12, r12
0x18000a022  jnz     loc_18000A243
0x18000a028  test    r13d, r13d
0x18000a02b  jnz     short loc_18000A03C
0x18000a02d  test    r12, r12
0x18000a030  jnz     short loc_18000A03C
0x18000a032  cmp     [rsp+88h+arg_28], r12
0x18000a03a  jz      short loc_18000A046
0x18000a03c  cmp     r14d, 0Ah
0x18000a040  jz      loc_18000A243
0x18000a046  test    r13d, r13d
0x18000a049  jz      short loc_18000A05B
0x18000a04b  test    r12, r12
0x18000a04e  jz      short loc_18000A05B
0x18000a050  cmp     [rsp+88h+arg_28], 0
0x18000a059  jnz     short loc_18000A065
0x18000a05b  cmp     r14d, 8
0x18000a05f  jz      loc_18000A243
0x18000a065  mov     r15, [rsp+88h+arg_30]
0x18000a06d  mov     rsi, [rsp+88h+arg_38]
0x18000a075  test    r15, r15
0x18000a078  jz      short loc_18000A088
0x18000a07a  test    rsi, rsi
0x18000a07d  jz      loc_18000A243
0x18000a083  test    r15, r15
0x18000a086  jnz     short loc_18000A0A5
0x18000a088  test    rsi, rsi
0x18000a08b  jnz     loc_18000A243
0x18000a091  test    r15, r15
0x18000a094  jnz     short loc_18000A0A5
0x18000a096  test    rsi, rsi
0x18000a099  jnz     short loc_18000A0A5
0x18000a09b  cmp     [rsp+88h+arg_20], r15
0x18000a0a3  jz      short loc_18000A0AF
0x18000a0a5  cmp     r14d, 8
0x18000a0a9  jz      loc_18000A243
0x18000a0af  test    r15, r15
0x18000a0b2  jz      short loc_18000A0C4
0x18000a0b4  test    rsi, rsi
0x18000a0b7  jz      short loc_18000A0C4
0x18000a0b9  cmp     [rsp+88h+arg_20], 0
0x18000a0c2  jnz     short loc_18000A0CE
0x18000a0c4  cmp     r14d, 0Ah
0x18000a0c8  jz      loc_18000A243
0x18000a0ce  cmp     r14d, 0Ah
0x18000a0d2  jnz     short loc_18000A0EE
0x18000a0d4  test    r15, r15
0x18000a0d7  jz      short loc_18000A0EE
0x18000a0d9  test    rsi, rsi
0x18000a0dc  jz      short loc_18000A0EE
0x18000a0de  mov     dword ptr [r15], 0
0x18000a0e5  mov     qword ptr [rsi], 0
0x18000a0ec  jmp     short loc_18000A108
0x18000a0ee  cmp     r14d, 8
0x18000a0f2  jnz     short loc_18000A108
0x18000a0f4  mov     rax, [rsp+88h+arg_28]
0x18000a0fc  test    rax, rax
0x18000a0ff  jz      short loc_18000A108
0x18000a101  mov     qword ptr [rax], 0
0x18000a108  xor     r9d, r9d; lpName
0x18000a10b  xor     r8d, r8d; bInitialState
0x18000a10e  lea     edx, [r9+1]; bManualReset
0x18000a112  xor     ecx, ecx; lpEventAttributes
0x18000a114  call    cs:__imp_CreateEventW
0x18000a11a  mov     [rsp+88h+hHandle], rax
0x18000a11f  test    rax, rax
0x18000a122  jnz     short loc_18000A142
0x18000a124  call    cs:__imp_GetLastError
0x18000a12a  mov     edi, eax
0x18000a12c  test    eax, eax
0x18000a12e  jle     loc_18000A248
0x18000a134  movzx   edi, ax
0x18000a137  or      edi, 80070000h
0x18000a13d  jmp     loc_18000A248
0x18000a142  lea     rax, [rsp+88h+var_48]
0x18000a147  mov     [rsp+88h+var_60], rax
0x18000a14c  lea     rax, [rsp+88h+arg_10]
0x18000a154  mov     [rsp+88h+var_68], rax
0x18000a159  lea     r9, [rsp+88h+hHandle]
0x18000a15e  xor     r8d, r8d
0x18000a161  lea     edx, [r8+0Ah]
0x18000a165  mov     rcx, rdi
0x18000a168  call    ?CreateAsyncUserContext@@YAJPEAU_DAC_CLIENT_CONTEXT@@W4DAC_CALLBACK_TYPE@@PEAX2PEAHPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CreateAsyncUserContext(_DAC_CLIENT_CONTEXT *,DAC_CALLBACK_TYPE,void *,void *,int *,_DAC_ASYNC_USER_CONTEXT * *)
0x18000a16d  mov     edi, eax
0x18000a16f  test    eax, eax
0x18000a171  js      loc_18000A225
0x18000a177  cmp     r14d, 8
0x18000a17b  jz      short loc_18000A1A9
0x18000a17d  cmp     r14d, 0Ah
0x18000a181  mov     r14, [rsp+88h+arg_0]
0x18000a189  jnz     short loc_18000A1EB
0x18000a18b  mov     [rsp+88h+var_50], rsi
0x18000a190  mov     [rsp+88h+var_58], r15
0x18000a195  mov     rax, [rsp+88h+arg_20]
0x18000a19d  mov     [rsp+88h+var_60], rax
0x18000a1a2  mov     edx, 0Eh
0x18000a1a7  jmp     short loc_18000A1CD
0x18000a1a9  mov     r14, [rsp+88h+arg_0]
0x18000a1b1  mov     rax, [rsp+88h+arg_28]
0x18000a1b9  mov     [rsp+88h+var_50], rax
0x18000a1be  mov     [rsp+88h+var_58], r12
0x18000a1c3  mov     dword ptr [rsp+88h+var_60], r13d
0x18000a1c8  mov     edx, 0Dh; nProcNum
0x18000a1cd  lea     rcx, [r14+38h]
0x18000a1d1  mov     [rsp+88h+var_68], rcx
0x18000a1d6  mov     r9, [rsp+88h+var_48]
0x18000a1db  xor     r8d, r8d; pReturnValue
0x18000a1de  lea     rcx, ?DeviceAssociation_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000a1e5  call    cs:__imp_Ndr64AsyncClientCall
0x18000a1eb  jmp     short loc_18000A205
0x18000a1ed  mov     edi, eax
0x18000a1ef  cmp     eax, 1
0x18000a1f2  jl      short loc_18000A1FD
0x18000a1f4  movzx   edi, ax
0x18000a1f7  or      edi, 80010000h
0x18000a1fd  mov     r14, [rsp+88h+arg_0]
0x18000a205  test    edi, edi
0x18000a207  js      short loc_18000A22D
0x18000a209  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000a20c  mov     rcx, [rsp+88h+hHandle]; hHandle
0x18000a211  call    cs:__imp_WaitForSingleObject
0x18000a217  test    eax, eax
0x18000a219  jnz     loc_18000A124
0x18000a21f  mov     edi, [rsp+88h+var_38]
0x18000a223  jmp     short loc_18000A248
0x18000a225  mov     r14, [rsp+88h+arg_0]
0x18000a22d  lea     r8, [rsp+88h+var_48]; struct _DAC_ASYNC_USER_CONTEXT **
0x18000a232  mov     edx, [rsp+88h+arg_10]; int
0x18000a239  mov     rcx, r14; struct _DAC_CLIENT_CONTEXT *
0x18000a23c  call    ?CleanupAsyncUserContext@@YAXPEAU_DAC_CLIENT_CONTEXT@@HPEAPEAU_DAC_ASYNC_USER_CONTEXT@@@Z; CleanupAsyncUserContext(_DAC_CLIENT_CONTEXT *,int,_DAC_ASYNC_USER_CONTEXT * *)
0x18000a241  jmp     short loc_18000A248
0x18000a243  mov     edi, 80070057h
0x18000a248  mov     rcx, [rsp+88h+hHandle]; hObject
0x18000a24d  test    rcx, rcx
0x18000a250  jz      short loc_18000A271
0x18000a252  call    cs:__imp_CloseHandle
0x18000a258  test    eax, eax
0x18000a25a  jnz     short loc_18000A271
0x18000a25c  call    cs:__imp_GetLastError
0x18000a262  mov     edi, eax
0x18000a264  test    eax, eax
0x18000a266  jle     short loc_18000A271
0x18000a268  movzx   edi, ax
0x18000a26b  or      edi, 80070000h
0x18000a271  mov     eax, edi
0x18000a273  mov     rsi, [rsp+88h+arg_8]
0x18000a27b  add     rsp, 60h
0x18000a27f  pop     r15
0x18000a281  pop     r14
0x18000a283  pop     r13
0x18000a285  pop     r12
0x18000a287  pop     rdi
0x18000a288  retn
0x18000c036  push    rbp
0x18000c038  sub     rsp, 40h
0x18000c03c  mov     rbp, rdx
0x18000c03f  mov     rcx, [rcx]
0x18000c042  mov     ecx, [rcx]; ExceptionCode
0x18000c044  call    cs:__imp_I_RpcExceptionFilter
0x18000c04a  nop
0x18000c04b  add     rsp, 40h
0x18000c04f  pop     rbp
0x18000c050  retn
```
