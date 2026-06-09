# CVPNDiagHelper::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180009250`
- end: `0x18000942e`
- name: `?GetRepairInfo@CVPNDiagHelper@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(CVPNDiagHelper *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180009250`
- `0x18000b864`
- `0x18000d2f8`
- `0x18000d864`
- `0x18000dd64`
- `0x18000dec6`
- `0x18000ded2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009307`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009307`

## string_xrefs

- `0x1800092a8`: `GetRepairInfo: called for Ras Miniport Missing`
- `0x1800093f6`: `GetRepairInfo: BuildRepairInfos failed, Error= 0x%x.`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::GetRepairInfo(
        CVPNDiagHelper *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  int v6; // ebx
  char *v7; // rbp
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  struct tagRepairInfo *v12; // rax
  struct tagRepairInfo *v13; // rdi
  int v14; // ebp
  _OWORD v16[5]; // [rsp+30h] [rbp-58h] BYREF
  char *v17; // [rsp+90h] [rbp+8h]

  v6 = -2147467263;
  if ( *(_OWORD *)((char *)this + 1436) == RCG_RAS_MINIPORT_MISSING )
  {
    v7 = (char *)this + 1416;
    v17 = (char *)this + 1416;
    v16[0] = ID_RASHC_LOWH_REPAIR_MINIPORT_NOT_INSTALLED;
    CRasLogger::Log((char *)this + 1416, 2, 1, L"CVPNDiagHelper", L"GetRepairInfo: called for Ras Miniport Missing");
    if ( !a3 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10, v11);
    if ( !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v9, v8, v10, v11);
    if ( a3 && a4 )
    {
      v12 = (struct tagRepairInfo *)CoTaskMemAlloc(0x70u);
      v13 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, sizeof(struct tagRepairInfo));
        v14 = 0;
        while ( !memcmp_0(&v16[v14], &CVPNDiagHelper::m_repairInfos + 1, 0x10u) && &CVPNDiagHelper::m_repairInfos )
        {
          v6 = PopulateRepairInfo((const struct tagRepairInfoMap *)&CVPNDiagHelper::m_repairInfos, &v13[v14]);
          if ( v6 < 0 )
            goto LABEL_17;
          if ( ++v14 )
          {
            *a3 = 1;
            v6 = 0;
            *a4 = v13;
            return (unsigned int)v6;
          }
        }
        v6 = -2147023728;
LABEL_17:
        FreeRepairInfos(v13, 1u, 1);
        v7 = v17;
      }
      else
      {
        v6 = -2147024882;
      }
      *a3 = 0;
      *a4 = 0;
    }
    else
    {
      v6 = -2147024809;
    }
    CRasLogger::Log(v7, 2, 1, L"CVPNDiagHelper", L"GetRepairInfo: BuildRepairInfos failed, Error= 0x%x.", v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009250  push    rbx
0x180009252  push    rbp
0x180009253  push    rsi
0x180009254  push    rdi
0x180009255  push    r12
0x180009257  push    r13
0x180009259  push    r14
0x18000925b  push    r15
0x18000925d  sub     rsp, 48h
0x180009261  mov     rax, [rcx+59Ch]
0x180009268  mov     rsi, r9
0x18000926b  cmp     rax, qword ptr cs:RCG_RAS_MINIPORT_MISSING
0x180009272  mov     r14, r8
0x180009275  mov     ebx, 80004001h
0x18000927a  jnz     loc_18000941A
0x180009280  mov     rax, [rcx+5A4h]
0x180009287  cmp     rax, qword ptr cs:RCG_RAS_MINIPORT_MISSING+8
0x18000928e  jnz     loc_18000941A
0x180009294  movups  xmm0, cs:ID_RASHC_LOWH_REPAIR_MINIPORT_NOT_INSTALLED
0x18000929b  lea     rbp, [rcx+588h]
0x1800092a2  mov     r12d, 1
0x1800092a8  lea     rax, aGetrepairinfoC; "GetRepairInfo: called for Ras Miniport "...
0x1800092af  movsx   r8d, r12w
0x1800092b3  lea     r9, aCvpndiaghelper; "CVPNDiagHelper"
0x1800092ba  mov     [rsp+88h+arg_0], rbp
0x1800092c2  mov     rcx, rbp
0x1800092c5  mov     [rsp+88h+var_68], rax
0x1800092ca  lea     edx, [r12+1]
0x1800092cf  movdqu  [rsp+88h+var_58], xmm0
0x1800092d5  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x1800092da  test    r14, r14
0x1800092dd  jnz     short loc_1800092E4
0x1800092df  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092e4  test    rsi, rsi
0x1800092e7  jnz     short loc_1800092EE
0x1800092e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800092ee  test    r14, r14
0x1800092f1  jz      loc_1800093EB
0x1800092f7  test    rsi, rsi
0x1800092fa  jz      loc_1800093EB
0x180009300  mov     ebx, 70h ; 'p'
0x180009305  mov     ecx, ebx; cb
0x180009307  call    cs:__imp_CoTaskMemAlloc
0x18000930e  nop     dword ptr [rax+rax+00h]
0x180009313  mov     rdi, rax
0x180009316  test    rax, rax
0x180009319  jnz     short loc_180009325
0x18000931b  mov     ebx, 8007000Eh
0x180009320  jmp     loc_1800093DB
0x180009325  mov     r8, rbx; Size
0x180009328  xor     edx, edx; Val
0x18000932a  mov     rcx, rdi; void *
0x18000932d  call    memset_0
0x180009332  xor     ebp, ebp
0x180009334  lea     rcx, ?m_repairInfos@CVPNDiagHelper@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CVPNDiagHelper::m_repairInfos
0x18000933b  mov     eax, ebp
0x18000933d  lea     r13, [rsp+88h+var_58]
0x180009342  shl     rax, 4
0x180009346  xor     ebx, ebx
0x180009348  add     r13, rax
0x18000934b  mov     r15d, ebp
0x18000934e  lea     rdx, [rcx+8]
0x180009352  mov     eax, ebx
0x180009354  imul    r12, rax, 78h ; 'x'
0x180009358  mov     r8d, 10h; Size
0x18000935e  mov     rcx, r13; Buf1
0x180009361  add     rdx, r12; Buf2
0x180009364  call    memcmp_0
0x180009369  test    eax, eax
0x18000936b  jz      short loc_18000937D
0x18000936d  inc     ebx
0x18000936f  cmp     ebx, 1
0x180009372  jnb     short loc_1800093BA
0x180009374  lea     rcx, ?m_repairInfos@CVPNDiagHelper@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CVPNDiagHelper::m_repairInfos
0x18000937b  jmp     short loc_18000934E
0x18000937d  lea     rcx, ?m_repairInfos@CVPNDiagHelper@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CVPNDiagHelper::m_repairInfos
0x180009384  add     rcx, r12; struct tagRepairInfoMap *
0x180009387  jz      short loc_1800093BA
0x180009389  imul    rdx, r15, 70h ; 'p'
0x18000938d  add     rdx, rdi; struct tagRepairInfo *
0x180009390  call    ?PopulateRepairInfo@@YAJPEBUtagRepairInfoMap@@PEAUtagRepairInfo@@@Z; PopulateRepairInfo(tagRepairInfoMap const *,tagRepairInfo *)
0x180009395  mov     ebx, eax
0x180009397  test    eax, eax
0x180009399  js      short loc_1800093BF
0x18000939b  mov     r12d, 1
0x1800093a1  lea     rcx, ?m_repairInfos@CVPNDiagHelper@@0QBUtagRepairInfoMap@@B; tagRepairInfoMap const near * const CVPNDiagHelper::m_repairInfos
0x1800093a8  add     ebp, r12d
0x1800093ab  cmp     ebp, r12d
0x1800093ae  jb      short loc_18000933B
0x1800093b0  mov     [r14], r12d
0x1800093b3  xor     ebx, ebx
0x1800093b5  mov     [rsi], rdi
0x1800093b8  jmp     short loc_18000941A
0x1800093ba  mov     ebx, 80070490h
0x1800093bf  mov     r12d, 1
0x1800093c5  mov     rcx, rdi; pv
0x1800093c8  mov     r8d, r12d; int
0x1800093cb  mov     edx, r12d; unsigned int
0x1800093ce  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x1800093d3  mov     rbp, [rsp+88h+arg_0]
0x1800093db  mov     dword ptr [r14], 0
0x1800093e2  mov     qword ptr [rsi], 0
0x1800093e9  jmp     short loc_1800093F0
0x1800093eb  mov     ebx, 80070057h
0x1800093f0  mov     eax, ebx
0x1800093f2  mov     [rsp+88h+var_60], ebx
0x1800093f6  lea     rax, aGetrepairinfoB; "GetRepairInfo: BuildRepairInfos failed,"...
0x1800093fd  movsx   r8d, r12w
0x180009401  lea     r9, aCvpndiaghelper; "CVPNDiagHelper"
0x180009408  mov     [rsp+88h+var_68], rax
0x18000940d  mov     edx, 2
0x180009412  mov     rcx, rbp
0x180009415  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000941a  mov     eax, ebx
0x18000941c  add     rsp, 48h
0x180009420  pop     r15
0x180009422  pop     r14
0x180009424  pop     r13
0x180009426  pop     r12
0x180009428  pop     rdi
0x180009429  pop     rsi
0x18000942a  pop     rbp
0x18000942b  pop     rbx
0x18000942c  retn
```
