# ExtSTASetDesiredSSID(EXTSTA_VELAN *,void *,ulong)

- ea: `0x14006ddb0`
- end: `0x14006e07e`
- name: `?ExtSTASetDesiredSSID@@YAJPEAUEXTSTA_VELAN@@PEAXK@Z`
- size: `718`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x14000a81c`
- `0x140019bbc`
- `0x140020dc0`
- `0x14002f44c`
- `0x14002f6c0`
- `0x14006ddb0`
- `0x14009bcc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006de5e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14006de5e`
- `ntoskrnl!ExAllocatePool2` at `0x14006de71`
- `ntoskrnl!ExAllocatePool2` at `0x14006de71`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006e04d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006e04d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e05e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e05e`

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
    p_DeviceQueue = &stru_1400B31C0;
    goto LABEL_13;
  }
  Pool2 = (char *)ExAllocatePool2(64, v9, 808464432);
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
  if ( (byte_1400B2801 & 2) != 0 )
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
0x14006ddb0  push    rbp
0x14006ddb2  push    rbx
0x14006ddb3  push    rsi
0x14006ddb4  push    rdi
0x14006ddb5  push    r12
0x14006ddb7  push    r13
0x14006ddb9  push    r14
0x14006ddbb  push    r15
0x14006ddbd  mov     rbp, rsp
0x14006ddc0  sub     rsp, 48h
0x14006ddc4  mov     r15d, r8d
0x14006ddc7  mov     rax, 0E38E38E38E38E38Fh
0x14006ddd1  mov     r12, rdx
0x14006ddd4  xor     ebx, ebx
0x14006ddd6  mul     r15
0x14006ddd9  mov     r13, rcx
0x14006dddc  mov     rdi, rdx
0x14006dddf  shr     rdi, 5
0x14006dde3  lea     r9, [rdi+rdi*8]
0x14006dde7  shl     r9, 2
0x14006ddeb  cmp     r15, r9
0x14006ddee  jnz     loc_14006DFDA
0x14006ddf4  cmp     r8d, 24h ; '$'
0x14006ddf8  jb      loc_14006DFDA
0x14006ddfe  lea     esi, [r8+0Ch]
0x14006de02  cmp     esi, r8d
0x14006de05  jb      loc_14006DFDA
0x14006de0b  lea     eax, [rsi+10h]
0x14006de0e  cmp     eax, 10h
0x14006de11  jb      loc_14006DFD1
0x14006de17  lea     ecx, [rbx+40h]
0x14006de1a  mov     r14d, 30303030h
0x14006de20  cmp     eax, ecx
0x14006de22  ja      short loc_14006DE2D
0x14006de24  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14006de2b  jmp     short loc_14006DE5B
0x14006de2d  cmp     eax, 100h
0x14006de32  ja      short loc_14006DE3D
0x14006de34  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14006de3b  jmp     short loc_14006DE5B
0x14006de3d  cmp     eax, 400h
0x14006de42  ja      short loc_14006DE4D
0x14006de44  lea     rbx, Lookaside
0x14006de4b  jmp     short loc_14006DE5B
0x14006de4d  cmp     eax, 800h
0x14006de52  ja      short loc_14006DE6C
0x14006de54  lea     rbx, stru_1400B31C0
0x14006de5b  mov     rcx, rbx; Lookaside
0x14006de5e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14006de65  nop     dword ptr [rax+rax+00h]
0x14006de6a  jmp     short loc_14006DE7D
0x14006de6c  mov     edx, eax
0x14006de6e  mov     r8d, r14d
0x14006de71  call    cs:__imp_ExAllocatePool2
0x14006de78  nop     dword ptr [rax+rax+00h]
0x14006de7d  test    rax, rax
0x14006de80  jz      loc_14006DFD1
0x14006de86  mov     [rax], rbx
0x14006de89  mov     r8, r15; Size
0x14006de8c  lea     rbx, [rax+10h]
0x14006de90  mov     [rax+8], r14d
0x14006de94  mov     dword ptr [rbx], 300180h
0x14006de9a  lea     rcx, [rbx+0Ch]; void *
0x14006de9e  mov     [rbx+4], edi
0x14006dea1  mov     rdx, r12; Src
0x14006dea4  mov     [rbx+8], edi
0x14006dea7  call    memmove
0x14006deac  mov     rcx, [r13+0A38h]
0x14006deb3  mov     r9, rbx; void *
0x14006deb6  mov     edx, 1; unsigned int
0x14006debb  mov     [rsp+48h+var_28], esi; unsigned int
0x14006debf  mov     r8d, 0E01017Ch; unsigned int
0x14006dec5  mov     rcx, [rcx+10h]; struct _ADAPT *
0x14006dec9  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x14006dece  mov     edi, eax
0x14006ded0  test    eax, eax
0x14006ded2  js      loc_14006DFDF
0x14006ded8  mov     r9d, [rbx+8]
0x14006dedc  cmp     r9d, 1
0x14006dee0  jnz     short loc_14006DF36
0x14006dee2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dee9  lea     rsi, WPP_GLOBAL_Control
0x14006def0  cmp     rcx, rsi
0x14006def3  jz      loc_14006E036
0x14006def9  movzx   eax, word ptr [rbx+0Ch]
0x14006defd  lea     edx, [r9+26h]
0x14006df01  mov     rcx, [rcx+18h]
0x14006df05  lea     r9, [rbp+var_18]
0x14006df09  xorps   xmm0, xmm0
0x14006df0c  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006df13  movups  [rbp+var_18], xmm0
0x14006df17  mov     word ptr [rbp+var_18], ax
0x14006df1b  lea     rax, [rbx+10h]
0x14006df1f  mov     qword ptr [rbp+var_18+8], rax
0x14006df23  movaps  xmm0, [rbp+var_18]
0x14006df27  movdqa  [rbp+var_18], xmm0
0x14006df2c  call    WPP_SF__HEX_
0x14006df31  jmp     loc_14006E036
0x14006df36  mov     rcx, cs:WPP_GLOBAL_Control
0x14006df3d  lea     rsi, WPP_GLOBAL_Control
0x14006df44  cmp     rcx, rsi
0x14006df47  jz      loc_14006E036
0x14006df4d  mov     rcx, [rcx+18h]
0x14006df51  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006df58  mov     edx, 28h ; '('
0x14006df5d  call    WPP_SF_d
0x14006df62  xor     eax, eax
0x14006df64  cmp     [rbx+8], eax
0x14006df67  jbe     loc_14006E036
0x14006df6d  mov     rcx, cs:WPP_GLOBAL_Control
0x14006df74  lea     r14d, [rax+1]
0x14006df78  cmp     rcx, rsi
0x14006df7b  jz      short loc_14006DFC7
0x14006df7d  mov     rcx, [rcx+18h]
0x14006df81  lea     rdx, [rax+rax*8]
0x14006df85  movzx   eax, word ptr [rbx+rdx*4+0Ch]
0x14006df8a  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006df91  xorps   xmm0, xmm0
0x14006df94  mov     r9d, r14d
0x14006df97  movups  [rbp+var_18], xmm0
0x14006df9b  mov     word ptr [rbp+var_18], ax
0x14006df9f  lea     rax, [rdx+4]
0x14006dfa3  lea     rax, [rbx+rax*4]
0x14006dfa7  mov     edx, 29h ; ')'
0x14006dfac  mov     qword ptr [rbp+var_18+8], rax
0x14006dfb0  lea     rax, [rbp+var_18]
0x14006dfb4  movaps  xmm0, [rbp+var_18]
0x14006dfb8  movdqa  [rbp+var_18], xmm0
0x14006dfbd  mov     qword ptr [rsp+48h+var_28], rax
0x14006dfc2  call    WPP_SF_d_HEX_
0x14006dfc7  mov     eax, r14d
0x14006dfca  cmp     eax, [rbx+8]
0x14006dfcd  jb      short loc_14006DF6D
0x14006dfcf  jmp     short loc_14006E036
0x14006dfd1  xor     ebx, ebx
0x14006dfd3  mov     edi, 0C000009Ah
0x14006dfd8  jmp     short loc_14006DFDF
0x14006dfda  mov     edi, 0C000000Dh
0x14006dfdf  mov     rcx, cs:WPP_GLOBAL_Control
0x14006dfe6  lea     rsi, WPP_GLOBAL_Control
0x14006dfed  cmp     rcx, rsi
0x14006dff0  jz      short loc_14006E00A
0x14006dff2  mov     rcx, [rcx+18h]
0x14006dff6  lea     r8, WPP_8bbb67aeb05736c535ef605b0e082247_Traceguids
0x14006dffd  mov     edx, 2Ah ; '*'
0x14006e002  mov     r9d, edi
0x14006e005  call    WPP_SF_d
0x14006e00a  test    cs:byte_1400B2801, 2
0x14006e011  jz      short loc_14006E036
0x14006e013  mov     r9, [r13+0A38h]
0x14006e01a  lea     rdx, SetDesiredSSIDListError
0x14006e021  mov     [rsp+48h+var_20], edi
0x14006e025  lea     r8, [r9+1338h]
0x14006e02c  mov     qword ptr [rsp+48h+var_28], r8
0x14006e031  call    McTemplateK0pjq_EtwWriteTransfer
0x14006e036  test    rbx, rbx
0x14006e039  jz      short loc_14006E06A
0x14006e03b  lea     rcx, [rbx-10h]; P
0x14006e03f  mov     rax, [rcx]
0x14006e042  test    rax, rax
0x14006e045  jz      short loc_14006E05B
0x14006e047  mov     rdx, rcx; Entry
0x14006e04a  mov     rcx, rax; Lookaside
0x14006e04d  call    cs:__imp_ExFreeToNPagedLookasideList
0x14006e054  nop     dword ptr [rax+rax+00h]
0x14006e059  jmp     short loc_14006E06A
0x14006e05b  mov     edx, [rcx+8]; Tag
0x14006e05e  call    cs:__imp_ExFreePoolWithTag
0x14006e065  nop     dword ptr [rax+rax+00h]
0x14006e06a  mov     eax, edi
0x14006e06c  add     rsp, 48h
0x14006e070  pop     r15
0x14006e072  pop     r14
0x14006e074  pop     r13
0x14006e076  pop     r12
0x14006e078  pop     rdi
0x14006e079  pop     rsi
0x14006e07a  pop     rbx
0x14006e07b  pop     rbp
0x14006e07c  retn
```
