# TlmiLogHydrationPerformance

- ea: `0x18001a308`
- end: `0x18001a68b`
- name: `TlmiLogHydrationPerformance`
- size: `899`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012c28`
- `0x180018564`

## callees

- `0x180001aa0`
- `0x18001a308`
- `0x18001ca5c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a362`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001a362`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001a37a`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x18001a37a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3f6`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3b0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001a3f6`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18001a392`
- `ntdll!RtlNumberGenericTableElementsAvl` at `0x18001a392`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001a3dd`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x18001a3dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a409`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001a409`

## pseudocode

```c
ULONG __fastcall TlmiLogHydrationPerformance(
        int a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int a8)
{
  int v8; // r14d
  ULONG result; // eax
  __int64 v14; // r15
  __int64 v15; // r12
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // edx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int8 NewElement[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  __int64 Buffer; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  __int64 v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h] BYREF
  __int64 v35; // [rsp+98h] [rbp-68h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v37; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v38; // [rsp+D0h] [rbp-30h]
  __int64 v39; // [rsp+D8h] [rbp-28h]
  __int64 *v40; // [rsp+E0h] [rbp-20h]
  __int64 v41; // [rsp+E8h] [rbp-18h]
  __int64 *v42; // [rsp+F0h] [rbp-10h]
  __int64 v43; // [rsp+F8h] [rbp-8h]
  __int64 *v44; // [rsp+100h] [rbp+0h]
  __int64 v45; // [rsp+108h] [rbp+8h]
  __int64 *v46; // [rsp+110h] [rbp+10h]
  __int64 v47; // [rsp+118h] [rbp+18h]
  __int64 *v48; // [rsp+120h] [rbp+20h]
  __int64 v49; // [rsp+128h] [rbp+28h]
  __int64 *v50; // [rsp+130h] [rbp+30h]
  __int64 v51; // [rsp+138h] [rbp+38h]
  __int64 *v52; // [rsp+140h] [rbp+40h]
  __int64 v53; // [rsp+148h] [rbp+48h]
  __int64 *v54; // [rsp+150h] [rbp+50h]
  __int64 v55; // [rsp+158h] [rbp+58h]
  const WCHAR *v56; // [rsp+160h] [rbp+60h]
  int v57; // [rsp+168h] [rbp+68h]
  int v58; // [rsp+16Ch] [rbp+6Ch]
  const WCHAR *v59; // [rsp+170h] [rbp+70h]
  int v60; // [rsp+178h] [rbp+78h]
  int v61; // [rsp+17Ch] [rbp+7Ch]
  __int64 *v62; // [rsp+180h] [rbp+80h]
  __int64 v63; // [rsp+188h] [rbp+88h]
  __int64 *v64; // [rsp+190h] [rbp+90h]
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 *v66; // [rsp+1A0h] [rbp+A0h]
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  int *v68; // [rsp+1B0h] [rbp+B0h]
  __int64 v69; // [rsp+1B8h] [rbp+B8h]
  __int64 *v70; // [rsp+1C0h] [rbp+C0h]
  __int64 v71; // [rsp+1C8h] [rbp+C8h]

  v8 = 0;
  Buffer = a4;
  if ( a7 != -2147023899 )
    v8 = a7;
  RtlAcquireSRWLockExclusive(&qword_18002AA60);
  if ( !RtlLookupElementGenericTableAvl(qword_18002AA68, &Buffer) )
  {
    if ( RtlNumberGenericTableElementsAvl(qword_18002AA68) > 0x32 )
    {
      ++dword_18002AB40;
      return RtlReleaseSRWLockExclusive(&qword_18002AA60);
    }
    NewElement[0] = 0;
    RtlInsertElementGenericTableAvl(qword_18002AA68, &Buffer, 8u, NewElement);
  }
  v14 = 0;
  v15 = 0;
  RtlReleaseSRWLockExclusive(&qword_18002AA60);
  SetEvent(hEvent);
  if ( a1 )
  {
    v16 = a5;
  }
  else
  {
    v16 = 0;
    if ( v8 < 0 )
      v15 = a5;
    else
      v14 = a5;
  }
  result = dword_18002A1A0;
  if ( (unsigned int)dword_18002A1A0 > 5 )
  {
    result = qword_18002A1B0;
    if ( (qword_18002A1B0 & 0x400000000000LL) != 0 )
    {
      result = 0;
      if ( (qword_18002A1B8 & 0x400000000000LL) == qword_18002A1B8 )
      {
        v24 = 1;
        v38 = &v24;
        v25 = a6;
        v26 = a6;
        v42 = &v26;
        v44 = &v27;
        v46 = &v28;
        v48 = &v29;
        v50 = &v30;
        v31 = v8;
        v52 = &v31;
        v32 = a8;
        v54 = &v32;
        v17 = -1;
        v40 = &v25;
        v18 = 2;
        v39 = 8;
        v41 = 8;
        v43 = 8;
        v27 = v16;
        v45 = 8;
        v28 = v14;
        v47 = 8;
        v29 = v15;
        v49 = 8;
        v30 = a5;
        v51 = 8;
        v53 = 8;
        v55 = 8;
        if ( a2 )
        {
          v19 = -1;
          do
            ++v19;
          while ( a2[v19] );
          v20 = (unsigned int)(2 * v19 + 2);
        }
        else
        {
          a2 = &SourceString;
          v20 = 2;
        }
        v56 = a2;
        v57 = v20;
        v58 = 0;
        if ( a3 )
        {
          do
            ++v17;
          while ( a3[v17] );
          v18 = 2 * v17 + 2;
        }
        else
        {
          a3 = &SourceString;
        }
        v60 = v18;
        v62 = &v33;
        v34 = (unsigned int)dword_18002AB78;
        v64 = &v34;
        v35 = qword_18002AB70;
        v66 = &v35;
        v22 = dword_18002AB7C;
        v68 = &v22;
        v70 = &v36;
        v61 = 0;
        v59 = a3;
        v33 = a4;
        v63 = 8;
        v65 = 8;
        v67 = 8;
        v69 = 4;
        v36 = 0x1000000;
        v71 = 8;
        return tlgWriteAgg(v20, (unsigned __int8 *)&word_180023D86, v16, 0x12u, &v37);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001a308  push    rbp
0x18001a30a  push    rbx
0x18001a30b  push    rsi
0x18001a30c  push    rdi
0x18001a30d  push    r12
0x18001a30f  push    r13
0x18001a311  push    r14
0x18001a313  push    r15
0x18001a315  lea     rbp, [rsp-0E8h]
0x18001a31d  sub     rsp, 1E8h
0x18001a324  mov     rax, cs:__security_cookie
0x18001a32b  xor     rax, rsp
0x18001a32e  mov     [rbp+120h+var_50], rax
0x18001a335  xor     r14d, r14d
0x18001a338  mov     rbx, r9
0x18001a33b  cmp     [rbp+120h+arg_30], 800703E5h
0x18001a345  mov     r13d, ecx
0x18001a348  lea     rcx, qword_18002AA60
0x18001a34f  mov     [rsp+220h+Buffer], rbx
0x18001a354  cmovnz  r14d, [rbp+120h+arg_30]
0x18001a35c  mov     rdi, r8
0x18001a35f  mov     rsi, rdx
0x18001a362  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001a369  nop     dword ptr [rax+rax+00h]
0x18001a36e  mov     rcx, cs:qword_18002AA68; Table
0x18001a375  lea     rdx, [rsp+220h+Buffer]; Buffer
0x18001a37a  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18001a381  nop     dword ptr [rax+rax+00h]
0x18001a386  test    rax, rax
0x18001a389  jnz     short loc_18001A3E9
0x18001a38b  mov     rcx, cs:qword_18002AA68; Table
0x18001a392  call    cs:__imp_RtlNumberGenericTableElementsAvl
0x18001a399  nop     dword ptr [rax+rax+00h]
0x18001a39e  cmp     eax, 32h ; '2'
0x18001a3a1  jbe     short loc_18001A3C1
0x18001a3a3  inc     cs:dword_18002AB40
0x18001a3a9  lea     rcx, qword_18002AA60
0x18001a3b0  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a3b7  nop     dword ptr [rax+rax+00h]
0x18001a3bc  jmp     loc_18001A667
0x18001a3c1  mov     rcx, cs:qword_18002AA68; Table
0x18001a3c8  lea     r9, [rsp+220h+NewElement]; NewElement
0x18001a3cd  mov     r8d, 8; BufferSize
0x18001a3d3  mov     [rsp+220h+NewElement], 0
0x18001a3d8  lea     rdx, [rsp+220h+Buffer]; Buffer
0x18001a3dd  call    cs:__imp_RtlInsertElementGenericTableAvl
0x18001a3e4  nop     dword ptr [rax+rax+00h]
0x18001a3e9  lea     rcx, qword_18002AA60
0x18001a3f0  xor     r15d, r15d
0x18001a3f3  xor     r12d, r12d
0x18001a3f6  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001a3fd  nop     dword ptr [rax+rax+00h]
0x18001a402  mov     rcx, cs:hEvent; hEvent
0x18001a409  call    cs:__imp_SetEvent
0x18001a410  nop     dword ptr [rax+rax+00h]
0x18001a415  mov     rcx, [rbp+120h+arg_20]
0x18001a41c  xor     r9d, r9d
0x18001a41f  test    r13d, r13d
0x18001a422  jz      short loc_18001A429
0x18001a424  mov     r8, rcx
0x18001a427  jmp     short loc_18001A439
0x18001a429  mov     r8, r9
0x18001a42c  test    r14d, r14d
0x18001a42f  js      short loc_18001A436
0x18001a431  mov     r15, rcx
0x18001a434  jmp     short loc_18001A439
0x18001a436  mov     r12, rcx
0x18001a439  mov     eax, cs:dword_18002A1A0
0x18001a43f  cmp     eax, 5
0x18001a442  jbe     loc_18001A667
0x18001a448  mov     rdx, cs:qword_18002A1B8
0x18001a44f  mov     r10, 400000000000h
0x18001a459  mov     rax, cs:qword_18002A1B0
0x18001a460  test    r10, rax
0x18001a463  jz      loc_18001A667
0x18001a469  mov     rax, rdx
0x18001a46c  and     rax, r10
0x18001a46f  cmp     rax, rdx
0x18001a472  jnz     loc_18001A667
0x18001a478  lea     rax, [rsp+220h+var_1E0]
0x18001a47d  mov     [rsp+220h+var_1E0], 1
0x18001a486  mov     [rbp+120h+var_150], rax
0x18001a48a  lea     rdx, [rsp+220h+var_1D8]
0x18001a48f  mov     rax, [rbp+120h+arg_28]
0x18001a496  mov     [rsp+220h+var_1D8], rax
0x18001a49b  mov     [rsp+220h+var_1D0], rax
0x18001a4a0  lea     rax, [rsp+220h+var_1D0]
0x18001a4a5  mov     [rbp+120h+var_130], rax
0x18001a4a9  lea     rax, [rsp+220h+var_1C8]
0x18001a4ae  mov     [rbp+120h+var_120], rax
0x18001a4b2  lea     rax, [rsp+220h+var_1C0]
0x18001a4b7  mov     [rbp+120h+var_110], rax
0x18001a4bb  lea     rax, [rsp+220h+var_1B8]
0x18001a4c0  mov     [rbp+120h+var_100], rax
0x18001a4c4  lea     rax, [rsp+220h+var_1B0]
0x18001a4c9  mov     [rbp+120h+var_F0], rax
0x18001a4cd  movsxd  rax, r14d
0x18001a4d0  mov     [rsp+220h+var_1A8], rax
0x18001a4d5  lea     rax, [rsp+220h+var_1A8]
0x18001a4da  mov     [rbp+120h+var_E0], rax
0x18001a4de  mov     eax, [rbp+120h+arg_38]
0x18001a4e4  mov     [rbp+120h+var_1A0], rax
0x18001a4e8  lea     rax, [rbp+120h+var_1A0]
0x18001a4ec  mov     [rbp+120h+var_D0], rax
0x18001a4f0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a4f4  mov     [rbp+120h+var_140], rdx
0x18001a4f8  mov     edx, 2
0x18001a4fd  mov     [rbp+120h+var_148], 8
0x18001a505  mov     [rbp+120h+var_138], 8
0x18001a50d  mov     [rbp+120h+var_128], 8
0x18001a515  mov     [rsp+220h+var_1C8], r8
0x18001a51a  mov     [rbp+120h+var_118], 8
0x18001a522  mov     [rsp+220h+var_1C0], r15
0x18001a527  mov     [rbp+120h+var_108], 8
0x18001a52f  mov     [rsp+220h+var_1B8], r12
0x18001a534  mov     [rbp+120h+var_F8], 8
0x18001a53c  mov     [rsp+220h+var_1B0], rcx
0x18001a541  mov     [rbp+120h+var_E8], 8
0x18001a549  mov     [rbp+120h+var_D8], 8
0x18001a551  mov     [rbp+120h+var_C8], 8
0x18001a559  test    rsi, rsi
0x18001a55c  jz      short loc_18001A574
0x18001a55e  mov     rcx, rax
0x18001a561  inc     rcx
0x18001a564  cmp     [rsi+rcx*2], r9w
0x18001a569  jnz     short loc_18001A561
0x18001a56b  lea     ecx, ds:2[rcx*2]
0x18001a572  jmp     short loc_18001A57D
0x18001a574  lea     rsi, SourceString
0x18001a57b  mov     ecx, edx
0x18001a57d  mov     [rbp+120h+var_C0], rsi
0x18001a581  mov     [rbp+120h+var_B8], ecx
0x18001a584  mov     [rbp+120h+var_B4], r9d
0x18001a588  test    rdi, rdi
0x18001a58b  jz      short loc_18001A5A0
0x18001a58d  inc     rax
0x18001a590  cmp     [rdi+rax*2], r9w
0x18001a595  jnz     short loc_18001A58D
0x18001a597  lea     edx, ds:2[rax*2]
0x18001a59e  jmp     short loc_18001A5A7
0x18001a5a0  lea     rdi, SourceString
0x18001a5a7  lea     rax, [rbp+120h+var_198]
0x18001a5ab  mov     [rbp+120h+var_A8], edx
0x18001a5ae  mov     [rbp+120h+var_A0], rax
0x18001a5b5  lea     rdx, word_180023D86
0x18001a5bc  mov     eax, cs:dword_18002AB78
0x18001a5c2  mov     [rbp+120h+var_190], rax
0x18001a5c6  lea     rax, [rbp+120h+var_190]
0x18001a5ca  mov     [rbp+120h+var_90], rax
0x18001a5d1  mov     rax, cs:qword_18002AB70
0x18001a5d8  mov     [rbp+120h+var_188], rax
0x18001a5dc  lea     rax, [rbp+120h+var_188]
0x18001a5e0  mov     [rbp+120h+var_80], rax
0x18001a5e7  mov     eax, cs:dword_18002AB7C
0x18001a5ed  mov     [rsp+220h+var_1EC], eax
0x18001a5f1  lea     rax, [rsp+220h+var_1EC]
0x18001a5f6  mov     [rbp+120h+var_70], rax
0x18001a5fd  lea     rax, [rbp+120h+var_180]
0x18001a601  mov     [rbp+120h+var_60], rax
0x18001a608  lea     rax, [rbp+120h+var_170]
0x18001a60c  mov     [rbp+120h+var_A4], r9d
0x18001a610  mov     r9d, 12h
0x18001a616  mov     [rsp+220h+var_200], rax
0x18001a61b  mov     [rbp+120h+var_B0], rdi
0x18001a61f  mov     [rbp+120h+var_198], rbx
0x18001a623  mov     [rbp+120h+var_98], 8
0x18001a62e  mov     [rbp+120h+var_88], 8
0x18001a639  mov     [rbp+120h+var_78], 8
0x18001a644  mov     [rbp+120h+var_68], 4
0x18001a64f  mov     [rbp+120h+var_180], 1000000h
0x18001a657  mov     [rbp+120h+var_58], 8
0x18001a662  call    _tlgWriteAgg
0x18001a667  mov     rcx, [rbp+120h+var_50]
0x18001a66e  xor     rcx, rsp; StackCookie
0x18001a671  call    __security_check_cookie
0x18001a676  add     rsp, 1E8h
0x18001a67d  pop     r15
0x18001a67f  pop     r14
0x18001a681  pop     r13
0x18001a683  pop     r12
0x18001a685  pop     rdi
0x18001a686  pop     rsi
0x18001a687  pop     rbx
0x18001a688  pop     rbp
0x18001a689  retn
```
