# FileStream::CopyTo(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *)

- ea: `0x18012ade0`
- end: `0x18012b354`
- name: `?CopyTo@FileStream@@UEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2@Z`
- size: `1396`
- prototype: `__int64 __fastcall(FileStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800fe680`
- `0x1800ff04c`
- `0x18012ade0`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ae6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012ae6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b32b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012b32b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012b319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012afdc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012afdc`

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
0x18012ade0  push    rbp
0x18012ade2  push    rbx
0x18012ade3  push    rsi
0x18012ade4  push    rdi
0x18012ade5  push    r12
0x18012ade7  push    r13
0x18012ade9  push    r14
0x18012adeb  push    r15
0x18012aded  lea     rbp, [rsp-28h]
0x18012adf2  sub     rsp, 128h
0x18012adf9  mov     rax, cs:__security_cookie
0x18012ae00  xor     rax, rsp
0x18012ae03  mov     [rbp+60h+var_50], rax
0x18012ae07  mov     rax, [rbp+60h+arg_20]
0x18012ae0e  xor     r12d, r12d
0x18012ae11  mov     rbx, r8
0x18012ae14  mov     [rsp+160h+var_110], rdx
0x18012ae19  mov     rdi, rdx
0x18012ae1c  mov     [rsp+160h+var_128], rcx
0x18012ae21  mov     rsi, rcx
0x18012ae24  mov     [rbp+60h+var_B0], r9
0x18012ae28  lea     r8d, [r12+50h]; Size
0x18012ae2d  mov     [rbp+60h+var_A8], rax
0x18012ae31  xor     edx, edx; Val
0x18012ae33  mov     [rsp+160h+var_108], r12d
0x18012ae38  lea     rcx, [rbp+60h+var_A0]; void *
0x18012ae3c  mov     [rsp+160h+var_104], r12d
0x18012ae41  mov     r15d, r12d
0x18012ae44  mov     [rsp+160h+var_F0], r12
0x18012ae49  mov     r14d, r12d
0x18012ae4c  mov     [rsp+160h+var_E8], r12
0x18012ae51  mov     [rsp+160h+var_100], r12
0x18012ae56  mov     [rsp+160h+var_F8], r12
0x18012ae5b  call    memset_0
0x18012ae60  lea     rax, [rsi+8]
0x18012ae64  mov     [rbp+60h+lpCriticalSection], rbx
0x18012ae68  mov     rcx, rax; lpCriticalSection
0x18012ae6b  mov     [rbp+60h+lpCriticalSection], rax
0x18012ae6f  call    cs:__imp_EnterCriticalSection
0x18012ae75  cmp     qword ptr [rsi+48h], 0FFFFFFFFFFFFFFFFh
0x18012ae7a  jnz     short loc_18012AE87
0x18012ae7c  mov     r12d, 80030102h
0x18012ae82  jmp     loc_18012B327
0x18012ae87  test    rdi, rdi
0x18012ae8a  jnz     short loc_18012AE97
0x18012ae8c  mov     r12d, 80030057h
0x18012ae92  jmp     loc_18012B327
0x18012ae97  mov     eax, 2000h
0x18012ae9c  mov     [rsp+160h+pv], r12
0x18012aea1  cmp     rbx, rax
0x18012aea4  lea     r9, [rsp+160h+var_100]
0x18012aea9  mov     r13d, ebx
0x18012aeac  mov     r8d, 1
0x18012aeb2  cmova   r13d, eax
0x18012aeb6  mov     rdx, r12
0x18012aeb9  mov     rax, [rsi]
0x18012aebc  mov     rcx, rsi
0x18012aebf  mov     rax, [rax+28h]
0x18012aec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aec8  mov     r12d, eax
0x18012aecb  test    eax, eax
0x18012aecd  js      loc_18012B327
0x18012aed3  mov     rax, [rdi]
0x18012aed6  lea     r9, [rsp+160h+var_F8]
0x18012aedb  mov     r8d, 1
0x18012aee1  mov     [rsp+160h+pv], r14
0x18012aee6  mov     rdx, r14
0x18012aee9  mov     rcx, rdi
0x18012aeec  mov     rax, [rax+28h]
0x18012aef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012aef5  mov     r12d, eax
0x18012aef8  test    eax, eax
0x18012aefa  js      loc_18012B327
0x18012af00  mov     rax, [rsi]
0x18012af03  lea     rdx, [rbp+60h+var_A0]
0x18012af07  mov     r8d, 1
0x18012af0d  mov     rcx, rsi
0x18012af10  mov     rax, [rax+60h]
0x18012af14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012af19  mov     r12d, eax
0x18012af1c  test    eax, eax
0x18012af1e  js      loc_18012B327
0x18012af24  mov     rax, [rdi]
0x18012af27  lea     rdx, [rbp+60h+var_A0]
0x18012af2b  mov     rsi, [rbp+60h+var_90]
0x18012af2f  mov     r8d, 1
0x18012af35  mov     rcx, rdi
0x18012af38  mov     [rsp+160h+var_118], rsi
0x18012af3d  mov     rax, [rax+60h]
0x18012af41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012af46  mov     r12d, eax
0x18012af49  test    eax, eax
0x18012af4b  js      loc_18012B327
0x18012af51  mov     eax, dword ptr [rsp+160h+var_118+4]
0x18012af55  mov     rdi, [rbp+60h+var_90]
0x18012af59  mov     dword ptr [rsp+160h+pv+4], eax
0x18012af5d  mov     dword ptr [rsp+160h+pv], esi
0x18012af61  cmp     [rsp+160h+pv], r14
0x18012af66  jl      loc_18012B321
0x18012af6c  mov     rax, rdi
0x18012af6f  mov     dword ptr [rsp+160h+pv], edi
0x18012af73  shr     rax, 20h
0x18012af77  mov     dword ptr [rsp+160h+pv+4], eax
0x18012af7b  cmp     [rsp+160h+pv], r14
0x18012af80  jl      loc_18012B321
0x18012af86  mov     rax, [rsp+160h+var_F8]
0x18012af8b  mov     rdx, rsi
0x18012af8e  sub     rdx, [rsp+160h+var_100]
0x18012af93  mov     rcx, rdi
0x18012af96  cmp     rbx, rdx
0x18012af99  cmova   rbx, rdx
0x18012af9d  sub     rcx, rax
0x18012afa0  cmp     rdx, rcx
0x18012afa3  jbe     short loc_18012AFD9
0x18012afa5  mov     rcx, [rsp+160h+var_110]
0x18012afaa  lea     rdi, [rdx+rax]
0x18012afae  mov     rax, rdi
0x18012afb1  mov     dword ptr [rsp+160h+pv], edi
0x18012afb5  shr     rax, 20h
0x18012afb9  mov     dword ptr [rsp+160h+pv+4], eax
0x18012afbd  mov     rax, [rcx]
0x18012afc0  mov     rdx, [rsp+160h+pv]
0x18012afc5  mov     rax, [rax+30h]
0x18012afc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012afce  mov     r12d, eax
0x18012afd1  test    eax, eax
0x18012afd3  js      loc_18012B327
0x18012afd9  mov     ecx, r13d; cb
0x18012afdc  call    cs:__imp_CoTaskMemAlloc
0x18012afe2  mov     [rsp+160h+pv], rax
0x18012afe7  mov     rcx, rax
0x18012afea  test    rax, rax
0x18012afed  jnz     short loc_18012AFFA
0x18012afef  mov     r12d, 80030008h
0x18012aff5  jmp     loc_18012B327
0x18012affa  mov     rax, [rsp+160h+var_F8]
0x18012afff  mov     edx, 1
0x18012b004  mov     dword ptr [rsp+160h+var_120], edx
0x18012b008  cmp     [rsp+160h+var_100], rax
0x18012b00d  jnb     loc_18012B0C5
0x18012b013  mov     dword ptr [rsp+160h+var_120], r13d
0x18012b018  xor     r9d, r9d
0x18012b01b  mov     dword ptr [rsp+160h+var_120+4], r14d
0x18012b020  xor     r8d, r8d
0x18012b023  sub     rsi, [rsp+160h+var_120]
0x18012b028  mov     rax, rsi
0x18012b02b  mov     dword ptr [rsp+160h+var_120], esi
0x18012b02f  mov     rsi, [rsp+160h+var_128]
0x18012b034  shr     rax, 20h
0x18012b038  mov     rcx, rsi
0x18012b03b  mov     dword ptr [rsp+160h+var_120+4], eax
0x18012b03f  mov     rdx, [rsp+160h+var_120]
0x18012b044  mov     rax, [rsi]
0x18012b047  mov     rax, [rax+28h]
0x18012b04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b050  mov     r12d, eax
0x18012b053  test    eax, eax
0x18012b055  js      loc_18012B314
0x18012b05b  mov     dword ptr [rsp+160h+var_128], r13d
0x18012b060  xor     r9d, r9d
0x18012b063  mov     dword ptr [rsp+160h+var_128+4], r14d
0x18012b068  xor     r8d, r8d
0x18012b06b  sub     rdi, [rsp+160h+var_128]
0x18012b070  mov     rax, rdi
0x18012b073  mov     dword ptr [rsp+160h+var_128], edi
0x18012b077  mov     rdi, [rsp+160h+var_110]
0x18012b07c  shr     rax, 20h
0x18012b080  mov     rcx, rdi
0x18012b083  mov     dword ptr [rsp+160h+var_128+4], eax
0x18012b087  mov     rdx, [rsp+160h+var_128]
0x18012b08c  mov     rax, [rdi]
0x18012b08f  mov     dword ptr [rsp+160h+var_120], r14d
0x18012b094  mov     rax, [rax+28h]
0x18012b098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b09d  mov     r12d, eax
0x18012b0a0  test    eax, eax
0x18012b0a2  js      loc_18012B314
0x18012b0a8  mov     rcx, [rsp+160h+pv]
0x18012b0ad  mov     edx, r14d
0x18012b0b0  mov     dword ptr [rsp+160h+var_128], r13d
0x18012b0b5  mov     dword ptr [rsp+160h+var_128+4], r14d
0x18012b0ba  cmp     rbx, [rsp+160h+var_128]
0x18012b0bf  cmovbe  r13d, ebx
0x18012b0c3  jmp     short loc_18012B0D6
0x18012b0c5  mov     rdi, [rsp+160h+var_110]
0x18012b0ca  mov     rsi, [rsp+160h+var_128]
0x18012b0cf  jmp     short loc_18012B0B0
0x18012b0d1  mov     rcx, [rsp+160h+pv]
0x18012b0d6  test    rbx, rbx
0x18012b0d9  jz      loc_18012B25A
0x18012b0df  mov     rax, [rsi]
0x18012b0e2  lea     r9, [rsp+160h+var_108]
0x18012b0e7  mov     rdx, rcx
0x18012b0ea  mov     r8d, r13d
0x18012b0ed  mov     rcx, rsi
0x18012b0f0  mov     rax, [rax+18h]
0x18012b0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b0f9  mov     r12d, eax
0x18012b0fc  test    eax, eax
0x18012b0fe  js      loc_18012B314
0x18012b104  mov     eax, [rsp+160h+var_108]
0x18012b108  cmp     eax, r13d
0x18012b10b  jnz     loc_18012B24F
0x18012b111  mov     rdx, [rsp+160h+pv]
0x18012b116  lea     r9, [rsp+160h+var_104]
0x18012b11b  mov     dword ptr [rsp+160h+var_128], eax
0x18012b11f  mov     r8d, r13d
0x18012b122  mov     rax, [rdi]
0x18012b125  mov     rcx, rdi
0x18012b128  mov     dword ptr [rsp+160h+var_128+4], 0
0x18012b130  add     r15, [rsp+160h+var_128]
0x18012b135  mov     [rsp+160h+var_F0], r15
0x18012b13a  mov     rax, [rax+20h]
0x18012b13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b143  mov     r12d, eax
0x18012b146  test    eax, eax
0x18012b148  js      loc_18012B314
0x18012b14e  mov     eax, [rsp+160h+var_104]
0x18012b152  cmp     eax, r13d
0x18012b155  jnz     loc_18012B244
0x18012b15b  mov     edx, dword ptr [rsp+160h+var_120]
0x18012b15f  mov     dword ptr [rbp+60h+var_E0], r13d
0x18012b163  mov     dword ptr [rbp+60h+var_D8], r13d
0x18012b167  mov     dword ptr [rsp+160h+var_110], eax
0x18012b16b  mov     dword ptr [rsp+160h+var_110+4], 0
0x18012b173  add     r14, [rsp+160h+var_110]
0x18012b178  mov     dword ptr [rbp+60h+var_E0+4], 0
0x18012b17f  sub     rbx, [rbp+60h+var_E0]
0x18012b183  mov     dword ptr [rbp+60h+var_D8+4], 0
0x18012b18a  cmp     rbx, [rbp+60h+var_D8]
0x18012b18e  mov     [rsp+160h+var_E8], r14
0x18012b193  cmovbe  r13d, ebx
0x18012b197  test    edx, edx
0x18012b199  jnz     loc_18012B0D1
0x18012b19f  test    rbx, rbx
0x18012b1a2  jz      loc_18012B0D1
0x18012b1a8  mov     dword ptr [rbp+60h+var_D0+4], edx
0x18012b1ab  lea     eax, [r13+2000h]
0x18012b1b2  mov     dword ptr [rbp+60h+var_D0], eax
0x18012b1b5  lea     r8d, [rdx+1]
0x18012b1b9  mov     rcx, [rbp+60h+var_D0]
0x18012b1bd  xor     r9d, r9d
0x18012b1c0  neg     rcx
0x18012b1c3  mov     rax, rcx
0x18012b1c6  mov     dword ptr [rbp+60h+var_C8], ecx
0x18012b1c9  shr     rax, 20h
0x18012b1cd  mov     rcx, rsi
0x18012b1d0  mov     dword ptr [rbp+60h+var_C8+4], eax
0x18012b1d3  mov     rax, [rsi]
0x18012b1d6  mov     rdx, [rbp+60h+var_C8]
0x18012b1da  mov     rax, [rax+28h]
0x18012b1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b1e3  mov     r12d, eax
0x18012b1e6  test    eax, eax
0x18012b1e8  js      loc_18012B314
0x18012b1ee  lea     eax, [r13+2000h]
0x18012b1f5  mov     dword ptr [rbp+60h+var_C0+4], 0
0x18012b1fc  mov     dword ptr [rbp+60h+var_C0], eax
0x18012b1ff  xor     r9d, r9d
0x18012b202  mov     rcx, [rbp+60h+var_C0]
0x18012b206  neg     rcx
0x18012b209  mov     rax, rcx
0x18012b20c  mov     dword ptr [rsp+160h+var_118], ecx
0x18012b210  shr     rax, 20h
0x18012b214  lea     r8d, [r9+1]
0x18012b218  mov     dword ptr [rsp+160h+var_118+4], eax
0x18012b21c  mov     rcx, rdi
0x18012b21f  mov     rax, [rdi]
0x18012b222  mov     rdx, [rsp+160h+var_118]
0x18012b227  mov     rax, [rax+28h]
0x18012b22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b230  mov     r12d, eax
0x18012b233  test    eax, eax
0x18012b235  js      loc_18012B314
0x18012b23b  mov     edx, dword ptr [rsp+160h+var_120]
0x18012b23f  jmp     loc_18012B0D1
0x18012b244  mov     r12d, 8003001Dh
0x18012b24a  jmp     loc_18012B314
0x18012b24f  mov     r12d, 8003001Eh
0x18012b255  jmp     loc_18012B314
0x18012b25a  test    edx, edx
0x18012b25c  jnz     short loc_18012B2D8
0x18012b25e  mov     rax, [rsp+160h+var_100]
0x18012b263  xor     r9d, r9d
0x18012b266  add     rax, r15
0x18012b269  xor     r8d, r8d
0x18012b26c  mov     rdx, rax
0x18012b26f  mov     dword ptr [rsp+160h+var_118], eax
0x18012b273  mov     [rsp+160h+var_100], rax
0x18012b278  mov     rcx, rsi
0x18012b27b  mov     rax, [rsi]
0x18012b27e  shr     rdx, 20h
0x18012b282  mov     dword ptr [rsp+160h+var_118+4], edx
0x18012b286  mov     rdx, [rsp+160h+var_118]
0x18012b28b  mov     rax, [rax+28h]
0x18012b28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b294  mov     r12d, eax
0x18012b297  test    eax, eax
0x18012b299  js      short loc_18012B314
0x18012b29b  mov     rax, [rsp+160h+var_F8]
  ... truncated ...
```
