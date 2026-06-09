# IsLanName

- ea: `0x18000bb40`
- end: `0x18000bd68`
- name: `IsLanName`
- size: `552`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800061c0`
- `0x180008570`

## callees

- `0x180002508`
- `0x180002538`
- `0x1800090dc`
- `0x18000bb40`
- `0x18000bda4`
- `0x18000c220`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000bca1`
- `RPCRT4!RpcBindingFree` at `0x18000bd21`
- `RPCRT4!RpcBindingFree` at `0x18000bca1`
- `RPCRT4!RpcBindingFree` at `0x18000bd21`
- `RPCRT4!NdrClientCall3` at `0x18000bc18`
- `RPCRT4!NdrClientCall3` at `0x18000bc18`

## pseudocode

```c
__int64 __fastcall IsLanName(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int Pointer; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rax
  CLIENT_CALL_RETURN v6; // rax
  int v8; // [rsp+78h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v10; // [rsp+88h] [rbp+20h]

  v8 = 0;
  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, a1);
  v2 = RpcBindForNfsClient(&Binding);
  Pointer = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_26:
      if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
        WPP_SF_d(v4[2], 67, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, Pointer);
      return 0;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v2);
LABEL_25:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(a1 + 2 * v5) );
  v10.Simple = 0;
  v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0, Binding, (int)v5 + 1, a1, &v8).Pointer;
  Pointer = (unsigned int)v6.Pointer;
  v10.Pointer = v6.Pointer;
  if ( LODWORD(v6.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        LODWORD(v6.Pointer));
LABEL_24:
    RpcBindingFree(&Binding);
    goto LABEL_25;
  }
  if ( v8 != 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
    goto LABEL_24;
  }
  RpcBindingFree(&Binding);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  return 1;
}

```

## disassembly

