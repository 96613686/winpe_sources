# GetBaseHypothesisData(tagHypothesisResult * *,ulong *,ProblemNode const *)

- ea: `0x18000bfcc`
- end: `0x18000c15c`
- name: `?GetBaseHypothesisData@@YAJPEAPEAUtagHypothesisResult@@PEAKPEBVProblemNode@@@Z`
- size: `400`
- prototype: `__int64 __fastcall(struct tagHypothesisResult **, unsigned int *, const struct ProblemNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ede4`

## callees

- `0x1800056bc`
- `0x180008cf0`
- `0x18000a124`
- `0x18000bfcc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c052`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetBaseHypothesisData(
        struct tagHypothesisResult **a1,
        unsigned int *a2,
        const struct ProblemNode *a3)
{
  __int64 v4; // r9
  int v5; // r15d
  unsigned __int64 v6; // rsi
  __int64 i; // rdx
  int v8; // r14d
  __int64 v9; // rbx
  struct tagHypothesisResult *v10; // rax
  struct tagHypothesisResult *v11; // r12
  unsigned __int64 v13; // r13
  __int64 ***v14; // r15
  __int64 **v15; // rbx
  struct tagHypothesisResult *v16; // [rsp+20h] [rbp-30h] BYREF
  __int64 v17; // [rsp+28h] [rbp-28h]
  _QWORD v18[4]; // [rsp+30h] [rbp-20h]
  int v21; // [rsp+A0h] [rbp+50h]

  v4 = *(_QWORD *)a3;
  v18[0] = *(_QWORD *)a3 + 120LL;
  v18[1] = v4 + 136;
  v18[2] = v4 + 152;
  v18[3] = v4 + 168;
  LOWORD(v5) = 0;
  v6 = 0;
  for ( i = 0; i != 4; ++i )
    v6 += *(_QWORD *)(v18[i] + 8LL);
  v8 = 0;
  if ( v6 )
  {
    v9 = 40 * v6;
    v10 = (struct tagHypothesisResult *)CoTaskMemAlloc(40 * v6);
    v11 = v10;
    if ( !v10 )
      return 2147942414LL;
    for ( ; v9; --v9 )
    {
      LOBYTE(v10->hypothesis.pwszClassName) = 0;
      v10 = (struct tagHypothesisResult *)((char *)v10 + 1);
    }
    v16 = v11;
    LODWORD(v17) = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v6);
    HIDWORD(v17) = 1;
    v13 = 0;
    v21 = 0;
    do
    {
      if ( v13 >= v6 )
        break;
      if ( v8 < 0 )
        goto LABEL_18;
      v14 = (__int64 ***)v18[(unsigned __int16)v5];
      v15 = (__int64 **)**v14;
      do
      {
        if ( v15 == *v14 )
          break;
        if ( v8 < 0 )
          break;
        v8 = CopyHypothesisWithAlloc(&v11[v13].hypothesis, (const struct tagHYPOTHESIS *)v15[2]);
        v11[v13++].pathStatus = DS_REJECTED;
        v15 = (__int64 **)*v15;
      }
      while ( v13 < v6 );
      HIWORD(v5) = HIWORD(v21);
      LOWORD(v5) = v21 + 1;
      v21 = v5;
    }
    while ( (unsigned __int16)v5 < 4u );
    if ( v8 >= 0 )
    {
      v16 = 0;
      v17 = 0;
      *a1 = v11;
      *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v6);
    }
