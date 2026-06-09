# CHwCommandBuffer::AddAlphaBlendCommand(ALPHABLEND_DATA *,uint,tagRECT const *)

- ea: `0x140020e48`
- end: `0x1400210b6`
- name: `?AddAlphaBlendCommand@CHwCommandBuffer@@QEAAHPEAUALPHABLEND_DATA@@IPEBUtagRECT@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this, struct ALPHABLEND_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140020ca0`

## callees

- `0x140004600`
- `0x1400101a0`
- `0x1400140c0`
- `0x14001d0a4`
- `0x140020e48`
- `0x140027bcc`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140020fb7`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140020fb7`
- `watchdog!WdLogSingleEntry0` at `0x140020f9e`
- `watchdog!WdLogSingleEntry0` at `0x140020f9e`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddAlphaBlendCommand(
        CHwCommandBuffer *this,
        struct ALPHABLEND_DATA *a2,
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
  *(_DWORD *)v16 = 3;
  *(_DWORD *)(v16 + 4) = v9;
  *(_DWORD *)(v16 + 40) = v14;
  *(_DWORD *)(v16 + 44) = v15;
  *(_DWORD *)(v16 + 68) = *((_DWORD *)a2 + 27);
  *(_OWORD *)(v16 + 24) = *(_OWORD *)*((_QWORD *)a2 + 2);
  v17 = *(_OWORD *)*((_QWORD *)a2 + 1);
  *(_DWORD *)(v16 + 48) = a3;
  *(_QWORD *)(v16 + 56) = v16 + 72;
  *(_OWORD *)(v16 + 8) = v17;
  *(_BYTE *)(v16 + 64) = *((_BYTE *)a2 + 105);
  *(_BYTE *)(v16 + 65) = *((_BYTE *)a2 + 104);
  memmove((void *)(v16 + 72), a4, v6);
  *((_QWORD *)this + 4) += v9;
  *(_BYTE *)(*(_QWORD *)this + 2753LL) = 1;
  if ( !*((_QWORD *)a2 + 11) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 729;
    v20 = (_QWORD *)WdLogNewEntry5_WdAssertion(v19, v18);
    v20[3] = gCddImageInfo;
    v20[4] = (unsigned int)dword_14003E570;
    v20[5] = 215857758;
    WdLogGlobalForLineNumber = 729;
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
  LODWORD(v27[0]) = 4;
  CDDETWPROFILER::CDDETWPROFILER((CDDETWPROFILER *)v26, v24, 0xBDFu, (struct _DXGKETW_PARAMS *)v27, 1);
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v26);
  return 1;
}

