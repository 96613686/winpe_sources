# ndisInvokeNextSendHandler(_NET_BUFFER_LIST *,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong))

- ea: `0x140010b10`
- end: `0x140011148`
- name: `?ndisInvokeNextSendHandler@@YAXPEAU_NET_BUFFER_LIST@@KKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KK@Z@Z`
- size: `1592`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000eb70`
- `0x140010300`
- `0x140057760`
- `0x140058d60`

## callees

- `0x140004890`
- `0x140010b10`
- `0x14002c970`
- `0x14002c9d0`
- `0x14002de40`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140010b6c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140010b6c`
- `ntoskrnl!IoGetStackLimits` at `0x140010da5`
- `ntoskrnl!IoGetStackLimits` at `0x140010da5`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140010e6c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140010e6c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010f44`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140010f44`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010fa0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140010fa0`

## pseudocode

```c
void __fastcall ndisInvokeNextSendHandler(
        struct _NET_BUFFER_LIST *a1,
        unsigned int a2,
        __int64 a3,
        struct _NDIS_OBJECT_HEADER *a4,
        void *a5,
        void (*a6)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))
{
  __int64 v6; // rax
  struct _NDIS_OBJECT_HEADER *v7; // rbx
  unsigned int v8; // esi
  __int64 *v11; // r15
  void (*v12)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int); // r13
  void *v13; // r10
  __int64 v14; // rsi
  __int64 v15; // rdi
  struct _NDIS_OBJECT_HEADER *v16; // r14
  __int64 v17; // rsi
  unsigned int v18; // r14d
  unsigned int v19; // ecx
  __int64 v20; // rdi
  __int64 v21; // rdi
  unsigned int v22; // r15d
  unsigned int v23; // ecx
  __int64 v24; // r14
  void *v25; // r14
  unsigned int v26; // ecx
  unsigned int v27; // edx
  __int64 v28; // r15
  unsigned __int64 v29; // r13
  unsigned int v30; // r12d
  __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // r8
  __int64 v34; // rdx
  int v35; // ecx
  int v36; // r8d
  struct _NET_BUFFER_LIST *i; // rax
  __int64 v38; // rax
  bool v39; // zf
  __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // r8
  __int64 v45; // rdx
  __int64 v46; // rdx
  void *v47; // [rsp+40h] [rbp-79h]
  struct _NDIS_OBJECT_HEADER v48; // [rsp+40h] [rbp-79h]
  unsigned int v49; // [rsp+48h] [rbp-71h]
  unsigned __int64 LowLimit; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int64 HighLimit; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-59h]
  __int128 Parameter; // [rsp+68h] [rbp-51h] BYREF
  __int128 v54; // [rsp+78h] [rbp-41h]
  __int64 v55; // [rsp+88h] [rbp-31h]
  unsigned int v56; // [rsp+90h] [rbp-29h]
  int v57; // [rsp+94h] [rbp-25h]
  __int64 v58; // [rsp+98h] [rbp-21h]
  _QWORD v59[12]; // [rsp+A0h] [rbp-19h] BYREF
  _UNKNOWN *retaddr; // [rsp+108h] [rbp+4Fh] BYREF
  unsigned int v61; // [rsp+128h] [rbp+6Fh]
  unsigned int v62; // [rsp+128h] [rbp+6Fh]
  unsigned int v63; // [rsp+128h] [rbp+6Fh]

  v7 = a4;
  v8 = a3;
  if ( a4->Type == 17 )
  {
LABEL_2:
    ((void (__fastcall *)(void *, struct _NET_BUFFER_LIST *, _QWORD, _QWORD))a6)(a5, a1, a2, v8);
    return;
  }
  if ( (a3 & 1) != 0 || KeGetCurrentIrql() == 2 )
  {
    LODWORD(v6) = KeGetPcr()->Prcb.Number;
    v11 = v59;
    v12 = a6;
    v13 = a5;
    v52 = v6;
    v59[2] = 0;
    a1->Scratch = 0;
    v59[0] = a1;
    v59[1] = a1;
    a1->ChildRefCount = v8;
    a1->Status = a2;
    while ( 1 )
    {
      v47 = v13;
      if ( v7->Type != 5 )
        break;
      v14 = *v11;
      if ( !*v11 )
        break;
      v15 = *(_QWORD *)&v7[106].Type + 96 * v6;
      v58 = v15;
      if ( *(_BYTE *)(v15 + 16) )
      {
        *v11 = 0;
        do
        {
          v18 = *(_DWORD *)(v14 + 132);
          v19 = *(_DWORD *)(v14 + 140);
          v20 = *(_QWORD *)(v14 + 112);
          *(_DWORD *)(v14 + 132) = 0;
          v61 = v19;
          if ( byte_14011D730 )
          {
            if ( v7->Type == 5 )
            {
              v43 = *(_QWORD *)&v7[228].Type;
              if ( v43 )
              {
                if ( (*(_DWORD *)(v43 + 56) & 1) != 0 )
                {
                  PktMonClientNblLogNdis(&v7[222], v14, a3, 2);
                  v13 = v47;
                  v19 = v61;
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && v7->Type == 5 && (v46 = *(_QWORD *)&v7[194].Type) != 0 )
            (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 10))(
              v13,
              v14,
              v19,
              v18,
              v46,
              v12);
          else
            ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD))v12)(v13, v14, v19, v18);
          v13 = v47;
          v14 = v20;
        }
        while ( v20 );
        break;
      }
      *(_BYTE *)(v15 + 16) = 1;
      v16 = v7;
      v17 = *v11;
      *v11 = 0;
      if ( v17 )
      {
        v25 = v13;
        do
        {
          v26 = *(_DWORD *)(v17 + 132);
          v27 = *(_DWORD *)(v17 + 140);
          v28 = *(_QWORD *)(v17 + 112);
          *(_DWORD *)(v17 + 132) = 0;
          v63 = v26;
          v49 = v27;
          if ( byte_14011D730 )
          {
            if ( v7->Type == 5 )
            {
              v38 = *(_QWORD *)&v7[228].Type;
              if ( v38 )
              {
                if ( (*(_DWORD *)(v38 + 56) & 1) != 0 )
                {
                  v39 = (*(_DWORD *)(v17 + 128) & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v55) = 0;
                  v54 = 0;
                  if ( v39 )
                  {
                    v48 = v7[230];
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v40 = *(_QWORD *)&v7[226].Type;
                      *(_QWORD *)((char *)&v54 + 4) = *(unsigned int *)&v48 | 0x200000000LL;
                      LOWORD(Parameter) = 40;
                      *((_QWORD *)&Parameter + 1) = v17;
                      LODWORD(v54) = 1;
                      v55 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                  + 40LL))(
                        xmmword_14011D750,
                        v40,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    v27 = v49;
                    v26 = v63;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && v7->Type == 5 && (v44 = *(_QWORD *)&v7[194].Type) != 0 )
            (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 10))(
              v25,
              v17,
              v27,
              v26,
              v44,
              v12);
          else
            ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD))v12)(v25, v17, v27, v26);
          v17 = v28;
        }
        while ( v28 );
        v15 = v58;
        v16 = v7;
      }
      v6 = v52;
      v11 = (__int64 *)v15;
      *(_BYTE *)(v15 + 16) = 0;
      v7 = *(struct _NDIS_OBJECT_HEADER **)&v7[114].Type;
      v12 = *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))&v16[108].Type;
      v13 = *(void **)&v16[110].Type;
    }
    v21 = *v11;
    if ( *v11 )
    {
      *v11 = 0;
      do
      {
        v22 = *(_DWORD *)(v21 + 132);
        v23 = *(_DWORD *)(v21 + 140);
        v24 = *(_QWORD *)(v21 + 112);
        *(_DWORD *)(v21 + 132) = 0;
        v62 = v23;
        if ( byte_14011D730 )
        {
          if ( v7->Type == 5 )
          {
            v41 = *(_QWORD *)&v7[228].Type;
            if ( v41 )
            {
              if ( (*(_DWORD *)(v41 + 56) & 1) != 0 )
              {
                PktMonClientNblLogNdis(&v7[222], v21, a3, 2);
                v23 = v62;
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && v7->Type == 5 && (v45 = *(_QWORD *)&v7[194].Type) != 0 )
          (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)))ndisVerifierNdisDispatch
           + 10))(
            v47,
            v21,
            v23,
            v22,
            v45,
            v12);
        else
          ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD))v12)(v47, v21, v23, v22);
        v21 = v24;
      }
      while ( v24 );
    }
  }
  else
  {
    v29 = (unsigned int)Size;
    v30 = 0;
    LowLimit = 0;
    HighLimit = 0;
    v31 = KeGetPcr()->Prcb.Number << 12;
    v32 = *(_QWORD *)(v31 + qword_14011CF78);
    LowLimit = v32;
    v33 = *(_QWORD *)(v31 + qword_14011CF70);
    HighLimit = v33;
    if ( (unsigned __int64)&retaddr >= v33 || v32 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v32 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v32 >= v29 )
    {
      if ( byte_14011D730 )
      {
        if ( v7->Type == 5 )
        {
          v42 = *(_QWORD *)&v7[228].Type;
          if ( v42 )
          {
            if ( (*(_DWORD *)(v42 + 56) & 1) != 0 )
              PktMonClientNblLogNdis(&v7[222], a1, v33, 2);
          }
        }
      }
      if ( ndisVerifierNdisDispatch )
      {
        if ( v7->Type == 5 )
        {
          v34 = *(_QWORD *)&v7[194].Type;
          if ( v34 )
          {
            (*((void (__fastcall **)(void *, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 10))(
              a5,
              a1,
              a2,
              v8,
              v34,
              a6);
            return;
          }
        }
      }
      goto LABEL_2;
    }
    v35 = 24576;
    *((_QWORD *)&Parameter + 1) = a5;
    *(_QWORD *)&v54 = a6;
    v57 = 0;
    *(_QWORD *)&Parameter = v7;
    *((_QWORD *)&v54 + 1) = a1;
    v55 = a2;
    v56 = v8;
    if ( (unsigned int)Size > 0x6000 )
      v35 = Size;
    if ( KeExpandKernelStackAndCalloutEx(
           ndisDataPathExpandStackCallback<0,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long)>,
           &Parameter,
           v35,
           0,
           0) < 0 )
    {
      if ( byte_14011D730 && (*(_DWORD *)&v7[210] & 2) != 0 )
        PktMonClientNblDropNdis((_DWORD)v7 + 784, (_DWORD)a1, v36, 2, -1073741670, -536866812);
      NdisSetStatusInNblChain(a1, -1073741670);
      for ( i = a1; i; ++v30 )
        i = (struct _NET_BUFFER_LIST *)i->Link.Alignment;
      _InterlockedAdd((volatile signed __int32 *)&v7[74], v30);
      ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)v7, a1, 1u);
    }
  }
}

