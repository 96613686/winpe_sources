# OutputAvc::OutputAvc(int,int,int,int,RecordSettings &,int)

- ea: `0x1805beb68`
- end: `0x1805befde`
- name: `??0OutputAvc@@QEAA@HHHHAEAURecordSettings@@H@Z`
- size: `1142`
- prototype: `OutputAvc *__usercall@<rax>(FILE **Stream@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, struct RecordSettings *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1802ed7f0`
- `0x180310430`

## callees

- `0x18012962c`
- `0x1805beb30`
- `0x1805beb68`
- `0x180688fc0`

## import_xrefs

- `msvcrt!_wfopen_s` at `0x1805bec82`
- `msvcrt!_wfopen_s` at `0x1805becd3`
- `msvcrt!_wfopen_s` at `0x1805bed44`
- `msvcrt!_wfopen_s` at `0x1805bed94`
- `msvcrt!_wfopen_s` at `0x1805bedf3`
- `msvcrt!_wfopen_s` at `0x1805bee45`
- `msvcrt!_wfopen_s` at `0x1805bee96`
- `msvcrt!_wfopen_s` at `0x1805beee7`
- `msvcrt!_wfopen_s` at `0x1805bec82`
- `msvcrt!_wfopen_s` at `0x1805becd3`
- `msvcrt!_wfopen_s` at `0x1805bed44`
- `msvcrt!_wfopen_s` at `0x1805bed94`
- `msvcrt!_wfopen_s` at `0x1805bedf3`
- `msvcrt!_wfopen_s` at `0x1805bee45`
- `msvcrt!_wfopen_s` at `0x1805bee96`
- `msvcrt!_wfopen_s` at `0x1805beee7`
- `msvcrt!swprintf_s` at `0x1805bef34`
- `msvcrt!swprintf_s` at `0x1805bef77`
- `msvcrt!swprintf_s` at `0x1805befb2`
- `msvcrt!swprintf_s` at `0x1805bef34`
- `msvcrt!swprintf_s` at `0x1805bef77`
- `msvcrt!swprintf_s` at `0x1805befb2`

## pseudocode

