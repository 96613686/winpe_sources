# Smb2Fsctl_Start

- ea: `0x14000fb60`
- end: `0x140010075`
- name: `Smb2Fsctl_Start`
- size: `1301`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000fb60`
- `0x140013c90`
- `0x140029840`
- `0x140037120`
- `0x140050270`
- `0x14005396c`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x14000ffb9`
- `ntoskrnl!IoGetRequestorProcess` at `0x14000ffb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ff98`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000ff98`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000fd6d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14000fd6d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010064`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140010064`
- `ntoskrnl!ProbeForWrite` at `0x140039d94`
- `ntoskrnl!ProbeForWrite` at `0x140039d94`
- `ntoskrnl!ProbeForRead` at `0x140039d73`
- `ntoskrnl!ProbeForRead` at `0x140039d73`
- `ntoskrnl!KeStackAttachProcess` at `0x14000ffcd`
- `ntoskrnl!KeStackAttachProcess` at `0x14000ffcd`
- `rdbss!RxFreeMdlChain` at `0x140010031`
- `rdbss!RxFreeMdlChain` at `0x140010031`
- `rdbss!RxFreeMdl` at `0x14001003f`
- `rdbss!RxFreeMdl` at `0x14001004e`
- `rdbss!RxFreeMdl` at `0x14001003f`
- `rdbss!RxFreeMdl` at `0x14001004e`
- `rdbss!RxAllocateMdl2` at `0x14000fd52`
- `rdbss!RxAllocateMdl2` at `0x14000fd99`
- `rdbss!RxAllocateMdl2` at `0x14000ff14`
- `rdbss!RxAllocateMdl2` at `0x14000fd52`
- `rdbss!RxAllocateMdl2` at `0x14000fd99`
- `rdbss!RxAllocateMdl2` at `0x14000ff14`
- `mrxsmb!RDR_PERF_ENTER` at `0x14000fbc1`
- `mrxsmb!RDR_PERF_ENTER` at `0x14000fbc1`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14000ff67`
- `mrxsmb!SmbCseFinalizeBufferContext` at `0x14000ff67`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14000fe66`
- `mrxsmb!SmbCseSubmitBufferContext` at `0x14000fe66`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14000fdff`
- `mrxsmb!SmbCseInitializeBufferContextWithMemoryRegistration` at `0x14000fdff`

## pseudocode

