# DerefClientInfo(_RPC_CLIENT_INFO *)

- ea: `0x180013c2c`
- end: `0x180013d9e`
- name: `?DerefClientInfo@@YAKPEAU_RPC_CLIENT_INFO@@@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct _RPC_CLIENT_INFO *lpMem, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180013e7c`
- `0x180014748`
- `0x180014830`
- `0x180014c30`

## callees

- `0x18000a87c`
- `0x18000c230`
- `0x180012e44`
- `0x180013bec`
- `0x180013c2c`
- `0x18001687c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013cbb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013cbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013d4f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013d4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013cef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013cef`

## pseudocode

```c
__int64 __fastcall DerefClientInfo(struct _RPC_CLIENT_INFO *lpMem, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  struct _RPC_CLIENT_INFO **v5; // rax
  unsigned int v6; // eax

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_qD(WPP_GLOBAL_Control[1].Flink, 12, a3, lpMem, *((_DWORD *)lpMem + 540));
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 540, 0xFFFFFFFF) == 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 13, WPP_b4750df92381326559acc6db9e2d425d_Traceguids, lpMem);
    }
    EnterCriticalSection(&stru_180052F50);
    v4 = *(_QWORD *)lpMem;
    if ( *(struct _RPC_CLIENT_INFO **)(*(_QWORD *)lpMem + 8LL) != lpMem
      || (v5 = (struct _RPC_CLIENT_INFO **)*((_QWORD *)lpMem + 1), *v5 != lpMem) )
    {
      __fastfail(3u);
    }
    *v5 = (struct _RPC_CLIENT_INFO *)v4;
    *(_QWORD *)(v4 + 8) = v5;
    --dword_180052EF8;
    LeaveCriticalSection(&stru_180052F50);
    NhFreeNotification(*((struct _L2_NOTIFICATION_DATA **)lpMem + 263));
    v6 = *((_DWORD *)lpMem + 524);
    *((_QWORD *)lpMem + 263) = 0;
    while ( v6 != *((_DWORD *)lpMem + 525) )
    {
      NhFreeNotification(*((struct _L2_NOTIFICATION_DATA **)lpMem + v6 + 6));
      *((_QWORD *)lpMem + *((unsigned int *)lpMem + 524) + 6) = 0;
      v6 = (unsigned __int8)(*((_DWORD *)lpMem + 524) + 1);
      *((_DWORD *)lpMem + 524) = (unsigned __int8)v6;
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)lpMem + 53);
    Dot3Free(lpMem);
  }
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 4u
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 14, WPP_b4750df92381326559acc6db9e2d425d_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180013c2c  mov     [rsp+arg_8], rbx
0x180013c31  push    rsi
0x180013c32  sub     rsp, 30h
0x180013c36  mov     rbx, rcx
0x180013c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c40  lea     rsi, WPP_GLOBAL_Control
0x180013c47  cmp     rcx, rsi
0x180013c4a  jz      short loc_180013C73
0x180013c4c  cmp     byte ptr [rcx+19h], 4
0x180013c50  jb      short loc_180013C73
0x180013c52  test    byte ptr [rcx+1Ch], 1
0x180013c56  jz      short loc_180013C73
0x180013c58  mov     eax, [rbx+870h]
0x180013c5e  mov     edx, 0Ch
0x180013c63  mov     rcx, [rcx+10h]
0x180013c67  mov     r9, rbx
0x180013c6a  mov     [rsp+38h+var_18], eax
0x180013c6e  call    WPP_SF_qD
0x180013c73  or      eax, 0FFFFFFFFh
0x180013c76  lock xadd [rbx+870h], eax
0x180013c7e  cmp     eax, 1
0x180013c81  jnz     loc_180013D5D
0x180013c87  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c8e  cmp     rcx, rsi
0x180013c91  jz      short loc_180013CB4
0x180013c93  cmp     byte ptr [rcx+19h], 4
0x180013c97  jb      short loc_180013CB4
0x180013c99  test    [rcx+1Ch], al
0x180013c9c  jz      short loc_180013CB4
0x180013c9e  mov     rcx, [rcx+10h]
0x180013ca2  lea     edx, [rax+0Ch]
0x180013ca5  mov     r9, rbx
0x180013ca8  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180013caf  call    WPP_SF_q
0x180013cb4  lea     rcx, stru_180052F50; lpCriticalSection
0x180013cbb  call    cs:__imp_EnterCriticalSection
0x180013cc1  mov     rdx, [rbx]
0x180013cc4  cmp     [rdx+8], rbx
0x180013cc8  jnz     loc_180013D97
0x180013cce  mov     rax, [rbx+8]
0x180013cd2  cmp     [rax], rbx
0x180013cd5  jnz     loc_180013D97
0x180013cdb  mov     [rax], rdx
0x180013cde  lea     rcx, stru_180052F50; lpCriticalSection
0x180013ce5  mov     [rdx+8], rax
0x180013ce9  dec     cs:dword_180052EF8
0x180013cef  call    cs:__imp_LeaveCriticalSection
0x180013cf5  mov     rcx, [rbx+838h]; lpMem
0x180013cfc  call    ?NhFreeNotification@@YAKPEAU_L2_NOTIFICATION_DATA@@@Z; NhFreeNotification(_L2_NOTIFICATION_DATA *)
0x180013d01  mov     eax, [rbx+830h]
0x180013d07  mov     qword ptr [rbx+838h], 0
0x180013d12  jmp     short loc_180013D40
0x180013d14  mov     ecx, eax
0x180013d16  mov     rcx, [rbx+rcx*8+30h]; lpMem
0x180013d1b  call    ?NhFreeNotification@@YAKPEAU_L2_NOTIFICATION_DATA@@@Z; NhFreeNotification(_L2_NOTIFICATION_DATA *)
0x180013d20  mov     eax, [rbx+830h]
0x180013d26  mov     qword ptr [rbx+rax*8+30h], 0
0x180013d2f  mov     eax, [rbx+830h]
0x180013d35  inc     eax
0x180013d37  movzx   eax, al
0x180013d3a  mov     [rbx+830h], eax
0x180013d40  cmp     eax, [rbx+834h]
0x180013d46  jnz     short loc_180013D14
0x180013d48  lea     rcx, [rbx+848h]; lpCriticalSection
0x180013d4f  call    cs:__imp_DeleteCriticalSection
0x180013d55  mov     rcx, rbx; lpMem
0x180013d58  call    ?Dot3Free@@YAXPEAX@Z; Dot3Free(void *)
0x180013d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d64  cmp     rcx, rsi
0x180013d67  jz      short loc_180013D8A
0x180013d69  cmp     byte ptr [rcx+19h], 4
0x180013d6d  jb      short loc_180013D8A
0x180013d6f  test    byte ptr [rcx+1Ch], 1
0x180013d73  jz      short loc_180013D8A
0x180013d75  mov     rcx, [rcx+10h]
0x180013d79  lea     r8, WPP_b4750df92381326559acc6db9e2d425d_Traceguids
0x180013d80  mov     edx, 0Eh
0x180013d85  call    WPP_SF_
0x180013d8a  mov     rbx, [rsp+38h+arg_8]
0x180013d8f  xor     eax, eax
0x180013d91  add     rsp, 30h
0x180013d95  pop     rsi
0x180013d96  retn
0x180013d97  mov     ecx, 3
0x180013d9c  int     29h; Win8: RtlFailFast(ecx)
```
