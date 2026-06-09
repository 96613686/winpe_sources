# RemoveDeviceEntry

- ea: `0x18000bda4`
- end: `0x18000bf95`
- name: `RemoveDeviceEntry`
- size: `497`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005c40`

## callees

- `0x180002508`
- `0x180002538`
- `0x18000bda4`
- `0x18000c220`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18000becb`
- `RPCRT4!RpcBindingFree` at `0x18000bf48`
- `RPCRT4!RpcBindingFree` at `0x18000becb`
- `RPCRT4!RpcBindingFree` at `0x18000bf48`
- `RPCRT4!NdrClientCall3` at `0x18000be78`
- `RPCRT4!NdrClientCall3` at `0x18000be78`

## pseudocode

```c
__int64 __fastcall RemoveDeviceEntry(int a1, __int64 a2)
{
  unsigned int v4; // eax
  unsigned int Pointer; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rax
  CLIENT_CALL_RETURN v8; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+88h] [rbp+20h]

  Binding = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  v4 = RpcBindForNfsClient(&Binding);
  Pointer = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return Pointer;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_20:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
        WPP_SF_d(v6[2], 88, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, Pointer);
      return Pointer;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_7b522c97afb2341f13613538df880a66_Traceguids, v4);
LABEL_19:
    v6 = WPP_GLOBAL_Control;
    goto LABEL_20;
  }
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(a2 + 2 * v7) );
  v11.Simple = 0;
  v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, Binding, a1, (int)v7 + 1, a2).Pointer;
  Pointer = (unsigned int)v8.Pointer;
  v11.Pointer = v8.Pointer;
  if ( LODWORD(v8.Pointer) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        &WPP_7b522c97afb2341f13613538df880a66_Traceguids,
        LODWORD(v8.Pointer));
    RpcBindingFree(&Binding);
    goto LABEL_19;
  }
  RpcBindingFree(&Binding);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_7b522c97afb2341f13613538df880a66_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x18000bda4  mov     rax, rsp
0x18000bda7  mov     [rax+8], rbx
0x18000bdab  mov     [rax+10h], rsi
0x18000bdaf  push    rdi
0x18000bdb0  push    r14
0x18000bdb2  push    r15
0x18000bdb4  sub     rsp, 50h
0x18000bdb8  mov     rsi, rdx
0x18000bdbb  mov     r14d, ecx
0x18000bdbe  xor     r15d, r15d
0x18000bdc1  mov     [rax+18h], r15
0x18000bdc5  lea     rdi, WPP_GLOBAL_Control
0x18000bdcc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bdd3  cmp     rcx, rdi
0x18000bdd6  jz      short loc_18000BDF2
0x18000bdd8  test    byte ptr [rcx+1Ch], 1
0x18000bddc  jz      short loc_18000BDF2
0x18000bdde  lea     edx, [r15+53h]
0x18000bde2  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bde9  mov     rcx, [rcx+10h]
0x18000bded  call    WPP_SF_
0x18000bdf2  lea     rcx, [rsp+68h+Binding]
0x18000bdfa  call    RpcBindForNfsClient
0x18000bdff  mov     ebx, eax
0x18000be01  test    eax, eax
0x18000be03  jz      short loc_18000BE3C
0x18000be05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be0c  cmp     rcx, rdi
0x18000be0f  jz      loc_18000BF7E
0x18000be15  test    byte ptr [rcx+1Ch], 2
0x18000be19  jz      loc_18000BF5B
0x18000be1f  mov     edx, 54h ; 'T'
0x18000be24  mov     r9d, eax
0x18000be27  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000be2e  mov     rcx, [rcx+10h]
0x18000be32  call    WPP_SF_d
0x18000be37  jmp     loc_18000BF54
0x18000be3c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000be40  inc     rax
0x18000be43  cmp     [rsi+rax*2], r15w
0x18000be48  jnz     short loc_18000BE40
0x18000be4a  inc     eax
0x18000be4c  mov     [rsp+68h+arg_18], r15
0x18000be54  mov     [rsp+68h+var_38], rsi
0x18000be59  mov     [rsp+68h+var_40], eax
0x18000be5d  mov     [rsp+68h+var_48], r14d
0x18000be62  mov     r9, [rsp+68h+Binding]
0x18000be6a  xor     r8d, r8d; pReturnValue
0x18000be6d  lea     edx, [r8+2]; nProcNum
0x18000be71  lea     rcx, pProxyInfo; pProxyInfo
0x18000be78  call    cs:__imp_NdrClientCall3
0x18000be7f  nop     dword ptr [rax+rax+00h]
0x18000be84  mov     rbx, rax
0x18000be87  mov     [rsp+68h+arg_18], rax
0x18000be8f  mov     [rsp+68h+var_20], eax
0x18000be93  test    eax, eax
0x18000be95  jz      short loc_18000BEC3
0x18000be97  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be9e  cmp     rcx, rdi
0x18000bea1  jz      short loc_18000BEC1
0x18000bea3  test    byte ptr [rcx+1Ch], 2
0x18000bea7  jz      short loc_18000BEC1
0x18000bea9  mov     edx, 55h ; 'U'
0x18000beae  mov     r9d, eax
0x18000beb1  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000beb8  mov     rcx, [rcx+10h]
0x18000bebc  call    WPP_SF_d
0x18000bec1  jmp     short loc_18000BF40
0x18000bec3  lea     rcx, [rsp+68h+Binding]; Binding
0x18000becb  call    cs:__imp_RpcBindingFree
0x18000bed2  nop     dword ptr [rax+rax+00h]
0x18000bed7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bede  cmp     rcx, rdi
0x18000bee1  jz      short loc_18000BEFE
0x18000bee3  test    byte ptr [rcx+1Ch], 1
0x18000bee7  jz      short loc_18000BEFE
0x18000bee9  mov     edx, 57h ; 'W'
0x18000beee  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bef5  mov     rcx, [rcx+10h]
0x18000bef9  call    WPP_SF_
0x18000befe  xor     eax, eax
0x18000bf00  jmp     short loc_18000BF80
0x18000bf02  mov     ebx, eax
0x18000bf04  mov     [rsp+68h+var_20], eax
0x18000bf08  lea     rdx, WPP_GLOBAL_Control
0x18000bf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf16  cmp     rcx, rdx
0x18000bf19  jz      short loc_18000BF39
0x18000bf1b  test    byte ptr [rcx+1Ch], 2
0x18000bf1f  jz      short loc_18000BF39
0x18000bf21  mov     edx, 56h ; 'V'
0x18000bf26  mov     r9d, eax
0x18000bf29  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bf30  mov     rcx, [rcx+10h]
0x18000bf34  call    WPP_SF_d
0x18000bf39  lea     rdi, WPP_GLOBAL_Control
0x18000bf40  lea     rcx, [rsp+68h+Binding]; Binding
0x18000bf48  call    cs:__imp_RpcBindingFree
0x18000bf4f  nop     dword ptr [rax+rax+00h]
0x18000bf54  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bf5b  cmp     rcx, rdi
0x18000bf5e  jz      short loc_18000BF7E
0x18000bf60  test    byte ptr [rcx+1Ch], 2
0x18000bf64  jz      short loc_18000BF7E
0x18000bf66  mov     edx, 58h ; 'X'
0x18000bf6b  mov     r9d, ebx
0x18000bf6e  lea     r8, WPP_7b522c97afb2341f13613538df880a66_Traceguids
0x18000bf75  mov     rcx, [rcx+10h]
0x18000bf79  call    WPP_SF_d
0x18000bf7e  mov     eax, ebx
0x18000bf80  mov     rbx, [rsp+68h+arg_0]
0x18000bf85  mov     rsi, [rsp+68h+arg_8]
0x18000bf8a  add     rsp, 50h
0x18000bf8e  pop     r15
0x18000bf90  pop     r14
0x18000bf92  pop     rdi
0x18000bf93  retn
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
