# AslStringDuplicateA

- ea: `0x1400164c4`
- end: `0x140016668`
- name: `AslStringDuplicateA`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400160ec`

## callees

- `0x1400151b0`
- `0x1400164c4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x14001662b`
- `ntdll!RtlFreeHeap` at `0x14001662b`
- `ntdll!RtlAllocateHeap` at `0x140016555`
- `ntdll!RtlAllocateHeap` at `0x140016555`

## string_xrefs

- `0x1400165f7`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicateA(_QWORD *a1)
{
  const unsigned __int16 *v2; // r14
  __int64 v3; // r8
  const unsigned __int16 *v4; // rax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  const char *v7; // r9
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  _BYTE *Heap; // rax
  _BYTE *v11; // rsi
  __int64 v12; // rax
  _BYTE *v13; // rcx
  _BYTE *v14; // rax

  *a1 = 0;
  v2 = &dword_1400ACDEC;
  v3 = 0x7FFFFFFF;
  v4 = &dword_1400ACDEC;
  do
  {
    if ( !*(_BYTE *)v4 )
      break;
    v4 = (const unsigned __int16 *)((char *)v4 + 1);
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0xC000000D : 0;
  v6 = (0x7FFFFFFF - v3) & -(__int64)(v3 != 0);
  if ( !v3 )
  {
    v7 = "RtlStringCchLengthA failed [%x]";
    v8 = 479;
LABEL_23:
    AslLogCallPrintf(1, "AslStringDuplicateA", v8, v7, v5);
    return v5;
  }
  v9 = v6 + 1;
  if ( v6 + 1 < v6 )
  {
    v5 = -1073741675;
    v7 = "SIZE_T arithmetic failed [%x]";
    v8 = 490;
    goto LABEL_23;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v6 + 1);
  v11 = Heap;
  if ( Heap )
  {
    if ( v9 )
    {
      if ( v9 <= 0x7FFFFFFF )
      {
        v12 = 2147483646;
        v13 = v11;
        do
        {
          if ( !v12 )
            break;
          if ( !*(_BYTE *)v2 )
            break;
          *v13 = *(_BYTE *)v2;
          v2 = (const unsigned __int16 *)((char *)v2 + 1);
          ++v13;
          --v12;
          --v9;
        }
        while ( v9 );
        v14 = v13 - 1;
        v5 = v9 == 0 ? 0x80000005 : 0;
        if ( v9 )
          v14 = v13;
        *v14 = 0;
        if ( v9 )
        {
          *a1 = v11;
          return 0;
        }
      }
      else
      {
        v5 = -1073741811;
        *Heap = 0;
      }
    }
    else
    {
      v5 = -1073741811;
    }
    AslLogCallPrintf(1, "AslStringDuplicateA", 507, "RtlStringCchCopyW failed [%x]", v5);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
    return v5;
  }
  v5 = -1073741801;
  AslLogCallPrintf(1, "AslStringDuplicateA", 497, "Out of memory");
  return v5;
}

```

## disassembly

