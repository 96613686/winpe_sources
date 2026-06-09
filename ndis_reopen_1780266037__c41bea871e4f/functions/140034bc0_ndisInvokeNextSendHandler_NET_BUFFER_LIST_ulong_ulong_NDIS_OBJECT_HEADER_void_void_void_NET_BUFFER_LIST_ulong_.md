# ndisInvokeNextSendHandler(_NET_BUFFER_LIST *,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong))

- ea: `0x140034bc0`
- end: `0x1400351f8`
- name: `?ndisInvokeNextSendHandler@@YAXPEAU_NET_BUFFER_LIST@@KKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KK@Z@Z`
- size: `1592`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, struct _NDIS_OBJECT_HEADER *@<r9>, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int))`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140026410`
- `0x1400332f0`
- `0x140034070`
- `0x14005c2d0`

## callees

- `0x1400334f0`
- `0x140034bc0`
- `0x140037bd0`
- `0x140038090`
- `0x14003a0e0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140034c1c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140034c1c`
- `ntoskrnl!IoGetStackLimits` at `0x140034e55`
- `ntoskrnl!IoGetStackLimits` at `0x140034e55`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140034f1c`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140034f1c`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140034ff4`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140034ff4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140035050`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140035050`

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
          if ( byte_140123720 )
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
          if ( byte_140123720 )
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
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                  + 40LL))(
                        xmmword_140123740,
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
        if ( byte_140123720 )
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
    v32 = *(_QWORD *)(v31 + qword_140122F78);
    LowLimit = v32;
    v33 = *(_QWORD *)(v31 + qword_140122F70);
    HighLimit = v33;
    if ( (unsigned __int64)&retaddr >= v33 || v32 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v32 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v32 >= v29 )
    {
      if ( byte_140123720 )
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
      if ( byte_140123720 && (*(_DWORD *)&v7[210] & 2) != 0 )
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
0x140034bc0  push    rbp
0x140034bc2  push    rbx
0x140034bc3  push    rsi
0x140034bc4  push    rdi
0x140034bc5  push    r12
0x140034bc7  push    r13
0x140034bc9  push    r14
0x140034bcb  push    r15
0x140034bcd  lea     rbp, [rsp-0Fh]
0x140034bd2  sub     rsp, 0C8h
0x140034bd9  cmp     byte ptr [r9], 11h
0x140034bdd  mov     rbx, r9
0x140034be0  mov     esi, r8d
0x140034be3  mov     r14d, edx
0x140034be6  mov     rdi, rcx
0x140034be9  jnz     short loc_140034C16
0x140034beb  mov     rcx, [rbp+47h+arg_20]
0x140034bef  mov     r9d, esi
0x140034bf2  mov     rax, [rbp+47h+arg_28]
0x140034bf6  mov     r8d, r14d
0x140034bf9  mov     rdx, rdi
0x140034bfc  call    _guard_dispatch_icall
0x140034c01  add     rsp, 0C8h
0x140034c08  pop     r15
0x140034c0a  pop     r14
0x140034c0c  pop     r13
0x140034c0e  pop     r12
0x140034c10  pop     rdi
0x140034c11  pop     rsi
0x140034c12  pop     rbx
0x140034c13  pop     rbp
0x140034c14  retn
0x140034c16  test    sil, 1
0x140034c1a  jnz     short loc_140034C30
0x140034c1c  call    cs:__imp_KeGetCurrentIrql
0x140034c23  nop     dword ptr [rax+rax+00h]
0x140034c28  cmp     al, 2
0x140034c2a  jnz     loc_140034E03
0x140034c30  mov     eax, gs:1A4h
0x140034c38  lea     r15, [rbp+47h+var_60]
0x140034c3c  mov     r13, [rbp+47h+arg_28]
0x140034c40  xor     r12d, r12d
0x140034c43  mov     r10, [rbp+47h+arg_20]
0x140034c47  mov     [rbp+47h+var_A0], eax
0x140034c4a  mov     [rbp+47h+var_50], r12
0x140034c4e  mov     [rdi+70h], r12
0x140034c52  mov     [rbp+47h+var_60], rdi
0x140034c56  mov     [rbp+47h+var_58], rdi
0x140034c5a  mov     [rdi+84h], esi
0x140034c60  mov     [rdi+8Ch], r14d
0x140034c67  cmp     byte ptr [rbx], 5
0x140034c6a  mov     [rbp+47h+var_C0], r10
0x140034c6e  jnz     loc_140034D2B
0x140034c74  mov     rsi, [r15]
0x140034c77  test    rsi, rsi
0x140034c7a  jz      loc_140034D2B
0x140034c80  lea     rdi, [rax+rax*2]
0x140034c84  shl     rdi, 5
0x140034c88  add     rdi, [rbx+1A8h]
0x140034c8f  mov     [rbp+47h+var_68], rdi
0x140034c93  cmp     [rdi+10h], r12b
0x140034c97  jnz     short loc_140034CD0
0x140034c99  mov     byte ptr [rdi+10h], 1
0x140034c9d  mov     r14, rbx
0x140034ca0  mov     rsi, [r15]
0x140034ca3  mov     [r15], r12
0x140034ca6  test    rsi, rsi
0x140034ca9  jnz     loc_140034D98
0x140034caf  mov     eax, [rbp+47h+var_A0]
0x140034cb2  mov     r15, rdi
0x140034cb5  mov     [rdi+10h], r12b
0x140034cb9  mov     rbx, [rbx+1C8h]
0x140034cc0  mov     r13, [r14+1B0h]
0x140034cc7  mov     r10, [r14+1B8h]
0x140034cce  jmp     short loc_140034C67
0x140034cd0  mov     [r15], r12
0x140034cd3  mov     r14d, [rsi+84h]
0x140034cda  mov     ecx, [rsi+8Ch]
0x140034ce0  mov     rdi, [rsi+70h]
0x140034ce4  mov     [rsi+84h], r12d
0x140034ceb  cmp     cs:byte_140123720, r12b
0x140034cf2  mov     [rbp+47h+arg_18], ecx
0x140034cf5  jnz     loc_1400350F1
0x140034cfb  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140034d02  test    rax, rax
0x140034d05  jnz     loc_1400351B0
0x140034d0b  mov     r8d, ecx
0x140034d0e  mov     r9d, r14d
0x140034d11  mov     rcx, r10
0x140034d14  mov     rdx, rsi
0x140034d17  mov     rax, r13
0x140034d1a  call    _guard_dispatch_icall
0x140034d1f  mov     r10, [rbp+47h+var_C0]
0x140034d23  mov     rsi, rdi
0x140034d26  test    rdi, rdi
0x140034d29  jnz     short loc_140034CD3
0x140034d2b  mov     rdi, [r15]
0x140034d2e  test    rdi, rdi
0x140034d31  jz      loc_140034C01
0x140034d37  mov     rsi, [rbp+47h+var_C0]
0x140034d3b  mov     [r15], r12
0x140034d3e  mov     r15d, [rdi+84h]
0x140034d45  mov     ecx, [rdi+8Ch]
0x140034d4b  mov     r14, [rdi+70h]
0x140034d4f  mov     [rdi+84h], r12d
0x140034d56  cmp     cs:byte_140123720, r12b
0x140034d5d  mov     [rbp+47h+arg_18], ecx
0x140034d60  jnz     loc_140035067
0x140034d66  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140034d6d  test    rax, rax
0x140034d70  jnz     loc_140035173
0x140034d76  mov     r8d, ecx
0x140034d79  mov     r9d, r15d
0x140034d7c  mov     rcx, rsi
0x140034d7f  mov     rdx, rdi
0x140034d82  mov     rax, r13
0x140034d85  call    _guard_dispatch_icall
0x140034d8a  mov     rdi, r14
0x140034d8d  test    r14, r14
0x140034d90  jz      loc_140034C01
0x140034d96  jmp     short loc_140034D3E
0x140034d98  mov     r14, [rbp+47h+var_C0]
0x140034d9c  mov     edi, 28h ; '('
0x140034da1  mov     ecx, [rsi+84h]
0x140034da7  mov     edx, [rsi+8Ch]
0x140034dad  mov     r15, [rsi+70h]
0x140034db1  mov     [rsi+84h], r12d
0x140034db8  cmp     cs:byte_140123720, r12b
0x140034dbf  mov     [rbp+47h+arg_18], ecx
0x140034dc2  mov     [rbp+47h+var_B8], edx
0x140034dc5  jnz     loc_140034FA0
0x140034dcb  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140034dd2  test    rax, rax
0x140034dd5  jnz     loc_140035136
0x140034ddb  mov     r9d, ecx
0x140034dde  mov     r8d, edx
0x140034de1  mov     rdx, rsi
0x140034de4  mov     rcx, r14
0x140034de7  mov     rax, r13
0x140034dea  call    _guard_dispatch_icall
0x140034def  mov     rsi, r15
0x140034df2  test    r15, r15
0x140034df5  jnz     short loc_140034DA1
0x140034df7  mov     rdi, [rbp+47h+var_68]
0x140034dfb  mov     r14, rbx
0x140034dfe  jmp     loc_140034CAF
0x140034e03  mov     r13d, cs:Size
0x140034e0a  lea     r15, [rbp+4Fh]
0x140034e0e  xor     r12d, r12d
0x140034e11  mov     [rbp+47h+LowLimit], r12
0x140034e15  mov     [rbp+47h+HighLimit], r12
0x140034e19  mov     eax, gs:1A4h
0x140034e21  shl     eax, 0Ch
0x140034e24  mov     ecx, eax
0x140034e26  mov     rax, cs:qword_140122F78
0x140034e2d  mov     rdx, [rcx+rax]
0x140034e31  mov     rax, cs:qword_140122F70
0x140034e38  mov     [rbp+47h+LowLimit], rdx
0x140034e3c  mov     r8, [rcx+rax]
0x140034e40  mov     [rbp+47h+HighLimit], r8
0x140034e44  cmp     r15, r8
0x140034e47  jb      loc_1400350A8
0x140034e4d  lea     rdx, [rbp+47h+HighLimit]; HighLimit
0x140034e51  lea     rcx, [rbp+47h+LowLimit]; LowLimit
0x140034e55  call    cs:__imp_IoGetStackLimits
0x140034e5c  nop     dword ptr [rax+rax+00h]
0x140034e61  mov     rdx, [rbp+47h+LowLimit]
0x140034e65  sub     r15, rdx
0x140034e68  cmp     r15, r13
0x140034e6b  jb      short loc_140034ECC
0x140034e6d  cmp     cs:byte_140123720, r12b
0x140034e74  jnz     loc_1400350B6
0x140034e7a  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140034e81  test    rax, rax
0x140034e84  jz      loc_140034BEB
0x140034e8a  cmp     byte ptr [rbx], 5
0x140034e8d  jnz     loc_140034BEB
0x140034e93  mov     rdx, [rbx+308h]
0x140034e9a  test    rdx, rdx
0x140034e9d  jz      loc_140034BEB
0x140034ea3  mov     rcx, [rbp+47h+arg_28]
0x140034ea7  mov     r9d, esi
0x140034eaa  mov     rax, [rax+50h]
0x140034eae  mov     r8d, r14d
0x140034eb1  mov     [rsp+100h+var_D8], rcx
0x140034eb6  mov     rcx, [rbp+47h+arg_20]
0x140034eba  mov     [rsp+100h+Context], rdx
0x140034ebf  mov     rdx, rdi
0x140034ec2  call    _guard_dispatch_icall
0x140034ec7  jmp     loc_140034C01
0x140034ecc  mov     rax, [rbp+47h+arg_20]
0x140034ed0  mov     ecx, 6000h
0x140034ed5  mov     qword ptr [rbp+47h+Parameter+8], rax
0x140034ed9  mov     rax, [rbp+47h+arg_28]
0x140034edd  mov     qword ptr [rbp+47h+var_88], rax
0x140034ee1  mov     eax, cs:Size
0x140034ee7  mov     [rbp+47h+var_6C], r12d
0x140034eeb  mov     qword ptr [rbp+47h+Parameter], rbx
0x140034eef  mov     qword ptr [rbp+47h+var_88+8], rdi
0x140034ef3  mov     dword ptr [rbp+47h+var_78+4], r12d
0x140034ef7  mov     dword ptr [rbp+47h+var_78], r14d
0x140034efb  mov     [rbp+47h+var_70], esi
0x140034efe  cmp     eax, ecx
0x140034f00  ja      loc_1400351ED
0x140034f06  movsxd  r8, ecx; Size
0x140034f09  lea     rdx, [rbp+47h+Parameter]; Parameter
0x140034f0d  lea     rcx, ??$ndisDataPathExpandStackCallback@$0A@$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KK@Z@@YAXPEAX@Z; Callout
0x140034f14  mov     [rsp+100h+Context], r12; Context
0x140034f19  xor     r9d, r9d; Wait
0x140034f1c  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140034f23  nop     dword ptr [rax+rax+00h]
0x140034f28  test    eax, eax
0x140034f2a  jns     loc_140034C01
0x140034f30  cmp     cs:byte_140123720, r12b
0x140034f37  jz      short loc_140034F65
0x140034f39  lea     rcx, [rbx+310h]
0x140034f40  mov     eax, [rcx+38h]
0x140034f43  test    al, 2
0x140034f45  jz      short loc_140034F65
0x140034f47  mov     dword ptr [rsp+100h+var_D8], 0E0001004h
0x140034f4f  mov     r9d, 2
0x140034f55  mov     rdx, rdi
0x140034f58  mov     dword ptr [rsp+100h+Context], 0C000009Ah
0x140034f60  call    PktMonClientNblDropNdis
0x140034f65  mov     edx, 0C000009Ah; int
0x140034f6a  mov     rcx, rdi; struct _NET_BUFFER_LIST *
0x140034f6d  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x140034f72  mov     rax, rdi
0x140034f75  test    rdi, rdi
0x140034f78  jz      short loc_140034F85
0x140034f7a  mov     rax, [rax]
0x140034f7d  inc     r12d
0x140034f80  test    rax, rax
0x140034f83  jnz     short loc_140034F7A
0x140034f85  lock add [rbx+128h], r12d
0x140034f8d  mov     r8b, 1; unsigned __int8
0x140034f90  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x140034f93  mov     rcx, rbx; struct _NDIS_FILTER_BLOCK *
0x140034f96  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x140034f9b  jmp     loc_140034C01
0x140034fa0  cmp     byte ptr [rbx], 5
0x140034fa3  jnz     loc_140034DCB
0x140034fa9  mov     rax, [rbx+390h]
0x140034fb0  test    rax, rax
0x140034fb3  jz      loc_140034DCB
0x140034fb9  mov     eax, [rax+38h]
0x140034fbc  test    al, 1
0x140034fbe  jz      loc_140034DCB
0x140034fc4  xor     eax, eax
0x140034fc6  xorps   xmm0, xmm0
0x140034fc9  test    dword ptr [rsi+80h], 8000h
0x140034fd3  movups  [rbp+47h+Parameter], xmm0
0x140034fd7  mov     dword ptr [rbp+47h+var_78], eax
0x140034fda  movups  [rbp+47h+var_88], xmm0
0x140034fde  jnz     loc_140034DCB
0x140034fe4  mov     eax, [rbx+398h]
0x140034fea  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140034ff1  mov     dword ptr [rbp+47h+var_C0], eax
0x140034ff4  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140034ffb  nop     dword ptr [rax+rax+00h]
0x140035000  test    al, al
0x140035002  jz      short loc_14003505C
0x140035004  mov     eax, dword ptr [rbp+47h+var_C0]
0x140035007  lea     r8, [rbp+47h+Parameter]
0x14003500b  mov     rdx, [rbx+388h]
0x140035012  xor     r9d, r9d
0x140035015  mov     rcx, qword ptr cs:xmmword_140123740
0x14003501c  mov     dword ptr [rbp+47h+var_88+4], eax
0x14003501f  mov     rax, qword ptr cs:xmmword_140123740+8
0x140035026  mov     word ptr [rbp+47h+Parameter], di
0x14003502a  mov     qword ptr [rbp+47h+Parameter+8], rsi
0x14003502e  mov     dword ptr [rbp+47h+var_88], 1
0x140035035  mov     dword ptr [rbp+47h+var_88+8], 2
0x14003503c  mov     [rbp+47h+var_78], r12
0x140035040  mov     rax, [rax+28h]
0x140035044  call    _guard_dispatch_icall
0x140035049  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140035050  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140035057  nop     dword ptr [rax+rax+00h]
0x14003505c  mov     edx, [rbp+47h+var_B8]
0x14003505f  mov     ecx, [rbp+47h+arg_18]
0x140035062  jmp     loc_140034DCB
0x140035067  cmp     byte ptr [rbx], 5
0x14003506a  jnz     loc_140034D66
0x140035070  mov     rax, [rbx+390h]
0x140035077  test    rax, rax
0x14003507a  jz      loc_140034D66
0x140035080  mov     eax, [rax+38h]
0x140035083  test    al, 1
0x140035085  jz      loc_140034D66
0x14003508b  lea     rcx, [rbx+378h]
0x140035092  mov     r9d, 2
0x140035098  mov     rdx, rdi
0x14003509b  call    PktMonClientNblLogNdis
0x1400350a0  mov     ecx, [rbp+47h+arg_18]
0x1400350a3  jmp     loc_140034D66
0x1400350a8  cmp     rdx, r15
0x1400350ab  jbe     loc_140034E65
0x1400350b1  jmp     loc_140034E4D
0x1400350b6  cmp     byte ptr [rbx], 5
  ... truncated ...
```