```

## disassembly

```asm
0x140020e48  mov     [rsp+Src], r9
0x140020e4d  push    rbx
0x140020e4e  push    rbp
0x140020e4f  push    rsi
0x140020e50  push    rdi
0x140020e51  push    r12
0x140020e53  push    r13
0x140020e55  push    r14
0x140020e57  push    r15
0x140020e59  sub     rsp, 88h
0x140020e60  mov     r10, [rcx+20h]
0x140020e64  mov     r14d, r8d
0x140020e67  mov     rsi, [rdx+20h]
0x140020e6b  mov     ebp, r8d
0x140020e6e  shl     r14d, 4
0x140020e72  mov     rdi, rdx
0x140020e75  mov     rbx, rcx
0x140020e78  lea     r15d, [r14+48h]
0x140020e7c  mov     r12d, r15d
0x140020e7f  add     r10, r12
0x140020e82  cmp     r10, [rcx+18h]
0x140020e86  ja      loc_14002108B
0x140020e8c  mov     rcx, [rcx]
0x140020e8f  mov     edx, [rbx+848h]
0x140020e95  cmp     edx, [rcx+31A8h]
0x140020e9b  ja      loc_14002108B
0x140020ea1  mov     r8, [rdi]
0x140020ea4  test    r8, r8
0x140020ea7  jz      short loc_140020EB6
0x140020ea9  cmp     byte ptr [r8+14h], 0
0x140020eae  jz      short loc_140020EB6
0x140020eb0  add     r8, 4
0x140020eb4  jmp     short loc_140020EBA
0x140020eb6  mov     r8, [rdi+18h]
0x140020eba  mov     r9d, [r8+0Ch]
0x140020ebe  sub     r9d, [r8+4]
0x140020ec2  mov     eax, [r8]
0x140020ec5  mov     r8d, [r8+8]
0x140020ec9  sub     r8d, eax
0x140020ecc  imul    r9d, r8d
0x140020ed0  xor     r8d, r8d; unsigned __int8
0x140020ed3  add     r9d, edx
0x140020ed6  mov     [rbx+848h], r9d
0x140020edd  cmp     [rbx+860h], r8b
0x140020ee4  jnz     loc_140021091
0x140020eea  mov     eax, [rbx+830h]
0x140020ef0  mov     rcx, rbx; this
0x140020ef3  mov     [rbx+834h], eax
0x140020ef9  mov     edx, [rdi+60h]; unsigned int
0x140020efc  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x140020f01  mov     edx, [rdi+64h]; unsigned int
0x140020f04  mov     r8b, 1; unsigned __int8
0x140020f07  mov     rcx, rbx; this
0x140020f0a  mov     r13d, eax
0x140020f0d  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x140020f12  or      ecx, 0FFFFFFFFh
0x140020f15  cmp     r13d, ecx
0x140020f18  jz      loc_140021083
0x140020f1e  cmp     eax, ecx
0x140020f20  jz      loc_140021083
0x140020f26  mov     rsi, [rbx+20h]
0x140020f2a  mov     r8d, r14d; Size
0x140020f2d  mov     r14, [rsp+0C8h+Src]
0x140020f35  mov     rdx, r14; Src
0x140020f38  mov     dword ptr [rsi], 3
0x140020f3e  lea     rcx, [rsi+48h]; void *
0x140020f42  mov     [rsi+4], r15d
0x140020f46  mov     [rsi+28h], r13d
0x140020f4a  mov     [rsi+2Ch], eax
0x140020f4d  mov     eax, [rdi+6Ch]
0x140020f50  mov     [rsi+44h], eax
0x140020f53  mov     rax, [rdi+10h]
0x140020f57  movups  xmm0, xmmword ptr [rax]
0x140020f5a  movdqu  xmmword ptr [rsi+18h], xmm0
0x140020f5f  mov     rax, [rdi+8]
0x140020f63  movups  xmm1, xmmword ptr [rax]
0x140020f66  mov     [rsi+30h], ebp
0x140020f69  mov     [rsi+38h], rcx
0x140020f6d  movdqu  xmmword ptr [rsi+8], xmm1
0x140020f72  mov     al, [rdi+69h]
0x140020f75  mov     [rsi+40h], al
0x140020f78  mov     al, [rdi+68h]
0x140020f7b  mov     [rsi+41h], al
0x140020f7e  call    memmove
0x140020f83  add     [rbx+20h], r12
0x140020f87  xor     r13d, r13d
0x140020f8a  mov     rax, [rbx]
0x140020f8d  mov     byte ptr [rax+0AC1h], 1
0x140020f94  cmp     [rdi+58h], r13
0x140020f98  jnz     short loc_140020FE7
0x140020f9a  lea     ecx, [r13+1]
0x140020f9e  call    cs:__imp_WdLogSingleEntry0
0x140020fa5  nop     dword ptr [rax+rax+00h]
0x140020faa  mov     r12d, 2D9h
0x140020fb0  mov     cs:WdLogGlobalForLineNumber, r12d
0x140020fb7  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140020fbe  nop     dword ptr [rax+rax+00h]
0x140020fc3  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140020fca  mov     [rax+18h], rcx
0x140020fce  mov     ecx, cs:dword_14003E570
0x140020fd4  mov     [rax+20h], rcx
0x140020fd8  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140020fe0  mov     cs:WdLogGlobalForLineNumber, r12d
0x140020fe7  mov     rcx, [rdi+58h]
0x140020feb  mov     rdx, rbx
0x140020fee  mov     qword ptr [rsp+0C8h+var_A8], r13
0x140020ff3  mov     rax, [rcx]
0x140020ff6  mov     rax, [rax]
0x140020ff9  cmp     ebp, 8
0x140020ffc  ja      short loc_140021006
0x140020ffe  mov     r9d, ebp
0x140021001  mov     r8, r14
0x140021004  jmp     short loc_140021010
0x140021006  mov     r9d, 1
0x14002100c  lea     r8, [rsi+18h]
0x140021010  call    _guard_dispatch_icall
0x140021015  mov     rcx, [rdi+50h]
0x140021019  test    rcx, rcx
0x14002101c  jz      short loc_140021037
0x14002101e  mov     rax, [rcx]
0x140021021  xor     r9d, r9d
0x140021024  xor     r8d, r8d
0x140021027  mov     qword ptr [rsp+0C8h+var_A8], r13
0x14002102c  mov     rdx, rbx
0x14002102f  mov     rax, [rax]
0x140021032  call    _guard_dispatch_icall
0x140021037  mov     rdx, [rbx]; struct CDDPDEV *
0x14002103a  lea     r9, [rsp+0C8h+var_78]; struct _DXGKETW_PARAMS *
0x14002103f  xorps   xmm0, xmm0
0x140021042  mov     [rbx+28h], rsi
0x140021046  movups  [rsp+0C8h+var_78], xmm0
0x14002104b  mov     r8d, 0BDFh; unsigned int
0x140021051  mov     dword ptr [rsp+0C8h+var_78], 4
0x140021059  lea     rcx, [rsp+0C8h+var_98]; this
0x14002105e  mov     [rsp+0C8h+var_A8], 1; bool
0x140021063  movups  [rsp+0C8h+var_68], xmm0
0x140021068  movups  [rsp+0C8h+var_58], xmm0
0x14002106d  call    ??0CDDETWPROFILER@@QEAA@PEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::CDDETWPROFILER(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140021072  lea     rcx, [rsp+0C8h+var_98]; this
0x140021077  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x14002107c  mov     eax, 1
0x140021081  jmp     short loc_1400210A1
0x140021083  mov     rcx, rbx; this
0x140021086  call    ?RecoverAllocationListState@CHwCommandBuffer@@IEAAXXZ; CHwCommandBuffer::RecoverAllocationListState(void)
0x14002108b  mov     rcx, [rbx]; this
0x14002108e  xor     r8d, r8d; int
0x140021091  mov     r9d, 2; unsigned int
0x140021097  mov     rdx, rsi; struct CCommandBufferMutex *
0x14002109a  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x14002109f  xor     eax, eax
0x1400210a1  add     rsp, 88h
0x1400210a8  pop     r15
0x1400210aa  pop     r14
0x1400210ac  pop     r13
0x1400210ae  pop     r12
0x1400210b0  pop     rdi
0x1400210b1  pop     rsi
0x1400210b2  pop     rbp
0x1400210b3  pop     rbx
0x1400210b4  retn
```
