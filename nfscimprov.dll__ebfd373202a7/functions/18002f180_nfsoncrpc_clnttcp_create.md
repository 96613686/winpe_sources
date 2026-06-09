# nfsoncrpc_clnttcp_create

- ea: `0x18002f180`
- end: `0x18002f395`
- name: `nfsoncrpc_clnttcp_create`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18002eaec`

## callees

- `0x180002178`
- `0x18002e7c4`
- `0x18002f180`
- `0x180030160`
- `0x180030348`
- `0x1800306c0`
- `0x180030c28`
- `0x1800349fc`
- `0x180035b02`
- `0x180037010`

## import_xrefs

- `msvcrt!fprintf` at `0x18002f1dc`
- `msvcrt!fprintf` at `0x18002f358`
- `msvcrt!fprintf` at `0x18002f1dc`
- `msvcrt!fprintf` at `0x18002f358`
- `KERNEL32!DeleteCriticalSection` at `0x18002f20a`
- `KERNEL32!DeleteCriticalSection` at `0x18002f20a`
- `KERNEL32!GlobalAlloc` at `0x18002f1bc`
- `KERNEL32!GlobalAlloc` at `0x18002f338`
- `KERNEL32!GlobalAlloc` at `0x18002f1bc`
- `KERNEL32!GlobalAlloc` at `0x18002f338`
- `KERNEL32!GlobalFree` at `0x18002f213`
- `KERNEL32!GlobalFree` at `0x18002f227`
- `KERNEL32!GlobalFree` at `0x18002f213`
- `KERNEL32!GlobalFree` at `0x18002f227`

## string_xrefs

- `0x18002f1d5`: `clnttcp_create: out of memory\n`
- `0x18002f351`: `clnttcp_create: out of memory\n`

## pseudocode

```c
char *__fastcall nfsoncrpc_clnttcp_create(__int64 a1, int a2, int a3, unsigned int a4, unsigned int a5)
{
  char *v9; // rbx
  int v10; // ebp
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  FILE *v13; // rax
  _QWORD *v14; // rdi
  void (__fastcall *v16)(_QWORD *); // rax
  char *v17; // rax
  FILE *v18; // rax
  _DWORD v19[38]; // [rsp+30h] [rbp-98h] BYREF

  memset_0(v19, 0, 0x48u);
  v9 = 0;
  v10 = 0;
  v11 = GlobalAlloc(0x40u, 0x120u);
  v12 = v11;
  if ( v11 )
  {
    *(_QWORD *)((char *)v11 + 12) = 0;
    v14 = (_QWORD *)(a1 + 184);
    *v11 = *(_QWORD *)(a1 + 184);
    *(_QWORD *)(a1 + 184) = -1;
    v11[19] = 128;
    nfsoncrpc_getdest(a1, v11 + 3);
    v19[0] = nfsoncrpc_get_next_xid();
    v19[1] = 0;
    v19[2] = 2;
    v19[3] = a2;
    v19[4] = a3;
    v12[26] = off_1800540D0;
    *((_DWORD *)v12 + 50) = 0;
    v12[29] = (char *)v12 + 172;
    v12[28] = (char *)v12 + 172;
    *((_DWORD *)v12 + 60) = 24;
    if ( (unsigned int)xdr_callhdr(v12 + 25, v19) )
    {
      *((_DWORD *)v12 + 49) = (*(__int64 (__fastcall **)(_QWORD *))(v12[26] + 32LL))(v12 + 25);
      v16 = *(void (__fastcall **)(_QWORD *))(v12[26] + 56LL);
      if ( v16 )
        v16(v12 + 25);
      if ( (unsigned int)xdrrec_create(v12 + 25, a4, a5, v12) && v12[28] )
      {
        v17 = (char *)GlobalAlloc(0x40u, 0x40u);
        v9 = v17;
        if ( v17 )
        {
          v10 = SafeInitializeCriticalSection((LPCRITICAL_SECTION)(v17 + 24));
          if ( v10 >= 0 )
          {
            *((_QWORD *)v9 + 2) = v12;
            *((_QWORD *)v9 + 1) = &off_180054000;
            *(_QWORD *)v9 = authnone_create();
            return v9;
          }
        }
        else
        {
          v18 = _acrt_iob_func(2u);
          fprintf(v18, "clnttcp_create: out of memory\n");
        }
      }
    }
  }
  else
  {
    v13 = _acrt_iob_func(2u);
    fprintf(v13, "clnttcp_create: out of memory\n");
    v14 = (_QWORD *)(a1 + 184);
  }
  rpc_createerr = 12;
  dword_180056908 = -1;
  if ( v9 )
  {
    if ( !v10 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
    GlobalFree(v9);
  }
  if ( v12 )
  {
    *v14 = *v12;
    GlobalFree(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18002f180  push    rbx
0x18002f182  push    rbp
0x18002f183  push    rsi
0x18002f184  push    rdi
0x18002f185  push    r12
0x18002f187  push    r13
0x18002f189  push    r14
0x18002f18b  push    r15
0x18002f18d  sub     rsp, 88h
0x18002f194  mov     r13d, edx
0x18002f197  mov     r12d, r8d
0x18002f19a  xor     edx, edx; Val
0x18002f19c  mov     r14, rcx
0x18002f19f  lea     rcx, [rsp+0C8h+var_98]; void *
0x18002f1a4  mov     r15d, r9d
0x18002f1a7  lea     r8d, [rdx+48h]; Size
0x18002f1ab  call    memset_0
0x18002f1b0  xor     ebx, ebx
0x18002f1b2  mov     edx, 120h; dwBytes
0x18002f1b7  xor     ebp, ebp
0x18002f1b9  lea     ecx, [rbx+40h]; uFlags
0x18002f1bc  call    cs:__imp_GlobalAlloc
0x18002f1c2  mov     rsi, rax
0x18002f1c5  test    rax, rax
0x18002f1c8  jnz     short loc_18002F243
0x18002f1ca  lea     ecx, [rbx+2]; Ix
0x18002f1cd  call    __acrt_iob_func
0x18002f1d2  mov     rcx, rax; Stream
0x18002f1d5  lea     rdx, aClnttcpCreateO; "clnttcp_create: out of memory\n"
0x18002f1dc  call    cs:__imp_fprintf
0x18002f1e2  lea     rdi, [r14+0B8h]
0x18002f1e9  mov     cs:rpc_createerr, 0Ch
0x18002f1f3  mov     cs:dword_180056908, 0FFFFFFFFh
0x18002f1fd  test    rbx, rbx
0x18002f200  jz      short loc_18002F219
0x18002f202  test    ebp, ebp
0x18002f204  jnz     short loc_18002F210
0x18002f206  lea     rcx, [rbx+18h]; lpCriticalSection
0x18002f20a  call    cs:__imp_DeleteCriticalSection
0x18002f210  mov     rcx, rbx; hMem
0x18002f213  call    cs:__imp_GlobalFree
0x18002f219  test    rsi, rsi
0x18002f21c  jz      short loc_18002F22D
0x18002f21e  mov     rax, [rsi]
0x18002f221  mov     rcx, rsi; hMem
0x18002f224  mov     [rdi], rax
0x18002f227  call    cs:__imp_GlobalFree
0x18002f22d  xor     eax, eax
0x18002f22f  add     rsp, 88h
0x18002f236  pop     r15
0x18002f238  pop     r14
0x18002f23a  pop     r13
0x18002f23c  pop     r12
0x18002f23e  pop     rdi
0x18002f23f  pop     rsi
0x18002f240  pop     rbp
0x18002f241  pop     rbx
0x18002f242  retn
0x18002f243  mov     [rax+0Ch], rbx
0x18002f247  lea     rdi, [r14+0B8h]
0x18002f24e  mov     rax, [rdi]
0x18002f251  lea     r8, [rsi+98h]
0x18002f258  mov     [rsi], rax
0x18002f25b  lea     rdx, [rsi+18h]
0x18002f25f  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18002f266  mov     rcx, r14
0x18002f269  mov     qword ptr [r8], 80h
0x18002f270  call    nfsoncrpc_getdest
0x18002f275  call    nfsoncrpc_get_next_xid
0x18002f27a  mov     [rsp+0C8h+var_98], eax
0x18002f27e  lea     r14, [rsi+0C8h]
0x18002f285  mov     [rsp+0C8h+var_94], ebx
0x18002f289  lea     rax, [rsi+0ACh]
0x18002f290  mov     [rsp+0C8h+var_90], 2
0x18002f298  lea     rcx, off_1800540D0
0x18002f29f  mov     [rsp+0C8h+var_8C], r13d
0x18002f2a4  lea     rdx, [rsp+0C8h+var_98]
0x18002f2a9  mov     [rsp+0C8h+var_88], r12d
0x18002f2ae  mov     [r14+8], rcx
0x18002f2b2  mov     rcx, r14
0x18002f2b5  mov     [r14], ebx
0x18002f2b8  mov     [r14+20h], rax
0x18002f2bc  mov     [r14+18h], rax
0x18002f2c0  mov     dword ptr [r14+28h], 18h
0x18002f2c8  call    xdr_callhdr
0x18002f2cd  test    eax, eax
0x18002f2cf  jz      loc_18002F1E9
0x18002f2d5  mov     rax, [rsi+0D0h]
0x18002f2dc  mov     rcx, r14
0x18002f2df  mov     rax, [rax+20h]
0x18002f2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2e8  mov     [rsi+0C4h], eax
0x18002f2ee  mov     rax, [rsi+0D0h]
0x18002f2f5  mov     rax, [rax+38h]
0x18002f2f9  test    rax, rax
0x18002f2fc  jz      short loc_18002F306
0x18002f2fe  mov     rcx, r14
0x18002f301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f306  mov     r8d, [rsp+0C8h+arg_20]
0x18002f30e  mov     r9, rsi
0x18002f311  mov     edx, r15d
0x18002f314  mov     rcx, r14
0x18002f317  call    xdrrec_create
0x18002f31c  test    eax, eax
0x18002f31e  jz      loc_18002F1E9
0x18002f324  cmp     [rsi+0E0h], rbx
0x18002f32b  jz      loc_18002F1E9
0x18002f331  mov     ecx, 40h ; '@'; uFlags
0x18002f336  mov     edx, ecx; dwBytes
0x18002f338  call    cs:__imp_GlobalAlloc
0x18002f33e  mov     rbx, rax
0x18002f341  test    rax, rax
0x18002f344  jnz     short loc_18002F363
0x18002f346  lea     ecx, [rax+2]; Ix
0x18002f349  call    __acrt_iob_func
0x18002f34e  mov     rcx, rax; Stream
0x18002f351  lea     rdx, aClnttcpCreateO; "clnttcp_create: out of memory\n"
0x18002f358  call    cs:__imp_fprintf
0x18002f35e  jmp     loc_18002F1E9
0x18002f363  lea     rcx, [rax+18h]; lpCriticalSection
0x18002f367  call    SafeInitializeCriticalSection
0x18002f36c  mov     ebp, eax
0x18002f36e  test    eax, eax
0x18002f370  js      loc_18002F1E9
0x18002f376  lea     rax, off_180054000
0x18002f37d  mov     [rbx+10h], rsi
0x18002f381  mov     [rbx+8], rax
0x18002f385  call    authnone_create
0x18002f38a  mov     [rbx], rax
0x18002f38d  mov     rax, rbx
0x18002f390  jmp     loc_18002F22F
```
