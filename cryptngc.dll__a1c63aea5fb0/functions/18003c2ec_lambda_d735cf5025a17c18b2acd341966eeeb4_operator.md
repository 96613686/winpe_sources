# _lambda_d735cf5025a17c18b2acd341966eeeb4_::operator()

- ea: `0x18003c2ec`
- end: `0x18003c69f`
- name: `_lambda_d735cf5025a17c18b2acd341966eeeb4_::operator()`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003c17c`

## callees

- `0x180006538`
- `0x1800065c0`
- `0x180018430`
- `0x18002cf74`
- `0x18002f7db`
- `0x18003c2ec`
- `0x18003c6f0`
- `0x18003c7d8`
- `0x180042728`
- `0x180042ae4`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c674`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003c674`

## string_xrefs

- `0x18003c331`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x18003c458`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_d735cf5025a17c18b2acd341966eeeb4_::operator()(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rdx
  int v5; // ebx
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  __int64 v9; // rdx
  HLOCAL v10; // rcx
  unsigned int v11; // r9d
  size_t v12; // rbx
  unsigned int v13; // r15d
  size_t v14; // r14
  _OWORD *v15; // rax
  unsigned int *v16; // rcx
  __int64 v17; // r12
  __int64 v18; // rdx
  _OWORD *v19; // rax
  unsigned __int8 *v20; // rcx
  HLOCAL v21; // rcx
  int pbInput; // [rsp+20h] [rbp-E0h]
  int pbInputa; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *cbInput; // [rsp+28h] [rbp-D8h]
  ULONG cbInputa; // [rsp+28h] [rbp-D8h]
  unsigned int v26; // [rsp+30h] [rbp-D0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 *v30; // [rsp+58h] [rbp-A8h] BYREF
  char v31; // [rsp+60h] [rbp-A0h]
  UCHAR v32[16]; // [rsp+68h] [rbp-98h] BYREF
  UCHAR pbBuffer[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v34[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v35[256]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( !**(_QWORD **)a1 )
  {
    v4 = 305;
LABEL_3:
    v5 = -2146893785;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)v5,
      pbInput);
    return (unsigned int)v5;
  }
  if ( !**(_DWORD **)(a1 + 8) )
  {
    v4 = 306;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 16) )
  {
    v4 = 307;
    goto LABEL_3;
  }
  if ( !**(_DWORD **)(a1 + 24) )
  {
    v4 = 308;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 32) )
  {
    v4 = 309;
    goto LABEL_3;
  }
  if ( !**(_QWORD **)(a1 + 40) )
  {
    v4 = 310;
    goto LABEL_3;
  }
  v5 = NgcUtils::GenRandom(pbBuffer, 0x20u, a3);
  if ( v5 < 0 )
  {
    v4 = 315;
    goto LABEL_4;
  }
  v5 = NgcUtils::GenRandom(v32, 0x10u, v7);
  if ( v5 < 0 )
  {
    v4 = 320;
    goto LABEL_4;
  }
  LODWORD(Size) = 0;
  hMem = 0;
  p_hMem = &hMem;
  v30 = 0;
  v31 = 1;
  v5 = EncryptNgcData(
         pbBuffer,
         (unsigned int)&v30,
         v32,
         v8,
         **(PUCHAR **)(a1 + 16),
         **(_DWORD **)(a1 + 24),
         &v30,
         (unsigned int *)&Size);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
  if ( v5 < 0 )
  {
    v9 = 332;
    goto LABEL_22;
  }
  v5 = NgcUtils::WrapContentEncryptionKey(
         **(NgcUtils ***)a1,
         (unsigned __int8 *)**(unsigned int **)(a1 + 8),
         (unsigned int)pbBuffer,
         (unsigned __int8 *)0x20,
         (unsigned int)v34,
         cbInput,
         v26);
  if ( v5 < 0 )
  {
    v9 = 342;
    goto LABEL_22;
  }
  if ( IsTpm12() )
  {
    v5 = WrapContentEncryptionKeyByTpm12(**(unsigned __int8 ***)a1, **(_DWORD **)(a1 + 8), pbBuffer, v11, v35, cbInputa);
    if ( v5 < 0 )
    {
      v9 = 354;
      goto LABEL_22;
    }
  }
  v12 = (unsigned int)Size;
  if ( (unsigned int)Size >= 0xFFFFFEEC )
  {
    v9 = 359;
LABEL_35:
    v5 = -2146893785;
    goto LABEL_22;
  }
  if ( (int)Size + 292 < (unsigned int)(Size + 276) )
  {
    v9 = 360;
    goto LABEL_35;
  }
  v13 = Size + 548;
  if ( (int)Size + 548 < (unsigned int)(Size + 292) )
  {
    v9 = 361;
    goto LABEL_35;
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&Size, v13);
  v14 = Size;
  if ( !Size )
  {
    v5 = -2147024882;
    v9 = 364;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)v5,
      pbInputa);
    v10 = hMem;
    hMem = 0;
    if ( v10 )
      LocalFree(v10);
    return (unsigned int)v5;
  }
  *(_DWORD *)Size = 1;
  *(_DWORD *)(v14 + 12) = v12;
  *(_DWORD *)(v14 + 4) = 256;
  *(_DWORD *)(v14 + 8) = 16;
  *(_DWORD *)(v14 + 16) = 256;
  v15 = (_OWORD *)(v14 + 20);
  v16 = v34;
  v17 = 2;
  v18 = 2;
  do
  {
    *v15 = *(_OWORD *)v16;
    v15[1] = *((_OWORD *)v16 + 1);
    v15[2] = *((_OWORD *)v16 + 2);
    v15[3] = *((_OWORD *)v16 + 3);
    v15[4] = *((_OWORD *)v16 + 4);
    v15[5] = *((_OWORD *)v16 + 5);
    v15[6] = *((_OWORD *)v16 + 6);
    v15[7] = *((_OWORD *)v16 + 7);
    v15 += 8;
    v16 += 32;
    --v18;
  }
  while ( v18 );
  *(_OWORD *)(v14 + 276) = *(_OWORD *)v32;
  memcpy_0((void *)(v14 + 292), hMem, v12);
  v19 = (_OWORD *)(v12 + v14 + 292);
  v20 = v35;
  do
  {
    *v19 = *(_OWORD *)v20;
    v19[1] = *((_OWORD *)v20 + 1);
    v19[2] = *((_OWORD *)v20 + 2);
    v19[3] = *((_OWORD *)v20 + 3);
    v19[4] = *((_OWORD *)v20 + 4);
    v19[5] = *((_OWORD *)v20 + 5);
    v19[6] = *((_OWORD *)v20 + 6);
    v19[7] = *((_OWORD *)v20 + 7);
    v19 += 8;
    v20 += 128;
    --v17;
  }
  while ( v17 );
  ***(_QWORD ***)(a1 + 32) = v14;
  ***(_DWORD ***)(a1 + 40) = v13;
  v21 = hMem;
  hMem = 0;
  if ( v21 )
    LocalFree(v21);
  return 0;
}

