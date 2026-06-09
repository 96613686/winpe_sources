# XpressUncompressReader::Read(uchar *,ulong,ulong &)

- ea: `0x140179150`
- end: `0x1401794e2`
- name: `?Read@XpressUncompressReader@@UEAAPEAVFrsStatus@@PEAEKAEAK@Z`
- size: `914`
- prototype: `struct FrsStatus *__fastcall(XpressUncompressReader *__hidden this, unsigned __int8 *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000bbc5`
- `0x140178a44`
- `0x140179150`
- `0x1401794e8`
- `0x1401796d0`
- `0x14017ad68`
- `0x14017ada4`
- `0x1401b9494`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14017934a`
- `KERNEL32!GetCurrentThreadId` at `0x140179383`
- `KERNEL32!GetCurrentThreadId` at `0x1401793b7`
- `KERNEL32!GetCurrentThreadId` at `0x1401793ed`
- `KERNEL32!GetCurrentThreadId` at `0x14017943f`
- `KERNEL32!GetCurrentThreadId` at `0x140179494`
- `KERNEL32!GetCurrentThreadId` at `0x14017934a`
- `KERNEL32!GetCurrentThreadId` at `0x140179383`
- `KERNEL32!GetCurrentThreadId` at `0x1401793b7`
- `KERNEL32!GetCurrentThreadId` at `0x1401793ed`
- `KERNEL32!GetCurrentThreadId` at `0x14017943f`
- `KERNEL32!GetCurrentThreadId` at `0x140179494`

## string_xrefs

- `0x14017916f`: `XpressUncompressReader::Read`
- `0x14017940a`: `XpressUncompressReader::Read`
- `0x14017945e`: `XpressUncompressReader::Read`
- `0x14017947a`: `XpressUncompressReader::Read`

## pseudocode

```c
struct FrsStatus *__fastcall XpressUncompressReader::Read(
        XpressUncompressReader *this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v4; // rbx
  bool v5; // zf
  unsigned int v7; // r14d
  struct FrsStatus *FileHeader; // rsi
  __int64 v10; // rcx
  _DWORD *v11; // r15
  __int64 v12; // r14
  __int64 v13; // xmm0_8
  unsigned int v14; // rdx^4
  _DWORD *v15; // r13
  __int64 v16; // rdx
  unsigned int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  DWORD v24; // eax
  __int64 v25; // rcx
  DWORD v27; // [rsp+38h] [rbp-40h]
  DWORD v28; // [rsp+38h] [rbp-40h]
  DWORD v29; // [rsp+38h] [rbp-40h]
  DWORD CurrentThreadId; // [rsp+38h] [rbp-40h]
  DWORD v31; // [rsp+38h] [rbp-40h]
  unsigned int v32; // [rsp+50h] [rbp-28h]
  unsigned int v33[2]; // [rsp+58h] [rbp-20h] BYREF
  int v34; // [rsp+60h] [rbp-18h]
  unsigned int v35; // [rsp+C0h] [rbp+48h] BYREF
  unsigned __int8 *v36; // [rsp+C8h] [rbp+50h]
  unsigned int v37; // [rsp+D0h] [rbp+58h]
  unsigned int v38; // [rsp+D8h] [rbp+60h] BYREF

  v37 = a3;
  v36 = a2;
  v4 = 0;
  *a4 = 0;
  v5 = *((_DWORD *)this + 9263) == 1;
  v7 = a3;
  v38 = 0;
  v35 = 0;
  FileHeader = 0;
  if ( !v5 )
  {
    FileHeader = XpressUncompressReader::InitForRead(this);
    if ( FileHeader )
      goto LABEL_33;
  }
  if ( !*((_DWORD *)this + 9270) )
  {
    FileHeader = XpressUncompressReader::ReadFileHeader(this);
    if ( FileHeader )
      goto LABEL_33;
  }
  if ( !*((_DWORD *)this + 9260) )
  {
    v10 = 0;
    v11 = (_DWORD *)((char *)this + 8236);
    v32 = 0;
    while ( 1 )
    {
      if ( (unsigned int)v10 >= v7 )
        goto LABEL_32;
      v12 = *((unsigned int *)this + 2060);
      if ( (_DWORD)v12 )
      {
        v15 = (_DWORD *)((char *)this + 8236);
      }
      else
      {
        *((_QWORD *)this + 4620) += (unsigned int)*v11;
        FileHeader = XpressReader::ReadAhead(this, 0xCu, &v38, &v35);
        if ( FileHeader )
          goto LABEL_33;
        if ( !v35 )
          goto LABEL_26;
        if ( v35 != 12 )
        {
          if ( !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 4627) + 24LL))(*((_QWORD *)this + 4627)) )
          {
            CurrentThreadId = GetCurrentThreadId();
            v19 = FrsStatusList::PushNewError(
                    v22,
                    9048,
                    0,
                    3,
                    "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                    "XpressUncompressReader::Read",
                    1300,
                    CurrentThreadId,
                    0);
            goto LABEL_30;
          }
LABEL_26:
          *((_DWORD *)this + 9260) = 1;
          return (struct FrsStatus *)v4;
        }
        v13 = *(_QWORD *)((char *)this + v38 + 8244);
        v12 = *(unsigned int *)((char *)this + v38 + 8252);
        *(_QWORD *)v33 = v13;
        v34 = v12;
        if ( !(unsigned int)XpressIsValidBlockHeaderUnaligned((struct FRS_XPRESS_BLOCK_HEADER *)v33) )
        {
          v29 = GetCurrentThreadId();
          v19 = FrsStatusList::PushNewError(
                  v21,
                  9048,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                  "XpressUncompressReader::Read",
                  1310,
                  v29,
                  0);
          goto LABEL_30;
        }
        v14 = v33[1];
        *((_QWORD *)this + 4636) = v13;
        *((_DWORD *)this + 9274) = v12;
        FileHeader = XpressReader::ReadAhead(this, v14, &v38, &v35);
        if ( FileHeader )
          goto LABEL_33;
        if ( v35 != v33[1] )
        {
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 4627) + 24LL))(*((_QWORD *)this + 4627)) )
          {
            *((_DWORD *)this + 2059) = 0;
            goto LABEL_26;
          }
          v28 = GetCurrentThreadId();
          v19 = FrsStatusList::PushNewError(
                  v20,
                  9048,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                  "XpressUncompressReader::Read",
                  1347,
                  v28,
                  0);
