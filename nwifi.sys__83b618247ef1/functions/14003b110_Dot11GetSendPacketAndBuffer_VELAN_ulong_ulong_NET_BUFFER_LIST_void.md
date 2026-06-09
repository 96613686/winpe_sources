# Dot11GetSendPacketAndBuffer(_VELAN *,ulong,ulong,_NET_BUFFER_LIST * *,void * *)

- ea: `0x14003b110`
- end: `0x14003b317`
- name: `?Dot11GetSendPacketAndBuffer@@YAHPEAU_VELAN@@KKPEAPEAU_NET_BUFFER_LIST@@PEAPEAX@Z`
- size: `519`
- prototype: `__int64 __usercall@<rax>(struct _VELAN *@<rcx>, SIZE_T DataLength@<rdx>, unsigned int@<r8d>, struct _NET_BUFFER_LIST **@<r9>, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140034b18`
- `0x140042680`
- `0x1400686d4`
- `0x140068868`
- `0x140075fe0`

## callees

- `0x140016f88`
- `0x14003b110`
- `0x14003b320`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b28b`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14003b28b`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b1a0`
- `ntoskrnl!MmSizeOfMdl` at `0x14003b1a0`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b1fe`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b1fe`
- `ntoskrnl!ExAllocatePool2` at `0x14003b216`
- `ntoskrnl!ExAllocatePool2` at `0x14003b216`
- `NDIS!NdisAllocateNetBuffer` at `0x14003b2ae`
- `NDIS!NdisAllocateNetBuffer` at `0x14003b2ae`

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
  __int64 v14; // r9
  unsigned int v15; // ecx
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rbx
  char *Pool2; // rax
  struct _MDL *v18; // rbx
  __int64 uBackFillSize; // rsi
  char *MappedSystemVa; // rbp
  PNET_BUFFER NetBuffer; // rax
  struct _NET_BUFFER_LIST *v22; // r10
  _NET_BUFFER_LIST_CONTEXT *Context; // r8
  __int64 Offset; // rdx
  _QWORD *v25; // r9
  struct _NET_BUFFER_LIST *v26; // [rsp+88h] [rbp+20h] BYREF

  v5 = a5;
  v6 = (unsigned int)DataLength;
  v26 = 0;
  *a4 = 0;
  *v5 = 0;
  v10 = Dot11AllocateSendPacket(a1, &v26);
  if ( v10 )
    goto LABEL_4;
  _InterlockedIncrement((volatile signed __int32 *)&a1->OutstandingSends);
  v11 = v6 + a1->uBackFillSize;
  if ( v11 > 0x1F3B || (v13 = (MmSizeOfMdl((PVOID)0xFFF, v11) + 7) & 0xFFFFFFF8, v15 = v13 + v11 + 16, v15 < 0x10) )
  {
LABEL_3:
    v10 = -1073741670;
LABEL_4:
    Dot11GetSendPacketCompletion(v26, v10, a1, 0);
    return v10;
  }
  if ( v15 > 0x40 )
  {
    if ( v15 > 0x100 )
    {
      if ( v15 > 0x400 )
      {
        if ( v15 > 0x800 )
        {
          p_WaitListHead = 0;
          Pool2 = (char *)ExAllocatePool2(64, v15, a3, v14);
          goto LABEL_16;
        }
        p_WaitListHead = &stru_1400B0180;
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
  v18 = (struct _MDL *)(Pool2 + 16);
  *((_DWORD *)Pool2 + 2) = a3;
  if ( Pool2 != (char *)-16LL )
  {
    v18->Next = 0;
    *((_DWORD *)Pool2 + 14) = v11;
    *((_QWORD *)Pool2 + 6) = ((unsigned __int64)v18 + v13) & 0xFFFFFFFFFFFFF000uLL;
    *((_WORD *)Pool2 + 13) = 0;
    *((_WORD *)Pool2 + 12) = 8 * ((((((_DWORD)Pool2 + 16 + v13) & 0xFFFLL) + (unsigned __int64)v11 + 4095) >> 12) + 6);
    *((_DWORD *)Pool2 + 15) = ((_DWORD)Pool2 + 16 + v13) & 0xFFF;
    MmBuildMdlForNonPagedPool(v18);
  }
  uBackFillSize = a1->uBackFillSize;
  MappedSystemVa = (char *)v18->MappedSystemVa;
  NetBuffer = NdisAllocateNetBuffer(a1->hSendNetBufferPool, v18, a1->uBackFillSize, v6);
  if ( !NetBuffer )
    goto LABEL_3;
  v22 = v26;
  NetBuffer->Link.Alignment = 0;
  *a4 = v22;
  v22->Link.Region = (unsigned __int64)NetBuffer;
  Context = v22->Context;
  Offset = Context->Offset;
  v25 = *(_QWORD **)&Context->ContextData[Offset + 40];
  *(_QWORD *)&Context->ContextData[Offset + 40] = v25 + 3;
  *v25 = Dot11GetSendPacketCompletion;
  result = 0;
  *v5 = &MappedSystemVa[uBackFillSize];
  v25[1] = a1;
  v25[2] = 0;
  return result;
}

```

