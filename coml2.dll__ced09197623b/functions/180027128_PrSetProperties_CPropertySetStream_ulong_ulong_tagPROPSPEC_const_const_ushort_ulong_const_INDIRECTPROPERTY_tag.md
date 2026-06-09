# PrSetProperties(CPropertySetStream *,ulong,ulong,tagPROPSPEC const * const,ushort *,ulong * const,_INDIRECTPROPERTY * *,tagPROPVARIANT const * const)

- ea: `0x180027128`
- end: `0x180027340`
- name: `?PrSetProperties@@YAJPEAVCPropertySetStream@@KKQEBUtagPROPSPEC@@PEAGQEAKPEAPEAU_INDIRECTPROPERTY@@QEBUtagPROPVARIANT@@@Z`
- size: `536`
- prototype: `__int64 __usercall@<rax>(struct CPropertySetStream *this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const struct tagPROPSPEC *const@<r9>, unsigned __int16 *, unsigned int *const, struct _INDIRECTPROPERTY **, const struct tagPROPVARIANT *const)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035e8c`

## callees

- `0x180026f60`
- `0x180027128`
- `0x180027ff4`
- `0x180028f78`
- `0x180028fa8`
- `0x180042800`
- `0x1800570f8`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800272ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002732a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002732a`

## pseudocode

```c
__int64 __fastcall PrSetProperties(
        struct CPropertySetStream *this,
        __int64 a2,
        unsigned int a3,
        struct tagPROPSPEC *a4,
        unsigned __int16 *a5,
        unsigned int *const a6,
        LPVOID *a7,
        const struct tagPROPVARIANT *const a8)
{
  int v8; // r15d
  unsigned __int64 v10; // rsi
  __int64 result; // rax
  struct tagPROPERTY_INFORMATION *v12; // rdi
  int v13; // [rsp+50h] [rbp-91h] BYREF
  int v14; // [rsp+54h] [rbp-8Dh] BYREF
  unsigned int v15; // [rsp+58h] [rbp-89h]
  SIZE_T cb; // [rsp+60h] [rbp-81h] BYREF
  unsigned int *v17; // [rsp+68h] [rbp-79h]
  struct tagPROPSPEC *v18; // [rsp+70h] [rbp-71h]
  _BYTE pv[80]; // [rsp+80h] [rbp-61h] BYREF

  v8 = 0;
  v18 = a4;
  v15 = a3;
  v10 = (unsigned int)a2;
  v17 = a6;
  v13 = 0;
  v14 = 0;
  cb = 0;
  if ( a7 )
  {
    *a7 = 0;
    if ( (_DWORD)a2 == 1 )
      *(_DWORD *)a7 = -1;
  }
  LOBYTE(a2) = 1;
  result = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5), a2);
  v13 = result;
  if ( (int)result < 0 )
    goto LABEL_20;
  v12 = (struct tagPROPERTY_INFORMATION *)pv;
  v8 = 1;
  if ( (unsigned int)v10 > 6
    && ((int)ULongLongMult(0xCu, v10, &cb) < 0 || (v12 = (struct tagPROPERTY_INFORMATION *)CoTaskMemAlloc(cb)) == 0) )
  {
    result = 3221225626LL;
    v13 = -1073741670;
LABEL_20:
    if ( a7 )
    {
      if ( (_DWORD)v10 == 1 )
      {
        *(_DWORD *)a7 = -1;
      }
      else if ( *a7 )
      {
        CoTaskMemFree(*a7);
        result = (unsigned int)v13;
        *a7 = 0;
      }
    }
    goto LABEL_10;
  }
  CPropertySetStream::ReOpen(this, &v13);
  result = (unsigned int)v13;
  if ( v13 >= 0 )
  {
    v13 = 0;
    ConvertVariantToPropInfo(
      this,
      v10,
      v15,
      v18,
      v17,
      a8,
      v12,
      (unsigned int *)((unsigned __int64)&v14 & -(__int64)(a7 != 0)),
      &v13);
    result = (unsigned int)v13;
    if ( v13 >= 0 )
    {
      CPropertySetStream::SetValue(this, v10, (struct _INDIRECTPROPERTY **)a7, a8, v12, a5, &v13);
      result = (unsigned int)v13;
      if ( v13 >= 0 )
      {
        result = 0;
        v13 = 0;
      }
    }
  }
  if ( v12 && v12 != (struct tagPROPERTY_INFORMATION *)pv )
  {
    CoTaskMemFree(v12);
    result = (unsigned int)v13;
  }
  if ( (int)result < 0 )
    goto LABEL_20;
