# NetworkDiagnosticsEngine::Resolve(DiagnosticsClient *)

- ea: `0x18001bb00`
- end: `0x18001bf76`
- name: `?Resolve@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(NetworkDiagnosticsEngine *__hidden this, struct DiagnosticsClient *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004940`

## callees

- `0x18000506c`
- `0x180007f1c`
- `0x18000844c`
- `0x180008db8`
- `0x18000c42c`
- `0x18000e034`
- `0x180010214`
- `0x180017f74`
- `0x18001bb00`
- `0x18001bfc0`
- `0x1800239b0`
- `0x180023ac8`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x18001bea8`
- `KERNEL32!WaitForSingleObject` at `0x18001bea8`
- `wdi!WdiAddParameter` at `0x18001be40`
- `wdi!WdiAddParameter` at `0x18001be40`

## string_xrefs

- `0x18001bde8`: `Failed while trying to find the selected repair.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NetworkDiagnosticsEngine::Resolve(NetworkDiagnosticsEngine *this, struct DiagnosticsClient *a2)
{
  NetworkDiagnosticsEngine *v3; // rsi
  int v4; // ebx
  __int64 v5; // rax
  __int64 v6; // rdi
  __int16 *v7; // r12
  __int64 v8; // rbx
  CTraceController *v9; // r13
  struct _FILETIME *TickCount; // rax
  __int64 v11; // rcx
  unsigned int v12; // r13d
  __int64 v13; // rdx
  __int64 v14; // r12
  _QWORD *v15; // rbx
  struct _FILETIME v16; // rcx
  int v17; // eax
  __int16 v19; // [rsp+30h] [rbp-59h] BYREF
  int v20; // [rsp+38h] [rbp-51h] BYREF
  int v21; // [rsp+3Ch] [rbp-4Dh] BYREF
  unsigned int v22; // [rsp+40h] [rbp-49h] BYREF
  struct _FILETIME v23; // [rsp+48h] [rbp-41h] BYREF
  __int64 v24; // [rsp+50h] [rbp-39h] BYREF
  void *v25[4]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v26; // [rsp+78h] [rbp-11h] BYREF
  __int128 v27; // [rsp+88h] [rbp-1h] BYREF

  v3 = qword_180041BB8;
  if ( a2 )
  {
    v26 = 0;
    v4 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, __int128 *))(*(_QWORD *)a2 + 72LL))(a2, &v26);
    if ( v4 >= 0 )
    {
      v5 = std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(
             (char *)v3 + 8,
             &v23,
             &v26);
      if ( *(_QWORD *)v5 == *((_QWORD *)v3 + 1) || (v6 = *(_QWORD *)(*(_QWORD *)v5 + 48LL)) == 0 )
      {
        v4 = -2147024809;
        if ( *(_QWORD *)v3 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 48LL))(*(_QWORD *)v3, 1, 2147942487LL);
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, 2147942487LL, 2);
        }
      }
      else
      {
        v7 = (__int16 *)(v6 + 92);
        v25[2] = (void *)(v6 + 92);
        v25[3] = a2;
        v8 = 0;
        v24 = 0;
        v9 = (CTraceController *)(v6 + 128);
        if ( (int)CTraceController::Resume((CTraceController *)(v6 + 128)) >= 0 )
          v8 = v6 + 128;
        v24 = v8;
        _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 24), 5, 4);
        if ( *(_QWORD *)(v6 + 100) && *(_QWORD *)(v6 + 120) )
        {
          TickCount = ATL::CFileTime::GetTickCount(&v23);
          (*(void (__fastcall **)(_QWORD, unsigned __int64))(**(_QWORD **)(v6 + 120) + 120LL))(
            *(_QWORD *)(v6 + 120),
            (*(_QWORD *)TickCount - (unsigned __int64)*(unsigned int *)(v6 + 100)) / 0x989680);
          *(_QWORD *)(v6 + 100) = 0;
        }
        if ( *v7 == 1 )
        {
          v11 = *(_QWORD *)(v6 + 32);
          if ( (*(_QWORD *)(v6 + 40) - v11) >> 3 )
          {
            v12 = 0;
            v13 = 0;
            do
            {
              v23 = *(struct _FILETIME *)(v11 + 8 * v13);
              std::list<ProblemNode *>::list<ProblemNode *>(v25);
              std::list<ProblemNode *>::_Insert<ProblemNode * const &>(v25, v25[0], &v23);
              while ( v25[1] )
              {
                v14 = *(_QWORD *)(*(_QWORD *)v25[0] + 16LL);
                std::list<ProblemNode *>::pop_front(v25);
                if ( v14 )
                {
                  if ( *(_QWORD *)(*(_QWORD *)v14 + 248LL) )
                    *(_QWORD *)(*(_QWORD *)v14 + 248LL) = 0;
                  if ( *(_DWORD *)(*(_QWORD *)v14 + 244LL) )
                    *(_DWORD *)(*(_QWORD *)v14 + 244LL) = 0;
                  v15 = **(_QWORD ***)(v14 + 64);
                  while ( v15 != *(_QWORD **)(v14 + 64) )
                  {
                    v16 = (struct _FILETIME)v15[2];
                    v15 = (_QWORD *)*v15;
                    v23 = v16;
                    if ( *(_QWORD *)&v16 && *(_DWORD *)(*(_QWORD *)&v16 + 96LL) != 8 )
                      std::list<ProblemNode *>::_Insert<ProblemNode * const &>(v25, v25[0], &v23);
                  }
                  *(_DWORD *)(v14 + 96) = 8;
                }
              }
              std::list<ProblemNode *>::~list<ProblemNode *>(v25);
              ++v12;
              v11 = *(_QWORD *)(v6 + 32);
              v13 = v12;
            }
            while ( v12 < (unsigned __int64)((*(_QWORD *)(v6 + 40) - v11) >> 3) );
            v7 = (__int16 *)(v6 + 92);
            v9 = (CTraceController *)(v6 + 128);
          }
        }
        v27 = 0;
        v22 = 0;
        v21 = 0;
        v4 = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, __int128 *, unsigned int *, int *))(*(_QWORD *)a2 + 48LL))(
               a2,
               &v27,
               &v22,
               &v21);
        if ( v4 >= 0 )
        {
          *(_QWORD *)(v6 + 80) = a2;
          v20 = 0;
          while ( 1 )
          {
            _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 24), 6, 5);
            v20 = 0;
            v17 = NetworkIncident::Repair(v6, &v27, &v20, v22, v21);
            v4 = v17;
            if ( v17 != -2147483638 )
              break;
            _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 24), 7, 6);
            if ( *(_DWORD *)(v6 + 24) == 13 || !WaitForSingleObject(*(HANDLE *)(v6 + 72), 1000 * v20) )
            {
              v4 = -2147467260;
              goto LABEL_47;
            }
            _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 24), 6, 7);
            if ( !v20 || *(_DWORD *)(v6 + 24) == 13 )
              goto LABEL_47;
          }
          if ( (int)(v17 + 0x80000000) >= 0 && v17 != -2147467260 )
          {
            v24 = 0;
            CTraceController::Stop(v9);
            NetworkDiagnosticsEngine::SendReport(v3, (struct NetworkIncident *)v6);
          }
