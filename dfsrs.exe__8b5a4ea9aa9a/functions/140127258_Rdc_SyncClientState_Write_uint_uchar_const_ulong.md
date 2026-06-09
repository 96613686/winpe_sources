# Rdc::SyncClientState::Write(uint,uchar const *,ulong)

- ea: `0x140127258`
- end: `0x140127770`
- name: `?Write@SyncClientState@Rdc@@QEAAPEAVFrsStatus@@IPEBEK@Z`
- size: `1304`
- prototype: `struct FrsStatus *__fastcall(Rdc::SyncClientState *__hidden this, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1401215ec`
- `0x140127778`

## callees

- `0x14000bbc5`
- `0x1401215ec`
- `0x140123284`
- `0x14012369c`
- `0x140123ac0`
- `0x140123d5c`
- `0x140127258`
- `0x1401b9494`
- `0x140206a40`
- `0x140206b08`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1401272bc`
- `KERNEL32!GetCurrentThreadId` at `0x1401273ea`
- `KERNEL32!GetCurrentThreadId` at `0x14012747d`
- `KERNEL32!GetCurrentThreadId` at `0x140127508`
- `KERNEL32!GetCurrentThreadId` at `0x140127554`
- `KERNEL32!GetCurrentThreadId` at `0x1401276cd`
- `KERNEL32!GetCurrentThreadId` at `0x14012770d`
- `KERNEL32!GetCurrentThreadId` at `0x1401272bc`
- `KERNEL32!GetCurrentThreadId` at `0x1401273ea`
- `KERNEL32!GetCurrentThreadId` at `0x14012747d`
- `KERNEL32!GetCurrentThreadId` at `0x140127508`
- `KERNEL32!GetCurrentThreadId` at `0x140127554`
- `KERNEL32!GetCurrentThreadId` at `0x1401276cd`
- `KERNEL32!GetCurrentThreadId` at `0x14012770d`

## string_xrefs

- `0x1401272d8`: `Rdc::SyncClientState::Write`
- `0x14012749f`: `Rdc::SyncClientState::Write`
- `0x140127518`: `Rdc::SyncClientState::Write`
- `0x14012757c`: `Rdc::SyncClientState::Write`
- `0x1401276b7`: `Rdc::SyncClientState::Write`

## pseudocode

```c
struct FrsStatus *__fastcall Rdc::SyncClientState::Write(
        Rdc::SyncClientState *this,
        _QWORD *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  __int64 v4; // rsi
  unsigned int v5; // ebx
  struct FrsStatus *v7; // r14
  unsigned __int64 v8; // rbp
  int v9; // edi
  char v10; // r15
  __int64 v11; // r12
  unsigned __int64 v12; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v14; // rcx
  __int64 v15; // r9
  __int64 v16; // rax
  int v17; // eax
  DWORD v18; // eax
  __int64 v19; // rcx
  struct FrsStatus *v20; // rax
  __int64 v21; // rax
  DWORD v22; // eax
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  _DWORD *v28; // rax
  const unsigned __int8 *v29; // r15
  unsigned int v30; // edi
  __int64 v31; // rcx
  __int64 v32; // rax
  DWORD v33; // eax
  __int64 v34; // rcx
  DWORD v35; // eax
  __int64 v36; // rcx
  unsigned int v38; // [rsp+50h] [rbp-68h] BYREF
  int v39; // [rsp+54h] [rbp-64h]
  unsigned int v40; // [rsp+58h] [rbp-60h]
  const unsigned __int8 *v41; // [rsp+60h] [rbp-58h] BYREF
  unsigned __int64 v42[10]; // [rsp+68h] [rbp-50h] BYREF
  char v43; // [rsp+C0h] [rbp+8h]
  unsigned int v44; // [rsp+C8h] [rbp+10h]
  const unsigned __int8 *Src; // [rsp+D0h] [rbp+18h]
  unsigned int v46; // [rsp+D8h] [rbp+20h]

  v46 = a4;
  Src = a3;
  v44 = (unsigned int)a2;
  v4 = 0;
  v5 = a4;
  *((_QWORD *)this + 9) += a4;
  v7 = 0;
  v8 = *((_QWORD *)this + 8) + ((unsigned __int64)(unsigned int)((_DWORD)a2 - 1) << 7);
  LOBYTE(v9) = 0;
  v10 = 0;
  v43 = 0;
  v40 = (_DWORD)a2 - 1;
  v11 = *(_QWORD *)(v8 + 8) + 1160LL;
  v12 = a4 + *(_QWORD *)(v8 + 48);
  if ( v12 <= *(_QWORD *)(v8 + 40) )
  {
    *(_QWORD *)(v8 + 48) = v12;
  }
  else
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v14,
                               9035,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                               "Rdc::SyncClientState::Write",
                               2039,
                               CurrentThreadId,
                               0);
  }
  v15 = 1;
  if ( !v5 )
  {
    a3 = *(const unsigned __int8 **)v8;
    if ( *(_QWORD *)v8 )
    {
      a2 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v11 + 16) + 64LL) + 416LL);
      *(_QWORD *)(a2[4] + 8LL * a2[3]) = a3;
      v16 = 0;
      if ( a2[3] + 1LL != *a2 )
        v16 = a2[3] + 1LL;
      a2[3] = v16;
      *(_QWORD *)v8 = 0;
    }
    *(_BYTE *)(*(_QWORD *)(v11 + 16) + 96LL) = 1;
    *(_BYTE *)(v11 + 32) = 1;
  }
  while ( 2 )
  {
    if ( !v7 && !**(_DWORD **)this && !(_BYTE)v9 )
    {
      do
      {
        switch ( *(_DWORD *)(v11 + 8) )
        {
          case 0x10:
            v17 = RDCLibFree::StreamPipe<Win32ReaderIndexCompareWrapper::StreamPipeTraits>::ProcessData(
                    v11,
                    a2,
                    a3,
                    v15);
            break;
          case 0x11:
            v17 = RDCLibFree::StreamPipe<Win32ReaderIndexCompareWrapper::StreamPipeTraits>::ProcessSecond(
                    v11,
                    a2,
                    a3,
                    v15);
            break;
          case 0x12:
LABEL_26:
            v10 = 1;
            v7 = Rdc::SyncClientState::Flush(this, v40);
            v43 = 1;
            if ( v7 )
              goto LABEL_52;
            goto LABEL_27;
          default:
            goto LABEL_23;
        }
        v15 = 1;
      }
      while ( v17 == 1 );
      if ( v17 == 2 )
      {
        v20 = Rdc::SyncClientState::ProcessNeeds(this, v44);
        goto LABEL_34;
      }
      if ( v17 == 3 )
      {
        v28 = *(_DWORD **)this;
        v9 = (unsigned __int8)v9;
        if ( !v5 )
          v9 = 1;
        v39 = v9;
        if ( !*v28 )
        {
          do
          {
            if ( !v5 )
              break;
            v41 = *(const unsigned __int8 **)v8;
            v29 = v41;
            *(_QWORD *)v8 = 0;
            if ( !v29 )
            {
              if ( !(unsigned __int8)RDCLibFree::TwoQueue<RDCLibFree::ChunkSignature<RDCLibFree::MD4Wrapper::Digest> *>::PopOldest(
                                       *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v11 + 16) + 64LL) + 416LL),
                                       &v41) )
                break;
              v29 = v41;
              *((_QWORD *)v41 + 2) = *(_QWORD *)v41;
            }
            v30 = *((_DWORD *)v29 + 2) - *((_DWORD *)v29 + 4);
            if ( v5 < v30 )
              v30 = v5;
            memcpy_0(*((void **)v29 + 2), Src, v30);
            *((_QWORD *)v29 + 2) += v30;
            v31 = *((_QWORD *)v29 + 2);
            v46 -= v30;
            Src += v30;
            if ( *((_QWORD *)v29 + 1) == v31 )
            {
              *(_QWORD *)(v8 + 56) += v31 - *(_QWORD *)v29;
              a2 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(v11 + 16) + 64LL) + 416LL);
              *(_QWORD *)(a2[4] + 8LL * a2[3]) = v29;
              v32 = 0;
              if ( a2[3] + 1LL != *a2 )
                v32 = a2[3] + 1LL;
              a2[3] = v32;
            }
            else
            {
              *(_QWORD *)v8 = v29;
            }
            v5 = v46;
          }
          while ( !**(_DWORD **)this );
          LOBYTE(v9) = v39;
          v10 = v43;
        }
        goto LABEL_51;
      }
      if ( v17 != 4 )
      {
        if ( v17 != 5 )
        {
          if ( v17 != 6 )
            goto LABEL_51;
LABEL_23:
          v41 = *(const unsigned __int8 **)v11;
          if ( (_DWORD)v41 == 10 )
          {
            v18 = GetCurrentThreadId();
            v20 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v19,
                                        HIDWORD(v41),
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                        "Rdc::SyncClientState::Write",
                                        2106,
                                        v18,
                                        0);
          }
          else
          {
            v26 = GetCurrentThreadId();
            v20 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                        v27,
                                        9035,
                                        0,
                                        3,
                                        "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                        "Rdc::SyncClientState::Write",
                                        2109,
                                        v26,
                                        0);
          }
