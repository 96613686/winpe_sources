# RxAllocateFcbObject

- ea: `0x14005c6c0`
- end: `0x14005cada`
- name: `RxAllocateFcbObject`
- size: `1050`
- prototype: `PVOID __stdcall(PRDBSS_DEVICE_OBJECT RxDeviceObject, NODE_TYPE_CODE NodeType, POOL_TYPE PoolType, ULONG NameSize, PVOID AlreadyAllocatedObject)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140052bb0`
- `0x140054ca0`
- `0x14005be90`
- `0x14005cae0`
- `0x14005d6d0`

## callees

- `0x140026080`
- `0x14005c6c0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005c79b`
- `ntoskrnl!ExAllocatePool2` at `0x14005c84c`
- `ntoskrnl!ExAllocatePool2` at `0x14005c883`
- `ntoskrnl!ExAllocatePool2` at `0x14005c79b`
- `ntoskrnl!ExAllocatePool2` at `0x14005c84c`
- `ntoskrnl!ExAllocatePool2` at `0x14005c883`
- `ntoskrnl!KeInitializeEvent` at `0x14005c934`
- `ntoskrnl!KeInitializeEvent` at `0x14005c9c8`
- `ntoskrnl!KeInitializeEvent` at `0x14005c934`
- `ntoskrnl!KeInitializeEvent` at `0x14005c9c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c8b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c8a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c8b3`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14005ca1a`
- `ntoskrnl!FsRtlInitializeOplock` at `0x14005ca1a`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
PVOID __stdcall RxAllocateFcbObject(
        PRDBSS_DEVICE_OBJECT RxDeviceObject,
        NODE_TYPE_CODE NodeType,
        POOL_TYPE PoolType,
        ULONG NameSize,
        PVOID AlreadyAllocatedObject)
{
  __int64 v5; // rbx
  __int64 v6; // rsi
  int v7; // ebp
  unsigned int v9; // r8d
  unsigned int v10; // r9d
  unsigned int v11; // r13d
  __int64 v12; // rdx
  __int64 v13; // rax
  _WORD *Pool2; // r14
  _WORD *v15; // r15
  struct _KEVENT *v16; // r15
  char *v17; // r12
  __int64 v18; // rax
  char v20; // al
  _WORD *v21; // rdi
  __int16 v22; // bx
  __int16 v23; // bx
  int v24; // [rsp+20h] [rbp-48h]
  unsigned int v25; // [rsp+28h] [rbp-40h]
  _WORD *v26; // [rsp+28h] [rbp-40h]
  __int64 v27; // [rsp+30h] [rbp-38h]
  _WORD *v28; // [rsp+30h] [rbp-38h]
  unsigned int v29; // [rsp+88h] [rbp+20h]

  v5 = NameSize;
  v6 = *(_QWORD *)&PoolType;
  v7 = NodeType;
  if ( NameSize > 0xFFFF )
    return 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v25 = 0;
  v24 = 0;
  if ( NodeType == 60188 || NodeType == 60189 )
  {
LABEL_7:
    v10 = 248;
    v24 = 124;
    goto LABEL_8;
  }
  if ( NodeType != 60464 )
  {
    v11 = 376;
    v12 = v6 & 0x40;
    v27 = v12;
    v9 = v12 != 0 ? 0x150 : 0;
    v25 = v9;
    if ( (_WORD)v7 == 0xEC24 )
    {
      v13 = 0;
      goto LABEL_9;
    }
    goto LABEL_7;
  }
LABEL_8:
  v13 = 312;
  v12 = v6 & 0x40;
  v27 = v12;
LABEL_9:
  Pool2 = AlreadyAllocatedObject;
  v29 = v13;
  if ( AlreadyAllocatedObject )
    goto LABEL_12;
  Pool2 = (_WORD *)ExAllocatePool2(v6, (unsigned int)v5 + v11 * 2 + v9 + v10 + (_DWORD)v13 + 2LL, 1665562706);
  if ( !Pool2 )
    return 0;
  v12 = v27;
  v9 = v25;
  v10 = v24 * 2;
  v13 = v29;
LABEL_12:
  v15 = 0;
  v26 = 0;
  if ( v7 == 60188 )
  {
    v21 = Pool2;
    v15 = (_WORD *)((char *)Pool2 + v10);
LABEL_33:
    if ( v21 )
    {
      v22 = v10;
      memset(v21, 0, (unsigned __int16)v10);
      v21[1] = v22;
      *v21 = -5348;
      if ( (_WORD)v7 == 0xEB1C )
      {
        v13 = (__int64)v15;
      }
      else
      {
        *((_DWORD *)v21 + 18) |= 0x20000u;
        v13 = 0;
      }
      *((_QWORD *)v21 + 25) = v13;
      *((_QWORD *)v21 + 18) = v21 + 68;
      *((_QWORD *)v21 + 17) = v21 + 68;
      LOWORD(v13) = v29;
    }
    goto LABEL_38;
  }
  if ( v7 == 60189 )
  {
    v21 = Pool2;
    goto LABEL_33;
  }
  if ( v7 != 60464 )
  {
    v28 = 0;
    if ( (_WORD)v7 != 0xEC24 )
    {
      v15 = (_WORD *)((char *)&Pool2[v11] + v10);
      v28 = &Pool2[v11];
      v13 = v29;
      v26 = v15;
    }
    if ( v12 )
    {
      v16 = (struct _KEVENT *)((char *)v15 + v13);
      v17 = (char *)v16 + v9;
    }
    else
    {
      v16 = (struct _KEVENT *)ExAllocatePool2(64, 336, 1716418642);
      if ( !v16 )
      {
LABEL_24:
        ExFreePoolWithTag(Pool2, 0);
        return 0;
      }
      v17 = (char *)&Pool2[v11 + v24] + v29;
    }
    v18 = ExAllocatePool2(64, 32, 1950447698);
    if ( !v18 )
    {
      if ( (v6 & 0x40) == 0 )
        ExFreePoolWithTag(v16, 0);
      goto LABEL_24;
    }
    *(_QWORD *)(v18 + 8) = v18;
    *(_QWORD *)v18 = v18;
    if ( Pool2 )
    {
      *((_QWORD *)Pool2 + 38) = v16;
      *Pool2 = -5088;
      Pool2[1] = v11 * 2;
      LOWORD(v16->Header.Lock) = -5123;
      *(_WORD *)(*((_QWORD *)Pool2 + 38) + 2LL) = 336;
      *((_QWORD *)Pool2 + 93) = v18;
      _InterlockedIncrement((volatile signed __int32 *)(v18 + 24));
      KeInitializeEvent((PRKEVENT)(*((_QWORD *)Pool2 + 38) + 304LL), NotificationEvent, 0);
      *((_QWORD *)Pool2 + 51) = v28;
      *((_QWORD *)Pool2 + 52) = v26;
      memset(v17, 0, v5 + 2);
      *((_QWORD *)Pool2 + 46) = v17;
      Pool2[180] = v5;
      Pool2[181] = v5;
      *(_OWORD *)(Pool2 + 156) = 0;
      *(_OWORD *)(Pool2 + 164) = 0;
      *(_OWORD *)(Pool2 + 172) = 0;
      _InterlockedIncrement(&RxNumberOfActiveFcbs);
      _InterlockedIncrement((volatile signed __int32 *)&RxDeviceObject->MiniRdrListLinks);
      v16[10].Header.LockNV = 1;
      v16[10].Header.WaitListHead.Flink = 0;
      LODWORD(v16[10].Header.WaitListHead.Blink) = 0;
      KeInitializeEvent(v16 + 11, SynchronizationEvent, 0);
      v20 = *((_BYTE *)Pool2 + 7);
      *((_BYTE *)Pool2 + 4) |= 0x40u;
      *((_BYTE *)Pool2 + 6) |= 2u;
      *((_BYTE *)Pool2 + 7) = v20 & 0xF | 0x50;
      *((_QWORD *)Pool2 + 8) = Pool2 + 28;
      *((_QWORD *)Pool2 + 7) = Pool2 + 28;
      if ( v16 != (struct _KEVENT *)-240LL )
        *((_QWORD *)Pool2 + 6) = v16 + 10;
      *((_QWORD *)Pool2 + 9) = 0;
      *((_QWORD *)Pool2 + 11) = 0;
      *((_QWORD *)Pool2 + 10) = 0;
      *((_QWORD *)Pool2 + 12) = 0;
      *((_DWORD *)Pool2 + 26) = 0;
      *((_QWORD *)Pool2 + 14) = 0;
      FsRtlInitializeOplock((POPLOCK)Pool2 + 11);
    }
    LOWORD(v13) = v29;
    LOWORD(v10) = v24 * 2;
    v21 = v28;
    v15 = v26;
    goto LABEL_33;
  }
  v15 = Pool2;
LABEL_38:
  if ( v15 )
  {
    v23 = v13;
    memset(v15, 0, (unsigned __int16)v13);
    *v15 = -5072;
    v15[1] = v23;
  }
  return Pool2;
}

```

