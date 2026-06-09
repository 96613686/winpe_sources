# CFontFolderCache::_GetCachedFontCollection(ushort const *,CFontCollection * *)

- ea: `0x18001b410`
- end: `0x18001b50b`
- name: `?_GetCachedFontCollection@CFontFolderCache@@AEAAJPEBGPEAPEAVCFontCollection@@@Z`
- size: `251`
- prototype: `int(CFontFolderCache *__hidden this, const unsigned __int16 *, struct CFontCollection **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001b34c`

## callees

- `0x18001037c`
- `0x18001b410`
- `0x18001b6ac`
- `0x18001b80c`
- `0x18001b8a4`
- `0x18001be48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b4c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b4c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b4dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b447`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b447`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b45e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b45e`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b4a2`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18001b4a2`

## pseudocode

```c
__int64 __fastcall CFontFolderCache::_GetCachedFontCollection(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        WCHAR **a3)
{
  unsigned int v6; // ebp
  int v7; // edi
  int v8; // r12d
  WCHAR *Ptr; // rsi
  int v10; // eax
  RTL_SRWLOCK *v11; // rcx
  int v12; // ebx
  struct CFontCollectionBuilder *Instance; // rax

  v6 = -2147467259;
  v7 = 0;
  v8 = *(_DWORD *)this->Ptr;
  while ( v7 < v8 )
  {
    AcquireSRWLockShared(this + 1);
    Ptr = (WCHAR *)IsolationAwareDPA_GetPtr(this->Ptr, v7);
    ReleaseSRWLockShared(this + 1);
    if ( Ptr )
    {
      if ( (unsigned int)CFontCollection::IsStale((CFontCollection *)Ptr) )
      {
        if ( this->Ptr )
        {
          AcquireSRWLockExclusive(this + 1);
          IsolationAwareDPA_EnumCallback(this->Ptr);
          v10 = IsolationAwareDPA_DeleteAllPtrs(this->Ptr);
          v11 = this + 1;
          v12 = v10;
          ReleaseSRWLockExclusive(v11);
          if ( v12 )
          {
            Instance = CFontCollectionBuilder::s_GetInstance();
            if ( Instance )
              *((_DWORD *)Instance + 2) = 1;
          }
        }
        return v6;
      }
      if ( CompareStringEx(0, 0x10u, a2, -1, Ptr + 4, -1, 0, 0, 0) == 2 )
      {
        *a3 = Ptr;
        return 0;
      }
    }
    ++v7;
  }
  return v6;
}

```

## disassembly

```asm
0x18001b410  push    rbx
0x18001b412  push    rbp
0x18001b413  push    rsi
0x18001b414  push    rdi
0x18001b415  push    r12
0x18001b417  push    r13
0x18001b419  push    r14
0x18001b41b  push    r15
0x18001b41d  sub     rsp, 58h
0x18001b421  mov     rax, [rcx]
0x18001b424  mov     r15, r8
0x18001b427  mov     r13, rdx
0x18001b42a  mov     rbx, rcx
0x18001b42d  mov     ebp, 80004005h
0x18001b432  xor     edi, edi
0x18001b434  mov     r12d, [rax]
0x18001b437  cmp     edi, r12d
0x18001b43a  jge     loc_18001B4F8
0x18001b440  lea     r14, [rbx+8]
0x18001b444  mov     rcx, r14; SRWLock
0x18001b447  call    cs:__imp_AcquireSRWLockShared
0x18001b44d  mov     rcx, [rbx]
0x18001b450  movsxd  rdx, edi
0x18001b453  call    IsolationAwareDPA_GetPtr
0x18001b458  mov     rcx, r14; SRWLock
0x18001b45b  mov     rsi, rax
0x18001b45e  call    cs:__imp_ReleaseSRWLockShared
0x18001b464  test    rsi, rsi
0x18001b467  jz      short loc_18001B4AD
0x18001b469  mov     rcx, rsi; this
0x18001b46c  call    ?IsStale@CFontCollection@@QEAAHXZ; CFontCollection::IsStale(void)
0x18001b471  test    eax, eax
0x18001b473  jnz     short loc_18001B4B9
0x18001b475  or      ecx, 0FFFFFFFFh
0x18001b478  lea     rax, [rsi+8]
0x18001b47c  xor     r14d, r14d
0x18001b47f  mov     r9d, ecx; cchCount1
0x18001b482  mov     [rsp+98h+lParam], r14; lParam
0x18001b487  mov     r8, r13; lpString1
0x18001b48a  mov     [rsp+98h+lpReserved], r14; lpReserved
0x18001b48f  mov     [rsp+98h+lpVersionInformation], r14; lpVersionInformation
0x18001b494  lea     edx, [rcx+11h]; dwCmpFlags
0x18001b497  mov     [rsp+98h+cchCount2], ecx; cchCount2
0x18001b49b  xor     ecx, ecx; lpLocaleName
0x18001b49d  mov     [rsp+98h+lpString2], rax; lpString2
0x18001b4a2  call    cs:__imp_CompareStringEx
0x18001b4a8  cmp     eax, 2
0x18001b4ab  jz      short loc_18001B4B1
0x18001b4ad  inc     edi
0x18001b4af  jmp     short loc_18001B437
0x18001b4b1  mov     [r15], rsi
0x18001b4b4  mov     ebp, r14d
0x18001b4b7  jmp     short loc_18001B4F8
0x18001b4b9  cmp     qword ptr [rbx], 0
0x18001b4bd  jz      short loc_18001B4F8
0x18001b4bf  mov     rcx, r14; SRWLock
0x18001b4c2  call    cs:__imp_AcquireSRWLockExclusive
0x18001b4c8  mov     rcx, [rbx]
0x18001b4cb  call    IsolationAwareDPA_EnumCallback
0x18001b4d0  mov     rcx, [rbx]
0x18001b4d3  call    IsolationAwareDPA_DeleteAllPtrs
0x18001b4d8  mov     rcx, r14; SRWLock
0x18001b4db  mov     ebx, eax
0x18001b4dd  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b4e3  test    ebx, ebx
0x18001b4e5  jz      short loc_18001B4F8
0x18001b4e7  call    ?s_GetInstance@CFontCollectionBuilder@@SAPEAV1@XZ; CFontCollectionBuilder::s_GetInstance(void)
0x18001b4ec  test    rax, rax
0x18001b4ef  jz      short loc_18001B4F8
0x18001b4f1  mov     dword ptr [rax+8], 1
0x18001b4f8  mov     eax, ebp
0x18001b4fa  add     rsp, 58h
0x18001b4fe  pop     r15
0x18001b500  pop     r14
0x18001b502  pop     r13
0x18001b504  pop     r12
0x18001b506  pop     rdi
0x18001b507  pop     rsi
0x18001b508  pop     rbp
0x18001b509  pop     rbx
0x18001b50a  retn
```
