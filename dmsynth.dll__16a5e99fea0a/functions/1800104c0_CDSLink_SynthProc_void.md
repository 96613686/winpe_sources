# CDSLink::SynthProc(void)

- ea: `0x1800104c0`
- end: `0x180010ba9`
- name: `?SynthProc@CDSLink@@AEAAXXZ`
- size: `1769`
- prototype: `void __fastcall(CDSLink *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180010bb0`

## callees

- `0x180001d9a`
- `0x1800104c0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800104eb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001057a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001057a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b8c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010587`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010b8c`

## pseudocode

```c
void __fastcall CDSLink::SynthProc(CDSLink *this)
{
  __int64 v2; // rcx
  int v3; // eax
  unsigned int v4; // r10d
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  unsigned int v7; // r8d
  unsigned int v8; // r11d
  __int16 *v9; // r15
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int16 v12; // r10
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  unsigned int v16; // r8d
  __int64 v17; // rsi
  unsigned int v18; // ecx
  unsigned int v19; // eax
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // rbx
  __int64 v23; // rbx
  __int64 v24; // rax
  unsigned int v25; // ebx
  int v26; // eax
  __int64 v27; // r8
  __int64 v28; // r10
  int v29; // ecx
  __int64 v30; // rdx
  __int64 v31; // r10
  __int64 v32; // rdx
  unsigned int v33; // ebx
  int v34; // eax
  __int64 v35; // r8
  int v36; // edx
  unsigned int v37; // [rsp+50h] [rbp-48h] BYREF
  void *v38; // [rsp+58h] [rbp-40h] BYREF
  void *v39; // [rsp+60h] [rbp-38h] BYREF
  _QWORD v40[6]; // [rsp+68h] [rbp-30h] BYREF
  size_t Size; // [rsp+A8h] [rbp+10h] BYREF
  size_t v42; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v43; // [rsp+B8h] [rbp+20h] BYREF

  v37 = 0;
  v43 = 0;
  try
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  }
  catch ( ... )
  {
    return;
  }
  if ( !*((_DWORD *)this + 56) )
    goto LABEL_13;
  v2 = *((_QWORD *)this + 15);
  if ( !v2 || !*((_QWORD *)this + 7) )
    goto LABEL_13;
  v3 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v2 + 32LL))(v2, &v37, &v43);
  if ( v3 )
  {
    if ( v3 == -2005401450
      && !(*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 160LL))(*((_QWORD *)this + 15)) )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 15) + 96LL))(
        *((_QWORD *)this + 15),
        0,
        0,
        1);
    }
    goto LABEL_13;
  }
  v4 = *((_DWORD *)this + 53);
  v5 = v4 >> 1;
  v6 = v37;
  if ( v43 < v37 )
    v7 = v4 - v37 + v43;
  else
    v7 = v43 - v37;
  v8 = *((_DWORD *)this + 55);
  if ( v7 <= v8 )
  {
    v9 = (__int16 *)((char *)this + 86);
    v7 = (v8 - (v8 - v7) / 0x64) >> *((_WORD *)this + 43) << *((_WORD *)this + 43);
  }
  else
  {
    if ( v7 >= v5 )
      goto LABEL_12;
    v9 = (__int16 *)((char *)this + 86);
  }
  *((_DWORD *)this + 55) = v7;
  v43 = (v7 + v6) % v4;
  v10 = v7;
  if ( !*((_QWORD *)this + 25) )
  {
    *((_DWORD *)this + 48) = v6;
    *((_DWORD *)this + 52) = (v7 + v6) % v4;
    *((_QWORD *)this + 25) = v7;
    v11 = *((_QWORD *)this + 7);
    Size = 0;
    *((_DWORD *)this + 18) = 0;
    *((_DWORD *)this + 19) = *((_DWORD *)this + 22);
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64, size_t *))(*(_QWORD *)v11 + 24LL))(v11, &Size);
      *((_QWORD *)this + 8) = Size;
    }
    *((_DWORD *)this + 10) = 0;
  }
  v40[0] = 0;
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 7) + 24LL))(*((_QWORD *)this + 7), v40);
  v12 = *v9;
  v13 = (*((unsigned int *)this + 18)
       + *((unsigned int *)this + 19) * ((v40[0] - *((_QWORD *)this + 8)) / 1000LL) / 10000) << *v9;
  v14 = *((_QWORD *)this + 23);
  v15 = v13 - v14;
  if ( v13 <= v14 )
    v15 = 0;
  v16 = v37;
  if ( v15 > v5 )
  {
    *((_QWORD *)this + 23) = v13;
    v17 = v13 + v10;
    *((_QWORD *)this + 25) = v17;
LABEL_29:
    *((_DWORD *)this + 52) = v43;
    goto LABEL_30;
  }
  v18 = *((_DWORD *)this + 48);
  if ( v37 < v18 )
    v19 = v37 + *((_DWORD *)this + 53) - v18;
  else
    v19 = v37 - v18;
  if ( v19 > v5 )
  {
LABEL_12:
    SetEvent(hEvent);
    goto LABEL_13;
  }
  v13 = v14 + v19;
  *((_QWORD *)this + 23) = v13;
  v17 = v13 + v10;
  v20 = *((_QWORD *)this + 25);
  if ( v17 > v20 )
  {
    *((_QWORD *)this + 25) = v20 + (unsigned int)(v17 - v20);
    goto LABEL_29;
  }
