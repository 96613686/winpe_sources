# CImpIAccessor::GetBindings(unsigned __int64,ulong *,unsigned __int64 *,tagDBBINDING * *)

- ea: `0x18000db80`
- end: `0x18000e123`
- name: `?GetBindings@CImpIAccessor@@UEAAJ_KPEAKPEA_KPEAPEAUtagDBBINDING@@@Z`
- size: `1443`
- prototype: `__int64 __fastcall(CImpIAccessor *__hidden this, unsigned __int64, unsigned int *, unsigned __int64 *, struct tagDBBINDING **)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x180003030`
- `0x1800030c0`
- `0x180003d80`
- `0x180008c80`
- `0x180009340`
- `0x18000db80`
- `0x18005ce20`
- `0x18013f360`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000de93`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df2b`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000de93`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000df2b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000de9f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000df37`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000de9f`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000df37`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000dcd0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000dcd0`

## string_xrefs

- `0x18000dc50`: `IAccessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CImpIAccessor::GetBindings(
        CImpIAccessor *this,
        unsigned __int64 a2,
        unsigned int *a3,
        unsigned __int64 *a4,
        struct tagDBBINDING **a5)
{
  int v9; // esi
  char *v10; // r14
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  _QWORD *v16; // rdx
  unsigned __int64 v17; // rcx
  __int64 v18; // r13
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  struct tagDBBINDING *v23; // rax
  size_t v24; // r8
  unsigned int v25; // ebx
  __int64 v26; // rax
  __int64 v27; // r14
  __int64 v28; // rax
  DBOBJECT *v29; // rbp
  DBOBJECT *pObject; // rcx
  __int64 v31; // rsi
  wchar_t *v32; // r8
  __int64 v33; // rdx
  __int64 v36; // [rsp+48h] [rbp-110h]
  _QWORD v37[2]; // [rsp+50h] [rbp-108h] BYREF
  wchar_t v38[80]; // [rsp+60h] [rbp-F8h] BYREF