## disassembly

```asm
0x14005c6c0  mov     [rsp+arg_8], rbx
0x14005c6c5  mov     [rsp+arg_10], rbp
0x14005c6ca  push    rsi
0x14005c6cb  push    rdi
0x14005c6cc  push    r12
0x14005c6ce  push    r13
0x14005c6d0  push    r14
0x14005c6d2  sub     rsp, 40h
0x14005c6d6  mov     ebx, r9d
0x14005c6d9  mov     rsi, r8
0x14005c6dc  movzx   ebp, dx
0x14005c6df  mov     rdi, rcx
0x14005c6e2  cmp     r9d, 0FFFFh
0x14005c6e9  ja      loc_14005CAD3
0x14005c6ef  xor     r8d, r8d
0x14005c6f2  xor     r9d, r9d
0x14005c6f5  xor     r13d, r13d
0x14005c6f8  mov     dword ptr [rsp+68h+var_40], r8d
0x14005c6fd  mov     ecx, ebp
0x14005c6ff  mov     [rsp+68h+var_48], r9d
0x14005c704  mov     r12d, ebp
0x14005c707  mov     r10d, 150h
0x14005c70d  mov     r11d, 0EC24h
0x14005c713  sub     ecx, 0EB1Ch
0x14005c719  jz      short loc_14005C753
0x14005c71b  sub     ecx, 1
0x14005c71e  jz      short loc_14005C753
0x14005c720  cmp     ecx, 113h
0x14005c726  jz      short loc_14005C75E
0x14005c728  mov     rdx, rsi
0x14005c72b  mov     r13d, 2F0h
0x14005c731  and     edx, 40h
0x14005c734  mov     eax, edx
0x14005c736  mov     [rsp+68h+var_38], rdx
0x14005c73b  neg     rax
0x14005c73e  sbb     r8d, r8d
0x14005c741  and     r8d, r10d
0x14005c744  mov     dword ptr [rsp+68h+var_40], r8d
0x14005c749  cmp     bp, r11w
0x14005c74d  jnz     short loc_14005C753
0x14005c74f  xor     eax, eax
0x14005c751  jmp     short loc_14005C76E
0x14005c753  mov     r9d, 0F8h
0x14005c759  mov     [rsp+68h+var_48], r9d
0x14005c75e  mov     rdx, rsi
0x14005c761  mov     eax, 138h
0x14005c766  and     edx, 40h
0x14005c769  mov     [rsp+68h+var_38], rdx
0x14005c76e  mov     r14, [rsp+68h+AlreadyAllocatedObject]
0x14005c776  mov     [rsp+68h+arg_18], eax
0x14005c77d  test    r14, r14
0x14005c780  jnz     short loc_14005C7D5
0x14005c782  lea     edx, [r9+rax]
0x14005c786  mov     rcx, rsi
0x14005c789  add     edx, r8d
0x14005c78c  mov     r8d, 63467852h
0x14005c792  add     edx, r13d
0x14005c795  add     edx, ebx
0x14005c797  add     rdx, 2
0x14005c79b  call    cs:__imp_ExAllocatePool2
0x14005c7a2  nop     dword ptr [rax+rax+00h]
0x14005c7a7  mov     r14, rax
0x14005c7aa  test    rax, rax
0x14005c7ad  jz      loc_14005CAD3
0x14005c7b3  mov     rdx, [rsp+68h+var_38]
0x14005c7b8  mov     r10d, 150h
0x14005c7be  mov     r8d, dword ptr [rsp+68h+var_40]
0x14005c7c3  mov     r11d, 0EC24h
0x14005c7c9  mov     r9d, [rsp+68h+var_48]
0x14005c7ce  mov     eax, [rsp+68h+arg_18]
0x14005c7d5  mov     [rsp+68h+arg_0], r15
0x14005c7da  xor     r15d, r15d
0x14005c7dd  mov     [rsp+68h+var_40], r15
0x14005c7e2  sub     r12d, 0EB1Ch
0x14005c7e9  jz      loc_14005CA34
0x14005c7ef  sub     r12d, 1
0x14005c7f3  jz      loc_14005CA2D
0x14005c7f9  cmp     r12d, 113h
0x14005c800  jz      loc_14005CA28
0x14005c806  mov     [rsp+68h+var_38], r15
0x14005c80b  cmp     bp, r11w
0x14005c80f  jz      short loc_14005C82E
0x14005c811  mov     eax, r13d
0x14005c814  add     rax, r14
0x14005c817  mov     r15d, r9d
0x14005c81a  add     r15, rax
0x14005c81d  mov     [rsp+68h+var_38], rax
0x14005c822  mov     eax, [rsp+68h+arg_18]
0x14005c829  mov     [rsp+68h+var_40], r15
0x14005c82e  test    rdx, rdx
0x14005c831  jz      short loc_14005C83E
0x14005c833  add     r15, rax
0x14005c836  mov     r12d, r8d
0x14005c839  add     r12, r15
0x14005c83c  jmp     short loc_14005C873
0x14005c83e  mov     r8d, 664E7852h
0x14005c844  mov     rdx, r10
0x14005c847  mov     ecx, 40h ; '@'
0x14005c84c  call    cs:__imp_ExAllocatePool2
0x14005c853  nop     dword ptr [rax+rax+00h]
0x14005c858  mov     r15, rax
0x14005c85b  test    rax, rax
0x14005c85e  jz      short loc_14005C8AE
0x14005c860  mov     r12d, [rsp+68h+arg_18]
0x14005c868  add     r12d, [rsp+68h+var_48]
0x14005c86d  add     r12d, r13d
0x14005c870  add     r12, r14
0x14005c873  mov     edx, 20h ; ' '
0x14005c878  mov     ecx, 40h ; '@'
0x14005c87d  mov     r8d, 74417852h
0x14005c883  call    cs:__imp_ExAllocatePool2
0x14005c88a  nop     dword ptr [rax+rax+00h]
0x14005c88f  mov     rcx, rax
0x14005c892  test    rax, rax
0x14005c895  jnz     short loc_14005C8E1
0x14005c897  test    sil, 40h
0x14005c89b  jnz     short loc_14005C8AE
0x14005c89d  xor     edx, edx; Tag
0x14005c89f  mov     rcx, r15; P
0x14005c8a2  call    cs:__imp_ExFreePoolWithTag
0x14005c8a9  nop     dword ptr [rax+rax+00h]
0x14005c8ae  xor     edx, edx; Tag
0x14005c8b0  mov     rcx, r14; P
0x14005c8b3  call    cs:__imp_ExFreePoolWithTag
0x14005c8ba  nop     dword ptr [rax+rax+00h]
0x14005c8bf  xor     eax, eax
0x14005c8c1  mov     r15, [rsp+68h+arg_0]
0x14005c8c6  mov     rbx, [rsp+68h+arg_8]
0x14005c8cb  mov     rbp, [rsp+68h+arg_10]
0x14005c8d3  add     rsp, 40h
0x14005c8d7  pop     r14
0x14005c8d9  pop     r13
0x14005c8db  pop     r12
0x14005c8dd  pop     rdi
0x14005c8de  pop     rsi
0x14005c8df  retn
0x14005c8e1  mov     [rax+8], rcx
0x14005c8e5  mov     [rax], rcx
0x14005c8e8  test    r14, r14
0x14005c8eb  jz      loc_14005CA41
0x14005c8f1  mov     [r14+130h], r15
0x14005c8f8  mov     word ptr [r14], 0EC20h
0x14005c8fe  mov     [r14+2], r13w
0x14005c903  mov     word ptr [r15], 0EBFDh
0x14005c909  mov     rax, [r14+130h]
0x14005c910  mov     word ptr [rax+2], 150h
0x14005c916  mov     [r14+2E8h], rcx
0x14005c91d  lock inc dword ptr [rcx+18h]
0x14005c921  mov     rcx, [r14+130h]
0x14005c928  xor     r8d, r8d; State
0x14005c92b  add     rcx, 130h; Event
0x14005c932  xor     edx, edx; Type
0x14005c934  call    cs:__imp_KeInitializeEvent
0x14005c93b  nop     dword ptr [rax+rax+00h]
0x14005c940  mov     rax, [rsp+68h+var_38]
0x14005c945  lea     r8, [rbx+2]; Size
0x14005c949  mov     [r14+198h], rax
0x14005c950  xor     edx, edx; Val
0x14005c952  mov     rax, [rsp+68h+var_40]
0x14005c957  mov     rcx, r12; void *
0x14005c95a  mov     [r14+1A0h], rax
0x14005c961  call    memset
0x14005c966  xorps   xmm0, xmm0
0x14005c969  mov     [r14+170h], r12
0x14005c970  mov     [r14+168h], bx
0x14005c978  mov     [r14+16Ah], bx
0x14005c980  movups  xmmword ptr [r14+138h], xmm0
0x14005c988  movups  xmmword ptr [r14+148h], xmm0
0x14005c990  movups  xmmword ptr [r14+158h], xmm0
0x14005c998  lock inc cs:RxNumberOfActiveFcbs
0x14005c99f  lock inc dword ptr [rdi+198h]
0x14005c9a6  lea     rbx, [r15+0F0h]
0x14005c9ad  xor     esi, esi
0x14005c9af  lea     rcx, [rbx+18h]; Event
0x14005c9b3  mov     dword ptr [rbx], 1
0x14005c9b9  xor     r8d, r8d; State
0x14005c9bc  mov     [rbx+8], rsi
0x14005c9c0  mov     edx, 1; Type
0x14005c9c5  mov     [rbx+10h], esi
0x14005c9c8  call    cs:__imp_KeInitializeEvent
0x14005c9cf  nop     dword ptr [rax+rax+00h]
0x14005c9d4  movzx   eax, byte ptr [r14+7]
0x14005c9d9  or      byte ptr [r14+4], 40h
0x14005c9de  and     al, 0Fh
0x14005c9e0  or      byte ptr [r14+6], 2
0x14005c9e5  or      al, 50h
0x14005c9e7  mov     [r14+7], al
0x14005c9eb  lea     rax, [r14+38h]
0x14005c9ef  mov     [rax+8], rax
0x14005c9f3  mov     [rax], rax
0x14005c9f6  test    rbx, rbx
0x14005c9f9  jz      short loc_14005C9FF
0x14005c9fb  mov     [r14+30h], rbx
0x14005c9ff  lea     rcx, [r14+58h]; Oplock
0x14005ca03  mov     [r14+48h], rsi
0x14005ca07  mov     [rcx], rsi
0x14005ca0a  mov     [r14+50h], rsi
0x14005ca0e  mov     [r14+60h], rsi
0x14005ca12  mov     [r14+68h], esi
0x14005ca16  mov     [r14+70h], rsi
0x14005ca1a  call    cs:__imp_FsRtlInitializeOplock
0x14005ca21  nop     dword ptr [rax+rax+00h]
0x14005ca26  jmp     short loc_14005CA43
0x14005ca28  mov     r15, r14
0x14005ca2b  jmp     short loc_14005CAAB
0x14005ca2d  mov     rdi, r14
0x14005ca30  xor     esi, esi
0x14005ca32  jmp     short loc_14005CA59
0x14005ca34  mov     r15d, r9d
0x14005ca37  mov     rdi, r14
0x14005ca3a  add     r15, r14
0x14005ca3d  xor     esi, esi
0x14005ca3f  jmp     short loc_14005CA59
0x14005ca41  xor     esi, esi
0x14005ca43  mov     eax, [rsp+68h+arg_18]
0x14005ca4a  mov     r9d, [rsp+68h+var_48]
0x14005ca4f  mov     rdi, [rsp+68h+var_38]
0x14005ca54  mov     r15, [rsp+68h+var_40]
0x14005ca59  test    rdi, rdi
0x14005ca5c  jz      short loc_14005CAAB
0x14005ca5e  movzx   ebx, r9w
0x14005ca62  xor     edx, edx; Val
0x14005ca64  mov     r8d, ebx; Size
0x14005ca67  mov     rcx, rdi; void *
0x14005ca6a  call    memset
0x14005ca6f  mov     eax, 0EB1Ch
0x14005ca74  mov     [rdi+2], bx
0x14005ca78  mov     [rdi], ax
0x14005ca7b  cmp     bp, ax
0x14005ca7e  jz      short loc_14005CA8C
0x14005ca80  or      dword ptr [rdi+48h], 20000h
0x14005ca87  mov     rax, rsi
0x14005ca8a  jmp     short loc_14005CA8F
0x14005ca8c  mov     rax, r15
0x14005ca8f  mov     [rdi+0C8h], rax
0x14005ca96  lea     rax, [rdi+88h]
0x14005ca9d  mov     [rax+8], rax
0x14005caa1  mov     [rax], rax
0x14005caa4  mov     eax, [rsp+68h+arg_18]
0x14005caab  test    r15, r15
0x14005caae  jz      short loc_14005CACB
0x14005cab0  movzx   ebx, ax
0x14005cab3  xor     edx, edx; Val
0x14005cab5  mov     r8d, ebx; Size
0x14005cab8  mov     rcx, r15; void *
0x14005cabb  call    memset
0x14005cac0  mov     word ptr [r15], 0EC30h
0x14005cac6  mov     [r15+2], bx
0x14005cacb  mov     rax, r14
0x14005cace  jmp     loc_14005C8C1
0x14005cad3  xor     eax, eax
0x14005cad5  jmp     loc_14005C8C6
```
