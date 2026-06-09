# CADMCOMW::OpenKeyHelper(ulong,ushort const *,ulong,ulong,ulong *)

- ea: `0x180007f40`
- end: `0x18000822c`
- name: `?OpenKeyHelper@CADMCOMW@@QEAAJKPEBGKKPEAK@Z`
- size: `748`
- prototype: `__int64 __fastcall(CADMCOMW *this, unsigned int, wchar_t *Str, unsigned int, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004dd0`
- `0x1800063c0`
- `0x180007ee0`

## callees

- `0x180001cec`
- `0x1800021e4`
- `0x180007068`
- `0x180007f40`
- `0x18000be20`
- `0x180010010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180007fcd`
- `msvcrt!wcsstr` at `0x180007fcd`
- `IisRTL!PuDbgPrint` at `0x180008146`
- `IisRTL!PuDbgPrint` at `0x180008146`

## string_xrefs

- `0x18000812d`: `inetsrv\iis\mb\coadmin\comobj.cxx`

## pseudocode

```c
__int64 __fastcall CADMCOMW::OpenKeyHelper(
        CADMCOMW *this,
        unsigned int a2,
        wchar_t *Str,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  COpenHandle *v10; // rdi
  int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  unsigned int v16; // [rsp+50h] [rbp-49h] BYREF
  int v17; // [rsp+54h] [rbp-45h] BYREF
  unsigned int v18; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v19; // [rsp+5Ch] [rbp-3Dh] BYREF
  unsigned int v20; // [rsp+60h] [rbp-39h] BYREF
  struct COpenHandle *v21; // [rsp+68h] [rbp-31h] BYREF
  __int64 v22; // [rsp+70h] [rbp-29h] BYREF
  _OWORD v23[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v24; // [rsp+98h] [rbp-1h]

  v18 = 0;
  v16 = 0;
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v24 = 0;
  v22 = 0;
  v10 = 0;
  v17 = 0;
  memset(v23, 0, sizeof(v23));
  if ( !a6 || (a4 & 3) == 0 || (a4 & 0xFFFFFFFC) != 0 || Str && wcsstr(Str, L"<nsepm>") )
  {
    v11 = -2147024809;
    goto LABEL_25;
  }
  v11 = CADMCOMW::Lookup(this, a2, &v20, &v19, &v21);
  if ( v11 < 0 )
    goto LABEL_23;
  v12 = *((_QWORD *)this + 101);
  if ( v12 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t *, int *))(*(_QWORD *)v12 + 168LL))(v12, v19, Str, &v17);
    if ( v11 < 0 )
      goto LABEL_23;
  }
  v13 = v17;
  if ( v17 == 1 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wchar_t *, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)this + 101) + 24LL))(
            *((_QWORD *)this + 101),
            v19,
            Str,
            a4,
            a5,
            &v16);
    if ( v11 < 0 )
      goto LABEL_23;
    v13 = v17;
  }
  if ( v13 != 2 )
    goto LABEL_15;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wchar_t *, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)this + 101) + 24LL))(
          *((_QWORD *)this + 101),
          v20,
          Str,
          a4,
          a5,
          &v16);
  if ( v11 < 0 )
  {
LABEL_23:
    v10 = v21;
    goto LABEL_25;
  }
  v13 = v17;
LABEL_15:
  v10 = v21;
  if ( v13 != 1 )
  {
    DWORD1(v23[0]) = 16;
    v14 = CADMCOMW::AccessCheck((__int64)this, a2, Str, 4 * (a4 & 1), (a4 >> 1) & 1, (unsigned int *)v23, v21, 0, 0);
    v11 = v14;
    if ( v14 < 0 )
    {
      if ( (g_dwDebugFlags & 4) != 0 )
        PuDbgPrint(g_pDebug, "inetsrv\\iis\\mb\\coadmin\\comobj.cxx", 4560, &word_1800127E6, "*%08x\n", v14);
      goto LABEL_25;
    }
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, wchar_t *, _QWORD, unsigned int, unsigned int *))(**((_QWORD **)this + 4) + 280LL))(
            *((_QWORD *)this + 4),
            v20,
            Str,
            a4,
            a5,
            &v18);
    if ( v11 < 0 )
      goto LABEL_25;
    v13 = v17;
  }
  v11 = CADMCOMW::AddNode(this, v18, v16, v10, a6, Str, &v22, v13);
  if ( v11 >= 0 )
  {
    v18 = 0;
LABEL_29:
    v16 = 0;
    goto LABEL_30;
  }
LABEL_25:
  if ( v18 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 288LL))(*((_QWORD *)this + 4));
    v18 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 101) + 32LL))(*((_QWORD *)this + 101));
    goto LABEL_29;
  }
LABEL_30:
  if ( v10 )
    COpenHandle::Release(v10, this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp-8+arg_8], edx
0x180007f44  push    rbp
0x180007f45  push    rbx
0x180007f46  push    rsi
0x180007f47  push    rdi
0x180007f48  push    r12
0x180007f4a  push    r13
0x180007f4c  push    r14
0x180007f4e  push    r15
0x180007f50  lea     rbp, [rsp-0Fh]
0x180007f55  sub     rsp, 0A8h
0x180007f5c  mov     r13, [rbp+47h+arg_28]
0x180007f60  xor     r12d, r12d
0x180007f63  xor     eax, eax
0x180007f65  mov     [rbp+47h+var_88], r12d
0x180007f69  mov     [rbp+47h+var_90], r12d
0x180007f6d  xorps   xmm0, xmm0
0x180007f70  mov     [rbp+47h+var_80], r12d
0x180007f74  mov     r15d, r9d
0x180007f77  mov     [rbp+47h+var_84], r12d
0x180007f7b  mov     r14, r8
0x180007f7e  mov     [rbp+47h+var_78], r12
0x180007f82  mov     ebx, edx
0x180007f84  mov     [rbp+47h+var_48], rax
0x180007f88  mov     rsi, rcx
0x180007f8b  mov     [rbp+47h+var_70], r12
0x180007f8f  mov     edi, r12d
0x180007f92  mov     [rbp+47h+var_8C], r12d
0x180007f96  movups  [rbp+47h+var_68], xmm0
0x180007f9a  movups  [rbp+47h+var_58], xmm0
0x180007f9e  test    r13, r13
0x180007fa1  jz      loc_1800081BF
0x180007fa7  test    r15b, 3
0x180007fab  jz      loc_1800081BF
0x180007fb1  test    r9d, 0FFFFFFFCh
0x180007fb8  jnz     loc_1800081BF
0x180007fbe  test    r8, r8
0x180007fc1  jz      short loc_180007FDC
0x180007fc3  lea     rdx, aNsepm; "<nsepm>"
0x180007fca  mov     rcx, r8; Str
0x180007fcd  call    cs:__imp_wcsstr
0x180007fd3  test    rax, rax
0x180007fd6  jnz     loc_1800081BF
0x180007fdc  lea     rax, [rbp+47h+var_78]
0x180007fe0  mov     edx, ebx; unsigned int
0x180007fe2  lea     r9, [rbp+47h+var_84]; unsigned int *
0x180007fe6  mov     [rsp+0E0h+var_C0], rax; struct COpenHandle **
0x180007feb  lea     r8, [rbp+47h+var_80]; unsigned int *
0x180007fef  mov     rcx, rsi; this
0x180007ff2  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x180007ff7  mov     ebx, eax
0x180007ff9  test    eax, eax
0x180007ffb  js      loc_1800081B9
0x180008001  mov     rcx, [rsi+328h]
0x180008008  test    rcx, rcx
0x18000800b  jz      short loc_180008030
0x18000800d  mov     rax, [rcx]
0x180008010  lea     r9, [rbp+47h+var_8C]
0x180008014  mov     edx, [rbp+47h+var_84]
0x180008017  mov     r8, r14
0x18000801a  mov     rax, [rax+0A8h]
0x180008021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008026  mov     ebx, eax
0x180008028  test    eax, eax
0x18000802a  js      loc_1800081B9
0x180008030  mov     eax, [rbp+47h+var_8C]
0x180008033  mov     r12d, [rbp+47h+arg_20]
0x180008037  cmp     eax, 1
0x18000803a  jnz     short loc_180008073
0x18000803c  mov     rcx, [rsi+328h]
0x180008043  lea     rdx, [rbp+47h+var_90]
0x180008047  mov     [rsp+0E0h+var_B8], rdx
0x18000804c  mov     r9d, r15d
0x18000804f  mov     edx, [rbp+47h+var_84]
0x180008052  mov     r8, r14
0x180008055  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x18000805a  mov     rax, [rcx]
0x18000805d  mov     rax, [rax+18h]
0x180008061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008066  mov     ebx, eax
0x180008068  test    eax, eax
0x18000806a  js      loc_1800081B9
0x180008070  mov     eax, [rbp+47h+var_8C]
0x180008073  cmp     eax, 2
0x180008076  jnz     short loc_1800080AF
0x180008078  mov     rcx, [rsi+328h]
0x18000807f  lea     rdx, [rbp+47h+var_90]
0x180008083  mov     [rsp+0E0h+var_B8], rdx
0x180008088  mov     r9d, r15d
0x18000808b  mov     edx, [rbp+47h+var_80]
0x18000808e  mov     r8, r14
0x180008091  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180008096  mov     rax, [rcx]
0x180008099  mov     rax, [rax+18h]
0x18000809d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a2  mov     ebx, eax
0x1800080a4  test    eax, eax
0x1800080a6  js      loc_1800081B9
0x1800080ac  mov     eax, [rbp+47h+var_8C]
0x1800080af  mov     rdi, [rbp+47h+var_78]
0x1800080b3  cmp     eax, 1
0x1800080b6  jz      loc_180008181
0x1800080bc  mov     edx, [rbp+47h+arg_8]
0x1800080bf  lea     rcx, [rbp+47h+var_68]
0x1800080c3  mov     [rsp+0E0h+var_A0], 0
0x1800080cc  mov     eax, r15d
0x1800080cf  mov     [rsp+0E0h+var_A8], 0
0x1800080d8  mov     r9d, r15d
0x1800080db  shr     eax, 1
0x1800080dd  and     r9d, 1
0x1800080e1  mov     [rsp+0E0h+var_B0], rdi
0x1800080e6  and     eax, 1
0x1800080e9  mov     [rsp+0E0h+var_B8], rcx
0x1800080ee  mov     r8, r14
0x1800080f1  shl     r9d, 2
0x1800080f5  mov     rcx, rsi
0x1800080f8  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800080fc  mov     dword ptr [rbp+47h+var_68+4], 10h
0x180008103  call    ?AccessCheck@CADMCOMW@@QEAAJKPEBGW4ACTP_ACCESSTYPE@@1PEAU_METADATA_RECORD@@PEAVCOpenHandle@@PEAH4@Z; CADMCOMW::AccessCheck(ulong,ushort const *,ACTP_ACCESSTYPE,ACTP_ACCESSTYPE,_METADATA_RECORD *,COpenHandle *,int *,int *)
0x180008108  mov     ebx, eax
0x18000810a  test    eax, eax
0x18000810c  jns     short loc_18000814E
0x18000810e  test    byte ptr cs:g_dwDebugFlags, 4
0x180008115  jz      loc_1800081C4
0x18000811b  mov     rcx, cs:g_pDebug
0x180008122  lea     r9, word_1800127E6
0x180008129  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18000812d  lea     rdx, aInetsrvIisMbCo_0; "inetsrv\\iis\\mb\\coadmin\\comobj.cxx"
0x180008134  lea     rax, a08x; "*%08x\n"
0x18000813b  mov     r8d, 11D0h
0x180008141  mov     [rsp+0E0h+var_C0], rax
0x180008146  call    cs:__imp_PuDbgPrint
0x18000814c  jmp     short loc_1800081C4
0x18000814e  mov     rcx, [rsi+20h]
0x180008152  lea     rdx, [rbp+47h+var_88]
0x180008156  mov     [rsp+0E0h+var_B8], rdx
0x18000815b  mov     r9d, r15d
0x18000815e  mov     edx, [rbp+47h+var_80]
0x180008161  mov     r8, r14
0x180008164  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180008169  mov     rax, [rcx]
0x18000816c  mov     rax, [rax+118h]
0x180008173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008178  mov     ebx, eax
0x18000817a  test    eax, eax
0x18000817c  js      short loc_1800081C4
0x18000817e  mov     eax, [rbp+47h+var_8C]
0x180008181  mov     r8d, [rbp+47h+var_90]
0x180008185  mov     r9, rdi
0x180008188  mov     edx, [rbp+47h+var_88]
0x18000818b  mov     rcx, rsi
0x18000818e  mov     dword ptr [rsp+0E0h+var_A8], eax
0x180008192  lea     rax, [rbp+47h+var_70]
0x180008196  mov     [rsp+0E0h+var_B0], rax
0x18000819b  mov     [rsp+0E0h+var_B8], r14
0x1800081a0  mov     [rsp+0E0h+var_C0], r13
0x1800081a5  call    ?AddNode@CADMCOMW@@QEAAJKKPEAVCOpenHandle@@PEAKPEBGPEAPEBGW4ABO_MAPPER_DISPOSITION@@@Z; CADMCOMW::AddNode(ulong,ulong,COpenHandle *,ulong *,ushort const *,ushort const * *,ABO_MAPPER_DISPOSITION)
0x1800081aa  mov     ebx, eax
0x1800081ac  test    eax, eax
0x1800081ae  js      short loc_1800081C4
0x1800081b0  mov     [rbp+47h+var_88], 0
0x1800081b7  jmp     short loc_1800081FF
0x1800081b9  mov     rdi, [rbp+47h+var_78]
0x1800081bd  jmp     short loc_1800081C4
0x1800081bf  mov     ebx, 80070057h
0x1800081c4  mov     edx, [rbp+47h+var_88]
0x1800081c7  test    edx, edx
0x1800081c9  jz      short loc_1800081E5
0x1800081cb  mov     rcx, [rsi+20h]
0x1800081cf  mov     rax, [rcx]
0x1800081d2  mov     rax, [rax+120h]
0x1800081d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081de  mov     [rbp+47h+var_88], 0
0x1800081e5  mov     edx, [rbp+47h+var_90]
0x1800081e8  test    edx, edx
0x1800081ea  jz      short loc_180008206
0x1800081ec  mov     rcx, [rsi+328h]
0x1800081f3  mov     rax, [rcx]
0x1800081f6  mov     rax, [rax+20h]
0x1800081fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ff  mov     [rbp+47h+var_90], 0
0x180008206  test    rdi, rdi
0x180008209  jz      short loc_180008216
0x18000820b  mov     rdx, rsi; void *
0x18000820e  mov     rcx, rdi; this
0x180008211  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x180008216  mov     eax, ebx
0x180008218  add     rsp, 0A8h
0x18000821f  pop     r15
0x180008221  pop     r14
0x180008223  pop     r13
0x180008225  pop     r12
0x180008227  pop     rdi
0x180008228  pop     rsi
0x180008229  pop     rbx
0x18000822a  pop     rbp
0x18000822b  retn
```
