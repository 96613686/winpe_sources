# IBaseCacheContextImpl::GetElementData(IElementKey const &,CachedElementData *)

- ea: `0x180147ca0`
- end: `0x180147e81`
- name: `?GetElementData@IBaseCacheContextImpl@@UEAAXAEBVIElementKey@@PEAUCachedElementData@@@Z`
- size: `481`
- prototype: `void __fastcall(IBaseCacheContextImpl *__hidden this, const struct IElementKey *, struct CachedElementData *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18012a85c`
- `0x180134718`
- `0x180147ca0`
- `0x180147e88`
- `0x180147ebc`
- `0x180147f28`
- `0x1801d6d84`
- `0x1801eb414`
- `0x180330010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180147cf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180147cf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147d94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147e4c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147d94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180147e4c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180147e6c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180147e6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall IBaseCacheContextImpl::GetElementData(
        IBaseCacheContextImpl *this,
        const struct IElementKey *a2,
        struct CachedElementData *a3)
{
  const struct LockHolder *v6; // rdx
  int v7; // eax
  _QWORD *v8; // r15
  struct IElementConstructionTask *i; // rdi
  __int64 v10; // rdx
  IElementConstructionTask *v11; // rsi
  struct IElementConstructionTask *v12; // rcx
  int v13; // eax
  HANDLE EventW; // rax

  if ( !(*(unsigned __int8 (__fastcall **)(IBaseCacheContextImpl *))(*(_QWORD *)this + 56LL))(this) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    if ( (*(unsigned __int8 (__fastcall **)(IBaseCacheContextImpl *, const struct IElementKey *, struct CachedElementData *))(*(_QWORD *)this + 56LL))(
           this,
           a2,
           a3) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
      v12 = 0;
    }
    else
    {
      v7 = *((_DWORD *)this + 77);
      v8 = (_QWORD *)((char *)this + 312);
      if ( v7 )
      {
        for ( i = *(struct IElementConstructionTask **)(*v8 + 8LL * (*((_DWORD *)a2 + 2) & (unsigned int)(v7 - 1)));
              i;
              i = (struct IElementConstructionTask *)*((_QWORD *)i + 2) )
        {
          if ( *((_DWORD *)i + 10) == *((_DWORD *)a2 + 2)
            && *((_DWORD *)i + 12) == *((_DWORD *)a2 + 3)
            && (*(unsigned __int8 (__fastcall **)(struct IElementConstructionTask *, const struct IElementKey *))(*(_QWORD *)i + 24LL))(
                 i,
                 a2) )
          {
            _InterlockedIncrement((volatile signed __int32 *)i + 2);
            ReleaseReference<IElementConstructionTask>(0);
            if ( !*((_QWORD *)i + 3) && *((_DWORD *)i + 8) == 1 )
            {
              EventW = CreateEventW(0, 1, 0, 0);
              *((_QWORD *)i + 3) = EventW;
              if ( !EventW )
                OSException::ThrowLastError();
            }
            v11 = i;
            goto LABEL_9;
          }
        }
      }
      if ( *((_DWORD *)this + 76) >= *((_DWORD *)this + 77) )
        ElementTaskList::GrowHashTable((IBaseCacheContextImpl *)((char *)this + 264), v6);
      i = (struct IElementConstructionTask *)(*(__int64 (__fastcall **)(const struct IElementKey *, IBaseCacheContextImpl *))(*(_QWORD *)a2 + 8LL))(
                                               a2,
                                               this);
      v10 = *((_DWORD *)a2 + 2) & (unsigned int)(*((_DWORD *)this + 77) - 1);
      *((_QWORD *)i + 2) = *(_QWORD *)(*v8 + 8 * v10);
      *(_QWORD *)(*v8 + 8 * v10) = i;
      _InterlockedIncrement((volatile signed __int32 *)i + 2);
      ++*((_DWORD *)this + 76);
      _InterlockedIncrement((volatile signed __int32 *)i + 2);
      ReleaseReference<IElementConstructionTask>(0);
      v11 = 0;
LABEL_9:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
      if ( v11 )
      {
        v13 = IElementConstructionTask::WaitForCompletion(v11);
        LogAndThrowIfFailed<OSException>(v13);
      }
      else
      {
        ElementTaskList::ExecuteTask((IBaseCacheContextImpl *)((char *)this + 264), this, i, 1);
      }
      CachedElementData::operator=(a3, (char *)i + 40);
      v12 = i;
    }
    ReleaseReference<IElementConstructionTask>(v12);
  }
}

```