LABEL_34:
          v7 = v20;
          goto LABEL_51;
        }
        goto LABEL_26;
      }
LABEL_27:
      v21 = *(_QWORD *)(v8 + 96);
      v38 = 0;
      v42[0] = 0;
      if ( !SignatureIndexFile::WriteSignatures(
              *(SignatureIndexFile **)(v8 + 112),
              v44,
              *(const unsigned __int8 **)v21,
              *(_QWORD *)(v21 + 16) - *(_QWORD *)v21,
              v42,
              &v38) )
      {
        v22 = GetCurrentThreadId();
        v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v23,
                                   v38,
                                   0,
                                   1,
                                   "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                   "Rdc::SyncClientState::Write",
                                   2133,
                                   v22,
                                   0);
      }
      *(_QWORD *)(*(_QWORD *)(v8 + 96) + 16LL) = **(_QWORD **)(v8 + 96);
      if ( !v7 )
      {
        if ( !v10 )
          continue;
        if ( !SignatureIndexFile::WriteHeader(*(SignatureIndexFile **)(v8 + 112), v44, 1, &v38) )
        {
          v24 = GetCurrentThreadId();
          v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                                     v25,
                                     v38,
                                     0,
                                     1,
                                     "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                     "Rdc::SyncClientState::Write",
                                     2139,
                                     v24,
                                     0);
        }
        break;
      }
