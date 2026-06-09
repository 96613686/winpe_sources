# KapiReceiveKaUpdateRequestCompletion

- ea: `0x180002cc0`
- end: `0x18000309d`
- name: `KapiReceiveKaUpdateRequestCompletion`
- size: `989`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001e20`
- `0x180001f9c`
- `0x180002024`
- `0x180002cc0`
- `0x1800032c0`
- `0x180003304`
- `0x180004010`

## import_xrefs

- `RPCRT4!Ndr64AsyncClientCall` at `0x180002f37`
- `RPCRT4!Ndr64AsyncClientCall` at `0x180002f37`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800035ff`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800035ff`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180002ea6`
- `RPCRT4!RpcAsyncInitializeHandle` at `0x180002ea6`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180002d23`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180002d23`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall KapiReceiveKaUpdateRequestCompletion(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // r8
  unsigned int v5; // r15d
  _DWORD *v6; // r14
  _QWORD *v7; // r15
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // eax
  __int64 v13; // r8
  _QWORD *v14; // rcx
  CLIENT_CALL_RETURN result; // rax
  __int64 v16; // rdx
  unsigned int Reply; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  Reply = 0;
  v2 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)(a1 + 24), &Reply);
  v5 = v2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, v4, v2);
  }
  v6 = (_DWORD *)(a1 + 16);
  v18 = a1 + 16;
  *(_DWORD *)(a1 + 16) = 0;
  if ( v5 || Reply )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), v3, v4, v5, Reply);
      goto LABEL_42;
    }
    goto LABEL_43;
  }
  v7 = (_QWORD *)(a1 + 168);
  if ( *(_QWORD *)(a1 + 208) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 192))(*v7, *(_QWORD *)(a1 + 176));
    FreeNetworkGuidsHelper(*(LPVOID *)(a1 + 208));
    *(_QWORD *)(a1 + 208) = 0;
  }
  if ( *(_QWORD *)(a1 + 216) )
    ((void (*)(void))FreeSampleSetHelper)();
  *(_QWORD *)(a1 + 200) = *(_QWORD *)(a1 + 136);
  v8 = *(_QWORD *)(a1 + 152);
  *(_QWORD *)(a1 + 216) = v8;
  v9 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 208) = v9;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  if ( v9 )
  {
    if ( v8 )
    {
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(a1 + 184))(*v7, a1, v8, a1 + 176);
      Reply = v10;
      if ( v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, v11, v10);
        }
        FreeSampleSetHelper(*(_QWORD *)(a1 + 216));
        *(_QWORD *)(a1 + 216) = 0;
      }
    }
    if ( !*(_QWORD *)(a1 + 216) )
    {
      FreeNetworkGuidsHelper(*(LPVOID *)(a1 + 208));
      *(_QWORD *)(a1 + 208) = 0;
    }
  }
  else if ( v8 )
  {
    ((void (*)(void))FreeSampleSetHelper)();
    *(_QWORD *)(a1 + 216) = 0;
  }
  v12 = RpcAsyncInitializeHandle((PRPC_ASYNC_STATE)(a1 + 24), 0x70u);
  if ( v12 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, v13, v12);
LABEL_42:
      v14 = WPP_GLOBAL_Control;
    }