```

## disassembly

```asm
0x140010b10  push    rbp
0x140010b12  push    rbx
0x140010b13  push    rsi
0x140010b14  push    rdi
0x140010b15  push    r12
0x140010b17  push    r13
0x140010b19  push    r14
0x140010b1b  push    r15
0x140010b1d  lea     rbp, [rsp-0Fh]
0x140010b22  sub     rsp, 0C8h
0x140010b29  cmp     byte ptr [r9], 11h
0x140010b2d  mov     rbx, r9
0x140010b30  mov     esi, r8d
0x140010b33  mov     r14d, edx
0x140010b36  mov     rdi, rcx
0x140010b39  jnz     short loc_140010B66
0x140010b3b  mov     rcx, [rbp+47h+arg_20]
0x140010b3f  mov     r9d, esi
0x140010b42  mov     rax, [rbp+47h+arg_28]
0x140010b46  mov     r8d, r14d
0x140010b49  mov     rdx, rdi
0x140010b4c  call    _guard_dispatch_icall
0x140010b51  add     rsp, 0C8h
0x140010b58  pop     r15
0x140010b5a  pop     r14
0x140010b5c  pop     r13
0x140010b5e  pop     r12
0x140010b60  pop     rdi
0x140010b61  pop     rsi
0x140010b62  pop     rbx
0x140010b63  pop     rbp
0x140010b64  retn
0x140010b66  test    sil, 1
0x140010b6a  jnz     short loc_140010B80
0x140010b6c  call    cs:__imp_KeGetCurrentIrql
0x140010b73  nop     dword ptr [rax+rax+00h]
0x140010b78  cmp     al, 2
0x140010b7a  jnz     loc_140010D53
0x140010b80  mov     eax, gs:1A4h
0x140010b88  lea     r15, [rbp+47h+var_60]
0x140010b8c  mov     r13, [rbp+47h+arg_28]
0x140010b90  xor     r12d, r12d
0x140010b93  mov     r10, [rbp+47h+arg_20]
0x140010b97  mov     [rbp+47h+var_A0], eax
0x140010b9a  mov     [rbp+47h+var_50], r12
0x140010b9e  mov     [rdi+70h], r12
0x140010ba2  mov     [rbp+47h+var_60], rdi
0x140010ba6  mov     [rbp+47h+var_58], rdi
0x140010baa  mov     [rdi+84h], esi
0x140010bb0  mov     [rdi+8Ch], r14d
0x140010bb7  cmp     byte ptr [rbx], 5
0x140010bba  mov     [rbp+47h+var_C0], r10
0x140010bbe  jnz     loc_140010C7B
0x140010bc4  mov     rsi, [r15]
0x140010bc7  test    rsi, rsi
0x140010bca  jz      loc_140010C7B
0x140010bd0  lea     rdi, [rax+rax*2]
0x140010bd4  shl     rdi, 5
0x140010bd8  add     rdi, [rbx+1A8h]
0x140010bdf  mov     [rbp+47h+var_68], rdi
0x140010be3  cmp     [rdi+10h], r12b
0x140010be7  jnz     short loc_140010C20
0x140010be9  mov     byte ptr [rdi+10h], 1
0x140010bed  mov     r14, rbx
0x140010bf0  mov     rsi, [r15]
0x140010bf3  mov     [r15], r12
0x140010bf6  test    rsi, rsi
0x140010bf9  jnz     loc_140010CE8
0x140010bff  mov     eax, [rbp+47h+var_A0]
0x140010c02  mov     r15, rdi
0x140010c05  mov     [rdi+10h], r12b
0x140010c09  mov     rbx, [rbx+1C8h]
0x140010c10  mov     r13, [r14+1B0h]
0x140010c17  mov     r10, [r14+1B8h]
0x140010c1e  jmp     short loc_140010BB7
0x140010c20  mov     [r15], r12
0x140010c23  mov     r14d, [rsi+84h]
0x140010c2a  mov     ecx, [rsi+8Ch]
0x140010c30  mov     rdi, [rsi+70h]
0x140010c34  mov     [rsi+84h], r12d
0x140010c3b  cmp     cs:byte_14011D730, r12b
0x140010c42  mov     [rbp+47h+arg_18], ecx
0x140010c45  jnz     loc_140011041
0x140010c4b  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140010c52  test    rax, rax
0x140010c55  jnz     loc_140011100
0x140010c5b  mov     r8d, ecx
0x140010c5e  mov     r9d, r14d
0x140010c61  mov     rcx, r10
0x140010c64  mov     rdx, rsi
0x140010c67  mov     rax, r13
0x140010c6a  call    _guard_dispatch_icall
0x140010c6f  mov     r10, [rbp+47h+var_C0]
0x140010c73  mov     rsi, rdi
0x140010c76  test    rdi, rdi
0x140010c79  jnz     short loc_140010C23
0x140010c7b  mov     rdi, [r15]
0x140010c7e  test    rdi, rdi
0x140010c81  jz      loc_140010B51
0x140010c87  mov     rsi, [rbp+47h+var_C0]
0x140010c8b  mov     [r15], r12
0x140010c8e  mov     r15d, [rdi+84h]
0x140010c95  mov     ecx, [rdi+8Ch]
0x140010c9b  mov     r14, [rdi+70h]
0x140010c9f  mov     [rdi+84h], r12d
0x140010ca6  cmp     cs:byte_14011D730, r12b
0x140010cad  mov     [rbp+47h+arg_18], ecx
0x140010cb0  jnz     loc_140010FB7
0x140010cb6  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140010cbd  test    rax, rax
0x140010cc0  jnz     loc_1400110C3
0x140010cc6  mov     r8d, ecx
0x140010cc9  mov     r9d, r15d
0x140010ccc  mov     rcx, rsi
0x140010ccf  mov     rdx, rdi
0x140010cd2  mov     rax, r13
0x140010cd5  call    _guard_dispatch_icall
0x140010cda  mov     rdi, r14
0x140010cdd  test    r14, r14
0x140010ce0  jz      loc_140010B51
0x140010ce6  jmp     short loc_140010C8E
0x140010ce8  mov     r14, [rbp+47h+var_C0]
0x140010cec  mov     edi, 28h ; '('
0x140010cf1  mov     ecx, [rsi+84h]
0x140010cf7  mov     edx, [rsi+8Ch]
0x140010cfd  mov     r15, [rsi+70h]
0x140010d01  mov     [rsi+84h], r12d
0x140010d08  cmp     cs:byte_14011D730, r12b
0x140010d0f  mov     [rbp+47h+arg_18], ecx
0x140010d12  mov     [rbp+47h+var_B8], edx
0x140010d15  jnz     loc_140010EF0
0x140010d1b  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140010d22  test    rax, rax
0x140010d25  jnz     loc_140011086
0x140010d2b  mov     r9d, ecx
0x140010d2e  mov     r8d, edx
0x140010d31  mov     rdx, rsi
0x140010d34  mov     rcx, r14
0x140010d37  mov     rax, r13
0x140010d3a  call    _guard_dispatch_icall
0x140010d3f  mov     rsi, r15
0x140010d42  test    r15, r15
0x140010d45  jnz     short loc_140010CF1
0x140010d47  mov     rdi, [rbp+47h+var_68]
0x140010d4b  mov     r14, rbx
0x140010d4e  jmp     loc_140010BFF
0x140010d53  mov     r13d, cs:Size
0x140010d5a  lea     r15, [rbp+4Fh]
0x140010d5e  xor     r12d, r12d
0x140010d61  mov     [rbp+47h+LowLimit], r12
0x140010d65  mov     [rbp+47h+HighLimit], r12
0x140010d69  mov     eax, gs:1A4h
0x140010d71  shl     eax, 0Ch
0x140010d74  mov     ecx, eax
0x140010d76  mov     rax, cs:qword_14011CF78
0x140010d7d  mov     rdx, [rcx+rax]
0x140010d81  mov     rax, cs:qword_14011CF70
0x140010d88  mov     [rbp+47h+LowLimit], rdx
0x140010d8c  mov     r8, [rcx+rax]
0x140010d90  mov     [rbp+47h+HighLimit], r8
0x140010d94  cmp     r15, r8
0x140010d97  jb      loc_140010FF8
0x140010d9d  lea     rdx, [rbp+47h+HighLimit]; HighLimit
0x140010da1  lea     rcx, [rbp+47h+LowLimit]; LowLimit
0x140010da5  call    cs:__imp_IoGetStackLimits
0x140010dac  nop     dword ptr [rax+rax+00h]
0x140010db1  mov     rdx, [rbp+47h+LowLimit]
0x140010db5  sub     r15, rdx
0x140010db8  cmp     r15, r13
0x140010dbb  jb      short loc_140010E1C
0x140010dbd  cmp     cs:byte_14011D730, r12b
0x140010dc4  jnz     loc_140011006
0x140010dca  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140010dd1  test    rax, rax
0x140010dd4  jz      loc_140010B3B
0x140010dda  cmp     byte ptr [rbx], 5
0x140010ddd  jnz     loc_140010B3B
0x140010de3  mov     rdx, [rbx+308h]
0x140010dea  test    rdx, rdx
0x140010ded  jz      loc_140010B3B
0x140010df3  mov     rcx, [rbp+47h+arg_28]
0x140010df7  mov     r9d, esi
0x140010dfa  mov     rax, [rax+50h]
0x140010dfe  mov     r8d, r14d
0x140010e01  mov     [rsp+100h+var_D8], rcx
0x140010e06  mov     rcx, [rbp+47h+arg_20]
0x140010e0a  mov     [rsp+100h+Context], rdx
0x140010e0f  mov     rdx, rdi
0x140010e12  call    _guard_dispatch_icall
0x140010e17  jmp     loc_140010B51
0x140010e1c  mov     rax, [rbp+47h+arg_20]
0x140010e20  mov     ecx, 6000h
0x140010e25  mov     qword ptr [rbp+47h+Parameter+8], rax
0x140010e29  mov     rax, [rbp+47h+arg_28]
0x140010e2d  mov     qword ptr [rbp+47h+var_88], rax
0x140010e31  mov     eax, cs:Size
0x140010e37  mov     [rbp+47h+var_6C], r12d
0x140010e3b  mov     qword ptr [rbp+47h+Parameter], rbx
0x140010e3f  mov     qword ptr [rbp+47h+var_88+8], rdi
0x140010e43  mov     dword ptr [rbp+47h+var_78+4], r12d
0x140010e47  mov     dword ptr [rbp+47h+var_78], r14d
0x140010e4b  mov     [rbp+47h+var_70], esi
0x140010e4e  cmp     eax, ecx
0x140010e50  ja      loc_14001113D
0x140010e56  movsxd  r8, ecx; Size
0x140010e59  lea     rdx, [rbp+47h+Parameter]; Parameter
0x140010e5d  lea     rcx, ??$ndisDataPathExpandStackCallback@$0A@$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KK@Z@@YAXPEAX@Z; Callout
0x140010e64  mov     [rsp+100h+Context], r12; Context
0x140010e69  xor     r9d, r9d; Wait
0x140010e6c  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140010e73  nop     dword ptr [rax+rax+00h]
0x140010e78  test    eax, eax
0x140010e7a  jns     loc_140010B51
0x140010e80  cmp     cs:byte_14011D730, r12b
0x140010e87  jz      short loc_140010EB5
0x140010e89  lea     rcx, [rbx+310h]
0x140010e90  mov     eax, [rcx+38h]
0x140010e93  test    al, 2
0x140010e95  jz      short loc_140010EB5
0x140010e97  mov     dword ptr [rsp+100h+var_D8], 0E0001004h
0x140010e9f  mov     r9d, 2
0x140010ea5  mov     rdx, rdi
0x140010ea8  mov     dword ptr [rsp+100h+Context], 0C000009Ah
0x140010eb0  call    PktMonClientNblDropNdis
0x140010eb5  mov     edx, 0C000009Ah; int
0x140010eba  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x140010ebd  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x140010ec2  mov     rax, rdi
0x140010ec5  test    rdi, rdi
0x140010ec8  jz      short loc_140010ED5
0x140010eca  mov     rax, [rax]
0x140010ecd  inc     r12d
0x140010ed0  test    rax, rax
0x140010ed3  jnz     short loc_140010ECA
0x140010ed5  lock add [rbx+128h], r12d
0x140010edd  mov     r8b, 1; unsigned __int8
0x140010ee0  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x140010ee3  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140010ee6  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x140010eeb  jmp     loc_140010B51
0x140010ef0  cmp     byte ptr [rbx], 5
0x140010ef3  jnz     loc_140010D1B
0x140010ef9  mov     rax, [rbx+390h]
0x140010f00  test    rax, rax
0x140010f03  jz      loc_140010D1B
0x140010f09  mov     eax, [rax+38h]
0x140010f0c  test    al, 1
0x140010f0e  jz      loc_140010D1B
0x140010f14  xor     eax, eax
0x140010f16  xorps   xmm0, xmm0
0x140010f19  test    dword ptr [rsi+80h], 8000h
0x140010f23  movups  [rbp+47h+Parameter], xmm0
0x140010f27  mov     dword ptr [rbp+47h+var_78], eax
0x140010f2a  movups  [rbp+47h+var_88], xmm0
0x140010f2e  jnz     loc_140010D1B
0x140010f34  mov     eax, [rbx+398h]
0x140010f3a  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140010f41  mov     dword ptr [rbp+47h+var_C0], eax
0x140010f44  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140010f4b  nop     dword ptr [rax+rax+00h]
0x140010f50  test    al, al
0x140010f52  jz      short loc_140010FAC
0x140010f54  mov     eax, dword ptr [rbp+47h+var_C0]
0x140010f57  lea     r8, [rbp+47h+Parameter]
0x140010f5b  mov     rdx, [rbx+388h]
0x140010f62  xor     r9d, r9d
0x140010f65  mov     rcx, qword ptr cs:xmmword_14011D750
0x140010f6c  mov     dword ptr [rbp+47h+var_88+4], eax
0x140010f6f  mov     rax, qword ptr cs:xmmword_14011D750+8
0x140010f76  mov     word ptr [rbp+47h+Parameter], di
0x140010f7a  mov     qword ptr [rbp+47h+Parameter+8], rsi
0x140010f7e  mov     dword ptr [rbp+47h+var_88], 1
0x140010f85  mov     dword ptr [rbp+47h+var_88+8], 2
0x140010f8c  mov     [rbp+47h+var_78], r12
0x140010f90  mov     rax, [rax+28h]
0x140010f94  call    _guard_dispatch_icall
0x140010f99  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140010fa0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140010fa7  nop     dword ptr [rax+rax+00h]
0x140010fac  mov     edx, [rbp+47h+var_B8]
0x140010faf  mov     ecx, [rbp+47h+arg_18]
0x140010fb2  jmp     loc_140010D1B
0x140010fb7  cmp     byte ptr [rbx], 5
0x140010fba  jnz     loc_140010CB6
0x140010fc0  mov     rax, [rbx+390h]
0x140010fc7  test    rax, rax
0x140010fca  jz      loc_140010CB6
0x140010fd0  mov     eax, [rax+38h]
0x140010fd3  test    al, 1
0x140010fd5  jz      loc_140010CB6
0x140010fdb  lea     rcx, [rbx+378h]
0x140010fe2  mov     r9d, 2
0x140010fe8  mov     rdx, rdi
0x140010feb  call    PktMonClientNblLogNdis
0x140010ff0  mov     ecx, [rbp+47h+arg_18]
0x140010ff3  jmp     loc_140010CB6
0x140010ff8  cmp     rdx, r15
0x140010ffb  jbe     loc_140010DB5
0x140011001  jmp     loc_140010D9D
0x140011006  cmp     byte ptr [rbx], 5
  ... truncated ...
```
