# ReleaseCompletion

- ea: `0x140019a10`
- end: `0x140019dac`
- name: `ReleaseCompletion`
- size: `924`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140006900`
- `0x14000a7b0`
- `0x14000b7e8`
- `0x14000b810`
- `0x140019a10`
- `0x140019db4`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019b54`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019c02`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019a53`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019b54`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019c02`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019af3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ba1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c31`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019af3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019ba1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019bc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140019c31`

## pseudocode

```c
void __fastcall ReleaseCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx
  char v6; // si
  KIRQL v7; // al
  __int64 *v8; // rdx
  KIRQL v9; // bp
  __int64 v11; // rax
  KIRQL v12; // bp
  KIRQL v13; // di
  int v14; // eax
  int v15; // [rsp+A0h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 48);
  if ( a3 )
  {
    if ( *(_QWORD *)(v4 + 96) )
    {
      v6 = 1;
      if ( !(unsigned int)IsBrowserName(v4 + 164) )
        v6 = NodeType;
    }
    else
    {
      v6 = 1;
      *(_WORD *)(a3 + 20) = 1;
    }
    v7 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
    v8 = (__int64 *)NbtConfig;
    v9 = v7;
    while ( v8 != &NbtConfig )
    {
      if ( v8 == (__int64 *)(*(_QWORD *)(a1 + 32) + 344LL) )
      {
        if ( (*(_WORD *)(a3 + 20))-- == 1 )
        {
          if ( (v6 & 4) == 0 )
            break;
          v14 = *(_DWORD *)(a1 + 240);
          if ( (v14 & 2) == 0 )
            break;
          *(_DWORD *)(a1 + 240) = v14 & 0xFFFFFFFC | 1;
          *(_DWORD *)(a3 + 24) = dword_1400395BC;
          *(_WORD *)(a3 + 20) = word_1400395DA;
        }
        v11 = *(_QWORD *)(a1 + 32);
        if ( v11 && *(_DWORD *)(v11 + 360) == 1131832644 )
        {
          _InterlockedAdd((volatile signed __int32 *)(v11 + 364), 1u);
          ++*(_DWORD *)(v11 + 1112);
          v15 = 0;
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              *(_DWORD *)(a1 + 20),
              15,
              (unsigned int)WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids,
              a1,
              *(_DWORD *)(a1 + 20),
              *(_DWORD *)(a1 + 20) + 1,
              81,
              (__int64)"minio\\netbt\\sys\\namesrv.c");
          _InterlockedAdd((volatile signed __int32 *)(a1 + 20), 1u);
          KeReleaseSpinLock(&SpinLock, v9);
          SendNameServiceRequest(*(_QWORD *)(a1 + 48), Str2, a1, 0, 0, 0, 0, 0, 7u, 1, &v15);
          v12 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
          NBT_DEREFERENCE_DEVICE(*(_QWORD *)(a1 + 32), 7);
          if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
            WPP_SF_qddds(
              *(_DWORD *)(a1 + 20) - 1,
              84,
              (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
              a1,
              *(_DWORD *)(a1 + 20),
              *(_DWORD *)(a1 + 20) - 1,
              97,
              (__int64)"minio\\netbt\\sys\\namesrv.c");
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
            FreeTracker(a1, 4);
          KeReleaseSpinLock(&SpinLock, v12);
          *(_WORD *)(a3 + 256) |= 1u;
          return;
        }
        break;
      }
      v8 = (__int64 *)*v8;
    }
    KeReleaseSpinLock(&SpinLock, v9);
    if ( (int)InterlockedCallCompletion(a3, 258) >= 0 )
    {
      if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
        WPP_SF_qddds(
          *(_DWORD *)(a1 + 20),
          84,
          (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
          a1,
          *(_DWORD *)(a1 + 20),
          *(_DWORD *)(a1 + 20) - 1,
          120,
          (__int64)"minio\\netbt\\sys\\namesrv.c");
      v13 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
        FreeTracker(a1, 4);
      KeReleaseSpinLock(&SpinLock, v13);
    }
  }
  else
  {
    *(_QWORD *)(v4 + 112) = 0;
    if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
      WPP_SF_qddds(
        *(_DWORD *)(a1 + 20),
        84,
        (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
        a1,
        *(_DWORD *)(a1 + 20),
        *(_DWORD *)(a1 + 20) - 1,
        19,
        (__int64)"minio\\netbt\\sys\\namesrv.c");
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
      FreeTracker(a1, 4);
  }
}

```

## disassembly

