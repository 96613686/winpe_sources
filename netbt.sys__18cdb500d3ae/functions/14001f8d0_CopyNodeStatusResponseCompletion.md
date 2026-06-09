# CopyNodeStatusResponseCompletion

- ea: `0x14001f8d0`
- end: `0x14001fc5a`
- name: `CopyNodeStatusResponseCompletion`
- size: `906`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140004880`
- `0x140006900`
- `0x14000b810`
- `0x14000e268`
- `0x14001f8d0`
- `0x14001fc60`
- `0x140031440`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fae0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001fae0`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001fb39`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001fb39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fac7`
- `ntoskrnl!ExAllocatePool2` at `0x14001f96d`
- `ntoskrnl!ExAllocatePool2` at `0x14001f96d`
- `TDI!TdiCopyBufferToMdl` at `0x14001faa6`
- `TDI!TdiCopyBufferToMdl` at `0x14001faa6`

## pseudocode

```c
void __fastcall CopyNodeStatusResponseCompletion(__int64 a1, NTSTATUS a2)
{
  unsigned __int64 v2; // r12
  NTSTATUS v3; // esi
  __int64 v4; // r14
  IRP *v6; // rbp
  __int64 v7; // r15
  ULONG v8; // r13d
  _WORD *Pool2; // rax
  _WORD *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rax
  char *v13; // r15
  unsigned int v14; // r12d
  __int64 i; // rsi
  char v16; // dl
  __int64 v17; // r8
  char v18; // al
  char v19; // al
  unsigned int ByteCount; // ecx
  KIRQL v21; // di
  __int64 v22; // rcx
  unsigned int v23; // r8d
  NTSTATUS v24; // edx
  __int64 v25; // [rsp+40h] [rbp-58h]
  ULONG BytesCopied; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v27; // [rsp+A8h] [rbp+10h]
  unsigned int v28; // [rsp+B0h] [rbp+18h]
  unsigned int v29; // [rsp+B8h] [rbp+20h]

  v2 = *(unsigned int *)(a1 + 244);
  v3 = a2;
  v4 = *(_QWORD *)(a1 + 104);
  v6 = *(IRP **)(a1 + 176);
  BytesCopied = 0;
  v25 = *(_QWORD *)(a1 + 32);
  v29 = v2;
  *(_DWORD *)(a1 + 244) = 0;
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  if ( !a2 )
  {
    v7 = *(unsigned __int8 *)(v4 + 10);
    v28 = v7;
    v8 = 18 * v7 + 60;
    v27 = *(_DWORD *)(a1 + 208);
    Pool2 = (_WORD *)ExAllocatePool2(64, v8, 963928654);
    v10 = Pool2;
    if ( Pool2 )
    {
      memset(Pool2, 0, v8);
      if ( v2 >= 18 * v7 + 46 )
      {
        *(_DWORD *)v10 = *(_DWORD *)(v4 + 18 * v7 + 11);
        v10[2] = *(_WORD *)(v4 + 18 * v7 + 15);
      }
      v12 = (unsigned int)(18 * v7 + 57);
      *((_BYTE *)v10 + 6) = 3;
      *((_BYTE *)v10 + 8) = -2;
      if ( (unsigned int)v12 <= (unsigned int)v2 )
        v10[27] = __ROR2__(*(unsigned __int8 *)(v12 + v4 - 2), 8);
      v13 = (char *)(v10 + 30);
      LOBYTE(v11) = 1;
      v14 = 11;
      *(_QWORD *)(a1 + 32) = GetDeviceFromInterface(_byteswap_ulong(v27), v25, v11);
      for ( i = 0; (unsigned int)i < v28; i = (unsigned int)(i + 1) )
      {
        v14 += 18;
        if ( v14 > v29 )
        {
          v3 = -1073741823;
          goto LABEL_16;
        }
        ++v10[29];
        v16 = *(_BYTE *)(v4 + 18 * i + 27);
        v17 = v4 + 11 + 18 * i;
        v18 = v16 & 0x10;
        if ( (v16 & 8) != 0 )
          v19 = (v18 != 0) + 6;
        else
          v19 = (v18 != 0) + 4;
        v13[17] = v19 | (*(char *)(v4 + 18 * i + 27) >> 7) & 0x80;
        v13[16] = i + 1;
        *(_OWORD *)v13 = *(_OWORD *)v17;
        if ( *(_BYTE *)(v17 + 15) == 32 && (v16 & 0x18) == 0 )
          NbtAddEntryToRemoteHashTable(*(_QWORD *)(a1 + 32), 256, v17, v27, dword_1400395F8 / 0x3E8u, 0);
        v13 += 18;
      }
      ByteCount = v6->MdlAddress->ByteCount;
      if ( v8 > ByteCount )
      {
        if ( ByteCount >= 0x3C )
          v10[29] = (unsigned __int16)(ByteCount - 60) / 0x12u;
        else
          v10[29] = 0;
      }
      v3 = TdiCopyBufferToMdl(v10, 0, v8, v6->MdlAddress, 0, &BytesCopied);
      v6->IoStatus.Information = BytesCopied;
      v6->IoStatus.Status = v3;
LABEL_16:
      ExFreePoolWithTag(v10, 0);
    }
    else
    {
      v3 = -1073741670;
    }
  }
  v21 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  if ( v6 )
  {
    if ( !v3 || v3 == -2147483643 )
    {
      v23 = -1;
      v24 = v3;
    }
    else
    {
      v23 = 0;
      v24 = -1073741643;
    }
    NTIoComplete(v6, v24, v23);
  }
  v22 = *(_QWORD *)(a1 + 32);
  if ( v22 )
    NBT_DEREFERENCE_DEVICE(v22, 10);
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(a1 + 20),
      84,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a1,
      *(_DWORD *)(a1 + 20),
      *(_DWORD *)(a1 + 20) - 1,
      149,
      (__int64)"minio\\netbt\\sys\\inbound.c");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
    FreeTracker(a1, 4);
  KeReleaseSpinLock(&SpinLock, v21);
}

```