LABEL_18:
    TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>::~TNDFDeallocator<tagHypothesisResult *,&void FreeHypothesisResults(tagHypothesisResult *,unsigned long,int)>(&v16);
  }
  else
  {
    *a1 = 0;
    *a2 = 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bfcc  mov     [rsp-38h+arg_18], rbx
0x18000bfd1  mov     [rsp-38h+arg_8], rdx
0x18000bfd6  mov     [rsp-38h+arg_0], rcx
0x18000bfdb  push    rbp
0x18000bfdc  push    rsi
0x18000bfdd  push    rdi
0x18000bfde  push    r12
0x18000bfe0  push    r13
0x18000bfe2  push    r14
0x18000bfe4  push    r15
0x18000bfe6  mov     rbp, rsp
0x18000bfe9  sub     rsp, 50h
0x18000bfed  mov     rdi, rdx
0x18000bff0  mov     r9, [r8]
0x18000bff3  lea     rax, [r9+78h]
0x18000bff7  mov     [rbp+var_20], rax
0x18000bffb  lea     rax, [r9+88h]
0x18000c002  mov     [rbp+var_18], rax
0x18000c006  lea     rax, [r9+98h]
0x18000c00d  mov     [rbp+var_10], rax
0x18000c011  lea     rax, [r9+0A8h]
0x18000c018  mov     [rbp+var_8], rax
0x18000c01c  xor     r15d, r15d
0x18000c01f  mov     esi, r15d
0x18000c022  mov     edx, r15d
0x18000c025  lea     r13d, [r15+1]
0x18000c029  mov     rax, [rbp+rdx*8+var_20]
0x18000c02e  add     rsi, [rax+8]
0x18000c032  add     rdx, r13
0x18000c035  cmp     rdx, 4
0x18000c039  jnz     short loc_18000C029
0x18000c03b  mov     r14d, r15d
0x18000c03e  test    rsi, rsi
0x18000c041  jz      loc_18000C13B
0x18000c047  lea     rbx, [rsi+rsi*4]
0x18000c04b  shl     rbx, 3
0x18000c04f  mov     rcx, rbx; cb
0x18000c052  call    cs:__imp_CoTaskMemAlloc
0x18000c058  mov     r12, rax
0x18000c05b  test    rax, rax
0x18000c05e  jnz     short loc_18000C06A
0x18000c060  mov     eax, 8007000Eh
0x18000c065  jmp     loc_18000C144
0x18000c06a  test    rbx, rbx
0x18000c06d  jz      short loc_18000C07A
0x18000c06f  mov     [rax], r15b
0x18000c072  add     rax, r13
0x18000c075  sub     rbx, r13
0x18000c078  jnz     short loc_18000C06F
0x18000c07a  mov     rcx, rsi
0x18000c07d  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000c082  mov     [rbp+var_30], r12
0x18000c086  mov     dword ptr [rbp+var_28], eax
0x18000c089  mov     dword ptr [rbp+var_28+4], r13d
0x18000c08d  mov     r13, r15
0x18000c090  mov     [rbp+arg_10], r15d
0x18000c094  cmp     r13, rsi
0x18000c097  jnb     short loc_18000C10C
0x18000c099  test    r14d, r14d
0x18000c09c  js      loc_18000C130
0x18000c0a2  movzx   eax, r15w
0x18000c0a6  mov     r15, [rbp+rax*8+var_20]
0x18000c0ab  mov     rbx, [r15]
0x18000c0ae  mov     rbx, [rbx]
0x18000c0b1  mov     eax, 1
0x18000c0b6  cmp     rbx, [r15]
0x18000c0b9  jz      short loc_18000C0F5
0x18000c0bb  test    r14d, r14d
0x18000c0be  js      short loc_18000C0F5
0x18000c0c0  lea     rax, ds:0[r13*4]
0x18000c0c8  add     rax, r13
0x18000c0cb  lea     rdi, [r12+rax*8]
0x18000c0cf  mov     rdx, [rbx+10h]; struct tagHYPOTHESIS *
0x18000c0d3  mov     rcx, rdi; struct tagHYPOTHESIS *
0x18000c0d6  call    ?CopyHypothesisWithAlloc@@YAJPEAUtagHYPOTHESIS@@PEBU1@@Z; CopyHypothesisWithAlloc(tagHYPOTHESIS *,tagHYPOTHESIS const *)
0x18000c0db  mov     r14d, eax
0x18000c0de  mov     dword ptr [rdi+20h], 2
0x18000c0e5  mov     eax, 1
0x18000c0ea  add     r13, rax
0x18000c0ed  mov     rbx, [rbx]
0x18000c0f0  cmp     r13, rsi
0x18000c0f3  jb      short loc_18000C0B6
0x18000c0f5  mov     r15d, [rbp+arg_10]
0x18000c0f9  add     r15w, ax
0x18000c0fd  mov     [rbp+arg_10], r15d
0x18000c101  mov     eax, 4
0x18000c106  cmp     r15w, ax
0x18000c10a  jb      short loc_18000C094
0x18000c10c  xor     eax, eax
0x18000c10e  test    r14d, r14d
0x18000c111  js      short loc_18000C130
0x18000c113  mov     [rbp+var_30], rax
0x18000c117  mov     [rbp+var_28], rax
0x18000c11b  mov     rax, [rbp+arg_0]
0x18000c11f  mov     [rax], r12
0x18000c122  mov     rcx, rsi
0x18000c125  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000c12a  mov     rcx, [rbp+arg_8]
0x18000c12e  mov     [rcx], eax
0x18000c130  lea     rcx, [rbp+var_30]
0x18000c134  call    ??1?$TNDFDeallocator@PEAUtagHypothesisResult@@$1?FreeHypothesisResults@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>::~TNDFDeallocator<tagHypothesisResult *,&FreeHypothesisResults(tagHypothesisResult *,ulong,int)>(void)
0x18000c139  jmp     short loc_18000C141
0x18000c13b  mov     [rcx], r15
0x18000c13e  mov     [rdi], r15d
0x18000c141  mov     eax, r14d
0x18000c144  mov     rbx, [rsp+50h+arg_18]
0x18000c14c  add     rsp, 50h
0x18000c150  pop     r15
0x18000c152  pop     r14
0x18000c154  pop     r13
0x18000c156  pop     r12
0x18000c158  pop     rdi
0x18000c159  pop     rsi
0x18000c15a  pop     rbp
0x18000c15b  retn
```
