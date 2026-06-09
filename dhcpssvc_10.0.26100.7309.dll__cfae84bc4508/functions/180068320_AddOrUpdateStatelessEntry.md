# AddOrUpdateStatelessEntry

- ea: `0x180068320`
- end: `0x1800684e3`
- name: `AddOrUpdateStatelessEntry`
- size: `451`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18007021c`

## callees

- `0x180002854`
- `0x180068320`
- `0x1800922d0`
- `0x18009fe04`
- `0x18009fee0`
- `0x1800b5d70`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetPrepareUpdate` at `0x1800683d9`
- `ESENT!JetPrepareUpdate` at `0x1800683d9`
- `KERNEL32!EnterCriticalSection` at `0x180068353`
- `KERNEL32!EnterCriticalSection` at `0x18006842f`
- `KERNEL32!EnterCriticalSection` at `0x180068353`
- `KERNEL32!EnterCriticalSection` at `0x18006842f`
- `KERNEL32!LeaveCriticalSection` at `0x180068410`
- `KERNEL32!LeaveCriticalSection` at `0x180068461`
- `KERNEL32!LeaveCriticalSection` at `0x180068410`
- `KERNEL32!LeaveCriticalSection` at `0x180068461`

## string_xrefs

- `0x1800683e5`: `DhcpDALJetPrepareUpdate`

## pseudocode

```c
__int64 __fastcall AddOrUpdateStatelessEntry(__int64 a1, __int128 *a2, __int64 a3)
{
  JET_SESID v6; // rsi
  __int64 v7; // rax
  unsigned int v8; // edi
  unsigned int v9; // eax
  unsigned int updated; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int128 v14; // [rsp+30h] [rbp-50h] BYREF
  __int64 v15; // [rsp+40h] [rbp-40h]
  int v16; // [rsp+48h] [rbp-38h]
  int v17; // [rsp+4Ch] [rbp-34h]
  __int64 v18; // [rsp+50h] [rbp-30h]
  int v19; // [rsp+58h] [rbp-28h]
  int v20; // [rsp+5Ch] [rbp-24h]
  __int64 v21; // [rsp+60h] [rbp-20h]
  int v22; // [rsp+68h] [rbp-18h]
  int v23; // [rsp+6Ch] [rbp-14h]

  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v6 = DhcpGlobalJetServerSession;
  v18 = a3 + 16;
  v7 = *(_QWORD *)(a3 + 24);
  v8 = 0;
  v20 = 0;
  v23 = 0;
  v21 = v7;
  v22 = *(_DWORD *)(a3 + 32);
  v15 = a3;
  v16 = 16;
  v17 = 1;
  v19 = 8;
  if ( (unsigned int)DhcpDALJetPrepareUpdate(DhcpGlobalJetServerSession, StatelessClientsTableHandle, 3, 0) != 2
    || (v8 = 1,
        v9 = JetPrepareUpdate(v6, StatelessClientsTableHandle, 0),
        (updated = DhcpDALMapJetError(v9, "DhcpDALJetPrepareUpdate")) == 0) )
  {
    updated = SetStatelessClientColumns(v6, a3, v8);
  }
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  if ( updated )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      v12 = 148;
      goto LABEL_13;
    }
  }
  else if ( v8 )
  {
    EnterCriticalSection(&DhcpGlobalStatelessCritSect);
    v14 = *a2;
    updated = MemServerUpdateStatelessRecordsCount(a1, &v14, 1, 0);
    LeaveCriticalSection(&DhcpGlobalStatelessCritSect);
    if ( updated )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v12 = 147;
LABEL_13:
        WPP_SF_D(v11[2], v12, &WPP_c478ec705b883cfeef20aad3be309da3_Traceguids, updated);
      }
    }
  }
  return updated;
}

```

## disassembly

