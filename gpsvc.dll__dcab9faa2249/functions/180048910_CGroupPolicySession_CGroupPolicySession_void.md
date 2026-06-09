# CGroupPolicySession::~CGroupPolicySession(void)

- ea: `0x180048910`
- end: `0x180048baa`
- name: `??1CGroupPolicySession@@AEAA@XZ`
- size: `666`
- prototype: `void __fastcall(CGroupPolicySession *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800488d0`

## callees

- `0x18000a404`
- `0x180048910`
- `0x18004df78`
- `0x18007cde4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800489ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048978`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800489ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048ad4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180048b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004899f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800489f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004899f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800489f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048aff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048b6b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048a3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048a94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048aa3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048ab2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048a3c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048a94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048aa3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180048ab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004898a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800489dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004898a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800489dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048ae6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048b52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048b2c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048a23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048b2c`

## pseudocode

```c
void __fastcall CGroupPolicySession::~CGroupPolicySession(CGroupPolicySession *this)
{
  __int64 **v2; // rbx
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  void *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  void *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rcx
  struct _RTL_CRITICAL_SECTION *v14; // rcx
  struct _RTL_CRITICAL_SECTION *v15; // rcx
  struct _RTL_CRITICAL_SECTION *v16; // rbx
  void *v17; // rcx
  __int64 *i; // rbx
  _QWORD *v19; // rax
  __int64 *v20; // rax
  struct _RTL_CRITICAL_SECTION *v21; // rbx
  void *v22; // rcx

  *(_QWORD *)this = &CGroupPolicySession::`vftable'{for `IAddRefRelease'};
  *((_QWORD *)this + 1) = &CGroupPolicySession::`vftable'{for `IPolicyApplicationResultConsumer'};
  v2 = (__int64 **)*((_QWORD *)this + 20);
  if ( v2 )
  {
    for ( i = *v2; ; LocalFree((HLOCAL)i[2]) )
    {
      v19 = (_QWORD *)*((_QWORD *)this + 20);
      i = (__int64 *)*i;
      v20 = v19 ? (__int64 *)*v19 : 0LL;
      if ( i == v20 )
        break;
    }
  }
  if ( *((_QWORD *)this + 35) )
  {
    v21 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
    if ( v21 )
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
    v22 = (void *)*((_QWORD *)this + 35);
    if ( v22 )
    {
      CloseHandle(v22);
      *((_QWORD *)this + 35) = 0;
    }
    if ( v21 )
      LeaveCriticalSection(v21);
  }
  if ( *((_QWORD *)this + 36) )
  {
    v16 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
    if ( v16 )
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
    v17 = (void *)*((_QWORD *)this + 36);
    if ( v17 )
    {
      CloseHandle(v17);
      *((_QWORD *)this + 36) = 0;
    }
    if ( v16 )
      LeaveCriticalSection(v16);
  }
  if ( *((_QWORD *)this + 27) )
  {
    v3 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
    if ( v3 )
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
    v4 = (void *)*((_QWORD *)this + 27);
    if ( v4 )
    {
      CloseHandle(v4);
      *((_QWORD *)this + 27) = 0;
    }
    if ( v3 )
      LeaveCriticalSection(v3);
  }
  if ( *((_QWORD *)this + 37) )
    CGroupPolicySession::SafeCloseHandle(this, (void **)this + 37);
  if ( *((_QWORD *)this + 39) )
  {
    v5 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
    if ( v5 )
      EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 13));
    v6 = (void *)*((_QWORD *)this + 39);
    if ( v6 )
    {
      CloseHandle(v6);
      *((_QWORD *)this + 39) = 0;
    }
    if ( v5 )
      LeaveCriticalSection(v5);
  }
  v7 = (void *)*((_QWORD *)this + 44);
  if ( v7 )
  {
    STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v7);
    *((_QWORD *)this + 44) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 56);
  if ( v8 )
  {
    STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(v8);
    *((_QWORD *)this + 56) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 52);
  if ( v9 )
    *((_QWORD *)this + 52) = LocalFree(v9);
  v10 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 34);
  if ( v10 )
    DeleteCriticalSection(v10);
  v11 = (void *)*((_QWORD *)this + 24);
  *((_QWORD *)this + 23) = &COwnedToken::`vftable';
  if ( v11 )
  {
    CloseHandle(v11);
    *((_QWORD *)this + 24) = 0;
  }
  *((_QWORD *)this + 23) = &CToken::`vftable';
  v12 = (void *)*((_QWORD *)this + 20);
  if ( v12 )
    std::list<_USER_COLLECTION_CONTEXT *,STLWrap_allocator<_USER_COLLECTION_CONTEXT *>>::`scalar deleting destructor'(v12);
  v13 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 19);
  if ( v13 )
    DeleteCriticalSection(v13);
  v14 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 13);
  if ( v14 )
    DeleteCriticalSection(v14);
  v15 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 7);
  if ( v15 )
    DeleteCriticalSection(v15);
}

```

