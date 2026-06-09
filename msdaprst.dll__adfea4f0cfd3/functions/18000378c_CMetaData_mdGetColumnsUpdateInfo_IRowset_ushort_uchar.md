# CMetaData::mdGetColumnsUpdateInfo(IRowset *,ushort * *,uchar * *)

- ea: `0x18000378c`
- end: `0x180003c32`
- name: `?mdGetColumnsUpdateInfo@CMetaData@@AEAAHPEAUIRowset@@PEAPEAGPEAPEAE@Z`
- size: `1190`
- prototype: `__int64 __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180002c1c`

## callees

- `0x180001dd4`
- `0x180002728`
- `0x180002770`
- `0x1800028b8`
- `0x180002fdc`
- `0x18000378c`
- `0x180003c70`
- `0x1800045cc`
- `0x18001b008`
- `0x18002dca4`
- `0x18002f0aa`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800037f9`
- `ole32!CoTaskMemFree` at `0x18000380b`
- `ole32!CoTaskMemFree` at `0x18000381d`
- `ole32!CoTaskMemFree` at `0x180003be0`
- `ole32!CoTaskMemFree` at `0x180003bf2`
- `ole32!CoTaskMemFree` at `0x180003c04`
- `ole32!CoTaskMemFree` at `0x1800037f9`
- `ole32!CoTaskMemFree` at `0x18000380b`
- `ole32!CoTaskMemFree` at `0x18000381d`
- `ole32!CoTaskMemFree` at `0x180003be0`
- `ole32!CoTaskMemFree` at `0x180003bf2`
- `ole32!CoTaskMemFree` at `0x180003c04`
- `ole32!CoTaskMemAlloc` at `0x1800038dc`
- `ole32!CoTaskMemAlloc` at `0x1800038dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMetaData::mdGetColumnsUpdateInfo(
        CMetaData *this,
        struct IRowset *a2,
        unsigned __int16 **a3,
        unsigned __int8 **a4)
{
  void *v6; // rbx
  int v7; // eax
  unsigned int v9; // r15d
  int v10; // eax
  int v11; // esi
  CMetaData *v12; // rcx
  unsigned int HiddenCount; // eax
  void *v14; // rcx
  unsigned __int128 v15; // rax
  unsigned __int8 *v16; // rax
  unsigned __int16 v17; // r12
  unsigned __int16 v18; // si
  __int64 v19; // r14
  __int64 v20; // r10
  unsigned __int16 *v21; // r8
  __int16 v22; // r13
  unsigned __int16 *v23; // rax
  unsigned __int8 *v24; // rax
  LPVOID v25; // [rsp+30h] [rbp-C8h] BYREF
  unsigned __int64 v26; // [rsp+38h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-B8h] BYREF
  int v28; // [rsp+48h] [rbp-B0h]
  LPVOID v29; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A0h] BYREF
  int v31; // [rsp+60h] [rbp-98h] BYREF
  struct tagDBCOLUMNINFO v32; // [rsp+70h] [rbp-88h] BYREF
  int v33; // [rsp+108h] [rbp+10h] BYREF
  unsigned __int16 **v34; // [rsp+110h] [rbp+18h]
  unsigned __int8 **v35; // [rsp+118h] [rbp+20h]

  v35 = a4;
  v34 = a3;
  try
  {
    v6 = 0;
    v28 = 0;
    v30 = 0;
    v26 = 0;
    v22 = 0;
    LOWORD(v33) = 0;
    v25 = 0;
    v29 = 0;
    pv = 0;
    v7 = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &IID_IColumnsUpdateInfo,
           &v30);
  }
  catch ( long v31 )
  {
    v33 = v31;
    v9 = v28;
    v6 = pv;
    goto LABEL_26;
  }
  if ( v7 )
  {
    CoTaskMemFree(pv);
    CoTaskMemFree(v29);
    CoTaskMemFree(v25);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
    return 0;
  }
  else
  {
    v9 = 1;
    v28 = 1;
    v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, LPVOID *, LPVOID *))(*(_QWORD *)v30 + 24LL))(
            v30,
            &v26,
            &v25,
            &v29,
            &pv);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180049488[0] )
          bidTraceW(off_1800491B8[0], 338944, off_180049488[0], (unsigned int)v10, 331);
      }
      ThrowHR(v11);
    }
    DownsizeToULONGThrow<unsigned __int64>(v26);
    HiddenCount = CMetaData::mdGetHiddenCount(v12, a2);
    v26 += HiddenCount;
    v14 = CoTaskMemAlloc((unsigned int)(168 * v26));
    *((_QWORD *)this + 1) = v14;
    if ( !v14 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180049480[0] )
        bidTraceW(off_1800491B8[0], 348160, off_180049480[0], 2147942414LL, 340);
      ThrowHR(-2147024882);
    }
    memset_0(v14, 0, (unsigned int)(168 * v26));
    if ( pv )
    {
      v15 = (unsigned __int64)(int)v26 * (unsigned __int128)4uLL;
      if ( !is_mul_ok((int)v26, 4u) )
        LODWORD(v15) = -1;
      v16 = MMMAlloc(v15, DWORD2(v15));
      *((_QWORD *)this + 5) = v16;
      OnNullThrowOOM(v16);
      memset_0(*((void **)this + 5), 0, (unsigned int)(4 * v26));
    }
    v17 = 0;
    v18 = 0;
    while ( v17 < v26 )
    {
      v19 = 168LL * v17;
      v32 = *(struct tagDBCOLUMNINFO *)((char *)v25 + v19);
      if ( (unsigned int)CMetaData::mdGetColInfo(this, &v32, v18, (unsigned __int16 *)&v33) )
      {
        v20 = 168LL * v18;
        *(_WORD *)(v20 + *((_QWORD *)this + 1) + 112) = *(_WORD *)((char *)v25 + v19 + 112);
        *(_WORD *)(v20 + *((_QWORD *)this + 1) + 114) = *(_WORD *)((char *)v25 + v19 + 114);
        *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 120) = *(_QWORD *)((char *)v25 + v19 + 120);
        *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 128) = *(_QWORD *)((char *)v25 + v19 + 128);
        *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 160) = *(_DWORD *)((char *)v25 + v19 + 160);
        if ( pv )
        {
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 80) = *(_QWORD *)((char *)v25 + v19 + 80);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 88) = *(_QWORD *)((char *)v25 + v19 + 88);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 96) = *(_QWORD *)((char *)v25 + v19 + 96);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 104) = *(_QWORD *)((char *)v25 + v19 + 104);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 136) = *(_QWORD *)((char *)v25 + v19 + 136);
          *(_QWORD *)(v20 + *((_QWORD *)this + 1) + 144) = *(_QWORD *)((char *)v25 + v19 + 144);
          v21 = (unsigned __int16 *)(*((_QWORD *)this + 5) + 4LL * v18);
          CMetaData::mdReadTableData(this, (struct DBCOLUMNUPDATEINFO *)(v20 + *((_QWORD *)this + 1)), v21, v21 + 1);
        }
        ++v18;
      }
      ++v17;
      v22 = v33;
    }
    *(_WORD *)this = v18;
    *((_WORD *)this + 1) = v18 - v22;
    v23 = (unsigned __int16 *)v29;
    v29 = 0;
    *v34 = v23;
    v24 = (unsigned __int8 *)pv;
    pv = 0;
    *v35 = v24;
    *((_WORD *)this + 2) = 0;