```c
__int64 __fastcall Smb2Fsctl_Start(__int64 a1, __int64 a2)
{
  __int64 v3; // r12
  _QWORD *p_Next; // rsi
  __int64 v5; // r15
  char v6; // r13
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 v12; // rax
  __int64 v13; // rcx
  __m128i si128; // xmm0
  struct _MDL *Mdl2; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // ecx
  __int64 v19; // rdx
  int RdmaMappingPre; // edi
  unsigned int v21; // ecx
  PVOID v23; // rax
  IRP *v24; // rcx
  struct _KPROCESS *RequestorProcess; // rax
  int v26; // eax
  volatile void *v27; // rcx
  volatile void *v28; // rcx
  _KAPC_STATE ApcState; // [rsp+78h] [rbp-60h] BYREF

  v3 = *(_QWORD *)(a1 + 48);
  p_Next = 0;
  v5 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  v6 = 0;
  LOBYTE(a2) = 15;
  RDR_PERF_ENTER(a1 + 512, a2);
  v7 = *(_DWORD *)(a1 + 2408);
  if ( v7 == 1311600 )
  {
    RdmaMappingPre = Smb2FsctlCreateRdmaMappingPre();
    if ( RdmaMappingPre < 0 )
      goto LABEL_29;
  }
  else if ( v7 == 1311604 )
  {
    v26 = Smb2FsctlReleaseRdmaMappingPre(a1);
    RdmaMappingPre = v26;
    if ( v26 < 0 && v26 != -1073741275 && v26 != -1073741736 )
      goto LABEL_29;
  }
  if ( (*(_BYTE *)(a1 + 2408) & 3) == 3 )
  {
    v24 = *(IRP **)(v3 + 40);
    if ( v24 )
    {
      RequestorProcess = IoGetRequestorProcess(v24);
      KeStackAttachProcess(RequestorProcess, &ApcState);
      v6 = 1;
      if ( *(_BYTE *)(*(_QWORD *)(v3 + 40) + 64LL) )
      {
        v27 = *(volatile void **)(a1 + 2416);
        if ( v27 )
          ProbeForRead(v27, *(unsigned int *)(a1 + 2424), 1u);
        v28 = *(volatile void **)(a1 + 2432);
        if ( v28 )
          ProbeForWrite(v28, *(unsigned int *)(a1 + 2440), 1u);
      }
    }
  }
  v8 = *(_QWORD *)(a1 + 72);
  v9 = *(_QWORD *)(a1 + 80);
  v10 = *(_QWORD *)(a1 + 88);
  *(_OWORD *)(a1 + 2488) = 0;
  *(_OWORD *)(a1 + 2504) = 0;
  *(_OWORD *)(a1 + 2520) = 0;
  *(_OWORD *)(a1 + 2536) = 0;
  *(_DWORD *)(a1 + 2488) = 1112364030;
  *(_DWORD *)(a1 + 2520) = 65279;
  *(_WORD *)(a1 + 2492) = 64;
  if ( *(char *)(v8 + 736) < 0 )
    *(_DWORD *)(a1 + 2504) = (16 * *(_BYTE *)(a1 + 33) + 16) & 0x70;
  *(_WORD *)(a1 + 2502) = 1;
  if ( v9 )
  {
    *(_QWORD *)(a1 + 2528) = *(_QWORD *)(v9 + 440);
    if ( (*(_DWORD *)(v8 + 716) & 0x3000) != 0 )
      *(_WORD *)(a1 + 2496) = *(_WORD *)(v8 + 700);
  }
  if ( v10 )
  {
    *(_DWORD *)(a1 + 2524) = *(_DWORD *)(v10 + 436);
    if ( (*(_DWORD *)(*(_QWORD *)(v10 + 424) + 176LL) & 2) != 0 && (*(_DWORD *)(a1 + 68) & 0x8000) != 0 )
      *(_DWORD *)(a1 + 2504) |= 0x10000000u;
  }
  if ( (*(_DWORD *)(v8 + 716) & 0x3000) != 0 && (*(_DWORD *)(a1 + 68) & 0x4000) != 0 )
    *(_DWORD *)(a1 + 2504) |= 0x20000000u;
  *(_WORD *)(a1 + 2500) = 11;
  *(_DWORD *)(a1 + 2552) = 57;
  *(_DWORD *)(a1 + 2556) = *(_DWORD *)(a1 + 2408);
  v11 = 120;
  *(_DWORD *)(a1 + 2576) = 120;
  *(_DWORD *)(a1 + 2580) = *(_DWORD *)(a1 + 2424);
  *(_DWORD *)(a1 + 2584) = 0;
  *(_QWORD *)(a1 + 2588) = 120;
  *(_DWORD *)(a1 + 2596) = *(_DWORD *)(a1 + 2440);
  *(_DWORD *)(a1 + 2600) = 1;
  v12 = *(_QWORD *)(v3 + 72);
  if ( v12 && (v13 = *(_QWORD *)(v12 + 48)) != 0 )
    si128 = *(__m128i *)(v13 + 28);
  else
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *(__m128i *)(a1 + 2560) = si128;
  Mdl2 = (struct _MDL *)RxAllocateMdl2(a1 + 2488, 120, 0, 0, 0);
  p_Next = &Mdl2->Next;
  if ( Mdl2 )
  {
    MmBuildMdlForNonPagedPool(Mdl2);
    v16 = *(unsigned int *)(a1 + 2424);
    if ( !(_DWORD)v16 )
    {
LABEL_21:
      v18 = 0;
      v19 = *(unsigned int *)(a1 + 2440);
      if ( (_DWORD)v19 )
      {
        v5 = RxAllocateMdl2(*(_QWORD *)(a1 + 2432), v19, 0, 0, 0);
        if ( !v5 )
        {
          RdmaMappingPre = -1073741670;
          goto LABEL_29;
        }
        v18 = *(_DWORD *)(a1 + 2440);
      }
      RdmaMappingPre = SmbCseInitializeBufferContextWithMemoryRegistration(
                         a1 + 1024,
                         a1,
                         p_Next,
                         v11,
                         v5,
                         v18,
                         0,
                         0,
                         0,
                         4);
      if ( !RdmaMappingPre )
      {
        if ( !v5
          || ((*(_BYTE *)(v5 + 10) & 5) == 0
            ? (v23 = MmMapLockedPagesSpecifyCache((PMDL)v5, 0, MmCached, 0, 0, 0x40000000u))
            : (v23 = *(PVOID *)(v5 + 24)),
              (*(_QWORD *)(a1 + 1736) = v23) != 0) )
        {
          v21 = *(_DWORD *)(a1 + 2424);
          if ( v21 <= *(_DWORD *)(a1 + 2440) )
            v21 = *(_DWORD *)(a1 + 2440);
          if ( !v21 )
            v21 = 1;
          *(_DWORD *)(a1 + 1104) = ((v21 - 1) >> 16) + 1;
          *(_DWORD *)(a1 + 1888) = *(_DWORD *)(a1 + 2408);
          p_Next = 0;
          v5 = 0;
          *(_QWORD *)(a1 + 1112) = *(_QWORD *)(a1 + 2416);
          RdmaMappingPre = SmbCseSubmitBufferContext(a1 + 1024);
          if ( RdmaMappingPre == -1073741507 )
          {
            RdmaMappingPre = -1073740757;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              WPP_SF_DDD(
                WPP_GLOBAL_Control->AttachedDevice,
                11,
                WPP_65e9b76cb4683fb66828063337b9192b_Traceguids,
                *(unsigned int *)(a1 + 2424),
                *(_DWORD *)(a1 + 2440),
                -1073740757);
            }
          }
        }
        else
        {
          RdmaMappingPre = -1073741670;
          SmbCseFinalizeBufferContext(a1 + 1024);
          p_Next = 0;
          v5 = 0;
        }
      }
LABEL_29:
      if ( RdmaMappingPre >= 0 )
        goto LABEL_30;
      goto LABEL_55;
    }
    v17 = RxAllocateMdl2(*(_QWORD *)(a1 + 2416), v16, 0, 0, 0);
    if ( v17 )
    {
      *p_Next = v17;
      v11 = *(_DWORD *)(a1 + 2424) + 120;
      goto LABEL_21;
    }
    RdmaMappingPre = -1073741670;
  }
  else
  {
    RdmaMappingPre = -1073741670;
  }
LABEL_55:
  RxFreeMdlChain(p_Next);
  RxFreeMdl(0);
  RxFreeMdl(v5);
LABEL_30:
  if ( v6 )
    KeUnstackDetachProcess(&ApcState);
  return (unsigned int)RdmaMappingPre;
}

```

