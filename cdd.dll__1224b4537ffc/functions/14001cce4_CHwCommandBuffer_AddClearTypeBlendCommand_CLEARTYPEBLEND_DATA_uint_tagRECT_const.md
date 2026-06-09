# CHwCommandBuffer::AddClearTypeBlendCommand(CLEARTYPEBLEND_DATA *,uint,tagRECT const *)

- ea: `0x14001cce4`
- end: `0x14001d09c`
- name: `?AddClearTypeBlendCommand@CHwCommandBuffer@@QEAAHPEAUCLEARTYPEBLEND_DATA@@IPEBUtagRECT@@@Z`
- size: `952`
- prototype: `__int64 __fastcall(CHwCommandBuffer *__hidden this, struct CLEARTYPEBLEND_DATA *, unsigned int, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002f640`

## callees

- `0x1400101a0`
- `0x14001cce4`
- `0x14001d0a4`
- `0x140027bcc`
- `0x1400372d0`
- `0x140037340`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14001cddd`
- `ntoskrnl!DbgPrint` at `0x14001cddd`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001cdca`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001ce05`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001ce05`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001cf76`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001cf76`
- `watchdog!WdLogSingleEntry0` at `0x14001cdee`
- `watchdog!WdLogSingleEntry0` at `0x14001cf5d`
- `watchdog!WdLogSingleEntry0` at `0x14001cdee`
- `watchdog!WdLogSingleEntry0` at `0x14001cf5d`

## string_xrefs

- `0x14001cdd6`: `hTmpSurface is NULL in CHwCommandBuffer::AddClearTypeBlendCommand`

## pseudocode