LABEL_51:
      if ( !v10 )
        continue;
    }
    break;
  }
LABEL_52:
  if ( **(_DWORD **)this )
  {
    if ( v7 )
    {
LABEL_56:
      v35 = GetCurrentThreadId();
      return (struct FrsStatus *)FrsStatusList::PushNewError(
                                   v36,
                                   *((unsigned int *)v7 + 1),
                                   *((unsigned int *)v7 + 2),
                                   *(unsigned int *)v7,
                                   "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                   "Rdc::SyncClientState::Write",
                                   2153,
                                   v35,
                                   v7);
    }
    v33 = GetCurrentThreadId();
    v7 = (struct FrsStatus *)FrsStatusList::PushNewError(
                               v34,
                               9033,
                               0,
                               3,
                               "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                               "Rdc::SyncClientState::Write",
                               2151,
                               v33,
                               0);
  }
  if ( v7 )
    goto LABEL_56;
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x140127258  mov     [rsp+arg_18], r9d
0x14012725d  mov     [rsp+Src], r8
0x140127262  mov     [rsp+arg_8], edx
0x140127266  push    rbx
0x140127267  push    rbp
0x140127268  push    rsi
0x140127269  push    rdi
0x14012726a  push    r12
0x14012726c  push    r13
0x14012726e  push    r14
0x140127270  push    r15
0x140127272  sub     rsp, 78h
0x140127276  xor     esi, esi
0x140127278  mov     ebx, r9d
0x14012727b  add     [rcx+48h], rbx
0x14012727f  lea     eax, [rdx-1]
0x140127282  mov     r13, rcx
0x140127285  mov     ebp, eax
0x140127287  shl     rbp, 7
0x14012728b  mov     r14d, esi
0x14012728e  add     rbp, [rcx+40h]
0x140127292  mov     dil, sil
0x140127295  mov     r15b, sil
0x140127298  mov     [rsp+0B8h+arg_0], sil
0x1401272a0  mov     [rsp+0B8h+var_60], eax
0x1401272a4  mov     r12, [rbp+8]
0x1401272a8  mov     rcx, [rbp+30h]
0x1401272ac  add     r12, 488h
0x1401272b3  add     rcx, rbx
0x1401272b6  cmp     rcx, [rbp+28h]
0x1401272ba  jbe     short loc_140127307
0x1401272bc  call    cs:__imp_GetCurrentThreadId
0x1401272c3  nop     dword ptr [rax+rax+00h]
0x1401272c8  mov     [rsp+0B8h+var_78], rsi
0x1401272cd  lea     r9d, [rsi+3]
0x1401272d1  mov     [rsp+0B8h+var_80], eax
0x1401272d5  xor     r8d, r8d
0x1401272d8  lea     rax, aRdcSyncclients_0; "Rdc::SyncClientState::Write"
0x1401272df  mov     [rsp+0B8h+var_88], 7F7h
0x1401272e7  mov     [rsp+0B8h+var_90], rax
0x1401272ec  mov     edx, 234Bh
0x1401272f1  lea     rax, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x1401272f8  mov     [rsp+0B8h+var_98], rax
0x1401272fd  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140127302  mov     r14, rax
0x140127305  jmp     short loc_14012730B
0x140127307  mov     [rbp+30h], rcx
0x14012730b  mov     r9d, 1
0x140127311  test    ebx, ebx
0x140127313  jnz     short loc_140127361
0x140127315  mov     r8, [rbp+0]
0x140127319  test    r8, r8
0x14012731c  jz      short loc_140127353
0x14012731e  mov     rax, [r12+10h]
0x140127323  mov     rcx, [rax+40h]
0x140127327  mov     rdx, [rcx+1A0h]
0x14012732e  mov     rcx, [rdx+18h]
0x140127332  mov     rax, [rdx+20h]
0x140127336  mov     [rax+rcx*8], r8
0x14012733a  mov     rax, rsi
0x14012733d  mov     rcx, [rdx+18h]
0x140127341  inc     rcx
0x140127344  cmp     rcx, [rdx]
0x140127347  cmovnz  rax, rcx
0x14012734b  mov     [rdx+18h], rax
0x14012734f  mov     [rbp+0], rsi
0x140127353  mov     rax, [r12+10h]
0x140127358  mov     [rax+60h], r9b
0x14012735c  mov     [r12+20h], r9b
0x140127361  test    r14, r14
0x140127364  jnz     loc_1401276B0
0x14012736a  mov     rax, [r13+0]
0x14012736e  mov     ecx, [rax]
0x140127370  test    ecx, ecx
0x140127372  jnz     loc_1401276B0
0x140127378  test    dil, dil
0x14012737b  jnz     loc_1401276B0
0x140127381  mov     ecx, [r12+8]
0x140127386  sub     ecx, 10h
0x140127389  jz      short loc_14012739E
0x14012738b  sub     ecx, 1
0x14012738e  jnz     loc_140127416
0x140127394  mov     rcx, r12
0x140127397  call    ?ProcessSecond@?$StreamPipe@VStreamPipeTraits@Win32ReaderIndexCompareWrapper@@@RDCLibFree@@AEAA?AW4ProcessAction@FilterBase@2@XZ; RDCLibFree::StreamPipe<Win32ReaderIndexCompareWrapper::StreamPipeTraits>::ProcessSecond(void)
0x14012739c  jmp     short loc_1401273A6
0x14012739e  mov     rcx, r12
0x1401273a1  call    ?ProcessData@?$StreamPipe@VStreamPipeTraits@Win32ReaderIndexCompareWrapper@@@RDCLibFree@@AEAA?AW4ProcessAction@FilterBase@2@XZ; RDCLibFree::StreamPipe<Win32ReaderIndexCompareWrapper::StreamPipeTraits>::ProcessData(void)
0x1401273a6  mov     r9d, 1
0x1401273ac  mov     ecx, eax
0x1401273ae  cmp     eax, r9d
0x1401273b1  jz      short loc_140127381
0x1401273b3  sub     ecx, 2
0x1401273b6  jz      loc_14012775C
0x1401273bc  sub     ecx, r9d
0x1401273bf  jz      loc_1401275A4
0x1401273c5  sub     ecx, r9d
0x1401273c8  jz      short loc_14012743E
0x1401273ca  sub     ecx, r9d
0x1401273cd  jz      short loc_14012741B
0x1401273cf  cmp     ecx, r9d
0x1401273d2  jnz     loc_1401276A7
0x1401273d8  mov     rax, [r12]
0x1401273dc  mov     [rsp+0B8h+var_58], rax
0x1401273e1  cmp     eax, 0Ah
0x1401273e4  jnz     loc_140127554
0x1401273ea  call    cs:__imp_GetCurrentThreadId
0x1401273f1  nop     dword ptr [rax+rax+00h]
0x1401273f6  mov     edx, dword ptr [rsp+0B8h+var_58+4]
0x1401273fa  mov     r9d, 1
0x140127400  mov     [rsp+0B8h+var_78], rsi
0x140127405  mov     [rsp+0B8h+var_80], eax
0x140127409  mov     [rsp+0B8h+var_88], 83Ah
0x140127411  jmp     loc_14012757C
0x140127416  cmp     ecx, 1
0x140127419  jnz     short loc_1401273D8
0x14012741b  mov     edx, [rsp+0B8h+var_60]; unsigned int
0x14012741f  mov     rcx, r13; this
0x140127422  call    ?Flush@SyncClientState@Rdc@@QEAAPEAVFrsStatus@@I@Z; Rdc::SyncClientState::Flush(uint)
0x140127427  mov     r15b, 1
0x14012742a  mov     r14, rax
0x14012742d  mov     [rsp+0B8h+arg_0], r15b
0x140127435  test    rax, rax
0x140127438  jnz     loc_1401276B0
0x14012743e  mov     rax, [rbp+60h]
0x140127442  lea     rcx, [rsp+0B8h+var_68]
0x140127447  mov     edx, [rsp+0B8h+arg_8]; unsigned int
0x14012744e  mov     [rsp+0B8h+var_90], rcx; unsigned int *
0x140127453  lea     rcx, [rsp+0B8h+var_50]
0x140127458  mov     [rsp+0B8h+var_68], esi
0x14012745c  mov     [rsp+0B8h+var_50], rsi
0x140127461  mov     r9, [rax+10h]
0x140127465  sub     r9, [rax]; unsigned __int64
0x140127468  mov     r8, [rax]; unsigned __int8 *
0x14012746b  mov     [rsp+0B8h+var_98], rcx; unsigned __int64 *
0x140127470  mov     rcx, [rbp+70h]; this
0x140127474  call    ?WriteSignatures@SignatureIndexFile@@QEAA_NIPEBE_KAEA_KAEAK@Z; SignatureIndexFile::WriteSignatures(uint,uchar const *,unsigned __int64,unsigned __int64 &,ulong &)
0x140127479  test    al, al
0x14012747b  jnz     short loc_1401274C7
0x14012747d  call    cs:__imp_GetCurrentThreadId
0x140127484  nop     dword ptr [rax+rax+00h]
0x140127489  mov     edx, [rsp+0B8h+var_68]
0x14012748d  mov     r9d, 1
0x140127493  mov     [rsp+0B8h+var_78], rsi
0x140127498  xor     r8d, r8d
0x14012749b  mov     [rsp+0B8h+var_80], eax
0x14012749f  lea     rax, aRdcSyncclients_0; "Rdc::SyncClientState::Write"
0x1401274a6  mov     [rsp+0B8h+var_88], 855h
0x1401274ae  mov     [rsp+0B8h+var_90], rax
0x1401274b3  lea     rax, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x1401274ba  mov     [rsp+0B8h+var_98], rax
0x1401274bf  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401274c4  mov     r14, rax
0x1401274c7  mov     rcx, [rbp+60h]
0x1401274cb  mov     rax, [rcx]
0x1401274ce  mov     [rcx+10h], rax
0x1401274d2  test    r14, r14
0x1401274d5  jnz     loc_1401276A7
0x1401274db  test    r15b, r15b
0x1401274de  jz      loc_140127361
0x1401274e4  mov     edx, [rsp+0B8h+arg_8]; unsigned int
0x1401274eb  lea     ebx, [r14+1]
0x1401274ef  mov     rcx, [rbp+70h]; this
0x1401274f3  lea     r9, [rsp+0B8h+var_68]; unsigned int *
0x1401274f8  mov     r8b, bl; bool
0x1401274fb  call    ?WriteHeader@SignatureIndexFile@@QEAA_NI_NAEAK@Z; SignatureIndexFile::WriteHeader(uint,bool,ulong &)
0x140127500  test    al, al
0x140127502  jnz     loc_1401276B0
0x140127508  call    cs:__imp_GetCurrentThreadId
0x14012750f  nop     dword ptr [rax+rax+00h]
0x140127514  mov     edx, [rsp+0B8h+var_68]
0x140127518  lea     rdi, aRdcSyncclients_0; "Rdc::SyncClientState::Write"
0x14012751f  mov     [rsp+0B8h+var_78], rsi
0x140127524  lea     rbp, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x14012752b  mov     [rsp+0B8h+var_80], eax
0x14012752f  mov     r9d, ebx
0x140127532  mov     [rsp+0B8h+var_88], 85Bh
0x14012753a  xor     r8d, r8d
0x14012753d  mov     [rsp+0B8h+var_90], rdi
0x140127542  mov     [rsp+0B8h+var_98], rbp
0x140127547  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012754c  mov     r14, rax
0x14012754f  jmp     loc_1401276BE
0x140127554  call    cs:__imp_GetCurrentThreadId
0x14012755b  nop     dword ptr [rax+rax+00h]
0x140127560  mov     [rsp+0B8h+var_78], rsi
0x140127565  mov     r9d, 3
0x14012756b  mov     [rsp+0B8h+var_80], eax
0x14012756f  mov     edx, 234Bh
0x140127574  mov     [rsp+0B8h+var_88], 83Dh
0x14012757c  lea     rax, aRdcSyncclients_0; "Rdc::SyncClientState::Write"
0x140127583  xor     r8d, r8d
0x140127586  mov     [rsp+0B8h+var_90], rax
0x14012758b  lea     rax, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x140127592  mov     [rsp+0B8h+var_98], rax
0x140127597  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x14012759c  mov     r14, rax
0x14012759f  jmp     loc_1401276A7
0x1401275a4  mov     rax, [r13+0]
0x1401275a8  test    ebx, ebx
0x1401275aa  movzx   edi, dil
0x1401275ae  cmovz   edi, r9d
0x1401275b2  mov     [rsp+0B8h+var_64], edi
0x1401275b6  mov     ecx, [rax]
0x1401275b8  test    ecx, ecx
0x1401275ba  jnz     loc_1401276A7
0x1401275c0  test    ebx, ebx
0x1401275c2  jz      loc_14012769B
0x1401275c8  mov     r15, [rbp+0]
0x1401275cc  mov     [rsp+0B8h+var_58], r15
0x1401275d1  mov     [rbp+0], rsi
0x1401275d5  test    r15, r15
0x1401275d8  jnz     short loc_140127608
0x1401275da  mov     rax, [r12+10h]
0x1401275df  lea     rdx, [rsp+0B8h+var_58]
0x1401275e4  mov     rcx, [rax+40h]
0x1401275e8  mov     rcx, [rcx+1A0h]
0x1401275ef  call    ?PopOldest@?$TwoQueue@PEAU?$ChunkSignature@UDigest@MD4Wrapper@RDCLibFree@@@RDCLibFree@@@RDCLibFree@@QEAA_NAEAPEAU?$ChunkSignature@UDigest@MD4Wrapper@RDCLibFree@@@2@@Z; RDCLibFree::TwoQueue<RDCLibFree::ChunkSignature<RDCLibFree::MD4Wrapper::Digest> *>::PopOldest(RDCLibFree::ChunkSignature<RDCLibFree::MD4Wrapper::Digest> * &)
0x1401275f4  test    al, al
0x1401275f6  jz      loc_14012769B
0x1401275fc  mov     r15, [rsp+0B8h+var_58]
0x140127601  mov     rax, [r15]
0x140127604  mov     [r15+10h], rax
0x140127608  mov     edi, [r15+8]
0x14012760c  sub     edi, [r15+10h]
0x140127610  mov     rdx, [rsp+0B8h+Src]; Src
0x140127618  cmp     ebx, edi
0x14012761a  mov     rcx, [r15+10h]; void *
0x14012761e  cmovb   edi, ebx
0x140127621  mov     r8d, edi; Size
0x140127624  mov     ebx, edi
0x140127626  call    memcpy_0
0x14012762b  add     [r15+10h], rbx
0x14012762f  mov     rcx, [r15+10h]
0x140127633  sub     [rsp+0B8h+arg_18], edi
0x14012763a  add     [rsp+0B8h+Src], rbx
0x140127642  cmp     [r15+8], rcx
0x140127646  jnz     short loc_140127682
0x140127648  sub     rcx, [r15]
0x14012764b  add     [rbp+38h], rcx
0x14012764f  mov     rax, [r12+10h]
0x140127654  mov     rcx, [rax+40h]
0x140127658  mov     rdx, [rcx+1A0h]
0x14012765f  mov     rcx, [rdx+18h]
0x140127663  mov     rax, [rdx+20h]
0x140127667  mov     [rax+rcx*8], r15
0x14012766b  mov     rax, rsi
0x14012766e  mov     rcx, [rdx+18h]
0x140127672  inc     rcx
0x140127675  cmp     rcx, [rdx]
0x140127678  cmovnz  rax, rcx
0x14012767c  mov     [rdx+18h], rax
0x140127680  jmp     short loc_140127686
0x140127682  mov     [rbp+0], r15
0x140127686  mov     rax, [r13+0]
0x14012768a  mov     ebx, [rsp+0B8h+arg_18]
0x140127691  mov     ecx, [rax]
0x140127693  test    ecx, ecx
0x140127695  jz      loc_1401275C0
0x14012769b  mov     edi, [rsp+0B8h+var_64]
0x14012769f  mov     r15b, [rsp+0B8h+arg_0]
0x1401276a7  test    r15b, r15b
0x1401276aa  jz      loc_140127361
0x1401276b0  lea     rbp, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x1401276b7  lea     rdi, aRdcSyncclients_0; "Rdc::SyncClientState::Write"
0x1401276be  mov     rax, [r13+0]
0x1401276c2  mov     ecx, [rax]
0x1401276c4  test    ecx, ecx
0x1401276c6  jz      short loc_140127708
0x1401276c8  test    r14, r14
0x1401276cb  jnz     short loc_14012770D
0x1401276cd  call    cs:__imp_GetCurrentThreadId
0x1401276d4  nop     dword ptr [rax+rax+00h]
0x1401276d9  mov     [rsp+0B8h+var_78], rsi
0x1401276de  lea     r9d, [r14+3]
0x1401276e2  mov     [rsp+0B8h+var_80], eax
0x1401276e6  xor     r8d, r8d
0x1401276e9  mov     [rsp+0B8h+var_88], 867h
0x1401276f1  mov     edx, 2349h
0x1401276f6  mov     [rsp+0B8h+var_90], rdi
0x1401276fb  mov     [rsp+0B8h+var_98], rbp
0x140127700  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140127705  mov     r14, rax
0x140127708  test    r14, r14
0x14012770b  jz      short loc_140127747
0x14012770d  call    cs:__imp_GetCurrentThreadId
0x140127714  nop     dword ptr [rax+rax+00h]
0x140127719  mov     r9d, [r14]
0x14012771c  mov     r8d, [r14+8]
0x140127720  mov     edx, [r14+4]
0x140127724  mov     [rsp+0B8h+var_78], r14
0x140127729  mov     [rsp+0B8h+var_80], eax
0x14012772d  mov     [rsp+0B8h+var_88], 869h
0x140127735  mov     [rsp+0B8h+var_90], rdi
0x14012773a  mov     [rsp+0B8h+var_98], rbp
0x14012773f  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140127744  mov     rsi, rax
0x140127747  mov     rax, rsi
0x14012774a  add     rsp, 78h
0x14012774e  pop     r15
0x140127750  pop     r14
  ... truncated ...
```
