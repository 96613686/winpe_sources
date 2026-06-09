# MSnodeCompletion

- ea: `0x140009ee0`
- end: `0x14000a79c`
- name: `MSnodeCompletion`
- size: `2236`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x140007c4c`
- `0x140007ed8`
- `0x140007ff8`
- `0x140008110`
- `0x1400089c8`
- `0x140009e1c`
- `0x140009ee0`
- `0x14000a7b0`
- `0x14000b7e8`
- `0x14000b810`
- `0x14000c28c`
- `0x140025144`
- `0x1400400dc`
- `0x140040294`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009f43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a01e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009f43`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a01e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009fbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a053`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a503`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009fbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a053`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a3a9`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a503`

## pseudocode

```c
void __fastcall MSnodeCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v3; // si
  unsigned __int8 v6; // r8
  KIRQL v7; // r15
  __int16 v8; // ax
  __int64 v9; // rbp
  KIRQL v11; // si
  KIRQL v12; // dl
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rbp
  PVOID *v21; // r14
  _QWORD *v22; // rax
  __int64 v23; // r11
  int v24; // r8d
  int v25; // r10d
  int v26; // esi
  __int16 v27; // r9
  __int16 v28; // cx
  volatile signed __int32 *v29; // rbp
  __int64 v30; // rbx
  _QWORD *v31; // rax
  __int64 v32; // rcx
  _QWORD *v33; // rdx
  __int64 v34; // r12
  _QWORD *v35; // rax
  volatile signed __int32 *v36; // r13
  __int16 v37; // ax
  int v38; // ecx
  __int16 v39; // r10
  __int16 v40; // ax
  bool v41; // cc
  volatile signed __int32 *v42; // rbp
  int v43; // [rsp+B0h] [rbp+18h] BYREF

  v3 = NodeType;
  v43 = 0;
  if ( (NodeType & 1) != 0 && (unsigned int)IsBrowserName(*(_QWORD *)(a1 + 48) + 164LL) )
    v3 = v6;
  if ( a3 )
  {
    v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    if ( !*(_QWORD *)(a3 + 72) )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
      _InterlockedDecrement(&dword_1400394B0);
      v29 = *(volatile signed __int32 **)(a1 + 48);
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *((_DWORD *)v29 + 5),
          81,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          (_DWORD)v29,
          *((_DWORD *)v29 + 5),
          *((_DWORD *)v29 + 5) - 1,
          8,
          (__int64)"minio\\netbt\\sys\\namesrv.c");
      if ( _InterlockedExchangeAdd(v29 + 5, 0xFFFFFFFF) == 1 )
      {
        NbtUnlinkNameFromHashTable(v29);
        NbtFreeNameAddr((PVOID)v29);
      }
      else
      {
        NbtCheckNameAddrTimer(v29);
      }
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *(_DWORD *)(a1 + 20),
          84,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          a1,
          *(_DWORD *)(a1 + 20),
          *(_DWORD *)(a1 + 20) - 1,
          9,
          (__int64)"minio\\netbt\\sys\\namesrv.c");
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
      {
        FreeTracker(a1, 4);
        v12 = v7;
        goto LABEL_16;
      }
LABEL_35:
      v12 = v7;
