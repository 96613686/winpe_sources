# RpcAsyncDoPlap

- ea: `0x180014d90`
- end: `0x180014f7d`
- name: `RpcAsyncDoPlap`
- size: `493`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x1800106ec`
- `0x180014d90`
- `0x180017a68`
- `0x180025e58`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180014f14`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014f14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f39`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014f39`

## pseudocode

```c
int __fastcall RpcAsyncDoPlap(
        PRPC_ASYNC_STATE pAsync,
        __int64 a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned int a5,
        struct _PLAP_INPUT_FIELD_DATA *a6)
{
  HANDLE v6; // rbx
  struct _LIST_ENTRY *v10; // rcx
  struct _LIST_ENTRY **v11; // rax
  unsigned int v12; // edi
  struct _PLAP_INPUT_FIELD_DATA *v13; // rsi
  __int64 v14; // rcx
  const unsigned __int16 *v15; // r9
  HANDLE hObject; // [rsp+40h] [rbp-18h] BYREF
  void *v18; // [rsp+48h] [rbp-10h] BYREF
  unsigned int Reply; // [rsp+90h] [rbp+38h] BYREF

  v6 = 0;
  Reply = 0;
  hObject = 0;
  v18 = 0;
  v10 = WPP_GLOBAL_Control;
  v11 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    LODWORD(v11) = WPP_SF_(WPP_GLOBAL_Control[1].Flink, 80, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( pAsync && a3 && a4 && (v12 = a5) != 0 && (v13 = a6) != 0 )
  {
    LODWORD(v11) = WimGetInterfaceContextHandle(a3, &v18);
    Reply = (unsigned int)v11;
    if ( (_DWORD)v11 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        return (int)v11;
      if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        LODWORD(v11) = WPP_SF_d(
                         WPP_GLOBAL_Control[1].Flink,
                         81,
                         WPP_b4750df92381326559acc6db9e2d425d_Traceguids,
                         (unsigned int)v11);
LABEL_27:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_28;
      }
      goto LABEL_28;
    }
    LODWORD(v11) = GetClientToken(v14, &hObject);
    Reply = (unsigned int)v11;
    if ( (_DWORD)v11 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control[1].Blink)
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        LODWORD(v11) = WPP_SF_d(
                         WPP_GLOBAL_Control[1].Flink,
                         82,
                         WPP_b4750df92381326559acc6db9e2d425d_Traceguids,
                         (unsigned int)v11);
        v10 = WPP_GLOBAL_Control;
        v6 = hObject;
      }
      else
      {
        v6 = hObject;
      }
    }
    else
    {
      v6 = hObject;
      LODWORD(v11) = IntfDoPlapOrTimely(1, pAsync, v18, v15, v12, v13, hObject, 0);
      Reply = (unsigned int)v11;
      if ( (_DWORD)v11 )
        LODWORD(v11) = RpcAsyncCompleteCall(pAsync, &Reply);
      v10 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    Reply = 87;
  }
  if ( v6 )
  {
    LODWORD(v11) = CloseHandle(v6);
    goto LABEL_27;
  }
LABEL_28:
  if ( v10 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v10[1].Blink) >= 4u && (BYTE4(v10[1].Blink) & 1) != 0 )
    LODWORD(v11) = WPP_SF_d(v10[1].Flink, 83, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, Reply);
  return (int)v11;
}

```

## disassembly

