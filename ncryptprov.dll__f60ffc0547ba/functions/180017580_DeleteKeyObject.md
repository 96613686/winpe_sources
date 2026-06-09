# DeleteKeyObject

- ea: `0x180017580`
- end: `0x180017a3f`
- name: `DeleteKeyObject`
- size: `1215`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `16`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180009b60`
- `0x180009f60`
- `0x180017440`
- `0x180022e14`
- `0x180027778`
- `0x18002b460`
- `0x18002c7b0`
- `0x1800489c8`
- `0x1800491d4`
- `0x180049dec`
- `0x18004acf8`
- `0x18004ae24`
- `0x18004b728`
- `0x18005b338`
- `0x18005bbcc`
- `0x18005e958`

## callees

- `0x180009440`
- `0x18000d3d0`
- `0x180017580`
- `0x180038970`
- `0x18004689c`
- `0x180062310`
- `0x1800623d0`
- `0x180063010`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x180017814`
- `ntdll!RtlDeleteResource` at `0x180017814`
- `ntdll!RtlFreeHeap` at `0x1800175f4`
- `ntdll!RtlFreeHeap` at `0x18001761c`
- `ntdll!RtlFreeHeap` at `0x180017644`
- `ntdll!RtlFreeHeap` at `0x1800176c6`
- `ntdll!RtlFreeHeap` at `0x1800176f4`
- `ntdll!RtlFreeHeap` at `0x180017762`
- `ntdll!RtlFreeHeap` at `0x180017790`
- `ntdll!RtlFreeHeap` at `0x1800177fc`
- `ntdll!RtlFreeHeap` at `0x180017842`
- `ntdll!RtlFreeHeap` at `0x18001786e`
- `ntdll!RtlFreeHeap` at `0x1800178b8`
- `ntdll!RtlFreeHeap` at `0x1800175f4`
- `ntdll!RtlFreeHeap` at `0x18001761c`
- `ntdll!RtlFreeHeap` at `0x180017644`
- `ntdll!RtlFreeHeap` at `0x1800176c6`
- `ntdll!RtlFreeHeap` at `0x1800176f4`
- `ntdll!RtlFreeHeap` at `0x180017762`
- `ntdll!RtlFreeHeap` at `0x180017790`
- `ntdll!RtlFreeHeap` at `0x1800177fc`
- `ntdll!RtlFreeHeap` at `0x180017842`
- `ntdll!RtlFreeHeap` at `0x18001786e`
- `ntdll!RtlFreeHeap` at `0x1800178b8`
- `bcrypt!BCryptDestroyKey` at `0x1800178d0`
- `bcrypt!BCryptDestroyKey` at `0x18001795a`
- `bcrypt!BCryptDestroyKey` at `0x1800178d0`
- `bcrypt!BCryptDestroyKey` at `0x18001795a`

## pseudocode

