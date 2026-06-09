# VIDMM_SYSTEM_HEAP::AllocateLocal(VIDMM_HEAP_ALLOC *,bool,void * *,void * *)

- ea: `0x14011d060`
- end: `0x14011d24c`
- name: `?AllocateLocal@VIDMM_SYSTEM_HEAP@@UEAAJPEAUVIDMM_HEAP_ALLOC@@_NPEAPEAX2@Z`
- size: `492`
- prototype: `__int64 __fastcall(VIDMM_SYSTEM_HEAP *__hidden this, struct VIDMM_HEAP_ALLOC *, bool, void **, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140004268`
- `0x140059030`
- `0x14011d060`

## import_xrefs

- `ntoskrnl!ObCloseHandle` at `0x14011d239`
- `ntoskrnl!ObCloseHandle` at `0x14011d239`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14011d10e`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14011d10e`
- `ntoskrnl!ObGetObjectType` at `0x14011d0e0`
- `ntoskrnl!ObGetObjectType` at `0x14011d0e0`
- `watchdog!WdLogSingleEntry2` at `0x14011d12e`
- `watchdog!WdLogSingleEntry2` at `0x14011d1bd`
- `watchdog!WdLogSingleEntry2` at `0x14011d12e`
- `watchdog!WdLogSingleEntry2` at `0x14011d1bd`

## string_xrefs

