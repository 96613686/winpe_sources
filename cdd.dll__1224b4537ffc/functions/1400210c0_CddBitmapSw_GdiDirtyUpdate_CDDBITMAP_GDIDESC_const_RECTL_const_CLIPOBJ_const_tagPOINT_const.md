# CddBitmapSw::GdiDirtyUpdate(CDDBITMAP_GDIDESC const *,_RECTL const *,_CLIPOBJ const *,tagPOINT const *)

- ea: `0x1400210c0`
- end: `0x140021293`
- name: `?GdiDirtyUpdate@CddBitmapSw@@UEAAXPEBUCDDBITMAP_GDIDESC@@PEBU_RECTL@@PEBU_CLIPOBJ@@PEBUtagPOINT@@@Z`
- size: `467`
- prototype: `void __fastcall(CddBitmapSw *__hidden this, const struct CDDBITMAP_GDIDESC *, const struct _RECTL *, const struct _CLIPOBJ *, const struct tagPOINT *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x14000cb44`
- `0x140010670`
- `0x1400210c0`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140021189`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140021189`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400211d9`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x1400211d9`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021206`
- `ntoskrnl!KeGetCurrentIrql` at `0x140021206`
- `ntoskrnl!KeSetEvent` at `0x140021275`
- `ntoskrnl!KeSetEvent` at `0x140021275`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021137`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021232`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021137`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140021232`
- `watchdog!WdLogSingleEntry0` at `0x140021120`
- `watchdog!WdLogSingleEntry0` at `0x14002121b`
- `watchdog!WdLogSingleEntry0` at `0x140021120`
- `watchdog!WdLogSingleEntry0` at `0x14002121b`

## pseudocode

```c
void __fastcall CddBitmapSw::GdiDirtyUpdate(
        PRKEVENT **this,
        const struct CDDBITMAP_GDIDESC *a2,
        const struct _RECTL *a3,
        const struct _CLIPOBJ *a4,
        const struct tagPOINT *a5)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  int v9; // eax
  PRKEVENT v10; // rdi
  struct _KEVENT *v11; // rcx
  PRKEVENT *v12; // rdx
  PRKEVENT v13; // rax
  PRKEVENT *v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rcx
  _QWORD *v17; // rax
  _QWORD v18[6]; // [rsp+20h] [rbp-68h] BYREF
  char v19; // [rsp+50h] [rbp-38h]
  __int64 v20; // [rsp+68h] [rbp-20h]
  CddBitmapSw *v21; // [rsp+70h] [rbp-18h]

  v19 = 0;
  v21 = (CddBitmapSw *)this;
  v20 = 0;
  v18[0] = a4;
  v18[1] = a3;
  v18[2] = a3;
  v18[3] = a3;
  v18[4] = 0;
  v18[5] = a5;
  if ( (int)ClipDstRects(
              (struct CLIP_RECTS_DATA *)v18,
              (int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *))CddBitmapSw::AddGDIDirtyRectsCallback) < 0 )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 792;
    v8 = (_QWORD *)WdLogNewEntry5_WdAssertion(v7, v6);
    v8[3] = gCddImageInfo;
    v8[4] = (unsigned int)dword_14003E570;
    v8[5] = 215857758;
    WdLogGlobalForLineNumber = 792;
  }
  v9 = *((_DWORD *)this + 32);
  *((_BYTE *)this + 568) = 1;
  if ( (v9 & 2) != 0 )
  {
    v10 = this[1][900];
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(v10);
    v11 = (struct _KEVENT *)(this + 109);
    *((_BYTE *)this[1] + 2753) = 1;
    if ( !this[109] )
    {
      v12 = (PRKEVENT *)this[1][902];
      v13 = *v12;
      if ( (PRKEVENT *)(*v12)->Header.WaitListHead.Flink != v12 )
        __fastfail(3u);
      *(_QWORD *)&v11->Header.Lock = v13;
      this[110] = v12;
      v13->Header.WaitListHead.Flink = (struct _LIST_ENTRY *)v11;
      *v12 = v11;
    }
    ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v10);
    if ( *((_BYTE *)this[1] + 2752) )
    {
      *((_BYTE *)this[1] + 2752) = 0;
      v14 = this[1];
      if ( KeGetCurrentIrql() )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 759;
        v17 = (_QWORD *)WdLogNewEntry5_WdAssertion(v16, v15);
        v17[3] = gCddImageInfo;
        v17[4] = (unsigned int)dword_14003E570;
        v17[5] = 215857758;
        WdLogGlobalForLineNumber = 759;
      }
      GetConnectedStandbyProcessName((struct CDDPDEV *)v14);
      KeSetEvent(v14[327], 0, 0);
    }
  }
}

