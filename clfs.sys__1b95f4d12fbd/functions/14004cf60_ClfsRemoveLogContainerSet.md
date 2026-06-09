# ClfsRemoveLogContainerSet

- ea: `0x14004cf60`
- end: `0x14004d2cf`
- name: `ClfsRemoveLogContainerSet`
- size: `879`
- prototype: `NTSTATUS __stdcall(PLOG_FILE_OBJECT plfoLog, USHORT cContainers, PUNICODE_STRING rgwszContainerPath, BOOLEAN fForce)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14004ce20`

## callees

- `0x14000bac0`
- `0x14000c2f0`
- `0x14000ed64`
- `0x140011d90`
- `0x140017f20`
- `0x14004cf60`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d084`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004d084`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d281`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140080687`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004d281`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140080687`

## string_xrefs

- `0x14004cfbb`: `ClfsRemoveLogContainerSet`
- `0x14004d006`: `ClfsRemoveLogContainerSet`
- `0x14004d066`: `ClfsRemoveLogContainerSet`
- `0x14004d107`: `ClfsRemoveLogContainerSet`
- `0x14004d1de`: `ClfsRemoveLogContainerSet`
- `0x14004d22e`: `ClfsRemoveLogContainerSet`
- `0x14004d2b0`: `ClfsRemoveLogContainerSet`

## pseudocode

```c
NTSTATUS __stdcall ClfsRemoveLogContainerSet(
        PLOG_FILE_OBJECT plfoLog,
        USHORT cContainers,
        PUNICODE_STRING rgwszContainerPath,
        BOOLEAN fForce)
{
  PUNICODE_STRING v4; // rax
  __int64 v8; // r12
  CClfsLogCcb *FsContext2; // r14
  CClfsLogCcb *v10; // rcx
  int v11; // eax
  __int64 v12; // r9
  NTSTATUS v13; // r15d
  USHORT i; // r14
  int v15; // r12d
  __int64 v16; // [rsp+28h] [rbp-70h]
  __int64 v17; // [rsp+30h] [rbp-68h]
  __int64 v18; // [rsp+38h] [rbp-60h]
  __int64 v19; // [rsp+40h] [rbp-58h]
  CClfsLogCcb *v20; // [rsp+48h] [rbp-50h]

  v4 = rgwszContainerPath;
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        82,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsRemoveLogContainerSet",
        2,
        cContainers);
    v4 = rgwszContainerPath;
  }
  if ( cContainers )
  {
    if ( v4 )
    {
      KeEnterCriticalRegion();
      v8 = *((_QWORD *)plfoLog->FsContext + 15);
      v19 = v8;
      FsContext2 = (CClfsLogCcb *)plfoLog->FsContext2;
      v20 = FsContext2;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 64LL))(v8);
      CClfsLogCcb::AddRef(FsContext2);
      v11 = CClfsLogCcb::CheckAccess(v10, 2u);
      v13 = v11;
      HIDWORD(v17) = v11;
      if ( v11 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          LOWORD(v17) = i;
          if ( i >= cContainers )
            break;
          LOBYTE(v12) = fForce;
          v15 = (*(__int64 (__fastcall **)(__int64, PLOG_FILE_OBJECT, UNICODE_STRING *, __int64))(*(_QWORD *)v8 + 224LL))(
                  v8,
                  plfoLog,
                  &rgwszContainerPath[i],
                  v12);
          LODWORD(v18) = v15;
          if ( v15 < 0 )
          {
            if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
            {
              LODWORD(v16) = v15;
              WPP_SF_slD(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                86,
                (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                (unsigned int)"ClfsRemoveLogContainerSet",
                102,
                v16,
                v17,
                v18);
            }
            v13 = v15;
            HIDWORD(v17) = v15;
            if ( v15 == -1072037871 )
            {
              if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
              {
                LODWORD(v16) = -1072037871;
                WPP_SF_slD(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  87,
                  (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
                  (unsigned int)"ClfsRemoveLogContainerSet",
                  117,
                  v16);
              }
              v8 = v19;
              break;
            }
          }
          v8 = v19;
        }
        FsContext2 = v20;
      }
      else if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
             && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        LODWORD(v16) = v11;
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          85,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsRemoveLogContainerSet",
          67,
          v16);
      }
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 72LL))(v8);
      if ( FsContext2 )
        CClfsLogCcb::Release(FsContext2);
      KeLeaveCriticalRegion();
      if ( v13 >= 0
        && WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          88,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsRemoveLogContainerSet",
          157);
      }
      return v13;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
      {
        LODWORD(v16) = -1073741789;
        WPP_SF_slD(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          84,
          (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
          (unsigned int)"ClfsRemoveLogContainerSet",
          29,
          v16);
      }
      return -1073741789;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      LODWORD(v16) = -1073741811;
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        83,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsRemoveLogContainerSet",
        14,
        v16);
    }
    return -1073741811;
  }
}

```

