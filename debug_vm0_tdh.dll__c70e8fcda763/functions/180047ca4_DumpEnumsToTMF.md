# DumpEnumsToTMF

- ea: `0x180047ca4`
- end: `0x180047f56`
- name: `DumpEnumsToTMF`
- size: `690`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180048650`

## callees

- `0x180018318`
- `0x180018a3c`
- `0x1800212ea`
- `0x180021724`
- `0x180042240`
- `0x1800431b4`
- `0x180047ab4`
- `0x180047ca4`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180047dbb`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x180047dbb`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047cda`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047ed6`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047f08`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047cda`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047ed6`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x180047f08`

## string_xrefs

- `0x180047d91`: `WPPFMT : error : File + Path\n`

## pseudocode

```c
void __fastcall DumpEnumsToTMF(__int64 a1)
{
  unsigned int v1; // r15d
  FILE *v3; // r10
  int v4; // r14d
  __int64 v5; // rsi
  __int64 v6; // rdi
  signed int v7; // eax
  FILE *v8; // rax
  unsigned __int16 v9; // bp
  __int64 v10; // r14
  _QWORD *v11; // r13
  __int64 v12; // r12
  wchar_t *FileName[11]; // [rsp+20h] [rbp-58h] BYREF
  int v14; // [rsp+88h] [rbp+10h]

  v1 = 0;
  if ( PostProcessEnums )
  {
    if ( TraceFileP )
    {
      fclose(TraceFileP);
      TraceFileP = 0;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(FileName);
    v4 = 0;
    v14 = 0;
    if ( NextFreeGuid )
    {
      while ( 1 )
      {
        v5 = *(_QWORD *)&GuidHead.Data1;
        v6 = 56LL * (unsigned __int16)v4;
        if ( *(_QWORD *)(a1 + 32) || v3 )
          break;
        if ( SingleFile )
          v7 = (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                  FileName,
                                  g_SingleFileName,
                                  (qword_18006CDD0 - (__int64)g_SingleFileName) >> 1) == 0
             ? 0x8007000E
             : 0;
        else
          v7 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                 FileName,
                 L"%ls\\%hs.tmf",
                 *(_QWORD *)(a1 + 16),
                 v6 + *(_QWORD *)&GuidHead.Data1 + 12LL);
        if ( v7 >= 0 )
        {
          TraceFileP = _wfsopen(FileName[0], L"a", 16);
          v3 = TraceFileP;
          if ( TraceFileP )
            break;
        }
        else
        {
          v8 = o___acrt_iob_func_0(2u);
          fprintf(v8, "WPPFMT : error : File + Path\n");
          v3 = TraceFileP;
        }
LABEL_27:
        LOWORD(v4) = v4 + 1;
        v14 = v4;
        if ( (unsigned __int16)v4 >= NextFreeGuid )
          goto LABEL_28;
      }
      if ( SingleFile )
      {
        fprintf(v3, "%hs %ls\n", (const char *)(v6 + v5 + 12), *(const wchar_t **)(a1 + 8));
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 32) )
        {
LABEL_18:
          v9 = 0;
          if ( *(_WORD *)(v6 + v5 + 10) )
          {
            v10 = *(_QWORD *)(v6 + v5);
            do
            {
              v11 = EnumHead;
              v12 = 3LL * *(unsigned int *)(v10 + 4LL * v9);
              BufferPrintf(a1, "#enumv %hs\n{\n", *((const char **)EnumHead + 3 * *(unsigned int *)(v10 + 4LL * v9)));
              if ( LODWORD(v11[v12 + 2]) )
              {
                do
                {
                  BufferPrintf(
                    a1,
                    "%ls,0x%I64X\n",
                    *(const wchar_t **)(v11[v12 + 1] + 16LL * v1),
                    *(_QWORD *)(v11[v12 + 1] + 16LL * v1 + 8));
                  ++v1;
                }
                while ( v1 < LODWORD(v11[v12 + 2]) );
              }
              BufferPrintf(a1, "}\n");
              ++v9;
              v1 = 0;
            }
            while ( v9 < *(_WORD *)(v6 + v5 + 10) );
            v3 = TraceFileP;
            v4 = v14;
          }
          if ( !SingleFile && v3 )
          {
            fclose(v3);
            v3 = 0;
            TraceFileP = 0;
          }
          goto LABEL_27;
        }
        BufferPrintf(a1, "%hs %ls\n", (const char *)(v6 + v5 + 12), *(const wchar_t **)(a1 + 8));
      }
      v3 = TraceFileP;
      goto LABEL_18;
    }
