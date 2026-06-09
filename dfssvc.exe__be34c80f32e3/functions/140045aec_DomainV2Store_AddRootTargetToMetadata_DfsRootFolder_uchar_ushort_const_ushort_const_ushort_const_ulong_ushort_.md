# DomainV2Store::AddRootTargetToMetadata(DfsRootFolder *,uchar,ushort const *,ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x140045aec`
- end: `0x140045de6`
- name: `?AddRootTargetToMetadata@DomainV2Store@@AEAAKPEAVDfsRootFolder@@EPEBG11K1@Z`
- size: `762`
- prototype: `unsigned int __usercall@<eax>(DomainV2Store *__hidden this@<rcx>, struct DfsRootFolder *@<rdx>, unsigned __int8@<r8b>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting`

## callers

- `0x140045478`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x140005b90`
- `0x14000aed8`
- `0x14000f784`
- `0x14000f808`
- `0x1400364d4`
- `0x140045aec`
- `0x140047d9c`
- `0x1400586a8`
- `0x140058a38`
- `0x14005ce3a`
- `0x14005ce70`
- `0x14005e010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140045ca0`
- `ntdll!RtlInitUnicodeStringEx` at `0x140045ca0`
- `ntdll!RtlNtStatusToDosError` at `0x140045cae`
- `ntdll!RtlNtStatusToDosError` at `0x140045cae`
- `RPCRT4!UuidCreate` at `0x140045ba0`
- `RPCRT4!UuidCreate` at `0x140045ba0`

## pseudocode

```c
__int64 __fastcall DomainV2Store::AddRootTargetToMetadata(
        DomainV2Store *this,
        struct DfsRootFolder *a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        const unsigned __int16 *a6,
        unsigned int a7,
        unsigned __int16 *a8)
{
  WCHAR *v12; // rsi
  unsigned int inited; // ebx
  __int64 v14; // r8
  DomainV2Store *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  int v20; // eax
  unsigned int ErrorFromHr; // eax
  NTSTATUS v22; // eax
  DfsStore *v23; // rcx
  DfsStore *v24; // rcx
  unsigned __int8 v26[8]; // [rsp+30h] [rbp-D0h] BYREF
  void *v27; // [rsp+38h] [rbp-C8h] BYREF
  const unsigned __int16 *v28; // [rsp+40h] [rbp-C0h]
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v31; // [rsp+68h] [rbp-98h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  _BYTE v33[64]; // [rsp+80h] [rbp-80h] BYREF
  UUID Uuid; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[68]; // [rsp+D0h] [rbp-30h] BYREF
  int v36; // [rsp+114h] [rbp+14h]
  unsigned int v37; // [rsp+158h] [rbp+58h]
  int v38; // [rsp+15Ch] [rbp+5Ch]

  v28 = a6;
  v26[0] = a3;
  v32 = 0;
  v31 = 0;
  memset_0(v33, 0, sizeof(v33));
  memset_0(v35, 0, 0x98u);
  v27 = 0;
  DestinationString = 0;
  v12 = 0;
  v30 = 0;
  Uuid = 0;
  inited = DfsRtlInitUnicodeStringEx(&v30, 0);
  if ( !inited )
  {
    inited = UuidCreate(&Uuid);
    if ( !inited )
    {
      inited = (*(__int64 (__fastcall **)(struct DfsRootFolder *, void **))(*(_QWORD *)a2 + 56LL))(a2, &v27);
      if ( !inited )
      {
        if ( a3 )
          goto LABEL_8;
        LOBYTE(v14) = 1;
        inited = (*(__int64 (__fastcall **)(struct DfsRootFolder *, __int64, __int64))(*(_QWORD *)a2 + 32LL))(
                   a2,
                   1,
                   v14);
        if ( inited )
          goto LABEL_20;
        inited = DomainV2Store::RootEntryExists(v15, v27, v26);
        if ( inited )
          goto LABEL_20;
        if ( v26[0] )
        {
LABEL_8:
          v16 = -1;
          do
            ++v16;
          while ( a5[v16] );
          v17 = -1;
          do
            ++v17;
          while ( a4[v17] );
          v18 = v16 + v17 + 4;
          v19 = (unsigned __int16 *)operator new(saturated_mul(v18, 2u));
          v12 = v19;
          if ( !v19 )
          {
            inited = 8;
LABEL_20:
            (*(void (__fastcall **)(struct DfsRootFolder *, void *))(*(_QWORD *)a2 + 64LL))(a2, v27);
            goto LABEL_21;
          }
          v20 = StringCchPrintfW(v19, v18, L"\\\\%s\\%s", a4, a5);
          if ( v20 >= 0 )
          {
            v22 = RtlInitUnicodeStringEx(&DestinationString, v12);
            inited = RtlNtStatusToDosError(v22);
            if ( inited )
              goto LABEL_20;
            DfsStore::StoreInitializeNameInformation(
              v23,
              (struct _DFS_NAME_INFORMATION_ *)v35,
              &DestinationString,
              &Uuid,
              a8);
            v36 |= 0x80u;
            v37 = a7;
            v38 = 0;
            DfsStore::StoreInitializeReplicaInformation(
              v24,
              (struct _DFS_REPLICA_LIST_INFORMATION_ *)&v31,
              (struct _DFS_REPLICA_INFORMATION__ *)v33,
              a4,
              a5);
            ErrorFromHr = (*(__int64 (__fastcall **)(DomainV2Store *, void *, _BYTE *, __int128 *, __int128 *))(*(_QWORD *)this + 24LL))(
                            this,
                            v27,
                            v35,
                            &v31,
                            &v30);
          }
          else
          {
            ErrorFromHr = DfsGetErrorFromHr(v20);
          }
        }
        else
        {
          ErrorFromHr = DfsStore::AddChildReplica(this, (unsigned __int64)v27, 0, a4, a5);
        }
        inited = ErrorFromHr;
        goto LABEL_20;
      }
    }
  }
LABEL_21:
  operator delete(v12);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (((1 << (inited != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_SD(
      *((_QWORD *)pWppControl + 2),
      28,
      (unsigned int)WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids,
      (_DWORD)v28,
      inited);
  }
  return inited;
}

```

## disassembly

```asm
0x140045aec  push    rbp
0x140045aee  push    rbx
0x140045aef  push    rsi
0x140045af0  push    rdi
0x140045af1  push    r12
0x140045af3  push    r13
0x140045af5  push    r14
0x140045af7  push    r15
0x140045af9  lea     rbp, [rsp-88h]
0x140045b01  sub     rsp, 188h
0x140045b08  mov     rax, cs:__security_cookie
0x140045b0f  xor     rax, rsp
0x140045b12  mov     [rbp+0C0h+var_50], rax
0x140045b16  mov     rax, [rbp+0C0h+arg_28]
0x140045b1d  mov     r14b, r8b
0x140045b20  mov     r15, [rbp+0C0h+arg_20]
0x140045b27  mov     rdi, rdx
0x140045b2a  mov     [rsp+1C0h+var_180], rax
0x140045b2f  mov     r13, rcx
0x140045b32  xor     eax, eax
0x140045b34  mov     [rsp+1C0h+var_190], r8b
0x140045b39  xorps   xmm0, xmm0
0x140045b3c  mov     [rsp+1C0h+var_148], rax
0x140045b41  xor     edx, edx; Val
0x140045b43  lea     rcx, [rbp+0C0h+var_140]; void *
0x140045b47  mov     r12, r9
0x140045b4a  lea     r8d, [rax+40h]; Size
0x140045b4e  movups  [rsp+1C0h+var_158], xmm0
0x140045b53  call    memset_0
0x140045b58  xor     edx, edx; Val
0x140045b5a  lea     rcx, [rbp+0C0h+var_F0]; void *
0x140045b5e  mov     r8d, 98h; Size
0x140045b64  call    memset_0
0x140045b69  xorps   xmm0, xmm0
0x140045b6c  lea     rcx, [rsp+1C0h+var_168]
0x140045b71  xor     eax, eax
0x140045b73  xorps   xmm1, xmm1
0x140045b76  xor     edx, edx
0x140045b78  mov     [rsp+1C0h+var_188], rax
0x140045b7d  movups  xmmword ptr [rsp+1C0h+DestinationString.Length], xmm0
0x140045b82  mov     esi, eax
0x140045b84  movups  [rsp+1C0h+var_168], xmm1
0x140045b89  movups  xmmword ptr [rbp+0C0h+Uuid.Data1], xmm0
0x140045b8d  call    DfsRtlInitUnicodeStringEx
0x140045b92  mov     ebx, eax
0x140045b94  test    eax, eax
0x140045b96  jnz     loc_140045D62
0x140045b9c  lea     rcx, [rbp+0C0h+Uuid]; Uuid
0x140045ba0  call    cs:__imp_UuidCreate
0x140045ba7  nop     dword ptr [rax+rax+00h]
0x140045bac  mov     ebx, eax
0x140045bae  test    eax, eax
0x140045bb0  jnz     loc_140045D62
0x140045bb6  mov     rax, [rdi]
0x140045bb9  lea     rdx, [rsp+1C0h+var_188]
0x140045bbe  mov     rcx, rdi
0x140045bc1  mov     rax, [rax+38h]
0x140045bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bca  mov     ebx, eax
0x140045bcc  test    eax, eax
0x140045bce  jnz     loc_140045D62
0x140045bd4  test    r14b, r14b
0x140045bd7  jnz     short loc_140045C22
0x140045bd9  mov     rax, [rdi]
0x140045bdc  lea     edx, [rsi+1]
0x140045bdf  mov     r9b, 1
0x140045be2  mov     rcx, rdi
0x140045be5  mov     r8b, r9b
0x140045be8  mov     rax, [rax+20h]
0x140045bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bf1  mov     ebx, eax
0x140045bf3  test    eax, eax
0x140045bf5  jnz     loc_140045D4E
0x140045bfb  mov     rdx, [rsp+1C0h+var_188]; void *
0x140045c00  lea     r8, [rsp+1C0h+var_190]; unsigned __int8 *
0x140045c05  call    ?RootEntryExists@DomainV2Store@@AEAAKPEAXPEAE@Z; DomainV2Store::RootEntryExists(void *,uchar *)
0x140045c0a  mov     ebx, eax
0x140045c0c  test    eax, eax
0x140045c0e  jnz     loc_140045D4E
0x140045c14  mov     r14b, [rsp+1C0h+var_190]
0x140045c19  test    r14b, r14b
0x140045c1c  jz      loc_140045D34
0x140045c22  or      r8, 0FFFFFFFFFFFFFFFFh
0x140045c26  mov     rax, r8
0x140045c29  xor     r14d, r14d
0x140045c2c  inc     rax
0x140045c2f  cmp     [r15+rax*2], r14w
0x140045c34  jnz     short loc_140045C2C
0x140045c36  mov     rcx, r8
0x140045c39  inc     rcx
0x140045c3c  cmp     [r12+rcx*2], r14w
0x140045c41  jnz     short loc_140045C39
0x140045c43  lea     rbx, [rcx+4]
0x140045c47  add     rbx, rax
0x140045c4a  mov     eax, 2
0x140045c4f  mul     rbx
0x140045c52  cmovo   rax, r8
0x140045c56  mov     rcx, rax; Size
0x140045c59  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140045c5e  mov     rsi, rax
0x140045c61  test    rax, rax
0x140045c64  jnz     short loc_140045C6E
0x140045c66  lea     ebx, [rax+8]
0x140045c69  jmp     loc_140045D4E
0x140045c6e  mov     r9, r12
0x140045c71  mov     [rsp+1C0h+var_1A0], r15
0x140045c76  lea     r8, aSS_3; "\\\\%s\\%s"
0x140045c7d  mov     rdx, rbx; unsigned __int64
0x140045c80  mov     rcx, rsi; unsigned __int16 *
0x140045c83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140045c88  test    eax, eax
0x140045c8a  jns     short loc_140045C98
0x140045c8c  mov     ecx, eax; int
0x140045c8e  call    ?DfsGetErrorFromHr@@YAKJ@Z; DfsGetErrorFromHr(long)
0x140045c93  jmp     loc_140045D4C
0x140045c98  mov     rdx, rsi; SourceString
0x140045c9b  lea     rcx, [rsp+1C0h+DestinationString]; DestinationString
0x140045ca0  call    cs:__imp_RtlInitUnicodeStringEx
0x140045ca7  nop     dword ptr [rax+rax+00h]
0x140045cac  mov     ecx, eax; Status
0x140045cae  call    cs:__imp_RtlNtStatusToDosError
0x140045cb5  nop     dword ptr [rax+rax+00h]
0x140045cba  mov     ebx, eax
0x140045cbc  test    eax, eax
0x140045cbe  jnz     loc_140045D4E
0x140045cc4  mov     rax, [rbp+0C0h+arg_38]
0x140045ccb  lea     r9, [rbp+0C0h+Uuid]; struct _GUID *
0x140045ccf  lea     r8, [rsp+1C0h+DestinationString]; struct _UNICODE_STRING *
0x140045cd4  mov     [rsp+1C0h+var_1A0], rax; unsigned __int16 *
0x140045cd9  lea     rdx, [rbp+0C0h+var_F0]; struct _DFS_NAME_INFORMATION_ *
0x140045cdd  call    ?StoreInitializeNameInformation@DfsStore@@QEAAKPEAU_DFS_NAME_INFORMATION_@@PEAU_UNICODE_STRING@@PEAU_GUID@@PEBG@Z; DfsStore::StoreInitializeNameInformation(_DFS_NAME_INFORMATION_ *,_UNICODE_STRING *,_GUID *,ushort const *)
0x140045ce2  mov     eax, [rbp+0C0h+arg_30]
0x140045ce8  lea     r8, [rbp+0C0h+var_140]; struct _DFS_REPLICA_INFORMATION__ *
0x140045cec  bts     [rbp+0C0h+var_AC], 7
0x140045cf1  lea     rdx, [rsp+1C0h+var_158]; struct _DFS_REPLICA_LIST_INFORMATION_ *
0x140045cf6  mov     r9, r12; unsigned __int16 *
0x140045cf9  mov     [rbp+0C0h+var_68], eax
0x140045cfc  mov     [rbp+0C0h+var_64], r14d
0x140045d00  mov     [rsp+1C0h+var_1A0], r15; unsigned __int16 *
0x140045d05  call    ?StoreInitializeReplicaInformation@DfsStore@@QEAAKPEAU_DFS_REPLICA_LIST_INFORMATION_@@PEAU_DFS_REPLICA_INFORMATION__@@PEBG2@Z; DfsStore::StoreInitializeReplicaInformation(_DFS_REPLICA_LIST_INFORMATION_ *,_DFS_REPLICA_INFORMATION__ *,ushort const *,ushort const *)
0x140045d0a  mov     rax, [r13+0]
0x140045d0e  lea     rcx, [rsp+1C0h+var_168]
0x140045d13  mov     rdx, [rsp+1C0h+var_188]
0x140045d18  lea     r9, [rsp+1C0h+var_158]
0x140045d1d  mov     [rsp+1C0h+var_1A0], rcx
0x140045d22  lea     r8, [rbp+0C0h+var_F0]
0x140045d26  mov     rcx, r13
0x140045d29  mov     rax, [rax+18h]
0x140045d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d32  jmp     short loc_140045D4C
0x140045d34  mov     rdx, [rsp+1C0h+var_188]; unsigned __int64
0x140045d39  mov     r9, r12; unsigned __int16 *
0x140045d3c  xor     r8d, r8d; unsigned __int16 *
0x140045d3f  mov     [rsp+1C0h+var_1A0], r15; unsigned __int16 *
0x140045d44  mov     rcx, r13; this
0x140045d47  call    ?AddChildReplica@DfsStore@@QEAAK_KPEBG11@Z; DfsStore::AddChildReplica(unsigned __int64,ushort const *,ushort const *,ushort const *)
0x140045d4c  mov     ebx, eax
0x140045d4e  mov     rax, [rdi]
0x140045d51  mov     rcx, rdi
0x140045d54  mov     rdx, [rsp+1C0h+var_188]
0x140045d59  mov     rax, [rax+40h]
0x140045d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045d62  mov     rcx, rsi; Block
0x140045d65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140045d6a  lea     rax, WPP_GLOBAL_Control
0x140045d71  cmp     cs:WPP_GLOBAL_Control, rax
0x140045d78  jz      short loc_140045DC3
0x140045d7a  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140045d81  test    rcx, rcx
0x140045d84  jz      short loc_140045DC3
0x140045d86  mov     eax, ebx
0x140045d88  neg     eax
0x140045d8a  mov     eax, 20h ; ' '
0x140045d8f  sbb     edx, edx
0x140045d91  and     edx, 0FFFFFFECh
0x140045d94  add     edx, 1Fh
0x140045d97  bts     eax, edx
0x140045d9a  test    [rcx+1Ch], eax
0x140045d9d  jz      short loc_140045DC3
0x140045d9f  cmp     byte ptr [rcx+19h], 3
0x140045da3  jb      short loc_140045DC3
0x140045da5  mov     r9, [rsp+1C0h+var_180]
0x140045daa  lea     r8, WPP_e9fa81dc5692377a3a30be063b7737c1_Traceguids
0x140045db1  mov     rcx, [rcx+10h]
0x140045db5  mov     edx, 1Ch
0x140045dba  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x140045dbe  call    WPP_SF_SD
0x140045dc3  mov     eax, ebx
0x140045dc5  mov     rcx, [rbp+0C0h+var_50]
0x140045dc9  xor     rcx, rsp; StackCookie
0x140045dcc  call    __security_check_cookie
0x140045dd1  add     rsp, 188h
0x140045dd8  pop     r15
0x140045dda  pop     r14
0x140045ddc  pop     r13
0x140045dde  pop     r12
0x140045de0  pop     rdi
0x140045de1  pop     rsi
0x140045de2  pop     rbx
0x140045de3  pop     rbp
0x140045de4  retn
```
