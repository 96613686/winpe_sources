# Container::Manager::Client::ConvertToContainerStorageInfo(__MIDL_CmRpc_0002,_CMS_STORAGE_INFO *,ulong *)

- ea: `0x1800044b0`
- end: `0x180004648`
- name: `?ConvertToContainerStorageInfo@Client@Manager@Container@@YAJU__MIDL_CmRpc_0002@@PEAU_CMS_STORAGE_INFO@@PEAK@Z`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180009110`
- `0x18000c420`

## callees

- `0x1800044b0`
- `0x1800066e4`
- `0x180007074`
- `0x18000ee00`

## string_xrefs

- `0x1800045da`: `onecore\base\gendrv\silos\clem\client\dll\CmClientHandles.h`

## pseudocode

```c
__int64 __fastcall Container::Manager::Client::ConvertToContainerStorageInfo(__int64 a1, __int64 a2, unsigned int *a3)
{
  int v3; // r14d
  __int64 v5; // rdx
  __int64 v7; // rcx
  __int64 v8; // rax
  unsigned int v9; // r12d
  unsigned __int64 v10; // r15
  unsigned int v11; // r13d
  __int64 v12; // rcx
  _WORD *v13; // r10
  unsigned int v14; // edx
  unsigned int v15; // r11d
  unsigned int v16; // eax
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // r8
  void *v20; // rbx
  int v21; // r14d
  __int128 v22; // xmm1
  int v23; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int Size; // [rsp+70h] [rbp+8h]

  v3 = *(_DWORD *)(a1 + 4);
  v5 = -1;
  if ( v3 == 1 )
  {
    v7 = *(_QWORD *)(a1 + 40);
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v9 = v8 + 1;
    v10 = 36;
    v11 = 2 * (v8 + 1);
    v12 = v11 + 72;
  }
  else
  {
    v12 = 72;
    v9 = 0;
    v11 = 0;
    v10 = 0;
  }
  v13 = *(_WORD **)(a1 + 32);
  if ( v13 )
  {
    do
      ++v5;
    while ( v13[v5] );
    v14 = v5 + 1;
    if ( !(_DWORD)v12 )
      LODWORD(v12) = 2;
    v15 = v12;
    v12 = 2 * v14 + (unsigned int)v12;
    Size = 2 * v14;
  }
  else
  {
    Size = 0;
    v15 = 0;
    v14 = 0;
  }
  v16 = *a3;
  *a3 = v12;
  if ( v16 < (unsigned int)v12 )
    return 2147942522LL;
  if ( a2 )
  {
    v18 = (unsigned __int64)(unsigned int)v12 >> 1;
  }
  else
  {
    if ( (_DWORD)v12 )
      goto LABEL_31;
    v18 = (unsigned __int64)(unsigned int)v12 >> 1;
    if ( v18 )
      goto LABEL_31;
  }
  *(_DWORD *)a2 = v3;
  *(_OWORD *)(a2 + 16) = *(_OWORD *)(a1 + 16);
  if ( v13 )
  {
    v19 = (unsigned __int64)v15 >> 1;
    if ( v18 < v19 )
      goto LABEL_31;
    v12 = v18 - v19;
    if ( v18 - v19 < v14 )
      goto LABEL_31;
    v20 = (void *)(a2 + 2 * v19);
    memcpy_0(v20, v13, Size);
    *(_QWORD *)(a2 + 32) = v20;
  }
  v21 = v3 - 1;
  if ( !v21 )
  {
    if ( v18 >= v10 && v18 - v10 >= v9 )
    {
      memcpy_0((void *)(a2 + 2 * v10), *(const void **)(a1 + 40), v11);
      *(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(a2 + 40) = a2 + 2 * v10;
      return 0;
    }
LABEL_31:
    gsl::details::terminate((gsl::details *)v12);
  }
  if ( v21 != 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\CmClientHandles.h",
      (const char *)0x8000FFFFLL,
      v23);
    return 2147549183LL;
  }
  v22 = *(_OWORD *)(a1 + 56);
  *(_OWORD *)(a2 + 40) = *(_OWORD *)(a1 + 40);
  *(_OWORD *)(a2 + 56) = v22;
  return 0;
}

