# CSchemaCache::GetLocalMachineSchemaView(_GUID const &,void * *)

- ea: `0x180039330`
- end: `0x1800394da`
- name: `?GetLocalMachineSchemaView@CSchemaCache@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `426`
- prototype: `__int64 __fastcall(CSchemaCache *__hidden this, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180037c70`
- `0x180039330`
- `0x1800394e0`
- `0x1800395b0`
- `0x18006ed20`
- `0x180091d78`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003939e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003939e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039369`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039369`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800393fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSchemaCache::GetLocalMachineSchemaView(CSchemaCache *this, const struct _GUID *a2, void **a3)
{
  unsigned __int64 v6; // r15
  int Instance; // edi
  LPVOID v9; // rdx
  unsigned __int64 v10; // r13
  __int64 v11; // r12
  _OWORD *v12; // r8
  _QWORD v13[2]; // [rsp+20h] [rbp-78h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-68h] BYREF
  __int128 v15; // [rsp+40h] [rbp-58h]

  v6 = 0;
  *a3 = 0;
  EnterCriticalSection(&CSchemaCache::s_critsec);
  Instance = 0;
  if ( *((_QWORD *)this + 24) )
    goto LABEL_2;
  Instance = CSchemaCache::_EnsureGlobalMappingLoaded(this, 0);
  if ( Instance >= 0 )
  {
    v13[0] = 1;
    v13[1] = this;
    pv[0] = 0;
    v9 = 0;
    pv[1] = 0;
    v15 = 0u;
    v10 = *(_QWORD *)(*((_QWORD *)this + 3) + 72LL);
    while ( v6 < v10 )
    {
      v11 = *(_QWORD *)(*((_QWORD *)this + 3) + 64LL);
      Instance = 0;
      if ( v9 != *((LPVOID *)&v15 + 1)
        || (Instance = CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_EnsureCapacity(
                         pv,
                         (char *)v9 + 1),
            v9 = pv[1],
            Instance >= 0) )
      {
        v9 = (char *)v9 + 1;
        pv[1] = v9;
        v12 = (char *)pv[0] + 16 * (_QWORD)v9 - 16;
        if ( v12 )
        {
          *v12 = *(_OWORD *)(164 * v6 + v11);
          v9 = pv[1];
        }
      }
      ++v6;
      if ( Instance < 0 )
        goto LABEL_7;
    }
    Instance = CSchemaObject<ISchemaView,CSchemaView,SCHEMA_VIEW_INIT>::CreateInstance(
                 &GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6,
                 (char *)this + 192,
                 v13);
LABEL_7:
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( Instance >= 0 )
LABEL_2:
      (***((void (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 24))(*((_QWORD *)this + 24), a2, a3);
  }
  LeaveCriticalSection(&CSchemaCache::s_critsec);
  if ( *((_BYTE *)this + 204) )
  {
    *((_BYTE *)this + 204) = 0;
    _ChangeNotifyHandlers();
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180039330  mov     [rsp+arg_18], rbx
0x180039335  push    rbp
0x180039336  push    rsi
0x180039337  push    rdi
0x180039338  push    r12
0x18003933a  push    r13
0x18003933c  push    r14
0x18003933e  push    r15
0x180039340  sub     rsp, 60h
0x180039344  mov     rax, cs:__security_cookie
0x18003934b  xor     rax, rsp
0x18003934e  mov     [rsp+98h+var_48], rax
0x180039353  mov     r14, r8
0x180039356  mov     rbp, rdx
0x180039359  mov     rbx, rcx
0x18003935c  xor     r15d, r15d
0x18003935f  mov     [r8], r15
0x180039362  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x180039369  call    cs:__imp_EnterCriticalSection
0x18003936f  mov     edi, r15d
0x180039372  cmp     [rbx+0C0h], rdi
0x180039379  jz      loc_18003940B
0x18003937f  mov     rcx, [rbx+0C0h]
0x180039386  mov     rax, [rcx]
0x180039389  mov     r8, r14
0x18003938c  mov     rdx, rbp
0x18003938f  mov     rax, [rax]
0x180039392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039397  lea     rcx, ?s_critsec@CSchemaCache@@0VCCritSec@@A; lpCriticalSection
0x18003939e  call    cs:__imp_LeaveCriticalSection
0x1800393a4  cmp     byte ptr [rbx+0CCh], 0
0x1800393ab  jnz     loc_1800394C9
0x1800393b1  mov     eax, edi
0x1800393b3  mov     rcx, [rsp+98h+var_48]
0x1800393b8  xor     rcx, rsp; StackCookie
0x1800393bb  call    __security_check_cookie
0x1800393c0  mov     rbx, [rsp+98h+arg_18]
0x1800393c8  add     rsp, 60h
0x1800393cc  pop     r15
0x1800393ce  pop     r14
0x1800393d0  pop     r13
0x1800393d2  pop     r12
0x1800393d4  pop     rdi
0x1800393d5  pop     rsi
0x1800393d6  pop     rbp
0x1800393d7  retn
0x1800393d8  lea     r8, [rsp+98h+var_78]
0x1800393dd  lea     rdx, [rbx+0C0h]
0x1800393e4  lea     rcx, _GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6
0x1800393eb  call    ?CreateInstance@?$CSchemaObject@UISchemaView@@VCSchemaView@@USCHEMA_VIEW_INIT@@@@SAJAEBU_GUID@@PEAPEAXPEBUSCHEMA_VIEW_INIT@@@Z; CSchemaObject<ISchemaView,CSchemaView,SCHEMA_VIEW_INIT>::CreateInstance(_GUID const &,void * *,SCHEMA_VIEW_INIT const *)
0x1800393f0  mov     edi, eax
0x1800393f2  mov     rcx, [rsp+98h+pv]; pv
0x1800393f7  test    rcx, rcx
0x1800393fa  jz      short loc_180039402
0x1800393fc  call    cs:__imp_CoTaskMemFree
0x180039402  test    edi, edi
0x180039404  js      short loc_180039397
0x180039406  jmp     loc_18003937F
0x18003940b  xor     edx, edx; int
0x18003940d  mov     rcx, rbx; this
0x180039410  call    ?_EnsureGlobalMappingLoaded@CSchemaCache@@AEAAJH@Z; CSchemaCache::_EnsureGlobalMappingLoaded(int)
0x180039415  mov     edi, eax
0x180039417  test    eax, eax
0x180039419  js      loc_180039397
0x18003941f  mov     [rsp+98h+var_78], 1
0x180039428  mov     [rsp+98h+var_70], rbx
0x18003942d  xorps   xmm0, xmm0
0x180039430  movups  xmmword ptr [rsp+98h+pv], xmm0
0x180039435  movups  [rsp+98h+var_58], xmm0
0x18003943a  mov     [rsp+98h+pv], r15
0x18003943f  mov     rdx, r15
0x180039442  mov     [rsp+98h+pv+8], rdx
0x180039447  mov     qword ptr [rsp+98h+var_58], r15
0x18003944c  mov     qword ptr [rsp+98h+var_58+8], r15
0x180039451  mov     rax, [rbx+18h]
0x180039455  mov     r13, [rax+48h]
0x180039459  cmp     r15, r13
0x18003945c  jnb     loc_1800393D8
0x180039462  mov     rax, [rbx+18h]
0x180039466  mov     r12, [rax+40h]
0x18003946a  xor     edi, edi
0x18003946c  cmp     rdx, qword ptr [rsp+98h+var_58+8]
0x180039471  jnz     short loc_18003948B
0x180039473  inc     rdx
0x180039476  lea     rcx, [rsp+98h+pv]
0x18003947b  call    ?_EnsureCapacity@?$CTSimpleArray@U_GUID@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@U_GUID@@@@V?$CSimpleArrayStandardCompareHelper@U_GUID@@@@V?$CSimpleArrayStandardMergeHelper@U_GUID@@@@@@QEAAJ_K0@Z; CTSimpleArray<_GUID,4294967294,CTPolicyCoTaskMem<_GUID>,CSimpleArrayStandardCompareHelper<_GUID>,CSimpleArrayStandardMergeHelper<_GUID>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180039480  mov     edi, eax
0x180039482  mov     rdx, [rsp+98h+pv+8]
0x180039487  test    eax, eax
0x180039489  js      short loc_1800394BD
0x18003948b  inc     rdx
0x18003948e  mov     [rsp+98h+pv+8], rdx
0x180039493  mov     rcx, rdx
0x180039496  shl     rcx, 4
0x18003949a  mov     r8, [rsp+98h+pv]
0x18003949f  add     r8, 0FFFFFFFFFFFFFFF0h
0x1800394a3  add     r8, rcx
0x1800394a6  jz      short loc_1800394BD
0x1800394a8  imul    rax, r15, 0A4h
0x1800394af  movups  xmm0, xmmword ptr [rax+r12]
0x1800394b4  movups  xmmword ptr [r8], xmm0
0x1800394b8  mov     rdx, [rsp+98h+pv+8]
0x1800394bd  inc     r15
0x1800394c0  test    edi, edi
0x1800394c2  jns     short loc_180039459
0x1800394c4  jmp     loc_1800393F2
0x1800394c9  mov     byte ptr [rbx+0CCh], 0
0x1800394d0  call    ?_ChangeNotifyHandlers@@YAJW4PSCNEVENT@@@Z; _ChangeNotifyHandlers(PSCNEVENT)
0x1800394d5  jmp     loc_1800393B1
```