LABEL_43:
    if ( *(_QWORD *)(a1 + 208) )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 192))(*(_QWORD *)(a1 + 168), *(_QWORD *)(a1 + 176));
      FreeNetworkGuidsHelper(*(LPVOID *)(a1 + 208));
      *(_QWORD *)(a1 + 208) = 0;
      v14 = WPP_GLOBAL_Control;
    }
    result.Pointer = *(void **)(a1 + 216);
    if ( result.Simple )
    {
      result.Simple = FreeSampleSetHelper(*(_QWORD *)(a1 + 216));
      *(_QWORD *)(a1 + 216) = 0;
      v14 = WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 6u )
    {
      v16 = 60;
      return (CLIENT_CALL_RETURN)WPP_SF_(v14[2], v16, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
    }
    return result;
  }
  *v6 = 1;
  result.Pointer = Ndr64AsyncClientCall(
                     (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                     3u,
                     0,
                     a1 + 24,
                     *(_QWORD *)a1,
                     *(_QWORD *)(a1 + 8),
                     a1 + 136,
                     a1 + 144,
                     a1 + 152).Pointer;
  v14 = WPP_GLOBAL_Control;
  if ( Reply )
  {
    *v6 = 0;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v16 = 59;
    return (CLIENT_CALL_RETURN)WPP_SF_(v14[2], v16, &WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180002cc0  mov     [rsp+arg_0], rcx
0x180002cc5  push    rbx
0x180002cc6  push    rsi
0x180002cc7  push    rdi
0x180002cc8  push    r12
0x180002cca  push    r13
0x180002ccc  push    r14
0x180002cce  push    r15
0x180002cd0  sub     rsp, 50h
0x180002cd4  mov     rbx, rcx
0x180002cd7  lea     rsi, WPP_GLOBAL_Control
0x180002cde  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ce5  cmp     rcx, rsi
0x180002ce8  jz      short loc_180002D0B
0x180002cea  test    byte ptr [rcx+1Ch], 1
0x180002cee  jz      short loc_180002D0B
0x180002cf0  cmp     byte ptr [rcx+19h], 6
0x180002cf4  jb      short loc_180002D0B
0x180002cf6  mov     edx, 35h ; '5'
0x180002cfb  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180002d02  mov     rcx, [rcx+10h]
0x180002d06  call    WPP_SF_
0x180002d0b  xor     edi, edi
0x180002d0d  mov     [rsp+88h+Reply], edi
0x180002d14  lea     r13, [rbx+18h]
0x180002d18  lea     rdx, [rsp+88h+Reply]; Reply
0x180002d20  mov     rcx, r13; pAsync
0x180002d23  call    cs:__imp_RpcAsyncCompleteCall
0x180002d29  mov     r15d, eax
0x180002d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d33  cmp     rcx, rsi
0x180002d36  jz      short loc_180002D53
0x180002d38  test    byte ptr [rcx+1Ch], 1
0x180002d3c  jz      short loc_180002D53
0x180002d3e  cmp     byte ptr [rcx+19h], 5
0x180002d42  jb      short loc_180002D53
0x180002d44  lea     edx, [rdi+36h]
0x180002d47  mov     r9d, eax
0x180002d4a  mov     rcx, [rcx+10h]
0x180002d4e  call    WPP_SF_D
0x180002d53  lea     r14, [rbx+10h]
0x180002d57  mov     [rsp+88h+arg_18], r14
0x180002d5f  mov     [r14], edi
0x180002d62  test    r15d, r15d
0x180002d65  jnz     loc_180002FD2
0x180002d6b  cmp     [rsp+88h+Reply], edi
0x180002d72  jnz     loc_180002FD2
0x180002d78  lea     r12, [rbx+0B0h]
0x180002d7f  lea     r15, [rbx+0A8h]
0x180002d86  cmp     [rbx+0D0h], rdi
0x180002d8d  jz      short loc_180002DB5
0x180002d8f  mov     rdx, [r12]
0x180002d93  mov     rcx, [r15]
0x180002d96  mov     rax, [rbx+0C0h]
0x180002d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da2  mov     rcx, [rbx+0D0h]; lpMem
0x180002da9  call    FreeNetworkGuidsHelper
0x180002dae  mov     [rbx+0D0h], rdi
0x180002db5  mov     rcx, [rbx+0D8h]
0x180002dbc  test    rcx, rcx
0x180002dbf  jz      short loc_180002DC6
0x180002dc1  call    FreeSampleSetHelper
0x180002dc6  lea     rdx, [rbx+88h]
0x180002dcd  mov     rax, [rdx]
0x180002dd0  mov     [rbx+0C8h], rax
0x180002dd7  lea     r8, [rbx+98h]
0x180002dde  mov     rcx, [r8]
0x180002de1  mov     [rbx+0D8h], rcx
0x180002de8  lea     r9, [rbx+90h]
0x180002def  mov     rax, [r9]
0x180002df2  mov     [rbx+0D0h], rax
0x180002df9  mov     [rdx], rdi
0x180002dfc  mov     [r8], rdi
0x180002dff  mov     [r9], rdi
0x180002e02  test    rax, rax
0x180002e05  jz      loc_180002E8D
0x180002e0b  test    rcx, rcx
0x180002e0e  jz      short loc_180002E6F
0x180002e10  mov     r9, r12
0x180002e13  mov     r8, rcx
0x180002e16  mov     rdx, rbx
0x180002e19  mov     rcx, [r15]
0x180002e1c  mov     rax, [rbx+0B8h]
0x180002e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e28  mov     [rsp+88h+Reply], eax
0x180002e2f  test    eax, eax
0x180002e31  jz      short loc_180002E6F
0x180002e33  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e3a  cmp     rcx, rsi
0x180002e3d  jz      short loc_180002E5C
0x180002e3f  test    byte ptr [rcx+1Ch], 1
0x180002e43  jz      short loc_180002E5C
0x180002e45  cmp     byte ptr [rcx+19h], 2
0x180002e49  jb      short loc_180002E5C
0x180002e4b  mov     edx, 38h ; '8'
0x180002e50  mov     r9d, eax
0x180002e53  mov     rcx, [rcx+10h]
0x180002e57  call    WPP_SF_D
0x180002e5c  mov     rcx, [rbx+0D8h]
0x180002e63  call    FreeSampleSetHelper
0x180002e68  mov     [rbx+0D8h], rdi
0x180002e6f  cmp     [rbx+0D8h], rdi
0x180002e76  jnz     short loc_180002E9E
0x180002e78  mov     rcx, [rbx+0D0h]; lpMem
0x180002e7f  call    FreeNetworkGuidsHelper
0x180002e84  mov     [rbx+0D0h], rdi
0x180002e8b  jmp     short loc_180002E9E
0x180002e8d  test    rcx, rcx
0x180002e90  jz      short loc_180002E9E
0x180002e92  call    FreeSampleSetHelper
0x180002e97  mov     [rbx+0D8h], rdi
0x180002e9e  mov     edx, 70h ; 'p'; Size
0x180002ea3  mov     rcx, r13; pAsync
0x180002ea6  call    cs:__imp_RpcAsyncInitializeHandle
0x180002eac  test    eax, eax
0x180002eae  jz      short loc_180002EEA
0x180002eb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb7  cmp     rcx, rsi
0x180002eba  jz      loc_180003008
0x180002ec0  test    byte ptr [rcx+1Ch], 1
0x180002ec4  jz      loc_180003008
0x180002eca  cmp     byte ptr [rcx+19h], 2
0x180002ece  jb      loc_180003008
0x180002ed4  mov     edx, 39h ; '9'
0x180002ed9  mov     r9d, eax
0x180002edc  mov     rcx, [rcx+10h]
0x180002ee0  call    WPP_SF_D
0x180002ee5  jmp     loc_180003001
0x180002eea  mov     dword ptr [r14], 1
0x180002ef1  lea     rax, [rbx+98h]
0x180002ef8  mov     [rsp+88h+var_48], rax
0x180002efd  lea     rax, [rbx+90h]
0x180002f04  mov     [rsp+88h+var_50], rax
0x180002f09  lea     rax, [rbx+88h]
0x180002f10  mov     [rsp+88h+var_58], rax
0x180002f15  mov     rax, [rbx+8]
0x180002f19  mov     [rsp+88h+var_60], rax
0x180002f1e  mov     rax, [rbx]
0x180002f21  mov     [rsp+88h+var_68], rax
0x180002f26  mov     r9, r13
0x180002f29  xor     r8d, r8d; pReturnValue
0x180002f2c  lea     edx, [r8+3]; nProcNum
0x180002f30  lea     rcx, pProxyInfo; pProxyInfo
0x180002f37  call    cs:__imp_Ndr64AsyncClientCall
0x180002f3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f44  jmp     short loc_180002F9D
0x180002f46  mov     [rsp+88h+Reply], eax
0x180002f4d  lea     rax, WPP_GLOBAL_Control
0x180002f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f5b  cmp     rcx, rax
0x180002f5e  jz      short loc_180002F84
0x180002f60  test    byte ptr [rcx+1Ch], 1
0x180002f64  jz      short loc_180002F84
0x180002f66  cmp     byte ptr [rcx+19h], 2
0x180002f6a  jb      short loc_180002F84
0x180002f6c  mov     edx, 3Ah ; ':'
0x180002f71  xor     r9d, r9d
0x180002f74  mov     rcx, [rcx+10h]
0x180002f78  call    WPP_SF_D
0x180002f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f84  lea     rsi, WPP_GLOBAL_Control
0x180002f8b  xor     edi, edi
0x180002f8d  mov     rbx, [rsp+88h+arg_0]
0x180002f95  mov     r14, [rsp+88h+arg_18]
0x180002f9d  cmp     [rsp+88h+Reply], edi
0x180002fa4  jz      short loc_180002FAB
0x180002fa6  mov     [r14], edi
0x180002fa9  jmp     short loc_180003001
0x180002fab  cmp     rcx, rsi
0x180002fae  jz      loc_18000308D
0x180002fb4  test    byte ptr [rcx+1Ch], 1
0x180002fb8  jz      loc_18000308D
0x180002fbe  cmp     byte ptr [rcx+19h], 6
0x180002fc2  jb      loc_18000308D
0x180002fc8  mov     edx, 3Bh ; ';'
0x180002fcd  jmp     loc_18000307D
0x180002fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fd9  cmp     rcx, rsi
0x180002fdc  jz      short loc_180003008
0x180002fde  test    byte ptr [rcx+1Ch], 1
0x180002fe2  jz      short loc_180003008
0x180002fe4  cmp     byte ptr [rcx+19h], 2
0x180002fe8  jb      short loc_180003008
0x180002fea  mov     eax, [rsp+88h+Reply]
0x180002ff1  mov     dword ptr [rsp+88h+var_68], eax
0x180002ff5  mov     r9d, r15d
0x180002ff8  mov     rcx, [rcx+10h]
0x180002ffc  call    WPP_SF_DD
0x180003001  mov     rcx, cs:WPP_GLOBAL_Control
0x180003008  cmp     [rbx+0D0h], rdi
0x18000300f  jz      short loc_180003045
0x180003011  mov     rdx, [rbx+0B0h]
0x180003018  mov     rcx, [rbx+0A8h]
0x18000301f  mov     rax, [rbx+0C0h]
0x180003026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302b  mov     rcx, [rbx+0D0h]; lpMem
0x180003032  call    FreeNetworkGuidsHelper
0x180003037  mov     [rbx+0D0h], rdi
0x18000303e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003045  mov     rax, [rbx+0D8h]
0x18000304c  test    rax, rax
0x18000304f  jz      short loc_180003067
0x180003051  mov     rcx, rax
0x180003054  call    FreeSampleSetHelper
0x180003059  mov     [rbx+0D8h], rdi
0x180003060  mov     rcx, cs:WPP_GLOBAL_Control
0x180003067  cmp     rcx, rsi
0x18000306a  jz      short loc_18000308D
0x18000306c  test    byte ptr [rcx+1Ch], 1
0x180003070  jz      short loc_18000308D
0x180003072  cmp     byte ptr [rcx+19h], 6
0x180003076  jb      short loc_18000308D
0x180003078  mov     edx, 3Ch ; '<'
0x18000307d  lea     r8, WPP_2b2e2230f10e328e3975e63995ea3324_Traceguids
0x180003084  mov     rcx, [rcx+10h]
0x180003088  call    WPP_SF_
0x18000308d  add     rsp, 50h
0x180003091  pop     r15
0x180003093  pop     r14
0x180003095  pop     r13
0x180003097  pop     r12
0x180003099  pop     rdi
0x18000309a  pop     rsi
0x18000309b  pop     rbx
0x18000309c  retn
0x1800035f1  push    rbp
0x1800035f3  sub     rsp, 50h
0x1800035f7  mov     rbp, rdx
0x1800035fa  mov     rcx, [rcx]
0x1800035fd  mov     ecx, [rcx]; ExceptionCode
0x1800035ff  call    cs:__imp_I_RpcExceptionFilter
0x180003605  nop
0x180003606  add     rsp, 50h
0x18000360a  pop     rbp
0x18000360b  retn
```
