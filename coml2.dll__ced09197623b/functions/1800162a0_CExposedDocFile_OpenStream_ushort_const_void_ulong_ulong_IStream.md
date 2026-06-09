# CExposedDocFile::OpenStream(ushort const *,void *,ulong,ulong,IStream * *)

- ea: `0x1800162a0`
- end: `0x180016808`
- name: `?OpenStream@CExposedDocFile@@UEAAJPEBGPEAXKKPEAPEAUIStream@@@Z`
- size: `1384`
- prototype: `int(CExposedDocFile *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, struct IStream **)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180015f30`
- `0x1800162a0`
- `0x180016810`
- `0x180016910`
- `0x180017d40`
- `0x180042800`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001656d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001656d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016763`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180016763`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800165a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800165a8`

## pseudocode

```c
__int64 __fastcall CExposedDocFile::OpenStream(
        CExposedDocFile *this,
        const unsigned __int16 *a2,
        void *a3,
        unsigned int a4,
        unsigned int a5,
        struct IStream **a6)
{
  _QWORD *v6; // r13
  int v11; // ebx
  unsigned int v13; // ecx
  unsigned int v14; // edx
  __int64 v15; // rax
  __int64 v16; // rbx
  _QWORD *v17; // rcx
  unsigned __int16 v18; // bx
  void *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  struct IStream *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  _QWORD *v25; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v27; // rcx
  bool v28; // zf
  __int64 v29; // rax
  __int64 v30; // rax
  BOOL v31; // r12d
  __int64 *v32; // rbx
  unsigned int v33; // r13d
  __int64 v34; // rax
  __int64 v35; // r9
  int v36; // ecx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  unsigned int v40; // eax
  __int64 v41; // rax
  unsigned int v42; // [rsp+30h] [rbp-99h] BYREF
  unsigned int v43; // [rsp+34h] [rbp-95h] BYREF
  void *v44; // [rsp+38h] [rbp-91h] BYREF
  int v45; // [rsp+40h] [rbp-89h] BYREF
  int v46; // [rsp+44h] [rbp-85h] BYREF
  _QWORD *v47; // [rsp+48h] [rbp-81h]
  int v48; // [rsp+50h] [rbp-79h] BYREF
  _QWORD *v49; // [rsp+58h] [rbp-71h]
  __int128 v50; // [rsp+60h] [rbp-69h]
  __int64 v51; // [rsp+70h] [rbp-59h]
  struct IStream **v52; // [rsp+78h] [rbp-51h]
  _BYTE v53[64]; // [rsp+80h] [rbp-49h] BYREF
  unsigned __int16 v54; // [rsp+C0h] [rbp-9h]