```asm
0x18000bb40  mov     rax, rsp
0x18000bb43  mov     [rax+8], rbx
0x18000bb47  push    rsi
0x18000bb48  push    rdi
0x18000bb49  push    r14
0x18000bb4b  sub     rsp, 50h
0x18000bb4f  mov     rsi, rcx
0x18000bb52  xor     r14d, r14d
0x18000bb55  mov     [rax+10h], r14d
0x18000bb59  mov     [rax+18h], r14
0x18000bb5d  lea     rdi, WPP_GLOBAL_Control
0x18000bb64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bb6b  cmp     rcx, rdi
0x18000bb6e  jz      short loc_18000BB8D
0x18000bb70  test    byte ptr [rcx+1Ch], 1
0x18000bb74  jz      short loc_18000BB8D
0x18000bb76  lea     edx, [r14+3Dh]
0x18000bb7a  mov     r9, rsi
0x18000bb7d  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bb84  mov     rcx, [rcx+10h]
0x18000bb88  call    WPP_SF_S
0x18000bb8d  lea     rcx, [rsp+68h+Binding]
0x18000bb95  call    RpcBindForNfsClient
0x18000bb9a  mov     ebx, eax
0x18000bb9c  test    eax, eax
0x18000bb9e  jz      short loc_18000BBD7
0x18000bba0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bba7  cmp     rcx, rdi
0x18000bbaa  jz      loc_18000BD57
0x18000bbb0  test    byte ptr [rcx+1Ch], 2
0x18000bbb4  jz      loc_18000BD34
0x18000bbba  mov     edx, 3Eh ; '>'
0x18000bbbf  mov     r9d, eax
0x18000bbc2  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bbc9  mov     rcx, [rcx+10h]
0x18000bbcd  call    WPP_SF_d
0x18000bbd2  jmp     loc_18000BD2D
0x18000bbd7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000bbdb  inc     rax
0x18000bbde  cmp     [rsi+rax*2], r14w
0x18000bbe3  jnz     short loc_18000BBDB
0x18000bbe5  inc     eax
0x18000bbe7  mov     [rsp+68h+arg_18], r14
0x18000bbef  lea     rcx, [rsp+68h+arg_8]
0x18000bbf4  mov     [rsp+68h+var_38], rcx
0x18000bbf9  mov     [rsp+68h+var_40], rsi
0x18000bbfe  mov     [rsp+68h+var_48], eax
0x18000bc02  mov     r9, [rsp+68h+Binding]
0x18000bc0a  xor     r8d, r8d; pReturnValue
0x18000bc0d  lea     edx, [r8+7]; nProcNum
0x18000bc11  lea     rcx, pProxyInfo; pProxyInfo
0x18000bc18  call    cs:__imp_NdrClientCall3
0x18000bc1f  nop     dword ptr [rax+rax+00h]
0x18000bc24  mov     rbx, rax
0x18000bc27  mov     [rsp+68h+arg_18], rax
0x18000bc2f  mov     [rsp+68h+var_20], eax
0x18000bc33  test    eax, eax
0x18000bc35  jz      short loc_18000BC66
0x18000bc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc3e  cmp     rcx, rdi
0x18000bc41  jz      short loc_18000BC61
0x18000bc43  test    byte ptr [rcx+1Ch], 2
0x18000bc47  jz      short loc_18000BC61
0x18000bc49  mov     edx, 3Fh ; '?'
0x18000bc4e  mov     r9d, eax
0x18000bc51  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bc58  mov     rcx, [rcx+10h]
0x18000bc5c  call    WPP_SF_d
0x18000bc61  jmp     loc_18000BD19
0x18000bc66  cmp     [rsp+68h+arg_8], 1
0x18000bc6b  jz      short loc_18000BC99
0x18000bc6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bc74  cmp     rcx, rdi
0x18000bc77  jz      short loc_18000BC94
0x18000bc79  test    byte ptr [rcx+1Ch], 2
0x18000bc7d  jz      short loc_18000BC94
0x18000bc7f  mov     edx, 40h ; '@'
0x18000bc84  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bc8b  mov     rcx, [rcx+10h]
0x18000bc8f  call    WPP_SF_
0x18000bc94  jmp     loc_18000BD19
0x18000bc99  lea     rcx, [rsp+68h+Binding]; Binding
0x18000bca1  call    cs:__imp_RpcBindingFree
0x18000bca8  nop     dword ptr [rax+rax+00h]
0x18000bcad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcb4  cmp     rcx, rdi
0x18000bcb7  jz      short loc_18000BCD4
0x18000bcb9  test    byte ptr [rcx+1Ch], 1
0x18000bcbd  jz      short loc_18000BCD4
0x18000bcbf  mov     edx, 42h ; 'B'
0x18000bcc4  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bccb  mov     rcx, [rcx+10h]
0x18000bccf  call    WPP_SF_
0x18000bcd4  mov     eax, 1
0x18000bcd9  jmp     short loc_18000BD59
0x18000bcdb  mov     ebx, eax
0x18000bcdd  mov     [rsp+68h+var_20], eax
0x18000bce1  lea     rdx, WPP_GLOBAL_Control
0x18000bce8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bcef  cmp     rcx, rdx
0x18000bcf2  jz      short loc_18000BD12
0x18000bcf4  test    byte ptr [rcx+1Ch], 2
0x18000bcf8  jz      short loc_18000BD12
0x18000bcfa  mov     edx, 41h ; 'A'
0x18000bcff  mov     r9d, eax
0x18000bd02  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bd09  mov     rcx, [rcx+10h]
0x18000bd0d  call    WPP_SF_d
0x18000bd12  lea     rdi, WPP_GLOBAL_Control
0x18000bd19  lea     rcx, [rsp+68h+Binding]; Binding
0x18000bd21  call    cs:__imp_RpcBindingFree
0x18000bd28  nop     dword ptr [rax+rax+00h]
0x18000bd2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd34  cmp     rcx, rdi
0x18000bd37  jz      short loc_18000BD57
0x18000bd39  test    byte ptr [rcx+1Ch], 2
0x18000bd3d  jz      short loc_18000BD57
0x18000bd3f  mov     edx, 43h ; 'C'
0x18000bd44  mov     r9d, ebx
0x18000bd47  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bd4e  mov     rcx, [rcx+10h]
0x18000bd52  call    WPP_SF_d
0x18000bd57  xor     eax, eax
0x18000bd59  mov     rbx, [rsp+68h+arg_0]
0x18000bd5e  add     rsp, 50h
0x18000bd62  pop     r14
0x18000bd64  pop     rdi
0x18000bd65  pop     rsi
0x18000bd66  retn
0x18001344a  push    rbp
0x18001344c  sub     rsp, 40h
0x180013450  mov     rbp, rdx
0x180013453  mov     rax, [rcx]
0x180013456  mov     edx, [rax]
0x180013458  mov     dword ptr [rbp+40h], 0
0x18001345f  mov     dword ptr [rbp+40h], 0
0x180013466  mov     eax, [rbp+40h]
0x180013469  cmp     eax, 8
0x18001346c  jge     short loc_180013491
0x18001346e  movsxd  rcx, dword ptr [rbp+40h]
0x180013472  lea     rax, FatalExceptions
0x180013479  cmp     edx, [rax+rcx*4]
0x18001347c  jnz     short loc_180013487
0x18001347e  mov     dword ptr [rbp+44h], 0
0x180013485  jmp     short loc_180013498
0x180013487  mov     eax, [rbp+40h]
0x18001348a  inc     eax
0x18001348c  mov     [rbp+40h], eax
0x18001348f  jmp     short loc_180013466
0x180013491  mov     dword ptr [rbp+44h], 1
0x180013498  mov     eax, [rbp+44h]
0x18001349b  add     rsp, 40h
0x18001349f  pop     rbp
0x1800134a0  retn
```
