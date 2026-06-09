# HsmIBitmapNORMALMarkRangeEx

- ea: `0x1400654a8`
- end: `0x140065940`
- name: `HsmIBitmapNORMALMarkRangeEx`
- size: `1176`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140065164`
- `0x1400651c4`

## callees

- `0x140003c50`
- `0x14001886c`
- `0x14001a764`
- `0x14001a844`
- `0x14001e580`
- `0x1400654a8`
- `0x140065948`

## import_xrefs

- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065609`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006592f`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x140065609`
- `ntoskrnl!FsRtlRemoveBaseMcbEntry` at `0x14006592f`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140065631`
- `ntoskrnl!FsRtlAddBaseMcbEntry` at `0x140065631`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1400655b8`
- `ntoskrnl!FsRtlInitializeBaseMcbEx` at `0x1400655b8`
- `ntoskrnl!RtlComputeCrc32` at `0x140065849`
- `ntoskrnl!RtlComputeCrc32` at `0x140065849`
- `ntoskrnl!ExAllocatePool2` at `0x140065594`
- `ntoskrnl!ExAllocatePool2` at `0x1400657ad`
- `ntoskrnl!ExAllocatePool2` at `0x140065594`
- `ntoskrnl!ExAllocatePool2` at `0x1400657ad`
- `FLTMGR!FltReleasePushLockEx` at `0x140065676`
- `FLTMGR!FltReleasePushLockEx` at `0x14006581b`
- `FLTMGR!FltReleasePushLockEx` at `0x140065864`
- `FLTMGR!FltReleasePushLockEx` at `0x140065676`
- `FLTMGR!FltReleasePushLockEx` at `0x14006581b`
- `FLTMGR!FltReleasePushLockEx` at `0x140065864`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065566`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065784`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065566`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140065784`

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
  unsigned int v11; // esi
  int v12; // r8d
  __int64 v13; // rcx
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
  if ( (v11 & 0x80000000) == 0 )
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
            HsmDbgBreakOnStatus(3221225626LL);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 26, v21, a1, *(_QWORD *)a1, a1 + 32, 154);
            }
            FltReleasePushLockEx(a1 + 48, 0);
            return v11;
          }
          memset(Pool2, -1, 0x1000u);
          v22 = *(_QWORD *)(a1 + 56);
          *(_DWORD *)(v22 + 4092) = RtlComputeCrc32(0, (PUCHAR)v22, 0xFFCu);
          *(_DWORD *)(a1 + 16) &= ~0x10u;
        }
        FltReleasePushLockEx(a1 + 48, 0);
        v4 = a4;
      }
      v13 = *(unsigned int *)(a1 + 24);
      if ( (int)v13 >= 0 )
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
              HsmDbgBreakOnStatus(3221225626LL);
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
          HsmDbgBreakOnStatus(3221225626LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 27, v23, a1, *(_QWORD *)a1, a1 + 32, 154);
          }
          v11 = -1073741670;
        }
        FltReleasePushLockEx(a1 + 64, 0);
        if ( (v11 & 0x80000000) == 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qislii(WPP_GLOBAL_Control->AttachedDevice, v17, v18, a1, *(_QWORD *)a1, a1 + 32, v4, v6, v7);
        }
        return v11;
      }
LABEL_31:
      v11 = v13;
      HsmDbgBreakOnStatus(v13);
      return v11;
    }
LABEL_30:
    v13 = 3221225701LL;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 25, v12, a1, *(_QWORD *)a1, a1 + 32, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x1400654a8  mov     [rsp+arg_10], rbx