## disassembly

```asm
0x180147ca0  mov     [rsp+arg_8], rbx
0x180147ca5  push    rbp
0x180147ca6  push    rsi
0x180147ca7  push    rdi
0x180147ca8  push    r14
0x180147caa  push    r15
0x180147cac  sub     rsp, 20h
0x180147cb0  mov     rbp, r8
0x180147cb3  mov     rsi, rdx
0x180147cb6  mov     r14, rcx
0x180147cb9  mov     rax, [rcx]
0x180147cbc  mov     rax, [rax+38h]
0x180147cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147cc5  test    al, al
0x180147cc7  jz      short loc_180147CDA
0x180147cc9  mov     rbx, [rsp+48h+arg_8]
0x180147cce  add     rsp, 20h
0x180147cd2  pop     r15
0x180147cd4  pop     r14
0x180147cd6  pop     rdi
0x180147cd7  pop     rsi
0x180147cd8  pop     rbp
0x180147cd9  retn
0x180147cda  lea     rbx, [r14+108h]
0x180147ce1  mov     [rsp+48h+arg_0], 0
0x180147cea  mov     [rsp+48h+arg_18], rbx
0x180147cef  mov     rcx, rbx; lpCriticalSection
0x180147cf2  call    cs:__imp_EnterCriticalSection
0x180147cf8  nop
0x180147cf9  mov     rax, [r14]
0x180147cfc  mov     r8, rbp
0x180147cff  mov     rdx, rsi
0x180147d02  mov     rcx, r14
0x180147d05  mov     rax, [rax+38h]
0x180147d09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147d0e  test    al, al
0x180147d10  jnz     loc_180147E49
0x180147d16  mov     eax, [rbx+2Ch]
0x180147d19  lea     r15, [rbx+30h]
0x180147d1d  test    eax, eax
0x180147d1f  jz      short loc_180147D3A
0x180147d21  lea     ecx, [rax-1]
0x180147d24  mov     eax, [rsi+8]
0x180147d27  and     rcx, rax
0x180147d2a  mov     rdi, [r15]
0x180147d2d  mov     rdi, [rdi+rcx*8]
0x180147d31  test    rdi, rdi
0x180147d34  jnz     loc_180147DD7
0x180147d3a  mov     eax, [rbx+2Ch]
0x180147d3d  cmp     [rbx+28h], eax
0x180147d40  jnb     loc_180147DCA
0x180147d46  mov     rax, [rsi]
0x180147d49  mov     rdx, r14
0x180147d4c  mov     rcx, rsi
0x180147d4f  mov     rax, [rax+8]
0x180147d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147d58  mov     rdi, rax
0x180147d5b  mov     edx, [rbx+2Ch]
0x180147d5e  dec     edx
0x180147d60  mov     eax, [rsi+8]
0x180147d63  and     rdx, rax
0x180147d66  mov     rax, [r15]
0x180147d69  mov     rcx, [rax+rdx*8]
0x180147d6d  mov     [rdi+10h], rcx
0x180147d71  mov     rax, [r15]
0x180147d74  mov     [rax+rdx*8], rdi
0x180147d78  lock inc dword ptr [rdi+8]
0x180147d7c  inc     dword ptr [rbx+28h]
0x180147d7f  mov     [rsp+48h+arg_0], rdi
0x180147d84  lock inc dword ptr [rdi+8]
0x180147d88  xor     ecx, ecx
0x180147d8a  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180147d8f  xor     esi, esi
0x180147d91  mov     rcx, rbx; lpCriticalSection
0x180147d94  call    cs:__imp_LeaveCriticalSection
0x180147d9a  test    rsi, rsi
0x180147d9d  jnz     short loc_180147DE8
0x180147d9f  mov     r9b, 1; bool
0x180147da2  mov     r8, rdi; struct IElementConstructionTask *
0x180147da5  mov     rdx, r14; struct IBaseCacheContext *
0x180147da8  mov     rcx, rbx; this
0x180147dab  call    ?ExecuteTask@ElementTaskList@@QEAAJPEAUIBaseCacheContext@@PEAVIElementConstructionTask@@_N@Z; ElementTaskList::ExecuteTask(IBaseCacheContext *,IElementConstructionTask *,bool)
0x180147db0  lea     rdx, [rdi+28h]
0x180147db4  mov     rcx, rbp
0x180147db7  call    ??4CachedElementData@@QEAAAEAU0@AEBU0@@Z; CachedElementData::operator=(CachedElementData const &)
0x180147dbc  nop
0x180147dbd  mov     rcx, rdi
0x180147dc0  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180147dc5  jmp     loc_180147CC9
0x180147dca  mov     rcx, rbx; this
0x180147dcd  call    ?GrowHashTable@ElementTaskList@@AEAAXAEBVLockHolder@@@Z; ElementTaskList::GrowHashTable(LockHolder const &)
0x180147dd2  jmp     loc_180147D46
0x180147dd7  mov     eax, [rsi+8]
0x180147dda  cmp     [rdi+28h], eax
0x180147ddd  jz      short loc_180147E0C
0x180147ddf  mov     rdi, [rdi+10h]
0x180147de3  jmp     loc_180147D31
0x180147de8  mov     rbx, 4445746567h
0x180147df2  mov     rcx, rsi; this
0x180147df5  call    ?WaitForCompletion@IElementConstructionTask@@AEAAJXZ; IElementConstructionTask::WaitForCompletion(void)
0x180147dfa  mov     ecx, eax; int
0x180147dfc  mov     r8d, 0AAh
0x180147e02  mov     rdx, rbx
0x180147e05  call    ??$LogAndThrowIfFailed@VOSException@@@@YAXJVEventTag@@I@Z; LogAndThrowIfFailed<OSException>(long,EventTag,uint)
0x180147e0a  jmp     short loc_180147DB0
0x180147e0c  mov     eax, [rsi+0Ch]
0x180147e0f  cmp     [rdi+30h], eax
0x180147e12  jnz     short loc_180147DDF
0x180147e14  mov     rax, [rdi]
0x180147e17  mov     rdx, rsi
0x180147e1a  mov     rcx, rdi
0x180147e1d  mov     rax, [rax+18h]
0x180147e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180147e26  test    al, al
0x180147e28  jz      short loc_180147DDF
0x180147e2a  mov     [rsp+48h+arg_0], rdi
0x180147e2f  lock inc dword ptr [rdi+8]
0x180147e33  xor     ecx, ecx
0x180147e35  call    ??$ReleaseReference@VIElementConstructionTask@@@@YAXPEAVIElementConstructionTask@@@Z; ReleaseReference<IElementConstructionTask>(IElementConstructionTask *)
0x180147e3a  cmp     qword ptr [rdi+18h], 0
0x180147e3f  jz      short loc_180147E5A
0x180147e41  mov     rsi, rdi
0x180147e44  jmp     loc_180147D91
0x180147e49  mov     rcx, rbx; lpCriticalSection
0x180147e4c  call    cs:__imp_LeaveCriticalSection
0x180147e52  nop
0x180147e53  xor     ecx, ecx
0x180147e55  jmp     loc_180147DC0
0x180147e5a  cmp     dword ptr [rdi+20h], 1
0x180147e5e  jnz     short loc_180147E41
0x180147e60  xor     r9d, r9d; lpName
0x180147e63  xor     r8d, r8d; bInitialState
0x180147e66  lea     edx, [r9+1]; bManualReset
0x180147e6a  xor     ecx, ecx; lpEventAttributes
0x180147e6c  call    cs:__imp_CreateEventW
0x180147e72  mov     [rdi+18h], rax
0x180147e76  test    rax, rax
0x180147e79  jnz     short loc_180147E41
0x180147e7b  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
```