## disassembly

```asm
0x180048910  mov     [rsp+arg_0], rbx
0x180048915  mov     [rsp+arg_8], rsi
0x18004891a  push    rdi
0x18004891b  sub     rsp, 20h
0x18004891f  lea     rax, ??_7CGroupPolicySession@@6BIAddRefRelease@@@; const CGroupPolicySession::`vftable'{for `IAddRefRelease'}
0x180048926  xor     esi, esi
0x180048928  mov     [rcx], rax
0x18004892b  mov     rdi, rcx
0x18004892e  lea     rax, ??_7CGroupPolicySession@@6BIPolicyApplicationResultConsumer@@@; const CGroupPolicySession::`vftable'{for `IPolicyApplicationResultConsumer'}
0x180048935  mov     [rcx+8], rax
0x180048939  mov     rbx, [rcx+0A0h]
0x180048940  test    rbx, rbx
0x180048943  jnz     loc_180048B0A
0x180048949  cmp     [rdi+118h], rsi
0x180048950  jnz     loc_180048B34
0x180048956  cmp     [rdi+120h], rsi
0x18004895d  jnz     loc_180048AC8
0x180048963  cmp     [rdi+0D8h], rsi
0x18004896a  jz      short loc_1800489A5
0x18004896c  mov     rbx, [rdi+68h]
0x180048970  test    rbx, rbx
0x180048973  jz      short loc_18004897E
0x180048975  mov     rcx, rbx; lpCriticalSection
0x180048978  call    cs:__imp_EnterCriticalSection
0x18004897e  mov     rcx, [rdi+0D8h]; hObject
0x180048985  test    rcx, rcx
0x180048988  jz      short loc_180048997
0x18004898a  call    cs:__imp_CloseHandle
0x180048990  mov     [rdi+0D8h], rsi
0x180048997  test    rbx, rbx
0x18004899a  jz      short loc_1800489A5
0x18004899c  mov     rcx, rbx; lpCriticalSection
0x18004899f  call    cs:__imp_LeaveCriticalSection
0x1800489a5  lea     rdx, [rdi+128h]; void **
0x1800489ac  cmp     [rdx], rsi
0x1800489af  jnz     loc_180048B7B
0x1800489b5  cmp     [rdi+138h], rsi
0x1800489bc  jz      short loc_1800489F7
0x1800489be  mov     rbx, [rdi+68h]
0x1800489c2  test    rbx, rbx
0x1800489c5  jz      short loc_1800489D0
0x1800489c7  mov     rcx, rbx; lpCriticalSection
0x1800489ca  call    cs:__imp_EnterCriticalSection
0x1800489d0  mov     rcx, [rdi+138h]; hObject
0x1800489d7  test    rcx, rcx
0x1800489da  jz      short loc_1800489E9
0x1800489dc  call    cs:__imp_CloseHandle
0x1800489e2  mov     [rdi+138h], rsi
0x1800489e9  test    rbx, rbx
0x1800489ec  jz      short loc_1800489F7
0x1800489ee  mov     rcx, rbx; lpCriticalSection
0x1800489f1  call    cs:__imp_LeaveCriticalSection
0x1800489f7  mov     rcx, [rdi+160h]; Block
0x1800489fe  test    rcx, rcx
0x180048a01  jnz     loc_180048B88
0x180048a07  mov     rcx, [rdi+1C0h]; Block
0x180048a0e  test    rcx, rcx
0x180048a11  jnz     loc_180048B99
0x180048a17  mov     rcx, [rdi+1A0h]; hMem
0x180048a1e  test    rcx, rcx
0x180048a21  jz      short loc_180048A30
0x180048a23  call    cs:__imp_LocalFree
0x180048a29  mov     [rdi+1A0h], rax
0x180048a30  mov     rcx, [rdi+110h]; lpCriticalSection
0x180048a37  test    rcx, rcx
0x180048a3a  jz      short loc_180048A42
0x180048a3c  call    cs:__imp_DeleteCriticalSection
0x180048a42  mov     rcx, [rdi+0C0h]; hObject
0x180048a49  lea     rax, ??_7COwnedToken@@6B@; const COwnedToken::`vftable'
0x180048a50  mov     [rdi+0B8h], rax
0x180048a57  test    rcx, rcx
0x180048a5a  jz      short loc_180048A69
0x180048a5c  call    cs:__imp_CloseHandle
0x180048a62  mov     [rdi+0C0h], rsi
0x180048a69  lea     rax, ??_7CToken@@6B@; const CToken::`vftable'
0x180048a70  mov     [rdi+0B8h], rax
0x180048a77  mov     rcx, [rdi+0A0h]; Block
0x180048a7e  test    rcx, rcx
0x180048a81  jz      short loc_180048A88
0x180048a83  call    ??_G?$list@PEAU_USER_COLLECTION_CONTEXT@@V?$STLWrap_allocator@PEAU_USER_COLLECTION_CONTEXT@@@@@std@@QEAAPEAXI@Z; std::list<_USER_COLLECTION_CONTEXT *,STLWrap_allocator<_USER_COLLECTION_CONTEXT *>>::`scalar deleting destructor'(uint)
0x180048a88  mov     rcx, [rdi+98h]; lpCriticalSection
0x180048a8f  test    rcx, rcx
0x180048a92  jz      short loc_180048A9A
0x180048a94  call    cs:__imp_DeleteCriticalSection
0x180048a9a  mov     rcx, [rdi+68h]; lpCriticalSection
0x180048a9e  test    rcx, rcx
0x180048aa1  jz      short loc_180048AA9
0x180048aa3  call    cs:__imp_DeleteCriticalSection
0x180048aa9  mov     rcx, [rdi+38h]; lpCriticalSection
0x180048aad  test    rcx, rcx
0x180048ab0  jz      short loc_180048AB8
0x180048ab2  call    cs:__imp_DeleteCriticalSection
0x180048ab8  mov     rbx, [rsp+28h+arg_0]
0x180048abd  mov     rsi, [rsp+28h+arg_8]
0x180048ac2  add     rsp, 20h
0x180048ac6  pop     rdi
0x180048ac7  retn
0x180048ac8  mov     rbx, [rdi+68h]
0x180048acc  test    rbx, rbx
0x180048acf  jz      short loc_180048ADA
0x180048ad1  mov     rcx, rbx; lpCriticalSection
0x180048ad4  call    cs:__imp_EnterCriticalSection
0x180048ada  mov     rcx, [rdi+120h]; hObject
0x180048ae1  test    rcx, rcx
0x180048ae4  jz      short loc_180048AF3
0x180048ae6  call    cs:__imp_CloseHandle
0x180048aec  mov     [rdi+120h], rsi
0x180048af3  test    rbx, rbx
0x180048af6  jz      loc_180048963
0x180048afc  mov     rcx, rbx; lpCriticalSection
0x180048aff  call    cs:__imp_LeaveCriticalSection
0x180048b05  jmp     loc_180048963
0x180048b0a  mov     rbx, [rbx]
0x180048b0d  mov     rax, [rdi+0A0h]
0x180048b14  mov     rbx, [rbx]
0x180048b17  test    rax, rax
0x180048b1a  jz      short loc_180048B76
0x180048b1c  mov     rax, [rax]
0x180048b1f  cmp     rbx, rax
0x180048b22  jz      loc_180048949
0x180048b28  mov     rcx, [rbx+10h]; hMem
0x180048b2c  call    cs:__imp_LocalFree
0x180048b32  jmp     short loc_180048B0D
0x180048b34  mov     rbx, [rdi+68h]
0x180048b38  test    rbx, rbx
0x180048b3b  jz      short loc_180048B46
0x180048b3d  mov     rcx, rbx; lpCriticalSection
0x180048b40  call    cs:__imp_EnterCriticalSection
0x180048b46  mov     rcx, [rdi+118h]; hObject
0x180048b4d  test    rcx, rcx
0x180048b50  jz      short loc_180048B5F
0x180048b52  call    cs:__imp_CloseHandle
0x180048b58  mov     [rdi+118h], rsi
0x180048b5f  test    rbx, rbx
0x180048b62  jz      loc_180048956
0x180048b68  mov     rcx, rbx; lpCriticalSection
0x180048b6b  call    cs:__imp_LeaveCriticalSection
0x180048b71  jmp     loc_180048956
0x180048b76  mov     rax, rsi
0x180048b79  jmp     short loc_180048B1F
0x180048b7b  mov     rcx, rdi; this
0x180048b7e  call    ?SafeCloseHandle@CGroupPolicySession@@AEAAXAEAPEAX@Z; CGroupPolicySession::SafeCloseHandle(void * &)
0x180048b83  jmp     loc_1800489B5
0x180048b88  call    ??_G?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAPEAXI@Z; STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(uint)
0x180048b8d  mov     [rdi+160h], rsi
0x180048b94  jmp     loc_180048A07
0x180048b99  call    ??_G?$STLWrap_List@PEAU_NOTIFY_CALLER_INFO@@@@QEAAPEAXI@Z; STLWrap_List<_NOTIFY_CALLER_INFO *>::`scalar deleting destructor'(uint)
0x180048b9e  mov     [rdi+1C0h], rsi
0x180048ba5  jmp     loc_180048A17
```
