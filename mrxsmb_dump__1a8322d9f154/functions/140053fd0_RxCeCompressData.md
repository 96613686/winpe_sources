# RxCeCompressData

- ea: `0x140053fd0`
- end: `0x140054465`
- name: `RxCeCompressData`
- size: `1173`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f1a0`
- `0x14008c298`

## callees

- `0x140017798`
- `0x1400383d0`
- `0x14004da20`
- `0x14004dbb8`
- `0x140053fd0`
- `0x140054830`
- `0x1400548b4`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140054414`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140054414`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054168`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400541fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400542dc`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140054168`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400541fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400542dc`
- `ntoskrnl!ExAllocatePool2` at `0x140054048`
- `ntoskrnl!ExAllocatePool2` at `0x14005422c`
- `ntoskrnl!ExAllocatePool2` at `0x140054048`
- `ntoskrnl!ExAllocatePool2` at `0x14005422c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005431e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005437a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005431e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005437a`
- `rdbss!RxAllocateMdl2` at `0x1400543ef`
- `rdbss!RxAllocateMdl2` at `0x1400543ef`
- `NETIO!RtlCopyMdlToBuffer` at `0x140054267`
- `NETIO!RtlCopyMdlToBuffer` at `0x140054267`

## pseudocode

```c
__int64 __fastcall RxCeCompressData(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        char a5,
        struct _MDL **a6,
        unsigned int *a7)
{
  char v7; // si
  __int64 v9; // r12
  unsigned int v12; // r10d
  unsigned int v13; // eax
  int v14; // ebx
  struct _MDL *v15; // r14
  __int64 Pool2; // rax
  int v17; // ebx
  __int64 v18; // rsi
  PVOID MappedSystemVa; // r14
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 ByteCount; // r8
  struct _MDL *v24; // rbx
  int v25; // eax
  PVOID v26; // rax
  char Socket; // al
  struct _MDL *Mdl2; // rax
  struct _MDL **v30; // rsi
  PVOID P; // [rsp+50h] [rbp-10h]
  unsigned int v32; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v33; // [rsp+B0h] [rbp+50h] BYREF
  char v34; // [rsp+B8h] [rbp+58h]

  v7 = a5;
  v9 = a4;
  v33 = 0;
  v32 = 0;
  v12 = a5 != 0 ? 96 : 16;
  v13 = v12 + a4;
  if ( v12 + a4 < v12 )
    return 3221226539LL;
  v14 = a1[147];
  v15 = *(struct _MDL **)a3;
  if ( a5 && v13 < 0x1000 )
    v13 = 4096;
  Pool2 = ExAllocatePool2(66, v13, 1834184771);
  P = (PVOID)Pool2;
  if ( !Pool2 )
  {
    v17 = -1073741670;
LABEL_46:
    Socket = RxCeGetSocket(a1);
    if ( (Microsoft_Windows_SMBClientEnableBits & 0x20) != 0 )
      McTemplateK0pppqqq_EtwWriteTransfer(
        a1[80],
        (unsigned int)CompressionFailure,
        v22,
        (_DWORD)a1,
        Socket,
        a3,
        v9,
        v17,
        a1[80]);
    if ( P )
      ExFreePoolWithTag(P, 0x6D537043u);
    *a6 = 0;
    *a7 = 0;
    goto LABEL_51;
  }
  v34 = 0;
  v18 = (v7 != 0 ? 0x50 : 0) + Pool2;
  *(_DWORD *)v18 = 1112364028;
  *(_WORD *)(v18 + 8) = 0;
  *(_DWORD *)(v18 + 4) = v9;
  *(_WORD *)(v18 + 10) = 0;
  *(_DWORD *)(v18 + 12) = 0;
  if ( (*(_DWORD *)(a2 + 20) & 1) != 0 )
  {
    MappedSystemVa = 0;
    v20 = SmbCompressionMdlCompress((unsigned int)a1[148], a3, (unsigned int)v9, v18 + 8, &v32);
    v32 += 8;
    v17 = v20;
    *(_WORD *)(v18 + 10) |= 1u;
  }
  else
  {
    if ( !v14 )
    {
      v17 = -1073741811;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_0b76558862d83d69241eb93c2054c057_Traceguids, a3);
      }
      goto LABEL_46;
    }
    *(_WORD *)(v18 + 8) = v14;
    if ( v15 )
    {
      v24 = *(struct _MDL **)a3;
      if ( **(_QWORD **)a3 || v24->ByteCount <= 0x1000 )
      {
        MappedSystemVa = (PVOID)ExAllocatePool2(66, v9, 1834184771);
        if ( !MappedSystemVa )
        {
          v17 = -1073741670;
LABEL_44:
          ExFreePoolWithTag(MappedSystemVa, 0x6D537043u);
          goto LABEL_45;
        }
        v34 = 1;
        RtlCopyMdlToBuffer(a3, 0, MappedSystemVa, v9, &v33);
        ByteCount = (unsigned int)v9;
        if ( v33 != v9 )
          __int2c();
      }
      else
      {
        if ( (v24->MdlFlags & 5) != 0 )
          MappedSystemVa = v24->MappedSystemVa;
        else
          MappedSystemVa = MmMapLockedPagesSpecifyCache(v24, 0, MmCached, 0, 0, 0x40000010u);
        ByteCount = v24->ByteCount;
        v25 = *(_DWORD *)(a3 + 40);
        *(_DWORD *)(v18 + 4) -= v25;
        *(_DWORD *)(v18 + 12) = v25;
      }
    }
    else
    {
      if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
        MappedSystemVa = *(PVOID *)(a3 + 24);
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000010u);
      if ( !MappedSystemVa )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_0b76558862d83d69241eb93c2054c057_Traceguids, a3);
        }
        v17 = -1073741670;
        goto LABEL_46;
      }
      ByteCount = (unsigned int)v9;
    }
    v17 = SmbCompressionLegacyCompress(
            (unsigned int)a1[148],
            MappedSystemVa,
            ByteCount,
            v18 + *(unsigned int *)(v18 + 12) + 16LL,
            &v32);
    v32 += 16 + *(_DWORD *)(v18 + 12);
    if ( *(_DWORD *)(v18 + 12) )
    {
      if ( (*(_BYTE *)(a3 + 10) & 5) != 0 )
        v26 = *(PVOID *)(a3 + 24);
      else
        v26 = MmMapLockedPagesSpecifyCache((PMDL)a3, 0, MmCached, 0, 0, 0x40000010u);
      memmove((void *)(v18 + 16), v26, *(unsigned int *)(v18 + 12));
    }
  }
  if ( v17 >= 0 )
  {
    if ( v32 < (unsigned int)v9 )
    {
      Mdl2 = (struct _MDL *)RxAllocateMdl2(v18, v32, 0, 0, 0);
      v30 = a6;
      *a6 = Mdl2;
      if ( Mdl2 )
      {
        MmBuildMdlForNonPagedPool(Mdl2);
        if ( a5 )
          (*v30)->MdlFlags |= 0x1000u;
        *a7 = v32;
      }
      else
      {
        v17 = -1073741670;
      }
    }
    else
    {
      v17 = -1073741789;
    }
  }
  if ( v34 )
    goto LABEL_44;
