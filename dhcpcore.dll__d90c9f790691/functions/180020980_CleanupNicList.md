# CleanupNicList

- ea: `0x180020980`
- end: `0x180020b14`
- name: `CleanupNicList`
- size: `404`
- prototype: `void __fastcall(_QWORD *, volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001c660`

## callees

- `0x180002534`
- `0x18000d278`
- `0x180015604`
- `0x180019a98`
- `0x18001eb68`
- `0x180020980`
- `0x1800210a4`
- `0x180033228`
- `0x18004d1a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020a1f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800209eb`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800209eb`
- `WS2_32!WSACloseEvent` at `0x180020a3c`
- `WS2_32!WSACloseEvent` at `0x180020a3c`

## pseudocode

```c
void __fastcall CleanupNicList(_QWORD *a1, volatile signed __int32 *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  int IsInitState; // eax
  __int64 v11; // r8
  int v12; // ecx
  unsigned int v13; // eax
  int v14; // [rsp+50h] [rbp+8h] BYREF

  while ( 1 )
  {
    v4 = (_QWORD *)*a1;
    if ( (_QWORD *)*a1 == a1 )
      break;
    if ( (_QWORD *)v4[1] != a1 || (v5 = *v4, *(_QWORD **)(*v4 + 8LL) != v4) )
      __fastfail(3u);
    *a1 = v5;
    *(_QWORD *)(v5 + 8) = a1;
    if ( a2 )
      _InterlockedDecrement(a2);
    v4[1] = v4;
    *v4 = v4;
    UnScheduleDhcpRenewal(v4);
    v6 = 2000;
    do
    {
      if ( *((_DWORD *)v4 + 4) == 1 )
        break;
      CancelRenew(v4);
      Sleep(0x64u);
      v6 -= 100;
    }
    while ( v6 );
    v7 = (void *)v4[83];
    if ( v7 )
    {
      CloseHandle(v7);
      v4[83] = 0;
    }
    v8 = (void *)v4[248];
    if ( v8 )
    {
      CloseHandle(v8);
      v4[248] = 0;
    }
    v9 = (void *)v4[104];
    if ( v9 )
    {
      WSACloseEvent(v9);
      v4[104] = 0;
    }
    if ( !*((_DWORD *)v4 + 198) )
      goto LABEL_26;
    if ( DhcpGlobalIsShuttingDown )
    {
      IsInitState = DhcpIsInitState(v4);
      if ( !IsInitState )
      {
        v12 = *((_DWORD *)v4 + 143);
        v14 = 0;
        if ( v12 != 2 )
        {
          LOBYTE(IsInitState) = v12 != 0;
LABEL_22:
          if ( IsInitState )
          {
            v13 = ReleaseIpAddress(v4);
            if ( v13 )
            {
              if ( (xmmword_1800616A0 & 2) != 0 )
                WPP_SF_D(1025, 110, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v13);
            }
          }
          goto LABEL_26;
        }
        if ( (unsigned int)DhcpFindDwordOption(v4, 2, v11, &v14) )
        {
          IsInitState = v14 & 1;
          goto LABEL_22;
        }
      }
LABEL_26:
      if ( !DhcpGlobalIsShuttingDown )
        goto LABEL_27;
    }
    else
    {
LABEL_27:
      DhcpDestroyLease(v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 4, 0xFFFFFFFF) == 1 )
        DhcpDestroyContextEx(v4);
    }
  }
}

