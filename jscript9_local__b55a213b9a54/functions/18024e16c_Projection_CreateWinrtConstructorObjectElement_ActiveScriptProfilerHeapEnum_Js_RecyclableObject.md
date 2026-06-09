# Projection::CreateWinrtConstructorObjectElement(ActiveScriptProfilerHeapEnum *,Js::RecyclableObject *)

- ea: `0x18024e16c`
- end: `0x18024e396`
- name: `?CreateWinrtConstructorObjectElement@Projection@@YAPEAUHostProfilerHeapObject@@PEAVActiveScriptProfilerHeapEnum@@PEAVRecyclableObject@Js@@@Z`
- size: `554`
- prototype: `struct HostProfilerHeapObject *__fastcall(Projection *__hidden this, struct ActiveScriptProfilerHeapEnum *, struct Js::RecyclableObject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1801d686c`

## callees

- `0x1801ab38c`
- `0x1801bced8`
- `0x1801cc26b`
- `0x18022bd8c`
- `0x18022bf34`
- `0x18022c500`
- `0x1802323a8`
- `0x18024e16c`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e208`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e239`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e2c4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e208`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e239`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18024e2c4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e2f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e30d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e2f8`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18024e30d`

## pseudocode

```c
struct HostProfilerHeapObject *__fastcall Projection::CreateWinrtConstructorObjectElement(
        Projection *this,
        struct ActiveScriptProfilerHeapEnum *a2,
        struct Js::RecyclableObject *a3)
{
  _QWORD *v3; // rdi
  unsigned __int16 v4; // r15
  struct Js::ScriptContext *v5; // r12
  __int64 v6; // rsi
  struct Projection::EventProjectionHandler *v7; // rdx
  unsigned int EventAndEventHandlerCount; // ebp
  __int64 v9; // rcx
  SIZE_T v10; // rbp
  int v11; // ebx
  _QWORD *v12; // rax
  void *v13; // rax
  struct Projection::EventProjectionHandler *v14; // r8
  struct _PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST *v15; // r9
  char *v16; // rax
  char *v17; // rbx
  __int64 i; // rsi
  void *v19; // rcx
  __int64 v20; // r9
  __int64 v22[7]; // [rsp+20h] [rbp-38h] BYREF

  v3 = 0;
  v4 = 0;
  v5 = *(struct Js::ScriptContext **)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) + 1072LL);
  v6 = *(_QWORD *)(*((_QWORD *)a2 + 8) + 24LL);
  if ( Projection::ThisInfo::CanHoldEventCookies((Projection::ThisInfo *)v6) )
    EventAndEventHandlerCount = Projection::GetEventAndEventHandlerCount((Projection *)(v6 + 48), v7);
  else
    EventAndEventHandlerCount = 0;
  v22[0] = 0;
  v9 = *(_QWORD *)(v6 + 40);
  if ( v9 )
  {
    v11 = IUnknown::QueryInterface<IUnknown>(v9, v22);
    if ( v11 < 0 )
      goto LABEL_17;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
    v12 = CoTaskMemAlloc(8u);
    v3 = v12;
    if ( !v12 )
    {
      v11 = -2147024882;
      goto LABEL_23;
    }
    v4 = 1;
    *v12 = 0;
    v13 = CoTaskMemAlloc(16 * (EventAndEventHandlerCount + 4));
    *v3 = v13;
    if ( !v13 )
    {
      v11 = -2147024882;
LABEL_18:
      for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
      {
        v19 = (void *)v3[i];
        if ( v19 )
          CoTaskMemFree(v19);
      }
      CoTaskMemFree(v3);
LABEL_23:
      Js::JavascriptError::MapAndThrowError(v5, v11);
    }
    memset_0(v13, 0, 16 * (EventAndEventHandlerCount + 4));
    *(_QWORD *)(*v3 + 8LL) = v22[0];
    *(_DWORD *)(*v3 + 16LL) = *(_DWORD *)(v6 + 32);
    *(_DWORD *)(*v3 + 20LL) = 1424;
    *(_WORD *)(*v3 + 40LL) = 1;
    *(_DWORD *)(*v3 + 48LL) = 10;
    if ( Projection::ThisInfo::CanHoldEventCookies((Projection::ThisInfo *)v6) )
      Projection::PopulateProfilerEventInfo(this, (struct ActiveScriptProfilerHeapEnum *)(v6 + 48), v14, v15);
    else
      *(_DWORD *)v14 = 0;
    v10 = 72;
  }
  else
  {
    v10 = 48;
  }
  v16 = (char *)CoTaskMemAlloc(v10);
  v17 = v16;
  if ( !v16 )
  {
    v11 = -2147024882;
LABEL_17:
    if ( !v3 )
      goto LABEL_23;
    goto LABEL_18;
  }
  memset_0(v16, 0, v10);
  *((_DWORD *)v17 + 4) = *(_DWORD *)(v6 + 32);
  *((_DWORD *)v17 + 5) = 1024;
  if ( v22[0] )
  {
    *((_WORD *)v17 + 20) = 1;
    *((_DWORD *)v17 + 12) = 4;
    *((_DWORD *)v17 + 14) = -1;
    ActiveScriptProfilerHeapEnum::SetRelationshipInfo(
      this,
      (struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *)(v17 + 56),
      PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT);
    *((_QWORD *)v17 + 8) = v20;
    *((_WORD *)v17 + 13) = v4;
    *((_QWORD *)v17 + 4) = v3;
  }
  return (struct HostProfilerHeapObject *)v17;
}

```

