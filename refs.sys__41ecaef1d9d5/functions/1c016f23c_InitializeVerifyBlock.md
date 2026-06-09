# InitializeVerifyBlock

- ea: `0x1c016f23c`
- end: `0x1c016f6c6`
- name: `InitializeVerifyBlock`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1c016fc10`

## callees

- `0x1c000247c`
- `0x1c00024cc`
- `0x1c0002548`
- `0x1c0004300`
- `0x1c000f770`
- `0x1c003ee44`
- `0x1c003efa0`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c016f1bc`
- `0x1c016f23c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c016f365`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c016f365`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c016f696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0180135`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c016f696`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0180135`

## string_xrefs

- `0x1c016f470`: `mount.c`
- `0x1c016f4d9`: `mount.c`
- `0x1c016f530`: `mount.c`
- `0x1c016f598`: `mount.c`
- `0x1c016f601`: `mount.c`
- `0x1c016f658`: `mount.c`

## pseudocode

```c
void __fastcall InitializeVerifyBlock(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 *PoolWithTag; // rsi
  __int64 inited; // rbx
  int Row; // eax
  unsigned __int64 v9; // xmm0_8
  unsigned int v10; // r15d
  int VolumeInfo; // eax
  __int64 v12; // rcx
  unsigned __int16 v13; // r9
  unsigned __int16 v14; // r8
  __int64 v15; // rax
  unsigned __int16 v16; // [rsp+30h] [rbp-108h]
  unsigned int Status; // [rsp+34h] [rbp-104h]
  __int64 v18; // [rsp+40h] [rbp-F8h] BYREF
  int v19; // [rsp+48h] [rbp-F0h]
  int v20; // [rsp+4Ch] [rbp-ECh]
  __int64 *v21; // [rsp+50h] [rbp-E8h]
  int v22; // [rsp+58h] [rbp-E0h]
  int v23; // [rsp+5Ch] [rbp-DCh]
  __int64 v24; // [rsp+60h] [rbp-D8h]
  __m128i v25; // [rsp+68h] [rbp-D0h]
  _BYTE v26[112]; // [rsp+80h] [rbp-B8h] BYREF

  v20 = 0;
  v23 = 0;
  PoolWithTag = 0;
  memset(v26, 0, sizeof(v26));
  inited = MsInitRowWithBuffer(&v26[32]);
  v18 = 1344;
  v21 = &v18;
  v19 = 8;
  v24 = 0;
  v22 = 0;
  RefsBindMinstoreTransaction(a1);
  Row = MsFindRow(
          *(struct CmsTransactionContext **)(a1 + 24),
          *(CmsTable **)(a3 + 96),
          (struct CmsRowWithBuffer *)inited);
  Status = Row;
  if ( Row < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
        (unsigned int)Row);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, Status);
    goto LABEL_18;
  }
  if ( *(_DWORD *)(inited + 16) < 0x10u )
  {
LABEL_18:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, 3221225490LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741806);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, 3221225490LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741806);
    VolumeInfo = RefsRaiseStatusInternal(a1, 3221225490LL);
LABEL_31:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_7031d589edf23cbf7a1abad52b310385_Traceguids,
        (unsigned int)VolumeInfo);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, Status);
    goto LABEL_38;
  }
  v25 = *(__m128i *)*(_QWORD *)(inited + 24);
  v9 = _mm_srli_si128(v25, 8).m128i_u64[0];
  if ( v9 - 1 <= 0xFFFFFFFE )
  {
    *(_DWORD *)(a3 + 384) = v9;
    *(_QWORD *)(a3 + 376) = v25.m128i_i64[0];
    if ( (*(_DWORD *)(a3 + 4) & 0x2000000) != 0 )
      goto LABEL_51;
    v10 = (_DWORD)v9 << *(_DWORD *)(a3 + 464);
    PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v10, 0x6F4D6552u);
    memset(PoolWithTag, 0, v10);
    VolumeInfo = RefsGetVolumeInfo(a1, a3, PoolWithTag);
    Status = VolumeInfo;
    if ( VolumeInfo >= 0 )
    {
      v13 = 0;
      v14 = 0;
      v16 = 0;
      while ( v14 < 0x1C0u )
      {
        v12 = (unsigned __int8)(v13 & 1) << 15;
        v13 = (v13 >> 1) + ((v13 & 1) << 15) + PoolWithTag[v14++];
        v16 = v14;
      }
      *(_WORD *)(a3 + 388) = v13;
      LOBYTE(v12) = *(_BYTE *)(a3 + 464);
      RefsWriteVerifyBlock(v12, a2, a3, PoolWithTag, *(_QWORD *)(a3 + 376) << v12, v10, v16, PoolWithTag);
      goto LABEL_51;
    }
    goto LABEL_31;
  }
LABEL_38:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, 3221225522LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741774);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids, 3221225522LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741774);
  RefsRaiseStatusInternal(a1, 3221225522LL);
LABEL_51:
  v15 = MsUseRowWithBuffer(&v26[32]);
  MsCleanupRowWithBuffer(v15);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
}

```

