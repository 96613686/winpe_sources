# HsmIBitmapNORMALMarkRangeEx

- ea: `0x1400655c8`
- end: `0x140065a60`
- name: `HsmIBitmapNORMALMarkRangeEx`
- size: `1176`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140065284`
- `0x1400652e4`

## callees

- `0x140003c50`
- `0x1400188ec`
- `0x14001a7e4`
- `0x14001a8c4`
- `0x14001e600`
- `0x1400655c8`
- `0x140065a68`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065729`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065a4f`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065729`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065a4f`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140065751`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140065751`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1400656d8`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1400656d8`
- `ntoskrnl!RtlComputeCrc32` at `0x140065969`
- `ntoskrnl!RtlComputeCrc32` at `0x140065969`
- `ntoskrnl!ExAllocatePool2` at `0x1400656b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400658cd`
- `ntoskrnl!ExAllocatePool2` at `0x1400656b4`
- `ntoskrnl!ExAllocatePool2` at `0x1400658cd`
- `FLTMGR!FltReleasePushLockEx` at `0x140065796`
- `FLTMGR!FltReleasePushLockEx` at `0x14006593b`
- `FLTMGR!FltReleasePushLockEx` at `0x140065984`
- `FLTMGR!FltReleasePushLockEx` at `0x140065796`
- `FLTMGR!FltReleasePushLockEx` at `0x14006593b`
- `FLTMGR!FltReleasePushLockEx` at `0x140065984`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065686`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400658a4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065686`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400658a4`

## pseudocode

