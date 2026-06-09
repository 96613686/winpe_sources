# MdaLocks

- ea: `0x14001e050`
- end: `0x14001e693`
- name: `MdaLocks`
- size: `1603`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140017590`
- `0x14001e050`
- `0x14001ea54`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x14001e2a8`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14001e546`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14001e2a8`
- `ntoskrnl!IoGetRequestorProcessId` at `0x14001e546`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14001e169`
- `rdbss!RxIndicateChangeOfOplockStateForTarget` at `0x14001e169`

## pseudocode

```c
__int64 __fastcall MdaLocks(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v3; // rsi
  __int64 v4; // r8
  __int64 v5; // r13
  __int64 v6; // rdi
  int v7; // eax
  __int16 v8; // di
  int v10; // ecx
  char v11; // r12
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int16 v14; // r14
  int v15; // ebx
  IRP *v16; // rcx
  ULONG RequestorProcessId; // eax
  __int64 v18; // r9
  __int64 v19; // rax
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdx
  _QWORD *v22; // rdi
  __int64 v23; // r9
  __int128 v24; // [rsp+20h] [rbp-30h] BYREF
  __int128 v25; // [rsp+30h] [rbp-20h]
  __int128 v26; // [rsp+40h] [rbp-10h]
  __int64 v27; // [rsp+90h] [rbp+40h]
  __int64 v28; // [rsp+98h] [rbp+48h]

  v1 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL);
  v4 = *(_QWORD *)(v1 + 136);
  v27 = v4;
  v5 = *(_QWORD *)(v3 + 40);
  v6 = *(_QWORD *)(v5 + 40);
  v28 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v5 + 32) + 32LL) + 32LL);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
    v4 = v27;
  }
  v7 = *(_DWORD *)(v6 + 32);
  v8 = 1;
  if ( (v7 & 1) != 0 )
  {
    v10 = *(_DWORD *)(v1 + 164);
    v11 = 0;
    if ( (v10 & 1) != 0 && (*(_DWORD *)(v1 + 160) & 0x2000000) != 0
      || (v10 & 8) != 0 && (*(_DWORD *)(v1 + 160) & 0x100000) != 0
      || (v10 & 2) != 0 && (*(_DWORD *)(v1 + 160) & 0x8000000) != 0 )
    {
      RxIndicateChangeOfOplockStateForTarget(
        *(_QWORD *)(*(_QWORD *)(v5 + 32) + 32LL),
        v3,
        0,
        0,
        v24,
        *((_QWORD *)&v24 + 1),
        v25,
        *((_QWORD *)&v25 + 1),
        v26,
        *((_QWORD *)&v26 + 1));
      v4 = v27;
      *(_DWORD *)(v27 + 28) |= 1u;
    }
    switch ( *(_WORD *)(a1 + 520) )
    {
      case 2:
      case 3:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
          v4 = v27;
        }
        v14 = 0;
        break;
      case 4:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
          v4 = v27;
        }
        v8 = 0;
        v14 = 1;
        break;
      case 5:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
          v4 = v27;
        }
        v8 = 0;
        v14 = 1;
        v11 = 1;
        break;
      default:
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          return 3221225485LL;
        v13 = 15;