```c
__int64 __fastcall CHwCommandBuffer::AddClearTypeBlendCommand(
        CHwCommandBuffer *this,
        struct CLEARTYPEBLEND_DATA *a2,
        unsigned int a3,
        const struct tagRECT *a4)
{
  struct CCommandBufferMutex *v4; // rsi
  unsigned int v7; // r15d
  CDDPDEV *v9; // rcx
  unsigned int v10; // edx
  __int64 v11; // r8
  _DWORD *v12; // r8
  unsigned int v13; // r12d
  _QWORD *v14; // rax
  unsigned int v15; // edx
  unsigned int v16; // ebp
  unsigned int v17; // r13d
  unsigned int v18; // eax
  __int64 v19; // r12
  _QWORD *v20; // rax
  __int64 v21; // r9
  const struct tagRECT *v22; // r8
  void (__fastcall ***v23)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD); // rcx
  void (__fastcall ***v24)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD); // rcx
  __int64 v25; // rbx
  _OWORD v27[6]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+8h]
  unsigned int v29; // [rsp+B0h] [rbp+18h]

  v4 = (struct CCommandBufferMutex *)*((_QWORD *)a2 + 4);
  v7 = 16 * a3;
  v28 = 16 * a3 + 80;
  if ( (unsigned __int64)(v28 + *((_QWORD *)this + 4)) > *((_QWORD *)this + 3) )
    goto LABEL_34;
  v9 = *(CDDPDEV **)this;
  v10 = *((_DWORD *)this + 530);
  if ( v10 > *(_DWORD *)(*(_QWORD *)this + 12712LL) )
    goto LABEL_34;
  v11 = *(_QWORD *)a2;
  if ( *(_QWORD *)a2 && *(_BYTE *)(v11 + 20) )
    v12 = (_DWORD *)(v11 + 4);
  else
    v12 = (_DWORD *)*((_QWORD *)a2 + 3);
  *((_DWORD *)this + 530) = v10 + (v12[2] - *v12) * (v12[3] - v12[1]);
  if ( *((_BYTE *)this + 2144) )
    goto LABEL_35;
  *((_DWORD *)this + 525) = *((_DWORD *)this + 524);
  v13 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 33), 0);
  v29 = v13;
  if ( !*((_DWORD *)a2 + 32) && (*(_DWORD *)(*(_QWORD *)this + 1900LL) & 0x8000000) == 0 && (_BYTE)KdDebuggerEnabled )
  {
    DbgPrint("hTmpSurface is NULL in CHwCommandBuffer::AddClearTypeBlendCommand");
    WdLogSingleEntry0(2);
    WdLogGlobalForLineNumber = 923;
    v14 = (_QWORD *)WdLogNewEntry5_WdError();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 923;
    __debugbreak();
  }
  v15 = *((_DWORD *)a2 + 32);
  if ( v15 )
    v16 = CHwCommandBuffer::InsertToAllocationList(this, v15, 0);
  else
    v16 = 0;
  v17 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 34), 1u);
  v18 = 0;
  if ( *((_DWORD *)a2 + 28) != -1 )
    v18 = CHwCommandBuffer::InsertToAllocationList(this, *((_DWORD *)a2 + 31), 1u);
  if ( v13 == -1 || v17 == -1 || v16 == -1 || v18 == -1 )
  {
    CHwCommandBuffer::RecoverAllocationListState(this);
LABEL_34:
    v9 = *(CDDPDEV **)this;
LABEL_35:
    CDDPDEV::FlushNoMutex(v9, v4, 0, 2);
    return 0;
  }
  v19 = *((_QWORD *)this + 4);
  *(_DWORD *)(v19 + 4) = v7 + 80;
  *(_DWORD *)v19 = 7;
  *(_DWORD *)(v19 + 28) = v18;
  *(_DWORD *)(v19 + 24) = v16;
  *(_DWORD *)(v19 + 32) = v29;
  *(_DWORD *)(v19 + 36) = v17;
  *(_OWORD *)(v19 + 8) = *(_OWORD *)*((_QWORD *)a2 + 3);
  *(_DWORD *)(v19 + 40) = *((_DWORD *)a2 + 29);
  *(_DWORD *)(v19 + 44) = *((_DWORD *)a2 + 30);
  *(_DWORD *)(v19 + 56) = a3;
  *(_QWORD *)(v19 + 64) = v19 + 80;
  *(_DWORD *)(v19 + 48) = *((_DWORD *)a2 + 26);
  *(_DWORD *)(v19 + 76) = *((_DWORD *)a2 + 27);
  *(_DWORD *)(v19 + 52) = *((_DWORD *)a2 + 28);
  *(_DWORD *)(v19 + 72) = *((_DWORD *)a2 + 35);
  memmove((void *)(v19 + 80), a4, v7);
  *((_QWORD *)this + 4) += v28;
  *(_BYTE *)(*(_QWORD *)this + 2753LL) = 1;
  if ( !*((_QWORD *)a2 + 10) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 963;
    v20 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v20[3] = gCddImageInfo;
    v20[4] = (unsigned int)dword_14003E570;
    v20[5] = 215857758;
    WdLogGlobalForLineNumber = 963;
  }
  if ( a3 > 8 )
  {
    v21 = 1;
    v22 = (const struct tagRECT *)(v19 + 8);
  }
  else
  {
    v21 = a3;
    v22 = a4;
  }
  (***((void (__fastcall ****)(_QWORD, CHwCommandBuffer *, const struct tagRECT *, __int64, _QWORD))a2 + 10))(
    *((_QWORD *)a2 + 10),
    this,
    v22,
    v21,
    0);
  v23 = (void (__fastcall ***)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD))*((_QWORD *)a2 + 11);
  if ( v23 )
    (**v23)(v23, this, 0, 0, 0);
  v24 = (void (__fastcall ***)(_QWORD, CHwCommandBuffer *, _QWORD, _QWORD, _QWORD))*((_QWORD *)a2 + 12);
  if ( v24 )
    (**v24)(v24, this, 0, 0, 0);
  *((_QWORD *)this + 5) = v19;
  v25 = *(_QWORD *)this;
  memset(v27, 0, 48);
  LODWORD(v27[0]) = 6;
  if ( (*(unsigned int (**)(void))(v25 + 80))() )
    (*(void (__fastcall **)(__int64, _QWORD, _OWORD *))(v25 + 264))(3039, 0, v27);
  return 1;
}

```

## disassembly

