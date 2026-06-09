# CHwCommandBuffer::AddTransparentBltCommand(TRANSPARENTBLT_DATA *,uint,tagRECT const *)

- ea: `0x14002ea64`
- end: `0x14002ecd9`
- name: `?AddTransparentBltCommand@CHwCommandBuffer@@QEAAHPEAUTRANSPARENTBLT_DATA@@IPEBUtagRECT@@@Z`
- size: `629`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this, struct TRANSPARENTBLT_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140031110`

## callees

- `0x140004600`
- `0x1400101a0`
- `0x1400140c0`
- `0x14001d0a4`
- `0x140027bcc`
- `0x14002ea64`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ebda`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14002ebda`
- `watchdog!WdLogSingleEntry0` at `0x14002ebc1`
- `watchdog!WdLogSingleEntry0` at `0x14002ebc1`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddTransparentBltCommand(
        CHwCommandBuffer *this,
        struct TRANSPARENTBLT_DATA *a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  struct CCommandBufferMutex *v4; // rsi
  unsigned int v6; // r14d
  unsigned int v9; // r15d
  CDDPDEV *v10; // rcx
  unsigned int v11; // edx
  __int64 v12; // r8
  _DWORD *v13; // r8
  int v14; // r13d
  int v15; // eax
  __int64 v16; // rsi
  __int128 v17; // xmm1
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // r9
  const struct tagRECT *v22; // r8
  void (__fastcall ***v23)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD); // rcx
  struct CDDPDEV *v24; // rdx
  _BYTE v26[32]; // [rsp+30h] [rbp-98h] BYREF
  _OWORD v27[7]; // [rsp+50h] [rbp-78h] BYREF

  v4 = (struct CCommandBufferMutex *)*((_QWORD *)a2 + 4);
  v6 = 16 * a3;
  v9 = 16 * a3 + 72;
  if ( (unsigned __int64)v9 + *((_QWORD *)this + 4) > *((_QWORD *)this + 3) )
    goto LABEL_19;
  v10 = *(CDDPDEV **)this;
  v11 = *((_DWORD *)this + 530);
  if ( v11 > *((_DWORD *)v10 + 3178) )
    goto LABEL_19;
  v12 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 && *(_BYTE *)(v12 + 20) )
    v13 = (_DWORD *)(v12 + 4);
  else
    v13 = (_DWORD *)*((_QWORD *)a2 + 3);
  *((_DWORD *)this + 530) = v11 + (v13[2] - *v13) * (v13[3] - v13[1]);
  if ( *((_BYTE *)this + 2144) )
    goto LABEL_20;
  *((_DWORD *)this + 525) = *((_DWORD *)this + 524);
  v14 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 24), 0);
  v15 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 25), 1);
  if ( v14 == -1 || v15 == -1 )
  {
    CHwCommandBuffer::RecoverAllocationListState(this);
LABEL_19:
    v10 = *(CDDPDEV **)this;
LABEL_20:
    CDDPDEV::FlushNoMutex(v10, v4, 0, 2);
    return 0;
  }
  v16 = *((_QWORD *)this + 4);
  *(_DWORD *)v16 = 6;
  *(_DWORD *)(v16 + 4) = v9;
  *(_DWORD *)(v16 + 40) = v14;
  *(_DWORD *)(v16 + 44) = v15;
  *(_DWORD *)(v16 + 68) = *((_DWORD *)a2 + 28);
  *(_OWORD *)(v16 + 24) = *(_OWORD *)*((_QWORD *)a2 + 3);
  v17 = *(_OWORD *)*((_QWORD *)a2 + 1);
  *(_DWORD *)(v16 + 52) = a3;
  *(_QWORD *)(v16 + 56) = v16 + 72;
  *(_OWORD *)(v16 + 8) = v17;
  *(_DWORD *)(v16 + 48) = *((_DWORD *)a2 + 26);
  *(_DWORD *)(v16 + 64) = 0;
  *(_DWORD *)(v16 + 64) = *((_DWORD *)a2 + 27) & 1;
  memmove((void *)(v16 + 72), a4, v6);
  *((_QWORD *)this + 4) += v9;
  *(_BYTE *)(*(_QWORD *)this + 2753LL) = 1;
  if ( !*((_QWORD *)a2 + 11) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 838;
    v20 = (_QWORD *)WdLogNewEntry5_WdAssertion(v19, v18);
    v20[3] = gCddImageInfo;
    v20[4] = (unsigned int)dword_14003E570;
    v20[5] = 215857758;
    WdLogGlobalForLineNumber = 838;
  }
  if ( a3 > 8 )
  {
    v21 = 1;
    v22 = (const struct tagRECT *)(v16 + 24);
  }
  else
  {
    v21 = a3;
    v22 = a4;
  }
  (***((void (__fastcall ****)(_QWORD, CHwCommandBuffer *, const struct tagRECT *, __int64, _QWORD))a2 + 11))(
    *((_QWORD *)a2 + 11),
    this,
    v22,
    v21,
    0);
  v23 = (void (__fastcall ***)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD))*((_QWORD *)a2 + 10);
  if ( v23 )
    (**v23)(v23, this, 0, 0, 0);
  v24 = *(struct CDDPDEV **)this;
  *((_QWORD *)this + 5) = v16;
  memset(v27, 0, 48);
  LODWORD(v27[0]) = 5;
  CDDETWPROFILER::CDDETWPROFILER((CDDETWPROFILER *)v26, v24, 0xBDFu, (struct _DXGKETW_PARAMS *)v27, 1);
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v26);
  return 1;
}

```

