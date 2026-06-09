# MRxSmbCacheFullDirectory

- ea: `0x140043368`
- end: `0x14004379f`
- name: `MRxSmbCacheFullDirectory`
- size: `1079`
- prototype: `void __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x14002a430`

## callees

- `0x14000f634`
- `0x140016324`
- `0x1400166c0`
- `0x1400169c0`
- `0x14002c464`
- `0x140043368`
- `0x140052fa0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004377a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004377a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400433f6`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400433f6`
- `ntoskrnl!RtlCopySid` at `0x14004356e`
- `ntoskrnl!RtlCopySid` at `0x14004356e`
- `rdbss!RxNameCacheExpireEntry` at `0x14004374a`
- `rdbss!RxNameCacheExpireEntry` at `0x14004374a`
- `rdbss!RxNameCacheActivateEntry` at `0x1400436fb`
- `rdbss!RxNameCacheActivateEntry` at `0x1400436fb`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140043440`
- `rdbss!RxNameCacheCreateEntryEx` at `0x140043440`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004340e`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004340e`
- `rdbss!RxNameCacheCheckEntry` at `0x140043492`
- `rdbss!RxNameCacheCheckEntry` at `0x140043492`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140043682`
- `mrxsmb!FsRtlValidateFileInformationBufferEx` at `0x140043682`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400433ac`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400436dd`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400433ac`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400436dd`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14004369a`

## pseudocode

