# CCscNetApiInterfaceImpl::NetWkstaGetInfo(ulong,ushort const *,ulong,uchar * *)

- ea: `0x180001020`
- end: `0x18000168f`
- name: `?NetWkstaGetInfo@CCscNetApiInterfaceImpl@@UEAAKKPEBGKPEAPEAE@Z`
- size: `1647`
- prototype: `unsigned int __fastcall(CCscNetApiInterfaceImpl *__hidden this, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180001010`

## callees

- `0x180001020`
- `0x180002820`
- `0x1800029a0`
- `0x180002b70`
- `0x1800036b0`
- `0x180003da0`
- `0x180006560`
- `0x180006750`
- `0x18000683c`
- `0x180008330`
- `0x18000854c`
- `0x180008a90`
- `0x180009456`
- `0x180009462`
- `0x180009490`
- `0x18000a010`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180001681`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180001681`

## pseudocode

```c
__int64 __fastcall CCscNetApiInterfaceImpl::NetWkstaGetInfo(
        CCscNetApiInterfaceImpl *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int8 **a5)
{
  char v5; // r14
  unsigned __int8 *v8; // rbx
  ULONG v10; // r15d
  void **v11; // r12
  __int64 v12; // rdx
  const unsigned __int16 *i; // r8
  bool v14; // zf
  int v15; // ebx
  NTSTATUS OpenPattern; // eax
  CCscNetApiInterfaceImpl *v17; // rdi
  unsigned __int8 **v18; // r13
  unsigned __int8 v20; // bl
  int v21; // ecx
  unsigned int v22; // ecx
  unsigned __int16 v23; // ax
  bool v24; // cc
  int v25; // edi
  unsigned __int16 v26; // ax
  int VariableSizeFromStrings; // eax
  _WORD *v28; // rdi
  unsigned __int64 v29; // rbx
  __int64 v30; // rdi
  int v31; // ebx
  unsigned __int8 *v32; // rax
  __int64 v33; // rcx
  unsigned __int8 v34; // [rsp+40h] [rbp-C0h]
  int v35; // [rsp+44h] [rbp-BCh] BYREF
  char v36[8]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 **v37; // [rsp+50h] [rbp-B0h]
  CCscNetApiInterfaceImpl *v38; // [rsp+58h] [rbp-A8h]
  unsigned __int8 *v39; // [rsp+60h] [rbp-A0h] BYREF
  void *Src[2]; // [rsp+68h] [rbp-98h] BYREF
  HANDLE FileHandle; // [rsp+78h] [rbp-88h] BYREF
  void **v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h] BYREF
  void **v44; // [rsp+90h] [rbp-70h] BYREF
  void *v45; // [rsp+98h] [rbp-68h]
  _DWORD Size[4]; // [rsp+A0h] [rbp-60h]
  __int128 v47; // [rsp+B0h] [rbp-50h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  __int128 v49; // [rsp+D0h] [rbp-30h]
  int v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E4h] [rbp-1Ch]
  char v52; // [rsp+E8h] [rbp-18h]
  void *v53[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+110h] [rbp+10h]
  _BYTE v56[560]; // [rsp+120h] [rbp+20h] BYREF

  v5 = 0;
  v38 = this;
  v37 = a5;
  v35 = -1073741811;
  v8 = *a5;
  v34 = 0;
  v36[0] = 0;
  v42 = 0;
  v10 = 0;
  v11 = 0;
  *(_OWORD *)Src = 0;
  memset_0(v56, 0, 0x226u);
  v39 = 0;
  v45 = 0;
  v47 = 0;
  v44 = &CDescriptor_WKSTA_INFO::`vftable';
  v48 = 0;
  Size[0] = 0;
  v49 = 0;
  v50 = -1;
  *(_OWORD *)v53 = 0;
  v51 = 0;
  v54 = 0;
  v52 = 0;
  v55 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_DSDq(*((_QWORD *)WPP_GLOBAL_Control + 27), v12, (_DWORD)i, a2, (__int64)a3, a4, (char)v8);
  }
  if ( a2 > 0x79 )
  {
    if ( a2 == 1231 )
      goto LABEL_28;
    v14 = a2 == 2114;
  }
  else
  {
    if ( a2 == 121 || a2 == 53 || a2 == 64 )
      goto LABEL_28;
    v14 = a2 == 67;
  }
  if ( !v14 )
  {
    v15 = 3767;
LABEL_10:
    OpenPattern = -1073741811;
LABEL_11:
    v5 = 1;
LABEL_12:
    v17 = v38;
LABEL_13:
    LOBYTE(v12) = 0;
LABEL_14:
    v18 = v37;
    goto LABEL_15;
  }
