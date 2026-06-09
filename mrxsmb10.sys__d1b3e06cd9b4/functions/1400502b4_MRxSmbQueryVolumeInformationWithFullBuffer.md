# MRxSmbQueryVolumeInformationWithFullBuffer

- ea: `0x1400502b4`
- end: `0x14005078c`
- name: `MRxSmbQueryVolumeInformationWithFullBuffer`
- size: `1240`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400501d0`

## callees

- `0x14000a340`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x1400166c0`
- `0x1400169c0`
- `0x14002cc54`
- `0x1400502b4`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400506f7`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400506f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050761`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140050761`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050755`
- `ntoskrnl!ExReleaseResourceLite` at `0x140050755`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005067d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005067d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050667`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140050667`
- `ntoskrnl!ExAllocatePool2` at `0x1400506c8`
- `ntoskrnl!ExAllocatePool2` at `0x1400506c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400506a0`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140050710`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140050710`

## pseudocode

```c
__int64 __fastcall MRxSmbQueryVolumeInformationWithFullBuffer(__int64 a1)
{
  __int64 v1; // rax
  int *v2; // rbx
  int v3; // r12d
  _DWORD *v4; // r13
  unsigned int v6; // r15d
  __int64 v7; // rax
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // rsi
  int v12; // eax
  __int64 v13; // rcx
  __int16 v14; // ax
  int v15; // edx
  __int16 v16; // r14
  int v17; // r14d
  __int64 v18; // rax
  __int64 v19; // rcx
  __int16 *v20; // rcx
  int v21; // edx
  __int16 v22; // ax
  signed int v23; // r15d
  void *v24; // rcx
  size_t v25; // r12
  __int64 v26; // rbx
  ULONG TimeIncrement; // eax
  __int64 v28; // [rsp+80h] [rbp-80h]
  _DWORD v29[44]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v30; // [rsp+150h] [rbp+50h] BYREF
  __int16 v31; // [rsp+158h] [rbp+58h] BYREF
  int v32; // [rsp+160h] [rbp+60h] BYREF
  __int64 v33; // [rsp+168h] [rbp+68h]

  v1 = *(_QWORD *)(a1 + 56);
  v2 = (int *)(a1 + 472);
  v3 = *(_DWORD *)(a1 + 448);
  v4 = *(_DWORD **)(a1 + 456);
  v6 = *(_DWORD *)(a1 + 472);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v7 = *(_QWORD *)(v1 + 120);
  if ( v3 == 4 )
  {
    if ( v6 >= 8 )
    {
      v4[1] = 16;
      if ( *(_BYTE *)(v7 + 77) == 1 )
        *(_DWORD *)(v7 + 80) = 17;
      *v4 = *(_DWORD *)(v7 + 80);
      *v2 -= 8;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
      }
      return 0;
    }
    return 3221225507LL;
  }
  v9 = *(_QWORD *)(a1 + 64);
  v33 = v9;
  if ( !v9 )
    return 3221225485LL;
  v10 = *(_QWORD *)(*(_QWORD *)(v7 + 32) + 32LL);
  v28 = v10;
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 40LL) + 40LL) + 104LL);
  v12 = *(_DWORD *)(a1 + 120);
  if ( (v12 & 0x1000) != 0 )
  {
    if ( (v12 & 2) == 0 )
    {
      *(_BYTE *)(a1 + 35) = 1;
      return 3225485315LL;
    }
    *(_DWORD *)(a1 + 120) = v12 & 0xFFFFEFFF;
  }
  if ( v3 == 1 && MEMORY[0xFFFFF78000000320] < *(_QWORD *)(v11 + 1224) )
  {
    if ( (unsigned int)*v2 >= *(_DWORD *)(v11 + 1216) )
    {
      memmove(v4, *(const void **)(v11 + 1208), *(int *)(v11 + 1216));
      *v2 -= *(_DWORD *)(v11 + 1216);
      return 0;
    }
    return 3221225507LL;
  }
  while ( 1 )
  {
    if ( **(_WORD **)(*(_QWORD *)(a1 + 72) + 40LL) != 0xEB12 )
    {
      v13 = *(_QWORD *)(a1 + 56);
      v14 = *(_WORD *)(v13 + 360);
      if ( !v14 || v14 == 2 && **(_BYTE **)(v13 + 368) == 92 )
        SmbCeReconnect(*(PVOID *)(*(_QWORD *)(*(_QWORD *)(v9 + 32) + 40LL) + 40LL));
    }
    v15 = *(_DWORD *)(v10 + 420);
    if ( (v15 & 0x10000000) != 0 && v3 == 5 )
    {
LABEL_37:
      v16 = 261;
      goto LABEL_41;
    }
    if ( (v15 & 0x40000) == 0 )
      break;
    switch ( v3 )
    {
      case 1:
        v16 = 258;
        break;
      case 2:
        v16 = 257;
        break;
      case 3:
        v16 = 259;
        break;
      case 5:
        goto LABEL_37;
      default:
        if ( (v15 & 0x20000000) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids);
          }
          v17 = -1073741811;
          goto LABEL_47;
        }
        v16 = v3 + 1000;
        break;
    }
LABEL_41:
    memset(v29, 0, 0x68u);
    v18 = *(_QWORD *)(v33 + 32);
    v19 = 0;
    if ( v18 )
      v19 = *(_QWORD *)(v18 + 48);
    if ( (*(_DWORD *)(v28 + 420) & 0x4000000) != 0 )
    {
      LOWORD(v32) = v16;
      v30 = 15;
      v21 = 4;
      v22 = *(_WORD *)(v19 + 8);
      v20 = (__int16 *)&v32;
      HIWORD(v32) = v22;
    }
    else
    {
      v31 = v16;
      v30 = 3;
      v20 = &v31;
      v21 = 2;
    }
    v17 = SmbCeTransact(
            a1,
            (int)&RxDefaultTransactionOptions,
            (int)&v30,
            2,
            0,
            0,
            (__int64)v20,
            v21,
            0,
            0,
            0,
            0,
            (__int64)v4,
            *v2,
            (__int64)v29);
    if ( v17 >= 0 )
    {
      *v2 -= v29[15];
      goto LABEL_54;
    }
LABEL_47:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids,
        (unsigned int)v17);
    if ( v17 != -1073741623 )
      goto LABEL_54;
    v9 = v33;
    v10 = v28;
  }
  v17 = MRxSmbCoreInformation(a1, v3, (_DWORD)v4, (_DWORD)v2, 3);
LABEL_54:
  if ( !v17 && v3 == 1 )
  {
    v23 = v6 - *v2;
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
    if ( v23 <= *(_DWORD *)(v11 + 1216) )
    {
      v25 = v23;
    }
    else
    {
      v24 = *(void **)(v11 + 1208);
      if ( v24 )
      {
        ExFreePoolWithTag(v24, 0);
        *(_QWORD *)(v11 + 1208) = 0;
      }
      v25 = v23;
      *(_QWORD *)(v11 + 1208) = ExAllocatePool2(258, v23, 1347513683);
    }
    if ( *(_QWORD *)(v11 + 1208) )
    {
      v26 = MEMORY[0xFFFFF78000000320];
      TimeIncrement = KeQueryTimeIncrement();
      *(_QWORD *)(v11 + 1224) = v26
                              + 0x989680
                              / TimeIncrement
                              * (unsigned __int64)*(unsigned int *)(MRxSmbGetConfigurationBlock(
                                                                      TimeIncrement,
                                                                      0x989680 % TimeIncrement)
                                                                  + 144);
      memmove(*(void **)(v11 + 1208), v4, v25);
    }
    else
    {
      v23 = 0;
    }
    *(_DWORD *)(v11 + 1216) = v23;
    ExReleaseResourceLite(&s_SmbCeDbResource);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400502b4  push    rbp
0x1400502b6  push    rbx
0x1400502b7  push    rsi
0x1400502b8  push    rdi
0x1400502b9  push    r12
0x1400502bb  push    r13
0x1400502bd  push    r14
0x1400502bf  push    r15
0x1400502c1  lea     rbp, [rsp-8]
0x1400502c6  sub     rsp, 108h
0x1400502cd  mov     rax, [rcx+38h]
0x1400502d1  lea     rbx, [rcx+1D8h]
0x1400502d8  mov     r12d, [rcx+1C0h]
0x1400502df  xor     r9d, r9d
0x1400502e2  mov     r13, [rcx+1C8h]
0x1400502e9  mov     rdi, rcx
0x1400502ec  mov     r15d, [rbx]
0x1400502ef  mov     [rbp+40h+arg_0], r9w
0x1400502f4  mov     [rbp+40h+arg_8], r9w
0x1400502f9  mov     [rbp+40h+arg_10], r9d
0x1400502fd  mov     rax, [rax+78h]
0x140050301  cmp     r12d, 4
0x140050305  jnz     short loc_140050368
0x140050307  cmp     r15d, 8
0x14005030b  jb      loc_1400503D7
0x140050311  mov     dword ptr [r13+4], 10h
0x140050319  cmp     byte ptr [rax+4Dh], 1
0x14005031d  jnz     short loc_140050326
0x14005031f  mov     dword ptr [rax+50h], 11h
0x140050326  mov     eax, [rax+50h]
0x140050329  mov     [r13+0], eax
0x14005032d  add     dword ptr [rbx], 0FFFFFFF8h
0x140050330  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140050337  lea     rax, WPP_GLOBAL_Control
0x14005033e  cmp     rcx, rax
0x140050341  jz      short loc_140050361
0x140050343  test    dword ptr [rcx+2Ch], 400h
0x14005034a  jz      short loc_140050361
0x14005034c  mov     rcx, [rcx+18h]
0x140050350  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x140050357  mov     edx, 35h ; '5'
0x14005035c  call    WPP_SF_
0x140050361  xor     eax, eax
0x140050363  jmp     loc_140050777
0x140050368  mov     rdx, [rcx+40h]
0x14005036c  mov     [rbp+40h+arg_18], rdx
0x140050370  test    rdx, rdx
0x140050373  jz      loc_140050772
0x140050379  mov     rax, [rax+20h]
0x14005037d  mov     r10d, 2
0x140050383  mov     r14, [rax+20h]
0x140050387  mov     rax, [rdx+20h]
0x14005038b  mov     [rbp+40h+var_C0], r14
0x14005038f  mov     rcx, [rax+28h]
0x140050393  mov     rax, [rcx+28h]
0x140050397  mov     rsi, [rax+68h]
0x14005039b  mov     eax, [rdi+78h]
0x14005039e  bt      eax, 0Ch
0x1400503a2  jnb     short loc_1400503B0
0x1400503a4  test    r10b, al
0x1400503a7  jz      short loc_1400503E1
0x1400503a9  btr     eax, 0Ch
0x1400503ad  mov     [rdi+78h], eax
0x1400503b0  mov     rax, 0FFFFF78000000320h
0x1400503ba  cmp     r12d, 1
0x1400503be  jnz     short loc_14005040E
0x1400503c0  mov     rax, [rax]
0x1400503c3  cmp     rax, [rsi+4C8h]
0x1400503ca  jge     short loc_14005040E
0x1400503cc  movsxd  rax, dword ptr [rsi+4C0h]
0x1400503d3  cmp     [rbx], eax
0x1400503d5  jnb     short loc_1400503EF
0x1400503d7  mov     eax, 0C0000023h
0x1400503dc  jmp     loc_140050777
0x1400503e1  mov     byte ptr [rdi+23h], 1
0x1400503e5  mov     eax, 0C0410003h
0x1400503ea  jmp     loc_140050777
0x1400503ef  mov     rdx, [rsi+4B8h]; Src
0x1400503f6  mov     r8, rax; Size
0x1400503f9  mov     rcx, r13; void *
0x1400503fc  call    memmove
0x140050401  mov     eax, [rsi+4C0h]
0x140050407  sub     [rbx], eax
0x140050409  jmp     loc_140050361
0x14005040e  lea     r8, WPP_GLOBAL_Control
0x140050415  mov     rax, [rdi+48h]
0x140050419  mov     r11d, 102h
0x14005041f  mov     rcx, [rax+28h]
0x140050423  mov     eax, 0EB12h
0x140050428  cmp     [rcx], ax
0x14005042b  jz      short loc_140050473
0x14005042d  mov     rcx, [rdi+38h]
0x140050431  movzx   eax, word ptr [rcx+168h]
0x140050438  test    ax, ax
0x14005043b  jz      short loc_14005044F
0x14005043d  cmp     ax, r10w
0x140050441  jnz     short loc_140050473
0x140050443  mov     rax, [rcx+170h]
0x14005044a  cmp     byte ptr [rax], 5Ch ; '\'
0x14005044d  jnz     short loc_140050473
0x14005044f  mov     rax, [rdx+20h]
0x140050453  mov     rcx, [rax+28h]
0x140050457  mov     rcx, [rcx+28h]; Context
0x14005045b  call    SmbCeReconnect
0x140050460  lea     r8, WPP_GLOBAL_Control
0x140050467  mov     r10d, 2
0x14005046d  mov     r11d, 102h
0x140050473  mov     edx, [r14+1A4h]
0x14005047a  bt      edx, 1Ch
0x14005047e  jnb     short loc_140050486
0x140050480  cmp     r12d, 5
0x140050484  jz      short loc_1400504F4
0x140050486  bt      edx, 12h
0x14005048a  jnb     loc_140050635
0x140050490  mov     ecx, r12d
0x140050493  sub     ecx, 1
0x140050496  jz      short loc_14005050C
0x140050498  sub     ecx, 1
0x14005049b  jz      short loc_140050504
0x14005049d  sub     ecx, 1
0x1400504a0  jz      short loc_1400504FC
0x1400504a2  cmp     ecx, r10d
0x1400504a5  jz      short loc_1400504F4
0x1400504a7  bt      edx, 1Dh
0x1400504ab  jnb     short loc_1400504B8
0x1400504ad  mov     r14d, 3E8h
0x1400504b3  add     r14d, r12d
0x1400504b6  jmp     short loc_140050510
0x1400504b8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400504bf  cmp     rcx, r8
0x1400504c2  jz      short loc_1400504E9
0x1400504c4  test    dword ptr [rcx+2Ch], 400h
0x1400504cb  jz      short loc_1400504E9
0x1400504cd  mov     rcx, [rcx+18h]
0x1400504d1  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x1400504d8  mov     edx, 36h ; '6'
0x1400504dd  call    WPP_SF_
0x1400504e2  lea     r8, WPP_GLOBAL_Control
0x1400504e9  mov     r14d, 0C000000Dh
0x1400504ef  jmp     loc_1400505DE
0x1400504f4  mov     r14d, 105h
0x1400504fa  jmp     short loc_140050510
0x1400504fc  mov     r14d, 103h
0x140050502  jmp     short loc_140050510
0x140050504  mov     r14d, 101h
0x14005050a  jmp     short loc_140050510
0x14005050c  movzx   r14d, r11w
0x140050510  xor     edx, edx; Val
0x140050512  lea     rcx, [rbp+40h+var_B0]; void *
0x140050516  lea     r8d, [rdx+68h]; Size
0x14005051a  call    memset
0x14005051f  mov     rcx, [rbp+40h+arg_18]
0x140050523  xor     r8d, r8d
0x140050526  mov     rax, [rcx+20h]
0x14005052a  mov     ecx, r8d
0x14005052d  test    rax, rax
0x140050530  jz      short loc_140050536
0x140050532  mov     rcx, [rax+30h]
0x140050536  mov     rax, [rbp+40h+var_C0]
0x14005053a  test    dword ptr [rax+1A4h], 4000000h
0x140050544  jnz     short loc_14005055D
0x140050546  mov     eax, 3
0x14005054b  mov     [rbp+40h+arg_8], r14w
0x140050550  mov     [rbp+40h+arg_0], ax
0x140050554  lea     rcx, [rbp+40h+arg_8]
0x140050558  lea     edx, [rax-1]
0x14005055b  jmp     short loc_14005057C
0x14005055d  mov     eax, 0Fh
0x140050562  mov     word ptr [rbp+40h+arg_10], r14w
0x140050567  mov     [rbp+40h+arg_0], ax
0x14005056b  mov     edx, 4
0x140050570  movzx   eax, word ptr [rcx+8]
0x140050574  lea     rcx, [rbp+40h+arg_10]
0x140050578  mov     word ptr [rbp+40h+arg_10+2], ax
0x14005057c  lea     rax, [rbp+40h+var_B0]
0x140050580  mov     r9d, 2
0x140050586  mov     [rsp+140h+var_D0], rax
0x14005058b  mov     eax, [rbx]
0x14005058d  mov     [rsp+140h+var_D8], eax
0x140050591  mov     [rsp+140h+var_E0], r13
0x140050596  mov     [rsp+140h+var_E8], r8d
0x14005059b  mov     [rsp+140h+var_F0], r8
0x1400505a0  mov     [rsp+140h+var_F8], r8d
0x1400505a5  mov     [rsp+140h+var_100], r8
0x1400505aa  mov     [rsp+140h+var_108], edx
0x1400505ae  lea     rdx, RxDefaultTransactionOptions
0x1400505b5  mov     [rsp+140h+var_110], rcx
0x1400505ba  mov     rcx, rdi
0x1400505bd  mov     [rsp+140h+var_118], r8d
0x1400505c2  mov     [rsp+140h+var_120], r8
0x1400505c7  lea     r8, [rbp+40h+arg_0]
0x1400505cb  call    SmbCeTransact
0x1400505d0  mov     r14d, eax
0x1400505d3  test    eax, eax
0x1400505d5  jns     short loc_14005062E
0x1400505d7  lea     r8, WPP_GLOBAL_Control
0x1400505de  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400505e5  cmp     rcx, r8
0x1400505e8  jz      short loc_140050612
0x1400505ea  test    dword ptr [rcx+2Ch], 400h
0x1400505f1  jz      short loc_140050612
0x1400505f3  mov     rcx, [rcx+18h]
0x1400505f7  lea     r8, WPP_7d6027e1c1d238a68a87f0b00a4de3fe_Traceguids
0x1400505fe  mov     edx, 37h ; '7'
0x140050603  mov     r9d, r14d
0x140050606  call    WPP_SF_d
0x14005060b  lea     r8, WPP_GLOBAL_Control
0x140050612  cmp     r14d, 0C00000C9h
0x140050619  jnz     short loc_140050651
0x14005061b  mov     rdx, [rbp+40h+arg_18]
0x14005061f  mov     r10d, 2
0x140050625  mov     r14, [rbp+40h+var_C0]
0x140050629  jmp     loc_140050415
0x14005062e  mov     eax, [rbp+40h+var_74]
0x140050631  sub     [rbx], eax
0x140050633  jmp     short loc_140050651
0x140050635  mov     r9, rbx
0x140050638  mov     dword ptr [rsp+140h+var_120], 3
0x140050640  mov     r8, r13
0x140050643  mov     edx, r12d
0x140050646  mov     rcx, rdi
0x140050649  call    MRxSmbCoreInformation
0x14005064e  mov     r14d, eax
0x140050651  test    r14d, r14d
0x140050654  jnz     loc_14005076D
0x14005065a  cmp     r12d, 1
0x14005065e  jnz     loc_14005076D
0x140050664  sub     r15d, [rbx]
0x140050667  call    cs:__imp_KeEnterCriticalRegion
0x14005066e  nop     dword ptr [rax+rax+00h]
0x140050673  mov     dl, r12b; Wait
0x140050676  lea     rcx, s_SmbCeDbResource; Resource
0x14005067d  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140050684  nop     dword ptr [rax+rax+00h]
0x140050689  cmp     r15d, [rsi+4C0h]
0x140050690  jle     short loc_1400506DD
0x140050692  mov     rcx, [rsi+4B8h]; P
0x140050699  test    rcx, rcx
0x14005069c  jz      short loc_1400506B7
0x14005069e  xor     edx, edx; Tag
0x1400506a0  call    cs:__imp_ExFreePoolWithTag
0x1400506a7  nop     dword ptr [rax+rax+00h]
0x1400506ac  mov     qword ptr [rsi+4B8h], 0
0x1400506b7  movsxd  r12, r15d
0x1400506ba  mov     r8d, 50516D53h
0x1400506c0  mov     rdx, r12
0x1400506c3  mov     ecx, 102h
0x1400506c8  call    cs:__imp_ExAllocatePool2
0x1400506cf  nop     dword ptr [rax+rax+00h]
0x1400506d4  mov     [rsi+4B8h], rax
0x1400506db  jmp     short loc_1400506E0
0x1400506dd  movsxd  r12, r15d
0x1400506e0  cmp     qword ptr [rsi+4B8h], 0
0x1400506e8  jz      short loc_140050744
0x1400506ea  mov     rbx, 0FFFFF78000000320h
0x1400506f4  mov     rbx, [rbx]
0x1400506f7  call    cs:__imp_KeQueryTimeIncrement
0x1400506fe  nop     dword ptr [rax+rax+00h]
0x140050703  mov     ecx, eax
0x140050705  xor     edx, edx
0x140050707  mov     eax, 989680h
0x14005070c  div     ecx
0x14005070e  mov     edi, eax
0x140050710  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140050717  nop     dword ptr [rax+rax+00h]
0x14005071c  mov     r8, r12; Size
0x14005071f  mov     rdx, r13; Src
0x140050722  mov     ecx, [rax+90h]
0x140050728  imul    rcx, rdi
0x14005072c  add     rcx, rbx
0x14005072f  mov     [rsi+4C8h], rcx
0x140050736  mov     rcx, [rsi+4B8h]; void *
0x14005073d  call    memmove
0x140050742  jmp     short loc_140050747
0x140050744  xor     r15d, r15d
0x140050747  lea     rcx, s_SmbCeDbResource; Resource
0x14005074e  mov     [rsi+4C0h], r15d
0x140050755  call    cs:__imp_ExReleaseResourceLite
0x14005075c  nop     dword ptr [rax+rax+00h]
0x140050761  call    cs:__imp_KeLeaveCriticalRegion
0x140050768  nop     dword ptr [rax+rax+00h]
0x14005076d  mov     eax, r14d
0x140050770  jmp     short loc_140050777
0x140050772  mov     eax, 0C000000Dh
0x140050777  add     rsp, 108h
0x14005077e  pop     r15
0x140050780  pop     r14
0x140050782  pop     r13
0x140050784  pop     r12
0x140050786  pop     rdi
0x140050787  pop     rsi
0x140050788  pop     rbx
0x140050789  pop     rbp
0x14005078a  retn
```
