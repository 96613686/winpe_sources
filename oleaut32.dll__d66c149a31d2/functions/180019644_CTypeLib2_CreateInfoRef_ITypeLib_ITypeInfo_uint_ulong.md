# CTypeLib2::CreateInfoRef(ITypeLib *,ITypeInfo *,uint,ulong *)

- ea: `0x180019644`
- end: `0x180019ae4`
- name: `?CreateInfoRef@CTypeLib2@@QEAAJPEAUITypeLib@@PEAUITypeInfo@@IPEAK@Z`
- size: `1184`
- prototype: `int(CTypeLib2 *__hidden this, struct ITypeLib *, struct ITypeInfo *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180019530`

## callees

- `0x18000f960`
- `0x180019644`
- `0x180019aec`
- `0x18001a538`
- `0x18001ab80`
- `0x18006e9f4`
- `0x18006fa68`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019981`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800199c3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180019981`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800199c3`

## pseudocode

```c
__int64 __fastcall CTypeLib2::CreateInfoRef(
        CTypeLib2 *this,
        struct ITypeLib *a2,
        struct ITypeInfo *a3,
        unsigned int a4,
        unsigned int *a5)
{
  struct ITypeLib *v5; // r14
  unsigned int v7; // r13d
  struct ITypeInfo *v8; // rsi
  struct ITypeLibVtbl *lpVtbl; // rax
  unsigned int v10; // r12d
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // edi
  unsigned int v14; // r15d
  __int64 v15; // rsi
  unsigned int v16; // ecx
  int v17; // ecx
  __int64 v18; // rax
  int v19; // r15d
  __int64 v20; // rdx
  __int16 v21; // ax
  unsigned int v22; // edx
  int v23; // edx
  unsigned int v24; // edx
  __int64 v25; // rcx
  const WCHAR *PathOfLoadedTypelib; // r12
  unsigned __int16 v27; // r13
  __int64 v28; // rdx
  int v29; // r9d
  __int64 v30; // rax
  __int64 v31; // rax
  unsigned int cbMultiByte; // [rsp+28h] [rbp-48h]
  unsigned int v33; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v34; // [rsp+44h] [rbp-2Ch] BYREF
  unsigned int v35; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v36; // [rsp+4Ch] [rbp-24h] BYREF
  struct _GUID *v37; // [rsp+50h] [rbp-20h] BYREF
  struct _GUID *v38; // [rsp+58h] [rbp-18h] BYREF
  struct ITypeInfo *v39; // [rsp+60h] [rbp-10h] BYREF
  struct ITypeLib *v40; // [rsp+B8h] [rbp+48h] BYREF
  struct ITypeInfo *v41; // [rsp+C0h] [rbp+50h]
  unsigned int v42; // [rsp+C8h] [rbp+58h]

  v42 = a4;
  v41 = a3;
  v40 = a2;
  v5 = a2;
  v34 = 0;
  v33 = 0;
  v37 = 0;
  v38 = 0;
  v7 = a4;
  v39 = 0;
  v8 = a3;
  lpVtbl = a2->lpVtbl;
  v10 = -1;
  v36 = 0;
  v35 = -1;
  result = ((__int64 (__fastcall *)(struct ITypeLib *, struct _GUID **))lpVtbl->GetLibAttr)(a2, &v37);
  if ( (int)result < 0 )
    return result;
  v12 = *(_QWORD *)&v37->Data1 - *(_QWORD *)&IID_StdOle.Data1;
  if ( *(_QWORD *)&v37->Data1 == *(_QWORD *)&IID_StdOle.Data1 )
    v12 = *(_QWORD *)v37->Data4 - *(_QWORD *)IID_StdOle.Data4;
  if ( !v12 && *(_WORD *)v37[1].Data4 == 1 && !*(_WORD *)&v37[1].Data4[2] )
  {
    ((void (__fastcall *)(struct ITypeLib *))v5->lpVtbl->ReleaseTLibAttr)(v5);
    result = CTypeLib2::GetPtlibStdole2(this, &v40);
    if ( (int)result < 0 )
      return result;
    v5 = v40;
    result = ((__int64 (__fastcall *)(struct ITypeLib *, struct _GUID **))v40->lpVtbl->GetLibAttr)(v40, &v37);
    if ( (int)result < 0 )
      return result;
    v13 = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, struct ITypeInfo **))v5->lpVtbl->GetTypeInfo)(
            v5,
            v7,
            &v39);
    if ( v13 < 0 )
      goto LABEL_24;
    v8 = v39;
    v41 = v39;
  }
  v13 = ((__int64 (__fastcall *)(struct ITypeInfo *, struct _GUID **))v8->lpVtbl->GetTypeAttr)(v8, &v38);
  if ( v13 >= 0 )
  {
    result = CTypeLib2::AllocGuidEntry(this, v37, 0xFFFFFFFF, &v36);
    v13 = 0;
    if ( (int)result < 0 )
      return result;
    v14 = v36;
    if ( v36 >= *((_DWORD *)this + 39) )
      v15 = 0;
    else
      v15 = *((_QWORD *)this + 21) + v36;
    v16 = *(_DWORD *)(v15 + 16);
    v33 = v16;
    if ( v16 == -1 )
    {
      PathOfLoadedTypelib = OLE_TYPEMGR::GetPathOfLoadedTypelib(g_poletmgr, v5, 1);
      if ( PathOfLoadedTypelib )
      {
        v30 = -1;
        do
          ++v30;
        while ( PathOfLoadedTypelib[v30] );
        LODWORD(v40) = v30;
        v27 = WideCharToMultiByte(0, 0, PathOfLoadedTypelib, (unsigned __int16)v30, 0, 0, 0, 0);
      }
      else
      {
        v27 = 0;
        LODWORD(v40) = 0;
      }
      v36 = v27;
      v13 = HEAP::AllocChunk2((CTypeLib2 *)((char *)this + 80), &v33, (unsigned int)v27 + 14);
      if ( v13 < 0 )
        goto LABEL_23;
      *(_DWORD *)(v15 + 16) = v33 | 2;
      if ( v33 >= *((_DWORD *)this + 21) )
      {
        v13 = 0;
        v28 = 0;
      }
      else
      {
        v28 = *((_QWORD *)this + 12) + v33;
        v13 = 0;
      }
      v29 = (unsigned __int16)v40;
      *(_DWORD *)v28 = v14;
      *(_DWORD *)(v28 + 4) = v37[1].Data1;
      *(_WORD *)(v28 + 8) = *(_WORD *)v37[1].Data4;
      *(_WORD *)(v28 + 10) = *(_WORD *)&v37[1].Data4[2];
      cbMultiByte = v36;
      *(_WORD *)(v28 + 12) = (4 * v27) | *((_WORD *)this + 202) & 3;
      WideCharToMultiByte(0, 0, PathOfLoadedTypelib, v29, (LPSTR)(v28 + 14), cbMultiByte, 0, 0);
      v10 = v35;
      v7 = v42;
    }
    else
    {
      if ( !IsLibRef(v16) )
      {
        v13 = -2147317562;
        goto LABEL_23;
      }
      v33 = v17 & 0xFFFFFFFC;
    }
    v18 = *(_QWORD *)&v38->Data1 - *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&v38->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
      v18 = *(_QWORD *)v38->Data4 - *(_QWORD *)GUID_NULL.Data4;
    if ( v18 )
    {
      result = CTypeLib2::AllocGuidEntry(this, v38, 0xFFFFFFFF, &v35);
      if ( (int)result < 0 )
        return result;
      v10 = v35;
      v19 = 1;
      if ( v35 >= *((_DWORD *)this + 39) )
        v15 = 0;
      else
        v15 = *((_QWORD *)this + 21) + v35;
      v22 = *(_DWORD *)(v15 + 16);
      v34 = v22;
      if ( v22 == -1 )
        goto LABEL_17;
      if ( IsInfoRef(v22) )
      {
        v24 = v23 & 0xFFFFFFFC;
        v25 = v24 >= *((_DWORD *)this + 15) ? 0LL : *((_QWORD *)this + 9) + v24;
        if ( *(_DWORD *)(v25 + 4) == v33 )
          goto LABEL_22;
      }
    }
    v19 = 0;
LABEL_17:
    v13 = HEAP::AllocChunk2((CTypeLib2 *)((char *)this + 56), &v34, 0xCu);
    if ( v13 < 0 )
    {
LABEL_23:
      v8 = v41;
      goto LABEL_24;
    }
    if ( v34 >= *((_DWORD *)this + 15) )
    {
      v13 = 0;
      v20 = 0;
    }
    else
    {
      v20 = *((_QWORD *)this + 9) + v34;
      v13 = 0;
    }
    v21 = *((_WORD *)this + 234);
    ++*((_DWORD *)this + 117);
    *(_WORD *)v20 = v21;
    *(_BYTE *)(v20 + 2) = v19;
    *(_BYTE *)(v20 + 3) = v38[2].Data4[4];
    *(_DWORD *)(v20 + 4) = v33;
    if ( v19 )
    {
      *(_DWORD *)(v15 + 16) = v34 | 1;
      *(_DWORD *)(v20 + 8) = v10;
      if ( *((_DWORD *)this + 116) == -1 )
      {
        v31 = *(_QWORD *)&v38->Data1 - *(_QWORD *)&IID_IDispatch.Data1;
        if ( *(_QWORD *)&v38->Data1 == *(_QWORD *)&IID_IDispatch.Data1 )
          v31 = *(_QWORD *)v38->Data4 - *(_QWORD *)IID_IDispatch.Data4;
        if ( !v31 )
          *((_DWORD *)this + 116) = v34 | 1;
      }
    }
    else
    {
      *(_DWORD *)(v20 + 8) = v7;
    }
LABEL_22:
    *a5 = v34 | 1;
    goto LABEL_23;
  }
