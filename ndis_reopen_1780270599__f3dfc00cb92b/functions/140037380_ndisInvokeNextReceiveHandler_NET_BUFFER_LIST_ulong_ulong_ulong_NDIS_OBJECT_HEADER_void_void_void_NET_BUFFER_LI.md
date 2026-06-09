# ndisInvokeNextReceiveHandler(_NET_BUFFER_LIST *,ulong,ulong,ulong,_NDIS_OBJECT_HEADER *,void *,void (*)(void *,_NET_BUFFER_LIST *,ulong,ulong,ulong))

- ea: `0x140037380`
- end: `0x140037ba2`
- name: `?ndisInvokeNextReceiveHandler@@YAXPEAU_NET_BUFFER_LIST@@KKKPEAU_NDIS_OBJECT_HEADER@@PEAXP6AX20KKK@Z@Z`
- size: `2082`
- prototype: `void __usercall(struct _NET_BUFFER_LIST *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, struct _NDIS_OBJECT_HEADER *, void *, void (*)(void *, struct _NET_BUFFER_LIST *, unsigned int, unsigned int, unsigned int))`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140036490`
- `0x140039140`

## callees

- `0x1400334f0`
- `0x140037380`
- `0x140037bd0`
- `0x140038090`
- `0x14003a0e0`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400373f0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400373f0`
- `ntoskrnl!IoGetStackLimits` at `0x140037458`
- `ntoskrnl!IoGetStackLimits` at `0x140037458`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140037526`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140037526`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140037838`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140037905`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400379d6`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140037838`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140037905`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400379d6`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037899`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037968`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037a3b`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037899`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037968`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140037a3b`

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
          if ( byte_140123720 )
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
          if ( byte_140123720 )
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
                      (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                  + 40LL))(
                        xmmword_140123740,
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
        if ( byte_140123720 )
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
                    (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                                + 40LL))(
                      xmmword_140123740,
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
    v15 = *(_QWORD *)(v14 + qword_140122F78);
    LowLimit = v15;
    HighLimit = *(_QWORD *)(v14 + qword_140122F70);
    if ( (unsigned __int64)&retaddr >= HighLimit || v15 > (unsigned __int64)&retaddr )
    {
      IoGetStackLimits(&LowLimit, &HighLimit);
      v15 = LowLimit;
    }
    if ( (unsigned __int64)&retaddr - v15 >= v66 )
    {
      if ( byte_140123720 )
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
                  (*(void (__fastcall **)(_QWORD, __int64, __int128 *, _QWORD))(*((_QWORD *)&xmmword_140123740 + 1)
                                                                              + 40LL))(
                    xmmword_140123740,
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
      if ( byte_140123720 && (*(_DWORD *)&p_Header[210] & 2) != 0 )
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
0x140037380  push    rbp
0x140037382  push    rbx
0x140037383  push    rsi
0x140037384  push    rdi
0x140037385  push    r12
0x140037387  push    r13
0x140037389  push    r14
0x14003738b  push    r15
0x14003738d  lea     rbp, [rsp-7]
0x140037392  sub     rsp, 0C8h
0x140037399  mov     rdi, [rbp+3Fh+arg_20]
0x14003739d  mov     ebx, r9d
0x1400373a0  mov     r14d, r8d
0x1400373a3  mov     r15d, edx
0x1400373a6  mov     rsi, rcx
0x1400373a9  cmp     byte ptr [rdi], 11h
0x1400373ac  jnz     short loc_1400373DD
0x1400373ae  mov     rcx, [rbp+3Fh+arg_28]
0x1400373b2  mov     r9d, r14d
0x1400373b5  mov     rax, [rbp+3Fh+arg_30]
0x1400373b9  mov     r8d, r15d
0x1400373bc  mov     rdx, rsi
0x1400373bf  mov     dword ptr [rsp+100h+Context], ebx
0x1400373c3  call    _guard_dispatch_icall
0x1400373c8  add     rsp, 0C8h
0x1400373cf  pop     r15
0x1400373d1  pop     r14
0x1400373d3  pop     r13
0x1400373d5  pop     r12
0x1400373d7  pop     rdi
0x1400373d8  pop     rsi
0x1400373d9  pop     rbx
0x1400373da  pop     rbp
0x1400373db  retn
0x1400373dd  mov     eax, ebx
0x1400373df  and     eax, 2
0x1400373e2  mov     [rbp+3Fh+var_B0], eax
0x1400373e5  jnz     short loc_140037404
0x1400373e7  test    bl, 1
0x1400373ea  jnz     loc_14003758C
0x1400373f0  call    cs:__imp_KeGetCurrentIrql
0x1400373f7  nop     dword ptr [rax+rax+00h]
0x1400373fc  cmp     al, 2
0x1400373fe  jz      loc_14003758C
0x140037404  mov     eax, cs:Size
0x14003740a  lea     r12, [rbp+47h]
0x14003740e  mov     dword ptr [rbp+3Fh+arg_20], eax
0x140037411  xor     r13d, r13d
0x140037414  mov     [rbp+3Fh+LowLimit], r13
0x140037418  mov     [rbp+3Fh+HighLimit], r13
0x14003741c  mov     eax, gs:1A4h
0x140037424  shl     eax, 0Ch
0x140037427  mov     ecx, eax
0x140037429  mov     rax, cs:qword_140122F78
0x140037430  mov     rdx, [rcx+rax]
0x140037434  mov     rax, cs:qword_140122F70
0x14003743b  mov     [rbp+3Fh+LowLimit], rdx
0x14003743f  mov     r8, [rcx+rax]
0x140037443  mov     [rbp+3Fh+HighLimit], r8
0x140037447  cmp     r12, r8
0x14003744a  jb      loc_140037759
0x140037450  lea     rdx, [rbp+3Fh+HighLimit]; HighLimit
0x140037454  lea     rcx, [rbp+3Fh+LowLimit]; LowLimit
0x140037458  call    cs:__imp_IoGetStackLimits
0x14003745f  nop     dword ptr [rax+rax+00h]
0x140037464  mov     rdx, [rbp+3Fh+LowLimit]
0x140037468  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x14003746b  sub     r12, rdx
0x14003746e  cmp     r12, rax
0x140037471  jb      short loc_1400374D6
0x140037473  cmp     cs:byte_140123720, r13b
0x14003747a  jnz     loc_1400378B3
0x140037480  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140037487  test    rax, rax
0x14003748a  jz      loc_1400373AE
0x140037490  cmp     byte ptr [rdi], 5
0x140037493  jnz     loc_1400373AE
0x140037499  mov     rdx, [rdi+308h]
0x1400374a0  test    rdx, rdx
0x1400374a3  jz      loc_1400373AE
0x1400374a9  mov     rcx, [rbp+3Fh+arg_30]
0x1400374ad  mov     r9d, r14d
0x1400374b0  mov     rax, [rax+70h]
0x1400374b4  mov     r8d, r15d
0x1400374b7  mov     [rsp+100h+var_D0], rcx
0x1400374bc  mov     rcx, [rbp+3Fh+arg_28]
0x1400374c0  mov     [rsp+100h+var_D8], rdx
0x1400374c5  mov     rdx, rsi
0x1400374c8  mov     dword ptr [rsp+100h+Context], ebx
0x1400374cc  call    _guard_dispatch_icall
0x1400374d1  jmp     loc_1400373C8
0x1400374d6  mov     rax, [rbp+3Fh+arg_28]
0x1400374da  mov     ecx, 6000h
0x1400374df  mov     qword ptr [rbp+3Fh+Parameter+8], rax
0x1400374e3  mov     rax, [rbp+3Fh+arg_30]
0x1400374e7  mov     qword ptr [rbp+3Fh+var_98], rax
0x1400374eb  mov     eax, cs:Size
0x1400374f1  mov     [rbp+3Fh+var_7C], r13d
0x1400374f5  mov     qword ptr [rbp+3Fh+Parameter], rdi
0x1400374f9  mov     qword ptr [rbp+3Fh+var_98+8], rsi
0x1400374fd  mov     dword ptr [rbp+3Fh+var_88+4], r14d
0x140037501  mov     dword ptr [rbp+3Fh+var_88], r15d
0x140037505  mov     [rbp+3Fh+var_80], ebx
0x140037508  cmp     eax, ecx
0x14003750a  ja      loc_140037B62
0x140037510  movsxd  r8, ecx; Size
0x140037513  lea     rdx, [rbp+3Fh+Parameter]; Parameter
0x140037517  lea     rcx, ??$ndisDataPathExpandStackCallback@$01$$A6AXPEAXPEAU_NET_BUFFER_LIST@@KKK@Z@@YAXPEAX@Z; Callout
0x14003751e  mov     [rsp+100h+Context], r13; Context
0x140037523  xor     r9d, r9d; Wait
0x140037526  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x14003752d  nop     dword ptr [rax+rax+00h]
0x140037532  test    eax, eax
0x140037534  jns     loc_1400373C8
0x14003753a  cmp     cs:byte_140123720, r13b
0x140037541  jnz     loc_140037B6D
0x140037547  mov     edx, 0C000009Ah; int
0x14003754c  mov     rcx, rsi; struct _NET_BUFFER_LIST *
0x14003754f  call    ?NdisSetStatusInNblChain@@YAXPEAU_NET_BUFFER_LIST@@H@Z; NdisSetStatusInNblChain(_NET_BUFFER_LIST *,int)
0x140037554  mov     rax, rsi
0x140037557  test    rsi, rsi
0x14003755a  jz      short loc_140037567
0x14003755c  mov     rax, [rax]
0x14003755f  inc     r13d
0x140037562  test    rax, rax
0x140037565  jnz     short loc_14003755C
0x140037567  lock add [rdi+124h], r13d
0x14003756f  cmp     [rbp+3Fh+var_B0], 0
0x140037573  jnz     loc_1400373C8
0x140037579  xor     r8d, r8d; unsigned __int8
0x14003757c  mov     rdx, rsi; struct _NET_BUFFER_LIST *
0x14003757f  mov     rcx, rdi; struct _NDIS_FILTER_BLOCK *
0x140037582  call    ?ndisQueueStackExpansionFallbackNbls@@YAXPEAU_NDIS_FILTER_BLOCK@@PEAU_NET_BUFFER_LIST@@E@Z; ndisQueueStackExpansionFallbackNbls(_NDIS_FILTER_BLOCK *,_NET_BUFFER_LIST *,uchar)
0x140037587  jmp     loc_1400373C8
0x14003758c  mov     eax, gs:1A4h
0x140037594  lea     r12, [rbp+3Fh+var_60]
0x140037598  mov     rcx, [rsi]
0x14003759b  xor     r13d, r13d
0x14003759e  mov     r10, [rbp+3Fh+arg_30]
0x1400375a2  mov     r11, [rbp+3Fh+arg_28]
0x1400375a6  mov     [rbp+3Fh+var_B8], r10
0x1400375aa  mov     [rsp+100h+var_C0], r11
0x1400375af  mov     dword ptr [rbp+3Fh+arg_20], eax
0x1400375b2  mov     [rbp+3Fh+var_50], r13
0x1400375b6  mov     [rbp+3Fh+var_60], rsi
0x1400375ba  mov     [rbp+3Fh+var_58], rsi
0x1400375be  mov     [rsi+70h], r13
0x1400375c2  mov     [rsi+84h], ebx
0x1400375c8  mov     [rsi+8Ch], r15d
0x1400375cf  test    rcx, rcx
0x1400375d2  jz      short loc_1400375D8
0x1400375d4  mov     [rcx+70h], r14
0x1400375d8  cmp     byte ptr [rdi], 5
0x1400375db  jnz     loc_1400376CC
0x1400375e1  mov     rbx, [r12]
0x1400375e5  test    rbx, rbx
0x1400375e8  jz      loc_1400376CC
0x1400375ee  lea     rcx, [rax+rax*2]
0x1400375f2  mov     rax, [rdi+1A8h]
0x1400375f9  add     rax, 30h ; '0'
0x1400375fd  shl     rcx, 5
0x140037601  add     rax, rcx
0x140037604  mov     [rbp+3Fh+var_68], rax
0x140037608  cmp     [rax+10h], r13b
0x14003760c  jnz     loc_140037767
0x140037612  mov     byte ptr [rax+10h], 1
0x140037616  mov     rcx, rdi
0x140037619  mov     rbx, [r12]
0x14003761d  mov     [r12], r13
0x140037621  test    rbx, rbx
0x140037624  jz      short loc_14003769F
0x140037626  mov     rax, [rbx]
0x140037629  mov     rsi, [rbx+70h]
0x14003762d  mov     r14d, [rbx+84h]
0x140037634  mov     r15d, [rbx+8Ch]
0x14003763b  test    rax, rax
0x14003763e  jnz     loc_14003774A
0x140037644  mov     r12d, 1
0x14003764a  mov     [rbx+84h], r13d
0x140037651  cmp     cs:byte_140123720, r13b
0x140037658  jnz     loc_1400377E4
0x14003765e  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140037665  test    rax, rax
0x140037668  jnz     loc_140037A96
0x14003766e  mov     r9d, r12d
0x140037671  mov     dword ptr [rsp+100h+Context], r14d
0x140037676  mov     r8d, r15d
0x140037679  mov     rdx, rbx
0x14003767c  mov     rcx, r11
0x14003767f  mov     rax, r10
0x140037682  call    _guard_dispatch_icall
0x140037687  mov     r10, [rbp+3Fh+var_B8]
0x14003768b  mov     rbx, rsi
0x14003768e  mov     r11, [rsp+100h+var_C0]
0x140037693  test    rsi, rsi
0x140037696  jnz     short loc_140037626
0x140037698  mov     rax, [rbp+3Fh+var_68]
0x14003769c  mov     rcx, rdi
0x14003769f  mov     [rax+10h], r13b
0x1400376a3  mov     r12, rax
0x1400376a6  mov     r10, [rcx+1F0h]
0x1400376ad  mov     r11, [rcx+1F8h]
0x1400376b4  mov     rdi, [rdi+208h]
0x1400376bb  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x1400376be  mov     [rbp+3Fh+var_B8], r10
0x1400376c2  mov     [rsp+100h+var_C0], r11
0x1400376c7  jmp     loc_1400375D8
0x1400376cc  mov     rbx, [r12]
0x1400376d0  test    rbx, rbx
0x1400376d3  jz      loc_1400373C8
0x1400376d9  mov     [r12], r13
0x1400376dd  mov     rax, [rbx]
0x1400376e0  mov     rsi, [rbx+70h]
0x1400376e4  mov     r15d, [rbx+84h]
0x1400376eb  mov     r12d, [rbx+8Ch]
0x1400376f2  test    rax, rax
0x1400376f5  jnz     short loc_140037753
0x1400376f7  mov     r14d, 1
0x1400376fd  mov     [rbx+84h], r13d
0x140037704  cmp     cs:byte_140123720, r13b
0x14003770b  jnz     loc_140037982
0x140037711  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x140037718  test    rax, rax
0x14003771b  jnz     loc_140037AD8
0x140037721  mov     rcx, [rsp+100h+var_C0]
0x140037726  mov     r9d, r14d
0x140037729  mov     rax, [rbp+3Fh+var_B8]
0x14003772d  mov     r8d, r12d
0x140037730  mov     rdx, rbx
0x140037733  mov     dword ptr [rsp+100h+Context], r15d
0x140037738  call    _guard_dispatch_icall
0x14003773d  mov     rbx, rsi
0x140037740  test    rsi, rsi
0x140037743  jnz     short loc_1400376DD
0x140037745  jmp     loc_1400373C8
0x14003774a  mov     r12d, [rax+70h]
0x14003774e  jmp     loc_14003764A
0x140037753  mov     r14d, [rax+70h]
0x140037757  jmp     short loc_1400376FD
0x140037759  cmp     rdx, r12
0x14003775c  jbe     loc_140037468
0x140037762  jmp     loc_140037450
0x140037767  mov     [r12], r13
0x14003776b  mov     rax, [rbx]
0x14003776e  mov     ecx, [rbx+8Ch]
0x140037774  mov     rsi, [rbx+70h]
0x140037778  mov     r15d, [rbx+84h]
0x14003777f  mov     dword ptr [rbp+3Fh+arg_20], ecx
0x140037782  test    rax, rax
0x140037785  jnz     loc_140037979
0x14003778b  mov     r14d, 1
0x140037791  mov     [rbx+84h], r13d
0x140037798  cmp     cs:byte_140123720, r13b
0x14003779f  jnz     loc_140037A4C
0x1400377a5  mov     rax, cs:?ndisVerifierNdisDispatch@@3PEAU_VF_NDIS_DISPATCH_TABLE@@EA; _VF_NDIS_DISPATCH_TABLE * ndisVerifierNdisDispatch
0x1400377ac  test    rax, rax
0x1400377af  jnz     loc_140037B20
0x1400377b5  mov     r8d, ecx
0x1400377b8  mov     dword ptr [rsp+100h+Context], r15d
0x1400377bd  mov     rcx, r11
0x1400377c0  mov     r9d, r14d
0x1400377c3  mov     rdx, rbx
0x1400377c6  mov     rax, r10
0x1400377c9  call    _guard_dispatch_icall
0x1400377ce  mov     r10, [rbp+3Fh+var_B8]
0x1400377d2  mov     rbx, rsi
0x1400377d5  mov     r11, [rsp+100h+var_C0]
0x1400377da  test    rsi, rsi
0x1400377dd  jnz     short loc_14003776B
0x1400377df  jmp     loc_1400376CC
0x1400377e4  cmp     byte ptr [rdi], 5
0x1400377e7  jnz     loc_14003765E
0x1400377ed  mov     rax, [rdi+368h]
0x1400377f4  test    rax, rax
0x1400377f7  jz      loc_14003765E
0x1400377fd  mov     eax, [rax+38h]
0x140037800  test    al, 1
0x140037802  jz      loc_14003765E
0x140037808  xor     eax, eax
0x14003780a  xorps   xmm0, xmm0
0x14003780d  test    dword ptr [rbx+80h], 8000h
0x140037817  movups  [rbp+3Fh+Parameter], xmm0
0x14003781b  mov     dword ptr [rbp+3Fh+var_88], eax
0x14003781e  movups  [rbp+3Fh+var_98], xmm0
0x140037822  jnz     loc_14003765E
0x140037828  mov     eax, [rdi+370h]
0x14003782e  mov     rcx, cs:RunRefCacheAware; RunRefCacheAware
0x140037835  mov     [rbp+3Fh+var_B0], eax
0x140037838  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x14003783f  nop     dword ptr [rax+rax+00h]
0x140037844  test    al, al
0x140037846  jz      short loc_1400378A5
0x140037848  mov     rdx, [rdi+360h]
0x14003784f  lea     r8, [rbp+3Fh+Parameter]
0x140037853  mov     rcx, qword ptr cs:xmmword_140123740
0x14003785a  mov     eax, 28h ; '('
0x14003785f  mov     word ptr [rbp+3Fh+Parameter], ax
0x140037863  xor     r9d, r9d
0x140037866  mov     eax, [rbp+3Fh+var_B0]
0x140037869  mov     dword ptr [rbp+3Fh+var_98+4], eax
  ... truncated ...
```
