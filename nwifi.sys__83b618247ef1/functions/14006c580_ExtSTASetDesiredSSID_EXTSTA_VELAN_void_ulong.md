# ExtSTASetDesiredSSID(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006c580`
- end: `0x14006c84e`
- name: `?ExtSTASetDesiredSSID@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `718`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000a82c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14002f1bc`
- `0x14002f430`
- `0x14006c580`
- `0x14009a4c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c62e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006c62e`
- `ntoskrnl!ExAllocatePool2` at `0x14006c641`
- `ntoskrnl!ExAllocatePool2` at `0x14006c641`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c81d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006c81d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c82e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c82e`

## pseudocode

```c
__int64 __fastcall ExtSTASetDesiredSSID(struct EXTSTA_VELAN *a1, void *a2, unsigned int a3)
{
  size_t v3; // r15
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  unsigned int v9; // eax
  char *Pool2; // rax
  int v11; // edi
  __int64 v12; // r9
  _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v14; // rax
  unsigned int v15; // r14d
  _DEVICE_OBJECT *v16; // rcx
  int v17; // ecx
  __int64 v19; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *p_Depth; // [rsp+38h] [rbp-10h]

  v3 = a3;
  p_DeviceQueue = 0;
  v7 = a3 / 0x24uLL;
  if ( a3 != 36 * v7 || a3 < 0x24 || (v8 = a3 + 12, a3 + 12 < a3) )
  {
    v11 = -1073741811;
    goto LABEL_28;
  }
  v9 = a3 + 28;
  if ( v8 >= 0xFFFFFFF0 )
    goto LABEL_26;
  if ( v9 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_13:
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_15;
  }
  if ( v9 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_13;
  }
  if ( v9 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_13;
  }
  if ( v9 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_13;
  }
  Pool2 = (char *)ExAllocatePool2(64, v9, 808464432, 36 * v7);
LABEL_15:
  if ( !Pool2 )
  {
LABEL_26:
    p_DeviceQueue = 0;
    v11 = -1073741670;
    goto LABEL_28;
  }
  *(_QWORD *)Pool2 = p_DeviceQueue;
  p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = 808464432;
  *((_DWORD *)Pool2 + 4) = 3146112;
  *((_DWORD *)Pool2 + 5) = v7;
  *((_DWORD *)Pool2 + 6) = v7;
  memmove(Pool2 + 28, a2, v3);
  v11 = PtRequestAdapterSync(a1->pGenVElan->pAdapt, 1u, 0xE01017Cu, p_DeviceQueue, v8);
  if ( v11 >= 0 )
  {
    v12 = *((unsigned int *)&p_DeviceQueue->L.SingleListHead + 2);
    if ( (_DWORD)v12 == 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
        v19 = *((unsigned __int16 *)&p_DeviceQueue->L.SingleListHead + 6);
        p_Depth = &p_DeviceQueue->L.Depth;
        WPP_SF__HEX_(AttachedDevice, 39, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, &v19);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, v12);
      v14 = 0;
      if ( *((_DWORD *)&p_DeviceQueue->L.SingleListHead + 2) )
      {
        do
        {
          v15 = v14 + 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            v16 = WPP_GLOBAL_Control->AttachedDevice;
            v19 = *((unsigned __int16 *)&p_DeviceQueue->L.SingleListHead + 18 * v14 + 6);
            p_Depth = &p_DeviceQueue->L.Depth + 18 * v14;
            WPP_SF_d_HEX_(
              (_DWORD)v16,
              41,
              (unsigned int)WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids,
              v15,
              (__int64)&v19);
          }
          v14 = v15;
        }
        while ( v15 < *((_DWORD *)&p_DeviceQueue->L.SingleListHead + 2) );
      }
    }
    goto LABEL_32;
  }
LABEL_28:
  v17 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids, (unsigned int)v11);
  if ( (byte_1400AF801 & 2) != 0 )
    McTemplateK0pjq_EtwWriteTransfer(
      v17,
      (unsigned int)SetDesiredSSIDListError,
      &a1->pGenVElan->gDeviceId,
      a1->pGenVElan,
      (__int64)&a1->pGenVElan->gDeviceId,
      v11);
LABEL_32:
  if ( p_DeviceQueue )
  {
    if ( *(_QWORD *)&p_DeviceQueue[-1].L.Future[6] )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)&p_DeviceQueue[-1].L.Future[6],
        &p_DeviceQueue[-1].L.Future[6]);
    else
      ExFreePoolWithTag(&p_DeviceQueue[-1].L.Future[6], p_DeviceQueue[-1].L.Future[8]);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14006c580  push    rbp
