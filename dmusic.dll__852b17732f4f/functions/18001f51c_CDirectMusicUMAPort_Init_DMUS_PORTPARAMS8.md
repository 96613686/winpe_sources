# CDirectMusicUMAPort::Init(_DMUS_PORTPARAMS8 *)

- ea: `0x18001f51c`
- end: `0x18001f9a4`
- name: `?Init@CDirectMusicUMAPort@@QEAAJPEAU_DMUS_PORTPARAMS8@@@Z`
- size: `1160`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, struct _DMUS_PORTPARAMS8 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x18001e008`

## callees

- `0x1800012d0`
- `0x1800016d0`
- `0x1800021a8`
- `0x18000a974`
- `0x180016080`
- `0x180016184`
- `0x18001dd40`
- `0x18001f170`
- `0x18001f51c`
- `0x18001f9ac`
- `0x18001fdd8`
- `0x180020b40`
- `0x1800210d0`
- `0x180021254`
- `0x180022010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f7d0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18001f7d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f881`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18001f881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f893`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f8bf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f8bf`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::Init(CDirectMusicUMAPort *this, struct _DMUS_PORTPARAMS8 *a2)
{
  void *v4; // rax
  __int64 result; // rax
  __int64 v6; // rcx
  int DefaultMasterClock; // ebx
  void **v8; // r12
  int v9; // r13d
  void *v10; // rcx
  BOOL fShare; // eax
  DWORD LastError; // eax
  DWORD v13; // eax
  int v14; // ecx
  DWORD v15; // edx
  DWORD v16; // r8d
  DWORD v17; // r9d
  DWORD v18; // r10d
  DWORD v19; // r11d
  DWORD *v20; // rbx
  unsigned int v21; // r14d
  unsigned int i; // esi
  __int64 v23; // rbx
  _QWORD *v24; // rax
  void *v25; // rcx
  int v26; // edx
  int v27; // eax
  HANDLE EventA; // rax
  DWORD v29; // eax
  HANDLE Thread; // rax
  __int64 v31; // rcx
  DWORD ThreadId[2]; // [rsp+30h] [rbp-89h] BYREF
  __int64 v33; // [rsp+38h] [rbp-81h] BYREF
  __int64 v34; // [rsp+40h] [rbp-79h] BYREF
  _OWORD v35[2]; // [rsp+48h] [rbp-71h] BYREF
  struct KSIDENTIFIER v36; // [rsp+70h] [rbp-49h] BYREF
  int v37; // [rsp+88h] [rbp-31h]
  int v38; // [rsp+8Ch] [rbp-2Dh]
  DWORD dwValidParams; // [rsp+90h] [rbp-29h]
  DWORD dwVoices; // [rsp+94h] [rbp-25h]
  DWORD dwChannelGroups; // [rsp+98h] [rbp-21h]
  DWORD dwAudioChannels; // [rsp+9Ch] [rbp-1Dh]
  DWORD dwSampleRate; // [rsp+A0h] [rbp-19h]
  DWORD dwEffectFlags; // [rsp+A4h] [rbp-15h]
  BOOL v45; // [rsp+A8h] [rbp-11h]
  int v46; // [rsp+ACh] [rbp-Dh]
  int v47; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v48; // [rsp+B4h] [rbp-5h]
  int v49; // [rsp+C4h] [rbp+Bh]
  int v50; // [rsp+C8h] [rbp+Fh]

  v4 = operator new[](0x180u);
  *((_QWORD *)this + 4446) = v4;
  if ( !v4 )
    return 2147942414LL;
  v6 = *((_QWORD *)this + 53);
  v49 = 0;
  v48 = 0;
  v50 = 4096;
  v47 = 28;
  result = (*(__int64 (__fastcall **)(__int64, int *, char *, _QWORD))(*(_QWORD *)v6 + 32LL))(
             v6,
             &v47,
             (char *)this + 35560,
             0);
  if ( (int)result >= 0 )
  {
    memset_0(*((void **)this + 4446), 0, 0x180u);
    DefaultMasterClock = FilterInstantiate((const unsigned __int16 *)this + 394, (void **)this + 164);
    if ( DefaultMasterClock < 0 )
      goto LABEL_9;
    v8 = (void **)((char *)this + 1320);
    DefaultMasterClock = CDirectMusicUMAPort::InstantiatePin(this, *((_DWORD *)this + 326), (void **)this + 165);
    if ( DefaultMasterClock < 0 )
      goto LABEL_9;
    v9 = 0;
    if ( a2 )
    {
      v10 = *v8;
      v37 = *((_DWORD *)this + 327);
      dwValidParams = a2->dwValidParams;
      dwVoices = a2->dwVoices;
      dwChannelGroups = a2->dwChannelGroups;
      dwAudioChannels = a2->dwAudioChannels;
      dwSampleRate = a2->dwSampleRate;
      dwEffectFlags = a2->dwEffectFlags;
      fShare = a2->fShare;
      v36.Set = GUID_fedfae25_e46e_11d1_aace_0000f875ac12;
      v45 = fShare;
      memset(v35, 0, 28);
      v46 = 0;
      *(&v36.Alignment + 2) = 0x1000000100000003LL;
      v38 = 0;
      if ( !(unsigned int)Property(v10, 0x40u, &v36, 0x1Cu, v35, 0) )
      {
        LastError = GetLastError();
        DefaultMasterClock = WIN32ERRORtoHRESULT(LastError);
        if ( DefaultMasterClock >= 0 )
          return (unsigned int)DefaultMasterClock;
LABEL_9:
        CDirectMusicUMAPort::Close((CDirectMusicUMAPort *)((char *)this + 400));
        return (unsigned int)DefaultMasterClock;
      }
      v13 = a2->dwValidParams;
      v14 = DWORD2(v35[1]);
      v15 = DWORD1(v35[1]);
      v16 = v35[1];
      v17 = HIDWORD(v35[0]);
      v18 = DWORD2(v35[0]);
      v19 = DWORD1(v35[0]);
      if ( v13 != LODWORD(v35[0])
        || (v13 & 1) != 0 && a2->dwVoices != DWORD1(v35[0])
        || (v13 & 2) != 0 && a2->dwChannelGroups != DWORD2(v35[0])
        || (v13 & 4) != 0 && a2->dwAudioChannels != HIDWORD(v35[0])
        || (v13 & 8) != 0 && a2->dwSampleRate != LODWORD(v35[1])
        || (v13 & 0x20) != 0 && a2->dwEffectFlags != DWORD1(v35[1])
        || (v13 & 0x40) != 0 && a2->fShare != DWORD2(v35[1]) )
      {
        v9 = 1;
        a2->dwValidParams = v35[0];
        a2->dwVoices = v19;
        a2->dwChannelGroups = v18;
        a2->dwAudioChannels = v17;
        a2->dwSampleRate = v16;
        a2->dwEffectFlags = v15;
        a2->fShare = v14;
      }
      v20 = (DWORD *)((char *)this + 764);
      if ( (a2->dwValidParams & 2) != 0 )
      {
        *v20 = a2->dwChannelGroups;
      }
      else if ( CDirectMusicUMAPort::GetNumChannelGroups(
                  (CDirectMusicUMAPort *)((char *)this + 384),
                  (unsigned int *)this + 191) < 0 )
      {
        *v20 = 1;
      }
      if ( *((_DWORD *)this + 108) )
      {
        v21 = *v20;
        for ( i = 1; i <= v21; ++i )
        {
          v23 = 0;
          do
          {
            CDirectMusicUMAPort::SetChannelPriority(
              (CDirectMusicUMAPort *)((char *)this + 384),
              i,
              v23,
              *((_DWORD *)qword_180025540 + v23));
            v23 = (unsigned int)(v23 + 1);
          }
          while ( (unsigned int)v23 < 0x10 );
        }
      }
    }
    v24 = malloc(0x28u);
    *(_QWORD *)ThreadId = v24;
    if ( v24 )
    {
      v25 = *v8;
      v26 = *((_DWORD *)this + 327);
      *v24 = &CUMAPortLatencyClock::`vftable';
      v24[2] = v25;
      *((_DWORD *)v24 + 2) = 1;
      *((_DWORD *)v24 + 6) = v26;
      v24[4] = this;
    }
    else
    {
      v24 = 0;
    }
    *((_QWORD *)this + 179) = v24;
    if ( !v24 )
    {
      DefaultMasterClock = -2147024882;
      goto LABEL_9;
    }
    DefaultMasterClock = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 53))(
                           *((_QWORD *)this + 53),
                           &IID_IDirectMusicPortNotify,
                           (char *)this + 440);
    if ( DefaultMasterClock < 0 )
      goto LABEL_9;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 55) + 16LL))(*((_QWORD *)this + 55));
    if ( *((_DWORD *)this + 108) )
    {
      v27 = CDirectMusicUMAPort::InitializeOverlappedStructs((struct _RTL_CRITICAL_SECTION *)this);
    }
    else
    {
      ThreadId[0] = 0;
      EventA = CreateEventA(0, 0, 0, 0);
      *((_QWORD *)this + 186) = EventA;
      if ( EventA )
      {
        Thread = CreateThread(0, 0, CaptureThread, this, 0, ThreadId);
        *((_QWORD *)this + 187) = Thread;
        if ( Thread )
        {
          DefaultMasterClock = 0;
          goto LABEL_48;
        }
      }
      v29 = GetLastError();
      v27 = WIN32ERRORtoHRESULT(v29);
    }
    DefaultMasterClock = v27;