```

## disassembly

```asm
0x1400210c0  mov     r11, rsp
0x1400210c3  mov     [r11+8], rbx
0x1400210c7  push    rdi
0x1400210c8  sub     rsp, 80h
0x1400210cf  mov     rax, [rsp+88h+arg_20]
0x1400210d7  lea     rdx, ?AddGDIDirtyRectsCallback@CddBitmapSw@@SAJPEAUCLIP_RECTS_DATA@@IPEBUtagRECT@@@Z; int (*)(struct CLIP_RECTS_DATA *, unsigned int, const struct tagRECT *)
0x1400210de  mov     [rsp+88h+var_38], 0
0x1400210e3  mov     rbx, rcx
0x1400210e6  mov     [r11-18h], rcx
0x1400210ea  lea     rcx, [r11-68h]; struct CLIP_RECTS_DATA *
0x1400210ee  mov     qword ptr [r11-20h], 0
0x1400210f6  mov     [r11-68h], r9
0x1400210fa  mov     [r11-60h], r8
0x1400210fe  mov     [r11-58h], r8
0x140021102  mov     [r11-50h], r8
0x140021106  mov     qword ptr [r11-48h], 0
0x14002110e  mov     [r11-40h], rax
0x140021112  call    ?ClipDstRects@@YAJPEAUCLIP_RECTS_DATA@@P6AJ0IPEBUtagRECT@@@Z@Z; ClipDstRects(CLIP_RECTS_DATA *,long (*)(CLIP_RECTS_DATA *,uint,tagRECT const *))
0x140021117  test    eax, eax
0x140021119  jns     short loc_140021166
0x14002111b  mov     ecx, 1
0x140021120  call    cs:__imp_WdLogSingleEntry0
0x140021127  nop     dword ptr [rax+rax+00h]
0x14002112c  mov     edi, 318h
0x140021131  mov     cs:WdLogGlobalForLineNumber, edi
0x140021137  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14002113e  nop     dword ptr [rax+rax+00h]
0x140021143  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14002114a  mov     [rax+18h], rcx
0x14002114e  mov     ecx, cs:dword_14003E570
0x140021154  mov     [rax+20h], rcx
0x140021158  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140021160  mov     cs:WdLogGlobalForLineNumber, edi
0x140021166  mov     eax, [rbx+80h]
0x14002116c  mov     byte ptr [rbx+238h], 1
0x140021173  test    al, 2
0x140021175  jz      loc_140021281
0x14002117b  mov     rax, [rbx+8]
0x14002117f  mov     rdi, [rax+1C20h]
0x140021186  mov     rcx, rdi
0x140021189  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x140021190  nop     dword ptr [rax+rax+00h]
0x140021195  mov     rax, [rbx+8]
0x140021199  lea     rcx, [rbx+368h]
0x1400211a0  mov     byte ptr [rax+0AC1h], 1
0x1400211a7  cmp     qword ptr [rcx], 0
0x1400211ab  jnz     short loc_1400211D6
0x1400211ad  mov     rax, [rbx+8]
0x1400211b1  mov     rdx, [rax+1C30h]
0x1400211b8  mov     rax, [rdx]
0x1400211bb  cmp     [rax+8], rdx
0x1400211bf  jz      short loc_1400211C8
0x1400211c1  mov     ecx, 3
0x1400211c6  int     29h; Win8: RtlFailFast(ecx)
0x1400211c8  mov     [rcx], rax
0x1400211cb  mov     [rcx+8], rdx
0x1400211cf  mov     [rax+8], rcx
0x1400211d3  mov     [rdx], rcx
0x1400211d6  mov     rcx, rdi
0x1400211d9  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x1400211e0  nop     dword ptr [rax+rax+00h]
0x1400211e5  mov     rax, [rbx+8]
0x1400211e9  mov     dl, [rax+0AC0h]
0x1400211ef  test    dl, dl
0x1400211f1  jz      loc_140021281
0x1400211f7  mov     rax, [rbx+8]
0x1400211fb  mov     byte ptr [rax+0AC0h], 0
0x140021202  mov     rbx, [rbx+8]
0x140021206  call    cs:__imp_KeGetCurrentIrql
0x14002120d  nop     dword ptr [rax+rax+00h]
0x140021212  test    al, al
0x140021214  jz      short loc_140021261
0x140021216  mov     ecx, 1
0x14002121b  call    cs:__imp_WdLogSingleEntry0
0x140021222  nop     dword ptr [rax+rax+00h]
0x140021227  mov     edi, 2F7h
0x14002122c  mov     cs:WdLogGlobalForLineNumber, edi
0x140021232  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140021239  nop     dword ptr [rax+rax+00h]
0x14002123e  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140021245  mov     [rax+18h], rdx
0x140021249  mov     edx, cs:dword_14003E570
0x14002124f  mov     [rax+20h], rdx
0x140021253  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14002125b  mov     cs:WdLogGlobalForLineNumber, edi
0x140021261  mov     rcx, rbx; struct CDDPDEV *
0x140021264  call    ?GetConnectedStandbyProcessName@@YAXPEAUCDDPDEV@@@Z; GetConnectedStandbyProcessName(CDDPDEV *)
0x140021269  mov     rcx, [rbx+0A38h]; Event
0x140021270  xor     r8d, r8d; Wait
0x140021273  xor     edx, edx; Increment
0x140021275  call    cs:__imp_KeSetEvent
0x14002127c  nop     dword ptr [rax+rax+00h]
0x140021281  mov     rbx, [rsp+88h+arg_0]
0x140021289  add     rsp, 80h
0x140021290  pop     rdi
0x140021291  retn
```
