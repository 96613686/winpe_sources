# CCscNetApiInterfaceImpl::NetShareGetInfo(ulong,ushort const *,ushort const *,ulong,uchar * *)

- ea: `0x180002080`
- end: `0x180002814`
- name: `?NetShareGetInfo@CCscNetApiInterfaceImpl@@UEAAKKPEBG0KPEAPEAE@Z`
- size: `1940`
- prototype: `unsigned int __fastcall(CCscNetApiInterfaceImpl *__hidden this, unsigned int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180002070`

## callees

- `0x180002080`
- `0x1800029a0`
- `0x180002a40`
- `0x180002b70`
- `0x180002db0`
- `0x1800036b0`
- `0x180003da0`
- `0x180003ef0`
- `0x1800064f0`
- `0x180006560`
- `0x180008730`
- `0x180008a90`
- `0x180009456`
- `0x180009462`
- `0x180009490`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002305`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002305`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180002363`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800023de`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x180002363`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800023de`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002341`
- `ntdll!RtlInitUnicodeStringEx` at `0x180002341`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002807`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180002807`
- `ntdll!RtlDuplicateUnicodeString` at `0x18000241c`
- `ntdll!RtlDuplicateUnicodeString` at `0x18000241c`

## pseudocode

```c
__int64 __fastcall CCscNetApiInterfaceImpl::NetShareGetInfo(
        CCscNetApiInterfaceImpl *this,
        ULONG a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int8 **a6)
{
  ULONG v8; // edi
  unsigned __int8 *v9; // rbx
  NTSTATUS inited; // r13d
  void *v11; // r14
  void **v12; // rsi
  unsigned __int64 i; // r8
  int v14; // r12d
  char v15; // bl
  __int16 v17; // cx
  unsigned __int8 v18; // al
  int v19; // ecx
  __int64 v20; // rdx
  unsigned int v21; // ecx
  __int16 v22; // ax
  bool v23; // cc
  __int64 v24; // rdx
  _DWORD *v25; // rax
  struct _UNICODE_STRING *v26; // rax
  __int64 v27; // rdx
  int Next; // eax
  int v29; // ecx
  unsigned int v30; // r12d
  void *v31; // r13
  unsigned int v32; // ecx
  __int64 j; // r12
  unsigned __int8 *v34; // rax
  unsigned __int16 v35; // ax
  ULONG v36; // [rsp+30h] [rbp-D0h]
  char v37; // [rsp+40h] [rbp-C0h] BYREF
  char v38; // [rsp+41h] [rbp-BFh]
  char v39; // [rsp+42h] [rbp-BEh]
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR SourceString; // [rsp+70h] [rbp-90h]
  char *v45; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v46[2]; // [rsp+80h] [rbp-80h] BYREF
  CCscNetApiInterfaceImpl *v47; // [rsp+90h] [rbp-70h]
  unsigned __int8 **v48; // [rsp+98h] [rbp-68h]
  _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+C0h] [rbp-40h]
  __int128 v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  _OWORD v54[5]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v55; // [rsp+140h] [rbp+40h] BYREF
  __int128 v56; // [rsp+150h] [rbp+50h]
  void **v57; // [rsp+160h] [rbp+60h] BYREF
  void *v58; // [rsp+168h] [rbp+68h]
  int v59; // [rsp+170h] [rbp+70h]
  int v60; // [rsp+174h] [rbp+74h]
  int v61; // [rsp+178h] [rbp+78h]
  __int128 v62; // [rsp+180h] [rbp+80h]
  __int128 v63; // [rsp+190h] [rbp+90h]
  int v64; // [rsp+1A0h] [rbp+A0h]
  unsigned int Size; // [rsp+1A4h] [rbp+A4h]
  char Size_4; // [rsp+1A8h] [rbp+A8h]
  char v67; // [rsp+1B0h] [rbp+B0h] BYREF
  _WORD v68[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char v69; // [rsp+1D4h] [rbp+D4h] BYREF

  v47 = this;
  v8 = 0;
  SourceString = a4;
  v48 = a6;
  v9 = *a6;
  v39 = 0;
  v37 = 0;
  inited = -1073741811;
  *(_OWORD *)Src = 0;
  v11 = 0;
  v12 = 0;
  DestinationString = 0;
  memset_0(v68, 0, 0x226u);
  v59 = 24;
  v64 = -1;
  v41 = 0;
  v45 = 0;
  v58 = &v67;
  v57 = &CDescriptor_SHARE_INFO::`vftable';
  memset(v54, 0, sizeof(v54));
  Size = 0;
  Size_4 = 0;
  v62 = 0;
  v63 = 0;
  v55 = 0;
  v56 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_DSSDq(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_DWORD)SourceString,
      i,
      a2,
      (__int64)a3,
      (__int64)SourceString,
      a5,
      (char)v9);
  }
  if ( v9 || !a3 || (v17 = *a3) == 0 || !SourceString || !*SourceString )
  {
    v14 = 3494;
LABEL_5:
    v15 = 1;
    goto LABEL_6;
  }
  if ( a5 > 1 )
  {
    v14 = 3515;
    goto LABEL_5;
  }
  v18 = 0;
  v38 = 0;
  if ( v17 == 92 )
  {
    if ( a3[1] != 92 || (v35 = a3[2], v35 == 92) || v35 == 47 || !v35 )
    {
LABEL_88:
      v14 = 3527;
      *(_OWORD *)Src = 0;
      goto LABEL_5;
    }
    v18 = 1;
    v38 = 1;
  }
  v19 = 2 * v18;
  v20 = (unsigned int)(v19 + 1);
  v21 = v19 + 256;
  for ( i = (unsigned __int64)&a3[v20]; ; i += 2LL )
  {
    v22 = *(_WORD *)i;
    if ( !*(_WORD *)i )
    {
      v23 = (unsigned int)v20 <= v21;
LABEL_32:
      if ( !v23 )
        goto LABEL_88;
      goto LABEL_33;
    }
    v23 = (unsigned int)v20 <= v21;
    if ( (unsigned int)v20 >= v21 )
      goto LABEL_32;
    if ( v22 == 92 || v22 == 47 )
      break;
    LODWORD(v20) = v20 + 1;
  }
  if ( *(_WORD *)(i + 2) )
    goto LABEL_88;
LABEL_33:
  Src[1] = (void *)a3;
  LOWORD(Src[0]) = 2 * v20;
  WORD1(Src[0]) = 2 * v20;
  if ( !CscUmpLibraryState )
  {
    inited = -1073741436;
LABEL_35:
    v14 = 3538;
    goto LABEL_5;
  }
  FileHandle = 0;
  inited = CscDriverpReferenceControlHandle(&FileHandle);
  if ( inited >= 0 )
  {
    v42 = 0;
    v46[0] = 0x1C00000008LL;
    inited = CscDriverpFsControlEx(FileHandle, v24, &v42, v46, 8u, &v37, 1u);
    CscDriverpDereferenceControlHandle(&FileHandle);
  }
  if ( inited < 0 || !v37 )
    goto LABEL_35;
  v15 = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
  if ( inited < 0 )
  {
    v14 = 3546;
    goto LABEL_6;
  }
  if ( !v38 )
  {
    v25 = LocalAlloc(0, LOWORD(Src[0]) + 4LL);
    v11 = v25;
    if ( !v25 )
    {
      inited = -1073741670;
      v14 = 3551;
      goto LABEL_6;
    }
    *v25 = 6029404;
    memcpy_0(v25 + 1, Src[1], LOWORD(Src[0]));
    Src[1] = v11;
    LOWORD(Src[0]) += 4;
    WORD1(Src[0]) = Src[0];
  }
  v46[0] = 393220;
  v53 = 0;
  v46[1] = L"\\\\";
  v50 = 0;
  v51 = 0;
  v52 = 0;
  if ( CscUmpLibraryState )
  {
    v26 = (struct _UNICODE_STRING *)LocalAlloc(0, 0x30u);
    v12 = (void **)v26;
    if ( v26 )
    {
      *v26 = 0;
      v26[1] = 0;
      v26[2] = 0;
      *(_DWORD *)&v26->Length = 1130718291;
      LOBYTE(v26[2].Length) = 1;
      if ( DestinationString.Length && (inited = RtlDuplicateUnicodeString(0, &DestinationString, v26 + 1), inited < 0)
        || (inited = CscDriverOpenItemWithDispositionEx(
                       v12 + 1,
                       v27,
                       (const UNICODE_STRING *)Src,
                       6,
                       1048577,
                       7u,
                       v36,
                       1),
            inited < 0)
        || (inited = CscDriverQueryItemInformation(v12[1]), inited < 0) )
      {
LABEL_48:
        CscUmFindClose(v12);
        v12 = 0;
        if ( inited == -1073741765
          || inited == -1073741809
          || inited == -1073741773
          || inited == -1073741772
          || inited == -1073741767
          || inited == -1073741766 )
        {
          v14 = 3578;
          goto LABEL_5;
        }
        goto LABEL_51;
      }
      if ( (v53 & 0x10) == 0 )
      {
        inited = -1073741565;
        goto LABEL_48;
      }
    }
    else
    {
      inited = -1073741670;
    }
  }
  else
  {
    inited = -1073741436;
  }
LABEL_51:
  if ( inited < 0 )
  {
    v14 = 3580;
  }
  else
  {
    Next = CscUmFindNext(v12, v68, v54);
    inited = Next;
    if ( Next == -2147483642 )
    {
      v14 = 3599;
      goto LABEL_5;
    }
    if ( Next < 0 )
    {
      v14 = 3602;
    }
    else
    {
      if ( (v54[0] & 0x800000) != 0 )
      {
        v14 = 3610;
        goto LABEL_5;
      }
      if ( !(unsigned __int8)CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::Init(&v57, a5) )
      {
        v14 = 3621;
        goto LABEL_5;
      }
      DWORD1(v56) = (_DWORD)v45;
      *((_QWORD *)&v55 + 1) = &v69;
      *((_QWORD *)&v56 + 1) = L"[Offline Share]";
      v29 = 0;
      LOWORD(v55) = v68[0];
      WORD1(v55) = v68[0];
      LODWORD(v56) = 2097182;
      if ( v60 != -1 )
        v29 = v68[0] + 2;
      if ( v61 != -1 )
        v29 += 32;
      v30 = v29 + Size;
      v8 = (*((__int64 (__fastcall **)(_QWORD, void **))v47 + 2))(v29 + Size, &v41);
      if ( v8 )
      {
        v39 = 1;
        v14 = 3638;
      }
      else
      {
        v31 = v41;
        v32 = 0;
        v45 = (char *)v41 + v30;
        if ( v60 != -1 )
          v32 = (unsigned __int16)v55 + 2;
        if ( v61 != -1 )
          v32 += (unsigned __int16)v56 + 2;
        i = Size;
        if ( (char *)v41 + Size <= (char *)v41 + v30 - v32 )
        {
          if ( v58 )
            memcpy_0(v41, v58, Size);
          else
            memset_0(v41, 0, Size);
          for ( j = 0; j != 2; ++j )
            CopyString(v31, &v45, (unsigned int)*(&v60 + j), &v55 + j);
          v34 = (unsigned __int8 *)v41;
          v14 = 0;
          inited = 0;
          v41 = 0;
          *v48 = v34;
          goto LABEL_8;
        }
        inited = -1073740768;
        v14 = 3648;
      }
    }
  }
LABEL_6:
  if ( v41 )
    (*((void (**)(void))v47 + 3))();
LABEL_8:
  if ( v12 )
    CscUmFindClose(v12);
  if ( v11 )
    LocalFree(v11);
  if ( v15 )
  {
    v8 = a2;
  }
  else if ( !v39 )
  {
    v8 = RtlNtStatusToDosErrorNoTeb(inited);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 228) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 225) >= 4u )
  {
    WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, i, *v48, v8, v14);
  }
  return v8;
}

```

## disassembly

```asm
0x180002080  push    rbp
0x180002082  push    rbx
0x180002083  push    rsi
0x180002084  push    rdi
0x180002085  push    r12
0x180002087  push    r13
0x180002089  push    r14
0x18000208b  push    r15
0x18000208d  lea     rbp, [rsp-318h]
0x180002095  sub     rsp, 418h
0x18000209c  mov     rax, cs:__security_cookie
0x1800020a3  xor     rax, rsp
0x1800020a6  mov     [rbp+350h+var_50], rax
0x1800020ad  mov     rax, [rbp+350h+arg_28]
0x1800020b4  mov     r12, r8
0x1800020b7  mov     r15d, edx
0x1800020ba  mov     [rbp+350h+var_3C0], rcx
0x1800020be  xor     edi, edi
0x1800020c0  mov     [rsp+450h+SourceString], r9
0x1800020c5  xorps   xmm0, xmm0
0x1800020c8  mov     [rbp+350h+var_3B8], rax
0x1800020cc  mov     rbx, [rax]
0x1800020cf  lea     rcx, [rbp+350h+var_280]; void *
0x1800020d6  xorps   xmm1, xmm1
0x1800020d9  mov     [rsp+450h+var_40E], dil
0x1800020de  xor     edx, edx; Val
0x1800020e0  mov     [rsp+450h+var_410], dil
0x1800020e5  mov     r8d, 226h; Size
0x1800020eb  mov     r13d, 0C000000Dh
0x1800020f1  movups  xmmword ptr [rsp+450h+Src], xmm0
0x1800020f6  xor     r14d, r14d
0x1800020f9  xor     esi, esi
0x1800020fb  movups  xmmword ptr [rbp+350h+DestinationString.Length], xmm1
0x1800020ff  call    memset_0
0x180002104  xorps   xmm0, xmm0
0x180002107  mov     [rbp+350h+var_2E0], 18h
0x18000210e  xor     r9d, r9d
0x180002111  mov     [rbp+350h+var_2B0], 0FFFFFFFFh
0x18000211b  xor     eax, eax
0x18000211d  mov     [rsp+450h+var_3F8], r9
0x180002122  mov     [rsp+450h+var_3D8], rax
0x180002127  lea     rax, [rbp+350h+var_2A0]
0x18000212e  mov     [rbp+350h+var_2E8], rax
0x180002132  lea     rax, ??_7CDescriptor_SHARE_INFO@@6B@; const CDescriptor_SHARE_INFO::`vftable'
0x180002139  mov     [rbp+350h+var_2F0], rax
0x18000213d  movups  [rbp+350h+var_360], xmm0
0x180002141  mov     dword ptr [rbp+350h+Size], r9d
0x180002148  movups  [rbp+350h+var_350], xmm0
0x18000214c  mov     byte ptr [rbp+350h+Size+4], sil
0x180002153  movups  [rbp+350h+var_340], xmm0
0x180002157  movups  [rbp+350h+var_330], xmm0
0x18000215b  movups  [rbp+350h+var_320], xmm0
0x18000215f  movups  [rbp+350h+var_2D0], xmm0
0x180002166  movups  [rbp+350h+var_2C0], xmm0
0x18000216d  movups  [rbp+350h+var_310], xmm0
0x180002171  movups  [rbp+350h+var_300], xmm0
0x180002175  mov     rcx, cs:WPP_GLOBAL_Control
0x18000217c  lea     rax, WPP_GLOBAL_Control
0x180002183  cmp     rcx, rax
0x180002186  jz      short loc_180002195
0x180002188  test    byte ptr [rcx+0E4h], 1
0x18000218f  jnz     loc_1800026A8
0x180002195  test    rbx, rbx
0x180002198  jz      loc_18000223E
0x18000219e  mov     r12d, 0DA6h
0x1800021a4  mov     bl, 1
0x1800021a6  mov     rcx, [rsp+450h+var_3F8]
0x1800021ab  test    rcx, rcx
0x1800021ae  jnz     loc_1800027DA
0x1800021b4  test    rsi, rsi
0x1800021b7  jnz     loc_1800027EC
0x1800021bd  test    r14, r14
0x1800021c0  jnz     loc_180002302
0x1800021c6  test    bl, bl
0x1800021c8  jz      loc_1800027F9
0x1800021ce  mov     edi, r15d
0x1800021d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021d8  lea     rax, WPP_GLOBAL_Control
0x1800021df  cmp     rcx, rax
0x1800021e2  jnz     short loc_180002209
0x1800021e4  mov     eax, edi
0x1800021e6  mov     rcx, [rbp+350h+var_50]
0x1800021ed  xor     rcx, rsp; StackCookie
0x1800021f0  call    __security_check_cookie
0x1800021f5  add     rsp, 418h
0x1800021fc  pop     r15
0x1800021fe  pop     r14
0x180002200  pop     r13
0x180002202  pop     r12
0x180002204  pop     rdi
0x180002205  pop     rsi
0x180002206  pop     rbx
0x180002207  pop     rbp
0x180002208  retn
0x180002209  test    byte ptr [rcx+0E4h], 1
0x180002210  jz      short loc_1800021E4
0x180002212  cmp     byte ptr [rcx+0E1h], 4
0x180002219  jb      short loc_1800021E4
0x18000221b  mov     rax, [rbp+350h+var_3B8]
0x18000221f  mov     edx, 0Fh
0x180002224  mov     rcx, [rcx+0D8h]
0x18000222b  mov     dword ptr [rsp+450h+var_428], r12d
0x180002230  mov     [rsp+450h+var_430], edi
0x180002234  mov     r9, [rax]
0x180002237  call    WPP_SF_qDD
0x18000223c  jmp     short loc_1800021E4
0x18000223e  test    r12, r12
0x180002241  jz      loc_18000219E
0x180002247  movzx   ecx, word ptr [r12]
0x18000224c  test    cx, cx
0x18000224f  jz      loc_18000219E
0x180002255  mov     rax, [rsp+450h+SourceString]
0x18000225a  test    rax, rax
0x18000225d  jz      loc_18000219E
0x180002263  cmp     [rax], si
0x180002266  jz      loc_18000219E
0x18000226c  mov     eax, [rbp+350h+arg_20]
0x180002272  test    eax, eax
0x180002274  jz      short loc_18000227F
0x180002276  cmp     eax, 1
0x180002279  jnz     loc_1800026EA
0x18000227f  xor     al, al
0x180002281  mov     edx, 5Ch ; '\'
0x180002286  mov     [rsp+450h+var_40F], al
0x18000228a  cmp     dx, cx
0x18000228d  jz      loc_1800026F5
0x180002293  movzx   eax, al
0x180002296  lea     ecx, [rax+rax]
0x180002299  lea     edx, [rcx+1]
0x18000229c  add     ecx, 100h
0x1800022a2  lea     r8, [r12+rdx*2]
0x1800022a6  movzx   eax, word ptr [r8]
0x1800022aa  test    ax, ax
0x1800022ad  jz      short loc_1800022CF
0x1800022af  cmp     edx, ecx
0x1800022b1  jnb     short loc_1800022D1
0x1800022b3  cmp     ax, 5Ch ; '\'
0x1800022b7  jz      loc_18000271E
0x1800022bd  cmp     ax, 2Fh ; '/'
0x1800022c1  jz      loc_18000271E
0x1800022c7  add     r8, 2
0x1800022cb  inc     edx
0x1800022cd  jmp     short loc_1800022A6
0x1800022cf  cmp     edx, ecx
0x1800022d1  ja      loc_180002729
0x1800022d7  add     dx, dx
0x1800022da  mov     [rsp+450h+Src+8], r12
0x1800022df  cmp     cs:CscUmpLibraryState, esi
0x1800022e5  mov     word ptr [rsp+450h+Src], dx
0x1800022ea  mov     word ptr [rsp+450h+Src+2], dx
0x1800022ef  jnz     short loc_180002310
0x1800022f1  mov     r13d, 0C0000184h
0x1800022f7  mov     r12d, 0DD2h
0x1800022fd  jmp     loc_1800021A4
0x180002302  mov     rcx, r14; hMem
0x180002305  call    cs:__imp_LocalFree
0x18000230b  jmp     loc_1800021C6
0x180002310  lea     rcx, [rsp+450h+FileHandle]
0x180002315  mov     [rsp+450h+FileHandle], r9
0x18000231a  call    CscDriverpReferenceControlHandle
0x18000231f  mov     r13d, eax
0x180002322  test    eax, eax
0x180002324  jns     loc_1800025DB
0x18000232a  test    r13d, r13d
0x18000232d  js      short loc_1800022F7
0x18000232f  cmp     [rsp+450h+var_410], sil
0x180002334  jz      short loc_1800022F7
0x180002336  mov     rdx, [rsp+450h+SourceString]; SourceString
0x18000233b  lea     rcx, [rbp+350h+DestinationString]; DestinationString
0x18000233f  xor     bl, bl
0x180002341  call    cs:__imp_RtlInitUnicodeStringEx
0x180002347  mov     r13d, eax
0x18000234a  test    eax, eax
0x18000234c  js      loc_18000273C
0x180002352  cmp     [rsp+450h+var_40F], bl
0x180002356  jnz     short loc_1800023A7
0x180002358  movzx   edx, word ptr [rsp+450h+Src]
0x18000235d  xor     ecx, ecx; uFlags
0x18000235f  add     rdx, 4; uBytes
0x180002363  call    cs:__imp_LocalAlloc
0x180002369  mov     r14, rax
0x18000236c  test    rax, rax
0x18000236f  jz      loc_180002747
0x180002375  mov     dword ptr [rax], 5C005Ch
0x18000237b  lea     rcx, [rax+4]; void *
0x18000237f  movzx   r8d, word ptr [rsp+450h+Src]; Size
0x180002385  mov     rdx, [rsp+450h+Src+8]; Src
0x18000238a  call    memcpy_0
0x18000238f  movzx   eax, word ptr [rsp+450h+Src]
0x180002394  add     ax, 4
0x180002398  mov     [rsp+450h+Src+8], r14
0x18000239d  mov     word ptr [rsp+450h+Src], ax
0x1800023a2  mov     word ptr [rsp+450h+Src+2], ax
0x1800023a7  xor     eax, eax
0x1800023a9  mov     [rbp+350h+var_3D0], 60004h
0x1800023b1  cmp     cs:CscUmpLibraryState, esi
0x1800023b7  xorps   xmm0, xmm0
0x1800023ba  mov     [rbp+350h+var_370], rax
0x1800023be  lea     rax, asc_18000B600; "\\\\"
0x1800023c5  mov     [rbp+350h+var_3C8], rax
0x1800023c9  movups  [rbp+350h+var_3A0], xmm0
0x1800023cd  movups  [rbp+350h+var_390], xmm0
0x1800023d1  movups  [rbp+350h+var_380], xmm0
0x1800023d5  jz      short loc_18000244F
0x1800023d7  mov     edx, 30h ; '0'; uBytes
0x1800023dc  xor     ecx, ecx; uFlags
0x1800023de  call    cs:__imp_LocalAlloc
0x1800023e4  mov     rsi, rax
0x1800023e7  test    rax, rax
0x1800023ea  jz      loc_180002758
0x1800023f0  xorps   xmm0, xmm0
0x1800023f3  movups  xmmword ptr [rax], xmm0
0x1800023f6  movups  xmmword ptr [rax+10h], xmm0
0x1800023fa  movups  xmmword ptr [rax+20h], xmm0
0x1800023fe  mov     dword ptr [rax], 43656453h
0x180002404  mov     byte ptr [rax+20h], 1
0x180002408  cmp     [rbp+350h+DestinationString.Length], di
0x18000240c  jz      loc_180002641
0x180002412  lea     r8, [rax+10h]; DestinationString
0x180002416  xor     ecx, ecx; Flags
0x180002418  lea     rdx, [rbp+350h+DestinationString]; SourceString
0x18000241c  call    cs:__imp_RtlDuplicateUnicodeString
0x180002422  mov     r13d, eax
0x180002425  test    eax, eax
0x180002427  jns     loc_180002641
0x18000242d  mov     rcx, rsi; hMem
0x180002430  call    CscUmFindClose
0x180002435  xor     esi, esi
0x180002437  cmp     r13d, 0C000003Bh
0x18000243e  jnz     loc_180002763
0x180002444  mov     r12d, 0DFAh
0x18000244a  jmp     loc_1800021A4
0x18000244f  mov     r13d, 0C0000184h
0x180002455  test    r13d, r13d
0x180002458  js      loc_1800027A9
0x18000245e  lea     r8, [rbp+350h+var_360]
0x180002462  mov     rcx, rsi
0x180002465  lea     rdx, [rbp+350h+var_280]
0x18000246c  call    CscUmFindNext
0x180002471  mov     r13d, eax
0x180002474  cmp     eax, 80000006h
0x180002479  jz      loc_1800027B4
0x18000247f  test    eax, eax
0x180002481  js      loc_1800027BF
0x180002487  test    dword ptr [rbp+350h+var_360], 800000h
0x18000248e  jz      short loc_18000249B
0x180002490  mov     r12d, 0E1Ah
0x180002496  jmp     loc_1800021A4
0x18000249b  mov     edx, [rbp+350h+arg_20]
0x1800024a1  lea     rcx, [rbp+350h+var_2F0]
0x1800024a5  call    ?Init@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAEK@Z; CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::Init(ulong)
0x1800024aa  test    al, al
0x1800024ac  jz      loc_18000262C
0x1800024b2  mov     rcx, [rsp+450h+var_3D8]
0x1800024b7  lea     rax, [rbp+350h+var_27C]
0x1800024be  mov     dword ptr [rbp+350h+var_300+4], ecx
0x1800024c1  mov     edx, 1Eh
0x1800024c6  lea     rcx, aOfflineShare; "[Offline Share]"
0x1800024cd  mov     qword ptr [rbp+350h+var_310+8], rax
0x1800024d1  movzx   eax, [rbp+350h+var_280]
0x1800024d8  mov     qword ptr [rbp+350h+var_300+8], rcx
0x1800024dc  xor     ecx, ecx
0x1800024de  cmp     [rbp+350h+var_2DC], 0FFFFFFFFh
0x1800024e2  mov     word ptr [rbp+350h+var_310], ax
0x1800024e6  mov     word ptr [rbp+350h+var_310+2], ax
0x1800024ea  mov     dword ptr [rbp+350h+var_300], 20001Eh
0x1800024f1  jz      short loc_1800024F6
0x1800024f3  lea     ecx, [rax+2]
0x1800024f6  cmp     [rbp+350h+var_2D8], 0FFFFFFFFh
0x1800024fa  jz      short loc_180002501
0x1800024fc  lea     eax, [rdx+2]
0x1800024ff  add     ecx, eax
0x180002501  mov     r12d, dword ptr [rbp+350h+Size]
0x180002508  lea     rdx, [rsp+450h+var_3F8]
0x18000250d  mov     rax, [rbp+350h+var_3C0]
0x180002511  add     r12d, ecx
0x180002514  mov     ecx, r12d
0x180002517  mov     rax, [rax+10h]
0x18000251b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002520  mov     edi, eax
0x180002522  test    eax, eax
0x180002524  jnz     loc_1800027CA
0x18000252a  mov     r13, [rsp+450h+var_3F8]
0x18000252f  xor     ecx, ecx
0x180002531  mov     edx, r12d
0x180002534  add     rdx, r13
0x180002537  cmp     [rbp+350h+var_2DC], 0FFFFFFFFh
0x18000253b  mov     [rsp+450h+var_3D8], rdx
0x180002540  jz      short loc_180002549
0x180002542  movzx   ecx, word ptr [rbp+350h+var_310]
0x180002546  add     ecx, 2
0x180002549  cmp     [rbp+350h+var_2D8], 0FFFFFFFFh
0x18000254d  jz      short loc_180002558
0x18000254f  movzx   eax, word ptr [rbp+350h+var_300]
0x180002553  add     eax, 2
0x180002556  add     ecx, eax
0x180002558  mov     r8d, dword ptr [rbp+350h+Size]; Size
0x18000255f  mov     eax, ecx
0x180002561  sub     rdx, rax
0x180002564  lea     rax, [r8+r13]
  ... truncated ...
```