LABEL_28:
    if ( v3 )
    {
      fclose(v3);
      TraceFileP = 0;
    }
    if ( *(_QWORD *)(a1 + 32) )
    {
      if ( *(_DWORD *)(a1 + 44) )
        (*(void (__fastcall **)(_QWORD))(a1 + 24))(**(_QWORD **)a1);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(FileName);
  }
}

```

## disassembly

```asm
0x180047ca4  mov     [rsp+arg_0], rbx
0x180047ca9  push    rbp
0x180047caa  push    rsi
0x180047cab  push    rdi
0x180047cac  push    r12
0x180047cae  push    r13
0x180047cb0  push    r14
0x180047cb2  push    r15
0x180047cb4  sub     rsp, 40h
0x180047cb8  xor     r15d, r15d
0x180047cbb  mov     rbx, rcx
0x180047cbe  cmp     cs:?PostProcessEnums@@3_NA, r15b; bool PostProcessEnums
0x180047cc5  jz      loc_180047F3E
0x180047ccb  mov     r10, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x180047cd2  test    r10, r10
0x180047cd5  jz      short loc_180047CEA
0x180047cd7  mov     rcx, r10; Stream
0x180047cda  call    cs:__imp_fclose
0x180047ce0  mov     r10d, r15d
0x180047ce3  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, r15; _iobuf * TraceFileP
0x180047cea  lea     rcx, [rsp+78h+FileName]
0x180047cef  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180047cf4  cmp     r15w, cs:?NextFreeGuid@@3GA; ushort NextFreeGuid
0x180047cfc  mov     r14d, r15d
0x180047cff  mov     [rsp+78h+arg_8], r15d
0x180047d07  jnb     loc_180047F00
0x180047d0d  mov     r12d, 1
0x180047d13  mov     rsi, qword ptr cs:?GuidHead@@3PEAUGUID_POST_PROCESS_DATA@@EA.Data1; GUID_POST_PROCESS_DATA * GuidHead ...
0x180047d1a  movzx   eax, r14w
0x180047d1e  imul    rdi, rax, 38h ; '8'
0x180047d22  cmp     [rbx+20h], r15
0x180047d26  jnz     loc_180047DD4
0x180047d2c  test    r10, r10
0x180047d2f  jnz     loc_180047DD4
0x180047d35  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x180047d3c  lea     rcx, [rsp+78h+FileName]
0x180047d41  jz      short loc_180047D69
0x180047d43  mov     r8, cs:qword_18006CDD0
0x180047d4a  mov     rdx, cs:?g_SingleFileName@@3V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@A; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> g_SingleFileName
0x180047d51  sub     r8, rdx
0x180047d54  sar     r8, 1
0x180047d57  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180047d5c  neg     al
0x180047d5e  sbb     eax, eax
0x180047d60  not     eax
0x180047d62  and     eax, 8007000Eh
0x180047d67  jmp     short loc_180047D80
0x180047d69  mov     r8, [rbx+10h]
0x180047d6d  lea     r9, [rsi+0Ch]
0x180047d71  add     r9, rdi
0x180047d74  lea     rdx, aLsHsTmf; "%ls\\%hs.tmf"
0x180047d7b  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x180047d80  test    eax, eax
0x180047d82  jns     short loc_180047DA9
0x180047d84  mov     ecx, 2; Ix
0x180047d89  call    _o___acrt_iob_func_0
0x180047d8e  mov     rcx, rax; Stream
0x180047d91  lea     rdx, aWppfmtErrorFil_0; "WPPFMT : error : File + Path\n"
0x180047d98  call    fprintf
0x180047d9d  mov     r10, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x180047da4  jmp     loc_180047EE6
0x180047da9  mov     rcx, [rsp+78h+FileName]; FileName
0x180047dae  lea     rdx, aA; "a"
0x180047db5  mov     r8d, 10h; ShFlag
0x180047dbb  call    cs:__imp__wfsopen
0x180047dc1  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, rax; _iobuf * TraceFileP
0x180047dc8  mov     r10, rax
0x180047dcb  test    rax, rax
0x180047dce  jz      loc_180047EE6
0x180047dd4  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x180047ddb  jz      short loc_180047DF9
0x180047ddd  mov     r9, [rbx+8]
0x180047de1  lea     r8, [rsi+0Ch]
0x180047de5  add     r8, rdi
0x180047de8  lea     rdx, aHsLs; "%hs %ls\n"
0x180047def  mov     rcx, r10; Stream
0x180047df2  call    fprintf
0x180047df7  jmp     short loc_180047E19
0x180047df9  cmp     [rbx+20h], r15
0x180047dfd  jz      short loc_180047E20
0x180047dff  mov     r9, [rbx+8]
0x180047e03  lea     r8, [rsi+0Ch]
0x180047e07  add     r8, rdi
0x180047e0a  lea     rdx, aHsLs; "%hs %ls\n"
0x180047e11  mov     rcx, rbx
0x180047e14  call    BufferPrintf
0x180047e19  mov     r10, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x180047e20  mov     ebp, r15d
0x180047e23  mov     rax, [rdi+rsi]
0x180047e27  cmp     r15w, [rdi+rsi+0Ah]
0x180047e2d  jnb     loc_180047EC5
0x180047e33  mov     r14, rax
0x180047e36  mov     r13, cs:?EnumHead@@3PEAUENUMDATA@@EA; ENUMDATA * EnumHead
0x180047e3d  lea     rdx, aEnumvHs; "#enumv %hs\n{\n"
0x180047e44  movzx   eax, bp
0x180047e47  mov     ecx, [r14+rax*4]
0x180047e4b  lea     r12, [rcx+rcx*2]
0x180047e4f  mov     rcx, rbx
0x180047e52  mov     r8, [r13+r12*8+0]
0x180047e57  call    BufferPrintf
0x180047e5c  cmp     dword ptr [r13+r12*8+10h], 0
0x180047e62  jbe     short loc_180047E91
0x180047e64  mov     r8, [r13+r12*8+8]
0x180047e69  lea     rdx, aLs0xI64x; "%ls,0x%I64X\n"
0x180047e70  mov     eax, r15d
0x180047e73  mov     rcx, rbx
0x180047e76  add     rax, rax
0x180047e79  mov     r9, [r8+rax*8+8]
0x180047e7e  mov     r8, [r8+rax*8]
0x180047e82  call    BufferPrintf
0x180047e87  inc     r15d
0x180047e8a  cmp     r15d, [r13+r12*8+10h]
0x180047e8f  jb      short loc_180047E64
0x180047e91  lea     rdx, asc_180061658; "}\n"
0x180047e98  mov     rcx, rbx
0x180047e9b  call    BufferPrintf
0x180047ea0  mov     r12d, 1
0x180047ea6  add     bp, r12w
0x180047eaa  lea     r15d, [r12-1]
0x180047eaf  cmp     bp, [rdi+rsi+0Ah]
0x180047eb4  jb      short loc_180047E36
0x180047eb6  mov     r10, cs:?TraceFileP@@3PEAU_iobuf@@EA; _iobuf * TraceFileP
0x180047ebd  mov     r14d, [rsp+78h+arg_8]
0x180047ec5  cmp     cs:?SingleFile@@3HA, r15d; int SingleFile
0x180047ecc  jnz     short loc_180047EE6
0x180047ece  test    r10, r10
0x180047ed1  jz      short loc_180047EE6
0x180047ed3  mov     rcx, r10; Stream
0x180047ed6  call    cs:__imp_fclose
0x180047edc  mov     r10, r15
0x180047edf  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, r15; _iobuf * TraceFileP
0x180047ee6  add     r14w, r12w
0x180047eea  cmp     r14w, cs:?NextFreeGuid@@3GA; ushort NextFreeGuid
0x180047ef2  mov     [rsp+78h+arg_8], r14d
0x180047efa  jb      loc_180047D13
0x180047f00  test    r10, r10
0x180047f03  jz      short loc_180047F15
0x180047f05  mov     rcx, r10; Stream
0x180047f08  call    cs:__imp_fclose
0x180047f0e  mov     cs:?TraceFileP@@3PEAU_iobuf@@EA, r15; _iobuf * TraceFileP
0x180047f15  mov     r8, [rbx+20h]
0x180047f19  test    r8, r8
0x180047f1c  jz      short loc_180047F34
0x180047f1e  mov     edx, [rbx+2Ch]
0x180047f21  test    edx, edx
0x180047f23  jz      short loc_180047F34
0x180047f25  mov     rcx, [rbx]
0x180047f28  mov     rax, [rbx+18h]
0x180047f2c  mov     rcx, [rcx]
0x180047f2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f34  lea     rcx, [rsp+78h+FileName]
0x180047f39  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180047f3e  mov     rbx, [rsp+78h+arg_0]
0x180047f46  add     rsp, 40h
0x180047f4a  pop     r15
0x180047f4c  pop     r14
0x180047f4e  pop     r13
0x180047f50  pop     r12
0x180047f52  pop     rdi
0x180047f53  pop     rsi
0x180047f54  pop     rbp
0x180047f55  retn
```
