# MRxSmbIsFullDirectoryCached

- ea: `0x140043f88`
- end: `0x140044241`
- name: `MRxSmbIsFullDirectoryCached`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14002a430`

## callees

- `0x14000dfa8`
- `0x14000e998`
- `0x1400166c0`
- `0x14002c464`
- `0x140043f88`
- `0x140052fa0`

## import_xrefs

- `ntoskrnl!RtlEqualSid` at `0x14004405e`
- `ntoskrnl!RtlEqualSid` at `0x14004405e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400441d3`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400441d3`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043ffb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140043ffb`
- `rdbss!RxNameCacheExpireEntry` at `0x140044100`
- `rdbss!RxNameCacheExpireEntry` at `0x1400441a6`
- `rdbss!RxNameCacheExpireEntry` at `0x1400441c0`
- `rdbss!RxNameCacheExpireEntry` at `0x140044100`
- `rdbss!RxNameCacheExpireEntry` at `0x1400441a6`
- `rdbss!RxNameCacheExpireEntry` at `0x1400441c0`
- `rdbss!RxNameCacheActivateEntry` at `0x14004418c`
- `rdbss!RxNameCacheActivateEntry` at `0x14004418c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140044013`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140044013`
- `rdbss!RxNameCacheCheckEntry` at `0x140044031`
- `rdbss!RxNameCacheCheckEntry` at `0x140044031`

## pseudocode