LABEL_28:
  if ( v8 || !a3 || !*a3 )
  {
    v15 = 3778;
    goto LABEL_10;
  }
  if ( a4 != 102 && a4 != 100 && a4 != 101 )
  {
    v15 = 3795;
    goto LABEL_10;
  }
  v20 = 0;
  if ( *a3 == 92 )
  {
    if ( a3[1] != 92 || (v26 = a3[2], v26 == 92) || v26 == 47 || !v26 )
    {
LABEL_63:
      v15 = 3807;
      *(_OWORD *)Src = 0;
      goto LABEL_10;
    }
    v20 = 1;
  }
  v21 = 2 * v20;
  v12 = (unsigned int)(v21 + 1);
  v22 = v21 + 256;
  for ( i = &a3[v12]; ; ++i )
  {
    v23 = *i;
    if ( !*i )
    {
      v24 = (unsigned int)v12 <= v22;
LABEL_40:
      if ( !v24 )
        goto LABEL_63;
      goto LABEL_41;
    }
    v24 = (unsigned int)v12 <= v22;
    if ( (unsigned int)v12 >= v22 )
      goto LABEL_40;
    if ( v23 == 92 || v23 == 47 )
      break;
    v12 = (unsigned int)(v12 + 1);
  }
  if ( i[1] )
    goto LABEL_63;