  v6 = (_QWORD *)*((_QWORD *)this + 22);
  v52 = a6;
  v48 = -2147286784;
  v47 = v6;
  v49 = v6;
  v44 = 0;
  v54 = 0;
  v50 = 0;
  if ( !a6 )
  {
    v11 = -2147287031;
LABEL_3:
    CSafeSem::Release((CSafeSem *)&v48);
    return (unsigned int)v11;
  }
  *a6 = 0;
  v11 = CheckName(a2);
  if ( v11 < 0 )
    goto LABEL_3;
  if ( a3 || a5 )
  {
    v11 = -2147286953;
    goto LABEL_3;
  }
  v13 = a4 & 3;
  if ( v13 > 2 )
    goto LABEL_56;
  v14 = a4 & 0x70;
  if ( v14 > 0x40 || (a4 & 0xF388EF8C) != 0 || (a4 & 0x40000) != 0 && (v13 - 1 <= 1 || (a4 & 0x10000) != 0) )
    goto LABEL_56;
  if ( (a4 & 0x21000) == 0x21000 )
    goto LABEL_56;
  if ( (a4 & 0x50000) != 0 )
    goto LABEL_16;
  if ( (a4 & 3) == 0 )
  {
    if ( ((v14 - 16) & 0xFFFFFFEF) == 0 )
      goto LABEL_16;
LABEL_56:
    v11 = -2147286785;
    goto LABEL_3;
  }
  if ( v14 != 16 )
    goto LABEL_56;
LABEL_16:
  if ( (a4 & 0x300000) != 0
    || (a4 & 0x100000) != 0 && ((a4 & 3) == 0 || (a4 & 0x10000) == 0)
    || (a4 & 0x200000) != 0 && (((v14 - 16) & 0xFFFFFFEF) == 0 || (a4 & 0x131000) != 0x10000)
    || (a4 & 0x21000) != 0 )
  {
    goto LABEL_56;
  }
  if ( (a4 & 0x4050000) != 0 )
  {
    v11 = -2147287039;
    goto LABEL_3;
  }
  v15 = *((_QWORD *)this + 15) - *(_QWORD *)&GUID_efe6e9cd_1af4_49c2_89fd_e27936f6b823.Data1;
  if ( !v15 )
    v15 = *((_QWORD *)this + 16) - *(_QWORD *)GUID_efe6e9cd_1af4_49c2_89fd_e27936f6b823.Data4;
  if ( v15 )
  {
    v11 = -2147287034;
  }
  else
  {
LABEL_24:
    while ( 1 )
    {
      v11 = CSafeSem::Take((CSafeSem *)&v48);
      if ( v11 < 0 )
        break;
      v16 = -1;
      v17 = (_QWORD *)*((_QWORD *)this + 21);
      v17[4] = v6[2];
      v17[5] = v6[3];
      v17[6] = v6[4];
      do
        ++v16;
      while ( a2[v16] );
      v18 = 2 * (v16 + 1);
      if ( v18 > 0x40u )
        v18 = 64;
      if ( a2 )
        memcpy_0(v53, a2, v18);
      v19 = v44;
      v54 = v18;
      if ( v44 )
      {
        v20 = *(_QWORD *)v44;
        v44 = 0;
        (*(void (__fastcall **)(void *))(v20 + 16))(v19);
      }
      v21 = CExposedDocFile::OpenEntry(this, (const struct CDfName *)v53, 2, a4, &v44);
      v11 = v21;
      if ( v21 != -2147483638 && v21 != -2147286524 )
      {
        if ( v21 >= 0 )
        {
          v22 = (struct IStream *)v44;
          v44 = 0;
          *v52 = v22;
        }
        break;
      }
      v30 = *((_QWORD *)this + 22);
      v51 = v30;
      v42 = 0;
      v31 = v11 == -2147483638;
      v43 = 0;
      v32 = *(__int64 **)(v30 + 72);
      v33 = 0;
      if ( v32 )
      {
        v33 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, unsigned int *))(*v32 + 24))(
                *(_QWORD *)(v30 + 72),
                &v42,
                &v43);
        if ( !v33 )
        {
          CSafeSem::Release((CSafeSem *)&v48);
          v38 = v42;
          v39 = v43;
          while ( 1 )
          {
            v40 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, BOOL, int))(**((_QWORD **)this + 13) + 40LL))(
                    *((_QWORD *)this + 13),
                    v38,
                    v39,
                    v31,
                    197123);
            v33 = v40;
            if ( v40 != 197121 && v40 != 197123 && v40 )
              goto LABEL_81;
            v45 = 0;
            WaitForSingleObject(*(HANDLE *)(v51 + 80), 0xFFFFFFFF);
            (*(void (__fastcall **)(__int64 *, int *))(*v32 + 32))(v32, &v45);
            if ( v45 == 2 )
              break;
            if ( v45 == 1 )
              goto LABEL_82;
            v41 = *v32;
            v46 = 0;
            (*(void (__fastcall **)(__int64 *, unsigned int *, int *))(v41 + 24))(v32, &v42, &v46);
            v38 = v42;
            v39 = v43;
            if ( v42 >= v43 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, BOOL, int))(**((_QWORD **)this + 13) + 40LL))(
                *((_QWORD *)this + 13),
                v42,
                v43,
                v31,
                197121);
LABEL_81:
              if ( v33 - 197121 > 2 )
                goto LABEL_65;
LABEL_82:
              v6 = v47;
              goto LABEL_24;
            }
          }
          v33 = -2147286527;
        }
LABEL_52:
        if ( v44 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 16LL))(v44);
        CSafeSem::Release((CSafeSem *)&v48);
        return v33;
      }