LABEL_45:
  if ( v17 < 0 )
    goto LABEL_46;
LABEL_51:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_dLLDq(WPP_GLOBAL_Control->AttachedDevice, v21, v22, (unsigned int)v17, v9, v32, a1[148], a1);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140053fd0  mov     [rsp-38h+arg_8], rbx
0x140053fd5  push    rbp
0x140053fd6  push    rsi
0x140053fd7  push    rdi
0x140053fd8  push    r12
0x140053fda  push    r13
0x140053fdc  push    r14
0x140053fde  push    r15
0x140053fe0  mov     rbp, rsp
0x140053fe3  sub     rsp, 60h
0x140053fe7  mov     sil, [rbp+arg_20]
0x140053feb  mov     rdi, r8
0x140053fee  mov     al, sil
0x140053ff1  mov     r12d, r9d
0x140053ff4  neg     al
0x140053ff6  mov     [rbp+arg_10], 0
0x140053ffe  mov     r13, rdx
0x140054001  mov     [rbp+arg_0], 0
0x140054008  sbb     r10d, r10d
0x14005400b  mov     r15, rcx
0x14005400e  and     r10d, 50h
0x140054012  add     r10d, 10h
0x140054016  lea     eax, [r10+r12]
0x14005401a  cmp     eax, r10d
0x14005401d  jb      loc_140054447
0x140054023  mov     ebx, [rcx+24Ch]
0x140054029  mov     ecx, 1000h
0x14005402e  mov     r14, [r8]
0x140054031  test    sil, sil
0x140054034  jz      short loc_14005403B
0x140054036  cmp     eax, ecx
0x140054038  cmovb   eax, ecx
0x14005403b  mov     edx, eax
0x14005403d  mov     ecx, 42h ; 'B'
0x140054042  mov     r8d, 6D537043h
0x140054048  call    cs:__imp_ExAllocatePool2
0x14005404f  nop     dword ptr [rax+rax+00h]
0x140054054  mov     [rbp+P], rax
0x140054058  mov     rdx, rax
0x14005405b  lea     r8, WPP_GLOBAL_Control
0x140054062  test    rax, rax
0x140054065  jnz     short loc_140054079
0x140054067  mov     ebx, 0C000009Ah
0x14005406c  xor     r13d, r13d
0x14005406f  mov     esi, 1000h
0x140054074  jmp     loc_14005432E
0x140054079  mov     al, sil
0x14005407c  mov     [rbp+arg_18], 0
0x140054080  neg     al
0x140054082  sbb     rcx, rcx
0x140054085  xor     eax, eax
0x140054087  and     ecx, 50h
0x14005408a  lea     rsi, [rcx+rdx]
0x14005408e  mov     edx, 1
0x140054093  lea     rcx, [rsi+8]
0x140054097  mov     dword ptr [rsi], 424D53FCh
0x14005409d  mov     [rcx], ax
0x1400540a0  mov     [rsi+4], r12d
0x1400540a4  mov     [rsi+0Ah], ax
0x1400540a8  mov     [rsi+0Ch], eax
0x1400540ab  mov     eax, [r13+14h]
0x1400540af  xor     r13d, r13d
0x1400540b2  test    dl, al
0x1400540b4  jz      short loc_1400540EA
0x1400540b6  lea     rax, [rbp+arg_0]
0x1400540ba  mov     r9, rcx
0x1400540bd  mov     ecx, [r15+250h]
0x1400540c4  mov     r8d, r12d
0x1400540c7  mov     rdx, rdi
0x1400540ca  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax
0x1400540cf  mov     r14d, r13d
0x1400540d2  call    SmbCompressionMdlCompress
0x1400540d7  add     [rbp+arg_0], 8
0x1400540db  mov     ebx, eax
0x1400540dd  lea     eax, [r13+1]
0x1400540e1  or      [rsi+0Ah], ax
0x1400540e5  jmp     loc_1400542F8
0x1400540ea  test    ebx, ebx
0x1400540ec  jnz     short loc_140054137
0x1400540ee  mov     ebx, 0C000000Dh
0x1400540f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400540fa  mov     esi, 1000h
0x1400540ff  cmp     rcx, r8
0x140054102  jz      loc_14005432E
0x140054108  test    [rcx+2Ch], esi
0x14005410b  jz      loc_14005432E
0x140054111  cmp     [rcx+29h], dl
0x140054114  jb      loc_14005432E
0x14005411a  mov     rcx, [rcx+18h]
0x14005411e  lea     r8, WPP_0b76558862d83d69241eb93c2054c057_Traceguids
0x140054125  mov     edx, 11h
0x14005412a  mov     r9, rdi
0x14005412d  call    WPP_SF_q
0x140054132  jmp     loc_14005432E
0x140054137  mov     [rcx], bx
0x14005413a  mov     ecx, 40000010h
0x14005413f  test    r14, r14
0x140054142  jnz     loc_1400541CC
0x140054148  test    byte ptr [rdi+0Ah], 5
0x14005414c  jz      short loc_140054154
0x14005414e  mov     r14, [rdi+18h]
0x140054152  jmp     short loc_140054183
0x140054154  mov     [rsp+60h+Priority], ecx; Priority
0x140054158  mov     r8d, edx; CacheType
0x14005415b  xor     edx, edx; AccessMode
0x14005415d  mov     [rsp+60h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x140054162  mov     rcx, rdi; MemoryDescriptorList
0x140054165  xor     r9d, r9d; RequestedAddress
0x140054168  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14005416f  nop     dword ptr [rax+rax+00h]
0x140054174  mov     edx, 1
0x140054179  lea     r8, WPP_GLOBAL_Control
0x140054180  mov     r14, rax
0x140054183  test    r14, r14
0x140054186  jnz     short loc_1400541C4
0x140054188  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005418f  mov     esi, 1000h
0x140054194  cmp     rcx, r8
0x140054197  jz      short loc_1400541BA
0x140054199  test    [rcx+2Ch], esi
0x14005419c  jz      short loc_1400541BA
0x14005419e  cmp     [rcx+29h], dl
0x1400541a1  jb      short loc_1400541BA
0x1400541a3  mov     rcx, [rcx+18h]
0x1400541a7  lea     edx, [r14+12h]
0x1400541ab  mov     r9, rdi
0x1400541ae  lea     r8, WPP_0b76558862d83d69241eb93c2054c057_Traceguids
0x1400541b5  call    WPP_SF_q
0x1400541ba  mov     ebx, 0C000009Ah
0x1400541bf  jmp     loc_14005432E
0x1400541c4  mov     r8d, r12d
0x1400541c7  jmp     loc_14005427E
0x1400541cc  mov     rbx, [rdi]
0x1400541cf  cmp     [rbx], r13
0x1400541d2  jnz     short loc_14005421B
0x1400541d4  cmp     dword ptr [rbx+28h], 1000h
0x1400541db  jbe     short loc_14005421B
0x1400541dd  test    byte ptr [rbx+0Ah], 5
0x1400541e1  jz      short loc_1400541E9
0x1400541e3  mov     r14, [rbx+18h]
0x1400541e7  jmp     short loc_14005420C
0x1400541e9  mov     [rsp+60h+Priority], ecx; Priority
0x1400541ed  mov     r8d, edx; CacheType
0x1400541f0  xor     edx, edx; AccessMode
0x1400541f2  mov     [rsp+60h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400541f7  mov     rcx, rbx; MemoryDescriptorList
0x1400541fa  xor     r9d, r9d; RequestedAddress
0x1400541fd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140054204  nop     dword ptr [rax+rax+00h]
0x140054209  mov     r14, rax
0x14005420c  mov     r8d, [rbx+28h]
0x140054210  mov     eax, [rdi+28h]
0x140054213  sub     [rsi+4], eax
0x140054216  mov     [rsi+0Ch], eax
0x140054219  jmp     short loc_14005427E
0x14005421b  mov     r8d, 6D537043h
0x140054221  mov     rdx, r12
0x140054224  mov     ecx, 42h ; 'B'
0x140054229  mov     rbx, r12
0x14005422c  call    cs:__imp_ExAllocatePool2
0x140054233  nop     dword ptr [rax+rax+00h]
0x140054238  mov     r14, rax
0x14005423b  test    rax, rax
0x14005423e  jnz     short loc_14005424F
0x140054240  mov     ebx, 0C000009Ah
0x140054245  mov     esi, 1000h
0x14005424a  jmp     loc_140054316
0x14005424f  lea     rax, [rbp+arg_10]
0x140054253  mov     [rbp+arg_18], 1
0x140054257  mov     r9, rbx
0x14005425a  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax
0x14005425f  mov     r8, r14
0x140054262  xor     edx, edx
0x140054264  mov     rcx, rdi
0x140054267  call    cs:__imp_RtlCopyMdlToBuffer
0x14005426e  nop     dword ptr [rax+rax+00h]
0x140054273  mov     r8d, r12d
0x140054276  cmp     [rbp+arg_10], rbx
0x14005427a  jz      short loc_14005427E
0x14005427c  int     2Ch; Windows NT - assertion failure
0x14005427e  mov     r9d, [rsi+0Ch]
0x140054282  lea     rax, [rbp+arg_0]
0x140054286  mov     ecx, [r15+250h]
0x14005428d  add     r9, 10h
0x140054291  add     r9, rsi
0x140054294  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax
0x140054299  mov     rdx, r14
0x14005429c  call    SmbCompressionLegacyCompress
0x1400542a1  mov     ecx, [rsi+0Ch]
0x1400542a4  mov     ebx, eax
0x1400542a6  mov     eax, [rbp+arg_0]
0x1400542a9  add     eax, 10h
0x1400542ac  add     ecx, eax
0x1400542ae  mov     [rbp+arg_0], ecx
0x1400542b1  cmp     [rsi+0Ch], r13d
0x1400542b5  jbe     short loc_1400542F8
0x1400542b7  test    byte ptr [rdi+0Ah], 5
0x1400542bb  jz      short loc_1400542C3
0x1400542bd  mov     rax, [rdi+18h]
0x1400542c1  jmp     short loc_1400542E8
0x1400542c3  xor     r9d, r9d; RequestedAddress
0x1400542c6  mov     [rsp+60h+Priority], 40000010h; Priority
0x1400542ce  xor     edx, edx; AccessMode
0x1400542d0  mov     [rsp+60h+BugCheckOnFailure], r13d; BugCheckOnFailure
0x1400542d5  mov     rcx, rdi; MemoryDescriptorList
0x1400542d8  lea     r8d, [r9+1]; CacheType
0x1400542dc  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400542e3  nop     dword ptr [rax+rax+00h]
0x1400542e8  mov     r8d, [rsi+0Ch]; Size
0x1400542ec  lea     rcx, [rsi+10h]; void *
0x1400542f0  mov     rdx, rax; Src
0x1400542f3  call    memmove
0x1400542f8  test    ebx, ebx
0x1400542fa  js      short loc_14005430B
0x1400542fc  cmp     [rbp+arg_0], r12d
0x140054300  jb      loc_1400543DE
0x140054306  mov     ebx, 0C0000023h
0x14005430b  mov     esi, 1000h
0x140054310  cmp     [rbp+arg_18], r13b
0x140054314  jz      short loc_14005432A
0x140054316  mov     edx, 6D537043h; Tag
0x14005431b  mov     rcx, r14; P
0x14005431e  call    cs:__imp_ExFreePoolWithTag
0x140054325  nop     dword ptr [rax+rax+00h]
0x14005432a  test    ebx, ebx
0x14005432c  jns     short loc_140054394
0x14005432e  mov     rcx, r15
0x140054331  call    RxCeGetSocket
0x140054336  test    cs:Microsoft_Windows_SMBClientEnableBits, 20h
0x14005433d  jz      short loc_14005436C
0x14005433f  mov     ecx, [r15+140h]
0x140054346  lea     rdx, CompressionFailure
0x14005434d  mov     [rsp+60h+var_20], ecx
0x140054351  mov     r9, r15
0x140054354  mov     dword ptr [rsp+60h+var_28], ebx
0x140054358  mov     [rsp+60h+var_30], r12d
0x14005435d  mov     qword ptr [rsp+60h+Priority], rdi
0x140054362  mov     qword ptr [rsp+60h+BugCheckOnFailure], rax
0x140054367  call    McTemplateK0pppqqq_EtwWriteTransfer
0x14005436c  mov     rcx, [rbp+P]; P
0x140054370  test    rcx, rcx
0x140054373  jz      short loc_140054386
0x140054375  mov     edx, 6D537043h; Tag
0x14005437a  call    cs:__imp_ExFreePoolWithTag
0x140054381  nop     dword ptr [rax+rax+00h]
0x140054386  mov     rax, [rbp+arg_28]
0x14005438a  mov     [rax], r13
0x14005438d  mov     rax, [rbp+arg_30]
0x140054391  mov     [rax], r13d
0x140054394  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005439b  lea     rax, WPP_GLOBAL_Control
0x1400543a2  cmp     rcx, rax
0x1400543a5  jz      short loc_1400543DA
0x1400543a7  test    [rcx+2Ch], esi
0x1400543aa  jz      short loc_1400543DA
0x1400543ac  cmp     byte ptr [rcx+29h], 4
0x1400543b0  jb      short loc_1400543DA
0x1400543b2  mov     eax, [r15+250h]
0x1400543b9  mov     r9d, ebx
0x1400543bc  mov     rcx, [rcx+18h]
0x1400543c0  mov     [rsp+60h+var_28], r15
0x1400543c5  mov     [rsp+60h+var_30], eax
0x1400543c9  mov     eax, [rbp+arg_0]
0x1400543cc  mov     [rsp+60h+Priority], eax
0x1400543d0  mov     [rsp+60h+BugCheckOnFailure], r12d
0x1400543d5  call    WPP_SF_dLLDq
0x1400543da  mov     eax, ebx
0x1400543dc  jmp     short loc_14005444C
0x1400543de  mov     edx, [rbp+arg_0]
0x1400543e1  xor     r9d, r9d
0x1400543e4  xor     r8d, r8d
0x1400543e7  mov     qword ptr [rsp+60h+BugCheckOnFailure], r13
0x1400543ec  mov     rcx, rsi
0x1400543ef  call    cs:__imp_RxAllocateMdl2
0x1400543f6  nop     dword ptr [rax+rax+00h]
0x1400543fb  mov     rsi, [rbp+arg_28]
0x1400543ff  mov     [rsi], rax
0x140054402  test    rax, rax
0x140054405  jnz     short loc_140054411
0x140054407  mov     ebx, 0C000009Ah
0x14005440c  jmp     loc_14005430B
0x140054411  mov     rcx, rax; MemoryDescriptorList
0x140054414  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14005441b  nop     dword ptr [rax+rax+00h]
0x140054420  cmp     [rbp+arg_20], r13b
0x140054424  jz      short loc_140054434
0x140054426  mov     rax, [rsi]
0x140054429  mov     esi, 1000h
0x14005442e  or      [rax+0Ah], si
0x140054432  jmp     short loc_140054439
0x140054434  mov     esi, 1000h
0x140054439  mov     rcx, [rbp+arg_30]
0x14005443d  mov     eax, [rbp+arg_0]
0x140054440  mov     [rcx], eax
0x140054442  jmp     loc_140054310
0x140054447  mov     eax, 0C000042Bh
0x14005444c  mov     rbx, [rsp+60h+arg_8]
0x140054454  add     rsp, 60h
0x140054458  pop     r15
0x14005445a  pop     r14
  ... truncated ...
```
