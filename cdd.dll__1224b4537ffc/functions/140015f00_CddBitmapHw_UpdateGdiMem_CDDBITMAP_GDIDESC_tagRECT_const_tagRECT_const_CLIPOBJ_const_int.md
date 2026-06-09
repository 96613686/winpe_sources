# CddBitmapHw::UpdateGdiMem(CDDBITMAP_GDIDESC *,tagRECT const *,tagRECT const *,_CLIPOBJ const *,int *)

- ea: `0x140015f00`
- end: `0x1400160c0`
- name: `?UpdateGdiMem@CddBitmapHw@@UEAAJPEAUCDDBITMAP_GDIDESC@@PEBUtagRECT@@1PEBU_CLIPOBJ@@PEAH@Z`
- size: `448`
- prototype: `__int64 __fastcall(CddBitmapHw *__hidden this, struct CDDBITMAP_GDIDESC *, const struct tagRECT *, const struct tagRECT *, const struct _CLIPOBJ *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x14000cb44`
- `0x140015f00`
- `0x1400160c8`
- `0x1400372d0`

## import_xrefs

- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015f83`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015fd7`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015f83`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140015fd7`
- `watchdog!WdLogSingleEntry0` at `0x140015f6d`
- `watchdog!WdLogSingleEntry0` at `0x140015fc1`
- `watchdog!WdLogSingleEntry0` at `0x140015f6d`
- `watchdog!WdLogSingleEntry0` at `0x140015fc1`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::UpdateGdiMem(
        CddBitmapHw *this,
        struct CDDBITMAP_GDIDESC *a2,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        const struct _CLIPOBJ *a5,
        int *a6)
{
  unsigned int (**v6)(void); // rsi
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v22; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-81h]
  __int64 v24; // [rsp+40h] [rbp-79h]
  int v25; // [rsp+48h] [rbp-71h]
  _QWORD v26[6]; // [rsp+50h] [rbp-69h] BYREF
  char v27; // [rsp+80h] [rbp-39h]
  __int64 v28; // [rsp+98h] [rbp-21h]
  CddBitmapHw *v29; // [rsp+A0h] [rbp-19h]
  __int64 v30; // [rsp+A8h] [rbp-11h]
  int v31; // [rsp+B0h] [rbp-9h]
  int v32; // [rsp+B4h] [rbp-5h]
  __int64 v33; // [rsp+B8h] [rbp-1h]
  int v34; // [rsp+C0h] [rbp+7h]
  bool v35; // [rsp+C4h] [rbp+Bh]

  v6 = (unsigned int (**)(void))*((_QWORD *)this + 1);
  if ( v6[10]() )
  {
    CDDETWPROFILER::Init((CDDETWPROFILER *)&v22, (struct CDDPDEV *)v6, 0xBDEu, 0, 0);
    v11 = v25;
  }
  else
  {
    v11 = 1;
  }
  *a6 = 0;
  if ( !a2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 798;
    v14 = (_QWORD *)WdLogNewEntry5_WdAssertion(v13, v12);
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = 798;
  }
  if ( *((_DWORD *)this + 8) != 2 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 799;
    v17 = (_QWORD *)WdLogNewEntry5_WdAssertion(v16, v15);
    v17[3] = gCddImageInfo;
    v17[4] = (unsigned int)dword_14003E570;
    v17[5] = 215857758;
    WdLogGlobalForLineNumber = 799;
  }
  v18 = *((_QWORD *)this + 1);
  v26[0] = a5;
  v26[3] = (char *)a2 + 36;
  v30 = *((_QWORD *)a2 + 3);
  v31 = *((_DWORD *)this + 10);
  v32 = *((_DWORD *)a2 + 4);
  v19 = *(_QWORD *)a2;
  v29 = this;
  v35 = 0;
  v28 = v18;
  v27 = 0;
  v26[1] = a3;
  v26[2] = a4;
  v33 = 1;
  v34 = *(_DWORD *)(v19 + 64);
  v26[5] = 0;
  v35 = (*(_DWORD *)(v18 + 2744) & 0x1000) != 0;
  ClipDstRects(
    (struct CLIP_RECTS_DATA *)v26,
    (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
  *((_DWORD *)a2 + 8) = *((_DWORD *)a2 + 4);
  *a6 = 1;
  if ( !v11 )
  {
    LOBYTE(v20) = 2;
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(v22 + 264))(v23, v20, v24);
  }
  return 0;
}

