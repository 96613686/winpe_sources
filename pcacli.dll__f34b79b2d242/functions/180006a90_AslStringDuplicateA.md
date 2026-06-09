# AslStringDuplicateA

- ea: `0x180006a90`
- end: `0x180006bf5`
- name: `AslStringDuplicateA`
- size: `357`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800069e0`

## callees

- `0x180006a90`
- `0x180007738`
- `0x18000a9ac`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180006aff`
- `ntdll!RtlAllocateHeap` at `0x180006aff`
- `ntdll!RtlFreeHeap` at `0x180006b85`
- `ntdll!RtlFreeHeap` at `0x180006b85`

## string_xrefs

- `0x180006b51`: `RtlStringCchCopyW failed [%x]`

## pseudocode

```c
__int64 __fastcall AslStringDuplicateA(_QWORD *a1)
{
  __int64 v1; // rdx
  int *v2; // rax
  unsigned __int64 v4; // r8
  __int64 v5; // rbx
  PVOID Heap; // rax
  void *v7; // rdi
  int v9; // eax
  unsigned int v10; // ebx

  *a1 = 0;
  v1 = 0x7FFFFFFF;
  v2 = &dword_18000F424;
  do
  {
    if ( !*(_BYTE *)v2 )
      break;
    v2 = (int *)((char *)v2 + 1);
    --v1;
  }
  while ( v1 );
  if ( v1 )
  {
    v4 = 0x7FFFFFFF - v1;
    v5 = 0x7FFFFFFF - v1 + 1;
    if ( v4 + 1 < v4 )
    {
      AslLogCallPrintf(1, "AslStringDuplicateA", 490, "SIZE_T arithmetic failed [%x]", -1073741675);
      return 3221225621LL;
    }
    else
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v4 + 1);
      v7 = Heap;
      if ( Heap )
      {
        v9 = RtlStringCchCopyA(Heap, v5);
        v10 = v9;
        if ( v9 >= 0 )
        {
          *a1 = v7;
          return 0;
        }
        else
        {
          AslLogCallPrintf(1, "AslStringDuplicateA", 507, "RtlStringCchCopyW failed [%x]", v9);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
          return v10;
        }
      }
      else
      {
        AslLogCallPrintf(1, "AslStringDuplicateA", 497, "Out of memory");
        return 3221225495LL;
      }
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslStringDuplicateA", 479, "RtlStringCchLengthA failed [%x]", -1073741811);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180006a90  mov     [rsp+arg_8], rbx
0x180006a95  push    rsi
0x180006a96  sub     rsp, 30h
0x180006a9a  mov     r8d, 7FFFFFFFh
0x180006aa0  mov     qword ptr [rcx], 0
0x180006aa7  mov     edx, r8d
0x180006aaa  lea     rax, dword_18000F424
0x180006ab1  mov     rsi, rcx
0x180006ab4  cmp     byte ptr [rax], 0
0x180006ab7  jz      short loc_180006AC2
0x180006ab9  inc     rax
0x180006abc  sub     rdx, 1
0x180006ac0  jnz     short loc_180006AB4
0x180006ac2  xor     eax, eax
0x180006ac4  mov     ebx, 0C000000Dh
0x180006ac9  test    rdx, rdx
0x180006acc  cmovnz  ebx, eax
0x180006acf  jz      loc_180006BCC
0x180006ad5  sub     r8, rdx
0x180006ad8  lea     rbx, [r8+1]
0x180006adc  cmp     rbx, r8
0x180006adf  jb      loc_180006B96
0x180006ae5  mov     rcx, gs:60h
0x180006aee  mov     r8, rbx; Size
0x180006af1  mov     edx, 8; Flags
0x180006af6  mov     [rsp+38h+arg_0], rdi
0x180006afb  mov     rcx, [rcx+30h]; HeapHandle
0x180006aff  call    cs:__imp_RtlAllocateHeap
0x180006b05  mov     rdi, rax
0x180006b08  test    rax, rax
0x180006b0b  jnz     short loc_180006B40
0x180006b0d  lea     r9, aOutOfMemory; "Out of memory"
0x180006b14  mov     r8d, 1F1h
0x180006b1a  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x180006b21  mov     ecx, 1
0x180006b26  call    AslLogCallPrintf
0x180006b2b  mov     eax, 0C0000017h
0x180006b30  mov     rdi, [rsp+38h+arg_0]
0x180006b35  mov     rbx, [rsp+38h+arg_8]
0x180006b3a  add     rsp, 30h
0x180006b3e  pop     rsi
0x180006b3f  retn
0x180006b40  mov     rdx, rbx
0x180006b43  mov     rcx, rdi
0x180006b46  call    RtlStringCchCopyA
0x180006b4b  mov     ebx, eax
0x180006b4d  test    eax, eax
0x180006b4f  jns     short loc_180006B8F
0x180006b51  lea     r9, aRtlstringcchco; "RtlStringCchCopyW failed [%x]"
0x180006b58  mov     [rsp+38h+var_18], eax
0x180006b5c  mov     r8d, 1FBh
0x180006b62  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x180006b69  mov     ecx, 1
0x180006b6e  call    AslLogCallPrintf
0x180006b73  mov     rcx, gs:60h
0x180006b7c  mov     r8, rdi; P
0x180006b7f  xor     edx, edx; Flags
0x180006b81  mov     rcx, [rcx+30h]; HeapHandle
0x180006b85  call    cs:__imp_RtlFreeHeap
0x180006b8b  mov     eax, ebx
0x180006b8d  jmp     short loc_180006B30
0x180006b8f  mov     [rsi], rdi
0x180006b92  xor     eax, eax
0x180006b94  jmp     short loc_180006B30
0x180006b96  lea     r9, aSizeTArithmeti; "SIZE_T arithmetic failed [%x]"
0x180006b9d  mov     [rsp+38h+var_18], 0C0000095h
0x180006ba5  mov     r8d, 1EAh
0x180006bab  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x180006bb2  mov     ecx, 1
0x180006bb7  call    AslLogCallPrintf
0x180006bbc  mov     rbx, [rsp+38h+arg_8]
0x180006bc1  mov     eax, 0C0000095h
0x180006bc6  add     rsp, 30h
0x180006bca  pop     rsi
0x180006bcb  retn
0x180006bcc  lea     r9, aRtlstringcchle_0; "RtlStringCchLengthA failed [%x]"
0x180006bd3  mov     [rsp+38h+var_18], ebx
0x180006bd7  mov     r8d, 1DFh
0x180006bdd  lea     rdx, aAslstringdupli_1; "AslStringDuplicateA"
0x180006be4  mov     ecx, 1
0x180006be9  call    AslLogCallPrintf
0x180006bee  mov     eax, ebx
0x180006bf0  jmp     loc_180006B35
```
