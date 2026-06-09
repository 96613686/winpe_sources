# Projection::CreateWinrtConstructorObjectElement(ActiveScriptProfilerHeapEnum *,Js::RecyclableObject *)

- ea: `0x18047287c`
- end: `0x180472aa6`
- name: `?CreateWinrtConstructorObjectElement@Projection@@YAPEAUHostProfilerHeapObject@@PEAVActiveScriptProfilerHeapEnum@@PEAVRecyclableObject@Js@@@Z`
- size: `554`
- prototype: `struct HostProfilerHeapObject *__fastcall(Projection *__hidden this, struct ActiveScriptProfilerHeapEnum *, struct Js::RecyclableObject *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180432f98`

## callees

- `0x1802401b0`
- `0x180384370`
- `0x1803fbd3c`
- `0x18047287c`
- `0x180482084`
- `0x180482104`
- `0x180482290`
- `0x1805a9c5a`
- `0x1805cd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180472a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180472a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180472a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180472a1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180472918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180472949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804729d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180472918`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180472949`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1804729d4`

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
  v5 = *(struct Js::ScriptContext **)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 8LL) + 1088LL);
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
0x18047287c  mov     rax, rsp
0x18047287f  mov     [rax+18h], rbx
0x180472883  mov     [rax+20h], rbp
0x180472887  mov     [rax+10h], rdx
0x18047288b  mov     [rax+8], rcx
0x18047288f  push    rsi
0x180472890  push    rdi
0x180472891  push    r12
0x180472893  push    r14
0x180472895  push    r15
0x180472897  sub     rsp, 30h
0x18047289b  mov     rax, [rdx+8]
0x18047289f  xor     edi, edi
0x1804728a1  xor     r15d, r15d
0x1804728a4  mov     rcx, [rax+8]
0x1804728a8  mov     rax, [rdx+40h]
0x1804728ac  mov     r12, [rcx+440h]
0x1804728b3  mov     rsi, [rax+18h]
0x1804728b7  mov     rcx, rsi; this
0x1804728ba  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x1804728bf  test    al, al
0x1804728c1  jnz     short loc_1804728C7
0x1804728c3  xor     ebp, ebp
0x1804728c5  jmp     short loc_1804728D2
0x1804728c7  lea     rcx, [rsi+30h]; this
0x1804728cb  call    ?GetEventAndEventHandlerCount@Projection@@YAIPEAVEventProjectionHandler@1@@Z; Projection::GetEventAndEventHandlerCount(Projection::EventProjectionHandler *)
0x1804728d0  mov     ebp, eax
0x1804728d2  mov     [rsp+58h+var_38], rdi
0x1804728d7  mov     r14d, 1
0x1804728dd  mov     rcx, [rsi+28h]
0x1804728e1  test    rcx, rcx
0x1804728e4  jnz     short loc_1804728EE
0x1804728e6  lea     ebp, [rcx+30h]
0x1804728e9  jmp     loc_1804729D1
0x1804728ee  lea     rdx, [rsp+58h+var_38]
0x1804728f3  call    ??$QueryInterface@UIUnknown@@@IUnknown@@QEAAJPEAPEAU0@@Z; IUnknown::QueryInterface<IUnknown>(IUnknown * *)
0x1804728f8  mov     ebx, eax
0x1804728fa  test    eax, eax
0x1804728fc  js      loc_1804729ED
0x180472902  mov     rcx, [rsp+58h+var_38]
0x180472907  mov     rax, [rcx]
0x18047290a  mov     rax, [rax+10h]
0x18047290e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180472913  mov     ecx, 8; cb
0x180472918  call    cs:__imp_CoTaskMemAlloc
0x18047291f  nop     dword ptr [rax+rax+00h]
0x180472924  mov     rdi, rax
0x180472927  test    rax, rax
0x18047292a  jnz     short loc_180472936
0x18047292c  mov     ebx, 8007000Eh
0x180472931  jmp     loc_180472A29
0x180472936  xor     eax, eax
0x180472938  movzx   r15d, r14w
0x18047293c  mov     [rdi], rax
0x18047293f  lea     eax, [rbp+4]
0x180472942  shl     eax, 4
0x180472945  mov     ecx, eax; cb
0x180472947  mov     ebx, eax
0x180472949  call    cs:__imp_CoTaskMemAlloc
0x180472950  nop     dword ptr [rax+rax+00h]
0x180472955  mov     [rdi], rax
0x180472958  test    rax, rax
0x18047295b  jnz     short loc_180472967
0x18047295d  mov     ebx, 8007000Eh
0x180472962  jmp     loc_1804729F2
0x180472967  mov     r8, rbx; Size
0x18047296a  xor     edx, edx; Val
0x18047296c  mov     rcx, rax; void *
0x18047296f  call    memset_0
0x180472974  mov     rax, [rsp+58h+var_38]
0x180472979  mov     rcx, [rdi]
0x18047297c  mov     [rcx+8], rax
0x180472980  mov     rcx, [rdi]
0x180472983  mov     eax, [rsi+20h]
0x180472986  mov     [rcx+10h], eax
0x180472989  mov     rcx, rsi; this
0x18047298c  mov     rax, [rdi]
0x18047298f  mov     dword ptr [rax+14h], 590h
0x180472996  mov     rax, [rdi]
0x180472999  mov     [rax+28h], r14w
0x18047299e  mov     rax, [rdi]
0x1804729a1  mov     dword ptr [rax+30h], 0Ah
0x1804729a8  lea     r8, [rax+38h]
0x1804729ac  call    ?CanHoldEventCookies@ThisInfo@Projection@@QEAA_NXZ; Projection::ThisInfo::CanHoldEventCookies(void)
0x1804729b1  test    al, al
0x1804729b3  jnz     short loc_1804729BE
0x1804729b5  mov     dword ptr [r8], 0
0x1804729bc  jmp     short loc_1804729CC
0x1804729be  mov     rcx, [rsp+58h+arg_0]; this
0x1804729c3  lea     rdx, [rsi+30h]; struct ActiveScriptProfilerHeapEnum *
0x1804729c7  call    ?PopulateProfilerEventInfo@Projection@@YAXPEAVActiveScriptProfilerHeapEnum@@PEAVEventProjectionHandler@1@PEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST@@@Z; Projection::PopulateProfilerEventInfo(ActiveScriptProfilerHeapEnum *,Projection::EventProjectionHandler *,_PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST *)
0x1804729cc  mov     ebp, 48h ; 'H'
0x1804729d1  mov     rcx, rbp; cb
0x1804729d4  call    cs:__imp_CoTaskMemAlloc
0x1804729db  nop     dword ptr [rax+rax+00h]
0x1804729e0  mov     rbx, rax
0x1804729e3  test    rax, rax
0x1804729e6  jnz     short loc_180472A34
0x1804729e8  mov     ebx, 8007000Eh
0x1804729ed  test    rdi, rdi
0x1804729f0  jz      short loc_180472A29
0x1804729f2  movzx   ebp, r15w
0x1804729f6  xor     esi, esi
0x1804729f8  mov     r14, rdi
0x1804729fb  test    ebp, ebp
0x1804729fd  jz      short loc_180472A1A
0x1804729ff  mov     rcx, [r14+rsi*8]; pv
0x180472a03  test    rcx, rcx
0x180472a06  jz      short loc_180472A14
0x180472a08  call    cs:__imp_CoTaskMemFree
0x180472a0f  nop     dword ptr [rax+rax+00h]
0x180472a14  inc     esi
0x180472a16  cmp     esi, ebp
0x180472a18  jb      short loc_1804729FF
0x180472a1a  mov     rcx, rdi; pv
0x180472a1d  call    cs:__imp_CoTaskMemFree
0x180472a24  nop     dword ptr [rax+rax+00h]
0x180472a29  mov     edx, ebx; int
0x180472a2b  mov     rcx, r12; struct Js::ScriptContext *
0x180472a2e  call    ?MapAndThrowError@JavascriptError@Js@@SAXPEAVScriptContext@2@J@Z; Js::JavascriptError::MapAndThrowError(Js::ScriptContext *,long)
0x180472a34  mov     r8, rbp; Size
0x180472a37  xor     edx, edx; Val
0x180472a39  mov     rcx, rbx; void *
0x180472a3c  call    memset_0
0x180472a41  mov     eax, [rsi+20h]
0x180472a44  mov     [rbx+10h], eax
0x180472a47  mov     dword ptr [rbx+14h], 400h
0x180472a4e  cmp     [rsp+58h+var_38], 0
0x180472a54  jz      short loc_180472A8B
0x180472a56  mov     rcx, [rsp+58h+arg_0]; this
0x180472a5b  lea     rdx, [rbx+38h]; struct _PROFILER_HEAP_OBJECT_RELATIONSHIP *
0x180472a5f  mov     [rbx+28h], r14w
0x180472a64  mov     r8d, 4; enum __MIDL___MIDL_itf_activprof_0000_0002_0005
0x180472a6a  mov     r9, [rsp+58h+var_38]
0x180472a6f  mov     [rbx+30h], r8d
0x180472a73  mov     dword ptr [rdx], 0FFFFFFFFh
0x180472a79  call    ?SetRelationshipInfo@ActiveScriptProfilerHeapEnum@@QEAAXAEAU_PROFILER_HEAP_OBJECT_RELATIONSHIP@@W4__MIDL___MIDL_itf_activprof_0000_0002_0005@@@Z; ActiveScriptProfilerHeapEnum::SetRelationshipInfo(_PROFILER_HEAP_OBJECT_RELATIONSHIP &,__MIDL___MIDL_itf_activprof_0000_0002_0005)
0x180472a7e  mov     [rbx+40h], r9
0x180472a82  mov     [rbx+1Ah], r15w
0x180472a87  mov     [rbx+20h], rdi
0x180472a8b  mov     rbp, [rsp+58h+arg_18]
0x180472a90  mov     rax, rbx
0x180472a93  mov     rbx, [rsp+58h+arg_10]
0x180472a98  add     rsp, 30h
0x180472a9c  pop     r15
0x180472a9e  pop     r14
0x180472aa0  pop     r12
0x180472aa2  pop     rdi
0x180472aa3  pop     rsi
0x180472aa4  retn
```