```c
__int64 __fastcall DeleteKeyObject(unsigned int *a1)
{
  __int64 v1; // rax
  NTSTATUS v3; // r14d
  void *v4; // rbp
  int v5; // r15d
  unsigned int v6; // r12d
  void *v7; // r8
  void *v8; // r8
  void *v9; // r8
  __int64 v10; // rcx
  void *v11; // rcx
  void *v12; // rcx
  _BYTE *v13; // rax
  void *v14; // r8
  void *v15; // r8
  void *v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  void *v20; // r8
  void *v21; // r8
  unsigned int *v22; // rdi
  unsigned int *v23; // rax
  unsigned int **v24; // rcx
  unsigned int *v25; // r8
  NTSTATUS v27; // eax
  __int64 v28; // rcx
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  int v31; // edx
  char v32[8]; // [rsp+30h] [rbp-2F8h] BYREF
  void *v33; // [rsp+38h] [rbp-2F0h]
  _BYTE *v34; // [rsp+70h] [rbp-2B8h]
  _BYTE v35[32]; // [rsp+280h] [rbp-A8h] BYREF
  int v36; // [rsp+2A0h] [rbp-88h]

  v1 = *((_QWORD *)a1 + 8);
  v3 = 0;
  v4 = 0;
  v5 = 0;
  if ( v1 )
    v5 = *(_DWORD *)(v1 + 32);
  v6 = a1[142];
  if ( *((_QWORD *)a1 + 1) )
  {
    v4 = (void *)*((_QWORD *)a1 + 1);
    *((_QWORD *)a1 + 1) = 0;
  }
  v7 = (void *)*((_QWORD *)a1 + 7);
  if ( v7 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    *((_QWORD *)a1 + 7) = 0;
  }
  v8 = (void *)*((_QWORD *)a1 + 2);
  if ( v8 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    *((_QWORD *)a1 + 2) = 0;
  }
  v9 = (void *)*((_QWORD *)a1 + 9);
  if ( v9 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
    *((_QWORD *)a1 + 9) = 0;
  }
  v10 = *((_QWORD *)a1 + 10);
  if ( v10 )
  {
    MSCryptFree(v10);
    *((_QWORD *)a1 + 10) = 0;
  }
  v11 = (void *)*((_QWORD *)a1 + 13);
  if ( v11 )
  {
    v3 = BCryptDestroyKey(v11);
    *((_QWORD *)a1 + 13) = 0;
  }
  if ( *((_QWORD *)a1 + 14) )
  {
    v27 = (*(__int64 (**)(void))(*((_QWORD *)a1 + 21) + 136LL))();
    *((_QWORD *)a1 + 14) = 0;
    if ( !v3 )
      v3 = v27;
  }
  v12 = (void *)*((_QWORD *)a1 + 16);
  if ( v12 )
  {
    v29 = BCryptDestroyKey(v12);
    *((_QWORD *)a1 + 16) = 0;
    if ( !v3 )
      v3 = v29;
  }
  if ( *((_QWORD *)a1 + 17) )
  {
    v30 = (*(__int64 (**)(void))(*((_QWORD *)a1 + 21) + 136LL))();
    *((_QWORD *)a1 + 17) = 0;
    if ( !v3 )
      v3 = v30;
  }
  v13 = (_BYTE *)*((_QWORD *)a1 + 26);
  if ( v13 )
  {
    v28 = a1[54];
    if ( a1[54] )
    {
      do
      {
        *v13++ = 0;
        --v28;
      }
      while ( v28 );
    }
    MSCryptFree(*((_QWORD *)a1 + 26));
    *((_QWORD *)a1 + 26) = 0;
  }
  v14 = (void *)*((_QWORD *)a1 + 28);
  if ( v14 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
    *((_QWORD *)a1 + 28) = 0;
  }
  v15 = (void *)*((_QWORD *)a1 + 30);
  if ( v15 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
    *((_QWORD *)a1 + 30) = 0;
  }
  v16 = (void *)*((_QWORD *)a1 + 32);
  if ( v16 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
    *((_QWORD *)a1 + 32) = 0;
  }
  v17 = *((_QWORD *)a1 + 52);
  if ( v17 )
  {
    MSCryptFree(v17);
    *((_QWORD *)a1 + 52) = 0;
  }
  v18 = *((_QWORD *)a1 + 63);
  if ( v18 )
  {
    MSCryptFree(v18);
    *((_QWORD *)a1 + 63) = 0;
  }
  v19 = *((_QWORD *)a1 + 64);
  if ( v19 )
  {
    MSCryptFree(v19);
    *((_QWORD *)a1 + 64) = 0;
  }
  v20 = (void *)*((_QWORD *)a1 + 68);
  if ( v20 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    *((_QWORD *)a1 + 68) = 0;
  }
  v21 = (void *)*((_QWORD *)a1 + 69);
  if ( v21 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
    *((_QWORD *)a1 + 69) = 0;
  }
  if ( *((_QWORD *)a1 + 72) )
  {
    EphemeralKeyTableEntryRelease();
    *((_QWORD *)a1 + 72) = 0;
  }
  v22 = (unsigned int *)*((_QWORD *)a1 + 36);
  while ( v22 != a1 + 72 )
  {
    v23 = *(unsigned int **)v22;
    if ( *(unsigned int **)(*(_QWORD *)v22 + 8LL) != v22 || (v24 = (unsigned int **)*((_QWORD *)v22 + 1), *v24 != v22) )
      __fastfail(3u);
    *v24 = v23;
    v25 = v22 - 38;
    *((_QWORD *)v23 + 1) = v24;
    v22 = v23;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
  }
  RtlDeleteResource((PRTL_RESOURCE)(a1 + 76));
  RtlSetVolatileMemory(a1, 0, 0x248u);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
  if ( v3 && !v6 )
  {
    memset_0(v35, 0, 0x68u);
    memset_0(v32, 0, 0x248u);
    v36 = v5;
    v34 = v35;
    v33 = v4;
    KspCryptAuditCryptOperation(0, v31, (unsigned int)v32, 2482, v3);
  }
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return 0;
}

```

## disassembly

