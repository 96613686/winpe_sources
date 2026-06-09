# CPartitionCache::Create(void)

- ea: `0x180052d08`
- end: `0x180052e11`
- name: `?Create@CPartitionCache@@SAPEAV1@XZ`
- size: `265`
- prototype: `struct CPartitionCache *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004c7ac`
- `0x18004d20c`

## callees

- `0x180052d08`
- `0x180052e18`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180052da8`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180052da8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052dfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180052dfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052d2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052d2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052db7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052db7`

## pseudocode

```c
struct CPartitionCache *CPartitionCache::Create(void)
{
  _QWORD *v0; // rax
  CPartitionCache *v1; // rbx
  HANDLE v2; // rax
  signed int LastError; // eax
  bool v4; // sf

  EnterCriticalSection(&stru_180072280);
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
      if ( CPartitionCache::CreateCache(v1) < 0 )
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
  LeaveCriticalSection(&stru_180072280);
  return CPartitionCache::sm_singletonPartitionCache;
}

```

## disassembly

```asm
0x180052d08  push    rbx
0x180052d0a  sub     rsp, 20h
0x180052d0e  lea     rcx, stru_180072280; lpCriticalSection
0x180052d15  call    cs:__imp_EnterCriticalSection
0x180052d1b  cmp     cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA, 0; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180052d23  jnz     loc_180052DF7
0x180052d29  mov     ecx, 50h ; 'P'; cb
0x180052d2e  call    cs:__imp_CoTaskMemAlloc
0x180052d34  mov     [rsp+28h+arg_0], rax
0x180052d39  mov     rbx, rax
0x180052d3c  test    rax, rax
0x180052d3f  jz      loc_180052DEE
0x180052d45  mov     dword ptr [rbx+8], 0DADADADAh
0x180052d4c  lea     rax, ??_7CPartitionCache@@6B@; const CPartitionCache::`vftable'
0x180052d53  mov     [rbx], rax
0x180052d56  mov     qword ptr [rbx+0Ch], 0
0x180052d5e  mov     qword ptr [rbx+18h], 0
0x180052d66  mov     qword ptr [rbx+20h], 0
0x180052d6e  mov     qword ptr [rbx+28h], 0
0x180052d76  mov     qword ptr [rbx+30h], 0
0x180052d7e  mov     qword ptr [rbx+38h], 0
0x180052d86  mov     qword ptr [rbx+40h], 0
0x180052d8e  mov     dword ptr [rbx+48h], 4
0x180052d95  test    rbx, rbx
0x180052d98  jz      short loc_180052DF0
0x180052d9a  lea     r8, aGlobalA3bd3259; "Global\\{A3BD3259-3E4F-428a-84C8-F0463A"...
0x180052da1  xor     edx, edx; bInheritHandle
0x180052da3  mov     ecx, 100000h; dwDesiredAccess
0x180052da8  call    cs:__imp_OpenMutexW
0x180052dae  mov     [rbx+20h], rax
0x180052db2  test    rax, rax
0x180052db5  jnz     short loc_180052DCD
0x180052db7  call    cs:__imp_GetLastError
0x180052dbd  test    eax, eax
0x180052dbf  jle     short loc_180052DCB
0x180052dc1  movzx   eax, ax
0x180052dc4  or      eax, 80070000h
0x180052dc9  test    eax, eax
0x180052dcb  js      short loc_180052DD9
0x180052dcd  mov     rcx, rbx; this
0x180052dd0  call    ?CreateCache@CPartitionCache@@AEAAJXZ; CPartitionCache::CreateCache(void)
0x180052dd5  test    eax, eax
0x180052dd7  jns     short loc_180052DF0
0x180052dd9  mov     rax, [rbx]
0x180052ddc  mov     edx, 1
0x180052de1  mov     rcx, rbx
0x180052de4  mov     rax, [rax]
0x180052de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dec  jmp     short loc_180052DF7
0x180052dee  xor     ebx, ebx
0x180052df0  mov     cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA, rbx; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180052df7  lea     rcx, stru_180072280; lpCriticalSection
0x180052dfe  call    cs:__imp_LeaveCriticalSection
0x180052e04  mov     rax, cs:?sm_singletonPartitionCache@CPartitionCache@@0PEAV1@EA; CPartitionCache * CPartitionCache::sm_singletonPartitionCache
0x180052e0b  add     rsp, 20h
0x180052e0f  pop     rbx
0x180052e10  retn
```
