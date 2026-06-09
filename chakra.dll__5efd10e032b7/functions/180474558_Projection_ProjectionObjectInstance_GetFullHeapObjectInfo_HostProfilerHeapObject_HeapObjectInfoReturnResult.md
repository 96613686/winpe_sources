# Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(HostProfilerHeapObject * *,HeapObjectInfoReturnResult *)

- ea: `0x180474558`
- end: `0x180474746`
- name: `?GetFullHeapObjectInfo@ProjectionObjectInstance@Projection@@QEAAJPEAPEAUHostProfilerHeapObject@@PEAW4HeapObjectInfoReturnResult@@@Z`
- size: `494`
- prototype: `__int64 __fastcall(Projection::ProjectionObjectInstance *__hidden this, struct HostProfilerHeapObject **, enum HeapObjectInfoReturnResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180481f40`

## callees

- `0x18008af9c`
- `0x180333b0c`
- `0x1803fbd3c`
- `0x180471050`
- `0x180474558`
- `0x1805a9c5a`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804745ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804745fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804745ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1804745fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180474578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18047459c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804745d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180474578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18047459c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804745d6`

## pseudocode

```c
__int64 __fastcall Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(
        Projection::ProjectionObjectInstance *this,
        struct HostProfilerHeapObject **a2,
        enum HeapObjectInfoReturnResult *a3)
{
  char *v3; // rax
  char *v4; // rsi
  __int64 *v5; // rax
  __int64 *v6; // rdi
  SIZE_T v7; // rbx
  void *v8; // rax
  ActiveScriptProfilerHeapEnum *v10; // rbp
  __int64 v11; // r9
  __int16 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rax
  Projection::ProjectionWriter *ProjectionWriter; // rax
  _DWORD *v16; // rbx
  int v17; // edx
  int v18; // ecx
  int v19; // ecx
  __int64 v20; // r8
  struct Projection::RuntimeClassTypeInformation *v21; // [rsp+20h] [rbp-38h] BYREF
  void *v22; // [rsp+28h] [rbp-30h] BYREF

  v3 = (char *)CoTaskMemAlloc(0x48u);
  v4 = v3;
  if ( !v3 )
    goto LABEL_6;
  memset_0(v3, 0, 0x48u);
  v5 = (__int64 *)CoTaskMemAlloc(8u);
  v6 = v5;
  if ( !v5 )
  {
LABEL_5:
    CoTaskMemFree(v4);
LABEL_6:
    *(_DWORD *)a3 = 1;
    return 2147942414LL;
  }
  *v5 = 0;
  v7 = 16
     * ((*(unsigned int (__fastcall **)(Projection::ProjectionObjectInstance *))(*(_QWORD *)this + 792LL))(this) + 4);
  v8 = CoTaskMemAlloc(v7);
  *v6 = (__int64)v8;
  if ( !v8 )
  {
    CoTaskMemFree(v6);
    goto LABEL_5;
  }
  memset_0(v8, 0, v7);
  *((_DWORD *)v4 + 5) = 512;
  *((_WORD *)v4 + 20) = 1;
  v10 = *(ActiveScriptProfilerHeapEnum **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 1088LL)
                                                     + 880LL)
                                         + 216LL);
  *((_DWORD *)v4 + 12) = 4;
  *((_DWORD *)v4 + 14) = -1;
  ActiveScriptProfilerHeapEnum::SetRelationshipInfo(
    v10,
    (struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *)(v4 + 56),
    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT);
  *((_QWORD *)v4 + 8) = v11;
  *((_WORD *)v4 + 13) = v12;
  *((_QWORD *)v4 + 4) = v6;
  v13 = *v6;
  v14 = *((_QWORD *)this + 7);
  v21 = 0;
  *(_QWORD *)(v13 + 8) = v14;
  *(_DWORD *)(*v6 + 16) = *(_DWORD *)(*((_QWORD *)this + 1) + 56LL);
  *(_DWORD *)(*v6 + 20) = 784;
  *(_WORD *)(*v6 + 40) = v12;
  ProjectionWriter = Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 12));
  v16 = (_DWORD *)*v6;
  Projection::ProjectionWriter::GetRuntimeClassTypeInformation(ProjectionWriter, *(_DWORD *)(*v6 + 16), &v22, &v21);
  *v16 = Projection::GetApproximateSizeForGCPressure((Projection *)*((unsigned int *)v21 + 11), v17);
  v18 = *(_DWORD *)(*v6 + 20);
  if ( *(_DWORD *)*v6 )
    v19 = v18 | 0x40;
  else
    v19 = v18 | 0x80;
  *(_DWORD *)(*v6 + 20) = v19;
  v20 = *v6;
  *(_DWORD *)(v20 + 48) = 10;
  (*(void (__fastcall **)(Projection::ProjectionObjectInstance *, ActiveScriptProfilerHeapEnum *, __int64))(*(_QWORD *)this + 800LL))(
    this,
    v10,
    v20 + 56);
  *a2 = (struct HostProfilerHeapObject *)v4;
  *(_DWORD *)a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180474558  mov     [rsp+arg_10], r8
