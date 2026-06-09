# LocalSendNotificaton(_RPC_CLIENT_INFO *)

- ea: `0x180014a40`
- end: `0x180014b74`
- name: `?LocalSendNotificaton@@YAKPEAU_RPC_CLIENT_INFO@@@Z`
- size: `308`
- prototype: `RPC_STATUS __fastcall(struct _RPC_CLIENT_INFO *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013e7c`
- `0x180014f90`

## callees

- `0x18000a9c0`
- `0x18000c230`
- `0x180012cc4`
- `0x180012e44`
- `0x180014a40`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180014af7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180014af7`

## pseudocode

```c
RPC_STATUS __fastcall LocalSendNotificaton(struct _RPC_CLIENT_INFO *a1)
{
  struct _LIST_ENTRY *v2; // rcx
  RPC_STATUS result; // eax
  struct _RPC_ASYNC_STATE *v4; // rsi
  struct _L2_NOTIFICATION_DATA **v5; // rdx
  unsigned int Reply; // [rsp+50h] [rbp+8h] BYREF

  Reply = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 19, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    result = 87;
LABEL_7:
    Reply = result;
    goto LABEL_18;
  }
  v4 = (struct _RPC_ASYNC_STATE *)*((_QWORD *)a1 + 3);
  if ( !v4 )
  {
    result = 13;
    goto LABEL_7;
  }
  NhFreeNotification(*((struct _L2_NOTIFICATION_DATA **)a1 + 263));
  v5 = (struct _L2_NOTIFICATION_DATA **)*((_QWORD *)a1 + 4);
  *((_QWORD *)a1 + 263) = 0;
  if ( NhDupNotification((struct _L2_NOTIFICATION_DATA **)a1 + 263, *v5) )
    *((_QWORD *)a1 + 263) = 0;
  *((_QWORD *)a1 + 3) = 0;
  *((_QWORD *)a1 + 4) = 0;
  result = RpcAsyncCompleteCall(v4, &Reply);
  Reply = result;
  if ( !result )
  {
LABEL_17:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return result;
  if ( BYTE1(WPP_GLOBAL_Control[1].Blink) && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 20, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
    result = Reply;
    goto LABEL_17;
  }
LABEL_18:
  if ( v2 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && BYTE1(v2[1].Blink) >= 4u && (BYTE4(v2[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(v2[1].Flink, 21, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, (unsigned int)result);
    return Reply;
  }
  return result;
}

```

## disassembly

```asm
0x180014a40  push    rbx
0x180014a42  push    rsi
0x180014a43  push    rdi
0x180014a44  push    r15
0x180014a46  sub     rsp, 28h
0x180014a4a  mov     rbx, rcx
0x180014a4d  mov     [rsp+48h+Reply], 0
0x180014a55  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a5c  lea     r15, WPP_GLOBAL_Control
0x180014a63  cmp     rcx, r15
0x180014a66  jz      short loc_180014A90
0x180014a68  cmp     byte ptr [rcx+19h], 4
0x180014a6c  jb      short loc_180014A90
0x180014a6e  test    byte ptr [rcx+1Ch], 1
0x180014a72  jz      short loc_180014A90
0x180014a74  mov     rcx, [rcx+10h]
0x180014a78  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014a7f  mov     edx, 13h
0x180014a84  call    WPP_SF_
0x180014a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a90  test    rbx, rbx
0x180014a93  jnz     short loc_180014AA1
0x180014a95  lea     eax, [rbx+57h]
0x180014a98  mov     [rsp+48h+Reply], eax
0x180014a9c  jmp     loc_180014B3D
0x180014aa1  mov     rsi, [rbx+18h]
0x180014aa5  test    rsi, rsi
0x180014aa8  jnz     short loc_180014AAF
0x180014aaa  lea     eax, [rsi+0Dh]
0x180014aad  jmp     short loc_180014A98
0x180014aaf  lea     rdi, [rbx+838h]
0x180014ab6  mov     rcx, [rdi]; lpMem
0x180014ab9  call    ?NhFreeNotification@@YAKPEAU_L2_NOTIFICATION_DATA@@@Z; NhFreeNotification(_L2_NOTIFICATION_DATA *)
0x180014abe  mov     rdx, [rbx+20h]
0x180014ac2  mov     rcx, rdi; struct _L2_NOTIFICATION_DATA **
0x180014ac5  mov     qword ptr [rdi], 0
0x180014acc  mov     rdx, [rdx]; struct _L2_NOTIFICATION_DATA *
0x180014acf  call    ?NhDupNotification@@YAKPEAPEAU_L2_NOTIFICATION_DATA@@PEAU1@@Z; NhDupNotification(_L2_NOTIFICATION_DATA * *,_L2_NOTIFICATION_DATA *)
0x180014ad4  test    eax, eax
0x180014ad6  jz      short loc_180014ADF
0x180014ad8  mov     qword ptr [rdi], 0
0x180014adf  lea     rdx, [rsp+48h+Reply]; Reply
0x180014ae4  mov     qword ptr [rbx+18h], 0
0x180014aec  mov     rcx, rsi; pAsync
0x180014aef  mov     qword ptr [rbx+20h], 0
0x180014af7  call    cs:__imp_RpcAsyncCompleteCall
0x180014afd  mov     [rsp+48h+Reply], eax
0x180014b01  test    eax, eax
0x180014b03  jz      short loc_180014B36
0x180014b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b0c  cmp     rcx, r15
0x180014b0f  jz      short loc_180014B6A
0x180014b11  cmp     byte ptr [rcx+19h], 1
0x180014b15  jb      short loc_180014B3D
0x180014b17  test    byte ptr [rcx+1Ch], 1
0x180014b1b  jz      short loc_180014B3D
0x180014b1d  mov     rcx, [rcx+10h]
0x180014b21  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014b28  mov     edx, 14h
0x180014b2d  call    WPP_SF_
0x180014b32  mov     eax, [rsp+48h+Reply]
0x180014b36  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b3d  cmp     rcx, r15
0x180014b40  jz      short loc_180014B6A
0x180014b42  cmp     byte ptr [rcx+19h], 4
0x180014b46  jb      short loc_180014B6A
0x180014b48  test    byte ptr [rcx+1Ch], 1
0x180014b4c  jz      short loc_180014B6A
0x180014b4e  mov     rcx, [rcx+10h]
0x180014b52  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180014b59  mov     edx, 15h
0x180014b5e  mov     r9d, eax
0x180014b61  call    WPP_SF_d
0x180014b66  mov     eax, [rsp+48h+Reply]
0x180014b6a  add     rsp, 28h
0x180014b6e  pop     r15
0x180014b70  pop     rdi
0x180014b71  pop     rsi
0x180014b72  pop     rbx
0x180014b73  retn
```
