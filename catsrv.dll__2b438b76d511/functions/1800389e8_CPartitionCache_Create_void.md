# CPartitionCache::Create(void)

- ea: `0x1800389e8`
- end: `0x180038af1`
- name: `?Create@CPartitionCache@@SAPEAV1@XZ`
- size: `265`
- prototype: `struct CPartitionCache *(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029510`

## callees

- `0x1800389e8`
- `0x180038af8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ade`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ade`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800389f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800389f5`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180038a88`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180038a88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038a0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038a0e`

## pseudocode

```c
struct CPartitionCache *CPartitionCache::Create(void)
{
  _QWORD *v0; // rax
  CPartitionCache *v1; // rbx
  HANDLE v2; // rax
  signed int LastError; // eax
  bool v4; // sf

  EnterCriticalSection(&stru_1800732F8);
  if ( !CPartitionCache::sm_singletonPartitionCache )
  {
    v0 = CoTaskMemAlloc(0x50u);
    v1 = (CPartitionCache *)v0;
    if ( v0 )
    {
      *((_DWORD *)v0 + 2) = -623191334;
      *v0 = &CPartitionCache::`vftable';
      *(_QWORD *)((char *)v0 + 12) = 0;
      v0[3] = 0;
      v0[4] = 0;
      v0[5] = 0;
      v0[6] = 0;
      v0[7] = 0;
      v0[8] = 0;
      *((_DWORD *)v0 + 18) = 4;
      v2 = OpenMutexW(0x100000u, 0, L"Global\\{A3BD3259-3E4F-428a-84C8-F0463A9D3EB5}");
      *((_QWORD *)v1 + 4) = v2;
      if ( !v2 )
      {
        LastError = GetLastError();
        v4 = LastError < 0;
        if ( LastError > 0 )
          v4 = 1;
        if ( v4 )
          goto LABEL_8;
      }
      if ( (int)CPartitionCache::CreateCache(v1) < 0 )
      {
LABEL_8:
        (**(void (__fastcall ***)(CPartitionCache *, __int64))v1)(v1, 1);
        goto LABEL_11;
      }
    }
    else
    {
      v1 = 0;
    }
    CPartitionCache::sm_singletonPartitionCache = v1;
  }
LABEL_11:
  LeaveCriticalSection(&stru_1800732F8);
  return CPartitionCache::sm_singletonPartitionCache;
}

```

## disassembly

```asm
0x1800389e8  push    rbx
0x1800389ea  sub     rsp, 20h
0x1800389ee  lea     rcx, stru_1800732F8; lpCriticalSection
0x1800389f5  call    cs:__imp_EnterCriticalSection
0x1800389fb  cmp     cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA, 0; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180038a03  jnz     loc_180038AD7
0x180038a09  mov     ecx, 50h ; 'P'; cb
0x180038a0e  call    cs:__imp_CoTaskMemAlloc
0x180038a14  mov     [rsp+28h+arg_0], rax
0x180038a19  mov     rbx, rax
0x180038a1c  test    rax, rax
0x180038a1f  jz      loc_180038ACE
0x180038a25  mov     dword ptr [rbx+8], 0DADADADAh
0x180038a2c  lea     rax, ??_7CPartitionCache@@6B@; const CPartitionCache::`vftable'
0x180038a33  mov     [rbx], rax
0x180038a36  mov     qword ptr [rbx+0Ch], 0
0x180038a3e  mov     qword ptr [rbx+18h], 0
0x180038a46  mov     qword ptr [rbx+20h], 0
0x180038a4e  mov     qword ptr [rbx+28h], 0
0x180038a56  mov     qword ptr [rbx+30h], 0
0x180038a5e  mov     qword ptr [rbx+38h], 0
0x180038a66  mov     qword ptr [rbx+40h], 0
0x180038a6e  mov     dword ptr [rbx+48h], 4
0x180038a75  test    rbx, rbx
0x180038a78  jz      short loc_180038AD0
0x180038a7a  lea     r8, aGlobalA3bd3259; "Global\\{A3BD3259-3E4F-428a-84C8-F0463A"...
0x180038a81  xor     edx, edx; bInheritHandle
0x180038a83  mov     ecx, 100000h; dwDesiredAccess
0x180038a88  call    cs:__imp_OpenMutexW
0x180038a8e  mov     [rbx+20h], rax
0x180038a92  test    rax, rax
0x180038a95  jnz     short loc_180038AAD
0x180038a97  call    cs:__imp_GetLastError
0x180038a9d  test    eax, eax
0x180038a9f  jle     short loc_180038AAB
0x180038aa1  movzx   eax, ax
0x180038aa4  or      eax, 80070000h
0x180038aa9  test    eax, eax
0x180038aab  js      short loc_180038AB9
0x180038aad  mov     rcx, rbx; this
0x180038ab0  call    ?CreateCache@CPartitionCache@@AEAAJXZ; CPartitionCache::CreateCache(void)
0x180038ab5  test    eax, eax
0x180038ab7  jns     short loc_180038AD0
0x180038ab9  mov     rax, [rbx]
0x180038abc  mov     edx, 1
0x180038ac1  mov     rcx, rbx
0x180038ac4  mov     rax, [rax]
0x180038ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038acc  jmp     short loc_180038AD7
0x180038ace  xor     ebx, ebx
0x180038ad0  mov     cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA, rbx; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180038ad7  lea     rcx, stru_1800732F8; lpCriticalSection
0x180038ade  call    cs:__imp_LeaveCriticalSection
0x180038ae4  mov     rax, cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180038aeb  add     rsp, 20h
0x180038aef  pop     rbx
0x180038af0  retn
```
