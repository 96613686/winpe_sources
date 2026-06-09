# SdbpOpenCompressedDatabase

- ea: `0x1800adcc8`
- end: `0x1800ade4d`
- name: `SdbpOpenCompressedDatabase`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180040ee0`

## callees

- `0x180041774`
- `0x18004281c`
- `0x18006b3b0`
- `0x1800ab684`
- `0x1800adcc8`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800add7d`
- `ntdll!RtlAllocateHeap` at `0x1800add7d`

## string_xrefs

- `0x1800adcfd`: `SdbpOpenCompressedDatabase`
- `0x1800addd2`: `SdbpOpenCompressedDatabase`
- `0x1800add52`: `SDB compression algorithm does not match callback algorithm.`
- `0x1800add38`: `SDB is not compressed`
- `0x1800add8b`: `SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory`

## pseudocode

```c
__int64 __fastcall SdbpOpenCompressedDatabase(_QWORD *a1, __int64 a2, unsigned int a3)
{
  unsigned int v3; // edi
  _DWORD *v4; // rbx
  __int64 v7; // rbp
  _DWORD *v8; // rcx
  PVOID Heap; // r14
  __int64 result; // rax
  _DWORD *v11; // rax
  unsigned int v12; // [rsp+78h] [rbp+10h] BYREF
  int v13; // [rsp+7Ch] [rbp+14h]

  v13 = HIDWORD(a2);
  v3 = 0;
  v4 = 0;
  v12 = 0;
  if ( !g_ExpandCallback )
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 175, "No expand callback method set. Cannot expand ZDB file.");
    goto LABEL_16;
  }
  v7 = *a1;
  if ( *(_DWORD *)(*a1 + 20LL) >= 0x14u )
  {
    v8 = *(_DWORD **)(v7 + 8);
    if ( v8[2] == 1717724282 )
    {
      if ( v8[3] == g_ExpectedAlgorithm )
      {
        v12 = v8[4];
        Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v12);
        if ( Heap )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(PVOID, unsigned int *, __int64, _QWORD))g_ExpandCallback)(
                               Heap,
                               &v12,
                               *(_QWORD *)(v7 + 8) + 20LL,
                               (unsigned int)(*(_DWORD *)(v7 + 20) - 20)) )
          {
            v11 = SdbpOpenDatabaseInMemory((__int64)Heap, v12, a3);
            v4 = v11;
            if ( v11 )
            {
              v11[6] |= 0xCu;
              v3 = 1;
              v12 = 0;
              goto LABEL_16;
            }
          }
          else
          {
            AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 221, "Expand callback failed to expand SDB");
          }
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
          v12 = 0;
          if ( v4 )
          {
            SdbCloseDatabaseRead(v4);
            v4 = 0;
          }
        }
        else
        {
          AslLogCallPrintf(
            1,
            "SdbpOpenCompressedDatabase",
            211,
            "SdbpOpenCompressedDatabase failed to allocate expanded buffer - out of memory");
        }
      }
      else
      {
        AslLogCallPrintf(
          1,
          "SdbpOpenCompressedDatabase",
          192,
          "SDB compression algorithm does not match callback algorithm.");
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 187, "SDB is not compressed");
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbpOpenCompressedDatabase", 180, "SDB file too small to be valid");
  }
LABEL_16:
  SdbCloseDatabaseRead(*a1);
  result = v3;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800adcc8  mov     [rsp+arg_8], rdx
0x1800adccd  push    rbx
0x1800adcce  push    rbp
0x1800adccf  push    rsi
0x1800adcd0  push    rdi
0x1800adcd1  push    r14
0x1800adcd3  push    r15
0x1800adcd5  sub     rsp, 38h
0x1800adcd9  xor     edi, edi
0x1800adcdb  xor     ebx, ebx
0x1800adcdd  cmp     cs:g_ExpandCallback, rbx
0x1800adce4  mov     r15d, r8d
0x1800adce7  mov     rsi, rcx
0x1800adcea  mov     dword ptr [rsp+68h+arg_8], edi
0x1800adcee  jnz     short loc_1800ADD13
0x1800adcf0  lea     r9, aNoExpandCallba; "No expand callback method set. Cannot e"...
0x1800adcf7  mov     r8d, 0AFh
0x1800adcfd  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x1800add04  mov     ecx, 1
0x1800add09  call    AslLogCallPrintf
0x1800add0e  jmp     loc_1800ADE09
0x1800add13  mov     rbp, [rcx]
0x1800add16  cmp     dword ptr [rbp+14h], 14h
0x1800add1a  jnb     short loc_1800ADD2B
0x1800add1c  lea     r9, aSdbFileTooSmal; "SDB file too small to be valid"
0x1800add23  mov     r8d, 0B4h
0x1800add29  jmp     short loc_1800ADCFD
0x1800add2b  mov     rcx, [rbp+8]
0x1800add2f  cmp     dword ptr [rcx+8], 6662647Ah
0x1800add36  jz      short loc_1800ADD47
0x1800add38  lea     r9, aSdbIsNotCompre; "SDB is not compressed"
0x1800add3f  mov     r8d, 0BBh
0x1800add45  jmp     short loc_1800ADCFD
0x1800add47  mov     eax, cs:g_ExpectedAlgorithm
0x1800add4d  cmp     [rcx+0Ch], eax
0x1800add50  jz      short loc_1800ADD61
0x1800add52  lea     r9, aSdbCompression; "SDB compression algorithm does not matc"...
0x1800add59  mov     r8d, 0C0h
0x1800add5f  jmp     short loc_1800ADCFD
0x1800add61  mov     eax, [rcx+10h]
0x1800add64  mov     edx, 8; Flags
0x1800add69  mov     dword ptr [rsp+68h+arg_8], eax
0x1800add6d  mov     r8d, eax; Size
0x1800add70  mov     rcx, gs:60h
0x1800add79  mov     rcx, [rcx+30h]; HeapHandle
0x1800add7d  call    cs:__imp_RtlAllocateHeap
0x1800add83  mov     r14, rax
0x1800add86  test    rax, rax
0x1800add89  jnz     short loc_1800ADD9D
0x1800add8b  lea     r9, aSdbpopencompre_1; "SdbpOpenCompressedDatabase failed to al"...
0x1800add92  mov     r8d, 0D3h
0x1800add98  jmp     loc_1800ADCFD
0x1800add9d  mov     r9d, [rbp+14h]
0x1800adda1  lea     rdx, [rsp+68h+arg_8]
0x1800adda6  mov     r8, [rbp+8]
0x1800addaa  sub     r9d, 14h
0x1800addae  mov     rax, cs:g_ExpandCallback
0x1800addb5  add     r8, 14h
0x1800addb9  mov     rcx, r14
0x1800addbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800addc1  test    eax, eax
0x1800addc3  jnz     short loc_1800ADE23
0x1800addc5  lea     r9, aExpandCallback; "Expand callback failed to expand SDB"
0x1800addcc  mov     r8d, 0DDh
0x1800addd2  lea     rdx, aSdbpopencompre_0; "SdbpOpenCompressedDatabase"
0x1800addd9  lea     ecx, [rax+1]
0x1800adddc  call    AslLogCallPrintf
0x1800adde1  mov     rcx, gs:60h
0x1800addea  mov     rdx, r14
0x1800added  mov     rcx, [rcx+30h]
0x1800addf1  call    AslFree
0x1800addf6  mov     dword ptr [rsp+68h+arg_8], edi
0x1800addfa  test    rbx, rbx
0x1800addfd  jz      short loc_1800ADE09
0x1800addff  mov     rcx, rbx
0x1800ade02  call    SdbCloseDatabaseRead
0x1800ade07  xor     ebx, ebx
0x1800ade09  mov     rcx, [rsi]
0x1800ade0c  call    SdbCloseDatabaseRead
0x1800ade11  mov     eax, edi
0x1800ade13  mov     [rsi], rbx
0x1800ade16  add     rsp, 38h
0x1800ade1a  pop     r15
0x1800ade1c  pop     r14
0x1800ade1e  pop     rdi
0x1800ade1f  pop     rsi
0x1800ade20  pop     rbp
0x1800ade21  pop     rbx
0x1800ade22  retn
0x1800ade23  mov     edx, dword ptr [rsp+68h+arg_8]
0x1800ade27  mov     r8d, r15d
0x1800ade2a  mov     rcx, r14
0x1800ade2d  call    SdbpOpenDatabaseInMemory
0x1800ade32  mov     rbx, rax
0x1800ade35  test    rax, rax
0x1800ade38  jz      short loc_1800ADDE1
0x1800ade3a  or      dword ptr [rax+18h], 0Ch
0x1800ade3e  mov     edi, 1
0x1800ade43  mov     dword ptr [rsp+68h+arg_8], 0
0x1800ade4b  jmp     short loc_1800ADE09
```