## disassembly

```asm
0x14001f8d0  mov     rax, rsp
0x14001f8d3  push    rbx
0x14001f8d4  push    rbp
0x14001f8d5  push    rsi
0x14001f8d6  push    rdi
0x14001f8d7  push    r12
0x14001f8d9  push    r13
0x14001f8db  push    r14
0x14001f8dd  push    r15
0x14001f8df  sub     rsp, 58h
0x14001f8e3  mov     r12d, [rcx+0F4h]
0x14001f8ea  mov     esi, edx
0x14001f8ec  mov     r14, [rcx+68h]
0x14001f8f0  mov     rbx, rcx
0x14001f8f3  mov     rbp, [rcx+0B0h]
0x14001f8fa  mov     r15d, 1
0x14001f900  mov     dword ptr [rax+8], 0
0x14001f907  mov     rax, [rcx+20h]
0x14001f90b  mov     [rsp+98h+var_58], rax
0x14001f910  mov     [rsp+98h+arg_18], r12d
0x14001f918  mov     dword ptr [rcx+0F4h], 0
0x14001f922  mov     qword ptr [rcx+68h], 0
0x14001f92a  mov     qword ptr [rcx+20h], 0
0x14001f932  test    edx, edx
0x14001f934  jnz     loc_14001FAD9
0x14001f93a  movzx   r15d, byte ptr [r14+0Ah]
0x14001f93f  mov     r8d, 3974624Eh
0x14001f945  mov     [rsp+98h+arg_10], r15d
0x14001f94d  lea     eax, [r15+r15*8]
0x14001f951  lea     esi, [rax+rax]
0x14001f954  mov     eax, [rcx+0D0h]
0x14001f95a  lea     r13d, [rsi+3Ch]
0x14001f95e  mov     [rsp+98h+arg_8], eax
0x14001f965  mov     edx, r13d
0x14001f968  mov     ecx, 40h ; '@'
0x14001f96d  call    cs:__imp_ExAllocatePool2
0x14001f974  nop     dword ptr [rax+rax+00h]
0x14001f979  mov     rdi, rax
0x14001f97c  test    rax, rax
0x14001f97f  jz      loc_14001FBF9
0x14001f985  mov     r8d, r13d; Size
0x14001f988  xor     edx, edx; Val
0x14001f98a  mov     rcx, rax; void *
0x14001f98d  call    memset
0x14001f992  lea     rdx, [r15+r15*8]
0x14001f996  lea     rcx, ds:2Eh[rdx*2]
0x14001f99e  cmp     r12, rcx
0x14001f9a1  jb      short loc_14001F9B4
0x14001f9a3  mov     eax, [r14+rdx*2+0Bh]
0x14001f9a8  mov     [rdi], eax
0x14001f9aa  movzx   eax, word ptr [r14+rdx*2+0Fh]
0x14001f9b0  mov     [rdi+4], ax
0x14001f9b4  lea     eax, [rsi+39h]
0x14001f9b7  mov     byte ptr [rdi+6], 3
0x14001f9bb  mov     byte ptr [rdi+8], 0FEh
0x14001f9bf  cmp     eax, r12d
0x14001f9c2  ja      short loc_14001F9D2
0x14001f9c4  movzx   ecx, byte ptr [rax+r14-2]
0x14001f9ca  ror     cx, 8
0x14001f9ce  mov     [rdi+36h], cx
0x14001f9d2  mov     ecx, [rsp+98h+arg_8]
0x14001f9d9  lea     r15, [rdi+3Ch]
0x14001f9dd  mov     rdx, [rsp+98h+var_58]
0x14001f9e2  mov     r8b, 1
0x14001f9e5  bswap   ecx
0x14001f9e7  mov     r12d, 0Bh
0x14001f9ed  call    GetDeviceFromInterface
0x14001f9f2  mov     [rbx+20h], rax
0x14001f9f6  lea     r9d, [r12-0Ah]
0x14001f9fb  xor     esi, esi
0x14001f9fd  cmp     esi, [rsp+98h+arg_10]
0x14001fa04  jnb     short loc_14001FA75
0x14001fa06  add     r12d, 12h
0x14001fa0a  cmp     r12d, [rsp+98h+arg_18]
0x14001fa12  ja      loc_14001FC03
0x14001fa18  add     [rdi+3Ah], r9w
0x14001fa1d  lea     rcx, [rsi+rsi*8]
0x14001fa21  mov     dl, [r14+rcx*2+1Bh]
0x14001fa26  lea     r8, [r14+0Bh]
0x14001fa2a  lea     r8, [r8+rcx*2]
0x14001fa2e  mov     al, dl
0x14001fa30  mov     cl, dl
0x14001fa32  and     al, 10h
0x14001fa34  sar     cl, 7
0x14001fa37  and     cl, 80h
0x14001fa3a  test    dl, 8
0x14001fa3d  jnz     loc_14001FB6F
0x14001fa43  test    al, al
0x14001fa45  setnz   al
0x14001fa48  add     al, 4
0x14001fa4a  or      cl, al
0x14001fa4c  lea     eax, [r9+rsi]
0x14001fa50  mov     [r15+11h], cl
0x14001fa54  mov     [r15+10h], al
0x14001fa58  movups  xmm0, xmmword ptr [r8]
0x14001fa5c  movdqu  xmmword ptr [r15], xmm0
0x14001fa61  cmp     byte ptr [r8+0Fh], 20h ; ' '
0x14001fa66  jz      loc_14001FB7B
0x14001fa6c  add     r15, 12h
0x14001fa70  add     esi, r9d
0x14001fa73  jmp     short loc_14001F9FD
0x14001fa75  mov     rax, [rbp+8]
0x14001fa79  mov     ecx, [rax+28h]
0x14001fa7c  cmp     r13d, ecx
0x14001fa7f  ja      loc_14001FC0D
0x14001fa85  mov     r9, [rbp+8]; DestinationMdlChain
0x14001fa89  lea     rax, [rsp+98h+arg_0]
0x14001fa91  mov     [rsp+98h+BytesCopied], rax; BytesCopied
0x14001fa96  mov     r8d, r13d; SourceBytesToCopy
0x14001fa99  xor     edx, edx; SourceOffset
0x14001fa9b  mov     [rsp+98h+DestinationOffset], 0; DestinationOffset
0x14001faa3  mov     rcx, rdi; SourceBuffer
0x14001faa6  call    cs:__imp_TdiCopyBufferToMdl
0x14001faad  nop     dword ptr [rax+rax+00h]
0x14001fab2  mov     esi, eax
0x14001fab4  mov     eax, [rsp+98h+arg_0]
0x14001fabb  mov     [rbp+38h], rax
0x14001fabf  mov     [rbp+30h], esi
0x14001fac2  xor     edx, edx; Tag
0x14001fac4  mov     rcx, rdi; P
0x14001fac7  call    cs:__imp_ExFreePoolWithTag
0x14001face  nop     dword ptr [rax+rax+00h]
0x14001fad3  mov     r15d, 1
0x14001fad9  lea     rcx, SpinLock; SpinLock
0x14001fae0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001fae7  nop     dword ptr [rax+rax+00h]
0x14001faec  mov     dil, al
0x14001faef  test    rbp, rbp
0x14001faf2  jnz     short loc_14001FB57
0x14001faf4  mov     rcx, [rbx+20h]
0x14001faf8  test    rcx, rcx
0x14001fafb  jz      short loc_14001FB0A
0x14001fafd  mov     r8b, r15b
0x14001fb00  mov     edx, 0Ah
0x14001fb05  call    NBT_DEREFERENCE_DEVICE
0x14001fb0a  test    byte ptr cs:xmmword_140038420+9, 40h
0x14001fb11  jnz     loc_14001FBBE
0x14001fb17  or      eax, 0FFFFFFFFh
0x14001fb1a  lock xadd [rbx+14h], eax
0x14001fb1f  cmp     eax, 1
0x14001fb22  jnz     short loc_14001FB2F
0x14001fb24  lea     edx, [rax+3]
0x14001fb27  mov     rcx, rbx
0x14001fb2a  call    FreeTracker
0x14001fb2f  mov     dl, dil; NewIrql
0x14001fb32  lea     rcx, SpinLock; SpinLock
0x14001fb39  call    cs:__imp_KeReleaseSpinLock
0x14001fb40  nop     dword ptr [rax+rax+00h]
0x14001fb45  add     rsp, 58h
0x14001fb49  pop     r15
0x14001fb4b  pop     r14
0x14001fb4d  pop     r13
0x14001fb4f  pop     r12
0x14001fb51  pop     rdi
0x14001fb52  pop     rsi
0x14001fb53  pop     rbp
0x14001fb54  pop     rbx
0x14001fb55  retn
0x14001fb57  test    esi, esi
0x14001fb59  jnz     loc_14001FC41
0x14001fb5f  or      r8d, 0FFFFFFFFh
0x14001fb63  mov     edx, esi
0x14001fb65  mov     rcx, rbp; Irp
0x14001fb68  call    NTIoComplete
0x14001fb6d  jmp     short loc_14001FAF4
0x14001fb6f  test    al, al
0x14001fb71  setnz   al
0x14001fb74  add     al, 6
0x14001fb76  jmp     loc_14001FA4A
0x14001fb7b  test    dl, 18h
0x14001fb7e  jnz     loc_14001FA6C
0x14001fb84  mov     r9d, [rsp+98h+arg_8]
0x14001fb8c  mov     eax, 10624DD3h
0x14001fb91  mul     cs:dword_1400395F8
0x14001fb97  mov     byte ptr [rsp+98h+BytesCopied], 0
0x14001fb9c  mov     ecx, edx
0x14001fb9e  mov     edx, 100h
0x14001fba3  shr     ecx, 6
0x14001fba6  mov     [rsp+98h+DestinationOffset], ecx
0x14001fbaa  mov     rcx, [rbx+20h]
0x14001fbae  call    NbtAddEntryToRemoteHashTable
0x14001fbb3  mov     r9d, 1
0x14001fbb9  jmp     loc_14001FA6C
0x14001fbbe  mov     ecx, [rbx+14h]
0x14001fbc1  lea     r8, aMinioNetbtSysI; "minio\\netbt\\sys\\inbound.c"
0x14001fbc8  mov     [rsp+98h+var_60], r8
0x14001fbcd  mov     edx, 54h ; 'T'
0x14001fbd2  mov     [rsp+98h+var_68], 0C95h
0x14001fbda  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x14001fbe1  mov     r9, rbx
0x14001fbe4  lea     eax, [rcx-1]
0x14001fbe7  mov     dword ptr [rsp+98h+BytesCopied], eax
0x14001fbeb  mov     [rsp+98h+DestinationOffset], ecx
0x14001fbef  call    WPP_SF_qddds
0x14001fbf4  jmp     loc_14001FB17
0x14001fbf9  mov     esi, 0C000009Ah
0x14001fbfe  jmp     loc_14001FAD3
0x14001fc03  mov     esi, 0C0000001h
0x14001fc08  jmp     loc_14001FAC2
0x14001fc0d  mov     eax, 3Ch ; '<'
0x14001fc12  cmp     ecx, eax
0x14001fc14  jnb     short loc_14001FC21
0x14001fc16  xor     eax, eax
0x14001fc18  mov     [rdi+3Ah], ax
0x14001fc1c  jmp     loc_14001FA85
0x14001fc21  sub     cx, ax
0x14001fc24  mov     rax, 0E38E38E38E38E38Fh
0x14001fc2e  movzx   ecx, cx
0x14001fc31  mul     rcx
0x14001fc34  shr     rdx, 4
0x14001fc38  mov     [rdi+3Ah], dx
0x14001fc3c  jmp     loc_14001FA85
0x14001fc41  cmp     esi, 80000005h
0x14001fc47  jz      loc_14001FB5F
0x14001fc4d  xor     r8d, r8d
0x14001fc50  mov     edx, 0C00000B5h
0x14001fc55  jmp     loc_14001FB65
```