```c
FILE **__fastcall OutputAvc::OutputAvc(
        FILE **Stream,
        int a2,
        int a3,
        int a4,
        int a5,
        struct RecordSettings *a6,
        int a7)
{
  FILE **v10; // r13
  bool v12; // zf
  const wchar_t *v13; // rdx
  const wchar_t *v14; // rdx
  int v15; // eax
  int v16; // ecx
  __int64 v17; // r9
  const wchar_t *v18; // rdx
  __int64 v19; // r9
  __int64 v20; // r9
  __int64 v21; // r9
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  __int64 v26; // [rsp+20h] [rbp-E0h]
  __int64 v27; // [rsp+28h] [rbp-D8h]
  __int64 v28; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+30h] [rbp-D0h]
  wchar_t FileName[1024]; // [rsp+40h] [rbp-C0h] BYREF

  *Stream = 0;
  v10 = Stream + 1;
  Stream[1] = 0;
  Stream[2] = 0;
  Stream[3] = 0;
  Stream[4] = 0;
  Stream[5] = 0;
  Stream[6] = 0;
  Stream[7] = 0;
  Stream[11] = (FILE *)((3 * a2 * a3) >> 1);
  Stream[8] = 0;
  Stream[9] = 0;
  Stream[10] = 0;
  *((_DWORD *)Stream + 24) = *(_DWORD *)a6;
  *((_DWORD *)Stream + 25) = *((_DWORD *)a6 + 12);
  *((_DWORD *)Stream + 26) = a7;
  *((_DWORD *)Stream + 27) = (a4 + 15) >> 4;
  *((_DWORD *)Stream + 28) = (a5 + 15) >> 4;
  Stream[15] = 0;
  Stream[16] = 0;
  if ( (unsigned int)(*((_DWORD *)a6 + 143) + 64) > 0x400 )
    return Stream;
  if ( *((_DWORD *)a6 + 1) )
  {
    v12 = *((_DWORD *)Stream + 24) == 0;
    FileName[0] = 0;
    v13 = L"%s\\rdp_dec_record_%d_%dx%d_24p.264";
    if ( v12 )
      v13 = L"%s\\rdp_record_%d_%dx%d_24p.264";
    swprintf_s<1024>(FileName, v13, (char *)a6 + 52, *((unsigned int *)Stream + 26), a4, a5);
    if ( _wfopen_s(Stream + 1, FileName, L"w+b") )
      *v10 = 0;
  }
  if ( *((_DWORD *)a6 + 6) )
  {
    if ( !*((_DWORD *)Stream + 24) )
    {
      FileName[0] = 0;
      LODWORD(v27) = a5;
      LODWORD(v26) = a4;
      swprintf_s<1024>(
        FileName,
        L"%s\\rdp_record_%d_%dx%d_24p.ravc",
        (char *)a6 + 52,
        *((unsigned int *)Stream + 26),
        v26,
        v27);
      if ( _wfopen_s(Stream + 2, FileName, L"w+b") )
        Stream[2] = 0;
    }
  }
  if ( *((_DWORD *)a6 + 2) )
  {
    FileName[0] = 0;
    if ( *((_DWORD *)Stream + 24) )
    {
      v14 = L"%s\\rdp_dec_record_%d_%dx%d_24p.yuv";
    }
    else
    {
      if ( *((_DWORD *)Stream + 25) )
      {
        v14 = L"%s\\shaderTest_record_%d_%dx%d_24p.yuv";
        v15 = a2;
        v16 = a3;
        goto LABEL_18;
      }
      v14 = L"%s\\rdp_record_%d_%dx%d_24p.yuv";
    }
    v16 = a5;
    v15 = a4;
LABEL_18:
    LODWORD(v27) = v16;
    LODWORD(v26) = v15;
    swprintf_s<1024>(FileName, v14, (char *)a6 + 52, *((unsigned int *)Stream + 26), v26, v27);
    if ( _wfopen_s(Stream, FileName, L"w+b") )
      *Stream = 0;
  }
  if ( *((_DWORD *)a6 + 4) )
  {
    if ( *((_DWORD *)Stream + 24) )
    {
      v17 = *((unsigned int *)Stream + 26);
      FileName[0] = 0;
      LODWORD(v27) = a5;
      LODWORD(v26) = a4;
      swprintf_s<1024>(FileName, L"%s\\rdp_dec_record_%d_%dx%d_24p.bitstream", (char *)a6 + 52, v17, v26, v27);
      if ( _wfopen_s(Stream + 3, FileName, L"w+b") )
        Stream[3] = 0;
    }
  }
  if ( *((_DWORD *)a6 + 1) || *((_DWORD *)a6 + 5) )
  {
    v12 = *((_DWORD *)Stream + 24) == 0;
    FileName[0] = 0;
    v18 = L"%s\\rdp_dec_record_%d_%dx%d_24p.log";
    if ( v12 )
      v18 = L"%s\\rdp_record_%d_%dx%d_24p.log";
    LODWORD(v27) = a5;
    LODWORD(v26) = a4;
    swprintf_s<1024>(FileName, v18, (char *)a6 + 52, *((unsigned int *)Stream + 26), v26, v27);
    if ( _wfopen_s(Stream + 4, FileName, L"w+b") )
      Stream[4] = 0;
  }
  if ( *((_DWORD *)a6 + 3) )
  {
    if ( !*((_DWORD *)Stream + 24) )
    {
      v19 = *((unsigned int *)Stream + 26);
      FileName[0] = 0;
      LODWORD(v27) = a3;
      LODWORD(v26) = a2;
      swprintf_s<1024>(FileName, L"%s\\rdp_record_%d_%dx%d_24p.rgb", (char *)a6 + 52, v19, v26, v27);
      if ( _wfopen_s(Stream + 5, FileName, L"w+b") )
        Stream[5] = 0;
    }
  }
  if ( *((_DWORD *)a6 + 10) )
  {
    if ( !*((_DWORD *)Stream + 24) )
    {
      v20 = *((unsigned int *)Stream + 26);
      FileName[0] = 0;
      LODWORD(v27) = a5;
      LODWORD(v26) = a4;
      swprintf_s<1024>(FileName, L"%s\\rdp_FM_%d_%dx%d_24p.csv", (char *)a6 + 52, v20, v26, v27);
      if ( _wfopen_s(Stream + 6, FileName, L"w+b") )
        Stream[6] = 0;
    }
  }
  if ( *((_DWORD *)a6 + 11) )
  {
    if ( !*((_DWORD *)Stream + 24) )
    {
      v21 = *((unsigned int *)Stream + 26);
      FileName[0] = 0;
      LODWORD(v27) = a5;
      LODWORD(v26) = a4;
      swprintf_s<1024>(FileName, L"%s\\rdp_QPMap_%d_%dx%d_24p.csv", (char *)a6 + 52, v21, v26, v27);
      if ( _wfopen_s(Stream + 7, FileName, L"w+b") )
        Stream[7] = 0;
    }
  }
  if ( *((_DWORD *)a6 + 7) )
  {
    v22 = (FILE *)operator new(0x800u);
    v29 = a3;
    LODWORD(v27) = a2;
    LODWORD(v26) = *((_DWORD *)Stream + 26);
    Stream[8] = v22;
    swprintf_s(
      (wchar_t *const)v22,
      0x400u,
      L"%s\\h264_record_srcframe_%d_%dx%d_24p.dump",
      (char *)a6 + 52,
      v26,
      v27,
      v29);
  }
  if ( *((_DWORD *)a6 + 8) )
  {
    v23 = (FILE *)operator new(0x800u);
    LODWORD(v28) = a3;
    LODWORD(v27) = a2;
    LODWORD(v26) = *((_DWORD *)Stream + 26);
    Stream[9] = v23;
    swprintf_s(
      (wchar_t *const)v23,
      0x400u,
      L"%s\\h264_record_refframe_%d_%dx%d_24p.dump",
      (char *)a6 + 52,
      v26,
      v27,
      v28);
  }
  if ( *((_DWORD *)a6 + 9) )
  {
    v24 = (FILE *)operator new(0x800u);
    LODWORD(v28) = a3;
    LODWORD(v27) = a2;
    LODWORD(v26) = *((_DWORD *)Stream + 26);
    Stream[10] = v24;
    swprintf_s(
      (wchar_t *const)v24,
      0x400u,
      L"%s\\h264_record_reconframe_%d_%dx%d_24p.dump",
      (char *)a6 + 52,
      v26,
      v27,
      v28);
  }
  return Stream;
}

```

