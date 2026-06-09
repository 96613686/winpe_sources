# IO_DP_DRIVE::CommonHardRead(void *,BIG_INT,ulong,void *)

- ea: `0x18001e4bc`
- end: `0x18001e822`
- name: `?CommonHardRead@IO_DP_DRIVE@@IEAAEPEAXVBIG_INT@@K0@Z`
- size: `870`
- prototype: `char __fastcall(__int64, void *, signed __int64, unsigned int, char *)`
- caller_count: `5`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001e480`
- `0x1800806b0`
- `0x1800809b0`
- `0x180080d2c`
- `0x180081210`

## callees

- `0x1800063b8`
- `0x18001e4bc`
- `0x18001eda0`
- `0x1800251f6`
- `0x1800620e0`
- `0x180069f58`
- `0x18007a2d4`
- `0x18007a4e0`
- `0x18007a554`
- `0x18007c608`
- `0x18007d1d0`
- `0x180088010`

## import_xrefs

- `ntdll!NtReadFile` at `0x18001e66f`
- `ntdll!NtReadFile` at `0x18001e66f`
- `KERNEL32!RaiseException` at `0x18001e7f2`
- `KERNEL32!RaiseException` at `0x18001e7f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
char __fastcall IO_DP_DRIVE::CommonHardRead(__int64 a1, void *a2, signed __int64 a3, unsigned int a4, char *a5)
{
  __int64 v5; // r12
  signed __int64 v6; // rbx
  char v8; // r14
  void *v9; // r13
  unsigned int v10; // ecx
  unsigned int v11; // esi
  unsigned int v12; // edi
  signed __int64 v13; // rdi
  PVOID Buffer; // rax
  ULONG Length; // r12d
  unsigned int v16; // eax
  __int64 v17; // r8
  IO_DP_DRIVE *v18; // rcx
  MESSAGE *v19; // rcx
  __int64 v20; // rcx
  unsigned int v22; // [rsp+50h] [rbp-31h]
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-29h] BYREF
  void *Src; // [rsp+60h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v26[2]; // [rsp+78h] [rbp-9h] BYREF
  int v27; // [rsp+88h] [rbp+7h]
  PVOID v28[2]; // [rsp+90h] [rbp+Fh]
  char v30; // [rsp+F8h] [rbp+77h]

  v5 = a4;
  v26[0] = &HMEM::`vftable';
  v26[1] = HMEM_cd;
  v6 = a3;
  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  v27 = 0;
  *(_OWORD *)v28 = 0;
  v8 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_iD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids, a3, a4);
  if ( (_DWORD)v5 )
  {
    v9 = a5;
    v30 = 0;
    if ( (*(_DWORD *)(a1 + 348) & (unsigned int)a5) != 0 )
    {
      v30 = 1;
      HMEM::Destroy((HMEM *)v26);
    }
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    v22 = v10;
    v11 = 0x10000000 / v10;
    if ( (unsigned int)v5 <= 0x10000000 / v10 )
    {
      v11 = v5;
    }
    else if ( !(0x10000000 / v10) )
    {
      v11 = 1;
    }
    v12 = v10 * v11;
    if ( !HMEM::Acquire((HMEM *)v26, v10 * v11, *(_DWORD *)(a1 + 348)) )
    {
      do
      {
        if ( v12 <= 0x40000 )
          break;
        if ( v11 < 2 )
          break;
        v11 >>= 1;
        v12 = v22 * v11;
      }
      while ( !HMEM::Acquire((HMEM *)v26, v22 * v11, *(_DWORD *)(a1 + 348)) );
      v9 = a5;
    }
    if ( v28[1] )
    {
      v13 = v6 + v5;
      while ( 1 )
      {
        if ( v6 >= v13 )
          goto LABEL_51;
        if ( v6 + v11 > v13 )
          v11 = v13 - v6;
        Buffer = v9;
        Length = v22 * v11;
        ByteOffset.QuadPart = v6 * (int)v22;
        if ( v30 )
          Buffer = v28[1];
        Src = Buffer;
        v16 = NtReadFile(a2, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
        *(_DWORD *)(a1 + 96) = v16;
        if ( v16 == -1073741801 )
        {
          v11 >>= 1;
          v6 -= v11;
        }
        else
        {
          if ( (v16 & 0xC0000000) == 0xC0000000 )
          {
            v18 = (IO_DP_DRIVE *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_DiD)(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                v17,
                v16,
                (union _LARGE_INTEGER)ByteOffset.QuadPart,
                Length);
LABEL_38:
              v18 = (IO_DP_DRIVE *)WPP_GLOBAL_Control;
            }
LABEL_39:
            if ( *(_QWORD *)(a1 + 408) )
            {
              v19 = *(MESSAGE **)(a1 + 408);
              if ( (*(_DWORD *)(a1 + 96) & 0xC0000000) == 0xC0000000 )
                MESSAGE::LogMsg(v19, 0x69A4u, "%x%I64x%x", *(_DWORD *)(a1 + 96), ByteOffset.QuadPart, Length);
              else
                MESSAGE::LogMsg(
                  v19,
                  0x69A5u,
                  "%I64d%x%x",
                  ByteOffset.QuadPart,
                  LODWORD(IoStatusBlock.Information),
                  Length);
              v18 = (IO_DP_DRIVE *)WPP_GLOBAL_Control;
            }
            if ( *(_BYTE *)(a1 + 416) && IO_DP_DRIVE::IsDiskDisappearedException(v18, *(_DWORD *)(a1 + 96)) )
            {
              if ( (PVOID *)v20 != &WPP_GLOBAL_Control && (*(_BYTE *)(v20 + 28) & 1) != 0 )
                WPP_SF_d(*(_QWORD *)(v20 + 16), 27, &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids);
              RaiseException(*(_DWORD *)(a1 + 96), 1u, 0, 0);
            }
            break;
          }
          if ( IoStatusBlock.Information != Length )
          {
            v18 = (IO_DP_DRIVE *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDD)(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                26,
                &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids,
                (union _LARGE_INTEGER)ByteOffset.QuadPart,
                IoStatusBlock.Information,
                Length);
              goto LABEL_38;
            }
            goto LABEL_39;
          }
          if ( v30 )
            memcpy_0(a5, Src, Length);
          a5 += Length;
          v9 = a5;
        }
        v6 += v11;
      }
    }
    v8 = 0;
  }
LABEL_51:
  HMEM::~HMEM((HMEM *)v26);
  return v8;
}

```

