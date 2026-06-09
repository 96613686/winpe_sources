# nfsoncrpc_clntudp_create

- ea: `0x18002fe34`
- end: `0x18003006d`
- name: `nfsoncrpc_clntudp_create`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002eaec`

## callees

- `0x180002178`
- `0x18002e7c4`
- `0x18002fe34`
- `0x180030160`
- `0x180030348`
- `0x180030c28`
- `0x1800349fc`
- `0x180035b02`
- `0x180037010`

## import_xrefs

- `msvcrt!fprintf` at `0x18002fec8`
- `msvcrt!fprintf` at `0x180030030`
- `msvcrt!fprintf` at `0x18002fec8`
- `msvcrt!fprintf` at `0x180030030`
- `KERNEL32!DeleteCriticalSection` at `0x18002fef6`
- `KERNEL32!DeleteCriticalSection` at `0x18002fef6`
- `KERNEL32!GlobalAlloc` at `0x18002fea8`
- `KERNEL32!GlobalAlloc` at `0x180030010`
- `KERNEL32!GlobalAlloc` at `0x18002fea8`
- `KERNEL32!GlobalAlloc` at `0x180030010`
- `KERNEL32!GlobalFree` at `0x18002feff`
- `KERNEL32!GlobalFree` at `0x18002ff13`
- `KERNEL32!GlobalFree` at `0x18002feff`
- `KERNEL32!GlobalFree` at `0x18002ff13`

## string_xrefs

- `0x18002fec1`: `clntudp_create: out of memory\n`
- `0x180030029`: `clntudp_create: out of memory\n`

## pseudocode

```c
char *__fastcall nfsoncrpc_clntudp_create(__int64 a1, int a2, int a3, __int64 a4, int a5, int a6)
{
  char *v9; // rdi
  int v10; // ebp
  int v11; // r15d
  int v12; // r12d
  unsigned int v13; // r12d
  unsigned int v14; // r15d
  char *v15; // rax
  _QWORD *v16; // rsi
  FILE *v17; // rax
  _QWORD *v18; // r14
  __int64 v20; // rax
  char *v21; // rax
  FILE *v22; // rax
  _DWORD v23[38]; // [rsp+20h] [rbp-98h] BYREF

  memset_0(v23, 0, 0x48u);
  v9 = 0;
  v10 = 0;
  v11 = 8800;
  v12 = 8800;
  if ( a5 )
    v12 = a5;
  v13 = (v12 + 3) & 0xFFFFFFFC;
  if ( a6 )
    v11 = a6;
  v14 = (v11 + 3) & 0xFFFFFFFC;
  v15 = (char *)GlobalAlloc(0x40u, v13 + v14 + 288);
  v16 = v15;
  if ( v15 )
  {
    *((_QWORD *)v15 + 17) = 128;
    *((_QWORD *)v15 + 34) = &v15[v14 + 284];
    nfsoncrpc_getdest(a1, v15 + 8);
    v18 = (_QWORD *)(a1 + 184);
    *v16 = *v18;
    *v18 = -1;
    v16[18] = a4;
    *((_DWORD *)v16 + 38) = -1;
    *((_DWORD *)v16 + 39) = -1;
    *((_DWORD *)v16 + 67) = v13;
    *((_DWORD *)v16 + 70) = v14;
    v23[0] = nfsoncrpc_get_next_xid();
    v23[3] = a2;
    v23[1] = 0;
    v23[2] = 2;
    v23[4] = a3;
    v20 = v16[34];
    v16[23] = off_1800540D0;
    *((_DWORD *)v16 + 44) = 0;
    v16[26] = v20;
    v16[25] = v20;
    *((_DWORD *)v16 + 54) = v13;
    if ( (unsigned int)xdr_callhdr(v16 + 22, v23) )
    {
      *((_DWORD *)v16 + 66) = (*(__int64 (__fastcall **)(_QWORD *))(v16[23] + 32LL))(v16 + 22);
      v21 = (char *)GlobalAlloc(0x40u, 0x40u);
      v9 = v21;
      if ( v21 )
      {
        v10 = SafeInitializeCriticalSection((LPCRITICAL_SECTION)(v21 + 24));
        if ( v10 >= 0 )
        {
          *((_QWORD *)v9 + 2) = v16;
          *((_QWORD *)v9 + 1) = &off_180054030;
          *(_QWORD *)v9 = authnone_create();
          return v9;
        }
      }
      else
      {
        v22 = _acrt_iob_func(2u);
        fprintf(v22, "clntudp_create: out of memory\n");
      }
    }
  }
  else
  {
    v17 = _acrt_iob_func(2u);
    fprintf(v17, "clntudp_create: out of memory\n");
    v18 = (_QWORD *)(a1 + 184);
  }
  rpc_createerr = 12;
  dword_180056908 = -1;
  if ( v9 )
  {
    if ( !v10 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 24));
    GlobalFree(v9);
  }
  if ( v16 )
  {
    *v18 = *v16;
    GlobalFree(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18002fe34  mov     [rsp+arg_8], edx
0x18002fe38  push    rbx
0x18002fe39  push    rbp
0x18002fe3a  push    rsi
0x18002fe3b  push    rdi
0x18002fe3c  push    r12
0x18002fe3e  push    r13
0x18002fe40  push    r14
0x18002fe42  push    r15
0x18002fe44  sub     rsp, 78h
0x18002fe48  xor     edx, edx; Val
0x18002fe4a  mov     r13d, r8d
0x18002fe4d  mov     r14, rcx
0x18002fe50  mov     rbx, r9
0x18002fe53  lea     rcx, [rsp+0B8h+var_98]; void *
0x18002fe58  lea     r8d, [rdx+48h]; Size
0x18002fe5c  call    memset_0
0x18002fe61  mov     eax, [rsp+0B8h+arg_20]
0x18002fe68  mov     ecx, 0FFFFFFFCh
0x18002fe6d  xor     edi, edi
0x18002fe6f  xor     ebp, ebp
0x18002fe71  test    eax, eax
0x18002fe73  mov     r15d, 2260h
0x18002fe79  mov     r12d, r15d
0x18002fe7c  cmovnz  r12d, eax
0x18002fe80  mov     eax, [rsp+0B8h+arg_28]
0x18002fe87  add     r12d, 3
0x18002fe8b  and     r12d, ecx
0x18002fe8e  test    eax, eax
0x18002fe90  cmovnz  r15d, eax
0x18002fe94  add     r15d, 3
0x18002fe98  and     r15d, ecx
0x18002fe9b  lea     ecx, [rdi+40h]; uFlags
0x18002fe9e  lea     edx, [r15+120h]
0x18002fea5  add     edx, r12d; dwBytes
0x18002fea8  call    cs:__imp_GlobalAlloc
0x18002feae  mov     rsi, rax
0x18002feb1  test    rax, rax
0x18002feb4  jnz     short loc_18002FF2C
0x18002feb6  lea     ecx, [rdi+2]; Ix
0x18002feb9  call    __acrt_iob_func
0x18002febe  mov     rcx, rax; Stream
0x18002fec1  lea     rdx, aClntudpCreateO; "clntudp_create: out of memory\n"
0x18002fec8  call    cs:__imp_fprintf
0x18002fece  add     r14, 0B8h
0x18002fed5  mov     cs:rpc_createerr, 0Ch
0x18002fedf  mov     cs:dword_180056908, 0FFFFFFFFh
0x18002fee9  test    rdi, rdi
0x18002feec  jz      short loc_18002FF05
0x18002feee  test    ebp, ebp
0x18002fef0  jnz     short loc_18002FEFC
0x18002fef2  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002fef6  call    cs:__imp_DeleteCriticalSection
0x18002fefc  mov     rcx, rdi; hMem
0x18002feff  call    cs:__imp_GlobalFree
0x18002ff05  test    rsi, rsi
0x18002ff08  jz      short loc_18002FF19
0x18002ff0a  mov     rax, [rsi]
0x18002ff0d  mov     rcx, rsi; hMem
0x18002ff10  mov     [r14], rax
0x18002ff13  call    cs:__imp_GlobalFree
0x18002ff19  xor     eax, eax
0x18002ff1b  add     rsp, 78h
0x18002ff1f  pop     r15
0x18002ff21  pop     r14
0x18002ff23  pop     r13
0x18002ff25  pop     r12
0x18002ff27  pop     rdi
0x18002ff28  pop     rsi
0x18002ff29  pop     rbp
0x18002ff2a  pop     rbx
0x18002ff2b  retn
0x18002ff2c  lea     r8, [rax+88h]
0x18002ff33  mov     ecx, r15d
0x18002ff36  add     rcx, 11Ch
0x18002ff3d  mov     qword ptr [r8], 80h
0x18002ff44  add     rcx, rsi
0x18002ff47  lea     rdx, [rax+8]
0x18002ff4b  mov     [rax+110h], rcx
0x18002ff52  mov     rcx, r14
0x18002ff55  call    nfsoncrpc_getdest
0x18002ff5a  add     r14, 0B8h
0x18002ff61  mov     rax, [r14]
0x18002ff64  mov     [rsi], rax
0x18002ff67  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ff6b  mov     [r14], rax
0x18002ff6e  mov     [rsi+90h], rbx
0x18002ff75  mov     [rsi+98h], eax
0x18002ff7b  mov     [rsi+9Ch], eax
0x18002ff81  mov     [rsi+10Ch], r12d
0x18002ff88  mov     [rsi+118h], r15d
0x18002ff8f  call    nfsoncrpc_get_next_xid
0x18002ff94  mov     [rsp+0B8h+var_98], eax
0x18002ff98  lea     rbx, [rsi+0B0h]
0x18002ff9f  mov     eax, [rsp+0B8h+arg_8]
0x18002ffa6  lea     rcx, off_1800540D0
0x18002ffad  mov     [rsp+0B8h+var_8C], eax
0x18002ffb1  lea     rdx, [rsp+0B8h+var_98]
0x18002ffb6  mov     [rsp+0B8h+var_94], edi
0x18002ffba  mov     [rsp+0B8h+var_90], 2
0x18002ffc2  mov     [rsp+0B8h+var_88], r13d
0x18002ffc7  mov     rax, [rsi+110h]
0x18002ffce  mov     [rbx+8], rcx
0x18002ffd2  mov     rcx, rbx
0x18002ffd5  mov     [rbx], edi
0x18002ffd7  mov     [rbx+20h], rax
0x18002ffdb  mov     [rbx+18h], rax
0x18002ffdf  mov     [rbx+28h], r12d
0x18002ffe3  call    xdr_callhdr
0x18002ffe8  test    eax, eax
0x18002ffea  jz      loc_18002FED5
0x18002fff0  mov     rax, [rsi+0B8h]
0x18002fff7  mov     rcx, rbx
0x18002fffa  mov     rax, [rax+20h]
0x18002fffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030003  mov     ecx, 40h ; '@'; uFlags
0x180030008  mov     [rsi+108h], eax
0x18003000e  mov     edx, ecx; dwBytes
0x180030010  call    cs:__imp_GlobalAlloc
0x180030016  mov     rdi, rax
0x180030019  test    rax, rax
0x18003001c  jnz     short loc_18003003B
0x18003001e  lea     ecx, [rax+2]; Ix
0x180030021  call    __acrt_iob_func
0x180030026  mov     rcx, rax; Stream
0x180030029  lea     rdx, aClntudpCreateO; "clntudp_create: out of memory\n"
0x180030030  call    cs:__imp_fprintf
0x180030036  jmp     loc_18002FED5
0x18003003b  lea     rcx, [rax+18h]; lpCriticalSection
0x18003003f  call    SafeInitializeCriticalSection
0x180030044  mov     ebp, eax
0x180030046  test    eax, eax
0x180030048  js      loc_18002FED5
0x18003004e  lea     rax, off_180054030
0x180030055  mov     [rdi+10h], rsi
0x180030059  mov     [rdi+8], rax
0x18003005d  call    authnone_create
0x180030062  mov     [rdi], rax
0x180030065  mov     rax, rdi
0x180030068  jmp     loc_18002FF1B
```
