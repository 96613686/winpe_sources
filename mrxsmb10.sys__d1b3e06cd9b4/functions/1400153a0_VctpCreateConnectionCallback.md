# VctpCreateConnectionCallback

- ea: `0x1400153a0`
- end: `0x140015654`
- name: `VctpCreateConnectionCallback`
- size: `692`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000dfd8`
- `0x14000ebd8`
- `0x140014abc`
- `0x1400153a0`
- `0x1400166c0`
- `0x140041168`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400155c5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400155b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400155b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140015584`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140015584`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001556f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001556f`
- `ntoskrnl!ExAllocatePool2` at `0x140015411`
- `ntoskrnl!ExAllocatePool2` at `0x140015411`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015530`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001559b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015530`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001559b`
- `mrxsmb!RxCeQueryInformation` at `0x1400155f2`
- `mrxsmb!RxCeQueryInformation` at `0x1400155f2`
- `mrxsmb!RxCeTearDownVC` at `0x1400154c1`
- `mrxsmb!RxCeTearDownVC` at `0x1400154c1`
- `mrxsmb!SmbMmFreeServerTransport` at `0x14001551f`
- `mrxsmb!SmbMmFreeServerTransport` at `0x14001551f`

## pseudocode

```c
__int64 __fastcall VctpCreateConnectionCallback(PVOID P)
{
  __int64 v1; // rsi
  __int64 v3; // rbp
  int Information; // edi
  bool v5; // sf
  __int64 v6; // r14
  size_t v7; // r15
  void *Pool2; // rax
  PDEVICE_OBJECT v9; // rcx
  struct _RXCE_VC_ *v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rax
  void *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r8
  int v18; // edx
  __int64 Type; // rax
  __int128 v20; // [rsp+20h] [rbp-48h]

  v1 = *((_QWORD *)P + 15);
  v3 = *((_QWORD *)P + 10);
  *(_DWORD *)v1 = *(_DWORD *)P;
  Information = *(_DWORD *)P;
  v5 = *(int *)P < 0;
  if ( !*(_DWORD *)P )
  {
    v6 = *(_QWORD *)(v1 + 32);
    if ( v3 && *(_QWORD *)(v3 + 464) )
    {
      v7 = *(unsigned __int16 *)(v3 + 456);
      *(_QWORD *)&v20 = *(unsigned int *)(v3 + 456);
      Pool2 = (void *)ExAllocatePool2(66, WORD1(v20), 1934454099);
      *((_QWORD *)&v20 + 1) = Pool2;
      if ( !Pool2 )
      {
        Information = -1073741670;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_14:
          *(_DWORD *)v1 = Information;
          v5 = Information < 0;
          goto LABEL_15;
        }
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids, v6);
        goto LABEL_8;
      }
      memmove(Pool2, *(const void **)(v3 + 464), v7);
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
      v15 = *(void **)(v6 + 120);
      if ( v15 )
        ExFreePoolWithTag(v15, 0);
      *(_OWORD *)(v6 + 112) = v20;
      ExReleaseResourceLite(&s_SmbCeDbResource);
      KeLeaveCriticalRegion();
    }
    if ( !*(_DWORD *)(*((_QWORD *)P + 10) + 320LL) )
    {
      Information = RxCeQueryInformation(
                      *((PRXCE_VC *)P + 10),
                      RxCeTransportProviderInformation,
                      *((PVOID *)P + 13),
                      *((_DWORD *)P + 24));
      if ( !Information && !*(_DWORD *)(*((_QWORD *)P + 10) + 320LL) )
      {
        v16 = *((_QWORD *)P + 13);
        v17 = (unsigned int)(Information + 2);
        v18 = *(_DWORD *)(v16 + 4);
        v9 = (PDEVICE_OBJECT)(v16 + 8);
        while ( v18 )
        {
          Type = (unsigned __int16)v9->Type;
          v9 = (PDEVICE_OBJECT)((char *)v9 + v17);
          if ( v9->Type == (_WORD)Information + 2 )
          {
            *(_DWORD *)(v6 + 428) = v9->ReferenceCount;
            break;
          }
          --v18;
          v9 = (PDEVICE_OBJECT)((char *)v9 + Type + v17);
        }
LABEL_12:
        Information = VctCompleteInitialization(v9, *(_QWORD *)(*((_QWORD *)P + 10) + 32LL), *((_QWORD *)P + 10));
        if ( Information >= 0 )
        {
          *(_QWORD *)(v1 + 56) = *((_QWORD *)P + 10);
          *((_QWORD *)P + 10) = 0;
        }
        goto LABEL_14;
      }
    }
LABEL_8:
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids,
        (unsigned int)Information);
    if ( Information < 0 )
      goto LABEL_14;
    goto LABEL_12;
  }