## disassembly

```asm
0x18001e4bc  mov     [rsp-8+arg_0], rbx
0x18001e4c1  mov     [rsp-8+FileHandle], rdx
0x18001e4c6  push    rbp
0x18001e4c7  push    rsi
0x18001e4c8  push    rdi
0x18001e4c9  push    r12
0x18001e4cb  push    r13
0x18001e4cd  push    r14
0x18001e4cf  push    r15
0x18001e4d1  lea     rbp, [rsp-1Fh]
0x18001e4d6  sub     rsp, 0A0h
0x18001e4dd  lea     rax, ??_7HMEM@@6B@; const HMEM::`vftable'
0x18001e4e4  mov     r12d, r9d
0x18001e4e7  xorps   xmm0, xmm0
0x18001e4ea  mov     [rbp+4Fh+var_58], rax
0x18001e4ee  mov     rax, cs:?HMEM_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const HMEM_cd
0x18001e4f5  xor     edi, edi
0x18001e4f7  mov     [rbp+4Fh+var_50], rax
0x18001e4fb  mov     rbx, r8
0x18001e4fe  mov     r15, rcx
0x18001e501  mov     qword ptr [rbp+4Fh+var_78], rdi
0x18001e505  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18001e509  mov     [rbp+4Fh+var_48], edi
0x18001e50c  movdqu  xmmword ptr [rbp+4Fh+var_40], xmm0
0x18001e511  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e518  lea     rax, WPP_GLOBAL_Control
0x18001e51f  lea     r14d, [rdi+1]
0x18001e523  cmp     rcx, rax
0x18001e526  jz      short loc_18001E549
0x18001e528  test    [rcx+1Ch], r14b
0x18001e52c  jz      short loc_18001E549
0x18001e52e  mov     rcx, [rcx+10h]
0x18001e532  lea     edx, [rdi+18h]
0x18001e535  mov     r9, rbx
0x18001e538  mov     dword ptr [rsp+0D0h+IoStatusBlock], r12d
0x18001e53d  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001e544  call    WPP_SF_iD
0x18001e549  test    r12d, r12d
0x18001e54c  jz      loc_18001E7FB
0x18001e552  mov     eax, [r15+15Ch]
0x18001e559  mov     r13, [rbp+4Fh+arg_20]
0x18001e55d  mov     [rbp+4Fh+arg_18], dil
0x18001e561  test    r13, rax
0x18001e564  jz      short loc_18001E573
0x18001e566  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e56a  mov     [rbp+4Fh+arg_18], r14b
0x18001e56e  call    ?Destroy@HMEM@@AEAAXXZ; HMEM::Destroy(void)
0x18001e573  mov     rax, [r15]
0x18001e576  mov     rcx, r15
0x18001e579  mov     rax, [rax+18h]
0x18001e57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e582  mov     ecx, eax
0x18001e584  mov     [rbp+4Fh+var_80], eax
0x18001e587  xor     edx, edx
0x18001e589  mov     eax, 10000000h
0x18001e58e  div     ecx
0x18001e590  mov     esi, eax
0x18001e592  cmp     r12d, eax
0x18001e595  jbe     short loc_18001E59F
0x18001e597  test    eax, eax
0x18001e599  cmovz   esi, r14d
0x18001e59d  jmp     short loc_18001E5A2
0x18001e59f  mov     esi, r12d
0x18001e5a2  mov     r8d, [r15+15Ch]; unsigned int
0x18001e5a9  mov     edi, esi
0x18001e5ab  imul    edi, ecx
0x18001e5ae  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e5b2  mov     edx, edi; unsigned int
0x18001e5b4  call    ?Acquire@HMEM@@UEAAPEAXKK@Z; HMEM::Acquire(ulong,ulong)
0x18001e5b9  test    rax, rax
0x18001e5bc  jnz     short loc_18001E5F2
0x18001e5be  mov     r13d, [rbp+4Fh+var_80]
0x18001e5c2  cmp     edi, 40000h
0x18001e5c8  jbe     short loc_18001E5EE
0x18001e5ca  cmp     esi, 2
0x18001e5cd  jb      short loc_18001E5EE
0x18001e5cf  mov     r8d, [r15+15Ch]; unsigned int
0x18001e5d6  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e5da  shr     esi, 1
0x18001e5dc  mov     edi, esi
0x18001e5de  imul    edi, r13d
0x18001e5e2  mov     edx, edi; unsigned int
0x18001e5e4  call    ?Acquire@HMEM@@UEAAPEAXKK@Z; HMEM::Acquire(ulong,ulong)
0x18001e5e9  test    rax, rax
0x18001e5ec  jz      short loc_18001E5C2
0x18001e5ee  mov     r13, [rbp+4Fh+arg_20]
0x18001e5f2  cmp     [rbp+4Fh+var_40+8], 0
0x18001e5f7  jz      loc_18001E7F8
0x18001e5fd  lea     rdi, [rbx+r12]
0x18001e601  cmp     rbx, rdi
0x18001e604  jge     loc_18001E7FB
0x18001e60a  movsxd  r8, [rbp+4Fh+var_80]
0x18001e60e  mov     rdx, r8
0x18001e611  mov     ecx, esi
0x18001e613  imul    rdx, rbx
0x18001e617  add     rcx, rbx
0x18001e61a  cmp     rcx, rdi
0x18001e61d  jle     short loc_18001E623
0x18001e61f  mov     esi, edi
0x18001e621  sub     esi, ebx
0x18001e623  mov     [rsp+0D0h+Key], 0; Key
0x18001e62c  lea     rcx, [rbp+4Fh+var_78]
0x18001e630  mov     [rsp+0D0h+ByteOffset], rcx; ByteOffset
0x18001e635  mov     r12d, esi
0x18001e638  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x18001e63c  mov     rax, r13
0x18001e63f  imul    r12d, r8d
0x18001e643  cmp     [rbp+4Fh+arg_18], 0
0x18001e647  mov     qword ptr [rbp+4Fh+var_78], rdx
0x18001e64b  cmovnz  rax, [rbp+4Fh+var_40+8]
0x18001e650  xor     r9d, r9d; ApcContext
0x18001e653  mov     [rbp+4Fh+Src], rax
0x18001e657  xor     r8d, r8d; ApcRoutine
0x18001e65a  mov     [rsp+0D0h+Length], r12d; Length
0x18001e65f  xor     edx, edx; Event
0x18001e661  mov     [rsp+0D0h+Buffer], rax; Buffer
0x18001e666  lea     rax, [rbp+4Fh+var_68]
0x18001e66a  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18001e66f  call    cs:__imp_NtReadFile
0x18001e675  mov     [r15+60h], eax
0x18001e679  mov     r9d, eax
0x18001e67c  cmp     eax, 0C0000017h
0x18001e681  jnz     short loc_18001E68C
0x18001e683  shr     esi, 1
0x18001e685  mov     eax, esi
0x18001e687  sub     rbx, rax
0x18001e68a  jmp     short loc_18001E6BE
0x18001e68c  mov     edx, 0C0000000h
0x18001e691  and     eax, edx
0x18001e693  cmp     eax, edx
0x18001e695  jz      short loc_18001E708
0x18001e697  mov     r13d, r12d
0x18001e69a  cmp     [rbp+4Fh+var_68.Information], r13
0x18001e69e  jnz     short loc_18001E6C8
0x18001e6a0  cmp     [rbp+4Fh+arg_18], 0
0x18001e6a4  jz      short loc_18001E6B6
0x18001e6a6  mov     rdx, [rbp+4Fh+Src]; Src
0x18001e6aa  mov     r8d, r13d; Size
0x18001e6ad  mov     rcx, [rbp+4Fh+arg_20]; void *
0x18001e6b1  call    memcpy_0
0x18001e6b6  add     [rbp+4Fh+arg_20], r13
0x18001e6ba  mov     r13, [rbp+4Fh+arg_20]
0x18001e6be  mov     eax, esi
0x18001e6c0  add     rbx, rax
0x18001e6c3  jmp     loc_18001E601
0x18001e6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6cf  lea     rbx, WPP_GLOBAL_Control
0x18001e6d6  cmp     rcx, rbx
0x18001e6d9  jz      short loc_18001E749
0x18001e6db  test    [rcx+1Ch], r14b
0x18001e6df  jz      short loc_18001E749
0x18001e6e1  mov     eax, dword ptr [rbp+4Fh+var_68.Information]
0x18001e6e4  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001e6eb  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001e6ef  mov     edx, 1Ah
0x18001e6f4  mov     rcx, [rcx+10h]
0x18001e6f8  mov     dword ptr [rsp+0D0h+Buffer], r12d
0x18001e6fd  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x18001e701  call    WPP_SF_iDD
0x18001e706  jmp     short loc_18001E73D
0x18001e708  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e70f  lea     rbx, WPP_GLOBAL_Control
0x18001e716  cmp     rcx, rbx
0x18001e719  jz      short loc_18001E749
0x18001e71b  test    [rcx+1Ch], r14b
0x18001e71f  jz      short loc_18001E749
0x18001e721  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001e725  mov     edx, 19h
0x18001e72a  mov     rcx, [rcx+10h]
0x18001e72e  mov     dword ptr [rsp+0D0h+Buffer], r12d
0x18001e733  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001e738  call    WPP_SF_DiD
0x18001e73d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e744  mov     edx, 0C0000000h
0x18001e749  mov     r10, [r15+198h]
0x18001e750  test    r10, r10
0x18001e753  jz      short loc_18001E7AB
0x18001e755  mov     r9d, [r15+60h]
0x18001e759  mov     rcx, r10; this
0x18001e75c  mov     eax, r9d
0x18001e75f  mov     dword ptr [rsp+0D0h+Buffer], r12d
0x18001e764  and     eax, edx
0x18001e766  cmp     eax, edx
0x18001e768  jnz     short loc_18001E786
0x18001e76a  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001e76e  lea     r8, aXI64xX; "%x%I64x%x"
0x18001e775  mov     edx, 69A4h; unsigned int
0x18001e77a  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001e77f  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001e784  jmp     short loc_18001E7A4
0x18001e786  mov     rax, [rbp+4Fh+var_68.Information]
0x18001e78a  lea     r8, aI64dXX; "%I64d%x%x"
0x18001e791  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001e795  mov     edx, 69A5h; unsigned int
0x18001e79a  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001e79f  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001e7a4  mov     rcx, cs:WPP_GLOBAL_Control; this
0x18001e7ab  cmp     byte ptr [r15+1A0h], 0
0x18001e7b3  jz      short loc_18001E7F8
0x18001e7b5  mov     r9d, [r15+60h]
0x18001e7b9  mov     edx, r9d; int
0x18001e7bc  call    ?IsDiskDisappearedException@IO_DP_DRIVE@@QEAAEJ@Z; IO_DP_DRIVE::IsDiskDisappearedException(long)
0x18001e7c1  test    al, al
0x18001e7c3  jz      short loc_18001E7F8
0x18001e7c5  cmp     rcx, rbx
0x18001e7c8  jz      short loc_18001E7E5
0x18001e7ca  test    [rcx+1Ch], r14b
0x18001e7ce  jz      short loc_18001E7E5
0x18001e7d0  mov     rcx, [rcx+10h]
0x18001e7d4  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001e7db  mov     edx, 1Bh
0x18001e7e0  call    WPP_SF_d
0x18001e7e5  mov     ecx, [r15+60h]; dwExceptionCode
0x18001e7e9  xor     r9d, r9d; lpArguments
0x18001e7ec  xor     r8d, r8d; nNumberOfArguments
0x18001e7ef  mov     edx, r14d; dwExceptionFlags
0x18001e7f2  call    cs:__imp_RaiseException
0x18001e7f8  xor     r14b, r14b
0x18001e7fb  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e7ff  call    ??1HMEM@@UEAA@XZ; HMEM::~HMEM(void)
0x18001e804  mov     rbx, [rsp+0D0h+arg_0]
0x18001e80c  mov     al, r14b
0x18001e80f  add     rsp, 0A0h
0x18001e816  pop     r15
0x18001e818  pop     r14
0x18001e81a  pop     r13
0x18001e81c  pop     r12
0x18001e81e  pop     rdi
0x18001e81f  pop     rsi
0x18001e820  pop     rbp
0x18001e821  retn
```
