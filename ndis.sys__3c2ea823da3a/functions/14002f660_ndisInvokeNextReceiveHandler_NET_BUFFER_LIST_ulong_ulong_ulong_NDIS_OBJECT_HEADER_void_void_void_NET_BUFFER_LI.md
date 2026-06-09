# ndisInvokeNextReceiveHandler(_NET_BUFFER_LIST *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong))

- ea: `0x14002f660`
- end: `0x14002fe82`
- name: `?ndisInvokeNextReceiveHandler@@YAXPEAU_NET_BUFFER_LIST@@KKKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KKK@Z@Z`
- size: `2082`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _NDIS_OBJECT_HEADER *, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14002ea00`
- `0x1400555b0`

## callees

- `0x140004890`
- `0x14002c970`
- `0x14002c9d0`
- `0x14002de40`
- `0x14002f660`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14002f6d0`
- `ntoskrnl!KeGetCurrentIrql` at `0x14002f6d0`
- `ntoskrnl!IoGetStackLimits` at `0x14002f738`
- `ntoskrnl!IoGetStackLimits` at `0x14002f738`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002f806`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x14002f806`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fb18`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fbe5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fcb6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fb18`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fbe5`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14002fcb6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fb79`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fc48`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fd1b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fb79`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fc48`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14002fd1b`

## pseudocode

