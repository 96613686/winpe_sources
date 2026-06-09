# Rdp::Avenc::RdpProg::CRdpProgProcessor::PacketWriterThreadProc(void)

- ea: `0x180063db0`
- end: `0x180064171`
- name: `?PacketWriterThreadProc@CRdpProgProcessor@RdpProg@Avenc@Rdp@@AEAAXXZ`
- size: `961`
- prototype: `void __fastcall(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006fc4`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800203d4`
- `0x180023a28`
- `0x180026ef0`
- `0x180063db0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180063eb0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180063eb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063e91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180063e91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180064127`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180063ec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180064053`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180063ec7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180064053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063e58`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180063e58`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180063e4a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180063e4a`

## string_xrefs

- `0x1800640bb`: `Failed to write packet to channel`

## pseudocode

```c
void __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::PacketWriterThreadProc(
        Rdp::Avenc::RdpProg::CRdpProgProcessor *this)
{
  char *v2; // r13
  bool v3; // zf
  __int64 v4; // rbx
  _QWORD **v5; // r14
  _QWORD *v6; // rdx
  _QWORD *v7; // rax
  _QWORD *i; // r14
  __int64 *v9; // rcx
  _QWORD *v10; // rsi
  _QWORD *v11; // r12
  __int64 v12; // r15
  __int64 *v13; // rax
  __int64 v14; // rdx
  __int64 **v15; // rcx
  __int64 *j; // rcx
  _QWORD *v17; // rax
  unsigned int v18; // eax
  const char *v19; // [rsp+28h] [rbp-30h]
  __int128 v20; // [rsp+30h] [rbp-28h] BYREF
  char *v21; // [rsp+40h] [rbp-18h]
  char v22; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  _QWORD *v24; // [rsp+A8h] [rbp+50h] BYREF
  __int64 v25; // [rsp+B0h] [rbp+58h]
  __int64 v26; // [rsp+B8h] [rbp+60h] BYREF

  v20 = xmmword_180093D68;
  if ( *((_BYTE *)this + 496) )
  {
    v2 = (char *)this + 344;
    while ( 1 )
    {
      if ( (unsigned int)mtx_do_lock(v2) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
      {
        *((_DWORD *)v2 + 19) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      while ( *((_BYTE *)this + 496) && !*((_DWORD *)this + 125) )
      {
        *((_DWORD *)this + 104) = -1;
        --*((_DWORD *)this + 105);
        if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 54, (PSRWLOCK)this + 45, 0xFFFFFFFF, 0) )
          abort();
        *((_DWORD *)this + 104) = GetCurrentThreadId();
        ++*((_DWORD *)this + 105);
      }
      if ( !*((_BYTE *)this + 496) )
        break;
      v3 = (*((_DWORD *)this + 105))-- == 1;
      if ( v3 )
      {
        *((_DWORD *)this + 104) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)this + 45);
      }
      v4 = 0;
      v25 = 0;
      v21 = (char *)this + 144;
      v22 = 1;
      AcquireSRWLockShared((PSRWLOCK)this + 18);
      v5 = (_QWORD **)((char *)this + 128);
      if ( *((_QWORD *)this + 17) )
      {
        std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::find(
          (char *)this + 128,
          &v24,
          &v20);
        v6 = *v5;
        v7 = v24;
        if ( v24 == *v5 )
          goto LABEL_24;
        i = (_QWORD *)v24[2];
        if ( *((_BYTE *)i + 25) )
        {
          for ( i = (_QWORD *)v24[1]; !*((_BYTE *)i + 25) && v7 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
            v7 = i;
        }
        else
        {
          v9 = (__int64 *)*i;
          if ( !*(_BYTE *)(*i + 25LL) )
          {
            do
            {
              i = v9;
              v9 = (__int64 *)*v9;
            }
            while ( !*((_BYTE *)v9 + 25) );
          }
        }
        v24 = i;
        if ( i == v6 )
        {
LABEL_24:
          i = (_QWORD *)*v6;
          v24 = (_QWORD *)*v6;
        }
        v10 = i;
        while ( 1 )
        {
          v11 = v10;
          v12 = *(_QWORD *)(v10[6] + 216LL);
          if ( v12 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
            v13 = (__int64 *)Rdp::Avenc::Hevc::CPacketQueue::Dequeue(v12 + 192, &v26);
            v14 = *v13;
            *v13 = 0;
            v4 = v14;
            v25 = v14;
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( v4 )
            break;
          v15 = (__int64 **)v10[2];
          if ( *((_BYTE *)v15 + 25) )
          {
            while ( 1 )
            {
              v10 = (_QWORD *)v10[1];
              if ( *((_BYTE *)v10 + 25) || v11 != (_QWORD *)v10[2] )
                break;
              v11 = v10;
            }
          }
          else
          {
            v10 = (_QWORD *)v10[2];
            for ( j = *v15; !*((_BYTE *)j + 25); j = (__int64 *)*j )
              v10 = j;
          }
          v24 = v10;
          v17 = (_QWORD *)*((_QWORD *)this + 16);
          if ( v10 == v17 )
          {
            v10 = (_QWORD *)*v17;
            v24 = (_QWORD *)*v17;
          }
          if ( v12 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          if ( v10 == i )
            goto LABEL_45;
        }
        v20 = *((_OWORD *)v10 + 2);
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_45:
        ReleaseSRWLockShared((PSRWLOCK)this + 18);
        if ( v4 )
        {
          if ( (unsigned int)mtx_do_lock(v2) )
            std::_Throw_Cpp_error(5);
          if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
          {
            *((_DWORD *)v2 + 19) = 2147483646;
            std::_Throw_Cpp_error(6);
          }
          --*((_DWORD *)this + 125);
          v3 = (*((_DWORD *)v2 + 19))-- == 1;
          if ( v3 )
          {
            *((_DWORD *)v2 + 18) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
          }
          v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 36) + 64LL))(
                  *((_QWORD *)this + 36),
                  v4,
                  0);
          wil::details::in1diag3::Log_IfFailedMsg(
            retaddr,
            (void *)0x3BE,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
            (const char *)v18,
            (int)"Failed to write packet to channel",
            v19);
        }
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      else
      {
        ReleaseSRWLockShared((PSRWLOCK)this + 18);
      }
      if ( !*((_BYTE *)this + 496) )
        return;
    }
    v3 = (*((_DWORD *)this + 105))-- == 1;
    if ( v3 )
    {
      *((_DWORD *)this + 104) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 45);
    }
  }
}