LABEL_41:
  LOWORD(v12) = 2 * v12;
  Src[1] = (void *)a3;
  LOWORD(Src[0]) = v12;
  WORD1(Src[0]) = v12;
  if ( !CscUmpLibraryState )
  {
    OpenPattern = -1073741436;
    v15 = 3818;
    v35 = -1073741436;
    goto LABEL_11;
  }
  FileHandle = 0;
  v35 = CscDriverpReferenceControlHandle(&FileHandle);
  v25 = v35;
  if ( v35 >= 0 )
  {
    v35 = 0;
    v43 = 0x1C00000008LL;
    v25 = CscDriverpFsControlEx(FileHandle, v12, &v35, &v43, 8u, v36, 1u);
    v35 = v25;
    CscDriverpDereferenceControlHandle(&FileHandle);
  }
  if ( v25 < 0 || !v36[0] )
  {
    OpenPattern = v35;
    v15 = 3818;
    goto LABEL_11;
  }
  v50 = a4;
  v51 = 0;
  memset_0(v45, 0, Size[0]);
  *(_QWORD *)&Size[1] = -1;
  Size[3] = -1;
  v52 = ((__int64 (__fastcall *)(void ***, _QWORD))*v44)(&v44, a4);
  if ( !v52 )
  {
    OpenPattern = v35;
    v15 = 3833;
    goto LABEL_11;
  }
  if ( v20 )
  {
    Src[1] = (char *)Src[1] + 4;
    LOWORD(Src[0]) -= 4;
    WORD1(Src[0]) = Src[0];
  }
  OpenPattern = CscUmFindOpenPattern(&v42, 0, (const UNICODE_STRING *)Src);
  v35 = OpenPattern;
  if ( OpenPattern == -1073741765
    || OpenPattern == -1073741809
    || OpenPattern == -1073741773
    || OpenPattern == -1073741772
    || OpenPattern == -1073741767
    || OpenPattern == -1073741766 )
  {
    v11 = v42;
    v15 = 3865;
    goto LABEL_11;
  }
  v11 = v42;
  if ( OpenPattern < 0 )
  {
    v15 = 3867;
    goto LABEL_12;
  }
  OpenPattern = CscUmFindNext(v42, v56, 0);
  v35 = OpenPattern;
  if ( OpenPattern == -2147483642 )
  {
    v15 = 3886;
    goto LABEL_11;
  }
  v17 = v38;
  if ( OpenPattern < 0 )
  {
    v15 = 3888;
    goto LABEL_13;
  }
  v10 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int8 **))v38 + 4))(a4, &v39);
  if ( v10 )
  {
    OpenPattern = v35;
    LOBYTE(v12) = 1;
    v34 = 1;
    v15 = 3902;
    goto LABEL_14;
  }
  CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(&v44, v53, v39);
  VariableSizeFromStrings = CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::GetVariableSizeFromStrings(&v44, v53);
  if ( LOWORD(Src[0]) <= LOWORD(v53[0]) )
  {
    v28 = v53[1];
    v29 = LOWORD(Src[0]);
    memcpy_0(v53[1], Src[1], LOWORD(Src[0]));
    v18 = v37;
    v28[v29 >> 1] = 0;
    v15 = 3925;
    *v18 = v39;
    OpenPattern = 0;
    v35 = 0;
    LOBYTE(v12) = 0;
    v39 = 0;
    goto LABEL_17;
  }
  v30 = (__int64)v39;
  v31 = VariableSizeFromStrings + v51;
  v39 = 0;
  v10 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int8 **))v38 + 2))(
          (unsigned int)(VariableSizeFromStrings + v51),
          &v39);
  if ( v10 )
  {
    OpenPattern = v35;
    LOBYTE(v12) = 1;
    v34 = 1;
    v15 = 3939;
  }
  else
  {
    FileHandle = v39;
    v43 = (__int64)&v39[v31];
    if ( CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CopyOrFillEntry(
           (__int64)&v44,
           &FileHandle,
           &v43,
           (__int64)v53,
           v30) )
    {
      v32 = v39;
      v15 = 0;
      v18 = v37;
      v39 = 0;
      *v37 = v32;
      OpenPattern = 0;
      v35 = 0;
      LOBYTE(v12) = 0;
      goto LABEL_87;
    }
    OpenPattern = -1073740768;
    v15 = 3952;
    v35 = -1073740768;
    LOBYTE(v12) = 0;
  }
  v18 = v37;
LABEL_87:
  if ( v30 )
  {
    v33 = v30;
    v17 = v38;
    (*((void (__fastcall **)(__int64, __int64))v38 + 3))(v33, v12);
    OpenPattern = v35;
    v12 = v34;
  }
  else
  {
    v17 = v38;
  }
LABEL_15:
  if ( v39 )
  {
    (*((void (__fastcall **)(unsigned __int8 *, __int64))v17 + 3))(v39, v12);
    OpenPattern = v35;
    LOBYTE(v12) = v34;
  }
LABEL_17:
  if ( v11 )
  {
    CscUmFindClose(v11);
    OpenPattern = v35;
    LOBYTE(v12) = v34;
  }
  if ( v5 )
  {
    v10 = a2;
  }
  else if ( !(_BYTE)v12 )
  {
    v10 = RtlNtStatusToDosErrorNoTeb(OpenPattern);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, i, *v18, v10, v15);
  }
  return v10;
}