```asm
0x180017580  mov     [rsp+arg_8], rbx
0x180017585  mov     [rsp+arg_10], rbp
0x18001758a  push    rsi
0x18001758b  push    rdi
0x18001758c  push    r12
0x18001758e  push    r14
0x180017590  push    r15
0x180017592  sub     rsp, 300h
0x180017599  mov     rax, cs:__security_cookie
0x1800175a0  xor     rax, rsp
0x1800175a3  mov     [rsp+328h+var_38], rax
0x1800175ab  mov     rax, [rcx+40h]
0x1800175af  xor     edi, edi
0x1800175b1  mov     rbx, rcx
0x1800175b4  mov     r14d, edi
0x1800175b7  mov     ebp, edi
0x1800175b9  mov     r15d, edi
0x1800175bc  test    rax, rax
0x1800175bf  jz      short loc_1800175C5
0x1800175c1  mov     r15d, [rax+20h]
0x1800175c5  mov     rax, [rcx+8]
0x1800175c9  mov     r12d, [rcx+238h]
0x1800175d0  test    rax, rax
0x1800175d3  jz      short loc_1800175DC
0x1800175d5  mov     rbp, rax
0x1800175d8  mov     [rcx+8], rdi
0x1800175dc  mov     r8, [rcx+38h]; P
0x1800175e0  test    r8, r8
0x1800175e3  jz      short loc_180017604
0x1800175e5  mov     rcx, gs:60h
0x1800175ee  xor     edx, edx; Flags
0x1800175f0  mov     rcx, [rcx+30h]; HeapHandle
0x1800175f4  call    cs:__imp_RtlFreeHeap
0x1800175fb  nop     dword ptr [rax+rax+00h]
0x180017600  mov     [rbx+38h], rdi
0x180017604  mov     r8, [rbx+10h]; P
0x180017608  test    r8, r8
0x18001760b  jz      short loc_18001762C
0x18001760d  mov     rcx, gs:60h
0x180017616  xor     edx, edx; Flags
0x180017618  mov     rcx, [rcx+30h]; HeapHandle
0x18001761c  call    cs:__imp_RtlFreeHeap
0x180017623  nop     dword ptr [rax+rax+00h]
0x180017628  mov     [rbx+10h], rdi
0x18001762c  mov     r8, [rbx+48h]; P
0x180017630  test    r8, r8
0x180017633  jz      short loc_180017654
0x180017635  mov     rcx, gs:60h
0x18001763e  xor     edx, edx; Flags
0x180017640  mov     rcx, [rcx+30h]; HeapHandle
0x180017644  call    cs:__imp_RtlFreeHeap
0x18001764b  nop     dword ptr [rax+rax+00h]
0x180017650  mov     [rbx+48h], rdi
0x180017654  mov     rcx, [rbx+50h]
0x180017658  test    rcx, rcx
0x18001765b  jnz     loc_18001791C
0x180017661  mov     rcx, [rbx+68h]; hKey
0x180017665  test    rcx, rcx
0x180017668  jnz     loc_1800178D0
0x18001766e  mov     rcx, [rbx+70h]
0x180017672  test    rcx, rcx
0x180017675  jnz     loc_1800178E8
0x18001767b  mov     rcx, [rbx+80h]; hKey
0x180017682  test    rcx, rcx
0x180017685  jnz     loc_18001795A
0x18001768b  mov     rcx, [rbx+88h]
0x180017692  test    rcx, rcx
0x180017695  jnz     loc_180017979
0x18001769b  mov     rax, [rbx+0D0h]
0x1800176a2  test    rax, rax
0x1800176a5  jnz     loc_18001792A
0x1800176ab  mov     r8, [rbx+0E0h]; P
0x1800176b2  test    r8, r8
0x1800176b5  jz      short loc_1800176D9
0x1800176b7  mov     rcx, gs:60h
0x1800176c0  xor     edx, edx; Flags
0x1800176c2  mov     rcx, [rcx+30h]; HeapHandle
0x1800176c6  call    cs:__imp_RtlFreeHeap
0x1800176cd  nop     dword ptr [rax+rax+00h]
0x1800176d2  mov     [rbx+0E0h], rdi
0x1800176d9  mov     r8, [rbx+0F0h]; P
0x1800176e0  test    r8, r8
0x1800176e3  jz      short loc_180017707
0x1800176e5  mov     rcx, gs:60h
0x1800176ee  xor     edx, edx; Flags
0x1800176f0  mov     rcx, [rcx+30h]; HeapHandle
0x1800176f4  call    cs:__imp_RtlFreeHeap
0x1800176fb  nop     dword ptr [rax+rax+00h]
0x180017700  mov     [rbx+0F0h], rdi
0x180017707  mov     r8, [rbx+100h]; P
0x18001770e  test    r8, r8
0x180017711  jnz     loc_1800178A9
0x180017717  mov     rcx, [rbx+1A0h]
0x18001771e  test    rcx, rcx
0x180017721  jnz     loc_18001790B
0x180017727  mov     rcx, [rbx+1F8h]
0x18001772e  test    rcx, rcx
0x180017731  jnz     loc_18001799F
0x180017737  mov     rcx, [rbx+200h]
0x18001773e  test    rcx, rcx
0x180017741  jnz     loc_1800179B0
0x180017747  mov     r8, [rbx+220h]; P
0x18001774e  test    r8, r8
0x180017751  jz      short loc_180017775
0x180017753  mov     rcx, gs:60h
0x18001775c  xor     edx, edx; Flags
0x18001775e  mov     rcx, [rcx+30h]; HeapHandle
0x180017762  call    cs:__imp_RtlFreeHeap
0x180017769  nop     dword ptr [rax+rax+00h]
0x18001776e  mov     [rbx+220h], rdi
0x180017775  mov     r8, [rbx+228h]; P
0x18001777c  test    r8, r8
0x18001777f  jz      short loc_1800177A3
0x180017781  mov     rcx, gs:60h
0x18001778a  xor     edx, edx; Flags
0x18001778c  mov     rcx, [rcx+30h]; HeapHandle
0x180017790  call    cs:__imp_RtlFreeHeap
0x180017797  nop     dword ptr [rax+rax+00h]
0x18001779c  mov     [rbx+228h], rdi
0x1800177a3  mov     rcx, [rbx+240h]
0x1800177aa  test    rcx, rcx
0x1800177ad  jnz     loc_1800179C1
0x1800177b3  lea     rsi, [rbx+120h]
0x1800177ba  mov     rdi, [rsi]
0x1800177bd  cmp     rdi, rsi
0x1800177c0  jz      short loc_18001780D
0x1800177c2  mov     rax, [rdi]
0x1800177c5  cmp     [rax+8], rdi
0x1800177c9  jnz     loc_1800179D2
0x1800177cf  mov     rcx, [rdi+8]
0x1800177d3  cmp     [rcx], rdi
0x1800177d6  jnz     loc_1800179D2
0x1800177dc  mov     [rcx], rax
0x1800177df  lea     r8, [rdi-98h]; P
0x1800177e6  mov     [rax+8], rcx
0x1800177ea  xor     edx, edx; Flags
0x1800177ec  mov     rcx, gs:60h
0x1800177f5  mov     rdi, rax
0x1800177f8  mov     rcx, [rcx+30h]; HeapHandle
0x1800177fc  call    cs:__imp_RtlFreeHeap
0x180017803  nop     dword ptr [rax+rax+00h]
0x180017808  cmp     rdi, rsi
0x18001780b  jnz     short loc_1800177C2
0x18001780d  lea     rcx, [rbx+130h]; Resource
0x180017814  call    cs:__imp_RtlDeleteResource
0x18001781b  nop     dword ptr [rax+rax+00h]
0x180017820  xor     edx, edx; Val
0x180017822  mov     r8d, 248h; Size
0x180017828  mov     rcx, rbx; void *
0x18001782b  call    RtlSetVolatileMemory
0x180017830  mov     rcx, gs:60h
0x180017839  mov     r8, rbx; P
0x18001783c  xor     edx, edx; Flags
0x18001783e  mov     rcx, [rcx+30h]; HeapHandle
0x180017842  call    cs:__imp_RtlFreeHeap
0x180017849  nop     dword ptr [rax+rax+00h]
0x18001784e  test    r14d, r14d
0x180017851  jnz     loc_1800179D9
0x180017857  test    rbp, rbp
0x18001785a  jz      short loc_18001787A
0x18001785c  mov     rcx, gs:60h
0x180017865  mov     r8, rbp; P
0x180017868  xor     edx, edx; Flags
0x18001786a  mov     rcx, [rcx+30h]; HeapHandle
0x18001786e  call    cs:__imp_RtlFreeHeap
0x180017875  nop     dword ptr [rax+rax+00h]
0x18001787a  xor     eax, eax
0x18001787c  mov     rcx, [rsp+328h+var_38]
0x180017884  xor     rcx, rsp; StackCookie
0x180017887  call    __security_check_cookie
0x18001788c  lea     r11, [rsp+328h+var_28]
0x180017894  mov     rbx, [r11+38h]
0x180017898  mov     rbp, [r11+40h]
0x18001789c  mov     rsp, r11
0x18001789f  pop     r15
0x1800178a1  pop     r14
0x1800178a3  pop     r12
0x1800178a5  pop     rdi
0x1800178a6  pop     rsi
0x1800178a7  retn
0x1800178a9  mov     rcx, gs:60h
0x1800178b2  xor     edx, edx; Flags
0x1800178b4  mov     rcx, [rcx+30h]; HeapHandle
0x1800178b8  call    cs:__imp_RtlFreeHeap
0x1800178bf  nop     dword ptr [rax+rax+00h]
0x1800178c4  mov     [rbx+100h], rdi
0x1800178cb  jmp     loc_180017717
0x1800178d0  call    cs:__imp_BCryptDestroyKey
0x1800178d7  nop     dword ptr [rax+rax+00h]
0x1800178dc  mov     r14d, eax
0x1800178df  mov     [rbx+68h], rdi
0x1800178e3  jmp     loc_18001766E
0x1800178e8  mov     rdx, [rbx+0A8h]
0x1800178ef  mov     rax, [rdx+88h]
0x1800178f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178fb  test    r14d, r14d
0x1800178fe  mov     [rbx+70h], rdi
0x180017902  cmovz   r14d, eax
0x180017906  jmp     loc_18001767B
0x18001790b  call    MSCryptFree
0x180017910  mov     [rbx+1A0h], rdi
0x180017917  jmp     loc_180017727
0x18001791c  call    MSCryptFree
0x180017921  mov     [rbx+50h], rdi
0x180017925  jmp     loc_180017661
0x18001792a  mov     ecx, [rbx+0D8h]
0x180017930  test    rcx, rcx
0x180017933  jz      short loc_180017942
0x180017935  mov     [rax], dil
0x180017938  lea     rax, [rax+1]
0x18001793c  sub     rcx, 1
0x180017940  jnz     short loc_180017935
0x180017942  mov     rcx, [rbx+0D0h]
0x180017949  call    MSCryptFree
0x18001794e  mov     [rbx+0D0h], rdi
0x180017955  jmp     loc_1800176AB
0x18001795a  call    cs:__imp_BCryptDestroyKey
0x180017961  nop     dword ptr [rax+rax+00h]
0x180017966  test    r14d, r14d
0x180017969  mov     [rbx+80h], rdi
0x180017970  cmovz   r14d, eax
0x180017974  jmp     loc_18001768B
0x180017979  mov     rax, [rbx+0A8h]
0x180017980  mov     rax, [rax+88h]
0x180017987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001798c  test    r14d, r14d
0x18001798f  mov     [rbx+88h], rdi
0x180017996  cmovz   r14d, eax
0x18001799a  jmp     loc_18001769B
0x18001799f  call    MSCryptFree
0x1800179a4  mov     [rbx+1F8h], rdi
0x1800179ab  jmp     loc_180017737
0x1800179b0  call    MSCryptFree
0x1800179b5  mov     [rbx+200h], rdi
0x1800179bc  jmp     loc_180017747
0x1800179c1  call    EphemeralKeyTableEntryRelease
0x1800179c6  mov     [rbx+240h], rdi
0x1800179cd  jmp     loc_1800177B3
0x1800179d2  mov     ecx, 3
0x1800179d7  int     29h; Win8: RtlFailFast(ecx)
0x1800179d9  test    r12d, r12d
0x1800179dc  jnz     loc_180017857
0x1800179e2  xor     edx, edx; Val
0x1800179e4  lea     rcx, [rsp+328h+var_A8]; void *
0x1800179ec  mov     r8d, 68h ; 'h'; Size
0x1800179f2  call    memset_0
0x1800179f7  xor     edx, edx; Val
0x1800179f9  lea     rcx, [rsp+328h+var_2F8]; void *
0x1800179fe  mov     r8d, 248h; Size
0x180017a04  call    memset_0
0x180017a09  lea     rax, [rsp+328h+var_A8]
0x180017a11  mov     [rsp+328h+var_88], r15d
0x180017a19  mov     r9d, 9B2h
0x180017a1f  mov     [rsp+328h+var_2B8], rax
0x180017a24  lea     r8, [rsp+328h+var_2F8]
0x180017a29  mov     [rsp+328h+var_2F0], rbp
0x180017a2e  xor     ecx, ecx
0x180017a30  mov     [rsp+328h+var_308], r14d
0x180017a35  call    KspCryptAuditCryptOperation
0x180017a3a  jmp     loc_180017857
```