```asm
0x180068320  push    rbp
0x180068322  push    rbx
0x180068323  push    rsi
0x180068324  push    rdi
0x180068325  push    r12
0x180068327  push    r14
0x180068329  push    r15
0x18006832b  mov     rbp, rsp
0x18006832e  sub     rsp, 80h
0x180068335  mov     rax, cs:__security_cookie
0x18006833c  xor     rax, rsp
0x18006833f  mov     [rbp+var_10], rax
0x180068343  mov     r15, rcx
0x180068346  mov     r14, r8
0x180068349  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180068350  mov     r12, rdx
0x180068353  call    cs:__imp_EnterCriticalSection
0x18006835a  nop     dword ptr [rax+rax+00h]
0x18006835f  mov     rsi, cs:DhcpGlobalJetServerSession
0x180068366  lea     rax, [r14+10h]
0x18006836a  mov     rdx, cs:StatelessClientsTableHandle; tableid
0x180068371  lea     r9, [rbp+var_40]
0x180068375  mov     [rbp+var_30], rax
0x180068379  lea     r8, aSubnetprefixin; "SubnetPrefixInterfaceIdClientDuid"
0x180068380  mov     rax, [r14+18h]
0x180068384  xor     edi, edi
0x180068386  and     [rsp+80h+var_58], edi
0x18006838a  mov     rcx, rsi; sesid
0x18006838d  and     [rbp+var_24], edi
0x180068390  and     [rbp+var_14], edi
0x180068393  mov     [rbp+var_20], rax
0x180068397  mov     eax, [r14+20h]
0x18006839b  mov     [rbp+var_18], eax
0x18006839e  mov     [rbp+var_40], r14
0x1800683a2  mov     [rbp+var_38], 10h
0x1800683a9  mov     [rbp+var_34], 1
0x1800683b0  mov     [rbp+var_28], 8
0x1800683b7  mov     [rsp+80h+var_60], 3; int
0x1800683bf  call    DhcpDALJetPrepareUpdate
0x1800683c4  cmp     eax, 2
0x1800683c7  jnz     short loc_1800683F9
0x1800683c9  mov     rdx, cs:StatelessClientsTableHandle; tableid
0x1800683d0  lea     edi, [rax-1]
0x1800683d3  xor     r8d, r8d; prep
0x1800683d6  mov     rcx, rsi; sesid
0x1800683d9  call    cs:__imp_JetPrepareUpdate
0x1800683e0  nop     dword ptr [rax+rax+00h]
0x1800683e5  lea     rdx, aDhcpdaljetprep_4; "DhcpDALJetPrepareUpdate"
0x1800683ec  mov     ecx, eax
0x1800683ee  call    DhcpDALMapJetError
0x1800683f3  mov     ebx, eax
0x1800683f5  test    eax, eax
0x1800683f7  jnz     short loc_180068409
0x1800683f9  mov     r8d, edi
0x1800683fc  mov     rdx, r14
0x1800683ff  mov     rcx, rsi
0x180068402  call    SetStatelessClientColumns
0x180068407  mov     ebx, eax
0x180068409  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180068410  call    cs:__imp_LeaveCriticalSection
0x180068417  nop     dword ptr [rax+rax+00h]
0x18006841c  test    ebx, ebx
0x18006841e  jnz     short loc_180068491
0x180068420  test    edi, edi
0x180068422  jz      loc_1800684C2
0x180068428  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x18006842f  call    cs:__imp_EnterCriticalSection
0x180068436  nop     dword ptr [rax+rax+00h]
0x18006843b  movups  xmm0, xmmword ptr [r12]
0x180068440  xor     r9d, r9d
0x180068443  lea     r8d, [rbx+1]
0x180068447  lea     rdx, [rbp+var_50]
0x18006844b  mov     rcx, r15
0x18006844e  movdqu  [rbp+var_50], xmm0
0x180068453  call    MemServerUpdateStatelessRecordsCount
0x180068458  lea     rcx, DhcpGlobalStatelessCritSect; lpCriticalSection
0x18006845f  mov     ebx, eax
0x180068461  call    cs:__imp_LeaveCriticalSection
0x180068468  nop     dword ptr [rax+rax+00h]
0x18006846d  test    ebx, ebx
0x18006846f  jz      short loc_1800684C2
0x180068471  mov     rcx, cs:WPP_GLOBAL_Control
0x180068478  lea     rax, WPP_GLOBAL_Control
0x18006847f  cmp     rcx, rax
0x180068482  jz      short loc_1800684C2
0x180068484  test    byte ptr [rcx+1Ch], 20h
0x180068488  jz      short loc_1800684C2
0x18006848a  mov     edx, 93h
0x18006848f  jmp     short loc_1800684AF
0x180068491  mov     rcx, cs:WPP_GLOBAL_Control
0x180068498  lea     rax, WPP_GLOBAL_Control
0x18006849f  cmp     rcx, rax
0x1800684a2  jz      short loc_1800684C2
0x1800684a4  test    byte ptr [rcx+1Ch], 20h
0x1800684a8  jz      short loc_1800684C2
0x1800684aa  mov     edx, 94h
0x1800684af  mov     rcx, [rcx+10h]
0x1800684b3  lea     r8, WPP_c478ec705b883cfeef20aad3be309da3_Traceguids
0x1800684ba  mov     r9d, ebx
0x1800684bd  call    WPP_SF_D
0x1800684c2  mov     eax, ebx
0x1800684c4  mov     rcx, [rbp+var_10]
0x1800684c8  xor     rcx, rsp; StackCookie
0x1800684cb  call    __security_check_cookie
0x1800684d0  add     rsp, 80h
0x1800684d7  pop     r15
0x1800684d9  pop     r14
0x1800684db  pop     r12
0x1800684dd  pop     rdi
0x1800684de  pop     rsi
0x1800684df  pop     rbx
0x1800684e0  pop     rbp
0x1800684e1  retn
```