```c
char __fastcall MRxSmbIsFullDirectoryCached(__int64 a1, __int64 a2, int *a3, __int64 a4, _DWORD *a5)
{
  __int64 v5; // rax
  RX_NC_CHECK_STATUS v6; // r15d
  char v7; // r14
  char v8; // r12
  __int64 v11; // rdi
  __int64 v12; // r13
  __int64 v13; // rax
  struct _NAME_CACHE_CONTROL_ *v14; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v16; // rdi
  struct _LIST_ENTRY *Flink; // r15
  void *v18; // rcx
  int Blink; // eax
  int v20; // eax
  bool v21; // zf
  __int64 v23; // [rsp+30h] [rbp-48h]

  v5 = *(_QWORD *)(a1 + 56);
  v6 = RX_NC_SUCCESS;
  v7 = 0;
  v8 = 0;
  v11 = v5 + 360;
  v23 = v5 + 360;
  if ( v5 )
    v12 = *(_QWORD *)(v5 + 136);
  else
    v12 = 0;
  if ( *(_BYTE *)(a1 + 32) )
    v13 = *(_QWORD *)(v5 + 120);
  else
    v13 = *(_QWORD *)(a1 + 648);
  v14 = (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v13 + 40) + 1024LL);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v14, v11, 0, 0);
  v16 = Entry;
  if ( Entry )
  {
    v6 = RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart);
    if ( v6 )
    {
      v8 = 1;
      RxNameCacheExpireEntry(v14, v16);
    }
    else
    {
      Flink = v16->Link.Flink;
      if ( !RtlEqualSid((PSID)(v12 + 16), &Flink[261].Blink) || (BYTE2(Flink->Flink) & 1) != 0 )
      {
        v8 = 1;
        RxNameCacheExpireEntry(v14, v16);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
        {
          WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids, v23);
        }
        *(_WORD *)(a4 + 52) |= 0x400u;
        _MRxSmbAllocateSideBuffer(a1, a4);
        v18 = *(void **)(a4 + 16);
        if ( v18 )
        {
          v7 = 1;
          memmove(v18, &Flink[5].Blink, LODWORD(Flink[3].Blink));
          *(_WORD *)a4 = Flink[1].Flink;
          *(_DWORD *)(a4 + 4) = HIDWORD(Flink[1].Flink);
          *(_QWORD *)(a4 + 8) = 0;
          *(_WORD *)(a4 + 52) &= ~2u;
          *(_WORD *)(a4 + 28) = 257;
          *(_BYTE *)(a4 + 30) = 0;
          *(_DWORD *)(a4 + 32) = Flink[3].Flink;
          *(_DWORD *)(a4 + 36) = HIDWORD(Flink[3].Flink);
          Blink = (int)Flink[3].Blink;
          *(_WORD *)(a4 + 52) |= 1u;
          *(_DWORD *)(a4 + 40) = Blink;
          *(_DWORD *)(a4 + 48) = 0;
          *(_BYTE *)(a4 + 58) = BYTE2(Flink[4].Blink);
          RxNameCacheActivateEntry(v14, v16, 0, 0);
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids);
          }
          RxNameCacheExpireEntry(v14, v16);
          v16 = 0;
          v7 = 0;
        }
      }
      v6 = RX_NC_SUCCESS;
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  if ( v16 )
  {
    if ( v6 == RX_NC_SUCCESS && !v8 )
    {
      v20 = MrxSmbUnalignedDirEntryCopyTail(a1, 3, a2, a3, a4);
      v21 = *(_QWORD *)(a4 + 16) == 0;
      *a5 = v20;
      if ( v21 )
        *(_WORD *)(a4 + 52) |= 0x20u;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x140043f88  mov     [rsp+arg_18], rbx
0x140043f8d  mov     [rsp+arg_10], r8
0x140043f92  mov     [rsp+arg_8], rdx
0x140043f97  push    rbp
0x140043f98  push    rsi
0x140043f99  push    rdi
0x140043f9a  push    r12
0x140043f9c  push    r13
0x140043f9e  push    r14
0x140043fa0  push    r15
0x140043fa2  sub     rsp, 40h
0x140043fa6  mov     rax, [rcx+38h]
0x140043faa  xor     r15d, r15d
0x140043fad  xor     r14b, r14b
0x140043fb0  xor     r12b, r12b
0x140043fb3  mov     rbx, r9
0x140043fb6  mov     rbp, rcx
0x140043fb9  lea     rdi, [rax+168h]
0x140043fc0  mov     [rsp+78h+var_48], rdi
0x140043fc5  test    rax, rax
0x140043fc8  jnz     short loc_140043FCF
0x140043fca  xor     r13d, r13d
0x140043fcd  jmp     short loc_140043FD6
0x140043fcf  mov     r13, [rax+88h]
0x140043fd6  cmp     [rcx+20h], r12b
0x140043fda  jnz     short loc_140043FE5
0x140043fdc  mov     rax, [rcx+288h]
0x140043fe3  jmp     short loc_140043FE9
0x140043fe5  mov     rax, [rax+78h]
0x140043fe9  mov     rsi, [rax+28h]
0x140043fed  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x140043ff4  add     rsi, 400h
0x140043ffb  call    cs:__imp_ExAcquireFastMutex
0x140044002  nop     dword ptr [rax+rax+00h]
0x140044007  xor     r9d, r9d
0x14004400a  xor     r8d, r8d
0x14004400d  mov     rdx, rdi
0x140044010  mov     rcx, rsi
0x140044013  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004401a  nop     dword ptr [rax+rax+00h]
0x14004401f  mov     rdi, rax
0x140044022  test    rax, rax
0x140044025  jz      loc_1400441CC
0x14004402b  mov     edx, [rax+20h]; MRxContext
0x14004402e  mov     rcx, rax; NameCache
0x140044031  call    cs:__imp_RxNameCacheCheckEntry
0x140044038  nop     dword ptr [rax+rax+00h]
0x14004403d  mov     [rsp+78h+arg_0], eax
0x140044044  mov     r15d, eax
0x140044047  test    eax, eax
0x140044049  jnz     loc_1400441B7
0x14004404f  mov     r15, [rdi+28h]
0x140044053  lea     rcx, [r13+10h]; Sid1
0x140044057  lea     rdx, [r15+1058h]; Sid2
0x14004405e  call    cs:__imp_RtlEqualSid
0x140044065  nop     dword ptr [rax+rax+00h]
0x14004406a  test    al, al
0x14004406c  jz      loc_14004419D
0x140044072  test    byte ptr [r15+2], 1
0x140044077  jnz     loc_14004419D
0x14004407d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044084  lea     r14, WPP_GLOBAL_Control
0x14004408b  cmp     rcx, r14
0x14004408e  jz      short loc_1400440B3
0x140044090  test    dword ptr [rcx+2Ch], 200h
0x140044097  jz      short loc_1400440B3
0x140044099  mov     r9, [rsp+78h+var_48]
0x14004409e  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x1400440a5  mov     rcx, [rcx+18h]
0x1400440a9  mov     edx, 13h
0x1400440ae  call    WPP_SF_Z
0x1400440b3  mov     eax, 400h
0x1400440b8  mov     rdx, rbx
0x1400440bb  or      [rbx+34h], ax
0x1400440bf  mov     rcx, rbp
0x1400440c2  call    __MRxSmbAllocateSideBuffer
0x1400440c7  mov     rcx, [rbx+10h]; void *
0x1400440cb  test    rcx, rcx
0x1400440ce  jnz     short loc_14004411E
0x1400440d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400440d7  cmp     rcx, r14
0x1400440da  jz      short loc_1400440FA
0x1400440dc  test    dword ptr [rcx+2Ch], 100h
0x1400440e3  jz      short loc_1400440FA
0x1400440e5  mov     rcx, [rcx+18h]
0x1400440e9  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x1400440f0  mov     edx, 14h
0x1400440f5  call    WPP_SF_
0x1400440fa  mov     rdx, rdi; NameCache
0x1400440fd  mov     rcx, rsi; NameCacheCtl
0x140044100  call    cs:__imp_RxNameCacheExpireEntry
0x140044107  nop     dword ptr [rax+rax+00h]
0x14004410c  xor     edi, edi
0x14004410e  xor     r14b, r14b
0x140044111  mov     r15d, [rsp+78h+arg_0]
0x140044119  jmp     loc_1400441CC
0x14004411e  mov     r8d, [r15+38h]; Size
0x140044122  lea     rdx, [r15+58h]; Src
0x140044126  mov     r14b, 1
0x140044129  call    memmove
0x14004412e  movzx   eax, word ptr [r15+10h]
0x140044133  xor     r9d, r9d; MRxContext
0x140044136  mov     [rbx], ax
0x140044139  xor     r8d, r8d; LifeTime
0x14004413c  mov     eax, [r15+14h]
0x140044140  mov     rdx, rdi; NameCache
0x140044143  mov     [rbx+4], eax
0x140044146  mov     rcx, rsi; NameCacheCtl
0x140044149  mov     qword ptr [rbx+8], 0
0x140044151  mov     eax, 0FFFDh
0x140044156  and     [rbx+34h], ax
0x14004415a  mov     word ptr [rbx+1Ch], 101h
0x140044160  mov     [rbx+1Eh], r12b
0x140044164  mov     eax, [r15+30h]
0x140044168  mov     [rbx+20h], eax
0x14004416b  mov     eax, [r15+34h]
0x14004416f  mov     [rbx+24h], eax
0x140044172  mov     eax, [r15+38h]
0x140044176  or      word ptr [rbx+34h], 1
0x14004417b  mov     [rbx+28h], eax
0x14004417e  mov     dword ptr [rbx+30h], 0
0x140044185  mov     al, [r15+4Ah]
0x140044189  mov     [rbx+3Ah], al
0x14004418c  call    cs:__imp_RxNameCacheActivateEntry
0x140044193  nop     dword ptr [rax+rax+00h]
0x140044198  jmp     loc_140044111
0x14004419d  mov     rdx, rdi; NameCache
0x1400441a0  mov     rcx, rsi; NameCacheCtl
0x1400441a3  mov     r12b, 1
0x1400441a6  call    cs:__imp_RxNameCacheExpireEntry
0x1400441ad  nop     dword ptr [rax+rax+00h]
0x1400441b2  jmp     loc_140044111
0x1400441b7  mov     rdx, rdi; NameCache
0x1400441ba  mov     rcx, rsi; NameCacheCtl
0x1400441bd  mov     r12b, 1
0x1400441c0  call    cs:__imp_RxNameCacheExpireEntry
0x1400441c7  nop     dword ptr [rax+rax+00h]
0x1400441cc  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x1400441d3  call    cs:__imp_ExReleaseFastMutex
0x1400441da  nop     dword ptr [rax+rax+00h]
0x1400441df  test    rdi, rdi
0x1400441e2  jz      short loc_140044225
0x1400441e4  test    r15d, r15d
0x1400441e7  jnz     short loc_140044225
0x1400441e9  test    r12b, r12b
0x1400441ec  jnz     short loc_140044225
0x1400441ee  mov     r9, [rsp+78h+arg_10]
0x1400441f6  lea     edx, [r15+3]
0x1400441fa  mov     r8, [rsp+78h+arg_8]
0x140044202  mov     rcx, rbp
0x140044205  mov     [rsp+78h+var_58], rbx
0x14004420a  call    MrxSmbUnalignedDirEntryCopyTail
0x14004420f  cmp     qword ptr [rbx+10h], 0
0x140044214  mov     rcx, [rsp+78h+arg_20]
0x14004421c  mov     [rcx], eax
0x14004421e  jnz     short loc_140044225
0x140044220  or      word ptr [rbx+34h], 20h
0x140044225  mov     rbx, [rsp+78h+arg_18]
0x14004422d  mov     al, r14b
0x140044230  add     rsp, 40h
0x140044234  pop     r15
0x140044236  pop     r14
0x140044238  pop     r13
0x14004423a  pop     r12
0x14004423c  pop     rdi
0x14004423d  pop     rsi
0x14004423e  pop     rbp
0x14004423f  retn
```
