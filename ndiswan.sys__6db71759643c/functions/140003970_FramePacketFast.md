# FramePacketFast

- ea: `0x140003970`
- end: `0x140003c1c`
- name: `FramePacketFast`
- size: `684`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1400312a0`
- `0x1400318c0`

## callees

- `0x140003970`
- `0x14000a290`
- `0x1400161f0`
- `0x140016230`
- `0x140016400`
- `0x14002e3e8`
- `0x1400321d0`

## import_xrefs

- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140003ad5`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x140003ad5`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140003af9`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x140003af9`
- `NDIS!NdisGetDataBuffer` at `0x140003b30`
- `NDIS!NdisGetDataBuffer` at `0x140003b30`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140003bc6`
- `NETIO!RtlCopyKernelBufferToMdl` at `0x140003bc6`

## pseudocode

```c
__int64 __fastcall FramePacketFast(
        __int64 a1,
        __int64 a2,
        struct _NET_BUFFER_LIST *a3,
        __int64 **a4,
        __int64 a5,
        int a6)
{
  PNET_BUFFER_LIST_CONTEXT Context; // rcx
  char *v11; // rdi
  unsigned int v12; // ebx
  __int16 v13; // r15
  __int64 *v14; // rax
  __int64 *v15; // rcx
  unsigned int v16; // ebx
  __int64 *v17; // r14
  ULONG v18; // ebx
  _BYTE *v19; // rcx
  size_t v20; // rsi
  struct _NET_BUFFER *i; // rbx
  PVOID DataBuffer; // rax
  __int64 CurrentMdlOffset; // r8
  PMDL CurrentMdl; // rdx
  __int64 v26; // [rsp+30h] [rbp-128h] BYREF
  _DWORD v27[2]; // [rsp+40h] [rbp-118h] BYREF
  ULONG DataOffsetDelta; // [rsp+48h] [rbp-110h]
  unsigned int v29; // [rsp+4Ch] [rbp-10Ch]
  __int128 v30; // [rsp+50h] [rbp-108h]
  __int128 v31; // [rsp+60h] [rbp-F8h]
  __int128 v32; // [rsp+70h] [rbp-E8h]
  __int128 v33; // [rsp+80h] [rbp-D8h]
  _BYTE Src[128]; // [rsp+90h] [rbp-C8h] BYREF

  DataOffsetDelta = 0;
  v30 = 0;
  Context = a3->Context;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v11 = (char *)Context + Context->Offset;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids);
  }
  *((_QWORD *)v11 + 9) = a1;
  v12 = *(_DWORD *)(a1 + 104);
  v13 = *(_WORD *)(a2 + 214);
  if ( v13 == 171 )
    v12 = *(_DWORD *)(a1 + 104) & 0xFFFFFFF0 | 8;
  v14 = *a4;
  if ( (__int64 **)(*a4)[1] != a4 || (v15 = (__int64 *)*v14, *(__int64 **)(*v14 + 8) != v14) )
    __fastfail(3u);
  *a4 = v15;
  v15[1] = (__int64)a4;
  v16 = v12 | 0x10;
  v17 = v14 - 30;
  v29 = v16;
  v27[0] = *((_DWORD *)v14 + 12);
  v27[1] = a6;
  BuildLinkHeader(v27, Src);
  if ( qword_14001E2D8 || gbEnablePacketCapture && *(_BYTE *)(a1 + 2436) )
    IndicatePromiscuousSendPacket(v17);
  v18 = ~(unsigned __int8)(v16 >> 2) & 2 | 0xC;
  if ( (_DWORD)v33 )
  {
    v19 = (_BYTE *)*((_QWORD *)&v33 + 1);
    if ( (v27[0] & 0x400) == 0 || (v29 & 6) != 0 )
    {
      **((_BYTE **)&v33 + 1) = HIBYTE(v13);
      ++v19;
    }
    *v19 = v13;
  }
  NdisAdvanceNetBufferListDataStart(a3, v18, 0, 0);
  v20 = DataOffsetDelta;
  *((_DWORD *)v11 + 11) |= 0x10u;
  NdisRetreatNetBufferListDataStart(a3, v20, 0, 0, 0);
  *((_DWORD *)v11 + 11) |= 0x20u;
  *((_DWORD *)v11 + 30) = v20;
  *((_QWORD *)v11 + 12) = a3;
  *((_QWORD *)v11 + 7) = v17;
  for ( i = a3->FirstNetBuffer; i; i = (struct _NET_BUFFER *)i->Link.Alignment )
  {
    DataBuffer = NdisGetDataBuffer(i, v20, 0, 1u, 0);
    if ( DataBuffer )
    {
      memmove(DataBuffer, Src, v20);
    }
    else
    {
      CurrentMdlOffset = i->CurrentMdlOffset;
      CurrentMdl = i->CurrentMdl;
      v26 = 0;
      RtlCopyKernelBufferToMdl(Src, CurrentMdl, CurrentMdlOffset, v20, &v26);
    }
  }
  return ((__int64 (__fastcall *)(char *))v17[14])(v11 + 16);
}

```