```

## disassembly

```asm
0x1800044b0  push    rbx
0x1800044b2  push    rbp
0x1800044b3  push    rsi
0x1800044b4  push    rdi
0x1800044b5  push    r12
0x1800044b7  push    r13
0x1800044b9  push    r14
0x1800044bb  push    r15
0x1800044bd  sub     rsp, 28h
0x1800044c1  mov     r14d, [rcx+4]
0x1800044c5  mov     rsi, rdx
0x1800044c8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800044cc  xor     r9d, r9d
0x1800044cf  mov     rbp, rcx
0x1800044d2  cmp     r14d, 1
0x1800044d6  jnz     short loc_1800044FD
0x1800044d8  mov     rcx, [rcx+28h]
0x1800044dc  mov     rax, rdx
0x1800044df  inc     rax
0x1800044e2  cmp     [rcx+rax*2], r9w
0x1800044e7  jnz     short loc_1800044DF
0x1800044e9  lea     r12d, [rax+1]
0x1800044ed  mov     r15d, 24h ; '$'
0x1800044f3  lea     r13d, [r12+r12]
0x1800044f7  lea     ecx, [r13+48h]
0x1800044fb  jmp     short loc_18000450B
0x1800044fd  mov     ecx, 48h ; 'H'; this
0x180004502  mov     r12d, r9d
0x180004505  mov     r13d, r9d
0x180004508  mov     r15, r9
0x18000450b  mov     r10, [rbp+20h]
0x18000450f  test    r10, r10
0x180004512  jz      short loc_180004538
0x180004514  inc     rdx
0x180004517  cmp     [r10+rdx*2], r9w
0x18000451c  jnz     short loc_180004514
0x18000451e  inc     edx
0x180004520  mov     eax, 2
0x180004525  test    ecx, ecx
0x180004527  cmovz   ecx, eax
0x18000452a  lea     ebx, [rdx+rdx]
0x18000452d  mov     r11d, ecx
0x180004530  add     ecx, ebx
0x180004532  mov     dword ptr [rsp+68h+Size], ebx
0x180004536  jmp     short loc_180004543
0x180004538  mov     dword ptr [rsp+68h+Size], r9d
0x18000453d  mov     r11d, r9d
0x180004540  mov     edx, r9d
0x180004543  mov     eax, [r8]
0x180004546  mov     [r8], ecx
0x180004549  cmp     eax, ecx
0x18000454b  jnb     short loc_180004563
0x18000454d  mov     eax, 8007007Ah
0x180004552  add     rsp, 28h
0x180004556  pop     r15
0x180004558  pop     r14
0x18000455a  pop     r13
0x18000455c  pop     r12
0x18000455e  pop     rdi
0x18000455f  pop     rsi
0x180004560  pop     rbp
0x180004561  pop     rbx
0x180004562  retn
0x180004563  mov     edi, ecx
0x180004565  test    rsi, rsi
0x180004568  jnz     short loc_18000457D
0x18000456a  test    ecx, ecx
0x18000456c  jnz     loc_180004642
0x180004572  shr     rdi, 1
0x180004575  jnz     loc_180004642
0x18000457b  jmp     short loc_180004580
0x18000457d  shr     rdi, 1
0x180004580  mov     [rsi], r14d
0x180004583  movups  xmm0, xmmword ptr [rbp+10h]
0x180004587  movdqu  xmmword ptr [rsi+10h], xmm0
0x18000458c  test    r10, r10
0x18000458f  jz      short loc_1800045C9
0x180004591  mov     r8d, r11d
0x180004594  shr     r8, 1
0x180004597  cmp     rdi, r8
0x18000459a  jb      loc_180004642
0x1800045a0  mov     rcx, rdi
0x1800045a3  mov     eax, edx
0x1800045a5  sub     rcx, r8
0x1800045a8  cmp     rcx, rax
0x1800045ab  jb      loc_180004642
0x1800045b1  lea     rbx, [rsi+r8*2]
0x1800045b5  mov     rdx, r10; Src
0x1800045b8  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x1800045bd  mov     rcx, rbx; void *
0x1800045c0  call    memcpy_0
0x1800045c5  mov     [rsi+20h], rbx
0x1800045c9  sub     r14d, 1
0x1800045cd  jz      short loc_18000460C
0x1800045cf  cmp     r14d, 1
0x1800045d3  jz      short loc_1800045FA
0x1800045d5  mov     rcx, [rsp+68h]; this
0x1800045da  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x1800045e1  mov     ebx, 8000FFFFh
0x1800045e6  mov     edx, 0F6h; void *
0x1800045eb  mov     r9d, ebx; char *
0x1800045ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800045f3  mov     eax, ebx
0x1800045f5  jmp     loc_180004552
0x1800045fa  movups  xmm0, xmmword ptr [rbp+28h]
0x1800045fe  movups  xmm1, xmmword ptr [rbp+38h]
0x180004602  movups  xmmword ptr [rsi+28h], xmm0
0x180004606  movups  xmmword ptr [rsi+38h], xmm1
0x18000460a  jmp     short loc_18000463B
0x18000460c  cmp     rdi, r15
0x18000460f  jb      short loc_180004642
0x180004611  sub     rdi, r15
0x180004614  mov     eax, r12d
0x180004617  cmp     rdi, rax
0x18000461a  jb      short loc_180004642
0x18000461c  mov     rdx, [rbp+28h]; Src
0x180004620  lea     rbx, [rsi+r15*2]
0x180004624  mov     rcx, rbx; void *
0x180004627  mov     r8d, r13d; Size
0x18000462a  call    memcpy_0
0x18000462f  mov     rax, [rbp+8]
0x180004633  mov     [rsi+8], rax
0x180004637  mov     [rsi+28h], rbx
0x18000463b  xor     eax, eax
0x18000463d  jmp     loc_180004552
0x180004642  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
