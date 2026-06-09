# CddBitmapHw::GdiDirtyUpdate(CDDBITMAP_GDIDESC const *,_RECTL const *,_CLIPOBJ const *,tagPOINT const *)

- ea: `0x140020af0`
- end: `0x140020c50`
- name: `?GdiDirtyUpdate@CddBitmapHw@@UEAAXPEBUCDDBITMAP_GDIDESC@@PEBU_RECTL@@PEBU_CLIPOBJ@@PEBUtagPOINT@@@Z`
- size: `352`
- prototype: `void __fastcall(CddBitmapHw *__hidden this, const struct CDDBITMAP_GDIDESC *, const struct _RECTL *, const struct _CLIPOBJ *, const struct tagPOINT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000cb44`
- `0x140010670`
- `0x140020af0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140020bc0`
- `ntoskrnl!KeGetCurrentIrql` at `0x140020bc0`
- `ntoskrnl!KeSetEvent` at `0x140020c32`
- `ntoskrnl!KeSetEvent` at `0x140020c32`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140020beb`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140020beb`
- `watchdog!WdLogSingleEntry0` at `0x140020bd5`
- `watchdog!WdLogSingleEntry0` at `0x140020bd5`

## pseudocode

```c
void __fastcall CddBitmapHw::GdiDirtyUpdate(
        CddBitmapHw *this,
        const struct CDDBITMAP_GDIDESC *a2,
        const struct _RECTL *a3,
        const struct _CLIPOBJ *a4)
{
  int v5; // ecx
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  PRKEVENT *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  _QWORD v14[6]; // [rsp+20h] [rbp-31h] BYREF
  char v15; // [rsp+50h] [rbp-1h]
  __int64 v16; // [rsp+58h] [rbp+7h]
  int v17; // [rsp+60h] [rbp+Fh]
  __int64 v18; // [rsp+68h] [rbp+17h]
  __int64 v19; // [rsp+70h] [rbp+1Fh]
  CddBitmapHw *v20; // [rsp+78h] [rbp+27h]
  int v21; // [rsp+80h] [rbp+2Fh]
  int v22; // [rsp+84h] [rbp+33h]
  int v23; // [rsp+88h] [rbp+37h]
  int v24; // [rsp+8Ch] [rbp+3Bh]
  int v25; // [rsp+90h] [rbp+3Fh]
  char v26; // [rsp+94h] [rbp+43h]

  v5 = *((_DWORD *)this + 10);
  if ( v5 )
  {
    v14[2] = a3;
    v14[1] = (char *)a2 + 36;
    v18 = *((_QWORD *)this + 1);
    v19 = *((_QWORD *)a2 + 3);
    v6 = *((_DWORD *)a2 + 4);
    v14[3] = a3;
    v7 = *(_QWORD *)a2;
    v21 = v6;
    v15 = 0;
    v26 = 0;
    v14[0] = a4;
    v20 = this;
    v22 = v5;
    v23 = 1;
    v24 = *(_DWORD *)(v7 + 64);
    v8 = *((_QWORD *)a2 + 7);
    v25 = 0;
    v14[5] = 0;
    if ( (*(_DWORD *)(v8 + 128) & 2) != 0 )
    {
      v9 = *((_QWORD *)a2 + 1);
      v15 = 1;
      v16 = *(_QWORD *)(v9 + 32);
      v17 = *(_DWORD *)(v7 + 64);
    }
    ClipDstRects(
      (struct CLIP_RECTS_DATA *)v14,
      (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmap::BitBltCallback);
    if ( *(_BYTE *)(*((_QWORD *)this + 1) + 2752LL) )
    {
      *(_BYTE *)(*((_QWORD *)this + 1) + 2752LL) = 0;
      v10 = (PRKEVENT *)*((_QWORD *)this + 1);
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 759;
        v13 = (_QWORD *)WdLogNewEntry5_WdAssertion(v12, v11);
        v13[3] = gCddImageInfo;
        v13[4] = (unsigned int)dword_14003E570;
        v13[5] = 215857758;
        WdLogGlobalForLineNumber = 759;
      }
      GetConnectedStandbyProcessName((struct CDDPDEV *)v10);
      KeSetEvent(v10[327], 0, 0);
    }
  }
}

```

## disassembly

