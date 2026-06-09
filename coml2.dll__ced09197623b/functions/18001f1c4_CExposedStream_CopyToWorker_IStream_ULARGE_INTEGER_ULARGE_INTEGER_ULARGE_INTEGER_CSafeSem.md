# CExposedStream::CopyToWorker(IStream *,_ULARGE_INTEGER,_ULARGE_INTEGER *,_ULARGE_INTEGER *,CSafeSem *)

- ea: `0x18001f1c4`
- end: `0x18001f5c6`
- name: `?CopyToWorker@CExposedStream@@AEAAJPEAUIStream@@T_ULARGE_INTEGER@@PEAT3@2PEAVCSafeSem@@@Z`
- size: `1026`
- prototype: `__int64 __fastcall(CExposedStream *__hidden this, struct IStream *, union _ULARGE_INTEGER, union _ULARGE_INTEGER *, union _ULARGE_INTEGER *, struct CSafeSem *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f0b0`

## callees

- `0x180010cf0`
- `0x180015f30`
- `0x180016810`
- `0x18001f1c4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001f2cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f46f`

## pseudocode

```c
__int64 __fastcall CExposedStream::CopyToWorker(
        CExposedStream *this,
        struct IStream *a2,
        union _ULARGE_INTEGER a3,
        union _ULARGE_INTEGER *a4,
        union _ULARGE_INTEGER *a5,
        struct CSafeSem *a6)
{
  _QWORD *v6; // r10
  ULONGLONG v7; // r14
  _QWORD *v8; // r11
  void *v10; // rbx
  union _ULARGE_INTEGER v11; // rsi
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  ULONGLONG v16; // r12
  union _ULARGE_INTEGER v17; // rcx
  __int64 v18; // rax
  int v19; // edi
  unsigned int v20; // ebp
  LPVOID v21; // rax
  void *v22; // r13
  ULONGLONG v23; // rdx
  ULONGLONG v24; // r10
  int v25; // ecx
  unsigned int LowPart; // r14d
  _QWORD *v27; // rcx
  _QWORD *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  PSStream *v31; // rcx
  struct IStream *v33; // rcx
  int v34; // [rsp+30h] [rbp-78h]
  int v35; // [rsp+34h] [rbp-74h]
  ULONGLONG v36; // [rsp+38h] [rbp-70h]
  ULONGLONG v37; // [rsp+40h] [rbp-68h]
  ULONGLONG v38; // [rsp+48h] [rbp-60h]
  ULONGLONG v39[11]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v40; // [rsp+B0h] [rbp+8h] BYREF
  struct IStream *v41; // [rsp+B8h] [rbp+10h]
  int v42; // [rsp+C0h] [rbp+18h] BYREF
  union _ULARGE_INTEGER *v43; // [rsp+C8h] [rbp+20h]

  v43 = a4;
  v41 = a2;
  v6 = (_QWORD *)*((_QWORD *)this + 15);
  v7 = 0;
  v8 = (_QWORD *)*((_QWORD *)this + 14);
  v39[0] = 0;
  v10 = 0;
  v11 = a3;
  v36 = 0;
  v8[4] = v6[2];
  v8[5] = v6[3];
  v8[6] = v6[4];
  v13 = *((_QWORD *)this + 13);
  if ( (*(_BYTE *)(v13 + 20) & 0x20) != 0 )
  {
    v19 = -2147286782;
  }
  else
  {
    v14 = *(_QWORD *)(v13 + 104);
    if ( v14 )
      v14 += *(_QWORD *)NtCurrentTeb()->ReservedForOle;
    if ( *(_DWORD *)v14 == 1381258052 )
    {
      v15 = *(_QWORD *)(v14 + 176);
    }
    else
    {
      v15 = 0;
      if ( *(_DWORD *)v14 == 1381258068 )
        v15 = *(_QWORD *)(v14 + 112);
    }
    v16 = *(_QWORD *)(*((_QWORD *)this + 17) + 16LL);
    if ( v15 < v16 )
    {
      v11.QuadPart = 0;
    }
    else
    {
      v17.QuadPart = v15 - v16;
      if ( v17.QuadPart < a3.QuadPart )
        v11 = v17;
    }
    v18 = *(_QWORD *)a2;
    v40 = 0;
    v34 = 1;
    v19 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(v18 + 40))(a2, 0, 1, v39);
    if ( v19 >= 0 )
    {
      v20 = (*(_DWORD *)(*((_QWORD *)this + 14) + 56LL) & 0x80000) != 0 ? 0x40000 : 0x2000;
      while ( 1 )
      {
        v21 = CoTaskMemAlloc(v20);
        v22 = v21;
        if ( v21 )
          break;
        v20 >>= 1;
        if ( v20 < 0x2000 )
        {
          v10 = 0;
          v19 = -2147287032;
          goto LABEL_31;
        }
      }
      if ( v39[0] <= v16 || v39[0] >= v16 + v11.QuadPart )
      {
        v23 = 0;
        v24 = 0;
        v25 = 0;
        v34 = 0;
      }
      else
      {
        v23 = v16 + v11.QuadPart;
        v25 = 1;
        v24 = v39[0] + v11.QuadPart;
      }
      v19 = 0;
      v38 = v24;
      v10 = v21;
      v37 = v23;
      while ( v11.QuadPart )
      {
        LowPart = v11.LowPart;
        if ( v11.QuadPart >= v20 )
          LowPart = v20;
        if ( v25 )
        {
          v33 = v41;
          v37 = v23 - LowPart;
          v38 = v24 - LowPart;
          *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) = v37;
          v19 = (*(__int64 (__fastcall **)(struct IStream *, ULONGLONG, _QWORD, _QWORD))(*(_QWORD *)v33 + 40LL))(
                  v33,
                  v38,
                  0,
                  0);
          if ( v19 < 0 )
            goto LABEL_30;
        }
        v27 = (_QWORD *)*((_QWORD *)this + 15);
        v28 = (_QWORD *)*((_QWORD *)this + 14);
        LODWORD(v40) = 0;
        v28[4] = v27[2];
        v28[5] = v27[3];
        v28[6] = v27[4];
        v29 = *((_QWORD *)this + 13);
        if ( (*(_BYTE *)(v29 + 20) & 0x20) != 0 )
        {
          v19 = -2147286782;
        }
        else if ( (*(_BYTE *)(v29 + 20) & 0x40) != 0 )
        {
          v30 = *(_QWORD *)(v29 + 104);
          v31 = v30 ? (PSStream *)(v30 + *(_QWORD *)NtCurrentTeb()->ReservedForOle) : 0LL;
          v19 = PSStream::ReadAt(v31, *(_QWORD *)(*((_QWORD *)this + 17) + 16LL), v22, LowPart, (unsigned int *)&v40);
        }
        else
        {
          v19 = -2147287035;
        }
        *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) += (unsigned int)v40;
        if ( v19 < 0 )
          goto LABEL_30;
        if ( LowPart != (_DWORD)v40 )
        {
          v19 = -2147287010;
          goto LABEL_30;
        }
        v42 = 0;
        CSafeSem::Release(a6);
        v35 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, int *))(*(_QWORD *)v41 + 32LL))(
                v41,
                v22,
                LowPart,
                &v42);
        v19 = CSafeSem::Take(a6);
        if ( v19 < 0 )
          goto LABEL_30;
        v19 = v35;
        if ( v35 < 0 )
          goto LABEL_30;
        if ( LowPart != v42 )
        {
          v19 = -2147287011;
LABEL_30:
          v7 = v36;
          goto LABEL_31;
        }
        v25 = v34;
        v23 = v37;
        v24 = v38;
        v11.QuadPart -= LowPart;
        v7 = LowPart + v36;
        v36 = v7;
      }
      if ( v25 )
      {
        *(_QWORD *)(*((_QWORD *)this + 17) + 16LL) = v7 + v16;
        v19 = (*(__int64 (__fastcall **)(struct IStream *, ULONGLONG, _QWORD, _QWORD))(*(_QWORD *)v41 + 40LL))(
                v41,
                v7 + v39[0],
                0,
                0);
      }
    }
  }
LABEL_31:
  CoTaskMemFree(v10);
  if ( v43 )
    v43->QuadPart = v7;
  if ( a5 )
    a5->QuadPart = v7;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18001f1c4  mov     [rsp+arg_18], r9
0x18001f1c9  mov     [rsp+arg_8], rdx
0x18001f1ce  push    rbx
0x18001f1cf  push    rbp
0x18001f1d0  push    rsi
0x18001f1d1  push    rdi
0x18001f1d2  push    r12
0x18001f1d4  push    r13
0x18001f1d6  push    r14
0x18001f1d8  push    r15
0x18001f1da  sub     rsp, 68h
0x18001f1de  mov     r10, [rcx+78h]
0x18001f1e2  xor     r14d, r14d
0x18001f1e5  mov     r11, [rcx+70h]
0x18001f1e9  mov     rdi, rdx
0x18001f1ec  mov     [rsp+0A8h+var_58], 0
0x18001f1f5  xor     ebx, ebx
0x18001f1f7  mov     rsi, r8
0x18001f1fa  mov     [rsp+0A8h+var_70], r14
0x18001f1ff  mov     rax, [r10+10h]
0x18001f203  mov     r15, rcx
0x18001f206  mov     [r11+20h], rax
0x18001f20a  mov     rax, [r10+18h]
0x18001f20e  mov     [r11+28h], rax
0x18001f212  mov     rax, [r10+20h]
0x18001f216  mov     [r11+30h], rax
0x18001f21a  mov     rdx, [rcx+68h]
0x18001f21e  test    byte ptr [rdx+14h], 20h
0x18001f222  jnz     loc_18001F516
0x18001f228  mov     rdx, [rdx+68h]
0x18001f22c  test    rdx, rdx
0x18001f22f  jz      loc_18001F507
0x18001f235  mov     rax, gs:30h
0x18001f23e  mov     rcx, [rax+1758h]
0x18001f245  add     rdx, [rcx]
0x18001f248  cmp     dword ptr [rdx], 52545344h
0x18001f24e  jnz     loc_18001F4E9
0x18001f254  mov     rcx, [rdx+0B0h]
0x18001f25b  mov     rax, [r15+88h]
0x18001f262  mov     r12, [rax+10h]
0x18001f266  cmp     rcx, r12
0x18001f269  jb      loc_18001F4A9
0x18001f26f  sub     rcx, r12
0x18001f272  cmp     rcx, rsi
0x18001f275  cmovb   rsi, rcx
0x18001f279  mov     rax, [rdi]
0x18001f27c  lea     r9, [rsp+0A8h+var_58]
0x18001f281  mov     r8d, 1
0x18001f287  mov     [rsp+0A8h+arg_0], rbx
0x18001f28f  mov     rdx, rbx
0x18001f292  mov     [rsp+0A8h+var_78], r8d
0x18001f297  mov     rcx, rdi
0x18001f29a  mov     rax, [rax+28h]
0x18001f29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a3  mov     edi, eax
0x18001f2a5  test    eax, eax
0x18001f2a7  js      loc_18001F46C
0x18001f2ad  mov     rax, [r15+70h]
0x18001f2b1  mov     ebx, 2000h
0x18001f2b6  mov     ecx, [rax+38h]
0x18001f2b9  and     ecx, 80000h
0x18001f2bf  neg     ecx
0x18001f2c1  sbb     ebp, ebp
0x18001f2c3  and     ebp, 3E000h
0x18001f2c9  add     ebp, ebx
0x18001f2cb  mov     ecx, ebp; cb
0x18001f2cd  call    cs:__imp_CoTaskMemAlloc
0x18001f2d3  mov     r13, rax
0x18001f2d6  test    rax, rax
0x18001f2d9  jz      loc_18001F520
0x18001f2df  mov     rax, [rsp+0A8h+var_58]
0x18001f2e4  cmp     rax, r12
0x18001f2e7  ja      loc_18001F537
0x18001f2ed  xor     edx, edx
0x18001f2ef  xor     r10d, r10d
0x18001f2f2  xor     ecx, ecx
0x18001f2f4  mov     [rsp+0A8h+var_78], ecx
0x18001f2f8  xor     edi, edi
0x18001f2fa  mov     [rsp+0A8h+var_60], r10
0x18001f2ff  mov     rbx, r13
0x18001f302  mov     [rsp+0A8h+var_68], rdx
0x18001f307  test    rsi, rsi
0x18001f30a  jz      loc_18001F4B0
0x18001f310  mov     eax, ebp
0x18001f312  mov     r14d, esi
0x18001f315  cmp     rsi, rax
0x18001f318  cmovnb  r14d, ebp
0x18001f31c  test    ecx, ecx
0x18001f31e  jnz     loc_18001F556
0x18001f324  mov     rcx, [r15+78h]
0x18001f328  mov     rdx, [r15+70h]
0x18001f32c  mov     dword ptr [rsp+0A8h+arg_0], 0
0x18001f337  mov     rax, [rcx+10h]
0x18001f33b  mov     [rdx+20h], rax
0x18001f33f  mov     rax, [rcx+18h]
0x18001f343  mov     [rdx+28h], rax
0x18001f347  mov     rax, [rcx+20h]
0x18001f34b  mov     [rdx+30h], rax
0x18001f34f  mov     rdx, [r15+68h]
0x18001f353  test    byte ptr [rdx+14h], 20h
0x18001f357  jnz     loc_18001F5A0
0x18001f35d  test    byte ptr [rdx+14h], 40h
0x18001f361  jz      loc_18001F50C
0x18001f367  mov     rax, [r15+88h]
0x18001f36e  mov     rdx, [rdx+68h]
0x18001f372  mov     r10, [rax+10h]
0x18001f376  test    rdx, rdx
0x18001f379  jz      loc_18001F500
0x18001f37f  mov     rax, gs:30h
0x18001f388  mov     rcx, [rax+1758h]
0x18001f38f  mov     rcx, [rcx]
0x18001f392  add     rcx, rdx; this
0x18001f395  lea     rax, [rsp+0A8h+arg_0]
0x18001f39d  mov     r9d, r14d; unsigned int
0x18001f3a0  mov     r8, r13; void *
0x18001f3a3  mov     [rsp+0A8h+var_88], rax; unsigned int *
0x18001f3a8  mov     rdx, r10; unsigned __int64
0x18001f3ab  call    ?ReadAt@PSStream@@QEAAJ_KPEAXKPEAK@Z; PSStream::ReadAt(unsigned __int64,void *,ulong,ulong *)
0x18001f3b0  mov     edi, eax
0x18001f3b2  mov     rcx, [r15+88h]
0x18001f3b9  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x18001f3c0  add     [rcx+10h], rax
0x18001f3c4  test    edi, edi
0x18001f3c6  js      loc_18001F467
0x18001f3cc  cmp     r14d, dword ptr [rsp+0A8h+arg_0]
0x18001f3d4  jnz     loc_18001F5B4
0x18001f3da  mov     rcx, [rsp+0A8h+arg_28]; this
0x18001f3e2  mov     [rsp+0A8h+arg_10], 0
0x18001f3ed  call    ?Release@CSafeSem@@QEAAXXZ; CSafeSem::Release(void)
0x18001f3f2  mov     rcx, [rsp+0A8h+arg_8]
0x18001f3fa  lea     r9, [rsp+0A8h+arg_10]
0x18001f402  mov     r8d, r14d
0x18001f405  mov     rdx, r13
0x18001f408  mov     rax, [rcx]
0x18001f40b  mov     rax, [rax+20h]
0x18001f40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f414  mov     rcx, [rsp+0A8h+arg_28]; this
0x18001f41c  mov     [rsp+0A8h+var_74], eax
0x18001f420  call    ?Take@CSafeSem@@QEAAJXZ; CSafeSem::Take(void)
0x18001f425  mov     edi, eax
0x18001f427  test    eax, eax
0x18001f429  js      short loc_18001F467
0x18001f42b  mov     edi, [rsp+0A8h+var_74]
0x18001f42f  test    edi, edi
0x18001f431  js      short loc_18001F467
0x18001f433  cmp     r14d, [rsp+0A8h+arg_10]
0x18001f43b  jnz     loc_18001F5AA
0x18001f441  mov     ecx, [rsp+0A8h+var_78]
0x18001f445  mov     rdx, [rsp+0A8h+var_68]
0x18001f44a  mov     r10, [rsp+0A8h+var_60]
0x18001f44f  mov     eax, r14d
0x18001f452  mov     r14, [rsp+0A8h+var_70]
0x18001f457  sub     rsi, rax
0x18001f45a  add     r14, rax
0x18001f45d  mov     [rsp+0A8h+var_70], r14
0x18001f462  jmp     loc_18001F307
0x18001f467  mov     r14, [rsp+0A8h+var_70]
0x18001f46c  mov     rcx, rbx; pv
0x18001f46f  call    cs:__imp_CoTaskMemFree
0x18001f475  mov     rax, [rsp+0A8h+arg_18]
0x18001f47d  test    rax, rax
0x18001f480  jnz     loc_18001F5BE
0x18001f486  mov     rax, [rsp+0A8h+arg_20]
0x18001f48e  test    rax, rax
0x18001f491  jz      short loc_18001F496
0x18001f493  mov     [rax], r14
0x18001f496  mov     eax, edi
0x18001f498  add     rsp, 68h
0x18001f49c  pop     r15
0x18001f49e  pop     r14
0x18001f4a0  pop     r13
0x18001f4a2  pop     r12
0x18001f4a4  pop     rdi
0x18001f4a5  pop     rsi
0x18001f4a6  pop     rbp
0x18001f4a7  pop     rbx
0x18001f4a8  retn
0x18001f4a9  xor     esi, esi
0x18001f4ab  jmp     loc_18001F279
0x18001f4b0  test    ecx, ecx
0x18001f4b2  jz      short loc_18001F46C
0x18001f4b4  mov     rax, [r15+88h]
0x18001f4bb  lea     rcx, [r14+r12]
0x18001f4bf  xor     r9d, r9d
0x18001f4c2  xor     r8d, r8d
0x18001f4c5  mov     [rax+10h], rcx
0x18001f4c9  mov     rcx, [rsp+0A8h+arg_8]
0x18001f4d1  mov     rdx, [rsp+0A8h+var_58]
0x18001f4d6  add     rdx, r14
0x18001f4d9  mov     rax, [rcx]
0x18001f4dc  mov     rax, [rax+28h]
0x18001f4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4e5  mov     edi, eax
0x18001f4e7  jmp     short loc_18001F46C
0x18001f4e9  xor     ecx, ecx
0x18001f4eb  cmp     dword ptr [rdx], 52545354h
0x18001f4f1  jnz     loc_18001F25B
0x18001f4f7  mov     rcx, [rdx+70h]
0x18001f4fb  jmp     loc_18001F25B
0x18001f500  xor     ecx, ecx
0x18001f502  jmp     loc_18001F395
0x18001f507  jmp     loc_18001F248
0x18001f50c  mov     edi, 80030005h
0x18001f511  jmp     loc_18001F3B2
0x18001f516  mov     edi, 80030102h
0x18001f51b  jmp     loc_18001F46C
0x18001f520  shr     ebp, 1
0x18001f522  cmp     ebp, ebx
0x18001f524  jnb     loc_18001F2CB
0x18001f52a  mov     rbx, r13
0x18001f52d  mov     edi, 80030008h
0x18001f532  jmp     loc_18001F46C
0x18001f537  lea     rcx, [r12+rsi]
0x18001f53b  cmp     rax, rcx
0x18001f53e  jnb     loc_18001F2ED
0x18001f544  lea     rdx, [r12+rsi]
0x18001f548  mov     ecx, 1
0x18001f54d  lea     r10, [rax+rsi]
0x18001f551  jmp     loc_18001F2F8
0x18001f556  mov     rcx, [rsp+0A8h+arg_8]
0x18001f55e  xor     r9d, r9d
0x18001f561  mov     eax, r14d
0x18001f564  xor     r8d, r8d
0x18001f567  sub     rdx, rax
0x18001f56a  sub     r10, rax
0x18001f56d  mov     rax, [r15+88h]
0x18001f574  mov     [rsp+0A8h+var_68], rdx
0x18001f579  mov     [rsp+0A8h+var_60], r10
0x18001f57e  mov     [rax+10h], rdx
0x18001f582  mov     rdx, r10
0x18001f585  mov     rax, [rcx]
0x18001f588  mov     rax, [rax+28h]
0x18001f58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f591  mov     edi, eax
0x18001f593  test    eax, eax
0x18001f595  js      loc_18001F467
0x18001f59b  jmp     loc_18001F324
0x18001f5a0  mov     edi, 80030102h
0x18001f5a5  jmp     loc_18001F3B2
0x18001f5aa  mov     edi, 8003001Dh
0x18001f5af  jmp     loc_18001F467
0x18001f5b4  mov     edi, 8003001Eh
0x18001f5b9  jmp     loc_18001F467
0x18001f5be  mov     [rax], r14
0x18001f5c1  jmp     loc_18001F486
```