```asm
0x140019a10  push    rbx
0x140019a12  push    rbp
0x140019a13  push    rsi
0x140019a14  push    rdi
0x140019a15  push    r12
0x140019a17  push    r13
0x140019a19  sub     rsp, 68h
0x140019a1d  mov     rbx, rcx
0x140019a20  mov     rcx, [rcx+30h]
0x140019a24  mov     rdi, r8
0x140019a27  test    r8, r8
0x140019a2a  jz      loc_140019C62
0x140019a30  cmp     qword ptr [rcx+60h], 0
0x140019a35  mov     r12d, 1
0x140019a3b  jnz     loc_140019C3F
0x140019a41  mov     esi, r12d
0x140019a44  mov     [r8+14h], r12w
0x140019a49  lea     r13, SpinLock
0x140019a50  mov     rcx, r13; SpinLock
0x140019a53  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019a5a  nop     dword ptr [rax+rax+00h]
0x140019a5f  mov     rdx, cs:NbtConfig
0x140019a66  mov     bpl, al
0x140019a69  lea     rax, NbtConfig
0x140019a70  cmp     rdx, rax
0x140019a73  jz      loc_140019BC1
0x140019a79  mov     rcx, [rbx+20h]
0x140019a7d  add     rcx, 158h
0x140019a84  cmp     rdx, rcx
0x140019a87  jz      short loc_140019A8E
0x140019a89  mov     rdx, [rdx]
0x140019a8c  jmp     short loc_140019A69
0x140019a8e  mov     eax, 0FFFFh
0x140019a93  add     [rdi+14h], ax
0x140019a97  jz      loc_140019BB7
0x140019a9d  mov     rax, [rbx+20h]
0x140019aa1  test    rax, rax
0x140019aa4  jz      loc_140019BC1
0x140019aaa  cmp     dword ptr [rax+168h], 43766544h
0x140019ab4  jnz     loc_140019BC1
0x140019aba  lock add [rax+16Ch], r12d
0x140019ac2  add     [rax+458h], r12d
0x140019ac9  mov     [rsp+98h+arg_0], 0
0x140019ad4  test    byte ptr cs:xmmword_140038420+9, 40h
0x140019adb  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x140019ae2  jnz     loc_140019CCB
0x140019ae8  lock add [rbx+14h], r12d
0x140019aed  mov     dl, bpl; NewIrql
0x140019af0  mov     rcx, r13; SpinLock
0x140019af3  call    cs:__imp_KeReleaseSpinLock
0x140019afa  nop     dword ptr [rax+rax+00h]
0x140019aff  mov     rdx, cs:Str2
0x140019b06  lea     rax, [rsp+98h+arg_0]
0x140019b0e  mov     rcx, [rbx+30h]
0x140019b12  xor     r9d, r9d
0x140019b15  mov     [rsp+98h+var_48], rax
0x140019b1a  mov     r8, rbx
0x140019b1d  mov     [rsp+98h+var_50], r12d
0x140019b22  mov     [rsp+98h+var_58], 7
0x140019b2a  mov     dword ptr [rsp+98h+var_60], 0
0x140019b32  mov     [rsp+98h+var_68], 0
0x140019b3a  mov     [rsp+98h+var_70], 0
0x140019b43  mov     [rsp+98h+var_78], 0
0x140019b4c  call    SendNameServiceRequest
0x140019b51  mov     rcx, r13; SpinLock
0x140019b54  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019b5b  nop     dword ptr [rax+rax+00h]
0x140019b60  mov     rcx, [rbx+20h]
0x140019b64  mov     r8b, r12b
0x140019b67  mov     edx, 7
0x140019b6c  mov     bpl, al
0x140019b6f  call    NBT_DEREFERENCE_DEVICE
0x140019b74  test    byte ptr cs:xmmword_140038420+9, 40h
0x140019b7b  jnz     loc_140019D3A
0x140019b81  or      eax, 0FFFFFFFFh
0x140019b84  lock xadd [rbx+14h], eax
0x140019b89  cmp     eax, r12d
0x140019b8c  jnz     short loc_140019B9B
0x140019b8e  mov     edx, 4
0x140019b93  mov     rcx, rbx
0x140019b96  call    FreeTracker
0x140019b9b  mov     dl, bpl; NewIrql
0x140019b9e  mov     rcx, r13; SpinLock
0x140019ba1  call    cs:__imp_KeReleaseSpinLock
0x140019ba8  nop     dword ptr [rax+rax+00h]
0x140019bad  or      [rdi+100h], r12w
0x140019bb5  jmp     short loc_140019BE4
0x140019bb7  test    sil, 4
0x140019bbb  jnz     loc_140019C98
0x140019bc1  mov     dl, bpl; NewIrql
0x140019bc4  mov     rcx, r13; SpinLock
0x140019bc7  call    cs:__imp_KeReleaseSpinLock
0x140019bce  nop     dword ptr [rax+rax+00h]
0x140019bd3  mov     edx, 102h
0x140019bd8  mov     rcx, rdi
0x140019bdb  call    InterlockedCallCompletion
0x140019be0  test    eax, eax
0x140019be2  jns     short loc_140019BF2
0x140019be4  add     rsp, 68h
0x140019be8  pop     r13
0x140019bea  pop     r12
0x140019bec  pop     rdi
0x140019bed  pop     rsi
0x140019bee  pop     rbp
0x140019bef  pop     rbx
0x140019bf0  retn
0x140019bf2  test    byte ptr cs:xmmword_140038420+9, 40h
0x140019bf9  jnz     loc_140019D71
0x140019bff  mov     rcx, r13; SpinLock
0x140019c02  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140019c09  nop     dword ptr [rax+rax+00h]
0x140019c0e  mov     dil, al
0x140019c11  or      ecx, 0FFFFFFFFh
0x140019c14  lock xadd [rbx+14h], ecx
0x140019c19  cmp     ecx, r12d
0x140019c1c  jnz     short loc_140019C2B
0x140019c1e  mov     edx, 4
0x140019c23  mov     rcx, rbx
0x140019c26  call    FreeTracker
0x140019c2b  mov     dl, dil; NewIrql
0x140019c2e  mov     rcx, r13; SpinLock
0x140019c31  call    cs:__imp_KeReleaseSpinLock
0x140019c38  nop     dword ptr [rax+rax+00h]
0x140019c3d  jmp     short loc_140019BE4
0x140019c3f  add     rcx, 0A4h
0x140019c46  call    IsBrowserName
0x140019c4b  mov     esi, r12d
0x140019c4e  test    eax, eax
0x140019c50  jnz     loc_140019A49
0x140019c56  movzx   esi, cs:NodeType
0x140019c5d  jmp     loc_140019A49
0x140019c62  mov     qword ptr [rcx+70h], 0
0x140019c6a  test    byte ptr cs:xmmword_140038420+9, 40h
0x140019c71  jnz     loc_140019CFF
0x140019c77  or      eax, 0FFFFFFFFh
0x140019c7a  lock xadd [rbx+14h], eax
0x140019c7f  cmp     eax, 1
0x140019c82  jnz     loc_140019BE4
0x140019c88  lea     edx, [rax+3]
0x140019c8b  mov     rcx, rbx
0x140019c8e  call    FreeTracker
0x140019c93  jmp     loc_140019BE4
0x140019c98  mov     eax, [rbx+0F0h]
0x140019c9e  test    al, 2
0x140019ca0  jz      loc_140019BC1
0x140019ca6  and     eax, 0FFFFFFFDh
0x140019ca9  or      eax, r12d
0x140019cac  mov     [rbx+0F0h], eax
0x140019cb2  mov     eax, cs:dword_1400395BC
0x140019cb8  mov     [rdi+18h], eax
0x140019cbb  movzx   eax, cs:word_1400395DA
0x140019cc2  mov     [rdi+14h], ax
0x140019cc6  jmp     loc_140019A9D
0x140019ccb  mov     ecx, [rbx+14h]
0x140019cce  lea     r8, WPP_d1b5c980e8823d44a1ca8055a7722167_Traceguids
0x140019cd5  mov     [rsp+98h+var_60], rsi
0x140019cda  mov     edx, 0Fh
0x140019cdf  mov     [rsp+98h+var_68], 851h
0x140019ce7  mov     r9, rbx
0x140019cea  lea     eax, [rcx+1]
0x140019ced  mov     dword ptr [rsp+98h+var_70], eax
0x140019cf1  mov     dword ptr [rsp+98h+var_78], ecx
0x140019cf5  call    WPP_SF_qddds
0x140019cfa  jmp     loc_140019AE8
0x140019cff  mov     ecx, [rbx+14h]
0x140019d02  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x140019d09  mov     [rsp+98h+var_60], rsi
0x140019d0e  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140019d15  mov     [rsp+98h+var_68], 813h
0x140019d1d  mov     edx, 54h ; 'T'
0x140019d22  mov     r9, rbx
0x140019d25  lea     eax, [rcx-1]
0x140019d28  mov     dword ptr [rsp+98h+var_70], eax
0x140019d2c  mov     dword ptr [rsp+98h+var_78], ecx
0x140019d30  call    WPP_SF_qddds
0x140019d35  jmp     loc_140019C77
0x140019d3a  mov     r8d, [rbx+14h]
0x140019d3e  mov     edx, 54h ; 'T'
0x140019d43  mov     [rsp+98h+var_60], rsi
0x140019d48  mov     r9, rbx
0x140019d4b  mov     [rsp+98h+var_68], 861h
0x140019d53  lea     ecx, [r8-1]
0x140019d57  mov     dword ptr [rsp+98h+var_70], ecx
0x140019d5b  mov     dword ptr [rsp+98h+var_78], r8d
0x140019d60  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140019d67  call    WPP_SF_qddds
0x140019d6c  jmp     loc_140019B81
0x140019d71  mov     ecx, [rbx+14h]
0x140019d74  lea     rsi, aMinioNetbtSysN_0; "minio\\netbt\\sys\\namesrv.c"
0x140019d7b  mov     [rsp+98h+var_60], rsi
0x140019d80  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x140019d87  mov     [rsp+98h+var_68], 878h
0x140019d8f  mov     edx, 54h ; 'T'
0x140019d94  mov     r9, rbx
0x140019d97  lea     eax, [rcx-1]
0x140019d9a  mov     dword ptr [rsp+98h+var_70], eax
0x140019d9e  mov     dword ptr [rsp+98h+var_78], ecx
0x140019da2  call    WPP_SF_qddds
0x140019da7  jmp     loc_140019BFF
```
