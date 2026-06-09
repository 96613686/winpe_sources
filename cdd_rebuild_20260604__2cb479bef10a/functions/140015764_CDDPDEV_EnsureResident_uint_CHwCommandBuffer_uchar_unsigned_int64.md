# CDDPDEV::EnsureResident(uint,CHwCommandBuffer *,uchar,unsigned __int64 *)

- ea: `0x140015764`
- end: `0x140015ac5`
- name: `?EnsureResident@CDDPDEV@@QEAAJIPEAVCHwCommandBuffer@@EPEA_K@Z`
- size: `865`
- prototype: `__int64 __usercall@<rax>(CDDPDEV *__hidden this@<rcx>, unsigned int@<edx>, struct CHwCommandBuffer *@<r8>, unsigned __int8@<r9b>, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400112f0`
- `0x14001b448`

## callees

- `0x1400113d4`
- `0x140012c34`
- `0x140015764`
- `0x140015ad0`
- `0x14002d3a4`
- `0x14002e960`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogSingleEntry1` at `0x1400159c0`
- `watchdog!WdLogSingleEntry1` at `0x1400159de`
- `watchdog!WdLogSingleEntry1` at `0x140015a21`
- `watchdog!WdLogSingleEntry1` at `0x140015a64`
- `watchdog!WdLogSingleEntry1` at `0x1400159c0`
- `watchdog!WdLogSingleEntry1` at `0x1400159de`
- `watchdog!WdLogSingleEntry1` at `0x140015a21`
- `watchdog!WdLogSingleEntry1` at `0x140015a64`
- `watchdog!WdLogNewEntry5_WdError` at `0x140015a7b`
- `watchdog!WdLogNewEntry5_WdError` at `0x140015a7b`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400157bf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015873`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400158ef`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400157bf`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015873`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x1400158ef`
- `watchdog!WdLogSingleEntry0` at `0x1400157a8`
- `watchdog!WdLogSingleEntry0` at `0x14001585d`
- `watchdog!WdLogSingleEntry0` at `0x1400158d9`
- `watchdog!WdLogSingleEntry0` at `0x1400157a8`
- `watchdog!WdLogSingleEntry0` at `0x14001585d`
- `watchdog!WdLogSingleEntry0` at `0x1400158d9`

## pseudocode