```c
__int64 __fastcall HsmIBitmapNORMALMarkRangeEx(__int64 a1, __int64 *a2, __int64 *a3, int a4)
{
  int v4; // r12d
  __int64 v6; // r15
  __int64 v7; // rbp
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // rbx
  int v11; // esi
  int v12; // r8d
  int v13; // ecx
  BASE_MCB *v14; // rax
  __int64 v15; // rbx
  BASE_MCB *v16; // rcx
  int v17; // edx
  int v18; // r8d
  void *Pool2; // rax
  int v21; // r8d
  __int64 v22; // rbx
  int v23; // r8d
  int v24; // edx
  int v25; // r8d
  __int64 SectorCount; // [rsp+98h] [rbp+10h]

  v4 = a4;
  if ( a2 )
    v6 = *a2;
  else
    v6 = 0;
  if ( !a3 )
    a3 = (__int64 *)(a1 + 8);
  v7 = *a3;
  if ( v6 >= *a3 )
    goto LABEL_30;
  v8 = (unsigned int)(1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F));
  v9 = v8;
  v10 = ~(v8 - 1);
  if ( v7 > (v10 & (*(_QWORD *)(a1 + 8) + v8 - 1)) )
    goto LABEL_30;
  v11 = HsmiBitmapNORMALEnsureOpened(a1);
  HsmDbgBreakOnStatus(v11);
  if ( v11 >= 0 )
  {
    if ( v7 == *(_QWORD *)(a1 + 8) )
      v7 = v10 & (v9 + v7 - 1);
    if ( ((unsigned int)(v9 - 1) & (v6 | v7)) == 0 )
    {
      if ( v4 == 2 && (*(_DWORD *)(a1 + 16) & 0x10) != 0 )
      {
        FltAcquirePushLockExclusiveEx(a1 + 48, 0);
        if ( (*(_DWORD *)(a1 + 16) & 0x10) != 0 )
        {
          Pool2 = (void *)ExAllocatePool2(258, 4096, 1833071432);
          *(_QWORD *)(a1 + 56) = Pool2;
          if ( !Pool2 )
          {
            v11 = -1073741670;
            HsmDbgBreakOnStatus(-1073741670);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 26, v21, a1, *(_QWORD *)a1, a1 + 32, 154);
            }
            FltReleasePushLockEx(a1 + 48, 0);
            return (unsigned int)v11;
          }
          memset(Pool2, -1, 0x1000u);
          v22 = *(_QWORD *)(a1 + 56);
          *(_DWORD *)(v22 + 4092) = RtlComputeCrc32(0, (PUCHAR)v22, 0xFFCu);
          *(_DWORD *)(a1 + 16) &= ~0x10u;
        }
        FltReleasePushLockEx(a1 + 48, 0);
        v4 = a4;
      }
      v13 = *(_DWORD *)(a1 + 24);
      if ( v13 >= 0 )
      {
        FltAcquirePushLockExclusiveEx(a1 + 64, 0);
        if ( *(_QWORD *)(a1 + 8LL * v4 + 88)
          || (v14 = (BASE_MCB *)ExAllocatePool2(256, 24, 1666020168), (*(_QWORD *)(a1 + 8LL * v4 + 88) = v14) != 0)
          && FsRtlInitializeBaseMcbEx(v14, PagedPool, 0) )
        {
          SectorCount = (v7 - v6) / v9;
          if ( SectorCount > 0 )
          {
            FsRtlRemoveBaseMcbEntry(*(PBASE_MCB *)(a1 + 8LL * v4 + 88), v6 / v9, (v7 - v6) / v9);
            if ( FsRtlAddBaseMcbEntry(*(PBASE_MCB *)(a1 + 8LL * v4 + 88), v6 / v9, v6 / v9 + 1, SectorCount) )
            {
              v15 = 0;
              do
              {
                if ( (_DWORD)v15 != v4 )
                {
                  v16 = *(BASE_MCB **)(a1 + 8 * v15 + 88);
                  if ( v16 )
                    FsRtlRemoveBaseMcbEntry(v16, v6 / v9, SectorCount);
                }
                v15 = (unsigned int)(v15 + 1);
              }
              while ( (int)v15 < 3 );
            }
            else
            {
              v11 = -1073741670;
              HsmDbgBreakOnStatus(-1073741670);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qisld(WPP_GLOBAL_Control->AttachedDevice, v24, v25, a1, *(_QWORD *)a1, a1 + 32, v4);
              }
            }
          }
        }
        else
        {
          HsmDbgBreakOnStatus(-1073741670);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 27, v23, a1, *(_QWORD *)a1, a1 + 32, 154);
          }
          v11 = -1073741670;
        }
        FltReleasePushLockEx(a1 + 64, 0);
        if ( v11 >= 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qislii(WPP_GLOBAL_Control->AttachedDevice, v17, v18, a1, *(_QWORD *)a1, a1 + 32, v4, v6, v7);
        }
        return (unsigned int)v11;
      }
LABEL_31:
      v11 = v13;
      HsmDbgBreakOnStatus(v13);
      return (unsigned int)v11;
    }
LABEL_30:
    v13 = -1073741595;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 25, v12, a1, *(_QWORD *)a1, a1 + 32, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400655c8  mov     [rsp+arg_10], rbx
0x1400655cd  mov     [rsp+arg_18], r9d
0x1400655d2  push    rbp
0x1400655d3  push    rsi
0x1400655d4  push    rdi
0x1400655d5  push    r12
0x1400655d7  push    r13
0x1400655d9  push    r14
0x1400655db  push    r15
0x1400655dd  sub     rsp, 50h
0x1400655e1  mov     r12d, r9d
0x1400655e4  mov     rdi, rcx
0x1400655e7  test    rdx, rdx
0x1400655ea  jz      loc_140065808
0x1400655f0  mov     r15, [rdx]
0x1400655f3  test    r8, r8
0x1400655f6  jz      loc_140065810
0x1400655fc  mov     rbp, [r8]
0x1400655ff  cmp     r15, rbp
0x140065602  jge     loc_140065819
0x140065608  mov     ecx, [rcx+10h]
0x14006560b  mov     eax, 1
0x140065610  shr     ecx, 6
0x140065613  and     ecx, 3Fh
0x140065616  shl     eax, cl
0x140065618  mov     r13d, eax
0x14006561b  lea     rcx, [rax-1]
0x14006561f  mov     rbx, rcx
0x140065622  add     rcx, [rdi+8]
0x140065626  not     rbx
0x140065629  and     rcx, rbx
0x14006562c  cmp     rbp, rcx
0x14006562f  jg      loc_140065819
0x140065635  mov     rcx, rdi
0x140065638  call    HsmiBitmapNORMALEnsureOpened
0x14006563d  mov     ecx, eax
0x14006563f  mov     esi, eax
0x140065641  call    HsmDbgBreakOnStatus
0x140065646  test    esi, esi
0x140065648  js      loc_14006582A
0x14006564e  cmp     rbp, [rdi+8]
0x140065652  jz      loc_140065882
0x140065658  mov     rax, rbp
0x14006565b  lea     ecx, [r13-1]
0x14006565f  or      rax, r15
0x140065662  test    rax, rcx
0x140065665  jnz     loc_140065819
0x14006566b  cmp     r12d, 2
0x14006566f  jz      loc_140065890
0x140065675  mov     ecx, [rdi+18h]
0x140065678  test    ecx, ecx
0x14006567a  js      loc_14006581E
0x140065680  lea     rcx, [rdi+40h]
0x140065684  xor     edx, edx
0x140065686  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006568d  nop     dword ptr [rax+rax+00h]
0x140065692  movsxd  rbx, r12d
0x140065695  lea     r14, WPP_GLOBAL_Control
0x14006569c  cmp     qword ptr [rdi+rbx*8+58h], 0
0x1400656a2  jnz     short loc_1400656EC
0x1400656a4  mov     edx, 18h
0x1400656a9  mov     ecx, 100h
0x1400656ae  mov     r8d, 634D7348h
0x1400656b4  call    cs:__imp_ExAllocatePool2
0x1400656bb  nop     dword ptr [rax+rax+00h]
0x1400656c0  mov     [rdi+rbx*8+58h], rax
0x1400656c5  test    rax, rax
0x1400656c8  jz      loc_14006599D
0x1400656ce  xor     r8d, r8d; Flags
0x1400656d1  mov     rcx, rax; Mcb
0x1400656d4  lea     edx, [r8+1]; PoolType
0x1400656d8  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x1400656df  nop     dword ptr [rax+rax+00h]
0x1400656e4  test    al, al
0x1400656e6  jz      loc_14006599D
0x1400656ec  mov     rax, rbp
0x1400656ef  sub     rax, r15
0x1400656f2  cqo
0x1400656f4  idiv    r13
0x1400656f7  mov     [rsp+88h+SectorCount], rax
0x1400656ff  mov     rcx, rax
0x140065702  test    rax, rax
0x140065705  jle     loc_140065790
0x14006570b  mov     rax, r15
0x14006570e  mov     r8, rcx; SectorCount
0x140065711  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x140065716  cqo
0x140065718  idiv    r13
0x14006571b  mov     rdx, rax; Vbn
0x14006571e  mov     [rsp+88h+Vbn], rax
0x140065726  mov     r13, rax
0x140065729  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x140065730  nop     dword ptr [rax+rax+00h]
0x140065735  mov     rdx, [rsp+88h+Vbn]; Vbn
0x14006573d  lea     r8, [r13+1]; Lbn
0x140065741  mov     r13, [rsp+88h+SectorCount]
0x140065749  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x14006574e  mov     r9, r13; SectorCount
0x140065751  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140065758  nop     dword ptr [rax+rax+00h]
0x14006575d  test    al, al
0x14006575f  jz      loc_1400659EF
0x140065765  mov     r14, [rsp+88h+Vbn]
0x14006576d  xor     ebx, ebx
0x14006576f  cmp     ebx, r12d
0x140065772  jz      short loc_140065782
0x140065774  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x140065779  test    rcx, rcx
0x14006577c  jnz     loc_140065A49
0x140065782  inc     ebx
0x140065784  cmp     ebx, 3
0x140065787  jl      short loc_14006576F
0x140065789  lea     r14, WPP_GLOBAL_Control
0x140065790  xor     edx, edx
0x140065792  lea     rcx, [rdi+40h]
0x140065796  call    cs:__imp_FltReleasePushLockEx
0x14006579d  nop     dword ptr [rax+rax+00h]
0x1400657a2  test    esi, esi
0x1400657a4  jns     short loc_1400657C1
0x1400657a6  mov     rbx, [rsp+88h+arg_10]
0x1400657ae  mov     eax, esi
0x1400657b0  add     rsp, 50h
0x1400657b4  pop     r15
0x1400657b6  pop     r14
0x1400657b8  pop     r13
0x1400657ba  pop     r12
0x1400657bc  pop     rdi
0x1400657bd  pop     rsi
0x1400657be  pop     rbp
0x1400657bf  retn
0x1400657c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400657c8  cmp     rcx, r14
0x1400657cb  jz      short loc_1400657A6
0x1400657cd  mov     eax, [rcx+2Ch]
0x1400657d0  test    al, 1
0x1400657d2  jz      short loc_1400657A6
0x1400657d4  cmp     byte ptr [rcx+29h], 4
0x1400657d8  jb      short loc_1400657A6
0x1400657da  mov     rcx, [rcx+18h]
0x1400657de  lea     rax, [rdi+20h]
0x1400657e2  mov     [rsp+88h+var_48], rbp
0x1400657e7  mov     r9, rdi
0x1400657ea  mov     [rsp+88h+var_50], r15
0x1400657ef  mov     [rsp+88h+var_58], r12d
0x1400657f4  mov     [rsp+88h+var_60], rax
0x1400657f9  mov     rax, [rdi]
0x1400657fc  mov     [rsp+88h+var_68], rax
0x140065801  call    WPP_SF_qislii
0x140065806  jmp     short loc_1400657A6
0x140065808  xor     r15d, r15d
0x14006580b  jmp     loc_1400655F3
0x140065810  lea     r8, [rcx+8]
0x140065814  jmp     loc_1400655FC
0x140065819  mov     ecx, 0C00000E5h
0x14006581e  mov     esi, ecx
0x140065820  call    HsmDbgBreakOnStatus
0x140065825  jmp     loc_1400657A6
0x14006582a  mov     rcx, cs:WPP_GLOBAL_Control
0x140065831  lea     r14, WPP_GLOBAL_Control
0x140065838  cmp     rcx, r14
0x14006583b  jz      loc_1400657A6
0x140065841  mov     edx, [rcx+2Ch]
0x140065844  test    dl, 1
0x140065847  jz      loc_1400657A6
0x14006584d  cmp     byte ptr [rcx+29h], 2
0x140065851  jb      loc_1400657A6
0x140065857  mov     rcx, [rcx+18h]
0x14006585b  lea     rax, [rdi+20h]
0x14006585f  mov     [rsp+88h+var_58], esi
0x140065863  mov     edx, 19h
0x140065868  mov     [rsp+88h+var_60], rax
0x14006586d  mov     r9, rdi
0x140065870  mov     rax, [rdi]
0x140065873  mov     [rsp+88h+var_68], rax
0x140065878  call    WPP_SF_qisd
0x14006587d  jmp     loc_1400657A6
0x140065882  dec     rbp
0x140065885  add     rbp, r13
0x140065888  and     rbp, rbx
0x14006588b  jmp     loc_140065658
0x140065890  mov     eax, [rdi+10h]
0x140065893  test    al, 10h
0x140065895  jz      loc_140065675
0x14006589b  lea     r12, [rdi+30h]
0x14006589f  xor     edx, edx
0x1400658a1  mov     rcx, r12
0x1400658a4  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400658ab  nop     dword ptr [rax+rax+00h]
0x1400658b0  mov     eax, [rdi+10h]
0x1400658b3  test    al, 10h
0x1400658b5  jz      loc_14006597F
0x1400658bb  mov     ebx, 1000h
0x1400658c0  mov     r8d, 6D427348h
0x1400658c6  mov     edx, ebx
0x1400658c8  mov     ecx, 102h
0x1400658cd  call    cs:__imp_ExAllocatePool2
0x1400658d4  nop     dword ptr [rax+rax+00h]
0x1400658d9  mov     [rdi+38h], rax
0x1400658dd  test    rax, rax
0x1400658e0  jnz     short loc_14006594C
0x1400658e2  mov     ebx, 0C000009Ah
0x1400658e7  mov     ecx, ebx
0x1400658e9  mov     esi, ebx
0x1400658eb  call    HsmDbgBreakOnStatus
0x1400658f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400658f7  lea     r14, WPP_GLOBAL_Control
0x1400658fe  cmp     rcx, r14
0x140065901  jz      short loc_140065936
0x140065903  mov     eax, [rcx+2Ch]
0x140065906  test    al, 1
0x140065908  jz      short loc_140065936
0x14006590a  cmp     byte ptr [rcx+29h], 2
0x14006590e  jb      short loc_140065936
0x140065910  mov     rcx, [rcx+18h]
0x140065914  lea     rax, [rdi+20h]
0x140065918  mov     [rsp+88h+var_58], ebx
0x14006591c  mov     edx, 1Ah
0x140065921  mov     [rsp+88h+var_60], rax
0x140065926  mov     r9, rdi
0x140065929  mov     rax, [rdi]
0x14006592c  mov     [rsp+88h+var_68], rax
0x140065931  call    WPP_SF_qisd
0x140065936  xor     edx, edx
0x140065938  mov     rcx, r12
0x14006593b  call    cs:__imp_FltReleasePushLockEx
0x140065942  nop     dword ptr [rax+rax+00h]
0x140065947  jmp     loc_1400657A6
0x14006594c  mov     r8, rbx; Size
0x14006594f  or      edx, 0FFFFFFFFh; Val
0x140065952  mov     rcx, rax; void *
0x140065955  call    memset
0x14006595a  mov     rbx, [rdi+38h]
0x14006595e  mov     r8d, 0FFCh; Length
0x140065964  mov     rdx, rbx; Buffer
0x140065967  xor     ecx, ecx; InitialCrc
0x140065969  call    cs:__imp_RtlComputeCrc32
0x140065970  nop     dword ptr [rax+rax+00h]
0x140065975  mov     [rbx+0FFCh], eax
0x14006597b  and     dword ptr [rdi+10h], 0FFFFFFEFh
0x14006597f  xor     edx, edx
0x140065981  mov     rcx, r12
0x140065984  call    cs:__imp_FltReleasePushLockEx
0x14006598b  nop     dword ptr [rax+rax+00h]
0x140065990  mov     r12d, [rsp+88h+arg_18]
0x140065998  jmp     loc_140065675
0x14006599d  mov     ebx, 0C000009Ah
0x1400659a2  mov     ecx, ebx
0x1400659a4  call    HsmDbgBreakOnStatus
0x1400659a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400659b0  cmp     rcx, r14
0x1400659b3  jz      short loc_1400659E8
0x1400659b5  mov     eax, [rcx+2Ch]
0x1400659b8  test    al, 1
0x1400659ba  jz      short loc_1400659E8
0x1400659bc  cmp     byte ptr [rcx+29h], 2
0x1400659c0  jb      short loc_1400659E8
0x1400659c2  mov     rcx, [rcx+18h]
0x1400659c6  lea     rax, [rdi+20h]
0x1400659ca  mov     [rsp+88h+var_58], ebx
0x1400659ce  mov     edx, 1Bh
0x1400659d3  mov     [rsp+88h+var_60], rax
0x1400659d8  mov     r9, rdi
0x1400659db  mov     rax, [rdi]
0x1400659de  mov     [rsp+88h+var_68], rax
0x1400659e3  call    WPP_SF_qisd
0x1400659e8  mov     esi, ebx
0x1400659ea  jmp     loc_140065790
0x1400659ef  mov     ebx, 0C000009Ah
0x1400659f4  mov     ecx, ebx
0x1400659f6  mov     esi, ebx
0x1400659f8  call    HsmDbgBreakOnStatus
0x1400659fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140065a04  cmp     rcx, r14
0x140065a07  jz      loc_140065790
0x140065a0d  mov     eax, [rcx+2Ch]
0x140065a10  test    al, 1
0x140065a12  jz      loc_140065790
0x140065a18  cmp     byte ptr [rcx+29h], 2
0x140065a1c  jb      loc_140065790
0x140065a22  mov     rcx, [rcx+18h]
0x140065a26  lea     rax, [rdi+20h]
0x140065a2a  mov     [rsp+88h+var_58], r12d
0x140065a2f  mov     r9, rdi
0x140065a32  mov     [rsp+88h+var_60], rax
0x140065a37  mov     rax, [rdi]
0x140065a3a  mov     [rsp+88h+var_68], rax
0x140065a3f  call    WPP_SF_qisld
0x140065a44  jmp     loc_140065790
0x140065a49  mov     r8, r13; SectorCount
0x140065a4c  mov     rdx, r14; Vbn
0x140065a4f  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x140065a56  nop     dword ptr [rax+rax+00h]
0x140065a5b  jmp     loc_140065782
```