- `0x14011d143`: `Unable to open section object 0x%I64p into handle table, Status = 0x%I64p`

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
0x14011d060  mov     rax, rsp
0x14011d063  mov     [rax+8], rbx
0x14011d067  push    rbp
0x14011d068  push    rsi
0x14011d069  push    rdi
0x14011d06a  push    r14
0x14011d06c  push    r15
0x14011d06e  sub     rsp, 50h
0x14011d072  mov     rbx, [rsp+78h+arg_20]
0x14011d07a  mov     r15, r9
0x14011d07d  mov     qword ptr [rax+10h], 0
0x14011d085  mov     bpl, r8b
0x14011d088  mov     qword ptr [rax+20h], 0
0x14011d090  mov     rdi, rdx
0x14011d093  mov     qword ptr [r9], 0
0x14011d09a  mov     r14, rcx
0x14011d09d  mov     eax, [rdx+30h]
0x14011d0a0  test    al, 8
0x14011d0a2  jz      short loc_14011D0D5
0x14011d0a4  mov     rax, [rdx+18h]
0x14011d0a8  mov     rcx, [rax]
0x14011d0ab  mov     rax, [rsp+78h+arg_8]
0x14011d0b3  mov     [r15], rax
0x14011d0b6  test    rbx, rbx
0x14011d0b9  jz      short loc_14011D0BE
0x14011d0bb  mov     [rbx], rcx
0x14011d0be  xor     eax, eax
0x14011d0c0  mov     rbx, [rsp+78h+arg_0]
0x14011d0c8  add     rsp, 50h
0x14011d0cc  pop     r15
0x14011d0ce  pop     r14
0x14011d0d0  pop     rdi
0x14011d0d1  pop     rsi
0x14011d0d2  pop     rbp
0x14011d0d3  retn
0x14011d0d5  test    al, 4
0x14011d0d7  jz      loc_14011D167
0x14011d0dd  mov     rcx, [rdx]
0x14011d0e0  call    cs:__imp_ObGetObjectType
0x14011d0e7  nop     dword ptr [rax+rax+00h]
0x14011d0ec  lea     rcx, [rsp+78h+arg_8]
0x14011d0f4  xor     r9d, r9d; DesiredAccess
0x14011d0f7  mov     [rsp+78h+Handle], rcx; Handle
0x14011d0fc  xor     r8d, r8d; PassedAccessState
0x14011d0ff  mov     rcx, [rdi]; Object
0x14011d102  xor     edx, edx; HandleAttributes
0x14011d104  mov     [rsp+78h+AccessMode], 1; AccessMode
0x14011d109  mov     [rsp+78h+ObjectType], rax; ObjectType
0x14011d10e  call    cs:__imp_ObOpenObjectByPointer
0x14011d115  nop     dword ptr [rax+rax+00h]
0x14011d11a  mov     esi, eax
0x14011d11c  test    eax, eax
0x14011d11e  jns     short loc_14011D167
0x14011d120  mov     rdx, [rdi]
0x14011d123  mov     ecx, 1
0x14011d128  movsxd  rbx, eax
0x14011d12b  mov     r8, rbx
0x14011d12e  call    cs:__imp_WdLogSingleEntry2
0x14011d135  nop     dword ptr [rax+rax+00h]
0x14011d13a  mov     [rsp+78h+var_40], 0
0x14011d143  lea     r9, aUnableToOpenSe; "Unable to open section object 0x%I64p i"...
0x14011d14a  mov     [rsp+78h+Handle], 0
0x14011d153  mov     qword ptr [rsp+78h+AccessMode], rbx
0x14011d158  mov     cs:WdLogGlobalForLineNumber, 416h
0x14011d162  jmp     loc_14011D1F1
0x14011d167  xor     ecx, ecx
0x14011d169  test    rbx, rbx
0x14011d16c  jz      loc_14011D0AB
0x14011d172  mov     rax, [r14]
0x14011d175  lea     rcx, [rsp+78h+arg_18]
0x14011d17d  mov     [rsp+78h+Handle], rcx
0x14011d182  xor     r9d, r9d
0x14011d185  mov     [rsp+78h+AccessMode], bpl
0x14011d18a  xor     r8d, r8d
0x14011d18d  mov     rdx, rdi
0x14011d190  mov     byte ptr [rsp+78h+ObjectType], 1
0x14011d195  mov     rax, [rax+38h]
0x14011d199  mov     rcx, r14
0x14011d19c  call    _guard_dispatch_icall
0x14011d1a1  mov     rcx, rax
0x14011d1a4  test    rax, rax
0x14011d1a7  jnz     loc_14011D0AB
0x14011d1ad  mov     rsi, 0FFFFFFFFC0000017h
0x14011d1b4  mov     rdx, [rdi]
0x14011d1b7  lea     ecx, [rax+1]
0x14011d1ba  mov     r8, rsi
0x14011d1bd  call    cs:__imp_WdLogSingleEntry2
0x14011d1c4  nop     dword ptr [rax+rax+00h]
0x14011d1c9  mov     [rsp+78h+var_40], 0
0x14011d1d2  lea     r9, aUnableToMapIni_0; "Unable to map initial view for section,"...
0x14011d1d9  mov     [rsp+78h+Handle], 0
0x14011d1e2  mov     qword ptr [rsp+78h+AccessMode], rsi
0x14011d1e7  mov     cs:WdLogGlobalForLineNumber, 42Bh
0x14011d1f1  mov     rax, [rdi]
0x14011d1f4  mov     edx, 40000h
0x14011d1f9  mov     [rsp+78h+ObjectType], rax
0x14011d1fe  call    DxgkLogInternalTriageEvent
0x14011d203  mov     r8, [rsp+78h+arg_18]
0x14011d20b  test    r8, r8
0x14011d20e  jz      short loc_14011D222
0x14011d210  mov     rax, [r14]
0x14011d213  mov     rdx, rdi
0x14011d216  mov     rcx, r14
0x14011d219  mov     rax, [rax+40h]
0x14011d21d  call    _guard_dispatch_icall
0x14011d222  mov     rcx, [rsp+78h+arg_8]; Handle
0x14011d22a  test    rcx, rcx
0x14011d22d  jz      short loc_14011D245
0x14011d22f  test    rcx, 0FFFFFFFF80000000h
0x14011d236  setz    dl; PreviousMode
0x14011d239  call    cs:__imp_ObCloseHandle
0x14011d240  nop     dword ptr [rax+rax+00h]
0x14011d245  mov     eax, esi
0x14011d247  jmp     loc_14011D0C0
```