```c
void __fastcall ndisInvokeNextReceiveHandler(
        struct _NET_BUFFER_LIST *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        struct _NDIS_FILTER_BLOCK *a5,
        void *a6,
        void (*a7)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))
{
  struct _NDIS_OBJECT_HEADER *p_Header; // rdi
  __int64 v9; // r14
  __int64 v12; // rax
  unsigned int v13; // r13d
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // r8d
  struct _NET_BUFFER_LIST *i; // rax
  __int64 *v20; // r12
  unsigned __int64 Alignment; // rcx
  void (*v22)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int); // r10
  void *v23; // r11
  __int64 v24; // rbx
  __int64 v25; // rax
  struct _NDIS_OBJECT_HEADER *v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rsi
  int v29; // r14d
  unsigned int v30; // r15d
  unsigned int v31; // r12d
  __int64 v32; // rbx
  __int64 v33; // rsi
  int v34; // r15d
  unsigned int v35; // r12d
  unsigned int v36; // r14d
  unsigned int v37; // ecx
  __int64 v38; // rsi
  int v39; // r15d
  unsigned int v40; // r14d
  __int64 v41; // rax
  bool v42; // zf
  __int64 v43; // rdx
  __int64 v44; // rax
  struct _NDIS_OBJECT_HEADER v45; // r12d
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // rdx
  void *v53; // [rsp+40h] [rbp-81h]
  void (*v54)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int); // [rsp+48h] [rbp-79h]
  struct _NDIS_OBJECT_HEADER v55; // [rsp+50h] [rbp-71h]
  __int128 Parameter; // [rsp+58h] [rbp-69h] BYREF
  __int128 v57; // [rsp+68h] [rbp-59h]
  unsigned __int64 v58; // [rsp+78h] [rbp-49h]
  int v59; // [rsp+80h] [rbp-41h]
  int v60; // [rsp+84h] [rbp-3Dh]
  unsigned __int64 LowLimit; // [rsp+88h] [rbp-39h] BYREF
  unsigned __int64 HighLimit; // [rsp+90h] [rbp-31h] BYREF
  __int64 v63; // [rsp+98h] [rbp-29h]
  _QWORD v64[12]; // [rsp+A0h] [rbp-21h] BYREF
  _UNKNOWN *retaddr; // [rsp+108h] [rbp+47h] BYREF
  unsigned int v66; // [rsp+130h] [rbp+6Fh]
  unsigned int v67; // [rsp+130h] [rbp+6Fh]
  unsigned int v68; // [rsp+130h] [rbp+6Fh]
  struct _NDIS_OBJECT_HEADER v69; // [rsp+130h] [rbp+6Fh]

  p_Header = &a5->Header;
  v9 = (unsigned int)a3;
  if ( a5->Header.Type == 17 )
  {
LABEL_2:
    ((void (__fastcall *)(void *, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, int))a7)(a6, a1, a2, (unsigned int)v9, a4);
    return;
  }
  v12 = a4 & 2;
  if ( (a4 & 2) == 0 && ((a4 & 1) != 0 || KeGetCurrentIrql() == 2) )
  {
    LODWORD(v12) = KeGetPcr()->Prcb.Number;
    v20 = v64;
    Alignment = a1->Link.Alignment;
    v22 = a7;
    v23 = a6;
    v54 = a7;
    v53 = a6;
    v67 = v12;
    v64[2] = 0;
    v64[0] = a1;
    v64[1] = a1;
    a1->Scratch = 0;
    a1->ChildRefCount = a4;
    a1->Status = a2;
    if ( Alignment )
      *(_QWORD *)(Alignment + 112) = v9;
    while ( p_Header->Type == 5 )
    {
      v24 = *v20;
      if ( !*v20 )
        break;
      v25 = 96 * v12 + *(_QWORD *)&p_Header[106].Type + 48LL;
      v63 = v25;
      if ( *(_BYTE *)(v25 + 16) )
      {
        *v20 = 0;
        do
        {
          v37 = *(_DWORD *)(v24 + 140);
          v38 = *(_QWORD *)(v24 + 112);
          v39 = *(_DWORD *)(v24 + 132);
          v68 = v37;
          if ( *(_QWORD *)v24 )
            v40 = *(_DWORD *)(*(_QWORD *)v24 + 112LL);
          else
            v40 = 1;
          *(_DWORD *)(v24 + 132) = 0;
          if ( byte_14011D730 )
          {
            if ( p_Header->Type == 5 )
            {
              v49 = *(_QWORD *)&p_Header[218].Type;
              if ( v49 )
              {
                if ( (*(_DWORD *)(v49 + 56) & 1) != 0 )
                {
                  PktMonClientNblLogNdis(&p_Header[212], v24, a3, 1);
                  v22 = v54;
                  v23 = v53;
                  v37 = v68;
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && p_Header->Type == 5 && (v52 = *(_QWORD *)&p_Header[194].Type) != 0 )
            (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, int, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 14))(
              v23,
              v24,
              v37,
              v40,
              v39,
              v52,
              v22);
          else
            ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD, int))v22)(v23, v24, v37, v40, v39);
          v22 = v54;
          v24 = v38;
          v23 = v53;
        }
        while ( v38 );
        break;
      }
      *(_BYTE *)(v25 + 16) = 1;
      v26 = p_Header;
      v27 = *v20;
      *v20 = 0;
      if ( v27 )
      {
        do
        {
          v28 = *(_QWORD *)(v27 + 112);
          v29 = *(_DWORD *)(v27 + 132);
          v30 = *(_DWORD *)(v27 + 140);
          if ( *(_QWORD *)v27 )
            v31 = *(_DWORD *)(*(_QWORD *)v27 + 112LL);
          else
            v31 = 1;
          *(_DWORD *)(v27 + 132) = 0;
          if ( byte_14011D730 )
          {
            if ( p_Header->Type == 5 )
            {
              v41 = *(_QWORD *)&p_Header[218].Type;
              if ( v41 )
              {
                if ( (*(_DWORD *)(v41 + 56) & 1) != 0 )
                {
                  v42 = (*(_DWORD *)(v27 + 128) & 0x8000) == 0;
                  Parameter = 0;
                  LODWORD(v58) = 0;
                  v57 = 0;
                  if ( v42 )
                  {
                    v55 = p_Header[220];
                    if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                    {
                      v43 = *(_QWORD *)&p_Header[216].Type;
                      LOWORD(Parameter) = 40;
                      *(_QWORD *)((char *)&v57 + 4) = *(unsigned int *)&v55 | 0x100000000LL;
                      *((_QWORD *)&Parameter + 1) = v27;
                      LODWORD(v57) = 1;
                      v58 = 0;
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                  + 40LL))(
                        xmmword_14011D750,
                        v43,
                        &Parameter,
                        0);
                      ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                    }
                    v23 = v53;
                    v22 = v54;
                  }
                }
              }
            }
          }
          if ( ndisVerifierNdisDispatch && p_Header->Type == 5 && (v50 = *(_QWORD *)&p_Header[194].Type) != 0 )
            (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, int, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 14))(
              v23,
              v27,
              v30,
              v31,
              v29,
              v50,
              v22);
          else
            ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD, int))v22)(v23, v27, v30, v31, v29);
          v22 = v54;
          v27 = v28;
          v23 = v53;
        }
        while ( v28 );
        v25 = v63;
        v26 = p_Header;
      }
      *(_BYTE *)(v25 + 16) = 0;
      v20 = (__int64 *)v25;
      v22 = *(void (**)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))&v26[124].Type;
      v23 = *(void **)&v26[126].Type;
      p_Header = *(struct _NDIS_OBJECT_HEADER **)&p_Header[130].Type;
      v12 = v67;
      v54 = v22;
      v53 = v23;
    }
    v32 = *v20;
    if ( *v20 )
    {
      *v20 = 0;
      do
      {
        v33 = *(_QWORD *)(v32 + 112);
        v34 = *(_DWORD *)(v32 + 132);
        v35 = *(_DWORD *)(v32 + 140);
        if ( *(_QWORD *)v32 )
          v36 = *(_DWORD *)(*(_QWORD *)v32 + 112LL);
        else
          v36 = 1;
        *(_DWORD *)(v32 + 132) = 0;
        if ( byte_14011D730 )
        {
          if ( p_Header->Type == 5 )
          {
            v47 = *(_QWORD *)&p_Header[218].Type;
            if ( v47 )
            {
              if ( (*(_DWORD *)(v47 + 56) & 1) != 0 )
              {
                v42 = (*(_DWORD *)(v32 + 128) & 0x8000) == 0;
                Parameter = 0;
                LODWORD(v58) = 0;
                v57 = 0;
                if ( v42 )
                {
                  v69 = p_Header[220];
                  if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                  {
                    v48 = *(_QWORD *)&p_Header[216].Type;
                    LOWORD(Parameter) = 40;
                    *(_QWORD *)((char *)&v57 + 4) = *(unsigned int *)&v69 | 0x100000000LL;
                    *((_QWORD *)&Parameter + 1) = v32;
                    LODWORD(v57) = 1;
                    v58 = 0;
                    (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                                + 40LL))(
                      xmmword_14011D750,
                      v48,
                      &Parameter,
                      0);
                    ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                  }
                }
              }
            }
          }
        }
        if ( ndisVerifierNdisDispatch && p_Header->Type == 5 && (v51 = *(_QWORD *)&p_Header[194].Type) != 0 )
          (*((void (__fastcall **)(void *, __int64, _QWORD, _QWORD, int, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)))ndisVerifierNdisDispatch
           + 14))(
            v53,
            v32,
            v35,
            v36,
            v34,
            v51,
            v54);
        else
          ((void (__fastcall *)(void *, __int64, _QWORD, _QWORD, int))v54)(v53, v32, v35, v36, v34);
        v32 = v33;
      }
      while ( v33 );
    }
  }
  else
  {
    v66 = Size;
    v13 = 0;
    LowLimit = 0;
    HighLimit = 0;
    v14 = KeGetPcr()->Prcb.Number << 12;
    v15 = *(_QWORD *)(v14 + qword_14011CF78);
    LowLimit = v15;
    HighLimit = *(_QWORD *)(v14 + qword_14011CF70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v15 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v15 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v15 >= v66 )
    {
      if ( byte_14011D730 )
      {
        if ( p_Header->Type == 5 )
        {
          v44 = *(_QWORD *)&p_Header[218].Type;
          if ( v44 )
          {
            if ( (*(_DWORD *)(v44 + 56) & 1) != 0 )
            {
              v42 = (a1->NblFlags & 0x8000) == 0;
              Parameter = 0;
              LODWORD(v58) = 0;
              v57 = 0;
              if ( v42 )
              {
                v45 = p_Header[220];
                if ( ExAcquireRundownProtectionCacheAware(RunRefCacheAware) )
                {
                  v46 = *(_QWORD *)&p_Header[216].Type;
                  LOWORD(Parameter) = 40;
                  *((_QWORD *)&Parameter + 1) = a1;
                  LODWORD(v57) = 1;
                  *(_QWORD *)((char *)&v57 + 4) = *(unsigned int *)&v45 | 0x100000000LL;
                  v58 = 0;
                  (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_14011D750 + 1)
                                                                              + 40LL))(
                    xmmword_14011D750,
                    v46,
                    &Parameter,
                    0);
                  ExReleaseRundownProtectionCacheAware(RunRefCacheAware);
                }
              }
            }
          }
        }
      }
      if ( ndisVerifierNdisDispatch )
      {
        if ( p_Header->Type == 5 )
        {
          v16 = *(_QWORD *)&p_Header[194].Type;
          if ( v16 )
          {
            (*((void (__fastcall **)(void *, struct _NET_BUFFER_LIST *, _QWORD, _QWORD, int, __int64, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int)))ndisVerifierNdisDispatch
             + 14))(
              a6,
              a1,
              a2,
              (unsigned int)v9,
              a4,
              v16,
              a7);
            return;
          }
        }
      }
      goto LABEL_2;
    }
    v17 = 24576;
    *((_QWORD *)&Parameter + 1) = a6;
    *(_QWORD *)&v57 = a7;
    v60 = 0;
    *(_QWORD *)&Parameter = p_Header;
    *((_QWORD *)&v57 + 1) = a1;
    v58 = __PAIR64__(v9, a2);
    v59 = a4;
    if ( (unsigned int)Size > 0x6000 )
      v17 = Size;
    if ( KeExpandKernelStackAndCalloutEx(
           ndisDataPathExpandStackCallback<2,void (void *,_NET_BUFFER_LIST *,unsigned long,unsigned long,unsigned long)>,
           &Parameter,
           v17,
           0,
           0) < 0 )
    {
      if ( byte_14011D730 && (*(_DWORD *)&p_Header[210] & 2) != 0 )
        PktMonClientNblDropNdis((_DWORD)p_Header + 784, (_DWORD)a1, v18, 1, -1073741670, -536866813);
      NdisSetStatusInNblChain(a1, -1073741670);
      for ( i = a1; i; ++v13 )
        i = (struct _NET_BUFFER_LIST *)i->Link.Alignment;
      _InterlockedAdd((volatile signed __int32 *)&p_Header[73], v13);
      if ( (a4 & 2) == 0 )
        ndisQueueStackExpansionFallbackNbls((struct _NDIS_FILTER_BLOCK *)p_Header, a1, 0);
    }
  }
}

```

