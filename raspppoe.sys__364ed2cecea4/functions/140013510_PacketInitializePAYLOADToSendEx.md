# PacketInitializePAYLOADToSendEx

- ea: `0x140013510`
- end: `0x1400138c7`
- name: `PacketInitializePAYLOADToSendEx`
- size: `951`
- prototype: `__int64 __fastcall(int, int, int, int, PNET_BUFFER_LIST OriginalNetBufferList, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001169c`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140006b40`
- `0x140007040`
- `0x140013510`

## import_xrefs

- `NDIS!NdisGetDataBuffer` at `0x140013784`
- `NDIS!NdisGetDataBuffer` at `0x140013784`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400135de`
- `NDIS!NdisAllocateNetBufferListContext` at `0x1400135de`
- `NDIS!NdisFreeNetBufferListContext` at `0x140013848`
- `NDIS!NdisFreeNetBufferListContext` at `0x140013848`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14001385c`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14001385c`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140013692`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140013692`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x1400135a9`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x1400135a9`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140013728`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400137e5`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140013728`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x1400137e5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400136fd`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400136fd`

## pseudocode

```c
__int64 __fastcall PacketInitializePAYLOADToSendEx(
        UCHAR **a1,
        __int64 a2,
        int *a3,
        __int16 a4,
        PNET_BUFFER_LIST OriginalNetBufferList,
        void *a6)
{
  PNET_BUFFER_LIST v6; // r13
  struct _NET_BUFFER_LIST *CloneNetBufferList; // rax
  struct _NET_BUFFER_LIST *v11; // rsi
  unsigned int NetBufferListContext; // r14d
  UCHAR *v13; // rbx
  __int16 v14; // ax
  int v15; // ecx
  struct _NET_BUFFER *FirstNetBuffer; // rdi
  ULONG CurrentMdlOffset; // r15d
  ULONG v18; // r15d
  __int64 v19; // r12
  _QWORD *p_Next; // rcx
  unsigned __int64 v21; // r9
  unsigned __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rax
  _DWORD *DataBuffer; // rax
  __int64 v26; // r8
  PMDL CurrentMdl; // rdx
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  struct _NET_BUFFER_LIST *v31; // [rsp+40h] [rbp-C0h]
  PNET_BUFFER_LIST v32; // [rsp+48h] [rbp-B8h]
  UCHAR **v33; // [rsp+50h] [rbp-B0h]
  __int128 v34; // [rsp+58h] [rbp-A8h]
  int v35; // [rsp+68h] [rbp-98h]
  _BYTE Storage[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v37[512]; // [rsp+90h] [rbp-70h] BYREF

  v6 = OriginalNetBufferList;
  v32 = OriginalNetBufferList;
  v34 = 0;
  v35 = 0;
  v33 = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  CloneNetBufferList = NdisAllocateCloneNetBufferList(OriginalNetBufferList, 0, 0, 2u);
  v31 = CloneNetBufferList;
  v11 = CloneNetBufferList;
  if ( CloneNetBufferList )
  {
    NetBufferListContext = NdisAllocateNetBufferListContext(CloneNetBufferList, 0xA0u, 0, 0x64456F50u);
    if ( !NetBufferListContext )
    {
      v13 = &v11->Context->ContextData[v11->Context->Offset];
      memset(v13, 0, 0xA0u);
      *((_DWORD *)v13 + 36) = 3;
      v14 = *((_WORD *)a3 + 2);
      HIWORD(v34) = BYTE14(v34) | 0x11;
      v15 = *a3;
      WORD2(v34) = v14;
      *(_DWORD *)((char *)&v34 + 6) = *(_DWORD *)a2;
      WORD5(v34) = *(_WORD *)(a2 + 4);
      WORD6(v34) = 25736;
      LODWORD(v34) = v15;
      LOWORD(v35) = __ROR2__(a4, 8);
      FirstNetBuffer = v11->FirstNetBuffer;
      if ( !FirstNetBuffer )
      {
LABEL_23:
        v11->ProtocolReserved[1] = a6;
        v11->ProtocolReserved[0] = v13;
        v11->ProtocolReserved[2] = v6;
        *((_QWORD *)v13 + 1) = DerefPppoePacket;
        *((_QWORD *)v13 + 17) = v11;
        *(_DWORD *)v13 = 0;
        _InterlockedIncrement((volatile signed __int32 *)v13);
        *v33 = v13;
        goto LABEL_28;
      }
      while ( 1 )
      {
        CurrentMdlOffset = FirstNetBuffer->CurrentMdlOffset;
        v18 = CurrentMdlOffset - 7 > 0xC ? 20 : CurrentMdlOffset + 14;
        NetBufferListContext = NdisRetreatNetBufferDataStart(FirstNetBuffer, v18, 0, 0);
        if ( NetBufferListContext )
          break;
        if ( v18 != 20 )
        {
          v19 = 0;
          do
          {
            p_Next = &FirstNetBuffer->CurrentMdl->Next;
            v21 = FirstNetBuffer->DataLength - (unsigned __int64)v18;
            v29 = 0;
            v22 = v21 - v19;
            v30 = 0;
            v23 = *p_Next;
            if ( v22 > 0x200 )
              v22 = 512;
            RtlCopyMdlToKernelBuffer(v23, v18 + v19 - 14, v37, v22, &v29);
            RtlCopyKernelBufferToMdl(v37, FirstNetBuffer->CurrentMdl->Next, v19 + 6, v29, &v30);
            v19 += v29;
            v24 = FirstNetBuffer->DataLength - v18;
          }
          while ( v19 != v24 );
          v11 = v31;
          v6 = v32;
          FirstNetBuffer->DataLength = v24 + 20;
        }
        if ( FirstNetBuffer->DataLength > 0x5EA )
        {
          NetBufferListContext = -1073676273;
          break;
        }
        DataBuffer = NdisGetDataBuffer(FirstNetBuffer, 0x14u, Storage, 1u, 0);
        *((_QWORD *)v13 + 14) = DataBuffer;
        *(_OWORD *)DataBuffer = v34;
        DataBuffer[4] = v35;
        *(_WORD *)(*((_QWORD *)v13 + 14) + 18LL) = __ROR2__(
                                                     *((_WORD *)&FirstNetBuffer->NetBufferHeader.Link + 12) - 20,
                                                     8);
        if ( *((_BYTE **)v13 + 14) == Storage )
        {
          v26 = FirstNetBuffer->CurrentMdlOffset;
          CurrentMdl = FirstNetBuffer->CurrentMdl;
          v30 = 0;
          RtlCopyKernelBufferToMdl(Storage, CurrentMdl, v26, 20, &v30);
        }
        FirstNetBuffer = (struct _NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        if ( !FirstNetBuffer )
          goto LABEL_23;
      }
      if ( v13 )
        NdisFreeNetBufferListContext(v11, 0xA0u);
    }
    NdisFreeCloneNetBufferList(v11, 2u);
    goto LABEL_28;
  }
  NetBufferListContext = -1073741670;
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      81,
      WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
      NetBufferListContext);
  }
  return NetBufferListContext;
}

