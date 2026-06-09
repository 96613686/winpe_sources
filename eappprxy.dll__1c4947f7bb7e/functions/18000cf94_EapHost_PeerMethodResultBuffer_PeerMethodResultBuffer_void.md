# EapHost::PeerMethodResultBuffer::~PeerMethodResultBuffer(void)

- ea: `0x18000cf94`
- end: `0x18000d04a`
- name: `??1PeerMethodResultBuffer@EapHost@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(EapHost::PeerMethodResultBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d0e0`

## callees

- `0x180002106`
- `0x1800022a8`
- `0x18000ce94`
- `0x18000cf00`
- `0x18000cf94`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cffb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d019`

## pseudocode

```c
void __fastcall EapHost::PeerMethodResultBuffer::~PeerMethodResultBuffer(LPVOID *this)
{
  void *v2; // rcx

  *this = &EapHost::PeerMethodResultBuffer::`vftable';
  CoTaskMemFree(this[4]);
  CoTaskMemFree(this[6]);
  if ( this[7] )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(this[7]);
  }
  if ( this[9] )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(this[9]);
  }
  v2 = this[10];
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(this[10]);
  }
  memset_0(this + 2, 0, 0x48u);
  *this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x18000cf94  mov     [rsp+arg_0], rbx
0x18000cf99  push    rdi
0x18000cf9a  sub     rsp, 20h
0x18000cf9e  mov     rdi, rcx
0x18000cfa1  lea     rax, ??_7PeerMethodResultBuffer@EapHost@@6B@; const EapHost::PeerMethodResultBuffer::`vftable'
0x18000cfa8  mov     [rcx], rax
0x18000cfab  mov     rcx, [rcx+20h]; pv
0x18000cfaf  call    cs:__imp_CoTaskMemFree
0x18000cfb6  nop     dword ptr [rax+rax+00h]
0x18000cfbb  mov     rcx, [rdi+30h]; pv
0x18000cfbf  call    cs:__imp_CoTaskMemFree
0x18000cfc6  nop     dword ptr [rax+rax+00h]
0x18000cfcb  mov     rcx, [rdi+38h]
0x18000cfcf  test    rcx, rcx
0x18000cfd2  jz      short loc_18000CFE9
0x18000cfd4  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x18000cfd9  mov     rcx, [rdi+38h]; pv
0x18000cfdd  call    cs:__imp_CoTaskMemFree
0x18000cfe4  nop     dword ptr [rax+rax+00h]
0x18000cfe9  mov     rcx, [rdi+48h]
0x18000cfed  test    rcx, rcx
0x18000cff0  jz      short loc_18000D007
0x18000cff2  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x18000cff7  mov     rcx, [rdi+48h]; pv
0x18000cffb  call    cs:__imp_CoTaskMemFree
0x18000d002  nop     dword ptr [rax+rax+00h]
0x18000d007  mov     rcx, [rdi+50h]; void *
0x18000d00b  test    rcx, rcx
0x18000d00e  jz      short loc_18000D025
0x18000d010  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x18000d015  mov     rcx, [rdi+50h]; pv
0x18000d019  call    cs:__imp_CoTaskMemFree
0x18000d020  nop     dword ptr [rax+rax+00h]
0x18000d025  xor     edx, edx; Val
0x18000d027  lea     r8d, [rdx+48h]; Size
0x18000d02b  lea     rcx, [rdi+10h]; void *
0x18000d02f  call    memset_0
0x18000d034  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18000d03b  mov     [rdi], rax
0x18000d03e  mov     rbx, [rsp+28h+arg_0]
0x18000d043  add     rsp, 20h
0x18000d047  pop     rdi
0x18000d048  retn
```