```c
__int64 __fastcall CDDPDEV::EnsureResident(
        CDDPDEV *this,
        unsigned int a2,
        struct CHwCommandBuffer *a3,
        char a4,
        unsigned __int64 *a5)
{
  __int64 v7; // rdx
  __int64 v8; // rcx
  _QWORD *v9; // rax
  unsigned int Resident; // eax
  _QWORD *v11; // r15
  unsigned int v12; // esi
  unsigned __int64 v13; // rsi
  __int64 v14; // rdx
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  int v24; // ebx
  int v25; // eax
  unsigned __int64 v26; // rdx
  int v27; // eax
  _QWORD *v28; // rax
  unsigned __int64 v30; // [rsp+30h] [rbp-10h] BYREF
  _QWORD *v31; // [rsp+38h] [rbp-8h]
  unsigned __int64 v32; // [rsp+80h] [rbp+40h] BYREF
  struct CHwCommandBuffer *v33; // [rsp+90h] [rbp+50h]
  char v34; // [rsp+98h] [rbp+58h]

  v34 = a4;
  v33 = a3;
  if ( *(struct _KTHREAD **)(*((_QWORD *)this + 1600) + 8LL) != KeGetCurrentThread() )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 735;
    v9 = (_QWORD *)WdLogNewEntry5_WdAssertion(v8, v7);
    v9[3] = gCddImageInfo;
    v9[4] = (unsigned int)dword_14003E570;
    v9[5] = 215857758;
    WdLogGlobalForLineNumber = 735;
  }
  v30 = 0;
  v32 = 0;
  *a5 = 0;
  Resident = CDDPDEV::MakeResident(this, a2, 0, &v30, &v32);
  v11 = (_QWORD *)*((_QWORD *)this + 1599);
LABEL_4:
  v12 = Resident;
  if ( Resident == -1073741801 )
  {
    if ( v11 != (_QWORD *)((char *)this + 12784) && *(v11 - 1) <= *((_QWORD *)this + 1595) )
    {
      v13 = v32;
      if ( !v32 )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 769;
        v16 = (_QWORD *)WdLogNewEntry5_WdAssertion(v15, v14);
        v16[3] = gCddImageInfo;
        v16[4] = (unsigned int)dword_14003E570;
        v16[5] = 215857758;
        WdLogGlobalForLineNumber = 769;
        goto LABEL_9;
      }
      while ( 1 )
      {
        if ( v11 == (_QWORD *)((char *)this + 12784) || *(v11 - 1) > *((_QWORD *)this + 1595) )
        {
LABEL_21:
          Resident = CDDPDEV::MakeResident(this, a2, 0, &v30, &v32);
          goto LABEL_4;
        }
        v31 = (_QWORD *)v11[1];
        if ( !*((_BYTE *)v11 - 24) )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 779;
          v19 = (_QWORD *)WdLogNewEntry5_WdAssertion(v18, v17);
          v19[3] = gCddImageInfo;
          v19[4] = (unsigned int)dword_14003E570;
          v19[5] = 215857758;
          WdLogGlobalForLineNumber = 779;
        }
        if ( (!v33
           || !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*(v11 - 4) + 16LL))(
                 *(v11 - 4),
                 *((unsigned int *)v33 + 2)))
          && *((_BYTE *)v11 - 24) )
        {
          v20 = CDDPDEV::WaitForCommandBufferMonitoredFence(this, *(v11 - 1));
          v12 = v20;
          if ( v20 < 0 )
          {
            WdLogSingleEntry1(2, v20);
            v24 = 794;
            goto LABEL_30;
          }
          v21 = CDDPDEV::Evict(this, *(_DWORD *)(*(v11 - 4) + 40LL), (struct D3DDDI_EVICT_FLAGS)1, &v32, 0);
          v12 = v21;
          if ( v21 < 0 )
          {
            WdLogSingleEntry1(2, v21);
            v24 = 813;
            goto LABEL_30;
          }
          *((_BYTE *)v11 - 24) = 0;
          CDDPDEV::RemoveLruListEntry(this, (struct _LIST_ENTRY *)v11);
          v13 = v32;
        }
        v11 = v31;
LABEL_9:
        if ( !v13 )
          goto LABEL_21;
      }
    }
    v25 = CDDPDEV::MakeResident(this, a2, (struct D3DDDI_MAKERESIDENT_FLAGS)3, &v30, &v32);
    v12 = v25;
    if ( v25 < 0 )
    {
      WdLogSingleEntry1(2, v25);
      v24 = 845;
LABEL_30:
      WdLogGlobalForLineNumber = v24;
      v28 = (_QWORD *)WdLogNewEntry5_WdError(v23, v22);
      v28[3] = gCddImageInfo;
      v28[4] = (unsigned int)dword_14003E570;
      v28[5] = 215857758;
      WdLogGlobalForLineNumber = v24;
      return v12;
    }
  }
  if ( v12 == 259 )
  {
    v26 = v30;
    *a5 = v30;
    if ( v34 )
    {
      v27 = CDDPDEV::WaitForPagingQueueMonitoredFence(this, v26);
      v12 = v27;
      if ( v27 < 0 )
      {
        WdLogSingleEntry1(2, v27);
        v24 = 859;
        goto LABEL_30;
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x140015764  mov     [rsp-38h+arg_8], rbx
0x140015769  mov     [rsp-38h+arg_18], r9b
0x14001576e  mov     [rsp-38h+arg_10], r8
0x140015773  push    rbp
0x140015774  push    rsi
0x140015775  push    rdi
0x140015776  push    r12
0x140015778  push    r13
0x14001577a  push    r14
0x14001577c  push    r15
0x14001577e  mov     rbp, rsp
0x140015781  sub     rsp, 40h
0x140015785  mov     r10, gs:188h
0x14001578e  mov     r13d, edx
0x140015791  mov     rax, [rcx+3200h]
0x140015798  mov     r14, rcx
0x14001579b  mov     ebx, 1
0x1400157a0  cmp     [rax+8], r10
0x1400157a4  jz      short loc_1400157EE
0x1400157a6  mov     ecx, ebx
0x1400157a8  call    cs:__imp_WdLogSingleEntry0
0x1400157af  nop     dword ptr [rax+rax+00h]
0x1400157b4  mov     edi, 2DFh
0x1400157b9  mov     cs:WdLogGlobalForLineNumber, edi
0x1400157bf  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400157c6  nop     dword ptr [rax+rax+00h]
0x1400157cb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400157d2  mov     [rax+18h], rcx
0x1400157d6  mov     ecx, cs:dword_14003E570
0x1400157dc  mov     [rax+20h], rcx
0x1400157e0  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x1400157e8  mov     cs:WdLogGlobalForLineNumber, edi
0x1400157ee  mov     r12, [rbp+arg_20]
0x1400157f2  lea     r9, [rbp+var_10]; unsigned __int64 *
0x1400157f6  xor     eax, eax
0x1400157f8  mov     edx, r13d; unsigned int
0x1400157fb  mov     edi, eax
0x1400157fd  mov     [rbp+var_10], rax
0x140015801  mov     [rbp+arg_0], rax
0x140015805  mov     r8d, edi; struct D3DDDI_MAKERESIDENT_FLAGS
0x140015808  mov     [r12], rax
0x14001580c  mov     rcx, r14; this
0x14001580f  lea     rax, [rbp+arg_0]
0x140015813  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x140015818  call    ?MakeResident@CDDPDEV@@QEAAJIUD3DDDI_MAKERESIDENT_FLAGS@@PEA_K1@Z; CDDPDEV::MakeResident(uint,D3DDDI_MAKERESIDENT_FLAGS,unsigned __int64 *,unsigned __int64 *)
0x14001581d  mov     r15, [r14+31F8h]
0x140015824  mov     esi, eax
0x140015826  cmp     eax, 0C0000017h
0x14001582b  jnz     loc_140015A34
0x140015831  lea     r12, [r14+31F0h]
0x140015838  cmp     r15, r12
0x14001583b  jz      loc_1400159F4
0x140015841  mov     rax, [r14+31D8h]
0x140015848  cmp     [r15-8], rax
0x14001584c  ja      loc_1400159F4
0x140015852  mov     rsi, [rbp+arg_0]
0x140015856  test    rsi, rsi
0x140015859  jnz     short loc_1400158AF
0x14001585b  mov     ecx, ebx
0x14001585d  call    cs:__imp_WdLogSingleEntry0
0x140015864  nop     dword ptr [rax+rax+00h]
0x140015869  mov     cs:WdLogGlobalForLineNumber, 301h
0x140015873  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001587a  nop     dword ptr [rax+rax+00h]
0x14001587f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015886  mov     [rax+18h], rcx
0x14001588a  mov     ecx, cs:dword_14003E570
0x140015890  mov     [rax+20h], rcx
0x140015894  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001589c  mov     cs:WdLogGlobalForLineNumber, 301h
0x1400158a6  test    rsi, rsi
0x1400158a9  jz      loc_140015998
0x1400158af  cmp     r15, r12
0x1400158b2  jz      loc_140015998
0x1400158b8  mov     rax, [r14+31D8h]
0x1400158bf  cmp     [r15-8], rax
0x1400158c3  ja      loc_140015998
0x1400158c9  mov     rax, [r15+8]
0x1400158cd  mov     [rbp+var_8], rax
0x1400158d1  cmp     [r15-18h], dil
0x1400158d5  jnz     short loc_140015922
0x1400158d7  mov     ecx, ebx
0x1400158d9  call    cs:__imp_WdLogSingleEntry0
0x1400158e0  nop     dword ptr [rax+rax+00h]
0x1400158e5  mov     cs:WdLogGlobalForLineNumber, 30Bh
0x1400158ef  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x1400158f6  nop     dword ptr [rax+rax+00h]
0x1400158fb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015902  mov     [rax+18h], rcx
0x140015906  mov     ecx, cs:dword_14003E570
0x14001590c  mov     [rax+20h], rcx
0x140015910  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140015918  mov     cs:WdLogGlobalForLineNumber, 30Bh
0x140015922  mov     rdx, [rbp+arg_10]
0x140015926  test    rdx, rdx
0x140015929  jz      short loc_140015942
0x14001592b  mov     rcx, [r15-20h]
0x14001592f  mov     edx, [rdx+8]
0x140015932  mov     rax, [rcx]
0x140015935  mov     rax, [rax+10h]
0x140015939  call    _guard_dispatch_icall
0x14001593e  test    al, al
0x140015940  jnz     short loc_14001598F
0x140015942  cmp     [r15-18h], dil
0x140015946  jz      short loc_14001598F
0x140015948  mov     rdx, [r15-8]; unsigned __int64
0x14001594c  mov     rcx, r14; this
0x14001594f  call    ?WaitForCommandBufferMonitoredFence@CDDPDEV@@QEAAJ_K@Z; CDDPDEV::WaitForCommandBufferMonitoredFence(unsigned __int64)
0x140015954  movsxd  rsi, eax
0x140015957  test    eax, eax
0x140015959  js      short loc_1400159D6
0x14001595b  mov     rdx, [r15-20h]
0x14001595f  lea     r9, [rbp+arg_0]; unsigned __int64 *
0x140015963  mov     r8d, ebx; struct D3DDDI_EVICT_FLAGS
0x140015966  mov     dword ptr [rsp+40h+var_20], edi; int
0x14001596a  mov     rcx, r14; this
0x14001596d  mov     edx, [rdx+28h]; unsigned int
0x140015970  call    ?Evict@CDDPDEV@@QEAAJIUD3DDDI_EVICT_FLAGS@@PEA_KH@Z; CDDPDEV::Evict(uint,D3DDDI_EVICT_FLAGS,unsigned __int64 *,int)
0x140015975  movsxd  rsi, eax
0x140015978  test    eax, eax
0x14001597a  js      short loc_1400159B8
0x14001597c  mov     rdx, r15; struct _LIST_ENTRY *
0x14001597f  mov     [r15-18h], dil
0x140015983  mov     rcx, r14; this
0x140015986  call    ?RemoveLruListEntry@CDDPDEV@@QEAAEPEAU_LIST_ENTRY@@@Z; CDDPDEV::RemoveLruListEntry(_LIST_ENTRY *)
0x14001598b  mov     rsi, [rbp+arg_0]
0x14001598f  mov     r15, [rbp+var_8]
0x140015993  jmp     loc_1400158A6
0x140015998  lea     rax, [rbp+arg_0]
0x14001599c  mov     r8d, edi; struct D3DDDI_MAKERESIDENT_FLAGS
0x14001599f  lea     r9, [rbp+var_10]; unsigned __int64 *
0x1400159a3  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x1400159a8  mov     edx, r13d; unsigned int
0x1400159ab  mov     rcx, r14; this
0x1400159ae  call    ?MakeResident@CDDPDEV@@QEAAJIUD3DDDI_MAKERESIDENT_FLAGS@@PEA_K1@Z; CDDPDEV::MakeResident(uint,D3DDDI_MAKERESIDENT_FLAGS,unsigned __int64 *,unsigned __int64 *)
0x1400159b3  jmp     loc_140015824
0x1400159b8  mov     rdx, rsi
0x1400159bb  mov     ecx, 2
0x1400159c0  call    cs:__imp_WdLogSingleEntry1
0x1400159c7  nop     dword ptr [rax+rax+00h]
0x1400159cc  mov     ebx, 32Dh
0x1400159d1  jmp     loc_140015A75
0x1400159d6  mov     rdx, rsi
0x1400159d9  mov     ecx, 2
0x1400159de  call    cs:__imp_WdLogSingleEntry1
0x1400159e5  nop     dword ptr [rax+rax+00h]
0x1400159ea  mov     ebx, 31Ah
0x1400159ef  jmp     loc_140015A75
0x1400159f4  lea     rax, [rbp+arg_0]
0x1400159f8  mov     r8d, 3; struct D3DDDI_MAKERESIDENT_FLAGS
0x1400159fe  lea     r9, [rbp+var_10]; unsigned __int64 *
0x140015a02  mov     [rsp+40h+var_20], rax; unsigned __int64 *
0x140015a07  mov     edx, r13d; unsigned int
0x140015a0a  mov     rcx, r14; this
0x140015a0d  call    ?MakeResident@CDDPDEV@@QEAAJIUD3DDDI_MAKERESIDENT_FLAGS@@PEA_K1@Z; CDDPDEV::MakeResident(uint,D3DDDI_MAKERESIDENT_FLAGS,unsigned __int64 *,unsigned __int64 *)
0x140015a12  movsxd  rsi, eax
0x140015a15  test    eax, eax
0x140015a17  jns     short loc_140015A34
0x140015a19  mov     rdx, rsi
0x140015a1c  mov     ecx, 2
0x140015a21  call    cs:__imp_WdLogSingleEntry1
0x140015a28  nop     dword ptr [rax+rax+00h]
0x140015a2d  mov     ebx, 34Dh
0x140015a32  jmp     short loc_140015A75
0x140015a34  cmp     esi, 103h
0x140015a3a  jnz     short loc_140015AAA
0x140015a3c  mov     rax, [rbp+arg_20]
0x140015a40  mov     rdx, [rbp+var_10]; unsigned __int64
0x140015a44  mov     [rax], rdx
0x140015a47  cmp     [rbp+arg_18], dil
0x140015a4b  jz      short loc_140015AAA
0x140015a4d  mov     rcx, r14; this
0x140015a50  call    ?WaitForPagingQueueMonitoredFence@CDDPDEV@@QEAAJ_K@Z; CDDPDEV::WaitForPagingQueueMonitoredFence(unsigned __int64)
0x140015a55  movsxd  rsi, eax
0x140015a58  test    eax, eax
0x140015a5a  jns     short loc_140015AAA
0x140015a5c  mov     rdx, rsi
0x140015a5f  mov     ecx, 2
0x140015a64  call    cs:__imp_WdLogSingleEntry1
0x140015a6b  nop     dword ptr [rax+rax+00h]
0x140015a70  mov     ebx, 35Bh
0x140015a75  mov     cs:WdLogGlobalForLineNumber, ebx
0x140015a7b  call    cs:__imp_WdLogNewEntry5_WdError
0x140015a82  nop     dword ptr [rax+rax+00h]
0x140015a87  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015a8e  mov     [rax+18h], rcx
0x140015a92  mov     ecx, cs:dword_14003E570
0x140015a98  mov     [rax+20h], rcx
0x140015a9c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140015aa4  mov     cs:WdLogGlobalForLineNumber, ebx
0x140015aaa  mov     rbx, [rsp+40h+arg_8]
0x140015ab2  mov     eax, esi
0x140015ab4  add     rsp, 40h
0x140015ab8  pop     r15
0x140015aba  pop     r14
0x140015abc  pop     r13
0x140015abe  pop     r12
0x140015ac0  pop     rdi
0x140015ac1  pop     rsi
0x140015ac2  pop     rbp
0x140015ac3  retn
```