LABEL_30:
  *((_DWORD *)this + 48) = v16;
  v21 = *((_QWORD *)this + 7);
  if ( v21 )
  {
    v22 = 1000 * (10000 * ((v13 >> v12) - *((unsigned int *)this + 18)) / *((unsigned int *)this + 19));
    Size = 0;
    (*(void (__fastcall **)(__int64, size_t *))(*(_QWORD *)v21 + 24LL))(v21, &Size);
    *((_QWORD *)this + 8) -= (__int64)(v22 + *((_QWORD *)this + 8) - Size) / 100;
  }
  v23 = v17 + *((unsigned int *)this + 54);
  v24 = *((_QWORD *)this + 25);
  if ( v23 <= v24 )
    goto LABEL_13;
  v25 = v23 - v24;
  if ( !v25 )
    goto LABEL_13;
  v39 = 0;
  v38 = 0;
  LODWORD(Size) = 0;
  LODWORD(v42) = 0;
  v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void **, size_t *, void **, size_t *, _DWORD))(**((_QWORD **)this + 15) + 88LL))(
          *((_QWORD *)this + 15),
          *((unsigned int *)this + 52),
          v25,
          &v39,
          &Size,
          &v38,
          &v42,
          0);
  if ( v26 == -2005401450 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 160LL))(*((_QWORD *)this + 15))
      || (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 15) + 96LL))(
           *((_QWORD *)this + 15),
           0,
           0,
           1) )
    {
      goto LABEL_13;
    }
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void **, size_t *, void **, size_t *, _DWORD))(**((_QWORD **)this + 15) + 88LL))(
            *((_QWORD *)this + 15),
            *((unsigned int *)this + 52),
            v25,
            &v39,
            &Size,
            &v38,
            &v42,
            0);
  }
  if ( v26 )
    goto LABEL_13;
  v27 = (unsigned int)Size;
  if ( (_DWORD)Size )
  {
    memset_0(v39, 0, (unsigned int)Size);
    v28 = *((_QWORD *)this + 3);
    if ( v28 )
      (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64))(*(_QWORD *)v28 + 120LL))(
        *((_QWORD *)this + 3),
        v39,
        (unsigned int)Size >> *v9,
        *((__int64 *)this + 25) >> *v9);
    v27 = (unsigned int)Size;
    *((_DWORD *)this + 52) += Size;
    v29 = *((_DWORD *)this + 52);
    *((_QWORD *)this + 25) += v27;
    if ( v29 == *((_DWORD *)this + 53) )
      *((_DWORD *)this + 52) = 0;
  }
  LODWORD(v30) = v42;
  if ( (_DWORD)v42 )
  {
    memset_0(v38, 0, (unsigned int)v42);
    v31 = *((_QWORD *)this + 3);
    if ( v31 )
      (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64))(*(_QWORD *)v31 + 120LL))(
        *((_QWORD *)this + 3),
        v38,
        (unsigned int)v42 >> *v9,
        *((__int64 *)this + 25) >> *v9);
    v30 = (unsigned int)v42;
    *((_DWORD *)this + 52) = v42;
    *((_QWORD *)this + 25) += v30;
    v27 = (unsigned int)Size;
  }
  (*(void (__fastcall **)(_QWORD, void *, __int64, void *, _DWORD))(**((_QWORD **)this + 15) + 152LL))(
    *((_QWORD *)this + 15),
    v39,
    v27,
    v38,
    v30);
  v32 = *((unsigned int *)this + 52);
  if ( (unsigned int)v32 < v37 )
    v33 = v37 - v32;
  else
    v33 = v37 + *((_DWORD *)this + 53) - v32;
  v34 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, void **, size_t *, void **, size_t *, _DWORD))(**((_QWORD **)this + 15) + 88LL))(
          *((_QWORD *)this + 15),
          v32,
          v33,
          &v39,
          &Size,
          &v38,
          &v42,
          0);
  if ( v34 == -2005401450 )
  {
    if ( (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 160LL))(*((_QWORD *)this + 15))
      || (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**((_QWORD **)this + 15) + 96LL))(
           *((_QWORD *)this + 15),
           0,
           0,
           1) )
    {
      goto LABEL_13;
    }
    v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void **, size_t *, void **, size_t *, _DWORD))(**((_QWORD **)this + 15) + 88LL))(
            *((_QWORD *)this + 15),
            *((unsigned int *)this + 52),
            v33,
            &v39,
            &Size,
            &v38,
            &v42,
            0);
  }
  if ( v34 )
  {
LABEL_13:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
    return;
  }
  v35 = (unsigned int)Size;
  if ( (_DWORD)Size )
  {
    memset_0(v39, 0, (unsigned int)Size);
    v35 = (unsigned int)Size;
  }
  v36 = v42;
  if ( (_DWORD)v42 )
  {
    memset_0(v38, 0, (unsigned int)v42);
    v35 = (unsigned int)Size;
    v36 = v42;
  }
  (*(void (__fastcall **)(_QWORD, void *, __int64, void *, int))(**((_QWORD **)this + 15) + 152LL))(
    *((_QWORD *)this + 15),
    v39,
    v35,
    v38,
    v36);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
}

