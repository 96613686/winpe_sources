# wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x140005fc4`
- end: `0x14000603b`
- name: `??1?$ActivityData@VDXGIAdapterCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140005f4c`
- `0x14000672c`

## callees

- `0x140004cbc`
- `0x140005fc4`
- `0x140006be8`
- `0x14000a9b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005fe9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ff7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005ff7`

## pseudocode

```c
void __fastcall wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int *v4; // rax

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
    v4 = (unsigned int *)DXGIAdapterCacheLogging::Provider();
    _tlgWriteActivityAutoStop<70368744177664,5>(v4, a1 + 8);
  }
  *(_DWORD *)a1 = 3;
}

```

## disassembly

```asm
0x140005fc4  mov     [rsp+arg_0], rbx
0x140005fc9  mov     [rsp+arg_8], rsi
0x140005fce  push    rdi
0x140005fcf  sub     rsp, 20h
0x140005fd3  mov     rdi, rcx
0x140005fd6  add     rcx, 50h ; 'P'; this
0x140005fda  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x140005fdf  cmp     byte ptr [rdi+40h], 0
0x140005fe3  jz      short loc_140006001
0x140005fe5  mov     rbx, [rdi+38h]
0x140005fe9  call    cs:__imp_GetProcessHeap
0x140005fef  mov     r8, rbx; lpMem
0x140005ff2  xor     edx, edx; dwFlags
0x140005ff4  mov     rcx, rax; hHeap
0x140005ff7  call    cs:__imp_HeapFree
0x140005ffd  mov     byte ptr [rdi+40h], 0
0x140006001  mov     qword ptr [rdi+38h], 0
0x140006009  cmp     dword ptr [rdi], 1
0x14000600c  jnz     short loc_140006025
0x14000600e  mov     dword ptr [rdi], 2
0x140006014  call    ?Provider@DXGIAdapterCacheLogging@@SAPEBU_tlgProvider_t@@XZ; DXGIAdapterCacheLogging::Provider(void)
0x140006019  lea     rdx, [rdi+8]
0x14000601d  mov     rcx, rax
0x140006020  call    ??$_tlgWriteActivityAutoStop@$0EAAAAAAAAAAA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<70368744177664,5>(_tlgProvider_t const *,_GUID const *)
0x140006025  mov     rbx, [rsp+28h+arg_0]
0x14000602a  mov     rsi, [rsp+28h+arg_8]
0x14000602f  mov     dword ptr [rdi], 3
0x140006035  add     rsp, 20h
0x140006039  pop     rdi
0x14000603a  retn
```
