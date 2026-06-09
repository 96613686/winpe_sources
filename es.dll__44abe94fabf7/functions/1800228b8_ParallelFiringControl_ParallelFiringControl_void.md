# ParallelFiringControl::~ParallelFiringControl(void)

- ea: `0x1800228b8`
- end: `0x1800229d1`
- name: `??1ParallelFiringControl@@UEAA@XZ`
- size: `281`
- prototype: `void __fastcall(ParallelFiringControl *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180022880`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180009034`
- `0x18001de98`
- `0x1800228b8`
- `0x1800229d8`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002292b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002292b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022923`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022923`

## string_xrefs

- `0x18002295e`: `com\complus\src\events\tier1\agent.cpp`
- `0x18002298d`: `com\complus\src\events\tier1\agent.cpp`
- `0x1800229b8`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
void __fastcall ParallelFiringControl::~ParallelFiringControl(ParallelFiringControl *this)
{
  void *v2; // rcx
  int i; // edi
  void *v4; // rcx
  int v5; // eax

  *(_QWORD *)this = &ParallelFiringControl::`vftable';
  v2 = (void *)*((_QWORD *)this + 8);
  if ( v2 )
  {
    if ( !CloseHandle(v2) )
      InternalError_Win32(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF95u, 0x12u, L"CloseHandle");
    *((_QWORD *)this + 8) = 0;
  }
  if ( !*((_QWORD *)this + 19) )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF9Bu, 0x80001203, 0x12u);
  for ( i = 0; i < *((_DWORD *)this + 36); ++i )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 15) + 4LL * i) )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 32LL))(*((_QWORD *)this + 19));
      if ( v5 < 0 )
        InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xFA1u, 0x12u, v5);
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 19) + 16LL))(*((_QWORD *)this + 19));
  v4 = (void *)*((_QWORD *)this + 15);
  if ( v4 )
    CoTaskMemFree(v4);
  CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveAll((char *)this + 72);
  FiringControl::~FiringControl(this);
}

```

## disassembly

```asm
0x1800228b8  mov     [rsp+arg_0], rbx
0x1800228bd  push    rdi
0x1800228be  sub     rsp, 20h
0x1800228c2  lea     rax, ??_7ParallelFiringControl@@6B@; const ParallelFiringControl::`vftable'
0x1800228c9  mov     rbx, rcx
0x1800228cc  mov     [rcx], rax
0x1800228cf  mov     rcx, [rcx+40h]; hObject
0x1800228d3  test    rcx, rcx
0x1800228d6  jnz     short loc_18002292B
0x1800228d8  cmp     qword ptr [rbx+98h], 0
0x1800228e0  jz      short loc_180022959
0x1800228e2  xor     edi, edi
0x1800228e4  cmp     [rbx+90h], edi
0x1800228ea  jg      short loc_18002293F
0x1800228ec  mov     rcx, [rbx+98h]
0x1800228f3  mov     rax, [rcx]
0x1800228f6  mov     rax, [rax+10h]
0x1800228fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228ff  mov     rcx, [rbx+78h]; pv
0x180022903  test    rcx, rcx
0x180022906  jnz     short loc_180022923
0x180022908  lea     rcx, [rbx+48h]
0x18002290c  call    ?RemoveAll@?$CList@PEAUAutoUpdateListElement@FiringAgent@@PEAU12@@@QEAAXXZ; CList<FiringAgent::AutoUpdateListElement *,FiringAgent::AutoUpdateListElement *>::RemoveAll(void)
0x180022911  mov     rcx, rbx; this
0x180022914  mov     rbx, [rsp+28h+arg_0]
0x180022919  add     rsp, 20h
0x18002291d  pop     rdi
0x18002291e  jmp     ??1FiringControl@@UEAA@XZ; FiringControl::~FiringControl(void)
0x180022923  call    cs:__imp_CoTaskMemFree
0x180022929  jmp     short loc_180022908
0x18002292b  call    cs:__imp_CloseHandle
0x180022931  test    eax, eax
0x180022933  jz      short loc_18002297B
0x180022935  mov     qword ptr [rbx+40h], 0
0x18002293d  jmp     short loc_1800228D8
0x18002293f  mov     rax, [rbx+78h]
0x180022943  movsxd  rcx, edi
0x180022946  mov     edx, [rax+rcx*4]
0x180022949  test    edx, edx
0x18002294b  jnz     short loc_18002299B
0x18002294d  inc     edi
0x18002294f  cmp     edi, [rbx+90h]
0x180022955  jge     short loc_1800228EC
0x180022957  jmp     short loc_18002293F
0x180022959  mov     edx, 0F9Bh; unsigned int
0x18002295e  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180022965  mov     r9d, 12h; unsigned __int16
0x18002296b  mov     r8d, 80001203h; unsigned int
0x180022971  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180022976  jmp     loc_1800228E2
0x18002297b  mov     r8d, 12h; unsigned __int16
0x180022981  lea     r9, aClosehandle; "CloseHandle"
0x180022988  mov     edx, 0F95h; unsigned int
0x18002298d  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180022994  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x180022999  jmp     short loc_180022935
0x18002299b  mov     rcx, [rbx+98h]
0x1800229a2  mov     rax, [rcx]
0x1800229a5  mov     rax, [rax+20h]
0x1800229a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229ae  test    eax, eax
0x1800229b0  jns     short loc_18002294D
0x1800229b2  mov     r8d, 12h; unsigned __int16
0x1800229b8  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x1800229bf  mov     r9d, eax; int
0x1800229c2  mov     edx, 0FA1h; unsigned int
0x1800229c7  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x1800229cc  jmp     loc_18002294D
```
