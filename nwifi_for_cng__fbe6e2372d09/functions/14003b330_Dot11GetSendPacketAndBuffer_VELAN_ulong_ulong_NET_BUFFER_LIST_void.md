# Dot11GetSendPacketAndBuffer(_VELAN *,ulong,ulong,_NET_BUFFER_LIST * *,void * *)

- ea: `0x14003b330`
- end: `0x14003b537`
- name: `?Dot11GetSendPacketAndBuffer@@YAHPEAU_VELAN@@KKPEAPEAU_NET_BUFFER_LIST@@PEAPEAX@Z`
- size: `519`
- prototype: `__int64 __usercall@<rax>(struct _VELAN *@<rcx>, SIZE_T DataLength@<rdx>, unsigned int@<r8d>, struct _NET_BUFFER_LIST **@<r9>, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140034d38`
- `0x140043200`
- `0x140069f04`
- `0x14006a098`
- `0x140077810`

## callees

- `0x140016f88`
- `0x14003b330`
- `0x14003b540`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b4ab`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b4ab`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b3c0`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b3c0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b41e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b41e`
- `ntoskrnl!ExAllocatePool2` at `0x14003b436`
- `ntoskrnl!ExAllocatePool2` at `0x14003b436`
- `NDIS!NdisAllocateNetBuffer` at `0x14003b4ce`
- `NDIS!NdisAllocateNetBuffer` at `0x14003b4ce`

## pseudocode

```c
__int64 __fastcall Dot11GetSendPacketAndBuffer(
        struct _VELAN *a1,
        SIZE_T DataLength,
        unsigned int a3,
        struct _NET_BUFFER_LIST **a4,
        void **a5)
{
  void **v5; // r13
  SIZE_T v6; // r15
  unsigned int v10; // ebx
  unsigned int v11; // ebp
  __int64 result; // rax
  unsigned int v13; // esi
  unsigned int v14; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  struct _MDL *v17; // rbx
  __int64 uBackFillSize; // rsi
  char *MappedSystemVa; // rbp
  PNET_BUFFER NetBuffer; // rax
  struct _NET_BUFFER_LIST *v21; // r10
  _NET_BUFFER_LIST_CONTEXT *Context; // r8
  __int64 Offset; // rdx
  _QWORD *v24; // r9
  struct _NET_BUFFER_LIST *v25; // [rsp+88h] [rbp+20h] BYREF

  v5 = a5;
  v6 = (unsigned int)DataLength;
  v25 = 0;
  *a4 = 0;
  *v5 = 0;
  v10 = Dot11AllocateSendPacket(a1, &v25);
  if ( v10 )
    goto LABEL_4;
  _InterlockedIncrement((volatile signed __int32 *)&a1->OutstandingSends);
  v11 = v6 + a1->uBackFillSize;
  if ( v11 > 0x1F3B || (v13 = (MmSizeOfMdl((PVOID)0xFFF, v11) + 7) & 0xFFFFFFF8, v14 = v13 + v11 + 16, v14 < 0x10) )
  {
LABEL_3:
    v10 = -1073741670;
LABEL_4:
    Dot11GetSendPacketCompletion(v25, v10, a1, 0);
    return v10;
  }
  if ( v14 > 0x40 )
  {
    if ( v14 > 0x100 )
    {
      if ( v14 > 0x400 )
      {
        if ( v14 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v14, a3);
          goto LABEL_16;
        }
        p_WaitListHead = &stru_1400B31C0;
      }
      else
      {
        p_WaitListHead = &Lookaside;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    }
  }
  else
  {
    p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
  }
  Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
LABEL_16:
  if ( !Pool2 )
    goto LABEL_3;
  *(_QWORD *)Pool2 = p_WaitListHead;
  v17 = (struct _MDL *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = a3;
  if ( Pool2 != (char *)-16LL )
  {
    v17->Next = 0;
    *((_DWORD *)Pool2 + 14) = v11;
    *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v17 + v13) & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)Pool2 + 13) = 0;
    *((_WORD *)Pool2 + 12) = 8 * ((((((_DWORD)Pool2 + 16 + v13) & 0xFFFLL) + (unsigned __int64)v11 + 4095) >> 12) + 6);
    *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v13) & 0xFFF;
    MmBuildMdlForNonPagedPool(v17);
  }
  uBackFillSize = a1->uBackFillSize;
  MappedSystemVa = (char *)v17->MappedSystemVa;
  NetBuffer = NdisAllocateNetBuffer(a1->hSendNetBufferPool, v17, a1->uBackFillSize, v6);
  if ( !NetBuffer )
    goto LABEL_3;
  v21 = v25;
  NetBuffer->Link.Alignment = 0;
  *a4 = v21;
  v21->Link.Region = (unsigned __int64)NetBuffer;
  Context = v21->Context;
  Offset = Context->Offset;
  v24 = *(_QWORD **)&Context->ContextData[Offset + 40];
  *(_QWORD *)&Context->ContextData[Offset + 40] = v24 + 3;
  *v24 = Dot11GetSendPacketCompletion;
  result = 0;
  *v5 = &MappedSystemVa[uBackFillSize];
  v24[1] = a1;
  v24[2] = 0;
  return result;
}

```