LABEL_26:
    CoTaskMemFree(v6);
    CoTaskMemFree(v29);
    CoTaskMemFree(v25);
    CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v30);
    return v9;
  }
}

```

## disassembly

```asm
0x18000378c  mov     rax, rsp
0x18000378f  mov     [rax+20h], r9
0x180003793  mov     [rax+18h], r8
0x180003797  push    rbx
0x180003798  push    rsi
0x180003799  push    rdi
0x18000379a  push    r12
0x18000379c  push    r13
0x18000379e  push    r14
0x1800037a0  push    r15
0x1800037a2  sub     rsp, 0C0h
0x1800037a9  mov     r14, rdx
0x1800037ac  mov     rdi, rcx
0x1800037af  xor     ebx, ebx
0x1800037b1  mov     [rsp+0F8h+var_B0], ebx
0x1800037b5  mov     [rsp+0F8h+var_A0], rbx
0x1800037ba  mov     [rsp+0F8h+var_C0], rbx
0x1800037bf  movzx   r13d, bx
0x1800037c3  mov     [rax+10h], bx
0x1800037c7  mov     [rsp+0F8h+var_C8], rbx
0x1800037cc  mov     [rsp+0F8h+var_A8], rbx
0x1800037d1  mov     [rsp+0F8h+pv], rbx
0x1800037d6  mov     rax, [rdx]
0x1800037d9  lea     r8, [rsp+0F8h+var_A0]
0x1800037de  lea     rdx, IID_IColumnsUpdateInfo
0x1800037e5  mov     rcx, r14
0x1800037e8  mov     rax, [rax]
0x1800037eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037f0  test    eax, eax
0x1800037f2  jz      short loc_18000383B
0x1800037f4  mov     rcx, [rsp+0F8h+pv]; pv
0x1800037f9  call    cs:__imp_CoTaskMemFree
0x180003800  nop     dword ptr [rax+rax+00h]
0x180003805  nop
0x180003806  mov     rcx, [rsp+0F8h+var_A8]; pv
0x18000380b  call    cs:__imp_CoTaskMemFree
0x180003812  nop     dword ptr [rax+rax+00h]
0x180003817  nop
0x180003818  mov     rcx, [rsp+0F8h+var_C8]; pv
0x18000381d  call    cs:__imp_CoTaskMemFree
0x180003824  nop     dword ptr [rax+rax+00h]
0x180003829  nop
0x18000382a  lea     rcx, [rsp+0F8h+var_A0]
0x18000382f  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180003834  xor     eax, eax
0x180003836  jmp     loc_180003C1E
0x18000383b  mov     r15d, 1
0x180003841  mov     [rsp+0F8h+var_B0], r15d
0x180003846  mov     rcx, [rsp+0F8h+var_A0]
0x18000384b  mov     rax, [rcx]
0x18000384e  lea     rdx, [rsp+0F8h+pv]
0x180003853  mov     [rsp+0F8h+var_D8], rdx
0x180003858  lea     r9, [rsp+0F8h+var_A8]
0x18000385d  lea     r8, [rsp+0F8h+var_C8]
0x180003862  lea     rdx, [rsp+0F8h+var_C0]
0x180003867  mov     rax, [rax+18h]
0x18000386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003870  mov     esi, eax
0x180003872  test    eax, eax
0x180003874  jns     short loc_1800038B5
0x180003876  test    byte ptr cs:_bidGblFlags, 2
0x18000387d  jz      short loc_1800038AE
0x18000387f  mov     rcx, cs:off_180049488; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003886  test    rcx, rcx
0x180003889  jz      short loc_1800038AE
0x18000388b  mov     dword ptr [rsp+0F8h+var_D8], 14Bh
0x180003893  mov     r9d, eax
0x180003896  mov     r8, cs:off_180049488; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x18000389d  mov     edx, 52C00h
0x1800038a2  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800038a9  call    _bidTraceW
0x1800038ae  mov     ecx, esi; int
0x1800038b0  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800038b5  mov     rcx, [rsp+0F8h+var_C0]
0x1800038ba  call    ??$DownsizeToULONGThrow@_K@@YAK_KJ@Z; DownsizeToULONGThrow<unsigned __int64>(unsigned __int64,long)
0x1800038bf  mov     rdx, r14; struct IRowset *
0x1800038c2  call    ?mdGetHiddenCount@CMetaData@@AEAAKPEAUIRowset@@@Z; CMetaData::mdGetHiddenCount(IRowset *)
0x1800038c7  mov     eax, eax
0x1800038c9  mov     rcx, [rsp+0F8h+var_C0]
0x1800038ce  add     rcx, rax
0x1800038d1  mov     [rsp+0F8h+var_C0], rcx
0x1800038d6  imul    ecx, 0A8h; cb
0x1800038dc  call    cs:__imp_CoTaskMemAlloc
0x1800038e3  nop     dword ptr [rax+rax+00h]
0x1800038e8  mov     rcx, rax; void *
0x1800038eb  mov     [rdi+8], rax
0x1800038ef  test    rax, rax
0x1800038f2  jnz     short loc_180003939
0x1800038f4  test    byte ptr cs:_bidGblFlags, 2
0x1800038fb  jz      short loc_18000392F
0x1800038fd  mov     rax, cs:off_180049480; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003904  test    rax, rax
0x180003907  jz      short loc_18000392F
0x180003909  mov     dword ptr [rsp+0F8h+var_D8], 154h
0x180003911  mov     r9d, 8007000Eh
0x180003917  mov     r8, cs:off_180049480; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x18000391e  mov     edx, 55000h
0x180003923  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000392a  call    _bidTraceW
0x18000392f  mov     ecx, 8007000Eh; int
0x180003934  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180003939  imul    r8d, dword ptr [rsp+0F8h+var_C0], 0A8h; Size
0x180003942  xor     edx, edx; Val
0x180003944  call    memset_0
0x180003949  cmp     [rsp+0F8h+pv], rbx
0x18000394e  jz      short loc_18000398F
0x180003950  movsxd  rcx, dword ptr [rsp+0F8h+var_C0]
0x180003955  mov     eax, 4
0x18000395a  mul     rcx
0x18000395d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180003964  cmovb   rax, rcx
0x180003968  mov     ecx, eax; unsigned int
0x18000396a  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18000396f  mov     [rdi+28h], rax
0x180003973  mov     rcx, rax; void *
0x180003976  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x18000397b  mov     r8d, dword ptr [rsp+0F8h+var_C0]
0x180003980  shl     r8d, 2; Size
0x180003984  xor     edx, edx; Val
0x180003986  mov     rcx, [rdi+28h]; void *
0x18000398a  call    memset_0
0x18000398f  movzx   r12d, bx
0x180003993  movzx   esi, bx
0x180003996  movzx   eax, r12w
0x18000399a  cmp     rax, [rsp+0F8h+var_C0]
0x18000399f  jnb     loc_180003B48
0x1800039a5  imul    r14, rax, 0A8h
0x1800039ac  mov     rax, [rsp+0F8h+var_C8]
0x1800039b1  movups  xmm0, xmmword ptr [r14+rax]
0x1800039b6  movaps  xmmword ptr [rsp+0F8h+var_88.pwszName], xmm0
0x1800039bb  movups  xmm1, xmmword ptr [r14+rax+10h]
0x1800039c1  movaps  xmmword ptr [rsp+0F8h+var_88.iOrdinal], xmm1
0x1800039c9  movups  xmm0, xmmword ptr [r14+rax+20h]
0x1800039cf  movaps  xmmword ptr [rsp+0F8h+var_88.ulColumnSize], xmm0
0x1800039d7  movups  xmm1, xmmword ptr [r14+rax+30h]
0x1800039dd  movaps  xmmword ptr [rsp+0F8h+var_88.columnid.uGuid], xmm1
0x1800039e5  movups  xmm0, xmmword ptr [r14+rax+40h]
0x1800039eb  movaps  xmmword ptr [rsp+0F8h+var_88.columnid.eKind], xmm0
0x1800039f3  lea     r9, [rsp+0F8h+arg_8]; unsigned __int16 *
0x1800039fb  movzx   r8d, si; unsigned __int16
0x1800039ff  lea     rdx, [rsp+0F8h+var_88]; struct tagDBCOLUMNINFO
0x180003a04  mov     rcx, rdi; this
0x180003a07  call    ?mdGetColInfo@CMetaData@@AEAAHUtagDBCOLUMNINFO@@GPEAG@Z; CMetaData::mdGetColInfo(tagDBCOLUMNINFO,ushort,ushort *)
0x180003a0c  test    eax, eax
0x180003a0e  jz      loc_180003B36
0x180003a14  movzx   r8d, si
0x180003a18  imul    r10, r8, 0A8h
0x180003a1f  mov     rdx, [rdi+8]
0x180003a23  mov     rax, [rsp+0F8h+var_C8]
0x180003a28  movzx   ecx, word ptr [r14+rax+70h]
0x180003a2e  mov     [r10+rdx+70h], cx
0x180003a34  mov     rdx, [rdi+8]
0x180003a38  mov     rax, [rsp+0F8h+var_C8]
0x180003a3d  movzx   ecx, word ptr [r14+rax+72h]
0x180003a43  mov     [r10+rdx+72h], cx
0x180003a49  mov     rdx, [rdi+8]
0x180003a4d  mov     rax, [rsp+0F8h+var_C8]
0x180003a52  mov     rcx, [r14+rax+78h]
0x180003a57  mov     [r10+rdx+78h], rcx
0x180003a5c  mov     rdx, [rdi+8]
0x180003a60  mov     rax, [rsp+0F8h+var_C8]
0x180003a65  mov     rcx, [r14+rax+80h]
0x180003a6d  mov     [r10+rdx+80h], rcx
0x180003a75  mov     rdx, [rdi+8]
0x180003a79  mov     rax, [rsp+0F8h+var_C8]
0x180003a7e  mov     ecx, [r14+rax+0A0h]
0x180003a86  mov     [r10+rdx+0A0h], ecx
0x180003a8e  cmp     [rsp+0F8h+pv], rbx
0x180003a93  jz      loc_180003B32
0x180003a99  mov     rdx, [rdi+8]
0x180003a9d  mov     rax, [rsp+0F8h+var_C8]
0x180003aa2  mov     rcx, [r14+rax+50h]
0x180003aa7  mov     [r10+rdx+50h], rcx
0x180003aac  mov     rdx, [rdi+8]
0x180003ab0  mov     rax, [rsp+0F8h+var_C8]
0x180003ab5  mov     rcx, [r14+rax+58h]
0x180003aba  mov     [r10+rdx+58h], rcx
0x180003abf  mov     rdx, [rdi+8]
0x180003ac3  mov     rax, [rsp+0F8h+var_C8]
0x180003ac8  mov     rcx, [r14+rax+60h]
0x180003acd  mov     [r10+rdx+60h], rcx
0x180003ad2  mov     rdx, [rdi+8]
0x180003ad6  mov     rax, [rsp+0F8h+var_C8]
0x180003adb  mov     rcx, [r14+rax+68h]
0x180003ae0  mov     [r10+rdx+68h], rcx
0x180003ae5  mov     rdx, [rdi+8]
0x180003ae9  mov     rax, [rsp+0F8h+var_C8]
0x180003aee  mov     rcx, [r14+rax+88h]
0x180003af6  mov     [r10+rdx+88h], rcx
0x180003afe  mov     rdx, [rdi+8]
0x180003b02  mov     rax, [rsp+0F8h+var_C8]
0x180003b07  mov     rcx, [r14+rax+90h]
0x180003b0f  mov     [r10+rdx+90h], rcx
0x180003b17  mov     rax, [rdi+28h]
0x180003b1b  lea     r8, [rax+r8*4]; unsigned __int16 *
0x180003b1f  lea     r9, [r8+2]; unsigned __int16 *
0x180003b23  mov     rdx, [rdi+8]
0x180003b27  add     rdx, r10; struct DBCOLUMNUPDATEINFO *
0x180003b2a  mov     rcx, rdi; this
0x180003b2d  call    ?mdReadTableData@CMetaData@@AEAAXPEAUDBCOLUMNUPDATEINFO@@PEAG1@Z; CMetaData::mdReadTableData(DBCOLUMNUPDATEINFO *,ushort *,ushort *)
0x180003b32  add     si, r15w
0x180003b36  add     r12w, r15w
0x180003b3a  movzx   r13d, word ptr [rsp+0F8h+arg_8]
0x180003b43  jmp     loc_180003996
0x180003b48  mov     [rdi], si
0x180003b4b  sub     si, r13w
0x180003b4f  mov     [rdi+2], si
0x180003b53  mov     rax, [rsp+0F8h+var_A8]
0x180003b58  mov     [rsp+0F8h+var_A8], rbx
0x180003b5d  mov     rcx, [rsp+0F8h+arg_10]
0x180003b65  mov     [rcx], rax
0x180003b68  mov     rax, [rsp+0F8h+pv]
0x180003b6d  mov     [rsp+0F8h+pv], rbx
0x180003b72  mov     rcx, [rsp+0F8h+arg_18]
0x180003b7a  mov     [rcx], rax
0x180003b7d  mov     [rdi+4], bx
0x180003b81  jmp     short loc_180003BDD
0x180003b83  mov     r15d, [rsp+0F8h+var_B0]
0x180003b88  test    r15d, r15d
0x180003b8b  jz      short loc_180003BD8
0x180003b8d  mov     edi, [rsp+0F8h+arg_8]
0x180003b94  test    edi, edi
0x180003b96  jns     short loc_180003BD8
0x180003b98  test    byte ptr cs:_bidGblFlags, 2
0x180003b9f  jz      short loc_180003BD0
0x180003ba1  mov     rax, cs:off_180049478; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003ba8  test    rax, rax
0x180003bab  jz      short loc_180003BD0
0x180003bad  mov     dword ptr [rsp+0F8h+var_D8], 18Eh
0x180003bb5  mov     r9d, edi
0x180003bb8  mov     r8, cs:off_180049478; "<CMetaData::mdGetColumnsUpdateInfo|ADO|"...
0x180003bbf  mov     edx, 63800h
0x180003bc4  mov     rcx, cs:off_1800491B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180003bcb  call    _bidTraceW
0x180003bd0  mov     ecx, edi; int
0x180003bd2  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180003bd8  mov     rbx, [rsp+0F8h+pv]
0x180003bdd  mov     rcx, rbx; pv
0x180003be0  call    cs:__imp_CoTaskMemFree
0x180003be7  nop     dword ptr [rax+rax+00h]
0x180003bec  nop
0x180003bed  mov     rcx, [rsp+0F8h+var_A8]; pv
0x180003bf2  call    cs:__imp_CoTaskMemFree
0x180003bf9  nop     dword ptr [rax+rax+00h]
0x180003bfe  nop
0x180003bff  mov     rcx, [rsp+0F8h+var_C8]; pv
0x180003c04  call    cs:__imp_CoTaskMemFree
0x180003c0b  nop     dword ptr [rax+rax+00h]
0x180003c10  nop
0x180003c11  lea     rcx, [rsp+0F8h+var_A0]
0x180003c16  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180003c1b  mov     eax, r15d
0x180003c1e  add     rsp, 0C0h
0x180003c25  pop     r15
0x180003c27  pop     r14
0x180003c29  pop     r13
0x180003c2b  pop     r12
0x180003c2d  pop     rdi
0x180003c2e  pop     rsi
0x180003c2f  pop     rbx
0x180003c30  retn
```
