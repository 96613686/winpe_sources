# IO_DP_DRIVE::HardWrite(BIG_INT,ulong,void *,uchar)

- ea: `0x18001e828`
- end: `0x18001ed9a`
- name: `?HardWrite@IO_DP_DRIVE@@QEAAEVBIG_INT@@KPEAXE@Z`
- size: `1394`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, loader_planting`

## callers

- `0x18007e1fc`
- `0x1800809b0`
- `0x180081040`
- `0x180081240`

## callees

- `0x180004ab0`
- `0x18001e828`
- `0x18001eda0`
- `0x1800251f6`
- `0x180028568`
- `0x1800620e0`
- `0x180069f58`
- `0x18007a2d4`
- `0x18007a4e0`
- `0x18007a554`
- `0x18007d1d0`
- `0x180081702`
- `0x180088010`

## import_xrefs

- `ntdll!NtReadFile` at `0x18001ea56`
- `ntdll!NtReadFile` at `0x18001ea56`
- `ntdll!NtWriteFile` at `0x18001e9d0`
- `ntdll!NtWriteFile` at `0x18001e9d0`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ebe8`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ec2e`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ed87`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ebe8`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ec2e`
- `ntdll!RtlSetLastWin32ErrorAndNtStatusFromNtStatus` at `0x18001ed87`

## pseudocode