LABEL_47:
        WPP_SF_(v12->AttachedDevice, v13, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
        return 3221225485LL;
    }
    v15 = 0;
    *(_QWORD *)&v24 = v5;
    *((_QWORD *)&v24 + 1) = *(_QWORD *)(v4 + 8);
    if ( v11 )
    {
      v22 = *(_QWORD **)(a1 + 536);
      LODWORD(v25) = *(_WORD *)(a1 + 520) == 3;
      DWORD1(v25) = (*(_BYTE *)(a1 + 544) & 1) == 0;
      for ( DWORD2(v25) = IoGetRequestorProcessId(*(PIRP *)(a1 + 40)); v22; v22 = (_QWORD *)*v22 )
      {
        v23 = v22[2];
        v26 = *((_OWORD *)v22 + 1);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
            v23 = v26;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids, v23);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids,
                  *((_QWORD *)&v26 + 1));
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
              {
                WPP_SF_Z(
                  WPP_GLOBAL_Control->AttachedDevice,
                  28,
                  WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids,
                  *(_QWORD *)(v27 + 8) + 64LL);
              }
            }
          }
        }
        v15 = NlmLockOrUnlock(a1, &v24, 4);
        if ( v15 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
        }
      }
      goto LABEL_75;
    }
    v16 = *(IRP **)(a1 + 40);
    *(_QWORD *)&v25 = *(_WORD *)(a1 + 520) == 3;
    RequestorProcessId = IoGetRequestorProcessId(v16);
    v18 = *(_QWORD *)(a1 + 552);
    DWORD2(v25) = RequestorProcessId;
    v19 = *(_QWORD *)(a1 + 536);
    *((_QWORD *)&v26 + 1) = v19;
    *(_QWORD *)&v26 = v18;
    if ( v8 && *(_DWORD *)(v28 + 160) == 3 )
    {
      if ( (v18 & 0xFFFFFFFF00000000uLL) != 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          return 3221225485LL;
        v13 = 16;
        goto LABEL_47;
      }
      if ( v19 != -1 && (v19 & 0xFFFFFFFF00000000uLL) != 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          return 3221225485LL;
        v13 = 17;
        goto LABEL_47;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
        v18 = v26;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids, v18);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids,
            *((_QWORD *)&v26 + 1));
        }
      }
    }
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids,
          *(_QWORD *)(v27 + 8) + 64LL);
      }
      v15 = NlmLockOrUnlock(a1, &v24, 22);
      if ( v15 >= 0 )
        goto LABEL_75;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v21 = 22;
LABEL_74:
          WPP_SF_d(v20->AttachedDevice, v21, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
          goto LABEL_75;
        }
        goto LABEL_75;
      }
    }
    else
    {
      if ( !v14 )
        goto LABEL_75;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          23,
          WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids,
          *(_QWORD *)(v27 + 8) + 64LL);
      }
      v15 = NlmLockOrUnlock(a1, &v24, 4);
      if ( v15 >= 0 )
        goto LABEL_75;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          v21 = 24;
          goto LABEL_74;
        }
LABEL_75:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
        }
      }
    }
    return (unsigned int)v15;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids);
  return 3221225659LL;
}

