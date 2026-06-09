# CHwCommandBuffer::AddStretchBltCommand(STRETCHBLT_DATA *,uint,tagRECT const *)

- ea: `0x14001fa08`
- end: `0x14001fca7`
- name: `?AddStretchBltCommand@CHwCommandBuffer@@QEAAHPEAUSTRETCHBLT_DATA@@IPEBUtagRECT@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this, struct STRETCHBLT_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001f860`

## callees

- `0x140004600`
- `0x1400101a0`
- `0x1400140c0`
- `0x14001d0a4`
- `0x14001fa08`
- `0x140027bcc`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001fba8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001fba8`
- `watchdog!WdLogSingleEntry0` at `0x14001fb8f`
- `watchdog!WdLogSingleEntry0` at `0x14001fb8f`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddStretchBltCommand(
        CHwCommandBuffer *this,
        struct STRETCHBLT_DATA *a2,
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
  unsigned int v14; // r13d
  unsigned int v15; // eax
  __int64 v16; // rsi
  __int128 v17; // xmm1
  int v18; // edx
  unsigned int v19; // r8d
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
  v15 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 25), 1u);
  if ( v14 == -1 || v15 == -1 )
  {
    CHwCommandBuffer::RecoverAllocationListState(this);
LABEL_19:
    v10 = *(CDDPDEV **)this;
LABEL_20:
    CDDPDEV::FlushNoMutex(v10, v4, 0, 2u);
    return 0;
  }
  v16 = *((_QWORD *)this + 4);
  *(_DWORD *)v16 = 4;
  *(_DWORD *)(v16 + 4) = v9;
  *(_DWORD *)(v16 + 40) = v15;
  *(_DWORD *)(v16 + 44) = v14;
  *(_DWORD *)(v16 + 68) = *((_DWORD *)a2 + 27);
  *(_OWORD *)(v16 + 24) = *(_OWORD *)*((_QWORD *)a2 + 2);
  v17 = *(_OWORD *)*((_QWORD *)a2 + 1);
  *(_DWORD *)(v16 + 64) = 0;
  *(_DWORD *)(v16 + 48) = a3;
  *(_OWORD *)(v16 + 8) = v17;
  *(_QWORD *)(v16 + 56) = v16 + 72;
  v18 = *((unsigned __int16 *)a2 + 52);
  *(_DWORD *)(v16 + 64) = v18;
  v19 = v18 & 0xFFFEFFFF | (*((_DWORD *)a2 + 28) != 0 ? 0x10000 : 0);
  *(_DWORD *)(v16 + 64) = v19;
  *(_DWORD *)(v16 + 64) = v19 & 0xFFFDFFFF | (*((_DWORD *)a2 + 29) != 0 ? 0x20000 : 0);
  memmove((void *)(v16 + 72), a4, v6);
  *((_QWORD *)this + 4) += v9;
  *(_BYTE *)(*(_QWORD *)this + 2753LL) = 1;
  if ( !*((_QWORD *)a2 + 11) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 622;
    v20 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v20[3] = gCddImageInfo;
    v20[4] = (unsigned int)dword_14003E570;
    v20[5] = 215857758;
    WdLogGlobalForLineNumber = 622;
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
  LODWORD(v27[0]) = 3;
  CDDETWPROFILER::CDDETWPROFILER((CDDETWPROFILER *)v26, v24, 0xBDFu, (struct _DXGKETW_PARAMS *)v27, 1);
  CDDETWPROFILER::~CDDETWPROFILER((CDDETWPROFILER *)v26);
  return 1;
}

```

## disassembly

