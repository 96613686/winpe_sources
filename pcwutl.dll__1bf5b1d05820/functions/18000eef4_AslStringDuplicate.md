# AslStringDuplicate

- ea: `0x18000eef4`
- end: `0x18000f127`
- name: `AslStringDuplicate`
- size: `563`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000d910`
- `0x18000e71c`
- `0x180013374`

## callees

- `0x18000e240`
- `0x18000eef4`
- `0x180013fc8`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000f10a`
- `ntdll!RtlFreeHeap` at `0x18000f10a`
- `ntdll!RtlAllocateHeap` at `0x18000f04a`
- `ntdll!RtlAllocateHeap` at `0x18000f04a`

## string_xrefs

- `0x18000f0a0`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicate(_QWORD *a1, _WORD *a2)
{
  void *v4; // rsi
  int v5; // ebx
  __int64 v6; // rax
  _WORD *i; // rcx
  const char *v8; // r9
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int64 v11; // rdx
  SIZE_T v12; // rax
  PVOID Heap; // rax
  int v14; // eax
  unsigned __int64 v16; // [rsp+90h] [rbp+18h]

  v4 = 0;
  *a1 = 0;
  v5 = 0;
  if ( a2 )
  {
    v6 = 0x7FFFFFFF;
    for ( i = a2; v6 && *i; ++i )
      --v6;
    if ( !v6 )
      v5 = -1073741811;
    if ( v5 < 0 )
      v16 = 0;
    else
      v16 = 0x7FFFFFFF - v6;
    if ( v5 < 0 )
    {
      v8 = "RtlStringCchLengthW failed [%x]";
      v9 = 590;
LABEL_13:
      AslLogCallPrintf(1, "AslStringDuplicate", v9, v8, v5);
      goto LABEL_29;
    }
    v10 = v16 + 1;
    if ( v16 + 1 < v16 )
    {
      v10 = -1;
      v5 = -1073741675;
      v11 = -1;
    }
    else
    {
      v5 = 0;
      v11 = v16 + 1;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 602;
      goto LABEL_13;
    }
    v12 = 2 * v11;
    if ( is_mul_ok(v11, 2u) )
    {
      v5 = 0;
    }
    else
    {
      v12 = -1;
      v5 = -1073741675;
    }
    if ( v5 < 0 )
    {
      v8 = "SIZE_T arithmetic failed [%x]";
      v9 = 608;
      goto LABEL_13;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
    v4 = Heap;
    if ( Heap )
    {
      v14 = RtlStringCchCopyW(Heap, v10, a2);
      v5 = v14;
      if ( v14 >= 0 )
      {
        *a1 = v4;
        v4 = 0;
        v5 = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AslStringDuplicate", 632, "RtlStringCchCopyW failed [%x]", v14);
      }
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslStringDuplicate", 615, "Out of memory");
    }
  }
LABEL_29:
  if ( v4 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000eef4  mov     rax, rsp
0x18000eef7  mov     [rax+8], rbx
0x18000eefb  push    rsi
0x18000eefc  push    rdi
0x18000eefd  push    r12
0x18000eeff  push    r14
0x18000ef01  push    r15
0x18000ef03  sub     rsp, 50h
0x18000ef07  mov     r15, rdx
0x18000ef0a  mov     r12, rcx
0x18000ef0d  xor     edi, edi
0x18000ef0f  mov     [rax+18h], rdi
0x18000ef13  mov     esi, edi
0x18000ef15  mov     [rax-40h], rdi
0x18000ef19  mov     [rcx], rdi
0x18000ef1c  mov     ebx, edi
0x18000ef1e  test    rdx, rdx
0x18000ef21  jz      loc_18000F0C0
0x18000ef27  lea     r8, [rax+18h]
0x18000ef2b  mov     edx, 7FFFFFFFh
0x18000ef30  mov     eax, edx
0x18000ef32  mov     [rsp+78h+var_30], rdx
0x18000ef37  mov     rcx, r15
0x18000ef3a  mov     [rsp+78h+var_38], rcx
0x18000ef3f  test    rax, rax
0x18000ef42  jz      short loc_18000EF5C
0x18000ef44  cmp     [rcx], di
0x18000ef47  jz      short loc_18000EF5C
0x18000ef49  add     rcx, 2
0x18000ef4d  mov     [rsp+78h+var_38], rcx
0x18000ef52  dec     rax
0x18000ef55  mov     [rsp+78h+var_30], rax
0x18000ef5a  jmp     short loc_18000EF3F
0x18000ef5c  mov     ecx, 0C000000Dh
0x18000ef61  test    rax, rax
0x18000ef64  cmovz   ebx, ecx
0x18000ef67  test    ebx, ebx
0x18000ef69  js      short loc_18000EF73
0x18000ef6b  sub     rdx, rax
0x18000ef6e  mov     [r8], rdx
0x18000ef71  jmp     short loc_18000EF76
0x18000ef73  mov     [r8], rdi
0x18000ef76  test    ebx, ebx
0x18000ef78  jns     short loc_18000EF7D
0x18000ef7a  mov     [r8], rdi
0x18000ef7d  mov     [rsp+78h+var_48], ebx
0x18000ef81  test    ebx, ebx
0x18000ef83  jns     short loc_18000EFAC
0x18000ef85  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x18000ef8c  mov     r8d, 24Eh
0x18000ef92  mov     [rsp+78h+var_58], ebx
0x18000ef96  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000ef9d  mov     ecx, 1
0x18000efa2  call    AslLogCallPrintf
0x18000efa7  jmp     loc_18000F0C4
0x18000efac  mov     rax, [rsp+78h+arg_10]
0x18000efb4  lea     r14, [rax+1]
0x18000efb8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000efbc  cmp     r14, rax
0x18000efbf  jb      short loc_18000EFD0
0x18000efc1  mov     [rsp+78h+arg_10], r14
0x18000efc9  mov     ebx, edi
0x18000efcb  mov     rdx, r14
0x18000efce  jmp     short loc_18000EFE3
0x18000efd0  mov     r14, rcx
0x18000efd3  mov     [rsp+78h+arg_10], rcx
0x18000efdb  mov     ebx, 0C0000095h
0x18000efe0  mov     rdx, rcx
0x18000efe3  mov     [rsp+78h+var_48], ebx
0x18000efe7  test    ebx, ebx
0x18000efe9  jns     short loc_18000EFFA
0x18000efeb  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18000eff2  mov     r8d, 25Ah
0x18000eff8  jmp     short loc_18000EF92
0x18000effa  mov     [rsp+78h+arg_18], rdi
0x18000f002  mov     eax, 2
0x18000f007  mul     rdx
0x18000f00a  test    rdx, rdx
0x18000f00d  jnz     short loc_18000F013
0x18000f00f  mov     ebx, edi
0x18000f011  jmp     short loc_18000F01B
0x18000f013  mov     rax, rcx
0x18000f016  mov     ebx, 0C0000095h
0x18000f01b  mov     [rsp+78h+var_48], ebx
0x18000f01f  test    ebx, ebx
0x18000f021  jns     short loc_18000F035
0x18000f023  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x18000f02a  mov     r8d, 260h
0x18000f030  jmp     loc_18000EF92
0x18000f035  mov     rcx, gs:60h
0x18000f03e  mov     r8, rax; Size
0x18000f041  mov     edx, 8; Flags
0x18000f046  mov     rcx, [rcx+30h]; HeapHandle
0x18000f04a  call    cs:__imp_RtlAllocateHeap
0x18000f050  mov     rsi, rax
0x18000f053  mov     [rsp+78h+var_40], rax
0x18000f058  test    rax, rax
0x18000f05b  jnz     short loc_18000F084
0x18000f05d  mov     ebx, 0C0000017h
0x18000f062  mov     [rsp+78h+var_48], ebx
0x18000f066  lea     r9, aOutOfMemory; "Out of memory"
0x18000f06d  mov     r8d, 267h
0x18000f073  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000f07a  lea     ecx, [rax+1]
0x18000f07d  call    AslLogCallPrintf
0x18000f082  jmp     short loc_18000F0C4
0x18000f084  mov     r8, r15
0x18000f087  mov     rdx, r14
0x18000f08a  mov     rcx, rsi
0x18000f08d  call    RtlStringCchCopyW
0x18000f092  mov     ebx, eax
0x18000f094  mov     [rsp+78h+var_48], eax
0x18000f098  test    eax, eax
0x18000f09a  jns     short loc_18000F0B2
0x18000f09c  mov     [rsp+78h+var_58], eax
0x18000f0a0  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x18000f0a7  mov     r8d, 278h
0x18000f0ad  jmp     loc_18000EF96
0x18000f0b2  mov     [r12], rsi
0x18000f0b6  mov     rsi, rdi
0x18000f0b9  mov     [rsp+78h+var_40], rdi
0x18000f0be  mov     ebx, edi
0x18000f0c0  mov     [rsp+78h+var_48], ebx
0x18000f0c4  jmp     short loc_18000F0F3
0x18000f0c6  mov     ebx, eax
0x18000f0c8  mov     [rsp+78h+var_48], eax
0x18000f0cc  mov     [rsp+78h+var_58], eax
0x18000f0d0  lea     r9, aExceptionEncou; "Exception encountered [%x]"
0x18000f0d7  mov     r8d, 289h
0x18000f0dd  lea     rdx, aAslstringdupli_0; "AslStringDuplicate"
0x18000f0e4  mov     ecx, 1
0x18000f0e9  call    AslLogCallPrintf
0x18000f0ee  mov     rsi, [rsp+78h+var_40]
0x18000f0f3  test    rsi, rsi
0x18000f0f6  jz      short loc_18000F110
0x18000f0f8  mov     rcx, gs:60h
0x18000f101  mov     r8, rsi; P
0x18000f104  xor     edx, edx; Flags
0x18000f106  mov     rcx, [rcx+30h]; HeapHandle
0x18000f10a  call    cs:__imp_RtlFreeHeap
0x18000f110  mov     eax, ebx
0x18000f112  mov     rbx, [rsp+78h+arg_0]
0x18000f11a  add     rsp, 50h
0x18000f11e  pop     r15
0x18000f120  pop     r14
0x18000f122  pop     r12
0x18000f124  pop     rdi
0x18000f125  pop     rsi
0x18000f126  retn
0x180019716  push    rbp
0x180019718  sub     rsp, 30h
0x18001971c  mov     rbp, rdx
0x18001971f  mov     rax, [rcx]
0x180019722  xor     ecx, ecx
0x180019724  cmp     dword ptr [rax], 0C00000FDh
0x18001972a  setnz   cl
0x18001972d  mov     [rbp+34h], ecx
0x180019730  mov     eax, [rbp+34h]
0x180019733  add     rsp, 30h
0x180019737  pop     rbp
0x180019738  retn
```
