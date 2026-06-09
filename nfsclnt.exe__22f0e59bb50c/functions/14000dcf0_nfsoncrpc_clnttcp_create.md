# nfsoncrpc_clnttcp_create

- ea: `0x14000dcf0`
- end: `0x14000df05`
- name: `nfsoncrpc_clnttcp_create`
- size: `533`
- prototype: `char *__fastcall(__int64, int, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000d5f8`

## callees

- `0x140001b2c`
- `0x14000c290`
- `0x14000c4dc`
- `0x14000d0e0`
- `0x14000dcf0`
- `0x14000ee24`
- `0x14000f388`
- `0x14000fa94`
- `0x14001830e`
- `0x140019010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000dd2c`
- `KERNEL32!GlobalAlloc` at `0x14000dea8`
- `KERNEL32!GlobalAlloc` at `0x14000dd2c`
- `KERNEL32!GlobalAlloc` at `0x14000dea8`
- `KERNEL32!GlobalFree` at `0x14000dd83`
- `KERNEL32!GlobalFree` at `0x14000dd97`
- `KERNEL32!GlobalFree` at `0x14000dd83`
- `KERNEL32!GlobalFree` at `0x14000dd97`
- `KERNEL32!DeleteCriticalSection` at `0x14000dd7a`
- `KERNEL32!DeleteCriticalSection` at `0x14000dd7a`
- `msvcrt!fprintf` at `0x14000dd4c`
- `msvcrt!fprintf` at `0x14000dec8`
- `msvcrt!fprintf` at `0x14000dd4c`
- `msvcrt!fprintf` at `0x14000dec8`

## string_xrefs

