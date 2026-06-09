# MadcapCreateClientEntry

- ea: `0x18002954c`
- end: `0x180029852`
- name: `MadcapCreateClientEntry`
- size: `774`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000fb40`
- `0x18002a700`
- `0x18002bca8`
- `0x18004e840`

## callees

- `0x18000282c`
- `0x18000e814`
- `0x180028388`
- `0x18002876c`
- `0x1800288a0`
- `0x1800288d0`
- `0x18002954c`

## import_xrefs

- `ESENT!JetUpdate` at `0x1800297b2`
- `ESENT!JetUpdate` at `0x1800297b2`
- `ESENT!JetBeginTransaction` at `0x1800295a7`
- `ESENT!JetBeginTransaction` at `0x1800295a7`
- `KERNEL32!EnterCriticalSection` at `0x180029598`
- `KERNEL32!EnterCriticalSection` at `0x180029598`
- `KERNEL32!LeaveCriticalSection` at `0x18002980b`
- `KERNEL32!LeaveCriticalSection` at `0x18002980b`

## string_xrefs

- `0x180029833`: `MCreateClientEntry:Update`

## pseudocode

```c
__int64 __fastcall MadcapCreateClientEntry(
        const void *a1,
        __int64 a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        char a7,
        char a8,
        char a9,
        char a10,
        int a11,
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
0x18002954c  mov     [rsp-28h+arg_0], rbx
0x180029551  mov     [rsp-28h+arg_8], rsi
0x180029556  mov     [rsp-28h+arg_10], r8d
0x18002955b  push    rbp
0x18002955c  push    rdi
0x18002955d  push    r12
0x18002955f  push    r14
0x180029561  push    r15
0x180029563  mov     rbp, rsp
0x180029566  sub     rsp, 50h
0x18002956a  mov     rbx, cs:DhcpGlobalJetServerSession
0x180029571  mov     rsi, rcx
0x180029574  mov     rax, cs:MadcapGlobalClientTableHandle
0x18002957b  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x180029582  xor     r15d, r15d
0x180029585  mov     [rbp+var_10], rbx
0x180029589  mov     [rbp+var_20], r15d
0x18002958d  mov     r14, r9
0x180029590  mov     [rbp+var_18], r15
0x180029594  mov     [rbp+var_8], rax
0x180029598  call    cs:__imp_EnterCriticalSection
0x18002959f  nop     dword ptr [rax+rax+00h]
0x1800295a4  mov     rcx, rbx; sesid
0x1800295a7  call    cs:__imp_JetBeginTransaction
0x1800295ae  nop     dword ptr [rax+rax+00h]
0x1800295b3  mov     ecx, eax
0x1800295b5  lea     rdx, aMBegintransact; "M:BeginTransaction"
0x1800295bc  call    DhcpMapJetError
0x1800295c1  mov     ebx, eax
0x1800295c3  test    eax, eax
0x1800295c5  jnz     loc_1800297CA
0x1800295cb  mov     rdx, cs:MadcapGlobalClientTable
0x1800295d2  lea     rcx, [rbp+var_18]
0x1800295d6  mov     edi, [rbp+arg_58]
0x1800295dc  mov     eax, r15d
0x1800295df  test    edi, edi
0x1800295e1  mov     r8, rsi
0x1800295e4  mov     rdx, [rdx]
0x1800295e7  setz    al
0x1800295ea  mov     dword ptr [rsp+50h+pcbActual], eax
0x1800295ee  call    MadcapJetPrepareUpdate
0x1800295f3  mov     ebx, eax
0x1800295f5  test    eax, eax
0x1800295f7  jnz     loc_1800297CA
0x1800295fd  lea     r12d, [r15+4]
0x180029601  test    edi, edi
0x180029603  jnz     short loc_180029628
0x180029605  mov     rdx, cs:MadcapGlobalClientTable
0x18002960c  lea     rcx, [rbp+var_18]
0x180029610  mov     r9d, r12d
0x180029613  mov     r8, rsi
0x180029616  mov     edx, [rdx+8]
0x180029619  call    MadcapJetSetValue
0x18002961e  mov     ebx, eax
0x180029620  test    eax, eax
0x180029622  jnz     loc_1800297CA
0x180029628  mov     rdx, cs:MadcapGlobalClientTable
0x18002962f  lea     r8, [rbp+arg_10]
0x180029633  mov     r9, r12
0x180029636  lea     rcx, [rbp+var_18]
0x18002963a  mov     edx, [rdx+58h]
0x18002963d  call    MadcapJetSetValue
0x180029642  mov     ebx, eax
0x180029644  test    eax, eax
0x180029646  jnz     loc_1800297CA
0x18002964c  mov     rdx, cs:MadcapGlobalClientTable
0x180029653  lea     r9d, [rax+1]
0x180029657  lea     r8, [rbp+arg_48]
0x18002965b  lea     rcx, [rbp+var_18]
0x18002965f  mov     edx, [rdx+38h]
0x180029662  call    MadcapJetSetValue
0x180029667  mov     ebx, eax
0x180029669  test    eax, eax
0x18002966b  jnz     loc_1800297CA
0x180029671  mov     rdx, cs:MadcapGlobalClientTable
0x180029678  lea     r8, [rbp+var_20]
0x18002967c  mov     r9, r12
0x18002967f  lea     rcx, [rbp+var_18]
0x180029683  mov     edx, [rdx+48h]
0x180029686  call    MadcapJetSetValue
0x18002968b  mov     ebx, eax
0x18002968d  test    eax, eax
0x18002968f  jnz     loc_1800297CA
0x180029695  mov     rdx, cs:MadcapGlobalClientTable
0x18002969c  lea     rcx, [rbp+var_18]
0x1800296a0  mov     r9d, [rbp+arg_20]
0x1800296a4  mov     r8, r14
0x1800296a7  mov     edx, [rdx+18h]
0x1800296aa  call    MadcapJetSetValue
0x1800296af  mov     ebx, eax
0x1800296b1  test    eax, eax
0x1800296b3  jnz     loc_1800297CA
0x1800296b9  mov     r8, [rbp+arg_28]
0x1800296bd  test    edi, edi
0x1800296bf  jz      short loc_1800296C6
0x1800296c1  test    r8, r8
0x1800296c4  jz      short loc_180029703
0x1800296c6  test    r8, r8
0x1800296c9  jnz     short loc_1800296D0
0x1800296cb  mov     r9, r15
0x1800296ce  jmp     short loc_1800296E6
0x1800296d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800296d4  inc     rax
0x1800296d7  cmp     [r8+rax*2], r15w
0x1800296dc  jnz     short loc_1800296D4
0x1800296de  lea     r9, ds:2[rax*2]
0x1800296e6  mov     rdx, cs:MadcapGlobalClientTable
0x1800296ed  lea     rcx, [rbp+var_18]
0x1800296f1  mov     edx, [rdx+28h]
0x1800296f4  call    MadcapJetSetValue
0x1800296f9  mov     ebx, eax
0x1800296fb  test    eax, eax
0x1800296fd  jnz     loc_1800297CA
0x180029703  mov     rdx, cs:MadcapGlobalClientTable
0x18002970a  lea     r8, [rbp+arg_30]
0x18002970e  mov     edi, 8
0x180029713  lea     rcx, [rbp+var_18]
0x180029717  mov     r9d, edi
0x18002971a  mov     edx, [rdx+68h]
0x18002971d  call    MadcapJetSetValue
0x180029722  mov     ebx, eax
0x180029724  test    eax, eax
0x180029726  jnz     loc_1800297CA
0x18002972c  mov     rdx, cs:MadcapGlobalClientTable
0x180029733  lea     r8, [rbp+arg_38]
0x180029737  mov     r9d, edi
0x18002973a  lea     rcx, [rbp+var_18]
0x18002973e  mov     edx, [rdx+78h]
0x180029741  call    MadcapJetSetValue
0x180029746  mov     ebx, eax
0x180029748  test    eax, eax
0x18002974a  jnz     short loc_1800297CA
0x18002974c  mov     rdx, cs:MadcapGlobalClientTable
0x180029753  lea     r8, DhcpGlobalServerName
0x18002975a  mov     r9d, cs:DhcpGlobalServerNameLen
0x180029761  lea     rcx, [rbp+var_18]
0x180029765  mov     edx, [rdx+98h]
0x18002976b  call    MadcapJetSetValue
0x180029770  mov     ebx, eax
0x180029772  test    eax, eax
0x180029774  jnz     short loc_1800297CA
0x180029776  mov     rdx, cs:MadcapGlobalClientTable
0x18002977d  lea     r8, [rbp+arg_40]
0x180029781  mov     r9, r12
0x180029784  lea     rcx, [rbp+var_18]
0x180029788  mov     edx, [rdx+88h]
0x18002978e  call    MadcapJetSetValue
0x180029793  mov     ebx, eax
0x180029795  test    eax, eax
0x180029797  jnz     short loc_1800297CA
0x180029799  mov     rdx, cs:MadcapGlobalClientTableHandle; tableid
0x1800297a0  xor     r9d, r9d; cbBookmark
0x1800297a3  mov     rcx, cs:DhcpGlobalJetServerSession; sesid
0x1800297aa  xor     r8d, r8d; pvBookmark
0x1800297ad  mov     [rsp+50h+pcbActual], r15; pcbActual
0x1800297b2  call    cs:__imp_JetUpdate
0x1800297b9  nop     dword ptr [rax+rax+00h]
0x1800297be  cmp     eax, 0FFFFF9BBh
0x1800297c3  jnz     short loc_180029833
0x1800297c5  mov     ebx, 4E2Dh
0x1800297ca  lea     rcx, [rbp+var_18]
0x1800297ce  call    MadcapJetRollBack
0x1800297d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800297da  lea     rax, WPP_GLOBAL_Control
0x1800297e1  cmp     rcx, rax
0x1800297e4  jz      short loc_180029804
0x1800297e6  test    byte ptr [rcx+1Ch], 10h
0x1800297ea  jz      short loc_180029804
0x1800297ec  mov     rcx, [rcx+10h]
0x1800297f0  lea     r8, WPP_e36c8f5dbeda3a86eadc8db68e688c0e_Traceguids
0x1800297f7  mov     edx, 0Ah
0x1800297fc  mov     r9d, ebx
0x1800297ff  call    WPP_SF_D
0x180029804  lea     rcx, DhcpGlobalJetDatabaseCritSect; lpCriticalSection
0x18002980b  call    cs:__imp_LeaveCriticalSection
0x180029812  nop     dword ptr [rax+rax+00h]
0x180029817  lea     r11, [rsp+50h+var_s0]
0x18002981c  mov     eax, ebx
0x18002981e  mov     rbx, [r11+30h]
0x180029822  mov     rsi, [r11+38h]
0x180029826  mov     rsp, r11
0x180029829  pop     r15
0x18002982b  pop     r14
0x18002982d  pop     r12
0x18002982f  pop     rdi
0x180029830  pop     rbp
0x180029831  retn
0x180029833  lea     rdx, aMcreatecliente; "MCreateClientEntry:Update"
0x18002983a  mov     ecx, eax
0x18002983c  call    DhcpMapJetError
0x180029841  mov     ebx, eax
0x180029843  test    eax, eax
0x180029845  jnz     short loc_1800297CA
0x180029847  lea     rcx, [rbp+var_18]
0x18002984b  call    MadcapJetCommitTransaction
0x180029850  jmp     short loc_180029804
```