## disassembly

```asm
0x140003970  push    rbx
0x140003972  push    rbp
0x140003973  push    rsi
0x140003974  push    rdi
0x140003975  push    r12
0x140003977  push    r13
0x140003979  push    r15
0x14000397b  sub     rsp, 120h
0x140003982  mov     rax, cs:__security_cookie
0x140003989  xor     rax, rsp
0x14000398c  mov     [rsp+158h+var_48], rax
0x140003994  xor     r12d, r12d
0x140003997  xorps   xmm0, xmm0
0x14000399a  xorps   xmm1, xmm1
0x14000399d  mov     [rsp+158h+DataOffsetDelta], r12d
0x1400039a2  mov     r13, rcx
0x1400039a5  movdqa  [rsp+158h+var_108], xmm0
0x1400039ab  mov     rcx, [r8+10h]
0x1400039af  mov     rsi, r9
0x1400039b2  mov     rbp, r8
0x1400039b5  movdqa  [rsp+158h+var_F8], xmm1
0x1400039bb  mov     r15, rdx
0x1400039be  movdqa  [rsp+158h+var_E8], xmm0
0x1400039c4  movdqa  [rsp+158h+var_D8], xmm1
0x1400039cd  movzx   edi, word ptr [rcx+0Ah]
0x1400039d1  add     rdi, rcx
0x1400039d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400039db  lea     rax, WPP_GLOBAL_Control
0x1400039e2  cmp     rcx, rax
0x1400039e5  jz      short loc_1400039F2
0x1400039e7  mov     eax, [rcx+2Ch]
0x1400039ea  test    al, 8
0x1400039ec  jnz     loc_140003BD4
0x1400039f2  mov     [rdi+48h], r13
0x1400039f6  mov     ecx, 0ABh
0x1400039fb  mov     ebx, [r13+68h]
0x1400039ff  mov     eax, ebx
0x140003a01  movzx   r15d, word ptr [r15+0D6h]
0x140003a09  and     eax, 0FFFFFFF8h
0x140003a0c  or      eax, 8
0x140003a0f  cmp     r15w, cx
0x140003a13  cmovz   ebx, eax
0x140003a16  mov     rax, [rsi]
0x140003a19  cmp     [rax+8], rsi
0x140003a1d  jnz     loc_140003C15
0x140003a23  mov     rcx, [rax]
0x140003a26  cmp     [rcx+8], rax
0x140003a2a  jnz     loc_140003C15
0x140003a30  mov     [rsi], rcx
0x140003a33  lea     rdx, [rsp+158h+Src]
0x140003a3b  mov     [rcx+8], rsi
0x140003a3f  or      ebx, 10h
0x140003a42  mov     [rsp+158h+arg_0], r14
0x140003a4a  lea     rcx, [rsp+158h+var_118]
0x140003a4f  lea     r14, [rax-0F0h]
0x140003a56  mov     [rsp+158h+var_10C], ebx
0x140003a5a  mov     eax, [r14+120h]
0x140003a61  mov     [rsp+158h+var_118], eax
0x140003a65  mov     eax, [rsp+158h+arg_28]
0x140003a6c  mov     [rsp+158h+var_114], eax
0x140003a70  call    BuildLinkHeader
0x140003a75  cmp     cs:qword_14001E2D8, r12
0x140003a7c  jnz     loc_140003C05
0x140003a82  cmp     cs:gbEnablePacketCapture, r12b
0x140003a89  jnz     loc_140003BF8
0x140003a8f  shr     ebx, 2
0x140003a92  not     ebx
0x140003a94  and     ebx, 2
0x140003a97  or      ebx, 0Ch
0x140003a9a  cmp     dword ptr [rsp+158h+var_D8], r12d
0x140003aa2  jz      short loc_140003ACA
0x140003aa4  test    [rsp+158h+var_118], 400h
0x140003aac  mov     rcx, qword ptr [rsp+158h+var_D8+8]
0x140003ab4  jnz     loc_140003B94
0x140003aba  movzx   eax, r15w
0x140003abe  shr     ax, 8
0x140003ac2  mov     [rcx], al
0x140003ac4  inc     rcx
0x140003ac7  mov     [rcx], r15b
0x140003aca  xor     r9d, r9d; FreeMdlMdlHandler
0x140003acd  xor     r8d, r8d; FreeMdl
0x140003ad0  mov     edx, ebx; DataOffsetDelta
0x140003ad2  mov     rcx, rbp; NetBufferList
0x140003ad5  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x140003adc  nop     dword ptr [rax+rax+00h]
0x140003ae1  mov     esi, [rsp+158h+DataOffsetDelta]
0x140003ae5  xor     r9d, r9d; AllocateMdlHandler
0x140003ae8  or      dword ptr [rdi+2Ch], 10h
0x140003aec  mov     edx, esi; DataOffsetDelta
0x140003aee  xor     r8d, r8d; DataBackFill
0x140003af1  mov     [rsp+158h+FreeMdlHandler], r12; FreeMdlHandler
0x140003af6  mov     rcx, rbp; NetBufferList
0x140003af9  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x140003b00  nop     dword ptr [rax+rax+00h]
0x140003b05  or      dword ptr [rdi+2Ch], 20h
0x140003b09  mov     [rdi+78h], esi
0x140003b0c  mov     [rdi+60h], rbp
0x140003b10  mov     [rdi+38h], r14
0x140003b14  mov     rbx, [rbp+8]
0x140003b18  test    rbx, rbx
0x140003b1b  jz      short loc_140003B5C
0x140003b1d  mov     r9d, 1; AlignMultiple
0x140003b23  mov     dword ptr [rsp+158h+FreeMdlHandler], r12d; AlignOffset
0x140003b28  xor     r8d, r8d; Storage
0x140003b2b  mov     edx, esi; BytesNeeded
0x140003b2d  mov     rcx, rbx; NetBuffer
0x140003b30  call    cs:__imp_NdisGetDataBuffer
0x140003b37  nop     dword ptr [rax+rax+00h]
0x140003b3c  test    rax, rax
0x140003b3f  jz      short loc_140003BA4
0x140003b41  mov     r8, rsi; Size
0x140003b44  lea     rdx, [rsp+158h+Src]; Src
0x140003b4c  mov     rcx, rax; void *
0x140003b4f  call    memmove
0x140003b54  mov     rbx, [rbx]
0x140003b57  test    rbx, rbx
0x140003b5a  jnz     short loc_140003B1D
0x140003b5c  mov     rax, [r14+70h]
0x140003b60  lea     rcx, [rdi+10h]
0x140003b64  call    _guard_dispatch_icall
0x140003b69  mov     r14, [rsp+158h+arg_0]
0x140003b71  mov     rcx, [rsp+158h+var_48]
0x140003b79  xor     rcx, rsp; StackCookie
0x140003b7c  call    __security_check_cookie
0x140003b81  add     rsp, 120h
0x140003b88  pop     r15
0x140003b8a  pop     r13
0x140003b8c  pop     r12
0x140003b8e  pop     rdi
0x140003b8f  pop     rsi
0x140003b90  pop     rbp
0x140003b91  pop     rbx
0x140003b92  retn
0x140003b94  test    byte ptr [rsp+158h+var_10C], 6
0x140003b99  jz      loc_140003AC7
0x140003b9f  jmp     loc_140003ABA
0x140003ba4  mov     r8d, [rbx+10h]
0x140003ba8  lea     rax, [rsp+158h+var_128]
0x140003bad  mov     rdx, [rbx+8]
0x140003bb1  lea     rcx, [rsp+158h+Src]
0x140003bb9  mov     r9, rsi
0x140003bbc  mov     [rsp+158h+FreeMdlHandler], rax
0x140003bc1  mov     [rsp+158h+var_128], r12
0x140003bc6  call    cs:__imp_RtlCopyKernelBufferToMdl
0x140003bcd  nop     dword ptr [rax+rax+00h]
0x140003bd2  jmp     short loc_140003B54
0x140003bd4  cmp     byte ptr [rcx+29h], 5
0x140003bd8  jb      loc_1400039F2
0x140003bde  mov     rcx, [rcx+18h]
0x140003be2  lea     r8, WPP_8fab404a276b37b5b154f85d9d785092_Traceguids
0x140003be9  mov     edx, 1Ch
0x140003bee  call    WPP_SF_
0x140003bf3  jmp     loc_1400039F2
0x140003bf8  cmp     [r13+984h], r12b
0x140003bff  jz      loc_140003A8F
0x140003c05  mov     rdx, rbp
0x140003c08  mov     rcx, r14
0x140003c0b  call    IndicatePromiscuousSendPacket
0x140003c10  jmp     loc_140003A8F
0x140003c15  mov     ecx, 3
0x140003c1a  int     29h; Win8: RtlFailFast(ecx)
```