```

## disassembly

```asm
0x180020980  push    rbx
0x180020982  push    rbp
0x180020983  push    rsi
0x180020984  push    rdi
0x180020985  sub     rsp, 28h
0x180020989  mov     rbp, rdx
0x18002098c  mov     rdi, rcx
0x18002098f  mov     rbx, [rdi]
0x180020992  cmp     rbx, rdi
0x180020995  jz      loc_180020B0B
0x18002099b  cmp     [rbx+8], rdi
0x18002099f  jnz     loc_180020B04
0x1800209a5  mov     rax, [rbx]
0x1800209a8  cmp     [rax+8], rbx
0x1800209ac  jnz     loc_180020B04
0x1800209b2  mov     [rdi], rax
0x1800209b5  mov     [rax+8], rdi
0x1800209b9  test    rbp, rbp
0x1800209bc  jz      short loc_1800209C2
0x1800209be  lock dec dword ptr [rbp+0]
0x1800209c2  mov     rcx, rbx
0x1800209c5  mov     [rbx+8], rbx
0x1800209c9  mov     [rbx], rbx
0x1800209cc  call    UnScheduleDhcpRenewal
0x1800209d1  mov     esi, 7D0h
0x1800209d6  mov     eax, [rbx+10h]
0x1800209d9  cmp     eax, 1
0x1800209dc  jz      short loc_1800209F6
0x1800209de  mov     rcx, rbx
0x1800209e1  call    CancelRenew
0x1800209e6  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800209eb  call    cs:__imp_Sleep
0x1800209f1  add     esi, 0FFFFFF9Ch
0x1800209f4  jnz     short loc_1800209D6
0x1800209f6  mov     rcx, [rbx+298h]; hObject
0x1800209fd  test    rcx, rcx
0x180020a00  jz      short loc_180020A13
0x180020a02  call    cs:__imp_CloseHandle
0x180020a08  mov     qword ptr [rbx+298h], 0
0x180020a13  mov     rcx, [rbx+7C0h]; hObject
0x180020a1a  test    rcx, rcx
0x180020a1d  jz      short loc_180020A30
0x180020a1f  call    cs:__imp_CloseHandle
0x180020a25  mov     qword ptr [rbx+7C0h], 0
0x180020a30  mov     rcx, [rbx+340h]; hEvent
0x180020a37  test    rcx, rcx
0x180020a3a  jz      short loc_180020A4D
0x180020a3c  call    cs:__imp_WSACloseEvent
0x180020a42  mov     qword ptr [rbx+340h], 0
0x180020a4d  mov     eax, [rbx+318h]
0x180020a53  test    eax, eax
0x180020a55  jz      short loc_180020AD1
0x180020a57  cmp     cs:DhcpGlobalIsShuttingDown, 0
0x180020a5e  jz      short loc_180020ADE
0x180020a60  mov     rcx, rbx
0x180020a63  call    DhcpIsInitState
0x180020a68  test    eax, eax
0x180020a6a  jnz     short loc_180020AD1
0x180020a6c  mov     ecx, [rbx+23Ch]
0x180020a72  mov     [rsp+48h+arg_0], eax
0x180020a76  cmp     ecx, 2
0x180020a79  jz      short loc_180020A82
0x180020a7b  test    ecx, ecx
0x180020a7d  setnz   al
0x180020a80  jmp     short loc_180020A9F
0x180020a82  lea     r9, [rsp+48h+arg_0]
0x180020a87  mov     edx, 2
0x180020a8c  mov     rcx, rbx
0x180020a8f  call    DhcpFindDwordOption
0x180020a94  test    eax, eax
0x180020a96  jz      short loc_180020AD1
0x180020a98  mov     eax, [rsp+48h+arg_0]
0x180020a9c  and     eax, 1
0x180020a9f  test    eax, eax
0x180020aa1  jz      short loc_180020AD1
0x180020aa3  mov     rcx, rbx
0x180020aa6  call    ReleaseIpAddress
0x180020aab  test    eax, eax
0x180020aad  jz      short loc_180020AD1
0x180020aaf  test    byte ptr cs:xmmword_1800616A0, 2
0x180020ab6  jz      short loc_180020AD1
0x180020ab8  mov     edx, 6Eh ; 'n'
0x180020abd  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180020ac4  mov     ecx, 401h
0x180020ac9  mov     r9d, eax
0x180020acc  call    WPP_SF_D
0x180020ad1  cmp     cs:DhcpGlobalIsShuttingDown, 0
0x180020ad8  jnz     loc_18002098F
0x180020ade  mov     rcx, rbx
0x180020ae1  call    DhcpDestroyLease
0x180020ae6  or      eax, 0FFFFFFFFh
0x180020ae9  lock xadd [rbx+10h], eax
0x180020aee  cmp     eax, 1
0x180020af1  jnz     loc_18002098F
0x180020af7  mov     rcx, rbx
0x180020afa  call    DhcpDestroyContextEx
0x180020aff  jmp     loc_18002098F
0x180020b04  mov     ecx, 3
0x180020b09  int     29h; Win8: RtlFailFast(ecx)
0x180020b0b  add     rsp, 28h
0x180020b0f  pop     rdi
0x180020b10  pop     rsi
0x180020b11  pop     rbp
0x180020b12  pop     rbx
0x180020b13  retn
```
