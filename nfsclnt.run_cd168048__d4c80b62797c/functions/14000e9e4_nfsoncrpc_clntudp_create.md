# nfsoncrpc_clntudp_create

- ea: `0x14000e9e4`
- end: `0x14000ec1d`
- name: `nfsoncrpc_clntudp_create`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000d5f8`

## callees

- `0x140001b2c`
- `0x14000c290`
- `0x14000c4dc`
- `0x14000d0e0`
- `0x14000e9e4`
- `0x14000f388`
- `0x14000fa94`
- `0x14001830e`
- `0x140019010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x14000ea58`
- `KERNEL32!GlobalAlloc` at `0x14000ebc0`
- `KERNEL32!GlobalAlloc` at `0x14000ea58`
- `KERNEL32!GlobalAlloc` at `0x14000ebc0`
- `KERNEL32!GlobalFree` at `0x14000eaaf`
- `KERNEL32!GlobalFree` at `0x14000eac3`
- `KERNEL32!GlobalFree` at `0x14000eaaf`
- `KERNEL32!GlobalFree` at `0x14000eac3`
- `KERNEL32!DeleteCriticalSection` at `0x14000eaa6`
- `KERNEL32!DeleteCriticalSection` at `0x14000eaa6`
- `msvcrt!fprintf` at `0x14000ea78`
- `msvcrt!fprintf` at `0x14000ebe0`
- `msvcrt!fprintf` at `0x14000ea78`
- `msvcrt!fprintf` at `0x14000ebe0`

## string_xrefs

- `0x14000ea71`: `clntudp_create: out of memory\n`
- `0x14000ebd9`: `clntudp_create: out of memory\n`

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
    v16[23] = off_140020030;
    v16[26] = v20;
    v16[25] = v20;
    *((_DWORD *)v16 + 44) = 0;
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
          *((_QWORD *)v9 + 1) = &off_1400200A0;
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
  dword_140022248 = -1;
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
0x14000e9e4  mov     [rsp+arg_8], edx
0x14000e9e8  push    rbx
0x14000e9e9  push    rbp
0x14000e9ea  push    rsi
0x14000e9eb  push    rdi
0x14000e9ec  push    r12
0x14000e9ee  push    r13
0x14000e9f0  push    r14
0x14000e9f2  push    r15
0x14000e9f4  sub     rsp, 78h
0x14000e9f8  xor     edx, edx; Val
0x14000e9fa  mov     r13d, r8d
0x14000e9fd  mov     r14, rcx
0x14000ea00  mov     rbx, r9
0x14000ea03  lea     rcx, [rsp+0B8h+var_98]; void *
0x14000ea08  lea     r8d, [rdx+48h]; Size
0x14000ea0c  call    memset_0
0x14000ea11  mov     eax, [rsp+0B8h+arg_20]
0x14000ea18  mov     ecx, 0FFFFFFFCh
0x14000ea1d  xor     edi, edi
0x14000ea1f  xor     ebp, ebp
0x14000ea21  test    eax, eax
0x14000ea23  mov     r15d, 2260h
0x14000ea29  mov     r12d, r15d
0x14000ea2c  cmovnz  r12d, eax
0x14000ea30  mov     eax, [rsp+0B8h+arg_28]
0x14000ea37  add     r12d, 3
0x14000ea3b  and     r12d, ecx
0x14000ea3e  test    eax, eax
0x14000ea40  cmovnz  r15d, eax
0x14000ea44  add     r15d, 3
0x14000ea48  and     r15d, ecx
0x14000ea4b  lea     ecx, [rdi+40h]; uFlags
0x14000ea4e  lea     edx, [r15+120h]
0x14000ea55  add     edx, r12d; dwBytes
0x14000ea58  call    cs:__imp_GlobalAlloc
0x14000ea5e  mov     rsi, rax
0x14000ea61  test    rax, rax
0x14000ea64  jnz     short loc_14000EADC
0x14000ea66  lea     ecx, [rdi+2]; Ix
0x14000ea69  call    __acrt_iob_func
0x14000ea6e  mov     rcx, rax; Stream
0x14000ea71  lea     rdx, aClntudpCreateO; "clntudp_create: out of memory\n"
0x14000ea78  call    cs:__imp_fprintf
0x14000ea7e  add     r14, 0B8h
0x14000ea85  mov     cs:rpc_createerr, 0Ch
0x14000ea8f  mov     cs:dword_140022248, 0FFFFFFFFh
0x14000ea99  test    rdi, rdi
0x14000ea9c  jz      short loc_14000EAB5
0x14000ea9e  test    ebp, ebp
0x14000eaa0  jnz     short loc_14000EAAC
0x14000eaa2  lea     rcx, [rdi+18h]; lpCriticalSection
0x14000eaa6  call    cs:__imp_DeleteCriticalSection
0x14000eaac  mov     rcx, rdi; hMem
0x14000eaaf  call    cs:__imp_GlobalFree
0x14000eab5  test    rsi, rsi
0x14000eab8  jz      short loc_14000EAC9
0x14000eaba  mov     rax, [rsi]
0x14000eabd  mov     rcx, rsi; hMem
0x14000eac0  mov     [r14], rax
0x14000eac3  call    cs:__imp_GlobalFree
0x14000eac9  xor     eax, eax
0x14000eacb  add     rsp, 78h
0x14000eacf  pop     r15
0x14000ead1  pop     r14
0x14000ead3  pop     r13
0x14000ead5  pop     r12
0x14000ead7  pop     rdi
0x14000ead8  pop     rsi
0x14000ead9  pop     rbp
0x14000eada  pop     rbx
0x14000eadb  retn
0x14000eadc  lea     r8, [rax+88h]
0x14000eae3  mov     ecx, r15d
0x14000eae6  add     rcx, 11Ch
0x14000eaed  mov     qword ptr [r8], 80h
0x14000eaf4  add     rcx, rsi
0x14000eaf7  lea     rdx, [rax+8]
0x14000eafb  mov     [rax+110h], rcx
0x14000eb02  mov     rcx, r14
0x14000eb05  call    nfsoncrpc_getdest
0x14000eb0a  add     r14, 0B8h
0x14000eb11  mov     rax, [r14]
0x14000eb14  mov     [rsi], rax
0x14000eb17  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000eb1b  mov     [r14], rax
0x14000eb1e  mov     [rsi+90h], rbx
0x14000eb25  mov     [rsi+98h], eax
0x14000eb2b  mov     [rsi+9Ch], eax
0x14000eb31  mov     [rsi+10Ch], r12d
0x14000eb38  mov     [rsi+118h], r15d
0x14000eb3f  call    nfsoncrpc_get_next_xid
0x14000eb44  mov     [rsp+0B8h+var_98], eax
0x14000eb48  lea     rbx, [rsi+0B0h]
0x14000eb4f  mov     eax, [rsp+0B8h+arg_8]
0x14000eb56  lea     rcx, off_140020030
0x14000eb5d  mov     [rsp+0B8h+var_8C], eax
0x14000eb61  lea     rdx, [rsp+0B8h+var_98]
0x14000eb66  mov     [rsp+0B8h+var_94], edi
0x14000eb6a  mov     [rsp+0B8h+var_90], 2
0x14000eb72  mov     [rsp+0B8h+var_88], r13d
0x14000eb77  mov     rax, [rsi+110h]
0x14000eb7e  mov     [rbx+8], rcx
0x14000eb82  mov     rcx, rbx
0x14000eb85  mov     [rbx+20h], rax
0x14000eb89  mov     [rbx+18h], rax
0x14000eb8d  mov     [rbx], edi
0x14000eb8f  mov     [rbx+28h], r12d
0x14000eb93  call    xdr_callhdr
0x14000eb98  test    eax, eax
0x14000eb9a  jz      loc_14000EA85
0x14000eba0  mov     rax, [rsi+0B8h]
0x14000eba7  mov     rcx, rbx
0x14000ebaa  mov     rax, [rax+20h]
0x14000ebae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ebb3  mov     ecx, 40h ; '@'; uFlags
0x14000ebb8  mov     [rsi+108h], eax
0x14000ebbe  mov     edx, ecx; dwBytes
0x14000ebc0  call    cs:__imp_GlobalAlloc
0x14000ebc6  mov     rdi, rax
0x14000ebc9  test    rax, rax
0x14000ebcc  jnz     short loc_14000EBEB
0x14000ebce  lea     ecx, [rax+2]; Ix
0x14000ebd1  call    __acrt_iob_func
0x14000ebd6  mov     rcx, rax; Stream
0x14000ebd9  lea     rdx, aClntudpCreateO; "clntudp_create: out of memory\n"
0x14000ebe0  call    cs:__imp_fprintf
0x14000ebe6  jmp     loc_14000EA85
0x14000ebeb  lea     rcx, [rax+18h]; lpCriticalSection
0x14000ebef  call    SafeInitializeCriticalSection
0x14000ebf4  mov     ebp, eax
0x14000ebf6  test    eax, eax
0x14000ebf8  js      loc_14000EA85
0x14000ebfe  lea     rax, off_1400200A0
0x14000ec05  mov     [rdi+10h], rsi
0x14000ec09  mov     [rdi+8], rax
0x14000ec0d  call    authnone_create
0x14000ec12  mov     [rdi], rax
0x14000ec15  mov     rax, rdi
0x14000ec18  jmp     loc_14000EACB
```
