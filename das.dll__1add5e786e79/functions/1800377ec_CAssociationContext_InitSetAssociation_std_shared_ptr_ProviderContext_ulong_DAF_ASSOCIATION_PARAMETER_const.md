# CAssociationContext::InitSetAssociation(std::shared_ptr<ProviderContext>,ulong,_DAF_ASSOCIATION_PARAMETER const *)

- ea: `0x1800377ec`
- end: `0x1800379c3`
- name: `?InitSetAssociation@CAssociationContext@@IEAAJV?$shared_ptr@VProviderContext@@@std@@KPEBU_DAF_ASSOCIATION_PARAMETER@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180055614`
- `0x180055e2c`

## callees

- `0x18001a268`
- `0x1800377ec`
- `0x180053cb0`
- `0x1800585a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003786f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003788b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003792a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003786f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003788b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003792a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003789d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003789d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003794d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18003794d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180037998`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180037998`

## pseudocode

```c
__int64 __fastcall CAssociationContext::InitSetAssociation(char *pv, _QWORD *a2, unsigned int a3, __int64 a4)
{
  unsigned int v6; // ebx
  BOOL v7; // eax
  __int64 i; // rcx
  __int64 v9; // rax
  HANDLE EventW; // rax
  int v11; // edx
  int v12; // r9d
  signed int LastError; // eax
  HANDLE v14; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct _TP_WAIT **v16; // rdx
  std::_Ref_count_base *v17; // rcx
  struct _TP_WAIT *v19; // [rsp+70h] [rbp+8h] BYREF

  v6 = 0;
  if ( (pv[24] & 0x20) != 0 )
  {
    v7 = (pv[24] & 0x40) != 0 || *(_DWORD *)(*a2 + 64LL) == 1;
    *((_DWORD *)pv + 104) = v7;
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      if ( *(_DWORD *)(a4 + 40 * i + 16) == 9 )
      {
        v9 = *(_QWORD *)(a4 + 40 * i) - DEVPKEY_DasParam_PrimaryAepId;
        if ( !v9 )
          v9 = *(_QWORD *)(a4 + 40 * i + 8) - *((_QWORD *)&DEVPKEY_DasParam_PrimaryAepId + 1);
        if ( !v9 )
        {
          EventW = CreateEventW(0, 1, 0, 0);
          *((_QWORD *)pv + 55) = EventW;
          goto LABEL_15;
        }
      }
    }
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)pv + 56) = EventW;
LABEL_15:
    if ( !EventW )
      goto LABEL_16;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SSSq(*((_QWORD *)WPP_GLOBAL_Control + 5), v11, (unsigned int)L"non-synced", v12);
    v14 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)pv + 54) = v14;
    if ( v14
      && (ThreadpoolWait = CreateThreadpoolWait(CAssociationContext::SetFinalizeWaitCallback, pv, 0),
          (v19 = ThreadpoolWait) != 0) )
    {
      v16 = (struct _TP_WAIT **)*((_QWORD *)pv + 69);
      if ( v16 == *((struct _TP_WAIT ***)pv + 70) )
      {
        std::vector<_TP_WAIT *>::_Emplace_reallocate<_TP_WAIT *>(pv + 544, v16, &v19);
        ThreadpoolWait = v19;
      }
      else
      {
        *v16 = ThreadpoolWait;
        *((_QWORD *)pv + 69) += 8LL;
      }
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)pv + 54), 0);
    }
    else
    {
LABEL_16:
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  v17 = (std::_Ref_count_base *)a2[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  return v6;
}

```

## disassembly

```asm
0x1800377ec  mov     [rsp+arg_8], rbx
0x1800377f1  mov     [rsp+arg_10], rbp
0x1800377f6  push    rsi
0x1800377f7  push    rdi
0x1800377f8  push    r14
0x1800377fa  sub     rsp, 50h
0x1800377fe  mov     r14, rdx
0x180037801  mov     rdi, rcx
0x180037804  xor     ebx, ebx
0x180037806  test    byte ptr [rcx+18h], 20h
0x18003780a  jz      loc_18003799E
0x180037810  lea     ebp, [rbx+1]
0x180037813  test    byte ptr [rcx+18h], 40h
0x180037817  jnz     short loc_180037825
0x180037819  mov     rax, [rdx]
0x18003781c  cmp     [rax+40h], ebp
0x18003781f  jz      short loc_180037825
0x180037821  xor     eax, eax
0x180037823  jmp     short loc_180037827
0x180037825  mov     eax, ebp
0x180037827  mov     [rcx+1A0h], eax
0x18003782d  xor     ecx, ecx
0x18003782f  cmp     ecx, r8d
0x180037832  jnb     short loc_18003787E
0x180037834  lea     rdx, [rcx+rcx*4]
0x180037838  cmp     dword ptr [r9+rdx*8+10h], 9
0x18003783e  jnz     short loc_18003785E
0x180037840  mov     rax, [r9+rdx*8]
0x180037844  sub     rax, qword ptr cs:DEVPKEY_DasParam_PrimaryAepId
0x18003784b  jnz     short loc_180037859
0x18003784d  mov     rax, [r9+rdx*8+8]
0x180037852  sub     rax, qword ptr cs:DEVPKEY_DasParam_PrimaryAepId+8
0x180037859  test    rax, rax
0x18003785c  jz      short loc_180037862
0x18003785e  add     ecx, ebp
0x180037860  jmp     short loc_18003782F
0x180037862  xor     sil, sil
0x180037865  xor     r9d, r9d; lpName
0x180037868  xor     r8d, r8d; bInitialState
0x18003786b  mov     edx, ebp; bManualReset
0x18003786d  xor     ecx, ecx; lpEventAttributes
0x18003786f  call    cs:__imp_CreateEventW
0x180037875  mov     [rdi+1B8h], rax
0x18003787c  jmp     short loc_180037898
0x18003787e  mov     sil, bpl
0x180037881  xor     r9d, r9d; lpName
0x180037884  xor     r8d, r8d; bInitialState
0x180037887  mov     edx, ebp; bManualReset
0x180037889  xor     ecx, ecx; lpEventAttributes
0x18003788b  call    cs:__imp_CreateEventW
0x180037891  mov     [rdi+1C0h], rax
0x180037898  test    rax, rax
0x18003789b  jnz     short loc_1800378BB
0x18003789d  call    cs:__imp_GetLastError
0x1800378a3  mov     ebx, eax
0x1800378a5  test    eax, eax
0x1800378a7  jle     loc_18003799E
0x1800378ad  movzx   ebx, ax
0x1800378b0  or      ebx, 80070000h
0x1800378b6  jmp     loc_18003799E
0x1800378bb  lea     rax, WPP_RECORDER_INITIALIZED
0x1800378c2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800378c9  jz      short loc_180037920
0x1800378cb  lea     rcx, aNot_0; "' not"
0x1800378d2  lea     rax, dword_18008C97C
0x1800378d9  test    sil, sil
0x1800378dc  cmovz   rax, rcx
0x1800378e0  lea     r8, aNonSynced; "non-synced"
0x1800378e7  lea     rcx, aSynced; "synced"
0x1800378ee  cmp     [rdi+1A0h], ebp
0x1800378f4  cmovnz  rcx, r8
0x1800378f8  mov     [rsp+68h+var_28], rdi
0x1800378fd  mov     [rsp+68h+var_30], rax
0x180037902  mov     rax, [rdi+8]
0x180037906  mov     [rsp+68h+var_38], rax
0x18003790b  mov     [rsp+68h+var_40], rcx
0x180037910  mov     rcx, cs:WPP_GLOBAL_Control
0x180037917  mov     rcx, [rcx+28h]
0x18003791b  call    WPP_RECORDER_SF_SSSq
0x180037920  xor     r9d, r9d; lpName
0x180037923  xor     r8d, r8d; bInitialState
0x180037926  mov     edx, ebp; bManualReset
0x180037928  xor     ecx, ecx; lpEventAttributes
0x18003792a  call    cs:__imp_CreateEventW
0x180037930  mov     [rdi+1B0h], rax
0x180037937  test    rax, rax
0x18003793a  jz      loc_18003789D
0x180037940  xor     r8d, r8d; pcbe
0x180037943  mov     rdx, rdi; pv
0x180037946  lea     rcx, ?SetFinalizeWaitCallback@CAssociationContext@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x18003794d  call    cs:__imp_CreateThreadpoolWait
0x180037953  mov     [rsp+68h+arg_0], rax
0x180037958  test    rax, rax
0x18003795b  jz      loc_18003789D
0x180037961  lea     rcx, [rdi+220h]
0x180037968  mov     rdx, [rcx+8]
0x18003796c  cmp     rdx, [rcx+10h]
0x180037970  jz      short loc_18003797C
0x180037972  mov     [rdx], rax
0x180037975  add     qword ptr [rcx+8], 8
0x18003797a  jmp     short loc_18003798B
0x18003797c  lea     r8, [rsp+68h+arg_0]
0x180037981  call    ??$_Emplace_reallocate@PEAU_TP_WAIT@@@?$vector@PEAU_TP_WAIT@@V?$allocator@PEAU_TP_WAIT@@@std@@@std@@AEAAPEAPEAU_TP_WAIT@@QEAPEAU2@$$QEAPEAU2@@Z; std::vector<_TP_WAIT *>::_Emplace_reallocate<_TP_WAIT *>(_TP_WAIT * * const,_TP_WAIT * &&)
0x180037986  mov     rax, [rsp+68h+arg_0]
0x18003798b  xor     r8d, r8d; pftTimeout
0x18003798e  mov     rdx, [rdi+1B0h]; h
0x180037995  mov     rcx, rax; pwa
0x180037998  call    cs:__imp_SetThreadpoolWait
0x18003799e  mov     rcx, [r14+8]; this
0x1800379a2  test    rcx, rcx
0x1800379a5  jz      short loc_1800379AC
0x1800379a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800379ac  mov     eax, ebx
0x1800379ae  lea     r11, [rsp+68h+var_18]
0x1800379b3  mov     rbx, [r11+28h]
0x1800379b7  mov     rbp, [r11+30h]
0x1800379bb  mov     rsp, r11
0x1800379be  pop     r14
0x1800379c0  pop     rdi
0x1800379c1  pop     rsi
0x1800379c2  retn
```