0x1400654ad  mov     [rsp+arg_18], r9d
0x1400654b2  push    rbp
0x1400654b3  push    rsi
0x1400654b4  push    rdi
0x1400654b5  push    r12
0x1400654b7  push    r13
0x1400654b9  push    r14
0x1400654bb  push    r15
0x1400654bd  sub     rsp, 50h
0x1400654c1  mov     r12d, r9d
0x1400654c4  mov     rdi, rcx
0x1400654c7  test    rdx, rdx
0x1400654ca  jz      loc_1400656E8
0x1400654d0  mov     r15, [rdx]
0x1400654d3  test    r8, r8
0x1400654d6  jz      loc_1400656F0
0x1400654dc  mov     rbp, [r8]
0x1400654df  cmp     r15, rbp
0x1400654e2  jge     loc_1400656F9
0x1400654e8  mov     ecx, [rcx+10h]
0x1400654eb  mov     eax, 1
0x1400654f0  shr     ecx, 6
0x1400654f3  and     ecx, 3Fh
0x1400654f6  shl     eax, cl
0x1400654f8  mov     r13d, eax
0x1400654fb  lea     rcx, [rax-1]
0x1400654ff  mov     rbx, rcx
0x140065502  add     rcx, [rdi+8]
0x140065506  not     rbx
0x140065509  and     rcx, rbx
0x14006550c  cmp     rbp, rcx
0x14006550f  jg      loc_1400656F9
0x140065515  mov     rcx, rdi
0x140065518  call    HsmiBitmapNORMALEnsureOpened
0x14006551d  mov     ecx, eax
0x14006551f  mov     esi, eax
0x140065521  call    HsmDbgBreakOnStatus
0x140065526  test    esi, esi
0x140065528  js      loc_14006570A
0x14006552e  cmp     rbp, [rdi+8]
0x140065532  jz      loc_140065762
0x140065538  mov     rax, rbp
0x14006553b  lea     ecx, [r13-1]
0x14006553f  or      rax, r15
0x140065542  test    rax, rcx
0x140065545  jnz     loc_1400656F9
0x14006554b  cmp     r12d, 2
0x14006554f  jz      loc_140065770
0x140065555  mov     ecx, [rdi+18h]
0x140065558  test    ecx, ecx
0x14006555a  js      loc_1400656FE
0x140065560  lea     rcx, [rdi+40h]
0x140065564  xor     edx, edx
0x140065566  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006556d  nop     dword ptr [rax+rax+00h]
0x140065572  movsxd  rbx, r12d
0x140065575  lea     r14, WPP_GLOBAL_Control
0x14006557c  cmp     qword ptr [rdi+rbx*8+58h], 0
0x140065582  jnz     short loc_1400655CC
0x140065584  mov     edx, 18h
0x140065589  mov     ecx, 100h
0x14006558e  mov     r8d, 634D7348h
0x140065594  call    cs:__imp_ExAllocatePool2
0x14006559b  nop     dword ptr [rax+rax+00h]
0x1400655a0  mov     [rdi+rbx*8+58h], rax
0x1400655a5  test    rax, rax
0x1400655a8  jz      loc_14006587D
0x1400655ae  xor     r8d, r8d; Flags
0x1400655b1  mov     rcx, rax; Mcb
0x1400655b4  lea     edx, [r8+1]; PoolType
0x1400655b8  call    cs:__imp_FsRtlInitializeBaseMcbEx
0x1400655bf  nop     dword ptr [rax+rax+00h]
0x1400655c4  test    al, al
0x1400655c6  jz      loc_14006587D
0x1400655cc  mov     rax, rbp
0x1400655cf  sub     rax, r15
0x1400655d2  cqo
0x1400655d4  idiv    r13
0x1400655d7  mov     [rsp+88h+SectorCount], rax
0x1400655df  mov     rcx, rax
0x1400655e2  test    rax, rax
0x1400655e5  jle     loc_140065670
0x1400655eb  mov     rax, r15
0x1400655ee  mov     r8, rcx; SectorCount
0x1400655f1  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x1400655f6  cqo
0x1400655f8  idiv    r13
0x1400655fb  mov     rdx, rax; Vbn
0x1400655fe  mov     [rsp+88h+Vbn], rax
0x140065606  mov     r13, rax
0x140065609  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x140065610  nop     dword ptr [rax+rax+00h]
0x140065615  mov     rdx, [rsp+88h+Vbn]; Vbn
0x14006561d  lea     r8, [r13+1]; Lbn
0x140065621  mov     r13, [rsp+88h+SectorCount]
0x140065629  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x14006562e  mov     r9, r13; SectorCount
0x140065631  call    cs:__imp_FsRtlAddBaseMcbEntry
0x140065638  nop     dword ptr [rax+rax+00h]
0x14006563d  test    al, al
0x14006563f  jz      loc_1400658CF
0x140065645  mov     r14, [rsp+88h+Vbn]
0x14006564d  xor     ebx, ebx
0x14006564f  cmp     ebx, r12d
0x140065652  jz      short loc_140065662
0x140065654  mov     rcx, [rdi+rbx*8+58h]; Mcb
0x140065659  test    rcx, rcx
0x14006565c  jnz     loc_140065929
0x140065662  inc     ebx
0x140065664  cmp     ebx, 3
0x140065667  jl      short loc_14006564F
0x140065669  lea     r14, WPP_GLOBAL_Control
0x140065670  xor     edx, edx
0x140065672  lea     rcx, [rdi+40h]
0x140065676  call    cs:__imp_FltReleasePushLockEx
0x14006567d  nop     dword ptr [rax+rax+00h]
0x140065682  test    esi, esi
0x140065684  jns     short loc_1400656A1
0x140065686  mov     rbx, [rsp+88h+arg_10]
0x14006568e  mov     eax, esi
0x140065690  add     rsp, 50h
0x140065694  pop     r15
0x140065696  pop     r14
0x140065698  pop     r13
0x14006569a  pop     r12
0x14006569c  pop     rdi
0x14006569d  pop     rsi
0x14006569e  pop     rbp
0x14006569f  retn
0x1400656a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400656a8  cmp     rcx, r14
0x1400656ab  jz      short loc_140065686
0x1400656ad  mov     eax, [rcx+2Ch]
0x1400656b0  test    al, 1
0x1400656b2  jz      short loc_140065686
0x1400656b4  cmp     byte ptr [rcx+29h], 4
0x1400656b8  jb      short loc_140065686
0x1400656ba  mov     rcx, [rcx+18h]
0x1400656be  lea     rax, [rdi+20h]
0x1400656c2  mov     [rsp+88h+var_48], rbp
0x1400656c7  mov     r9, rdi
0x1400656ca  mov     [rsp+88h+var_50], r15
0x1400656cf  mov     [rsp+88h+var_58], r12d
0x1400656d4  mov     [rsp+88h+var_60], rax
0x1400656d9  mov     rax, [rdi]
0x1400656dc  mov     [rsp+88h+var_68], rax
0x1400656e1  call    WPP_SF_qislii
0x1400656e6  jmp     short loc_140065686
0x1400656e8  xor     r15d, r15d
0x1400656eb  jmp     loc_1400654D3
0x1400656f0  lea     r8, [rcx+8]
0x1400656f4  jmp     loc_1400654DC
0x1400656f9  mov     ecx, 0C00000E5h
0x1400656fe  mov     esi, ecx
0x140065700  call    HsmDbgBreakOnStatus
0x140065705  jmp     loc_140065686
0x14006570a  mov     rcx, cs:WPP_GLOBAL_Control
0x140065711  lea     r14, WPP_GLOBAL_Control
0x140065718  cmp     rcx, r14
0x14006571b  jz      loc_140065686
0x140065721  mov     edx, [rcx+2Ch]
0x140065724  test    dl, 1
0x140065727  jz      loc_140065686
0x14006572d  cmp     byte ptr [rcx+29h], 2
0x140065731  jb      loc_140065686
0x140065737  mov     rcx, [rcx+18h]
0x14006573b  lea     rax, [rdi+20h]
0x14006573f  mov     [rsp+88h+var_58], esi
0x140065743  mov     edx, 19h
0x140065748  mov     [rsp+88h+var_60], rax
0x14006574d  mov     r9, rdi
0x140065750  mov     rax, [rdi]
0x140065753  mov     [rsp+88h+var_68], rax
0x140065758  call    WPP_SF_qisd
0x14006575d  jmp     loc_140065686
0x140065762  dec     rbp
0x140065765  add     rbp, r13
0x140065768  and     rbp, rbx
0x14006576b  jmp     loc_140065538
0x140065770  mov     eax, [rdi+10h]
0x140065773  test    al, 10h
0x140065775  jz      loc_140065555
0x14006577b  lea     r12, [rdi+30h]
0x14006577f  xor     edx, edx
0x140065781  mov     rcx, r12
0x140065784  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14006578b  nop     dword ptr [rax+rax+00h]
0x140065790  mov     eax, [rdi+10h]
0x140065793  test    al, 10h
0x140065795  jz      loc_14006585F
0x14006579b  mov     ebx, 1000h
0x1400657a0  mov     r8d, 6D427348h
0x1400657a6  mov     edx, ebx
0x1400657a8  mov     ecx, 102h
0x1400657ad  call    cs:__imp_ExAllocatePool2
0x1400657b4  nop     dword ptr [rax+rax+00h]
0x1400657b9  mov     [rdi+38h], rax
0x1400657bd  test    rax, rax
0x1400657c0  jnz     short loc_14006582C
0x1400657c2  mov     ebx, 0C000009Ah
0x1400657c7  mov     ecx, ebx
0x1400657c9  mov     esi, ebx
0x1400657cb  call    HsmDbgBreakOnStatus
0x1400657d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400657d7  lea     r14, WPP_GLOBAL_Control
0x1400657de  cmp     rcx, r14
0x1400657e1  jz      short loc_140065816
0x1400657e3  mov     eax, [rcx+2Ch]
0x1400657e6  test    al, 1
0x1400657e8  jz      short loc_140065816
0x1400657ea  cmp     byte ptr [rcx+29h], 2
0x1400657ee  jb      short loc_140065816
0x1400657f0  mov     rcx, [rcx+18h]
0x1400657f4  lea     rax, [rdi+20h]
0x1400657f8  mov     [rsp+88h+var_58], ebx
0x1400657fc  mov     edx, 1Ah
0x140065801  mov     [rsp+88h+var_60], rax
0x140065806  mov     r9, rdi
0x140065809  mov     rax, [rdi]
0x14006580c  mov     [rsp+88h+var_68], rax
0x140065811  call    WPP_SF_qisd
0x140065816  xor     edx, edx
0x140065818  mov     rcx, r12
0x14006581b  call    cs:__imp_FltReleasePushLockEx
0x140065822  nop     dword ptr [rax+rax+00h]
0x140065827  jmp     loc_140065686
0x14006582c  mov     r8, rbx; Size
0x14006582f  or      edx, 0FFFFFFFFh; Val
0x140065832  mov     rcx, rax; void *
0x140065835  call    memset
0x14006583a  mov     rbx, [rdi+38h]
0x14006583e  mov     r8d, 0FFCh; Length
0x140065844  mov     rdx, rbx; Buffer
0x140065847  xor     ecx, ecx; InitialCrc
0x140065849  call    cs:__imp_RtlComputeCrc32
0x140065850  nop     dword ptr [rax+rax+00h]
0x140065855  mov     [rbx+0FFCh], eax
0x14006585b  and     dword ptr [rdi+10h], 0FFFFFFEFh
0x14006585f  xor     edx, edx
0x140065861  mov     rcx, r12
0x140065864  call    cs:__imp_FltReleasePushLockEx
0x14006586b  nop     dword ptr [rax+rax+00h]
0x140065870  mov     r12d, [rsp+88h+arg_18]
0x140065878  jmp     loc_140065555
0x14006587d  mov     ebx, 0C000009Ah
0x140065882  mov     ecx, ebx
0x140065884  call    HsmDbgBreakOnStatus
0x140065889  mov     rcx, cs:WPP_GLOBAL_Control
0x140065890  cmp     rcx, r14
0x140065893  jz      short loc_1400658C8
0x140065895  mov     eax, [rcx+2Ch]
0x140065898  test    al, 1
0x14006589a  jz      short loc_1400658C8
0x14006589c  cmp     byte ptr [rcx+29h], 2
0x1400658a0  jb      short loc_1400658C8
0x1400658a2  mov     rcx, [rcx+18h]
0x1400658a6  lea     rax, [rdi+20h]
0x1400658aa  mov     [rsp+88h+var_58], ebx
0x1400658ae  mov     edx, 1Bh
0x1400658b3  mov     [rsp+88h+var_60], rax
0x1400658b8  mov     r9, rdi
0x1400658bb  mov     rax, [rdi]
0x1400658be  mov     [rsp+88h+var_68], rax
0x1400658c3  call    WPP_SF_qisd
0x1400658c8  mov     esi, ebx
0x1400658ca  jmp     loc_140065670
0x1400658cf  mov     ebx, 0C000009Ah
0x1400658d4  mov     ecx, ebx
0x1400658d6  mov     esi, ebx
0x1400658d8  call    HsmDbgBreakOnStatus
0x1400658dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400658e4  cmp     rcx, r14
0x1400658e7  jz      loc_140065670
0x1400658ed  mov     eax, [rcx+2Ch]
0x1400658f0  test    al, 1
0x1400658f2  jz      loc_140065670
0x1400658f8  cmp     byte ptr [rcx+29h], 2
0x1400658fc  jb      loc_140065670
0x140065902  mov     rcx, [rcx+18h]
0x140065906  lea     rax, [rdi+20h]
0x14006590a  mov     [rsp+88h+var_58], r12d
0x14006590f  mov     r9, rdi
0x140065912  mov     [rsp+88h+var_60], rax
0x140065917  mov     rax, [rdi]
0x14006591a  mov     [rsp+88h+var_68], rax
0x14006591f  call    WPP_SF_qisld
0x140065924  jmp     loc_140065670
0x140065929  mov     r8, r13; SectorCount
0x14006592c  mov     rdx, r14; Vbn
0x14006592f  call    cs:__imp_FsRtlRemoveBaseMcbEntry
0x140065936  nop     dword ptr [rax+rax+00h]
0x14006593b  jmp     loc_140065662
```
