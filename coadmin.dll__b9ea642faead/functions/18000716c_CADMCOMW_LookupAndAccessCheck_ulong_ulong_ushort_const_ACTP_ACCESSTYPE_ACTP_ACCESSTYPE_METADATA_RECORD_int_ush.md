# CADMCOMW::LookupAndAccessCheck(ulong,ulong *,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,int *,ushort const * *,ABO_MAPPER_DISPOSITION *,int *)

- ea: `0x18000716c`
- end: `0x18000738d`
- name: `?LookupAndAccessCheck@CADMCOMW@@QEAAJKPEAKPEBGW4ACTP_ACCESSTYPE@@2PEAU_METADATA_RECORD@@PEAHPEAPEBGPEAW4ABO_MAPPER_DISPOSITION@@4@Z`
- size: `545`
- prototype: `__int64 __fastcall(CADMCOMW *, unsigned int, unsigned int *, __int64, unsigned int, int, __int64, __int64, _QWORD *, _DWORD *, __int64)`
- caller_count: `23`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002f70`
- `0x180003230`
- `0x180003400`
- `0x180003ca0`
- `0x180003ef0`
- `0x180003fd0`
- `0x1800041a0`
- `0x1800049a0`
- `0x180004c60`
- `0x180005290`
- `0x180005920`
- `0x180005a20`
- `0x180005bd0`
- `0x180005e90`
- `0x180006010`
- `0x1800062d0`
- `0x180008240`
- `0x1800087f0`
- `0x1800090f0`
- `0x180009200`
- `0x180009520`
- `0x18000de90`

## callees

- `0x180001cec`
- `0x180007068`
- `0x18000716c`
- `0x18000be20`
- `0x180010010`

## import_xrefs

- `IisRTL!PuDbgPrint` at `0x180007202`
- `IisRTL!PuDbgPrint` at `0x18000733c`
- `IisRTL!PuDbgPrint` at `0x180007374`
- `IisRTL!PuDbgPrint` at `0x180007202`
- `IisRTL!PuDbgPrint` at `0x18000733c`
- `IisRTL!PuDbgPrint` at `0x180007374`

## string_xrefs

- `0x1800071f6`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x180007335`: `inetsrv\iis\mb\coadmin\comobj.cxx`
- `0x18000736d`: `inetsrv\iis\mb\coadmin\comobj.cxx`

## pseudocode

