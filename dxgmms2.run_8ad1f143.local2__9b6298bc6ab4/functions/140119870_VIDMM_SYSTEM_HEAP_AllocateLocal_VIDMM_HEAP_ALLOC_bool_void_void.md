# VIDMM_SYSTEM_HEAP::AllocateLocal(VIDMM_HEAP_ALLOC *,bool,void * *,void * *)

- ea: `0x140119870`
- end: `0x140119a5c`
- name: `?AllocateLocal@VIDMM_SYSTEM_HEAP@@UEAAJPEAUVIDMM_HEAP_ALLOC@@_NPEAPEAX2@Z`
- size: `492`
- prototype: `__int64 __fastcall(VIDMM_SYSTEM_HEAP *__hidden this, struct VIDMM_HEAP_ALLOC *, bool, void **, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400045ec`
- `0x140058760`
- `0x140119870`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x140119a49`
- `ntoskrnl!ObCloseHandle` at `0x140119a49`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14011991e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14011991e`
- `ntoskrnl!ObGetObjectType` at `0x1401198f0`
- `ntoskrnl!ObGetObjectType` at `0x1401198f0`
- `watchdog!WdLogSingleEntry2` at `0x14011993e`
- `watchdog!WdLogSingleEntry2` at `0x1401199cd`
- `watchdog!WdLogSingleEntry2` at `0x14011993e`
- `watchdog!WdLogSingleEntry2` at `0x1401199cd`

## string_xrefs

- `0x140119953`: `Unable to open section object 0x%I64p into handle table, Status = 0x%I64p`

## pseudocode

```c
__int64 __fastcall VIDMM_SYSTEM_HEAP::AllocateLocal(
        VIDMM_SYSTEM_HEAP *this,
        struct VIDMM_HEAP_ALLOC *a2,
        char a3,
        void **a4,
        void **a5)
{
  void **v5; // rbx
  int v10; // eax
  __int64 v11; // rcx
  struct _OBJECT_TYPE *v13; // rax
  NTSTATUS v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rbx
  int v17; // ecx
  int v18; // r8d
  int v19; // ecx
  int v20; // r8d
  int ObjectType; // [rsp+20h] [rbp-58h]
  int AccessMode; // [rsp+28h] [rbp-50h]
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF
  __int64 v24; // [rsp+98h] [rbp+20h] BYREF

  v5 = a5;
  Handle = 0;
  v24 = 0;
  *a4 = 0;
  v10 = *((_DWORD *)a2 + 12);
  if ( (v10 & 8) != 0 )
  {
    v11 = **((_QWORD **)a2 + 3);
    goto LABEL_3;
  }
  if ( (v10 & 4) != 0
    && (v13 = (struct _OBJECT_TYPE *)ObGetObjectType(*(_QWORD *)a2),
        v14 = ObOpenObjectByPointer(*(PVOID *)a2, 0, 0, 0, v13, 1, &Handle),
        v15 = v14,
        v14 < 0) )
  {
    v16 = v14;
    WdLogSingleEntry2(1, *(_QWORD *)a2, v14);
    WdLogGlobalForLineNumber = 1046;
    DxgkLogInternalTriageEvent(
      v17,
      0x40000,
      v18,
      (unsigned int)L"Unable to open section object 0x%I64p into handle table, Status = 0x%I64p",
      *(_QWORD *)a2,
      v16,
      0,
      0);
  }
  else
  {
    v11 = 0;
    if ( !v5
      || (LOBYTE(AccessMode) = a3,
          LOBYTE(ObjectType) = 1,
          (v11 = (*(__int64 (__fastcall **)(VIDMM_SYSTEM_HEAP *, struct VIDMM_HEAP_ALLOC *, _QWORD, _QWORD, int, int, __int64 *))(*(_QWORD *)this + 56LL))(
                   this,
                   a2,
                   0,
                   0,
                   ObjectType,
                   AccessMode,
                   &v24)) != 0) )
    {
LABEL_3:
      *a4 = Handle;
      if ( v5 )
        *v5 = (void *)v11;
      return 0;
    }
    v15 = -1073741801;
    WdLogSingleEntry2(1, *(_QWORD *)a2, -1073741801);
    WdLogGlobalForLineNumber = 1067;
    DxgkLogInternalTriageEvent(
      v19,
      0x40000,
      v20,
      (unsigned int)L"Unable to map initial view for section, Status = 0x%I64p",
      *(_QWORD *)a2,
      -1073741801,
      0,
      0);
  }
  if ( v24 )
    (*(void (__fastcall **)(VIDMM_SYSTEM_HEAP *, struct VIDMM_HEAP_ALLOC *))(*(_QWORD *)this + 64LL))(this, a2);
  if ( Handle )
    ObCloseHandle(Handle, ((unsigned __int64)Handle & 0xFFFFFFFF80000000uLL) == 0);
  return v15;
}

```

## disassembly

