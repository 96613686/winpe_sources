# MadcapCreateClientEntry

- ea: `0x180029f8c`
- end: `0x18002a292`
- name: `MadcapCreateClientEntry`
- size: `774`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, unsigned int, __int64, char, char, char, char, __int64, int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180010460`
- `0x18002b154`
- `0x18002c714`
- `0x18004ebe0`

## callees

- `0x180002854`
- `0x18000f144`
- `0x180028df4`
- `0x1800291c0`
- `0x1800292f4`
- `0x180029324`
- `0x180029f8c`

## import_xrefs

- `ESENT!JetUpdate` at `0x18002a1f2`
- `ESENT!JetUpdate` at `0x18002a1f2`
- `ESENT!JetBeginTransaction` at `0x180029fe7`
- `ESENT!JetBeginTransaction` at `0x180029fe7`
- `KERNEL32!EnterCriticalSection` at `0x180029fd8`
- `KERNEL32!EnterCriticalSection` at `0x180029fd8`
- `KERNEL32!LeaveCriticalSection` at `0x18002a24b`
- `KERNEL32!LeaveCriticalSection` at `0x18002a24b`

## string_xrefs

- `0x18002a273`: `MCreateClientEntry:Update`

## pseudocode

```c
__int64 __fastcall MadcapCreateClientEntry(
        const void *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        int a12)
{
  JET_SESID v12; // rbx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // r9
  int v18; // edi
  __int64 v19; // r9
  __int64 v20; // rax
  unsigned int v21; // eax
  int v23; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v24[3]; // [rsp+38h] [rbp-18h] BYREF
  int v25; // [rsp+90h] [rbp+40h] BYREF

  v25 = a3;
  v12 = DhcpGlobalJetServerSession;
  v24[1] = DhcpGlobalJetServerSession;
  v23 = 0;
  v24[0] = 0;
  v24[2] = MadcapGlobalClientTableHandle;
  EnterCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  v15 = JetBeginTransaction(v12);
  v16 = DhcpMapJetError(v15, "M:BeginTransaction");
  if ( !v16 )
  {
    v18 = a12;
    v16 = MadcapJetPrepareUpdate((__int64)v24, *(_QWORD *)MadcapGlobalClientTable, a1, v17, a12 == 0);
    if ( !v16 && (v18 || (v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 8), a1, 4)) == 0) )
    {
      v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 88), &v25, 4);
      if ( !v16 )
      {
        v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 56), &a10, 1);
        if ( !v16 )
        {
          v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 72), &v23, 4);
          if ( !v16 )
          {
            v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 24), a4, a5);
            if ( !v16 )
            {
              if ( v18 && !a6 )
                goto LABEL_31;
              if ( a6 )
              {
                v20 = -1;
                do
                  ++v20;
                while ( *(_WORD *)(a6 + 2 * v20) );
                v19 = 2 * v20 + 2;
              }
              else
              {
                v19 = 0;
              }
              v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 40), a6, v19);
              if ( !v16 )
              {
LABEL_31:
                v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 104), &a7, 8);
                if ( !v16 )
                {
                  v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 120), &a8, 8);
                  if ( !v16 )
                  {
                    v16 = MadcapJetSetValue(
                            v24,
                            *(unsigned int *)(MadcapGlobalClientTable + 152),
                            &DhcpGlobalServerName,
                            DhcpGlobalServerNameLen);
                    if ( !v16 )
                    {
                      v16 = MadcapJetSetValue(v24, *(unsigned int *)(MadcapGlobalClientTable + 136), &a9, 4);
                      if ( !v16 )
                      {
                        v21 = JetUpdate(DhcpGlobalJetServerSession, MadcapGlobalClientTableHandle, 0, 0, 0);
                        if ( v21 == -1605 )
                        {
                          v16 = 20013;
                        }
                        else
                        {
                          v16 = DhcpMapJetError(v21, "MCreateClientEntry:Update");
                          if ( !v16 )
                          {
                            MadcapJetCommitTransaction(v24);
                            goto LABEL_26;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  MadcapJetRollBack(v24);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids, v16);
LABEL_26:
  LeaveCriticalSection(&DhcpGlobalJetDatabaseCritSect);
  return v16;
}

```

## disassembly

```asm
0x180029f8c  mov     [rsp-28h+arg_0], rbx
0x180029f91  mov     [rsp-28h+arg_8], rsi
0x180029f96  mov     [rsp-28h+arg_10], r8d
0x180029f9b  push    rbp
0x180029f9c  push    rdi
0x180029f9d  push    r12
0x180029f9f  push    r14
0x180029fa1  push    r15
0x180029fa3  mov     rbp, rsp
0x180029fa6  sub     rsp, 50h
0x180029faa  mov     rbx, cs:DhcpGlobalJetServerSession
0x180029fb1  mov     rsi, rcx
0x180029fb4  mov     rax, cs:MadcapGlobalClientTableHandle
0x180029fbb  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029fc2  xor     r15d, r15d
0x180029fc5  mov     [rbp+var_10], rbx
0x180029fc9  mov     [rbp+var_20], r15d
0x180029fcd  mov     r14, r9
0x180029fd0  mov     [rbp+var_18], r15
0x180029fd4  mov     [rbp+var_8], rax
0x180029fd8  call    cs:__imp_EnterCriticalSection
0x180029fdf  nop     dword ptr [rax+rax+00h]
0x180029fe4  mov     rcx, rbx; sesid
0x180029fe7  call    cs:__imp_JetBeginTransaction
0x180029fee  nop     dword ptr [rax+rax+00h]
0x180029ff3  mov     ecx, eax
0x180029ff5  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x180029ffc  call    DhcpMapJetError
0x18002a001  mov     ebx, eax
0x18002a003  test    eax, eax
0x18002a005  jnz     loc_18002A20A
0x18002a00b  mov     rdx, cs:MadcapGlobalClientTable
0x18002a012  lea     rcx, [rbp+var_18]
0x18002a016  mov     edi, [rbp+arg_58]
0x18002a01c  mov     eax, r15d
0x18002a01f  test    edi, edi
0x18002a021  mov     r8, rsi
0x18002a024  mov     rdx, [rdx]
0x18002a027  setz    al
0x18002a02a  mov     dword ptr [rsp+50h+pcbActual], eax
0x18002a02e  call    MadcapJetPrepareUpdate
0x18002a033  mov     ebx, eax
0x18002a035  test    eax, eax
0x18002a037  jnz     loc_18002A20A
0x18002a03d  lea     r12d, [r15+4]
0x18002a041  test    edi, edi
0x18002a043  jnz     short loc_18002A068
0x18002a045  mov     rdx, cs:MadcapGlobalClientTable
0x18002a04c  lea     rcx, [rbp+var_18]
0x18002a050  mov     r9d, r12d
0x18002a053  mov     r8, rsi
0x18002a056  mov     edx, [rdx+8]
0x18002a059  call    MadcapJetSetValue
0x18002a05e  mov     ebx, eax
0x18002a060  test    eax, eax
0x18002a062  jnz     loc_18002A20A
0x18002a068  mov     rdx, cs:MadcapGlobalClientTable
0x18002a06f  lea     r8, [rbp+arg_10]
0x18002a073  mov     r9, r12
0x18002a076  lea     rcx, [rbp+var_18]
0x18002a07a  mov     edx, [rdx+58h]
0x18002a07d  call    MadcapJetSetValue
0x18002a082  mov     ebx, eax
0x18002a084  test    eax, eax
0x18002a086  jnz     loc_18002A20A
0x18002a08c  mov     rdx, cs:MadcapGlobalClientTable
0x18002a093  lea     r9d, [rax+1]
0x18002a097  lea     r8, [rbp+arg_48]
0x18002a09b  lea     rcx, [rbp+var_18]
0x18002a09f  mov     edx, [rdx+38h]
0x18002a0a2  call    MadcapJetSetValue
0x18002a0a7  mov     ebx, eax
0x18002a0a9  test    eax, eax
0x18002a0ab  jnz     loc_18002A20A
0x18002a0b1  mov     rdx, cs:MadcapGlobalClientTable
0x18002a0b8  lea     r8, [rbp+var_20]
0x18002a0bc  mov     r9, r12
0x18002a0bf  lea     rcx, [rbp+var_18]
0x18002a0c3  mov     edx, [rdx+48h]
0x18002a0c6  call    MadcapJetSetValue
0x18002a0cb  mov     ebx, eax
0x18002a0cd  test    eax, eax
0x18002a0cf  jnz     loc_18002A20A
0x18002a0d5  mov     rdx, cs:MadcapGlobalClientTable
0x18002a0dc  lea     rcx, [rbp+var_18]
0x18002a0e0  mov     r9d, [rbp+arg_20]
0x18002a0e4  mov     r8, r14
0x18002a0e7  mov     edx, [rdx+18h]
0x18002a0ea  call    MadcapJetSetValue
0x18002a0ef  mov     ebx, eax
0x18002a0f1  test    eax, eax
0x18002a0f3  jnz     loc_18002A20A
0x18002a0f9  mov     r8, [rbp+arg_28]
0x18002a0fd  test    edi, edi
0x18002a0ff  jz      short loc_18002A106
0x18002a101  test    r8, r8
0x18002a104  jz      short loc_18002A143
0x18002a106  test    r8, r8
0x18002a109  jnz     short loc_18002A110
0x18002a10b  mov     r9, r15
0x18002a10e  jmp     short loc_18002A126
0x18002a110  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a114  inc     rax
0x18002a117  cmp     [r8+rax*2], r15w
0x18002a11c  jnz     short loc_18002A114
0x18002a11e  lea     r9, ds:2[rax*2]
0x18002a126  mov     rdx, cs:MadcapGlobalClientTable
0x18002a12d  lea     rcx, [rbp+var_18]
0x18002a131  mov     edx, [rdx+28h]
0x18002a134  call    MadcapJetSetValue
0x18002a139  mov     ebx, eax
0x18002a13b  test    eax, eax
0x18002a13d  jnz     loc_18002A20A
0x18002a143  mov     rdx, cs:MadcapGlobalClientTable
0x18002a14a  lea     r8, [rbp+arg_30]
0x18002a14e  mov     edi, 8
0x18002a153  lea     rcx, [rbp+var_18]
0x18002a157  mov     r9d, edi
0x18002a15a  mov     edx, [rdx+68h]
0x18002a15d  call    MadcapJetSetValue
0x18002a162  mov     ebx, eax
0x18002a164  test    eax, eax
0x18002a166  jnz     loc_18002A20A
0x18002a16c  mov     rdx, cs:MadcapGlobalClientTable
0x18002a173  lea     r8, [rbp+arg_38]
0x18002a177  mov     r9d, edi
0x18002a17a  lea     rcx, [rbp+var_18]
0x18002a17e  mov     edx, [rdx+78h]
0x18002a181  call    MadcapJetSetValue
0x18002a186  mov     ebx, eax
0x18002a188  test    eax, eax
0x18002a18a  jnz     short loc_18002A20A
0x18002a18c  mov     rdx, cs:MadcapGlobalClientTable
0x18002a193  lea     r8, DhcpGlobalServerName
0x18002a19a  mov     r9d, cs:DhcpGlobalServerNameLen
0x18002a1a1  lea     rcx, [rbp+var_18]
0x18002a1a5  mov     edx, [rdx+98h]
0x18002a1ab  call    MadcapJetSetValue
0x18002a1b0  mov     ebx, eax
0x18002a1b2  test    eax, eax
0x18002a1b4  jnz     short loc_18002A20A
0x18002a1b6  mov     rdx, cs:MadcapGlobalClientTable
0x18002a1bd  lea     r8, [rbp+arg_40]
0x18002a1c1  mov     r9, r12
0x18002a1c4  lea     rcx, [rbp+var_18]
0x18002a1c8  mov     edx, [rdx+88h]
0x18002a1ce  call    MadcapJetSetValue
0x18002a1d3  mov     ebx, eax
0x18002a1d5  test    eax, eax
0x18002a1d7  jnz     short loc_18002A20A
0x18002a1d9  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x18002a1e0  xor     r9d, r9d; cbBookmark
0x18002a1e3  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x18002a1ea  xor     r8d, r8d; pvBookmark
0x18002a1ed  mov     [rsp+50h+pcbActual], r15; pcbActual
0x18002a1f2  call    cs:__imp_JetUpdate
0x18002a1f9  nop     dword ptr [rax+rax+00h]
0x18002a1fe  cmp     eax, 0FFFFF9BBh
0x18002a203  jnz     short loc_18002A273
0x18002a205  mov     ebx, 4E2Dh
0x18002a20a  lea     rcx, [rbp+var_18]
0x18002a20e  call    MadcapJetRollBack
0x18002a213  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a21a  lea     rax, WPP_GLOBAL_Control
0x18002a221  cmp     rcx, rax
0x18002a224  jz      short loc_18002A244
0x18002a226  test    byte ptr [rcx+1Ch], 10h
0x18002a22a  jz      short loc_18002A244
0x18002a22c  mov     rcx, [rcx+10h]
0x18002a230  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x18002a237  mov     edx, 0Ah
0x18002a23c  mov     r9d, ebx
0x18002a23f  call    WPP_SF_D
0x18002a244  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002a24b  call    cs:__imp_LeaveCriticalSection
0x18002a252  nop     dword ptr [rax+rax+00h]
0x18002a257  lea     r11, [rsp+50h+var_s0]
0x18002a25c  mov     eax, ebx
0x18002a25e  mov     rbx, [r11+30h]
0x18002a262  mov     rsi, [r11+38h]
0x18002a266  mov     rsp, r11
0x18002a269  pop     r15
0x18002a26b  pop     r14
0x18002a26d  pop     r12
0x18002a26f  pop     rdi
0x18002a270  pop     rbp
0x18002a271  retn
0x18002a273  lea     rdx, aMcreatecliente; "MCreateClientEntry:Update"
0x18002a27a  mov     ecx, eax
0x18002a27c  call    DhcpMapJetError
0x18002a281  mov     ebx, eax
0x18002a283  test    eax, eax
0x18002a285  jnz     short loc_18002A20A
0x18002a287  lea     rcx, [rbp+var_18]
0x18002a28b  call    MadcapJetCommitTransaction
0x18002a290  jmp     short loc_18002A244
```
