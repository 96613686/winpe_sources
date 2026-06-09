# GenADTG::SaveResultRow(unsigned __int64,ADTGTOKENTYPEENUM,uchar *)

- ea: `0x180008b90`
- end: `0x180008df7`
- name: `?SaveResultRow@GenADTG@@QEAAX_KW4ADTGTOKENTYPEENUM@@PEAE@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update`

## callers

- `0x180008e00`

## callees

- `0x180002770`
- `0x180003c38`
- `0x180004384`
- `0x1800066f4`
- `0x180007838`
- `0x180008b90`
- `0x18000912c`
- `0x180009678`
- `0x18000983c`
- `0x18001b008`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008dd1`
- `ole32!CoTaskMemFree` at `0x180008dd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GenADTG::SaveResultRow(__int64 a1, __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rbx
  int v10; // eax
  int v11; // ebx
  unsigned int v12; // r14d
  unsigned __int16 i; // bx
  __int64 v14; // r8
  __int64 v15; // r15
  unsigned __int16 v16; // dx
  unsigned __int16 Type; // ax
  __int64 v18; // r8
  __int64 v19; // r11
  __int16 v20; // r10
  unsigned int v21; // ecx
  int v22; // eax
  unsigned int v23; // edx
  LPVOID pv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v25; // [rsp+38h] [rbp-18h] BYREF
  __int64 v26; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int64 v27; // [rsp+48h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+90h] [rbp+40h] BYREF

  v28 = a3;
  v27 = 0;
  v26 = 0;
  pv = 0;
  v25 = 0;
  GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)&v28, 1u);
  v8 = v28;
  if ( (v28 & 0x80u) != 0 )
  {
    GenADTG::SaveToBuffer((GenADTG *)a1, (const unsigned __int8 *)(a1 + 284), 4u);
    v8 = v28;
  }
  LODWORD(v8) = v8 & 0xFFFFFF7F;
  v28 = v8;
  if ( (_DWORD)v8 != 12 )
  {
    if ( (_DWORD)v8 == 10 || (_DWORD)v8 == 13 )
    {
      v25 = 0;
      if ( !*(_QWORD *)(a1 + 48) )
      {
        (***(void (__fastcall ****)(_QWORD, GUID *, __int64))(a1 + 24))(*(_QWORD *)(a1 + 24), &IID_IUpdateInfo, a1 + 48);
        v8 = v28;
      }
      v9 = *(_QWORD *)(a1 + 48);
      if ( v9 )
      {
        v25 = *(_QWORD *)(a1 + 48);
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v9 + 8LL))(v9, v7, v8);
        v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, LPVOID *))(*(_QWORD *)v9 + 24LL))(
                v9,
                a2,
                &v26,
                &pv);
        v11 = v10;
        if ( v10 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( off_180049550[0] )
              bidTraceW(off_1800491C0[0], 1902592, off_180049550[0], (unsigned int)v10, 1858);
          }
          ThrowHR(v11);
        }
        v8 = v28;
      }
    }
    GenADTG::SaveRowMaps(a1, v7, v8, a4, v26, pv);
    v12 = 0;
    for ( i = 0; i < *(_WORD *)(a1 + 64); ++i )
    {
      if ( (unsigned int)GenADTG::FShouldSave(a1, v28, i, v26, pv) )
        GenADTG::SaveColumnData(a1, i, v14, &v27, a4);
      v15 = *(_QWORD *)(a1 + 56);
      CMetaData::mdGetFlags((CMetaData *)(a1 + 128), *(_WORD *)(88LL * i + v15) - 1);
      Type = CMetaData::mdGetType((CMetaData *)(a1 + 128), v16);
      if ( (v20 & 0x2000) != 0 || Type == 136 )
      {
        v21 = *(_DWORD *)(*(unsigned int *)(v19 + v15 + 24) + a4);
        if ( v21 <= 0xD )
        {
          v22 = 8209;
          if ( _bittest(&v22, v21) )
          {
            GenADTG::SaveColumnData(a1, i, v18, &v27, a4);
            v23 = v12++;
            GenADTG::SetChildHChapter((GenADTG *)a1, v23, v27);
          }
        }
      }
    }
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v25);
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x180008b90  mov     [rsp-28h+arg_0], rbx
0x180008b95  mov     [rsp-28h+arg_8], rsi
0x180008b9a  mov     [rsp-28h+arg_10], r8d
0x180008b9f  push    rbp
0x180008ba0  push    rdi
0x180008ba1  push    r12
0x180008ba3  push    r14
0x180008ba5  push    r15
0x180008ba7  mov     rbp, rsp
0x180008baa  sub     rsp, 50h
0x180008bae  mov     rsi, r9
0x180008bb1  mov     r14, rdx
0x180008bb4  mov     rdi, rcx
0x180008bb7  mov     [rbp+var_8], 0
0x180008bbf  mov     [rbp+var_10], 0
0x180008bc7  mov     [rbp+pv], 0
0x180008bcf  mov     [rbp+var_18], 0
0x180008bd7  mov     r8d, 1; unsigned int
0x180008bdd  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x180008be1  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008be6  mov     r8d, [rbp+arg_10]
0x180008bea  test    r8b, r8b
0x180008bed  jns     short loc_180008C08
0x180008bef  lea     rdx, [rdi+11Ch]; unsigned __int8 *
0x180008bf6  mov     r8d, 4; unsigned int
0x180008bfc  mov     rcx, rdi; this
0x180008bff  call    ?SaveToBuffer@GenADTG@@AEAAXPEBEK@Z; GenADTG::SaveToBuffer(uchar const *,ulong)
0x180008c04  mov     r8d, [rbp+arg_10]
0x180008c08  btr     r8d, 7
0x180008c0d  mov     [rbp+arg_10], r8d
0x180008c11  cmp     r8d, 0Ch
0x180008c15  jz      loc_180008DC3
0x180008c1b  cmp     r8d, 0Ah
0x180008c1f  jz      short loc_180008C2B
0x180008c21  cmp     r8d, 0Dh
0x180008c25  jnz     loc_180008CD9
0x180008c2b  mov     [rbp+var_18], 0
0x180008c33  lea     rbx, [rdi+30h]
0x180008c37  cmp     qword ptr [rbx], 0
0x180008c3b  jnz     short loc_180008C5A
0x180008c3d  mov     rcx, [rdi+18h]
0x180008c41  mov     rax, [rcx]
0x180008c44  mov     r8, rbx
0x180008c47  lea     rdx, ?IID_IUpdateInfo@@3U_GUID@@B; _GUID const IID_IUpdateInfo
0x180008c4e  mov     rax, [rax]
0x180008c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c56  mov     r8d, [rbp+arg_10]
0x180008c5a  mov     rbx, [rbx]
0x180008c5d  test    rbx, rbx
0x180008c60  jz      short loc_180008CD9
0x180008c62  mov     [rbp+var_18], rbx
0x180008c66  mov     rax, [rbx]
0x180008c69  mov     rcx, rbx
0x180008c6c  mov     rax, [rax+8]
0x180008c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c75  mov     rax, [rbx]
0x180008c78  lea     r9, [rbp+pv]
0x180008c7c  lea     r8, [rbp+var_10]
0x180008c80  mov     rdx, r14
0x180008c83  mov     rcx, rbx
0x180008c86  mov     rax, [rax+18h]
0x180008c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8f  mov     ebx, eax
0x180008c91  test    eax, eax
0x180008c93  jns     short loc_180008CD5
0x180008c95  test    byte ptr cs:_bidGblFlags, 2
0x180008c9c  jz      short loc_180008CCD
0x180008c9e  mov     rcx, cs:off_180049550; "<GenADTG::SaveResultRow|ADO|ERR>  HRESU"...
0x180008ca5  test    rcx, rcx
0x180008ca8  jz      short loc_180008CCD
0x180008caa  mov     dword ptr [rsp+50h+var_30], 742h
0x180008cb2  mov     r9d, eax
0x180008cb5  mov     r8, cs:off_180049550; "<GenADTG::SaveResultRow|ADO|ERR>  HRESU"...
0x180008cbc  mov     edx, 1D0800h
0x180008cc1  mov     rcx, cs:off_1800491C0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180008cc8  call    _bidTraceW
0x180008ccd  mov     ecx, ebx; int
0x180008ccf  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180008cd5  mov     r8d, [rbp+arg_10]
0x180008cd9  mov     rax, [rbp+pv]
0x180008cdd  mov     [rsp+50h+var_28], rax
0x180008ce2  mov     rax, [rbp+var_10]
0x180008ce6  mov     [rsp+50h+var_30], rax
0x180008ceb  mov     r9, rsi
0x180008cee  mov     rcx, rdi
0x180008cf1  call    ?SaveRowMaps@GenADTG@@AEAAX_KW4ADTGTOKENTYPEENUM@@PEAE0PEA_K@Z; GenADTG::SaveRowMaps(unsigned __int64,ADTGTOKENTYPEENUM,uchar *,unsigned __int64,unsigned __int64 *)
0x180008cf6  xor     r14d, r14d
0x180008cf9  xor     ebx, ebx
0x180008cfb  xor     eax, eax
0x180008cfd  cmp     ax, [rdi+40h]
0x180008d01  jnb     loc_180008DC3
0x180008d07  lea     r12, [rdi+80h]
0x180008d0e  movzx   r8d, bx
0x180008d12  mov     rax, [rbp+pv]
0x180008d16  mov     [rsp+50h+var_30], rax
0x180008d1b  mov     r9, [rbp+var_10]
0x180008d1f  mov     edx, [rbp+arg_10]
0x180008d22  mov     rcx, rdi
0x180008d25  call    ?FShouldSave@GenADTG@@AEAAHW4ADTGTOKENTYPEENUM@@K_KPEA_K@Z; GenADTG::FShouldSave(ADTGTOKENTYPEENUM,ulong,unsigned __int64,unsigned __int64 *)
0x180008d2a  test    eax, eax
0x180008d2c  jz      short loc_180008D42
0x180008d2e  mov     [rsp+50h+var_30], rsi
0x180008d33  lea     r9, [rbp+var_8]
0x180008d37  movzx   edx, bx
0x180008d3a  mov     rcx, rdi
0x180008d3d  call    ?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z; GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)
0x180008d42  movzx   eax, bx
0x180008d45  imul    r11, rax, 58h ; 'X'
0x180008d49  mov     r15, [rdi+38h]
0x180008d4d  movzx   edx, word ptr [r11+r15]
0x180008d52  dec     dx; unsigned __int16
0x180008d55  mov     rcx, r12; this
0x180008d58  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x180008d5d  mov     r10d, eax
0x180008d60  mov     rcx, r12; this
0x180008d63  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x180008d68  bt      r10d, 0Dh
0x180008d6d  jb      short loc_180008D79
0x180008d6f  mov     ecx, 88h
0x180008d74  cmp     ax, cx
0x180008d77  jnz     short loc_180008DB6
0x180008d79  mov     eax, [r11+r15+18h]
0x180008d7e  mov     ecx, [rax+rsi]
0x180008d81  cmp     ecx, 0Dh
0x180008d84  ja      short loc_180008DB6
0x180008d86  mov     eax, 2011h
0x180008d8b  bt      eax, ecx
0x180008d8e  jnb     short loc_180008DB6
0x180008d90  mov     [rsp+50h+var_30], rsi
0x180008d95  lea     r9, [rbp+var_8]
0x180008d99  movzx   edx, bx
0x180008d9c  mov     rcx, rdi
0x180008d9f  call    ?SaveColumnData@GenADTG@@AEAAXGW4ADTGTOKENTYPEENUM@@PEA_KPEAE@Z; GenADTG::SaveColumnData(ushort,ADTGTOKENTYPEENUM,unsigned __int64 *,uchar *)
0x180008da4  mov     edx, r14d; unsigned int
0x180008da7  inc     r14d
0x180008daa  mov     r8, [rbp+var_8]; unsigned __int64
0x180008dae  mov     rcx, rdi; this
0x180008db1  call    ?SetChildHChapter@GenADTG@@AEAAXK_K@Z; GenADTG::SetChildHChapter(ulong,unsigned __int64)
0x180008db6  inc     bx
0x180008db9  cmp     bx, [rdi+40h]
0x180008dbd  jb      loc_180008D0E
0x180008dc3  lea     rcx, [rbp+var_18]
0x180008dc7  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180008dcc  nop
0x180008dcd  mov     rcx, [rbp+pv]; pv
0x180008dd1  call    cs:__imp_CoTaskMemFree
0x180008dd8  nop     dword ptr [rax+rax+00h]
0x180008ddd  lea     r11, [rsp+50h+var_s0]
0x180008de2  mov     rbx, [r11+30h]
0x180008de6  mov     rsi, [r11+38h]
0x180008dea  mov     rsp, r11
0x180008ded  pop     r15
0x180008def  pop     r14
0x180008df1  pop     r12
0x180008df3  pop     rdi
0x180008df4  pop     rbp
0x180008df5  retn
```
