# crRequestCertificate(ulong,uchar const *,ulong,ulong,ushort const *,ushort const *,ushort const *,ushort const *,_CERTSERVERENROLL * *)

- ea: `0x180012358`
- end: `0x1800126de`
- name: `?crRequestCertificate@@YAJKPEBEKKPEBG111PEAPEAU_CERTSERVERENROLL@@@Z`
- size: `902`
- prototype: `__int64 __fastcall(int, BYTE *, unsigned int, unsigned int, BYTE *, BYTE *, unsigned __int16 *NetworkAddr, unsigned __int16 *, struct _CERTSERVERENROLL **)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012920`
- `0x1800129a0`

## callees

- `0x180002306`
- `0x180011e14`
- `0x180012034`
- `0x180012114`
- `0x180012358`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800125b3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800125b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001269d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001269d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800126bb`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001268d`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001268d`

## pseudocode

```c
__int64 __fastcall crRequestCertificate(
        int a1,
        BYTE *a2,
        unsigned int a3,
        unsigned int a4,
        BYTE *a5,
        BYTE *a6,
        unsigned __int16 *NetworkAddr,
        unsigned __int16 *a8,
        struct _CERTSERVERENROLL **a9)
{
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned __int64 v12; // rcx
  int v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // ebx
  unsigned __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // edx
  unsigned int v22; // ecx
  _OWORD *v23; // rax
  _OWORD *v24; // rdi
  char *v25; // r14
  char *v26; // rsi
  int v28; // [rsp+60h] [rbp-A0h] BYREF
  struct _CERTTRANSBLOB Size; // [rsp+68h] [rbp-98h] BYREF
  struct _CERTTRANSBLOB v30; // [rsp+78h] [rbp-88h] BYREF
  struct _CERTTRANSBLOB v31; // [rsp+88h] [rbp-78h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-68h] BYREF
  struct _CERTTRANSBLOB v33; // [rsp+A0h] [rbp-60h] BYREF
  struct _CERTTRANSBLOB v34; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v35[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v36; // [rsp+D0h] [rbp-30h]
  __int128 v37; // [rsp+E0h] [rbp-20h]
  __int64 v38; // [rsp+F0h] [rbp-10h]
  struct _CERTTRANSBLOB v39; // [rsp+F8h] [rbp-8h] BYREF

  Binding = 0;
  v28 = 0;
  *(_QWORD *)&Size.cb = 0;
  Size.pb = 0;
  *(_QWORD *)&v30.cb = 0;
  v30.pb = 0;
  *(_QWORD *)&v31.cb = 0;
  v31.pb = 0;
  v38 = 0;
  v39 = 0;
  v34 = 0;
  v33 = 0;
  *(_OWORD *)v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( !NetworkAddr || !a8 || !a9 )
  {
    v15 = -2147467261;
    v14 = 22086340;
    goto LABEL_41;
  }
  v39.pb = a2;
  v10 = -1;
  v39.cb = a3;
  *a9 = 0;
  v35[1] = -2147467259;
  v35[0] = 1;
  v35[2] = a4;
  v34.pb = a5;
  v34.cb = 0;
  if ( a5 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&a5[2 * v11] );
    v12 = 2 * v11 + 2;
    if ( v12 > 0x10000 )
    {
      v13 = -2147024362;
      v14 = 23397060;
      v15 = -2147024362;
LABEL_42:
      CSPrintErrorLineFile(v14, v13);
      goto LABEL_43;
    }
    v34.cb = v12;
  }
  v33.pb = a6;
  v33.cb = 0;
  if ( a6 )
  {
    do
      ++v10;
    while ( *(_WORD *)&a6[2 * v10] );
    v16 = 2 * v10 + 2;
    if ( v16 > 0x10000 )
    {
      v13 = -2147024362;
      v14 = 24249028;
      v15 = -2147024362;
      goto LABEL_42;
    }
    v33.cb = v16;
  }
  v17 = crOpenRPCConnection(NetworkAddr, &v28, &Binding);
  v15 = v17;
  if ( v17 )
  {
    v13 = v17;
    v14 = 24642244;
    goto LABEL_42;
  }
  v18 = crCertServerRequest(Binding, &v28, a1, a8, &v35[2], v35, &v34, &v33, &v39, &v30, &Size, &v31);
  v15 = v18;
  if ( v18 )
  {
    v13 = v18;
    v14 = 25625284;
    goto LABEL_42;
  }
  v19 = 0;
  if ( (v35[0] & 0x80000000) == 0 )
  {
    if ( v35[0] == 2 )
      v19 = -2146877420;
    v35[1] = v19;
  }
  else
  {
    v35[1] = v35[0];
    v35[0] = 2;
  }
  v20 = ((Size.cb + 3) & 0xFFFFFFFC) + 56;
  if ( ((Size.cb + 3) & 0xFFFFFFFC) >= 0xFFFFFFC8 )
  {
    v13 = -2147024362;
    v14 = 26739396;
    v15 = -2147024362;
    goto LABEL_42;
  }
  v21 = v20 + ((v30.cb + 3) & 0xFFFFFFFC);
  if ( v21 < v20 )
  {
    v13 = -2147024362;
    v14 = 26936004;
    v15 = -2147024362;
    goto LABEL_42;
  }
  v22 = v21 + ((v31.cb + 3) & 0xFFFFFFFC);
  if ( v22 < v21 )
  {
    v13 = -2147024362;
    v14 = 27132612;
    v15 = -2147024362;
    goto LABEL_42;
  }
  v23 = LocalAlloc(0, v22);
  v24 = v23;
  if ( !v23 )
  {
    v15 = -2147024882;
    v14 = 27525828;
LABEL_41:
    v13 = v15;
    goto LABEL_42;
  }
  v15 = 0;
  v25 = (char *)v23 + 56;
  *v23 = *(_OWORD *)v35;
  v23[1] = v36;
  v23[2] = v37;
  *((_QWORD *)v23 + 6) = v38;
  if ( Size.cb )
  {
    *((_QWORD *)v23 + 2) = v25;
    *((_DWORD *)v23 + 6) = Size.cb;
    memcpy_0((char *)v23 + 56, Size.pb, Size.cb);
    v26 = &v25[(Size.cb + 3LL) & 0xFFFFFFFFFFFFFFFCuLL];
  }
  else
  {
    v26 = (char *)v23 + 56;
  }
  if ( v30.cb )
  {
    *((_QWORD *)v24 + 4) = v26;
    *((_DWORD *)v24 + 10) = v30.cb;
    memcpy_0(v26, v30.pb, v30.cb);
    v26 += (v30.cb + 3LL) & 0xFFFFFFFFFFFFFFFCuLL;
  }
  if ( v31.cb )
  {
    *((_QWORD *)v24 + 6) = v26;
    memcpy_0(v26, v31.pb, v31.cb);
  }
  *a9 = (struct _CERTSERVERENROLL *)v24;
LABEL_43:
  if ( Size.pb )
    CoTaskMemFree(Size.pb);
  if ( v30.pb )
    CoTaskMemFree(v30.pb);
  if ( v31.pb )
    CoTaskMemFree(v31.pb);
  crCloseRPCConnection(&Binding);
  return v15;
}

