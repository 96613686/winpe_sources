# RepoMan::Legacy::StreamManifest::GetStreamUnits(RepoMan::Legacy::FileData &)

- ea: `0x1800c7e38`
- end: `0x1800c819c`
- name: `?GetStreamUnits@StreamManifest@Legacy@RepoMan@@QEAA?AU?$FieldNItems@VStreamUnit@Legacy@RepoMan@@@Meta@3@AEAVFileData@23@@Z`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c819c`

## callees

- `0x180013b14`
- `0x18001c448`
- `0x180038a34`
- `0x1800c7e38`
- `0x1800d0a84`
- `0x1800d4f48`
- `0x1800dfffc`
- `0x18018aed8`
- `0x18019f7a0`
- `0x18019f800`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c7f25`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800c7f25`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c80ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c813d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c80ec`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800c813d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8136`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800c8136`

## string_xrefs

- `0x1800c815d`: `src\repoman\src\inc\StreamManifest.hpp`
- `0x1800c8184`: `src\repoman\src\inc\StreamManifest.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall RepoMan::Legacy::StreamManifest::GetStreamUnits(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rdx
  __int64 *v7; // r15
  unsigned int v8; // eax
  const char *v9; // r9
  void *v10; // rsi
  void *v11; // rax
  void *v12; // r14
  __int64 v13; // rcx
  unsigned int v14; // eax
  const char *v15; // r9
  __int64 v16; // rcx
  unsigned int v17; // eax
  const char *v18; // r9
  __int64 v19; // r9
  void *v20; // rdx
  void *v21; // rcx
  const void *v22; // rax
  _BYTE *v23; // rcx
  _BYTE *v24; // rcx
  __int16 v25; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 v26; // [rsp+32h] [rbp-37h]
  unsigned int v27; // [rsp+34h] [rbp-35h]
  const void *Src; // [rsp+38h] [rbp-31h] BYREF
  void *Src_8[2]; // [rsp+40h] [rbp-29h]
  int v30; // [rsp+50h] [rbp-19h]
  int v31; // [rsp+58h] [rbp-11h]
  int v32; // [rsp+60h] [rbp-9h]
  int v33; // [rsp+68h] [rbp-1h]
  int v34; // [rsp+70h] [rbp+7h]
  __int64 v35; // [rsp+78h] [rbp+Fh]
  __int64 v36; // [rsp+80h] [rbp+17h]
  __int64 v37; // [rsp+88h] [rbp+1Fh]
  __int16 *v38; // [rsp+E8h] [rbp+7Fh] BYREF

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  a2[3] = 0;
  a2[4] = 0;
  v5 = *(unsigned int *)(a3 + 64);
  a2[3] = v5;
  if ( v5 )
  {
    v7 = (__int64 *)(a1 + 216);
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(a1 + 216) + 40LL))(
           *(_QWORD *)(a1 + 216),
           v5,
           0,
           0);
    RepoMan::RaiseExceptionIfFailed((RepoMan *)v8, 361, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v9);
    while ( 1 )
    {
      v25 = 0;
      v26 = 0;
      v27 = 0;
      Src = 0;
      *(_OWORD *)Src_8 = 0;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      if ( _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] < 0x20 )
      {
        v10 = Src_8[0];
        v11 = malloc(0x20u);
        v12 = v11;
        if ( !v11 )
          std::_Xbad_alloc();
        memmove(v11, Src, (char *)Src_8[0] - (char *)Src);
        std::vector<unsigned char>::_Change_array(&Src, v12, v10, 32);
      }
      v13 = *v7;
      v38 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int16 **))(*(_QWORD *)v13 + 40LL))(v13, 0, 1, &v38);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v14, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v15);
      v35 = (unsigned int)v38;
      v38 = &v25;
      ___for_each__0A_V_lambda_1___1__Read_StreamUnit_Legacy_RepoMan__QEAAXAEAV__ComPtr_UIStream___5__Z_AEAV65____TypeList_UField4Bytes_Meta_RepoMan__U123_U123_U123_U123_UFieldNBytes_23_U123_UField1Byte_23_U523_U523__Meta_RepoMan__QEAAXAEBV_lambda_1___1__Read_StreamUnit_Legacy_2_QEAAXAEAV__ComPtr_UIStream___2__Z_0_Z(
        (__int64)&v25,
        (__int64)&v38,
        v7);
      if ( v27 > 2 )
        RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
          178,
          (unsigned int)"src\\repoman\\src\\inc\\StreamManifest.hpp",
          (unsigned int)"invalid type",
          -1941503407,
          8);
      if ( v26 > 1u )
        RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
          179,
          (unsigned int)"src\\repoman\\src\\inc\\StreamManifest.hpp",
          (unsigned int)"invalid state",
          -1941503407,
          8);
      v16 = *v7;
      v38 = 0;
      v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int16 **))(*(_QWORD *)v16 + 40LL))(v16, 0, 1, &v38);
      RepoMan::RaiseExceptionIfFailed((RepoMan *)v17, 353, (int)"src\\repoman\\src\\inc\\StreamBase.hpp", v18);
      v36 = (unsigned int)v38;
      if ( v34 != *(_QWORD *)(a3 + 88) )
        break;
      v19 = a2[1];
      if ( v19 == a2[2] )
      {
        std::vector<RepoMan::Legacy::StreamUnit>::_Emplace_reallocate<RepoMan::Legacy::StreamUnit>(a2, a2[1], &v25);
      }
      else
      {
        *(_WORD *)v19 = v25;
        *(_BYTE *)(v19 + 2) = v26;
        *(_DWORD *)(v19 + 4) = v27;
        v20 = Src_8[1];
        v21 = Src_8[0];
        *(_OWORD *)Src_8 = 0u;
        v22 = Src;
        Src = 0;
        *(_QWORD *)(v19 + 8) = v22;
        *(_QWORD *)(v19 + 16) = v21;
        *(_QWORD *)(v19 + 24) = v20;
        *(_DWORD *)(v19 + 32) = v30;
        *(_DWORD *)(v19 + 40) = v31;
        *(_DWORD *)(v19 + 48) = v32;
        *(_DWORD *)(v19 + 56) = v33;
        *(_DWORD *)(v19 + 64) = v34;
        *(_QWORD *)(v19 + 72) = v35;
        *(_QWORD *)(v19 + 80) = v36;
        *(_QWORD *)(v19 + 88) = v37;
        a2[1] += 96LL;
      }
      a2[4] = (unsigned int)RepoMan::StreamBase<>::Position(v7);
      v23 = Src;
      if ( Src )
      {
        if ( (void *)((char *)Src_8[1] - (char *)Src) >= (void *)0x1000 )
        {
          v23 = (_BYTE *)*((_QWORD *)Src - 1);
          if ( (unsigned __int64)((_BYTE *)Src - v23 - 8) > 0x1F )
            goto LABEL_20;
        }
        free(v23);
      }
    }
    v24 = Src;
    if ( Src )
    {
      if ( (void *)((char *)Src_8[1] - (char *)Src) >= (void *)0x1000 )
      {
        v24 = (_BYTE *)*((_QWORD *)Src - 1);
        if ( (unsigned __int64)((_BYTE *)Src - v24 - 8) > 0x1F )
LABEL_20:
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v24);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800c7e38  mov     [rsp-8+arg_8], rdx
0x1800c7e3d  push    rbp
0x1800c7e3e  push    rbx
0x1800c7e3f  push    rsi
0x1800c7e40  push    rdi
0x1800c7e41  push    r12
0x1800c7e43  push    r14
0x1800c7e45  push    r15
0x1800c7e47  lea     rbp, [rsp-27h]
0x1800c7e4c  sub     rsp, 90h
0x1800c7e53  mov     r12, r8
0x1800c7e56  mov     rdi, rdx
0x1800c7e59  mov     [rbp+57h+arg_10], 1
0x1800c7e60  xor     ebx, ebx
0x1800c7e62  mov     [rdx], rbx
0x1800c7e65  mov     [rdx+8], rbx
0x1800c7e69  mov     [rdx+10h], rbx
0x1800c7e6d  mov     [rdx+18h], rbx
0x1800c7e71  mov     [rdx+20h], rbx
0x1800c7e75  mov     [rbp+57h+arg_10], 1
0x1800c7e7c  mov     edx, [r8+40h]
0x1800c7e80  mov     [rdi+18h], rdx
0x1800c7e84  test    rdx, rdx
0x1800c7e87  jnz     short loc_1800C7E9E
0x1800c7e89  mov     rax, rdi
0x1800c7e8c  add     rsp, 90h
0x1800c7e93  pop     r15
0x1800c7e95  pop     r14
0x1800c7e97  pop     r12
0x1800c7e99  pop     rdi
0x1800c7e9a  pop     rsi
0x1800c7e9b  pop     rbx
0x1800c7e9c  pop     rbp
0x1800c7e9d  retn
0x1800c7e9e  lea     r15, [rcx+0D8h]
0x1800c7ea5  mov     rcx, [r15]
0x1800c7ea8  mov     rax, [rcx]
0x1800c7eab  xor     r9d, r9d
0x1800c7eae  xor     r8d, r8d
0x1800c7eb1  mov     rax, [rax+28h]
0x1800c7eb5  call    cs:__guard_dispatch_icall_fptr
0x1800c7ebb  mov     ecx, eax; this
0x1800c7ebd  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x1800c7ec4  mov     edx, 169h; int
0x1800c7ec9  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c7ece  nop
0x1800c7ecf  xor     eax, eax
0x1800c7ed1  mov     [rbp+57h+var_90], ax
0x1800c7ed5  mov     [rbp+57h+var_8E], al
0x1800c7ed8  mov     [rbp+57h+var_8C], eax
0x1800c7edb  xorps   xmm0, xmm0
0x1800c7ede  movups  xmmword ptr [rbp+57h+Src], xmm0
0x1800c7ee2  mov     [rbp+57h+Src], rbx
0x1800c7ee6  movdqa  xmmword ptr [rbp+57h+Src+8], xmm0
0x1800c7eeb  mov     [rbp+57h+var_70], eax
0x1800c7eee  mov     [rbp+57h+var_68], eax
0x1800c7ef1  mov     [rbp+57h+var_60], eax
0x1800c7ef4  mov     [rbp+57h+var_58], eax
0x1800c7ef7  mov     [rbp+57h+var_50], eax
0x1800c7efa  mov     [rbp+57h+var_48], rbx
0x1800c7efe  mov     [rbp+57h+var_40], rbx
0x1800c7f02  mov     [rbp+57h+var_38], rbx
0x1800c7f06  psrldq  xmm0, 8
0x1800c7f0b  movq    rax, xmm0
0x1800c7f10  sub     rax, rbx
0x1800c7f13  cmp     rax, 20h ; ' '
0x1800c7f17  jnb     short loc_1800C7F60
0x1800c7f19  mov     rsi, [rbp+57h+Src+8]
0x1800c7f1d  sub     rsi, rbx
0x1800c7f20  mov     ecx, 20h ; ' '; Size
0x1800c7f25  call    cs:__imp_malloc
0x1800c7f2b  mov     r14, rax
0x1800c7f2e  test    rax, rax
0x1800c7f31  jz      loc_1800C8196
0x1800c7f37  mov     r8, [rbp+57h+Src+8]
0x1800c7f3b  mov     rdx, [rbp+57h+Src]; Src
0x1800c7f3f  sub     r8, rdx; Size
0x1800c7f42  mov     rcx, rax; void *
0x1800c7f45  call    memmove
0x1800c7f4a  mov     r9d, 20h ; ' '
0x1800c7f50  mov     r8, rsi
0x1800c7f53  mov     rdx, r14
0x1800c7f56  lea     rcx, [rbp+57h+Src]
0x1800c7f5a  call    ?_Change_array@?$vector@EV?$allocator@E@std@@@std@@AEAAXQEAE_K1@Z; std::vector<uchar>::_Change_array(uchar * const,unsigned __int64,unsigned __int64)
0x1800c7f5f  nop
0x1800c7f60  mov     rcx, [r15]
0x1800c7f63  mov     [rbp+57h+arg_18], rbx
0x1800c7f67  mov     rax, [rcx]
0x1800c7f6a  lea     r9, [rbp+57h+arg_18]
0x1800c7f6e  mov     r8d, 1
0x1800c7f74  mov     rdx, rbx
0x1800c7f77  mov     rax, [rax+28h]
0x1800c7f7b  call    cs:__guard_dispatch_icall_fptr
0x1800c7f81  mov     ecx, eax; this
0x1800c7f83  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x1800c7f8a  mov     edx, 161h; int
0x1800c7f8f  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c7f94  mov     eax, dword ptr [rbp+57h+arg_18]
0x1800c7f97  mov     [rbp+57h+var_48], rax
0x1800c7f9b  lea     rax, [rbp+57h+var_90]
0x1800c7f9f  mov     [rbp+57h+arg_18], rax
0x1800c7fa3  mov     r8, r15
0x1800c7fa6  lea     rdx, [rbp+57h+arg_18]
0x1800c7faa  lea     rcx, [rbp+57h+var_90]
0x1800c7fae  call    ??$for_each@$0A@V_lambda_1_@?1??Read@StreamUnit@Legacy@RepoMan@@QEAAXAEAV?$ComPtr@UIStream@@@5@@Z@AEAV65@@?$TypeList@UField4Bytes@Meta@RepoMan@@U123@U123@U123@U123@UFieldNBytes@23@U123@UField1Byte@23@U523@U523@@Meta@RepoMan@@QEAAXAEBV_lambda_1_@?1??Read@StreamUnit@Legacy@2@QEAAXAEAV?$ComPtr@UIStream@@@2@@Z@0@Z; RepoMan::Meta::TypeList<RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::FieldNBytes,RepoMan::Meta::Field4Bytes,RepoMan::Meta::Field1Byte,RepoMan::Meta::Field1Byte,RepoMan::Meta::Field1Byte>::for_each<0,`RepoMan::Legacy::StreamUnit::Read(RepoMan::ComPtr<IStream> &)'::`2'::_lambda_1_,RepoMan::ComPtr<IStream> &>(`RepoMan::Legacy::StreamUnit::Read(RepoMan::ComPtr<IStream> &)'::`2'::_lambda_1_ const &,RepoMan::ComPtr<IStream> &)
0x1800c7fb3  cmp     [rbp+57h+var_8C], 2
0x1800c7fb7  ja      loc_1800C816F
0x1800c7fbd  cmp     [rbp+57h+var_8E], 1
0x1800c7fc1  ja      loc_1800C8148
0x1800c7fc7  mov     rcx, [r15]
0x1800c7fca  mov     [rbp+57h+arg_18], rbx
0x1800c7fce  mov     rax, [rcx]
0x1800c7fd1  lea     r9, [rbp+57h+arg_18]
0x1800c7fd5  mov     r8d, 1
0x1800c7fdb  mov     rdx, rbx
0x1800c7fde  mov     rax, [rax+28h]
0x1800c7fe2  call    cs:__guard_dispatch_icall_fptr
0x1800c7fe8  mov     ecx, eax; this
0x1800c7fea  lea     r8, aSrcRepomanSrcI; "src\\repoman\\src\\inc\\StreamBase.hpp"
0x1800c7ff1  mov     edx, 161h; int
0x1800c7ff6  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x1800c7ffb  mov     eax, dword ptr [rbp+57h+arg_18]
0x1800c7ffe  mov     [rbp+57h+var_40], rax
0x1800c8002  mov     eax, [rbp+57h+var_50]
0x1800c8005  cmp     rax, [r12+58h]
0x1800c800a  jnz     loc_1800C80F7
0x1800c8010  mov     r9, [rdi+8]
0x1800c8014  cmp     r9, [rdi+10h]
0x1800c8018  jz      loc_1800C809F
0x1800c801e  mov     al, byte ptr [rbp+57h+var_90]
0x1800c8021  mov     [r9], al
0x1800c8024  mov     al, byte ptr [rbp+57h+var_90+1]
0x1800c8027  mov     [r9+1], al
0x1800c802b  mov     al, [rbp+57h+var_8E]
0x1800c802e  mov     [r9+2], al
0x1800c8032  mov     eax, [rbp+57h+var_8C]
0x1800c8035  mov     [r9+4], eax
0x1800c8039  mov     rdx, [rbp+57h+var_78]
0x1800c803d  mov     [rbp+57h+var_78], rbx
0x1800c8041  mov     rcx, [rbp+57h+Src+8]
0x1800c8045  mov     [rbp+57h+Src+8], rbx
0x1800c8049  mov     rax, [rbp+57h+Src]
0x1800c804d  mov     [rbp+57h+Src], rbx
0x1800c8051  mov     [r9+8], rax
0x1800c8055  mov     [r9+10h], rcx
0x1800c8059  mov     [r9+18h], rdx
0x1800c805d  mov     eax, [rbp+57h+var_70]
0x1800c8060  mov     [r9+20h], eax
0x1800c8064  mov     eax, [rbp+57h+var_68]
0x1800c8067  mov     [r9+28h], eax
0x1800c806b  mov     eax, [rbp+57h+var_60]
0x1800c806e  mov     [r9+30h], eax
0x1800c8072  mov     eax, [rbp+57h+var_58]
0x1800c8075  mov     [r9+38h], eax
0x1800c8079  mov     eax, [rbp+57h+var_50]
0x1800c807c  mov     [r9+40h], eax
0x1800c8080  mov     rax, [rbp+57h+var_48]
0x1800c8084  mov     [r9+48h], rax
0x1800c8088  mov     rax, [rbp+57h+var_40]
0x1800c808c  mov     [r9+50h], rax
0x1800c8090  mov     rax, [rbp+57h+var_38]
0x1800c8094  mov     [r9+58h], rax
0x1800c8098  add     qword ptr [rdi+8], 60h ; '`'
0x1800c809d  jmp     short loc_1800C80AE
0x1800c809f  lea     r8, [rbp+57h+var_90]
0x1800c80a3  mov     rdx, r9
0x1800c80a6  mov     rcx, rdi
0x1800c80a9  call    ??$_Emplace_reallocate@VStreamUnit@Legacy@RepoMan@@@?$vector@VStreamUnit@Legacy@RepoMan@@V?$allocator@VStreamUnit@Legacy@RepoMan@@@std@@@std@@AEAAPEAVStreamUnit@Legacy@RepoMan@@QEAV234@$$QEAV234@@Z; std::vector<RepoMan::Legacy::StreamUnit>::_Emplace_reallocate<RepoMan::Legacy::StreamUnit>(RepoMan::Legacy::StreamUnit * const,RepoMan::Legacy::StreamUnit &&)
0x1800c80ae  mov     rcx, r15
0x1800c80b1  call    ?Position@?$StreamBase@$$V@RepoMan@@SA_KAEAV?$ComPtr@UIStream@@@2@@Z; RepoMan::StreamBase<>::Position(RepoMan::ComPtr<IStream> &)
0x1800c80b6  mov     ecx, eax
0x1800c80b8  mov     [rdi+20h], rcx
0x1800c80bc  mov     rcx, [rbp+57h+Src]
0x1800c80c0  test    rcx, rcx
0x1800c80c3  jz      loc_1800C7ECF
0x1800c80c9  mov     rdx, rcx
0x1800c80cc  mov     rax, [rbp+57h+var_78]
0x1800c80d0  sub     rax, rcx
0x1800c80d3  cmp     rax, 1000h
0x1800c80d9  jb      short loc_1800C80EC
0x1800c80db  mov     rcx, [rcx-8]; Block
0x1800c80df  sub     rdx, rcx
0x1800c80e2  lea     rax, [rdx-8]
0x1800c80e6  cmp     rax, 1Fh
0x1800c80ea  ja      short loc_1800C8127
0x1800c80ec  call    cs:__imp_free
0x1800c80f2  jmp     loc_1800C7ECF
0x1800c80f7  mov     rcx, [rbp+57h+Src]; Block
0x1800c80fb  test    rcx, rcx
0x1800c80fe  jz      loc_1800C7E89
0x1800c8104  mov     rdx, rcx
0x1800c8107  mov     rax, [rbp+57h+var_78]
0x1800c810b  sub     rax, rcx
0x1800c810e  cmp     rax, 1000h
0x1800c8114  jb      short loc_1800C813D
0x1800c8116  mov     rcx, [rcx-8]
0x1800c811a  sub     rdx, rcx
0x1800c811d  lea     rax, [rdx-8]
0x1800c8121  cmp     rax, 1Fh
0x1800c8125  jbe     short loc_1800C813D
0x1800c8127  mov     [rsp+0C0h+Reserved], rbx; Reserved
0x1800c812c  xor     r9d, r9d; LineNo
0x1800c812f  xor     r8d, r8d; FileName
0x1800c8132  xor     edx, edx; FunctionName
0x1800c8134  xor     ecx, ecx; Expression
0x1800c8136  call    cs:__imp__invoke_watson
0x1800c813d  call    cs:__imp_free
0x1800c8143  jmp     loc_1800C7E89
0x1800c8148  mov     dword ptr [rsp+0C0h+Reserved], 8
0x1800c8150  mov     r9d, 8C470251h
0x1800c8156  lea     r8, aInvalidState; "invalid state"
0x1800c815d  lea     rdx, aSrcRepomanSrcI_8; "src\\repoman\\src\\inc\\StreamManifest."...
0x1800c8164  mov     ecx, 0B3h
0x1800c8169  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800c816f  mov     dword ptr [rsp+0C0h+Reserved], 8
0x1800c8177  mov     r9d, 8C470251h
0x1800c817d  lea     r8, aInvalidType; "invalid type"
0x1800c8184  lea     rdx, aSrcRepomanSrcI_8; "src\\repoman\\src\\inc\\StreamManifest."...
0x1800c818b  mov     ecx, 0B2h
0x1800c8190  call    ??$RaiseException@VException@RepoMan@@W4Error@2@@RepoMan@@YAXHQEBDPEBDW4Error@0@W4Verbosity@ILogger@0@@Z; RepoMan::RaiseException<RepoMan::Exception,RepoMan::Error>(int,char const * const,char const *,RepoMan::Error,RepoMan::ILogger::Verbosity)
0x1800c8196  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