LABEL_30:
          FileHeader = (struct FrsStatus *)v19;
LABEL_32:
          if ( FileHeader )
          {
LABEL_33:
            *((_QWORD *)this + 4104) = 0;
            *(_QWORD *)((char *)this + 8236) = 0;
            v24 = GetCurrentThreadId();
            return (struct FrsStatus *)FrsStatusList::PushNewError(
                                         v25,
                                         *((unsigned int *)FileHeader + 1),
                                         *((unsigned int *)FileHeader + 2),
                                         *(unsigned int *)FileHeader,
                                         "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                                         "XpressUncompressReader::Read",
                                         1393,
                                         v24,
                                         FileHeader);
          }
          return (struct FrsStatus *)v4;
        }
        if ( !XpressUncompressBlock(
                *((struct UNNAMED_STRUCT_XpressDecodeStream **)this + 2),
                (unsigned __int8 *)this + v38 + 8244,
                v33[1],
                (unsigned __int8 *)this + 28,
                v12,
                (XpressUncompressReader *)((char *)this + 36968)) )
        {
          v27 = GetCurrentThreadId();
          v19 = FrsStatusList::PushNewError(
                  v18,
                  9048,
                  0,
                  3,
                  "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                  "XpressUncompressReader::Read",
                  1339,
                  v27,
                  0);
          goto LABEL_30;
        }
        v10 = v32;
        v15 = (_DWORD *)((char *)this + 8236);
        *v11 = 0;
        *((_DWORD *)this + 2060) = v12;
      }
      if ( (unsigned int)v12 >= v37 - (unsigned int)v10 )
        v12 = v37 - (unsigned int)v10;
      v16 = (unsigned int)*v11 + 28LL;
      v35 = v12;
      memcpy_0(&v36[v10], (char *)this + v16, (unsigned int)v12);
      *v15 += v12;
      *((_DWORD *)this + 2060) -= v12;
      v10 = (unsigned int)v12 + v32;
      v32 += v12;
      v17 = v12 + *a4;
      if ( v17 < *a4 )
      {
        *a4 = -1;
        v31 = GetCurrentThreadId();
        v19 = FrsStatusList::PushNewError(
                v23,
                9048,
                0,
                3,
                "base\\fs\\remotefs\\frs\\src\\sync\\xpressstreams.cpp",
                "XpressUncompressReader::Read",
                1377,
                v31,
                0);
        goto LABEL_30;
      }
      *a4 = v17;
      *((_QWORD *)this + 4629) += v12;
      v7 = v37;
    }
  }
  return (struct FrsStatus *)v4;
}

