# CEventSystem2::Shutdown(void)

- ea: `0x180034e14`
- end: `0x180034f96`
- name: `?Shutdown@CEventSystem2@@QEAAXXZ`
- size: `386`
- prototype: `void __fastcall(CEventSystem2 *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800344fc`

## callees

- `0x180010410`
- `0x18001fde8`
- `0x180020350`
- `0x180020ab0`
- `0x1800234f4`
- `0x180034cc0`
- `0x180034e14`
- `0x180035640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034f65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180034f65`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034f53`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180034f53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034ed7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180034ed7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034efc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034efc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180034f72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180034ebd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180034ebd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180034ee8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180034ee8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180034ef2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180034ef2`

## pseudocode

```c
void __fastcall CEventSystem2::Shutdown(CEventSystem2 *this)
{
  CEventSystem2::TransientSubscriberProcessData *v2; // rdi
  _QWORD *v3; // r14
  _QWORD *v4; // r9
  __int64 v5; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 i; // rcx
  __int64 *v9; // rbp
  CEventSystem2::TransientSubscriberProcessData *v10; // rax
  CEventSystem2::TransientSubscriberProcessData *v11; // rcx
  LPCRITICAL_SECTION v12[9]; // [rsp+20h] [rbp-48h] BYREF

  *((_DWORD *)this + 100) = 1;
  CSemExclusiveES::Lock((CEventSystem2 *)((char *)this + 120));
  v2 = 0;
  v3 = (_QWORD *)((char *)this + 80);
  if ( *((_DWORD *)this + 23) )
  {
    v4 = 0;
    v5 = -1;
    do
    {
      v6 = v5;
      if ( v5 == -1 && *((_DWORD *)this + 22) )
      {
        v7 = 0;
        do
        {
          v6 = *(_QWORD *)(*v3 + 8 * v7);
          if ( v6 )
            break;
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < *((_DWORD *)this + 22) );
      }
      v5 = *(_QWORD *)v6;
      if ( !*(_QWORD *)v6 )
      {
        for ( i = (unsigned int)(*(_DWORD *)(v6 + 8) + 1);
              (unsigned int)i < *((_DWORD *)this + 22);
              i = (unsigned int)(i + 1) )
        {
          v5 = *(_QWORD *)(*v3 + 8 * i);
          if ( v5 )
            break;
        }
      }
      v9 = *(__int64 **)(v6 + 16);
      v10 = (CEventSystem2::TransientSubscriberProcessData *)v9;
      if ( v2 )
        v10 = v2;
      v2 = v10;
      if ( v4 )
        *v4 = v9;
      SetThreadpoolWait((PTP_WAIT)v9[2], 0, 0);
      v4 = v9;
    }
    while ( v5 );
  }
  CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::RemoveAll((char *)this + 80);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
  while ( v2 )
  {
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)v2 + 2), 1);
    CloseThreadpoolWait(*((PTP_WAIT *)v2 + 2));
    CloseHandle(*((HANDLE *)v2 + 1));
    v11 = v2;
    v2 = *(CEventSystem2::TransientSubscriberProcessData **)v2;
    CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(v11);
  }
  Notifier::Shutdown((CEventSystem2 *)((char *)this + 168));
  CLockES::CLockES((CLockES *)v12, (CEventSystem2 *)((char *)this + 344));
  *((_DWORD *)this + 66) = 1;
  CLockES::UnLock((CLockES *)v12);
  if ( *((_QWORD *)this + 30) )
  {
    SetEvent(*((HANDLE *)this + 40));
    WaitForSingleObject(*((HANDLE *)this + 30), 0x2710u);
    CloseHandle(*((HANDLE *)this + 30));
    *((_QWORD *)this + 30) = 0;
  }
  CLockES::~CLockES(v12);
}

```

## disassembly

