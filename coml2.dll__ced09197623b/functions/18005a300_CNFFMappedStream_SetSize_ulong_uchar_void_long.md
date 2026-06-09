# CNFFMappedStream::SetSize(ulong,uchar,void * *,long *)

- ea: `0x18005a300`
- end: `0x18005a439`
- name: `?SetSize@CNFFMappedStream@@UEAAXKEPEAPEAXPEAJ@Z`
- size: `313`
- prototype: `void(CNFFMappedStream *__hidden this, SIZE_T cb, unsigned __int8, void **, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x18003f974`
- `0x18003f9a0`
- `0x1800586b4`
- `0x180059bdc`
- `0x180059c24`
- `0x180059c50`
- `0x18005a300`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005a3dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18005a3dc`

## pseudocode

```c
void __fastcall CNFFMappedStream::SetSize(CNFFMappedStream *this, SIZE_T cb, char a3, void **a4, int *a5)
{
  int *v5; // rsi
  SIZE_T v7; // rbp
  int UpdateStreamIfNecessary; // eax
  __int64 v11; // rcx
  int v12; // eax
  int v13; // edi
  int v14; // r14d
  void *v15; // rax

  v5 = a5;
  v7 = (unsigned int)cb;
  *a5 = 0;
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 24LL))(
    *(_QWORD *)(*((_QWORD *)this + 1) + 104LL),
    0xFFFFFFFFLL);
  if ( *(_QWORD *)(*((_QWORD *)this + 1) + 96LL) == -1 )
  {
    *v5 = -2147286782;
    goto LABEL_22;
  }
  *v5 = 0;
  if ( (unsigned int)v7 > 0x200000 )
  {
    *v5 = -2147286928;
    goto LABEL_22;
  }
  if ( a3 )
  {
    UpdateStreamIfNecessary = CNFFMappedStream::CreateUpdateStreamIfNecessary(this);
    *v5 = UpdateStreamIfNecessary;
    if ( UpdateStreamIfNecessary < 0 )
      goto LABEL_22;
    CNFFMappedStream::BeginUsingUpdateStream(this);
    if ( (unsigned int)v7 > *((_DWORD *)this + 9) )
    {
      v11 = *((_QWORD *)this + 1);
      a5 = (int *)(unsigned int)v7;
      v12 = CNtfsStream::SetFileSize(v11, (__int64 *)&a5);
      *v5 = v12;
      if ( v12 < 0 )
      {
LABEL_19:
        CNFFMappedStream::EndUsingUpdateStream(this);
        goto LABEL_22;
      }
      *((_DWORD *)this + 9) = v7;
    }
    v13 = 0;
    v14 = 1;
  }
  else
  {
    v14 = 0;
    CNFFMappedStream::BeginUsingLatestStream(this);
    v13 = 1;
  }
  if ( (_DWORD)v7 != *((_DWORD *)this + 8) )
  {
    v15 = CoTaskMemRealloc(*((LPVOID *)this + 3), v7);
    if ( !v15 )
    {
      *v5 = -2147024882;
      goto LABEL_18;
    }
    *((_QWORD *)this + 3) = v15;
    if ( a4 )
      *a4 = v15;
  }
  *((_DWORD *)this + 8) = v7;
LABEL_18:
  if ( v14 )
    goto LABEL_19;
  if ( v13 )
    CNFFMappedStream::EndUsingLatestStream(this);
LABEL_22:
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 1) + 104LL) + 32LL))(*(_QWORD *)(*((_QWORD *)this + 1) + 104LL));
}