```asm
0x1400164c4  push    rbx
0x1400164c6  push    rsi
0x1400164c7  push    rdi
0x1400164c8  push    r14
0x1400164ca  push    r15
0x1400164cc  sub     rsp, 30h
0x1400164d0  mov     r15, rcx
0x1400164d3  mov     qword ptr [rcx], 0
0x1400164da  mov     ecx, 7FFFFFFFh
0x1400164df  lea     r14, dword_1400ACDEC
0x1400164e6  mov     r8d, ecx
0x1400164e9  mov     rax, r14
0x1400164ec  cmp     byte ptr [rax], 0
0x1400164ef  jz      short loc_1400164FA
0x1400164f1  inc     rax
0x1400164f4  sub     r8, 1
0x1400164f8  jnz     short loc_1400164EC
0x1400164fa  mov     rax, r8
0x1400164fd  mov     rdx, rcx
0x140016500  neg     rax
0x140016503  mov     rax, r8
0x140016506  sbb     ebx, ebx
0x140016508  sub     rdx, r8
0x14001650b  not     ebx
0x14001650d  and     ebx, 0C000000Dh
0x140016513  neg     rax
0x140016516  sbb     r9, r9
0x140016519  and     r9, rdx
0x14001651c  test    r8, r8
0x14001651f  jnz     short loc_140016533
0x140016521  lea     r9, aRtlstringcchle_0; "RtlStringCchLengthA failed [%x]"
0x140016528  mov     r8d, 1DFh
0x14001652e  jmp     loc_140016645
0x140016533  lea     rdi, [r9+1]
0x140016537  cmp     rdi, r9
0x14001653a  jb      loc_140016633
0x140016540  mov     rcx, gs:60h
0x140016549  mov     r8, rdi; Size
0x14001654c  mov     edx, 8; Flags
0x140016551  mov     rcx, [rcx+30h]; HeapHandle
0x140016555  call    cs:__imp_RtlAllocateHeap
0x14001655b  mov     rsi, rax
0x14001655e  test    rax, rax
0x140016561  jnz     short loc_140016589
0x140016563  lea     r9, aOutOfMemory_0; "Out of memory"
0x14001656a  mov     r8d, 1F1h
0x140016570  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x140016577  mov     ebx, 0C0000017h
0x14001657c  lea     ecx, [rax+1]
0x14001657f  call    AslLogCallPrintf
0x140016584  jmp     loc_14001665A
0x140016589  test    rdi, rdi
0x14001658c  jz      short loc_1400165EA
0x14001658e  cmp     rdi, 7FFFFFFFh
0x140016595  jbe     short loc_14001659E
0x140016597  mov     ebx, 0C000000Dh
0x14001659c  jmp     short loc_1400165F4
0x14001659e  mov     eax, 7FFFFFFEh
0x1400165a3  mov     rcx, rsi
0x1400165a6  test    rax, rax
0x1400165a9  jz      short loc_1400165C3
0x1400165ab  mov     dl, [r14]
0x1400165ae  test    dl, dl
0x1400165b0  jz      short loc_1400165C3
0x1400165b2  mov     [rcx], dl
0x1400165b4  inc     r14
0x1400165b7  inc     rcx
0x1400165ba  dec     rax
0x1400165bd  sub     rdi, 1
0x1400165c1  jnz     short loc_1400165A6
0x1400165c3  mov     rax, rdi
0x1400165c6  neg     rax
0x1400165c9  lea     rax, [rcx-1]
0x1400165cd  sbb     ebx, ebx
0x1400165cf  not     ebx
0x1400165d1  and     ebx, 80000005h
0x1400165d7  test    rdi, rdi
0x1400165da  cmovnz  rax, rcx
0x1400165de  mov     byte ptr [rax], 0
0x1400165e1  jz      short loc_1400165F7
0x1400165e3  mov     [r15], rsi
0x1400165e6  xor     ebx, ebx
0x1400165e8  jmp     short loc_14001665A
0x1400165ea  mov     ebx, 0C000000Dh
0x1400165ef  test    rdi, rdi
0x1400165f2  jz      short loc_1400165F7
0x1400165f4  mov     byte ptr [rax], 0
0x1400165f7  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x1400165fe  mov     [rsp+58h+var_38], ebx
0x140016602  mov     r8d, 1FBh
0x140016608  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x14001660f  mov     ecx, 1
0x140016614  call    AslLogCallPrintf
0x140016619  mov     rcx, gs:60h
0x140016622  mov     r8, rsi; P
0x140016625  xor     edx, edx; Flags
0x140016627  mov     rcx, [rcx+30h]; HeapHandle
0x14001662b  call    cs:__imp_RtlFreeHeap
0x140016631  jmp     short loc_14001665A
0x140016633  mov     ebx, 0C0000095h
0x140016638  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x14001663f  mov     r8d, 1EAh
0x140016645  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x14001664c  mov     [rsp+58h+var_38], ebx
0x140016650  mov     ecx, 1
0x140016655  call    AslLogCallPrintf
0x14001665a  mov     eax, ebx
0x14001665c  add     rsp, 30h
0x140016660  pop     r15
0x140016662  pop     r14
0x140016664  pop     rdi
0x140016665  pop     rsi
0x140016666  pop     rbx
0x140016667  retn
```
