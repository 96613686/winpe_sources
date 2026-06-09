# NdisAllocateNetBufferPool

- ea: `0x14005dee0`
- end: `0x14005e190`
- name: `NdisAllocateNetBufferPool`
- size: `688`
- prototype: `NDIS_HANDLE __stdcall(NDIS_HANDLE NdisHandle, PNET_BUFFER_POOL_PARAMETERS Parameters)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x140191240`

## callees

- `0x1400100f0`
- `0x1400110b0`
- `0x14005dee0`
- `0x14005e4e0`
- `0x14005e7c0`
- `0x140088cc0`
- `0x1400cd75c`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x14005dff5`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e010`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e072`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e091`
- `ntoskrnl!MmSizeOfMdl` at `0x14005dff5`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e010`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e072`
- `ntoskrnl!MmSizeOfMdl` at `0x14005e091`
- `ntoskrnl!RtlGetCallersAddress` at `0x14005df09`
- `ntoskrnl!RtlGetCallersAddress` at `0x14005df09`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e0bb`
- `ntoskrnl!KeInitializeSpinLock` at `0x14005e0bb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e120`
- `ntoskrnl!KeReleaseSpinLock` at `0x14005e120`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e0d9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14005e0d9`

## pseudocode

```c
NDIS_HANDLE __stdcall NdisAllocateNetBufferPool(NDIS_HANDLE NdisHandle, PNET_BUFFER_POOL_PARAMETERS Parameters)
{
  struct PPL_POOL_HANDLE__ *v4; // rbx
  int v5; // edx
  unsigned int v6; // ecx
  int v7; // r8d
  unsigned __int16 v8; // r9
  UCHAR Revision; // al
  bool v10; // r12
  unsigned int Flags; // r12d
  SIZE_T DataSize; // rsi
  int v13; // eax
  char v14; // al
  unsigned __int64 v15; // r15
  struct PPL_POOL_HANDLE__ *Pool; // rax
  unsigned int v17; // esi
  int v18; // edi
  KIRQL v19; // al
  __int64 v20; // rcx
  void *v22; // [rsp+78h] [rbp+10h] BYREF
  PVOID v23; // [rsp+80h] [rbp+18h] BYREF

  v22 = 0;
  v23 = 0;
  v4 = 0;
  RtlGetCallersAddress(&v22, &v23);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      21,
      10,
      (struct _GUID *)&WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids,
      (char)NdisHandle);
  }
  if ( Parameters->Header.Type != 0x80 )
    goto LABEL_20;
  Revision = Parameters->Header.Revision;
  if ( !Revision )
    goto LABEL_20;
  v10 = 0;
  if ( Revision >= 2u )
  {
    Flags = Parameters->Flags;
    if ( (Flags & 0xFFFFFFFE) != 0 )
      ndisBugCheckEx(0x2Du, 5u, Flags, 0);
    v10 = Flags & 1;
  }
  DataSize = Parameters->DataSize;
  v13 = 176;
  if ( !(_DWORD)DataSize )
    goto LABEL_14;
  if ( (unsigned int)DataSize <= 0x100000 )
  {
    v14 = MmSizeOfMdl((PVOID)0xFFF, Parameters->DataSize);
    v13 = DataSize - ((v14 - 1) & 7) + MmSizeOfMdl((PVOID)0xFFF, DataSize) + 183;
LABEL_14:
    v15 = (v13 + 7) & 0xFFFFFFF8;
    Pool = ndisPplCreatePool(v6, v15, Parameters->PoolTag, v8, 0);
    v4 = Pool;
    if ( Pool )
    {
      *(_DWORD *)Pool = 25166092;
      *((_QWORD *)Pool + 5) = NdisHandle;
      *((_DWORD *)Pool + 9) = Parameters->PoolTag;
      if ( Parameters->DataSize )
      {
        *((_DWORD *)Pool + 20) |= 1u;
        *((_DWORD *)Pool + 21) = Parameters->DataSize;
        v17 = Parameters->DataSize;
        v18 = 7 - (((unsigned __int8)MmSizeOfMdl((PVOID)0xFFF, v17) - 1) & 7);
        *((_DWORD *)v4 + 22) = v18 + MmSizeOfMdl((PVOID)0xFFF, v17);
      }
      ndisPplConfigureVerifier((struct _NDIS_POOL_HEADER *)v4, v22, v10);
      *((_DWORD *)v4 + 8) = v15;
      KeInitializeSpinLock((PKSPIN_LOCK)v4 + 7);
      *((_QWORD *)v4 + 3) = (char *)v4 + 16;
      *((_QWORD *)v4 + 2) = (char *)v4 + 16;
      v19 = KeAcquireSpinLockRaiseToDpc(&qword_140122888);
      v20 = qword_1401231F0;
      if ( *(__int64 **)(qword_1401231F0 + 8) != &qword_1401231F0 )
        __fastfail(3u);
      *((_QWORD *)v4 + 8) = qword_1401231F0;
      *((_QWORD *)v4 + 9) = &qword_1401231F0;
      *(_QWORD *)(v20 + 8) = (char *)v4 + 64;
      qword_1401231F0 = (__int64)v4 + 64;
      KeReleaseSpinLock(&qword_140122888, v19);
      *((_QWORD *)v4 + 6) = v22;
    }
    goto LABEL_20;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
    return v4;
  WPP_RECORDER_SF_PP(
    *((_QWORD *)WPP_GLOBAL_Control + 8),
    v5,
    v7,
    11,
    (__int64)&WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids,
    Parameters->DataSize);
LABEL_20:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      21,
      12,
      (struct _GUID *)&WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids,
      (char)NdisHandle,
      (char)v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14005dee0  mov     r11, rsp
0x14005dee3  push    rbx
0x14005dee4  push    rdi
0x14005dee5  push    r13
0x14005dee7  push    r14
0x14005dee9  push    r15
0x14005deeb  sub     rsp, 40h
0x14005deef  xor     eax, eax
0x14005def1  mov     rdi, rdx
0x14005def4  mov     r14, rcx
0x14005def7  mov     [r11+10h], rax
0x14005defb  lea     rdx, [r11+18h]; CallersCaller
0x14005deff  mov     [r11+18h], rax
0x14005df03  lea     rcx, [r11+10h]; CallersAddress
0x14005df07  mov     ebx, eax
0x14005df09  call    cs:__imp_RtlGetCallersAddress
0x14005df10  nop     dword ptr [rax+rax+00h]
0x14005df15  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005df1c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14005df23  lea     r15, WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids
0x14005df2a  jz      short loc_14005DF54
0x14005df2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005df33  mov     r9d, 0Ah; int
0x14005df39  mov     qword ptr [rsp+68h+var_40], r14; char
0x14005df3e  mov     r8d, 15h; int
0x14005df44  mov     dl, 4; int
0x14005df46  mov     [rsp+68h+var_48], r15; struct _GUID *
0x14005df4b  mov     rcx, [rcx+40h]; int
0x14005df4f  call    WPP_RECORDER_SF_q
0x14005df54  cmp     byte ptr [rdi], 80h
0x14005df57  mov     [rsp+68h+arg_0], rsi
0x14005df5c  mov     [rsp+68h+arg_18], r12
0x14005df64  jnz     loc_14005E13C
0x14005df6a  movzx   eax, byte ptr [rdi+1]
0x14005df6e  cmp     al, 1
0x14005df70  jb      loc_14005E13C
0x14005df76  xor     r12b, r12b
0x14005df79  cmp     al, 2
0x14005df7b  jb      short loc_14005DFA4
0x14005df7d  mov     r12d, [rdi+0Ch]
0x14005df81  test    r12d, 0FFFFFFFEh
0x14005df88  jz      short loc_14005DFA0
0x14005df8a  mov     r8d, r12d; BugCheckParameter3
0x14005df8d  xor     r9d, r9d; BugCheckParameter4
0x14005df90  mov     edx, 5; BugCheckParameter2
0x14005df95  mov     ecx, 2Dh ; '-'; BugCheckParameter1
0x14005df9a  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x14005dfa0  and     r12b, 1
0x14005dfa4  mov     esi, [rdi+8]
0x14005dfa7  mov     eax, 0B0h
0x14005dfac  test    esi, esi
0x14005dfae  jz      short loc_14005E023
0x14005dfb0  cmp     esi, 100000h
0x14005dfb6  jbe     short loc_14005DFEA
0x14005dfb8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14005dfbf  jz      loc_14005E172
0x14005dfc5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dfcc  mov     r9d, 0Bh
0x14005dfd2  mov     qword ptr [rsp+68h+var_40], rsi
0x14005dfd7  mov     [rsp+68h+var_48], r15
0x14005dfdc  mov     rcx, [rcx+40h]
0x14005dfe0  call    WPP_RECORDER_SF_PP
0x14005dfe5  jmp     loc_14005E13C
0x14005dfea  mov     rdx, rsi; Length
0x14005dfed  mov     ecx, 0FFFh; Base
0x14005dff2  mov     rbx, rsi
0x14005dff5  call    cs:__imp_MmSizeOfMdl
0x14005dffc  nop     dword ptr [rax+rax+00h]
0x14005e001  mov     rdx, rbx; Length
0x14005e004  mov     ecx, 0FFFh; Base
0x14005e009  dec     eax
0x14005e00b  and     eax, 7
0x14005e00e  sub     esi, eax
0x14005e010  call    cs:__imp_MmSizeOfMdl
0x14005e017  nop     dword ptr [rax+rax+00h]
0x14005e01c  add     eax, 0B7h
0x14005e021  add     eax, esi
0x14005e023  mov     r8d, [rdi+4]; unsigned int
0x14005e027  add     eax, 7
0x14005e02a  and     eax, 0FFFFFFF8h
0x14005e02d  mov     byte ptr [rsp+68h+var_48], 0; unsigned __int8
0x14005e032  mov     edx, eax; unsigned __int64
0x14005e034  mov     r15d, eax
0x14005e037  call    ?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z; ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)
0x14005e03c  mov     rbx, rax
0x14005e03f  test    rax, rax
0x14005e042  jz      loc_14005E135
0x14005e048  mov     dword ptr [rax], 180010Ch
0x14005e04e  mov     [rax+28h], r14
0x14005e052  mov     eax, [rdi+4]
0x14005e055  mov     [rbx+24h], eax
0x14005e058  cmp     dword ptr [rdi+8], 0
0x14005e05c  jz      short loc_14005E0A2
0x14005e05e  or      dword ptr [rbx+50h], 1
0x14005e062  mov     ecx, 0FFFh; Base
0x14005e067  mov     eax, [rdi+8]
0x14005e06a  mov     [rbx+54h], eax
0x14005e06d  mov     esi, [rdi+8]
0x14005e070  mov     edx, esi; Length
0x14005e072  call    cs:__imp_MmSizeOfMdl
0x14005e079  nop     dword ptr [rax+rax+00h]
0x14005e07e  mov     edi, 7
0x14005e083  mov     edx, esi; Length
0x14005e085  dec     eax
0x14005e087  mov     ecx, 0FFFh; Base
0x14005e08c  and     eax, 7
0x14005e08f  sub     edi, eax
0x14005e091  call    cs:__imp_MmSizeOfMdl
0x14005e098  nop     dword ptr [rax+rax+00h]
0x14005e09d  add     eax, edi
0x14005e09f  mov     [rbx+58h], eax
0x14005e0a2  mov     rdx, [rsp+68h+arg_8]; void *
0x14005e0a7  movzx   r8d, r12b; bool
0x14005e0ab  mov     rcx, rbx; struct _NDIS_POOL_HEADER *
0x14005e0ae  call    ?ndisPplConfigureVerifier@@YAXPEAU_NDIS_POOL_HEADER@@PEAX_N@Z; ndisPplConfigureVerifier(_NDIS_POOL_HEADER *,void *,bool)
0x14005e0b3  lea     rcx, [rbx+38h]; SpinLock
0x14005e0b7  mov     [rbx+20h], r15d
0x14005e0bb  call    cs:__imp_KeInitializeSpinLock
0x14005e0c2  nop     dword ptr [rax+rax+00h]
0x14005e0c7  lea     rax, [rbx+10h]
0x14005e0cb  lea     rcx, qword_140122888; SpinLock
0x14005e0d2  mov     [rax+8], rax
0x14005e0d6  mov     [rax], rax
0x14005e0d9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14005e0e0  nop     dword ptr [rax+rax+00h]
0x14005e0e5  mov     rcx, cs:qword_1401231F0
0x14005e0ec  lea     r8, qword_1401231F0
0x14005e0f3  movzx   edx, al; NewIrql
0x14005e0f6  cmp     [rcx+8], r8
0x14005e0fa  jz      short loc_14005E103
0x14005e0fc  mov     ecx, 3
0x14005e101  int     29h; Win8: RtlFailFast(ecx)
0x14005e103  lea     rax, [rbx+40h]
0x14005e107  mov     [rax], rcx
0x14005e10a  mov     [rax+8], r8
0x14005e10e  mov     [rcx+8], rax
0x14005e112  lea     rcx, qword_140122888; SpinLock
0x14005e119  mov     cs:qword_1401231F0, rax
0x14005e120  call    cs:__imp_KeReleaseSpinLock
0x14005e127  nop     dword ptr [rax+rax+00h]
0x14005e12c  mov     rax, [rsp+68h+arg_8]
0x14005e131  mov     [rbx+30h], rax
0x14005e135  lea     r15, WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids
0x14005e13c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x14005e143  jz      short loc_14005E172
0x14005e145  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e14c  mov     r9d, 0Ch; int
0x14005e152  mov     qword ptr [rsp+68h+var_38], rbx; char
0x14005e157  mov     r8d, 15h; int
0x14005e15d  mov     qword ptr [rsp+68h+var_40], r14; char
0x14005e162  mov     dl, 4; int
0x14005e164  mov     [rsp+68h+var_48], r15; struct _GUID *
0x14005e169  mov     rcx, [rcx+40h]; int
0x14005e16d  call    WPP_RECORDER_SF_qq
0x14005e172  mov     r12, [rsp+68h+arg_18]
0x14005e17a  mov     rax, rbx
0x14005e17d  mov     rsi, [rsp+68h+arg_0]
0x14005e182  add     rsp, 40h
0x14005e186  pop     r15
0x14005e188  pop     r14
0x14005e18a  pop     r13
0x14005e18c  pop     rdi
0x14005e18d  pop     rbx
0x14005e18e  retn
```
