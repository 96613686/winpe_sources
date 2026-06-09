# CPipeVCMgr::InitializeInstance(void)

- ea: `0x180075520`
- end: `0x180075792`
- name: `?InitializeInstance@CPipeVCMgr@@UEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(CPipeVCMgr *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800071c0`
- `0x1800071f0`
- `0x1800091a8`
- `0x18000bef4`
- `0x18002e600`
- `0x180075520`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180075626`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180075626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007553e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007553e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800755c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075635`

## string_xrefs

- `0x18007560e`: `m_FirstReadWorkItemListLock.Initialize`
- `0x18007572a`: `Failed to create the manager thread`
- `0x18007567f`: `Failed CreateEvent call for m_hFirstReadWorkItemEvent Event`
- `0x180075777`: `Failed to start the manager thread`

## pseudocode

```c
__int64 __fastcall CPipeVCMgr::InitializeInstance(CPipeVCMgr *this)
{
  signed int LastError; // eax
  signed int v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  signed int v7; // eax
  HANDLE EventW; // rax
  signed int v9; // eax
  __int64 *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rsi
  __int64 v13; // r8
  signed int v15; // [rsp+28h] [rbp-30h]

  if ( (unsigned int)CTSCriticalSection::Initialize((CPipeVCMgr *)((char *)this + 104)) )
    goto LABEL_13;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
LABEL_13:
    if ( (unsigned int)CTSCriticalSection::Initialize((CPipeVCMgr *)((char *)this + 72)) )
      goto LABEL_18;
    v7 = GetLastError();
    v3 = v7;
    if ( v7 > 0 )
      v3 = (unsigned __int16)v7 | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_18:
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 8) = EventW;
      if ( EventW )
        goto LABEL_26;
      v9 = GetLastError();
      v3 = v9;
      if ( v9 > 0 )
        v3 = (unsigned __int16)v9 | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_26:
        v10 = (__int64 *)((char *)this + 16);
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 144LL))(*((_QWORD *)this + 1));
        if ( v12 != *((_QWORD *)this + 2) )
        {
          TCntPtr<IRdpSQMLogger>::SafeRelease((char *)this + 16, v11, v13);
          *v10 = v12;
          TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 16);
        }
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 8LL))(*((_QWORD *)this - 2));
        v3 = (*(__int64 (__fastcall **)(__int64, void (__fastcall *)(void *), char *, char *))(*(_QWORD *)*v10 + 56LL))(
               *v10,
               CPipeVCMgr::STATIC_PipeVCMgrThreadProc,
               (char *)this - 48,
               (char *)this + 24);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 3) + 32LL))(*((_QWORD *)this + 3), 0);
          if ( v3 >= 0 )
          {
            *((_DWORD *)this - 5) |= 2u;
            return (unsigned int)v3;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v5 = 50;
            v6 = "Failed to start the manager thread";
            goto LABEL_9;
          }
        }
        else
        {
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this - 2) + 16LL))(*((_QWORD *)this - 2));
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v5 = 49;
            v6 = "Failed to create the manager thread";
            goto LABEL_9;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v5 = 48;
        v6 = "Failed CreateEvent call for m_hFirstReadWorkItemEvent Event";
        goto LABEL_9;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v5 = 47;
      v6 = "m_FirstReadWorkItemListLock.Initialize";
      goto LABEL_9;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 46;
    v6 = "m_objLock.Initialize";
LABEL_9:
    v15 = v3;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)&WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6,
      v15);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180075520  push    rbx
0x180075522  push    rbp
0x180075523  push    rsi
0x180075524  push    rdi
0x180075525  sub     rsp, 38h
0x180075529  mov     rdi, rcx
0x18007552c  add     rcx, 68h ; 'h'; this
0x180075530  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x180075535  mov     esi, 80070000h
0x18007553a  test    eax, eax
0x18007553c  jnz     short loc_1800755B7
0x18007553e  call    cs:__imp_GetLastError
0x180075544  mov     ebx, eax
0x180075546  test    eax, eax
0x180075548  jle     short loc_18007554F
0x18007554a  movzx   ebx, ax
0x18007554d  or      ebx, esi
0x18007554f  test    ebx, ebx
0x180075551  jns     short loc_1800755B7
0x180075553  mov     rcx, cs:WPP_GLOBAL_Control
0x18007555a  lea     rax, WPP_GLOBAL_Control
0x180075561  cmp     rcx, rax
0x180075564  jz      loc_180075787
0x18007556a  test    byte ptr [rcx+1Ch], 8
0x18007556e  jz      loc_180075787
0x180075574  cmp     byte ptr [rcx+19h], 2
0x180075578  jb      loc_180075787
0x18007557e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075583  mov     edx, 2Eh ; '.'
0x180075588  lea     rcx, aMObjlockInitia; "m_objLock.Initialize"
0x18007558f  mov     [rsp+58h+var_30], ebx
0x180075593  lea     r8, WPP_a8eb692f3fb033f28c886fd1ceeaf1a3_Traceguids
0x18007559a  mov     [rsp+58h+var_38], rcx
0x18007559f  mov     r9d, eax
0x1800755a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800755a9  mov     rcx, [rcx+10h]
0x1800755ad  call    WPP_SF_DsD
0x1800755b2  jmp     loc_180075787
0x1800755b7  lea     rcx, [rdi+48h]; this
0x1800755bb  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800755c0  test    eax, eax
0x1800755c2  jnz     short loc_18007561A
0x1800755c4  call    cs:__imp_GetLastError
0x1800755ca  mov     ebx, eax
0x1800755cc  test    eax, eax
0x1800755ce  jle     short loc_1800755D5
0x1800755d0  movzx   ebx, ax
0x1800755d3  or      ebx, esi
0x1800755d5  test    ebx, ebx
0x1800755d7  jns     short loc_18007561A
0x1800755d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800755e0  lea     rax, WPP_GLOBAL_Control
0x1800755e7  cmp     rcx, rax
0x1800755ea  jz      loc_180075787
0x1800755f0  test    byte ptr [rcx+1Ch], 8
0x1800755f4  jz      loc_180075787
0x1800755fa  cmp     byte ptr [rcx+19h], 2
0x1800755fe  jb      loc_180075787
0x180075604  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075609  mov     edx, 2Fh ; '/'
0x18007560e  lea     rcx, aMFirstreadwork_0; "m_FirstReadWorkItemListLock.Initialize"
0x180075615  jmp     loc_18007558F
0x18007561a  xor     r9d, r9d; lpName
0x18007561d  xor     r8d, r8d; bInitialState
0x180075620  xor     ecx, ecx; lpEventAttributes
0x180075622  lea     edx, [r9+1]; bManualReset
0x180075626  call    cs:__imp_CreateEventW
0x18007562c  mov     [rdi+40h], rax
0x180075630  test    rax, rax
0x180075633  jnz     short loc_18007568B
0x180075635  call    cs:__imp_GetLastError
0x18007563b  mov     ebx, eax
0x18007563d  test    eax, eax
0x18007563f  jle     short loc_180075646
0x180075641  movzx   ebx, ax
0x180075644  or      ebx, esi
0x180075646  test    ebx, ebx
0x180075648  jns     short loc_18007568B
0x18007564a  mov     rcx, cs:WPP_GLOBAL_Control
0x180075651  lea     rax, WPP_GLOBAL_Control
0x180075658  cmp     rcx, rax
0x18007565b  jz      loc_180075787
0x180075661  test    byte ptr [rcx+1Ch], 8
0x180075665  jz      loc_180075787
0x18007566b  cmp     byte ptr [rcx+19h], 2
0x18007566f  jb      loc_180075787
0x180075675  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007567a  mov     edx, 30h ; '0'
0x18007567f  lea     rcx, aFailedCreateev_0; "Failed CreateEvent call for m_hFirstRea"...
0x180075686  jmp     loc_18007558F
0x18007568b  mov     rcx, [rdi+8]
0x18007568f  mov     rax, [rcx]
0x180075692  mov     rax, [rax+90h]
0x180075699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007569e  lea     rbx, [rdi+10h]
0x1800756a2  mov     rsi, rax
0x1800756a5  cmp     rax, [rbx]
0x1800756a8  jz      short loc_1800756BD
0x1800756aa  mov     rcx, rbx
0x1800756ad  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x1800756b2  mov     rcx, rbx
0x1800756b5  mov     [rbx], rsi
0x1800756b8  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800756bd  mov     rcx, [rdi-10h]
0x1800756c1  mov     rax, [rcx]
0x1800756c4  mov     rax, [rax+8]
0x1800756c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756cd  mov     rcx, [rbx]
0x1800756d0  lea     r9, [rdi+18h]
0x1800756d4  lea     r8, [rdi-30h]
0x1800756d8  lea     rdx, ?STATIC_PipeVCMgrThreadProc@CPipeVCMgr@@CAXPEAX@Z; CPipeVCMgr::STATIC_PipeVCMgrThreadProc(void *)
0x1800756df  mov     rax, [rcx]
0x1800756e2  mov     rax, [rax+38h]
0x1800756e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756eb  mov     ebx, eax
0x1800756ed  test    eax, eax
0x1800756ef  jns     short loc_180075736
0x1800756f1  mov     rcx, [rdi-10h]
0x1800756f5  mov     rdx, [rcx]
0x1800756f8  mov     rax, [rdx+10h]
0x1800756fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075701  mov     rcx, cs:WPP_GLOBAL_Control
0x180075708  lea     rax, WPP_GLOBAL_Control
0x18007570f  cmp     rcx, rax
0x180075712  jz      short loc_180075787
0x180075714  test    byte ptr [rcx+1Ch], 8
0x180075718  jz      short loc_180075787
0x18007571a  cmp     byte ptr [rcx+19h], 2
0x18007571e  jb      short loc_180075787
0x180075720  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075725  mov     edx, 31h ; '1'
0x18007572a  lea     rcx, aFailedToCreate_3; "Failed to create the manager thread"
0x180075731  jmp     loc_18007558F
0x180075736  mov     rcx, [rdi+18h]
0x18007573a  xor     edx, edx
0x18007573c  mov     rax, [rcx]
0x18007573f  mov     rax, [rax+20h]
0x180075743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075748  mov     ebx, eax
0x18007574a  test    eax, eax
0x18007574c  jns     short loc_180075783
0x18007574e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075755  lea     rax, WPP_GLOBAL_Control
0x18007575c  cmp     rcx, rax
0x18007575f  jz      short loc_180075787
0x180075761  test    byte ptr [rcx+1Ch], 8
0x180075765  jz      short loc_180075787
0x180075767  cmp     byte ptr [rcx+19h], 2
0x18007576b  jb      short loc_180075787
0x18007576d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180075772  mov     edx, 32h ; '2'
0x180075777  lea     rcx, aFailedToStartT_0; "Failed to start the manager thread"
0x18007577e  jmp     loc_18007558F
0x180075783  or      dword ptr [rdi-14h], 2
0x180075787  mov     eax, ebx
0x180075789  add     rsp, 38h
0x18007578d  pop     rdi
0x18007578e  pop     rsi
0x18007578f  pop     rbp
0x180075790  pop     rbx
0x180075791  retn
```