## disassembly

```asm
0x1805beb68  push    rbp
0x1805beb6a  push    rbx
0x1805beb6b  push    rsi
0x1805beb6c  push    rdi
0x1805beb6d  push    r12
0x1805beb6f  push    r13
0x1805beb71  push    r14
0x1805beb73  push    r15
0x1805beb75  lea     rbp, [rsp-758h]
0x1805beb7d  sub     rsp, 858h
0x1805beb84  mov     rax, cs:__security_cookie
0x1805beb8b  xor     rax, rsp
0x1805beb8e  mov     [rbp+790h+var_50], rax
0x1805beb95  mov     rdi, [rbp+790h+arg_28]
0x1805beb9c  mov     rbx, rcx
0x1805beb9f  mov     r14d, [rbp+790h+arg_20]
0x1805beba6  xor     ecx, ecx
0x1805beba8  mov     eax, r8d
0x1805bebab  mov     esi, r9d
0x1805bebae  imul    eax, edx
0x1805bebb1  mov     r12d, r8d
0x1805bebb4  mov     [rbx], rcx
0x1805bebb7  lea     r13, [rbx+8]
0x1805bebbb  mov     [r13+0], rcx
0x1805bebbf  mov     r15d, edx
0x1805bebc2  mov     [rbx+10h], rcx
0x1805bebc6  mov     [rbx+18h], rcx
0x1805bebca  mov     [rbx+20h], rcx
0x1805bebce  mov     [rbx+28h], rcx
0x1805bebd2  mov     [rbx+30h], rcx
0x1805bebd6  lea     eax, [rax+rax*2]
0x1805bebd9  mov     [rbx+38h], rcx
0x1805bebdd  sar     eax, 1
0x1805bebdf  cdqe
0x1805bebe1  mov     [rbx+58h], rax
0x1805bebe5  mov     [rbx+40h], rcx
0x1805bebe9  mov     [rbx+48h], rcx
0x1805bebed  mov     [rbx+50h], rcx
0x1805bebf1  mov     eax, [rdi]
0x1805bebf3  mov     [rbx+60h], eax
0x1805bebf6  mov     eax, [rdi+30h]
0x1805bebf9  mov     [rbx+64h], eax
0x1805bebfc  mov     eax, [rbp+790h+arg_30]
0x1805bec02  mov     [rbx+68h], eax
0x1805bec05  lea     eax, [r9+0Fh]
0x1805bec09  sar     eax, 4
0x1805bec0c  mov     [rbx+6Ch], eax
0x1805bec0f  lea     eax, [r14+0Fh]
0x1805bec13  sar     eax, 4
0x1805bec16  mov     [rbx+70h], eax
0x1805bec19  mov     [rbx+78h], rcx
0x1805bec1d  mov     [rbx+80h], rcx
0x1805bec24  mov     eax, [rdi+23Ch]
0x1805bec2a  add     eax, 40h ; '@'
0x1805bec2d  cmp     eax, 400h
0x1805bec32  ja      loc_1805BEFB8
0x1805bec38  cmp     [rdi+4], ecx
0x1805bec3b  jz      short loc_1805BEC92
0x1805bec3d  cmp     [rbx+60h], ecx
0x1805bec40  lea     rax, aSRdpRecordDDxD_3; "%s\\rdp_record_%d_%dx%d_24p.264"
0x1805bec47  mov     [rsp+890h+FileName], cx
0x1805bec4c  lea     rdx, aSRdpDecRecordD_2; "%s\\rdp_dec_record_%d_%dx%d_24p.264"
0x1805bec53  mov     dword ptr [rsp+890h+var_868], r14d
0x1805bec58  lea     r8, [rdi+34h]
0x1805bec5c  mov     dword ptr [rsp+890h+var_870], r9d
0x1805bec61  lea     rcx, [rsp+890h+FileName]
0x1805bec66  mov     r9d, [rbx+68h]
0x1805bec6a  cmovz   rdx, rax
0x1805bec6e  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bec73  lea     r8, aWB; "w+b"
0x1805bec7a  mov     rcx, r13; Stream
0x1805bec7d  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bec82  call    cs:__imp__wfopen_s
0x1805bec88  xor     ecx, ecx
0x1805bec8a  test    eax, eax
0x1805bec8c  jz      short loc_1805BEC92
0x1805bec8e  mov     [r13+0], rcx
0x1805bec92  cmp     [rdi+18h], ecx
0x1805bec95  jz      short loc_1805BECE3
0x1805bec97  cmp     [rbx+60h], ecx
0x1805bec9a  jnz     short loc_1805BECE3
0x1805bec9c  mov     [rsp+890h+FileName], cx
0x1805beca1  lea     r8, [rdi+34h]
0x1805beca5  mov     r9d, [rbx+68h]
0x1805beca9  lea     rcx, [rsp+890h+FileName]
0x1805becae  mov     dword ptr [rsp+890h+var_868], r14d
0x1805becb3  lea     rdx, aSRdpRecordDDxD_2; "%s\\rdp_record_%d_%dx%d_24p.ravc"
0x1805becba  mov     dword ptr [rsp+890h+var_870], esi
0x1805becbe  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805becc3  lea     r8, aWB; "w+b"
0x1805becca  lea     rdx, [rsp+890h+FileName]; FileName
0x1805beccf  lea     rcx, [rbx+10h]; Stream
0x1805becd3  call    cs:__imp__wfopen_s
0x1805becd9  xor     ecx, ecx
0x1805becdb  test    eax, eax
0x1805becdd  jz      short loc_1805BECE3
0x1805becdf  mov     [rbx+10h], rcx
0x1805bece3  cmp     [rdi+8], ecx
0x1805bece6  jz      short loc_1805BED53
0x1805bece8  lea     r8, [rdi+34h]
0x1805becec  mov     [rsp+890h+FileName], cx
0x1805becf1  cmp     [rbx+60h], ecx
0x1805becf4  jz      short loc_1805BECFF
0x1805becf6  lea     rdx, aSRdpDecRecordD_0; "%s\\rdp_dec_record_%d_%dx%d_24p.yuv"
0x1805becfd  jmp     short loc_1805BED1A
0x1805becff  cmp     [rbx+64h], ecx
0x1805bed02  jz      short loc_1805BED13
0x1805bed04  lea     rdx, aSShadertestRec; "%s\\shaderTest_record_%d_%dx%d_24p.yuv"
0x1805bed0b  mov     eax, r15d
0x1805bed0e  mov     ecx, r12d
0x1805bed11  jmp     short loc_1805BED1F
0x1805bed13  lea     rdx, aSRdpRecordDDxD_0; "%s\\rdp_record_%d_%dx%d_24p.yuv"
0x1805bed1a  mov     ecx, r14d
0x1805bed1d  mov     eax, esi
0x1805bed1f  mov     r9d, [rbx+68h]
0x1805bed23  mov     dword ptr [rsp+890h+var_868], ecx
0x1805bed27  lea     rcx, [rsp+890h+FileName]
0x1805bed2c  mov     dword ptr [rsp+890h+var_870], eax
0x1805bed30  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bed35  lea     r8, aWB; "w+b"
0x1805bed3c  mov     rcx, rbx; Stream
0x1805bed3f  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bed44  call    cs:__imp__wfopen_s
0x1805bed4a  xor     ecx, ecx
0x1805bed4c  test    eax, eax
0x1805bed4e  jz      short loc_1805BED53
0x1805bed50  mov     [rbx], rcx
0x1805bed53  cmp     [rdi+10h], ecx
0x1805bed56  jz      short loc_1805BEDA4
0x1805bed58  cmp     [rbx+60h], ecx
0x1805bed5b  jz      short loc_1805BEDA4
0x1805bed5d  mov     r9d, [rbx+68h]
0x1805bed61  lea     r8, [rdi+34h]
0x1805bed65  mov     [rsp+890h+FileName], cx
0x1805bed6a  lea     rdx, aSRdpDecRecordD; "%s\\rdp_dec_record_%d_%dx%d_24p.bitstre"...
0x1805bed71  lea     rcx, [rsp+890h+FileName]
0x1805bed76  mov     dword ptr [rsp+890h+var_868], r14d
0x1805bed7b  mov     dword ptr [rsp+890h+var_870], esi
0x1805bed7f  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bed84  lea     r8, aWB; "w+b"
0x1805bed8b  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bed90  lea     rcx, [rbx+18h]; Stream
0x1805bed94  call    cs:__imp__wfopen_s
0x1805bed9a  xor     ecx, ecx
0x1805bed9c  test    eax, eax
0x1805bed9e  jz      short loc_1805BEDA4
0x1805beda0  mov     [rbx+18h], rcx
0x1805beda4  cmp     [rdi+4], ecx
0x1805beda7  jnz     short loc_1805BEDAE
0x1805beda9  cmp     [rdi+14h], ecx
0x1805bedac  jz      short loc_1805BEE03
0x1805bedae  cmp     [rbx+60h], ecx
0x1805bedb1  lea     rax, aSRdpRecordDDxD; "%s\\rdp_record_%d_%dx%d_24p.log"
0x1805bedb8  mov     [rsp+890h+FileName], cx
0x1805bedbd  lea     rdx, aSRdpDecRecordD_1; "%s\\rdp_dec_record_%d_%dx%d_24p.log"
0x1805bedc4  mov     r9d, [rbx+68h]
0x1805bedc8  lea     r8, [rdi+34h]
0x1805bedcc  cmovz   rdx, rax
0x1805bedd0  mov     dword ptr [rsp+890h+var_868], r14d
0x1805bedd5  lea     rcx, [rsp+890h+FileName]
0x1805bedda  mov     dword ptr [rsp+890h+var_870], esi
0x1805bedde  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bede3  lea     r8, aWB; "w+b"
0x1805bedea  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bedef  lea     rcx, [rbx+20h]; Stream
0x1805bedf3  call    cs:__imp__wfopen_s
0x1805bedf9  xor     ecx, ecx
0x1805bedfb  test    eax, eax
0x1805bedfd  jz      short loc_1805BEE03
0x1805bedff  mov     [rbx+20h], rcx
0x1805bee03  cmp     [rdi+0Ch], ecx
0x1805bee06  jz      short loc_1805BEE55
0x1805bee08  cmp     [rbx+60h], ecx
0x1805bee0b  jnz     short loc_1805BEE55
0x1805bee0d  mov     r9d, [rbx+68h]
0x1805bee11  lea     r8, [rdi+34h]
0x1805bee15  mov     [rsp+890h+FileName], cx
0x1805bee1a  lea     rdx, aSRdpRecordDDxD_1; "%s\\rdp_record_%d_%dx%d_24p.rgb"
0x1805bee21  lea     rcx, [rsp+890h+FileName]
0x1805bee26  mov     dword ptr [rsp+890h+var_868], r12d
0x1805bee2b  mov     dword ptr [rsp+890h+var_870], r15d
0x1805bee30  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bee35  lea     r8, aWB; "w+b"
0x1805bee3c  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bee41  lea     rcx, [rbx+28h]; Stream
0x1805bee45  call    cs:__imp__wfopen_s
0x1805bee4b  xor     ecx, ecx
0x1805bee4d  test    eax, eax
0x1805bee4f  jz      short loc_1805BEE55
0x1805bee51  mov     [rbx+28h], rcx
0x1805bee55  cmp     [rdi+28h], ecx
0x1805bee58  jz      short loc_1805BEEA6
0x1805bee5a  cmp     [rbx+60h], ecx
0x1805bee5d  jnz     short loc_1805BEEA6
0x1805bee5f  mov     r9d, [rbx+68h]
0x1805bee63  lea     r8, [rdi+34h]
0x1805bee67  mov     [rsp+890h+FileName], cx
0x1805bee6c  lea     rdx, aSRdpFmDDxD24pC; "%s\\rdp_FM_%d_%dx%d_24p.csv"
0x1805bee73  lea     rcx, [rsp+890h+FileName]
0x1805bee78  mov     dword ptr [rsp+890h+var_868], r14d
0x1805bee7d  mov     dword ptr [rsp+890h+var_870], esi
0x1805bee81  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805bee86  lea     r8, aWB; "w+b"
0x1805bee8d  lea     rdx, [rsp+890h+FileName]; FileName
0x1805bee92  lea     rcx, [rbx+30h]; Stream
0x1805bee96  call    cs:__imp__wfopen_s
0x1805bee9c  xor     ecx, ecx
0x1805bee9e  test    eax, eax
0x1805beea0  jz      short loc_1805BEEA6
0x1805beea2  mov     [rbx+30h], rcx
0x1805beea6  cmp     [rdi+2Ch], ecx
0x1805beea9  jz      short loc_1805BEEF7
0x1805beeab  cmp     [rbx+60h], ecx
0x1805beeae  jnz     short loc_1805BEEF7
0x1805beeb0  mov     r9d, [rbx+68h]
0x1805beeb4  lea     r8, [rdi+34h]
0x1805beeb8  mov     [rsp+890h+FileName], cx
0x1805beebd  lea     rdx, aSRdpQpmapDDxD2; "%s\\rdp_QPMap_%d_%dx%d_24p.csv"
0x1805beec4  lea     rcx, [rsp+890h+FileName]
0x1805beec9  mov     dword ptr [rsp+890h+var_868], r14d
0x1805beece  mov     dword ptr [rsp+890h+var_870], esi
0x1805beed2  call    ??$swprintf_s@$0EAA@@@YAHAEAY0EAA@GPEBGZZ; swprintf_s<1024>(ushort (&)[1024],ushort const *,...)
0x1805beed7  lea     r8, aWB; "w+b"
0x1805beede  lea     rdx, [rsp+890h+FileName]; FileName
0x1805beee3  lea     rcx, [rbx+38h]; Stream
0x1805beee7  call    cs:__imp__wfopen_s
0x1805beeed  xor     ecx, ecx
0x1805beeef  test    eax, eax
0x1805beef1  jz      short loc_1805BEEF7
0x1805beef3  mov     [rbx+38h], rcx
0x1805beef7  mov     esi, 800h
0x1805beefc  cmp     [rdi+1Ch], ecx
0x1805beeff  jz      short loc_1805BEF3E
0x1805bef01  mov     ecx, esi; Size
0x1805bef03  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805bef08  mov     ecx, [rbx+68h]
0x1805bef0b  lea     r9, [rdi+34h]
0x1805bef0f  mov     [rsp+890h+var_860], r12d
0x1805bef14  lea     r8, aSH264RecordSrc; "%s\\h264_record_srcframe_%d_%dx%d_24p.d"...
0x1805bef1b  mov     dword ptr [rsp+890h+var_868], r15d
0x1805bef20  mov     r14d, 400h
0x1805bef26  mov     dword ptr [rsp+890h+var_870], ecx
0x1805bef2a  mov     edx, r14d; BufferCount
0x1805bef2d  mov     rcx, rax; Buffer
0x1805bef30  mov     [rbx+40h], rax
0x1805bef34  call    cs:__imp_swprintf_s
0x1805bef3a  xor     ecx, ecx
0x1805bef3c  jmp     short loc_1805BEF44
0x1805bef3e  mov     r14d, 400h
0x1805bef44  cmp     [rdi+20h], ecx
0x1805bef47  jz      short loc_1805BEF7F
0x1805bef49  mov     rcx, rsi; Size
0x1805bef4c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805bef51  mov     edx, [rbx+68h]
0x1805bef54  lea     r9, [rdi+34h]
0x1805bef58  mov     [rsp+890h+var_860], r12d
0x1805bef5d  lea     r8, aSH264RecordRef; "%s\\h264_record_refframe_%d_%dx%d_24p.d"...
0x1805bef64  mov     dword ptr [rsp+890h+var_868], r15d
0x1805bef69  mov     rcx, rax; Buffer
0x1805bef6c  mov     dword ptr [rsp+890h+var_870], edx
0x1805bef70  mov     rdx, r14; BufferCount
0x1805bef73  mov     [rbx+48h], rax
0x1805bef77  call    cs:__imp_swprintf_s
0x1805bef7d  xor     ecx, ecx
0x1805bef7f  cmp     [rdi+24h], ecx
0x1805bef82  jz      short loc_1805BEFB8
0x1805bef84  mov     rcx, rsi; Size
0x1805bef87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1805bef8c  mov     ecx, [rbx+68h]
0x1805bef8f  lea     r9, [rdi+34h]
0x1805bef93  mov     [rsp+890h+var_860], r12d
0x1805bef98  lea     r8, aSH264RecordRec; "%s\\h264_record_reconframe_%d_%dx%d_24p"...
0x1805bef9f  mov     dword ptr [rsp+890h+var_868], r15d
0x1805befa4  mov     rdx, r14; BufferCount
0x1805befa7  mov     dword ptr [rsp+890h+var_870], ecx
0x1805befab  mov     rcx, rax; Buffer
0x1805befae  mov     [rbx+50h], rax
0x1805befb2  call    cs:__imp_swprintf_s
0x1805befb8  mov     rax, rbx
0x1805befbb  mov     rcx, [rbp+790h+var_50]
0x1805befc2  xor     rcx, rsp; StackCookie
0x1805befc5  call    __security_check_cookie
0x1805befca  add     rsp, 858h
0x1805befd1  pop     r15
0x1805befd3  pop     r14
0x1805befd5  pop     r13
0x1805befd7  pop     r12
0x1805befd9  pop     rdi
0x1805befda  pop     rsi
0x1805befdb  pop     rbx
0x1805befdc  pop     rbp
0x1805befdd  retn
```