```

## disassembly

```asm
0x180063db0  push    rbp
0x180063db2  push    rbx
0x180063db3  push    rsi
0x180063db4  push    rdi
0x180063db5  push    r12
0x180063db7  push    r13
0x180063db9  push    r14
0x180063dbb  push    r15
0x180063dbd  mov     rbp, rsp
0x180063dc0  sub     rsp, 58h
0x180063dc4  mov     rdi, rcx
0x180063dc7  xor     r15d, r15d
0x180063dca  movups  xmm0, cs:xmmword_180093D68
0x180063dd1  movdqu  [rbp+var_28], xmm0
0x180063dd6  mov     al, [rcx+1F0h]
0x180063ddc  nop
0x180063ddd  test    al, al
0x180063ddf  jz      loc_180064100
0x180063de5  lea     r13, [rcx+158h]
0x180063dec  mov     rcx, r13
0x180063def  call    mtx_do_lock
0x180063df4  test    eax, eax
0x180063df6  jnz     loc_180064142
0x180063dfc  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x180063e04  jz      loc_18006412F
0x180063e0a  lea     rbx, [rdi+168h]
0x180063e11  mov     al, [rdi+1F0h]
0x180063e17  nop
0x180063e18  test    al, al
0x180063e1a  jz      short loc_180063E6C
0x180063e1c  cmp     [rdi+1F4h], r15d
0x180063e23  ja      short loc_180063E6C
0x180063e25  mov     dword ptr [rdi+1A0h], 0FFFFFFFFh
0x180063e2f  dec     dword ptr [rdi+1A4h]
0x180063e35  lea     rdx, [rdi+168h]; SRWLock
0x180063e3c  lea     rcx, [rdi+1B0h]; ConditionVariable
0x180063e43  xor     r9d, r9d; Flags
0x180063e46  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180063e4a  call    cs:__imp_SleepConditionVariableSRW
0x180063e50  test    eax, eax
0x180063e52  jz      loc_18006414D
0x180063e58  call    cs:__imp_GetCurrentThreadId
0x180063e5e  mov     [rdi+1A0h], eax
0x180063e64  inc     dword ptr [rdi+1A4h]
0x180063e6a  jmp     short loc_180063E11
0x180063e6c  mov     al, [rdi+1F0h]
0x180063e72  nop
0x180063e73  test    al, al
0x180063e75  jz      loc_180064111
0x180063e7b  sub     dword ptr [rdi+1A4h], 1
0x180063e82  jnz     short loc_180063E97
0x180063e84  mov     dword ptr [rdi+1A0h], 0FFFFFFFFh
0x180063e8e  mov     rcx, rbx; SRWLock
0x180063e91  call    cs:__imp_ReleaseSRWLockExclusive
0x180063e97  mov     rbx, r15
0x180063e9a  mov     [rbp+arg_10], rbx
0x180063e9e  lea     rsi, [rdi+90h]
0x180063ea5  mov     [rbp+var_18], rsi
0x180063ea9  mov     [rbp+var_10], 1
0x180063ead  mov     rcx, rsi; SRWLock
0x180063eb0  call    cs:__imp_AcquireSRWLockShared
0x180063eb6  nop
0x180063eb7  lea     r14, [rdi+80h]
0x180063ebe  cmp     [r14+8], r15
0x180063ec2  jnz     short loc_180063ED3
0x180063ec4  mov     rcx, rsi; SRWLock
0x180063ec7  call    cs:__imp_ReleaseSRWLockShared
0x180063ecd  nop
0x180063ece  jmp     loc_1800640F1
0x180063ed3  lea     r8, [rbp+var_28]
0x180063ed7  lea     rdx, [rbp+arg_8]
0x180063edb  mov     rcx, r14
0x180063ede  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@UGUIDComparer@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCMonitorContext@Hevc@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>,GUIDComparer,std::allocator<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Hevc::CMonitorContext,wil::err_exception_policy>>>,0>>::find(_GUID const &)
0x180063ee3  mov     rdx, [r14]
0x180063ee6  mov     rax, [rbp+arg_8]
0x180063eea  cmp     rax, rdx
0x180063eed  jz      short loc_180063F35
0x180063eef  mov     r14, [rax+10h]
0x180063ef3  cmp     [r14+19h], r15b
0x180063ef7  jz      short loc_180063F14
0x180063ef9  mov     r14, [rax+8]
0x180063efd  jmp     short loc_180063F0C
0x180063eff  cmp     rax, [r14+10h]
0x180063f03  jnz     short loc_180063F2C
0x180063f05  mov     rax, r14
0x180063f08  mov     r14, [r14+8]
0x180063f0c  cmp     [r14+19h], r15b
0x180063f10  jz      short loc_180063EFF
0x180063f12  jmp     short loc_180063F2C
0x180063f14  mov     rcx, [r14]
0x180063f17  cmp     [rcx+19h], r15b
0x180063f1b  jnz     short loc_180063F2C
0x180063f1d  mov     r14, rcx
0x180063f20  mov     rax, [rcx]
0x180063f23  mov     rcx, rax
0x180063f26  cmp     [rax+19h], r15b
0x180063f2a  jz      short loc_180063F1D
0x180063f2c  mov     [rbp+arg_8], r14
0x180063f30  cmp     r14, rdx
0x180063f33  jnz     short loc_180063F3C
0x180063f35  mov     r14, [rdx]
0x180063f38  mov     [rbp+arg_8], r14
0x180063f3c  mov     rsi, r14
0x180063f3f  mov     r12, rsi
0x180063f42  mov     rax, [rsi+30h]
0x180063f46  mov     r15, [rax+0D8h]
0x180063f4d  mov     [rbp+arg_0], r15
0x180063f51  test    r15, r15
0x180063f54  jz      short loc_180063F66
0x180063f56  mov     rax, [r15]
0x180063f59  mov     rcx, r15
0x180063f5c  mov     rax, [rax+8]
0x180063f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f65  nop
0x180063f66  test    r15, r15
0x180063f69  jz      short loc_180063FB7
0x180063f6b  lea     rcx, [r15+0C0h]
0x180063f72  lea     rdx, [rbp+arg_18]
0x180063f76  call    ?Dequeue@CPacketQueue@Hevc@Avenc@Rdp@@QEAA?AV?$com_ptr_t@UIIoPacket@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Avenc::Hevc::CPacketQueue::Dequeue(void)
0x180063f7b  mov     rdx, [rax]
0x180063f7e  mov     qword ptr [rax], 0
0x180063f85  mov     rcx, rbx
0x180063f88  mov     rbx, rdx
0x180063f8b  mov     [rbp+arg_10], rdx
0x180063f8f  test    rcx, rcx
0x180063f92  jz      short loc_180063FA1
0x180063f94  mov     rax, [rcx]
0x180063f97  mov     rax, [rax+10h]
0x180063f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fa0  nop
0x180063fa1  mov     rcx, [rbp+arg_18]
0x180063fa5  test    rcx, rcx
0x180063fa8  jz      short loc_180063FB7
0x180063faa  mov     rax, [rcx]
0x180063fad  mov     rax, [rax+10h]
0x180063fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fb6  nop
0x180063fb7  test    rbx, rbx
0x180063fba  jnz     short loc_18006402E
0x180063fbc  mov     rcx, [rsi+10h]
0x180063fc0  cmp     [rcx+19h], bl
0x180063fc3  jnz     short loc_180064022
0x180063fc5  mov     rsi, rcx
0x180063fc8  mov     rcx, [rcx]
0x180063fcb  cmp     [rcx+19h], bl
0x180063fce  jnz     short loc_180063FDF
0x180063fd0  mov     rsi, rcx
0x180063fd3  mov     rax, [rcx]
0x180063fd6  mov     rcx, rax
0x180063fd9  cmp     byte ptr [rax+19h], 0
0x180063fdd  jz      short loc_180063FD0
0x180063fdf  mov     [rbp+arg_8], rsi
0x180063fe3  mov     rax, [rdi+80h]
0x180063fea  cmp     rsi, rax
0x180063fed  jnz     short loc_180063FF6
0x180063fef  mov     rsi, [rax]
0x180063ff2  mov     [rbp+arg_8], rsi
0x180063ff6  mov     r12, rsi
0x180063ff9  test    r15, r15
0x180063ffc  jz      short loc_18006400E
0x180063ffe  mov     rax, [r15]
0x180064001  mov     rcx, r15
0x180064004  mov     rax, [rax+10h]
0x180064008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006400d  nop
0x18006400e  cmp     r12, r14
0x180064011  jnz     loc_180063F3F
0x180064017  jmp     short loc_18006404C
0x180064019  cmp     r12, [rsi+10h]
0x18006401d  jnz     short loc_180063FDF
0x18006401f  mov     r12, rsi
0x180064022  mov     rsi, [rsi+8]
0x180064026  cmp     byte ptr [rsi+19h], 0
0x18006402a  jz      short loc_180064019
0x18006402c  jmp     short loc_180063FDF
0x18006402e  movups  xmm0, xmmword ptr [rsi+20h]
0x180064032  movdqu  [rbp+var_28], xmm0
0x180064037  test    r15, r15
0x18006403a  jz      short loc_18006404C
0x18006403c  mov     rax, [r15]
0x18006403f  mov     rcx, r15
0x180064042  mov     rax, [rax+10h]
0x180064046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006404b  nop
0x18006404c  lea     rcx, [rdi+90h]; SRWLock
0x180064053  call    cs:__imp_ReleaseSRWLockShared
0x180064059  xor     r15d, r15d
0x18006405c  test    rbx, rbx
0x18006405f  jz      short loc_1800640DC
0x180064061  mov     rcx, r13
0x180064064  call    mtx_do_lock
0x180064069  test    eax, eax
0x18006406b  jnz     loc_180064166
0x180064071  cmp     dword ptr [r13+4Ch], 7FFFFFFFh
0x180064079  jz      loc_180064153
0x18006407f  dec     dword ptr [rdi+1F4h]
0x180064085  sub     dword ptr [r13+4Ch], 1
0x18006408a  jnz     short loc_18006409E
0x18006408c  mov     dword ptr [r13+48h], 0FFFFFFFFh
0x180064094  lea     rcx, [r13+10h]; SRWLock
0x180064098  call    cs:__imp_ReleaseSRWLockExclusive
0x18006409e  mov     rcx, [rdi+120h]
0x1800640a5  mov     rax, [rcx]
0x1800640a8  xor     r8d, r8d
0x1800640ab  mov     rdx, rbx
0x1800640ae  mov     rax, [rax+40h]
0x1800640b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640b7  mov     rcx, [rbp+40h]; this
0x1800640bb  lea     rdx, aFailedToWriteP; "Failed to write packet to channel"
0x1800640c2  mov     qword ptr [rsp+58h+var_38], rdx; int
0x1800640c7  mov     r9d, eax; char *
0x1800640ca  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800640d1  mov     edx, 3BEh; void *
0x1800640d6  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800640db  nop
0x1800640dc  test    rbx, rbx
0x1800640df  jz      short loc_1800640F1
0x1800640e1  mov     rax, [rbx]
0x1800640e4  mov     rcx, rbx
0x1800640e7  mov     rax, [rax+10h]
0x1800640eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800640f0  nop
0x1800640f1  mov     al, [rdi+1F0h]
0x1800640f7  nop
0x1800640f8  test    al, al
0x1800640fa  jnz     loc_180063DEC
0x180064100  add     rsp, 58h
0x180064104  pop     r15
0x180064106  pop     r14
0x180064108  pop     r13
0x18006410a  pop     r12
0x18006410c  pop     rdi
0x18006410d  pop     rsi
0x18006410e  pop     rbx
0x18006410f  pop     rbp
0x180064110  retn
0x180064111  sub     dword ptr [rdi+1A4h], 1
0x180064118  jnz     short loc_180064100
0x18006411a  mov     dword ptr [rdi+1A0h], 0FFFFFFFFh
0x180064124  mov     rcx, rbx; SRWLock
0x180064127  call    cs:__imp_ReleaseSRWLockExclusive
0x18006412d  jmp     short loc_180064100
0x18006412f  mov     dword ptr [r13+4Ch], 7FFFFFFEh
0x180064137  mov     ecx, 6; int
0x18006413c  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180064142  mov     ecx, 5; int
0x180064147  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18006414d  call    abort
0x180064153  mov     dword ptr [r13+4Ch], 7FFFFFFEh
0x18006415b  mov     ecx, 6; int
0x180064160  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180064166  mov     ecx, 5; int
0x18006416b  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