```asm
0x140020af0  mov     [rsp-8+arg_0], rbx
0x140020af5  push    rbp
0x140020af6  lea     rbp, [rsp-4Fh]
0x140020afb  sub     rsp, 0A0h
0x140020b02  mov     rbx, rcx
0x140020b05  mov     ecx, [rcx+28h]
0x140020b08  test    ecx, ecx
0x140020b0a  jz      loc_140020C3E
0x140020b10  mov     [rbp+4Fh+var_70], r8
0x140020b14  lea     rax, [rdx+24h]
0x140020b18  mov     [rbp+4Fh+var_78], rax
0x140020b1c  mov     rax, [rbx+8]
0x140020b20  mov     [rbp+4Fh+var_38], rax
0x140020b24  mov     rax, [rdx+18h]
0x140020b28  mov     [rbp+4Fh+var_30], rax
0x140020b2c  mov     eax, [rdx+10h]
0x140020b2f  mov     [rbp+4Fh+var_68], r8
0x140020b33  mov     r8, [rdx]
0x140020b36  mov     [rbp+4Fh+var_20], eax
0x140020b39  mov     [rbp+4Fh+var_50], 0
0x140020b3d  mov     [rbp+4Fh+var_C], 0
0x140020b41  mov     [rbp+4Fh+var_80], r9
0x140020b45  mov     [rbp+4Fh+var_28], rbx
0x140020b49  mov     [rbp+4Fh+var_1C], ecx
0x140020b4c  mov     [rbp+4Fh+var_18], 1
0x140020b53  mov     eax, [r8+40h]
0x140020b57  mov     [rbp+4Fh+var_14], eax
0x140020b5a  mov     rax, [rdx+38h]
0x140020b5e  mov     [rbp+4Fh+var_10], 0
0x140020b65  mov     [rbp+4Fh+var_58], 0
0x140020b6d  mov     ecx, [rax+80h]
0x140020b73  test    cl, 2
0x140020b76  jz      short loc_140020B8F
0x140020b78  mov     rax, [rdx+8]
0x140020b7c  mov     [rbp+4Fh+var_50], 1
0x140020b80  mov     rcx, [rax+20h]
0x140020b84  mov     [rbp+4Fh+var_48], rcx
0x140020b88  mov     eax, [r8+40h]
0x140020b8c  mov     [rbp+4Fh+var_40], eax
0x140020b8f  lea     rdx, ?BitBltCallback@CddBitmap@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x140020b96  lea     rcx, [rbp+4Fh+var_80]; struct CLIP_RECTS_DATA *
0x140020b9a  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140020b9f  mov     rax, [rbx+8]
0x140020ba3  mov     dl, [rax+0AC0h]
0x140020ba9  test    dl, dl
0x140020bab  jz      loc_140020C3E
0x140020bb1  mov     rax, [rbx+8]
0x140020bb5  mov     byte ptr [rax+0AC0h], 0
0x140020bbc  mov     rbx, [rbx+8]
0x140020bc0  call    cs:__imp_KeGetCurrentIrql
0x140020bc7  nop     dword ptr [rax+rax+00h]
0x140020bcc  test    al, al
0x140020bce  jz      short loc_140020C1E
0x140020bd0  mov     ecx, 1
0x140020bd5  call    cs:__imp_WdLogSingleEntry0
0x140020bdc  nop     dword ptr [rax+rax+00h]
0x140020be1  mov     cs:WdLogGlobalForLineNumber, 2F7h
0x140020beb  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140020bf2  nop     dword ptr [rax+rax+00h]
0x140020bf7  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140020bfe  mov     [rax+18h], rdx
0x140020c02  mov     edx, cs:dword_14003E570
0x140020c08  mov     [rax+20h], rdx
0x140020c0c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140020c14  mov     cs:WdLogGlobalForLineNumber, 2F7h
0x140020c1e  mov     rcx, rbx; struct CDDPDEV *
0x140020c21  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x140020c26  mov     rcx, [rbx+0A38h]; Event
0x140020c2d  xor     r8d, r8d; Wait
0x140020c30  xor     edx, edx; Increment
0x140020c32  call    cs:__imp_KeSetEvent
0x140020c39  nop     dword ptr [rax+rax+00h]
0x140020c3e  mov     rbx, [rsp+0A0h+arg_0]
0x140020c46  add     rsp, 0A0h
0x140020c4d  pop     rbp
0x140020c4e  retn
```
