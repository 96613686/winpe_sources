# FveFrRangeListFree

- ea: `0x1400944cc`
- end: `0x140094608`
- name: `FveFrRangeListFree`
- size: `316`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `9`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14002e3d8`
- `0x14005822c`
- `0x1400701c4`
- `0x140077a10`
- `0x140093e10`
- `0x140094020`
- `0x14009422c`
- `0x1400be670`
- `0x1400c2498`

## callees

- `0x140018128`
- `0x1400218c0`
- `0x140021d00`
- `0x1400944cc`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009455f`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x14009455f`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14009452c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14009452c`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400945d6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400945d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094548`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094577`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400945fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094548`
- `ntoskrnl!ExFreePoolWithTag` at `0x140094577`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400945fa`

## pseudocode

```c
void *__fastcall FveFrRangeListFree(char *a1)
{
  char *v2; // rax
  __int64 v3; // rcx
  char **v4; // rdx
  _QWORD *v5; // rax
  struct _RTL_AVL_TABLE *v6; // rcx
  void *v7; // rcx
  __int128 Buffer; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h]

  v10 = 0;
  Buffer = 0;
  if ( *((_QWORD *)a1 + 2) )
  {
    v2 = a1 + 72;
    v3 = *((_QWORD *)a1 + 9);
    if ( (char *)v3 != v2 )
    {
      if ( *(char **)(v3 + 8) != v2 || (v4 = (char **)*((_QWORD *)v2 + 1), *v4 != v2) )
        __fastfail(3u);
      *v4 = (char *)v3;
      *(_QWORD *)(v3 + 8) = v4;
    }
    while ( 1 )
    {
      v5 = RtlEnumerateGenericTableAvl(*(PRTL_AVL_TABLE *)a1, 1u);
      v6 = *(struct _RTL_AVL_TABLE **)a1;
      if ( !v5 )
        break;
      Buffer = *(_OWORD *)v5;
      HIDWORD(v10) = HIDWORD(v5[2]);
      LODWORD(v10) = 3;
      RtlDeleteElementGenericTableAvl(v6, &Buffer);
    }
    if ( v6 )
    {
      ExFreePoolWithTag(v6, *((_DWORD *)a1 + 15));
      *(_QWORD *)a1 = 0;
    }
    ExDeleteLookasideListEx(*((PLOOKASIDE_LIST_EX *)a1 + 1));
    v7 = (void *)*((_QWORD *)a1 + 1);
    if ( v7 )
    {
      ExFreePoolWithTag(v7, *((_DWORD *)a1 + 15));
      *((_QWORD *)a1 + 1) = 0;
    }
    if ( *((_QWORD *)a1 + 8) )
    {
      FveRangeListFree();
      ExFreePoolWithTag(*((PVOID *)a1 + 8), *((_DWORD *)a1 + 14));
    }
  }
  return memset(a1, 0, 0x58u);
}

```

## disassembly

```asm
0x1400944cc  push    rbx
0x1400944ce  sub     rsp, 40h
0x1400944d2  mov     rax, cs:__security_cookie
0x1400944d9  xor     rax, rsp
0x1400944dc  mov     [rsp+48h+var_10], rax
0x1400944e1  xor     eax, eax
0x1400944e3  xorps   xmm0, xmm0
0x1400944e6  mov     rbx, rcx
0x1400944e9  mov     [rsp+48h+var_18], rax
0x1400944ee  movups  [rsp+48h+Buffer], xmm0
0x1400944f3  cmp     [rcx+10h], rax
0x1400944f7  jz      loc_140094594
0x1400944fd  lea     rax, [rcx+48h]
0x140094501  mov     rcx, [rax]
0x140094504  cmp     rcx, rax
0x140094507  jz      short loc_140094527
0x140094509  cmp     [rcx+8], rax
0x14009450d  jnz     loc_1400945E7
0x140094513  mov     rdx, [rax+8]
0x140094517  cmp     [rdx], rax
0x14009451a  jnz     loc_1400945E7
0x140094520  mov     [rdx], rcx
0x140094523  mov     [rcx+8], rdx
0x140094527  mov     rcx, [rbx]; Table
0x14009452a  mov     dl, 1; Restart
0x14009452c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140094533  nop     dword ptr [rax+rax+00h]
0x140094538  mov     rcx, [rbx]; Table
0x14009453b  test    rax, rax
0x14009453e  jnz     short loc_1400945B6
0x140094540  test    rcx, rcx
0x140094543  jz      short loc_14009455B
0x140094545  mov     edx, [rbx+3Ch]; Tag
0x140094548  call    cs:__imp_ExFreePoolWithTag
0x14009454f  nop     dword ptr [rax+rax+00h]
0x140094554  mov     qword ptr [rbx], 0
0x14009455b  mov     rcx, [rbx+8]; Lookaside
0x14009455f  call    cs:__imp_ExDeleteLookasideListEx
0x140094566  nop     dword ptr [rax+rax+00h]
0x14009456b  mov     rcx, [rbx+8]; P
0x14009456f  test    rcx, rcx
0x140094572  jz      short loc_14009458B
0x140094574  mov     edx, [rbx+3Ch]; Tag
0x140094577  call    cs:__imp_ExFreePoolWithTag
0x14009457e  nop     dword ptr [rax+rax+00h]
0x140094583  mov     qword ptr [rbx+8], 0
0x14009458b  mov     rcx, [rbx+40h]
0x14009458f  test    rcx, rcx
0x140094592  jnz     short loc_1400945EE
0x140094594  xor     edx, edx; Val
0x140094596  mov     rcx, rbx; void *
0x140094599  lea     r8d, [rdx+58h]; Size
0x14009459d  call    memset
0x1400945a2  mov     rcx, [rsp+48h+var_10]
0x1400945a7  xor     rcx, rsp; StackCookie
0x1400945aa  call    __security_check_cookie
0x1400945af  add     rsp, 40h
0x1400945b3  pop     rbx
0x1400945b4  retn
0x1400945b6  movups  xmm0, xmmword ptr [rax]
0x1400945b9  lea     rdx, [rsp+48h+Buffer]; Buffer
0x1400945be  movups  [rsp+48h+Buffer], xmm0
0x1400945c3  movsd   xmm1, qword ptr [rax+10h]
0x1400945c8  movsd   [rsp+48h+var_18], xmm1
0x1400945ce  mov     dword ptr [rsp+48h+var_18], 3
0x1400945d6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400945dd  nop     dword ptr [rax+rax+00h]
0x1400945e2  jmp     loc_140094527
0x1400945e7  mov     ecx, 3
0x1400945ec  int     29h; Win8: RtlFailFast(ecx)
0x1400945ee  call    FveRangeListFree
0x1400945f3  mov     edx, [rbx+38h]; Tag
0x1400945f6  mov     rcx, [rbx+40h]; P
0x1400945fa  call    cs:__imp_ExFreePoolWithTag
0x140094601  nop     dword ptr [rax+rax+00h]
0x140094606  jmp     short loc_140094594
```