```c
void __fastcall MRxSmbCacheFullDirectory(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // rbx
  size_t v6; // r12
  __int64 v8; // r13
  _WORD *v9; // rbp
  __int64 v10; // rbx
  struct _NAME_CACHE_CONTROL_ *v11; // r14
  __int64 Entry; // rsi
  __int64 v13; // r9
  __int64 v14; // rbx
  int v15; // r13d
  void *v16; // rcx
  ULONG v17; // ebx
  __int64 ConfigurationBlock; // rax
  int v19; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+10h]
  char v21; // [rsp+B0h] [rbp+18h]

  v20 = a2;
  v4 = *(_QWORD *)(a1 + 56);
  v6 = a3;
  if ( v4 )
    v8 = *(_QWORD *)(v4 + 136);
  else
    v8 = 0;
  if ( a3 <= 0x1000 && *(_DWORD *)(MRxSmbGetConfigurationBlock() + 152) )
  {
    v9 = (_WORD *)(v4 + 360);
    if ( *(_BYTE *)(a1 + 32) )
      v10 = *(_QWORD *)(v4 + 120);
    else
      v10 = *(_QWORD *)(a1 + 648);
    v11 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v10 + 40) + 1024LL);
    ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
    Entry = RxNameCacheFetchEntryEx(v11, v9, 0, 0);
    if ( Entry )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_Zl(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids,
          (_DWORD)v9,
          v6);
      }
      RxNameCacheCheckEntry((PNAME_CACHE)Entry, *(_DWORD *)(Entry + 32));
      memset(*(void **)(Entry + 40), 0, 0x20A0u);
    }
    else if ( (*(_DWORD *)(v10 + 56) & 0x20) == 0
           || (LOBYTE(v13) = 1, (Entry = RxNameCacheCreateEntryEx(v11, v9, 0, v13)) == 0) )
    {
LABEL_35:
      ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
      return;
    }
    v14 = *(_QWORD *)(Entry + 40);
    *(_DWORD *)(Entry + 48) = 0;
    *(_QWORD *)v14 = 0;
    *(_DWORD *)(v14 + 8) = 4096;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_ZdqDqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (unsigned __int16)*v9,
        v14 + 88,
        (_DWORD)v9,
        *v9,
        v14 + 88,
        *(_BYTE *)(v14 + 88),
        v20,
        v6);
    *(_OWORD *)(v14 + 16) = *(_OWORD *)a4;
    *(_OWORD *)(v14 + 32) = *(_OWORD *)(a4 + 16);
    *(_OWORD *)(v14 + 48) = *(_OWORD *)(a4 + 32);
    *(_OWORD *)(v14 + 64) = *(_OWORD *)(a4 + 48);
    *(_QWORD *)(v14 + 80) = *(_QWORD *)(a4 + 64);
    *(_QWORD *)(v14 + 32) = 0;
    RtlCopySid(4 * *(unsigned __int8 *)(v8 + 17) + 8, (PSID)(v14 + 4184), (PSID)(v8 + 16));
    memmove((void *)(v14 + 88), *(const void **)(a4 + 16), v6);
    v15 = 0;
    v19 = 0;
    v21 = 0;
    if ( *(_BYTE *)(a1 + 517) )
    {
      v21 = 1;
      *(_BYTE *)(a1 + 517) = 0;
    }
    if ( *(_DWORD *)(a1 + 512) )
    {
      v15 = *(_DWORD *)(a1 + 512);
      *(_DWORD *)(a1 + 512) = 0;
    }
    _MRxSmbAllocateSideBuffer(a1, v14 + 16);
    v16 = *(void **)(v14 + 32);
    if ( !v16 )
      goto LABEL_30;
    memmove(v16, *(const void **)(a4 + 16), v6);
    *(_WORD *)(v14 + 44) = 257;
    *(_QWORD *)(v14 + 24) = 0;
    *(_BYTE *)(v14 + 46) = 0;
    *(_WORD *)(v14 + 68) &= ~2u;
    *(_DWORD *)(v14 + 48) = *(_DWORD *)(a4 + 32);
    *(_DWORD *)(v14 + 52) = 0;
    *(_DWORD *)(v14 + 56) = *(_DWORD *)(a4 + 40);
    *(_WORD *)(v14 + 68) &= ~1u;
    *(_DWORD *)(v14 + 64) = 0;
    *(_BYTE *)(v14 + 74) = *(_BYTE *)(a4 + 58);
    v19 = *(_DWORD *)(v14 + 8);
    if ( (unsigned int)MrxSmbUnalignedDirEntryCopyTail(a1, 3, v14 + 4256, &v19, v14 + 16)
      || (unsigned int)FsRtlValidateFileInformationBufferEx(
                         a1,
                         3,
                         v14 + 4256,
                         (unsigned int)(*(_DWORD *)(v14 + 8) - v19),
                         0,
                         0,
                         0) )
    {
LABEL_30:
      RxNameCacheExpireEntry(v11, (PNAME_CACHE)Entry);
    }
    else
    {
      *(_OWORD *)(v14 + 16) = *(_OWORD *)a4;
      *(_OWORD *)(v14 + 32) = *(_OWORD *)(a4 + 16);
      *(_OWORD *)(v14 + 48) = *(_OWORD *)(a4 + 32);
      *(_OWORD *)(v14 + 64) = *(_OWORD *)(a4 + 48);
      *(_QWORD *)(v14 + 80) = *(_QWORD *)(a4 + 64);
      *(_QWORD *)(v14 + 32) = 0;
      v17 = *(_DWORD *)(MRxSmbLegacyPerfCtrs + 8LL);
      ConfigurationBlock = MRxSmbGetConfigurationBlock();
      RxNameCacheActivateEntry(v11, (PNAME_CACHE)Entry, *(_DWORD *)(ConfigurationBlock + 152), v17);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_Zl(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          (unsigned int)WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids,
          (_DWORD)v9,
          v6);
      }
    }
    if ( v21 )
      *(_BYTE *)(a1 + 517) = 1;
    if ( v15 )
      *(_DWORD *)(a1 + 512) = v15;
    goto LABEL_35;
  }
}

```

## disassembly