```

## disassembly

```asm
0x18005a300  push    rbx
0x18005a302  push    rbp
0x18005a303  push    rsi
0x18005a304  push    rdi
0x18005a305  push    r14
0x18005a307  push    r15
0x18005a309  sub     rsp, 28h
0x18005a30d  mov     rsi, [rsp+58h+arg_20]
0x18005a315  mov     rbx, rcx
0x18005a318  mov     ebp, edx
0x18005a31a  mov     r15, r9
0x18005a31d  or      edx, 0FFFFFFFFh
0x18005a320  mov     dil, r8b
0x18005a323  mov     dword ptr [rsi], 0
0x18005a329  mov     rax, [rcx+8]
0x18005a32d  mov     rcx, [rax+68h]
0x18005a331  mov     rax, [rcx]
0x18005a334  mov     rax, [rax+18h]
0x18005a338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a33d  mov     rax, [rbx+8]
0x18005a341  cmp     qword ptr [rax+60h], 0FFFFFFFFFFFFFFFFh
0x18005a346  jnz     short loc_18005A353
0x18005a348  mov     dword ptr [rsi], 80030102h
0x18005a34e  jmp     loc_18005A419
0x18005a353  mov     dword ptr [rsi], 0
0x18005a359  cmp     ebp, 200000h
0x18005a35f  jbe     short loc_18005A36C
0x18005a361  mov     dword ptr [rsi], 80030070h
0x18005a367  jmp     loc_18005A419
0x18005a36c  mov     rcx, rbx; this
0x18005a36f  test    dil, dil
0x18005a372  jz      short loc_18005A3C4
0x18005a374  call    ?CreateUpdateStreamIfNecessary@CNFFMappedStream@@AEAAJXZ; CNFFMappedStream::CreateUpdateStreamIfNecessary(void)
0x18005a379  mov     [rsi], eax
0x18005a37b  test    eax, eax
0x18005a37d  js      loc_18005A419
0x18005a383  mov     rcx, rbx; this
0x18005a386  call    ?BeginUsingUpdateStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::BeginUsingUpdateStream(void)
0x18005a38b  cmp     ebp, [rbx+24h]
0x18005a38e  jbe     short loc_18005A3BC
0x18005a390  mov     rcx, [rbx+8]
0x18005a394  lea     rdx, [rsp+58h+arg_20]
0x18005a39c  mov     dword ptr [rsp+58h+arg_20], ebp
0x18005a3a3  mov     dword ptr [rsp+58h+arg_20+4], 0
0x18005a3ae  call    ?SetFileSize@CNtfsStream@@AEAAJAEBV?$TXLargeIntegerWrapper@T_ULARGE_INTEGER@@K_K@@@Z; CNtfsStream::SetFileSize(TXLargeIntegerWrapper<_ULARGE_INTEGER,ulong,unsigned __int64> const &)
0x18005a3b3  mov     [rsi], eax
0x18005a3b5  test    eax, eax
0x18005a3b7  js      short loc_18005A403
0x18005a3b9  mov     [rbx+24h], ebp
0x18005a3bc  xor     edi, edi
0x18005a3be  lea     r14d, [rdi+1]
0x18005a3c2  jmp     short loc_18005A3D0
0x18005a3c4  xor     r14d, r14d
0x18005a3c7  call    ?BeginUsingLatestStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::BeginUsingLatestStream(void)
0x18005a3cc  lea     edi, [r14+1]
0x18005a3d0  cmp     ebp, [rbx+20h]
0x18005a3d3  jz      short loc_18005A3FB
0x18005a3d5  mov     rcx, [rbx+18h]; pv
0x18005a3d9  mov     rdx, rbp; cb
0x18005a3dc  call    cs:__imp_CoTaskMemRealloc
0x18005a3e2  test    rax, rax
0x18005a3e5  jnz     short loc_18005A3EF
0x18005a3e7  mov     dword ptr [rsi], 8007000Eh
0x18005a3ed  jmp     short loc_18005A3FE
0x18005a3ef  mov     [rbx+18h], rax
0x18005a3f3  test    r15, r15
0x18005a3f6  jz      short loc_18005A3FB
0x18005a3f8  mov     [r15], rax
0x18005a3fb  mov     [rbx+20h], ebp
0x18005a3fe  test    r14d, r14d
0x18005a401  jz      short loc_18005A40D
0x18005a403  mov     rcx, rbx; this
0x18005a406  call    ?EndUsingUpdateStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::EndUsingUpdateStream(void)
0x18005a40b  jmp     short loc_18005A419
0x18005a40d  test    edi, edi
0x18005a40f  jz      short loc_18005A419
0x18005a411  mov     rcx, rbx; this
0x18005a414  call    ?EndUsingLatestStream@CNFFMappedStream@@AEAAXXZ; CNFFMappedStream::EndUsingLatestStream(void)
0x18005a419  mov     rax, [rbx+8]
0x18005a41d  mov     rcx, [rax+68h]
0x18005a421  mov     rax, [rcx]
0x18005a424  mov     rax, [rax+20h]
0x18005a428  add     rsp, 28h
0x18005a42c  pop     r15
0x18005a42e  pop     r14
0x18005a430  pop     rdi
0x18005a431  pop     rsi
0x18005a432  pop     rbp
0x18005a433  pop     rbx
0x18005a434  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
