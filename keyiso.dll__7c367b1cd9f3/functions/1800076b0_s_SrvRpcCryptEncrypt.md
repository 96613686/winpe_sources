# s_SrvRpcCryptEncrypt

- ea: `0x1800076b0`
- end: `0x18000784f`
- name: `s_SrvRpcCryptEncrypt`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x1800076b0`
- `0x180007ad0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800076e6`
- `RPCRT4!RpcImpersonateClient` at `0x1800076e6`
- `RPCRT4!RpcRevertToSelf` at `0x1800077a5`
- `RPCRT4!RpcRevertToSelf` at `0x1800077a5`

## string_xrefs

- `0x180007764`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007783`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800077df`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007810`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007830`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptEncrypt(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        int a11)
{
  unsigned int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // ebx

  if ( a10 )
  {
    if ( (a11 & 0x10) != 0 )
    {
      v17 = -2146893815;
      DebugTraceError(2148073481LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 871);
    }
    else
    {
      v14 = RpcImpersonateClient(a1);
      if ( v14 )
      {
        DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 878);
        return (unsigned int)-2146893792;
      }
      else
      {
        *a10 = 0;
        v15 = UnpackPaddingInfoPtr(a7);
        v16 = off_180025078[0](a2, a3, a4, a5, a6, v15, a8, a9, (__int64)a10, a11);
        v17 = v16;
        if ( v16 < 0 )
          DebugTraceError(
            (unsigned int)v16,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
            900);
        RpcRevertToSelf();
      }
    }
  }
  else
  {
    v17 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        96);
  }
  return v17;
}

```

## disassembly

```asm
0x1800076b0  push    rbx
0x1800076b2  push    rsi
0x1800076b3  push    rdi
0x1800076b4  push    r14
0x1800076b6  push    r15
0x1800076b8  sub     rsp, 70h
0x1800076bc  mov     rsi, r9
0x1800076bf  mov     r14, r8
0x1800076c2  mov     r15, rdx
0x1800076c5  mov     rdi, [rsp+98h+arg_48]
0x1800076cd  test    rdi, rdi
0x1800076d0  jz      loc_1800077B9
0x1800076d6  mov     ebx, [rsp+98h+arg_50]
0x1800076dd  test    bl, 10h
0x1800076e0  jnz     loc_180007805
0x1800076e6  call    cs:__imp_RpcImpersonateClient
0x1800076ec  test    eax, eax
0x1800076ee  jnz     loc_18000782A
0x1800076f4  mov     [rdi], eax
0x1800076f6  mov     rcx, [rsp+98h+arg_30]
0x1800076fe  call    _UnpackPaddingInfoPtr
0x180007703  mov     rcx, rax
0x180007706  mov     [rsp+98h+var_50], ebx
0x18000770a  mov     [rsp+98h+var_58], rdi
0x18000770f  mov     eax, [rsp+98h+arg_40]
0x180007716  mov     [rsp+98h+var_60], eax
0x18000771a  mov     rax, [rsp+98h+arg_38]
0x180007722  mov     [rsp+98h+var_68], rax
0x180007727  mov     [rsp+98h+var_70], rcx
0x18000772c  mov     eax, [rsp+98h+arg_28]
0x180007733  mov     [rsp+98h+var_78], eax
0x180007737  mov     r9, [rsp+98h+arg_20]
0x18000773f  mov     r8, rsi
0x180007742  mov     rdx, r14
0x180007745  mov     rcx, r15
0x180007748  mov     rax, cs:off_180025078
0x18000774f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007754  mov     ebx, eax
0x180007756  mov     [rsp+98h+var_38], eax
0x18000775a  test    eax, eax
0x18000775c  jns     short loc_180007779
0x18000775e  mov     r9d, 384h
0x180007764  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000776b  lea     rdx, aStatus; "Status"
0x180007772  mov     ecx, eax
0x180007774  call    DebugTraceError
0x180007779  jmp     short loc_1800077A5
0x18000777b  mov     ebx, eax
0x18000777d  mov     r9d, 38Ah
0x180007783  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000778a  lea     rdx, aNtstatus; "ntStatus"
0x180007791  mov     ecx, eax
0x180007793  call    DebugTraceError
0x180007798  mov     ecx, ebx
0x18000779a  call    NormalizeNteStatus
0x18000779f  mov     ebx, eax
0x1800077a1  mov     [rsp+98h+var_38], eax
0x1800077a5  call    cs:__imp_RpcRevertToSelf
0x1800077ab  mov     eax, ebx
0x1800077ad  add     rsp, 70h
0x1800077b1  pop     r15
0x1800077b3  pop     r14
0x1800077b5  pop     rdi
0x1800077b6  pop     rsi
0x1800077b7  pop     rbx
0x1800077b8  retn
0x1800077b9  mov     ebx, 80090027h
0x1800077be  lea     rax, WPP_GLOBAL_Control
0x1800077c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077cc  cmp     rcx, rax
0x1800077cf  jz      short loc_1800077AB
0x1800077d1  test    byte ptr [rcx+1Ch], 1
0x1800077d5  jz      short loc_1800077AB
0x1800077d7  mov     dword ptr [rsp+98h+var_68], 360h
0x1800077df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800077e6  mov     [rsp+98h+var_70], r8
0x1800077eb  mov     [rsp+98h+var_78], 80090027h
0x1800077f3  lea     r9, aStatus; "Status"
0x1800077fa  mov     rcx, [rcx+10h]
0x1800077fe  call    WPP_SF_sDsd
0x180007803  jmp     short loc_1800077AB
0x180007805  mov     ebx, 80090009h
0x18000780a  mov     r9d, 367h
0x180007810  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007817  lea     rdx, aStatus; "Status"
0x18000781e  mov     ecx, 80090009h
0x180007823  call    DebugTraceError
0x180007828  jmp     short loc_1800077AB
0x18000782a  mov     r9d, 36Eh
0x180007830  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007837  lea     rdx, aStatus; "Status"
0x18000783e  mov     ecx, eax
0x180007840  call    DebugTraceError
0x180007845  mov     ebx, 80090020h
0x18000784a  jmp     loc_1800077AB
```