## disassembly

```asm
0x14004cf60  mov     rax, rsp
0x14004cf63  mov     [rax+20h], r9b
0x14004cf67  mov     [rax+18h], r8
0x14004cf6b  mov     [rax+10h], dx
0x14004cf6f  mov     [rax+8], rcx
0x14004cf73  push    rbx
0x14004cf74  push    rsi
0x14004cf75  push    rdi
0x14004cf76  push    r12
0x14004cf78  push    r13
0x14004cf7a  push    r14
0x14004cf7c  push    r15
0x14004cf7e  sub     rsp, 60h
0x14004cf82  mov     rax, r8
0x14004cf85  movzx   r13d, dx
0x14004cf89  mov     r14, rcx
0x14004cf8c  lea     rsi, WPP_GLOBAL_Control
0x14004cf93  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cf9a  mov     edi, 4000000h
0x14004cf9f  cmp     rcx, rsi
0x14004cfa2  jz      short loc_14004CFDA
0x14004cfa4  test    [rcx+2Ch], edi
0x14004cfa7  jz      short loc_14004CFD2
0x14004cfa9  mov     edx, 52h ; 'R'
0x14004cfae  mov     dword ptr [rsp+98h+var_70], r13d
0x14004cfb3  mov     [rsp+98h+var_78], 0A02h
0x14004cfbb  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004cfc2  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004cfc9  mov     rcx, [rcx+18h]
0x14004cfcd  call    WPP_SF_slD
0x14004cfd2  mov     rax, [rsp+98h+arg_10]
0x14004cfda  xor     ebx, ebx
0x14004cfdc  cmp     bx, r13w
0x14004cfe0  jnz     short loc_14004D033
0x14004cfe2  mov     rcx, cs:WPP_GLOBAL_Control
0x14004cfe9  cmp     rcx, rsi
0x14004cfec  jz      short loc_14004D01D
0x14004cfee  test    [rcx+2Ch], edi
0x14004cff1  jz      short loc_14004D01D
0x14004cff3  lea     edx, [rbx+53h]
0x14004cff6  mov     dword ptr [rsp+98h+var_70], 0C000000Dh
0x14004cffe  mov     [rsp+98h+var_78], 0A0Eh
0x14004d006  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d00d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d014  mov     rcx, [rcx+18h]
0x14004d018  call    WPP_SF_slD
0x14004d01d  mov     eax, 0C000000Dh
0x14004d022  add     rsp, 60h
0x14004d026  pop     r15
0x14004d028  pop     r14
0x14004d02a  pop     r13
0x14004d02c  pop     r12
0x14004d02e  pop     rdi
0x14004d02f  pop     rsi
0x14004d030  pop     rbx
0x14004d031  retn
0x14004d033  mov     [rsp+98h+var_48], rbx
0x14004d038  mov     [rsp+98h+var_40], rbx
0x14004d03d  test    rax, rax
0x14004d040  jnz     short loc_14004D084
0x14004d042  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d049  cmp     rcx, rsi
0x14004d04c  jz      short loc_14004D07D
0x14004d04e  test    [rcx+2Ch], edi
0x14004d051  jz      short loc_14004D07D
0x14004d053  lea     edx, [rax+54h]
0x14004d056  mov     dword ptr [rsp+98h+var_70], 0C0000023h
0x14004d05e  mov     [rsp+98h+var_78], 0A1Dh
0x14004d066  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d06d  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d074  mov     rcx, [rcx+18h]
0x14004d078  call    WPP_SF_slD
0x14004d07d  mov     eax, 0C0000023h
0x14004d082  jmp     short loc_14004D022
0x14004d084  call    cs:__imp_KeEnterCriticalRegion
0x14004d08b  nop     dword ptr [rax+rax+00h]
0x14004d090  mov     rax, [r14+18h]
0x14004d094  mov     r12, [rax+78h]
0x14004d098  mov     [rsp+98h+var_58], r12
0x14004d09d  mov     [rsp+98h+var_48], r12
0x14004d0a2  mov     r14, [r14+20h]
0x14004d0a6  mov     [rsp+98h+var_50], r14
0x14004d0ab  mov     [rsp+98h+var_40], r14
0x14004d0b0  mov     rax, [r12]
0x14004d0b4  mov     rax, [rax+40h]
0x14004d0b8  mov     rcx, r12
0x14004d0bb  call    _guard_dispatch_icall
0x14004d0c0  mov     rcx, r14; this
0x14004d0c3  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x14004d0c8  mov     edx, 2; unsigned int
0x14004d0cd  call    ?CheckAccess@CClfsLogCcb@@QEAAJK@Z; CClfsLogCcb::CheckAccess(ulong)
0x14004d0d2  mov     r15d, eax
0x14004d0d5  mov     [rsp+98h+var_64], eax
0x14004d0d9  test    eax, eax
0x14004d0db  jns     short loc_14004D123
0x14004d0dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d0e4  cmp     rcx, rsi
0x14004d0e7  jz      loc_14004D25F
0x14004d0ed  test    [rcx+2Ch], edi
0x14004d0f0  jz      loc_14004D25F
0x14004d0f6  mov     edx, 55h ; 'U'
0x14004d0fb  mov     dword ptr [rsp+98h+var_70], eax
0x14004d0ff  mov     [rsp+98h+var_78], 0A43h
0x14004d107  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d10e  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d115  mov     rcx, [rcx+18h]
0x14004d119  call    WPP_SF_slD
0x14004d11e  jmp     loc_14004D25F
0x14004d123  movzx   r14d, bx
0x14004d127  mov     [rsp+98h+var_68], r14w
0x14004d12d  cmp     r14w, r13w
0x14004d131  jnb     loc_14004D25A
0x14004d137  mov     rax, [r12]
0x14004d13b  movzx   r8d, r14w
0x14004d13f  shl     r8, 4
0x14004d143  add     r8, [rsp+98h+arg_10]
0x14004d14b  mov     rax, [rax+0E0h]
0x14004d152  mov     r9b, [rsp+98h+arg_18]
0x14004d15a  mov     rdx, [rsp+98h+arg_0]
0x14004d162  mov     rcx, r12
0x14004d165  call    _guard_dispatch_icall
0x14004d16a  mov     r12d, eax
0x14004d16d  mov     dword ptr [rsp+98h+var_60], eax
0x14004d171  jmp     short loc_14004D1B0
0x14004d173  mov     r12d, eax
0x14004d176  mov     dword ptr [rsp+98h+var_60], eax
0x14004d17a  lea     rsi, WPP_GLOBAL_Control
0x14004d181  mov     edi, 4000000h
0x14004d186  xor     ebx, ebx
0x14004d188  movzx   r13d, [rsp+98h+arg_8]
0x14004d191  mov     rax, [rsp+98h+var_48]
0x14004d196  mov     [rsp+98h+var_58], rax
0x14004d19b  mov     rcx, [rsp+98h+var_40]
0x14004d1a0  mov     [rsp+98h+var_50], rcx
0x14004d1a5  mov     r15d, [rsp+98h+var_64]
0x14004d1aa  movzx   r14d, [rsp+98h+var_68]
0x14004d1b0  test    r12d, r12d
0x14004d1b3  jns     loc_14004D247
0x14004d1b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d1c0  cmp     rcx, rsi
0x14004d1c3  jz      short loc_14004D1F5
0x14004d1c5  mov     eax, [rcx+2Ch]
0x14004d1c8  test    edi, eax
0x14004d1ca  jz      short loc_14004D1F5
0x14004d1cc  mov     edx, 56h ; 'V'
0x14004d1d1  mov     dword ptr [rsp+98h+var_70], r12d
0x14004d1d6  mov     [rsp+98h+var_78], 0A66h
0x14004d1de  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d1e5  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d1ec  mov     rcx, [rcx+18h]
0x14004d1f0  call    WPP_SF_slD
0x14004d1f5  mov     r15d, r12d
0x14004d1f8  mov     [rsp+98h+var_64], r12d
0x14004d1fd  cmp     r12d, 0C01A0011h
0x14004d204  jnz     short loc_14004D247
0x14004d206  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d20d  cmp     rcx, rsi
0x14004d210  jz      short loc_14004D255
0x14004d212  mov     eax, [rcx+2Ch]
0x14004d215  test    edi, eax
0x14004d217  jz      short loc_14004D255
0x14004d219  mov     edx, 57h ; 'W'
0x14004d21e  mov     dword ptr [rsp+98h+var_70], 0C01A0011h
0x14004d226  mov     [rsp+98h+var_78], 0A75h
0x14004d22e  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d235  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d23c  mov     rcx, [rcx+18h]
0x14004d240  call    WPP_SF_slD
0x14004d245  jmp     short loc_14004D255
0x14004d247  inc     r14w
0x14004d24b  mov     r12, [rsp+98h+var_58]
0x14004d250  jmp     loc_14004D127
0x14004d255  mov     r12, [rsp+98h+var_58]
0x14004d25a  mov     r14, [rsp+98h+var_50]
0x14004d25f  test    r12, r12
0x14004d262  jz      short loc_14004D274
0x14004d264  mov     rax, [r12]
0x14004d268  mov     rax, [rax+48h]
0x14004d26c  mov     rcx, r12
0x14004d26f  call    _guard_dispatch_icall
0x14004d274  test    r14, r14
0x14004d277  jz      short loc_14004D281
0x14004d279  mov     rcx, r14; Entry
0x14004d27c  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14004d281  call    cs:__imp_KeLeaveCriticalRegion
0x14004d288  nop     dword ptr [rax+rax+00h]
0x14004d28d  test    r15d, r15d
0x14004d290  js      short loc_14004D2C7
0x14004d292  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d299  cmp     rcx, rsi
0x14004d29c  jz      short loc_14004D2C7
0x14004d29e  test    [rcx+2Ch], edi
0x14004d2a1  jz      short loc_14004D2C7
0x14004d2a3  mov     edx, 58h ; 'X'
0x14004d2a8  mov     [rsp+98h+var_78], 0A9Dh
0x14004d2b0  lea     r9, aClfsremovelogc; "ClfsRemoveLogContainerSet"
0x14004d2b7  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14004d2be  mov     rcx, [rcx+18h]
0x14004d2c2  call    WPP_SF_sd
0x14004d2c7  mov     eax, r15d
0x14004d2ca  jmp     loc_14004D022
0x14008064b  push    rbp
0x14008064d  sub     rsp, 30h
0x140080651  mov     rbp, rdx
0x140080654  mov     rcx, [rbp+50h]
0x140080658  test    rcx, rcx
0x14008065b  jz      short loc_140080671
0x14008065d  mov     rax, [rcx]
0x140080660  mov     rax, [rax+48h]
0x140080664  call    _guard_dispatch_icall
0x140080669  mov     qword ptr [rbp+50h], 0
0x140080671  mov     rcx, [rbp+58h]; Entry
0x140080675  test    rcx, rcx
0x140080678  jz      short loc_140080687
0x14008067a  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14008067f  mov     qword ptr [rbp+58h], 0
0x140080687  call    cs:__imp_KeLeaveCriticalRegion
0x14008068e  nop     dword ptr [rax+rax+00h]
0x140080693  nop
0x140080694  add     rsp, 30h
0x140080698  pop     rbp
0x140080699  retn
```
