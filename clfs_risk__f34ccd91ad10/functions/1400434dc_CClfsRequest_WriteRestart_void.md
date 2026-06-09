# CClfsRequest::WriteRestart(void)

- ea: `0x1400434dc`
- end: `0x1400439cd`
- name: `?WriteRestart@CClfsRequest@@AEAAJXZ`
- size: `1265`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x14000c2f0`
- `0x14000f3d4`
- `0x14000f688`
- `0x14000fdd8`
- `0x140014d00`
- `0x140017e70`
- `0x140017f20`
- `0x1400358cc`
- `0x140035904`
- `0x140041098`
- `0x1400434dc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400437ce`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400437ce`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004379d`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004379d`
- `ntoskrnl!IoFreeMdl` at `0x140043765`
- `ntoskrnl!IoFreeMdl` at `0x140043765`
- `ntoskrnl!ProbeForRead` at `0x140043580`
- `ntoskrnl!ProbeForRead` at `0x140043580`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004371e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004371e`

## pseudocode

```c
__int64 __fastcall CClfsRequest::WriteRestart(CClfsRequest *this)
{
  int v2; // ebx
  char *v3; // r15
  __int64 v4; // rcx
  __int64 v5; // r13
  unsigned int v6; // eax
  __int64 v7; // rdi
  __int64 ULong64FromUser; // rax
  __int64 *v9; // rcx
  __int64 v10; // rax
  __int64 *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int AlignedBufferSize; // eax
  __int64 v15; // rcx
  _DWORD *PoolWithTag; // rcx
  PMDL v17; // rdi
  PVOID MappedSystemVa; // rax
  int v19; // ecx
  char *v20; // rdi
  __int64 v21; // rdx
  _QWORD v23[2]; // [rsp+98h] [rbp-50h] BYREF
  CClfsRequest *v24; // [rsp+A8h] [rbp-40h]
  char UCharFromUser; // [rsp+F8h] [rbp+10h]
  unsigned int v26; // [rsp+100h] [rbp+18h] BYREF
  PMDL Mdl; // [rsp+108h] [rbp+20h]

  v24 = this;
  Mdl = 0;
  v2 = 0;
  v23[0] = 0;
  v26 = 0;
  UCharFromUser = 0;
  v3 = (char *)this + 48;
  v23[1] = (char *)this + 48;
  v4 = *((_QWORD *)this + 6);
  v5 = *(_QWORD *)(v4 + 184);
  if ( *(_DWORD *)(v5 + 16) == 48 && (v6 = *(_DWORD *)(v5 + 8), *((_DWORD *)this + 66) = v6, v6 >= 0x70) )
  {
    *(_QWORD *)(v4 + 120) = this;
    v7 = *(_QWORD *)(v5 + 32);
    if ( v7 )
    {
      ProbeForRead(*(volatile void **)(v5 + 32), 0x30u, 4u);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        *((_QWORD *)this + 27) = RtlReadULong64FromUser(v7 + 24);
      else
        RtlCopyVolatileMemory((char *)this + 216, (const void *)(v7 + 24), 8u);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        *((_QWORD *)this + 28) = RtlReadULong64FromUser(v7 + 32);
      else
        RtlCopyVolatileMemory((char *)this + 224, (const void *)(v7 + 32), 8u);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        ULong64FromUser = RtlReadULong64FromUser(v7);
      else
        ULong64FromUser = *(_QWORD *)v7;
      *((_QWORD *)this + 30) = ULong64FromUser;
      v9 = (__int64 *)(v7 + 16);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        v10 = RtlReadULong64FromUser(v9);
      else
        v10 = *v9;
      *((_QWORD *)this + 31) = v10;
      v11 = (__int64 *)(v7 + 8);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        v12 = RtlReadULong64FromUser(v11);
      else
        v12 = *v11;
      *((_QWORD *)this + 32) = v12;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        UCharFromUser = RtlReadUCharFromUser(v7 + 40);
      else
        UCharFromUser = *(_BYTE *)(v7 + 40);
    }
    else
    {
      v2 = -1073741592;
    }
    if ( v2 >= 0 )
    {
      v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 48) + 24LL) + 120LL);
      *((_QWORD *)this + 18) = v13;
      *((_QWORD *)this + 19) = *(_QWORD *)(*(_QWORD *)(v5 + 48) + 32LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 64LL))(v13);
      CClfsLogCcb::AddRef(*((CClfsLogCcb **)this + 19));
      if ( (*(_BYTE *)(*(_QWORD *)v3 + 112LL) & 7) != 0 )
      {
        v2 = -1073741592;
      }
      else
      {
        AlignedBufferSize = CClfsRequest::GetAlignedBufferSize(this, *((_DWORD *)this + 66));
        v15 = *(_QWORD *)v3;
        LOBYTE(v15) = *(_BYTE *)(*(_QWORD *)v3 + 64LL);
        v2 = ClfsProbeAndAllocateMdl(v15, *(_QWORD *)(*(_QWORD *)v3 + 112LL), AlignedBufferSize);
        if ( v2 >= 0 )
        {
          PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x4A666C43u);
          if ( PoolWithTag )
          {
            *(_QWORD *)PoolWithTag = &CClfsMdlReference::`vftable';
            PoolWithTag[2] = 0;
            v17 = Mdl;
            *((_QWORD *)PoolWithTag + 2) = Mdl;
          }
          else
          {
            PoolWithTag = 0;
            v17 = Mdl;
          }
          *((_QWORD *)this + 10) = PoolWithTag;
          if ( PoolWithTag )
          {
            (**(void (__fastcall ***)(PVOID))PoolWithTag)(PoolWithTag);
            MmProbeAndLockPages(v17, *(_BYTE *)(*(_QWORD *)v3 + 64LL), IoModifyAccess);
            if ( (v17->MdlFlags & 5) != 0 )
              MappedSystemVa = v17->MappedSystemVa;
            else
              MappedSystemVa = MmMapLockedPagesSpecifyCache(v17, 0, MmCached, 0, 0, 0x40000010u);
            *((_QWORD *)this + 34) = MappedSystemVa;
            v19 = v2;
            if ( !MappedSystemVa )
              v19 = -1073741670;
            v2 = v19;
          }
          else
          {
            IoFreeMdl(v17);
            Mdl = 0;
            v2 = -1073741670;
          }
        }
      }
      if ( v2 >= 0 )
      {
        if ( (__int64)(*((_QWORD *)this + 30) + *(_QWORD *)(*((_QWORD *)this + 19) + 104LL)) >= 0 )
        {
          CClfsRequest_State::Change_State_WriteRestartPending(*((CClfsRequest_State **)this + 13), this);
          v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, char *, char *, char *, char, _BYTE, _BYTE, CClfsRequest *, char *, char *, char *, __int64, unsigned int *, _QWORD *))(**((_QWORD **)this + 18) + 152LL))(
                 *((_QWORD *)this + 18),
                 *(_QWORD *)(v5 + 48),
                 *((_QWORD *)this + 34),
                 *((unsigned int *)this + 66),
                 (char *)this + 240,
                 (char *)this + 248,
                 (char *)this + 256,
                 UCharFromUser,
                 0,
                 0,
                 this,
                 (char *)this + 216,
                 (char *)this + 224,
                 (char *)this + 208,
                 *((_QWORD *)this + 34) + 32LL,
                 &v26,
                 v23);
        }
        else
        {
          v2 = -1072037872;
        }
      }
    }
  }
  else
  {
    v2 = -1073741306;
  }
  if ( v2 < 0 )
  {
    v20 = (char *)v24 + 152;
  }
  else
  {
    v20 = (char *)this + 152;
    *(_QWORD *)(*((_QWORD *)this + 19) + 104LL) += v23[0];
  }
  if ( v2 == 259 )
  {
    *(_BYTE *)(*(_QWORD *)(*(_QWORD *)v3 + 184LL) + 3LL) |= 1u;
  }
  else
  {
    CClfsRequest_State::Change_State_Done(*((CClfsRequest_State **)this + 13), this);
    if ( v2 >= 0 )
    {
      v21 = *((_QWORD *)this + 34);
      if ( (*(_DWORD *)(*(_QWORD *)v20 + 28LL) & 8) == 0 )
        _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)v20 + 28LL), 8u);
      *(_QWORD *)(v21 + 24) = *((_QWORD *)this + 31);
    }
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = v2;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = v26;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400434dc  mov     rax, rsp
0x1400434df  mov     [rax+8], rcx
0x1400434e3  push    rbx
0x1400434e4  push    rsi
0x1400434e5  push    rdi
0x1400434e6  push    r12
0x1400434e8  push    r13
0x1400434ea  push    r14
0x1400434ec  push    r15
0x1400434ee  sub     rsp, 0B0h
0x1400434f5  mov     rsi, rcx
0x1400434f8  mov     [rsp+0E8h+var_40], rcx
0x140043500  xor     r14d, r14d
0x140043503  mov     [rax+20h], r14
0x140043507  mov     ebx, r14d
0x14004350a  mov     [rax-54h], ebx
0x14004350d  mov     [rax-50h], r14
0x140043511  mov     [rax+18h], r14d
0x140043515  mov     [rax+10h], r14b
0x140043519  lea     r15, [rcx+30h]
0x14004351d  mov     [rsp+0E8h+var_48], r15
0x140043525  mov     rcx, [r15]
0x140043528  mov     r13, [rcx+0B8h]
0x14004352f  lea     edx, [r14+30h]; Length
0x140043533  cmp     [r13+10h], edx
0x140043537  jz      short loc_14004354A
0x140043539  mov     ebx, 0C0000206h
0x14004353e  mov     [rsp+0E8h+var_54], ebx
0x140043545  jmp     loc_14004392D
0x14004354a  mov     eax, [r13+8]
0x14004354e  mov     [rsi+108h], eax
0x140043554  cmp     eax, 70h ; 'p'
0x140043557  jb      short loc_140043539
0x140043559  mov     [rcx+78h], rsi
0x14004355d  mov     rdi, [r13+20h]
0x140043561  test    rdi, rdi
0x140043564  jnz     short loc_140043577
0x140043566  mov     ebx, 0C00000E8h
0x14004356b  mov     [rsp+0E8h+var_54], ebx
0x140043572  jmp     loc_140043673
0x140043577  mov     r8d, 4; Alignment
0x14004357d  mov     rcx, rdi; Address
0x140043580  call    cs:__imp_ProbeForRead
0x140043587  nop     dword ptr [rax+rax+00h]
0x14004358c  lea     rdx, [rdi+18h]; Src
0x140043590  lea     r12, [rsi+0D8h]
0x140043597  mov     rax, [r15]
0x14004359a  cmp     [rax+40h], r14b
0x14004359e  jz      short loc_1400435AE
0x1400435a0  mov     rcx, rdx
0x1400435a3  call    RtlReadULong64FromUser
0x1400435a8  mov     [r12], rax
0x1400435ac  jmp     short loc_1400435BC
0x1400435ae  mov     r8d, 8; Size
0x1400435b4  mov     rcx, r12; void *
0x1400435b7  call    RtlCopyVolatileMemory
0x1400435bc  lea     rdx, [rdi+20h]; Src
0x1400435c0  lea     r12, [rsi+0E0h]
0x1400435c7  mov     rax, [r15]
0x1400435ca  cmp     [rax+40h], r14b
0x1400435ce  jz      short loc_1400435DE
0x1400435d0  mov     rcx, rdx
0x1400435d3  call    RtlReadULong64FromUser
0x1400435d8  mov     [r12], rax
0x1400435dc  jmp     short loc_1400435EC
0x1400435de  mov     r8d, 8; Size
0x1400435e4  mov     rcx, r12; void *
0x1400435e7  call    RtlCopyVolatileMemory
0x1400435ec  mov     rax, [r15]
0x1400435ef  cmp     [rax+40h], r14b
0x1400435f3  jz      short loc_1400435FF
0x1400435f5  mov     rcx, rdi
0x1400435f8  call    RtlReadULong64FromUser
0x1400435fd  jmp     short loc_140043602
0x1400435ff  mov     rax, [rdi]
0x140043602  mov     [rsi+0F0h], rax
0x140043609  lea     rcx, [rdi+10h]
0x14004360d  mov     rax, [r15]
0x140043610  cmp     [rax+40h], r14b
0x140043614  jz      short loc_14004361D
0x140043616  call    RtlReadULong64FromUser
0x14004361b  jmp     short loc_140043620
0x14004361d  mov     rax, [rcx]
0x140043620  mov     [rsi+0F8h], rax
0x140043627  lea     rcx, [rdi+8]
0x14004362b  mov     rax, [r15]
0x14004362e  cmp     [rax+40h], r14b
0x140043632  jz      short loc_14004363B
0x140043634  call    RtlReadULong64FromUser
0x140043639  jmp     short loc_14004363E
0x14004363b  mov     rax, [rcx]
0x14004363e  mov     [rsi+100h], rax
0x140043645  mov     rax, [r15]
0x140043648  cmp     [rax+40h], r14b
0x14004364c  jz      short loc_140043662
0x14004364e  lea     rcx, [rdi+28h]
0x140043652  call    RtlReadUCharFromUser
0x140043657  mov     dl, al
0x140043659  mov     [rsp+0E8h+arg_8], al
0x140043660  jmp     short loc_14004366C
0x140043662  mov     dl, [rdi+28h]
0x140043665  mov     [rsp+0E8h+arg_8], dl
0x14004366c  mov     [rsp+0E8h+var_58], dl
0x140043673  test    ebx, ebx
0x140043675  js      loc_14004392D
0x14004367b  mov     rax, [r13+30h]
0x14004367f  mov     rcx, [rax+18h]
0x140043683  mov     rcx, [rcx+78h]
0x140043687  mov     [rsi+90h], rcx
0x14004368e  mov     rax, [r13+30h]
0x140043692  mov     rdx, [rax+20h]
0x140043696  mov     [rsi+98h], rdx
0x14004369d  mov     rax, [rcx]
0x1400436a0  mov     rax, [rax+40h]
0x1400436a4  call    _guard_dispatch_icall
0x1400436a9  mov     rcx, [rsi+98h]; this
0x1400436b0  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x1400436b5  nop
0x1400436b6  mov     rax, [r15]
0x1400436b9  test    byte ptr [rax+70h], 7
0x1400436bd  jz      short loc_1400436D0
0x1400436bf  mov     ebx, 0C00000E8h
0x1400436c4  mov     [rsp+0E8h+var_54], ebx
0x1400436cb  jmp     loc_1400437F7
0x1400436d0  mov     edx, [rsi+108h]; unsigned int
0x1400436d6  mov     rcx, rsi; this
0x1400436d9  call    ?GetAlignedBufferSize@CClfsRequest@@AEAAKK@Z; CClfsRequest::GetAlignedBufferSize(ulong)
0x1400436de  mov     rcx, [r15]
0x1400436e1  lea     rdx, [rsp+0E8h+Mdl]
0x1400436e9  mov     [rsp+0E8h+var_B8], rdx
0x1400436ee  mov     r8d, eax
0x1400436f1  mov     rdx, [rcx+70h]
0x1400436f5  mov     cl, [rcx+40h]
0x1400436f8  call    ClfsProbeAndAllocateMdl
0x1400436fd  mov     ebx, eax
0x1400436ff  mov     [rsp+0E8h+var_54], eax
0x140043706  test    eax, eax
0x140043708  js      loc_1400437F7
0x14004370e  mov     edx, 18h; NumberOfBytes
0x140043713  mov     ecx, 200h; PoolType
0x140043718  mov     r8d, 4A666C43h; Tag
0x14004371e  call    cs:__imp_ExAllocatePoolWithTag
0x140043725  nop     dword ptr [rax+rax+00h]
0x14004372a  mov     rcx, rax
0x14004372d  test    rax, rax
0x140043730  jz      short loc_14004374E
0x140043732  lea     rax, ??_7CClfsMdlReference@@6B@; const CClfsMdlReference::`vftable'
0x140043739  mov     [rcx], rax
0x14004373c  mov     [rcx+8], r14d
0x140043740  mov     rdi, [rsp+0E8h+Mdl]
0x140043748  mov     [rcx+10h], rdi
0x14004374c  jmp     short loc_140043759
0x14004374e  mov     rcx, r14
0x140043751  mov     rdi, [rsp+0E8h+Mdl]
0x140043759  mov     [rsi+50h], rcx
0x14004375d  test    rcx, rcx
0x140043760  jnz     short loc_140043783
0x140043762  mov     rcx, rdi; Mdl
0x140043765  call    cs:__imp_IoFreeMdl
0x14004376c  nop     dword ptr [rax+rax+00h]
0x140043771  mov     [rsp+0E8h+Mdl], r14
0x140043779  mov     ebx, 0C000009Ah
0x14004377e  jmp     loc_1400436C4
0x140043783  mov     rax, [rcx]
0x140043786  mov     rax, [rax]
0x140043789  call    _guard_dispatch_icall
0x14004378e  mov     rdx, [r15]
0x140043791  mov     r8d, 2; Operation
0x140043797  mov     dl, [rdx+40h]; AccessMode
0x14004379a  mov     rcx, rdi; MemoryDescriptorList
0x14004379d  call    cs:__imp_MmProbeAndLockPages
0x1400437a4  nop     dword ptr [rax+rax+00h]
0x1400437a9  test    byte ptr [rdi+0Ah], 5
0x1400437ad  jz      short loc_1400437B5
0x1400437af  mov     rax, [rdi+18h]
0x1400437b3  jmp     short loc_1400437DA
0x1400437b5  mov     [rsp+0E8h+Priority], 40000010h; Priority
0x1400437bd  mov     [rsp+0E8h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x1400437c2  xor     r9d, r9d; RequestedAddress
0x1400437c5  xor     edx, edx; AccessMode
0x1400437c7  lea     r8d, [r9+1]; CacheType
0x1400437cb  mov     rcx, rdi; MemoryDescriptorList
0x1400437ce  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400437d5  nop     dword ptr [rax+rax+00h]
0x1400437da  mov     [rsi+110h], rax
0x1400437e1  mov     ecx, ebx
0x1400437e3  mov     ebx, 0C000009Ah
0x1400437e8  test    rax, rax
0x1400437eb  cmovz   ecx, ebx
0x1400437ee  mov     ebx, ecx
0x1400437f0  mov     [rsp+0E8h+var_54], ecx
0x1400437f7  test    ebx, ebx
0x1400437f9  js      loc_14004392D
0x1400437ff  mov     rax, [rsi+98h]
0x140043806  mov     rcx, [rax+68h]
0x14004380a  add     rcx, [rsi+0F0h]
0x140043811  jns     short loc_14004381D
0x140043813  mov     ebx, 0C01A0010h
0x140043818  jmp     loc_14004353E
0x14004381d  mov     rdx, rsi; struct CClfsRequest *
0x140043820  mov     rcx, [rsi+68h]; this
0x140043824  call    ?Change_State_WriteRestartPending@CClfsRequest_State@@QEAAXPEAVCClfsRequest@@@Z; CClfsRequest_State::Change_State_WriteRestartPending(CClfsRequest *)
0x140043829  mov     rcx, [rsi+90h]
0x140043830  mov     r8, [rsi+110h]
0x140043837  mov     rax, [rcx]
0x14004383a  lea     rdx, [r8+20h]
0x14004383e  lea     r9, [rsi+0D0h]
0x140043845  lea     r10, [rsi+0E0h]
0x14004384c  lea     r11, [rsi+0D8h]
0x140043853  lea     rbx, [rsi+100h]
0x14004385a  lea     rdi, [rsi+0F8h]
0x140043861  mov     rax, [rax+98h]
0x140043868  lea     r12, [rsp+0E8h+var_50]
0x140043870  mov     [rsp+0E8h+var_68], r12
0x140043878  lea     r12, [rsp+0E8h+arg_10]
0x140043880  mov     [rsp+0E8h+var_70], r12
0x140043885  mov     [rsp+0E8h+var_78], rdx
0x14004388a  mov     [rsp+0E8h+var_80], r9
0x14004388f  mov     [rsp+0E8h+var_88], r10
0x140043894  mov     [rsp+0E8h+var_90], r11
0x140043899  mov     [rsp+0E8h+var_98], rsi
0x14004389e  mov     [rsp+0E8h+var_A0], r14b
0x1400438a3  mov     [rsp+0E8h+var_A8], r14b
0x1400438a8  mov     dl, [rsp+0E8h+arg_8]
0x1400438af  mov     [rsp+0E8h+var_B0], dl
0x1400438b3  mov     [rsp+0E8h+var_B8], rbx
0x1400438b8  mov     qword ptr [rsp+0E8h+Priority], rdi
0x1400438bd  lea     r12, [rsi+0F0h]
0x1400438c4  mov     qword ptr [rsp+0E8h+BugCheckOnFailure], r12
0x1400438c9  mov     r9d, [rsi+108h]
0x1400438d0  mov     rdx, [r13+30h]
0x1400438d4  call    _guard_dispatch_icall
0x1400438d9  mov     ebx, eax
0x1400438db  mov     [rsp+0E8h+var_54], eax
0x1400438e2  jmp     short loc_14004392D
0x1400438e4  mov     ebx, eax
0x1400438e6  mov     [rsp+0E8h+var_54], eax
0x1400438ed  mov     rsi, [rsp+0E8h+arg_0]
0x1400438f5  mov     r15, [rsp+0E8h+var_48]
0x1400438fd  jmp     short loc_14004392D
0x1400438ff  mov     ebx, eax
0x140043901  mov     [rsp+0E8h+var_54], eax
0x140043908  mov     eax, 0C00000E8h
0x14004390d  cmp     ebx, 0C0000005h
0x140043913  cmovz   ebx, eax
0x140043916  mov     [rsp+0E8h+var_54], ebx
0x14004391d  mov     rsi, [rsp+0E8h+arg_0]
0x140043925  mov     r15, [rsp+0E8h+var_48]
0x14004392d  test    ebx, ebx
0x14004392f  js      short loc_140043949
0x140043931  lea     rdi, [rsi+98h]
0x140043938  mov     rcx, [rdi]
0x14004393b  mov     rax, [rsp+0E8h+var_50]
0x140043943  add     [rcx+68h], rax
0x140043947  jmp     short loc_140043958
0x140043949  mov     rdi, [rsp+0E8h+var_40]
0x140043951  add     rdi, 98h
0x140043958  cmp     ebx, 103h
0x14004395e  jnz     short loc_140043970
0x140043960  mov     rax, [r15]
0x140043963  mov     rcx, [rax+0B8h]
0x14004396a  or      byte ptr [rcx+3], 1
0x14004396e  jmp     short loc_1400439B7
0x140043970  mov     rdx, rsi; struct CClfsRequest *
0x140043973  mov     rcx, [rsi+68h]; this
0x140043977  call    ?Change_State_Done@CClfsRequest_State@@QEAAXPEAVCClfsRequest@@@Z; CClfsRequest_State::Change_State_Done(CClfsRequest *)
0x14004397c  test    ebx, ebx
0x14004397e  js      short loc_1400439A1
0x140043980  mov     rdx, [rsi+110h]
0x140043987  mov     rcx, [rdi]
0x14004398a  mov     eax, [rcx+1Ch]
0x14004398d  test    al, 8
0x14004398f  jnz     short loc_140043996
0x140043991  lock or dword ptr [rcx+1Ch], 8
0x140043996  mov     rax, [rsi+0F8h]
0x14004399d  mov     [rdx+18h], rax
0x1400439a1  mov     rax, [rsi+30h]
0x1400439a5  mov     [rax+30h], ebx
0x1400439a8  mov     ecx, [rsp+0E8h+arg_10]
0x1400439af  mov     rax, [rsi+30h]
0x1400439b3  mov     [rax+38h], rcx
0x1400439b7  mov     eax, ebx
0x1400439b9  add     rsp, 0B0h
0x1400439c0  pop     r15
0x1400439c2  pop     r14
0x1400439c4  pop     r13
0x1400439c6  pop     r12
0x1400439c8  pop     rdi
0x1400439c9  pop     rsi
0x1400439ca  pop     rbx
0x1400439cb  retn
0x14007f3c1  push    rbp
0x14007f3c3  sub     rsp, 90h
0x14007f3ca  mov     rbp, rdx
0x14007f3cd  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x14007f3d0  mov     rcx, [rbp+0F0h]; struct CClfsRequest *
0x14007f3d7  call    ?ProcessException@CClfsRequest@@CAJPEAV1@PEAU_EXCEPTION_POINTERS@@@Z; CClfsRequest::ProcessException(CClfsRequest *,_EXCEPTION_POINTERS *)
0x14007f3dc  nop
0x14007f3dd  add     rsp, 90h
0x14007f3e4  pop     rbp
  ... truncated ...
```