```asm
0x180034e14  push    rbx
0x180034e16  push    rbp
0x180034e17  push    rsi
0x180034e18  push    rdi
0x180034e19  push    r14
0x180034e1b  push    r15
0x180034e1d  sub     rsp, 38h
0x180034e21  mov     rbx, rcx
0x180034e24  mov     dword ptr [rcx+190h], 1
0x180034e2e  add     rcx, 78h ; 'x'; this
0x180034e32  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x180034e37  xor     edi, edi
0x180034e39  lea     r14, [rbx+50h]
0x180034e3d  cmp     [r14+0Ch], edi
0x180034e41  jz      loc_180034ECB
0x180034e47  xor     r9d, r9d
0x180034e4a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180034e4e  mov     rdx, rsi
0x180034e51  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180034e55  jnz     short loc_180034E74
0x180034e57  cmp     dword ptr [r14+8], 0
0x180034e5c  jbe     short loc_180034E74
0x180034e5e  mov     r8, [r14]
0x180034e61  xor     ecx, ecx
0x180034e63  mov     rdx, [r8+rcx*8]
0x180034e67  test    rdx, rdx
0x180034e6a  jnz     short loc_180034E74
0x180034e6c  inc     ecx
0x180034e6e  cmp     ecx, [r14+8]
0x180034e72  jb      short loc_180034E63
0x180034e74  mov     rsi, [rdx]
0x180034e77  test    rsi, rsi
0x180034e7a  jnz     short loc_180034E9B
0x180034e7c  mov     ecx, [rdx+8]
0x180034e7f  inc     ecx
0x180034e81  cmp     ecx, [r14+8]
0x180034e85  jnb     short loc_180034E9B
0x180034e87  mov     r8, [r14]
0x180034e8a  mov     rsi, [r8+rcx*8]
0x180034e8e  test    rsi, rsi
0x180034e91  jnz     short loc_180034E9B
0x180034e93  inc     ecx
0x180034e95  cmp     ecx, [r14+8]
0x180034e99  jb      short loc_180034E8A
0x180034e9b  mov     rbp, [rdx+10h]
0x180034e9f  test    rdi, rdi
0x180034ea2  mov     rax, rbp
0x180034ea5  cmovnz  rax, rdi
0x180034ea9  mov     rdi, rax
0x180034eac  test    r9, r9
0x180034eaf  jz      short loc_180034EB4
0x180034eb1  mov     [r9], rbp
0x180034eb4  mov     rcx, [rbp+10h]; pwa
0x180034eb8  xor     r8d, r8d; pftTimeout
0x180034ebb  xor     edx, edx; h
0x180034ebd  call    cs:__imp_SetThreadpoolWait
0x180034ec3  mov     r9, rbp
0x180034ec6  test    rsi, rsi
0x180034ec9  jnz     short loc_180034E4E
0x180034ecb  mov     rcx, r14
0x180034ece  call    ?RemoveAll@?$CMap@U_GUID@@AEBU1@PEAUElement@Notifier@@AEAPEAU23@@@QEAAXXZ; CMap<_GUID,_GUID const &,Notifier::Element *,Notifier::Element * &>::RemoveAll(void)
0x180034ed3  lea     rcx, [rbx+78h]; lpCriticalSection
0x180034ed7  call    cs:__imp_LeaveCriticalSection
0x180034edd  jmp     short loc_180034F0D
0x180034edf  mov     rcx, [rdi+10h]; pwa
0x180034ee3  mov     edx, 1; fCancelPendingCallbacks
0x180034ee8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180034eee  mov     rcx, [rdi+10h]; pwa
0x180034ef2  call    cs:__imp_CloseThreadpoolWait
0x180034ef8  mov     rcx, [rdi+8]; hObject
0x180034efc  call    cs:__imp_CloseHandle
0x180034f02  mov     rcx, rdi; this
0x180034f05  mov     rdi, [rdi]
0x180034f08  call    ??_GTransientSubscriberProcessData@CEventSystem2@@QEAAPEAXI@Z; CEventSystem2::TransientSubscriberProcessData::`scalar deleting destructor'(uint)
0x180034f0d  test    rdi, rdi
0x180034f10  jnz     short loc_180034EDF
0x180034f12  lea     rcx, [rbx+0A8h]; this
0x180034f19  call    ?Shutdown@Notifier@@QEAAXXZ; Notifier::Shutdown(void)
0x180034f1e  lea     rdx, [rbx+158h]; struct CSemExclusiveES *
0x180034f25  lea     rcx, [rsp+68h+var_48]; this
0x180034f2a  call    ??0CLockES@@QEAA@PEAVCSemExclusiveES@@@Z; CLockES::CLockES(CSemExclusiveES *)
0x180034f2f  lea     rcx, [rsp+68h+var_48]; this
0x180034f34  mov     dword ptr [rbx+108h], 1
0x180034f3e  call    ?UnLock@CLockES@@QEAAXXZ; CLockES::UnLock(void)
0x180034f43  cmp     [rbx+0F0h], rdi
0x180034f4a  jz      short loc_180034F7F
0x180034f4c  mov     rcx, [rbx+140h]; hEvent
0x180034f53  call    cs:__imp_SetEvent
0x180034f59  mov     rcx, [rbx+0F0h]; hHandle
0x180034f60  mov     edx, 2710h; dwMilliseconds
0x180034f65  call    cs:__imp_WaitForSingleObject
0x180034f6b  mov     rcx, [rbx+0F0h]; hObject
0x180034f72  call    cs:__imp_CloseHandle
0x180034f78  mov     [rbx+0F0h], rdi
0x180034f7f  lea     rcx, [rsp+68h+var_48]; this
0x180034f84  call    ??1CLockES@@QEAA@XZ; CLockES::~CLockES(void)
0x180034f89  add     rsp, 38h
0x180034f8d  pop     r15
0x180034f8f  pop     r14
0x180034f91  pop     rdi
0x180034f92  pop     rsi
0x180034f93  pop     rbp
0x180034f94  pop     rbx
0x180034f95  retn
```