```

## disassembly

```asm
0x180012358  push    rbp
0x18001235a  push    rbx
0x18001235b  push    rsi
0x18001235c  push    rdi
0x18001235d  push    r12
0x18001235f  push    r14
0x180012361  push    r15
0x180012363  lea     rbp, [rsp-10h]
0x180012368  sub     rsp, 110h
0x18001236f  mov     r10, [rbp+40h+NetworkAddr]
0x180012376  xor     r12d, r12d
0x180012379  xorps   xmm0, xmm0
0x18001237c  mov     [rbp+40h+Binding], r12
0x180012380  xor     eax, eax
0x180012382  mov     [rsp+140h+var_E0], r12d
0x180012387  mov     [rsp+140h+Size], r12
0x18001238c  xorps   xmm1, xmm1
0x18001238f  mov     [rsp+140h+Src], r12
0x180012394  mov     esi, ecx
0x180012396  mov     [rsp+140h+var_C8], r12
0x18001239b  mov     [rbp+40h+pv], r12
0x18001239f  mov     [rbp+40h+var_B8], r12
0x1800123a3  mov     [rbp+40h+var_B0], r12
0x1800123a7  mov     [rbp+40h+var_50], rax
0x1800123ab  movups  xmmword ptr [rbp+40h+var_48.cb], xmm0
0x1800123af  movups  xmmword ptr [rbp+40h+var_90.cb], xmm1
0x1800123b3  movups  xmmword ptr [rbp+40h+var_A0.cb], xmm0
0x1800123b7  movups  xmmword ptr [rbp+40h+var_80], xmm0
0x1800123bb  movups  [rbp+40h+var_70], xmm0
0x1800123bf  movups  [rbp+40h+var_60], xmm0
0x1800123c3  test    r10, r10
0x1800123c6  jz      loc_180012681
0x1800123cc  mov     rdi, [rbp+40h+arg_38]
0x1800123d3  test    rdi, rdi
0x1800123d6  jz      loc_180012681
0x1800123dc  mov     r15, [rbp+40h+arg_40]
0x1800123e3  test    r15, r15
0x1800123e6  jz      loc_180012681
0x1800123ec  mov     [rbp+40h+var_48.pb], rdx
0x1800123f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800123f4  mov     rdx, [rbp+40h+arg_20]
0x1800123f8  mov     [rbp+40h+var_48.cb], r8d
0x1800123fc  mov     r8d, 10000h
0x180012402  mov     [r15], r12
0x180012405  mov     [rbp+40h+var_80+4], 80004005h
0x18001240c  mov     [rbp+40h+var_80], 1
0x180012413  mov     [rbp+40h+var_80+8], r9d
0x180012417  mov     [rbp+40h+var_90.pb], rdx
0x18001241b  mov     [rbp+40h+var_90.cb], r12d
0x18001241f  test    rdx, rdx
0x180012422  jz      short loc_180012452
0x180012424  mov     rcx, rax
0x180012427  inc     rcx
0x18001242a  cmp     [rdx+rcx*2], r12w
0x18001242f  jnz     short loc_180012427
0x180012431  lea     rcx, ds:2[rcx*2]
0x180012439  cmp     rcx, r8
0x18001243c  jbe     short loc_18001244F
0x18001243e  mov     edx, 80070216h
0x180012443  mov     ecx, 16502C4h
0x180012448  mov     ebx, edx
0x18001244a  jmp     loc_18001268D
0x18001244f  mov     [rbp+40h+var_90.cb], ecx
0x180012452  mov     rcx, [rbp+40h+arg_28]
0x180012456  mov     [rbp+40h+var_A0.pb], rcx
0x18001245a  mov     [rbp+40h+var_A0.cb], r12d
0x18001245e  test    rcx, rcx
0x180012461  jz      short loc_18001248E
0x180012463  inc     rax
0x180012466  cmp     [rcx+rax*2], r12w
0x18001246b  jnz     short loc_180012463
0x18001246d  lea     rax, ds:2[rax*2]
0x180012475  cmp     rax, r8
0x180012478  jbe     short loc_18001248B
0x18001247a  mov     edx, 80070216h
0x18001247f  mov     ecx, 17202C4h
0x180012484  mov     ebx, edx
0x180012486  jmp     loc_18001268D
0x18001248b  mov     [rbp+40h+var_A0.cb], eax
0x18001248e  lea     r8, [rbp+40h+Binding]; Binding
0x180012492  mov     rcx, r10; NetworkAddr
0x180012495  lea     rdx, [rsp+140h+var_E0]; int *
0x18001249a  call    ?crOpenRPCConnection@@YAJPEBGPEAHPEAPEAX@Z; crOpenRPCConnection(ushort const *,int *,void * *)
0x18001249f  mov     ebx, eax
0x1800124a1  test    eax, eax
0x1800124a3  jz      short loc_1800124B1
0x1800124a5  mov     edx, eax
0x1800124a7  mov     ecx, 17802C4h
0x1800124ac  jmp     loc_18001268D
0x1800124b1  mov     rcx, [rbp+40h+Binding]; Binding
0x1800124b5  lea     rax, [rbp+40h+var_B8]
0x1800124b9  mov     [rsp+140h+var_E8], rax; struct _CERTTRANSBLOB *
0x1800124be  lea     rdx, [rsp+140h+var_E0]; int *
0x1800124c3  lea     rax, [rsp+140h+Size]
0x1800124c8  mov     r9, rdi; unsigned __int16 *
0x1800124cb  mov     [rsp+140h+var_F0], rax; struct _CERTTRANSBLOB *
0x1800124d0  mov     r8d, esi; unsigned int
0x1800124d3  lea     rax, [rsp+140h+var_C8]
0x1800124d8  mov     [rsp+140h+var_F8], rax; struct _CERTTRANSBLOB *
0x1800124dd  lea     rax, [rbp+40h+var_48]
0x1800124e1  mov     [rsp+140h+var_100], rax; struct _CERTTRANSBLOB *
0x1800124e6  lea     rax, [rbp+40h+var_A0]
0x1800124ea  mov     [rsp+140h+var_108], rax; struct _CERTTRANSBLOB *
0x1800124ef  lea     rax, [rbp+40h+var_90]
0x1800124f3  mov     [rsp+140h+var_110], rax; struct _CERTTRANSBLOB *
0x1800124f8  lea     rax, [rbp+40h+var_80]
0x1800124fc  mov     [rsp+140h+var_118], rax; unsigned int *
0x180012501  lea     rax, [rbp+40h+var_80+8]
0x180012505  mov     [rsp+140h+var_120], rax; unsigned int *
0x18001250a  call    ?crCertServerRequest@@YAJPEAXPEAHKPEBGPEAK3PEBU_CERTTRANSBLOB@@44PEAU1@55@Z; crCertServerRequest(void *,int *,ulong,ushort const *,ulong *,ulong *,_CERTTRANSBLOB const *,_CERTTRANSBLOB const *,_CERTTRANSBLOB const *,_CERTTRANSBLOB *,_CERTTRANSBLOB *,_CERTTRANSBLOB *)
0x18001250f  mov     ebx, eax
0x180012511  test    eax, eax
0x180012513  jz      short loc_180012521
0x180012515  mov     edx, eax
0x180012517  mov     ecx, 18702C4h
0x18001251c  jmp     loc_18001268D
0x180012521  mov     eax, [rbp+40h+var_80]
0x180012524  mov     ecx, r12d
0x180012527  test    eax, eax
0x180012529  jns     short loc_180012537
0x18001252b  mov     [rbp+40h+var_80+4], eax
0x18001252e  mov     [rbp+40h+var_80], 2
0x180012535  jmp     short loc_180012545
0x180012537  cmp     eax, 2
0x18001253a  mov     edx, 80094014h
0x18001253f  cmovz   ecx, edx
0x180012542  mov     [rbp+40h+var_80+4], ecx
0x180012545  mov     ecx, dword ptr [rsp+140h+Size]
0x180012549  mov     r8d, 0FFFFFFFCh
0x18001254f  add     ecx, 3
0x180012552  and     ecx, r8d
0x180012555  add     ecx, 38h ; '8'
0x180012558  cmp     ecx, 38h ; '8'
0x18001255b  jnb     short loc_18001256E
0x18001255d  mov     edx, 80070216h
0x180012562  mov     ecx, 19802C4h
0x180012567  mov     ebx, edx
0x180012569  jmp     loc_18001268D
0x18001256e  mov     edx, dword ptr [rsp+140h+var_C8]
0x180012572  add     edx, 3
0x180012575  and     edx, r8d
0x180012578  add     edx, ecx
0x18001257a  cmp     edx, ecx
0x18001257c  jnb     short loc_18001258F
0x18001257e  mov     edx, 80070216h
0x180012583  mov     ecx, 19B02C4h
0x180012588  mov     ebx, edx
0x18001258a  jmp     loc_18001268D
0x18001258f  mov     ecx, dword ptr [rbp+40h+var_B8]
0x180012592  add     ecx, 3
0x180012595  and     ecx, r8d
0x180012598  add     ecx, edx
0x18001259a  cmp     ecx, edx
0x18001259c  jnb     short loc_1800125AF
0x18001259e  mov     edx, 80070216h
0x1800125a3  mov     ecx, 19E02C4h
0x1800125a8  mov     ebx, edx
0x1800125aa  jmp     loc_18001268D
0x1800125af  mov     edx, ecx; uBytes
0x1800125b1  xor     ecx, ecx; uFlags
0x1800125b3  call    cs:__imp_LocalAlloc
0x1800125b9  mov     rdi, rax
0x1800125bc  test    rax, rax
0x1800125bf  jnz     short loc_1800125D0
0x1800125c1  mov     ebx, 8007000Eh
0x1800125c6  mov     ecx, 1A402C4h
0x1800125cb  jmp     loc_18001268B
0x1800125d0  movups  xmm0, xmmword ptr [rbp+40h+var_80]
0x1800125d4  mov     ebx, r12d
0x1800125d7  lea     r14, [rax+38h]
0x1800125db  movups  xmmword ptr [rax], xmm0
0x1800125de  movups  xmm1, [rbp+40h+var_70]
0x1800125e2  movups  xmmword ptr [rax+10h], xmm1
0x1800125e6  movups  xmm0, [rbp+40h+var_60]
0x1800125ea  movups  xmmword ptr [rax+20h], xmm0
0x1800125ee  movsd   xmm1, [rbp+40h+var_50]
0x1800125f3  movsd   qword ptr [rax+30h], xmm1
0x1800125f8  cmp     dword ptr [rsp+140h+Size], r12d
0x1800125fd  jz      short loc_18001262D
0x1800125ff  mov     [rax+10h], r14
0x180012603  mov     rcx, r14; void *
0x180012606  mov     eax, dword ptr [rsp+140h+Size]
0x18001260a  mov     [rdi+18h], eax
0x18001260d  mov     r8d, dword ptr [rsp+140h+Size]; Size
0x180012612  mov     rdx, [rsp+140h+Src]; Src
0x180012617  call    memcpy_0
0x18001261c  mov     esi, dword ptr [rsp+140h+Size]
0x180012620  add     rsi, 3
0x180012624  and     rsi, 0FFFFFFFFFFFFFFFCh
0x180012628  add     rsi, r14
0x18001262b  jmp     short loc_180012630
0x18001262d  mov     rsi, r14
0x180012630  cmp     dword ptr [rsp+140h+var_C8], r12d
0x180012635  jz      short loc_180012662
0x180012637  mov     [rdi+20h], rsi
0x18001263b  mov     rcx, rsi; void *
0x18001263e  mov     eax, dword ptr [rsp+140h+var_C8]
0x180012642  mov     [rdi+28h], eax
0x180012645  mov     r8d, dword ptr [rsp+140h+var_C8]; Size
0x18001264a  mov     rdx, [rbp+40h+pv]; Src
0x18001264e  call    memcpy_0
0x180012653  mov     eax, dword ptr [rsp+140h+var_C8]
0x180012657  add     rax, 3
0x18001265b  and     rax, 0FFFFFFFFFFFFFFFCh
0x18001265f  add     rsi, rax
0x180012662  cmp     dword ptr [rbp+40h+var_B8], r12d
0x180012666  jz      short loc_18001267C
0x180012668  mov     [rdi+30h], rsi
0x18001266c  mov     rcx, rsi; void *
0x18001266f  mov     r8d, dword ptr [rbp+40h+var_B8]; Size
0x180012673  mov     rdx, [rbp+40h+var_B0]; Src
0x180012677  call    memcpy_0
0x18001267c  mov     [r15], rdi
0x18001267f  jmp     short loc_180012693
0x180012681  mov     ebx, 80004003h
0x180012686  mov     ecx, 15102C4h
0x18001268b  mov     edx, ebx
0x18001268d  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180012693  mov     rcx, [rsp+140h+Src]; pv
0x180012698  test    rcx, rcx
0x18001269b  jz      short loc_1800126A3
0x18001269d  call    cs:__imp_CoTaskMemFree
0x1800126a3  mov     rcx, [rbp+40h+pv]; pv
0x1800126a7  test    rcx, rcx
0x1800126aa  jz      short loc_1800126B2
0x1800126ac  call    cs:__imp_CoTaskMemFree
0x1800126b2  mov     rcx, [rbp+40h+var_B0]; pv
0x1800126b6  test    rcx, rcx
0x1800126b9  jz      short loc_1800126C1
0x1800126bb  call    cs:__imp_CoTaskMemFree
0x1800126c1  lea     rcx, [rbp+40h+Binding]; void **
0x1800126c5  call    ?crCloseRPCConnection@@YAXPEAPEAX@Z; crCloseRPCConnection(void * *)
0x1800126ca  mov     eax, ebx
0x1800126cc  add     rsp, 110h
0x1800126d3  pop     r15
0x1800126d5  pop     r14
0x1800126d7  pop     r12
0x1800126d9  pop     rdi
0x1800126da  pop     rsi
0x1800126db  pop     rbx
0x1800126dc  pop     rbp
0x1800126dd  retn
```
