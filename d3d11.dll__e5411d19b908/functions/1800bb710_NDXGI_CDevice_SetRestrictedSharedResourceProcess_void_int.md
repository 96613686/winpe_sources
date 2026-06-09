# NDXGI::CDevice::SetRestrictedSharedResourceProcess(void *,int)

- ea: `0x1800bb710`
- end: `0x1800bb871`
- name: `?SetRestrictedSharedResourceProcess@CDevice@NDXGI@@UEAAJPEAXH@Z`
- size: `353`
- prototype: `int(NDXGI::CDevice *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1800a65d0`

## callees

- `0x18004e694`
- `0x18006b7ec`
- `0x1800b6e40`
- `0x1800bb710`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800bb76b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800bb76b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb857`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb778`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb857`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb738`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb738`

## pseudocode

```c
__int64 __fastcall NDXGI::CDevice::SetRestrictedSharedResourceProcess(NDXGI::CDevice *this, void *a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // r12
  __int64 v7; // rax
  __int64 v8; // rbp
  int v10; // r15d
  _QWORD *v11; // rbx
  _QWORD *i; // rbx
  _QWORD *v13; // rdx
  __int64 v14; // rdx
  void *v15; // [rsp+88h] [rbp+10h] BYREF

  v15 = a2;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1296);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1296));
  v7 = std::_Find_vectorized<void *,void *>(*((_QWORD *)this + 159), *((_QWORD *)this + 160), a2);
  v8 = v7;
  if ( !a3 || v7 == *((_QWORD *)this + 160) && GetProcessId(a2) )
  {
    v10 = 0;
    v11 = (_QWORD *)*((_QWORD *)this + 157);
    do
    {
      v11 = (_QWORD *)*v11;
      if ( v11 == *((_QWORD **)this + 157) )
        break;
      v10 = (*(__int64 (__fastcall **)(NDXGI::CDevice *, _QWORD, void *, _QWORD, _DWORD))(*(_QWORD *)this + 400LL))(
              this,
              0,
              a2,
              a3,
              *(_DWORD *)(v11[2] + 4LL));
    }
    while ( v10 >= 0 );
    if ( a3 )
    {
      if ( v10 >= 0 )
      {
        v13 = (_QWORD *)*((_QWORD *)this + 160);
        if ( v13 == *((_QWORD **)this + 161) )
        {
          std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>((char *)this + 1272, v13, &v15);
        }
        else
        {
          *v13 = a2;
          *((_QWORD *)this + 160) += 8LL;
        }
      }
      else
      {
        for ( i = (_QWORD *)*((_QWORD *)this + 157);
              ;
              (*(void (__fastcall **)(NDXGI::CDevice *, _QWORD, void *, _QWORD, _DWORD))(*(_QWORD *)this + 400LL))(
                this,
                0,
                a2,
                0,
                *(_DWORD *)(i[2] + 4LL)) )
        {
          i = (_QWORD *)*i;
          if ( i == *((_QWORD **)this + 157) )
            break;
        }
      }
    }
    else
    {
      v14 = *((_QWORD *)this + 160);
      if ( v8 != v14 )
      {
        std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
          v8 + 8,
          v14,
          v8);
        *((_QWORD *)this + 160) -= 8LL;
      }
    }
    LeaveCriticalSection(v6);
    return (unsigned int)v10;
  }
  else
  {
    LeaveCriticalSection(v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800bb710  mov     [rsp+arg_8], rdx
0x1800bb715  push    rbx
0x1800bb716  push    rbp
0x1800bb717  push    rsi
0x1800bb718  push    rdi
0x1800bb719  push    r12
0x1800bb71b  push    r13
0x1800bb71d  push    r14
0x1800bb71f  push    r15
0x1800bb721  sub     rsp, 38h
0x1800bb725  mov     r13d, r8d
0x1800bb728  mov     r14, rdx
0x1800bb72b  mov     rdi, rcx
0x1800bb72e  lea     r12, [rcx+510h]
0x1800bb735  mov     rcx, r12; lpCriticalSection
0x1800bb738  call    cs:__imp_EnterCriticalSection
0x1800bb73e  lea     rsi, [rdi+4F8h]
0x1800bb745  mov     r8, r14
0x1800bb748  mov     rdx, [rdi+500h]
0x1800bb74f  mov     rcx, [rsi]
0x1800bb752  call    ??$_Find_vectorized@PEAXPEAX@std@@YAPEAPEAXQEAPEAX0QEAX@Z; std::_Find_vectorized<void *,void *>(void * * const,void * * const,void * const)
0x1800bb757  mov     rbp, rax
0x1800bb75a  test    r13d, r13d
0x1800bb75d  jz      short loc_1800BB788
0x1800bb75f  cmp     rax, [rdi+500h]
0x1800bb766  jnz     short loc_1800BB775
0x1800bb768  mov     rcx, r14; Process
0x1800bb76b  call    cs:__imp_GetProcessId
0x1800bb771  test    eax, eax
0x1800bb773  jnz     short loc_1800BB788
0x1800bb775  mov     rcx, r12; lpCriticalSection
0x1800bb778  call    cs:__imp_LeaveCriticalSection
0x1800bb77e  mov     eax, 80070057h
0x1800bb783  jmp     loc_1800BB860
0x1800bb788  xor     r15d, r15d
0x1800bb78b  mov     rbx, [rdi+4E8h]
0x1800bb792  mov     rbx, [rbx]
0x1800bb795  cmp     rbx, [rdi+4E8h]
0x1800bb79c  jz      short loc_1800BB7CA
0x1800bb79e  mov     rax, [rdi]
0x1800bb7a1  mov     rcx, [rbx+10h]
0x1800bb7a5  mov     ecx, [rcx+4]
0x1800bb7a8  mov     [rsp+78h+var_58], ecx
0x1800bb7ac  mov     r9d, r13d
0x1800bb7af  mov     r8, r14
0x1800bb7b2  xor     edx, edx
0x1800bb7b4  mov     rcx, rdi
0x1800bb7b7  mov     rax, [rax+190h]
0x1800bb7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb7c3  mov     r15d, eax
0x1800bb7c6  test    eax, eax
0x1800bb7c8  jns     short loc_1800BB792
0x1800bb7ca  test    r13d, r13d
0x1800bb7cd  jz      short loc_1800BB834
0x1800bb7cf  test    r15d, r15d
0x1800bb7d2  jns     short loc_1800BB80E
0x1800bb7d4  mov     rbx, [rdi+4E8h]
0x1800bb7db  mov     rbx, [rbx]
0x1800bb7de  cmp     rbx, [rdi+4E8h]
0x1800bb7e5  jz      short loc_1800BB854
0x1800bb7e7  mov     rax, [rdi]
0x1800bb7ea  mov     rcx, [rbx+10h]
0x1800bb7ee  mov     ecx, [rcx+4]
0x1800bb7f1  mov     [rsp+78h+var_58], ecx
0x1800bb7f5  xor     r9d, r9d
0x1800bb7f8  mov     r8, r14
0x1800bb7fb  xor     edx, edx
0x1800bb7fd  mov     rcx, rdi
0x1800bb800  mov     rax, [rax+190h]
0x1800bb807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb80c  jmp     short loc_1800BB7DB
0x1800bb80e  mov     rdx, [rsi+8]
0x1800bb812  cmp     rdx, [rsi+10h]
0x1800bb816  jz      short loc_1800BB822
0x1800bb818  mov     [rdx], r14
0x1800bb81b  add     qword ptr [rsi+8], 8
0x1800bb820  jmp     short loc_1800BB854
0x1800bb822  lea     r8, [rsp+78h+arg_8]
0x1800bb82a  mov     rcx, rsi
0x1800bb82d  call    ??$_Emplace_reallocate@AEB_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAPEA_KQEA_KAEB_K@Z; std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(unsigned __int64 * const,unsigned __int64 const &)
0x1800bb832  jmp     short loc_1800BB854
0x1800bb834  mov     rdx, [rdi+500h]
0x1800bb83b  cmp     rbp, rdx
0x1800bb83e  jz      short loc_1800BB854
0x1800bb840  lea     rcx, [rbp+8]
0x1800bb844  mov     r8, rbp
0x1800bb847  call    ??$_Copy_memmove@PEBU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEAU1@@std@@YAPEAU_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3@@PEBU1@0PEAU1@@Z; std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *)
0x1800bb84c  add     qword ptr [rdi+500h], 0FFFFFFFFFFFFFFF8h
0x1800bb854  mov     rcx, r12; lpCriticalSection
0x1800bb857  call    cs:__imp_LeaveCriticalSection
0x1800bb85d  mov     eax, r15d
0x1800bb860  add     rsp, 38h
0x1800bb864  pop     r15
0x1800bb866  pop     r14
0x1800bb868  pop     r13
0x1800bb86a  pop     r12
0x1800bb86c  pop     rdi
0x1800bb86d  pop     rsi
0x1800bb86e  pop     rbp
0x1800bb86f  pop     rbx
0x1800bb870  retn
```