0x14006c582  push    rbx
0x14006c583  push    rsi
0x14006c584  push    rdi
0x14006c585  push    r12
0x14006c587  push    r13
0x14006c589  push    r14
0x14006c58b  push    r15
0x14006c58d  mov     rbp, rsp
0x14006c590  sub     rsp, 48h
0x14006c594  mov     r15d, r8d
0x14006c597  mov     rax, 0E38E38E38E38E38Fh
0x14006c5a1  mov     r12, rdx
0x14006c5a4  xor     ebx, ebx
0x14006c5a6  mul     r15
0x14006c5a9  mov     r13, rcx
0x14006c5ac  mov     rdi, rdx
0x14006c5af  shr     rdi, 5
0x14006c5b3  lea     r9, [rdi+rdi*8]
0x14006c5b7  shl     r9, 2
0x14006c5bb  cmp     r15, r9
0x14006c5be  jnz     loc_14006C7AA
0x14006c5c4  cmp     r8d, 24h ; '$'
0x14006c5c8  jb      loc_14006C7AA
0x14006c5ce  lea     esi, [r8+0Ch]
0x14006c5d2  cmp     esi, r8d
0x14006c5d5  jb      loc_14006C7AA
0x14006c5db  lea     eax, [rsi+10h]
0x14006c5de  cmp     eax, 10h
0x14006c5e1  jb      loc_14006C7A1
0x14006c5e7  lea     ecx, [rbx+40h]
0x14006c5ea  mov     r14d, 30303030h
0x14006c5f0  cmp     eax, ecx
0x14006c5f2  ja      short loc_14006C5FD
0x14006c5f4  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006c5fb  jmp     short loc_14006C62B
0x14006c5fd  cmp     eax, 100h
0x14006c602  ja      short loc_14006C60D
0x14006c604  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006c60b  jmp     short loc_14006C62B
0x14006c60d  cmp     eax, 400h
0x14006c612  ja      short loc_14006C61D
0x14006c614  lea     rbx, Lookaside
0x14006c61b  jmp     short loc_14006C62B
0x14006c61d  cmp     eax, 800h
0x14006c622  ja      short loc_14006C63C
0x14006c624  lea     rbx, stru_1400B0180
0x14006c62b  mov     rcx, rbx; Lookaside
0x14006c62e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006c635  nop     dword ptr [rax+rax+00h]
0x14006c63a  jmp     short loc_14006C64D
0x14006c63c  mov     edx, eax
0x14006c63e  mov     r8d, r14d
0x14006c641  call    cs:__imp_ExAllocatePool2
0x14006c648  nop     dword ptr [rax+rax+00h]
0x14006c64d  test    rax, rax
0x14006c650  jz      loc_14006C7A1
0x14006c656  mov     [rax], rbx
0x14006c659  mov     r8, r15; Size
0x14006c65c  lea     rbx, [rax+10h]
0x14006c660  mov     [rax+8], r14d
0x14006c664  mov     dword ptr [rbx], 300180h
0x14006c66a  lea     rcx, [rbx+0Ch]; void *
0x14006c66e  mov     [rbx+4], edi
0x14006c671  mov     rdx, r12; Src
0x14006c674  mov     [rbx+8], edi
0x14006c677  call    memmove
0x14006c67c  mov     rcx, [r13+0A38h]
0x14006c683  mov     r9, rbx; void *
0x14006c686  mov     edx, 1; unsigned int
0x14006c68b  mov     [rsp+48h+var_28], esi; unsigned int
0x14006c68f  mov     r8d, 0E01017Ch; unsigned int
0x14006c695  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006c699  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006c69e  mov     edi, eax
0x14006c6a0  test    eax, eax
0x14006c6a2  js      loc_14006C7AF
0x14006c6a8  mov     r9d, [rbx+8]
0x14006c6ac  cmp     r9d, 1
0x14006c6b0  jnz     short loc_14006C706
0x14006c6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c6b9  lea     rsi, WPP_GLOBAL_Control
0x14006c6c0  cmp     rcx, rsi
0x14006c6c3  jz      loc_14006C806
0x14006c6c9  movzx   eax, word ptr [rbx+0Ch]
0x14006c6cd  lea     edx, [r9+26h]
0x14006c6d1  mov     rcx, [rcx+18h]
0x14006c6d5  lea     r9, [rbp+var_18]
0x14006c6d9  xorps   xmm0, xmm0
0x14006c6dc  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c6e3  movups  [rbp+var_18], xmm0
0x14006c6e7  mov     word ptr [rbp+var_18], ax
0x14006c6eb  lea     rax, [rbx+10h]
0x14006c6ef  mov     qword ptr [rbp+var_18+8], rax
0x14006c6f3  movaps  xmm0, [rbp+var_18]
0x14006c6f7  movdqa  [rbp+var_18], xmm0
0x14006c6fc  call    WPP_SF__HEX_
0x14006c701  jmp     loc_14006C806
0x14006c706  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c70d  lea     rsi, WPP_GLOBAL_Control
0x14006c714  cmp     rcx, rsi
0x14006c717  jz      loc_14006C806
0x14006c71d  mov     rcx, [rcx+18h]
0x14006c721  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c728  mov     edx, 28h ; '('
0x14006c72d  call    WPP_SF_d
0x14006c732  xor     eax, eax
0x14006c734  cmp     [rbx+8], eax
0x14006c737  jbe     loc_14006C806
0x14006c73d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c744  lea     r14d, [rax+1]
0x14006c748  cmp     rcx, rsi
0x14006c74b  jz      short loc_14006C797
0x14006c74d  mov     rcx, [rcx+18h]
0x14006c751  lea     rdx, [rax+rax*8]
0x14006c755  movzx   eax, word ptr [rbx+rdx*4+0Ch]
0x14006c75a  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c761  xorps   xmm0, xmm0
0x14006c764  mov     r9d, r14d
0x14006c767  movups  [rbp+var_18], xmm0
0x14006c76b  mov     word ptr [rbp+var_18], ax
0x14006c76f  lea     rax, [rdx+4]
0x14006c773  lea     rax, [rbx+rax*4]
0x14006c777  mov     edx, 29h ; ')'
0x14006c77c  mov     qword ptr [rbp+var_18+8], rax
0x14006c780  lea     rax, [rbp+var_18]
0x14006c784  movaps  xmm0, [rbp+var_18]
0x14006c788  movdqa  [rbp+var_18], xmm0
0x14006c78d  mov     qword ptr [rsp+48h+var_28], rax
0x14006c792  call    WPP_SF_d_HEX_
0x14006c797  mov     eax, r14d
0x14006c79a  cmp     eax, [rbx+8]
0x14006c79d  jb      short loc_14006C73D
0x14006c79f  jmp     short loc_14006C806
0x14006c7a1  xor     ebx, ebx
0x14006c7a3  mov     edi, 0C000009Ah
0x14006c7a8  jmp     short loc_14006C7AF
0x14006c7aa  mov     edi, 0C000000Dh
0x14006c7af  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c7b6  lea     rsi, WPP_GLOBAL_Control
0x14006c7bd  cmp     rcx, rsi
0x14006c7c0  jz      short loc_14006C7DA
0x14006c7c2  mov     rcx, [rcx+18h]
0x14006c7c6  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006c7cd  mov     edx, 2Ah ; '*'
0x14006c7d2  mov     r9d, edi
0x14006c7d5  call    WPP_SF_d
0x14006c7da  test    cs:byte_1400AF801, 2
0x14006c7e1  jz      short loc_14006C806
0x14006c7e3  mov     r9, [r13+0A38h]
0x14006c7ea  lea     rdx, SetDesiredSSIDListError
0x14006c7f1  mov     [rsp+48h+var_20], edi
0x14006c7f5  lea     r8, [r9+1338h]
0x14006c7fc  mov     qword ptr [rsp+48h+var_28], r8
0x14006c801  call    McTemplateK0pjq_EtwWriteTransfer
0x14006c806  test    rbx, rbx
0x14006c809  jz      short loc_14006C83A
0x14006c80b  lea     rcx, [rbx-10h]; P
0x14006c80f  mov     rax, [rcx]
0x14006c812  test    rax, rax
0x14006c815  jz      short loc_14006C82B
0x14006c817  mov     rdx, rcx; Entry
0x14006c81a  mov     rcx, rax; Lookaside
0x14006c81d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006c824  nop     dword ptr [rax+rax+00h]
0x14006c829  jmp     short loc_14006C83A
0x14006c82b  mov     edx, [rcx+8]; Tag
0x14006c82e  call    cs:__imp_ExFreePoolWithTag
0x14006c835  nop     dword ptr [rax+rax+00h]
0x14006c83a  mov     eax, edi
0x14006c83c  add     rsp, 48h
0x14006c840  pop     r15
0x14006c842  pop     r14
0x14006c844  pop     r13
0x14006c846  pop     r12
0x14006c848  pop     rdi
0x14006c849  pop     rsi
0x14006c84a  pop     rbx
0x14006c84b  pop     rbp
0x14006c84c  retn
```
