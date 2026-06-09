# CDDPDEV::TrimAllocations(D3DDDI_TRIMRESIDENCYSET_FLAGS,unsigned __int64,int)

- ea: `0x1400218e4`
- end: `0x140021d55`
- name: `?TrimAllocations@CDDPDEV@@QEAAJUD3DDDI_TRIMRESIDENCYSET_FLAGS@@_KH@Z`
- size: `1137`
- prototype: `__int64 __fastcall(CDDPDEV *__hidden this, struct D3DDDI_TRIMRESIDENCYSET_FLAGS, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002b480`

## callees

- `0x1400023c0`
- `0x140002420`
- `0x1400113d4`
- `0x140012e98`
- `0x1400218e4`
- `0x14002d3a4`
- `0x14002e784`
- `0x14002e960`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdWarning` at `0x140021cde`
- `watchdog!WdLogNewEntry5_WdWarning` at `0x140021cde`
- `watchdog!WdLogSingleEntry1` at `0x140021aa4`
- `watchdog!WdLogSingleEntry1` at `0x140021c2b`
- `watchdog!WdLogSingleEntry1` at `0x140021c8a`
- `watchdog!WdLogSingleEntry1` at `0x140021cc7`
- `watchdog!WdLogSingleEntry1` at `0x140021aa4`
- `watchdog!WdLogSingleEntry1` at `0x140021c2b`
- `watchdog!WdLogSingleEntry1` at `0x140021c8a`
- `watchdog!WdLogSingleEntry1` at `0x140021cc7`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021abb`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021c42`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021abb`
- `watchdog!WdLogNewEntry5_WdError` at `0x140021c42`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400219c4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021a22`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021b92`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400219c4`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021a22`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021b92`
- `watchdog!WdLogSingleEntry0` at `0x1400219ae`
- `watchdog!WdLogSingleEntry0` at `0x140021a0c`
- `watchdog!WdLogSingleEntry0` at `0x140021b7c`
- `watchdog!WdLogSingleEntry0` at `0x1400219ae`
- `watchdog!WdLogSingleEntry0` at `0x140021a0c`
- `watchdog!WdLogSingleEntry0` at `0x140021b7c`

## pseudocode

```c
__int64 __fastcall CDDPDEV::TrimAllocations(
        CDDPDEV *this,
        struct D3DDDI_TRIMRESIDENCYSET_FLAGS a2,
        unsigned __int64 a3)
{
  char v4; // di
  unsigned __int64 v5; // rcx
  int v7; // r13d
  unsigned int v8; // r15d
  char v9; // r14
  CDDPDEV *v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  char v21; // r14
  CDDPDEV *v22; // rbp
  __int64 v23; // rdx
  __int64 v24; // rcx
  _QWORD *v25; // rax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rcx
  int v30; // ebp
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  CDDPDEV *v33; // rcx
  void *v34; // rdx
  unsigned __int64 v35; // [rsp+80h] [rbp+8h] BYREF

  v4 = (char)a2.0;
  v5 = 0;
  if ( (*((_DWORD *)this + 686) & 0x400) != 0 )
    return 0;
  v7 = *(_BYTE *)&a2.0 & 1;
  if ( (*(_BYTE *)&a2.0 & 1) == 0 && (*(_BYTE *)&a2.0 & 2) == 0 && (*(_BYTE *)&a2.0 & 4) == 0 )
    return 3221225485LL;
  v8 = 0;
  v9 = 1;
  if ( (*(_BYTE *)&a2.0 & 4) != 0 )
    v5 = a3;
  v35 = v5;
  if ( (*(_BYTE *)&a2.0 & 1) != 0 )
  {
    while ( v9 )
    {
      CDDPDEV::AcquireResidencyLock(this);
      if ( !*((_QWORD *)this + 1593) )
      {
        CDDPDEV::ReleaseResidencyLock(this);
        break;
      }
      v10 = (CDDPDEV *)*((_QWORD *)this + 1599);
      if ( v10 == (CDDPDEV *)((char *)this + 12784) || *((_QWORD *)v10 - 1) >= *((_QWORD *)this + 1597) )
      {
        v9 = 0;
      }
      else
      {
        CDDPDEV::RemoveLruListEntry(this, *((struct _LIST_ENTRY **)this + 1599));
        if ( !*((_BYTE *)v10 - 24) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 957;
          v13 = (_QWORD *)WdLogNewEntry5_WdAssertion(v12, v11);
          v13[3] = gCddImageInfo;
          v13[4] = (unsigned int)dword_14003E570;
          v13[5] = 215857758;
          WdLogGlobalForLineNumber = 957;
        }
        if ( CDDPDEV::IsCommandBufferFencePending(this, *((_QWORD *)v10 - 1)) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 958;
          v16 = (_QWORD *)WdLogNewEntry5_WdAssertion(v15, v14);
          v16[3] = gCddImageInfo;
          v16[4] = (unsigned int)dword_14003E570;
          v16[5] = 215857758;
          WdLogGlobalForLineNumber = 958;
        }
        if ( *((_BYTE *)v10 - 24) )
        {
          v17 = CDDPDEV::Evict(this, *(_DWORD *)(*((_QWORD *)v10 - 4) + 40LL), (struct D3DDDI_EVICT_FLAGS)1, &v35, 1);
          v8 = v17;
          if ( v17 < 0 )
          {
            v9 = 0;
            if ( (*((_DWORD *)this + 686) & 0x400) == 0 )
            {
              WdLogSingleEntry1(2, v17);
              WdLogGlobalForLineNumber = 983;
              v20 = (_QWORD *)WdLogNewEntry5_WdError(v19, v18);
              v20[3] = gCddImageInfo;
              v20[4] = (unsigned int)dword_14003E570;
              v20[5] = 215857758;
              WdLogGlobalForLineNumber = 983;
            }
          }
          else
          {
            *((_BYTE *)v10 - 24) = 0;
          }
        }
      }
      CDDPDEV::ReleaseResidencyLock(this);
    }
  }
  if ( (v4 & 4) == 0 )
    goto LABEL_48;
  v21 = 1;
  while ( v21 && v35 )
  {
    CDDPDEV::AcquireResidencyLock(this);
    if ( !*((_QWORD *)this + 1593) )
    {
      CDDPDEV::ReleaseResidencyLock(this);
      break;
    }
    v22 = (CDDPDEV *)*((_QWORD *)this + 1599);
    if ( v22 == (CDDPDEV *)((char *)this + 12784) || *((_QWORD *)v22 - 1) > *((_QWORD *)this + 1595) )
    {
      v21 = 0;
    }
    else
    {
      CDDPDEV::RemoveLruListEntry(this, *((struct _LIST_ENTRY **)this + 1599));
      if ( *((_BYTE *)v22 - 24)
        || (WdLogSingleEntry0(1),
            WdLogGlobalForLineNumber = 1027,
            v25 = (_QWORD *)WdLogNewEntry5_WdAssertion(v24, v23),
            v25[3] = gCddImageInfo,
            v25[4] = (unsigned int)dword_14003E570,
            v25[5] = 215857758,
            WdLogGlobalForLineNumber = 1027,
            *((_BYTE *)v22 - 24)) )
      {
        v26 = CDDPDEV::WaitForCommandBufferMonitoredFence(this, *((_QWORD *)v22 - 1));
        v8 = v26;
        if ( v26 < 0 )
        {
          v21 = 0;
          if ( (*((_DWORD *)this + 686) & 0x400) == 0 )
          {
            WdLogSingleEntry1(2, v26);
            v30 = 1063;
            goto LABEL_40;
          }
        }
        else
        {
          v27 = CDDPDEV::Evict(this, *(_DWORD *)(*((_QWORD *)v22 - 4) + 40LL), (struct D3DDDI_EVICT_FLAGS)1, &v35, 1);
          v8 = v27;
          if ( v27 >= 0 )
          {
            *((_BYTE *)v22 - 24) = 0;
            goto LABEL_44;
          }
          v21 = 0;
          if ( (*((_DWORD *)this + 686) & 0x400) == 0 )
          {
            WdLogSingleEntry1(2, v27);
            v30 = 1053;
LABEL_40:
            WdLogGlobalForLineNumber = v30;
            v31 = (_QWORD *)WdLogNewEntry5_WdError(v29, v28);
            v31[3] = gCddImageInfo;
            v31[4] = (unsigned int)dword_14003E570;
            v31[5] = 215857758;
            WdLogGlobalForLineNumber = v30;
          }
        }
      }
    }
LABEL_44:
    CDDPDEV::ReleaseResidencyLock(this);
  }
  if ( v35 )
  {
    WdLogSingleEntry1(3, v35);
    WdLogGlobalForLineNumber = 1075;
    v32 = (_QWORD *)WdLogNewEntry5_WdWarning();
    v32[3] = gCddImageInfo;
    v32[4] = (unsigned int)dword_14003E570;
    v32[5] = 215857758;
    WdLogGlobalForLineNumber = 1075;
  }
LABEL_48:
  if ( v7 || (v4 & 2) != 0 )
  {
    CDDPDEV::AcquireResidencyLock(this);
    v34 = (void *)*((_QWORD *)this + 1593);
    if ( v34 )
      *((_QWORD *)this + 1597) = CDDPDEV::GetMonitoredFenceValue(v33, v34);
    CDDPDEV::ReleaseResidencyLock(this);
  }
  return v8;
}

