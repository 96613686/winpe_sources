# RpcCloseHandle

- ea: `0x1800151f0`
- end: `0x180015354`
- name: `RpcCloseHandle`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000a87c`
- `0x18000a9c0`
- `0x18000c230`
- `0x180012e44`
- `0x1800151f0`

## import_xrefs

- `RPCRT4!RpcAsyncAbortCall` at `0x1800152b8`
- `RPCRT4!RpcAsyncAbortCall` at `0x1800152b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001525b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800152fc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800152fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015291`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015291`

## pseudocode

```c
__int64 __fastcall RpcCloseHandle(void **a1)
{
  void ***v1; // rbx
  unsigned int v3; // edi
  void **v4; // rdx
  void **v5; // rax
  struct _RPC_ASYNC_STATE *v6; // rcx

  v1 = (void ***)*a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 48, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
  }
  if ( g_bRpcServerStarted )
  {
    if ( v1 )
    {
      EnterCriticalSection(&stru_180052F50);
      v4 = *v1;
      if ( (*v1)[1] != v1 || (v5 = v1[1], *v5 != v1) )
        __fastfail(3u);
      *v5 = v4;
      v4[1] = v5;
      v3 = 0;
      --dword_180052EF8;
      LeaveCriticalSection(&stru_180052F50);
      NhFreeNotification((struct _L2_NOTIFICATION_DATA *)v1[263]);
      v6 = (struct _RPC_ASYNC_STATE *)v1[3];
      v1[263] = 0;
      if ( v6 )
      {
        if ( RpcAsyncAbortCall(v6, 0x4D4u)
          && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control[1].Blink)
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 49, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
        }
        v1[3] = 0;
        v1[4] = 0;
      }
      DeleteCriticalSection((LPCRITICAL_SECTION)v1 + 53);
      Dot3Free(v1);
    }
    else
    {
      v3 = 87;
    }
  }
  else
  {
    v3 = 1722;
  }
  *a1 = 0;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 50, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x1800151f0  push    rbx
0x1800151f2  push    rsi
0x1800151f3  push    rdi
0x1800151f4  push    r15
0x1800151f6  sub     rsp, 28h
0x1800151fa  mov     rbx, [rcx]
0x1800151fd  mov     rsi, rcx
0x180015200  mov     rcx, cs:WPP_GLOBAL_Control
0x180015207  lea     r15, WPP_GLOBAL_Control
0x18001520e  cmp     rcx, r15
0x180015211  jz      short loc_180015234
0x180015213  cmp     byte ptr [rcx+19h], 4
0x180015217  jb      short loc_180015234
0x180015219  test    byte ptr [rcx+1Ch], 1
0x18001521d  jz      short loc_180015234
0x18001521f  mov     rcx, [rcx+10h]
0x180015223  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x18001522a  mov     edx, 30h ; '0'
0x18001522f  call    WPP_SF_
0x180015234  cmp     cs:?g_bRpcServerStarted@@3EA, 0; uchar g_bRpcServerStarted
0x18001523b  jnz     short loc_180015247
0x18001523d  mov     edi, 6BAh
0x180015242  jmp     loc_18001530A
0x180015247  test    rbx, rbx
0x18001524a  jnz     short loc_180015254
0x18001524c  lea     edi, [rbx+57h]
0x18001524f  jmp     loc_18001530A
0x180015254  lea     rcx, stru_180052F50; lpCriticalSection
0x18001525b  call    cs:__imp_EnterCriticalSection
0x180015261  mov     rdx, [rbx]
0x180015264  cmp     [rdx+8], rbx
0x180015268  jnz     loc_18001534D
0x18001526e  mov     rax, [rbx+8]
0x180015272  cmp     [rax], rbx
0x180015275  jnz     loc_18001534D
0x18001527b  mov     [rax], rdx
0x18001527e  lea     rcx, stru_180052F50; lpCriticalSection
0x180015285  mov     [rdx+8], rax
0x180015289  xor     edi, edi
0x18001528b  dec     cs:dword_180052EF8
0x180015291  call    cs:__imp_LeaveCriticalSection
0x180015297  mov     rcx, [rbx+838h]; lpMem
0x18001529e  call    ?NhFreeNotification@@YAKPEAU_L2_NOTIFICATION_DATA@@@Z; NhFreeNotification(_L2_NOTIFICATION_DATA *)
0x1800152a3  mov     rcx, [rbx+18h]; pAsync
0x1800152a7  mov     [rbx+838h], rdi
0x1800152ae  test    rcx, rcx
0x1800152b1  jz      short loc_1800152F5
0x1800152b3  mov     edx, 4D4h; ExceptionCode
0x1800152b8  call    cs:__imp_RpcAsyncAbortCall
0x1800152be  test    eax, eax
0x1800152c0  jz      short loc_1800152ED
0x1800152c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152c9  cmp     rcx, r15
0x1800152cc  jz      short loc_1800152ED
0x1800152ce  cmp     byte ptr [rcx+19h], 1
0x1800152d2  jb      short loc_1800152ED
0x1800152d4  test    byte ptr [rcx+1Ch], 1
0x1800152d8  jz      short loc_1800152ED
0x1800152da  mov     rcx, [rcx+10h]
0x1800152de  lea     edx, [rdi+31h]
0x1800152e1  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x1800152e8  call    WPP_SF_
0x1800152ed  mov     [rbx+18h], rdi
0x1800152f1  mov     [rbx+20h], rdi
0x1800152f5  lea     rcx, [rbx+848h]; lpCriticalSection
0x1800152fc  call    cs:__imp_DeleteCriticalSection
0x180015302  mov     rcx, rbx; lpMem
0x180015305  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x18001530a  mov     qword ptr [rsi], 0
0x180015311  mov     rcx, cs:WPP_GLOBAL_Control
0x180015318  cmp     rcx, r15
0x18001531b  jz      short loc_180015341
0x18001531d  cmp     byte ptr [rcx+19h], 4
0x180015321  jb      short loc_180015341
0x180015323  test    byte ptr [rcx+1Ch], 1
0x180015327  jz      short loc_180015341
0x180015329  mov     rcx, [rcx+10h]
0x18001532d  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180015334  mov     edx, 32h ; '2'
0x180015339  mov     r9d, edi
0x18001533c  call    WPP_SF_d
0x180015341  mov     eax, edi
0x180015343  add     rsp, 28h
0x180015347  pop     r15
0x180015349  pop     rdi
0x18001534a  pop     rsi
0x18001534b  pop     rbx
0x18001534c  retn
0x18001534d  mov     ecx, 3
0x180015352  int     29h; Win8: RtlFailFast(ecx)
```