```c
char __fastcall IO_DP_DRIVE::HardWrite(__int64 a1, signed __int64 a2, unsigned int a3, char *a4, char a5)
{
  __int64 v5; // rdi
  signed __int64 v6; // rbx
  char v8; // r12
  unsigned int v9; // r14d
  unsigned int v10; // r15d
  unsigned int v11; // r13d
  PVOID v12; // r9
  signed __int64 v13; // rdi
  union _LARGE_INTEGER v14; // rdx
  size_t Length; // r14
  PVOID Buffer; // rax
  NTSTATUS v17; // eax
  unsigned int v18; // eax
  __int64 v19; // r8
  MESSAGE *v20; // rcx
  MESSAGE *v21; // rcx
  __int64 v22; // r8
  MESSAGE *v23; // r10
  int v24; // eax
  unsigned int v25; // ecx
  unsigned int v27; // [rsp+50h] [rbp-31h]
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-29h] BYREF
  PVOID v29; // [rsp+60h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v31[2]; // [rsp+78h] [rbp-9h] BYREF
  int v32; // [rsp+88h] [rbp+7h]
  PVOID Buf1[2]; // [rsp+90h] [rbp+Fh]
  char v34; // [rsp+F0h] [rbp+6Fh]
  char *Src; // [rsp+F8h] [rbp+77h]

  Src = a4;
  v5 = a3;
  v31[0] = &HMEM::`vftable';
  v31[1] = HMEM_cd;
  v6 = a2;
  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  v32 = 0;
  *(_OWORD *)Buf1 = 0;
  v8 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_iD(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids, a2, a3);
    LODWORD(a4) = (_DWORD)Src;
  }
  if ( (_DWORD)v5 )
  {
    v34 = 0;
    if ( (*(_DWORD *)(a1 + 348) & (unsigned int)a4) != 0 )
    {
      v34 = 1;
      HMEM::Destroy((HMEM *)v31);
    }
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
    v27 = v9;
    v10 = 0x10000000 / v9;
    if ( (unsigned int)v5 <= 0x10000000 / v9 )
    {
      v10 = v5;
    }
    else if ( !(0x10000000 / v9) )
    {
      v10 = 1;
    }
    while ( 1 )
    {
      v11 = v9 * v10;
      if ( HMEM::Acquire((HMEM *)v31, v9 * v10, *(_DWORD *)(a1 + 348)) || v11 <= 0x40000 || v10 < 2 )
        break;
      v10 >>= 1;
    }
    v12 = Buf1[1];
    if ( Buf1[1] )
    {
      v13 = v6 + v5;
      while ( 1 )
      {
        if ( v6 >= v13 )
          goto LABEL_68;
        v14.QuadPart = v6 * (int)v9;
        if ( v6 + v10 > v13 )
          v10 = v13 - v6;
        Length = v10 * v9;
        ByteOffset = v14;
        if ( v34 )
        {
          v29 = v12;
          memcpy_0(v12, Src, (unsigned int)Length);
          Buffer = v29;
        }
        else
        {
          Buffer = Src;
        }
        v17 = NtWriteFile(*(HANDLE *)(a1 + 64), 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
        *(_DWORD *)(a1 + 96) = v17;
        if ( v17 == -1073741801 )
        {
          if ( v10 == 1 )
            break;
          v10 >>= 1;
          v6 -= v10;
        }
        else
        {
          if ( (v17 & 0xC0000000) == 0xC0000000 )
          {
            RtlSetLastWin32ErrorAndNtStatusFromNtStatus(v17);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_DiD)(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                32,
                v22,
                *(unsigned int *)(a1 + 96),
                (union _LARGE_INTEGER)ByteOffset.QuadPart,
                Length);
            goto LABEL_57;
          }
          if ( IoStatusBlock.Information != Length )
          {
            RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741811);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDD)(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids,
                (union _LARGE_INTEGER)ByteOffset.QuadPart,
                IoStatusBlock.Information,
                Length);
LABEL_57:
            v23 = *(MESSAGE **)(a1 + 408);
            if ( v23 )
            {
              v24 = *(_DWORD *)(a1 + 464);
              if ( (v24 & 1) == 0
                || (v24 & 2) != 0
                && (v25 = *(_DWORD *)(a1 + 468), *(_DWORD *)(a1 + 468) = v25 + 1, v25 >= *(_DWORD *)(a1 + 472)) )
              {
                v8 = 0;
              }
              if ( (*(_DWORD *)(a1 + 96) & 0xC0000000) == 0xC0000000 )
              {
                MESSAGE::LogMsg(v23, 0x69A6u, "%x%I64x%x", *(_DWORD *)(a1 + 96), ByteOffset.QuadPart, Length);
                if ( v8 )
                  MESSAGE::DisplayMsg(
                    *(MESSAGE **)(a1 + 408),
                    0x69A6u,
                    "%x%I64x%x",
                    *(_DWORD *)(a1 + 96),
                    ByteOffset.QuadPart,
                    Length);
              }
              else
              {
                MESSAGE::LogMsg(
                  v23,
                  0x69A7u,
                  "%I64d%x%x",
                  ByteOffset.QuadPart,
                  LODWORD(IoStatusBlock.Information),
                  Length);
                if ( v8 )
                  MESSAGE::DisplayMsg(
                    *(MESSAGE **)(a1 + 408),
                    0x69A7u,
                    "%I64d%x%x",
                    ByteOffset.QuadPart,
                    LODWORD(IoStatusBlock.Information),
                    Length);
              }
            }
            goto LABEL_67;
          }
          if ( a5 )
          {
            if ( (unsigned int)Length > v11 )
              goto LABEL_67;
            v18 = NtReadFile(*(HANDLE *)(a1 + 64), 0, 0, 0, &IoStatusBlock, Buf1[1], Length, &ByteOffset, 0);
            *(_DWORD *)(a1 + 96) = v18;
            if ( (v18 & 0xC0000000) == 0xC0000000 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD))WPP_SF_DiD)(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  34,
                  v19,
                  v18,
                  (union _LARGE_INTEGER)ByteOffset.QuadPart,
                  Length);
LABEL_47:
              v21 = *(MESSAGE **)(a1 + 408);
              if ( v21 )
              {
                if ( (*(_DWORD *)(a1 + 96) & 0xC0000000) == 0xC0000000 )
                  MESSAGE::LogMsg(v21, 0x69A6u, "%x%I64x%x", *(_DWORD *)(a1 + 96), ByteOffset.QuadPart, Length);
                else
                  MESSAGE::LogMsg(
                    v21,
                    0x69A7u,
                    "%I64x%x%x",
                    ByteOffset.QuadPart,
                    LODWORD(IoStatusBlock.Information),
                    Length);
              }
LABEL_67:
              v8 = 0;
              goto LABEL_68;
            }
            if ( IoStatusBlock.Information != Length )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_iDD)(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  35,
                  &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids,
                  (union _LARGE_INTEGER)ByteOffset.QuadPart,
                  IoStatusBlock.Information,
                  Length);
              goto LABEL_47;
            }
            if ( memcmp_0(Buf1[1], Src, Length) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids);
              v20 = *(MESSAGE **)(a1 + 408);
              if ( v20 )
                MESSAGE::LogMsg(v20, 0x69A8u, "%I64x%x", ByteOffset.QuadPart, Length);
              goto LABEL_67;
            }
          }
          Src += Length;
        }
        v12 = Buf1[1];
        v9 = v27;
        v6 += v10;
      }
    }
    RtlSetLastWin32ErrorAndNtStatusFromNtStatus(-1073741811);
    HMEM::~HMEM((HMEM *)v31);
    return 0;
  }
  else
  {
LABEL_68:
    HMEM::~HMEM((HMEM *)v31);
    return v8;
  }
}

