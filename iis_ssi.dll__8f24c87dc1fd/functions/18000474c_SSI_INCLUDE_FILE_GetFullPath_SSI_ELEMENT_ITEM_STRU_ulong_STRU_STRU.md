# SSI_INCLUDE_FILE::GetFullPath(SSI_ELEMENT_ITEM *,STRU *,ulong,STRU *,STRU *)

- ea: `0x18000474c`
- end: `0x180004991`
- name: `?GetFullPath@SSI_INCLUDE_FILE@@AEAAJPEAVSSI_ELEMENT_ITEM@@PEAVSTRU@@K11@Z`
- size: `581`
- prototype: `__int64 __fastcall(SSI_REQUEST **this, struct SSI_ELEMENT_ITEM *, struct STRU *, int, const unsigned __int16 **, struct STRU *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180004afc`

## callees

- `0x180003678`
- `0x18000474c`
- `0x18000574a`
- `0x180005780`
- `0x180005810`

## import_xrefs

- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000495a`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x18000495a`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180004802`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180004802`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180004874`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x180004874`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004847`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004847`
- `iisutil!NormalizeUrlW` at `0x180004836`
- `iisutil!NormalizeUrlW` at `0x180004836`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004986`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180004986`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004887`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000489c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800048ed`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004902`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004887`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000489c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800048ed`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180004902`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004891`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800048f7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180004891`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800048f7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800047b8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800047ef`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800047b8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800047ef`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800047c9`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x1800047c9`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004825`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800048dc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004941`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000496e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004825`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800048dc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004941`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000496e`

## pseudocode

```c
__int64 __fastcall SSI_INCLUDE_FILE::GetFullPath(
        SSI_REQUEST **this,
        struct SSI_ELEMENT_ITEM *a2,
        struct STRU *a3,
        int a4,
        const unsigned __int16 **a5,
        struct STRU *a6)
{
  int v10; // ebx
  const unsigned __int16 *v11; // rbx
  int v12; // eax
  int v14; // edi
  unsigned __int16 *v15; // rdx
  bool v16; // zf
  unsigned __int64 v17; // rax
  _BYTE v18[32]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int16 *v19; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+50h] [rbp-B0h]
  _BYTE v21[32]; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[56]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v24[12]; // [rsp+C8h] [rbp-38h] BYREF
  char v25[16]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v26[2056]; // [rsp+F0h] [rbp-10h] BYREF

  memset(v24, 0, 22);
  STRU::STRU((STRU *)v21, v24, 0xBu);
  STRA::STRA((STRA *)v23, v25, 0xBu);
  memset_0(v26, 0, 0x1004u);
  STRU::STRU((STRU *)v18, v26, 0x802u);
  v10 = STRU::CopyA((STRU *)v21, *(const char **)(*((_QWORD *)a2 + 2) + 32LL));
  if ( v10 < 0 )
  {
LABEL_10:
    STRU::~STRU((STRU *)v18);
    STRA::~STRA((STRA *)v23);
    STRU::~STRU((STRU *)v21);
    return (unsigned int)v10;
  }
  v11 = v22;
  if ( *v22 == 47 )
  {
    v12 = STRU::Copy((STRU *)v18, v22);
LABEL_4:
    v10 = v12;
    if ( v12 >= 0 )
    {
      v10 = NormalizeUrlW(v19);
      if ( v10 >= 0 )
      {
        STRU::SyncWithBuffer((STRU *)v18);
        v10 = SSI_REQUEST::LookupVirtualRoot(this[2], v19, a3, a4);
        if ( v10 >= 0 )
        {
          if ( !a6 || (v10 = STRU::Copy(a6, (const struct STRU *)v18), v10 >= 0) )
            v10 = 0;
        }
      }
    }
    goto LABEL_10;
  }
  if ( *((_DWORD *)a2 + 2) )
  {
    v14 = STRU::Copy((STRU *)v18, L"/");
    if ( v14 < 0 )
      goto LABEL_13;
LABEL_24:
    v12 = STRU::Append((STRU *)v18, v11);
    goto LABEL_4;
  }
  v14 = STRU::Copy((STRU *)v18, a5[4]);
  if ( v14 >= 0 )
  {
    v15 = &v19[v20];
    v16 = v15 == v19;
    if ( v15 > v19 )
    {
      do
      {
        v17 = (unsigned __int64)(v15 - 1);
        if ( *(v15 - 1) == 47 )
          break;
        --v15;
      }
      while ( v17 > (unsigned __int64)v19 );
      v16 = v15 == v19;
    }
    if ( v16 )
    {
      v14 = STRU::Copy((STRU *)v18, L"/");
      if ( v14 < 0 )
        goto LABEL_13;
    }
    else
    {
      STRU::SetLen((STRU *)v18, v15 - v19);
    }
    goto LABEL_24;
  }
