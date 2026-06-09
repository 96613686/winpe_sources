# CClassFactory::CreateProvidersIfNeeded(_GUID const &)

- ea: `0x18000d230`
- end: `0x18000d344`
- name: `?CreateProvidersIfNeeded@CClassFactory@@AEAAJAEBU_GUID@@@Z`
- size: `276`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000ce20`

## callees

- `0x180001ef4`
- `0x18000d230`
- `0x180015ff8`
- `0x180016e2c`
- `0x18001a5ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d290`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000d290`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d25d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d25d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d312`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d31f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d312`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d31f`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateProvidersIfNeeded(CClassFactory *this, const struct _GUID *a2)
{
  DockingProviders *v3; // rcx
  RTL_SRWLOCK *v4; // rax
  RTL_SRWLOCK *v5; // rbx
  int v6; // edi
  DockingProviders *v7; // rcx
  int IfNeeded; // eax
  unsigned int v10; // ecx

  v3 = (DockingProviders *)*((_QWORD *)this + 8);
  if ( v3 )
  {
    IfNeeded = DockingProviders::LoadIfNeeded(v3);
    v10 = 0;
    if ( IfNeeded < 0 )
      return (unsigned int)IfNeeded;
    return v10;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    if ( *((_QWORD *)this + 8) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      return 0;
    }
    else
    {
      v4 = (RTL_SRWLOCK *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
      v5 = v4;
      if ( v4 )
      {
        InitializeSRWLock(v4);
        LODWORD(v5[1].Ptr) = 0;
        BYTE4(v5[1].Ptr) = 0;
        LODWORD(v5[2].Ptr) = 0;
        v5[3].Ptr = 0;
        WorkItems::WorkItems((WorkItems *)&v5[4]);
        _InterlockedIncrement((volatile signed __int32 *)&g_cLockCount);
        _InterlockedIncrement((volatile signed __int32 *)&v5[1]);
      }
      else
      {
        v5 = 0;
      }
      if ( v5 )
      {
        v6 = DockingProviders::LoadIfNeeded((DockingProviders *)v5);
        if ( v6 >= 0 )
        {
          v7 = (DockingProviders *)*((_QWORD *)this + 8);
          if ( v7 )
            DockingProviders::Release(v7);
          *((_QWORD *)this + 8) = v5;
          v6 = 0;
        }
        else
        {
          DockingProviders::Release((DockingProviders *)v5);
        }
      }
      else
      {
        v6 = -2147024882;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      return (unsigned int)v6;
    }
  }
}

```

## disassembly

```asm
0x18000d230  mov     [rsp+arg_10], rbx
0x18000d235  mov     [rsp+arg_8], rdx
0x18000d23a  push    rbp
0x18000d23b  push    rsi
0x18000d23c  push    rdi
0x18000d23d  sub     rsp, 20h
0x18000d241  mov     rsi, rcx
0x18000d244  mov     rcx, [rcx+40h]; this
0x18000d248  test    rcx, rcx
0x18000d24b  jnz     loc_18000D329
0x18000d251  lea     rbp, [rsi+18h]
0x18000d255  mov     [rsp+38h+arg_0], rbp
0x18000d25a  mov     rcx, rbp; lpCriticalSection
0x18000d25d  call    cs:__imp_EnterCriticalSection
0x18000d263  nop
0x18000d264  cmp     qword ptr [rsi+40h], 0
0x18000d269  jnz     loc_18000D31C
0x18000d26f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d276  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000d27b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d280  mov     rbx, rax
0x18000d283  mov     [rsp+38h+arg_8], rax
0x18000d288  test    rax, rax
0x18000d28b  jz      short loc_18000D2D0
0x18000d28d  mov     rcx, rax; SRWLock
0x18000d290  call    cs:__imp_InitializeSRWLock
0x18000d296  mov     dword ptr [rbx+8], 0
0x18000d29d  mov     byte ptr [rbx+0Ch], 0
0x18000d2a1  mov     dword ptr [rbx+10h], 0
0x18000d2a8  mov     qword ptr [rbx+18h], 0
0x18000d2b0  lea     rcx, [rbx+20h]; this
0x18000d2b4  call    ??0WorkItems@@QEAA@XZ; WorkItems::WorkItems(void)
0x18000d2b9  lock inc cs:?g_cLockCount@@3KA; ulong g_cLockCount
0x18000d2c0  mov     [rsp+38h+arg_8], rbx
0x18000d2c5  test    rbx, rbx
0x18000d2c8  jz      short loc_18000D2D7
0x18000d2ca  lock inc dword ptr [rbx+8]
0x18000d2ce  jmp     short loc_18000D2D7
0x18000d2d0  xor     ebx, ebx
0x18000d2d2  mov     [rsp+38h+arg_8], rbx
0x18000d2d7  test    rbx, rbx
0x18000d2da  jnz     short loc_18000D2E3
0x18000d2dc  mov     edi, 8007000Eh
0x18000d2e1  jmp     short loc_18000D30F
0x18000d2e3  mov     rcx, rbx; this
0x18000d2e6  call    ?LoadIfNeeded@DockingProviders@@QEAAJXZ; DockingProviders::LoadIfNeeded(void)
0x18000d2eb  mov     edi, eax
0x18000d2ed  test    eax, eax
0x18000d2ef  jns     short loc_18000D2FB
0x18000d2f1  mov     rcx, rbx; this
0x18000d2f4  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18000d2f9  jmp     short loc_18000D30F
0x18000d2fb  mov     rcx, [rsi+40h]; this
0x18000d2ff  test    rcx, rcx
0x18000d302  jz      short loc_18000D309
0x18000d304  call    ?Release@DockingProviders@@QEAAKXZ; DockingProviders::Release(void)
0x18000d309  mov     [rsi+40h], rbx
0x18000d30d  xor     edi, edi
0x18000d30f  mov     rcx, rbp; lpCriticalSection
0x18000d312  call    cs:__imp_LeaveCriticalSection
0x18000d318  mov     eax, edi
0x18000d31a  jmp     short loc_18000D337
0x18000d31c  mov     rcx, rbp; lpCriticalSection
0x18000d31f  call    cs:__imp_LeaveCriticalSection
0x18000d325  xor     eax, eax
0x18000d327  jmp     short loc_18000D337
0x18000d329  call    ?LoadIfNeeded@DockingProviders@@QEAAJXZ; DockingProviders::LoadIfNeeded(void)
0x18000d32e  xor     ecx, ecx
0x18000d330  test    eax, eax
0x18000d332  cmovs   ecx, eax
0x18000d335  mov     eax, ecx
0x18000d337  mov     rbx, [rsp+38h+arg_10]
0x18000d33c  add     rsp, 20h
0x18000d340  pop     rdi
0x18000d341  pop     rsi
0x18000d342  pop     rbp
0x18000d343  retn
```