```c
__int64 __fastcall CADMCOMW::LookupAndAccessCheck(
        CADMCOMW *a1,
        unsigned int a2,
        unsigned int *a3,
        __int64 a4,
        unsigned int a5,
        int a6,
        __int64 a7,
        __int64 a8,
        _QWORD *a9,
        _DWORD *a10,
        __int64 a11)
{
  int v15; // eax
  struct COpenHandle *v16; // rsi
  int v17; // ebx
  int v18; // eax
  __int64 v19; // rcx
  unsigned int v20; // eax
  unsigned int v21; // edi
  int v22; // eax
  int v24; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-24h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-20h] BYREF
  struct COpenHandle *v27; // [rsp+60h] [rbp-18h] BYREF

  v27 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  if ( a9 )
    *a9 = 0;
  v15 = CADMCOMW::Lookup(a1, a2, &v26, &v25, &v27);
  v16 = v27;
  v17 = v15;
  if ( v15 >= 0 )
  {
    v18 = CADMCOMW::AccessCheck(a1, a2, a4, a5, a6, a7, v27, a8, a11);
    v17 = v18;
    if ( v18 >= 0 )
    {
      if ( a9 )
        *a9 = *(_QWORD *)v16;
    }
    else if ( (g_dwDebugFlags & 4) != 0 )
    {
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4752, &word_1800127E6, "*%08x\n", v18);
    }
  }
  else if ( (g_dwDebugFlags & 4) != 0 )
  {
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4743, &word_1800127E6, "*%08x\n", v15);
  }
  if ( v16 )
  {
    LODWORD(v19) = *((_DWORD *)v16 + 4);
    v24 = v19;
  }
  else
  {
    LODWORD(v19) = v24;
  }
  if ( (_DWORD)v19 == 1 )
  {
    v20 = v25;
LABEL_20:
    *a3 = v20;
    goto LABEL_27;
  }
  if ( !(_DWORD)v19 && a2 )
  {
    v20 = v26;
    goto LABEL_20;
  }
  v19 = *((_QWORD *)a1 + 101);
  if ( !v19 )
  {
    v24 = 0;
    v17 = 0;
LABEL_25:
    v21 = v26;
    goto LABEL_26;
  }
  v21 = v25;
  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)v19 + 168LL))(v19, v25, a4, &v24);
  LODWORD(v19) = v24;
  v17 = v22;
  if ( v22 < 0 )
    goto LABEL_27;
  if ( v24 != 1 )
    goto LABEL_25;
LABEL_26:
  *a3 = v21;
LABEL_27:
  if ( a10 )
    *a10 = v19;
  if ( v16 )
    COpenHandle::Release(v16, a1);
  if ( v17 >= 0 )
  {
    if ( (g_dwDebugFlags & 1) != 0 )
      PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4810, &word_1800127E6, "\n");
  }
  else if ( (g_dwDebugFlags & 8) != 0 )
  {
    PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4810, &word_1800127E6, "*%08x\n", v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000716c  push    rbp
0x18000716e  push    rbx
0x18000716f  push    rsi
0x180007170  push    rdi
0x180007171  push    r12
0x180007173  push    r13
0x180007175  push    r14
0x180007177  push    r15
0x180007179  mov     rbp, rsp
0x18000717c  sub     rsp, 78h
0x180007180  mov     rdi, [rbp+arg_40]
0x180007187  xor     eax, eax
0x180007189  mov     [rbp+var_18], rax
0x18000718d  mov     r12, r9
0x180007190  mov     [rbp+var_20], eax
0x180007193  mov     r14, r8
0x180007196  mov     [rbp+var_24], eax
0x180007199  mov     r15d, edx
0x18000719c  mov     [rbp+var_28], eax
0x18000719f  mov     r13, rcx
0x1800071a2  test    rdi, rdi
0x1800071a5  jz      short loc_1800071AA
0x1800071a7  mov     [rdi], rax
0x1800071aa  lea     rax, [rbp+var_18]
0x1800071ae  lea     r9, [rbp+var_24]; unsigned int *
0x1800071b2  mov     [rsp+78h+var_58], rax; struct COpenHandle **
0x1800071b7  lea     r8, [rbp+var_20]; unsigned int *
0x1800071bb  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x1800071c0  mov     rsi, [rbp+var_18]
0x1800071c4  mov     ebx, eax
0x1800071c6  lea     rax, a08x; "*%08x\n"
0x1800071cd  test    ebx, ebx
0x1800071cf  jns     short loc_18000720A
0x1800071d1  test    byte ptr cs:g_dwDebugFlags, 4
0x1800071d8  jz      loc_180007279
0x1800071de  mov     dword ptr [rsp+78h+var_50], ebx
0x1800071e2  mov     r8d, 1287h
0x1800071e8  mov     rcx, cs:g_pDebug
0x1800071ef  lea     r9, word_1800127E6
0x1800071f6  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x1800071fd  mov     [rsp+78h+var_58], rax
0x180007202  call    cs:__imp_PuDbgPrint
0x180007208  jmp     short loc_180007279
0x18000720a  mov     rax, [rbp+arg_50]
0x180007211  mov     r8, r12
0x180007214  mov     r9d, [rbp+arg_20]
0x180007218  mov     edx, r15d
0x18000721b  mov     [rsp+78h+var_38], rax
0x180007220  mov     rcx, r13
0x180007223  mov     rax, [rbp+arg_38]
0x18000722a  mov     [rsp+78h+var_40], rax
0x18000722f  mov     rax, [rbp+arg_30]
0x180007233  mov     [rsp+78h+var_48], rsi
0x180007238  mov     [rsp+78h+var_50], rax
0x18000723d  mov     eax, [rbp+arg_28]
0x180007240  mov     dword ptr [rsp+78h+var_58], eax
0x180007244  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180007249  mov     ebx, eax
0x18000724b  test    eax, eax
0x18000724d  jns     short loc_18000726E
0x18000724f  test    byte ptr cs:g_dwDebugFlags, 4
0x180007256  jz      short loc_180007279
0x180007258  mov     dword ptr [rsp+78h+var_50], eax
0x18000725c  mov     r8d, 1290h
0x180007262  lea     rax, a08x; "*%08x\n"
0x180007269  jmp     loc_1800071E8
0x18000726e  test    rdi, rdi
0x180007271  jz      short loc_180007279
0x180007273  mov     rax, [rsi]
0x180007276  mov     [rdi], rax
0x180007279  test    rsi, rsi
0x18000727c  jz      short loc_180007286
0x18000727e  mov     ecx, [rsi+10h]
0x180007281  mov     [rbp+var_28], ecx
0x180007284  jmp     short loc_180007289
0x180007286  mov     ecx, [rbp+var_28]
0x180007289  cmp     ecx, 1
0x18000728c  jnz     short loc_180007293
0x18000728e  mov     eax, [rbp+var_24]
0x180007291  jmp     short loc_18000729F
0x180007293  test    ecx, ecx
0x180007295  jnz     short loc_1800072A4
0x180007297  test    r15d, r15d
0x18000729a  jz      short loc_1800072A4
0x18000729c  mov     eax, [rbp+var_20]
0x18000729f  mov     [r14], eax
0x1800072a2  jmp     short loc_1800072E6
0x1800072a4  mov     rcx, [r13+328h]
0x1800072ab  test    rcx, rcx
0x1800072ae  jnz     short loc_1800072B7
0x1800072b0  mov     [rbp+var_28], ecx
0x1800072b3  xor     ebx, ebx
0x1800072b5  jmp     short loc_1800072E0
0x1800072b7  mov     rax, [rcx]
0x1800072ba  lea     r9, [rbp+var_28]
0x1800072be  mov     edi, [rbp+var_24]
0x1800072c1  mov     r8, r12
0x1800072c4  mov     edx, edi
0x1800072c6  mov     rax, [rax+0A8h]
0x1800072cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d2  mov     ecx, [rbp+var_28]
0x1800072d5  mov     ebx, eax
0x1800072d7  test    eax, eax
0x1800072d9  js      short loc_1800072E6
0x1800072db  cmp     ecx, 1
0x1800072de  jz      short loc_1800072E3
0x1800072e0  mov     edi, [rbp+var_20]
0x1800072e3  mov     [r14], edi
0x1800072e6  mov     rax, [rbp+arg_48]
0x1800072ed  test    rax, rax
0x1800072f0  jz      short loc_1800072F4
0x1800072f2  mov     [rax], ecx
0x1800072f4  test    rsi, rsi
0x1800072f7  jz      short loc_180007304
0x1800072f9  mov     rdx, r13; void *
0x1800072fc  mov     rcx, rsi; this
0x1800072ff  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180007304  test    ebx, ebx
0x180007306  jns     short loc_180007344
0x180007308  test    byte ptr cs:g_dwDebugFlags, 8
0x18000730f  jz      short loc_18000737A
0x180007311  mov     rcx, cs:g_pDebug
0x180007318  lea     rax, a08x; "*%08x\n"
0x18000731f  mov     dword ptr [rsp+78h+var_50], ebx
0x180007323  lea     r9, word_1800127E6
0x18000732a  mov     r8d, 12CAh
0x180007330  mov     [rsp+78h+var_58], rax
0x180007335  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x18000733c  call    cs:__imp_PuDbgPrint
0x180007342  jmp     short loc_18000737A
0x180007344  test    byte ptr cs:g_dwDebugFlags, 1
0x18000734b  jz      short loc_18000737A
0x18000734d  mov     rcx, cs:g_pDebug
0x180007354  lea     rax, asc_1800127E4; "\n"
0x18000735b  lea     r9, word_1800127E6
0x180007362  mov     [rsp+78h+var_58], rax
0x180007367  mov     r8d, 12CAh
0x18000736d  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180007374  call    cs:__imp_PuDbgPrint
0x18000737a  mov     eax, ebx
0x18000737c  add     rsp, 78h
0x180007380  pop     r15
0x180007382  pop     r14
0x180007384  pop     r13
0x180007386  pop     r12
0x180007388  pop     rdi
0x180007389  pop     rsi
0x18000738a  pop     rbx
0x18000738b  pop     rbp
0x18000738c  retn
```