```

## disassembly

```asm
0x140179150  mov     [rsp-40h+arg_10], r8d
0x140179155  mov     [rsp-40h+arg_8], rdx
0x14017915a  push    rbp
0x14017915b  push    rbx
0x14017915c  push    rsi
0x14017915d  push    rdi
0x14017915e  push    r12
0x140179160  push    r13
0x140179162  push    r14
0x140179164  push    r15
0x140179166  mov     rbp, rsp
0x140179169  sub     rsp, 78h
0x14017916d  xor     ebx, ebx
0x14017916f  lea     r13, aXpressuncompre_10; "XpressUncompressReader::Read"
0x140179176  mov     [r9], ebx
0x140179179  lea     r15, aBaseFsRemotefs_43; "base\\fs\\remotefs\\frs\\src\\sync\\xpr"...
0x140179180  cmp     dword ptr [rcx+90BCh], 1
0x140179187  mov     r12, r9
0x14017918a  mov     r14d, r8d
0x14017918d  mov     [rbp+arg_18], ebx
0x140179190  mov     rdi, rcx
0x140179193  mov     [rbp+arg_0], ebx
0x140179196  mov     esi, ebx
0x140179198  jz      short loc_1401791AB
0x14017919a  call    ?InitForRead@XpressUncompressReader@@IEAAPEAVFrsStatus@@XZ; XpressUncompressReader::InitForRead(void)
0x14017919f  mov     rsi, rax
0x1401791a2  test    rax, rax
0x1401791a5  jnz     loc_140179481
0x1401791ab  cmp     [rdi+90D8h], ebx
0x1401791b1  jnz     short loc_1401791C7
0x1401791b3  mov     rcx, rdi; this
0x1401791b6  call    ?ReadFileHeader@XpressUncompressReader@@IEAAPEAVFrsStatus@@XZ; XpressUncompressReader::ReadFileHeader(void)
0x1401791bb  mov     rsi, rax
0x1401791be  test    rax, rax
0x1401791c1  jnz     loc_140179481
0x1401791c7  cmp     [rdi+90B0h], ebx
0x1401791cd  jnz     loc_1401794CD
0x1401791d3  mov     ecx, ebx
0x1401791d5  lea     r15, [rdi+202Ch]
0x1401791dc  mov     [rbp+var_28], ecx
0x1401791df  cmp     ecx, r14d
0x1401791e2  jnb     loc_14017945E
0x1401791e8  mov     r14d, [rdi+2030h]
0x1401791ef  test    r14d, r14d
0x1401791f2  jnz     loc_1401792E9
0x1401791f8  mov     eax, [r15]
0x1401791fb  lea     r9, [rbp+arg_0]; unsigned int *
0x1401791ff  add     [rdi+9060h], rax
0x140179206  lea     r8, [rbp+arg_18]; unsigned int *
0x14017920a  lea     edx, [r14+0Ch]; unsigned int
0x14017920e  mov     rcx, rdi; this
0x140179211  call    ?ReadAhead@XpressReader@@IEAAPEAVFrsStatus@@KAEAK0@Z; XpressReader::ReadAhead(ulong,ulong &,ulong &)
0x140179216  mov     rsi, rax
0x140179219  test    rax, rax
0x14017921c  jnz     loc_140179473
0x140179222  cmp     [rbp+arg_0], ebx
0x140179225  jz      loc_1401793A8
0x14017922b  cmp     [rbp+arg_0], 0Ch
0x14017922f  jnz     loc_1401793D6
0x140179235  mov     eax, [rbp+arg_18]
0x140179238  lea     rcx, [rbp+var_20]; struct FRS_XPRESS_BLOCK_HEADER *
0x14017923c  movsd   xmm0, qword ptr [rax+rdi+2034h]
0x140179245  mov     r14d, [rax+rdi+203Ch]
0x14017924d  movsd   qword ptr [rbp+var_20], xmm0
0x140179252  mov     [rbp+var_18], r14d
0x140179256  call    ?XpressIsValidBlockHeaderUnaligned@@YAHPEFAUFRS_XPRESS_BLOCK_HEADER@@@Z; XpressIsValidBlockHeaderUnaligned(FRS_XPRESS_BLOCK_HEADER *)
0x14017925b  test    eax, eax
0x14017925d  jz      loc_1401793B7
0x140179263  mov     rdx, qword ptr [rbp+var_20]
0x140179267  lea     r9, [rbp+arg_0]; unsigned int *
0x14017926b  movsd   qword ptr [rdi+90E0h], xmm0
0x140179273  lea     r8, [rbp+arg_18]; unsigned int *
0x140179277  shr     rdx, 20h; unsigned int
0x14017927b  mov     rcx, rdi; this
0x14017927e  mov     [rdi+90E8h], r14d
0x140179285  call    ?ReadAhead@XpressReader@@IEAAPEAVFrsStatus@@KAEAK0@Z; XpressReader::ReadAhead(ulong,ulong &,ulong &)
0x14017928a  mov     rsi, rax
0x14017928d  test    rax, rax
0x140179290  jnz     loc_140179473
0x140179296  mov     r8d, [rbp+var_20+4]; unsigned int
0x14017929a  cmp     [rbp+arg_0], r8d
0x14017929e  jnz     loc_14017936C
0x1401792a4  mov     edx, [rbp+arg_18]
0x1401792a7  lea     rcx, [rdi+9068h]
0x1401792ae  mov     [rsp+78h+var_50], rcx; struct FRS_XPRESS_STAT *
0x1401792b3  lea     r9, [rdi+1Ch]; unsigned __int8 *
0x1401792b7  mov     rcx, [rdi+10h]; struct UNNAMED_STRUCT_XpressDecodeStream *
0x1401792bb  add     rdx, 2034h
0x1401792c2  add     rdx, rdi; unsigned __int8 *
0x1401792c5  mov     [rsp+78h+var_58], r14d; unsigned int
0x1401792ca  call    ?XpressUncompressBlock@@YAHPEAUUNNAMED_STRUCT_XpressDecodeStream@@PEAEK1KPEAUFRS_XPRESS_STAT@@@Z; XpressUncompressBlock(UNNAMED_STRUCT_XpressDecodeStream *,uchar *,ulong,uchar *,ulong,FRS_XPRESS_STAT *)
0x1401792cf  test    eax, eax
0x1401792d1  jz      short loc_14017934A
0x1401792d3  mov     ecx, [rbp+var_28]
0x1401792d6  lea     r13, [rdi+202Ch]
0x1401792dd  mov     [r15], ebx
0x1401792e0  mov     [rdi+2030h], r14d
0x1401792e7  jmp     short loc_1401792EC
0x1401792e9  mov     r13, r15
0x1401792ec  mov     eax, [rbp+arg_10]
0x1401792ef  mov     edx, [r15]
0x1401792f2  sub     eax, ecx
0x1401792f4  cmp     r14d, eax
0x1401792f7  cmovnb  r14d, eax
0x1401792fb  add     rcx, [rbp+arg_8]; void *
0x1401792ff  add     rdx, 1Ch
0x140179303  mov     [rbp+arg_0], r14d
0x140179307  add     rdx, rdi; Src
0x14017930a  mov     r8d, r14d; Size
0x14017930d  call    memcpy_0
0x140179312  add     [r13+0], r14d
0x140179316  sub     [rdi+2030h], r14d
0x14017931d  mov     eax, [r12]
0x140179321  mov     ecx, [rbp+var_28]
0x140179324  add     ecx, r14d
0x140179327  mov     [rbp+var_28], ecx
0x14017932a  lea     edx, [r14+rax]
0x14017932e  cmp     edx, eax
0x140179330  jb      loc_14017943A
0x140179336  mov     [r12], edx
0x14017933a  add     [rdi+90A8h], r14
0x140179341  mov     r14d, [rbp+arg_10]
0x140179345  jmp     loc_1401791DF
0x14017934a  call    cs:__imp_GetCurrentThreadId
0x140179351  nop     dword ptr [rax+rax+00h]
0x140179356  mov     [rsp+78h+var_38], rbx
0x14017935b  mov     [rsp+78h+var_40], eax
0x14017935f  mov     [rsp+78h+var_48], 53Bh
0x140179367  jmp     loc_14017940A
0x14017936c  mov     rcx, [rdi+9098h]
0x140179373  mov     rax, [rcx]
0x140179376  mov     rax, [rax+18h]
0x14017937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14017937f  test    eax, eax
0x140179381  jnz     short loc_1401793A2
0x140179383  call    cs:__imp_GetCurrentThreadId
0x14017938a  nop     dword ptr [rax+rax+00h]
0x14017938f  mov     [rsp+78h+var_38], rbx
0x140179394  mov     [rsp+78h+var_40], eax
0x140179398  mov     [rsp+78h+var_48], 543h
0x1401793a0  jmp     short loc_14017940A
0x1401793a2  mov     [rdi+202Ch], ebx
0x1401793a8  mov     dword ptr [rdi+90B0h], 1
0x1401793b2  jmp     loc_1401794CD
0x1401793b7  call    cs:__imp_GetCurrentThreadId
0x1401793be  nop     dword ptr [rax+rax+00h]
0x1401793c3  mov     [rsp+78h+var_38], rbx
0x1401793c8  mov     [rsp+78h+var_40], eax
0x1401793cc  mov     [rsp+78h+var_48], 51Eh
0x1401793d4  jmp     short loc_14017940A
0x1401793d6  mov     rcx, [rdi+9098h]
0x1401793dd  mov     rax, [rcx]
0x1401793e0  mov     rax, [rax+18h]
0x1401793e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401793e9  test    eax, eax
0x1401793eb  jnz     short loc_1401793A8
0x1401793ed  call    cs:__imp_GetCurrentThreadId
0x1401793f4  nop     dword ptr [rax+rax+00h]
0x1401793f9  mov     [rsp+78h+var_38], rbx
0x1401793fe  mov     [rsp+78h+var_40], eax
0x140179402  mov     [rsp+78h+var_48], 514h
0x14017940a  lea     r13, aXpressuncompre_10; "XpressUncompressReader::Read"
0x140179411  mov     r9d, 3
0x140179417  lea     r15, aBaseFsRemotefs_43; "base\\fs\\remotefs\\frs\\src\\sync\\xpr"...
0x14017941e  mov     [rsp+78h+var_50], r13
0x140179423  xor     r8d, r8d
0x140179426  mov     qword ptr [rsp+78h+var_58], r15
0x14017942b  mov     edx, 2358h
0x140179430  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140179435  mov     rsi, rax
0x140179438  jmp     short loc_14017946C
0x14017943a  or      dword ptr [r12], 0FFFFFFFFh
0x14017943f  call    cs:__imp_GetCurrentThreadId
0x140179446  nop     dword ptr [rax+rax+00h]
0x14017944b  mov     [rsp+78h+var_38], rbx
0x140179450  mov     [rsp+78h+var_40], eax
0x140179454  mov     [rsp+78h+var_48], 561h
0x14017945c  jmp     short loc_14017940A
0x14017945e  lea     r13, aXpressuncompre_10; "XpressUncompressReader::Read"
0x140179465  lea     r15, aBaseFsRemotefs_43; "base\\fs\\remotefs\\frs\\src\\sync\\xpr"...
0x14017946c  test    rsi, rsi
0x14017946f  jz      short loc_1401794CD
0x140179471  jmp     short loc_140179481
0x140179473  lea     r15, aBaseFsRemotefs_43; "base\\fs\\remotefs\\frs\\src\\sync\\xpr"...
0x14017947a  lea     r13, aXpressuncompre_10; "XpressUncompressReader::Read"
0x140179481  mov     [rdi+8040h], rbx
0x140179488  mov     [rdi+202Ch], rbx
0x14017948f  test    rsi, rsi
0x140179492  jz      short loc_1401794CD
0x140179494  call    cs:__imp_GetCurrentThreadId
0x14017949b  nop     dword ptr [rax+rax+00h]
0x1401794a0  mov     r9d, [rsi]
0x1401794a3  mov     r8d, [rsi+8]
0x1401794a7  mov     edx, [rsi+4]
0x1401794aa  mov     [rsp+78h+var_38], rsi
0x1401794af  mov     [rsp+78h+var_40], eax
0x1401794b3  mov     [rsp+78h+var_48], 571h
0x1401794bb  mov     [rsp+78h+var_50], r13
0x1401794c0  mov     qword ptr [rsp+78h+var_58], r15
0x1401794c5  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401794ca  mov     rbx, rax
0x1401794cd  mov     rax, rbx
0x1401794d0  add     rsp, 78h
0x1401794d4  pop     r15
0x1401794d6  pop     r14
0x1401794d8  pop     r13
0x1401794da  pop     r12
0x1401794dc  pop     rdi
0x1401794dd  pop     rsi
0x1401794de  pop     rbx
0x1401794df  pop     rbp
0x1401794e0  retn
```