LABEL_13:
  STRU::~STRU((STRU *)v18);
  STRA::~STRA((STRA *)v23);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000474c  mov     [rsp-8+arg_18], rbx
0x180004751  push    rbp
0x180004752  push    rsi
0x180004753  push    rdi
0x180004754  push    r12
0x180004756  push    r13
0x180004758  push    r14
0x18000475a  push    r15
0x18000475c  lea     rbp, [rsp-1010h]
0x180004764  mov     eax, 1110h
0x180004769  call    _alloca_probe
0x18000476e  sub     rsp, rax
0x180004771  mov     rax, cs:__security_cookie
0x180004778  xor     rax, rsp
0x18000477b  mov     [rbp+1040h+var_40], rax
0x180004782  mov     r14, [rbp+1040h+arg_20]
0x180004789  xor     eax, eax
0x18000478b  mov     rsi, [rbp+1040h+arg_28]
0x180004792  xorps   xmm0, xmm0
0x180004795  mov     r12, r8
0x180004798  mov     rdi, rdx
0x18000479b  mov     r13, rcx
0x18000479e  lea     rdx, [rbp+1040h+var_1078]
0x1800047a2  lea     ebx, [rax+0Bh]
0x1800047a5  mov     r15d, r9d
0x1800047a8  movups  xmmword ptr [rbp+1040h+var_1078], xmm0
0x1800047ac  mov     r8d, ebx
0x1800047af  mov     qword ptr [rbp+1040h+var_1078+0Eh], rax
0x1800047b3  lea     rcx, [rsp+1140h+var_10E8]
0x1800047b8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800047be  mov     r8d, ebx
0x1800047c1  lea     rdx, [rbp+1040h+var_1060]
0x1800047c5  lea     rcx, [rbp+1040h+var_10B0]
0x1800047c9  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x1800047cf  xor     edx, edx; Val
0x1800047d1  lea     rcx, [rbp+1040h+var_1050]; void *
0x1800047d5  mov     r8d, 1004h; Size
0x1800047db  call    memset_0
0x1800047e0  mov     r8d, 802h
0x1800047e6  lea     rdx, [rbp+1040h+var_1050]
0x1800047ea  lea     rcx, [rsp+1140h+var_1120]
0x1800047ef  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800047f5  mov     rdx, [rdi+10h]
0x1800047f9  lea     rcx, [rsp+1140h+var_10E8]
0x1800047fe  mov     rdx, [rdx+20h]
0x180004802  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180004808  mov     ebx, eax
0x18000480a  test    eax, eax
0x18000480c  js      short loc_180004882
0x18000480e  mov     rbx, [rsp+1140h+var_10C8]
0x180004813  lea     rcx, [rsp+1140h+var_1120]
0x180004818  cmp     word ptr [rbx], 2Fh ; '/'
0x18000481c  jnz     loc_1800048CE
0x180004822  mov     rdx, rbx
0x180004825  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000482b  mov     ebx, eax
0x18000482d  test    eax, eax
0x18000482f  js      short loc_180004882
0x180004831  mov     rcx, [rsp+1140h+var_1100]
0x180004836  call    cs:__imp_?NormalizeUrlW@@YAJPEAG@Z; NormalizeUrlW(ushort *)
0x18000483c  lea     rcx, [rsp+1140h+var_1120]
0x180004841  mov     ebx, eax
0x180004843  test    eax, eax
0x180004845  js      short loc_180004887
0x180004847  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000484d  mov     rdx, [rsp+1140h+var_1100]; unsigned __int16 *
0x180004852  mov     r9d, r15d; int
0x180004855  mov     rcx, [r13+10h]; this
0x180004859  mov     r8, r12; struct STRU *
0x18000485c  call    ?LookupVirtualRoot@SSI_REQUEST@@QEAAJPEBGPEAVSTRU@@H@Z; SSI_REQUEST::LookupVirtualRoot(ushort const *,STRU *,int)
0x180004861  mov     ebx, eax
0x180004863  test    eax, eax
0x180004865  js      short loc_180004882
0x180004867  test    rsi, rsi
0x18000486a  jz      short loc_180004880
0x18000486c  lea     rdx, [rsp+1140h+var_1120]
0x180004871  mov     rcx, rsi
0x180004874  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18000487a  mov     ebx, eax
0x18000487c  test    eax, eax
0x18000487e  js      short loc_180004882
0x180004880  xor     ebx, ebx
0x180004882  lea     rcx, [rsp+1140h+var_1120]
0x180004887  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000488d  lea     rcx, [rbp+1040h+var_10B0]
0x180004891  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180004897  lea     rcx, [rsp+1140h+var_10E8]
0x18000489c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800048a2  mov     eax, ebx
0x1800048a4  mov     rcx, [rbp+1040h+var_40]
0x1800048ab  xor     rcx, rsp; StackCookie
0x1800048ae  call    __security_check_cookie
0x1800048b3  mov     rbx, [rsp+1140h+arg_18]
0x1800048bb  add     rsp, 1110h
0x1800048c2  pop     r15
0x1800048c4  pop     r14
0x1800048c6  pop     r13
0x1800048c8  pop     r12
0x1800048ca  pop     rdi
0x1800048cb  pop     rsi
0x1800048cc  pop     rbp
0x1800048cd  retn
0x1800048ce  cmp     dword ptr [rdi+8], 0
0x1800048d2  jnz     loc_180004967
0x1800048d8  mov     rdx, [r14+20h]
0x1800048dc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800048e2  mov     edi, eax
0x1800048e4  test    eax, eax
0x1800048e6  jns     short loc_18000490C
0x1800048e8  lea     rcx, [rsp+1140h+var_1120]
0x1800048ed  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800048f3  lea     rcx, [rbp+1040h+var_10B0]
0x1800048f7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800048fd  lea     rcx, [rsp+1140h+var_10E8]
0x180004902  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180004908  mov     eax, edi
0x18000490a  jmp     short loc_1800048A4
0x18000490c  mov     rcx, [rsp+1140h+var_1100]
0x180004911  mov     eax, [rsp+1140h+var_10F0]
0x180004915  lea     rdx, [rcx+rax*2]
0x180004919  cmp     rdx, rcx
0x18000491c  jbe     short loc_180004933
0x18000491e  lea     rax, [rdx-2]
0x180004922  cmp     word ptr [rax], 2Fh ; '/'
0x180004926  jz      short loc_180004930
0x180004928  mov     rdx, rax
0x18000492b  cmp     rax, rcx
0x18000492e  ja      short loc_18000491E
0x180004930  cmp     rdx, rcx
0x180004933  jnz     short loc_18000494F
0x180004935  lea     rdx, asc_1800077F0; "/"
0x18000493c  lea     rcx, [rsp+1140h+var_1120]
0x180004941  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004947  mov     edi, eax
0x180004949  test    eax, eax
0x18000494b  jns     short loc_180004960
0x18000494d  jmp     short loc_1800048E8
0x18000494f  sub     rdx, rcx
0x180004952  lea     rcx, [rsp+1140h+var_1120]
0x180004957  sar     rdx, 1
0x18000495a  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180004960  lea     rcx, [rsp+1140h+var_1120]
0x180004965  jmp     short loc_180004983
0x180004967  lea     rdx, asc_1800077F0; "/"
0x18000496e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004974  lea     rcx, [rsp+1140h+var_1120]
0x180004979  mov     edi, eax
0x18000497b  test    eax, eax
0x18000497d  js      loc_1800048ED
0x180004983  mov     rdx, rbx
0x180004986  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000498c  jmp     loc_18000482B
```