## disassembly

```asm
0x1c016f23c  push    rbx
0x1c016f23e  push    rsi
0x1c016f23f  push    rdi
0x1c016f240  push    r12
0x1c016f242  push    r13
0x1c016f244  push    r14
0x1c016f246  push    r15
0x1c016f248  sub     rsp, 100h
0x1c016f24f  mov     rax, cs:__security_cookie
0x1c016f256  xor     rax, rsp
0x1c016f259  mov     [rsp+138h+var_48], rax
0x1c016f261  mov     rdi, r8
0x1c016f264  mov     r12, rdx
0x1c016f267  mov     r14, rcx
0x1c016f26a  xorps   xmm0, xmm0
0x1c016f26d  movups  [rsp+138h+var_F0], xmm0
0x1c016f272  movups  [rsp+138h+var_E0], xmm0
0x1c016f277  xor     r13d, r13d
0x1c016f27a  mov     esi, r13d
0x1c016f27d  mov     [rsp+138h+var_100], r13
0x1c016f282  mov     [rsp+138h+var_F8], r13
0x1c016f287  xor     edx, edx; Val
0x1c016f289  lea     r8d, [r13+70h]; Size
0x1c016f28d  lea     rcx, [rsp+138h+var_B8]; void *
0x1c016f295  call    memset
0x1c016f29a  lea     rcx, [rsp+138h+var_98]
0x1c016f2a2  call    MsInitRowWithBuffer
0x1c016f2a7  mov     rbx, rax
0x1c016f2aa  mov     [rsp+138h+var_F8], 540h
0x1c016f2b3  lea     rax, [rsp+138h+var_F8]
0x1c016f2b8  mov     qword ptr [rsp+138h+var_F0+8], rax
0x1c016f2bd  mov     dword ptr [rsp+138h+var_F0], 8
0x1c016f2c5  mov     qword ptr [rsp+138h+var_E0+8], r13
0x1c016f2ca  mov     dword ptr [rsp+138h+var_E0], r13d
0x1c016f2cf  mov     rcx, r14
0x1c016f2d2  call    RefsBindMinstoreTransaction
0x1c016f2d7  mov     [rsp+138h+var_118], rbx; struct CmsRowWithBuffer *
0x1c016f2dc  lea     r8, [rsp+138h+var_F0]
0x1c016f2e1  mov     rdx, [rdi+60h]; this
0x1c016f2e5  mov     rcx, [r14+18h]; struct CmsTransactionContext *
0x1c016f2e9  call    MsFindRow
0x1c016f2ee  mov     r9d, eax
0x1c016f2f1  mov     [rsp+138h+Status], eax
0x1c016f2f5  test    eax, eax
0x1c016f2f7  js      loc_1C016F429
0x1c016f2fd  cmp     dword ptr [rbx+10h], 10h
0x1c016f301  jb      loc_1C016F48C
0x1c016f307  mov     rax, [rbx+18h]
0x1c016f30b  movups  xmm0, xmmword ptr [rax]
0x1c016f30e  movups  [rsp+138h+var_D0], xmm0
0x1c016f313  psrldq  xmm0, 8
0x1c016f318  movq    r15, xmm0
0x1c016f31d  lea     rax, [r15-1]
0x1c016f321  mov     ecx, 0FFFFFFFEh
0x1c016f326  cmp     rax, rcx
0x1c016f329  ja      loc_1C016F5B4
0x1c016f32f  mov     [rdi+180h], r15d
0x1c016f336  mov     rax, qword ptr [rsp+138h+var_D0]
0x1c016f33b  mov     [rdi+178h], rax
0x1c016f342  test    dword ptr [rdi+4], 2000000h
0x1c016f349  jnz     loc_1C016F424
0x1c016f34f  mov     ecx, [rdi+1D0h]
0x1c016f355  shl     r15d, cl
0x1c016f358  mov     r8d, 6F4D6552h; Tag
0x1c016f35e  mov     edx, r15d; NumberOfBytes
0x1c016f361  lea     ecx, [r13+11h]; PoolType
0x1c016f365  call    cs:__imp_ExAllocatePoolWithTag
0x1c016f36c  nop     dword ptr [rax+rax+00h]
0x1c016f371  mov     rsi, rax
0x1c016f374  mov     [rsp+138h+var_100], rax
0x1c016f379  mov     r8d, r15d; Size
0x1c016f37c  xor     edx, edx; Val
0x1c016f37e  mov     rcx, rax; void *
0x1c016f381  call    memset
0x1c016f386  mov     r8, rsi
0x1c016f389  mov     rdx, rdi
0x1c016f38c  mov     rcx, r14
0x1c016f38f  call    RefsGetVolumeInfo
0x1c016f394  mov     [rsp+138h+Status], eax
0x1c016f398  test    eax, eax
0x1c016f39a  js      loc_1C016F54E
0x1c016f3a0  movzx   r9d, r13w
0x1c016f3a4  mov     [rsp+138h+var_108], r13w
0x1c016f3aa  movzx   r8d, r13w
0x1c016f3ae  mov     [rsp+138h+var_108], r13w
0x1c016f3b4  mov     eax, 1C0h
0x1c016f3b9  cmp     r8w, ax
0x1c016f3bd  jnb     short loc_1C016F3F4
0x1c016f3bf  movzx   eax, r8w
0x1c016f3c3  movzx   edx, byte ptr [rax+rsi]
0x1c016f3c7  movzx   ecx, r9w
0x1c016f3cb  and     cx, 1
0x1c016f3cf  mov     eax, 8000h
0x1c016f3d4  movzx   ecx, cx
0x1c016f3d7  imul    ecx, eax
0x1c016f3da  add     dx, cx
0x1c016f3dd  movzx   eax, r9w
0x1c016f3e1  shr     ax, 1
0x1c016f3e4  lea     r9d, [rax+rdx]
0x1c016f3e8  inc     r8w
0x1c016f3ec  mov     [rsp+138h+var_108], r8w
0x1c016f3f2  jmp     short loc_1C016F3B4
0x1c016f3f4  mov     [rdi+184h], r9w
0x1c016f3fc  mov     cl, [rdi+1D0h]
0x1c016f402  mov     rax, [rdi+178h]
0x1c016f409  shl     rax, cl
0x1c016f40c  mov     [rsp+138h+var_110], r15d
0x1c016f411  mov     [rsp+138h+var_118], rax
0x1c016f416  mov     r9, rsi
0x1c016f419  mov     r8, rdi
0x1c016f41c  mov     rdx, r12
0x1c016f41f  call    RefsWriteVerifyBlock
0x1c016f424  jmp     loc_1C016F677
0x1c016f429  lea     rbx, WPP_GLOBAL_Control
0x1c016f430  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f437  cmp     rcx, rbx
0x1c016f43a  jz      short loc_1C016F460
0x1c016f43c  test    dword ptr [rcx+2Ch], 100h
0x1c016f443  jz      short loc_1C016F460
0x1c016f445  cmp     byte ptr [rcx+29h], 4
0x1c016f449  jb      short loc_1C016F460
0x1c016f44b  mov     edx, 32h ; '2'
0x1c016f450  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f457  mov     rcx, [rcx+18h]
0x1c016f45b  call    WPP_SF_D
0x1c016f460  mov     al, cs:RefsStatusDebugEnabled
0x1c016f466  test    al, al
0x1c016f468  jz      short loc_1C016F480
0x1c016f46a  mov     r8d, 0C1Dh
0x1c016f470  lea     rdx, aMountC; "mount.c"
0x1c016f477  mov     ecx, [rsp+138h+Status]; Status
0x1c016f47b  call    RefsStatusDebug
0x1c016f480  mov     edx, [rsp+138h+Status]
0x1c016f484  mov     rcx, r14
0x1c016f487  call    RefsRaiseStatusInternal
0x1c016f48c  lea     rbx, WPP_GLOBAL_Control
0x1c016f493  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f49a  cmp     rcx, rbx
0x1c016f49d  jz      short loc_1C016F4C9
0x1c016f49f  test    dword ptr [rcx+2Ch], 100h
0x1c016f4a6  jz      short loc_1C016F4C9
0x1c016f4a8  cmp     byte ptr [rcx+29h], 4
0x1c016f4ac  jb      short loc_1C016F4C9
0x1c016f4ae  mov     edx, 33h ; '3'
0x1c016f4b3  mov     r9d, 0C0000012h
0x1c016f4b9  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f4c0  mov     rcx, [rcx+18h]
0x1c016f4c4  call    WPP_SF_D
0x1c016f4c9  mov     al, cs:RefsStatusDebugEnabled
0x1c016f4cf  test    al, al
0x1c016f4d1  jz      short loc_1C016F4EA
0x1c016f4d3  mov     r8d, 0C25h
0x1c016f4d9  lea     rdx, aMountC; "mount.c"
0x1c016f4e0  mov     ecx, 0C0000012h; Status
0x1c016f4e5  call    RefsStatusDebug
0x1c016f4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f4f1  cmp     rcx, rbx
0x1c016f4f4  jz      short loc_1C016F520
0x1c016f4f6  test    dword ptr [rcx+2Ch], 100h
0x1c016f4fd  jz      short loc_1C016F520
0x1c016f4ff  cmp     byte ptr [rcx+29h], 4
0x1c016f503  jb      short loc_1C016F520
0x1c016f505  mov     edx, 34h ; '4'
0x1c016f50a  mov     r9d, 0C0000012h
0x1c016f510  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f517  mov     rcx, [rcx+18h]
0x1c016f51b  call    WPP_SF_D
0x1c016f520  mov     al, cs:RefsStatusDebugEnabled
0x1c016f526  test    al, al
0x1c016f528  jz      short loc_1C016F541
0x1c016f52a  mov     r8d, 0C26h
0x1c016f530  lea     rdx, aMountC; "mount.c"
0x1c016f537  mov     ecx, 0C0000012h; Status
0x1c016f53c  call    RefsStatusDebug
0x1c016f541  mov     edx, 0C0000012h
0x1c016f546  mov     rcx, r14
0x1c016f549  call    RefsRaiseStatusInternal
0x1c016f54e  lea     rbx, WPP_GLOBAL_Control
0x1c016f555  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f55c  cmp     rcx, rbx
0x1c016f55f  jz      short loc_1C016F588
0x1c016f561  test    dword ptr [rcx+2Ch], 100h
0x1c016f568  jz      short loc_1C016F588
0x1c016f56a  cmp     byte ptr [rcx+29h], 4
0x1c016f56e  jb      short loc_1C016F588
0x1c016f570  mov     edx, 37h ; '7'
0x1c016f575  mov     r9d, eax
0x1c016f578  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f57f  mov     rcx, [rcx+18h]
0x1c016f583  call    WPP_SF_D
0x1c016f588  mov     al, cs:RefsStatusDebugEnabled
0x1c016f58e  test    al, al
0x1c016f590  jz      short loc_1C016F5A8
0x1c016f592  mov     r8d, 0C41h
0x1c016f598  lea     rdx, aMountC; "mount.c"
0x1c016f59f  mov     ecx, [rsp+138h+Status]; Status
0x1c016f5a3  call    RefsStatusDebug
0x1c016f5a8  mov     edx, [rsp+138h+Status]
0x1c016f5ac  mov     rcx, r14
0x1c016f5af  call    RefsRaiseStatusInternal
0x1c016f5b4  lea     rbx, WPP_GLOBAL_Control
0x1c016f5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f5c2  cmp     rcx, rbx
0x1c016f5c5  jz      short loc_1C016F5F1
0x1c016f5c7  test    dword ptr [rcx+2Ch], 100h
0x1c016f5ce  jz      short loc_1C016F5F1
0x1c016f5d0  cmp     byte ptr [rcx+29h], 4
0x1c016f5d4  jb      short loc_1C016F5F1
0x1c016f5d6  mov     edx, 35h ; '5'
0x1c016f5db  mov     r9d, 0C0000032h
0x1c016f5e1  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f5e8  mov     rcx, [rcx+18h]
0x1c016f5ec  call    WPP_SF_D
0x1c016f5f1  mov     al, cs:RefsStatusDebugEnabled
0x1c016f5f7  test    al, al
0x1c016f5f9  jz      short loc_1C016F612
0x1c016f5fb  mov     r8d, 0C2Dh
0x1c016f601  lea     rdx, aMountC; "mount.c"
0x1c016f608  mov     ecx, 0C0000032h; Status
0x1c016f60d  call    RefsStatusDebug
0x1c016f612  mov     rcx, cs:WPP_GLOBAL_Control
0x1c016f619  cmp     rcx, rbx
0x1c016f61c  jz      short loc_1C016F648
0x1c016f61e  test    dword ptr [rcx+2Ch], 100h
0x1c016f625  jz      short loc_1C016F648
0x1c016f627  cmp     byte ptr [rcx+29h], 4
0x1c016f62b  jb      short loc_1C016F648
0x1c016f62d  mov     edx, 36h ; '6'
0x1c016f632  mov     r9d, 0C0000032h
0x1c016f638  lea     r8, WPP_7031d589edf23cbf7a1abad52b310385_Traceguids
0x1c016f63f  mov     rcx, [rcx+18h]
0x1c016f643  call    WPP_SF_D
0x1c016f648  mov     al, cs:RefsStatusDebugEnabled
0x1c016f64e  test    al, al
0x1c016f650  jz      short loc_1C016F669
0x1c016f652  mov     r8d, 0C2Eh
0x1c016f658  lea     rdx, aMountC; "mount.c"
0x1c016f65f  mov     ecx, 0C0000032h; Status
0x1c016f664  call    RefsStatusDebug
0x1c016f669  mov     edx, 0C0000032h
0x1c016f66e  mov     rcx, r14
0x1c016f671  call    RefsRaiseStatusInternal
0x1c016f676  nop
0x1c016f677  lea     rcx, [rsp+138h+var_98]
0x1c016f67f  call    MsUseRowWithBuffer
0x1c016f684  mov     rcx, rax
0x1c016f687  call    MsCleanupRowWithBuffer
0x1c016f68c  test    rsi, rsi
0x1c016f68f  jz      short loc_1C016F6A2
0x1c016f691  xor     edx, edx; Tag
0x1c016f693  mov     rcx, rsi; P
0x1c016f696  call    cs:__imp_ExFreePoolWithTag
0x1c016f69d  nop     dword ptr [rax+rax+00h]
0x1c016f6a2  mov     rcx, [rsp+138h+var_48]
0x1c016f6aa  xor     rcx, rsp; StackCookie
0x1c016f6ad  call    __security_check_cookie
0x1c016f6b2  add     rsp, 100h
0x1c016f6b9  pop     r15
0x1c016f6bb  pop     r14
0x1c016f6bd  pop     r13
0x1c016f6bf  pop     r12
0x1c016f6c1  pop     rdi
0x1c016f6c2  pop     rsi
0x1c016f6c3  pop     rbx
0x1c016f6c4  retn
0x1c018010d  push    rbp
0x1c018010f  sub     rsp, 30h
0x1c0180113  mov     rbp, rdx
0x1c0180116  lea     rcx, [rbp+0A0h]
0x1c018011d  call    MsUseRowWithBuffer
0x1c0180122  mov     rcx, rax
0x1c0180125  call    MsCleanupRowWithBuffer
0x1c018012a  mov     rcx, [rbp+38h]; P
0x1c018012e  test    rcx, rcx
0x1c0180131  jz      short loc_1C0180146
0x1c0180133  xor     edx, edx; Tag
0x1c0180135  call    cs:__imp_ExFreePoolWithTag
0x1c018013c  nop     dword ptr [rax+rax+00h]
0x1c0180141  and     qword ptr [rbp+38h], 0
0x1c0180146  add     rsp, 30h
0x1c018014a  pop     rbp
0x1c018014b  retn
```