```

## disassembly

```asm
0x18001e828  mov     [rsp-8+arg_0], rbx
0x18001e82d  mov     [rsp-8+Src], r9
0x18001e832  push    rbp
0x18001e833  push    rsi
0x18001e834  push    rdi
0x18001e835  push    r12
0x18001e837  push    r13
0x18001e839  push    r14
0x18001e83b  push    r15
0x18001e83d  lea     rbp, [rsp-1Fh]
0x18001e842  sub     rsp, 0A0h
0x18001e849  lea     rax, ??_7HMEM@@6B@; const HMEM::`vftable'
0x18001e850  mov     edi, r8d
0x18001e853  xorps   xmm0, xmm0
0x18001e856  mov     [rbp+4Fh+var_58], rax
0x18001e85a  mov     rax, cs:?HMEM_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const HMEM_cd
0x18001e861  xor     r13d, r13d
0x18001e864  mov     [rbp+4Fh+var_50], rax
0x18001e868  mov     rbx, rdx
0x18001e86b  mov     rsi, rcx
0x18001e86e  mov     qword ptr [rbp+4Fh+var_78], r13
0x18001e872  movups  xmmword ptr [rbp+4Fh+var_68], xmm0
0x18001e876  mov     [rbp+4Fh+var_48], r13d
0x18001e87a  movdqu  xmmword ptr [rbp+4Fh+Buf1], xmm0
0x18001e87f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e886  lea     rax, WPP_GLOBAL_Control
0x18001e88d  lea     r12d, [r13+1]
0x18001e891  cmp     rcx, rax
0x18001e894  jz      short loc_18001E8BB
0x18001e896  test    [rcx+1Ch], r12b
0x18001e89a  jz      short loc_18001E8BB
0x18001e89c  mov     rcx, [rcx+10h]
0x18001e8a0  lea     edx, [r13+1Fh]
0x18001e8a4  mov     r9, rbx
0x18001e8a7  mov     dword ptr [rsp+0D0h+IoStatusBlock], edi
0x18001e8ab  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001e8b2  call    WPP_SF_iD
0x18001e8b7  mov     r9, [rbp+4Fh+Src]
0x18001e8bb  test    edi, edi
0x18001e8bd  jz      loc_18001ED5B
0x18001e8c3  mov     eax, [rsi+15Ch]
0x18001e8c9  mov     [rbp+4Fh+arg_10], r13b
0x18001e8cd  test    r9, rax
0x18001e8d0  jz      short loc_18001E8DF
0x18001e8d2  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e8d6  mov     [rbp+4Fh+arg_10], r12b
0x18001e8da  call    ?Destroy@HMEM@@AEAAXXZ; HMEM::Destroy(void)
0x18001e8df  mov     rax, [rsi]
0x18001e8e2  mov     rcx, rsi
0x18001e8e5  mov     rax, [rax+18h]
0x18001e8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ee  mov     r14d, eax
0x18001e8f1  mov     [rbp+4Fh+var_80], eax
0x18001e8f4  xor     edx, edx
0x18001e8f6  mov     eax, 10000000h
0x18001e8fb  div     r14d
0x18001e8fe  mov     r15d, eax
0x18001e901  cmp     edi, eax
0x18001e903  jbe     short loc_18001E90D
0x18001e905  test    eax, eax
0x18001e907  cmovz   r15d, r12d
0x18001e90b  jmp     short loc_18001E924
0x18001e90d  mov     r15d, edi
0x18001e910  jmp     short loc_18001E924
0x18001e912  cmp     r13d, 40000h
0x18001e919  jbe     short loc_18001E943
0x18001e91b  cmp     r15d, 2
0x18001e91f  jb      short loc_18001E943
0x18001e921  shr     r15d, 1
0x18001e924  mov     r8d, [rsi+15Ch]; unsigned int
0x18001e92b  lea     rcx, [rbp+4Fh+var_58]; this
0x18001e92f  mov     r13d, r15d
0x18001e932  imul    r13d, r14d
0x18001e936  mov     edx, r13d; unsigned int
0x18001e939  call    ?Acquire@HMEM@@UEAAPEAXKK@Z; HMEM::Acquire(ulong,ulong)
0x18001e93e  test    rax, rax
0x18001e941  jz      short loc_18001E912
0x18001e943  mov     r9, [rbp+4Fh+Buf1+8]
0x18001e947  test    r9, r9
0x18001e94a  jz      loc_18001ED82
0x18001e950  add     rdi, rbx
0x18001e953  cmp     rbx, rdi
0x18001e956  jge     loc_18001ED5B
0x18001e95c  movsxd  rdx, r14d
0x18001e95f  mov     ecx, r15d
0x18001e962  imul    rdx, rbx
0x18001e966  add     rcx, rbx
0x18001e969  cmp     rcx, rdi
0x18001e96c  jle     short loc_18001E974
0x18001e96e  mov     r15d, edi
0x18001e971  sub     r15d, ebx
0x18001e974  imul    r14d, r15d
0x18001e978  cmp     [rbp+4Fh+arg_10], 0
0x18001e97c  mov     qword ptr [rbp+4Fh+var_78], rdx
0x18001e980  jz      short loc_18001E99B
0x18001e982  mov     rdx, [rbp+4Fh+Src]; Src
0x18001e986  mov     r8d, r14d; Size
0x18001e989  mov     rcx, r9; void *
0x18001e98c  mov     [rbp+4Fh+var_70], r9
0x18001e990  call    memcpy_0
0x18001e995  mov     rax, [rbp+4Fh+var_70]
0x18001e999  jmp     short loc_18001E99F
0x18001e99b  mov     rax, [rbp+4Fh+Src]
0x18001e99f  mov     [rsp+0D0h+Key], 0; Key
0x18001e9a8  lea     rcx, [rbp+4Fh+var_78]
0x18001e9ac  mov     [rsp+0D0h+ByteOffset], rcx; ByteOffset
0x18001e9b1  xor     r9d, r9d; ApcContext
0x18001e9b4  mov     rcx, [rsi+40h]; FileHandle
0x18001e9b8  xor     r8d, r8d; ApcRoutine
0x18001e9bb  mov     [rsp+0D0h+Length], r14d; Length
0x18001e9c0  xor     edx, edx; Event
0x18001e9c2  mov     [rsp+0D0h+Buffer], rax; Buffer
0x18001e9c7  lea     rax, [rbp+4Fh+var_68]
0x18001e9cb  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18001e9d0  call    cs:__imp_NtWriteFile
0x18001e9d6  mov     [rsi+60h], eax
0x18001e9d9  mov     ecx, eax; Status
0x18001e9db  cmp     eax, 0C0000017h
0x18001e9e0  jnz     short loc_18001E9F9
0x18001e9e2  cmp     r15d, r12d
0x18001e9e5  jz      loc_18001ED82
0x18001e9eb  shr     r15d, 1
0x18001e9ee  mov     eax, r15d
0x18001e9f1  sub     rbx, rax
0x18001e9f4  jmp     loc_18001EA95
0x18001e9f9  mov     edx, 0C0000000h
0x18001e9fe  and     eax, edx
0x18001ea00  cmp     eax, edx
0x18001ea02  jz      loc_18001EC2E
0x18001ea08  cmp     [rbp+4Fh+var_68.Information], r14
0x18001ea0c  jnz     loc_18001EBE3
0x18001ea12  cmp     [rbp+4Fh+arg_20], 0
0x18001ea16  jz      short loc_18001EA91
0x18001ea18  cmp     r14d, r13d
0x18001ea1b  ja      loc_18001ED58
0x18001ea21  mov     rcx, [rsi+40h]; FileHandle
0x18001ea25  lea     rax, [rbp+4Fh+var_78]
0x18001ea29  mov     [rsp+0D0h+Key], 0; Key
0x18001ea32  xor     r9d, r9d; ApcContext
0x18001ea35  mov     [rsp+0D0h+ByteOffset], rax; ByteOffset
0x18001ea3a  xor     r8d, r8d; ApcRoutine
0x18001ea3d  mov     rax, [rbp+4Fh+Buf1+8]
0x18001ea41  xor     edx, edx; Event
0x18001ea43  mov     [rsp+0D0h+Length], r14d; Length
0x18001ea48  mov     [rsp+0D0h+Buffer], rax; Buffer
0x18001ea4d  lea     rax, [rbp+4Fh+var_68]
0x18001ea51  mov     [rsp+0D0h+IoStatusBlock], rax; IoStatusBlock
0x18001ea56  call    cs:__imp_NtReadFile
0x18001ea5c  mov     edx, 0C0000000h
0x18001ea61  mov     [rsi+60h], eax
0x18001ea64  mov     ecx, eax
0x18001ea66  mov     r9d, eax
0x18001ea69  and     ecx, edx
0x18001ea6b  cmp     ecx, edx
0x18001ea6d  jz      loc_18001EB45
0x18001ea73  cmp     [rbp+4Fh+var_68.Information], r14
0x18001ea77  jnz     loc_18001EB05
0x18001ea7d  mov     rdx, [rbp+4Fh+Src]; Buf2
0x18001ea81  mov     r8, r14; Size
0x18001ea84  mov     rcx, [rbp+4Fh+Buf1+8]; Buf1
0x18001ea88  call    memcmp_0
0x18001ea8d  test    eax, eax
0x18001ea8f  jnz     short loc_18001EAA8
0x18001ea91  add     [rbp+4Fh+Src], r14
0x18001ea95  mov     r9, [rbp+4Fh+Buf1+8]
0x18001ea99  mov     r14d, [rbp+4Fh+var_80]
0x18001ea9d  mov     eax, r15d
0x18001eaa0  add     rbx, rax
0x18001eaa3  jmp     loc_18001E953
0x18001eaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eaaf  lea     rax, WPP_GLOBAL_Control
0x18001eab6  cmp     rcx, rax
0x18001eab9  jz      short loc_18001EAD6
0x18001eabb  test    [rcx+1Ch], r12b
0x18001eabf  jz      short loc_18001EAD6
0x18001eac1  mov     rcx, [rcx+10h]
0x18001eac5  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001eacc  mov     edx, 24h ; '$'
0x18001ead1  call    WPP_SF_
0x18001ead6  mov     rcx, [rsi+198h]; this
0x18001eadd  test    rcx, rcx
0x18001eae0  jz      loc_18001ED58
0x18001eae6  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001eaea  lea     r8, aI64xX; "%I64x%x"
0x18001eaf1  mov     edx, 69A8h; unsigned int
0x18001eaf6  mov     dword ptr [rsp+0D0h+IoStatusBlock], r14d
0x18001eafb  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001eb00  jmp     loc_18001ED58
0x18001eb05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb0c  lea     rax, WPP_GLOBAL_Control
0x18001eb13  cmp     rcx, rax
0x18001eb16  jz      short loc_18001EB7F
0x18001eb18  test    [rcx+1Ch], r12b
0x18001eb1c  jz      short loc_18001EB7F
0x18001eb1e  mov     eax, dword ptr [rbp+4Fh+var_68.Information]
0x18001eb21  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001eb28  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001eb2c  mov     edx, 23h ; '#'
0x18001eb31  mov     rcx, [rcx+10h]
0x18001eb35  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001eb3a  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x18001eb3e  call    WPP_SF_iDD
0x18001eb43  jmp     short loc_18001EB7A
0x18001eb45  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb4c  lea     rax, WPP_GLOBAL_Control
0x18001eb53  cmp     rcx, rax
0x18001eb56  jz      short loc_18001EB7F
0x18001eb58  test    [rcx+1Ch], r12b
0x18001eb5c  jz      short loc_18001EB7F
0x18001eb5e  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001eb62  mov     edx, 22h ; '"'
0x18001eb67  mov     rcx, [rcx+10h]
0x18001eb6b  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001eb70  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001eb75  call    WPP_SF_DiD
0x18001eb7a  mov     edx, 0C0000000h
0x18001eb7f  mov     rcx, [rsi+198h]; this
0x18001eb86  test    rcx, rcx
0x18001eb89  jz      loc_18001ED58
0x18001eb8f  mov     r9d, [rsi+60h]
0x18001eb93  mov     eax, r9d
0x18001eb96  and     eax, edx
0x18001eb98  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001eb9d  cmp     eax, edx
0x18001eb9f  jnz     short loc_18001EBC0
0x18001eba1  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001eba5  lea     r8, aXI64xX; "%x%I64x%x"
0x18001ebac  mov     edx, 69A6h; unsigned int
0x18001ebb1  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001ebb6  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001ebbb  jmp     loc_18001ED58
0x18001ebc0  mov     rax, [rbp+4Fh+var_68.Information]
0x18001ebc4  lea     r8, aI64xXX; "%I64x%x%x"
0x18001ebcb  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001ebcf  mov     edx, 69A7h; unsigned int
0x18001ebd4  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001ebd9  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001ebde  jmp     loc_18001ED58
0x18001ebe3  mov     ecx, 0C000000Dh; Status
0x18001ebe8  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18001ebee  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ebf5  lea     rax, WPP_GLOBAL_Control
0x18001ebfc  cmp     rcx, rax
0x18001ebff  jz      short loc_18001EC6D
0x18001ec01  test    [rcx+1Ch], r12b
0x18001ec05  jz      short loc_18001EC6D
0x18001ec07  mov     eax, dword ptr [rbp+4Fh+var_68.Information]
0x18001ec0a  lea     r8, WPP_afc0f7a8c486397a4aa17ad3eb433f70_Traceguids
0x18001ec11  mov     r9, qword ptr [rbp+4Fh+var_78]
0x18001ec15  mov     edx, 21h ; '!'
0x18001ec1a  mov     rcx, [rcx+10h]
0x18001ec1e  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001ec23  mov     dword ptr [rsp+0D0h+IoStatusBlock], eax
0x18001ec27  call    WPP_SF_iDD
0x18001ec2c  jmp     short loc_18001EC6D
0x18001ec2e  call    cs:__imp_RtlSetLastWin32ErrorAndNtStatusFromNtStatus
0x18001ec34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec3b  lea     rax, WPP_GLOBAL_Control
0x18001ec42  cmp     rcx, rax
0x18001ec45  jz      short loc_18001EC6D
0x18001ec47  test    [rcx+1Ch], r12b
0x18001ec4b  jz      short loc_18001EC6D
0x18001ec4d  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001ec51  mov     edx, 20h ; ' '
0x18001ec56  mov     r9d, [rsi+60h]
0x18001ec5a  mov     rcx, [rcx+10h]
0x18001ec5e  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001ec63  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001ec68  call    WPP_SF_DiD
0x18001ec6d  mov     r10, [rsi+198h]
0x18001ec74  test    r10, r10
0x18001ec77  jz      loc_18001ED58
0x18001ec7d  mov     eax, [rsi+1D0h]
0x18001ec83  test    r12b, al
0x18001ec86  jz      short loc_18001ECA3
0x18001ec88  test    al, 2
0x18001ec8a  jz      short loc_18001ECA6
0x18001ec8c  mov     ecx, [rsi+1D4h]
0x18001ec92  lea     eax, [rcx+1]
0x18001ec95  mov     [rsi+1D4h], eax
0x18001ec9b  cmp     ecx, [rsi+1D8h]
0x18001eca1  jb      short loc_18001ECA6
0x18001eca3  xor     r12b, r12b
0x18001eca6  mov     r9d, [rsi+60h]
0x18001ecaa  mov     ecx, 0C0000000h
0x18001ecaf  mov     eax, r9d
0x18001ecb2  mov     dword ptr [rsp+0D0h+Buffer], r14d
0x18001ecb7  and     eax, ecx
0x18001ecb9  cmp     eax, ecx
0x18001ecbb  mov     rcx, r10; this
0x18001ecbe  jnz     short loc_18001ED0B
0x18001ecc0  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001ecc4  lea     r8, aXI64xX; "%x%I64x%x"
0x18001eccb  mov     edx, 69A6h; unsigned int
0x18001ecd0  mov     [rsp+0D0h+IoStatusBlock], rax
0x18001ecd5  call    ?LogMsg@MESSAGE@@QEAAEKPEBDZZ; MESSAGE::LogMsg(ulong,char const *,...)
0x18001ecda  test    r12b, r12b
0x18001ecdd  jz      short loc_18001ED58
0x18001ecdf  mov     rax, qword ptr [rbp+4Fh+var_78]
0x18001ece3  lea     r8, aXI64xX; "%x%I64x%x"
  ... truncated ...
```
