# Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(HostProfilerHeapObject * *,HeapObjectInfoReturnResult *)

- ea: `0x180255c74`
- end: `0x180255e65`
- name: `?GetFullHeapObjectInfo@ProjectionObjectInstance@Projection@@QEAAJPEAPEAUHostProfilerHeapObject@@PEAW4HeapObjectInfoReturnResult@@@Z`
- size: `497`
- prototype: `__int64 __fastcall(Projection::ProjectionObjectInstance *__hidden this, struct HostProfilerHeapObject **, enum HeapObjectInfoReturnResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180233490`

## callees

- `0x1801bced8`
- `0x1801c3250`
- `0x1801cc26b`
- `0x180247840`
- `0x18024f464`
- `0x180255c74`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255c95`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255cb9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255cf3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255c95`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255cb9`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180255cf3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180255d0a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180255d19`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180255d0a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180255d19`

## pseudocode

```c
__int64 __fastcall Projection::ProjectionObjectInstance::GetFullHeapObjectInfo(
        Projection::ProjectionObjectInstance *this,
        struct HostProfilerHeapObject **a2,
        enum HeapObjectInfoReturnResult *a3)
{
  char *v3; // rax
  char *v4; // rdi
  __int64 *v5; // rax
  __int64 *v6; // rbx
  SIZE_T v7; // rbp
  void *v8; // rax
  ActiveScriptProfilerHeapEnum *v10; // rbp
  __int64 v11; // r9
  __int16 v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rax
  Projection::ProjectionWriter *ProjectionWriter; // rax
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // r8
  struct Projection::RuntimeClassTypeInformation *v19; // [rsp+20h] [rbp-28h] BYREF
  void *v20; // [rsp+28h] [rbp-20h] BYREF

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
     * ((*(unsigned int (__fastcall **)(Projection::ProjectionObjectInstance *))(*(_QWORD *)this + 776LL))(this) + 4);
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
  v10 = *(ActiveScriptProfilerHeapEnum **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL) + 1072LL)
                                                     + 1184LL)
                                         + 24LL);
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
  v19 = 0;
  *(_QWORD *)(v13 + 8) = v14;
  *(_DWORD *)(*v6 + 16) = *(_DWORD *)(*((_QWORD *)this + 1) + 64LL);
  *(_DWORD *)(*v6 + 20) = 784;
  *(_WORD *)(*v6 + 40) = v12;
  ProjectionWriter = Projection::ProjectionContext::GetProjectionWriter(*((Projection::ProjectionContext **)this + 12));
  Projection::ProjectionWriter::GetRuntimeClassTypeInformation(ProjectionWriter, *(_DWORD *)(*v6 + 16), &v20, &v19);
  *(_DWORD *)*v6 = Projection::GetApproximateSizeForGCPressure((Projection *)*((unsigned int *)v19 + 11));
  v16 = *(_DWORD *)(*v6 + 20);
  if ( *(_DWORD *)*v6 )
    v17 = v16 | 0x40;
  else
    v17 = v16 | 0x80;
  *(_DWORD *)(*v6 + 20) = v17;
  v18 = *v6;
  *(_DWORD *)(v18 + 48) = 10;
  (*(void (__fastcall **)(Projection::ProjectionObjectInstance *, ActiveScriptProfilerHeapEnum *, __int64))(*(_QWORD *)this + 784LL))(
    this,
    v10,
    v18 + 56);
  *a2 = (struct HostProfilerHeapObject *)v4;
  *(_DWORD *)a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180255c74  mov     rax, rsp