## disassembly

```asm
0x14000fb60  mov     r11, rsp
0x14000fb63  mov     [r11+10h], rbx
0x14000fb67  mov     [r11+18h], rsi
0x14000fb6b  push    rdi
0x14000fb6c  push    r12
0x14000fb6e  push    r13
0x14000fb70  push    r14
0x14000fb72  push    r15
0x14000fb74  sub     rsp, 0B0h
0x14000fb7b  mov     rax, cs:__security_cookie
0x14000fb82  xor     rax, rsp
0x14000fb85  mov     [rsp+0D8h+var_30], rax
0x14000fb8d  mov     rbx, rcx
0x14000fb90  mov     [rsp+0D8h+var_80], rcx
0x14000fb95  mov     r12, [rcx+30h]
0x14000fb99  xor     esi, esi
0x14000fb9b  mov     [rsp+0D8h+var_70], rsi
0x14000fba0  xor     r15d, r15d
0x14000fba3  xorps   xmm0, xmm0
0x14000fba6  movups  xmmword ptr [rsp+0D8h+ApcState.ApcListHead.Flink], xmm0
0x14000fbab  movups  xmmword ptr [r11-50h], xmm0
0x14000fbb0  movups  xmmword ptr [r11-40h], xmm0
0x14000fbb5  xor     r13b, r13b
0x14000fbb8  add     rcx, 200h
0x14000fbbf  mov     dl, 0Fh
0x14000fbc1  call    cs:__imp_RDR_PERF_ENTER
0x14000fbc8  nop     dword ptr [rax+rax+00h]
0x14000fbcd  mov     eax, [rbx+968h]
0x14000fbd3  cmp     eax, 140370h
0x14000fbd8  jz      loc_14000FECD
0x14000fbde  cmp     eax, 140374h
0x14000fbe3  jz      loc_14000FFF5
0x14000fbe9  mov     eax, [rbx+968h]
0x14000fbef  and     eax, 3
0x14000fbf2  cmp     al, 3
0x14000fbf4  jz      loc_14000FFA6
0x14000fbfa  mov     r14d, 1
0x14000fc00  lea     r10, [rbx+9B8h]
0x14000fc07  mov     rdx, [rbx+48h]
0x14000fc0b  mov     r8, [rbx+50h]
0x14000fc0f  mov     rcx, [rbx+58h]
0x14000fc13  xorps   xmm0, xmm0
0x14000fc16  movups  xmmword ptr [r10], xmm0
0x14000fc1a  movups  xmmword ptr [r10+10h], xmm0
0x14000fc1f  movups  xmmword ptr [r10+20h], xmm0
0x14000fc24  movups  xmmword ptr [r10+30h], xmm0
0x14000fc29  mov     dword ptr [r10], 424D53FEh
0x14000fc30  mov     dword ptr [r10+20h], 0FEFFh
0x14000fc38  mov     word ptr [r10+4], 40h ; '@'
0x14000fc3f  cmp     byte ptr [rdx+2E0h], 0
0x14000fc46  jge     short loc_14000FC59
0x14000fc48  movzx   eax, byte ptr [rbx+21h]
0x14000fc4c  shl     eax, 4
0x14000fc4f  add     eax, 10h
0x14000fc52  and     eax, 70h
0x14000fc55  mov     [r10+10h], eax
0x14000fc59  mov     [r10+0Eh], r14w
0x14000fc5e  test    r8, r8
0x14000fc61  jz      short loc_14000FC86
0x14000fc63  mov     rax, [r8+1B8h]
0x14000fc6a  mov     [r10+28h], rax
0x14000fc6e  test    dword ptr [rdx+2CCh], 3000h
0x14000fc78  jz      short loc_14000FC86
0x14000fc7a  movzx   eax, word ptr [rdx+2BCh]
0x14000fc81  mov     [r10+8], ax
0x14000fc86  test    rcx, rcx
0x14000fc89  jz      short loc_14000FCAB
0x14000fc8b  mov     eax, [rcx+1B4h]
0x14000fc91  mov     [r10+24h], eax
0x14000fc95  mov     rax, [rcx+1A8h]
0x14000fc9c  mov     ecx, [rax+0B0h]
0x14000fca2  test    cl, 2
0x14000fca5  jnz     loc_14000FEDE
0x14000fcab  test    dword ptr [rdx+2CCh], 3000h
0x14000fcb5  jz      short loc_14000FCC4
0x14000fcb7  mov     eax, [rbx+44h]
0x14000fcba  bt      eax, 0Eh
0x14000fcbe  jb      loc_14000FEF8
0x14000fcc4  mov     word ptr [rbx+9C4h], 0Bh
0x14000fccd  mov     dword ptr [rbx+9F8h], 39h ; '9'
0x14000fcd7  mov     eax, [rbx+968h]
0x14000fcdd  mov     [rbx+9FCh], eax
0x14000fce3  mov     edi, 78h ; 'x'
0x14000fce8  mov     [rbx+0A10h], edi
0x14000fcee  mov     eax, [rbx+978h]
0x14000fcf4  mov     [rbx+0A14h], eax
0x14000fcfa  xor     edx, edx
0x14000fcfc  mov     [rbx+0A18h], edx
0x14000fd02  mov     [rbx+0A1Ch], rdi
0x14000fd09  mov     eax, [rbx+988h]
0x14000fd0f  mov     [rbx+0A24h], eax
0x14000fd15  mov     [rbx+0A28h], r14d
0x14000fd1c  mov     rax, [r12+48h]
0x14000fd21  test    rax, rax
0x14000fd24  jz      loc_14000FEC0
0x14000fd2a  mov     rcx, [rax+30h]
0x14000fd2e  test    rcx, rcx
0x14000fd31  jz      loc_14000FEC0
0x14000fd37  movups  xmm0, xmmword ptr [rcx+1Ch]
0x14000fd3b  movups  xmmword ptr [rbx+0A00h], xmm0
0x14000fd42  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], rdx
0x14000fd47  xor     r9d, r9d
0x14000fd4a  xor     r8d, r8d
0x14000fd4d  mov     edx, edi
0x14000fd4f  mov     rcx, r10
0x14000fd52  call    cs:__imp_RxAllocateMdl2
0x14000fd59  nop     dword ptr [rax+rax+00h]
0x14000fd5e  mov     rsi, rax
0x14000fd61  test    rax, rax
0x14000fd64  jz      loc_140010022
0x14000fd6a  mov     rcx, rax; MemoryDescriptorList
0x14000fd6d  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14000fd74  nop     dword ptr [rax+rax+00h]
0x14000fd79  mov     edx, [rbx+978h]
0x14000fd7f  test    edx, edx
0x14000fd81  jz      short loc_14000FDBA
0x14000fd83  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], 0
0x14000fd8c  xor     r9d, r9d
0x14000fd8f  xor     r8d, r8d
0x14000fd92  mov     rcx, [rbx+970h]
0x14000fd99  call    cs:__imp_RxAllocateMdl2
0x14000fda0  nop     dword ptr [rax+rax+00h]
0x14000fda5  test    rax, rax
0x14000fda8  jz      loc_140010029
0x14000fdae  mov     [rsi], rax
0x14000fdb1  mov     edi, [rbx+978h]
0x14000fdb7  add     edi, 78h ; 'x'
0x14000fdba  xor     r8d, r8d
0x14000fdbd  mov     ecx, r8d
0x14000fdc0  mov     edx, [rbx+988h]
0x14000fdc6  test    edx, edx
0x14000fdc8  jnz     loc_14000FF05
0x14000fdce  mov     [rsp+0D8h+var_90], 4
0x14000fdd6  mov     [rsp+0D8h+var_98], r8w
0x14000fddc  mov     [rsp+0D8h+var_A0], r8d
0x14000fde1  mov     [rsp+0D8h+var_A8], r8
0x14000fde6  mov     [rsp+0D8h+Priority], ecx
0x14000fdea  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], r15
0x14000fdef  mov     r9d, edi
0x14000fdf2  mov     r8, rsi
0x14000fdf5  mov     rdx, rbx
0x14000fdf8  lea     rcx, [rbx+400h]
0x14000fdff  call    cs:__imp_SmbCseInitializeBufferContextWithMemoryRegistration
0x14000fe06  nop     dword ptr [rax+rax+00h]
0x14000fe0b  mov     edi, eax
0x14000fe0d  test    eax, eax
0x14000fe0f  jnz     short loc_14000FE7F
0x14000fe11  test    r15, r15
0x14000fe14  jnz     loc_14000FF40
0x14000fe1a  mov     eax, [rbx+988h]
0x14000fe20  mov     ecx, [rbx+978h]
0x14000fe26  cmp     ecx, eax
0x14000fe28  cmovbe  ecx, eax
0x14000fe2b  cmp     ecx, 1
0x14000fe2e  cmovb   ecx, r14d
0x14000fe32  lea     eax, [rcx-1]
0x14000fe35  shr     eax, 10h
0x14000fe38  inc     eax
0x14000fe3a  mov     [rbx+450h], eax
0x14000fe40  mov     eax, [rbx+968h]
0x14000fe46  mov     [rbx+760h], eax
0x14000fe4c  xor     esi, esi
0x14000fe4e  xor     r15d, r15d
0x14000fe51  mov     rax, [rbx+970h]
0x14000fe58  mov     [rbx+458h], rax
0x14000fe5f  lea     rcx, [rbx+400h]
0x14000fe66  call    cs:__imp_SmbCseSubmitBufferContext
0x14000fe6d  nop     dword ptr [rax+rax+00h]
0x14000fe72  mov     edi, eax
0x14000fe74  cmp     eax, 0C000013Dh
0x14000fe79  jz      loc_140039E09
0x14000fe7f  test    edi, edi
0x14000fe81  js      loc_14001002E
0x14000fe87  test    r13b, r13b
0x14000fe8a  jnz     loc_14001005F
0x14000fe90  mov     eax, edi
0x14000fe92  mov     rcx, [rsp+0D8h+var_30]
0x14000fe9a  xor     rcx, rsp; StackCookie
0x14000fe9d  call    __security_check_cookie
0x14000fea2  lea     r11, [rsp+0D8h+var_28]
0x14000feaa  mov     rbx, [r11+38h]
0x14000feae  mov     rsi, [r11+40h]
0x14000feb2  mov     rsp, r11
0x14000feb5  pop     r15
0x14000feb7  pop     r14
0x14000feb9  pop     r13
0x14000febb  pop     r12
0x14000febd  pop     rdi
0x14000febe  retn
0x14000fec0  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000fec8  jmp     loc_14000FD3B
0x14000fecd  call    Smb2FsctlCreateRdmaMappingPre
0x14000fed2  mov     edi, eax
0x14000fed4  test    eax, eax
0x14000fed6  jns     loc_14000FBE9
0x14000fedc  jmp     short loc_14000FE7F
0x14000fede  mov     eax, [rbx+44h]
0x14000fee1  bt      eax, 0Fh
0x14000fee5  jnb     loc_14000FCAB
0x14000feeb  or      dword ptr [r10+10h], 10000000h
0x14000fef3  jmp     loc_14000FCAB
0x14000fef8  or      dword ptr [r10+10h], 20000000h
0x14000ff00  jmp     loc_14000FCC4
0x14000ff05  mov     qword ptr [rsp+0D8h+BugCheckOnFailure], r8
0x14000ff0a  xor     r9d, r9d
0x14000ff0d  mov     rcx, [rbx+980h]
0x14000ff14  call    cs:__imp_RxAllocateMdl2
0x14000ff1b  nop     dword ptr [rax+rax+00h]
0x14000ff20  mov     r15, rax
0x14000ff23  test    rax, rax
0x14000ff26  jnz     short loc_14000FF32
0x14000ff28  mov     edi, 0C000009Ah
0x14000ff2d  jmp     loc_14000FE7F
0x14000ff32  mov     ecx, [rbx+988h]
0x14000ff38  xor     r8d, r8d
0x14000ff3b  jmp     loc_14000FDCE
0x14000ff40  test    byte ptr [r15+0Ah], 5
0x14000ff45  jz      short loc_14000FF7D
0x14000ff47  mov     rax, [r15+18h]
0x14000ff4b  mov     [rbx+6C8h], rax
0x14000ff52  test    rax, rax
0x14000ff55  jnz     loc_14000FE1A
0x14000ff5b  mov     edi, 0C000009Ah
0x14000ff60  lea     rcx, [rbx+400h]
0x14000ff67  call    cs:__imp_SmbCseFinalizeBufferContext
0x14000ff6e  nop     dword ptr [rax+rax+00h]
0x14000ff73  xor     esi, esi
0x14000ff75  xor     r15d, r15d
0x14000ff78  jmp     loc_14000FE7F
0x14000ff7d  mov     [rsp+0D8h+Priority], 40000000h; Priority
0x14000ff85  mov     [rsp+0D8h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000ff8d  xor     r9d, r9d; RequestedAddress
0x14000ff90  mov     r8d, r14d; CacheType
0x14000ff93  xor     edx, edx; AccessMode
0x14000ff95  mov     rcx, r15; MemoryDescriptorList
0x14000ff98  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000ff9f  nop     dword ptr [rax+rax+00h]
0x14000ffa4  jmp     short loc_14000FF4B
0x14000ffa6  mov     rcx, [r12+28h]; Irp
0x14000ffab  test    rcx, rcx
0x14000ffae  jz      loc_14000FBFA
0x14000ffb4  mov     [rsp+0D8h+var_78], r12
0x14000ffb9  call    cs:__imp_IoGetRequestorProcess
0x14000ffc0  nop     dword ptr [rax+rax+00h]
0x14000ffc5  mov     rcx, rax; PROCESS
0x14000ffc8  lea     rdx, [rsp+0D8h+ApcState]; ApcState
0x14000ffcd  call    cs:__imp_KeStackAttachProcess
0x14000ffd4  nop     dword ptr [rax+rax+00h]
0x14000ffd9  mov     r13b, 1
0x14000ffdc  mov     [rsp+0D8h+var_88], r13b
0x14000ffe1  mov     rax, [r12+28h]
0x14000ffe6  cmp     [rax+40h], sil
0x14000ffea  jz      loc_14000FBFA
0x14000fff0  jmp     loc_140039D58
0x14000fff5  mov     rcx, rbx
0x14000fff8  call    Smb2FsctlReleaseRdmaMappingPre
0x14000fffd  mov     edi, eax
0x14000ffff  test    eax, eax
0x140010001  jns     loc_14000FBE9
0x140010007  cmp     eax, 0C0000225h
0x14001000c  jz      loc_14000FBE9
0x140010012  cmp     eax, 0C0000058h
0x140010017  jnz     loc_14000FE7F
0x14001001d  jmp     loc_14000FBE9
0x140010022  mov     edi, 0C000009Ah
0x140010027  jmp     short loc_14001002E
0x140010029  mov     edi, 0C000009Ah
0x14001002e  mov     rcx, rsi
0x140010031  call    cs:__imp_RxFreeMdlChain
0x140010038  nop     dword ptr [rax+rax+00h]
0x14001003d  xor     ecx, ecx
0x14001003f  call    cs:__imp_RxFreeMdl
0x140010046  nop     dword ptr [rax+rax+00h]
0x14001004b  mov     rcx, r15
0x14001004e  call    cs:__imp_RxFreeMdl
0x140010055  nop     dword ptr [rax+rax+00h]
0x14001005a  jmp     loc_14000FE87
0x14001005f  lea     rcx, [rsp+0D8h+ApcState]; ApcState
0x140010064  call    cs:__imp_KeUnstackDetachProcess
0x14001006b  nop     dword ptr [rax+rax+00h]
0x140010070  jmp     loc_14000FE90
0x140039d58  mov     rcx, [rbx+970h]; Address
0x140039d5f  mov     r14d, 1
0x140039d65  test    rcx, rcx
0x140039d68  jz      short loc_140039D7F
0x140039d6a  mov     edx, [rbx+978h]; Length
0x140039d70  mov     r8d, r14d; Alignment
0x140039d73  call    cs:__imp_ProbeForRead
0x140039d7a  nop     dword ptr [rax+rax+00h]
0x140039d7f  mov     rcx, [rbx+980h]; Address
0x140039d86  test    rcx, rcx
0x140039d89  jz      short loc_140039DA1
0x140039d8b  mov     edx, [rbx+988h]; Length
0x140039d91  mov     r8d, r14d; Alignment
0x140039d94  call    cs:__imp_ProbeForWrite
0x140039d9b  nop     dword ptr [rax+rax+00h]
0x140039da0  nop
0x140039da1  jmp     loc_14000FC00
0x140039da6  lea     rax, WPP_GLOBAL_Control
0x140039dad  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