- `0x14000dd45`: `clnttcp_create: out of memory\n`
- `0x14000dec1`: `clnttcp_create: out of memory\n`

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
    v12[26] = off_140020030;
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
            *((_QWORD *)v9 + 1) = &off_140020070;
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
  dword_140022248 = -1;
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
0x14000dcf0  push    rbx
0x14000dcf2  push    rbp
0x14000dcf3  push    rsi
0x14000dcf4  push    rdi
0x14000dcf5  push    r12
0x14000dcf7  push    r13
0x14000dcf9  push    r14
0x14000dcfb  push    r15
0x14000dcfd  sub     rsp, 88h
0x14000dd04  mov     r13d, edx
0x14000dd07  mov     r12d, r8d
0x14000dd0a  xor     edx, edx; Val
0x14000dd0c  mov     r14, rcx
0x14000dd0f  lea     rcx, [rsp+0C8h+var_98]; void *
0x14000dd14  mov     r15d, r9d
0x14000dd17  lea     r8d, [rdx+48h]; Size
0x14000dd1b  call    memset_0
0x14000dd20  xor     ebx, ebx
0x14000dd22  mov     edx, 120h; dwBytes
0x14000dd27  xor     ebp, ebp
0x14000dd29  lea     ecx, [rbx+40h]; uFlags
0x14000dd2c  call    cs:__imp_GlobalAlloc
0x14000dd32  mov     rsi, rax
0x14000dd35  test    rax, rax
0x14000dd38  jnz     short loc_14000DDB3
0x14000dd3a  lea     ecx, [rbx+2]; Ix
0x14000dd3d  call    __acrt_iob_func
0x14000dd42  mov     rcx, rax; Stream
0x14000dd45  lea     rdx, aClnttcpCreateO; "clnttcp_create: out of memory\n"
0x14000dd4c  call    cs:__imp_fprintf
0x14000dd52  lea     rdi, [r14+0B8h]
0x14000dd59  mov     cs:rpc_createerr, 0Ch
0x14000dd63  mov     cs:dword_140022248, 0FFFFFFFFh
0x14000dd6d  test    rbx, rbx
0x14000dd70  jz      short loc_14000DD89
0x14000dd72  test    ebp, ebp
0x14000dd74  jnz     short loc_14000DD80
0x14000dd76  lea     rcx, [rbx+18h]; lpCriticalSection
0x14000dd7a  call    cs:__imp_DeleteCriticalSection
0x14000dd80  mov     rcx, rbx; hMem
0x14000dd83  call    cs:__imp_GlobalFree
0x14000dd89  test    rsi, rsi
0x14000dd8c  jz      short loc_14000DD9D
0x14000dd8e  mov     rax, [rsi]
0x14000dd91  mov     rcx, rsi; hMem
0x14000dd94  mov     [rdi], rax
0x14000dd97  call    cs:__imp_GlobalFree
0x14000dd9d  xor     eax, eax
0x14000dd9f  add     rsp, 88h
0x14000dda6  pop     r15
0x14000dda8  pop     r14
0x14000ddaa  pop     r13
0x14000ddac  pop     r12
0x14000ddae  pop     rdi
0x14000ddaf  pop     rsi
0x14000ddb0  pop     rbp
0x14000ddb1  pop     rbx
0x14000ddb2  retn
0x14000ddb3  mov     [rax+0Ch], rbx
0x14000ddb7  lea     rdi, [r14+0B8h]
0x14000ddbe  mov     rax, [rdi]
0x14000ddc1  lea     r8, [rsi+98h]
0x14000ddc8  mov     [rsi], rax
0x14000ddcb  lea     rdx, [rsi+18h]
0x14000ddcf  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x14000ddd6  mov     rcx, r14
0x14000ddd9  mov     qword ptr [r8], 80h
0x14000dde0  call    nfsoncrpc_getdest
0x14000dde5  call    nfsoncrpc_get_next_xid
0x14000ddea  mov     [rsp+0C8h+var_98], eax
0x14000ddee  lea     r14, [rsi+0C8h]
0x14000ddf5  mov     [rsp+0C8h+var_94], ebx
0x14000ddf9  lea     rax, [rsi+0ACh]
0x14000de00  mov     [rsp+0C8h+var_90], 2
0x14000de08  lea     rcx, off_140020030
0x14000de0f  mov     [rsp+0C8h+var_8C], r13d
0x14000de14  lea     rdx, [rsp+0C8h+var_98]
0x14000de19  mov     [rsp+0C8h+var_88], r12d
0x14000de1e  mov     [r14+8], rcx
0x14000de22  mov     rcx, r14
0x14000de25  mov     [r14], ebx
0x14000de28  mov     [r14+20h], rax
0x14000de2c  mov     [r14+18h], rax
0x14000de30  mov     dword ptr [r14+28h], 18h
0x14000de38  call    xdr_callhdr
0x14000de3d  test    eax, eax
0x14000de3f  jz      loc_14000DD59
0x14000de45  mov     rax, [rsi+0D0h]
0x14000de4c  mov     rcx, r14
0x14000de4f  mov     rax, [rax+20h]
0x14000de53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de58  mov     [rsi+0C4h], eax
0x14000de5e  mov     rax, [rsi+0D0h]
0x14000de65  mov     rax, [rax+38h]
0x14000de69  test    rax, rax
0x14000de6c  jz      short loc_14000DE76
0x14000de6e  mov     rcx, r14
0x14000de71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de76  mov     r8d, [rsp+0C8h+arg_20]
0x14000de7e  mov     r9, rsi
0x14000de81  mov     edx, r15d
0x14000de84  mov     rcx, r14
0x14000de87  call    xdrrec_create
0x14000de8c  test    eax, eax
0x14000de8e  jz      loc_14000DD59
0x14000de94  cmp     [rsi+0E0h], rbx
0x14000de9b  jz      loc_14000DD59
0x14000dea1  mov     ecx, 40h ; '@'; uFlags
0x14000dea6  mov     edx, ecx; dwBytes
0x14000dea8  call    cs:__imp_GlobalAlloc
0x14000deae  mov     rbx, rax
0x14000deb1  test    rax, rax
0x14000deb4  jnz     short loc_14000DED3
0x14000deb6  lea     ecx, [rax+2]; Ix
0x14000deb9  call    __acrt_iob_func
0x14000debe  mov     rcx, rax; Stream
0x14000dec1  lea     rdx, aClnttcpCreateO; "clnttcp_create: out of memory\n"
0x14000dec8  call    cs:__imp_fprintf
0x14000dece  jmp     loc_14000DD59
0x14000ded3  lea     rcx, [rax+18h]; lpCriticalSection
0x14000ded7  call    SafeInitializeCriticalSection
0x14000dedc  mov     ebp, eax
0x14000dede  test    eax, eax
0x14000dee0  js      loc_14000DD59
0x14000dee6  lea     rax, off_140020070
0x14000deed  mov     [rbx+10h], rsi
0x14000def1  mov     [rbx+8], rax
0x14000def5  call    authnone_create
0x14000defa  mov     [rbx], rax
0x14000defd  mov     rax, rbx
0x14000df00  jmp     loc_14000DD9F
```