LABEL_24:
  if ( v38 )
    ((void (__fastcall *)(struct ITypeInfo *))v8->lpVtbl->ReleaseTypeAttr)(v8);
  if ( v39 )
    ((void (__fastcall *)(struct ITypeInfo *))v39->lpVtbl->Release)(v39);
  ((void (__fastcall *)(struct ITypeLib *, struct _GUID *))v5->lpVtbl->ReleaseTLibAttr)(v5, v37);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180019644  mov     rax, rsp
0x180019647  mov     [rax+8], rbx
0x18001964b  mov     [rax+20h], r9d
0x18001964f  mov     [rax+18h], r8
0x180019653  mov     [rax+10h], rdx
0x180019657  push    rbp
0x180019658  push    rsi
0x180019659  push    rdi
0x18001965a  push    r12
0x18001965c  push    r13
0x18001965e  push    r14
0x180019660  push    r15
0x180019662  mov     rbp, rsp
0x180019665  sub     rsp, 70h
0x180019669  xor     edi, edi
0x18001966b  mov     r14, rdx
0x18001966e  mov     [rbp+var_2C], edi
0x180019671  mov     rbx, rcx
0x180019674  mov     [rbp+var_30], edi
0x180019677  or      r15d, 0FFFFFFFFh
0x18001967b  mov     [rbp+var_20], rdi
0x18001967f  mov     rcx, r14
0x180019682  mov     [rbp+var_18], rdi
0x180019686  mov     r13d, r9d
0x180019689  mov     [rbp+var_10], rdi
0x18001968d  mov     rsi, r8
0x180019690  mov     rax, [rdx]
0x180019693  mov     r12d, r15d
0x180019696  lea     rdx, [rbp+var_20]
0x18001969a  mov     [rbp+var_24], edi
0x18001969d  mov     [rbp+var_28], r15d
0x1800196a1  mov     rax, [rax+38h]
0x1800196a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196aa  test    eax, eax
0x1800196ac  js      loc_18001982A
0x1800196b2  mov     rdx, [rbp+var_20]
0x1800196b6  mov     rax, [rdx]
0x1800196b9  sub     rax, qword ptr cs:IID_StdOle.Data1
0x1800196c0  jnz     short loc_1800196CD
0x1800196c2  mov     rax, [rdx+8]
0x1800196c6  sub     rax, qword ptr cs:IID_StdOle.Data4
0x1800196cd  mov     ecx, 1
0x1800196d2  test    rax, rax
0x1800196d5  jnz     short loc_1800196E1
0x1800196d7  cmp     [rdx+18h], cx
0x1800196db  jz      loc_180019A3B
0x1800196e1  mov     rax, [rsi]
0x1800196e4  lea     rdx, [rbp+var_18]
0x1800196e8  mov     rcx, rsi
0x1800196eb  mov     rax, [rax+18h]
0x1800196ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f4  mov     edi, eax
0x1800196f6  test    eax, eax
0x1800196f8  js      loc_1800197ED
0x1800196fe  mov     rdx, [rbp+var_20]; struct _GUID *
0x180019702  lea     r9, [rbp+var_24]; unsigned int *
0x180019706  mov     r8d, r15d; unsigned int
0x180019709  mov     rcx, rbx; this
0x18001970c  call    ?AllocGuidEntry@CTypeLib2@@QEAAJAEBU_GUID@@KPEAK@Z; CTypeLib2::AllocGuidEntry(_GUID const &,ulong,ulong *)
0x180019711  xor     edi, edi
0x180019713  test    eax, eax
0x180019715  js      loc_18001982A
0x18001971b  mov     r15d, [rbp+var_24]
0x18001971f  cmp     r15d, [rbx+9Ch]
0x180019726  jnb     loc_1800199DC
0x18001972c  mov     esi, r15d
0x18001972f  add     rsi, [rbx+0A8h]
0x180019736  mov     ecx, [rsi+10h]; unsigned int
0x180019739  mov     [rbp+var_30], ecx
0x18001973c  cmp     ecx, 0FFFFFFFFh
0x18001973f  jz      loc_1800198B8
0x180019745  call    ?IsLibRef@@YAEK@Z; IsLibRef(ulong)
0x18001974a  test    al, al
0x18001974c  jz      loc_1800199D2
0x180019752  and     ecx, 0FFFFFFFCh
0x180019755  mov     [rbp+var_30], ecx
0x180019758  mov     rdx, [rbp+var_18]; struct _GUID *
0x18001975c  mov     rax, [rdx]
0x18001975f  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180019766  jnz     short loc_180019773
0x180019768  mov     rax, [rdx+8]
0x18001976c  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180019773  test    rax, rax
0x180019776  jnz     loc_180019842
0x18001977c  mov     r15d, edi
0x18001977f  lea     rcx, [rbx+38h]; this
0x180019783  mov     r8d, 0Ch; unsigned int
0x180019789  lea     rdx, [rbp+var_2C]; unsigned int *
0x18001978d  call    ?AllocChunk2@HEAP@@AEAAJPEAKKK@Z; HEAP::AllocChunk2(ulong *,ulong,ulong)
0x180019792  mov     edi, eax
0x180019794  test    eax, eax
0x180019796  js      short loc_1800197E9
0x180019798  mov     eax, [rbp+var_2C]
0x18001979b  cmp     eax, [rbx+3Ch]
0x18001979e  jnb     loc_1800199FD
0x1800197a4  mov     edx, eax
0x1800197a6  add     rdx, [rbx+48h]
0x1800197aa  xor     edi, edi
0x1800197ac  movzx   eax, word ptr [rbx+1D4h]
0x1800197b3  inc     dword ptr [rbx+1D4h]
0x1800197b9  mov     [rdx], ax
0x1800197bc  mov     [rdx+2], r15b
0x1800197c0  mov     rax, [rbp+var_18]
0x1800197c4  mov     cl, [rax+2Ch]
0x1800197c7  mov     [rdx+3], cl
0x1800197ca  mov     eax, [rbp+var_30]
0x1800197cd  mov     [rdx+4], eax
0x1800197d0  test    r15d, r15d
0x1800197d3  jnz     loc_180019AB4
0x1800197d9  mov     [rdx+8], r13d
0x1800197dd  mov     rax, [rbp+arg_20]
0x1800197e1  mov     ecx, [rbp+var_2C]
0x1800197e4  or      ecx, 1
0x1800197e7  mov     [rax], ecx
0x1800197e9  mov     rsi, [rbp+arg_10]
0x1800197ed  mov     rdx, [rbp+var_18]
0x1800197f1  test    rdx, rdx
0x1800197f4  jz      short loc_180019808
0x1800197f6  mov     rax, [rsi]
0x1800197f9  mov     rcx, rsi
0x1800197fc  mov     rax, [rax+98h]
0x180019803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019808  mov     rcx, [rbp+var_10]
0x18001980c  test    rcx, rcx
0x18001980f  jnz     loc_180019AD3
0x180019815  mov     rax, [r14]
0x180019818  mov     rcx, r14
0x18001981b  mov     rdx, [rbp+var_20]
0x18001981f  mov     rax, [rax+60h]
0x180019823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019828  mov     eax, edi
0x18001982a  mov     rbx, [rsp+70h+arg_0]
0x180019832  add     rsp, 70h
0x180019836  pop     r15
0x180019838  pop     r14
0x18001983a  pop     r13
0x18001983c  pop     r12
0x18001983e  pop     rdi
0x18001983f  pop     rsi
0x180019840  pop     rbp
0x180019841  retn
0x180019842  lea     r9, [rbp+var_28]; unsigned int *
0x180019846  or      r8d, 0FFFFFFFFh; unsigned int
0x18001984a  mov     rcx, rbx; this
0x18001984d  call    ?AllocGuidEntry@CTypeLib2@@QEAAJAEBU_GUID@@KPEAK@Z; CTypeLib2::AllocGuidEntry(_GUID const &,ulong,ulong *)
0x180019852  test    eax, eax
0x180019854  js      short loc_18001982A
0x180019856  mov     r12d, [rbp+var_28]
0x18001985a  mov     r15d, 1
0x180019860  cmp     r12d, [rbx+9Ch]
0x180019867  jnb     loc_1800199ED
0x18001986d  mov     esi, r12d
0x180019870  add     rsi, [rbx+0A8h]
0x180019877  mov     edx, [rsi+10h]
0x18001987a  mov     [rbp+var_2C], edx
0x18001987d  cmp     edx, 0FFFFFFFFh
0x180019880  jz      loc_18001977F
0x180019886  mov     ecx, edx; unsigned int
0x180019888  call    ?IsInfoRef@@YAEK@Z; IsInfoRef(ulong)
0x18001988d  test    al, al
0x18001988f  jz      loc_18001977C
0x180019895  and     edx, 0FFFFFFFCh
0x180019898  cmp     edx, [rbx+3Ch]
0x18001989b  jnb     loc_1800199F5
0x1800198a1  mov     ecx, edx
0x1800198a3  add     rcx, [rbx+48h]
0x1800198a7  mov     eax, [rbp+var_30]
0x1800198aa  cmp     [rcx+4], eax
0x1800198ad  jz      loc_1800197DD
0x1800198b3  jmp     loc_18001977C
0x1800198b8  mov     rcx, cs:?g_poletmgr@@3PEAVOLE_TYPEMGR@@EA; this
0x1800198bf  mov     r8d, 1; int
0x1800198c5  mov     rdx, r14; struct ITypeLib *
0x1800198c8  call    ?GetPathOfLoadedTypelib@OLE_TYPEMGR@@QEAAPEBGPEAUITypeLib@@H@Z; OLE_TYPEMGR::GetPathOfLoadedTypelib(ITypeLib *,int)
0x1800198cd  mov     r12, rax
0x1800198d0  test    rax, rax
0x1800198d3  jnz     loc_180019994
0x1800198d9  mov     r13d, edi
0x1800198dc  mov     dword ptr [rbp+arg_8], edi
0x1800198df  movzx   eax, r13w
0x1800198e3  lea     rcx, [rbx+50h]; this
0x1800198e7  lea     rdx, [rbp+var_30]; unsigned int *
0x1800198eb  mov     [rbp+var_24], eax
0x1800198ee  lea     r8d, [rax+0Eh]; unsigned int
0x1800198f2  call    ?AllocChunk2@HEAP@@AEAAJPEAKKK@Z; HEAP::AllocChunk2(ulong *,ulong,ulong)
0x1800198f7  mov     edi, eax
0x1800198f9  test    eax, eax
0x1800198fb  js      loc_1800197E9
0x180019901  mov     eax, [rbp+var_30]
0x180019904  or      eax, 2
0x180019907  mov     [rsi+10h], eax
0x18001990a  mov     eax, [rbp+var_30]
0x18001990d  cmp     eax, [rbx+54h]
0x180019910  jnb     loc_1800199E4
0x180019916  mov     edx, eax
0x180019918  add     rdx, [rbx+60h]
0x18001991c  xor     edi, edi
0x18001991e  movzx   r9d, word ptr [rbp+arg_8]; cchWideChar
0x180019923  mov     r8, r12; lpWideCharStr
0x180019926  mov     [rdx], r15d
0x180019929  mov     rax, [rbp+var_20]
0x18001992d  mov     [rsp+70h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x180019932  shl     r13w, 2
0x180019937  mov     [rsp+70h+lpDefaultChar], rdi; lpDefaultChar
0x18001993c  mov     ecx, [rax+10h]
0x18001993f  mov     [rdx+4], ecx
0x180019942  mov     rax, [rbp+var_20]
0x180019946  movzx   ecx, word ptr [rax+18h]
0x18001994a  mov     [rdx+8], cx
0x18001994e  mov     rax, [rbp+var_20]
0x180019952  movzx   ecx, word ptr [rax+1Ah]
0x180019956  mov     [rdx+0Ah], cx
0x18001995a  movzx   eax, word ptr [rbx+194h]
0x180019961  mov     ecx, [rbp+var_24]
0x180019964  and     ax, 3
0x180019968  or      ax, r13w
0x18001996c  mov     [rsp+70h+cbMultiByte], ecx; cbMultiByte
0x180019970  mov     [rdx+0Ch], ax
0x180019974  xor     ecx, ecx; CodePage
0x180019976  lea     rax, [rdx+0Eh]
0x18001997a  xor     edx, edx; dwFlags
0x18001997c  mov     [rsp+70h+lpMultiByteStr], rax; lpMultiByteStr
0x180019981  call    cs:__imp_WideCharToMultiByte
0x180019987  mov     r12d, [rbp+var_28]
0x18001998b  mov     r13d, [rbp+arg_18]
0x18001998f  jmp     loc_180019758
0x180019994  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019998  inc     rax
0x18001999b  cmp     [r12+rax*2], di
0x1800199a0  jnz     short loc_180019998
0x1800199a2  mov     [rsp+70h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800199a7  mov     r8, r12; lpWideCharStr
0x1800199aa  mov     [rsp+70h+lpDefaultChar], rdi; lpDefaultChar
0x1800199af  xor     edx, edx; dwFlags
0x1800199b1  mov     [rsp+70h+cbMultiByte], edi; cbMultiByte
0x1800199b5  xor     ecx, ecx; CodePage
0x1800199b7  movzx   r9d, ax; cchWideChar
0x1800199bb  mov     [rsp+70h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800199c0  mov     dword ptr [rbp+arg_8], eax
0x1800199c3  call    cs:__imp_WideCharToMultiByte
0x1800199c9  movzx   r13d, ax
0x1800199cd  jmp     loc_1800198DF
0x1800199d2  mov     edi, 800288C6h
0x1800199d7  jmp     loc_1800197E9
0x1800199dc  mov     rsi, rdi
0x1800199df  jmp     loc_180019736
0x1800199e4  xor     edi, edi
0x1800199e6  mov     edx, edi
0x1800199e8  jmp     loc_18001991E
0x1800199ed  mov     rsi, rdi
0x1800199f0  jmp     loc_180019877
0x1800199f5  mov     rcx, rdi
0x1800199f8  jmp     loc_1800198A7
0x1800199fd  xor     edi, edi
0x1800199ff  mov     edx, edi
0x180019a01  jmp     loc_1800197AC
0x180019a06  mov     rcx, [rbp+var_18]
0x180019a0a  mov     rax, [rcx]
0x180019a0d  sub     rax, qword ptr cs:IID_IDispatch.Data1
0x180019a14  jnz     short loc_180019A21
0x180019a16  mov     rax, [rcx+8]
0x180019a1a  sub     rax, qword ptr cs:IID_IDispatch.Data4
0x180019a21  test    rax, rax
0x180019a24  jnz     loc_1800197DD
0x180019a2a  mov     eax, [rbp+var_2C]
0x180019a2d  or      eax, 1
0x180019a30  mov     [rbx+1D0h], eax
0x180019a36  jmp     loc_1800197DD
0x180019a3b  cmp     [rdx+1Ah], di
0x180019a3f  jnz     loc_1800196E1
0x180019a45  mov     rax, [r14]
0x180019a48  mov     rcx, r14
0x180019a4b  mov     rax, [rax+60h]
0x180019a4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a54  lea     rdx, [rbp+arg_8]; struct ITypeLib **
0x180019a58  mov     rcx, rbx; this
0x180019a5b  call    ?GetPtlibStdole2@CTypeLib2@@QEAAJPEAPEAUITypeLib@@@Z; CTypeLib2::GetPtlibStdole2(ITypeLib * *)
0x180019a60  test    eax, eax
0x180019a62  js      loc_18001982A
0x180019a68  mov     r14, [rbp+arg_8]
0x180019a6c  lea     rdx, [rbp+var_20]
0x180019a70  mov     rcx, r14
0x180019a73  mov     rax, [r14]
0x180019a76  mov     rax, [rax+38h]
0x180019a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a7f  test    eax, eax
0x180019a81  js      loc_18001982A
0x180019a87  mov     rax, [r14]
0x180019a8a  lea     r8, [rbp+var_10]
0x180019a8e  mov     edx, r13d
0x180019a91  mov     rcx, r14
0x180019a94  mov     rax, [rax+20h]
0x180019a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a9d  mov     edi, eax
0x180019a9f  test    eax, eax
0x180019aa1  js      loc_1800197ED
0x180019aa7  mov     rsi, [rbp+var_10]
0x180019aab  mov     [rbp+arg_10], rsi
0x180019aaf  jmp     loc_1800196E1
0x180019ab4  mov     eax, [rbp+var_2C]
  ... truncated ...
```