LABEL_65:
      if ( v33 )
        goto LABEL_52;
      v6 = v47;
    }
  }
  if ( v44 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v44 + 16LL))(v44);
  v23 = *((_QWORD *)&v50 + 1);
  if ( *((_QWORD *)&v50 + 1) )
  {
    v24 = v50;
    if ( (_QWORD)v50 )
    {
      v34 = *(_QWORD *)(v50 + 88);
      v35 = *(_QWORD *)(v50 + 96);
      v36 = *(_DWORD *)(v50 + 104);
      *(_QWORD *)(*((_QWORD *)&v50 + 1) + 8LL) = v34;
      *(_QWORD *)(v23 + 16) = v35;
      if ( v34 )
        v37 = *(_DWORD *)(v34 + 16) - 24;
      else
        v37 = 0;
      *(_DWORD *)(v23 + 32) = v37;
      *(_DWORD *)(v23 + 36) = v36;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = v35;
      *(_QWORD *)(v23 + 24) = v24;
    }
    else
    {
      *(_QWORD *)(*((_QWORD *)&v50 + 1) + 8LL) = 0;
      *(_QWORD *)(v23 + 16) = 0;
      *(_QWORD *)(v23 + 32) = 0;
      *(_QWORD *)NtCurrentTeb()->ReservedForOle = 0;
      *(_QWORD *)(v23 + 24) = 0;
    }
  }
  if ( v48 >= 0 )
  {
    v25 = v49;
    CurrentThreadId = GetCurrentThreadId();
    v27 = v25[14];
    if ( *(_DWORD *)(v27 + 8) == CurrentThreadId )
    {
      v28 = (*(_DWORD *)(v27 + 4))-- == 1;
      v29 = v25[14];
      if ( v28 )
      {
        *(_DWORD *)(v29 + 8) = 0;
        if ( _InterlockedDecrement((volatile signed __int32 *)v25[14]) >= 0 )
          SetEvent((HANDLE)v25[15]);
      }
      else
      {
        _InterlockedDecrement((volatile signed __int32 *)v29);
      }
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800162a0  mov     [rsp-8+arg_10], rbx
0x1800162a5  push    rbp
0x1800162a6  push    rsi
0x1800162a7  push    rdi
0x1800162a8  push    r12
0x1800162aa  push    r13
0x1800162ac  push    r14
0x1800162ae  push    r15
0x1800162b0  lea     rbp, [rsp-17h]
0x1800162b5  sub     rsp, 0E0h
0x1800162bc  mov     rax, cs:__security_cookie
0x1800162c3  xor     rax, rsp
0x1800162c6  mov     [rbp+47h+var_40], rax
0x1800162ca  mov     r13, [rcx+0B0h]
0x1800162d1  mov     r15, rcx
0x1800162d4  mov     r12, [rbp+47h+arg_28]
0x1800162d8  xor     ecx, ecx
0x1800162da  mov     [rbp+47h+var_98], r12
0x1800162de  xorps   xmm0, xmm0
0x1800162e1  mov     [rbp+47h+var_C0], 80030100h
0x1800162e8  mov     esi, r9d
0x1800162eb  mov     [rsp+110h+var_C8], r13
0x1800162f0  mov     r14, r8
0x1800162f3  mov     [rbp+47h+var_B8], r13
0x1800162f7  mov     rdi, rdx
0x1800162fa  mov     [rsp+110h+var_D8], rcx
0x1800162ff  mov     [rbp+47h+var_50], cx
0x180016303  movdqu  [rbp+47h+var_B0], xmm0
0x180016308  test    r12, r12
0x18001630b  jnz     short loc_180016344
0x18001630d  mov     ebx, 80030009h
0x180016312  lea     rcx, [rbp+47h+var_C0]; this
0x180016316  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x18001631b  mov     eax, ebx
0x18001631d  mov     rcx, [rbp+47h+var_40]
0x180016321  xor     rcx, rsp; StackCookie
0x180016324  call    __security_check_cookie
0x180016329  mov     rbx, [rsp+110h+arg_10]
0x180016331  add     rsp, 0E0h
0x180016338  pop     r15
0x18001633a  pop     r14
0x18001633c  pop     r13
0x18001633e  pop     r12
0x180016340  pop     rdi
0x180016341  pop     rsi
0x180016342  pop     rbp
0x180016343  retn
0x180016344  mov     [r12], rcx
0x180016348  mov     rcx, rdi; unsigned __int16 *
0x18001634b  call    ?CheckName@@YAJPEBG@Z; CheckName(ushort const *)
0x180016350  mov     ebx, eax
0x180016352  test    eax, eax
0x180016354  js      short loc_180016312
0x180016356  test    r14, r14
0x180016359  jnz     loc_1800167FE
0x18001635f  cmp     [rbp+47h+arg_20], r14d
0x180016363  jnz     loc_1800167FE
0x180016369  mov     ecx, esi
0x18001636b  and     ecx, 3
0x18001636e  cmp     ecx, 2
0x180016371  ja      loc_18001664F
0x180016377  mov     edx, esi
0x180016379  and     edx, 70h
0x18001637c  cmp     edx, 40h ; '@'
0x18001637f  ja      loc_18001664F
0x180016385  test    esi, 0F388EF8Ch
0x18001638b  jnz     loc_18001664F
0x180016391  bt      esi, 12h
0x180016395  jb      loc_1800166C8
0x18001639b  mov     r8d, esi
0x18001639e  and     r8d, 21000h
0x1800163a5  cmp     r8d, 21000h
0x1800163ac  jz      loc_18001664F
0x1800163b2  test    esi, 50000h
0x1800163b8  jnz     short loc_1800163D0
0x1800163ba  test    ecx, ecx
0x1800163bc  jnz     loc_180016646
0x1800163c2  lea     eax, [rdx-10h]
0x1800163c5  test    eax, 0FFFFFFEFh
0x1800163ca  jnz     loc_18001664F
0x1800163d0  test    esi, 300000h
0x1800163d6  jnz     loc_18001664F
0x1800163dc  bt      esi, 14h
0x1800163e0  jb      loc_1800166A2
0x1800163e6  bt      esi, 15h
0x1800163ea  jb      loc_1800166E3
0x1800163f0  test    r8d, r8d
0x1800163f3  jnz     loc_18001664F
0x1800163f9  test    esi, 4050000h
0x1800163ff  jnz     loc_1800165BF
0x180016405  mov     rax, [r15+78h]
0x180016409  sub     rax, qword ptr cs:_GUID_efe6e9cd_1af4_49c2_89fd_e27936f6b823.Data1
0x180016410  jnz     short loc_180016420
0x180016412  mov     rax, [r15+80h]
0x180016419  sub     rax, qword ptr cs:_GUID_efe6e9cd_1af4_49c2_89fd_e27936f6b823.Data4
0x180016420  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180016427  test    rax, rax
0x18001642a  jnz     loc_1800165B3
0x180016430  lea     rcx, [rbp+47h+var_C0]; this
0x180016434  mov     r12d, 40h ; '@'
0x18001643a  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x18001643f  mov     ebx, eax
0x180016441  test    eax, eax
0x180016443  js      loc_1800165B8
0x180016449  mov     rax, [r13+10h]
0x18001644d  mov     rbx, r14
0x180016450  mov     rcx, [r15+0A8h]
0x180016457  mov     [rcx+20h], rax
0x18001645b  mov     rax, [r13+18h]
0x18001645f  mov     [rcx+28h], rax
0x180016463  mov     rax, [r13+20h]
0x180016467  mov     [rcx+30h], rax
0x18001646b  nop     dword ptr [rax+rax+00h]
0x180016470  inc     rbx
0x180016473  cmp     word ptr [rdi+rbx*2], 0
0x180016478  jnz     short loc_180016470
0x18001647a  inc     bx
0x18001647d  add     bx, bx
0x180016480  cmp     bx, 40h ; '@'
0x180016484  jbe     short loc_18001648A
0x180016486  movzx   ebx, r12w
0x18001648a  test    rdi, rdi
0x18001648d  jz      short loc_18001649F
0x18001648f  movzx   r8d, bx; Size
0x180016493  lea     rcx, [rbp+47h+var_90]; void *
0x180016497  mov     rdx, rdi; Src
0x18001649a  call    memcpy_0
0x18001649f  mov     rcx, [rsp+110h+var_D8]
0x1800164a4  mov     [rbp+47h+var_50], bx
0x1800164a8  test    rcx, rcx
0x1800164ab  jz      short loc_1800164C2
0x1800164ad  mov     rax, [rcx]
0x1800164b0  mov     [rsp+110h+var_D8], 0
0x1800164b9  mov     rax, [rax+10h]
0x1800164bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164c2  lea     rax, [rsp+110h+var_D8]
0x1800164c7  mov     r9d, esi; unsigned int
0x1800164ca  mov     r8d, 2; unsigned int
0x1800164d0  mov     [rsp+110h+var_F0], rax; void **
0x1800164d5  lea     rdx, [rbp+47h+var_90]; struct CDfName *
0x1800164d9  mov     rcx, r15; this
0x1800164dc  call    ?OpenEntry@CExposedDocFile@@AEAAJPEBVCDfName@@KKPEAPEAX@Z; CExposedDocFile::OpenEntry(CDfName const *,ulong,ulong,void * *)
0x1800164e1  mov     ebx, eax
0x1800164e3  cmp     eax, 8000000Ah
0x1800164e8  jz      loc_1800165C9
0x1800164ee  cmp     eax, 80030204h
0x1800164f3  jz      loc_1800165C9
0x1800164f9  xor     esi, esi
0x1800164fb  test    eax, eax
0x1800164fd  js      short loc_180016510
0x1800164ff  mov     rax, [rsp+110h+var_D8]
0x180016504  mov     rcx, [rbp+47h+var_98]
0x180016508  mov     [rsp+110h+var_D8], rsi
0x18001650d  mov     [rcx], rax
0x180016510  mov     rcx, [rsp+110h+var_D8]
0x180016515  test    rcx, rcx
0x180016518  jz      short loc_180016526
0x18001651a  mov     rax, [rcx]
0x18001651d  mov     rax, [rax+10h]
0x180016521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016526  mov     rdx, qword ptr [rbp+47h+var_B0+8]
0x18001652a  test    rdx, rdx
0x18001652d  jz      short loc_18001655F
0x18001652f  mov     r8, qword ptr [rbp+47h+var_B0]
0x180016533  test    r8, r8
0x180016536  jnz     loc_180016661
0x18001653c  mov     [rdx+8], rsi
0x180016540  mov     [rdx+10h], rsi
0x180016544  mov     [rdx+20h], r8
0x180016548  mov     rax, gs:30h
0x180016551  mov     rcx, [rax+1758h]
0x180016558  mov     [rcx], rsi
0x18001655b  mov     [rdx+18h], rsi
0x18001655f  cmp     [rbp+47h+var_C0], 0
0x180016563  jl      loc_18001631B
0x180016569  mov     rdi, [rbp+47h+var_B8]
0x18001656d  call    cs:__imp_GetCurrentThreadId
0x180016573  mov     rcx, [rdi+70h]
0x180016577  cmp     [rcx+8], eax
0x18001657a  jnz     loc_18001631B
0x180016580  sub     dword ptr [rcx+4], 1
0x180016584  mov     rax, [rdi+70h]
0x180016588  jnz     loc_180016659
0x18001658e  mov     [rax+8], esi
0x180016591  mov     rax, [rdi+70h]
0x180016595  lock xadd [rax], r14d
0x18001659a  cmp     r14d, 1
0x18001659e  js      loc_18001631B
0x1800165a4  mov     rcx, [rdi+78h]; hEvent
0x1800165a8  call    cs:__imp_SetEvent
0x1800165ae  jmp     loc_18001631B
0x1800165b3  mov     ebx, 80030006h
0x1800165b8  xor     esi, esi
0x1800165ba  jmp     loc_180016510
0x1800165bf  mov     ebx, 80030001h
0x1800165c4  jmp     loc_180016312
0x1800165c9  mov     rax, [r15+0B0h]
0x1800165d0  xor     ecx, ecx
0x1800165d2  cmp     ebx, 8000000Ah
0x1800165d8  mov     [rbp+47h+var_A0], rax
0x1800165dc  mov     r12d, ecx
0x1800165df  mov     [rsp+110h+var_E0], ecx
0x1800165e3  setz    r12b
0x1800165e7  mov     [rsp+110h+var_DC], ecx
0x1800165eb  mov     rbx, [rax+48h]
0x1800165ef  mov     r13d, ecx
0x1800165f2  test    rbx, rbx
0x1800165f5  jz      loc_1800166B5
0x1800165fb  mov     rax, [rbx]
0x1800165fe  lea     r8, [rsp+110h+var_DC]
0x180016603  lea     rdx, [rsp+110h+var_E0]
0x180016608  mov     rcx, rbx
0x18001660b  mov     rax, [rax+18h]
0x18001660f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016614  mov     r13d, eax
0x180016617  test    eax, eax
0x180016619  jz      loc_180016708
0x18001661f  mov     rcx, [rsp+110h+var_D8]
0x180016624  test    rcx, rcx
0x180016627  jz      short loc_180016635
0x180016629  mov     rax, [rcx]
0x18001662c  mov     rax, [rax+10h]
0x180016630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016635  lea     rcx, [rbp+47h+var_C0]; this
0x180016639  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x18001663e  mov     eax, r13d
0x180016641  jmp     loc_18001631D
0x180016646  cmp     edx, 10h
0x180016649  jz      loc_1800163D0
0x18001664f  mov     ebx, 800300FFh
0x180016654  jmp     loc_180016312
0x180016659  lock dec dword ptr [rax]
0x18001665c  jmp     loc_18001631B
0x180016661  mov     rax, [r8+58h]
0x180016665  mov     r9, [r8+60h]
0x180016669  mov     ecx, [r8+68h]
0x18001666d  mov     [rdx+8], rax
0x180016671  mov     [rdx+10h], r9
0x180016675  test    rax, rax
0x180016678  jz      short loc_1800166B1
0x18001667a  mov     eax, [rax+10h]
0x18001667d  sub     eax, 18h
0x180016680  mov     [rdx+20h], eax
0x180016683  mov     [rdx+24h], ecx
0x180016686  mov     rax, gs:30h
0x18001668f  mov     rcx, [rax+1758h]
0x180016696  mov     [rcx], r9
0x180016699  mov     [rdx+18h], r8
0x18001669d  jmp     loc_18001655F
0x1800166a2  test    ecx, ecx
0x1800166a4  jz      short loc_18001664F
0x1800166a6  bt      esi, 10h
0x1800166aa  jnb     short loc_18001664F
0x1800166ac  jmp     loc_1800163E6
0x1800166b1  mov     eax, esi
0x1800166b3  jmp     short loc_180016680
0x1800166b5  test    r13d, r13d
0x1800166b8  jnz     loc_18001661F
0x1800166be  mov     r13, [rsp+110h+var_C8]
0x1800166c3  jmp     loc_180016430
0x1800166c8  lea     eax, [rcx-1]
0x1800166cb  cmp     eax, 1
0x1800166ce  jbe     loc_18001664F
0x1800166d4  bt      esi, 10h
0x1800166d8  jb      loc_18001664F
0x1800166de  jmp     loc_18001639B
0x1800166e3  lea     eax, [rdx-10h]
0x1800166e6  test    eax, 0FFFFFFEFh
0x1800166eb  jz      loc_18001664F
0x1800166f1  mov     eax, esi
0x1800166f3  and     eax, 131000h
0x1800166f8  cmp     eax, 10000h
0x1800166fd  jnz     loc_18001664F
0x180016703  jmp     loc_1800163F0
0x180016708  lea     rcx, [rbp+47h+var_C0]; this
0x18001670c  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x180016711  mov     edx, [rsp+110h+var_E0]
0x180016715  mov     r8d, [rsp+110h+var_DC]
0x18001671a  mov     rcx, [r15+68h]
0x18001671e  mov     r9d, r12d
0x180016721  mov     dword ptr [rsp+110h+var_F0], 30203h
0x180016729  mov     rax, [rcx]
0x18001672c  mov     rax, [rax+28h]
0x180016730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016735  mov     r13d, eax
0x180016738  cmp     eax, 30201h
0x18001673d  jz      short loc_18001674E
0x18001673f  cmp     eax, 30203h
0x180016744  jz      short loc_18001674E
0x180016746  test    eax, eax
0x180016748  jnz     loc_1800167D9
0x18001674e  mov     rax, [rbp+47h+var_A0]
0x180016752  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180016757  mov     [rsp+110h+var_D0], 0
0x18001675f  mov     rcx, [rax+50h]; hHandle
0x180016763  call    cs:__imp_WaitForSingleObject
0x180016769  mov     rax, [rbx]
0x18001676c  lea     rdx, [rsp+110h+var_D0]
0x180016771  mov     rcx, rbx
0x180016774  mov     rax, [rax+20h]
  ... truncated ...
```
