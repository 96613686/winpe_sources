# FileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x180133100`
- end: `0x18013368d`
- name: `?CopyTo@FileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `1421`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180105d40`
- `0x18010673c`
- `0x180133100`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013318f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18013318f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013365d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18013365d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180133645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180133302`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180133302`

## pseudocode

```c
__int64 __fastcall FileStream::CopyTo(
        FileStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5)
{
  ULONGLONG v8; // r15
  ULONGLONG v9; // r14
  int v10; // r12d
  DWORD LowPart; // r13d
  __int64 v12; // rsi
  __int64 v13; // rdi
  unsigned __int64 v14; // rdx
  void *v15; // rcx
  int v16; // edx
  FileStream *v17; // rsi
  struct IStream *v18; // rdi
  __int64 v19; // rax
  void *pv; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
  int v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  unsigned int v26; // [rsp+4Ch] [rbp-B4h]
  unsigned int v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v29; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  ULONGLONG v32; // [rsp+70h] [rbp-90h]
  ULONGLONG v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A8h] [rbp-58h]
  union _ULARGE_INTEGER *v40; // [rsp+B0h] [rbp-50h]
  union _ULARGE_INTEGER *v41; // [rsp+B8h] [rbp-48h]
  _BYTE v42[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]

  v40 = a4;
  v41 = a5;
  v28 = 0;
  v29 = 0;
  v8 = 0;
  v32 = 0;
  v9 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  memset_0(v42, 0, 0x50u);
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 9) == -1 )
  {
    v10 = -2147286782;
    goto LABEL_51;
  }
  if ( !a2 )
  {
    v10 = -2147286953;
    goto LABEL_51;
  }
  LowPart = a3.LowPart;
  if ( a3.QuadPart > 0x2000 )
    LowPart = 0x2000;
  v10 = (*(__int64 (__fastcall **)(FileStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)this + 40LL))(
          this,
          0,
          1,
          &v30);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a2 + 40LL))(
            a2,
            0,
            1,
            &v31);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(FileStream *, _BYTE *, __int64))(*(_QWORD *)this + 96LL))(this, v42, 1);
      if ( v10 >= 0 )
      {
        v12 = v43;
        v26 = HIDWORD(v43);
        v10 = (*(__int64 (__fastcall **)(struct IStream *, _BYTE *, __int64))(*(_QWORD *)a2 + 96LL))(a2, v42, 1);
        if ( v10 >= 0 )
        {
          v13 = v43;
          if ( __SPAIR64__(v26, v12) < 0 || v43 < 0 )
          {
            v10 = -2147286789;
            goto LABEL_51;
          }
          v14 = v12 - v30;
          if ( a3.QuadPart > v12 - v30 )
            a3.QuadPart = v12 - v30;
          if ( v14 <= v43 - v31
            || (v13 = v14 + v31,
                v10 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64))(*(_QWORD *)a2 + 48LL))(
                        a2,
                        v14 + v31),
                v10 >= 0) )
          {
            pv = CoTaskMemAlloc(LowPart);
            v15 = pv;
            if ( !pv )
            {
              v10 = -2147287032;
              goto LABEL_51;
            }
            v16 = 1;
            v24 = 1;
            if ( v30 >= v31 )
            {
              v18 = a2;
              v17 = this;
            }
            else
            {
              v25 = v12 - LowPart;
              v17 = this;
              v10 = (*(__int64 (__fastcall **)(FileStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)this + 40LL))(
                      this,
                      v25,
                      0,
                      0);
              if ( v10 < 0
                || (v23 = v13 - LowPart,
                    v18 = a2,
                    v24 = 0,
                    v10 = (*(__int64 (__fastcall **)(struct IStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                            a2,
                            v23,
                            0,
                            0),
                    v10 < 0) )
              {
LABEL_49:
                CoTaskMemFree(pv);
                goto LABEL_51;
              }
              v15 = pv;
              v16 = 0;
            }
            if ( a3.QuadPart <= LowPart )
              LowPart = a3.LowPart;
            while ( a3.QuadPart )
            {
              v10 = (*(__int64 (__fastcall **)(FileStream *, void *, _QWORD, unsigned int *))(*(_QWORD *)v17 + 24LL))(
                      v17,
                      v15,
                      LowPart,
                      &v28);
              if ( v10 < 0 )
                goto LABEL_49;
              if ( v28 != LowPart )
              {
                v10 = -2147287010;
                goto LABEL_49;
              }
              v19 = *(_QWORD *)v18;
              v8 += v28;
              v32 = v8;
              v10 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, unsigned int *))(v19 + 32))(
                      v18,
                      pv,
                      LowPart,
                      &v29);
              if ( v10 < 0 )
                goto LABEL_49;
              if ( v29 != LowPart )
              {
                v10 = -2147287011;
                goto LABEL_49;
              }
              v16 = v24;
              v34 = LowPart;
              v35 = LowPart;
              v9 += v29;
              a3.QuadPart -= LowPart;
              v33 = v9;
              if ( a3.QuadPart <= LowPart )
                LowPart = a3.LowPart;
              if ( !v24 && a3.QuadPart )
              {
                v36 = LowPart + 0x2000;
                v37 = -v36;
                v10 = (*(__int64 (__fastcall **)(FileStream *, __int64, __int64, _QWORD))(*(_QWORD *)v17 + 40LL))(
                        v17,
                        -v36,
                        1,
                        0);
                if ( v10 < 0 )
                  goto LABEL_49;
                v38 = LowPart + 0x2000;
                v10 = (*(__int64 (__fastcall **)(struct IStream *, __int64, __int64))(*(_QWORD *)v18 + 40LL))(
                        v18,
                        -v38,
                        1);
                if ( v10 < 0 )
                  goto LABEL_49;
                v16 = v24;
              }
              v15 = pv;
            }
            if ( v16
              || (v30 += v8,
                  v10 = (*(__int64 (__fastcall **)(FileStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(
                          v17,
                          v30,
                          0,
                          0),
                  v10 >= 0)
              && (v31 += v9,
                  v10 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 40LL))(
                          v18,
                          v31,
                          0,
                          0),
                  v10 >= 0) )
            {
              if ( v40 )
              {
                LODWORD(v32) = v8;
                v40->QuadPart = v32;
              }
              if ( v41 )
              {
                LODWORD(v33) = v9;
                v41->QuadPart = v33;
              }
            }
            goto LABEL_49;
          }
        }
      }
    }
  }
LABEL_51:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180133100  push    rbp
0x180133102  push    rbx
0x180133103  push    rsi
0x180133104  push    rdi
0x180133105  push    r12
0x180133107  push    r13
0x180133109  push    r14
0x18013310b  push    r15
0x18013310d  lea     rbp, [rsp-28h]
0x180133112  sub     rsp, 128h
0x180133119  mov     rax, cs:__security_cookie
0x180133120  xor     rax, rsp
0x180133123  mov     [rbp+60h+var_50], rax
0x180133127  mov     rax, [rbp+60h+arg_20]
0x18013312e  xor     r12d, r12d
0x180133131  mov     rbx, r8
0x180133134  mov     [rsp+160h+var_110], rdx
0x180133139  mov     rdi, rdx
0x18013313c  mov     [rsp+160h+var_128], rcx
0x180133141  mov     rsi, rcx
0x180133144  mov     [rbp+60h+var_B0], r9
0x180133148  lea     r8d, [r12+50h]; Size
0x18013314d  mov     [rbp+60h+var_A8], rax
0x180133151  xor     edx, edx; Val
0x180133153  mov     [rsp+160h+var_108], r12d
0x180133158  lea     rcx, [rbp+60h+var_A0]; void *
0x18013315c  mov     [rsp+160h+var_104], r12d
0x180133161  mov     r15d, r12d
0x180133164  mov     [rsp+160h+var_F0], r12
0x180133169  mov     r14d, r12d
0x18013316c  mov     [rsp+160h+var_E8], r12
0x180133171  mov     [rsp+160h+var_100], r12
0x180133176  mov     [rsp+160h+var_F8], r12
0x18013317b  call    memset_0
0x180133180  lea     rax, [rsi+8]
0x180133184  mov     [rbp+60h+lpCriticalSection], rbx
0x180133188  mov     rcx, rax; lpCriticalSection
0x18013318b  mov     [rbp+60h+lpCriticalSection], rax
0x18013318f  call    cs:__imp_EnterCriticalSection
0x180133196  nop     dword ptr [rax+rax+00h]
0x18013319b  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x1801331a0  jnz     short loc_1801331AD
0x1801331a2  mov     r12d, 80030102h
0x1801331a8  jmp     loc_180133659
0x1801331ad  test    rdi, rdi
0x1801331b0  jnz     short loc_1801331BD
0x1801331b2  mov     r12d, 80030057h
0x1801331b8  jmp     loc_180133659
0x1801331bd  mov     eax, 2000h
0x1801331c2  mov     [rsp+160h+pv], r12
0x1801331c7  cmp     rbx, rax
0x1801331ca  lea     r9, [rsp+160h+var_100]
0x1801331cf  mov     r13d, ebx
0x1801331d2  mov     r8d, 1
0x1801331d8  cmova   r13d, eax
0x1801331dc  mov     rdx, r12
0x1801331df  mov     rax, [rsi]
0x1801331e2  mov     rcx, rsi
0x1801331e5  mov     rax, [rax+28h]
0x1801331e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801331ee  mov     r12d, eax
0x1801331f1  test    eax, eax
0x1801331f3  js      loc_180133659
0x1801331f9  mov     rax, [rdi]
0x1801331fc  lea     r9, [rsp+160h+var_F8]
0x180133201  mov     r8d, 1
0x180133207  mov     [rsp+160h+pv], r14
0x18013320c  mov     rdx, r14
0x18013320f  mov     rcx, rdi
0x180133212  mov     rax, [rax+28h]
0x180133216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013321b  mov     r12d, eax
0x18013321e  test    eax, eax
0x180133220  js      loc_180133659
0x180133226  mov     rax, [rsi]
0x180133229  lea     rdx, [rbp+60h+var_A0]
0x18013322d  mov     r8d, 1
0x180133233  mov     rcx, rsi
0x180133236  mov     rax, [rax+60h]
0x18013323a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013323f  mov     r12d, eax
0x180133242  test    eax, eax
0x180133244  js      loc_180133659
0x18013324a  mov     rax, [rdi]
0x18013324d  lea     rdx, [rbp+60h+var_A0]
0x180133251  mov     rsi, [rbp+60h+var_90]
0x180133255  mov     r8d, 1
0x18013325b  mov     rcx, rdi
0x18013325e  mov     [rsp+160h+var_118], rsi
0x180133263  mov     rax, [rax+60h]
0x180133267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013326c  mov     r12d, eax
0x18013326f  test    eax, eax
0x180133271  js      loc_180133659
0x180133277  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18013327b  mov     rdi, [rbp+60h+var_90]
0x18013327f  mov     dword ptr [rsp+160h+pv+4], eax
0x180133283  mov     dword ptr [rsp+160h+pv], esi
0x180133287  cmp     [rsp+160h+pv], r14
0x18013328c  jl      loc_180133653
0x180133292  mov     rax, rdi
0x180133295  mov     dword ptr [rsp+160h+pv], edi
0x180133299  shr     rax, 20h
0x18013329d  mov     dword ptr [rsp+160h+pv+4], eax
0x1801332a1  cmp     [rsp+160h+pv], r14
0x1801332a6  jl      loc_180133653
0x1801332ac  mov     rax, [rsp+160h+var_F8]
0x1801332b1  mov     rdx, rsi
0x1801332b4  sub     rdx, [rsp+160h+var_100]
0x1801332b9  mov     rcx, rdi
0x1801332bc  cmp     rbx, rdx
0x1801332bf  cmova   rbx, rdx
0x1801332c3  sub     rcx, rax
0x1801332c6  cmp     rdx, rcx
0x1801332c9  jbe     short loc_1801332FF
0x1801332cb  mov     rcx, [rsp+160h+var_110]
0x1801332d0  lea     rdi, [rdx+rax]
0x1801332d4  mov     rax, rdi
0x1801332d7  mov     dword ptr [rsp+160h+pv], edi
0x1801332db  shr     rax, 20h
0x1801332df  mov     dword ptr [rsp+160h+pv+4], eax
0x1801332e3  mov     rax, [rcx]
0x1801332e6  mov     rdx, [rsp+160h+pv]
0x1801332eb  mov     rax, [rax+30h]
0x1801332ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801332f4  mov     r12d, eax
0x1801332f7  test    eax, eax
0x1801332f9  js      loc_180133659
0x1801332ff  mov     ecx, r13d; cb
0x180133302  call    cs:__imp_CoTaskMemAlloc
0x180133309  nop     dword ptr [rax+rax+00h]
0x18013330e  mov     [rsp+160h+pv], rax
0x180133313  mov     rcx, rax
0x180133316  test    rax, rax
0x180133319  jnz     short loc_180133326
0x18013331b  mov     r12d, 80030008h
0x180133321  jmp     loc_180133659
0x180133326  mov     rax, [rsp+160h+var_F8]
0x18013332b  mov     edx, 1
0x180133330  mov     dword ptr [rsp+160h+var_120], edx
0x180133334  cmp     [rsp+160h+var_100], rax
0x180133339  jnb     loc_1801333F1
0x18013333f  mov     dword ptr [rsp+160h+var_120], r13d
0x180133344  xor     r9d, r9d
0x180133347  mov     dword ptr [rsp+160h+var_120+4], r14d
0x18013334c  xor     r8d, r8d
0x18013334f  sub     rsi, [rsp+160h+var_120]
0x180133354  mov     rax, rsi
0x180133357  mov     dword ptr [rsp+160h+var_120], esi
0x18013335b  mov     rsi, [rsp+160h+var_128]
0x180133360  shr     rax, 20h
0x180133364  mov     rcx, rsi
0x180133367  mov     dword ptr [rsp+160h+var_120+4], eax
0x18013336b  mov     rdx, [rsp+160h+var_120]
0x180133370  mov     rax, [rsi]
0x180133373  mov     rax, [rax+28h]
0x180133377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013337c  mov     r12d, eax
0x18013337f  test    eax, eax
0x180133381  js      loc_180133640
0x180133387  mov     dword ptr [rsp+160h+var_128], r13d
0x18013338c  xor     r9d, r9d
0x18013338f  mov     dword ptr [rsp+160h+var_128+4], r14d
0x180133394  xor     r8d, r8d
0x180133397  sub     rdi, [rsp+160h+var_128]
0x18013339c  mov     rax, rdi
0x18013339f  mov     dword ptr [rsp+160h+var_128], edi
0x1801333a3  mov     rdi, [rsp+160h+var_110]
0x1801333a8  shr     rax, 20h
0x1801333ac  mov     rcx, rdi
0x1801333af  mov     dword ptr [rsp+160h+var_128+4], eax
0x1801333b3  mov     rdx, [rsp+160h+var_128]
0x1801333b8  mov     rax, [rdi]
0x1801333bb  mov     dword ptr [rsp+160h+var_120], r14d
0x1801333c0  mov     rax, [rax+28h]
0x1801333c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801333c9  mov     r12d, eax
0x1801333cc  test    eax, eax
0x1801333ce  js      loc_180133640
0x1801333d4  mov     rcx, [rsp+160h+pv]
0x1801333d9  mov     edx, r14d
0x1801333dc  mov     dword ptr [rsp+160h+var_128], r13d
0x1801333e1  mov     dword ptr [rsp+160h+var_128+4], r14d
0x1801333e6  cmp     rbx, [rsp+160h+var_128]
0x1801333eb  cmovbe  r13d, ebx
0x1801333ef  jmp     short loc_180133402
0x1801333f1  mov     rdi, [rsp+160h+var_110]
0x1801333f6  mov     rsi, [rsp+160h+var_128]
0x1801333fb  jmp     short loc_1801333DC
0x1801333fd  mov     rcx, [rsp+160h+pv]
0x180133402  test    rbx, rbx
0x180133405  jz      loc_180133586
0x18013340b  mov     rax, [rsi]
0x18013340e  lea     r9, [rsp+160h+var_108]
0x180133413  mov     rdx, rcx
0x180133416  mov     r8d, r13d
0x180133419  mov     rcx, rsi
0x18013341c  mov     rax, [rax+18h]
0x180133420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180133425  mov     r12d, eax
0x180133428  test    eax, eax
0x18013342a  js      loc_180133640
0x180133430  mov     eax, [rsp+160h+var_108]
0x180133434  cmp     eax, r13d
0x180133437  jnz     loc_18013357B
0x18013343d  mov     rdx, [rsp+160h+pv]
0x180133442  lea     r9, [rsp+160h+var_104]
0x180133447  mov     dword ptr [rsp+160h+var_128], eax
0x18013344b  mov     r8d, r13d
0x18013344e  mov     rax, [rdi]
0x180133451  mov     rcx, rdi
0x180133454  mov     dword ptr [rsp+160h+var_128+4], 0
0x18013345c  add     r15, [rsp+160h+var_128]
0x180133461  mov     [rsp+160h+var_F0], r15
0x180133466  mov     rax, [rax+20h]
0x18013346a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013346f  mov     r12d, eax
0x180133472  test    eax, eax
0x180133474  js      loc_180133640
0x18013347a  mov     eax, [rsp+160h+var_104]
0x18013347e  cmp     eax, r13d
0x180133481  jnz     loc_180133570
0x180133487  mov     edx, dword ptr [rsp+160h+var_120]
0x18013348b  mov     dword ptr [rbp+60h+var_E0], r13d
0x18013348f  mov     dword ptr [rbp+60h+var_D8], r13d
0x180133493  mov     dword ptr [rsp+160h+var_110], eax
0x180133497  mov     dword ptr [rsp+160h+var_110+4], 0
0x18013349f  add     r14, [rsp+160h+var_110]
0x1801334a4  mov     dword ptr [rbp+60h+var_E0+4], 0
0x1801334ab  sub     rbx, [rbp+60h+var_E0]
0x1801334af  mov     dword ptr [rbp+60h+var_D8+4], 0
0x1801334b6  cmp     rbx, [rbp+60h+var_D8]
0x1801334ba  mov     [rsp+160h+var_E8], r14
0x1801334bf  cmovbe  r13d, ebx
0x1801334c3  test    edx, edx
0x1801334c5  jnz     loc_1801333FD
0x1801334cb  test    rbx, rbx
0x1801334ce  jz      loc_1801333FD
0x1801334d4  mov     dword ptr [rbp+60h+var_D0+4], edx
0x1801334d7  lea     eax, [r13+2000h]
0x1801334de  mov     dword ptr [rbp+60h+var_D0], eax
0x1801334e1  lea     r8d, [rdx+1]
0x1801334e5  mov     rcx, [rbp+60h+var_D0]
0x1801334e9  xor     r9d, r9d
0x1801334ec  neg     rcx
0x1801334ef  mov     rax, rcx
0x1801334f2  mov     dword ptr [rbp+60h+var_C8], ecx
0x1801334f5  shr     rax, 20h
0x1801334f9  mov     rcx, rsi
0x1801334fc  mov     dword ptr [rbp+60h+var_C8+4], eax
0x1801334ff  mov     rax, [rsi]
0x180133502  mov     rdx, [rbp+60h+var_C8]
0x180133506  mov     rax, [rax+28h]
0x18013350a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013350f  mov     r12d, eax
0x180133512  test    eax, eax
0x180133514  js      loc_180133640
0x18013351a  lea     eax, [r13+2000h]
0x180133521  mov     dword ptr [rbp+60h+var_C0+4], 0
0x180133528  mov     dword ptr [rbp+60h+var_C0], eax
0x18013352b  xor     r9d, r9d
0x18013352e  mov     rcx, [rbp+60h+var_C0]
0x180133532  neg     rcx
0x180133535  mov     rax, rcx
0x180133538  mov     dword ptr [rsp+160h+var_118], ecx
0x18013353c  shr     rax, 20h
0x180133540  lea     r8d, [r9+1]
0x180133544  mov     dword ptr [rsp+160h+var_118+4], eax
0x180133548  mov     rcx, rdi
0x18013354b  mov     rax, [rdi]
0x18013354e  mov     rdx, [rsp+160h+var_118]
0x180133553  mov     rax, [rax+28h]
0x180133557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013355c  mov     r12d, eax
0x18013355f  test    eax, eax
0x180133561  js      loc_180133640
0x180133567  mov     edx, dword ptr [rsp+160h+var_120]
0x18013356b  jmp     loc_1801333FD
0x180133570  mov     r12d, 8003001Dh
0x180133576  jmp     loc_180133640
0x18013357b  mov     r12d, 8003001Eh
0x180133581  jmp     loc_180133640
0x180133586  test    edx, edx
0x180133588  jnz     short loc_180133604
0x18013358a  mov     rax, [rsp+160h+var_100]
0x18013358f  xor     r9d, r9d
0x180133592  add     rax, r15
0x180133595  xor     r8d, r8d
0x180133598  mov     rdx, rax
0x18013359b  mov     dword ptr [rsp+160h+var_118], eax
0x18013359f  mov     [rsp+160h+var_100], rax
0x1801335a4  mov     rcx, rsi
0x1801335a7  mov     rax, [rsi]
0x1801335aa  shr     rdx, 20h
0x1801335ae  mov     dword ptr [rsp+160h+var_118+4], edx
0x1801335b2  mov     rdx, [rsp+160h+var_118]
0x1801335b7  mov     rax, [rax+28h]
0x1801335bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801335c0  mov     r12d, eax
0x1801335c3  test    eax, eax
  ... truncated ...
```