```asm
0x14001fa08  mov     [rsp+Src], r9
0x14001fa0d  push    rbx
0x14001fa0e  push    rbp
0x14001fa0f  push    rsi
0x14001fa10  push    rdi
0x14001fa11  push    r12
0x14001fa13  push    r13
0x14001fa15  push    r14
0x14001fa17  push    r15
0x14001fa19  sub     rsp, 88h
0x14001fa20  mov     r10, [rcx+20h]
0x14001fa24  mov     r14d, r8d
0x14001fa27  mov     rsi, [rdx+20h]
0x14001fa2b  mov     ebp, r8d
0x14001fa2e  shl     r14d, 4
0x14001fa32  mov     rdi, rdx
0x14001fa35  mov     rbx, rcx
0x14001fa38  lea     r15d, [r14+48h]
0x14001fa3c  mov     r12d, r15d
0x14001fa3f  add     r10, r12
0x14001fa42  cmp     r10, [rcx+18h]
0x14001fa46  ja      loc_14001FC7C
0x14001fa4c  mov     rcx, [rcx]
0x14001fa4f  mov     edx, [rbx+848h]
0x14001fa55  cmp     edx, [rcx+31A8h]
0x14001fa5b  ja      loc_14001FC7C
0x14001fa61  mov     r8, [rdi]
0x14001fa64  test    r8, r8
0x14001fa67  jz      short loc_14001FA76
0x14001fa69  cmp     byte ptr [r8+14h], 0
0x14001fa6e  jz      short loc_14001FA76
0x14001fa70  add     r8, 4
0x14001fa74  jmp     short loc_14001FA7A
0x14001fa76  mov     r8, [rdi+18h]
0x14001fa7a  mov     r9d, [r8+0Ch]
0x14001fa7e  sub     r9d, [r8+4]
0x14001fa82  mov     eax, [r8]
0x14001fa85  mov     r8d, [r8+8]
0x14001fa89  sub     r8d, eax
0x14001fa8c  imul    r9d, r8d
0x14001fa90  xor     r8d, r8d; unsigned __int8
0x14001fa93  add     r9d, edx
0x14001fa96  mov     [rbx+848h], r9d
0x14001fa9d  cmp     [rbx+860h], r8b
0x14001faa4  jnz     loc_14001FC82
0x14001faaa  mov     eax, [rbx+830h]
0x14001fab0  mov     rcx, rbx; this
0x14001fab3  mov     [rbx+834h], eax
0x14001fab9  mov     edx, [rdi+60h]; unsigned int
0x14001fabc  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001fac1  mov     edx, [rdi+64h]; unsigned int
0x14001fac4  mov     r8b, 1; unsigned __int8
0x14001fac7  mov     rcx, rbx; this
0x14001faca  mov     r13d, eax
0x14001facd  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001fad2  or      ecx, 0FFFFFFFFh
0x14001fad5  cmp     r13d, ecx
0x14001fad8  jz      loc_14001FC74
0x14001fade  cmp     eax, ecx
0x14001fae0  jz      loc_14001FC74
0x14001fae6  mov     rsi, [rbx+20h]
0x14001faea  mov     dword ptr [rsi], 4
0x14001faf0  lea     rcx, [rsi+48h]; void *
0x14001faf4  mov     [rsi+4], r15d
0x14001faf8  mov     [rsi+28h], eax
0x14001fafb  mov     [rsi+2Ch], r13d
0x14001faff  xor     r13d, r13d
0x14001fb02  mov     eax, [rdi+6Ch]
0x14001fb05  mov     [rsi+44h], eax
0x14001fb08  mov     rax, [rdi+10h]
0x14001fb0c  movups  xmm0, xmmword ptr [rax]
0x14001fb0f  movdqu  xmmword ptr [rsi+18h], xmm0
0x14001fb14  mov     rax, [rdi+8]
0x14001fb18  movups  xmm1, xmmword ptr [rax]
0x14001fb1b  mov     [rsi+40h], r13d
0x14001fb1f  mov     [rsi+30h], ebp
0x14001fb22  movdqu  xmmword ptr [rsi+8], xmm1
0x14001fb27  mov     [rsi+38h], rcx
0x14001fb2b  movzx   edx, word ptr [rdi+68h]
0x14001fb2f  mov     [rsi+40h], edx
0x14001fb32  mov     eax, [rdi+70h]
0x14001fb35  neg     eax
0x14001fb37  sbb     r8d, r8d
0x14001fb3a  btr     edx, 10h
0x14001fb3e  and     r8d, 10000h
0x14001fb45  or      r8d, edx
0x14001fb48  mov     [rsi+40h], r8d
0x14001fb4c  mov     eax, [rdi+74h]
0x14001fb4f  neg     eax
0x14001fb51  sbb     edx, edx
0x14001fb53  btr     r8d, 11h
0x14001fb58  and     edx, 20000h
0x14001fb5e  or      edx, r8d
0x14001fb61  mov     r8d, r14d; Size
0x14001fb64  mov     r14, [rsp+0C8h+Src]
0x14001fb6c  mov     [rsi+40h], edx
0x14001fb6f  mov     rdx, r14; Src
0x14001fb72  call    memmove
0x14001fb77  add     [rbx+20h], r12
0x14001fb7b  mov     rax, [rbx]
0x14001fb7e  mov     byte ptr [rax+0AC1h], 1
0x14001fb85  cmp     [rdi+58h], r13
0x14001fb89  jnz     short loc_14001FBD8
0x14001fb8b  lea     ecx, [r13+1]
0x14001fb8f  call    cs:__imp_WdLogSingleEntry0
0x14001fb96  nop     dword ptr [rax+rax+00h]
0x14001fb9b  mov     r12d, 26Eh
0x14001fba1  mov     cs:WdLogGlobalForLineNumber, r12d
0x14001fba8  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001fbaf  nop     dword ptr [rax+rax+00h]
0x14001fbb4  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001fbbb  mov     [rax+18h], rcx
0x14001fbbf  mov     ecx, cs:dword_14003E570
0x14001fbc5  mov     [rax+20h], rcx
0x14001fbc9  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001fbd1  mov     cs:WdLogGlobalForLineNumber, r12d
0x14001fbd8  mov     rcx, [rdi+58h]
0x14001fbdc  mov     rdx, rbx
0x14001fbdf  mov     qword ptr [rsp+0C8h+var_A8], r13
0x14001fbe4  mov     rax, [rcx]
0x14001fbe7  mov     rax, [rax]
0x14001fbea  cmp     ebp, 8
0x14001fbed  ja      short loc_14001FBF7
0x14001fbef  mov     r9d, ebp
0x14001fbf2  mov     r8, r14
0x14001fbf5  jmp     short loc_14001FC01
0x14001fbf7  mov     r9d, 1
0x14001fbfd  lea     r8, [rsi+18h]
0x14001fc01  call    _guard_dispatch_icall
0x14001fc06  mov     rcx, [rdi+50h]
0x14001fc0a  test    rcx, rcx
0x14001fc0d  jz      short loc_14001FC28
0x14001fc0f  mov     rax, [rcx]
0x14001fc12  xor     r9d, r9d
0x14001fc15  xor     r8d, r8d
0x14001fc18  mov     qword ptr [rsp+0C8h+var_A8], r13
0x14001fc1d  mov     rdx, rbx
0x14001fc20  mov     rax, [rax]
0x14001fc23  call    _guard_dispatch_icall
0x14001fc28  mov     rdx, [rbx]; struct CDDPDEV *
0x14001fc2b  lea     r9, [rsp+0C8h+var_78]; struct _DXGKETW_PARAMS *
0x14001fc30  xorps   xmm0, xmm0
0x14001fc33  mov     [rbx+28h], rsi
0x14001fc37  movups  [rsp+0C8h+var_78], xmm0
0x14001fc3c  mov     r8d, 0BDFh; unsigned int
0x14001fc42  mov     dword ptr [rsp+0C8h+var_78], 3
0x14001fc4a  lea     rcx, [rsp+0C8h+var_98]; this
0x14001fc4f  mov     [rsp+0C8h+var_A8], 1; bool
0x14001fc54  movups  [rsp+0C8h+var_68], xmm0
0x14001fc59  movups  [rsp+0C8h+var_58], xmm0
0x14001fc5e  call    ??0CDDETWPROFILER@@QEAA@PEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::CDDETWPROFILER(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x14001fc63  lea     rcx, [rsp+0C8h+var_98]; this
0x14001fc68  call    ??1CDDETWPROFILER@@QEAA@XZ; CDDETWPROFILER::~CDDETWPROFILER(void)
0x14001fc6d  mov     eax, 1
0x14001fc72  jmp     short loc_14001FC92
0x14001fc74  mov     rcx, rbx; this
0x14001fc77  call    ?RecoverAllocationListState@CHwCommandBuffer@@IEAAXXZ; CHwCommandBuffer::RecoverAllocationListState(void)
0x14001fc7c  mov     rcx, [rbx]; this
0x14001fc7f  xor     r8d, r8d; int
0x14001fc82  mov     r9d, 2; unsigned int
0x14001fc88  mov     rdx, rsi; struct CCommandBufferMutex *
0x14001fc8b  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x14001fc90  xor     eax, eax
0x14001fc92  add     rsp, 88h
0x14001fc99  pop     r15
0x14001fc9b  pop     r14
0x14001fc9d  pop     r13
0x14001fc9f  pop     r12
0x14001fca1  pop     rdi
0x14001fca2  pop     rsi
0x14001fca3  pop     rbp
0x14001fca4  pop     rbx
0x14001fca5  retn
```
