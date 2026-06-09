# CPacketRadius::~CPacketRadius(void)

- ea: `0x180012898`
- end: `0x18001293b`
- name: `??1CPacketRadius@@UEAA@XZ`
- size: `163`
- prototype: `void __fastcall(CPacketRadius *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012950`

## callees

- `0x180012898`
- `0x180014580`
- `0x18002af04`
- `0x180030010`

## import_xrefs

- `msvcrt!free` at `0x1800128ed`
- `msvcrt!free` at `0x1800128ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012929`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012929`

## pseudocode

```c
void __fastcall CPacketRadius::~CPacketRadius(CPacketRadius *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CPacketRadius::`vftable';
  if ( *((_QWORD *)this + 2) )
  {
    v2 = 0;
    if ( *((_DWORD *)this + 22) != -8 )
    {
      do
        IASAttributeRelease(*(LPVOID *)(*((_QWORD *)this + 2) + 16LL * v2++ + 8));
      while ( v2 < *((_DWORD *)this + 22) + 8 );
    }
    CoTaskMemFree(*((LPVOID *)this + 2));
  }
  free(*((void **)this + 10));
  v3 = *((_QWORD *)this + 16);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  if ( *((_QWORD *)this + 5) )
    memory_pool<4096,task_allocator>::deallocate(&CPacketRadius::m_OutBufferPool);
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    CoTaskMemFree(v4);
}

```

## disassembly

```asm
0x180012898  mov     [rsp+arg_0], rbx
0x18001289d  push    rdi
0x18001289e  sub     rsp, 20h
0x1800128a2  mov     rbx, rcx
0x1800128a5  lea     rax, ??_7CPacketRadius@@6B@; const CPacketRadius::`vftable'
0x1800128ac  mov     [rcx], rax
0x1800128af  cmp     qword ptr [rcx+10h], 0
0x1800128b4  jz      short loc_1800128E9
0x1800128b6  xor     edi, edi
0x1800128b8  mov     eax, [rcx+58h]
0x1800128bb  add     eax, 8
0x1800128be  jz      short loc_1800128DF
0x1800128c0  mov     eax, edi
0x1800128c2  add     rax, rax
0x1800128c5  mov     rcx, [rbx+10h]
0x1800128c9  mov     rcx, [rcx+rax*8+8]; pv
0x1800128ce  call    IASAttributeRelease
0x1800128d3  inc     edi
0x1800128d5  mov     eax, [rbx+58h]
0x1800128d8  add     eax, 8
0x1800128db  cmp     edi, eax
0x1800128dd  jb      short loc_1800128C0
0x1800128df  mov     rcx, [rbx+10h]; pv
0x1800128e3  call    cs:__imp_CoTaskMemFree
0x1800128e9  mov     rcx, [rbx+50h]; Block
0x1800128ed  call    cs:__imp_free
0x1800128f3  mov     rcx, [rbx+80h]
0x1800128fa  test    rcx, rcx
0x1800128fd  jz      short loc_18001290B
0x1800128ff  mov     rax, [rcx]
0x180012902  mov     rax, [rax+10h]
0x180012906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001290b  mov     rdx, [rbx+28h]
0x18001290f  test    rdx, rdx
0x180012912  jz      short loc_180012920
0x180012914  lea     rcx, ?m_OutBufferPool@CPacketRadius@@0V?$memory_pool@$0BAAA@Vtask_allocator@@@@A; lpCriticalSection
0x18001291b  call    ?deallocate@?$memory_pool@$0BAAA@Vtask_allocator@@@@QEAAXPEAX@Z; memory_pool<4096,task_allocator>::deallocate(void *)
0x180012920  mov     rcx, [rbx+18h]; pv
0x180012924  test    rcx, rcx
0x180012927  jz      short loc_180012930
0x180012929  call    cs:__imp_CoTaskMemFree
0x18001292f  nop
0x180012930  mov     rbx, [rsp+28h+arg_0]
0x180012935  add     rsp, 20h
0x180012939  pop     rdi
0x18001293a  retn
```