LABEL_15:
  if ( v5 )
  {
    v10 = (struct _RXCE_VC_ *)*((_QWORD *)P + 10);
    if ( v10 )
      RxCeTearDownVC(v10);
  }
  v11 = (void *)*((_QWORD *)P + 13);
  if ( v11 )
  {
    ExFreePoolWithTag(v11, 0);
    *((_QWORD *)P + 13) = 0;
  }
  v12 = (void *)*((_QWORD *)P + 9);
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    *((_QWORD *)P + 9) = 0;
  }
  v13 = *((_QWORD *)P + 10);
  if ( v13 )
  {
    *(_DWORD *)(v13 + 8) = 0;
    SmbMmFreeServerTransport(*((_QWORD *)P + 10));
  }
  ExFreePoolWithTag(P, 0);
  *(_DWORD *)(v1 + 4) = 4;
  SmbCeConstructServerTransport((_QWORD *)v1);
  return 0;
}

```

## disassembly

```asm
0x1400153a0  push    rbx
0x1400153a2  push    rbp
0x1400153a3  push    rsi
0x1400153a4  push    rdi
0x1400153a5  push    r13
0x1400153a7  push    r14
0x1400153a9  push    r15
0x1400153ab  sub     rsp, 30h
0x1400153af  mov     rsi, [rcx+78h]
0x1400153b3  mov     rbx, rcx
0x1400153b6  mov     rbp, [rcx+50h]
0x1400153ba  mov     eax, [rcx]
0x1400153bc  mov     [rsi], eax
0x1400153be  mov     edi, [rcx]
0x1400153c0  test    edi, edi
0x1400153c2  jnz     loc_1400154B6
0x1400153c8  mov     r14, [rsi+20h]
0x1400153cc  lea     r13, WPP_GLOBAL_Control
0x1400153d3  test    rbp, rbp
0x1400153d6  jz      loc_1400155D1
0x1400153dc  cmp     qword ptr [rbp+1D0h], 0
0x1400153e4  jz      loc_1400155D1
0x1400153ea  movzx   r15d, word ptr [rbp+1C8h]
0x1400153f2  lea     ecx, [rdi+42h]
0x1400153f5  movzx   edx, word ptr [rbp+1CAh]
0x1400153fc  mov     r8d, 734D6D53h
0x140015402  mov     word ptr [rsp+68h+var_48], r15w
0x140015408  mov     word ptr [rsp+68h+var_48+2], dx
0x14001540d  mov     dword ptr [rsp+68h+var_48+4], edi
0x140015411  call    cs:__imp_ExAllocatePool2
0x140015418  nop     dword ptr [rax+rax+00h]
0x14001541d  mov     qword ptr [rsp+68h+var_48+8], rax
0x140015422  test    rax, rax
0x140015425  jnz     loc_14001555D
0x14001542b  mov     edi, 0C000009Ah
0x140015430  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015437  cmp     rcx, r13
0x14001543a  jz      short loc_1400154B2
0x14001543c  test    dword ptr [rcx+2Ch], 100h
0x140015443  jz      short loc_14001545B
0x140015445  mov     rcx, [rcx+18h]
0x140015449  lea     edx, [rax+20h]
0x14001544c  mov     r9, r14
0x14001544f  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x140015456  call    WPP_SF_q
0x14001545b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140015462  cmp     rcx, r13
0x140015465  jz      short loc_140015488
0x140015467  test    dword ptr [rcx+2Ch], 400h
0x14001546e  jz      short loc_140015488
0x140015470  mov     rcx, [rcx+18h]
0x140015474  lea     r8, WPP_97951c25c2543b4290bd9ef1a8ac3fa7_Traceguids
0x14001547b  mov     edx, 21h ; '!'
0x140015480  mov     r9d, edi
0x140015483  call    WPP_SF_d
0x140015488  test    edi, edi
0x14001548a  js      short loc_1400154B2
0x14001548c  mov     rdx, [rbx+50h]
0x140015490  mov     r8, rdx
0x140015493  mov     rdx, [rdx+20h]
0x140015497  call    VctCompleteInitialization
0x14001549c  mov     edi, eax
0x14001549e  test    eax, eax
0x1400154a0  js      short loc_1400154B2
0x1400154a2  mov     rax, [rbx+50h]
0x1400154a6  mov     [rsi+38h], rax
0x1400154aa  mov     qword ptr [rbx+50h], 0
0x1400154b2  mov     [rsi], edi
0x1400154b4  test    edi, edi
0x1400154b6  jns     short loc_1400154CD
0x1400154b8  mov     rcx, [rbx+50h]; pVc
0x1400154bc  test    rcx, rcx
0x1400154bf  jz      short loc_1400154CD
0x1400154c1  call    cs:__imp_RxCeTearDownVC
0x1400154c8  nop     dword ptr [rax+rax+00h]
0x1400154cd  mov     rcx, [rbx+68h]; P
0x1400154d1  test    rcx, rcx
0x1400154d4  jz      short loc_1400154EC
0x1400154d6  xor     edx, edx; Tag
0x1400154d8  call    cs:__imp_ExFreePoolWithTag
0x1400154df  nop     dword ptr [rax+rax+00h]
0x1400154e4  mov     qword ptr [rbx+68h], 0
0x1400154ec  mov     rcx, [rbx+48h]; P
0x1400154f0  test    rcx, rcx
0x1400154f3  jz      short loc_14001550B
0x1400154f5  xor     edx, edx; Tag
0x1400154f7  call    cs:__imp_ExFreePoolWithTag
0x1400154fe  nop     dword ptr [rax+rax+00h]
0x140015503  mov     qword ptr [rbx+48h], 0
0x14001550b  mov     rax, [rbx+50h]
0x14001550f  test    rax, rax
0x140015512  jz      short loc_14001552B
0x140015514  mov     dword ptr [rax+8], 0
0x14001551b  mov     rcx, [rbx+50h]
0x14001551f  call    cs:__imp_SmbMmFreeServerTransport
0x140015526  nop     dword ptr [rax+rax+00h]
0x14001552b  xor     edx, edx; Tag
0x14001552d  mov     rcx, rbx; P
0x140015530  call    cs:__imp_ExFreePoolWithTag
0x140015537  nop     dword ptr [rax+rax+00h]
0x14001553c  mov     rcx, rsi; P
0x14001553f  mov     dword ptr [rsi+4], 4
0x140015546  call    SmbCeConstructServerTransport
0x14001554b  xor     eax, eax
0x14001554d  add     rsp, 30h
0x140015551  pop     r15
0x140015553  pop     r14
0x140015555  pop     r13
0x140015557  pop     rdi
0x140015558  pop     rsi
0x140015559  pop     rbp
0x14001555a  pop     rbx
0x14001555b  retn
0x14001555d  mov     rdx, [rbp+1D0h]; Src
0x140015564  mov     r8, r15; Size
0x140015567  mov     rcx, rax; void *
0x14001556a  call    memmove
0x14001556f  call    cs:__imp_KeEnterCriticalRegion
0x140015576  nop     dword ptr [rax+rax+00h]
0x14001557b  mov     dl, 1; Wait
0x14001557d  lea     rcx, s_SmbCeDbResource; Resource
0x140015584  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001558b  nop     dword ptr [rax+rax+00h]
0x140015590  mov     rcx, [r14+78h]; P
0x140015594  test    rcx, rcx
0x140015597  jz      short loc_1400155A7
0x140015599  xor     edx, edx; Tag
0x14001559b  call    cs:__imp_ExFreePoolWithTag
0x1400155a2  nop     dword ptr [rax+rax+00h]
0x1400155a7  movups  xmm0, [rsp+68h+var_48]
0x1400155ac  lea     rcx, s_SmbCeDbResource; Resource
0x1400155b3  movdqu  xmmword ptr [r14+70h], xmm0
0x1400155b9  call    cs:__imp_ExReleaseResourceLite
0x1400155c0  nop     dword ptr [rax+rax+00h]
0x1400155c5  call    cs:__imp_KeLeaveCriticalRegion
0x1400155cc  nop     dword ptr [rax+rax+00h]
0x1400155d1  mov     rax, [rbx+50h]
0x1400155d5  cmp     dword ptr [rax+140h], 0
0x1400155dc  jnz     loc_14001545B
0x1400155e2  mov     r9d, [rbx+60h]; Length
0x1400155e6  mov     edx, 1; InformationClass
0x1400155eb  mov     r8, [rbx+68h]; pInformation
0x1400155ef  mov     rcx, rax; pVc
0x1400155f2  call    cs:__imp_RxCeQueryInformation
0x1400155f9  nop     dword ptr [rax+rax+00h]
0x1400155fe  mov     edi, eax
0x140015600  test    eax, eax
0x140015602  jnz     loc_14001545B
0x140015608  mov     rax, [rbx+50h]
0x14001560c  cmp     [rax+140h], edi
0x140015612  jnz     loc_14001545B
0x140015618  mov     rax, [rbx+68h]
0x14001561c  lea     r8d, [rdi+2]
0x140015620  mov     edx, [rax+4]
0x140015623  lea     rcx, [rax+8]
0x140015627  test    edx, edx
0x140015629  jz      loc_14001548C
0x14001562f  movzx   eax, word ptr [rcx]
0x140015632  add     rcx, r8
0x140015635  cmp     [rcx], r8w
0x140015639  jz      short loc_140015645
0x14001563b  dec     edx
0x14001563d  add     rcx, r8
0x140015640  add     rcx, rax
0x140015643  jmp     short loc_140015627
0x140015645  mov     eax, [rcx+4]
0x140015648  mov     [r14+1ACh], eax
0x14001564f  jmp     loc_14001548C
```
