# NdisAllocateNetBufferPool

- ea: `0x1400597f0`
- end: `0x140059aa0`
- name: `NdisAllocateNetBufferPool`
- size: `688`
- prototype: `NDIS_HANDLE __stdcall(NDIS_HANDLE NdisHandle, PNET_BUFFER_POOL_PARAMETERS Parameters)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x14018b240`

## callees

- `0x14001c050`
- `0x14001cf50`
- `0x1400597f0`
- `0x140059df0`
- `0x14005a0d0`
- `0x140083a40`
- `0x1400c85ac`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140059905`
- `ntoskrnl!MmSizeOfMdl` at `0x140059920`
- `ntoskrnl!MmSizeOfMdl` at `0x140059982`
- `ntoskrnl!MmSizeOfMdl` at `0x1400599a1`
- `ntoskrnl!MmSizeOfMdl` at `0x140059905`
- `ntoskrnl!MmSizeOfMdl` at `0x140059920`
- `ntoskrnl!MmSizeOfMdl` at `0x140059982`
- `ntoskrnl!MmSizeOfMdl` at `0x1400599a1`
- `ntoskrnl!RtlGetCallersAddress` at `0x140059819`
- `ntoskrnl!RtlGetCallersAddress` at `0x140059819`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400599cb`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400599cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059a30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140059a30`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400599e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400599e9`

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
      v19 = KeAcquireSpinLockRaiseToDpc(&qword_14011C888);
      v20 = qword_14011D1F0;
      if ( *(__int64 **)(qword_14011D1F0 + 8) != &qword_14011D1F0 )
        __fastfail(3u);
      *((_QWORD *)v4 + 8) = qword_14011D1F0;
      *((_QWORD *)v4 + 9) = &qword_14011D1F0;
      *(_QWORD *)(v20 + 8) = (char *)v4 + 64;
      qword_14011D1F0 = (__int64)v4 + 64;
      KeReleaseSpinLock(&qword_14011C888, v19);
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
0x1400597f0  mov     r11, rsp
0x1400597f3  push    rbx
0x1400597f4  push    rdi
0x1400597f5  push    r13
0x1400597f7  push    r14
0x1400597f9  push    r15
0x1400597fb  sub     rsp, 40h
0x1400597ff  xor     eax, eax
0x140059801  mov     rdi, rdx
0x140059804  mov     r14, rcx
0x140059807  mov     [r11+10h], rax
0x14005980b  lea     rdx, [r11+18h]; CallersCaller
0x14005980f  mov     [r11+18h], rax
0x140059813  lea     rcx, [r11+10h]; CallersAddress
0x140059817  mov     ebx, eax
0x140059819  call    cs:__imp_RtlGetCallersAddress
0x140059820  nop     dword ptr [rax+rax+00h]
0x140059825  lea     r13, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14005982c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140059833  lea     r15, WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids
0x14005983a  jz      short loc_140059864
0x14005983c  mov     rcx, cs:WPP_GLOBAL_Control
0x140059843  mov     r9d, 0Ah; int
0x140059849  mov     qword ptr [rsp+68h+var_40], r14; char
0x14005984e  mov     r8d, 15h; int
0x140059854  mov     dl, 4; int
0x140059856  mov     [rsp+68h+var_48], r15; struct _GUID *
0x14005985b  mov     rcx, [rcx+40h]; int
0x14005985f  call    WPP_RECORDER_SF_q
0x140059864  cmp     byte ptr [rdi], 80h
0x140059867  mov     [rsp+68h+arg_0], rsi
0x14005986c  mov     [rsp+68h+arg_18], r12
0x140059874  jnz     loc_140059A4C
0x14005987a  movzx   eax, byte ptr [rdi+1]
0x14005987e  cmp     al, 1
0x140059880  jb      loc_140059A4C
0x140059886  xor     r12b, r12b
0x140059889  cmp     al, 2
0x14005988b  jb      short loc_1400598B4
0x14005988d  mov     r12d, [rdi+0Ch]
0x140059891  test    r12d, 0FFFFFFFEh
0x140059898  jz      short loc_1400598B0
0x14005989a  mov     r8d, r12d; BugCheckParameter3
0x14005989d  xor     r9d, r9d; BugCheckParameter4
0x1400598a0  mov     edx, 5; BugCheckParameter2
0x1400598a5  mov     ecx, 2Dh ; '-'; BugCheckParameter1
0x1400598aa  call    ?ndisBugCheckEx@@YAX_K000@Z; ndisBugCheckEx(unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x1400598b0  and     r12b, 1
0x1400598b4  mov     esi, [rdi+8]
0x1400598b7  mov     eax, 0B0h
0x1400598bc  test    esi, esi
0x1400598be  jz      short loc_140059933
0x1400598c0  cmp     esi, 100000h
0x1400598c6  jbe     short loc_1400598FA
0x1400598c8  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x1400598cf  jz      loc_140059A82
0x1400598d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400598dc  mov     r9d, 0Bh
0x1400598e2  mov     qword ptr [rsp+68h+var_40], rsi
0x1400598e7  mov     [rsp+68h+var_48], r15
0x1400598ec  mov     rcx, [rcx+40h]
0x1400598f0  call    WPP_RECORDER_SF_PP
0x1400598f5  jmp     loc_140059A4C
0x1400598fa  mov     rdx, rsi; Length
0x1400598fd  mov     ecx, 0FFFh; Base
0x140059902  mov     rbx, rsi
0x140059905  call    cs:__imp_MmSizeOfMdl
0x14005990c  nop     dword ptr [rax+rax+00h]
0x140059911  mov     rdx, rbx; Length
0x140059914  mov     ecx, 0FFFh; Base
0x140059919  dec     eax
0x14005991b  and     eax, 7
0x14005991e  sub     esi, eax
0x140059920  call    cs:__imp_MmSizeOfMdl
0x140059927  nop     dword ptr [rax+rax+00h]
0x14005992c  add     eax, 0B7h
0x140059931  add     eax, esi
0x140059933  mov     r8d, [rdi+4]; unsigned int
0x140059937  add     eax, 7
0x14005993a  and     eax, 0FFFFFFF8h
0x14005993d  mov     byte ptr [rsp+68h+var_48], 0; unsigned __int8
0x140059942  mov     edx, eax; unsigned __int64
0x140059944  mov     r15d, eax
0x140059947  call    ?ndisPplCreatePool@@YAPEAUPPL_POOL_HANDLE__@@K_KKGE@Z; ndisPplCreatePool(ulong,unsigned __int64,ulong,ushort,uchar)
0x14005994c  mov     rbx, rax
0x14005994f  test    rax, rax
0x140059952  jz      loc_140059A45
0x140059958  mov     dword ptr [rax], 180010Ch
0x14005995e  mov     [rax+28h], r14
0x140059962  mov     eax, [rdi+4]
0x140059965  mov     [rbx+24h], eax
0x140059968  cmp     dword ptr [rdi+8], 0
0x14005996c  jz      short loc_1400599B2
0x14005996e  or      dword ptr [rbx+50h], 1
0x140059972  mov     ecx, 0FFFh; Base
0x140059977  mov     eax, [rdi+8]
0x14005997a  mov     [rbx+54h], eax
0x14005997d  mov     esi, [rdi+8]
0x140059980  mov     edx, esi; Length
0x140059982  call    cs:__imp_MmSizeOfMdl
0x140059989  nop     dword ptr [rax+rax+00h]
0x14005998e  mov     edi, 7
0x140059993  mov     edx, esi; Length
0x140059995  dec     eax
0x140059997  mov     ecx, 0FFFh; Base
0x14005999c  and     eax, 7
0x14005999f  sub     edi, eax
0x1400599a1  call    cs:__imp_MmSizeOfMdl
0x1400599a8  nop     dword ptr [rax+rax+00h]
0x1400599ad  add     eax, edi
0x1400599af  mov     [rbx+58h], eax
0x1400599b2  mov     rdx, [rsp+68h+arg_8]; void *
0x1400599b7  movzx   r8d, r12b; bool
0x1400599bb  mov     rcx, rbx; struct _NDIS_POOL_HEADER *
0x1400599be  call    ?ndisPplConfigureVerifier@@YAXPEAU_NDIS_POOL_HEADER@@PEAX_N@Z; ndisPplConfigureVerifier(_NDIS_POOL_HEADER *,void *,bool)
0x1400599c3  lea     rcx, [rbx+38h]; SpinLock
0x1400599c7  mov     [rbx+20h], r15d
0x1400599cb  call    cs:__imp_KeInitializeSpinLock
0x1400599d2  nop     dword ptr [rax+rax+00h]
0x1400599d7  lea     rax, [rbx+10h]
0x1400599db  lea     rcx, qword_14011C888; SpinLock
0x1400599e2  mov     [rax+8], rax
0x1400599e6  mov     [rax], rax
0x1400599e9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400599f0  nop     dword ptr [rax+rax+00h]
0x1400599f5  mov     rcx, cs:qword_14011D1F0
0x1400599fc  lea     r8, qword_14011D1F0
0x140059a03  movzx   edx, al; NewIrql
0x140059a06  cmp     [rcx+8], r8
0x140059a0a  jz      short loc_140059A13
0x140059a0c  mov     ecx, 3
0x140059a11  int     29h; Win8: RtlFailFast(ecx)
0x140059a13  lea     rax, [rbx+40h]
0x140059a17  mov     [rax], rcx
0x140059a1a  mov     [rax+8], r8
0x140059a1e  mov     [rcx+8], rax
0x140059a22  lea     rcx, qword_14011C888; SpinLock
0x140059a29  mov     cs:qword_14011D1F0, rax
0x140059a30  call    cs:__imp_KeReleaseSpinLock
0x140059a37  nop     dword ptr [rax+rax+00h]
0x140059a3c  mov     rax, [rsp+68h+arg_8]
0x140059a41  mov     [rbx+30h], rax
0x140059a45  lea     r15, WPP_cd3cd4c8e5733a8d9138b29e4c73b290_Traceguids
0x140059a4c  cmp     cs:WPP_RECORDER_INITIALIZED, r13; __annotation("TMF:",
0x140059a53  jz      short loc_140059A82
0x140059a55  mov     rcx, cs:WPP_GLOBAL_Control
0x140059a5c  mov     r9d, 0Ch; int
0x140059a62  mov     qword ptr [rsp+68h+var_38], rbx; char
0x140059a67  mov     r8d, 15h; int
0x140059a6d  mov     qword ptr [rsp+68h+var_40], r14; char
0x140059a72  mov     dl, 4; int
0x140059a74  mov     [rsp+68h+var_48], r15; struct _GUID *
0x140059a79  mov     rcx, [rcx+40h]; int
0x140059a7d  call    WPP_RECORDER_SF_qq
0x140059a82  mov     r12, [rsp+68h+arg_18]
0x140059a8a  mov     rax, rbx
0x140059a8d  mov     rsi, [rsp+68h+arg_0]
0x140059a92  add     rsp, 40h
0x140059a96  pop     r15
0x140059a98  pop     r14
0x140059a9a  pop     r13
0x140059a9c  pop     rdi
0x140059a9d  pop     rbx
0x140059a9e  retn
```