```asm
0x140119870  mov     rax, rsp
0x140119873  mov     [rax+8], rbx
0x140119877  push    rbp
0x140119878  push    rsi
0x140119879  push    rdi
0x14011987a  push    r14
0x14011987c  push    r15
0x14011987e  sub     rsp, 50h
0x140119882  mov     rbx, [rsp+78h+arg_20]
0x14011988a  mov     r15, r9
0x14011988d  mov     qword ptr [rax+10h], 0
0x140119895  mov     bpl, r8b
0x140119898  mov     qword ptr [rax+20h], 0
0x1401198a0  mov     rdi, rdx
0x1401198a3  mov     qword ptr [r9], 0
0x1401198aa  mov     r14, rcx
0x1401198ad  mov     eax, [rdx+30h]
0x1401198b0  test    al, 8
0x1401198b2  jz      short loc_1401198E5
0x1401198b4  mov     rax, [rdx+18h]
0x1401198b8  mov     rcx, [rax]
0x1401198bb  mov     rax, [rsp+78h+arg_8]
0x1401198c3  mov     [r15], rax
0x1401198c6  test    rbx, rbx
0x1401198c9  jz      short loc_1401198CE
0x1401198cb  mov     [rbx], rcx
0x1401198ce  xor     eax, eax
0x1401198d0  mov     rbx, [rsp+78h+arg_0]
0x1401198d8  add     rsp, 50h
0x1401198dc  pop     r15
0x1401198de  pop     r14
0x1401198e0  pop     rdi
0x1401198e1  pop     rsi
0x1401198e2  pop     rbp
0x1401198e3  retn
0x1401198e5  test    al, 4
0x1401198e7  jz      loc_140119977
0x1401198ed  mov     rcx, [rdx]
0x1401198f0  call    cs:__imp_ObGetObjectType
0x1401198f7  nop     dword ptr [rax+rax+00h]
0x1401198fc  lea     rcx, [rsp+78h+arg_8]
0x140119904  xor     r9d, r9d; DesiredAccess
0x140119907  mov     [rsp+78h+Handle], rcx; Handle
0x14011990c  xor     r8d, r8d; PassedAccessState
0x14011990f  mov     rcx, [rdi]; Object
0x140119912  xor     edx, edx; HandleAttributes
0x140119914  mov     [rsp+78h+AccessMode], 1; AccessMode
0x140119919  mov     [rsp+78h+ObjectType], rax; ObjectType
0x14011991e  call    cs:__imp_ObOpenObjectByPointer
0x140119925  nop     dword ptr [rax+rax+00h]
0x14011992a  mov     esi, eax
0x14011992c  test    eax, eax
0x14011992e  jns     short loc_140119977
0x140119930  mov     rdx, [rdi]
0x140119933  mov     ecx, 1
0x140119938  movsxd  rbx, eax
0x14011993b  mov     r8, rbx
0x14011993e  call    cs:__imp_WdLogSingleEntry2
0x140119945  nop     dword ptr [rax+rax+00h]
0x14011994a  mov     [rsp+78h+var_40], 0
0x140119953  lea     r9, aUnableToOpenSe; "Unable to open section object 0x%I64p i"...
0x14011995a  mov     [rsp+78h+Handle], 0
0x140119963  mov     qword ptr [rsp+78h+AccessMode], rbx
0x140119968  mov     cs:WdLogGlobalForLineNumber, 416h
0x140119972  jmp     loc_140119A01
0x140119977  xor     ecx, ecx
0x140119979  test    rbx, rbx
0x14011997c  jz      loc_1401198BB
0x140119982  mov     rax, [r14]
0x140119985  lea     rcx, [rsp+78h+arg_18]
0x14011998d  mov     [rsp+78h+Handle], rcx
0x140119992  xor     r9d, r9d
0x140119995  mov     [rsp+78h+AccessMode], bpl
0x14011999a  xor     r8d, r8d
0x14011999d  mov     rdx, rdi
0x1401199a0  mov     byte ptr [rsp+78h+ObjectType], 1
0x1401199a5  mov     rax, [rax+38h]
0x1401199a9  mov     rcx, r14
0x1401199ac  call    _guard_dispatch_icall
0x1401199b1  mov     rcx, rax
0x1401199b4  test    rax, rax
0x1401199b7  jnz     loc_1401198BB
0x1401199bd  mov     rsi, 0FFFFFFFFC0000017h
0x1401199c4  mov     rdx, [rdi]
0x1401199c7  lea     ecx, [rax+1]
0x1401199ca  mov     r8, rsi
0x1401199cd  call    cs:__imp_WdLogSingleEntry2
0x1401199d4  nop     dword ptr [rax+rax+00h]
0x1401199d9  mov     [rsp+78h+var_40], 0
0x1401199e2  lea     r9, aUnableToMapIni_0; "Unable to map initial view for section,"...
0x1401199e9  mov     [rsp+78h+Handle], 0
0x1401199f2  mov     qword ptr [rsp+78h+AccessMode], rsi
0x1401199f7  mov     cs:WdLogGlobalForLineNumber, 42Bh
0x140119a01  mov     rax, [rdi]
0x140119a04  mov     edx, 40000h
0x140119a09  mov     [rsp+78h+ObjectType], rax
0x140119a0e  call    DxgkLogInternalTriageEvent
0x140119a13  mov     r8, [rsp+78h+arg_18]
0x140119a1b  test    r8, r8
0x140119a1e  jz      short loc_140119A32
0x140119a20  mov     rax, [r14]
0x140119a23  mov     rdx, rdi
0x140119a26  mov     rcx, r14
0x140119a29  mov     rax, [rax+40h]
0x140119a2d  call    _guard_dispatch_icall
0x140119a32  mov     rcx, [rsp+78h+arg_8]; Handle
0x140119a3a  test    rcx, rcx
0x140119a3d  jz      short loc_140119A55
0x140119a3f  test    rcx, 0FFFFFFFF80000000h
0x140119a46  setz    dl; PreviousMode
0x140119a49  call    cs:__imp_ObCloseHandle
0x140119a50  nop     dword ptr [rax+rax+00h]
0x140119a55  mov     eax, esi
0x140119a57  jmp     loc_1401198D0
```