```asm
0x180014d90  push    rbp
0x180014d92  push    rbx
0x180014d93  push    rsi
0x180014d94  push    rdi
0x180014d95  push    r14
0x180014d97  push    r15
0x180014d99  mov     rbp, rsp
0x180014d9c  sub     rsp, 58h
0x180014da0  xor     ebx, ebx
0x180014da2  mov     [rbp+Reply], 0
0x180014da9  mov     [rbp+hObject], rbx
0x180014dad  mov     rdi, r9
0x180014db0  mov     r15, r8
0x180014db3  mov     [rbp+var_10], 0
0x180014dbb  mov     r14, rcx
0x180014dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180014dc5  lea     rax, WPP_GLOBAL_Control
0x180014dcc  cmp     rcx, rax
0x180014dcf  jz      short loc_180014DF7
0x180014dd1  cmp     byte ptr [rcx+19h], 4
0x180014dd5  jb      short loc_180014DF7
0x180014dd7  test    byte ptr [rcx+1Ch], 1
0x180014ddb  jz      short loc_180014DF7
0x180014ddd  mov     rcx, [rcx+10h]
0x180014de1  lea     edx, [rbx+50h]
0x180014de4  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014deb  call    WPP_SF_
0x180014df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180014df7  test    r14, r14
0x180014dfa  jz      loc_180014F23
0x180014e00  test    r15, r15
0x180014e03  jz      loc_180014F23
0x180014e09  test    rdi, rdi
0x180014e0c  jz      loc_180014F23
0x180014e12  mov     edi, [rbp+arg_20]
0x180014e15  test    edi, edi
0x180014e17  jz      loc_180014F23
0x180014e1d  mov     rsi, [rbp+arg_28]
0x180014e21  test    rsi, rsi
0x180014e24  jz      loc_180014F23
0x180014e2a  lea     rdx, [rbp+var_10]; void **
0x180014e2e  mov     rcx, r15; struct _GUID *
0x180014e31  call    ?WimGetInterfaceContextHandle@@YAKPEBU_GUID@@PEAPEAX@Z; WimGetInterfaceContextHandle(_GUID const *,void * *)
0x180014e36  mov     [rbp+Reply], eax
0x180014e39  test    eax, eax
0x180014e3b  jz      short loc_180014E85
0x180014e3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e44  lea     rdi, WPP_GLOBAL_Control
0x180014e4b  cmp     rcx, rdi
0x180014e4e  jz      loc_180014F70
0x180014e54  cmp     byte ptr [rcx+19h], 1
0x180014e58  jb      loc_180014F46
0x180014e5e  test    byte ptr [rcx+1Ch], 1
0x180014e62  jz      loc_180014F46
0x180014e68  mov     rcx, [rcx+10h]
0x180014e6c  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014e73  mov     edx, 51h ; 'Q'
0x180014e78  mov     r9d, eax
0x180014e7b  call    WPP_SF_d
0x180014e80  jmp     loc_180014F3F
0x180014e85  lea     rdx, [rbp+hObject]; void **
0x180014e89  call    ?GetClientToken@@YAKHPEAPEAX@Z; GetClientToken(int,void * *)
0x180014e8e  mov     [rbp+Reply], eax
0x180014e91  test    eax, eax
0x180014e93  jz      short loc_180014EDF
0x180014e95  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e9c  lea     rdi, WPP_GLOBAL_Control
0x180014ea3  cmp     rcx, rdi
0x180014ea6  jz      short loc_180014ED9
0x180014ea8  cmp     byte ptr [rcx+19h], 1
0x180014eac  jb      short loc_180014ED9
0x180014eae  test    byte ptr [rcx+1Ch], 1
0x180014eb2  jz      short loc_180014ED9
0x180014eb4  mov     rcx, [rcx+10h]
0x180014eb8  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014ebf  mov     edx, 52h ; 'R'
0x180014ec4  mov     r9d, eax
0x180014ec7  call    WPP_SF_d
0x180014ecc  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ed3  mov     rbx, [rbp+hObject]
0x180014ed7  jmp     short loc_180014F31
0x180014ed9  mov     rbx, [rbp+hObject]
0x180014edd  jmp     short loc_180014F31
0x180014edf  mov     r8, [rbp+var_10]; void *
0x180014ee3  mov     rdx, r14; struct _RPC_ASYNC_STATE *
0x180014ee6  mov     [rsp+58h+var_20], ebx; unsigned int
0x180014eea  mov     ecx, 1; int
0x180014eef  mov     rbx, [rbp+hObject]
0x180014ef3  mov     [rsp+58h+hSourceHandle], rbx; hSourceHandle
0x180014ef8  mov     [rsp+58h+var_30], rsi; struct _PLAP_INPUT_FIELD_DATA *
0x180014efd  mov     [rsp+58h+var_38], edi; unsigned int
0x180014f01  call    ?IntfDoPlapOrTimely@@YAKHPEAU_RPC_ASYNC_STATE@@PEAXPEBGKQEAU_PLAP_INPUT_FIELD_DATA@@1K@Z; IntfDoPlapOrTimely(int,_RPC_ASYNC_STATE *,void *,ushort const *,ulong,_PLAP_INPUT_FIELD_DATA * const,void *,ulong)
0x180014f06  mov     [rbp+Reply], eax
0x180014f09  test    eax, eax
0x180014f0b  jz      short loc_180014F1A
0x180014f0d  lea     rdx, [rbp+Reply]; Reply
0x180014f11  mov     rcx, r14; pAsync
0x180014f14  call    cs:__imp_RpcAsyncCompleteCall
0x180014f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f21  jmp     short loc_180014F2A
0x180014f23  mov     [rbp+Reply], 57h ; 'W'
0x180014f2a  lea     rdi, WPP_GLOBAL_Control
0x180014f31  test    rbx, rbx
0x180014f34  jz      short loc_180014F46
0x180014f36  mov     rcx, rbx; hObject
0x180014f39  call    cs:__imp_CloseHandle
0x180014f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f46  cmp     rcx, rdi
0x180014f49  jz      short loc_180014F70
0x180014f4b  cmp     byte ptr [rcx+19h], 4
0x180014f4f  jb      short loc_180014F70
0x180014f51  test    byte ptr [rcx+1Ch], 1
0x180014f55  jz      short loc_180014F70
0x180014f57  mov     r9d, [rbp+Reply]
0x180014f5b  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014f62  mov     rcx, [rcx+10h]
0x180014f66  mov     edx, 53h ; 'S'
0x180014f6b  call    WPP_SF_d
0x180014f70  add     rsp, 58h
0x180014f74  pop     r15
0x180014f76  pop     r14
0x180014f78  pop     rdi
0x180014f79  pop     rsi
0x180014f7a  pop     rbx
0x180014f7b  pop     rbp
0x180014f7c  retn
```
