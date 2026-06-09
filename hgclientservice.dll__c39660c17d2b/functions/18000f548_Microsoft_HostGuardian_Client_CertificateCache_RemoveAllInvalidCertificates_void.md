# Microsoft::HostGuardian::Client::CertificateCache::RemoveAllInvalidCertificates(void)

- ea: `0x18000f548`
- end: `0x18000f80b`
- name: `?RemoveAllInvalidCertificates@CertificateCache@Client@HostGuardian@Microsoft@@AEAAXXZ`
- size: `707`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f814`

## callees

- `0x180001bb4`
- `0x18000e9a0`
- `0x18000ec58`
- `0x18000f548`
- `0x1800101c4`
- `0x180010870`
- `0x180014ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f563`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f563`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f57a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f57a`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f7f7`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000f7f7`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::CertificateCache::RemoveAllInvalidCertificates(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // r12
  RTL_SRWLOCK *v3; // r15
  __int64 *v4; // rdi
  __int64 *v5; // rbx
  __int64 **v6; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  _QWORD *Ptr; // rcx
  _QWORD *v10; // rbx
  _BYTE *v11; // rbp
  _QWORD *v12; // rax
  int v13; // edx
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  void **v16; // r14
  _QWORD *v17; // rsi
  void **v18; // rcx
  void **v19; // rbx
  __int64 **v20; // rcx
  __int64 *m; // rax
  _BYTE *v22; // rcx
  _QWORD *v23; // rdx
  __int64 *v24; // r8
  _QWORD *v25; // rax
  __int64 k; // rcx
  __int64 v27; // r8
  RTL_SRWLOCK *v28; // r9
  _QWORD *v29; // r8
  __int64 *v30; // r8
  void **v31; // rsi
  __int64 *n; // rcx
  __time64_t Time; // [rsp+70h] [rbp+8h] BYREF

  v1 = this + 5;
  AcquireSRWLockExclusive(this + 5);
  if ( this[2].Ptr )
  {
    v3 = this + 1;
    v4 = *(__int64 **)this[1].Ptr;
    while ( !*((_BYTE *)v4 + 25) )
    {
      v5 = *(__int64 **)v4[5];
      while ( !*((_BYTE *)v5 + 25) )
      {
        if ( (unsigned int)Microsoft::HostGuardian::Client::Utilities::GetDurationStatus((FILETIME)v5[8]) == 3 )
          std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::erase(
            v4 + 5,
            v5 + 4);
        v6 = (__int64 **)v5[2];
        if ( *((_BYTE *)v6 + 25) )
        {
          for ( i = (__int64 *)v5[1]; !*((_BYTE *)i + 25) && v5 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v5 = i;
          v5 = i;
        }
        else
        {
          v5 = (__int64 *)v5[2];
          for ( j = *v6; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v5 = j;
        }
      }
      if ( !v4[6] )
      {
        Ptr = v3->Ptr;
        v10 = v3->Ptr;
        v11 = v3->Ptr;
        v12 = (_QWORD *)*((_QWORD *)v3->Ptr + 1);
        if ( !*((_BYTE *)v12 + 25) )
        {
          v13 = *((_DWORD *)v4 + 8);
          do
          {
            if ( *((_DWORD *)v12 + 8) >= v13 )
            {
              if ( v11[25] && v13 < *((_DWORD *)v12 + 8) )
                v11 = v12;
              v10 = v12;
              v12 = (_QWORD *)*v12;
            }
            else
            {
              v12 = (_QWORD *)v12[2];
            }
          }
          while ( !*((_BYTE *)v12 + 25) );
        }
        if ( v11[25] )
          v14 = Ptr + 1;
        else
          v14 = v11;
        v15 = (_QWORD *)*v14;
        while ( !*((_BYTE *)v15 + 25) )
        {
          if ( *((_DWORD *)v4 + 8) >= *((_DWORD *)v15 + 8) )
          {
            v15 = (_QWORD *)v15[2];
          }
          else
          {
            v11 = v15;
            v15 = (_QWORD *)*v15;
          }
        }
        if ( v10 == (_QWORD *)*Ptr && v11[25] )
        {
          v16 = (void **)Ptr[1];
          v17 = v3->Ptr;
          while ( !*((_BYTE *)v16 + 25) )
          {
            std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,void *>>>(
              &this[1],
              &this[1],
              v16[2]);
            v18 = v16;
            v19 = v16;
            v16 = (void **)*v16;
            std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v18 + 5);
            operator delete(v19);
          }
          v17[1] = v17;
          *v17 = v17;
          v17[2] = v17;
          this[2].Ptr = 0;
        }
        else
        {
          while ( v10 != (_QWORD *)v11 )
          {
            v22 = (_BYTE *)v10[2];
            v23 = v10;
            if ( v22[25] )
            {
              v24 = v10 + 1;
              v25 = v10;
              for ( k = v10[1]; !*(_BYTE *)(k + 25) && v10 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
                v10 = (_QWORD *)k;
              v27 = *v24;
              v10 = (_QWORD *)k;
              v28 = this + 1;
              while ( !*(_BYTE *)(v27 + 25) && v25 == *(_QWORD **)(v27 + 16) )
              {
                v25 = (_QWORD *)v27;
                v27 = *(_QWORD *)(v27 + 8);
              }
            }
            else
            {
              v29 = *(_QWORD **)v22;
              if ( *(_BYTE *)(*(_QWORD *)v22 + 25LL) )
              {
                v10 = (_QWORD *)v10[2];
              }
              else
              {
                do
                {
                  v10 = v29;
                  v29 = (_QWORD *)*v29;
                }
                while ( !*((_BYTE *)v29 + 25) );
              }
              v30 = *(__int64 **)v22;
              v28 = this + 1;
              if ( !*(_BYTE *)(*(_QWORD *)v22 + 25LL) )
              {
                do
                  v30 = (__int64 *)*v30;
                while ( !*((_BYTE *)v30 + 25) );
              }
            }
            v31 = (void **)std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>>>::_Extract(
                             v28,
                             v23);
            std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v31 + 5);
            operator delete(v31);
          }
        }
      }
      v20 = (__int64 **)v4[2];
      if ( *((_BYTE *)v20 + 25) )
      {
        for ( m = (__int64 *)v4[1]; !*((_BYTE *)m + 25) && v4 == (__int64 *)m[2]; m = (__int64 *)m[1] )
          v4 = m;
        v4 = m;
      }
      else
      {
        v4 = (__int64 *)v4[2];
        for ( n = *v20; !*((_BYTE *)n + 25); n = (__int64 *)*n )
          v4 = n;
      }
    }
    Time = 0;
    _time64(&Time);
    this->Ptr = (PVOID)Time;
  }
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18000f548  push    rbx
0x18000f54a  push    rbp
0x18000f54b  push    rsi
0x18000f54c  push    rdi
0x18000f54d  push    r12
0x18000f54f  push    r13
0x18000f551  push    r14
0x18000f553  push    r15
0x18000f555  sub     rsp, 28h
0x18000f559  lea     r12, [rcx+28h]
0x18000f55d  mov     r13, rcx
0x18000f560  mov     rcx, r12; SRWLock
0x18000f563  call    cs:__imp_AcquireSRWLockExclusive
0x18000f569  xor     r10d, r10d
0x18000f56c  cmp     [r13+10h], r10
0x18000f570  jnz     short loc_18000F591
0x18000f572  test    r12, r12
0x18000f575  jz      short loc_18000F580
0x18000f577  mov     rcx, r12; SRWLock
0x18000f57a  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f580  add     rsp, 28h
0x18000f584  pop     r15
0x18000f586  pop     r14
0x18000f588  pop     r13
0x18000f58a  pop     r12
0x18000f58c  pop     rdi
0x18000f58d  pop     rsi
0x18000f58e  pop     rbp
0x18000f58f  pop     rbx
0x18000f590  retn
0x18000f591  lea     r15, [r13+8]
0x18000f595  mov     rdi, [r15]
0x18000f598  mov     rdi, [rdi]
0x18000f59b  cmp     [rdi+19h], r10b
0x18000f59f  jnz     loc_18000F7ED
0x18000f5a5  mov     rbx, [rdi+28h]
0x18000f5a9  mov     rbx, [rbx]
0x18000f5ac  cmp     [rbx+19h], r10b
0x18000f5b0  jnz     short loc_18000F615
0x18000f5b2  mov     rcx, [rbx+40h]
0x18000f5b6  call    ?GetDurationStatus@Utilities@Client@HostGuardian@Microsoft@@YA?AW4DurationStatus@1234@U_FILETIME@@@Z; Microsoft::HostGuardian::Client::Utilities::GetDurationStatus(_FILETIME)
0x18000f5bb  cmp     eax, 3
0x18000f5be  jnz     short loc_18000F5CD
0x18000f5c0  lea     rdx, [rbx+20h]
0x18000f5c4  lea     rcx, [rdi+28h]
0x18000f5c8  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::erase(std::wstring const &)
0x18000f5cd  mov     rcx, [rbx+10h]
0x18000f5d1  xor     r10d, r10d
0x18000f5d4  cmp     [rcx+19h], r10b
0x18000f5d8  jz      short loc_18000F5F8
0x18000f5da  mov     rax, [rbx+8]
0x18000f5de  jmp     short loc_18000F5ED
0x18000f5e0  cmp     rbx, [rax+10h]
0x18000f5e4  jnz     short loc_18000F5F3
0x18000f5e6  mov     rbx, rax
0x18000f5e9  mov     rax, [rax+8]
0x18000f5ed  cmp     [rax+19h], r10b
0x18000f5f1  jz      short loc_18000F5E0
0x18000f5f3  mov     rbx, rax
0x18000f5f6  jmp     short loc_18000F5AC
0x18000f5f8  mov     rbx, rcx
0x18000f5fb  mov     rcx, [rcx]
0x18000f5fe  cmp     [rcx+19h], r10b
0x18000f602  jnz     short loc_18000F5AC
0x18000f604  mov     rax, [rcx]
0x18000f607  mov     rbx, rcx
0x18000f60a  mov     rcx, rax
0x18000f60d  cmp     [rax+19h], r10b
0x18000f611  jz      short loc_18000F604
0x18000f613  jmp     short loc_18000F5AC
0x18000f615  cmp     [rdi+30h], r10
0x18000f619  jnz     loc_18000F6E8
0x18000f61f  mov     rcx, [r15]
0x18000f622  mov     rbx, rcx
0x18000f625  mov     rbp, rcx
0x18000f628  mov     rax, [rcx+8]
0x18000f62c  cmp     [rax+19h], r10b
0x18000f630  jnz     short loc_18000F659
0x18000f632  mov     edx, [rdi+20h]
0x18000f635  cmp     [rax+20h], edx
0x18000f638  jge     short loc_18000F640
0x18000f63a  mov     rax, [rax+10h]
0x18000f63e  jmp     short loc_18000F653
0x18000f640  cmp     [rbp+19h], r10b
0x18000f644  jz      short loc_18000F64D
0x18000f646  cmp     edx, [rax+20h]
0x18000f649  cmovl   rbp, rax
0x18000f64d  mov     rbx, rax
0x18000f650  mov     rax, [rax]
0x18000f653  cmp     [rax+19h], r10b
0x18000f657  jz      short loc_18000F635
0x18000f659  mov     rax, rcx
0x18000f65c  cmp     [rbp+19h], r10b
0x18000f660  jz      short loc_18000F668
0x18000f662  add     rax, 8
0x18000f666  jmp     short loc_18000F66B
0x18000f668  mov     rax, rbp
0x18000f66b  mov     rax, [rax]
0x18000f66e  cmp     [rax+19h], r10b
0x18000f672  jnz     short loc_18000F68E
0x18000f674  mov     edx, [rdi+20h]
0x18000f677  cmp     edx, [rax+20h]
0x18000f67a  jge     short loc_18000F684
0x18000f67c  mov     rbp, rax
0x18000f67f  mov     rax, [rax]
0x18000f682  jmp     short loc_18000F688
0x18000f684  mov     rax, [rax+10h]
0x18000f688  cmp     [rax+19h], r10b
0x18000f68c  jz      short loc_18000F677
0x18000f68e  cmp     rbx, [rcx]
0x18000f691  jnz     short loc_18000F6FF
0x18000f693  cmp     [rbp+19h], r10b
0x18000f697  jz      short loc_18000F6FF
0x18000f699  mov     r14, [rcx+8]
0x18000f69d  mov     rsi, rcx
0x18000f6a0  jmp     short loc_18000F6D3
0x18000f6a2  mov     r8, [r14+10h]
0x18000f6a6  mov     rdx, r15
0x18000f6a9  mov     rcx, r15
0x18000f6ac  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@1@@Z
0x18000f6b1  mov     rcx, r14
0x18000f6b4  mov     rbx, r14
0x18000f6b7  mov     r14, [r14]
0x18000f6ba  add     rcx, 28h ; '('
0x18000f6be  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000f6c3  mov     edx, 38h ; '8'
0x18000f6c8  mov     rcx, rbx; Block
0x18000f6cb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f6d0  xor     r10d, r10d
0x18000f6d3  cmp     [r14+19h], r10b
0x18000f6d7  jz      short loc_18000F6A2
0x18000f6d9  mov     [rsi+8], rsi
0x18000f6dd  mov     [rsi], rsi
0x18000f6e0  mov     [rsi+10h], rsi
0x18000f6e4  mov     [r15+8], r10
0x18000f6e8  mov     rcx, [rdi+10h]
0x18000f6ec  cmp     [rcx+19h], r10b
0x18000f6f0  jz      loc_18000F7C9
0x18000f6f6  mov     rax, [rdi+8]
0x18000f6fa  jmp     loc_18000F7BB
0x18000f6ff  cmp     rbx, rbp
0x18000f702  jz      short loc_18000F6E8
0x18000f704  mov     rcx, [rbx+10h]
0x18000f708  mov     rdx, rbx
0x18000f70b  cmp     [rcx+19h], r10b
0x18000f70f  jz      short loc_18000F750
0x18000f711  lea     r8, [rbx+8]
0x18000f715  mov     rax, rbx
0x18000f718  mov     rcx, [r8]
0x18000f71b  jmp     short loc_18000F72A
0x18000f71d  cmp     rbx, [rcx+10h]
0x18000f721  jnz     short loc_18000F730
0x18000f723  mov     rbx, rcx
0x18000f726  mov     rcx, [rcx+8]
0x18000f72a  cmp     [rcx+19h], r10b
0x18000f72e  jz      short loc_18000F71D
0x18000f730  mov     r8, [r8]
0x18000f733  mov     rbx, rcx
0x18000f736  mov     r9, r15
0x18000f739  jmp     short loc_18000F748
0x18000f73b  cmp     rax, [r8+10h]
0x18000f73f  jnz     short loc_18000F785
0x18000f741  mov     rax, r8
0x18000f744  mov     r8, [r8+8]
0x18000f748  cmp     [r8+19h], r10b
0x18000f74c  jz      short loc_18000F73B
0x18000f74e  jmp     short loc_18000F785
0x18000f750  mov     r8, [rcx]
0x18000f753  cmp     [r8+19h], r10b
0x18000f757  jnz     short loc_18000F76A
0x18000f759  mov     rax, [r8]
0x18000f75c  mov     rbx, r8
0x18000f75f  mov     r8, rax
0x18000f762  cmp     [rax+19h], r10b
0x18000f766  jz      short loc_18000F759
0x18000f768  jmp     short loc_18000F76D
0x18000f76a  mov     rbx, rcx
0x18000f76d  mov     r8, [rcx]
0x18000f770  mov     r9, r15
0x18000f773  cmp     [r8+19h], r10b
0x18000f777  jnz     short loc_18000F785
0x18000f779  mov     rax, [r8]
0x18000f77c  mov     r8, rax
0x18000f77f  cmp     [rax+19h], r10b
0x18000f783  jz      short loc_18000F779
0x18000f785  mov     rcx, r9
0x18000f788  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>>>,std::_Iterator_base0>)
0x18000f78d  mov     rsi, rax
0x18000f790  lea     rcx, [rax+28h]
0x18000f794  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000f799  mov     edx, 38h ; '8'
0x18000f79e  mov     rcx, rsi; Block
0x18000f7a1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f7a6  xor     r10d, r10d
0x18000f7a9  jmp     loc_18000F6FF
0x18000f7ae  cmp     rdi, [rax+10h]
0x18000f7b2  jnz     short loc_18000F7C1
0x18000f7b4  mov     rdi, rax
0x18000f7b7  mov     rax, [rax+8]
0x18000f7bb  cmp     [rax+19h], r10b
0x18000f7bf  jz      short loc_18000F7AE
0x18000f7c1  mov     rdi, rax
0x18000f7c4  jmp     loc_18000F59B
0x18000f7c9  mov     rdi, rcx
0x18000f7cc  mov     rcx, [rcx]
0x18000f7cf  cmp     [rcx+19h], r10b
0x18000f7d3  jnz     loc_18000F59B
0x18000f7d9  mov     rax, [rcx]
0x18000f7dc  mov     rdi, rcx
0x18000f7df  mov     rcx, rax
0x18000f7e2  cmp     [rax+19h], r10b
0x18000f7e6  jz      short loc_18000F7D9
0x18000f7e8  jmp     loc_18000F59B
0x18000f7ed  lea     rcx, [rsp+68h+Time]; Time
0x18000f7f2  mov     [rsp+68h+Time], r10
0x18000f7f7  call    cs:__imp__time64
0x18000f7fd  mov     rax, [rsp+68h+Time]
0x18000f802  mov     [r13+0], rax
0x18000f806  jmp     loc_18000F572
```