```

## disassembly

```asm
0x1800104c0  mov     [rsp+arg_0], rbx
0x1800104c5  push    rsi
0x1800104c6  push    rdi
0x1800104c7  push    r12
0x1800104c9  push    r14
0x1800104cb  push    r15
0x1800104cd  sub     rsp, 70h
0x1800104d1  mov     rdi, rcx
0x1800104d4  xor     r12d, r12d
0x1800104d7  mov     [rsp+98h+var_48], r12d
0x1800104dc  mov     [rsp+98h+arg_18], r12d
0x1800104e4  add     rcx, 88h; lpCriticalSection
0x1800104eb  call    cs:__imp_EnterCriticalSection
0x1800104f1  nop
0x1800104f2  cmp     dword ptr [rdi+0E0h], 0
0x1800104f9  jz      loc_180010580
0x1800104ff  mov     rcx, [rdi+78h]
0x180010503  test    rcx, rcx
0x180010506  jz      short loc_180010580
0x180010508  cmp     qword ptr [rdi+38h], 0
0x18001050d  jz      short loc_180010580
0x18001050f  mov     rax, [rcx]
0x180010512  lea     r8, [rsp+98h+arg_18]
0x18001051a  lea     rdx, [rsp+98h+var_48]
0x18001051f  mov     rax, [rax+20h]
0x180010523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010528  test    eax, eax
0x18001052a  jnz     loc_180010B4C
0x180010530  mov     r10d, [rdi+0D4h]
0x180010537  mov     ebx, r10d
0x18001053a  shr     ebx, 1
0x18001053c  mov     r8d, [rsp+98h+arg_18]
0x180010544  mov     r9d, [rsp+98h+var_48]
0x180010549  cmp     r8d, r9d
0x18001054c  jb      short loc_180010553
0x18001054e  sub     r8d, r9d
0x180010551  jmp     short loc_18001055C
0x180010553  mov     eax, r10d
0x180010556  sub     eax, r9d
0x180010559  add     r8d, eax
0x18001055c  mov     r11d, [rdi+0DCh]
0x180010563  cmp     r8d, r11d
0x180010566  jbe     short loc_180010592
0x180010568  cmp     r8d, ebx
0x18001056b  jnb     short loc_180010573
0x18001056d  lea     r15, [rdi+56h]
0x180010571  jmp     short loc_1800105B6
0x180010573  mov     rcx, cs:hEvent; hEvent
0x18001057a  call    cs:__imp_SetEvent
0x180010580  lea     rcx, [rdi+88h]; lpCriticalSection
0x180010587  call    cs:__imp_LeaveCriticalSection
0x18001058d  jmp     loc_180010B94
0x180010592  lea     r15, [rdi+56h]
0x180010596  movzx   ecx, word ptr [r15]
0x18001059a  mov     edx, r11d
0x18001059d  sub     edx, r8d
0x1800105a0  mov     eax, 51EB851Fh
0x1800105a5  mul     edx
0x1800105a7  shr     edx, 5
0x1800105aa  mov     r8d, r11d
0x1800105ad  sub     r8d, edx
0x1800105b0  shr     r8d, cl
0x1800105b3  shl     r8d, cl
0x1800105b6  mov     eax, r8d
0x1800105b9  mov     [rdi+0DCh], eax
0x1800105bf  lea     eax, [r8+r9]
0x1800105c3  xor     edx, edx
0x1800105c5  div     r10d
0x1800105c8  mov     [rsp+98h+arg_18], edx
0x1800105cf  mov     esi, r8d
0x1800105d2  cmp     qword ptr [rdi+0C8h], 0
0x1800105da  jnz     short loc_18001062F
0x1800105dc  mov     [rdi+0C0h], r9d
0x1800105e3  mov     [rdi+0D0h], edx
0x1800105e9  mov     [rdi+0C8h], rsi
0x1800105f0  mov     rcx, [rdi+38h]
0x1800105f4  mov     [rsp+98h+Size], r12
0x1800105fc  mov     [rdi+48h], r12d
0x180010600  mov     eax, [rdi+58h]
0x180010603  mov     [rdi+4Ch], eax
0x180010606  test    rcx, rcx
0x180010609  jz      short loc_18001062B
0x18001060b  mov     rax, [rcx]
0x18001060e  lea     rdx, [rsp+98h+Size]
0x180010616  mov     rax, [rax+18h]
0x18001061a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001061f  mov     rax, [rsp+98h+Size]
0x180010627  mov     [rdi+40h], rax
0x18001062b  mov     [rdi+28h], r12d
0x18001062f  mov     [rsp+98h+var_30], r12
0x180010634  mov     rcx, [rdi+38h]
0x180010638  mov     rax, [rcx]
0x18001063b  lea     rdx, [rsp+98h+var_30]
0x180010640  mov     rax, [rax+18h]
0x180010644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010649  movzx   r10d, word ptr [r15]
0x18001064d  mov     rcx, [rsp+98h+var_30]
0x180010652  sub     rcx, [rdi+40h]
0x180010656  mov     rax, 20C49BA5E353F7CFh
0x180010660  imul    rcx
0x180010663  sar     rdx, 7
0x180010667  mov     rax, rdx
0x18001066a  shr     rax, 3Fh
0x18001066e  add     rdx, rax
0x180010671  mov     eax, [rdi+4Ch]
0x180010674  imul    rdx, rax
0x180010678  mov     rax, 346DC5D63886594Bh
0x180010682  imul    rdx
0x180010685  sar     rdx, 0Bh
0x180010689  mov     rax, rdx
0x18001068c  shr     rax, 3Fh
0x180010690  add     rdx, rax
0x180010693  mov     eax, [rdi+48h]
0x180010696  add     rdx, rax
0x180010699  mov     ecx, r10d
0x18001069c  shl     rdx, cl
0x18001069f  mov     r9, [rdi+0B8h]
0x1800106a6  mov     rcx, rdx
0x1800106a9  sub     rcx, r9
0x1800106ac  cmp     rdx, r9
0x1800106af  cmovle  rcx, r12
0x1800106b3  mov     eax, ebx
0x1800106b5  mov     r8d, [rsp+98h+var_48]
0x1800106ba  cmp     rcx, rax
0x1800106bd  jle     short loc_1800106D2
0x1800106bf  mov     [rdi+0B8h], rdx
0x1800106c6  add     rsi, rdx
0x1800106c9  mov     [rdi+0C8h], rsi
0x1800106d0  jmp     short loc_180010724
0x1800106d2  mov     ecx, [rdi+0C0h]
0x1800106d8  cmp     r8d, ecx
0x1800106db  jb      short loc_1800106E4
0x1800106dd  mov     eax, r8d
0x1800106e0  sub     eax, ecx
0x1800106e2  jmp     short loc_1800106EF
0x1800106e4  mov     eax, [rdi+0D4h]
0x1800106ea  sub     eax, ecx
0x1800106ec  add     eax, r8d
0x1800106ef  cmp     eax, ebx
0x1800106f1  ja      loc_180010573
0x1800106f7  mov     edx, eax
0x1800106f9  add     rdx, r9
0x1800106fc  mov     [rdi+0B8h], rdx
0x180010703  add     rsi, rdx
0x180010706  mov     r9, [rdi+0C8h]
0x18001070d  cmp     rsi, r9
0x180010710  jle     short loc_180010731
0x180010712  mov     rcx, rsi
0x180010715  sub     rcx, r9
0x180010718  mov     ecx, ecx
0x18001071a  add     rcx, r9
0x18001071d  mov     [rdi+0C8h], rcx
0x180010724  mov     eax, [rsp+98h+arg_18]
0x18001072b  mov     [rdi+0D0h], eax
0x180010731  mov     [rdi+0C0h], r8d
0x180010738  mov     r9, [rdi+38h]
0x18001073c  test    r9, r9
0x18001073f  jz      short loc_1800107BA
0x180010741  mov     ecx, r10d
0x180010744  sar     rdx, cl
0x180010747  mov     eax, [rdi+48h]
0x18001074a  sub     rdx, rax
0x18001074d  imul    rax, rdx, 2710h
0x180010754  mov     r8d, [rdi+4Ch]
0x180010758  cqo
0x18001075a  idiv    r8
0x18001075d  imul    rbx, rax, 3E8h
0x180010764  mov     [rsp+98h+Size], r12
0x18001076c  mov     rax, [r9]
0x18001076f  lea     rdx, [rsp+98h+Size]
0x180010777  mov     rcx, r9
0x18001077a  mov     rax, [rax+18h]
0x18001077e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010783  mov     r8, [rdi+40h]
0x180010787  mov     rcx, r8
0x18001078a  sub     rcx, [rsp+98h+Size]
0x180010792  add     rcx, rbx
0x180010795  mov     rax, 0A3D70A3D70A3D70Bh
0x18001079f  imul    rcx
0x1800107a2  add     rdx, rcx
0x1800107a5  sar     rdx, 6
0x1800107a9  mov     rax, rdx
0x1800107ac  shr     rax, 3Fh
0x1800107b0  add     rdx, rax
0x1800107b3  sub     r8, rdx
0x1800107b6  mov     [rdi+40h], r8
0x1800107ba  mov     ebx, [rdi+0D8h]
0x1800107c0  add     rbx, rsi
0x1800107c3  mov     rax, [rdi+0C8h]
0x1800107ca  cmp     rbx, rax
0x1800107cd  jle     loc_180010B85
0x1800107d3  sub     ebx, eax
0x1800107d5  jz      loc_180010B85
0x1800107db  mov     [rsp+98h+var_38], r12
0x1800107e0  mov     [rsp+98h+var_40], r12
0x1800107e5  mov     dword ptr [rsp+98h+Size], r12d
0x1800107ed  mov     dword ptr [rsp+98h+arg_10], r12d
0x1800107f5  mov     rcx, [rdi+78h]
0x1800107f9  mov     rax, [rcx]
0x1800107fc  mov     [rsp+98h+var_60], r12d
0x180010801  lea     rdx, [rsp+98h+arg_10]
0x180010809  mov     [rsp+98h+var_68], rdx
0x18001080e  lea     rdx, [rsp+98h+var_40]
0x180010813  mov     [rsp+98h+var_70], rdx
0x180010818  lea     rdx, [rsp+98h+Size]
0x180010820  mov     [rsp+98h+var_78], rdx
0x180010825  lea     r9, [rsp+98h+var_38]
0x18001082a  mov     r8d, ebx
0x18001082d  mov     edx, [rdi+0D0h]
0x180010833  mov     rax, [rax+58h]
0x180010837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001083c  cmp     eax, 88780096h
0x180010841  jnz     loc_1800108CC
0x180010847  mov     rcx, [rdi+78h]
0x18001084b  mov     rax, [rcx]
0x18001084e  mov     rax, [rax+0A0h]
0x180010855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001085a  test    eax, eax
0x18001085c  jnz     loc_180010B85
0x180010862  mov     rcx, [rdi+78h]
0x180010866  mov     rax, [rcx]
0x180010869  mov     r9d, 1
0x18001086f  xor     r8d, r8d
0x180010872  xor     edx, edx
0x180010874  mov     rax, [rax+60h]
0x180010878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001087d  test    eax, eax
0x18001087f  jnz     loc_180010B85
0x180010885  mov     rcx, [rdi+78h]
0x180010889  mov     rax, [rcx]
0x18001088c  mov     [rsp+98h+var_60], r12d
0x180010891  lea     rdx, [rsp+98h+arg_10]
0x180010899  mov     [rsp+98h+var_68], rdx
0x18001089e  lea     rdx, [rsp+98h+var_40]
0x1800108a3  mov     [rsp+98h+var_70], rdx
0x1800108a8  lea     rdx, [rsp+98h+Size]
0x1800108b0  mov     [rsp+98h+var_78], rdx
0x1800108b5  lea     r9, [rsp+98h+var_38]
0x1800108ba  mov     r8d, ebx
0x1800108bd  mov     edx, [rdi+0D0h]
0x1800108c3  mov     rax, [rax+58h]
0x1800108c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108cc  test    eax, eax
0x1800108ce  jnz     loc_180010B85
0x1800108d4  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x1800108dc  test    r8d, r8d
0x1800108df  jz      short loc_18001094E
0x1800108e1  xor     edx, edx; Val
0x1800108e3  mov     rcx, [rsp+98h+var_38]; void *
0x1800108e8  call    memset_0
0x1800108ed  mov     r10, [rdi+18h]
0x1800108f1  test    r10, r10
0x1800108f4  jz      short loc_180010923
0x1800108f6  movzx   ecx, word ptr [r15]
0x1800108fa  mov     rax, [r10]
0x1800108fd  mov     r9, [rdi+0C8h]
0x180010904  sar     r9, cl
0x180010907  mov     r8d, dword ptr [rsp+98h+Size]
0x18001090f  shr     r8d, cl
0x180010912  mov     rdx, [rsp+98h+var_38]
0x180010917  mov     rcx, r10
0x18001091a  mov     rax, [rax+78h]
0x18001091e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010923  mov     r8d, dword ptr [rsp+98h+Size]
0x18001092b  add     [rdi+0D0h], r8d
0x180010932  mov     ecx, [rdi+0D0h]
0x180010938  add     [rdi+0C8h], r8
0x18001093f  cmp     ecx, [rdi+0D4h]
0x180010945  jnz     short loc_18001094E
0x180010947  mov     [rdi+0D0h], r12d
0x18001094e  mov     edx, dword ptr [rsp+98h+arg_10]
0x180010955  test    edx, edx
0x180010957  jz      short loc_1800109BA
0x180010959  mov     r8d, edx; Size
0x18001095c  xor     edx, edx; Val
0x18001095e  mov     rcx, [rsp+98h+var_40]; void *
0x180010963  call    memset_0
0x180010968  mov     r10, [rdi+18h]
0x18001096c  test    r10, r10
0x18001096f  jz      short loc_18001099E
0x180010971  movzx   ecx, word ptr [r15]
0x180010975  mov     rax, [r10]
0x180010978  mov     r9, [rdi+0C8h]
0x18001097f  sar     r9, cl
0x180010982  mov     r8d, dword ptr [rsp+98h+arg_10]
0x18001098a  shr     r8d, cl
0x18001098d  mov     rdx, [rsp+98h+var_40]
0x180010992  mov     rcx, r10
0x180010995  mov     rax, [rax+78h]
0x180010999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001099e  mov     edx, dword ptr [rsp+98h+arg_10]
0x1800109a5  mov     [rdi+0D0h], edx
0x1800109ab  add     [rdi+0C8h], rdx
0x1800109b2  mov     r8d, dword ptr [rsp+98h+Size]
0x1800109ba  mov     rcx, [rdi+78h]
0x1800109be  mov     rax, [rcx]
0x1800109c1  mov     dword ptr [rsp+98h+var_78], edx
0x1800109c5  mov     r9, [rsp+98h+var_40]
0x1800109ca  mov     rdx, [rsp+98h+var_38]
0x1800109cf  mov     rax, [rax+98h]
  ... truncated ...
```