```

## disassembly

```asm
0x140013510  push    rbp
0x140013512  push    rbx
0x140013513  push    rsi
0x140013514  push    rdi
0x140013515  push    r12
0x140013517  push    r13
0x140013519  push    r14
0x14001351b  push    r15
0x14001351d  lea     rbp, [rsp-1A8h]
0x140013525  sub     rsp, 2A8h
0x14001352c  mov     rax, cs:__security_cookie
0x140013533  xor     rax, rsp
0x140013536  mov     [rbp+1E0h+var_50], rax
0x14001353d  mov     r13, [rbp+1E0h+OriginalNetBufferList]
0x140013544  xorps   xmm0, xmm0
0x140013547  xor     eax, eax
0x140013549  mov     [rsp+2E0h+var_298], r13
0x14001354e  movups  [rsp+2E0h+var_288], xmm0
0x140013553  mov     [rsp+2E0h+var_278], eax
0x140013557  movzx   edi, r9w
0x14001355b  mov     r15, r8
0x14001355e  mov     [rsp+2E0h+var_290], rcx
0x140013563  mov     r12, rdx
0x140013566  mov     rcx, cs:WPP_GLOBAL_Control
0x14001356d  lea     rax, WPP_GLOBAL_Control
0x140013574  cmp     rcx, rax
0x140013577  jz      short loc_14001359B
0x140013579  mov     eax, [rcx+2Ch]
0x14001357c  test    al, 20h
0x14001357e  jz      short loc_14001359B
0x140013580  cmp     byte ptr [rcx+29h], 4
0x140013584  jb      short loc_14001359B
0x140013586  mov     rcx, [rcx+18h]
0x14001358a  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013591  mov     edx, 50h ; 'P'
0x140013596  call    WPP_SF_
0x14001359b  mov     r9d, 2; AllocateCloneFlags
0x1400135a1  xor     r8d, r8d; NetBufferPoolHandle
0x1400135a4  xor     edx, edx; NetBufferListPoolHandle
0x1400135a6  mov     rcx, r13; OriginalNetBufferList
0x1400135a9  call    cs:__imp_NdisAllocateCloneNetBufferList
0x1400135b0  nop     dword ptr [rax+rax+00h]
0x1400135b5  mov     [rsp+2E0h+var_2A0], rax
0x1400135ba  mov     rsi, rax
0x1400135bd  test    rax, rax
0x1400135c0  jnz     short loc_1400135CD
0x1400135c2  mov     r14d, 0C000009Ah
0x1400135c8  jmp     loc_140013868
0x1400135cd  xor     r8d, r8d; ContextBackFill
0x1400135d0  mov     edx, 0A0h; ContextSize
0x1400135d5  mov     r9d, 64456F50h; PoolTag
0x1400135db  mov     rcx, rsi; NetBufferList
0x1400135de  call    cs:__imp_NdisAllocateNetBufferListContext
0x1400135e5  nop     dword ptr [rax+rax+00h]
0x1400135ea  mov     r14d, eax
0x1400135ed  test    eax, eax
0x1400135ef  jnz     loc_140013854
0x1400135f5  mov     rdx, [rsi+10h]
0x1400135f9  mov     r8d, 0A0h; Size
0x1400135ff  movzx   ebx, word ptr [rdx+0Ah]
0x140013603  add     rbx, 10h
0x140013607  add     rbx, rdx
0x14001360a  xor     edx, edx; Val
0x14001360c  mov     rcx, rbx; void *
0x14001360f  call    memset
0x140013614  mov     dword ptr [rbx+90h], 3
0x14001361e  movzx   eax, word ptr [r15+4]
0x140013623  or      byte ptr [rsp+2E0h+var_288+0Eh], 11h
0x140013628  mov     ecx, [r15]
0x14001362b  mov     word ptr [rsp+2E0h+var_288+4], ax
0x140013630  mov     eax, [r12]
0x140013634  mov     dword ptr [rsp+2E0h+var_288+6], eax
0x140013638  movzx   eax, word ptr [r12+4]
0x14001363e  ror     di, 8
0x140013642  mov     word ptr [rsp+2E0h+var_288+0Ah], ax
0x140013647  mov     eax, 6488h
0x14001364c  mov     word ptr [rsp+2E0h+var_288+0Ch], ax
0x140013651  mov     dword ptr [rsp+2E0h+var_288], ecx
0x140013655  mov     byte ptr [rsp+2E0h+var_288+0Fh], r14b
0x14001365a  mov     word ptr [rsp+2E0h+var_278], di
0x14001365f  mov     rdi, [rsi+8]
0x140013663  test    rdi, rdi
0x140013666  jz      loc_1400137FD
0x14001366c  lea     r12d, [r14+14h]
0x140013670  mov     r15d, [rdi+10h]
0x140013674  lea     eax, [r15-7]
0x140013678  cmp     eax, 0Ch
0x14001367b  ja      short loc_140013683
0x14001367d  add     r15d, 0Eh
0x140013681  jmp     short loc_140013686
0x140013683  mov     r15d, r12d
0x140013686  xor     r9d, r9d; AllocateMdlHandler
0x140013689  xor     r8d, r8d; DataBackFill
0x14001368c  mov     edx, r15d; DataOffsetDelta
0x14001368f  mov     rcx, rdi; NetBuffer
0x140013692  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140013699  nop     dword ptr [rax+rax+00h]
0x14001369e  mov     r14d, eax
0x1400136a1  test    eax, eax
0x1400136a3  jnz     loc_14001383B
0x1400136a9  cmp     r15d, r12d
0x1400136ac  jz      loc_14001375E
0x1400136b2  xor     r12d, r12d
0x1400136b5  mov     r13d, r15d
0x1400136b8  mov     esi, 200h
0x1400136bd  mov     r9d, [rdi+18h]
0x1400136c1  lea     rax, [rsp+2E0h+var_2B0]
0x1400136c6  mov     rcx, [rdi+8]
0x1400136ca  lea     rdx, [r12-0Eh]
0x1400136cf  sub     r9, r13
0x1400136d2  mov     [rsp+2E0h+var_2B0], 0
0x1400136db  sub     r9, r12
0x1400136de  mov     [rsp+2E0h+var_2A8], 0
0x1400136e7  cmp     r9, rsi
0x1400136ea  mov     qword ptr [rsp+2E0h+AlignOffset], rax
0x1400136ef  mov     rcx, [rcx]
0x1400136f2  lea     r8, [rbp+1E0h+var_250]
0x1400136f6  cmova   r9, rsi
0x1400136fa  add     rdx, r13
0x1400136fd  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x140013704  nop     dword ptr [rax+rax+00h]
0x140013709  mov     rdx, [rdi+8]
0x14001370d  lea     rax, [rsp+2E0h+var_2A8]
0x140013712  mov     r9, [rsp+2E0h+var_2B0]
0x140013717  lea     r8, [r12+6]
0x14001371c  lea     rcx, [rbp+1E0h+var_250]
0x140013720  mov     qword ptr [rsp+2E0h+AlignOffset], rax
0x140013725  mov     rdx, [rdx]
0x140013728  call    cs:__imp_RtlCopyKernelBufferToMdl
0x14001372f  nop     dword ptr [rax+rax+00h]
0x140013734  mov     eax, [rdi+18h]
0x140013737  add     r12, [rsp+2E0h+var_2B0]
0x14001373c  sub     eax, r15d
0x14001373f  cmp     r12, rax
0x140013742  jnz     loc_1400136BD
0x140013748  mov     rsi, [rsp+2E0h+var_2A0]
0x14001374d  add     eax, 14h
0x140013750  mov     r13, [rsp+2E0h+var_298]
0x140013755  mov     r12d, 14h
0x14001375b  mov     [rdi+18h], eax
0x14001375e  cmp     dword ptr [rdi+18h], 5EAh
0x140013765  ja      loc_140013835
0x14001376b  mov     r9d, 1; AlignMultiple
0x140013771  mov     [rsp+2E0h+AlignOffset], 0; AlignOffset
0x140013779  lea     r8, [rsp+2E0h+Storage]; Storage
0x14001377e  mov     edx, r12d; BytesNeeded
0x140013781  mov     rcx, rdi; NetBuffer
0x140013784  call    cs:__imp_NdisGetDataBuffer
0x14001378b  nop     dword ptr [rax+rax+00h]
0x140013790  mov     [rbx+70h], rax
0x140013794  movups  xmm0, [rsp+2E0h+var_288]
0x140013799  movups  xmmword ptr [rax], xmm0
0x14001379c  mov     ecx, [rsp+2E0h+var_278]
0x1400137a0  mov     [rax+10h], ecx
0x1400137a3  movzx   ecx, word ptr [rdi+18h]
0x1400137a7  mov     rax, [rbx+70h]
0x1400137ab  sub     cx, r12w
0x1400137af  ror     cx, 8
0x1400137b3  mov     [rax+12h], cx
0x1400137b7  lea     rax, [rsp+2E0h+Storage]
0x1400137bc  cmp     [rbx+70h], rax
0x1400137c0  jnz     short loc_1400137F1
0x1400137c2  mov     r8d, [rdi+10h]
0x1400137c6  lea     rax, [rsp+2E0h+var_2A8]
0x1400137cb  mov     rdx, [rdi+8]
0x1400137cf  lea     rcx, [rsp+2E0h+Storage]
0x1400137d4  mov     r9, r12
0x1400137d7  mov     qword ptr [rsp+2E0h+AlignOffset], rax
0x1400137dc  mov     [rsp+2E0h+var_2A8], 0
0x1400137e5  call    cs:__imp_RtlCopyKernelBufferToMdl
0x1400137ec  nop     dword ptr [rax+rax+00h]
0x1400137f1  mov     rdi, [rdi]
0x1400137f4  test    rdi, rdi
0x1400137f7  jnz     loc_140013670
0x1400137fd  mov     rax, [rbp+1E0h+arg_28]
0x140013804  mov     [rsi+48h], rax
0x140013808  lea     rax, DerefPppoePacket
0x14001380f  mov     [rsi+40h], rbx
0x140013813  mov     [rsi+50h], r13
0x140013817  mov     [rbx+8], rax
0x14001381b  mov     [rbx+88h], rsi
0x140013822  mov     dword ptr [rbx], 0
0x140013828  lock inc dword ptr [rbx]
0x14001382b  mov     rax, [rsp+2E0h+var_290]
0x140013830  mov     [rax], rbx
0x140013833  jmp     short loc_140013868
0x140013835  mov     r14d, 0C001000Fh
0x14001383b  test    rbx, rbx
0x14001383e  jz      short loc_140013854
0x140013840  mov     edx, 0A0h; ContextSize
0x140013845  mov     rcx, rsi; NetBufferList
0x140013848  call    cs:__imp_NdisFreeNetBufferListContext
0x14001384f  nop     dword ptr [rax+rax+00h]
0x140013854  mov     edx, 2; FreeCloneFlags
0x140013859  mov     rcx, rsi; CloneNetBufferList
0x14001385c  call    cs:__imp_NdisFreeCloneNetBufferList
0x140013863  nop     dword ptr [rax+rax+00h]
0x140013868  mov     rcx, cs:WPP_GLOBAL_Control
0x14001386f  lea     rax, WPP_GLOBAL_Control
0x140013876  cmp     rcx, rax
0x140013879  jz      short loc_1400138A0
0x14001387b  mov     eax, [rcx+2Ch]
0x14001387e  test    al, 20h
0x140013880  jz      short loc_1400138A0
0x140013882  cmp     byte ptr [rcx+29h], 4
0x140013886  jb      short loc_1400138A0
0x140013888  mov     rcx, [rcx+18h]
0x14001388c  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140013893  mov     edx, 51h ; 'Q'
0x140013898  mov     r9d, r14d
0x14001389b  call    WPP_SF_d
0x1400138a0  mov     eax, r14d
0x1400138a3  mov     rcx, [rbp+1E0h+var_50]
0x1400138aa  xor     rcx, rsp; StackCookie
0x1400138ad  call    __security_check_cookie
0x1400138b2  add     rsp, 2A8h
0x1400138b9  pop     r15
0x1400138bb  pop     r14
0x1400138bd  pop     r13
0x1400138bf  pop     r12
0x1400138c1  pop     rdi
0x1400138c2  pop     rsi
0x1400138c3  pop     rbx
0x1400138c4  pop     rbp
0x1400138c5  retn
```