0x180255c77  mov     [rax+20h], rbx
0x180255c7b  mov     [rax+18h], r8
0x180255c7f  mov     [rax+10h], rdx
0x180255c83  mov     [rax+8], rcx
0x180255c87  push    rbp
0x180255c88  push    rsi
0x180255c89  push    rdi
0x180255c8a  sub     rsp, 30h
0x180255c8e  mov     ebx, 48h ; 'H'
0x180255c93  mov     ecx, ebx; cb
0x180255c95  call    cs:__imp_CoTaskMemAlloc
0x180255c9c  nop     dword ptr [rax+rax+00h]
0x180255ca1  mov     rdi, rax
0x180255ca4  test    rax, rax
0x180255ca7  jz      short loc_180255D25
0x180255ca9  mov     r8d, ebx; Size
0x180255cac  xor     edx, edx; Val
0x180255cae  mov     rcx, rax; void *
0x180255cb1  call    memset_0
0x180255cb6  lea     ecx, [rbx-40h]; cb
0x180255cb9  call    cs:__imp_CoTaskMemAlloc
0x180255cc0  nop     dword ptr [rax+rax+00h]
0x180255cc5  mov     rbx, rax
0x180255cc8  test    rax, rax
0x180255ccb  jz      short loc_180255D16
0x180255ccd  mov     rsi, [rsp+48h+arg_0]
0x180255cd2  xor     eax, eax
0x180255cd4  mov     [rbx], rax
0x180255cd7  mov     rcx, [rsi]
0x180255cda  mov     rax, [rcx+308h]
0x180255ce1  mov     rcx, rsi
0x180255ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180255ce9  add     eax, 4
0x180255cec  shl     eax, 4
0x180255cef  mov     ecx, eax; cb
0x180255cf1  mov     ebp, eax
0x180255cf3  call    cs:__imp_CoTaskMemAlloc
0x180255cfa  nop     dword ptr [rax+rax+00h]
0x180255cff  mov     [rbx], rax
0x180255d02  test    rax, rax
0x180255d05  jnz     short loc_180255D43
0x180255d07  mov     rcx, rbx; pv
0x180255d0a  call    cs:__imp_CoTaskMemFree
0x180255d11  nop     dword ptr [rax+rax+00h]
0x180255d16  mov     rcx, rdi; pv
0x180255d19  call    cs:__imp_CoTaskMemFree
0x180255d20  nop     dword ptr [rax+rax+00h]
0x180255d25  mov     rax, [rsp+48h+arg_10]
0x180255d2a  mov     dword ptr [rax], 1
0x180255d30  mov     eax, 8007000Eh
0x180255d35  mov     rbx, [rsp+48h+arg_18]
0x180255d3a  add     rsp, 30h
0x180255d3e  pop     rdi
0x180255d3f  pop     rsi
0x180255d40  pop     rbp
0x180255d41  retn
0x180255d43  mov     r8, rbp; Size
0x180255d46  xor     edx, edx; Val
0x180255d48  mov     rcx, rax; void *
0x180255d4b  call    memset_0
0x180255d50  mov     dword ptr [rdi+14h], 200h
0x180255d57  lea     rdx, [rdi+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x180255d5b  mov     r10d, 1
0x180255d61  mov     [rdi+28h], r10w
0x180255d66  mov     rax, [rsi+8]
0x180255d6a  mov     r9, [rsi+38h]
0x180255d6e  lea     r8d, [r10+3]; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x180255d72  mov     rcx, [rax+8]
0x180255d76  mov     rax, [rcx+430h]
0x180255d7d  mov     rcx, [rax+4A0h]
0x180255d84  mov     rbp, [rcx+18h]
0x180255d88  mov     rcx, rbp; this
0x180255d8b  mov     dword ptr [rdi+30h], 4
0x180255d92  mov     dword ptr [rdx], 0FFFFFFFFh
0x180255d98  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x180255d9d  mov     [rdi+40h], r9
0x180255da1  mov     [rdi+1Ah], r10w
0x180255da6  mov     [rdi+20h], rbx
0x180255daa  mov     rcx, [rbx]
0x180255dad  mov     rax, [rsi+38h]
0x180255db1  mov     [rsp+48h+var_28], 0
0x180255dba  mov     [rcx+8], rax
0x180255dbe  mov     rax, [rsi+8]
0x180255dc2  mov     rcx, [rbx]
0x180255dc5  mov     eax, [rax+40h]
0x180255dc8  mov     [rcx+10h], eax
0x180255dcb  mov     rax, [rbx]
0x180255dce  mov     dword ptr [rax+14h], 310h
0x180255dd5  mov     rax, [rbx]
0x180255dd8  mov     [rax+28h], r10w
0x180255ddd  mov     rcx, [rsi+60h]; this
0x180255de1  call    ?GetProjectionWriter@ProjectionContext@Projection@@QEAAPEAVProjectionWriter@2@XZ; Projection::ProjectionContext::GetProjectionWriter(void)
0x180255de6  mov     rdx, [rbx]
0x180255de9  lea     r9, [rsp+48h+var_28]; struct Projection::RuntimeClassTypeInformation **
0x180255dee  lea     r8, [rsp+48h+var_20]; void **
0x180255df3  mov     rcx, rax; this
0x180255df6  mov     edx, [rdx+10h]; int
0x180255df9  call    ?GetRuntimeClassTypeInformation@ProjectionWriter@Projection@@QEAA_NHPEAPEAXPEAPEAVRuntimeClassTypeInformation@2@@Z; Projection::ProjectionWriter::GetRuntimeClassTypeInformation(int,void * *,Projection::RuntimeClassTypeInformation * *)
0x180255dfe  mov     rcx, [rsp+48h+var_28]
0x180255e03  mov     ecx, [rcx+2Ch]; this
0x180255e06  call    ?GetApproximateSizeForGCPressure@Projection@@YA_KH@Z; Projection::GetApproximateSizeForGCPressure(int)
0x180255e0b  mov     rcx, [rbx]
0x180255e0e  mov     [rcx], eax
0x180255e10  mov     rax, [rbx]
0x180255e13  cmp     dword ptr [rax], 0
0x180255e16  mov     ecx, [rax+14h]
0x180255e19  jnz     short loc_180255E21
0x180255e1b  bts     ecx, 7
0x180255e1f  jmp     short loc_180255E24
0x180255e21  or      ecx, 40h
0x180255e24  mov     [rax+14h], ecx
0x180255e27  mov     rdx, rbp
0x180255e2a  mov     r8, [rbx]
0x180255e2d  mov     rcx, rsi
0x180255e30  mov     dword ptr [r8+30h], 0Ah
0x180255e38  add     r8, 38h ; '8'
0x180255e3c  mov     rax, [rsi]
0x180255e3f  mov     rax, [rax+310h]
0x180255e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180255e4b  mov     rax, [rsp+48h+arg_8]
0x180255e50  mov     [rax], rdi
0x180255e53  mov     rax, [rsp+48h+arg_10]
0x180255e58  mov     dword ptr [rax], 0
0x180255e5e  xor     eax, eax
0x180255e60  jmp     loc_180255D35
```