LABEL_48:
    if ( DefaultMasterClock >= 0 )
    {
      DefaultMasterClock = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 53) + 56LL))(
                             *((_QWORD *)this + 53),
                             0,
                             (char *)this + 1424);
      if ( DefaultMasterClock >= 0 )
      {
        PinSetState(*v8, KSSTATE_STOP);
        PinSetState(*v8, KSSTATE_PAUSE);
        DefaultMasterClock = CMasterClock::CreateDefaultMasterClock(
                               *(CMasterClock **)(*((_QWORD *)this + 53) + 96LL),
                               (struct IReferenceClock **)this + 4449);
        if ( DefaultMasterClock >= 0 )
        {
          v31 = *((_QWORD *)this + 178);
          v33 = 0;
          v34 = 0;
          DefaultMasterClock = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v31 + 24LL))(v31, &v33);
          if ( DefaultMasterClock >= 0 )
          {
            DefaultMasterClock = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 4449) + 24LL))(
                                   *((_QWORD *)this + 4449),
                                   &v34);
            if ( DefaultMasterClock >= 0 )
            {
              *((_QWORD *)this + 4448) = v33 - v34;
              return v9 != 0;
            }
          }
        }
      }
    }
    goto LABEL_9;
  }
  return result;
}

```

## disassembly

```asm
0x18001f51c  mov     [rsp-8+arg_10], rbx
0x18001f521  push    rbp
0x18001f522  push    rsi
0x18001f523  push    rdi
0x18001f524  push    r12
0x18001f526  push    r13
0x18001f528  push    r14
0x18001f52a  push    r15
0x18001f52c  lea     rbp, [rsp-27h]
0x18001f531  sub     rsp, 0E0h
0x18001f538  mov     rax, cs:__security_cookie
0x18001f53f  xor     rax, rsp
0x18001f542  mov     [rbp+57h+var_40], rax
0x18001f546  mov     rdi, rcx
0x18001f549  mov     ebx, 180h
0x18001f54e  mov     ecx, ebx; unsigned __int64
0x18001f550  mov     rsi, rdx
0x18001f553  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001f558  xor     r15d, r15d
0x18001f55b  mov     [rdi+8AF0h], rax
0x18001f562  test    rax, rax
0x18001f565  jnz     short loc_18001F571
0x18001f567  mov     eax, 8007000Eh
0x18001f56c  jmp     loc_18001F6BA
0x18001f571  mov     rcx, [rdi+1A8h]
0x18001f578  lea     r8, [rdi+8AE8h]
0x18001f57f  xorps   xmm0, xmm0
0x18001f582  mov     [rbp+57h+var_4C], r15d
0x18001f586  movdqu  [rbp+57h+var_5C], xmm0
0x18001f58b  mov     [rbp+57h+var_48], 1000h
0x18001f592  lea     rdx, [rbp+57h+var_60]
0x18001f596  mov     r14d, 1Ch
0x18001f59c  xor     r9d, r9d
0x18001f59f  mov     [rbp+57h+var_60], r14d
0x18001f5a3  mov     rax, [rcx]
0x18001f5a6  mov     rax, [rax+20h]
0x18001f5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5af  test    eax, eax
0x18001f5b1  js      loc_18001F6BA
0x18001f5b7  mov     rcx, [rdi+8AF0h]; void *
0x18001f5be  mov     r8, rbx; Size
0x18001f5c1  xor     edx, edx; Val
0x18001f5c3  call    memset_0
0x18001f5c8  lea     rdx, [rdi+520h]; void **
0x18001f5cf  lea     rcx, [rdi+314h]; unsigned __int16 *
0x18001f5d6  call    ?FilterInstantiate@@YAJPEBGPEAPEAX@Z; FilterInstantiate(ushort const *,void * *)
0x18001f5db  mov     ebx, eax
0x18001f5dd  test    eax, eax
0x18001f5df  js      loc_18001F6AC
0x18001f5e5  mov     edx, [rdi+518h]; unsigned int
0x18001f5eb  lea     r12, [rdi+528h]
0x18001f5f2  mov     r8, r12; void **
0x18001f5f5  mov     rcx, rdi; this
0x18001f5f8  call    ?InstantiatePin@CDirectMusicUMAPort@@AEAAJKPEAPEAX@Z; CDirectMusicUMAPort::InstantiatePin(ulong,void * *)
0x18001f5fd  mov     ebx, eax
0x18001f5ff  test    eax, eax
0x18001f601  js      loc_18001F6AC
0x18001f607  mov     r13d, r15d
0x18001f60a  test    rsi, rsi
0x18001f60d  jz      loc_18001F7CB
0x18001f613  mov     eax, [rdi+51Ch]
0x18001f619  lea     r8, [rbp+57h+var_A0]; struct KSIDENTIFIER *
0x18001f61d  movups  xmm0, xmmword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
0x18001f624  mov     rcx, [r12]; void *
0x18001f628  lea     edx, [r14+24h]; unsigned int
0x18001f62c  mov     [rbp+57h+var_88], eax
0x18001f62f  mov     r9d, r14d; unsigned int
0x18001f632  mov     eax, [rsi+4]
0x18001f635  mov     [rbp+57h+var_80], eax
0x18001f638  mov     eax, [rsi+8]
0x18001f63b  mov     [rbp+57h+var_7C], eax
0x18001f63e  mov     eax, [rsi+0Ch]
0x18001f641  mov     [rbp+57h+var_78], eax
0x18001f644  mov     eax, [rsi+10h]
0x18001f647  mov     [rbp+57h+var_74], eax
0x18001f64a  mov     eax, [rsi+14h]
0x18001f64d  mov     [rbp+57h+var_70], eax
0x18001f650  mov     eax, [rsi+18h]
0x18001f653  mov     [rbp+57h+var_6C], eax
0x18001f656  mov     eax, [rsi+1Ch]
0x18001f659  movdqu  xmmword ptr [rbp+57h+var_A0], xmm0
0x18001f65e  mov     [rbp+57h+var_68], eax
0x18001f661  lea     rax, [rbp+57h+var_C8]
0x18001f665  xorps   xmm0, xmm0
0x18001f668  mov     [rsp+110h+lpThreadId], r15; unsigned int *
0x18001f66d  movups  [rbp+57h+var_C8], xmm0
0x18001f671  mov     qword ptr [rsp+110h+dwCreationFlags], rax; void *
0x18001f676  mov     [rbp+57h+var_64], r15d
0x18001f67a  mov     dword ptr [rbp+57h+var_A0+10h], 3
0x18001f681  mov     dword ptr [rbp+57h+var_A0+14h], 10000001h
0x18001f688  mov     [rbp+57h+var_84], r15d
0x18001f68c  movups  [rbp+57h+var_C8+0Ch], xmm0
0x18001f690  call    ?Property@@YAHPEAXKPEAUKSIDENTIFIER@@K0PEAK@Z; Property(void *,ulong,KSIDENTIFIER *,ulong,void *,ulong *)
0x18001f695  test    eax, eax
0x18001f697  jnz     short loc_18001F6E1
0x18001f699  call    cs:__imp_GetLastError
0x18001f69f  mov     ecx, eax; unsigned int
0x18001f6a1  call    ?WIN32ERRORtoHRESULT@@YAJK@Z; WIN32ERRORtoHRESULT(ulong)
0x18001f6a6  mov     ebx, eax
0x18001f6a8  test    eax, eax
0x18001f6aa  jns     short loc_18001F6B8
0x18001f6ac  lea     rcx, [rdi+190h]; this
0x18001f6b3  call    ?Close@CDirectMusicUMAPort@@UEAAJXZ; CDirectMusicUMAPort::Close(void)
0x18001f6b8  mov     eax, ebx
0x18001f6ba  mov     rcx, [rbp+57h+var_40]
0x18001f6be  xor     rcx, rsp; StackCookie
0x18001f6c1  call    __security_check_cookie
0x18001f6c6  mov     rbx, [rsp+110h+arg_10]
0x18001f6ce  add     rsp, 0E0h
0x18001f6d5  pop     r15
0x18001f6d7  pop     r14
0x18001f6d9  pop     r13
0x18001f6db  pop     r12
0x18001f6dd  pop     rdi
0x18001f6de  pop     rsi
0x18001f6df  pop     rbp
0x18001f6e0  retn
0x18001f6e1  mov     eax, [rsi+4]
0x18001f6e4  mov     ebx, dword ptr [rbp+57h+var_C8]
0x18001f6e7  mov     ecx, [rbp+57h+var_B0]
0x18001f6ea  mov     edx, [rbp+57h+var_B4]
0x18001f6ed  mov     r8d, [rbp+57h+var_B8]
0x18001f6f1  mov     r9d, dword ptr [rbp+57h+var_C8+0Ch]
0x18001f6f5  mov     r10d, dword ptr [rbp+57h+var_C8+8]
0x18001f6f9  mov     r11d, dword ptr [rbp+57h+var_C8+4]
0x18001f6fd  cmp     eax, ebx
0x18001f6ff  jnz     short loc_18001F73B
0x18001f701  test    al, 1
0x18001f703  jz      short loc_18001F70B
0x18001f705  cmp     [rsi+8], r11d
0x18001f709  jnz     short loc_18001F73B
0x18001f70b  test    al, 2
0x18001f70d  jz      short loc_18001F715
0x18001f70f  cmp     [rsi+0Ch], r10d
0x18001f713  jnz     short loc_18001F73B
0x18001f715  test    al, 4
0x18001f717  jz      short loc_18001F71F
0x18001f719  cmp     [rsi+10h], r9d
0x18001f71d  jnz     short loc_18001F73B
0x18001f71f  test    al, 8
0x18001f721  jz      short loc_18001F729
0x18001f723  cmp     [rsi+14h], r8d
0x18001f727  jnz     short loc_18001F73B
0x18001f729  test    al, 20h
0x18001f72b  jz      short loc_18001F732
0x18001f72d  cmp     [rsi+18h], edx
0x18001f730  jnz     short loc_18001F73B
0x18001f732  test    al, 40h
0x18001f734  jz      short loc_18001F75A
0x18001f736  cmp     [rsi+1Ch], ecx
0x18001f739  jz      short loc_18001F75A
0x18001f73b  mov     r13d, 1
0x18001f741  mov     [rsi+4], ebx
0x18001f744  mov     [rsi+8], r11d
0x18001f748  mov     [rsi+0Ch], r10d
0x18001f74c  mov     [rsi+10h], r9d
0x18001f750  mov     [rsi+14h], r8d
0x18001f754  mov     [rsi+18h], edx
0x18001f757  mov     [rsi+1Ch], ecx
0x18001f75a  test    byte ptr [rsi+4], 2
0x18001f75e  lea     rbx, [rdi+2FCh]
0x18001f765  lea     r15, [rdi+180h]
0x18001f76c  jz      short loc_18001F775
0x18001f76e  mov     eax, [rsi+0Ch]
0x18001f771  mov     [rbx], eax
0x18001f773  jmp     short loc_18001F78A
0x18001f775  mov     rdx, rbx; unsigned int *
0x18001f778  mov     rcx, r15; this
0x18001f77b  call    ?GetNumChannelGroups@CDirectMusicUMAPort@@UEAAJPEAK@Z; CDirectMusicUMAPort::GetNumChannelGroups(ulong *)
0x18001f780  test    eax, eax
0x18001f782  jns     short loc_18001F78A
0x18001f784  mov     dword ptr [rbx], 1
0x18001f78a  cmp     dword ptr [rdi+1B0h], 0
0x18001f791  jz      short loc_18001F7C8
0x18001f793  mov     r14d, [rbx]
0x18001f796  mov     esi, 1
0x18001f79b  cmp     r14d, esi
0x18001f79e  jb      short loc_18001F7C8
0x18001f7a0  xor     ebx, ebx
0x18001f7a2  lea     rax, qword_180025540
0x18001f7a9  mov     r8d, ebx; unsigned int
0x18001f7ac  mov     r9d, [rax+rbx*4]; unsigned int
0x18001f7b0  mov     edx, esi; unsigned int
0x18001f7b2  mov     rcx, r15; this
0x18001f7b5  call    ?SetChannelPriority@CDirectMusicUMAPort@@UEAAJKKK@Z; CDirectMusicUMAPort::SetChannelPriority(ulong,ulong,ulong)
0x18001f7ba  inc     ebx
0x18001f7bc  cmp     ebx, 10h
0x18001f7bf  jb      short loc_18001F7A2
0x18001f7c1  inc     esi
0x18001f7c3  cmp     esi, r14d
0x18001f7c6  jbe     short loc_18001F7A0
0x18001f7c8  xor     r15d, r15d
0x18001f7cb  mov     ecx, 28h ; '('; Size
0x18001f7d0  call    cs:__imp_malloc
0x18001f7d6  mov     qword ptr [rsp+110h+ThreadId], rax
0x18001f7db  test    rax, rax
0x18001f7de  jz      short loc_18001F808
0x18001f7e0  mov     rcx, [r12]
0x18001f7e4  lea     r8, ??_7CUMAPortLatencyClock@@6B@; const CUMAPortLatencyClock::`vftable'
0x18001f7eb  mov     edx, [rdi+51Ch]
0x18001f7f1  mov     [rax], r8
0x18001f7f4  mov     [rax+10h], rcx
0x18001f7f8  mov     dword ptr [rax+8], 1
0x18001f7ff  mov     [rax+18h], edx
0x18001f802  mov     [rax+20h], rdi
0x18001f806  jmp     short loc_18001F80B
0x18001f808  mov     rax, r15
0x18001f80b  mov     [rdi+598h], rax
0x18001f812  test    rax, rax
0x18001f815  jnz     short loc_18001F821
0x18001f817  mov     ebx, 8007000Eh
0x18001f81c  jmp     loc_18001F6AC
0x18001f821  mov     rcx, [rdi+1A8h]
0x18001f828  lea     rsi, [rdi+1B8h]
0x18001f82f  mov     r8, rsi
0x18001f832  lea     rdx, IID_IDirectMusicPortNotify
0x18001f839  mov     rax, [rcx]
0x18001f83c  mov     rax, [rax]
0x18001f83f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f844  mov     ebx, eax
0x18001f846  test    eax, eax
0x18001f848  js      loc_18001F6AC
0x18001f84e  mov     rcx, [rsi]
0x18001f851  mov     rax, [rcx]
0x18001f854  mov     rax, [rax+10h]
0x18001f858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f85d  cmp     [rdi+1B0h], r15d
0x18001f864  jz      short loc_18001F872
0x18001f866  mov     rcx, rdi; this
0x18001f869  call    ?InitializeOverlappedStructs@CDirectMusicUMAPort@@AEAAJXZ; CDirectMusicUMAPort::InitializeOverlappedStructs(void)
0x18001f86e  mov     ebx, eax
0x18001f870  jmp     short loc_18001F8D4
0x18001f872  xor     r9d, r9d; lpName
0x18001f875  mov     [rsp+110h+ThreadId], r15d
0x18001f87a  xor     r8d, r8d; bInitialState
0x18001f87d  xor     edx, edx; bManualReset
0x18001f87f  xor     ecx, ecx; lpEventAttributes
0x18001f881  call    cs:__imp_CreateEventA
0x18001f887  mov     [rdi+5D0h], rax
0x18001f88e  test    rax, rax
0x18001f891  jnz     short loc_18001F8A2
0x18001f893  call    cs:__imp_GetLastError
0x18001f899  mov     ecx, eax; unsigned int
0x18001f89b  call    ?WIN32ERRORtoHRESULT@@YAJK@Z; WIN32ERRORtoHRESULT(ulong)
0x18001f8a0  jmp     short loc_18001F86E
0x18001f8a2  lea     rax, [rsp+110h+ThreadId]
0x18001f8a7  mov     r9, rdi; lpParameter
0x18001f8aa  mov     [rsp+110h+lpThreadId], rax; lpThreadId
0x18001f8af  lea     r8, ?CaptureThread@@YAKPEAX@Z; lpStartAddress
0x18001f8b6  xor     edx, edx; dwStackSize
0x18001f8b8  mov     [rsp+110h+dwCreationFlags], r15d; dwCreationFlags
0x18001f8bd  xor     ecx, ecx; lpThreadAttributes
0x18001f8bf  call    cs:__imp_CreateThread
0x18001f8c5  mov     [rdi+5D8h], rax
0x18001f8cc  test    rax, rax
0x18001f8cf  jz      short loc_18001F893
0x18001f8d1  mov     ebx, r15d
0x18001f8d4  test    ebx, ebx
0x18001f8d6  js      loc_18001F6AC
0x18001f8dc  mov     rcx, [rdi+1A8h]
0x18001f8e3  lea     r14, [rdi+590h]
0x18001f8ea  mov     r8, r14
0x18001f8ed  xor     edx, edx
0x18001f8ef  mov     rax, [rcx]
0x18001f8f2  mov     rax, [rax+38h]
0x18001f8f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8fb  mov     ebx, eax
0x18001f8fd  test    eax, eax
0x18001f8ff  js      loc_18001F6AC
0x18001f905  mov     rcx, [r12]; void *
0x18001f909  xor     edx, edx; enum KSSTATE
0x18001f90b  call    ?PinSetState@@YAJPEAXW4KSSTATE@@@Z; PinSetState(void *,KSSTATE)
0x18001f910  mov     rcx, [r12]; void *
0x18001f914  mov     edx, 2; enum KSSTATE
0x18001f919  call    ?PinSetState@@YAJPEAXW4KSSTATE@@@Z; PinSetState(void *,KSSTATE)
0x18001f91e  mov     rcx, [rdi+1A8h]
0x18001f925  lea     rsi, [rdi+8B08h]
0x18001f92c  mov     rdx, rsi; struct IReferenceClock **
0x18001f92f  mov     rcx, [rcx+60h]; this
0x18001f933  call    ?CreateDefaultMasterClock@CMasterClock@@QEAAJPEAPEAUIReferenceClock@@@Z; CMasterClock::CreateDefaultMasterClock(IReferenceClock * *)
0x18001f938  mov     ebx, eax
0x18001f93a  test    eax, eax
0x18001f93c  js      loc_18001F6AC
0x18001f942  mov     rcx, [r14]
0x18001f945  lea     rdx, [rsp+110h+var_D8]
0x18001f94a  mov     [rsp+110h+var_D8], r15
0x18001f94f  mov     [rbp+57h+var_D0], r15
0x18001f953  mov     rax, [rcx]
0x18001f956  mov     rax, [rax+18h]
0x18001f95a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f95f  mov     ebx, eax
0x18001f961  test    eax, eax
0x18001f963  js      loc_18001F6AC
0x18001f969  mov     rcx, [rsi]
0x18001f96c  lea     rdx, [rbp+57h+var_D0]
0x18001f970  mov     rax, [rcx]
0x18001f973  mov     rax, [rax+18h]
0x18001f977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f97c  mov     ebx, eax
0x18001f97e  test    eax, eax
  ... truncated ...
```