LABEL_10:
  if ( v8 )
    return Unlock(this, result);
  return result;
}

```

## disassembly

```asm
0x180027128  push    rbp
0x18002712a  push    rbx
0x18002712b  push    rsi
0x18002712c  push    rdi
0x18002712d  push    r12
0x18002712f  push    r13
0x180027131  push    r14
0x180027133  push    r15
0x180027135  lea     rbp, [rsp-7]
0x18002713a  sub     rsp, 0E8h
0x180027141  mov     rax, cs:__security_cookie
0x180027148  xor     rax, rsp
0x18002714b  mov     [rbp+3Fh+var_50], rax
0x18002714f  mov     rbx, [rbp+3Fh+arg_30]
0x180027153  xor     r15d, r15d
0x180027156  mov     rax, [rbp+3Fh+arg_28]
0x18002715a  mov     r14, rcx
0x18002715d  mov     r13, [rbp+3Fh+arg_20]
0x180027161  mov     r12, [rbp+3Fh+arg_38]
0x180027168  mov     [rbp+3Fh+var_B0], r9
0x18002716c  mov     [rsp+120h+var_C8], r8d
0x180027171  mov     esi, edx
0x180027173  mov     [rbp+3Fh+var_B8], rax
0x180027177  mov     [rsp+120h+var_D0], 0
0x18002717f  mov     [rsp+120h+var_CC], r15d
0x180027184  mov     [rsp+120h+cb], r15
0x180027189  test    rbx, rbx
0x18002718c  jnz     loc_1800272B8
0x180027192  mov     rcx, [rcx+28h]
0x180027196  mov     dl, 1
0x180027198  mov     rax, [rcx]
0x18002719b  mov     rax, [rax+58h]
0x18002719f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271a4  mov     [rsp+120h+var_D0], eax
0x1800271a8  test    eax, eax
0x1800271aa  js      loc_180027305
0x1800271b0  lea     rdi, [rbp+3Fh+pv]
0x1800271b4  mov     r15d, 1
0x1800271ba  cmp     esi, 6
0x1800271bd  ja      loc_1800272CF
0x1800271c3  lea     rdx, [rsp+120h+var_D0]; int *
0x1800271c8  mov     rcx, r14; this
0x1800271cb  call    ?ReOpen@CPropertySetStream@@QEAAKPEAJ@Z; CPropertySetStream::ReOpen(long *)
0x1800271d0  mov     eax, [rsp+120h+var_D0]
0x1800271d4  test    eax, eax
0x1800271d6  js      loc_180027264
0x1800271dc  mov     r9, [rbp+3Fh+var_B0]; struct tagPROPSPEC *
0x1800271e0  mov     rax, rbx
0x1800271e3  mov     r8d, [rsp+120h+var_C8]; unsigned int
0x1800271e8  neg     rax
0x1800271eb  lea     rax, [rsp+120h+var_CC]
0x1800271f0  mov     [rsp+120h+var_D0], 0
0x1800271f8  sbb     rcx, rcx
0x1800271fb  mov     edx, esi; unsigned int
0x1800271fd  and     rcx, rax
0x180027200  lea     rax, [rsp+120h+var_D0]
0x180027205  mov     [rsp+120h+var_E0], rax; int *
0x18002720a  mov     rax, [rbp+3Fh+var_B8]
0x18002720e  mov     [rsp+120h+var_E8], rcx; unsigned int *
0x180027213  mov     rcx, r14; this
0x180027216  mov     [rsp+120h+var_F0], rdi; struct tagPROPERTY_INFORMATION *
0x18002721b  mov     [rsp+120h+var_F8], r12; struct tagPROPVARIANT *
0x180027220  mov     [rsp+120h+var_100], rax; unsigned int *
0x180027225  call    ?ConvertVariantToPropInfo@@YAXPEAVCPropertySetStream@@KKQEBUtagPROPSPEC@@QEAKQEBUtagPROPVARIANT@@PEAUtagPROPERTY_INFORMATION@@PEAKPEAJ@Z; ConvertVariantToPropInfo(CPropertySetStream *,ulong,ulong,tagPROPSPEC const * const,ulong * const,tagPROPVARIANT const * const,tagPROPERTY_INFORMATION *,ulong *,long *)
0x18002722a  mov     eax, [rsp+120h+var_D0]
0x18002722e  test    eax, eax
0x180027230  js      short loc_180027264
0x180027232  lea     rax, [rsp+120h+var_D0]
0x180027237  mov     r9, r12; struct tagPROPVARIANT *
0x18002723a  mov     [rsp+120h+var_F0], rax; int *
0x18002723f  mov     r8, rbx; struct _INDIRECTPROPERTY **
0x180027242  mov     [rsp+120h+var_F8], r13; unsigned __int16 *
0x180027247  mov     edx, esi; unsigned int
0x180027249  mov     rcx, r14; this
0x18002724c  mov     [rsp+120h+var_100], rdi; struct tagPROPERTY_INFORMATION *
0x180027251  call    ?SetValue@CPropertySetStream@@QEAAXKPEAPEAU_INDIRECTPROPERTY@@QEBUtagPROPVARIANT@@PEAUtagPROPERTY_INFORMATION@@PEAGPEAJ@Z; CPropertySetStream::SetValue(ulong,_INDIRECTPROPERTY * *,tagPROPVARIANT const * const,tagPROPERTY_INFORMATION *,ushort *,long *)
0x180027256  mov     eax, [rsp+120h+var_D0]
0x18002725a  test    eax, eax
0x18002725c  js      short loc_180027264
0x18002725e  xor     eax, eax
0x180027260  mov     [rsp+120h+var_D0], eax
0x180027264  test    rdi, rdi
0x180027267  jnz     short loc_1800272A0
0x180027269  test    eax, eax
0x18002726b  js      loc_180027305
0x180027271  test    r15d, r15d
0x180027274  jz      short loc_180027280
0x180027276  mov     edx, eax; int
0x180027278  mov     rcx, r14; struct CPropertySetStream *
0x18002727b  call    ?Unlock@@YAJPEAVCPropertySetStream@@J@Z; Unlock(CPropertySetStream *,long)
0x180027280  mov     rcx, [rbp+3Fh+var_50]
0x180027284  xor     rcx, rsp; StackCookie
0x180027287  call    __security_check_cookie
0x18002728c  add     rsp, 0E8h
0x180027293  pop     r15
0x180027295  pop     r14
0x180027297  pop     r13
0x180027299  pop     r12
0x18002729b  pop     rdi
0x18002729c  pop     rsi
0x18002729d  pop     rbx
0x18002729e  pop     rbp
0x18002729f  retn
0x1800272a0  lea     rcx, [rbp+3Fh+pv]
0x1800272a4  cmp     rdi, rcx
0x1800272a7  jz      short loc_180027269
0x1800272a9  mov     rcx, rdi; pv
0x1800272ac  call    cs:__imp_CoTaskMemFree
0x1800272b2  mov     eax, [rsp+120h+var_D0]
0x1800272b6  jmp     short loc_180027269
0x1800272b8  mov     [rbx], r15
0x1800272bb  cmp     esi, 1
0x1800272be  jnz     loc_180027192
0x1800272c4  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800272ca  jmp     loc_180027192
0x1800272cf  mov     rdx, rsi; unsigned __int64
0x1800272d2  lea     r8, [rsp+120h+cb]; unsigned __int64 *
0x1800272d7  mov     ecx, 0Ch; unsigned __int64
0x1800272dc  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800272e1  test    eax, eax
0x1800272e3  js      short loc_1800272FC
0x1800272e5  mov     rcx, [rsp+120h+cb]; cb
0x1800272ea  call    cs:__imp_CoTaskMemAlloc
0x1800272f0  mov     rdi, rax
0x1800272f3  test    rax, rax
0x1800272f6  jnz     loc_1800271C3
0x1800272fc  mov     eax, 0C000009Ah
0x180027301  mov     [rsp+120h+var_D0], eax
0x180027305  test    rbx, rbx
0x180027308  jz      loc_180027271
0x18002730e  cmp     esi, 1
0x180027311  jnz     short loc_18002731E
0x180027313  mov     dword ptr [rbx], 0FFFFFFFFh
0x180027319  jmp     loc_180027271
0x18002731e  mov     rcx, [rbx]; pv
0x180027321  test    rcx, rcx
0x180027324  jz      loc_180027271
0x18002732a  call    cs:__imp_CoTaskMemFree
0x180027330  mov     eax, [rsp+120h+var_D0]
0x180027334  mov     qword ptr [rbx], 0
0x18002733b  jmp     loc_180027271
```