## disassembly

```asm
0x14003b110  mov     rax, rsp
0x14003b113  push    rbx
0x14003b114  push    rbp
0x14003b115  push    rsi
0x14003b116  push    rdi
0x14003b117  push    r12
0x14003b119  push    r13
0x14003b11b  push    r14
0x14003b11d  push    r15
0x14003b11f  sub     rsp, 28h
0x14003b123  mov     r13, [rsp+68h+arg_20]
0x14003b12b  xor     esi, esi
0x14003b12d  mov     r15d, edx
0x14003b130  mov     r12, r9
0x14003b133  lea     rdx, [rax+20h]; struct _NET_BUFFER_LIST **
0x14003b137  mov     [rax+20h], rsi
0x14003b13b  mov     r14d, r8d
0x14003b13e  mov     [r9], rsi
0x14003b141  mov     [r13+0], rsi
0x14003b145  mov     rdi, rcx
0x14003b148  call    ?Dot11AllocateSendPacket@@YAHPEAU_VELAN@@PEAPEAU_NET_BUFFER_LIST@@@Z; Dot11AllocateSendPacket(_VELAN *,_NET_BUFFER_LIST * *)
0x14003b14d  mov     ebx, eax
0x14003b14f  test    eax, eax
0x14003b151  jnz     short loc_14003B170
0x14003b153  lock inc dword ptr [rdi+1358h]
0x14003b15a  mov     ebp, [rdi+84h]
0x14003b160  add     ebp, r15d
0x14003b163  cmp     ebp, 1F3Bh
0x14003b169  jbe     short loc_14003B199
0x14003b16b  mov     ebx, 0C000009Ah
0x14003b170  mov     rcx, [rsp+68h+arg_18]; struct _NET_BUFFER_LIST *
0x14003b178  xor     r9d, r9d; void *
0x14003b17b  mov     r8, rdi; struct _VELAN *
0x14003b17e  mov     edx, ebx; int
0x14003b180  call    ?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z; Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)
0x14003b185  mov     eax, ebx
0x14003b187  add     rsp, 28h
0x14003b18b  pop     r15
0x14003b18d  pop     r14
0x14003b18f  pop     r13
0x14003b191  pop     r12
0x14003b193  pop     rdi
0x14003b194  pop     rsi
0x14003b195  pop     rbp
0x14003b196  pop     rbx
0x14003b197  retn
0x14003b199  mov     edx, ebp; Length
0x14003b19b  mov     ecx, 0FFFh; Base
0x14003b1a0  call    cs:__imp_MmSizeOfMdl
0x14003b1a7  nop     dword ptr [rax+rax+00h]
0x14003b1ac  lea     ecx, [rbp+10h]
0x14003b1af  lea     esi, [rax+7]
0x14003b1b2  and     esi, 0FFFFFFF8h
0x14003b1b5  add     ecx, esi
0x14003b1b7  cmp     ecx, 10h
0x14003b1ba  jb      short loc_14003B16B
0x14003b1bc  cmp     ecx, 40h ; '@'
0x14003b1bf  ja      short loc_14003B1CA
0x14003b1c1  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x14003b1c8  jmp     short loc_14003B1FB
0x14003b1ca  cmp     ecx, 100h
0x14003b1d0  ja      short loc_14003B1DB
0x14003b1d2  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14003b1d9  jmp     short loc_14003B1FB
0x14003b1db  cmp     ecx, 400h
0x14003b1e1  ja      short loc_14003B1EC
0x14003b1e3  lea     rbx, Lookaside
0x14003b1ea  jmp     short loc_14003B1FB
0x14003b1ec  cmp     ecx, 800h
0x14003b1f2  ja      short loc_14003B20C
0x14003b1f4  lea     rbx, stru_1400B0180
0x14003b1fb  mov     rcx, rbx; Lookaside
0x14003b1fe  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b205  nop     dword ptr [rax+rax+00h]
0x14003b20a  jmp     short loc_14003B222
0x14003b20c  xor     ebx, ebx
0x14003b20e  mov     edx, ecx
0x14003b210  mov     r8d, r14d
0x14003b213  lea     ecx, [rbx+40h]
0x14003b216  call    cs:__imp_ExAllocatePool2
0x14003b21d  nop     dword ptr [rax+rax+00h]
0x14003b222  test    rax, rax
0x14003b225  jz      loc_14003B16B
0x14003b22b  mov     [rax], rbx
0x14003b22e  lea     rbx, [rax+10h]
0x14003b232  mov     [rax+8], r14d
0x14003b236  xor     r14d, r14d
0x14003b239  test    rbx, rbx
0x14003b23c  jz      short loc_14003B297
0x14003b23e  mov     r9d, 0FFFh
0x14003b244  mov     edx, esi
0x14003b246  add     rdx, rbx
0x14003b249  mov     ecx, ebp
0x14003b24b  add     rcx, r9
0x14003b24e  mov     [rbx], r14
0x14003b251  mov     r8d, edx
0x14003b254  mov     [rbx+28h], ebp
0x14003b257  mov     eax, r8d
0x14003b25a  and     rdx, 0FFFFFFFFFFFFF000h
0x14003b261  and     rax, r9
0x14003b264  mov     [rbx+20h], rdx
0x14003b268  add     rcx, rax
0x14003b26b  and     r8d, r9d
0x14003b26e  shr     rcx, 0Ch
0x14003b272  xor     eax, eax
0x14003b274  add     cx, 6
0x14003b278  mov     [rbx+0Ah], ax
0x14003b27c  shl     cx, 3
0x14003b280  mov     [rbx+8], cx
0x14003b284  mov     rcx, rbx; MemoryDescriptorList
0x14003b287  mov     [rbx+2Ch], r8d
0x14003b28b  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003b292  nop     dword ptr [rax+rax+00h]
0x14003b297  mov     esi, [rdi+84h]
0x14003b29d  mov     r9, r15; DataLength
0x14003b2a0  mov     rcx, [rdi+38h]; PoolHandle
0x14003b2a4  mov     r8d, esi; DataOffset
0x14003b2a7  mov     rbp, [rbx+18h]
0x14003b2ab  mov     rdx, rbx; MdlChain
0x14003b2ae  call    cs:__imp_NdisAllocateNetBuffer
0x14003b2b5  nop     dword ptr [rax+rax+00h]
0x14003b2ba  test    rax, rax
0x14003b2bd  jz      loc_14003B16B
0x14003b2c3  mov     r10, [rsp+68h+arg_18]
0x14003b2cb  mov     qword ptr [rax], 0
0x14003b2d2  mov     [r12], r10
0x14003b2d6  mov     [r10+8], rax
0x14003b2da  lea     rax, ?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z; Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)
0x14003b2e1  mov     r8, [r10+10h]
0x14003b2e5  movzx   edx, word ptr [r8+0Ah]
0x14003b2ea  mov     r9, [rdx+r8+38h]
0x14003b2ef  lea     rcx, [r9+18h]
0x14003b2f3  mov     [rdx+r8+38h], rcx
0x14003b2f8  lea     rcx, [rsi+rbp]
0x14003b2fc  mov     [r9], rax
0x14003b2ff  mov     eax, r14d
0x14003b302  mov     [r13+0], rcx
0x14003b306  mov     [r9+8], rdi
0x14003b30a  mov     qword ptr [r9+10h], 0
0x14003b312  jmp     loc_14003B187
```