  v37[0] = -1;
  if ( (bidGblFlags & 4) != 0 && off_1802662D0[0] )
    bidScopeEnterW(v37, off_1802662D0[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  if ( (bidGblFlags & 0x40002) == 0x40002
    && (unsigned int)ConstrBidActID(v38, 0x50u)
    && (bidGblFlags & 2) != 0
    && off_180262DC8[0] )
  {
    bidTraceW(off_1802601F0[0], 1945600, off_180262DC8[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL));
  }
  v9 = 0;
  v10 = (char *)this + 192;
  if ( this == (CImpIAccessor *)-192LL )
  {
    v36 = 0;
  }
  else
  {
    if ( *(_QWORD *)v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v10 + 32LL) + 8LL))(*(_QWORD *)v10 + 32LL);
    v36 = *(_QWORD *)v10;
  }
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a3 )
    *a3 = 0;
  SetErrorInfo(0, 0);
  v11 = *((_QWORD *)this + 1);
  if ( *(_DWORD *)(v11 + 8) == 6 )
  {
    if ( (*(_DWORD *)(v11 + 344) & 0x1000) != 0
      || *(_DWORD *)(v11 + 632) != *(_DWORD *)(*(_QWORD *)(v11 + 64) + 940LL)
      && (unsigned int)CRowset::FMakeZombie((CRowset *)v11) )
    {
      v9 = -2147418113;
      if ( (bidGblFlags & 2) != 0 )
        v14 = bidTraceHR(off_1802601F0[0], 1970185, 2147549183LL);
      else
        v14 = -2147418113;
      CError::PostError(g_pCError, v14, &IID_IAccessor, 0x9F07u, 0);
      goto LABEL_83;
    }
    v12 = *(_QWORD *)(*((_QWORD *)this + 1) + 624LL);
    if ( v12 )
    {
      if ( *(_DWORD *)(v12 + 144) )
      {
        v9 = -2147217842;
        if ( (bidGblFlags & 2) != 0 )
          v13 = bidTraceHR(off_1802601F0[0], 1970185, 2147749454LL);
        else
          v13 = -2147217842;
        CError::PostHResult(g_pCError, v13, &IID_IAccessor);
        goto LABEL_83;
      }
    }
  }
  if ( !a3 || !a4 || !a5 )
  {
    if ( (bidGblFlags & 2) != 0 )
      v19 = bidTraceHR(off_1802601F0[0], 1975305, 2147942487LL);
    else
      v19 = -2147024809;
    goto LABEL_75;
  }
  v15 = *((_QWORD *)this + 3);
  v16 = *(_QWORD **)(v15 + 32);
  v17 = 0;
  if ( a2 < *(_QWORD *)(v15 + 8) )
    v17 = a2;
  v18 = v16[v17];
  if ( v18 == *v16 )
  {
    v19 = *((_DWORD *)this + 13);
    if ( (bidGblFlags & 2) != 0 )
    {
      v20 = v19;
      v21 = 1988617;
      goto LABEL_42;
    }
    goto LABEL_75;
  }
  v22 = *(_QWORD *)(v18 + 56);
  if ( !v22 )
    goto LABEL_60;
  if ( is_mul_ok(v22, 0x58u) )
  {
    v23 = (struct tagDBBINDING *)((__int64 (__fastcall *)(LPMALLOC, unsigned __int64))g_pIMalloc->lpVtbl->Alloc)(
                                   g_pIMalloc,
                                   88 * v22);
    *a5 = v23;
    if ( v23 )
    {
      v24 = 88LL * *(_QWORD *)(v18 + 56);
      if ( v24 )
      {
        if ( v18 == -64 )
        {
          memset_0(v23, 0, v24);
          *_errno() = 22;
          _invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v23, (const void *)(v18 + 64), v24);
        }
      }
      v25 = 0;
      v22 = *(_QWORD *)(v18 + 56);
      if ( v22 )
      {
        v26 = 0;
        do
        {
          v27 = v26;
          (*a5)[v27].pTypeInfo = 0;
          (*a5)[v27].dwFlags &= ~0x80000000;
          if ( (*a5)[v26].pObject )
          {
            v28 = ((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 20);
            v29 = (DBOBJECT *)v28;
            if ( !v28 )
            {
              if ( v25 )
              {
                v31 = v25;
                do
                {
                  --v25;
                  if ( (*a5)[--v31].pObject )
                    ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Free)(g_pIMalloc);
                }
                while ( v25 );
              }
              ((void (__fastcall *)(LPMALLOC, _QWORD))g_pIMalloc->lpVtbl->Free)(g_pIMalloc, *a5);
              *a5 = 0;
              if ( (bidGblFlags & 2) != 0 )
              {
                v21 = 2039817;
                v20 = 2147942414LL;
                goto LABEL_42;
              }
LABEL_68:
              v19 = -2147024882;
              goto LABEL_75;
            }
            pObject = (*a5)[v27].pObject;
            if ( pObject )
            {
              *(_OWORD *)v28 = *(_OWORD *)&pObject->dwFlags;
              *(_DWORD *)(v28 + 16) = *(_DWORD *)&pObject->iid.Data4[4];
            }
            else
            {
              *(_OWORD *)v28 = 0;
              *(_DWORD *)(v28 + 16) = 0;
              *_errno() = 22;
              _invalid_parameter_noinfo();
            }
            (*a5)[v27].pObject = v29;
          }
          v26 = ++v25;
          v22 = *(_QWORD *)(v18 + 56);
        }
        while ( v25 < v22 );
      }
LABEL_60:
      *a4 = v22;
      *a3 = *(_DWORD *)(v18 + 24) & 0xFFFF7FFF;
      goto LABEL_76;
    }
  }
  else
  {
    *a5 = 0;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_68;
  v21 = 2002953;
  v20 = 2147942414LL;
LABEL_42:
  v19 = bidTraceHR(off_1802601F0[0], v21, v20);
LABEL_75:
  v9 = CError::PostHResult(g_pCError, v19, &IID_IAccessor);
LABEL_76:
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_83;
  if ( v9 < 0 )
  {
    if ( !off_180262DD8[0] )
      goto LABEL_83;
    _mm_lfence();
    v32 = off_180262DD8[0];
    v33 = 2061312;
  }
  else
  {
    if ( !off_180262DD0[0] )
      goto LABEL_83;
    _mm_lfence();
    v32 = off_180262DD0[0];
    v33 = 2057216;
  }
  bidTraceW(off_1802601F0[0], v33, v32, (unsigned int)v9);
LABEL_83:
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v36 + 32) + 24LL))(v36 + 32);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)v37);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000db80  push    rbx
0x18000db82  push    rbp
0x18000db83  push    rsi
0x18000db84  push    rdi
0x18000db85  push    r12
0x18000db87  push    r13
0x18000db89  push    r14
0x18000db8b  push    r15
0x18000db8d  sub     rsp, 118h
0x18000db94  mov     rax, cs:__security_cookie
0x18000db9b  xor     rax, rsp
0x18000db9e  mov     [rsp+158h+var_58], rax
0x18000dba6  mov     r12, r9
0x18000dba9  mov     r13, r8
0x18000dbac  mov     [rsp+158h+var_118], r8
0x18000dbb1  mov     rbp, rdx
0x18000dbb4  mov     rbx, rcx
0x18000dbb7  mov     rdi, [rsp+158h+arg_20]
0x18000dbbf  mov     [rsp+158h+var_108], 0FFFFFFFFFFFFFFFFh
0x18000dbc8  test    byte ptr cs:_bidGblFlags, 4
0x18000dbcf  jz      short loc_18000DC08
0x18000dbd1  mov     rax, cs:off_1802662D0; "<IAccessor::GetBindings|OLEDB|API> %u#{"...
0x18000dbd8  test    rax, rax
0x18000dbdb  jz      short loc_18000DC08
0x18000dbdd  mov     r8, [rcx+8]
0x18000dbe1  mov     [rsp+158h+var_128], rdi
0x18000dbe6  mov     [rsp+158h+var_130], r9
0x18000dbeb  mov     [rsp+158h+var_138], r13
0x18000dbf0  mov     r9, rdx
0x18000dbf3  mov     r8d, [r8+34h]
0x18000dbf7  mov     rdx, cs:off_1802662D0; "<IAccessor::GetBindings|OLEDB|API> %u#{"...
0x18000dbfe  lea     rcx, [rsp+158h+var_108]
0x18000dc03  call    _bidScopeEnterW
0x18000dc08  mov     eax, cs:_bidGblFlags
0x18000dc0e  and     eax, 40002h
0x18000dc13  cmp     eax, 40002h
0x18000dc18  jnz     short loc_18000DC78
0x18000dc1a  mov     edx, 50h ; 'P'; unsigned __int64
0x18000dc1f  lea     rcx, [rsp+158h+var_F8]; wchar_t *
0x18000dc24  call    ?ConstrBidActID@@YAHPEA_W_K@Z; ConstrBidActID(wchar_t *,unsigned __int64)
0x18000dc29  test    eax, eax
0x18000dc2b  jz      short loc_18000DC78
0x18000dc2d  test    byte ptr cs:_bidGblFlags, 2
0x18000dc34  jz      short loc_18000DC78
0x18000dc36  mov     rax, cs:off_180262DC8; "<CImpIAccessor::GetBindings|OLEDB|DRIVE"...
0x18000dc3d  test    rax, rax
0x18000dc40  jz      short loc_18000DC78
0x18000dc42  mov     r9, [rbx+8]
0x18000dc46  lea     rax, [rsp+158h+var_F8]
0x18000dc4b  mov     [rsp+158h+var_130], rax
0x18000dc50  lea     rax, aIaccessor; "IAccessor"
0x18000dc57  mov     [rsp+158h+var_138], rax
0x18000dc5c  mov     r9d, [r9+34h]
0x18000dc60  mov     r8, cs:off_180262DC8; "<CImpIAccessor::GetBindings|OLEDB|DRIVE"...
0x18000dc67  mov     edx, 1DB000h
0x18000dc6c  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000dc73  call    _bidTraceW
0x18000dc78  xor     r15d, r15d
0x18000dc7b  mov     esi, r15d
0x18000dc7e  lea     r14, [rbx+0C0h]
0x18000dc85  test    r14, r14
0x18000dc88  jz      short loc_18000DCAD
0x18000dc8a  mov     rcx, [r14]
0x18000dc8d  test    rcx, rcx
0x18000dc90  jz      short loc_18000DCA3
0x18000dc92  add     rcx, 20h ; ' '
0x18000dc96  mov     rax, [rcx]
0x18000dc99  mov     rax, [rax+8]
0x18000dc9d  call    cs:__guard_dispatch_icall_fptr
0x18000dca3  mov     rax, [r14]
0x18000dca6  mov     [rsp+158h+var_110], rax
0x18000dcab  jmp     short loc_18000DCB2
0x18000dcad  mov     [rsp+158h+var_110], r15
0x18000dcb2  test    r12, r12
0x18000dcb5  jz      short loc_18000DCBB
0x18000dcb7  mov     [r12], r15
0x18000dcbb  test    rdi, rdi
0x18000dcbe  jz      short loc_18000DCC3
0x18000dcc0  mov     [rdi], r15
0x18000dcc3  test    r13, r13
0x18000dcc6  jz      short loc_18000DCCC
0x18000dcc8  mov     [r13+0], r15d
0x18000dccc  xor     edx, edx; perrinfo
0x18000dcce  xor     ecx, ecx; dwReserved
0x18000dcd0  call    cs:__imp_SetErrorInfo
0x18000dcd6  mov     rcx, [rbx+8]; this
0x18000dcda  cmp     dword ptr [rcx+8], 6
0x18000dcde  jnz     loc_18000DDB7
0x18000dce4  test    dword ptr [rcx+158h], 1000h
0x18000dcee  jnz     short loc_18000DD6C
0x18000dcf0  mov     rax, [rcx+40h]
0x18000dcf4  mov     edx, [rax+3ACh]
0x18000dcfa  cmp     [rcx+278h], edx
0x18000dd00  jz      short loc_18000DD0B
0x18000dd02  call    ?FMakeZombie@CRowset@@QEAAHXZ; CRowset::FMakeZombie(void)
0x18000dd07  test    eax, eax
0x18000dd09  jnz     short loc_18000DD6C
0x18000dd0b  mov     rax, [rbx+8]
0x18000dd0f  mov     rcx, [rax+270h]
0x18000dd16  test    rcx, rcx
0x18000dd19  jz      loc_18000DDB7
0x18000dd1f  cmp     dword ptr [rcx+90h], 0
0x18000dd26  jz      loc_18000DDB7
0x18000dd2c  mov     esi, 80040E4Eh
0x18000dd31  test    byte ptr cs:_bidGblFlags, 2
0x18000dd38  jz      short loc_18000DD50
0x18000dd3a  mov     r8d, esi
0x18000dd3d  mov     edx, 1E1009h
0x18000dd42  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000dd49  call    _bidTraceHR
0x18000dd4e  jmp     short loc_18000DD52
0x18000dd50  mov     eax, esi
0x18000dd52  lea     r8, IID_IAccessor; struct _GUID *
0x18000dd59  mov     edx, eax; int
0x18000dd5b  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000dd62  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18000dd67  jmp     loc_18000E0D6
0x18000dd6c  mov     esi, 8000FFFFh
0x18000dd71  test    byte ptr cs:_bidGblFlags, 2
0x18000dd78  jz      short loc_18000DD90
0x18000dd7a  mov     r8d, esi
0x18000dd7d  mov     edx, 1E1009h
0x18000dd82  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000dd89  call    _bidTraceHR
0x18000dd8e  jmp     short loc_18000DD92
0x18000dd90  mov     eax, esi
0x18000dd92  mov     [rsp+158h+var_138], r15; struct tagDISPPARAMS *
0x18000dd97  mov     r9d, 9F07h; unsigned int
0x18000dd9d  lea     r8, IID_IAccessor; struct _GUID *
0x18000dda4  mov     edx, eax; int
0x18000dda6  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000ddad  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x18000ddb2  jmp     loc_18000E0D6
0x18000ddb7  test    r13, r13
0x18000ddba  jz      loc_18000E004
0x18000ddc0  test    r12, r12
0x18000ddc3  jz      loc_18000E004
0x18000ddc9  test    rdi, rdi
0x18000ddcc  jz      loc_18000E004
0x18000ddd2  mov     rax, [rbx+18h]
0x18000ddd6  mov     rdx, [rax+20h]
0x18000ddda  mov     rcx, r15
0x18000dddd  cmp     rbp, [rax+8]
0x18000dde1  cmovb   rcx, rbp
0x18000dde5  mov     r13, [rdx+rcx*8]
0x18000dde9  cmp     r13, [rdx]
0x18000ddec  jnz     short loc_18000DE2D
0x18000ddee  mov     eax, [rbx+34h]
0x18000ddf1  test    byte ptr cs:_bidGblFlags, 2
0x18000ddf8  jz      short loc_18000DE0E
0x18000ddfa  mov     r8d, eax
0x18000ddfd  mov     edx, 1E5809h
0x18000de02  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000de09  call    _bidTraceHR
0x18000de0e  lea     r8, IID_IAccessor; struct _GUID *
0x18000de15  mov     edx, eax; int
0x18000de17  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000de1e  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18000de23  mov     r13, [rsp+158h+var_118]
0x18000de28  jmp     loc_18000E040
0x18000de2d  mov     rcx, [r13+38h]
0x18000de31  test    rcx, rcx
0x18000de34  jz      loc_18000DF56
0x18000de3a  mov     eax, 58h ; 'X'
0x18000de3f  mul     rcx
0x18000de42  mov     r8, rax
0x18000de45  test    rdx, rdx
0x18000de48  jnz     loc_18000DFE8
0x18000de4e  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x18000de55  mov     rdx, [rcx]
0x18000de58  mov     rax, [rdx+18h]
0x18000de5c  mov     rdx, r8
0x18000de5f  call    cs:__guard_dispatch_icall_fptr
0x18000de65  mov     [rdi], rax
0x18000de68  test    rax, rax
0x18000de6b  jz      loc_18000DFEB
0x18000de71  imul    r8, [r13+38h], 58h ; 'X'; Size
0x18000de76  lea     rdx, [r13+40h]; Src
0x18000de7a  test    r8, r8
0x18000de7d  jz      short loc_18000DEA5
0x18000de7f  mov     rcx, rax; void *
0x18000de82  test    rdx, rdx
0x18000de85  jz      short loc_18000DE8E
0x18000de87  call    memcpy_0
0x18000de8c  jmp     short loc_18000DEA5
0x18000de8e  call    memset_0
0x18000de93  call    cs:__imp__errno
0x18000de99  mov     dword ptr [rax], 16h
0x18000de9f  call    cs:__imp__invalid_parameter_noinfo
0x18000dea5  mov     ebx, r15d
0x18000dea8  mov     rcx, [r13+38h]
0x18000deac  test    rcx, rcx
0x18000deaf  jz      loc_18000DF56
0x18000deb5  mov     rax, r15
0x18000deb8  nop     dword ptr [rax+rax+00000000h]
0x18000dec0  imul    r14, rax, 58h ; 'X'
0x18000dec4  mov     rax, [rdi]
0x18000dec7  mov     [r14+rax+20h], r15
0x18000decc  mov     rax, [rdi]
0x18000decf  and     dword ptr [rax+r14+50h], 7FFFFFFFh
0x18000ded8  mov     rax, [rdi]
0x18000dedb  cmp     qword ptr [rax+r14+28h], 0
0x18000dee1  jz      short loc_18000DF45
0x18000dee3  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x18000deea  mov     rax, [rcx]
0x18000deed  mov     edx, 14h
0x18000def2  mov     rax, [rax+18h]
0x18000def6  call    cs:__guard_dispatch_icall_fptr
0x18000defc  mov     rbp, rax
0x18000deff  test    rax, rax
0x18000df02  jz      short loc_18000DF70
0x18000df04  mov     rcx, [rdi]
0x18000df07  mov     rcx, [rcx+r14+28h]
0x18000df0c  test    rcx, rcx
0x18000df0f  jz      short loc_18000DF1F
0x18000df11  movups  xmm0, xmmword ptr [rcx]
0x18000df14  movups  xmmword ptr [rax], xmm0
0x18000df17  mov     ecx, [rcx+10h]
0x18000df1a  mov     [rax+10h], ecx
0x18000df1d  jmp     short loc_18000DF3D
0x18000df1f  xorps   xmm0, xmm0
0x18000df22  xor     eax, eax
0x18000df24  movups  xmmword ptr [rbp+0], xmm0
0x18000df28  mov     [rbp+10h], eax
0x18000df2b  call    cs:__imp__errno
0x18000df31  mov     dword ptr [rax], 16h
0x18000df37  call    cs:__imp__invalid_parameter_noinfo
0x18000df3d  mov     rax, [rdi]
0x18000df40  mov     [rax+r14+28h], rbp
0x18000df45  inc     ebx
0x18000df47  mov     eax, ebx
0x18000df49  mov     rcx, [r13+38h]
0x18000df4d  cmp     rax, rcx
0x18000df50  jb      loc_18000DEC0
0x18000df56  mov     [r12], rcx
0x18000df5a  mov     eax, [r13+18h]
0x18000df5e  btr     eax, 0Fh
0x18000df62  mov     r13, [rsp+158h+var_118]
0x18000df67  mov     [r13+0], eax
0x18000df6b  jmp     loc_18000E042
0x18000df70  test    ebx, ebx
0x18000df72  jz      short loc_18000DFAB
0x18000df74  mov     eax, ebx
0x18000df76  imul    rsi, rax, 58h ; 'X'
0x18000df7a  nop     word ptr [rax+rax+00h]
0x18000df80  dec     ebx
0x18000df82  lea     rsi, [rsi-58h]
0x18000df86  mov     rax, [rdi]
0x18000df89  mov     rdx, [rax+rsi+28h]
0x18000df8e  test    rdx, rdx
0x18000df91  jz      short loc_18000DFA7
0x18000df93  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x18000df9a  mov     rax, [rcx]
0x18000df9d  mov     rax, [rax+28h]
0x18000dfa1  call    cs:__guard_dispatch_icall_fptr
0x18000dfa7  test    ebx, ebx
0x18000dfa9  jnz     short loc_18000DF80
0x18000dfab  mov     rcx, cs:?g_pIMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pIMalloc
0x18000dfb2  mov     rax, [rcx]
0x18000dfb5  mov     rdx, [rdi]
0x18000dfb8  mov     rax, [rax+28h]
0x18000dfbc  call    cs:__guard_dispatch_icall_fptr
0x18000dfc2  mov     [rdi], r15
0x18000dfc5  test    byte ptr cs:_bidGblFlags, 2
0x18000dfcc  jz      short loc_18000DFDE
0x18000dfce  mov     edx, 1F2009h
0x18000dfd3  mov     r8d, 8007000Eh
0x18000dfd9  jmp     loc_18000DE02
0x18000dfde  mov     eax, 8007000Eh
0x18000dfe3  jmp     loc_18000DE0E
0x18000dfe8  mov     [rdi], r15
0x18000dfeb  test    byte ptr cs:_bidGblFlags, 2
0x18000dff2  jz      short loc_18000DFDE
0x18000dff4  mov     edx, 1E9009h
0x18000dff9  mov     r8d, 8007000Eh
0x18000dfff  jmp     loc_18000DE02
0x18000e004  test    byte ptr cs:_bidGblFlags, 2
0x18000e00b  jz      short loc_18000E026
0x18000e00d  mov     edx, 1E2409h
0x18000e012  mov     r8d, 80070057h
0x18000e018  mov     rcx, cs:off_1802601F0; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x18000e01f  call    _bidTraceHR
0x18000e024  jmp     short loc_18000E02B
0x18000e026  mov     eax, 80070057h
0x18000e02b  lea     r8, IID_IAccessor; struct _GUID *
0x18000e032  mov     edx, eax; int
0x18000e034  mov     rcx, cs:?g_pCError@@3PEAVCError@@EA; this
0x18000e03b  call    ?PostHResult@CError@@QEAAJJPEBU_GUID@@@Z; CError::PostHResult(long,_GUID const *)
0x18000e040  mov     esi, eax
0x18000e042  test    byte ptr cs:_bidGblFlags, 2
0x18000e049  jz      loc_18000E0D6
0x18000e04f  test    esi, esi
0x18000e051  js      short loc_18000E08E
0x18000e053  mov     rax, cs:off_180262DD0; "<IAccessor::GetBindings|OLEDB|RET> %08X"...
0x18000e05a  test    rax, rax
0x18000e05d  jz      short loc_18000E0D6
0x18000e05f  lfence
0x18000e062  mov     rcx, [r12]
0x18000e066  mov     rax, [rdi]
0x18000e069  mov     [rsp+158h+var_120], rax
  ... truncated ...
```