LABEL_47:
          *(_DWORD *)(v6 + 96) = v4;
          _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 24), ((v4 >> 31) & 0xFFFFFFFC) + 8, 6);
        }
        else if ( *(_QWORD *)v3 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)v3 + 96LL))(
            *(_QWORD *)v3,
            2,
            L"Failed while trying to find the selected repair.");
          (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, (unsigned int)v4, 2);
        }
        CTraceAutoSuspend::~CTraceAutoSuspend((CTraceAutoSuspend *)&v24);
        v19 = *v7;
        WdiAddParameter(*((_QWORD *)a2 + 1), 0, L"NDFStopStatus", 2, &v19);
      }
    }
    else if ( *(_QWORD *)v3 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)v3 + 48LL))(*(_QWORD *)v3, 1, (unsigned int)v4);
      (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, (unsigned int)v4, 2);
    }
  }
  else
  {
    v4 = -2147024890;
    if ( *(_QWORD *)qword_180041BB8 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)qword_180041BB8 + 48LL))(
        *(_QWORD *)qword_180041BB8,
        1,
        2147942406LL);
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, 2147942406LL, 2);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bb00  push    rbp
0x18001bb02  push    rbx
0x18001bb03  push    rsi
0x18001bb04  push    rdi
0x18001bb05  push    r12
0x18001bb07  push    r13
0x18001bb09  push    r14
0x18001bb0b  push    r15
0x18001bb0d  lea     rbp, [rsp-1Fh]
0x18001bb12  sub     rsp, 0A8h
0x18001bb19  mov     rax, cs:__security_cookie
0x18001bb20  xor     rax, rsp
0x18001bb23  mov     [rbp+57h+var_48], rax
0x18001bb27  mov     r14, rdx
0x18001bb2a  mov     rsi, cs:qword_180041BB8
0x18001bb31  test    rdx, rdx
0x18001bb34  jnz     short loc_18001BB6C
0x18001bb36  mov     rcx, [rsi]
0x18001bb39  mov     ebx, 80070006h
0x18001bb3e  test    rcx, rcx
0x18001bb41  jz      loc_18001BF54
0x18001bb47  mov     rax, [rcx]
0x18001bb4a  mov     r8d, ebx
0x18001bb4d  lea     edx, [r14+1]
0x18001bb51  mov     rax, [rax+30h]
0x18001bb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb5a  mov     r9, [rsi]
0x18001bb5d  mov     rcx, [r9]
0x18001bb60  mov     rax, [rcx+38h]
0x18001bb64  mov     rcx, r9
0x18001bb67  jmp     loc_18001BF47
0x18001bb6c  xorps   xmm0, xmm0
0x18001bb6f  movups  [rbp+57h+var_68], xmm0
0x18001bb73  mov     rax, [rdx]
0x18001bb76  lea     rdx, [rbp+57h+var_68]
0x18001bb7a  mov     rcx, r14
0x18001bb7d  mov     rax, [rax+48h]
0x18001bb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb86  mov     ebx, eax
0x18001bb88  test    eax, eax
0x18001bb8a  jns     short loc_18001BBBE
0x18001bb8c  mov     r9, [rsi]
0x18001bb8f  test    r9, r9
0x18001bb92  jz      loc_18001BF54
0x18001bb98  mov     rcx, [r9]
0x18001bb9b  mov     rax, [rcx+30h]
0x18001bb9f  mov     r8d, ebx
0x18001bba2  mov     edx, 1
0x18001bba7  mov     rcx, r9
0x18001bbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbaf  mov     rcx, [rsi]
0x18001bbb2  mov     rax, [rcx]
0x18001bbb5  mov     rax, [rax+38h]
0x18001bbb9  jmp     loc_18001BF47
0x18001bbbe  lea     r8, [rbp+57h+var_68]
0x18001bbc2  lea     rdx, [rbp+57h+var_98]
0x18001bbc6  lea     rcx, [rsi+8]
0x18001bbca  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(_GUID const &)
0x18001bbcf  mov     rdi, [rax]
0x18001bbd2  cmp     rdi, [rsi+8]
0x18001bbd6  jz      loc_18001BF1C
0x18001bbdc  mov     rdi, [rdi+30h]
0x18001bbe0  test    rdi, rdi
0x18001bbe3  jz      loc_18001BF1C
0x18001bbe9  lea     r12, [rdi+5Ch]
0x18001bbed  mov     [rbp+57h+var_78], r12
0x18001bbf1  mov     [rbp+57h+var_70], r14
0x18001bbf5  xor     ebx, ebx
0x18001bbf7  mov     [rbp+57h+var_90], rbx
0x18001bbfb  lea     r13, [rdi+80h]
0x18001bc02  mov     rcx, r13; this
0x18001bc05  call    ?Resume@CTraceController@@QEAAJXZ; CTraceController::Resume(void)
0x18001bc0a  test    eax, eax
0x18001bc0c  cmovns  rbx, r13
0x18001bc10  mov     [rbp+57h+var_90], rbx
0x18001bc14  mov     ecx, 5
0x18001bc19  lea     eax, [rcx-1]
0x18001bc1c  lock cmpxchg [rdi+18h], ecx
0x18001bc21  mov     ecx, [rdi+68h]
0x18001bc24  shl     rcx, 20h
0x18001bc28  mov     eax, [rdi+64h]
0x18001bc2b  or      rcx, rax
0x18001bc2e  jz      short loc_18001BC91
0x18001bc30  xor     ebx, ebx
0x18001bc32  cmp     [rdi+78h], rbx
0x18001bc36  jz      short loc_18001BC93
0x18001bc38  lea     rcx, [rbp+57h+var_98]
0x18001bc3c  call    ?GetTickCount@CFileTime@ATL@@SA?AV12@XZ; ATL::CFileTime::GetTickCount(void)
0x18001bc41  mov     r9, [rdi+78h]
0x18001bc45  mov     r8, [r9]
0x18001bc48  mov     edx, [rax+4]
0x18001bc4b  shl     rdx, 20h
0x18001bc4f  mov     eax, [rax]
0x18001bc51  or      rdx, rax
0x18001bc54  mov     rcx, [rdi+64h]
0x18001bc58  mov     rax, 0FFFFFFFF00000000h
0x18001bc62  and     rcx, rax
0x18001bc65  mov     eax, [rdi+64h]
0x18001bc68  or      rcx, rax
0x18001bc6b  sub     rdx, rcx
0x18001bc6e  mov     rax, 0D6BF94D5E57A42BDh
0x18001bc78  mul     rdx
0x18001bc7b  shr     rdx, 17h
0x18001bc7f  mov     rcx, r9
0x18001bc82  mov     rax, [r8+78h]
0x18001bc86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc8b  mov     [rdi+64h], rbx
0x18001bc8f  jmp     short loc_18001BC93
0x18001bc91  xor     ebx, ebx
0x18001bc93  mov     r15d, 1
0x18001bc99  cmp     [r12], r15w
0x18001bc9e  jnz     loc_18001BDA8
0x18001bca4  mov     rcx, [rdi+20h]
0x18001bca8  mov     rax, [rdi+28h]
0x18001bcac  sub     rax, rcx
0x18001bcaf  sar     rax, 3
0x18001bcb3  test    rax, rax
0x18001bcb6  jz      loc_18001BDA8
0x18001bcbc  mov     r13d, ebx
0x18001bcbf  mov     rdx, rbx
0x18001bcc2  mov     rax, [rcx+rdx*8]
0x18001bcc6  mov     [rbp+57h+var_98], rax
0x18001bcca  lea     rcx, [rbp+57h+var_88]
0x18001bcce  call    ??0?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::list<ProblemNode *>(void)
0x18001bcd3  nop
0x18001bcd4  lea     r8, [rbp+57h+var_98]
0x18001bcd8  mov     rdx, [rbp+57h+var_88]
0x18001bcdc  lea     rcx, [rbp+57h+var_88]
0x18001bce0  call    ??$_Insert@AEBQEAVProblemNode@@@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVProblemNode@@@std@@@std@@U_Iterator_base0@2@@1@AEBQEAVProblemNode@@@Z; std::list<ProblemNode *>::_Insert<ProblemNode * const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProblemNode *>>,std::_Iterator_base0>,ProblemNode * const &)
0x18001bce5  cmp     [rbp+57h+var_80], rbx
0x18001bce9  jz      loc_18001BD76
0x18001bcef  mov     rax, [rbp+57h+var_88]
0x18001bcf3  mov     rcx, [rax]
0x18001bcf6  mov     r12, [rcx+10h]
0x18001bcfa  lea     rcx, [rbp+57h+var_88]
0x18001bcfe  call    ?pop_front@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXXZ; std::list<ProblemNode *>::pop_front(void)
0x18001bd03  test    r12, r12
0x18001bd06  jz      short loc_18001BCE5
0x18001bd08  mov     rax, [r12]
0x18001bd0c  cmp     [rax+0F8h], rbx
0x18001bd13  jz      short loc_18001BD1C
0x18001bd15  mov     [rax+0F8h], rbx
0x18001bd1c  mov     rax, [r12]
0x18001bd20  cmp     [rax+0F4h], ebx
0x18001bd26  jz      short loc_18001BD2E
0x18001bd28  mov     [rax+0F4h], ebx
0x18001bd2e  mov     rbx, [r12+40h]
0x18001bd33  mov     rbx, [rbx]
0x18001bd36  cmp     rbx, [r12+40h]
0x18001bd3b  jz      short loc_18001BD66
0x18001bd3d  mov     rcx, [rbx+10h]
0x18001bd41  mov     rbx, [rbx]
0x18001bd44  mov     [rbp+57h+var_98], rcx
0x18001bd48  test    rcx, rcx
0x18001bd4b  jz      short loc_18001BD36
0x18001bd4d  cmp     dword ptr [rcx+60h], 8
0x18001bd51  jz      short loc_18001BD36
0x18001bd53  lea     r8, [rbp+57h+var_98]
0x18001bd57  mov     rdx, [rbp+57h+var_88]
0x18001bd5b  lea     rcx, [rbp+57h+var_88]
0x18001bd5f  call    ??$_Insert@AEBQEAVProblemNode@@@?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVProblemNode@@@std@@@std@@U_Iterator_base0@2@@1@AEBQEAVProblemNode@@@Z; std::list<ProblemNode *>::_Insert<ProblemNode * const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ProblemNode *>>,std::_Iterator_base0>,ProblemNode * const &)
0x18001bd64  jmp     short loc_18001BD36
0x18001bd66  mov     dword ptr [r12+60h], 8
0x18001bd6f  xor     ebx, ebx
0x18001bd71  jmp     loc_18001BCE5
0x18001bd76  lea     rcx, [rbp+57h+var_88]
0x18001bd7a  call    ??1?$list@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::list<ProblemNode *>::~list<ProblemNode *>(void)
0x18001bd7f  add     r13d, r15d
0x18001bd82  mov     rcx, [rdi+20h]
0x18001bd86  mov     edx, r13d
0x18001bd89  mov     rax, [rdi+28h]
0x18001bd8d  sub     rax, rcx
0x18001bd90  sar     rax, 3
0x18001bd94  cmp     rdx, rax
0x18001bd97  jb      loc_18001BCC2
0x18001bd9d  lea     r12, [rdi+5Ch]
0x18001bda1  lea     r13, [rdi+80h]
0x18001bda8  xorps   xmm0, xmm0
0x18001bdab  movups  [rbp+57h+var_58], xmm0
0x18001bdaf  mov     [rbp+57h+var_A0], ebx
0x18001bdb2  mov     [rbp+57h+var_A4], ebx
0x18001bdb5  mov     rax, [r14]
0x18001bdb8  lea     r9, [rbp+57h+var_A4]
0x18001bdbc  lea     r8, [rbp+57h+var_A0]
0x18001bdc0  lea     rdx, [rbp+57h+var_58]
0x18001bdc4  mov     rcx, r14
0x18001bdc7  mov     rax, [rax+30h]
0x18001bdcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdd0  mov     ebx, eax
0x18001bdd2  xor     r15d, r15d
0x18001bdd5  test    eax, eax
0x18001bdd7  jns     short loc_18001BE4B
0x18001bdd9  mov     r9, [rsi]
0x18001bddc  test    r9, r9
0x18001bddf  jz      short loc_18001BE11
0x18001bde1  mov     rcx, [r9]
0x18001bde4  mov     rax, [rcx+60h]
0x18001bde8  lea     r8, aFailedWhileTry; "Failed while trying to find the selecte"...
0x18001bdef  lea     edx, [r15+2]
0x18001bdf3  mov     rcx, r9
0x18001bdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bdfb  mov     rcx, [rsi]
0x18001bdfe  mov     rax, [rcx]
0x18001be01  lea     r8d, [r15+2]
0x18001be05  mov     edx, ebx
0x18001be07  mov     rax, [rax+38h]
0x18001be0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be10  nop
0x18001be11  lea     rcx, [rbp+57h+var_90]; this
0x18001be15  call    ??1CTraceAutoSuspend@@QEAA@XZ; CTraceAutoSuspend::~CTraceAutoSuspend(void)
0x18001be1a  nop
0x18001be1b  movzx   eax, word ptr [r12]
0x18001be20  mov     [rbp+57h+var_B0], ax
0x18001be24  lea     rax, [rbp+57h+var_B0]
0x18001be28  mov     [rsp+0E0h+var_C0], rax
0x18001be2d  mov     r9d, 2
0x18001be33  lea     r8, aNdfstopstatus; "NDFStopStatus"
0x18001be3a  xor     edx, edx
0x18001be3c  mov     rcx, [r14+8]
0x18001be40  call    cs:__imp_WdiAddParameter
0x18001be46  jmp     loc_18001BF54
0x18001be4b  mov     [rdi+50h], r14
0x18001be4f  mov     [rbp+57h+var_A8], r15d
0x18001be53  mov     edx, 6
0x18001be58  mov     eax, 5
0x18001be5d  lock cmpxchg [rdi+18h], edx
0x18001be62  mov     [rbp+57h+var_A8], r15d
0x18001be66  mov     eax, [rbp+57h+var_A4]
0x18001be69  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18001be6d  mov     r9d, [rbp+57h+var_A0]
0x18001be71  lea     r8, [rbp+57h+var_A8]
0x18001be75  lea     rdx, [rbp+57h+var_58]
0x18001be79  mov     rcx, rdi
0x18001be7c  call    ?Repair@NetworkIncident@@QEAAJPEAU_GUID@@PEAJIW4NDFRepairState@@@Z; NetworkIncident::Repair(_GUID *,long *,uint,NDFRepairState)
0x18001be81  mov     ebx, eax
0x18001be83  cmp     eax, 8000000Ah
0x18001be88  jnz     short loc_18001BED4
0x18001be8a  mov     eax, 6
0x18001be8f  lea     ecx, [rax+1]
0x18001be92  lock cmpxchg [rdi+18h], ecx
0x18001be97  cmp     dword ptr [rdi+18h], 0Dh
0x18001be9b  jz      short loc_18001BECD
0x18001be9d  imul    edx, [rbp+57h+var_A8], 3E8h; dwMilliseconds
0x18001bea4  mov     rcx, [rdi+48h]; hHandle
0x18001bea8  call    cs:__imp_WaitForSingleObject
0x18001beae  test    eax, eax
0x18001beb0  jz      short loc_18001BECD
0x18001beb2  mov     eax, 7
0x18001beb7  lea     edx, [rax-1]
0x18001beba  lock cmpxchg [rdi+18h], edx
0x18001bebf  cmp     [rbp+57h+var_A8], r15d
0x18001bec3  jz      short loc_18001BEFF
0x18001bec5  cmp     dword ptr [rdi+18h], 0Dh
0x18001bec9  jnz     short loc_18001BE58
0x18001becb  jmp     short loc_18001BEFF
0x18001becd  mov     ebx, 80004004h
0x18001bed2  jmp     short loc_18001BEFF
0x18001bed4  mov     ecx, 80000000h
0x18001bed9  add     eax, ecx
0x18001bedb  test    ecx, eax
0x18001bedd  jnz     short loc_18001BEFF
0x18001bedf  cmp     ebx, 80004004h
0x18001bee5  jz      short loc_18001BEFF
0x18001bee7  mov     [rbp+57h+var_90], r15
0x18001beeb  mov     rcx, r13; this
0x18001beee  call    ?Stop@CTraceController@@QEAAJXZ; CTraceController::Stop(void)
0x18001bef3  mov     rdx, rdi; struct NetworkIncident *
0x18001bef6  mov     rcx, rsi; this
0x18001bef9  call    ?SendReport@NetworkDiagnosticsEngine@@QEAAXPEAVNetworkIncident@@@Z; NetworkDiagnosticsEngine::SendReport(NetworkIncident *)
0x18001befe  nop
0x18001beff  mov     [rdi+60h], ebx
0x18001bf02  mov     edx, ebx
0x18001bf04  sar     edx, 1Fh
0x18001bf07  and     edx, 0FFFFFFFCh
0x18001bf0a  add     edx, 8
0x18001bf0d  mov     eax, 6
0x18001bf12  lock cmpxchg [rdi+18h], edx
0x18001bf17  jmp     loc_18001BE11
0x18001bf1c  mov     rcx, [rsi]
0x18001bf1f  mov     ebx, 80070057h
0x18001bf24  test    rcx, rcx
0x18001bf27  jz      short loc_18001BF54
0x18001bf29  mov     rax, [rcx]
0x18001bf2c  mov     r8d, ebx
0x18001bf2f  mov     edx, 1
0x18001bf34  mov     rax, [rax+30h]
0x18001bf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf3d  mov     rcx, [rsi]
0x18001bf40  mov     rdx, [rcx]
0x18001bf43  mov     rax, [rdx+38h]
0x18001bf47  mov     r8d, 2
0x18001bf4d  mov     edx, ebx
0x18001bf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf54  mov     eax, ebx
0x18001bf56  mov     rcx, [rbp+57h+var_48]
0x18001bf5a  xor     rcx, rsp; StackCookie
0x18001bf5d  call    __security_check_cookie
0x18001bf62  add     rsp, 0A8h
0x18001bf69  pop     r15
0x18001bf6b  pop     r14
  ... truncated ...
```
