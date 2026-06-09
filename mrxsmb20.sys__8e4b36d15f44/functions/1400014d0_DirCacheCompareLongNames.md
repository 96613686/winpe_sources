# DirCacheCompareLongNames

- ea: `0x1400014d0`
- end: `0x140001733`
- name: `DirCacheCompareLongNames`
- size: `611`
- prototype: `int __cdecl(void *, const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400014d0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400016ab`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400016ab`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400014e7`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000155a`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x1400014e7`
- `ntoskrnl!RtlFindMostSignificantBit` at `0x14000155a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000162d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001650`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000166f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000168e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000162d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140001650`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000166f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000168e`

## pseudocode

```c
LONG __fastcall DirCacheCompareLongNames(_QWORD *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int v3; // ebp
  CCHAR MostSignificantBit; // al
  __int64 v7; // rbx
  unsigned int v8; // edx
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // r14
  unsigned int v12; // ebp
  CCHAR v13; // al
  unsigned int v14; // edx
  unsigned int v15; // eax
  __int64 v16; // rdx
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-48h] BYREF

  v3 = *a2;
  MostSignificantBit = RtlFindMostSignificantBit(*a2);
  v7 = 0;
  if ( MostSignificantBit <= 4 )
  {
    v8 = 0;
  }
  else
  {
    v8 = (unsigned int)(MostSignificantBit - 3) >> 1;
    if ( v8 >= 8 )
      goto LABEL_29;
  }
  _mm_lfence();
  if ( v8 )
    v9 = v3 - (32 << (2 * v8 - 2));
  else
    v9 = v3;
  v10 = a1[v8 + 19];
  if ( v10 && v3 < *((_DWORD *)a1 + 54) )
  {
    v11 = v10 + (v9 << 7);
    goto LABEL_8;
  }
LABEL_29:
  __int2c();
  v11 = 0;
LABEL_8:
  v12 = *a3;
  v13 = RtlFindMostSignificantBit(*a3);
  if ( v13 <= 4 )
  {
    v14 = 0;
  }
  else
  {
    v14 = (unsigned int)(v13 - 3) >> 1;
    if ( v14 >= 8 )
      goto LABEL_30;
  }
  _mm_lfence();
  v15 = v12;
  if ( v14 )
    v15 = v12 - (32 << (2 * v14 - 2));
  v16 = a1[v14 + 19];
  if ( v16 && v12 < *((_DWORD *)a1 + 54) )
  {
    v7 = v16 + (v15 << 7);
    goto LABEL_15;
  }
LABEL_30:
  __int2c();
LABEL_15:
  String1 = 0;
  String2 = 0;
  String1.MaximumLength = 2 * (*(_WORD *)(v11 + 86) >> 4);
  String1.Length = String1.MaximumLength;
  String1.Buffer = (PWSTR)(v11 + 2 * ((*(_WORD *)(v11 + 86) & 0xF) + 44LL));
  String2.MaximumLength = 2 * (*(_WORD *)(v7 + 86) >> 4);
  String2.Length = String2.MaximumLength;
  String2.Buffer = (PWSTR)(v7 + 2 * ((*(_WORD *)(v7 + 86) & 0xF) + 44LL));
  if ( !RtlEqualUnicodeString(&String1, &::String2, 0) )
  {
    if ( RtlEqualUnicodeString(&String2, &::String2, 0) )
      return 1;
    if ( !RtlEqualUnicodeString(&String1, &stru_14003E010, 0) )
    {
      if ( !RtlEqualUnicodeString(&String2, &stru_14003E010, 0) )
        return RtlCompareUnicodeString(&String1, &String2, 1u);
      return 1;
    }
  }
  return -1;
}

```

## disassembly