```

## disassembly

```asm
0x1400218e4  push    rbx
0x1400218e6  push    rbp
0x1400218e7  push    rsi
0x1400218e8  push    rdi
0x1400218e9  push    r12
0x1400218eb  push    r13
0x1400218ed  push    r14
0x1400218ef  push    r15
0x1400218f1  sub     rsp, 38h
0x1400218f5  mov     rsi, rcx
0x1400218f8  mov     edi, edx
0x1400218fa  xor     ecx, ecx
0x1400218fc  test    dword ptr [rsi+0AB8h], 400h
0x140021906  jz      short loc_14002190F
0x140021908  xor     eax, eax
0x14002190a  jmp     loc_140021D43
0x14002190f  mov     r13d, edi
0x140021912  mov     ebx, 1
0x140021917  and     r13d, ebx
0x14002191a  jnz     short loc_140021932
0x14002191c  test    dil, 2
0x140021920  jnz     short loc_140021932
0x140021922  test    dil, 4
0x140021926  jnz     short loc_140021932
0x140021928  mov     eax, 0C000000Dh
0x14002192d  jmp     loc_140021D43
0x140021932  xor     r15d, r15d
0x140021935  mov     r12d, edi
0x140021938  and     r12d, 4
0x14002193c  mov     r14b, bl
0x14002193f  cmovnz  rcx, r8
0x140021943  mov     [rsp+78h+arg_0], rcx
0x14002194b  test    r13d, r13d
0x14002194e  jz      loc_140021B04
0x140021954  test    r14b, r14b
0x140021957  jz      loc_140021B04
0x14002195d  mov     rcx, rsi; this
0x140021960  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x140021965  cmp     qword ptr [rsi+31C8h], 0
0x14002196d  jz      loc_140021AFC
0x140021973  mov     rbp, [rsi+31F8h]
0x14002197a  lea     rax, [rsi+31F0h]
0x140021981  cmp     rbp, rax
0x140021984  jz      loc_140021AEC
0x14002198a  mov     rax, [rsi+31E8h]
0x140021991  cmp     [rbp-8], rax
0x140021995  jnb     loc_140021AEC
0x14002199b  mov     rdx, rbp; struct _LIST_ENTRY *
0x14002199e  mov     rcx, rsi; this
0x1400219a1  call    ?RemoveLruListEntry@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntry(_LIST_ENTRY *)
0x1400219a6  cmp     byte ptr [rbp-18h], 0
0x1400219aa  jnz     short loc_1400219FA
0x1400219ac  mov     ecx, ebx
0x1400219ae  call    cs:__imp_WdLogSingleEntry0
0x1400219b5  nop     dword ptr [rax+rax+00h]
0x1400219ba  mov     cs:WdLogGlobalForLineNumber, 3BDh
0x1400219c4  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400219cb  nop     dword ptr [rax+rax+00h]
0x1400219d0  mov     rcx, rax
0x1400219d3  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400219da  mov     [rcx+18h], rax
0x1400219de  mov     eax, cs:dword_14003E570
0x1400219e4  mov     [rcx+20h], rax
0x1400219e8  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x1400219f0  mov     cs:WdLogGlobalForLineNumber, 3BDh
0x1400219fa  mov     rdx, [rbp-8]; unsigned __int64
0x1400219fe  mov     rcx, rsi; this
0x140021a01  call    ?IsCommandBufferFencePending@CDDPDEV@@QEAAE_K@Z; CDDPDEV::IsCommandBufferFencePending(unsigned __int64)
0x140021a06  test    al, al
0x140021a08  jz      short loc_140021A58
0x140021a0a  mov     ecx, ebx
0x140021a0c  call    cs:__imp_WdLogSingleEntry0
0x140021a13  nop     dword ptr [rax+rax+00h]
0x140021a18  mov     cs:WdLogGlobalForLineNumber, 3BEh
0x140021a22  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140021a29  nop     dword ptr [rax+rax+00h]
0x140021a2e  mov     rcx, rax
0x140021a31  mov     rax, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021a38  mov     [rcx+18h], rax
0x140021a3c  mov     eax, cs:dword_14003E570
0x140021a42  mov     [rcx+20h], rax
0x140021a46  mov     qword ptr [rcx+28h], 0CDDBA5Eh
0x140021a4e  mov     cs:WdLogGlobalForLineNumber, 3BEh
0x140021a58  cmp     byte ptr [rbp-18h], 0
0x140021a5c  jz      loc_140021AEF
0x140021a62  mov     rdx, [rbp-20h]
0x140021a66  lea     r9, [rsp+78h+arg_0]; unsigned __int64 *
0x140021a6e  mov     r8d, ebx; struct D3DDDI_EVICT_FLAGS
0x140021a71  mov     [rsp+78h+var_58], ebx; int
0x140021a75  mov     rcx, rsi; this
0x140021a78  mov     edx, [rdx+28h]; unsigned int
0x140021a7b  call    ?Evict@CDDPDEV@@QEAAJIUD3DDDI_EVICT_FLAGS@@PEA_KH@Z; CDDPDEV::Evict(uint,D3DDDI_EVICT_FLAGS,unsigned __int64 *,int)
0x140021a80  movsxd  r15, eax
0x140021a83  test    eax, eax
0x140021a85  js      short loc_140021A8D
0x140021a87  mov     byte ptr [rbp-18h], 0
0x140021a8b  jmp     short loc_140021AEF
0x140021a8d  xor     r14b, r14b
0x140021a90  test    dword ptr [rsi+0AB8h], 400h
0x140021a9a  jnz     short loc_140021AEF
0x140021a9c  mov     rdx, r15
0x140021a9f  mov     ecx, 2
0x140021aa4  call    cs:__imp_WdLogSingleEntry1
0x140021aab  nop     dword ptr [rax+rax+00h]
0x140021ab0  mov     ebp, 3D7h
0x140021ab5  mov     cs:WdLogGlobalForLineNumber, ebp
0x140021abb  call    cs:__imp_WdLogNewEntry5_WdError
0x140021ac2  nop     dword ptr [rax+rax+00h]
0x140021ac7  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021ace  mov     [rax+18h], rcx
0x140021ad2  mov     ecx, cs:dword_14003E570
0x140021ad8  mov     [rax+20h], rcx
0x140021adc  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021ae4  mov     cs:WdLogGlobalForLineNumber, ebp
0x140021aea  jmp     short loc_140021AEF
0x140021aec  xor     r14b, r14b
0x140021aef  mov     rcx, rsi; this
0x140021af2  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140021af7  jmp     loc_140021954
0x140021afc  mov     rcx, rsi; this
0x140021aff  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140021b04  test    r12d, r12d
0x140021b07  jz      loc_140021D0D
0x140021b0d  mov     r14b, bl
0x140021b10  test    r14b, r14b
0x140021b13  jz      loc_140021CB5
0x140021b19  cmp     [rsp+78h+arg_0], 0
0x140021b22  jbe     loc_140021CB5
0x140021b28  mov     rcx, rsi; this
0x140021b2b  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x140021b30  cmp     qword ptr [rsi+31C8h], 0
0x140021b38  jz      loc_140021CAD
0x140021b3e  mov     rbp, [rsi+31F8h]
0x140021b45  lea     rax, [rsi+31F0h]
0x140021b4c  cmp     rbp, rax
0x140021b4f  jz      loc_140021C9D
0x140021b55  mov     rax, [rsi+31D8h]
0x140021b5c  cmp     [rbp-8], rax
0x140021b60  ja      loc_140021C9D
0x140021b66  mov     rdx, rbp; struct _LIST_ENTRY *
0x140021b69  mov     rcx, rsi; this
0x140021b6c  call    ?RemoveLruListEntry@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntry(_LIST_ENTRY *)
0x140021b71  xor     r12d, r12d
0x140021b74  cmp     [rbp-18h], r12b
0x140021b78  jnz     short loc_140021BCF
0x140021b7a  mov     ecx, ebx
0x140021b7c  call    cs:__imp_WdLogSingleEntry0
0x140021b83  nop     dword ptr [rax+rax+00h]
0x140021b88  mov     cs:WdLogGlobalForLineNumber, 403h
0x140021b92  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140021b99  nop     dword ptr [rax+rax+00h]
0x140021b9e  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021ba5  mov     [rax+18h], rcx
0x140021ba9  mov     ecx, cs:dword_14003E570
0x140021baf  mov     [rax+20h], rcx
0x140021bb3  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021bbb  mov     cs:WdLogGlobalForLineNumber, 403h
0x140021bc5  cmp     [rbp-18h], r12b
0x140021bc9  jz      loc_140021CA0
0x140021bcf  mov     rdx, [rbp-8]; unsigned __int64
0x140021bd3  mov     rcx, rsi; this
0x140021bd6  call    ?WaitForCommandBufferMonitoredFence@CDDPDEV@@QEAAJ_K@Z; CDDPDEV::WaitForCommandBufferMonitoredFence(unsigned __int64)
0x140021bdb  movsxd  r15, eax
0x140021bde  test    eax, eax
0x140021be0  js      loc_140021C73
0x140021be6  mov     rdx, [rbp-20h]
0x140021bea  lea     r9, [rsp+78h+arg_0]; unsigned __int64 *
0x140021bf2  mov     r8d, ebx; struct D3DDDI_EVICT_FLAGS
0x140021bf5  mov     [rsp+78h+var_58], ebx; int
0x140021bf9  mov     rcx, rsi; this
0x140021bfc  mov     edx, [rdx+28h]; unsigned int
0x140021bff  call    ?Evict@CDDPDEV@@QEAAJIUD3DDDI_EVICT_FLAGS@@PEA_KH@Z; CDDPDEV::Evict(uint,D3DDDI_EVICT_FLAGS,unsigned __int64 *,int)
0x140021c04  movsxd  r15, eax
0x140021c07  test    eax, eax
0x140021c09  js      short loc_140021C14
0x140021c0b  mov     [rbp-18h], r12b
0x140021c0f  jmp     loc_140021CA0
0x140021c14  xor     r14b, r14b
0x140021c17  test    dword ptr [rsi+0AB8h], 400h
0x140021c21  jnz     short loc_140021CA0
0x140021c23  mov     rdx, r15
0x140021c26  mov     ecx, 2
0x140021c2b  call    cs:__imp_WdLogSingleEntry1
0x140021c32  nop     dword ptr [rax+rax+00h]
0x140021c37  mov     ebp, 41Dh
0x140021c3c  mov     cs:WdLogGlobalForLineNumber, ebp
0x140021c42  call    cs:__imp_WdLogNewEntry5_WdError
0x140021c49  nop     dword ptr [rax+rax+00h]
0x140021c4e  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021c55  mov     [rax+18h], rcx
0x140021c59  mov     ecx, cs:dword_14003E570
0x140021c5f  mov     [rax+20h], rcx
0x140021c63  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021c6b  mov     cs:WdLogGlobalForLineNumber, ebp
0x140021c71  jmp     short loc_140021CA0
0x140021c73  xor     r14b, r14b
0x140021c76  test    dword ptr [rsi+0AB8h], 400h
0x140021c80  jnz     short loc_140021CA0
0x140021c82  mov     rdx, r15
0x140021c85  mov     ecx, 2
0x140021c8a  call    cs:__imp_WdLogSingleEntry1
0x140021c91  nop     dword ptr [rax+rax+00h]
0x140021c96  mov     ebp, 427h
0x140021c9b  jmp     short loc_140021C3C
0x140021c9d  xor     r14b, r14b
0x140021ca0  mov     rcx, rsi; this
0x140021ca3  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140021ca8  jmp     loc_140021B10
0x140021cad  mov     rcx, rsi; this
0x140021cb0  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140021cb5  mov     rdx, [rsp+78h+arg_0]
0x140021cbd  test    rdx, rdx
0x140021cc0  jz      short loc_140021D0D
0x140021cc2  mov     ecx, 3
0x140021cc7  call    cs:__imp_WdLogSingleEntry1
0x140021cce  nop     dword ptr [rax+rax+00h]
0x140021cd3  mov     ebx, 433h
0x140021cd8  mov     cs:WdLogGlobalForLineNumber, ebx
0x140021cde  call    cs:__imp_WdLogNewEntry5_WdWarning
0x140021ce5  nop     dword ptr [rax+rax+00h]
0x140021cea  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021cf1  mov     [rax+18h], rcx
0x140021cf5  mov     ecx, cs:dword_14003E570
0x140021cfb  mov     [rax+20h], rcx
0x140021cff  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021d07  mov     cs:WdLogGlobalForLineNumber, ebx
0x140021d0d  test    r13d, r13d
0x140021d10  jnz     short loc_140021D18
0x140021d12  test    dil, 2
0x140021d16  jz      short loc_140021D40
0x140021d18  mov     rcx, rsi; this
0x140021d1b  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x140021d20  mov     rdx, [rsi+31C8h]; void *
0x140021d27  test    rdx, rdx
0x140021d2a  jz      short loc_140021D38
0x140021d2c  call    ?GetMonitoredFenceValue@CDDPDEV@@QEAA_KPEAX@Z; CDDPDEV::GetMonitoredFenceValue(void *)
0x140021d31  mov     [rsi+31E8h], rax
0x140021d38  mov     rcx, rsi; this
0x140021d3b  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x140021d40  mov     eax, r15d
0x140021d43  add     rsp, 38h
0x140021d47  pop     r15
0x140021d49  pop     r14
0x140021d4b  pop     r13
0x140021d4d  pop     r12
0x140021d4f  pop     rdi
0x140021d50  pop     rsi
0x140021d51  pop     rbp
0x140021d52  pop     rbx
0x140021d53  retn
```