## disassembly

```asm
0x14002f660  push    rbp
0x14002f662  push    rbx
0x14002f663  push    rsi
0x14002f664  push    rdi
0x14002f665  push    r12
0x14002f667  push    r13
0x14002f669  push    r14
0x14002f66b  push    r15
0x14002f66d  lea     rbp, [rsp-7]
0x14002f672  sub     rsp, 0C8h
0x14002f679  mov     rdi, [rbp+3Fh+arg_20]
0x14002f67d  mov     ebx, r9d
0x14002f680  mov     r14d, r8d
0x14002f683  mov     r15d, edx
0x14002f686  mov     rsi, rcx
0x14002f689  cmp     byte ptr [rdi], 11h
0x14002f68c  jnz     short loc_14002F6BD
0x14002f68e  mov     rcx, [rbp+3Fh+arg_28]
0x14002f692  mov     r9d, r14d
0x14002f695  mov     rax, [rbp+3Fh+arg_30]
0x14002f699  mov     r8d, r15d
0x14002f69c  mov     rdx, rsi
0x14002f69f  mov     dword ptr [rsp+100h+Context], ebx
0x14002f6a3  call    _guard_dispatch_icall
0x14002f6a8  add     rsp, 0C8h
0x14002f6af  pop     r15
0x14002f6b1  pop     r14
0x14002f6b3  pop     r13
0x14002f6b5  pop     r12
0x14002f6b7  pop     rdi
0x14002f6b8  pop     rsi
0x14002f6b9  pop     rbx
0x14002f6ba  pop     rbp
0x14002f6bb  retn
0x14002f6bd  mov     eax, ebx
0x14002f6bf  and     eax, 2
0x14002f6c2  mov     [rbp+3Fh+var_B0], eax
0x14002f6c5  jnz     short loc_14002F6E4
0x14002f6c7  test    bl, 1
0x14002f6ca  jnz     loc_14002F86C
0x14002f6d0  call    cs:__imp_KeGetCurrentIrql
0x14002f6d7  nop     dword ptr [rax+rax+00h]
0x14002f6dc  cmp     al, 2
0x14002f6de  jz      loc_14002F86C
0x14002f6e4  mov     eax, cs:Size
0x14002f6ea  lea     r12, [rbp+47h]
0x14002f6ee  mov     dword ptr [rbp+3Fh+arg_20], eax
0x14002f6f1  xor     r13d, r13d
0x14002f6f4  mov     [rbp+3Fh+LowLimit], r13
0x14002f6f8  mov     [rbp+3Fh+HighLimit], r13
0x14002f6fc  mov     eax, gs:1A4h
0x14002f704  shl     eax, 0Ch
0x14002f707  mov     ecx, eax
0x14002f709  mov     rax, cs:qword_14011CF78
0x14002f710  mov     rdx, [rcx+rax]
0x14002f714  mov     rax, cs:qword_14011CF70
0x14002f71b  mov     [rbp+3Fh+LowLimit], rdx
0x14002f71f  mov     r8, [rcx+rax]
0x14002f723  mov     [rbp+3Fh+HighLimit], r8
0x14002f727  cmp     r12, r8
0x14002f72a  jb      loc_14002FA39
0x14002f730  lea     rdx, [rbp+3Fh+HighLimit]; HighLimit
0x14002f734  lea     rcx, [rbp+3Fh+LowLimit]; LowLimit
0x14002f738  call    cs:__imp_IoGetStackLimits
0x14002f73f  nop     dword ptr [rax+rax+00h]
0x14002f744  mov     rdx, [rbp+3Fh+LowLimit]
0x14002f748  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x14002f74b  sub     r12, rdx
0x14002f74e  cmp     r12, rax
0x14002f751  jb      short loc_14002F7B6
0x14002f753  cmp     cs:byte_14011D730, r13b
0x14002f75a  jnz     loc_14002FB93
0x14002f760  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14002f767  test    rax, rax
0x14002f76a  jz      loc_14002F68E
0x14002f770  cmp     byte ptr [rdi], 5
0x14002f773  jnz     loc_14002F68E
0x14002f779  mov     rdx, [rdi+308h]
0x14002f780  test    rdx, rdx
0x14002f783  jz      loc_14002F68E
0x14002f789  mov     rcx, [rbp+3Fh+arg_30]
0x14002f78d  mov     r9d, r14d
0x14002f790  mov     rax, [rax+70h]
0x14002f794  mov     r8d, r15d
0x14002f797  mov     [rsp+100h+var_D0], rcx
0x14002f79c  mov     rcx, [rbp+3Fh+arg_28]
0x14002f7a0  mov     [rsp+100h+var_D8], rdx
0x14002f7a5  mov     rdx, rsi
0x14002f7a8  mov     dword ptr [rsp+100h+Context], ebx
0x14002f7ac  call    _guard_dispatch_icall
0x14002f7b1  jmp     loc_14002F6A8
0x14002f7b6  mov     rax, [rbp+3Fh+arg_28]
0x14002f7ba  mov     ecx, 6000h
0x14002f7bf  mov     qword ptr [rbp+3Fh+Parameter+8], rax
0x14002f7c3  mov     rax, [rbp+3Fh+arg_30]
0x14002f7c7  mov     qword ptr [rbp+3Fh+var_98], rax
0x14002f7cb  mov     eax, cs:Size
0x14002f7d1  mov     [rbp+3Fh+var_7C], r13d
0x14002f7d5  mov     qword ptr [rbp+3Fh+Parameter], rdi
0x14002f7d9  mov     qword ptr [rbp+3Fh+var_98+8], rsi
0x14002f7dd  mov     dword ptr [rbp+3Fh+var_88+4], r14d
0x14002f7e1  mov     dword ptr [rbp+3Fh+var_88], r15d
0x14002f7e5  mov     [rbp+3Fh+var_80], ebx
0x14002f7e8  cmp     eax, ecx
0x14002f7ea  ja      loc_14002FE42
0x14002f7f0  movsxd  r8, ecx; Size
0x14002f7f3  lea     rdx, [rbp+3Fh+Parameter]; Parameter
0x14002f7f7  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x14002f7fe  mov     [rsp+100h+Context], r13; Context
0x14002f803  xor     r9d, r9d; Wait
0x14002f806  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14002f80d  nop     dword ptr [rax+rax+00h]
0x14002f812  test    eax, eax
0x14002f814  jns     loc_14002F6A8
0x14002f81a  cmp     cs:byte_14011D730, r13b
0x14002f821  jnz     loc_14002FE4D
0x14002f827  mov     edx, 0C000009Ah; int
0x14002f82c  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14002f82f  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x14002f834  mov     rax, rsi
0x14002f837  test    rsi, rsi
0x14002f83a  jz      short loc_14002F847
0x14002f83c  mov     rax, [rax]
0x14002f83f  inc     r13d
0x14002f842  test    rax, rax
0x14002f845  jnz     short loc_14002F83C
0x14002f847  lock add [rdi+124h], r13d
0x14002f84f  cmp     [rbp+3Fh+var_B0], 0
0x14002f853  jnz     loc_14002F6A8
0x14002f859  xor     r8d, r8d; unsigned __int8
0x14002f85c  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14002f85f  mov     rcx, rdi; struct _NDIS_FILTER_BLOCK *
0x14002f862  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x14002f867  jmp     loc_14002F6A8
0x14002f86c  mov     eax, gs:1A4h
0x14002f874  lea     r12, [rbp+3Fh+var_60]
0x14002f878  mov     rcx, [rsi]
0x14002f87b  xor     r13d, r13d
0x14002f87e  mov     r10, [rbp+3Fh+arg_30]
0x14002f882  mov     r11, [rbp+3Fh+arg_28]
0x14002f886  mov     [rbp+3Fh+var_B8], r10
0x14002f88a  mov     [rsp+100h+var_C0], r11
0x14002f88f  mov     dword ptr [rbp+3Fh+arg_20], eax
0x14002f892  mov     [rbp+3Fh+var_50], r13
0x14002f896  mov     [rbp+3Fh+var_60], rsi
0x14002f89a  mov     [rbp+3Fh+var_58], rsi
0x14002f89e  mov     [rsi+70h], r13
0x14002f8a2  mov     [rsi+84h], ebx
0x14002f8a8  mov     [rsi+8Ch], r15d
0x14002f8af  test    rcx, rcx
0x14002f8b2  jz      short loc_14002F8B8
0x14002f8b4  mov     [rcx+70h], r14
0x14002f8b8  cmp     byte ptr [rdi], 5
0x14002f8bb  jnz     loc_14002F9AC
0x14002f8c1  mov     rbx, [r12]
0x14002f8c5  test    rbx, rbx
0x14002f8c8  jz      loc_14002F9AC
0x14002f8ce  lea     rcx, [rax+rax*2]
0x14002f8d2  mov     rax, [rdi+1A8h]
0x14002f8d9  add     rax, 30h ; '0'
0x14002f8dd  shl     rcx, 5
0x14002f8e1  add     rax, rcx
0x14002f8e4  mov     [rbp+3Fh+var_68], rax
0x14002f8e8  cmp     [rax+10h], r13b
0x14002f8ec  jnz     loc_14002FA47
0x14002f8f2  mov     byte ptr [rax+10h], 1
0x14002f8f6  mov     rcx, rdi
0x14002f8f9  mov     rbx, [r12]
0x14002f8fd  mov     [r12], r13
0x14002f901  test    rbx, rbx
0x14002f904  jz      short loc_14002F97F
0x14002f906  mov     rax, [rbx]
0x14002f909  mov     rsi, [rbx+70h]
0x14002f90d  mov     r14d, [rbx+84h]
0x14002f914  mov     r15d, [rbx+8Ch]
0x14002f91b  test    rax, rax
0x14002f91e  jnz     loc_14002FA2A
0x14002f924  mov     r12d, 1
0x14002f92a  mov     [rbx+84h], r13d
0x14002f931  cmp     cs:byte_14011D730, r13b
0x14002f938  jnz     loc_14002FAC4
0x14002f93e  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14002f945  test    rax, rax
0x14002f948  jnz     loc_14002FD76
0x14002f94e  mov     r9d, r12d
0x14002f951  mov     dword ptr [rsp+100h+Context], r14d
0x14002f956  mov     r8d, r15d
0x14002f959  mov     rdx, rbx
0x14002f95c  mov     rcx, r11
0x14002f95f  mov     rax, r10
0x14002f962  call    _guard_dispatch_icall
0x14002f967  mov     r10, [rbp+3Fh+var_B8]
0x14002f96b  mov     rbx, rsi
0x14002f96e  mov     r11, [rsp+100h+var_C0]
0x14002f973  test    rsi, rsi
0x14002f976  jnz     short loc_14002F906
0x14002f978  mov     rax, [rbp+3Fh+var_68]
0x14002f97c  mov     rcx, rdi
0x14002f97f  mov     [rax+10h], r13b
0x14002f983  mov     r12, rax
0x14002f986  mov     r10, [rcx+1F0h]
0x14002f98d  mov     r11, [rcx+1F8h]
0x14002f994  mov     rdi, [rdi+208h]
0x14002f99b  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x14002f99e  mov     [rbp+3Fh+var_B8], r10
0x14002f9a2  mov     [rsp+100h+var_C0], r11
0x14002f9a7  jmp     loc_14002F8B8
0x14002f9ac  mov     rbx, [r12]
0x14002f9b0  test    rbx, rbx
0x14002f9b3  jz      loc_14002F6A8
0x14002f9b9  mov     [r12], r13
0x14002f9bd  mov     rax, [rbx]
0x14002f9c0  mov     rsi, [rbx+70h]
0x14002f9c4  mov     r15d, [rbx+84h]
0x14002f9cb  mov     r12d, [rbx+8Ch]
0x14002f9d2  test    rax, rax
0x14002f9d5  jnz     short loc_14002FA33
0x14002f9d7  mov     r14d, 1
0x14002f9dd  mov     [rbx+84h], r13d
0x14002f9e4  cmp     cs:byte_14011D730, r13b
0x14002f9eb  jnz     loc_14002FC62
0x14002f9f1  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14002f9f8  test    rax, rax
0x14002f9fb  jnz     loc_14002FDB8
0x14002fa01  mov     rcx, [rsp+100h+var_C0]
0x14002fa06  mov     r9d, r14d
0x14002fa09  mov     rax, [rbp+3Fh+var_B8]
0x14002fa0d  mov     r8d, r12d
0x14002fa10  mov     rdx, rbx
0x14002fa13  mov     dword ptr [rsp+100h+Context], r15d
0x14002fa18  call    _guard_dispatch_icall
0x14002fa1d  mov     rbx, rsi
0x14002fa20  test    rsi, rsi
0x14002fa23  jnz     short loc_14002F9BD
0x14002fa25  jmp     loc_14002F6A8
0x14002fa2a  mov     r12d, [rax+70h]
0x14002fa2e  jmp     loc_14002F92A
0x14002fa33  mov     r14d, [rax+70h]
0x14002fa37  jmp     short loc_14002F9DD
0x14002fa39  cmp     rdx, r12
0x14002fa3c  jbe     loc_14002F748
0x14002fa42  jmp     loc_14002F730
0x14002fa47  mov     [r12], r13
0x14002fa4b  mov     rax, [rbx]
0x14002fa4e  mov     ecx, [rbx+8Ch]
0x14002fa54  mov     rsi, [rbx+70h]
0x14002fa58  mov     r15d, [rbx+84h]
0x14002fa5f  mov     dword ptr [rbp+3Fh+arg_20], ecx
0x14002fa62  test    rax, rax
0x14002fa65  jnz     loc_14002FC59
0x14002fa6b  mov     r14d, 1
0x14002fa71  mov     [rbx+84h], r13d
0x14002fa78  cmp     cs:byte_14011D730, r13b
0x14002fa7f  jnz     loc_14002FD2C
0x14002fa85  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x14002fa8c  test    rax, rax
0x14002fa8f  jnz     loc_14002FE00
0x14002fa95  mov     r8d, ecx
0x14002fa98  mov     dword ptr [rsp+100h+Context], r15d
0x14002fa9d  mov     rcx, r11
0x14002faa0  mov     r9d, r14d
0x14002faa3  mov     rdx, rbx
0x14002faa6  mov     rax, r10
0x14002faa9  call    _guard_dispatch_icall
0x14002faae  mov     r10, [rbp+3Fh+var_B8]
0x14002fab2  mov     rbx, rsi
0x14002fab5  mov     r11, [rsp+100h+var_C0]
0x14002faba  test    rsi, rsi
0x14002fabd  jnz     short loc_14002FA4B
0x14002fabf  jmp     loc_14002F9AC
0x14002fac4  cmp     byte ptr [rdi], 5
0x14002fac7  jnz     loc_14002F93E
0x14002facd  mov     rax, [rdi+368h]
0x14002fad4  test    rax, rax
0x14002fad7  jz      loc_14002F93E
0x14002fadd  mov     eax, [rax+38h]
0x14002fae0  test    al, 1
0x14002fae2  jz      loc_14002F93E
0x14002fae8  xor     eax, eax
0x14002faea  xorps   xmm0, xmm0
0x14002faed  test    dword ptr [rbx+80h], 8000h
0x14002faf7  movups  [rbp+3Fh+Parameter], xmm0
0x14002fafb  mov     dword ptr [rbp+3Fh+var_88], eax
0x14002fafe  movups  [rbp+3Fh+var_98], xmm0
0x14002fb02  jnz     loc_14002F93E
0x14002fb08  mov     eax, [rdi+370h]
0x14002fb0e  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x14002fb15  mov     [rbp+3Fh+var_B0], eax
0x14002fb18  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14002fb1f  nop     dword ptr [rax+rax+00h]
0x14002fb24  test    al, al
0x14002fb26  jz      short loc_14002FB85
0x14002fb28  mov     rdx, [rdi+360h]
0x14002fb2f  lea     r8, [rbp+3Fh+Parameter]
0x14002fb33  mov     rcx, qword ptr cs:xmmword_14011D750
0x14002fb3a  mov     eax, 28h ; '('
0x14002fb3f  mov     word ptr [rbp+3Fh+Parameter], ax
0x14002fb43  xor     r9d, r9d
0x14002fb46  mov     eax, [rbp+3Fh+var_B0]
0x14002fb49  mov     dword ptr [rbp+3Fh+var_98+4], eax
  ... truncated ...
```