```asm
0x140043368  mov     [rsp+arg_18], rbx
0x14004336d  mov     [rsp+arg_8], rdx
0x140043372  push    rbp
0x140043373  push    rsi
0x140043374  push    rdi
0x140043375  push    r12
0x140043377  push    r13
0x140043379  push    r14
0x14004337b  push    r15
0x14004337d  sub     rsp, 60h
0x140043381  mov     rbx, [rcx+38h]
0x140043385  mov     r15, r9
0x140043388  mov     r12d, r8d
0x14004338b  mov     rdi, rcx
0x14004338e  test    rbx, rbx
0x140043391  jnz     short loc_140043398
0x140043393  xor     r13d, r13d
0x140043396  jmp     short loc_14004339F
0x140043398  mov     r13, [rbx+88h]
0x14004339f  cmp     r12d, 1000h
0x1400433a6  ja      loc_140043786
0x1400433ac  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400433b3  nop     dword ptr [rax+rax+00h]
0x1400433b8  cmp     dword ptr [rax+98h], 0
0x1400433bf  jz      loc_140043786
0x1400433c5  cmp     byte ptr [rdi+20h], 0
0x1400433c9  lea     rbp, [rbx+168h]
0x1400433d0  jnz     short loc_1400433DB
0x1400433d2  mov     rbx, [rdi+288h]
0x1400433d9  jmp     short loc_1400433DF
0x1400433db  mov     rbx, [rbx+78h]
0x1400433df  mov     r14, [rbx+28h]
0x1400433e3  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400433ea  add     r14, 400h
0x1400433f1  mov     [rsp+98h+NameCacheCtl], r14
0x1400433f6  call    cs:__imp_ExAcquireFastMutex
0x1400433fd  nop     dword ptr [rax+rax+00h]
0x140043402  xor     r9d, r9d
0x140043405  xor     r8d, r8d
0x140043408  mov     rdx, rbp
0x14004340b  mov     rcx, r14
0x14004340e  call    cs:__imp_RxNameCacheFetchEntryEx
0x140043415  nop     dword ptr [rax+rax+00h]
0x14004341a  mov     rsi, rax
0x14004341d  lea     rax, WPP_GLOBAL_Control
0x140043424  test    rsi, rsi
0x140043427  jnz     short loc_14004345A
0x140043429  mov     eax, [rbx+38h]
0x14004342c  test    al, 20h
0x14004342e  jz      loc_140043773
0x140043434  mov     r9b, 1
0x140043437  xor     r8d, r8d
0x14004343a  mov     rdx, rbp
0x14004343d  mov     rcx, r14
0x140043440  call    cs:__imp_RxNameCacheCreateEntryEx
0x140043447  nop     dword ptr [rax+rax+00h]
0x14004344c  mov     rsi, rax
0x14004344f  test    rax, rax
0x140043452  jz      loc_140043773
0x140043458  jmp     short loc_1400434AF
0x14004345a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140043461  cmp     rcx, rax
0x140043464  jz      short loc_14004348C
0x140043466  test    dword ptr [rcx+2Ch], 200h
0x14004346d  jz      short loc_14004348C
0x14004346f  mov     rcx, [rcx+18h]
0x140043473  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004347a  mov     edx, 0Fh
0x14004347f  mov     dword ptr [rsp+98h+var_78], r12d
0x140043484  mov     r9, rbp
0x140043487  call    WPP_SF_Zl
0x14004348c  mov     edx, [rsi+20h]; MRxContext
0x14004348f  mov     rcx, rsi; NameCache
0x140043492  call    cs:__imp_RxNameCacheCheckEntry
0x140043499  nop     dword ptr [rax+rax+00h]
0x14004349e  mov     rcx, [rsi+28h]; void *
0x1400434a2  xor     edx, edx; Val
0x1400434a4  mov     r8d, 20A0h; Size
0x1400434aa  call    memset
0x1400434af  mov     rbx, [rsi+28h]
0x1400434b3  xor     eax, eax
0x1400434b5  mov     dword ptr [rsi+30h], 0
0x1400434bc  mov     [rbx], rax
0x1400434bf  mov     dword ptr [rbx+8], 1000h
0x1400434c6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400434cd  lea     rax, WPP_GLOBAL_Control
0x1400434d4  cmp     rcx, rax
0x1400434d7  jz      short loc_140043519
0x1400434d9  test    dword ptr [rcx+2Ch], 200h
0x1400434e0  jz      short loc_140043519
0x1400434e2  mov     r9, [rsp+98h+arg_8]
0x1400434ea  lea     r8, [rbx+58h]
0x1400434ee  movzx   eax, byte ptr [r8]
0x1400434f2  movzx   edx, word ptr [rbp+0]
0x1400434f6  mov     rcx, [rcx+18h]
0x1400434fa  mov     [rsp+98h+var_58], r12d
0x1400434ff  mov     [rsp+98h+var_60], r9
0x140043504  mov     r9, rbp
0x140043507  mov     [rsp+98h+var_68], eax
0x14004350b  mov     [rsp+98h+var_70], r8
0x140043510  mov     dword ptr [rsp+98h+var_78], edx
0x140043514  call    WPP_SF_ZdqDqd
0x140043519  movups  xmm0, xmmword ptr [r15]
0x14004351d  lea     r14, [rbx+10h]
0x140043521  lea     r8, [r13+10h]; SourceSid
0x140043525  movups  xmmword ptr [r14], xmm0
0x140043529  lea     rdx, [rbx+1058h]; DestinationSid
0x140043530  movups  xmm1, xmmword ptr [r15+10h]
0x140043535  movups  xmmword ptr [r14+10h], xmm1
0x14004353a  movups  xmm0, xmmword ptr [r15+20h]
0x14004353f  movups  xmmword ptr [r14+20h], xmm0
0x140043544  movups  xmm1, xmmword ptr [r15+30h]
0x140043549  movups  xmmword ptr [r14+30h], xmm1
0x14004354e  movsd   xmm0, qword ptr [r15+40h]
0x140043554  movsd   qword ptr [r14+40h], xmm0
0x14004355a  mov     qword ptr [rbx+20h], 0
0x140043562  movzx   ecx, byte ptr [r13+11h]
0x140043567  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14004356e  call    cs:__imp_RtlCopySid
0x140043575  nop     dword ptr [rax+rax+00h]
0x14004357a  mov     rdx, [r15+10h]; Src
0x14004357e  lea     rcx, [rbx+58h]; void *
0x140043582  mov     r8, r12; Size
0x140043585  call    memmove
0x14004358a  xor     ecx, ecx
0x14004358c  mov     r13d, ecx
0x14004358f  mov     [rsp+98h+arg_0], ecx
0x140043596  mov     [rsp+98h+arg_10], cl
0x14004359d  cmp     [rdi+205h], cl
0x1400435a3  jz      short loc_1400435B3
0x1400435a5  mov     [rsp+98h+arg_10], 1
0x1400435ad  mov     [rdi+205h], cl
0x1400435b3  mov     eax, [rdi+200h]
0x1400435b9  test    eax, eax
0x1400435bb  jz      short loc_1400435C6
0x1400435bd  mov     r13d, eax
0x1400435c0  mov     [rdi+200h], ecx
0x1400435c6  mov     rdx, r14
0x1400435c9  mov     rcx, rdi
0x1400435cc  call    __MRxSmbAllocateSideBuffer
0x1400435d1  mov     rcx, [rbx+20h]; void *
0x1400435d5  test    rcx, rcx
0x1400435d8  jz      loc_140043742
0x1400435de  mov     rdx, [r15+10h]; Src
0x1400435e2  mov     r8, r12; Size
0x1400435e5  call    memmove
0x1400435ea  xor     edx, edx
0x1400435ec  mov     word ptr [rbx+2Ch], 101h
0x1400435f2  mov     [rbx+18h], rdx
0x1400435f6  lea     r8, [rbx+10A0h]
0x1400435fd  mov     [rbx+2Eh], dl
0x140043600  lea     r9, [rsp+98h+arg_0]
0x140043608  mov     eax, 0FFFDh
0x14004360d  mov     [rsp+98h+var_78], r14
0x140043612  and     [rbx+44h], ax
0x140043616  mov     rcx, rdi
0x140043619  mov     eax, [r15+20h]
0x14004361d  mov     [rbx+30h], eax
0x140043620  mov     [rbx+34h], edx
0x140043623  mov     eax, [r15+28h]
0x140043627  mov     [rbx+38h], eax
0x14004362a  mov     eax, 0FFFEh
0x14004362f  and     [rbx+44h], ax
0x140043633  mov     [rbx+40h], edx
0x140043636  mov     edx, 3
0x14004363b  mov     al, [r15+3Ah]
0x14004363f  mov     [rbx+4Ah], al
0x140043642  mov     eax, [rbx+8]
0x140043645  mov     [rsp+98h+arg_0], eax
0x14004364c  call    MrxSmbUnalignedDirEntryCopyTail
0x140043651  xor     ecx, ecx
0x140043653  test    eax, eax
0x140043655  jnz     loc_140043742
0x14004365b  mov     r9d, [rbx+8]
0x14004365f  lea     edx, [rcx+3]
0x140043662  sub     r9d, [rsp+98h+arg_0]
0x14004366a  lea     r8, [rbx+10A0h]
0x140043671  mov     [rsp+98h+var_68], ecx
0x140043675  mov     [rsp+98h+var_70], rcx
0x14004367a  mov     [rsp+98h+var_78], rcx
0x14004367f  mov     rcx, rdi
0x140043682  call    cs:__imp_FsRtlValidateFileInformationBufferEx
0x140043689  nop     dword ptr [rax+rax+00h]
0x14004368e  test    eax, eax
0x140043690  jnz     loc_140043742
0x140043696  movups  xmm0, xmmword ptr [r15]
0x14004369a  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x1400436a1  movups  xmmword ptr [r14], xmm0
0x1400436a5  movups  xmm1, xmmword ptr [r15+10h]
0x1400436aa  movups  xmmword ptr [r14+10h], xmm1
0x1400436af  movups  xmm0, xmmword ptr [r15+20h]
0x1400436b4  movups  xmmword ptr [r14+20h], xmm0
0x1400436b9  movups  xmm1, xmmword ptr [r15+30h]
0x1400436be  movups  xmmword ptr [r14+30h], xmm1
0x1400436c3  movsd   xmm0, qword ptr [r15+40h]
0x1400436c9  movsd   qword ptr [r14+40h], xmm0
0x1400436cf  mov     qword ptr [rbx+20h], 0
0x1400436d7  mov     rdx, [rax]
0x1400436da  mov     ebx, [rdx+8]
0x1400436dd  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400436e4  nop     dword ptr [rax+rax+00h]
0x1400436e9  mov     rcx, [rsp+98h+NameCacheCtl]; NameCacheCtl
0x1400436ee  mov     r9d, ebx; MRxContext
0x1400436f1  mov     rdx, rsi; NameCache
0x1400436f4  mov     r8d, [rax+98h]; LifeTime
0x1400436fb  call    cs:__imp_RxNameCacheActivateEntry
0x140043702  nop     dword ptr [rax+rax+00h]
0x140043707  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004370e  lea     rax, WPP_GLOBAL_Control
0x140043715  cmp     rcx, rax
0x140043718  jz      short loc_140043756
0x14004371a  test    dword ptr [rcx+2Ch], 200h
0x140043721  jz      short loc_140043756
0x140043723  mov     rcx, [rcx+18h]
0x140043727  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004372e  mov     edx, 11h
0x140043733  mov     dword ptr [rsp+98h+var_78], r12d
0x140043738  mov     r9, rbp
0x14004373b  call    WPP_SF_Zl
0x140043740  jmp     short loc_140043756
0x140043742  mov     rcx, [rsp+98h+NameCacheCtl]; NameCacheCtl
0x140043747  mov     rdx, rsi; NameCache
0x14004374a  call    cs:__imp_RxNameCacheExpireEntry
0x140043751  nop     dword ptr [rax+rax+00h]
0x140043756  cmp     [rsp+98h+arg_10], 0
0x14004375e  jz      short loc_140043767
0x140043760  mov     byte ptr [rdi+205h], 1
0x140043767  test    r13d, r13d
0x14004376a  jz      short loc_140043773
0x14004376c  mov     [rdi+200h], r13d
0x140043773  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004377a  call    cs:__imp_ExReleaseFastMutex
0x140043781  nop     dword ptr [rax+rax+00h]
0x140043786  mov     rbx, [rsp+98h+arg_18]
0x14004378e  add     rsp, 60h
0x140043792  pop     r15
0x140043794  pop     r14
0x140043796  pop     r13
0x140043798  pop     r12
0x14004379a  pop     rdi
0x14004379b  pop     rsi
0x14004379c  pop     rbp
0x14004379d  retn
```