```

## disassembly

```asm
0x140015f00  push    rbp
0x140015f02  push    rbx
0x140015f03  push    rsi
0x140015f04  push    rdi
0x140015f05  push    r12
0x140015f07  push    r14
0x140015f09  push    r15
0x140015f0b  lea     rbp, [rsp-17h]
0x140015f10  sub     rsp, 0D0h
0x140015f17  mov     rsi, [rcx+8]
0x140015f1b  mov     r15, r9
0x140015f1e  mov     r12, r8
0x140015f21  mov     rbx, rdx
0x140015f24  mov     rdi, rcx
0x140015f27  mov     rax, [rsi+50h]
0x140015f2b  call    _guard_dispatch_icall
0x140015f30  test    eax, eax
0x140015f32  jz      short loc_140015F55
0x140015f34  xor     r9d, r9d; struct _DXGKETW_PARAMS *
0x140015f37  mov     [rsp+100h+var_E0], 0; bool
0x140015f3c  mov     r8d, 0BDEh; unsigned int
0x140015f42  lea     rcx, [rsp+100h+var_D0]; this
0x140015f47  mov     rdx, rsi; struct CDDPDEV *
0x140015f4a  call    ?Init@CDDETWPROFILER@@QEAAXPEAUCDDPDEV@@IPEAU_DXGKETW_PARAMS@@_N@Z; CDDETWPROFILER::Init(CDDPDEV *,uint,_DXGKETW_PARAMS *,bool)
0x140015f4f  mov     r14d, [rbp+47h+var_B8]
0x140015f53  jmp     short loc_140015F5B
0x140015f55  mov     r14d, 1
0x140015f5b  mov     rsi, [rbp+47h+arg_28]
0x140015f5f  mov     dword ptr [rsi], 0
0x140015f65  test    rbx, rbx
0x140015f68  jnz     short loc_140015FB6
0x140015f6a  lea     ecx, [rbx+1]
0x140015f6d  call    cs:__imp_WdLogSingleEntry0
0x140015f74  nop     dword ptr [rax+rax+00h]
0x140015f79  mov     cs:WdLogGlobalForLineNumber, 31Eh
0x140015f83  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140015f8a  nop     dword ptr [rax+rax+00h]
0x140015f8f  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015f96  mov     [rax+18h], rcx
0x140015f9a  mov     ecx, cs:dword_14003E570
0x140015fa0  mov     [rax+20h], rcx
0x140015fa4  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140015fac  mov     cs:WdLogGlobalForLineNumber, 31Eh
0x140015fb6  cmp     dword ptr [rdi+20h], 2
0x140015fba  jz      short loc_14001600A
0x140015fbc  mov     ecx, 1
0x140015fc1  call    cs:__imp_WdLogSingleEntry0
0x140015fc8  nop     dword ptr [rax+rax+00h]
0x140015fcd  mov     cs:WdLogGlobalForLineNumber, 31Fh
0x140015fd7  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140015fde  nop     dword ptr [rax+rax+00h]
0x140015fe3  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140015fea  mov     [rax+18h], rcx
0x140015fee  mov     ecx, cs:dword_14003E570
0x140015ff4  mov     [rax+20h], rcx
0x140015ff8  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140016000  mov     cs:WdLogGlobalForLineNumber, 31Fh
0x14001600a  mov     rdx, [rdi+8]
0x14001600e  mov     rax, [rbp+47h+arg_20]
0x140016012  mov     [rbp+47h+var_B0], rax
0x140016016  lea     rax, [rbx+24h]
0x14001601a  mov     [rbp+47h+var_98], rax
0x14001601e  mov     rax, [rbx+18h]
0x140016022  mov     [rbp+47h+var_58], rax
0x140016026  mov     eax, [rdi+28h]
0x140016029  mov     [rbp+47h+var_50], eax
0x14001602c  mov     eax, [rbx+10h]
0x14001602f  mov     [rbp+47h+var_4C], eax
0x140016032  mov     rax, [rbx]
0x140016035  mov     [rbp+47h+var_60], rdi
0x140016039  mov     edi, 1
0x14001603e  mov     [rbp+47h+var_3C], 0
0x140016042  mov     [rbp+47h+var_68], rdx
0x140016046  mov     [rbp+47h+var_80], 0
0x14001604a  mov     [rbp+47h+var_A8], r12
0x14001604e  mov     [rbp+47h+var_A0], r15
0x140016052  mov     [rbp+47h+var_48], rdi
0x140016056  mov     ecx, [rax+40h]
0x140016059  mov     [rbp+47h+var_40], ecx
0x14001605c  lea     rcx, [rbp+47h+var_B0]; struct CLIP_RECTS_DATA *
0x140016060  mov     [rbp+47h+var_88], 0
0x140016068  mov     eax, [rdx+0AB8h]
0x14001606e  lea     rdx, ?BitBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x140016075  shr     eax, 0Ch
0x140016078  and     al, dil
0x14001607b  mov     [rbp+47h+var_3C], al
0x14001607e  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140016083  mov     eax, [rbx+10h]
0x140016086  mov     [rbx+20h], eax
0x140016089  mov     [rsi], edi
0x14001608b  test    r14d, r14d
0x14001608e  jnz     short loc_1400160AB
0x140016090  mov     rax, [rsp+100h+var_D0]
0x140016095  mov     dl, 2
0x140016097  mov     r8, [rbp+47h+var_C0]
0x14001609b  mov     ecx, [rsp+100h+var_C8]
0x14001609f  mov     rax, [rax+108h]
0x1400160a6  call    _guard_dispatch_icall
0x1400160ab  xor     eax, eax
0x1400160ad  add     rsp, 0D0h
0x1400160b4  pop     r15
0x1400160b6  pop     r14
0x1400160b8  pop     r12
0x1400160ba  pop     rdi
0x1400160bb  pop     rsi
0x1400160bc  pop     rbx
0x1400160bd  pop     rbp
0x1400160be  retn
```