```

## disassembly

```asm
0x14001e050  mov     [rsp-38h+arg_10], rbx
0x14001e055  push    rbp
0x14001e056  push    rsi
0x14001e057  push    rdi
0x14001e058  push    r12
0x14001e05a  push    r13
0x14001e05c  push    r14
0x14001e05e  push    r15
0x14001e060  mov     rbp, rsp
0x14001e063  sub     rsp, 50h
0x14001e067  mov     rax, [rcx+40h]
0x14001e06b  xorps   xmm0, xmm0
0x14001e06e  mov     rbx, [rcx+38h]
0x14001e072  mov     r15, rcx
0x14001e075  mov     rsi, [rax+20h]
0x14001e079  mov     r8, [rbx+88h]
0x14001e080  mov     [rbp+arg_0], r8
0x14001e084  mov     r13, [rsi+28h]
0x14001e088  mov     rax, [r13+20h]
0x14001e08c  mov     rdi, [r13+28h]
0x14001e090  mov     rdx, [rax+20h]
0x14001e094  mov     rax, [rdx+20h]
0x14001e098  mov     [rbp+arg_8], rax
0x14001e09c  movups  [rbp+var_30], xmm0
0x14001e0a0  movups  [rbp+var_20], xmm0
0x14001e0a4  movups  [rbp+var_10], xmm0
0x14001e0a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0af  lea     r14, WPP_GLOBAL_Control
0x14001e0b6  cmp     rcx, r14
0x14001e0b9  jz      short loc_14001E0DD
0x14001e0bb  test    dword ptr [rcx+2Ch], 40000h
0x14001e0c2  jz      short loc_14001E0DD
0x14001e0c4  mov     rcx, [rcx+18h]
0x14001e0c8  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e0cf  mov     edx, 0Ah
0x14001e0d4  call    WPP_SF_
0x14001e0d9  mov     r8, [rbp+arg_0]
0x14001e0dd  mov     eax, [rdi+20h]
0x14001e0e0  mov     edi, 1
0x14001e0e5  test    dil, al
0x14001e0e8  jnz     short loc_14001E11C
0x14001e0ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0f1  cmp     rcx, r14
0x14001e0f4  jz      short loc_14001E112
0x14001e0f6  test    dword ptr [rcx+2Ch], 40000h
0x14001e0fd  jz      short loc_14001E112
0x14001e0ff  mov     rcx, [rcx+18h]
0x14001e103  lea     edx, [rdi+0Ah]
0x14001e106  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e10d  call    WPP_SF_
0x14001e112  mov     eax, 0C00000BBh
0x14001e117  jmp     loc_14001E4FD
0x14001e11c  mov     ecx, [rbx+0A4h]
0x14001e122  xor     r12b, r12b
0x14001e125  test    dil, cl
0x14001e128  jz      short loc_14001E136
0x14001e12a  test    dword ptr [rbx+0A0h], 2000000h
0x14001e134  jnz     short loc_14001E158
0x14001e136  test    cl, 8
0x14001e139  jz      short loc_14001E147
0x14001e13b  test    dword ptr [rbx+0A0h], 100000h
0x14001e145  jnz     short loc_14001E158
0x14001e147  test    cl, 2
0x14001e14a  jz      short loc_14001E17D
0x14001e14c  test    dword ptr [rbx+0A0h], 8000000h
0x14001e156  jz      short loc_14001E17D
0x14001e158  mov     rcx, [r13+20h]
0x14001e15c  xor     r9d, r9d
0x14001e15f  xor     r8d, r8d
0x14001e162  mov     rdx, rsi
0x14001e165  mov     rcx, [rcx+20h]
0x14001e169  call    cs:__imp_RxIndicateChangeOfOplockStateForTarget
0x14001e170  nop     dword ptr [rax+rax+00h]
0x14001e175  mov     r8, [rbp+arg_0]
0x14001e179  or      [r8+1Ch], edi
0x14001e17d  movzx   ecx, word ptr [r15+208h]
0x14001e185  sub     ecx, 2
0x14001e188  jz      loc_14001E23B
0x14001e18e  sub     ecx, edi
0x14001e190  jz      loc_14001E23B
0x14001e196  sub     ecx, edi
0x14001e198  jz      short loc_14001E200
0x14001e19a  cmp     ecx, edi
0x14001e19c  jz      short loc_14001E1C4
0x14001e19e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1a5  cmp     rcx, r14
0x14001e1a8  jz      loc_14001E349
0x14001e1ae  mov     eax, [rcx+2Ch]
0x14001e1b1  test    dil, al
0x14001e1b4  jz      loc_14001E349
0x14001e1ba  mov     edx, 0Fh
0x14001e1bf  jmp     loc_14001E339
0x14001e1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1cb  cmp     rcx, r14
0x14001e1ce  jz      short loc_14001E1F2
0x14001e1d0  test    dword ptr [rcx+2Ch], 40000h
0x14001e1d7  jz      short loc_14001E1F2
0x14001e1d9  mov     rcx, [rcx+18h]
0x14001e1dd  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e1e4  mov     edx, 0Eh
0x14001e1e9  call    WPP_SF_
0x14001e1ee  mov     r8, [rbp+arg_0]
0x14001e1f2  xor     edi, edi
0x14001e1f4  lea     edx, [rdi+1]
0x14001e1f7  movzx   r14d, dx
0x14001e1fb  mov     r12b, dl
0x14001e1fe  jmp     short loc_14001E272
0x14001e200  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e207  cmp     rcx, r14
0x14001e20a  jz      short loc_14001E22E
0x14001e20c  test    dword ptr [rcx+2Ch], 40000h
0x14001e213  jz      short loc_14001E22E
0x14001e215  mov     rcx, [rcx+18h]
0x14001e219  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e220  mov     edx, 0Dh
0x14001e225  call    WPP_SF_
0x14001e22a  mov     r8, [rbp+arg_0]
0x14001e22e  xor     eax, eax
0x14001e230  movzx   edi, ax
0x14001e233  lea     edx, [rax+1]
0x14001e236  mov     r14d, edx
0x14001e239  jmp     short loc_14001E272
0x14001e23b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e242  cmp     rcx, r14
0x14001e245  jz      short loc_14001E269
0x14001e247  test    dword ptr [rcx+2Ch], 40000h
0x14001e24e  jz      short loc_14001E269
0x14001e250  mov     rcx, [rcx+18h]
0x14001e254  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e25b  mov     edx, 0Ch
0x14001e260  call    WPP_SF_
0x14001e265  mov     r8, [rbp+arg_0]
0x14001e269  xor     eax, eax
0x14001e26b  movzx   r14d, ax
0x14001e26f  lea     edx, [rax+1]
0x14001e272  xor     ebx, ebx
0x14001e274  mov     qword ptr [rbp+var_30], r13
0x14001e278  mov     rax, [r8+8]
0x14001e27c  mov     qword ptr [rbp+var_30+8], rax
0x14001e280  lea     esi, [rbx+3]
0x14001e283  test    r12b, r12b
0x14001e286  jnz     loc_14001E516
0x14001e28c  mov     rcx, [r15+28h]; Irp
0x14001e290  xor     r13d, r13d
0x14001e293  cmp     [r15+208h], si
0x14001e29b  mov     eax, r13d
0x14001e29e  mov     dword ptr [rbp+var_20+4], r13d
0x14001e2a2  setz    al
0x14001e2a5  mov     dword ptr [rbp+var_20], eax
0x14001e2a8  call    cs:__imp_IoGetRequestorProcessId
0x14001e2af  nop     dword ptr [rax+rax+00h]
0x14001e2b4  mov     r9, [r15+228h]
0x14001e2bb  mov     r8d, eax
0x14001e2be  mov     dword ptr [rbp+var_20+8], eax
0x14001e2c1  mov     rax, [r15+218h]
0x14001e2c8  mov     qword ptr [rbp+var_10+8], rax
0x14001e2cc  mov     qword ptr [rbp+var_10], r9
0x14001e2d0  test    di, di
0x14001e2d3  jz      short loc_14001E353
0x14001e2d5  mov     rcx, [rbp+arg_8]
0x14001e2d9  cmp     [rcx+0A0h], esi
0x14001e2df  jnz     short loc_14001E353
0x14001e2e1  mov     rcx, 0FFFFFFFF00000000h
0x14001e2eb  test    rcx, r9
0x14001e2ee  jz      short loc_14001E30F
0x14001e2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e2f7  lea     rax, WPP_GLOBAL_Control
0x14001e2fe  cmp     rcx, rax
0x14001e301  jz      short loc_14001E349
0x14001e303  mov     eax, [rcx+2Ch]
0x14001e306  test    al, 1
0x14001e308  jz      short loc_14001E349
0x14001e30a  lea     edx, [rbx+10h]
0x14001e30d  jmp     short loc_14001E339
0x14001e30f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001e313  jz      short loc_14001E353
0x14001e315  test    rcx, rax
0x14001e318  jz      short loc_14001E353
0x14001e31a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e321  lea     rax, WPP_GLOBAL_Control
0x14001e328  cmp     rcx, rax
0x14001e32b  jz      short loc_14001E349
0x14001e32d  mov     eax, [rcx+2Ch]
0x14001e330  test    al, 1
0x14001e332  jz      short loc_14001E349
0x14001e334  mov     edx, 11h
0x14001e339  mov     rcx, [rcx+18h]
0x14001e33d  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e344  call    WPP_SF_
0x14001e349  mov     eax, 0C000000Dh
0x14001e34e  jmp     loc_14001E4FD
0x14001e353  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e35a  lea     r12, WPP_GLOBAL_Control
0x14001e361  mov     esi, 40000h
0x14001e366  cmp     rcx, r12
0x14001e369  jz      short loc_14001E3DC
0x14001e36b  test    [rcx+2Ch], esi
0x14001e36e  jz      short loc_14001E38C
0x14001e370  mov     rcx, [rcx+18h]
0x14001e374  mov     r9d, r8d
0x14001e377  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e37e  mov     edx, 12h
0x14001e383  call    WPP_SF_d
0x14001e388  mov     r9, qword ptr [rbp+var_10]
0x14001e38c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e393  cmp     rcx, r12
0x14001e396  jz      short loc_14001E3DC
0x14001e398  test    [rcx+2Ch], esi
0x14001e39b  jz      short loc_14001E3B2
0x14001e39d  mov     rcx, [rcx+18h]
0x14001e3a1  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e3a8  mov     edx, 13h
0x14001e3ad  call    WPP_SF_q
0x14001e3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3b9  cmp     rcx, r12
0x14001e3bc  jz      short loc_14001E3DC
0x14001e3be  test    [rcx+2Ch], esi
0x14001e3c1  jz      short loc_14001E3DC
0x14001e3c3  mov     r9, qword ptr [rbp+var_10+8]
0x14001e3c7  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e3ce  mov     rcx, [rcx+18h]
0x14001e3d2  mov     edx, 14h
0x14001e3d7  call    WPP_SF_q
0x14001e3dc  test    di, di
0x14001e3df  jz      short loc_14001E456
0x14001e3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3e8  cmp     rcx, r12
0x14001e3eb  jz      short loc_14001E413
0x14001e3ed  test    [rcx+2Ch], esi
0x14001e3f0  jz      short loc_14001E413
0x14001e3f2  mov     rsi, [rbp+arg_0]
0x14001e3f6  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e3fd  mov     rcx, [rcx+18h]
0x14001e401  mov     edx, 15h
0x14001e406  mov     r9, [rsi+8]
0x14001e40a  add     r9, 40h ; '@'
0x14001e40e  call    WPP_SF_Z
0x14001e413  mov     edi, 16h
0x14001e418  lea     rdx, [rbp+var_30]
0x14001e41c  mov     r8d, edi
0x14001e41f  mov     rcx, r15
0x14001e422  call    NlmLockOrUnlock
0x14001e427  mov     ebx, eax
0x14001e429  test    eax, eax
0x14001e42b  jns     loc_14001E4D1
0x14001e431  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e438  cmp     rcx, r12
0x14001e43b  jz      loc_14001E4FB
0x14001e441  mov     r8d, [rcx+2Ch]
0x14001e445  test    r8b, 1
0x14001e449  jz      loc_14001E4D1
0x14001e44f  mov     edx, edi
0x14001e451  mov     r9d, eax
0x14001e454  jmp     short loc_14001E4C1
0x14001e456  test    r14w, r14w
0x14001e45a  jz      short loc_14001E4D1
0x14001e45c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e463  cmp     rcx, r12
0x14001e466  jz      short loc_14001E48E
0x14001e468  test    [rcx+2Ch], esi
0x14001e46b  jz      short loc_14001E48E
0x14001e46d  mov     rsi, [rbp+arg_0]
0x14001e471  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e478  mov     rcx, [rcx+18h]
0x14001e47c  mov     edx, 17h
0x14001e481  mov     r9, [rsi+8]
0x14001e485  add     r9, 40h ; '@'
0x14001e489  call    WPP_SF_Z
0x14001e48e  mov     r8d, 4
0x14001e494  lea     rdx, [rbp+var_30]
0x14001e498  mov     rcx, r15
0x14001e49b  call    NlmLockOrUnlock
0x14001e4a0  mov     ebx, eax
0x14001e4a2  test    eax, eax
0x14001e4a4  jns     short loc_14001E4D1
0x14001e4a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4ad  cmp     rcx, r12
0x14001e4b0  jz      short loc_14001E4FB
0x14001e4b2  mov     eax, [rcx+2Ch]
0x14001e4b5  test    al, 1
0x14001e4b7  jz      short loc_14001E4D1
0x14001e4b9  mov     edx, 18h
0x14001e4be  mov     r9d, ebx
0x14001e4c1  mov     rcx, [rcx+18h]
0x14001e4c5  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e4cc  call    WPP_SF_d
0x14001e4d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4d8  cmp     rcx, r12
0x14001e4db  jz      short loc_14001E4FB
0x14001e4dd  test    dword ptr [rcx+2Ch], 40000h
0x14001e4e4  jz      short loc_14001E4FB
0x14001e4e6  mov     rcx, [rcx+18h]
0x14001e4ea  lea     r8, WPP_b0a0c257da1b3740516819ddf69830b5_Traceguids
0x14001e4f1  mov     edx, 1Eh
0x14001e4f6  call    WPP_SF_
0x14001e4fb  mov     eax, ebx
0x14001e4fd  mov     rbx, [rsp+50h+arg_10]
0x14001e505  add     rsp, 50h
0x14001e509  pop     r15
0x14001e50b  pop     r14
  ... truncated ...
```
