# CDwmAppHost::s_LpcCommandHandler(IPortMessage *,PORT_CONTEXT const *,int *,int *)

- ea: `0x140002630`
- end: `0x140002848`
- name: `?s_LpcCommandHandler@CDwmAppHost@@CAJPEAUIPortMessage@@PEBUPORT_CONTEXT@@PEAH2@Z`
- size: `536`
- prototype: `__int64 __fastcall(struct IPortMessage *, const struct PORT_CONTEXT *, int *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140002630`
- `0x140002850`
- `0x1400028cc`
- `0x140002988`
- `0x140002c1c`
- `0x140002c64`
- `0x140002e6c`
- `0x140002f10`
- `0x1400065cc`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400027b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400027b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400027d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400027d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027b7`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostHandleGhostMsg` at `0x1400026dc`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostHandleGhostMsg` at `0x1400026fc`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostHandleGhostMsg` at `0x1400026dc`
- `ext-ms-win-composition-ghost-l1-1-0!DWMGhostHandleGhostMsg` at `0x1400026fc`

## pseudocode

```c
__int64 __fastcall CDwmAppHost::s_LpcCommandHandler(
        struct IPortMessage *a1,
        const struct PORT_CONTEXT *a2,
        int *a3,
        int *a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  CDwmAppHost *v10; // rcx
  __int64 result; // rax
  int v12; // eax
  CDwmAppHost *v13; // rcx
  CDwmAppHost *v14; // rcx

  v7 = 0;
  v8 = (*(__int64 (__fastcall **)(struct IPortMessage *, const struct PORT_CONTEXT *))(*(_QWORD *)a1 + 16LL))(a1, a2);
  v9 = *(_WORD *)(v8 + 4) >> 15;
  *a3 = 1;
  *a4 = 0;
  if ( (*(unsigned __int16 *)(v8 + 4) & 0xFFFF00FF) == 1 )
  {
    if ( *(_DWORD *)(v8 + 40) == 536870913 )
    {
      if ( *(_DWORD *)(v8 + 8) == (_DWORD)qword_14001C060 )
      {
        (*(void (__fastcall **)(struct IPortMessage *, _QWORD, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0, v9);
        *a4 = 1;
        CDwmAppHost::Shutdown(v14, -805305602);
      }
      return v7;
    }
    if ( *(_DWORD *)(v8 + 40) != 536870915 )
    {
      if ( *(_DWORD *)(v8 + 40) == 1073741876 )
      {
        if ( (_BYTE)v9 && (unsigned __int8)IsDWMGhostHandleGhostMsgPresent() )
        {
          DWMGhostHandleGhostMsg(a1);
          *a4 = 1;
        }
        return v7;
      }
      goto LABEL_6;
    }
    if ( *(_DWORD *)(v8 + 8) != (_DWORD)qword_14001C060 )
      return v7;
    CSettingsManager::Cleanup((CSettingsManager *)&qword_14001C078);
    AcquireSRWLockExclusive(&SRWLock);
    GetCurrentThreadId();
    byte_14001C098 = 1;
    dword_14001C0B0 = 0;
    ReleaseSRWLockExclusive(&SRWLock);
    CSettingsManager::RefreshPreferencesAndPolicies((CSettingsManager *)&qword_14001C078);
    CDwmAppHost::LpcNotifySettingsChange(v13, 0x7D3u);
    (*(void (__fastcall **)(struct IPortMessage *, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, 0);
    result = 0;
    *a4 = 1;
  }
  else
  {
    if ( (*(unsigned __int16 *)(v8 + 4) & 0xFFFF00FF) != 3 )
      return v7;
    if ( *(_DWORD *)(v8 + 40) == 536870914 )
    {
      if ( *(_DWORD *)(v8 + 8) != (_DWORD)qword_14001C060 )
        return v7;
      CSettingsManager::PropagateUserLogon(
        (CSettingsManager *)&qword_14001C078,
        *(HKEY *)(v8 + 52),
        *(HKEY *)(v8 + 60),
        *(HKEY *)(v8 + 68),
        *(_DWORD *)(v8 + 76) != 0);
      return 0;
    }
    else
    {
      v10 = (CDwmAppHost *)(unsigned int)(*(_DWORD *)(v8 + 40) - 1073741876);
      if ( *(_DWORD *)(v8 + 40) == 1073741876 )
      {
        if ( !(_BYTE)v9 || !(unsigned __int8)IsDWMGhostHandleGhostMsgPresent() )
          return v7;
        DWMGhostHandleGhostMsg(a1);
        return 0;
      }
      else
      {
        if ( *(_DWORD *)(v8 + 40) != 1073741878 )
        {
LABEL_6:
          *a3 = 0;
          return v7;
        }
        if ( !(_BYTE)v9 )
          return v7;
        *a3 = 0;
        v12 = CDwmAppHost::HandleDisplayModeChange(v10);
        v7 = v12;
        if ( v12 >= 0 )
          return v7;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v12, 0x1BEu, 0);
        return v7;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140002630  push    rbx
0x140002632  push    rbp
0x140002633  push    rsi
0x140002634  push    rdi
0x140002635  push    r14
0x140002637  sub     rsp, 30h
0x14000263b  mov     rax, [rcx]
0x14000263e  xor     ebp, ebp
0x140002640  mov     r14, r9
0x140002643  mov     rdi, r8
0x140002646  mov     rsi, rcx
0x140002649  mov     ebx, ebp
0x14000264b  mov     rax, [rax+10h]
0x14000264f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002654  mov     rdx, rax
0x140002657  movzx   r8d, word ptr [rax+4]
0x14000265c  mov     dword ptr [rdi], 1
0x140002662  mov     [r14], ebp
0x140002665  movzx   eax, word ptr [rax+4]
0x140002669  and     eax, 0FFFF00FFh
0x14000266e  shr     r8w, 0Fh
0x140002673  sub     eax, 1
0x140002676  jz      short loc_1400026AB
0x140002678  cmp     eax, 2
0x14000267b  jnz     short loc_14000269E
0x14000267d  mov     ecx, [rdx+28h]
0x140002680  sub     ecx, 20000002h
0x140002686  jz      loc_14000270F
0x14000268c  sub     ecx, 20000032h; this
0x140002692  jz      short loc_1400026EB
0x140002694  cmp     ecx, eax
0x140002696  jz      loc_140002749
0x14000269c  mov     [rdi], ebp
0x14000269e  mov     eax, ebx
0x1400026a0  add     rsp, 30h
0x1400026a4  pop     r14
0x1400026a6  pop     rdi
0x1400026a7  pop     rsi
0x1400026a8  pop     rbp
0x1400026a9  pop     rbx
0x1400026aa  retn
0x1400026ab  mov     ecx, [rdx+28h]
0x1400026ae  sub     ecx, 20000001h
0x1400026b4  jz      loc_140002812
0x1400026ba  sub     ecx, 2
0x1400026bd  jz      loc_14000278F
0x1400026c3  cmp     ecx, 20000031h
0x1400026c9  jnz     short loc_14000269C
0x1400026cb  test    r8b, r8b
0x1400026ce  jz      short loc_14000269E
0x1400026d0  call    IsDWMGhostHandleGhostMsgPresent
0x1400026d5  test    al, al
0x1400026d7  jz      short loc_14000269E
0x1400026d9  mov     rcx, rsi
0x1400026dc  call    cs:__imp_DWMGhostHandleGhostMsg
0x1400026e2  mov     dword ptr [r14], 1
0x1400026e9  jmp     short loc_14000269E
0x1400026eb  test    r8b, r8b
0x1400026ee  jz      short loc_14000269E
0x1400026f0  call    IsDWMGhostHandleGhostMsgPresent
0x1400026f5  test    al, al
0x1400026f7  jz      short loc_14000269E
0x1400026f9  mov     rcx, rsi
0x1400026fc  call    cs:__imp_DWMGhostHandleGhostMsg
0x140002702  mov     eax, ebx
0x140002704  add     rsp, 30h
0x140002708  pop     r14
0x14000270a  pop     rdi
0x14000270b  pop     rsi
0x14000270c  pop     rbp
0x14000270d  pop     rbx
0x14000270e  retn
0x14000270f  mov     eax, dword ptr cs:qword_14001C060
0x140002715  cmp     [rdx+8], eax
0x140002718  jnz     short loc_14000269E
0x14000271a  cmp     [rdx+4Ch], ebx
0x14000271d  lea     rcx, qword_14001C078; this
0x140002724  mov     r9, [rdx+44h]; HKEY
0x140002728  mov     r8, [rdx+3Ch]; HKEY
0x14000272c  setnz   al
0x14000272f  mov     rdx, [rdx+34h]; HKEY
0x140002733  mov     [rsp+58h+var_38], al; bool
0x140002737  call    ?PropagateUserLogon@CSettingsManager@@QEAAXPEAUHKEY__@@00_N@Z; CSettingsManager::PropagateUserLogon(HKEY__ *,HKEY__ *,HKEY__ *,bool)
0x14000273c  mov     eax, ebx
0x14000273e  add     rsp, 30h
0x140002742  pop     r14
0x140002744  pop     rdi
0x140002745  pop     rsi
0x140002746  pop     rbp
0x140002747  pop     rbx
0x140002748  retn
0x140002749  test    r8b, r8b
0x14000274c  jz      loc_14000269E
0x140002752  mov     [rdi], ebp
0x140002754  call    ?HandleDisplayModeChange@CDwmAppHost@@AEAAJXZ; CDwmAppHost::HandleDisplayModeChange(void)
0x140002759  mov     ebx, eax
0x14000275b  test    eax, eax
0x14000275d  jns     loc_14000269E
0x140002763  mov     [rsp+58h+var_30], rbp; void *
0x140002768  mov     r9d, eax; int
0x14000276b  xor     r8d, r8d; unsigned int
0x14000276e  mov     dword ptr [rsp+58h+var_38], 1BEh; unsigned int
0x140002776  xor     edx, edx; int *
0x140002778  mov     ecx, 14h; unsigned int
0x14000277d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140002782  mov     eax, ebx
0x140002784  add     rsp, 30h
0x140002788  pop     r14
0x14000278a  pop     rdi
0x14000278b  pop     rsi
0x14000278c  pop     rbp
0x14000278d  pop     rbx
0x14000278e  retn
0x14000278f  mov     eax, dword ptr cs:qword_14001C060
0x140002795  cmp     [rdx+8], eax
0x140002798  jnz     loc_14000269E
0x14000279e  lea     rcx, qword_14001C078; this
0x1400027a5  call    ?Cleanup@CSettingsManager@@QEAAXXZ; CSettingsManager::Cleanup(void)
0x1400027aa  lea     rcx, SRWLock; SRWLock
0x1400027b1  call    cs:__imp_AcquireSRWLockExclusive
0x1400027b7  call    cs:__imp_GetCurrentThreadId
0x1400027bd  lea     rcx, SRWLock; SRWLock
0x1400027c4  mov     cs:byte_14001C098, 1
0x1400027cb  mov     cs:dword_14001C0B0, ebp
0x1400027d1  call    cs:__imp_ReleaseSRWLockExclusive
0x1400027d7  lea     rcx, qword_14001C078; this
0x1400027de  call    ?RefreshPreferencesAndPolicies@CSettingsManager@@QEAAXXZ; CSettingsManager::RefreshPreferencesAndPolicies(void)
0x1400027e3  mov     edx, 7D3h; unsigned int
0x1400027e8  call    ?LpcNotifySettingsChange@CDwmAppHost@@AEAAJK@Z; CDwmAppHost::LpcNotifySettingsChange(ulong)
0x1400027ed  mov     rax, [rsi]
0x1400027f0  xor     edx, edx
0x1400027f2  mov     rcx, rsi
0x1400027f5  mov     rax, [rax+18h]
0x1400027f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027fe  mov     eax, ebx
0x140002800  mov     dword ptr [r14], 1
0x140002807  add     rsp, 30h
0x14000280b  pop     r14
0x14000280d  pop     rdi
0x14000280e  pop     rsi
0x14000280f  pop     rbp
0x140002810  pop     rbx
0x140002811  retn
0x140002812  mov     eax, dword ptr cs:qword_14001C060
0x140002818  cmp     [rdx+8], eax
0x14000281b  jnz     loc_14000269E
0x140002821  mov     rax, [rsi]
0x140002824  xor     edx, edx
0x140002826  mov     rcx, rsi
0x140002829  mov     rax, [rax+18h]
0x14000282d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002832  mov     edx, 0D00002FEh; int
0x140002837  mov     dword ptr [r14], 1
0x14000283e  call    ?Shutdown@CDwmAppHost@@QEAAXJ@Z; CDwmAppHost::Shutdown(long)
0x140002843  jmp     loc_14000269E
```