0x18047455d  mov     [rsp+arg_8], rdx
0x180474562  mov     [rsp+arg_0], rcx
0x180474567  push    rbx
0x180474568  push    rbp
0x180474569  push    rsi
0x18047456a  push    rdi
0x18047456b  push    r14
0x18047456d  sub     rsp, 30h
0x180474571  mov     ebx, 48h ; 'H'
0x180474576  mov     ecx, ebx; cb
0x180474578  call    cs:__imp_CoTaskMemAlloc
0x18047457f  nop     dword ptr [rax+rax+00h]
0x180474584  mov     rsi, rax
0x180474587  test    rax, rax
0x18047458a  jz      short loc_180474608
0x18047458c  mov     r8d, ebx; Size
0x18047458f  xor     edx, edx; Val
0x180474591  mov     rcx, rax; void *
0x180474594  call    memset_0
0x180474599  lea     ecx, [rbx-40h]; cb
0x18047459c  call    cs:__imp_CoTaskMemAlloc
0x1804745a3  nop     dword ptr [rax+rax+00h]
0x1804745a8  mov     rdi, rax
0x1804745ab  test    rax, rax
0x1804745ae  jz      short loc_1804745F9
0x1804745b0  mov     r14, [rsp+58h+arg_0]
0x1804745b5  xor     eax, eax
0x1804745b7  mov     [rdi], rax
0x1804745ba  mov     rcx, [r14]
0x1804745bd  mov     rax, [rcx+318h]
0x1804745c4  mov     rcx, r14
0x1804745c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804745cc  add     eax, 4
0x1804745cf  shl     eax, 4
0x1804745d2  mov     ecx, eax; cb
0x1804745d4  mov     ebx, eax
0x1804745d6  call    cs:__imp_CoTaskMemAlloc
0x1804745dd  nop     dword ptr [rax+rax+00h]
0x1804745e2  mov     [rdi], rax
0x1804745e5  test    rax, rax
0x1804745e8  jnz     short loc_180474624
0x1804745ea  mov     rcx, rdi; pv
0x1804745ed  call    cs:__imp_CoTaskMemFree
0x1804745f4  nop     dword ptr [rax+rax+00h]
0x1804745f9  mov     rcx, rsi; pv
0x1804745fc  call    cs:__imp_CoTaskMemFree
0x180474603  nop     dword ptr [rax+rax+00h]
0x180474608  mov     rax, [rsp+58h+arg_10]
0x18047460d  mov     dword ptr [rax], 1
0x180474613  mov     eax, 8007000Eh
0x180474618  add     rsp, 30h
0x18047461c  pop     r14
0x18047461e  pop     rdi
0x18047461f  pop     rsi
0x180474620  pop     rbp
0x180474621  pop     rbx
0x180474622  retn
0x180474624  mov     r8, rbx; Size
0x180474627  xor     edx, edx; Val
0x180474629  mov     rcx, rax; void *
0x18047462c  call    memset_0
0x180474631  mov     dword ptr [rsi+14h], 200h
0x180474638  lea     rdx, [rsi+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x18047463c  mov     r10d, 1
0x180474642  mov     [rsi+28h], r10w
0x180474647  mov     rax, [r14+8]
0x18047464b  mov     r9, [r14+38h]
0x18047464f  lea     r8d, [r10+3]; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x180474653  mov     rcx, [rax+8]
0x180474657  mov     rax, [rcx+440h]
0x18047465e  mov     rcx, [rax+370h]
0x180474665  mov     rbp, [rcx+0D8h]
0x18047466c  mov     rcx, rbp; this
0x18047466f  mov     dword ptr [rsi+30h], 4
0x180474676  mov     dword ptr [rdx], 0FFFFFFFFh
0x18047467c  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x180474681  mov     [rsi+40h], r9
0x180474685  mov     [rsi+1Ah], r10w
0x18047468a  mov     [rsi+20h], rdi
0x18047468e  mov     rcx, [rdi]
0x180474691  mov     rax, [r14+38h]
0x180474695  mov     [rsp+58h+var_38], 0
0x18047469e  mov     [rcx+8], rax
0x1804746a2  mov     rax, [r14+8]
0x1804746a6  mov     rcx, [rdi]
0x1804746a9  mov     eax, [rax+38h]
0x1804746ac  mov     [rcx+10h], eax
0x1804746af  mov     rax, [rdi]
0x1804746b2  mov     dword ptr [rax+14h], 310h
0x1804746b9  mov     rax, [rdi]
0x1804746bc  mov     [rax+28h], r10w
0x1804746c1  mov     rcx, [r14+60h]; this
0x1804746c5  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x1804746ca  mov     rbx, [rdi]
0x1804746cd  lea     r9, [rsp+58h+var_38]; struct Projection::RuntimeClassTypeInformation **
0x1804746d2  lea     r8, [rsp+58h+var_30]; void **
0x1804746d7  mov     rcx, rax; this
0x1804746da  mov     edx, [rbx+10h]; int
0x1804746dd  call    ?GetRuntimeClassTypeInformation@ProjectionWriter@Projection@@QEAA_NHPEAPEAXPEAPEAVRuntimeClassTypeInformation@2@@Z; Projection::ProjectionWriter::GetRuntimeClassTypeInformation(int,void * *,Projection::RuntimeClassTypeInformation * *)
0x1804746e2  mov     rcx, [rsp+58h+var_38]
0x1804746e7  mov     ecx, [rcx+2Ch]; this
0x1804746ea  call    ?GetApproximateSizeForGCPressure@Projection@@YA_KH@Z; Projection::GetApproximateSizeForGCPressure(int)
0x1804746ef  mov     [rbx], eax
0x1804746f1  mov     rax, [rdi]
0x1804746f4  cmp     dword ptr [rax], 0
0x1804746f7  mov     ecx, [rax+14h]
0x1804746fa  jnz     short loc_180474702
0x1804746fc  bts     ecx, 7
0x180474700  jmp     short loc_180474705
0x180474702  or      ecx, 40h
0x180474705  mov     [rax+14h], ecx
0x180474708  mov     rdx, rbp
0x18047470b  mov     r8, [rdi]
0x18047470e  mov     rcx, r14
0x180474711  mov     dword ptr [r8+30h], 0Ah
0x180474719  add     r8, 38h ; '8'
0x18047471d  mov     rax, [r14]
0x180474720  mov     rax, [rax+320h]
0x180474727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18047472c  mov     rax, [rsp+58h+arg_8]
0x180474731  mov     [rax], rsi
0x180474734  mov     rax, [rsp+58h+arg_10]
0x180474739  mov     dword ptr [rax], 0
0x18047473f  xor     eax, eax
0x180474741  jmp     loc_180474618
```