## disassembly

```asm
0x18024e16c  mov     rax, rsp
0x18024e16f  mov     [rax+18h], rbx
0x18024e173  mov     [rax+20h], rbp
0x18024e177  mov     [rax+10h], rdx
0x18024e17b  mov     [rax+8], rcx
0x18024e17f  push    rsi
0x18024e180  push    rdi
0x18024e181  push    r12
0x18024e183  push    r14
0x18024e185  push    r15
0x18024e187  sub     rsp, 30h
0x18024e18b  mov     rax, [rdx+8]
0x18024e18f  xor     edi, edi
0x18024e191  xor     r15d, r15d
0x18024e194  mov     rcx, [rax+8]
0x18024e198  mov     rax, [rdx+40h]
0x18024e19c  mov     r12, [rcx+430h]
0x18024e1a3  mov     rsi, [rax+18h]
0x18024e1a7  mov     rcx, rsi; this
0x18024e1aa  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x18024e1af  test    al, al
0x18024e1b1  jnz     short loc_18024E1B7
0x18024e1b3  xor     ebp, ebp
0x18024e1b5  jmp     short loc_18024E1C2
0x18024e1b7  lea     rcx, [rsi+30h]; this
0x18024e1bb  call    ?GetEventAndEventHandlerCount@Projection@@YAIPEAVEventProjectionHandler@1@@Z; Projection::GetEventAndEventHandlerCount(Projection::EventProjectionHandler *)
0x18024e1c0  mov     ebp, eax
0x18024e1c2  mov     [rsp+58h+var_38], rdi
0x18024e1c7  mov     r14d, 1
0x18024e1cd  mov     rcx, [rsi+28h]
0x18024e1d1  test    rcx, rcx
0x18024e1d4  jnz     short loc_18024E1DE
0x18024e1d6  lea     ebp, [rcx+30h]
0x18024e1d9  jmp     loc_18024E2C1
0x18024e1de  lea     rdx, [rsp+58h+var_38]
0x18024e1e3  call    ??$QueryInterface@UIUnknown@@@IUnknown@@QEAAJPEAPEAU0@@Z; IUnknown::QueryInterface<IUnknown>(IUnknown * *)
0x18024e1e8  mov     ebx, eax
0x18024e1ea  test    eax, eax
0x18024e1ec  js      loc_18024E2DD
0x18024e1f2  mov     rcx, [rsp+58h+var_38]
0x18024e1f7  mov     rax, [rcx]
0x18024e1fa  mov     rax, [rax+10h]
0x18024e1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024e203  mov     ecx, 8; cb
0x18024e208  call    cs:__imp_CoTaskMemAlloc
0x18024e20f  nop     dword ptr [rax+rax+00h]
0x18024e214  mov     rdi, rax
0x18024e217  test    rax, rax
0x18024e21a  jnz     short loc_18024E226
0x18024e21c  mov     ebx, 8007000Eh
0x18024e221  jmp     loc_18024E319
0x18024e226  xor     eax, eax
0x18024e228  movzx   r15d, r14w
0x18024e22c  mov     [rdi], rax
0x18024e22f  lea     eax, [rbp+4]
0x18024e232  shl     eax, 4
0x18024e235  mov     ecx, eax; cb
0x18024e237  mov     ebx, eax
0x18024e239  call    cs:__imp_CoTaskMemAlloc
0x18024e240  nop     dword ptr [rax+rax+00h]
0x18024e245  mov     [rdi], rax
0x18024e248  test    rax, rax
0x18024e24b  jnz     short loc_18024E257
0x18024e24d  mov     ebx, 8007000Eh
0x18024e252  jmp     loc_18024E2E2
0x18024e257  mov     r8, rbx; Size
0x18024e25a  xor     edx, edx; Val
0x18024e25c  mov     rcx, rax; void *
0x18024e25f  call    memset_0
0x18024e264  mov     rax, [rsp+58h+var_38]
0x18024e269  mov     rcx, [rdi]
0x18024e26c  mov     [rcx+8], rax
0x18024e270  mov     rcx, [rdi]
0x18024e273  mov     eax, [rsi+20h]
0x18024e276  mov     [rcx+10h], eax
0x18024e279  mov     rcx, rsi; this
0x18024e27c  mov     rax, [rdi]
0x18024e27f  mov     dword ptr [rax+14h], 590h
0x18024e286  mov     rax, [rdi]
0x18024e289  mov     [rax+28h], r14w
0x18024e28e  mov     rax, [rdi]
0x18024e291  mov     dword ptr [rax+30h], 0Ah
0x18024e298  lea     r8, [rax+38h]
0x18024e29c  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x18024e2a1  test    al, al
0x18024e2a3  jnz     short loc_18024E2AE
0x18024e2a5  mov     dword ptr [r8], 0
0x18024e2ac  jmp     short loc_18024E2BC
0x18024e2ae  mov     rcx, [rsp+58h+arg_0]; this
0x18024e2b3  lea     rdx, [rsi+30h]; struct ActiveScriptProfilerHeapEnum *
0x18024e2b7  call    ?PopulateProfilerEventInfo@Projection@@YAXPEAVActiveScriptProfilerHeapEnum@@PEAVEventProjectionHandler@1@PEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST@@@Z; Projection::PopulateProfilerEventInfo(ActiveScriptProfilerHeapEnum *,Projection::EventProjectionHandler *,_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST *)
0x18024e2bc  mov     ebp, 48h ; 'H'
0x18024e2c1  mov     rcx, rbp; cb
0x18024e2c4  call    cs:__imp_CoTaskMemAlloc
0x18024e2cb  nop     dword ptr [rax+rax+00h]
0x18024e2d0  mov     rbx, rax
0x18024e2d3  test    rax, rax
0x18024e2d6  jnz     short loc_18024E324
0x18024e2d8  mov     ebx, 8007000Eh
0x18024e2dd  test    rdi, rdi
0x18024e2e0  jz      short loc_18024E319
0x18024e2e2  movzx   ebp, r15w
0x18024e2e6  xor     esi, esi
0x18024e2e8  mov     r14, rdi
0x18024e2eb  test    ebp, ebp
0x18024e2ed  jz      short loc_18024E30A
0x18024e2ef  mov     rcx, [r14+rsi*8]; pv
0x18024e2f3  test    rcx, rcx
0x18024e2f6  jz      short loc_18024E304
0x18024e2f8  call    cs:__imp_CoTaskMemFree
0x18024e2ff  nop     dword ptr [rax+rax+00h]
0x18024e304  inc     esi
0x18024e306  cmp     esi, ebp
0x18024e308  jb      short loc_18024E2EF
0x18024e30a  mov     rcx, rdi; pv
0x18024e30d  call    cs:__imp_CoTaskMemFree
0x18024e314  nop     dword ptr [rax+rax+00h]
0x18024e319  mov     edx, ebx; int
0x18024e31b  mov     rcx, r12; struct Js::ScriptContext *
0x18024e31e  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x18024e324  mov     r8, rbp; Size
0x18024e327  xor     edx, edx; Val
0x18024e329  mov     rcx, rbx; void *
0x18024e32c  call    memset_0
0x18024e331  mov     eax, [rsi+20h]
0x18024e334  mov     [rbx+10h], eax
0x18024e337  mov     dword ptr [rbx+14h], 400h
0x18024e33e  cmp     [rsp+58h+var_38], 0
0x18024e344  jz      short loc_18024E37B
0x18024e346  mov     rcx, [rsp+58h+arg_0]; this
0x18024e34b  lea     rdx, [rbx+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x18024e34f  mov     [rbx+28h], r14w
0x18024e354  mov     r8d, 4; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x18024e35a  mov     r9, [rsp+58h+var_38]
0x18024e35f  mov     [rbx+30h], r8d
0x18024e363  mov     dword ptr [rdx], 0FFFFFFFFh
0x18024e369  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x18024e36e  mov     [rbx+40h], r9
0x18024e372  mov     [rbx+1Ah], r15w
0x18024e377  mov     [rbx+20h], rdi
0x18024e37b  mov     rbp, [rsp+58h+arg_18]
0x18024e380  mov     rax, rbx
0x18024e383  mov     rbx, [rsp+58h+arg_10]
0x18024e388  add     rsp, 30h
0x18024e38c  pop     r15
0x18024e38e  pop     r14
0x18024e390  pop     r12
0x18024e392  pop     rdi
0x18024e393  pop     rsi
0x18024e394  retn
```