LABEL_16:
      KeReleaseSpinLock(&SpinLock, v12);
      return;
    }
    v8 = *(_WORD *)(a3 + 256);
    if ( (v8 & 0x10) != 0 )
    {
      *(_WORD *)(a3 + 256) = v8 & 0xFFEE | 1;
      if ( !*(_DWORD *)(*(_QWORD *)(a1 + 32) + 488LL) )
      {
        *(_DWORD *)(a3 + 24) = 10;
        v12 = v7;
        goto LABEL_16;
      }
      goto LABEL_35;
    }
    v9 = *(_QWORD *)(a3 + 64);
    if ( (*(_DWORD *)(v9 + 240) & 0x40) == 0 )
    {
      if ( (*(_WORD *)(a3 + 20))-- != 1 )
      {
LABEL_9:
        if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
          WPP_SF_qddds(
            *(_DWORD *)(a1 + 20),
            15,
            (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
            a1,
            *(_DWORD *)(a1 + 20),
            *(_DWORD *)(a1 + 20) + 1,
            72,
            (__int64)"minio\\netbt\\sys\\namesrv.c");
        _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
        *(_WORD *)(a3 + 256) |= 1u;
        KeReleaseSpinLock(&SpinLock, v7);
        SendNameServiceRequest(*(_QWORD *)(a1 + 48), Str2, a1, 0, 0, 0, 0, 0, 0, 1, &v43);
        if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
          WPP_SF_qddds(
            *(_DWORD *)(a1 + 20),
            84,
            (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
            a1,
            *(_DWORD *)(a1 + 20),
            *(_DWORD *)(a1 + 20) - 1,
            90,
            (__int64)"minio\\netbt\\sys\\namesrv.c");
        v11 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
          FreeTracker(a1, 4);
        v12 = v11;
        goto LABEL_16;
      }
      *(_WORD *)(a3 + 20) = word_1400395D8;
      v13 = *(_DWORD *)(a1 + 240);
      v14 = v13 & 0xFFFFFFF0;
      *(_DWORD *)(a1 + 240) = v13 & 0xFFFFFFF0;
      if ( (v13 & 1) != 0 && (v3 & 4) != 0 )
      {
        v15 = *(_QWORD *)(a1 + 32);
        if ( *(_DWORD *)(v15 + 504) != 2130706432 && !*(_BYTE *)(v15 + 858) )
        {
          *(_DWORD *)(a1 + 240) = v14 | 2;
          *(_DWORD *)(a3 + 24) = dword_1400395C0;
          goto LABEL_9;
        }
      }
      if ( (v13 & 2) != 0 && (v3 & 1) == 0 )
      {
        v16 = *(_QWORD *)(a1 + 32);
        *(_DWORD *)(a1 + 240) = v14 | 4;
        if ( *(_DWORD *)(v16 + 508) != 2130706432 && !*(_BYTE *)(v16 + 858) )
          goto LABEL_9;
LABEL_44:
        *(_WORD *)(a3 + 20) = 1;
        *(_DWORD *)(a3 + 24) = 10;
        goto LABEL_9;
      }
      if ( (v13 & 4) != 0 && (v3 & 1) == 0 )
      {
        v23 = *(_QWORD *)(a1 + 32);
        v24 = v14 | 8;
        v25 = *(unsigned __int16 *)(a1 + 204);
        v26 = *(unsigned __int16 *)(v23 + 552);
        *(_DWORD *)(a1 + 240) = v24;
        if ( (v13 & 8) != 0 )
        {
          --*(_WORD *)(a1 + 206);
          if ( v25 < v26 - 1 )
            LOWORD(v25) = v25 + 1;
          else
            LOWORD(v25) = 0;
        }
        v27 = *(_WORD *)(a1 + 206);
        if ( v27 )
        {
          v37 = *(_WORD *)(a1 + 206);
          do
          {
            v28 = v37;
            if ( *(_DWORD *)(v23 + 4LL * (unsigned __int16)v25 + 512) != 2130706432 )
              break;
            --v27;
            v38 = (unsigned __int16)v25;
            v39 = v25 + 1;
            *(_WORD *)(a1 + 206) = v27;
            v40 = 0;
            v41 = v38 < v26 - 1;
            v28 = v27;
            if ( v41 )
              v40 = v39;
            LOWORD(v25) = v40;
            v37 = v27;
          }
          while ( v27 );
        }
        else
        {
          v28 = 0;
        }
        *(_WORD *)(a1 + 204) = v25;
        if ( v28 )
        {
          *(_DWORD *)(a1 + 240) = v24 | 4;
          goto LABEL_9;
        }
        goto LABEL_44;
      }
      if ( (v3 & (unsigned __int8)v13 & 8) != 0 )
      {
        *(_DWORD *)(a1 + 240) = v14 | 1;
        *(_DWORD *)(a3 + 24) = dword_1400395BC;
        *(_WORD *)(a3 + 20) = word_1400395DA;
        if ( (v13 & 0x200) == 0 )
          SetWinsDownFlag(*(_QWORD *)(a1 + 32));
        goto LABEL_9;
      }
      v17 = *(_QWORD **)(a1 + 48);
      *(_DWORD *)(a1 + 184) = 255;
      v18 = *v17;
      if ( *(_QWORD **)(*v17 + 8LL) == v17 )
      {
        v19 = (_QWORD *)v17[1];
        if ( (_QWORD *)*v19 == v17 )
        {
          v20 = *(_QWORD *)(a3 + 72);
          v21 = (PVOID *)(a1 + 48);
          *v19 = v18;
          *(_QWORD *)(v18 + 8) = v19;
          v22 = *(_QWORD **)(a1 + 48);
          v22[1] = v22;
          *v22 = v22;
          *(_QWORD *)(*(_QWORD *)(a3 + 80) + 112LL) = 0;
          *(_QWORD *)(a3 + 72) = 0;
          if ( byte_140039679 )
          {
            v21 = (PVOID *)(a1 + 48);
          }
          else if ( !byte_140039673 || (*(_DWORD *)(a1 + 240) & 0x10000) != 0 )
          {
            goto LABEL_55;
          }
          if ( !*((_BYTE *)*v21 + 132)
            && v20
            && (int)LmHostQueueRequest(a1, *(_QWORD *)(a3 + 64), v20, *(_QWORD *)(a1 + 32)) >= 0 )
          {
            goto LABEL_35;
          }
LABEL_55:
          *((_DWORD *)*v21 + 18) &= 0xFFFFFF0F;
          *((_DWORD *)*v21 + 18) |= 0x20u;
          NbtCheckNameAddrTimer(*v21);
          *((_QWORD *)*v21 + 14) = 0;
          _InterlockedDecrement(&dword_1400394B0);
          NbtDereferenceName(*v21, (__int64)"minio\\netbt\\sys\\namesrv.c");
          *v21 = 0;
          v30 = *(_QWORD *)(a3 + 64);
          KeReleaseSpinLock(&SpinLock, v7);
          CompleteClientReq(v20, v30, 258);
          NbtDereferenceTracker(a1, 0, 1089, "minio\\netbt\\sys\\namesrv.c");
          return;
        }
      }
LABEL_79:
      __fastfail(3u);
    }
    if ( (BYTE3(xmmword_140038420) & 2) != 0 )
      WPP_SF_(1049, 14, WPP_bce120156c883c01baa58c4fefcf98ff_Traceguids);
    v31 = *(_QWORD **)(a1 + 48);
    v32 = *v31;
    if ( *(_QWORD **)(*v31 + 8LL) != v31 )
      goto LABEL_79;
    v33 = (_QWORD *)v31[1];
    if ( (_QWORD *)*v33 != v31 )
      goto LABEL_79;
    v34 = *(_QWORD *)(a3 + 72);
    *v33 = v32;
    *(_QWORD *)(v32 + 8) = v33;
    v35 = *(_QWORD **)(a1 + 48);
    v35[1] = v35;
    *v35 = v35;
    *(_QWORD *)(*(_QWORD *)(a3 + 80) + 112LL) = 0;
    *(_QWORD *)(a3 + 72) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 72LL) &= 0xFFFFFF0F;
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 72LL) |= 0x20u;
    NbtCheckNameAddrTimer(*(_QWORD *)(a1 + 48));
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
    _InterlockedDecrement(&dword_1400394B0);
    v36 = *(volatile signed __int32 **)(a1 + 48);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v36 + 5),
        81,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        (_DWORD)v36,
        *((_DWORD *)v36 + 5),
        *((_DWORD *)v36 + 5) - 1,
        73,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd(v36 + 5, 0xFFFFFFFF) == 1 )
    {
      NbtUnlinkNameFromHashTable(v36);
      NbtFreeNameAddr((PVOID)v36);
    }
    else
    {
      NbtCheckNameAddrTimer(v36);
    }
    *(_QWORD *)(a1 + 48) = 0;
    KeReleaseSpinLock(&SpinLock, v7);
    if ( (BYTE11(xmmword_140038420) & 2) != 0 )
      WPP_SF_qzD(
        1305,
        15,
        (unsigned int)WPP_bce120156c883c01baa58c4fefcf98ff_Traceguids,
        v9,
        *(_QWORD *)(v9 + 40),
        *(_BYTE *)(*(_QWORD *)(v9 + 40) + 15LL));
    CompleteClientReq(v34, v9, 3221225760LL);
    NbtDereferenceTracker(a1, 0, 865, "minio\\netbt\\sys\\namesrv.c");
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(a1 + 48) + 112LL) = 0;
    _InterlockedDecrement(&dword_1400394B0);
    v42 = *(volatile signed __int32 **)(a1 + 48);
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *((_DWORD *)v42 + 5),
        81,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        (_DWORD)v42,
        *((_DWORD *)v42 + 5),
        *((_DWORD *)v42 + 5) - 1,
        242,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd(v42 + 5, 0xFFFFFFFF) == 1 )
    {
      NbtUnlinkNameFromHashTable(v42);
      NbtFreeNameAddr((PVOID)v42);
    }
    else
    {
      NbtCheckNameAddrTimer(v42);
    }
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(a1 + 20),
        84,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        a1,
        *(_DWORD *)(a1 + 20),
        *(_DWORD *)(a1 + 20) - 1,
        243,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
      FreeTracker(a1, 4);
  }
}