```asm
0x14001cce4  mov     [rsp+arg_8], rbx
0x14001cce9  mov     [rsp+Src], r9
0x14001ccee  push    rbp
0x14001ccef  push    rsi
0x14001ccf0  push    rdi
0x14001ccf1  push    r12
0x14001ccf3  push    r13
0x14001ccf5  push    r14
0x14001ccf7  push    r15
0x14001ccf9  sub     rsp, 60h
0x14001ccfd  mov     rsi, [rdx+20h]
0x14001cd01  mov     rbx, rcx
0x14001cd04  mov     r15d, r8d
0x14001cd07  mov     r14d, r8d
0x14001cd0a  shl     r15d, 4
0x14001cd0e  mov     rdi, rdx
0x14001cd11  mov     r10, [rbx+20h]
0x14001cd15  lea     ecx, [r15+50h]
0x14001cd19  add     r10, rcx
0x14001cd1c  mov     [rsp+98h+arg_0], rcx
0x14001cd24  cmp     r10, [rbx+18h]
0x14001cd28  ja      loc_14001D06D
0x14001cd2e  mov     rcx, [rbx]
0x14001cd31  mov     edx, [rbx+848h]
0x14001cd37  cmp     edx, [rcx+31A8h]
0x14001cd3d  ja      loc_14001D06D
0x14001cd43  mov     r8, [rdi]
0x14001cd46  xor     r13d, r13d
0x14001cd49  test    r8, r8
0x14001cd4c  jz      short loc_14001CD5A
0x14001cd4e  cmp     [r8+14h], r13b
0x14001cd52  jz      short loc_14001CD5A
0x14001cd54  add     r8, 4
0x14001cd58  jmp     short loc_14001CD5E
0x14001cd5a  mov     r8, [rdi+18h]
0x14001cd5e  mov     r9d, [r8+0Ch]
0x14001cd62  sub     r9d, [r8+4]
0x14001cd66  mov     eax, [r8]
0x14001cd69  mov     r8d, [r8+8]
0x14001cd6d  sub     r8d, eax
0x14001cd70  imul    r9d, r8d
0x14001cd74  xor     r8d, r8d; unsigned __int8
0x14001cd77  add     r9d, edx
0x14001cd7a  mov     [rbx+848h], r9d
0x14001cd81  cmp     [rbx+860h], r13b
0x14001cd88  jnz     loc_14001D073
0x14001cd8e  mov     eax, [rbx+830h]
0x14001cd94  mov     rcx, rbx; this
0x14001cd97  mov     [rbx+834h], eax
0x14001cd9d  mov     edx, [rdi+84h]; unsigned int
0x14001cda3  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001cda8  mov     r12d, eax
0x14001cdab  mov     [rsp+98h+arg_10], eax
0x14001cdb2  cmp     [rdi+80h], r13d
0x14001cdb9  jnz     short loc_14001CE35
0x14001cdbb  mov     rcx, [rbx]
0x14001cdbe  test    dword ptr [rcx+76Ch], 8000000h
0x14001cdc8  jnz     short loc_14001CE35
0x14001cdca  mov     rcx, cs:KdDebuggerEnabled
0x14001cdd1  cmp     [rcx], r13b
0x14001cdd4  jz      short loc_14001CE35
0x14001cdd6  lea     rcx, aHtmpsurfaceIsN; "hTmpSurface is NULL in CHwCommandBuffer"...
0x14001cddd  call    cs:__imp_DbgPrint
0x14001cde4  nop     dword ptr [rax+rax+00h]
0x14001cde9  mov     ecx, 2
0x14001cdee  call    cs:__imp_WdLogSingleEntry0
0x14001cdf5  nop     dword ptr [rax+rax+00h]
0x14001cdfa  mov     ebp, 39Bh
0x14001cdff  mov     cs:WdLogGlobalForLineNumber, ebp
0x14001ce05  call    cs:__imp_WdLogNewEntry5_WdError
0x14001ce0c  nop     dword ptr [rax+rax+00h]
0x14001ce11  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001ce18  mov     [rax+18h], rcx
0x14001ce1c  mov     ecx, cs:dword_14003E570
0x14001ce22  mov     [rax+20h], rcx
0x14001ce26  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001ce2e  mov     cs:WdLogGlobalForLineNumber, ebp
0x14001ce34  int     3; Trap to Debugger
0x14001ce35  mov     edx, [rdi+80h]; unsigned int
0x14001ce3b  test    edx, edx
0x14001ce3d  jz      short loc_14001CE4E
0x14001ce3f  xor     r8d, r8d; unsigned __int8
0x14001ce42  mov     rcx, rbx; this
0x14001ce45  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001ce4a  mov     ebp, eax
0x14001ce4c  jmp     short loc_14001CE51
0x14001ce4e  mov     ebp, r13d
0x14001ce51  mov     edx, [rdi+88h]; unsigned int
0x14001ce57  mov     r8b, 1; unsigned __int8
0x14001ce5a  mov     rcx, rbx; this
0x14001ce5d  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001ce62  mov     r13d, eax
0x14001ce65  or      ecx, 0FFFFFFFFh
0x14001ce68  xor     eax, eax
0x14001ce6a  cmp     [rdi+70h], ecx
0x14001ce6d  jz      short loc_14001CE80
0x14001ce6f  mov     edx, [rdi+7Ch]; unsigned int
0x14001ce72  mov     r8b, 1; unsigned __int8
0x14001ce75  mov     rcx, rbx; this
0x14001ce78  call    ?InsertToAllocationList@CHwCommandBuffer@@IEAAIIE@Z; CHwCommandBuffer::InsertToAllocationList(uint,uchar)
0x14001ce7d  or      ecx, 0FFFFFFFFh
0x14001ce80  cmp     r12d, ecx
0x14001ce83  jz      loc_14001D065
0x14001ce89  cmp     r13d, ecx
0x14001ce8c  jz      loc_14001D065
0x14001ce92  cmp     ebp, ecx
0x14001ce94  jz      loc_14001D065
0x14001ce9a  cmp     eax, ecx
0x14001ce9c  jz      loc_14001D065
0x14001cea2  mov     r12, [rbx+20h]
0x14001cea6  lea     ecx, [r15+50h]
0x14001ceaa  mov     r8d, r15d; Size
0x14001cead  mov     [r12+4], ecx
0x14001ceb2  lea     rcx, [r12+50h]; void *
0x14001ceb7  mov     dword ptr [r12], 7
0x14001cebf  mov     [r12+1Ch], eax
0x14001cec4  mov     eax, [rsp+98h+arg_10]
0x14001cecb  mov     [r12+18h], ebp
0x14001ced0  mov     rbp, [rsp+98h+Src]
0x14001ced8  mov     [r12+20h], eax
0x14001cedd  mov     rdx, rbp; Src
0x14001cee0  mov     [r12+24h], r13d
0x14001cee5  mov     rax, [rdi+18h]
0x14001cee9  movups  xmm0, xmmword ptr [rax]
0x14001ceec  movdqu  xmmword ptr [r12+8], xmm0
0x14001cef3  mov     eax, [rdi+74h]
0x14001cef6  mov     [r12+28h], eax
0x14001cefb  mov     eax, [rdi+78h]
0x14001cefe  mov     [r12+2Ch], eax
0x14001cf03  mov     [r12+38h], r14d
0x14001cf08  mov     [r12+40h], rcx
0x14001cf0d  mov     eax, [rdi+68h]
0x14001cf10  mov     [r12+30h], eax
0x14001cf15  mov     eax, [rdi+6Ch]
0x14001cf18  mov     [r12+4Ch], eax
0x14001cf1d  mov     eax, [rdi+70h]
0x14001cf20  mov     [r12+34h], eax
0x14001cf25  mov     eax, [rdi+8Ch]
0x14001cf2b  mov     [r12+48h], eax
0x14001cf30  call    memmove
0x14001cf35  mov     rax, [rsp+98h+arg_0]
0x14001cf3d  mov     r13d, 1
0x14001cf43  add     [rbx+20h], rax
0x14001cf47  xor     r15d, r15d
0x14001cf4a  mov     rax, [rbx]
0x14001cf4d  mov     [rax+0AC1h], r13b
0x14001cf54  cmp     [rdi+50h], r15
0x14001cf58  jnz     short loc_14001CFA9
0x14001cf5a  mov     ecx, r13d
0x14001cf5d  call    cs:__imp_WdLogSingleEntry0
0x14001cf64  nop     dword ptr [rax+rax+00h]
0x14001cf69  mov     r15d, 3C3h
0x14001cf6f  mov     cs:WdLogGlobalForLineNumber, r15d
0x14001cf76  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001cf7d  nop     dword ptr [rax+rax+00h]
0x14001cf82  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001cf89  mov     [rax+18h], rcx
0x14001cf8d  mov     ecx, cs:dword_14003E570
0x14001cf93  mov     [rax+20h], rcx
0x14001cf97  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001cf9f  mov     cs:WdLogGlobalForLineNumber, r15d
0x14001cfa6  xor     r15d, r15d
0x14001cfa9  mov     rcx, [rdi+50h]
0x14001cfad  mov     rdx, rbx
0x14001cfb0  mov     [rsp+98h+var_78], r15
0x14001cfb5  mov     rax, [rcx]
0x14001cfb8  mov     rax, [rax]
0x14001cfbb  cmp     r14d, 8
0x14001cfbf  ja      short loc_14001CFC9
0x14001cfc1  mov     r9d, r14d
0x14001cfc4  mov     r8, rbp
0x14001cfc7  jmp     short loc_14001CFD1
0x14001cfc9  mov     r9d, r13d
0x14001cfcc  lea     r8, [r12+8]
0x14001cfd1  call    _guard_dispatch_icall
0x14001cfd6  mov     rcx, [rdi+58h]
0x14001cfda  test    rcx, rcx
0x14001cfdd  jz      short loc_14001CFF8
0x14001cfdf  mov     rax, [rcx]
0x14001cfe2  xor     r9d, r9d
0x14001cfe5  xor     r8d, r8d
0x14001cfe8  mov     [rsp+98h+var_78], r15
0x14001cfed  mov     rdx, rbx
0x14001cff0  mov     rax, [rax]
0x14001cff3  call    _guard_dispatch_icall
0x14001cff8  mov     rcx, [rdi+60h]
0x14001cffc  test    rcx, rcx
0x14001cfff  jz      short loc_14001D01A
0x14001d001  mov     rax, [rcx]
0x14001d004  xor     r9d, r9d
0x14001d007  xor     r8d, r8d
0x14001d00a  mov     [rsp+98h+var_78], r15
0x14001d00f  mov     rdx, rbx
0x14001d012  mov     rax, [rax]
0x14001d015  call    _guard_dispatch_icall
0x14001d01a  xorps   xmm0, xmm0
0x14001d01d  mov     [rbx+28h], r12
0x14001d021  mov     rbx, [rbx]
0x14001d024  movups  [rsp+98h+var_68], xmm0
0x14001d029  mov     dword ptr [rsp+98h+var_68], 6
0x14001d031  movups  [rsp+98h+var_58], xmm0
0x14001d036  movups  [rsp+98h+var_48], xmm0
0x14001d03b  mov     rax, [rbx+50h]
0x14001d03f  call    _guard_dispatch_icall
0x14001d044  test    eax, eax
0x14001d046  jz      short loc_14001D060
0x14001d048  mov     rax, [rbx+108h]
0x14001d04f  lea     r8, [rsp+98h+var_68]
0x14001d054  xor     edx, edx
0x14001d056  mov     ecx, 0BDFh
0x14001d05b  call    _guard_dispatch_icall
0x14001d060  mov     eax, r13d
0x14001d063  jmp     short loc_14001D083
0x14001d065  mov     rcx, rbx; this
0x14001d068  call    ?RecoverAllocationListState@CHwCommandBuffer@@IEAAXXZ; CHwCommandBuffer::RecoverAllocationListState(void)
0x14001d06d  mov     rcx, [rbx]; this
0x14001d070  xor     r8d, r8d; int
0x14001d073  mov     r9d, 2; unsigned int
0x14001d079  mov     rdx, rsi; struct CCommandBufferMutex *
0x14001d07c  call    ?FlushNoMutex@CDDPDEV@@QEAAJPEAVCCommandBufferMutex@@HI@Z; CDDPDEV::FlushNoMutex(CCommandBufferMutex *,int,uint)
0x14001d081  xor     eax, eax
0x14001d083  mov     rbx, [rsp+98h+arg_8]
0x14001d08b  add     rsp, 60h
0x14001d08f  pop     r15
0x14001d091  pop     r14
0x14001d093  pop     r13
0x14001d095  pop     r12
0x14001d097  pop     rdi
0x14001d098  pop     rsi
0x14001d099  pop     rbp
0x14001d09a  retn
```