```

## disassembly

```asm
0x180001020  push    rbp
0x180001022  push    rbx
0x180001023  push    rsi
0x180001024  push    rdi
0x180001025  push    r12
0x180001027  push    r13
0x180001029  push    r14
0x18000102b  push    r15
0x18000102d  lea     rbp, [rsp-268h]
0x180001035  sub     rsp, 368h
0x18000103c  mov     rax, cs:__security_cookie
0x180001043  xor     rax, rsp
0x180001046  mov     [rbp+2A0h+var_50], rax
0x18000104d  mov     rax, [rbp+2A0h+arg_20]
0x180001054  xor     r14d, r14d
0x180001057  mov     rdi, r8
0x18000105a  mov     [rsp+3A0h+var_348], rcx
0x18000105f  mov     esi, edx
0x180001061  mov     [rsp+3A0h+var_350], rax
0x180001066  xorps   xmm0, xmm0
0x180001069  mov     [rsp+3A0h+var_35C], 0C000000Dh
0x180001071  mov     rbx, [rax]
0x180001074  lea     rcx, [rbp+2A0h+var_280]; void *
0x180001078  xor     edx, edx; Val
0x18000107a  mov     [rsp+3A0h+var_360], r14b
0x18000107f  mov     r8d, 226h; Size
0x180001085  mov     [rsp+3A0h+var_358], r14b
0x18000108a  mov     r13d, r9d
0x18000108d  mov     [rbp+2A0h+var_320], r14
0x180001091  mov     r15d, r14d
0x180001094  mov     r12d, r14d
0x180001097  movups  xmmword ptr [rsp+3A0h+Src], xmm0
0x18000109c  call    memset_0
0x1800010a1  xorps   xmm0, xmm0
0x1800010a4  mov     [rsp+3A0h+var_340], r14
0x1800010a9  lea     rax, ??_7CDescriptor_WKSTA_INFO@@6B@; const CDescriptor_WKSTA_INFO::`vftable'
0x1800010b0  mov     [rbp+2A0h+var_308], r14
0x1800010b4  movups  [rbp+2A0h+var_2F0], xmm0
0x1800010b8  mov     [rbp+2A0h+var_310], rax
0x1800010bc  movups  [rbp+2A0h+var_2E0], xmm0
0x1800010c0  mov     dword ptr [rbp+2A0h+Size], r14d
0x1800010c4  movups  [rbp+2A0h+var_2D0], xmm0
0x1800010c8  mov     [rbp+2A0h+var_2C0], 0FFFFFFFFh
0x1800010cf  movups  xmmword ptr [rbp+2A0h+var_2B0], xmm0
0x1800010d3  mov     [rbp+2A0h+var_2BC], r14d
0x1800010d7  movups  [rbp+2A0h+var_2A0], xmm0
0x1800010db  mov     [rbp+2A0h+var_2B8], r12b
0x1800010df  movups  [rbp+2A0h+var_290], xmm0
0x1800010e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800010ea  lea     rax, WPP_GLOBAL_Control
0x1800010f1  cmp     rcx, rax
0x1800010f4  jz      short loc_180001103
0x1800010f6  test    byte ptr [rcx+0E4h], 1
0x1800010fd  jnz     loc_180001397
0x180001103  cmp     esi, 79h ; 'y'
0x180001106  ja      loc_1800011A2
0x18000110c  jz      loc_1800011E7
0x180001112  cmp     esi, 35h ; '5'
0x180001115  jz      loc_1800011E7
0x18000111b  cmp     esi, 40h ; '@'
0x18000111e  jz      loc_1800011E7
0x180001124  cmp     esi, 43h ; 'C'
0x180001127  jz      loc_1800011E7
0x18000112d  mov     ebx, 0EB7h
0x180001132  mov     eax, 0C000000Dh
0x180001137  mov     r14b, 1
0x18000113a  mov     rdi, [rsp+3A0h+var_348]
0x18000113f  xor     dl, dl
0x180001141  mov     r13, [rsp+3A0h+var_350]
0x180001146  mov     rcx, [rsp+3A0h+var_340]
0x18000114b  test    rcx, rcx
0x18000114e  jnz     loc_18000164A
0x180001154  test    r12, r12
0x180001157  jnz     loc_180001661
0x18000115d  test    r14b, r14b
0x180001160  jz      loc_180001677
0x180001166  mov     r15d, esi
0x180001169  mov     rcx, cs:WPP_GLOBAL_Control
0x180001170  lea     rax, WPP_GLOBAL_Control
0x180001177  cmp     rcx, rax
0x18000117a  jnz     short loc_1800011B5
0x18000117c  mov     eax, r15d
0x18000117f  mov     rcx, [rbp+2A0h+var_50]
0x180001186  xor     rcx, rsp; StackCookie
0x180001189  call    __security_check_cookie
0x18000118e  add     rsp, 368h
0x180001195  pop     r15
0x180001197  pop     r14
0x180001199  pop     r13
0x18000119b  pop     r12
0x18000119d  pop     rdi
0x18000119e  pop     rsi
0x18000119f  pop     rbx
0x1800011a0  pop     rbp
0x1800011a1  retn
0x1800011a2  cmp     esi, 4CFh
0x1800011a8  jz      short loc_1800011E7
0x1800011aa  cmp     esi, 842h
0x1800011b0  jmp     loc_180001127
0x1800011b5  test    byte ptr [rcx+0E4h], 1
0x1800011bc  jz      short loc_18000117C
0x1800011be  cmp     byte ptr [rcx+0E1h], 4
0x1800011c5  jb      short loc_18000117C
0x1800011c7  mov     r9, [r13+0]
0x1800011cb  mov     edx, 11h
0x1800011d0  mov     rcx, [rcx+0D8h]
0x1800011d7  mov     dword ptr [rsp+3A0h+var_378], ebx
0x1800011db  mov     [rsp+3A0h+var_380], r15d
0x1800011e0  call    WPP_SF_qDD
0x1800011e5  jmp     short loc_18000117C
0x1800011e7  test    rbx, rbx
0x1800011ea  jnz     loc_180001640
0x1800011f0  test    rdi, rdi
0x1800011f3  jz      loc_180001640
0x1800011f9  movzx   eax, word ptr [rdi]
0x1800011fc  test    ax, ax
0x1800011ff  jz      loc_180001640
0x180001205  cmp     r13d, 66h ; 'f'
0x180001209  jnz     loc_1800013C7
0x18000120f  xor     bl, bl
0x180001211  mov     ecx, 5Ch ; '\'
0x180001216  cmp     cx, ax
0x180001219  jz      loc_1800013E6
0x18000121f  movzx   eax, bl
0x180001222  lea     ecx, [rax+rax]
0x180001225  lea     edx, [rcx+1]
0x180001228  add     ecx, 100h
0x18000122e  lea     r8, [rdi+rdx*2]
0x180001232  movzx   eax, word ptr [r8]
0x180001236  test    ax, ax
0x180001239  jz      short loc_18000125B
0x18000123b  cmp     edx, ecx
0x18000123d  jnb     short loc_18000125D
0x18000123f  cmp     ax, 5Ch ; '\'
0x180001243  jz      loc_180001407
0x180001249  cmp     ax, 2Fh ; '/'
0x18000124d  jz      loc_180001407
0x180001253  add     r8, 2
0x180001257  inc     edx
0x180001259  jmp     short loc_180001232
0x18000125b  cmp     edx, ecx
0x18000125d  ja      loc_180001412
0x180001263  add     dx, dx
0x180001266  mov     [rsp+3A0h+Src+8], rdi
0x18000126b  cmp     cs:CscUmpLibraryState, r12d
0x180001272  mov     word ptr [rsp+3A0h+Src], dx
0x180001277  mov     word ptr [rsp+3A0h+Src+2], dx
0x18000127c  jnz     short loc_180001291
0x18000127e  mov     eax, 0C0000184h
0x180001283  mov     ebx, 0EEAh
0x180001288  mov     [rsp+3A0h+var_35C], eax
0x18000128c  jmp     loc_180001137
0x180001291  lea     rcx, [rsp+3A0h+FileHandle]
0x180001296  mov     [rsp+3A0h+FileHandle], r14
0x18000129b  call    CscDriverpReferenceControlHandle
0x1800012a0  mov     [rsp+3A0h+var_35C], eax
0x1800012a4  mov     edi, eax
0x1800012a6  test    eax, eax
0x1800012a8  jns     short loc_180001315
0x1800012aa  test    edi, edi
0x1800012ac  js      short loc_180001307
0x1800012ae  cmp     [rsp+3A0h+var_358], r12b
0x1800012b3  jz      short loc_180001307
0x1800012b5  mov     r8d, dword ptr [rbp+2A0h+Size]; Size
0x1800012b9  xor     edx, edx; Val
0x1800012bb  mov     rcx, [rbp+2A0h+var_308]; void *
0x1800012bf  mov     [rbp+2A0h+var_2C0], r13d
0x1800012c3  mov     [rbp+2A0h+var_2BC], r14d
0x1800012c7  call    memset_0
0x1800012cc  mov     rax, [rbp+2A0h+var_310]
0x1800012d0  lea     rcx, [rbp+2A0h+var_310]
0x1800012d4  mov     edx, r13d
0x1800012d7  mov     qword ptr [rbp+2A0h+Size+4], 0FFFFFFFFFFFFFFFFh
0x1800012df  mov     [rbp+2A0h+var_2F4], 0FFFFFFFFh
0x1800012e6  mov     rax, [rax]
0x1800012e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012ee  mov     [rbp+2A0h+var_2B8], al
0x1800012f1  test    al, al
0x1800012f3  jnz     loc_180001424
0x1800012f9  mov     eax, [rsp+3A0h+var_35C]
0x1800012fd  mov     ebx, 0EF9h
0x180001302  jmp     loc_180001137
0x180001307  mov     eax, [rsp+3A0h+var_35C]
0x18000130b  mov     ebx, 0EEAh
0x180001310  jmp     loc_180001137
0x180001315  mov     rcx, [rsp+3A0h+FileHandle]; FileHandle
0x18000131a  lea     rax, [rsp+3A0h+var_358]
0x18000131f  mov     [rsp+3A0h+var_370], 1; ULONG
0x180001327  lea     r9, [rbp+2A0h+var_318]
0x18000132b  mov     [rsp+3A0h+var_378], rax; PVOID
0x180001330  lea     r8, [rsp+3A0h+var_35C]
0x180001335  mov     [rsp+3A0h+var_380], 8; ULONG
0x18000133d  mov     [rsp+3A0h+var_35C], r14d
0x180001342  mov     dword ptr [rbp+2A0h+var_318], 8
0x180001349  mov     dword ptr [rbp+2A0h+var_318+4], 1Ch
0x180001350  call    CscDriverpFsControlEx
0x180001355  mov     edi, eax
0x180001357  mov     [rsp+3A0h+var_35C], eax
0x18000135b  lea     rcx, [rsp+3A0h+FileHandle]
0x180001360  call    CscDriverpDereferenceControlHandle
0x180001365  jmp     loc_1800012AA
0x18000136a  lea     r8, [rsp+3A0h+Src]
0x18000136f  xor     edx, edx
0x180001371  lea     rcx, [rbp+2A0h+var_320]
0x180001375  call    CscUmFindOpenPattern
0x18000137a  mov     [rsp+3A0h+var_35C], eax
0x18000137e  cmp     eax, 0C000003Bh
0x180001383  jnz     loc_18000144E
0x180001389  mov     r12, [rbp+2A0h+var_320]
0x18000138d  mov     ebx, 0F19h
0x180001392  jmp     loc_180001137
0x180001397  cmp     byte ptr [rcx+0E1h], 4
0x18000139e  jb      loc_180001103
0x1800013a4  mov     rcx, [rcx+0D8h]
0x1800013ab  mov     r9d, esi
0x1800013ae  mov     qword ptr [rsp+3A0h+var_370], rbx
0x1800013b3  mov     dword ptr [rsp+3A0h+var_378], r13d
0x1800013b8  mov     qword ptr [rsp+3A0h+var_380], rdi
0x1800013bd  call    WPP_SF_DSDq
0x1800013c2  jmp     loc_180001103
0x1800013c7  mov     ecx, r13d
0x1800013ca  sub     ecx, 64h ; 'd'
0x1800013cd  jz      loc_18000120F
0x1800013d3  cmp     ecx, 1
0x1800013d6  jz      loc_18000120F
0x1800013dc  mov     ebx, 0ED3h
0x1800013e1  jmp     loc_180001132
0x1800013e6  cmp     cx, [rdi+2]
0x1800013ea  jnz     short loc_180001412
0x1800013ec  movzx   eax, word ptr [rdi+4]
0x1800013f0  cmp     ax, cx
0x1800013f3  jz      short loc_180001412
0x1800013f5  cmp     ax, 2Fh ; '/'
0x1800013f9  jz      short loc_180001412
0x1800013fb  test    ax, ax
0x1800013fe  jz      short loc_180001412
0x180001400  mov     bl, 1
0x180001402  jmp     loc_18000121F
0x180001407  cmp     [r8+2], r12w
0x18000140c  jz      loc_180001263
0x180001412  xorps   xmm0, xmm0
0x180001415  mov     ebx, 0EDFh
0x18000141a  movups  xmmword ptr [rsp+3A0h+Src], xmm0
0x18000141f  jmp     loc_180001132
0x180001424  test    bl, bl
0x180001426  jz      loc_18000136A
0x18000142c  movzx   eax, word ptr [rsp+3A0h+Src]
0x180001431  mov     ecx, 0FFFCh
0x180001436  add     [rsp+3A0h+Src+8], 4
0x18000143c  add     ax, cx
0x18000143f  mov     word ptr [rsp+3A0h+Src], ax
0x180001444  mov     word ptr [rsp+3A0h+Src+2], ax
0x180001449  jmp     loc_18000136A
0x18000144e  cmp     eax, 0C000000Fh
0x180001453  jz      loc_180001389
0x180001459  cmp     eax, 0C0000033h
0x18000145e  jz      loc_180001389
0x180001464  cmp     eax, 0C0000034h
0x180001469  jz      loc_180001389
0x18000146f  cmp     eax, 0C0000039h
0x180001474  jz      loc_180001389
0x18000147a  cmp     eax, 0C000003Ah
0x18000147f  jz      loc_180001389
0x180001485  mov     r12, [rbp+2A0h+var_320]
0x180001489  test    eax, eax
0x18000148b  jns     short loc_180001497
0x18000148d  mov     ebx, 0F1Bh
0x180001492  jmp     loc_18000113A
0x180001497  xor     r8d, r8d
0x18000149a  lea     rdx, [rbp+2A0h+var_280]
0x18000149e  mov     rcx, r12
0x1800014a1  call    CscUmFindNext
0x1800014a6  mov     [rsp+3A0h+var_35C], eax
0x1800014aa  cmp     eax, 80000006h
0x1800014af  jnz     short loc_1800014BB
0x1800014b1  mov     ebx, 0F2Eh
0x1800014b6  jmp     loc_180001137
0x1800014bb  mov     rdi, [rsp+3A0h+var_348]
0x1800014c0  test    eax, eax
0x1800014c2  jns     short loc_1800014CE
0x1800014c4  mov     ebx, 0F30h
0x1800014c9  jmp     loc_18000113F
0x1800014ce  mov     rax, [rdi+20h]
0x1800014d2  lea     rdx, [rsp+3A0h+var_340]
0x1800014d7  mov     ecx, r13d
0x1800014da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014df  mov     r15d, eax
0x1800014e2  test    eax, eax
0x1800014e4  jz      short loc_1800014FA
0x1800014e6  mov     eax, [rsp+3A0h+var_35C]
0x1800014ea  mov     dl, 1
0x1800014ec  mov     [rsp+3A0h+var_360], dl
0x1800014f0  mov     ebx, 0F3Eh
0x1800014f5  jmp     loc_180001141
0x1800014fa  mov     r8, [rsp+3A0h+var_340]
0x1800014ff  lea     rdx, [rbp+2A0h+var_2B0]
0x180001503  lea     rcx, [rbp+2A0h+var_310]
0x180001507  call    ?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z; CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *,void *)
0x18000150c  lea     rdx, [rbp+2A0h+var_2B0]
0x180001510  lea     rcx, [rbp+2A0h+var_310]
  ... truncated ...
```