## disassembly

```asm
0x14002ea64  mov     [rsp+Src], r9
0x14002ea69  push    rbx
0x14002ea6a  push    rbp
0x14002ea6b  push    rsi
0x14002ea6c  push    rdi
0x14002ea6d  push    r12
0x14002ea6f  push    r13
0x14002ea71  push    r14
0x14002ea73  push    r15
0x14002ea75  sub     rsp, 88h
0x14002ea7c  mov     r10, [rcx+20h]
0x14002ea80  mov     r14d, r8d
0x14002ea83  mov     rsi, [rdx+20h]
0x14002ea87  mov     ebp, r8d
0x14002ea8a  shl     r14d, 4
0x14002ea8e  mov     rdi, rdx
0x14002ea91  mov     rbx, rcx
0x14002ea94  lea     r15d, [r14+48h]
0x14002ea98  mov     r12d, r15d
0x14002ea9b  add     r10, r12
0x14002ea9e  cmp     r10, [rcx+18h]
0x14002eaa2  ja      loc_14002ECAE
0x14002eaa8  mov     rcx, [rcx]
0x14002eaab  mov     edx, [rbx+848h]
0x14002eab1  cmp     edx, [rcx+31A8h]
0x14002eab7  ja      loc_14002ECAE
0x14002eabd  mov     r8, [rdi]
0x14002eac0  test    r8, r8
0x14002eac3  jz      short loc_14002EAD2
0x14002eac5  cmp     byte ptr [r8+14h], 0
0x14002eaca  jz      short loc_14002EAD2
0x14002eacc  add     r8, 4
0x14002ead0  jmp     short loc_14002EAD6
0x14002ead2  mov     r8, [rdi+18h]
0x14002ead6  mov     r9d, [r8+0Ch]
0x14002eada  sub     r9d, [r8+4]
0x14002eade  mov     eax, [r8]
0x14002eae1  mov     r8d, [r8+8]
0x14002eae5  sub     r8d, eax
0x14002eae8  imul    r9d, r8d
0x14002eaec  xor     r8d, r8d; unsigned __int8
0x14002eaef  add     r9d, edx
0x14002eaf2  mov     [rbx+848h], r9d
0x14002eaf9  cmp     [rbx+860h], r8b
0x14002eb00  jnz     loc_14002ECB4
0x14002eb06  mov     eax, [rbx+830h]
0x14002eb0c  mov     rcx, rbx; this
0x14002eb0f  mov     [rbx+834h], eax
0x14002eb15  mov     edx, [rdi+60h]; unsigned int
0x14002eb18  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14002eb1d  mov     edx, [rdi+64h]; unsigned int
0x14002eb20  mov     r8b, 1; unsigned __int8
0x14002eb23  mov     rcx, rbx; this
0x14002eb26  mov     r13d, eax
0x14002eb29  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14002eb2e  or      ecx, 0FFFFFFFFh
0x14002eb31  cmp     r13d, ecx
0x14002eb34  jz      loc_14002ECA6
0x14002eb3a  cmp     eax, ecx
0x14002eb3c  jz      loc_14002ECA6
0x14002eb42  mov     rsi, [rbx+20h]
0x14002eb46  mov     r8d, r14d; Size
0x14002eb49  mov     r14, [rsp+0C8h+Src]
0x14002eb51  mov     rdx, r14; Src
0x14002eb54  mov     dword ptr [rsi], 6
0x14002eb5a  lea     rcx, [rsi+48h]; void *
0x14002eb5e  mov     [rsi+4], r15d
0x14002eb62  mov     [rsi+28h], r13d
0x14002eb66  xor     r13d, r13d
0x14002eb69  mov     [rsi+2Ch], eax
0x14002eb6c  mov     eax, [rdi+70h]
0x14002eb6f  mov     [rsi+44h], eax
0x14002eb72  mov     rax, [rdi+18h]
0x14002eb76  movups  xmm0, xmmword ptr [rax]
0x14002eb79  movdqu  xmmword ptr [rsi+18h], xmm0
0x14002eb7e  mov     rax, [rdi+8]
0x14002eb82  movups  xmm1, xmmword ptr [rax]
0x14002eb85  mov     [rsi+34h], ebp
0x14002eb88  mov     [rsi+38h], rcx
0x14002eb8c  movdqu  xmmword ptr [rsi+8], xmm1
0x14002eb91  mov     eax, [rdi+68h]
0x14002eb94  mov     [rsi+30h], eax
0x14002eb97  mov     [rsi+40h], r13d
0x14002eb9b  mov     eax, [rdi+6Ch]
0x14002eb9e  and     eax, 1
0x14002eba1  mov     [rsi+40h], eax
0x14002eba4  call    memmove
0x14002eba9  add     [rbx+20h], r12
0x14002ebad  mov     rax, [rbx]
0x14002ebb0  mov     byte ptr [rax+0AC1h], 1
0x14002ebb7  cmp     [rdi+58h], r13
0x14002ebbb  jnz     short loc_14002EC0A
0x14002ebbd  lea     ecx, [r13+1]
0x14002ebc1  call    cs:__imp_WdLogSingleEntry0
0x14002ebc8  nop     dword ptr [rax+rax+00h]
0x14002ebcd  mov     r12d, 346h
0x14002ebd3  mov     cs:WdLogGlobalForLineNumber, r12d
0x14002ebda  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002ebe1  nop     dword ptr [rax+rax+00h]
0x14002ebe6  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002ebed  mov     [rax+18h], rcx
0x14002ebf1  mov     ecx, cs:dword_14003E570
0x14002ebf7  mov     [rax+20h], rcx
0x14002ebfb  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002ec03  mov     cs:WdLogGlobalForLineNumber, r12d
0x14002ec0a  mov     rcx, [rdi+58h]
0x14002ec0e  mov     rdx, rbx
0x14002ec11  mov     qword ptr [rsp+0C8h+var_A8], r13
0x14002ec16  mov     rax, [rcx]
0x14002ec19  mov     rax, [rax]
0x14002ec1c  cmp     ebp, 8
0x14002ec1f  ja      short loc_14002EC29
0x14002ec21  mov     r9d, ebp
0x14002ec24  mov     r8, r14
0x14002ec27  jmp     short loc_14002EC33
0x14002ec29  mov     r9d, 1
0x14002ec2f  lea     r8, [rsi+18h]
0x14002ec33  call    _guard_dispatch_icall
0x14002ec38  mov     rcx, [rdi+50h]
0x14002ec3c  test    rcx, rcx
0x14002ec3f  jz      short loc_14002EC5A
0x14002ec41  mov     rax, [rcx]
0x14002ec44  xor     r9d, r9d
0x14002ec47  xor     r8d, r8d
0x14002ec4a  mov     qword ptr [rsp+0C8h+var_A8], r13
0x14002ec4f  mov     rdx, rbx
0x14002ec52  mov     rax, [rax]
0x14002ec55  call    _guard_dispatch_icall
0x14002ec5a  mov     rdx, [rbx]; struct CDDPDEV *
0x14002ec5d  lea     r9, [rsp+0C8h+var_78]; struct _DXGKETW_PARAMS *
0x14002ec62  xorps   xmm0, xmm0
0x14002ec65  mov     [rbx+28h], rsi
0x14002ec69  movups  [rsp+0C8h+var_78], xmm0
0x14002ec6e  mov     r8d, 0BDFh; unsigned int
0x14002ec74  mov     dword ptr [rsp+0C8h+var_78], 5
0x14002ec7c  lea     rcx, [rsp+0C8h+var_98]; this
0x14002ec81  mov     [rsp+0C8h+var_A8], 1; bool
0x14002ec86  movups  [rsp+0C8h+var_68], xmm0
0x14002ec8b  movups  [rsp+0C8h+var_58], xmm0
0x14002ec90  call    ??0CDDETWPROFILER@@QEAA@PEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::CDDETWPROFILER(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14002ec95  lea     rcx, [rsp+0C8h+var_98]; this
0x14002ec9a  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x14002ec9f  mov     eax, 1
0x14002eca4  jmp     short loc_14002ECC4
0x14002eca6  mov     rcx, rbx; this
0x14002eca9  call    ?RecoverAllocationListState@CHwCommandBuffer@@IEAAXXZ; CHwCommandBuffer::RecoverAllocationListState(void)
0x14002ecae  mov     rcx, [rbx]; this
0x14002ecb1  xor     r8d, r8d; int
0x14002ecb4  mov     r9d, 2; unsigned int
0x14002ecba  mov     rdx, rsi; struct CCommandBufferMutex *
0x14002ecbd  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x14002ecc2  xor     eax, eax
0x14002ecc4  add     rsp, 88h
0x14002eccb  pop     r15
0x14002eccd  pop     r14
0x14002eccf  pop     r13
0x14002ecd1  pop     r12
0x14002ecd3  pop     rdi
0x14002ecd4  pop     rsi
0x14002ecd5  pop     rbp
0x14002ecd6  pop     rbx
0x14002ecd7  retn
```