```

## disassembly

```asm
0x18003c2ec  push    rbp
0x18003c2ee  push    rbx
0x18003c2ef  push    rsi
0x18003c2f0  push    rdi
0x18003c2f1  push    r12
0x18003c2f3  push    r13
0x18003c2f5  push    r14
0x18003c2f7  push    r15
0x18003c2f9  lea     rbp, [rsp-1B8h]
0x18003c301  sub     rsp, 2B8h
0x18003c308  mov     rax, cs:__security_cookie
0x18003c30f  xor     rax, rsp
0x18003c312  mov     [rbp+1F0h+var_50], rax
0x18003c319  mov     rsi, rcx
0x18003c31c  mov     rax, [rcx]
0x18003c31f  xor     r13d, r13d
0x18003c322  cmp     [rax], r13
0x18003c325  jnz     short loc_18003C34E
0x18003c327  mov     edx, 131h; void *
0x18003c32c  mov     ebx, 80090027h
0x18003c331  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003c338  mov     r9d, ebx; char *
0x18003c33b  mov     rcx, [rbp+1F8h]; this
0x18003c342  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c347  mov     eax, ebx
0x18003c349  jmp     loc_18003C67C
0x18003c34e  mov     rax, [rcx+8]
0x18003c352  cmp     [rax], r13d
0x18003c355  jnz     short loc_18003C35E
0x18003c357  mov     edx, 132h
0x18003c35c  jmp     short loc_18003C32C
0x18003c35e  mov     rax, [rcx+10h]
0x18003c362  cmp     [rax], r13
0x18003c365  jnz     short loc_18003C36E
0x18003c367  mov     edx, 133h
0x18003c36c  jmp     short loc_18003C32C
0x18003c36e  mov     rax, [rcx+18h]
0x18003c372  cmp     [rax], r13d
0x18003c375  jnz     short loc_18003C37E
0x18003c377  mov     edx, 134h
0x18003c37c  jmp     short loc_18003C32C
0x18003c37e  mov     rax, [rcx+20h]
0x18003c382  cmp     [rax], r13
0x18003c385  jnz     short loc_18003C38E
0x18003c387  mov     edx, 135h
0x18003c38c  jmp     short loc_18003C32C
0x18003c38e  mov     rax, [rcx+28h]
0x18003c392  cmp     [rax], r13
0x18003c395  jnz     short loc_18003C39E
0x18003c397  mov     edx, 136h
0x18003c39c  jmp     short loc_18003C32C
0x18003c39e  mov     edi, 20h ; ' '
0x18003c3a3  mov     edx, edi; cbBuffer
0x18003c3a5  lea     rcx, [rsp+2F0h+pbBuffer]; pbBuffer
0x18003c3aa  call    ?GenRandom@NgcUtils@@YAJPEAEK@Z; NgcUtils::GenRandom(uchar *,ulong)
0x18003c3af  mov     ebx, eax
0x18003c3b1  test    eax, eax
0x18003c3b3  jns     short loc_18003C3BF
0x18003c3b5  mov     edx, 13Bh
0x18003c3ba  jmp     loc_18003C331
0x18003c3bf  mov     r12d, 10h
0x18003c3c5  mov     edx, r12d; cbBuffer
0x18003c3c8  lea     rcx, [rsp+2F0h+var_288]; pbBuffer
0x18003c3cd  call    ?GenRandom@NgcUtils@@YAJPEAEK@Z; NgcUtils::GenRandom(uchar *,ulong)
0x18003c3d2  mov     ebx, eax
0x18003c3d4  test    eax, eax
0x18003c3d6  jns     short loc_18003C3E2
0x18003c3d8  mov     edx, 140h
0x18003c3dd  jmp     loc_18003C331
0x18003c3e2  mov     dword ptr [rsp+2F0h+Size], r13d
0x18003c3e7  mov     [rsp+2F0h+hMem], r13
0x18003c3ec  lea     rax, [rsp+2F0h+hMem]
0x18003c3f1  mov     [rsp+2F0h+var_2A0], rax
0x18003c3f6  mov     [rsp+2F0h+var_298], r13
0x18003c3fb  mov     [rsp+2F0h+var_290], 1
0x18003c400  mov     rax, [rsi+18h]
0x18003c404  mov     rcx, [rsi+10h]
0x18003c408  lea     rdx, [rsp+2F0h+Size]
0x18003c40d  mov     [rsp+2F0h+var_2B8], rdx; unsigned int *
0x18003c412  lea     rdx, [rsp+2F0h+var_298]; unsigned int
0x18003c417  mov     [rsp+2F0h+var_2C0], rdx; unsigned int
0x18003c41c  mov     eax, [rax]
0x18003c41e  mov     dword ptr [rsp+2F0h+cbInput], eax; unsigned int
0x18003c422  mov     rax, [rcx]
0x18003c425  mov     [rsp+2F0h+pbInput], rax; int
0x18003c42a  lea     r8, [rsp+2F0h+var_288]; unsigned __int8 *
0x18003c42f  lea     rcx, [rsp+2F0h+pbBuffer]; unsigned __int8 *
0x18003c434  call    ?EncryptNgcData@@YAJPEAEK0K0KPEAPEAEPEAK@Z; EncryptNgcData(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18003c439  mov     ebx, eax
0x18003c43b  lea     rcx, [rsp+2F0h+var_2A0]
0x18003c440  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18003c445  test    ebx, ebx
0x18003c447  jns     short loc_18003C483
0x18003c449  mov     edx, 14Ch; void *
0x18003c44e  mov     rcx, [rbp+1F8h]; this
0x18003c455  mov     r9d, ebx; char *
0x18003c458  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003c45f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c464  nop
0x18003c465  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18003c46a  mov     [rsp+2F0h+hMem], r13
0x18003c46f  test    rcx, rcx
0x18003c472  jz      loc_18003C347
0x18003c478  call    cs:__imp_LocalFree
0x18003c47e  jmp     loc_18003C347
0x18003c483  mov     rdx, [rsi+8]
0x18003c487  mov     rcx, [rsi]
0x18003c48a  lea     rax, [rbp+1F0h+var_250]
0x18003c48e  mov     [rsp+2F0h+pbInput], rax; unsigned int
0x18003c493  mov     r9d, edi; unsigned __int8 *
0x18003c496  lea     r8, [rsp+2F0h+pbBuffer]; unsigned int
0x18003c49b  mov     edx, [rdx]; unsigned __int8 *
0x18003c49d  mov     rcx, [rcx]; this
0x18003c4a0  call    ?WrapContentEncryptionKey@NgcUtils@@YAJPEAEK0K0K@Z; NgcUtils::WrapContentEncryptionKey(uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18003c4a5  mov     ebx, eax
0x18003c4a7  test    eax, eax
0x18003c4a9  jns     short loc_18003C4B2
0x18003c4ab  mov     edx, 156h
0x18003c4b0  jmp     short loc_18003C44E
0x18003c4b2  call    ?IsTpm12@@YA_NXZ; IsTpm12(void)
0x18003c4b7  test    al, al
0x18003c4b9  jz      short loc_18003C4ED
0x18003c4bb  mov     rdx, [rsi+8]
0x18003c4bf  mov     rcx, [rsi]
0x18003c4c2  lea     rax, [rbp+1F0h+var_150]
0x18003c4c9  mov     [rsp+2F0h+pbInput], rax; unsigned __int8 *
0x18003c4ce  lea     r8, [rsp+2F0h+pbBuffer]; unsigned __int8 *
0x18003c4d3  mov     edx, [rdx]; unsigned int
0x18003c4d5  mov     rcx, [rcx]; unsigned __int8 *
0x18003c4d8  call    ?WrapContentEncryptionKeyByTpm12@@YAJPEAEK0K0K@Z; WrapContentEncryptionKeyByTpm12(uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18003c4dd  mov     ebx, eax
0x18003c4df  test    eax, eax
0x18003c4e1  jns     short loc_18003C4ED
0x18003c4e3  mov     edx, 162h
0x18003c4e8  jmp     loc_18003C44E
0x18003c4ed  mov     ebx, dword ptr [rsp+2F0h+Size]
0x18003c4f1  lea     eax, [rbx+114h]
0x18003c4f7  cmp     eax, 114h
0x18003c4fc  jnb     short loc_18003C505
0x18003c4fe  mov     edx, 167h
0x18003c503  jmp     short loc_18003C524
0x18003c505  lea     ecx, [rax+10h]
0x18003c508  cmp     ecx, eax
0x18003c50a  jnb     short loc_18003C513
0x18003c50c  mov     edx, 168h
0x18003c511  jmp     short loc_18003C524
0x18003c513  lea     r15d, [rcx+100h]
0x18003c51a  cmp     r15d, ecx
0x18003c51d  jnb     short loc_18003C52E
0x18003c51f  mov     edx, 169h
0x18003c524  mov     ebx, 80090027h
0x18003c529  jmp     loc_18003C44E
0x18003c52e  mov     edx, r15d
0x18003c531  lea     rcx, [rsp+2F0h+Size]
0x18003c536  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18003c53b  mov     r14, [rsp+2F0h+Size]
0x18003c540  test    r14, r14
0x18003c543  jnz     short loc_18003C554
0x18003c545  mov     ebx, 8007000Eh
0x18003c54a  mov     edx, 16Ch
0x18003c54f  jmp     loc_18003C44E
0x18003c554  mov     dword ptr [r14], 1
0x18003c55b  mov     [r14+0Ch], ebx
0x18003c55f  mov     eax, 100h
0x18003c564  mov     [r14+4], eax
0x18003c568  mov     [r14+8], r12d
0x18003c56c  mov     [r14+10h], eax
0x18003c570  lea     rdi, [r14+14h]
0x18003c574  mov     rax, rdi
0x18003c577  lea     rcx, [rbp+1F0h+var_250]
0x18003c57b  mov     r12d, 2
0x18003c581  mov     edx, r12d
0x18003c584  lea     r8d, [r12+7Eh]
0x18003c589  movups  xmm0, xmmword ptr [rcx]
0x18003c58c  movups  xmmword ptr [rax], xmm0
0x18003c58f  movups  xmm1, xmmword ptr [rcx+10h]
0x18003c593  movups  xmmword ptr [rax+10h], xmm1
0x18003c597  movups  xmm0, xmmword ptr [rcx+20h]
0x18003c59b  movups  xmmword ptr [rax+20h], xmm0
0x18003c59f  movups  xmm1, xmmword ptr [rcx+30h]
0x18003c5a3  movups  xmmword ptr [rax+30h], xmm1
0x18003c5a7  movups  xmm0, xmmword ptr [rcx+40h]
0x18003c5ab  movups  xmmword ptr [rax+40h], xmm0
0x18003c5af  movups  xmm1, xmmword ptr [rcx+50h]
0x18003c5b3  movups  xmmword ptr [rax+50h], xmm1
0x18003c5b7  movups  xmm0, xmmword ptr [rcx+60h]
0x18003c5bb  movups  xmmword ptr [rax+60h], xmm0
0x18003c5bf  movups  xmm1, xmmword ptr [rcx+70h]
0x18003c5c3  movups  xmmword ptr [rax+70h], xmm1
0x18003c5c7  add     rax, r8
0x18003c5ca  add     rcx, r8
0x18003c5cd  sub     rdx, 1
0x18003c5d1  jnz     short loc_18003C589
0x18003c5d3  movups  xmm0, xmmword ptr [rsp+2F0h+var_288]
0x18003c5d8  movdqu  xmmword ptr [rdi+100h], xmm0
0x18003c5e0  add     rdi, 110h
0x18003c5e7  mov     r8, rbx; Size
0x18003c5ea  mov     rdx, [rsp+2F0h+hMem]; Src
0x18003c5ef  mov     rcx, rdi; void *
0x18003c5f2  call    memcpy_0
0x18003c5f7  lea     rax, [rbx+rdi]
0x18003c5fb  lea     rcx, [rbp+1F0h+var_150]
0x18003c602  mov     edx, 80h
0x18003c607  movups  xmm0, xmmword ptr [rcx]
0x18003c60a  movups  xmmword ptr [rax], xmm0
0x18003c60d  movups  xmm1, xmmword ptr [rcx+10h]
0x18003c611  movups  xmmword ptr [rax+10h], xmm1
0x18003c615  movups  xmm0, xmmword ptr [rcx+20h]
0x18003c619  movups  xmmword ptr [rax+20h], xmm0
0x18003c61d  movups  xmm1, xmmword ptr [rcx+30h]
0x18003c621  movups  xmmword ptr [rax+30h], xmm1
0x18003c625  movups  xmm0, xmmword ptr [rcx+40h]
0x18003c629  movups  xmmword ptr [rax+40h], xmm0
0x18003c62d  movups  xmm1, xmmword ptr [rcx+50h]
0x18003c631  movups  xmmword ptr [rax+50h], xmm1
0x18003c635  movups  xmm0, xmmword ptr [rcx+60h]
0x18003c639  movups  xmmword ptr [rax+60h], xmm0
0x18003c63d  movups  xmm1, xmmword ptr [rcx+70h]
0x18003c641  movups  xmmword ptr [rax+70h], xmm1
0x18003c645  add     rax, rdx
0x18003c648  add     rcx, rdx
0x18003c64b  sub     r12, 1
0x18003c64f  jnz     short loc_18003C607
0x18003c651  mov     rax, [rsi+20h]
0x18003c655  mov     rcx, [rax]
0x18003c658  mov     [rcx], r14
0x18003c65b  mov     rax, [rsi+28h]
0x18003c65f  mov     rcx, [rax]
0x18003c662  mov     [rcx], r15d
0x18003c665  mov     rcx, [rsp+2F0h+hMem]; hMem
0x18003c66a  mov     [rsp+2F0h+hMem], r13
0x18003c66f  test    rcx, rcx
0x18003c672  jz      short loc_18003C67A
0x18003c674  call    cs:__imp_LocalFree
0x18003c67a  xor     eax, eax
0x18003c67c  mov     rcx, [rbp+1F0h+var_50]
0x18003c683  xor     rcx, rsp; StackCookie
0x18003c686  call    __security_check_cookie
0x18003c68b  add     rsp, 2B8h
0x18003c692  pop     r15
0x18003c694  pop     r14
0x18003c696  pop     r13
0x18003c698  pop     r12
0x18003c69a  pop     rdi
0x18003c69b  pop     rsi
0x18003c69c  pop     rbx
0x18003c69d  pop     rbp
0x18003c69e  retn
```
