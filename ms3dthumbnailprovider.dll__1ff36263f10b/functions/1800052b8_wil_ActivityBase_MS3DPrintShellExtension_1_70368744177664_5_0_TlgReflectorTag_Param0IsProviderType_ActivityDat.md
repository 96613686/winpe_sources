# wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x1800052b8`
- end: `0x18000532f`
- name: `??1?$ActivityData@VMS3DPrintShellExtension@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VMS3DPrintShellExtension@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180005240`
- `0x180005624`

## callees

- `0x180004f6c`
- `0x1800052b8`
- `0x180005748`
- `0x180007c04`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800052eb`
- `KERNEL32!HeapFree` at `0x1800052eb`
- `KERNEL32!GetProcessHeap` at `0x1800052dd`
- `KERNEL32!GetProcessHeap` at `0x1800052dd`

## pseudocode

```c
void __fastcall wil::ActivityBase<MS3DPrintShellExtension,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MS3DPrintShellExtension,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  const struct _tlgProvider_t *v4; // rax

  wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)(a1 + 80));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  if ( *(_DWORD *)a1 == 1 )
  {
    *(_DWORD *)a1 = 2;
    v4 = MS3DPrintShellExtension::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x1800052b8  mov     [rsp+arg_0], rbx
0x1800052bd  mov     [rsp+arg_8], rsi
0x1800052c2  push    rdi
0x1800052c3  sub     rsp, 20h
0x1800052c7  mov     rdi, rcx
0x1800052ca  add     rcx, 50h ; 'P'; this
0x1800052ce  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800052d3  cmp     byte ptr [rdi+40h], 0
0x1800052d7  jz      short loc_1800052F5
0x1800052d9  mov     rbx, [rdi+38h]
0x1800052dd  call    cs:__imp_GetProcessHeap
0x1800052e3  mov     r8, rbx; lpMem
0x1800052e6  xor     edx, edx; dwFlags
0x1800052e8  mov     rcx, rax; hHeap
0x1800052eb  call    cs:__imp_HeapFree
0x1800052f1  mov     byte ptr [rdi+40h], 0
0x1800052f5  mov     qword ptr [rdi+38h], 0
0x1800052fd  cmp     dword ptr [rdi], 1
0x180005300  jnz     short loc_180005319
0x180005302  mov     dword ptr [rdi], 2
0x180005308  call    ?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ; MS3DPrintShellExtension::Provider(void)
0x18000530d  lea     rdx, [rdi+8]
0x180005311  mov     rcx, rax
0x180005314  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x180005319  mov     rbx, [rsp+28h+arg_0]
0x18000531e  mov     rsi, [rsp+28h+arg_8]
0x180005323  mov     dword ptr [rdi], 3
0x180005329  add     rsp, 20h
0x18000532d  pop     rdi
0x18000532e  retn
```