```

## disassembly

```asm
0x140009ee0  push    rbx
0x140009ee2  push    rsi
0x140009ee3  push    rdi
0x140009ee4  push    r13
0x140009ee6  sub     rsp, 78h
0x140009eea  movzx   esi, cs:NodeType
0x140009ef1  mov     rbx, r8
0x140009ef4  xor     r13d, r13d
0x140009ef7  mov     r8d, esi
0x140009efa  mov     [rsp+98h+arg_10], r13d
0x140009f02  mov     rdi, rcx
0x140009f05  and     r8d, 1
0x140009f09  jz      short loc_140009F21
0x140009f0b  mov     rcx, [rcx+30h]
0x140009f0f  add     rcx, 0A4h
0x140009f16  call    IsBrowserName
0x140009f1b  test    eax, eax
0x140009f1d  cmovnz  esi, r8d
0x140009f21  mov     [rsp+98h+arg_8], rbp
0x140009f29  mov     [rsp+98h+var_30], r14
0x140009f2e  test    rbx, rbx
0x140009f31  jz      loc_14000A5EB
0x140009f37  lea     rcx, SpinLock; SpinLock
0x140009f3e  mov     [rsp+98h+var_38], r15
0x140009f43  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009f4a  nop     dword ptr [rax+rax+00h]
0x140009f4f  movzx   r15d, al
0x140009f53  cmp     [rbx+48h], r13
0x140009f57  jz      loc_14000A2B8
0x140009f5d  movzx   eax, word ptr [rbx+100h]
0x140009f64  test    al, 10h
0x140009f66  jnz     loc_14000A3EE
0x140009f6c  mov     rbp, [rbx+40h]
0x140009f70  mov     eax, [rbp+0F0h]
0x140009f76  test    al, 40h
0x140009f78  jnz     loc_14000A422
0x140009f7e  mov     r9d, 0FFFFh
0x140009f84  mov     ebp, 1
0x140009f89  add     [rbx+14h], r9w
0x140009f8e  jz      loc_14000A07C
0x140009f94  test    byte ptr cs:xmmword_140038420+9, 40h
0x140009f9b  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x140009fa2  jnz     loc_14000A1DB
0x140009fa8  lock inc dword ptr [rdi+14h]
0x140009fac  or      [rbx+100h], bp
0x140009fb3  lea     rcx, SpinLock; SpinLock
0x140009fba  movzx   edx, r15b; NewIrql
0x140009fbe  call    cs:__imp_KeReleaseSpinLock
0x140009fc5  nop     dword ptr [rax+rax+00h]
0x140009fca  mov     rdx, cs:Str2
0x140009fd1  lea     rax, [rsp+98h+arg_10]
0x140009fd9  mov     rcx, [rdi+30h]
0x140009fdd  xor     r9d, r9d
0x140009fe0  mov     [rsp+98h+var_48], rax
0x140009fe5  mov     r8, rdi
0x140009fe8  mov     [rsp+98h+var_50], ebp
0x140009fec  mov     [rsp+98h+var_58], r13d
0x140009ff1  mov     dword ptr [rsp+98h+var_60], r13d
0x140009ff6  mov     [rsp+98h+var_68], r13d
0x140009ffb  mov     [rsp+98h+var_70], r13
0x14000a000  mov     [rsp+98h+var_78], r13
0x14000a005  call    SendNameServiceRequest
0x14000a00a  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000a011  jnz     loc_14000A663
0x14000a017  lea     rcx, SpinLock; SpinLock
0x14000a01e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a025  nop     dword ptr [rax+rax+00h]
0x14000a02a  movzx   esi, al
0x14000a02d  mov     ebx, 0FFFFFFFFh
0x14000a032  lock xadd [rdi+14h], ebx
0x14000a037  cmp     ebx, ebp
0x14000a039  jnz     short loc_14000A048
0x14000a03b  mov     edx, 4
0x14000a040  mov     rcx, rdi
0x14000a043  call    FreeTracker
0x14000a048  movzx   edx, sil; NewIrql
0x14000a04c  lea     rcx, SpinLock; SpinLock
0x14000a053  call    cs:__imp_KeReleaseSpinLock
0x14000a05a  nop     dword ptr [rax+rax+00h]
0x14000a05f  mov     r15, [rsp+98h+var_38]
0x14000a064  mov     r14, [rsp+98h+var_30]
0x14000a069  mov     rbp, [rsp+98h+arg_8]
0x14000a071  add     rsp, 78h
0x14000a075  pop     r13
0x14000a077  pop     rdi
0x14000a078  pop     rsi
0x14000a079  pop     rbx
0x14000a07a  retn
0x14000a07c  movzx   eax, cs:word_1400395D8
0x14000a083  mov     [rbx+14h], ax
0x14000a087  mov     edx, [rdi+0F0h]
0x14000a08d  mov     r8d, edx
0x14000a090  and     r8d, 0FFFFFFF0h
0x14000a094  test    bpl, dl
0x14000a097  mov     [rdi+0F0h], r8d
0x14000a09e  setnz   cl
0x14000a0a1  test    sil, 4
0x14000a0a5  setnz   al
0x14000a0a8  test    al, cl
0x14000a0aa  jz      short loc_14000A0DE
0x14000a0ac  mov     rax, [rdi+20h]
0x14000a0b0  cmp     dword ptr [rax+1F8h], 7F000000h
0x14000a0ba  jz      short loc_14000A0DE
0x14000a0bc  cmp     [rax+35Ah], r13b
0x14000a0c3  jnz     short loc_14000A0DE
0x14000a0c5  or      r8d, 2
0x14000a0c9  mov     [rdi+0F0h], r8d
0x14000a0d0  mov     eax, cs:dword_1400395C0
0x14000a0d6  mov     [rbx+18h], eax
0x14000a0d9  jmp     loc_140009F94
0x14000a0de  test    dl, 2
0x14000a0e1  setnz   cl
0x14000a0e4  test    bpl, sil
0x14000a0e7  setz    al
0x14000a0ea  test    al, cl
0x14000a0ec  jz      short loc_14000A11F
0x14000a0ee  mov     rax, [rdi+20h]
0x14000a0f2  or      r8d, 4
0x14000a0f6  mov     [rdi+0F0h], r8d
0x14000a0fd  cmp     dword ptr [rax+1FCh], 7F000000h
0x14000a107  jz      loc_14000A2A8
0x14000a10d  cmp     [rax+35Ah], r13b
0x14000a114  jz      loc_140009F94
0x14000a11a  jmp     loc_14000A2A8
0x14000a11f  test    dl, 4
0x14000a122  setnz   cl
0x14000a125  test    bpl, sil
0x14000a128  setz    al
0x14000a12b  test    al, cl
0x14000a12d  jnz     loc_14000A245
0x14000a133  mov     eax, edx
0x14000a135  and     eax, esi
0x14000a137  test    al, 8
0x14000a139  jnz     loc_14000A20F
0x14000a13f  mov     rax, [rdi+30h]
0x14000a143  mov     dword ptr [rdi+0B8h], 0FFh
0x14000a14d  mov     rdx, [rax]
0x14000a150  cmp     [rdx+8], rax
0x14000a154  jnz     loc_14000A5E4
0x14000a15a  mov     r8, [rax+8]
0x14000a15e  cmp     [r8], rax
0x14000a161  jnz     loc_14000A5E4
0x14000a167  mov     rbp, [rbx+48h]
0x14000a16b  lea     r14, [rdi+30h]
0x14000a16f  mov     [r8], rdx
0x14000a172  mov     [rdx+8], r8
0x14000a176  mov     rax, [rdi+30h]
0x14000a17a  mov     [rax+8], rax
0x14000a17e  mov     [rax], rax
0x14000a181  mov     rax, [rbx+50h]
0x14000a185  mov     [rax+70h], r13
0x14000a189  mov     [rbx+48h], r13
0x14000a18d  cmp     cs:byte_140039679, r13b
0x14000a194  jz      loc_14000A335
0x14000a19a  lea     r14, [rdi+30h]
0x14000a19e  mov     rax, [r14]
0x14000a1a1  cmp     [rax+84h], r13b
0x14000a1a8  jnz     loc_14000A34E
0x14000a1ae  test    rbp, rbp
0x14000a1b1  jz      loc_14000A34E
0x14000a1b7  mov     r9, [rdi+20h]
0x14000a1bb  mov     r8, rbp
0x14000a1be  mov     rdx, [rbx+40h]
0x14000a1c2  mov     rcx, rdi
0x14000a1c5  call    LmHostQueueRequest
0x14000a1ca  test    eax, eax
0x14000a1cc  js      loc_14000A34E
0x14000a1d2  movzx   edx, r15b
0x14000a1d6  jmp     loc_14000A04C
0x14000a1db  mov     ecx, [rdi+14h]
0x14000a1de  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x14000a1e5  mov     [rsp+98h+var_60], rsi
0x14000a1ea  mov     edx, 0Fh
0x14000a1ef  mov     [rsp+98h+var_68], 448h
0x14000a1f7  mov     r9, rdi
0x14000a1fa  lea     eax, [rcx+1]
0x14000a1fd  mov     dword ptr [rsp+98h+var_70], eax
0x14000a201  mov     dword ptr [rsp+98h+var_78], ecx
0x14000a205  call    WPP_SF_qddds
0x14000a20a  jmp     loc_140009FA8
0x14000a20f  or      r8d, ebp
0x14000a212  mov     [rdi+0F0h], r8d
0x14000a219  mov     eax, cs:dword_1400395BC
0x14000a21f  mov     [rbx+18h], eax
0x14000a222  movzx   eax, cs:word_1400395DA
0x14000a229  mov     [rbx+14h], ax
0x14000a22d  bt      edx, 9
0x14000a231  jb      loc_140009F94
0x14000a237  mov     rcx, [rdi+20h]
0x14000a23b  call    SetWinsDownFlag
0x14000a240  jmp     loc_140009F94
0x14000a245  mov     r11, [rdi+20h]
0x14000a249  or      r8d, 8
0x14000a24d  movzx   r10d, word ptr [rdi+0CCh]
0x14000a255  movzx   esi, word ptr [r11+228h]
0x14000a25d  mov     [rdi+0F0h], r8d
0x14000a264  test    dl, 8
0x14000a267  jz      short loc_14000A280
0x14000a269  add     [rdi+0CEh], r9w
0x14000a271  lea     ecx, [rsi-1]
0x14000a274  cmp     r10d, ecx
0x14000a277  jl      loc_14000A571
0x14000a27d  mov     r10d, r13d
0x14000a280  movzx   r9d, word ptr [rdi+0CEh]
0x14000a288  test    r9w, r9w
0x14000a28c  jnz     loc_14000A57A
0x14000a292  movzx   ecx, r9w
0x14000a296  mov     [rdi+0CCh], r10w
0x14000a29e  cmp     r13w, cx
0x14000a2a2  jnz     loc_14000A3DE
0x14000a2a8  mov     [rbx+14h], bp
0x14000a2ac  mov     dword ptr [rbx+18h], 0Ah
0x14000a2b3  jmp     loc_140009F94
0x14000a2b8  mov     rcx, [rdi+30h]
0x14000a2bc  mov     [rcx+70h], r13
0x14000a2c0  lock dec cs:dword_1400394B0
0x14000a2c7  mov     rbp, [rdi+30h]
0x14000a2cb  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000a2d2  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000a2d9  jnz     loc_14000A733
0x14000a2df  mov     ebx, 0FFFFFFFFh
0x14000a2e4  mov     eax, ebx
0x14000a2e6  lock xadd [rbp+14h], eax
0x14000a2eb  mov     rcx, rbp
0x14000a2ee  cmp     eax, 1
0x14000a2f1  jnz     loc_14000A5D0
0x14000a2f7  call    NbtUnlinkNameFromHashTable
0x14000a2fc  mov     rcx, rbp; P
0x14000a2ff  call    NbtFreeNameAddr
0x14000a304  test    byte ptr cs:xmmword_140038420+9, 40h
0x14000a30b  jnz     loc_14000A6CB
0x14000a311  lock xadd [rdi+14h], ebx
0x14000a316  cmp     ebx, 1
0x14000a319  jnz     loc_14000A1D2
0x14000a31f  mov     edx, 4
0x14000a324  mov     rcx, rdi
0x14000a327  call    FreeTracker
0x14000a32c  movzx   edx, r15b
0x14000a330  jmp     loc_14000A04C
0x14000a335  cmp     cs:byte_140039673, r13b
0x14000a33c  jz      short loc_14000A34E
0x14000a33e  test    dword ptr [rdi+0F0h], 10000h
0x14000a348  jz      loc_14000A19E
0x14000a34e  mov     rax, [r14]
0x14000a351  and     dword ptr [rax+48h], 0FFFFFF0Fh
0x14000a358  mov     rax, [r14]
0x14000a35b  or      dword ptr [rax+48h], 20h
0x14000a35f  mov     rcx, [r14]
0x14000a362  call    NbtCheckNameAddrTimer
0x14000a367  mov     r9, [r14]
0x14000a36a  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x14000a371  mov     r8b, 1
0x14000a374  mov     [rsp+98h+var_78], rsi; __int64
0x14000a379  mov     edx, 0Ch
0x14000a37e  mov     [r9+70h], r13
0x14000a382  mov     r9d, 434h
0x14000a388  lock dec cs:dword_1400394B0
0x14000a38f  mov     rcx, [r14]; P
0x14000a392  call    NbtDereferenceName
0x14000a397  mov     [r14], r13
0x14000a39a  lea     rcx, SpinLock; SpinLock
0x14000a3a1  mov     rbx, [rbx+40h]
0x14000a3a5  movzx   edx, r15b; NewIrql
0x14000a3a9  call    cs:__imp_KeReleaseSpinLock
0x14000a3b0  nop     dword ptr [rax+rax+00h]
0x14000a3b5  mov     r8d, 102h
0x14000a3bb  mov     rdx, rbx
0x14000a3be  mov     rcx, rbp
0x14000a3c1  call    CompleteClientReq
0x14000a3c6  mov     r9, rsi
0x14000a3c9  xor     edx, edx
0x14000a3cb  mov     r8d, 441h
0x14000a3d1  mov     rcx, rdi
0x14000a3d4  call    NbtDereferenceTracker
0x14000a3d9  jmp     loc_14000A05F
0x14000a3de  or      r8d, 4
0x14000a3e2  mov     [rdi+0F0h], r8d
0x14000a3e9  jmp     loc_140009F94
0x14000a3ee  mov     ecx, 0FFEFh
0x14000a3f3  and     ax, cx
0x14000a3f6  or      ax, 1
0x14000a3fa  mov     [rbx+100h], ax
0x14000a401  mov     rax, [rdi+20h]
0x14000a405  cmp     [rax+1E8h], r13d
0x14000a40c  jnz     loc_14000A1D2
0x14000a412  mov     dword ptr [rbx+18h], 0Ah
0x14000a419  movzx   edx, r15b
0x14000a41d  jmp     loc_14000A04C
0x14000a422  test    byte ptr cs:xmmword_140038420+3, 2
0x14000a429  jz      short loc_14000A441
0x14000a42b  mov     edx, 0Eh
0x14000a430  lea     r8, WPP_bce120156c883c01baa58c4fefcf98ff_Traceguids
0x14000a437  mov     ecx, 419h
0x14000a43c  call    WPP_SF_
0x14000a441  mov     rax, [rdi+30h]
0x14000a445  lea     r8, [rbx+48h]
0x14000a449  mov     rcx, [rax]
0x14000a44c  cmp     [rcx+8], rax
0x14000a450  jnz     loc_14000A5E4
0x14000a456  mov     rdx, [rax+8]
  ... truncated ...
```