## disassembly

```asm
0x14003b330  mov     rax, rsp
0x14003b333  push    rbx
0x14003b334  push    rbp
0x14003b335  push    rsi
0x14003b336  push    rdi
0x14003b337  push    r12
0x14003b339  push    r13
0x14003b33b  push    r14
0x14003b33d  push    r15
0x14003b33f  sub     rsp, 28h
0x14003b343  mov     r13, [rsp+68h+arg_20]
0x14003b34b  xor     esi, esi
0x14003b34d  mov     r15d, edx
0x14003b350  mov     r12, r9
0x14003b353  lea     rdx, [rax+20h]; struct _NET_BUFFER_LIST **
0x14003b357  mov     [rax+20h], rsi
0x14003b35b  mov     r14d, r8d
0x14003b35e  mov     [r9], rsi
0x14003b361  mov     [r13+0], rsi
0x14003b365  mov     rdi, rcx
0x14003b368  call    ?Dot11AllocateSendPacket@@YAHPEAU_VELAN@@PEAPEAU_NET_BUFFER_LIST@@@Z; Dot11AllocateSendPacket(_VELAN *,_NET_BUFFER_LIST * *)
0x14003b36d  mov     ebx, eax
0x14003b36f  test    eax, eax
0x14003b371  jnz     short loc_14003B390
0x14003b373  lock inc dword ptr [rdi+1358h]
0x14003b37a  mov     ebp, [rdi+84h]
0x14003b380  add     ebp, r15d
0x14003b383  cmp     ebp, 1F3Bh
0x14003b389  jbe     short loc_14003B3B9
0x14003b38b  mov     ebx, 0C000009Ah
0x14003b390  mov     rcx, [rsp+68h+arg_18]; struct _NET_BUFFER_LIST *
0x14003b398  xor     r9d, r9d; void *
0x14003b39b  mov     r8, rdi; struct _VELAN *
0x14003b39e  mov     edx, ebx; int
0x14003b3a0  call    ?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z; Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)
0x14003b3a5  mov     eax, ebx
0x14003b3a7  add     rsp, 28h
0x14003b3ab  pop     r15
0x14003b3ad  pop     r14
0x14003b3af  pop     r13
0x14003b3b1  pop     r12
0x14003b3b3  pop     rdi
0x14003b3b4  pop     rsi
0x14003b3b5  pop     rbp
0x14003b3b6  pop     rbx
0x14003b3b7  retn
0x14003b3b9  mov     edx, ebp; Length
0x14003b3bb  mov     ecx, 0FFFh; Base
0x14003b3c0  call    cs:__imp_MmSizeOfMdl
0x14003b3c7  nop     dword ptr [rax+rax+00h]
0x14003b3cc  lea     ecx, [rbp+10h]
0x14003b3cf  lea     esi, [rax+7]
0x14003b3d2  and     esi, 0FFFFFFF8h
0x14003b3d5  add     ecx, esi
0x14003b3d7  cmp     ecx, 10h
0x14003b3da  jb      short loc_14003B38B
0x14003b3dc  cmp     ecx, 40h ; '@'
0x14003b3df  ja      short loc_14003B3EA
0x14003b3e1  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14003b3e8  jmp     short loc_14003B41B
0x14003b3ea  cmp     ecx, 100h
0x14003b3f0  ja      short loc_14003B3FB
0x14003b3f2  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003b3f9  jmp     short loc_14003B41B
0x14003b3fb  cmp     ecx, 400h
0x14003b401  ja      short loc_14003B40C
0x14003b403  lea     rbx, Lookaside
0x14003b40a  jmp     short loc_14003B41B
0x14003b40c  cmp     ecx, 800h
0x14003b412  ja      short loc_14003B42C
0x14003b414  lea     rbx, stru_1400B31C0
0x14003b41b  mov     rcx, rbx; Lookaside
0x14003b41e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b425  nop     dword ptr [rax+rax+00h]
0x14003b42a  jmp     short loc_14003B442
0x14003b42c  xor     ebx, ebx
0x14003b42e  mov     edx, ecx
0x14003b430  mov     r8d, r14d
0x14003b433  lea     ecx, [rbx+40h]
0x14003b436  call    cs:__imp_ExAllocatePool2
0x14003b43d  nop     dword ptr [rax+rax+00h]
0x14003b442  test    rax, rax
0x14003b445  jz      loc_14003B38B
0x14003b44b  mov     [rax], rbx
0x14003b44e  lea     rbx, [rax+10h]
0x14003b452  mov     [rax+8], r14d
0x14003b456  xor     r14d, r14d
0x14003b459  test    rbx, rbx
0x14003b45c  jz      short loc_14003B4B7
0x14003b45e  mov     r9d, 0FFFh
0x14003b464  mov     edx, esi
0x14003b466  add     rdx, rbx
0x14003b469  mov     ecx, ebp
0x14003b46b  add     rcx, r9
0x14003b46e  mov     [rbx], r14
0x14003b471  mov     r8d, edx
0x14003b474  mov     [rbx+28h], ebp
0x14003b477  mov     eax, r8d
0x14003b47a  and     rdx, 0FFFFFFFFFFFFF000h
0x14003b481  and     rax, r9
0x14003b484  mov     [rbx+20h], rdx
0x14003b488  add     rcx, rax
0x14003b48b  and     r8d, r9d
0x14003b48e  shr     rcx, 0Ch
0x14003b492  xor     eax, eax
0x14003b494  add     cx, 6
0x14003b498  mov     [rbx+0Ah], ax
0x14003b49c  shl     cx, 3
0x14003b4a0  mov     [rbx+8], cx
0x14003b4a4  mov     rcx, rbx; MemoryDescriptorList
0x14003b4a7  mov     [rbx+2Ch], r8d
0x14003b4ab  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003b4b2  nop     dword ptr [rax+rax+00h]
0x14003b4b7  mov     esi, [rdi+84h]
0x14003b4bd  mov     r9, r15; DataLength
0x14003b4c0  mov     rcx, [rdi+38h]; PoolHandle
0x14003b4c4  mov     r8d, esi; DataOffset
0x14003b4c7  mov     rbp, [rbx+18h]
0x14003b4cb  mov     rdx, rbx; MdlChain
0x14003b4ce  call    cs:__imp_NdisAllocateNetBuffer
0x14003b4d5  nop     dword ptr [rax+rax+00h]
0x14003b4da  test    rax, rax
0x14003b4dd  jz      loc_14003B38B
0x14003b4e3  mov     r10, [rsp+68h+arg_18]
0x14003b4eb  mov     qword ptr [rax], 0
0x14003b4f2  mov     [r12], r10
0x14003b4f6  mov     [r10+8], rax
0x14003b4fa  lea     rax, ?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z; Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)
0x14003b501  mov     r8, [r10+10h]
0x14003b505  movzx   edx, word ptr [r8+0Ah]
0x14003b50a  mov     r9, [rdx+r8+38h]
0x14003b50f  lea     rcx, [r9+18h]
0x14003b513  mov     [rdx+r8+38h], rcx
0x14003b518  lea     rcx, [rsi+rbp]
0x14003b51c  mov     [r9], rax
0x14003b51f  mov     eax, r14d
0x14003b522  mov     [r13+0], rcx
0x14003b526  mov     [r9+8], rdi
0x14003b52a  mov     qword ptr [r9+10h], 0
0x14003b532  jmp     loc_14003B3A7
```