```asm
0x1400014d0  push    rbx
0x1400014d2  push    rbp
0x1400014d3  push    rsi
0x1400014d4  push    rdi
0x1400014d5  push    r14
0x1400014d7  push    r15
0x1400014d9  sub     rsp, 48h
0x1400014dd  mov     ebp, [rdx]
0x1400014df  mov     rdi, rcx
0x1400014e2  mov     ecx, ebp; Set
0x1400014e4  mov     r15, r8
0x1400014e7  call    cs:__imp_RtlFindMostSignificantBit
0x1400014ee  nop     dword ptr [rax+rax+00h]
0x1400014f3  xor     ebx, ebx
0x1400014f5  mov     esi, 20h ; ' '
0x1400014fa  cmp     al, 4
0x1400014fc  jle     loc_1400016C5
0x140001502  movsx   edx, al
0x140001505  sub     edx, 3
0x140001508  shr     edx, 1
0x14000150a  cmp     edx, 8
0x14000150d  jnb     loc_140001722
0x140001513  lfence
0x140001516  test    edx, edx
0x140001518  jz      loc_1400016E6
0x14000151e  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x140001525  mov     eax, esi
0x140001527  shl     eax, cl
0x140001529  mov     ecx, ebp
0x14000152b  sub     ecx, eax
0x14000152d  mov     eax, edx
0x14000152f  mov     rdx, [rdi+rax*8+98h]
0x140001537  test    rdx, rdx
0x14000153a  jz      loc_140001700
0x140001540  cmp     ebp, [rdi+0D8h]
0x140001546  jnb     loc_140001711
0x14000154c  shl     ecx, 7
0x14000154f  mov     r14d, ecx
0x140001552  add     r14, rdx
0x140001555  mov     ebp, [r15]
0x140001558  mov     ecx, ebp; Set
0x14000155a  call    cs:__imp_RtlFindMostSignificantBit
0x140001561  nop     dword ptr [rax+rax+00h]
0x140001566  cmp     al, 4
0x140001568  jle     loc_1400016CC
0x14000156e  movsx   edx, al
0x140001571  sub     edx, 3
0x140001574  shr     edx, 1
0x140001576  cmp     edx, 8
0x140001579  jnb     loc_14000172C
0x14000157f  lfence
0x140001582  mov     eax, ebp
0x140001584  test    edx, edx
0x140001586  jz      short loc_140001593
0x140001588  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]
0x14000158f  shl     esi, cl
0x140001591  sub     eax, esi
0x140001593  mov     ecx, edx
0x140001595  mov     rdx, [rdi+rcx*8+98h]
0x14000159d  test    rdx, rdx
0x1400015a0  jz      loc_14000170A
0x1400015a6  cmp     ebp, [rdi+0D8h]
0x1400015ac  jnb     loc_14000171B
0x1400015b2  shl     eax, 7
0x1400015b5  mov     ebx, eax
0x1400015b7  add     rbx, rdx
0x1400015ba  xorps   xmm0, xmm0
0x1400015bd  lea     rdx, String2; String2
0x1400015c4  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x1400015c9  lea     rcx, [rsp+78h+String1]; String1
0x1400015ce  xor     r8d, r8d; CaseInSensitive
0x1400015d1  xorps   xmm1, xmm1
0x1400015d4  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x1400015d9  movzx   eax, word ptr [r14+56h]
0x1400015de  shr     ax, 4
0x1400015e2  add     ax, ax
0x1400015e5  mov     [rsp+78h+String1.MaximumLength], ax
0x1400015ea  mov     [rsp+78h+String1.Length], ax
0x1400015ef  movzx   eax, word ptr [r14+56h]
0x1400015f4  and     eax, 0Fh
0x1400015f7  add     rax, 2Ch ; ','
0x1400015fb  lea     rax, [r14+rax*2]
0x1400015ff  mov     [rsp+78h+String1.Buffer], rax
0x140001604  movzx   eax, word ptr [rbx+56h]
0x140001608  shr     ax, 4
0x14000160c  add     ax, ax
0x14000160f  mov     [rsp+78h+String2.MaximumLength], ax
0x140001614  mov     [rsp+78h+String2.Length], ax
0x140001619  movzx   eax, word ptr [rbx+56h]
0x14000161d  and     eax, 0Fh
0x140001620  add     rax, 2Ch ; ','
0x140001624  lea     rax, [rbx+rax*2]
0x140001628  mov     [rsp+78h+String2.Buffer], rax
0x14000162d  call    cs:__imp_RtlEqualUnicodeString
0x140001634  nop     dword ptr [rax+rax+00h]
0x140001639  test    al, al
0x14000163b  jnz     loc_1400016ED
0x140001641  xor     r8d, r8d; CaseInSensitive
0x140001644  lea     rdx, String2; String2
0x14000164b  lea     rcx, [rsp+78h+String2]; String1
0x140001650  call    cs:__imp_RtlEqualUnicodeString
0x140001657  nop     dword ptr [rax+rax+00h]
0x14000165c  test    al, al
0x14000165e  jnz     short loc_1400016D3
0x140001660  xor     r8d, r8d; CaseInSensitive
0x140001663  lea     rdx, stru_14003E010; String2
0x14000166a  lea     rcx, [rsp+78h+String1]; String1
0x14000166f  call    cs:__imp_RtlEqualUnicodeString
0x140001676  nop     dword ptr [rax+rax+00h]
0x14000167b  test    al, al
0x14000167d  jnz     short loc_1400016ED
0x14000167f  xor     r8d, r8d; CaseInSensitive
0x140001682  lea     rdx, stru_14003E010; String2
0x140001689  lea     rcx, [rsp+78h+String2]; String1
0x14000168e  call    cs:__imp_RtlEqualUnicodeString
0x140001695  nop     dword ptr [rax+rax+00h]
0x14000169a  test    al, al
0x14000169c  jnz     short loc_1400016D3
0x14000169e  mov     r8b, 1; CaseInSensitive
0x1400016a1  lea     rdx, [rsp+78h+String2]; String2
0x1400016a6  lea     rcx, [rsp+78h+String1]; String1
0x1400016ab  call    cs:__imp_RtlCompareUnicodeString
0x1400016b2  nop     dword ptr [rax+rax+00h]
0x1400016b7  add     rsp, 48h
0x1400016bb  pop     r15
0x1400016bd  pop     r14
0x1400016bf  pop     rdi
0x1400016c0  pop     rsi
0x1400016c1  pop     rbp
0x1400016c2  pop     rbx
0x1400016c3  retn
0x1400016c5  mov     edx, ebx
0x1400016c7  jmp     loc_140001513
0x1400016cc  mov     edx, ebx
0x1400016ce  jmp     loc_14000157F
0x1400016d3  mov     eax, 1
0x1400016d8  add     rsp, 48h
0x1400016dc  pop     r15
0x1400016de  pop     r14
0x1400016e0  pop     rdi
0x1400016e1  pop     rsi
0x1400016e2  pop     rbp
0x1400016e3  pop     rbx
0x1400016e4  retn
0x1400016e6  mov     ecx, ebp
0x1400016e8  jmp     loc_14000152D
0x1400016ed  mov     eax, 0FFFFFFFFh
0x1400016f2  add     rsp, 48h
0x1400016f6  pop     r15
0x1400016f8  pop     r14
0x1400016fa  pop     rdi
0x1400016fb  pop     rsi
0x1400016fc  pop     rbp
0x1400016fd  pop     rbx
0x1400016fe  retn
0x140001700  int     2Ch; Windows NT - assertion failure
0x140001702  mov     r14, rbx
0x140001705  jmp     loc_140001555
0x14000170a  int     2Ch; Windows NT - assertion failure
0x14000170c  jmp     loc_1400015BA
0x140001711  int     2Ch; Windows NT - assertion failure
0x140001713  mov     r14, rbx
0x140001716  jmp     loc_140001555
0x14000171b  int     2Ch; Windows NT - assertion failure
0x14000171d  jmp     loc_1400015BA
0x140001722  int     2Ch; Windows NT - assertion failure
0x140001724  mov     r14, rbx
0x140001727  jmp     loc_140001555
0x14000172c  int     2Ch; Windows NT - assertion failure
0x14000172e  jmp     loc_1400015BA
```
