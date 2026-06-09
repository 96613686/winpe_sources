# s_SrvRpcCryptVerifySignature

- ea: `0x180007860`
- end: `0x180007999`
- name: `s_SrvRpcCryptVerifySignature`
- size: `313`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, __int64, int, __int64, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180007860`
- `0x180007ad0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180007878`
- `RPCRT4!RpcImpersonateClient` at `0x180007878`
- `RPCRT4!RpcRevertToSelf` at `0x180007937`
- `RPCRT4!RpcRevertToSelf` at `0x180007937`

## string_xrefs

- `0x1800078f6`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007915`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007977`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptVerifySignature(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        int a9,
        int a10)
{
  RPC_STATUS v13; // eax
  __int64 v14; // rax
  signed int v15; // eax
  unsigned int v16; // ebx

  v13 = RpcImpersonateClient(a1);
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        153);
    return (unsigned int)-2146893792;
  }
  else
  {
    v14 = UnpackPaddingInfoPtr(a5);
    v15 = off_1800250B8(a2, a3, a4, v14, a6, a7, a8, a9, a10);
    v16 = v15;
    if ( v15 < 0 )
      DebugTraceError(
        v15,
        (int)"Status",
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        172);
    RpcRevertToSelf();
  }
  return v16;
}

```

## disassembly

```asm
0x180007860  mov     [rsp+arg_0], rbx
0x180007865  mov     [rsp+arg_8], rsi
0x18000786a  push    rdi
0x18000786b  sub     rsp, 60h
0x18000786f  mov     rbx, r9
0x180007872  mov     rdi, r8
0x180007875  mov     rsi, rdx
0x180007878  call    cs:__imp_RpcImpersonateClient
0x18000787e  test    eax, eax
0x180007880  jnz     loc_18000794F
0x180007886  mov     rcx, [rsp+68h+arg_20]
0x18000788e  call    _UnpackPaddingInfoPtr
0x180007893  mov     r9, rax
0x180007896  mov     ecx, [rsp+68h+arg_48]
0x18000789d  mov     [rsp+68h+var_28], ecx
0x1800078a1  mov     ecx, [rsp+68h+arg_40]
0x1800078a8  mov     [rsp+68h+var_30], ecx
0x1800078ac  mov     rcx, [rsp+68h+arg_38]
0x1800078b4  mov     [rsp+68h+var_38], rcx
0x1800078b9  mov     ecx, [rsp+68h+arg_30]
0x1800078c0  mov     dword ptr [rsp+68h+var_40], ecx
0x1800078c4  mov     rcx, [rsp+68h+arg_28]
0x1800078cc  mov     [rsp+68h+var_48], rcx
0x1800078d1  mov     r8, rbx
0x1800078d4  mov     rdx, rdi
0x1800078d7  mov     rcx, rsi
0x1800078da  mov     rax, cs:off_1800250B8
0x1800078e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800078e6  mov     ebx, eax
0x1800078e8  mov     [rsp+68h+var_18], eax
0x1800078ec  test    eax, eax
0x1800078ee  jns     short loc_18000790B
0x1800078f0  mov     r9d, 5ACh
0x1800078f6  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800078fd  lea     rdx, aStatus; "Status"
0x180007904  mov     ecx, eax
0x180007906  call    DebugTraceError
0x18000790b  jmp     short loc_180007937
0x18000790d  mov     ebx, eax
0x18000790f  mov     r9d, 5B2h
0x180007915  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000791c  lea     rdx, aNtstatus; "ntStatus"
0x180007923  mov     ecx, eax
0x180007925  call    DebugTraceError
0x18000792a  mov     ecx, ebx
0x18000792c  call    NormalizeNteStatus
0x180007931  mov     ebx, eax
0x180007933  mov     [rsp+68h+var_18], eax
0x180007937  call    cs:__imp_RpcRevertToSelf
0x18000793d  mov     eax, ebx
0x18000793f  mov     rbx, [rsp+68h+arg_0]
0x180007944  mov     rsi, [rsp+68h+arg_8]
0x180007949  add     rsp, 60h
0x18000794d  pop     rdi
0x18000794e  retn
0x18000794f  lea     rdx, WPP_GLOBAL_Control
0x180007956  mov     rcx, cs:WPP_GLOBAL_Control
0x18000795d  cmp     rcx, rdx
0x180007960  jz      short loc_180007968
0x180007962  test    byte ptr [rcx+1Ch], 1
0x180007966  jnz     short loc_18000796F
0x180007968  mov     ebx, 80090020h
0x18000796d  jmp     short loc_18000793D
0x18000796f  mov     dword ptr [rsp+68h+var_38], 599h
0x180007977  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000797e  mov     [rsp+68h+var_40], r8
0x180007983  mov     dword ptr [rsp+68h+var_48], eax
0x180007987  lea     r9, aStatus; "Status"
0x18000798e  mov     rcx, [rcx+10h]
0x180007992  call    WPP_SF_sDsd
0x180007997  jmp     short loc_180007968
```
