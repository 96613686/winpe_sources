# ConstructKernelKeyPath

- ea: `0x1800035a0`
- end: `0x1800037fb`
- name: `ConstructKernelKeyPath`
- size: `603`
- prototype: `__int64 __fastcall(__int16, __int64, int *, __int64, bool *, struct _UNICODE_STRING **)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001d38c`
- `0x18001d698`

## callees

- `0x1800035a0`
- `0x18001d32c`
- `0x18001dae8`
- `0x18001dea8`

## import_xrefs

- `ntdll!RtlAppendUnicodeStringToString` at `0x18000373d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18000373d`
- `ntdll!RtlFreeHeap` at `0x1800037d1`
- `ntdll!RtlFreeHeap` at `0x1800037d1`
- `ntdll!NtQueryKey` at `0x18000364b`
- `ntdll!NtQueryKey` at `0x18000364b`
- `ntdll!RtlAppendUnicodeToString` at `0x180003727`
- `ntdll!RtlAppendUnicodeToString` at `0x180003727`
- `ntdll!RtlAllocateHeap` at `0x1800036bd`
- `ntdll!RtlAllocateHeap` at `0x1800036bd`

## pseudocode

```c
__int64 __fastcall ConstructKernelKeyPath(
        __int16 a1,
        __int64 a2,
        int *a3,
        __int64 a4,
        bool *a5,
        struct _UNICODE_STRING **a6)
{
  int v6; // eax
  struct _UNICODE_STRING *v7; // rsi
  const UNICODE_STRING *v10; // rbp
  NTSTATUS KeyPath; // ebx
  int v13; // r12d
  void *v14; // rcx
  struct _UNICODE_STRING *Heap; // rax
  struct _UNICODE_STRING *v16; // r12
  __int64 v17; // rcx
  int v18; // ecx
  int v19; // eax
  __int16 v21; // [rsp+28h] [rbp-40h]
  int KeyInformation; // [rsp+78h] [rbp+10h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+20h] BYREF

  v6 = 0;
  *(_BYTE *)a4 = 0;
  v7 = 0;
  *(_DWORD *)(a4 + 2) = 0;
  *(_DWORD *)(a4 + 8) = 0;
  v10 = *(const UNICODE_STRING **)(a2 + 16);
  KeyInformation = 0;
  if ( !v10->Length || (*(_QWORD *)(a2 + 8) == 0) == (*v10->Buffer == 92) )
  {
    v13 = a1 & 0x300;
    if ( v13 == 768 )
    {
LABEL_5:
      KeyPath = -1073741811;
      goto LABEL_28;
    }
    v14 = *(void **)(a2 + 8);
    if ( v14 )
    {
      ResultLength = 0;
      KeyPath = NtQueryKey(v14, KeyHandleTagsInformation, &KeyInformation, 4u, &ResultLength);
      if ( KeyPath < 0 )
        goto LABEL_28;
      v6 = KeyInformation & 0xF01;
      KeyInformation = v6;
      if ( !v13 )
      {
        v13 = v6 & 0x300;
        if ( v13 == 768 )
          goto LABEL_5;
      }
      *a3 = v13 | v6 & 0x401;
      if ( (v6 & 0x400) != 0 )
        goto LABEL_11;
    }
    else
    {
      *a3 = v13;
    }
    if ( v13 == 512 )
    {
      Heap = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1060u);
      v7 = Heap;
      if ( !Heap )
      {
        KeyPath = -1073741801;
        goto LABEL_28;
      }
      *(_DWORD *)&Heap->Length = 135790592;
      v16 = Heap + 1;
      Heap->Buffer = &Heap[2].Length;
      Heap[1].Length = 0;
      Heap[1].Buffer = (PWSTR)&Heap[131].Buffer;
      Heap[1].MaximumLength = 2072;
      v17 = *(_QWORD *)(a2 + 8);
      if ( v17
        && ((KeyPath = GetKeyPath(v17, Heap), KeyPath < 0)
         || (KeyPath = RtlAppendUnicodeToString(v7, L"\\"), KeyPath < 0))
        || (KeyPath = RtlAppendUnicodeStringToString(v7, v10), KeyPath < 0)
        || (v21 = Wow64DetectMachineTypeInternal(),
            KeyPath = Wow64RedirectKeyPathInternal(&off_180022240, v7, &v7[1], a4, 512, v21),
            KeyPath < 0) )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
        v7 = 0;
        goto LABEL_28;
      }
      v18 = *(_DWORD *)(a4 + 8);
      if ( (v18 & 0x300) != 0 )
      {
        v19 = *(_DWORD *)(a4 + 8);
      }
      else
      {
        v19 = v18 | *a3 & 0x300;
        *(_DWORD *)(a4 + 8) = v19;
      }
      *a3 = v19;
      v6 = KeyInformation;
      if ( *(_BYTE *)a4 )
      {
        *(_QWORD *)(a2 + 8) = 0;
        *(_QWORD *)(a2 + 16) = v16;
      }
LABEL_26:
      *a5 = *a3 != v6;
      goto LABEL_28;
    }
LABEL_11:
    KeyPath = 0;
    goto LABEL_26;
  }
  KeyPath = -1073741765;
LABEL_28:
  *a6 = v7;
  return (unsigned int)KeyPath;
}

```

## disassembly

```asm
0x1800035a0  mov     [rsp+arg_0], rbx
0x1800035a5  push    rbp
0x1800035a6  push    rsi
0x1800035a7  push    rdi
0x1800035a8  push    r12
0x1800035aa  push    r13
0x1800035ac  push    r14
0x1800035ae  push    r15
0x1800035b0  sub     rsp, 30h
0x1800035b4  xor     eax, eax
0x1800035b6  xor     r10d, r10d
0x1800035b9  mov     [r9], al
0x1800035bc  xor     esi, esi
0x1800035be  mov     [r9+2], r10d
0x1800035c2  mov     rdi, r9
0x1800035c5  mov     [r9+8], eax
0x1800035c9  mov     r13, r8
0x1800035cc  mov     rbp, [rdx+10h]
0x1800035d0  mov     r15, rdx
0x1800035d3  mov     [rsp+68h+KeyInformation], eax
0x1800035d7  mov     r12d, ecx
0x1800035da  cmp     [rbp+0], ax
0x1800035de  jz      short loc_180003604
0x1800035e0  mov     rcx, [rbp+8]
0x1800035e4  xor     edx, edx
0x1800035e6  cmp     word ptr [rcx], 5Ch ; '\'
0x1800035ea  setz    dl
0x1800035ed  xor     ecx, ecx
0x1800035ef  cmp     [r15+8], rax
0x1800035f3  setz    cl
0x1800035f6  cmp     ecx, edx
0x1800035f8  jz      short loc_180003604
0x1800035fa  mov     ebx, 0C000003Bh
0x1800035ff  jmp     loc_1800037D9
0x180003604  and     r12d, 300h
0x18000360b  cmp     r12d, 300h
0x180003612  jnz     short loc_18000361E
0x180003614  mov     ebx, 0C000000Dh
0x180003619  jmp     loc_1800037D9
0x18000361e  mov     rcx, [r15+8]; KeyHandle
0x180003622  test    rcx, rcx
0x180003625  jz      short loc_18000369C
0x180003627  mov     [rsp+68h+arg_18], eax
0x18000362e  lea     r8, [rsp+68h+KeyInformation]; KeyInformation
0x180003633  lea     rax, [rsp+68h+arg_18]
0x18000363b  mov     r9d, 4; Length
0x180003641  mov     edx, 7; KeyInformationClass
0x180003646  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18000364b  call    cs:__imp_NtQueryKey
0x180003651  mov     ebx, eax
0x180003653  test    eax, eax
0x180003655  js      loc_1800037D9
0x18000365b  mov     eax, [rsp+68h+KeyInformation]
0x18000365f  and     eax, 0F01h
0x180003664  mov     [rsp+68h+KeyInformation], eax
0x180003668  test    r12d, r12d
0x18000366b  jnz     short loc_180003680
0x18000366d  mov     r12d, eax
0x180003670  and     r12d, 300h
0x180003677  cmp     r12d, 300h
0x18000367e  jz      short loc_180003614
0x180003680  mov     ecx, eax
0x180003682  and     ecx, 401h
0x180003688  or      ecx, r12d
0x18000368b  mov     [r13+0], ecx
0x18000368f  bt      eax, 0Ah
0x180003693  jnb     short loc_18000369F
0x180003695  xor     ebx, ebx
0x180003697  jmp     loc_1800037AC
0x18000369c  mov     [r8], r12d
0x18000369f  cmp     r12d, 200h
0x1800036a6  jnz     short loc_180003695
0x1800036a8  mov     rcx, gs:60h
0x1800036b1  xor     edx, edx; Flags
0x1800036b3  mov     r8d, 1060h; Size
0x1800036b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800036bd  call    cs:__imp_RtlAllocateHeap
0x1800036c3  mov     rsi, rax
0x1800036c6  test    rax, rax
0x1800036c9  jnz     short loc_1800036D5
0x1800036cb  mov     ebx, 0C0000017h
0x1800036d0  jmp     loc_1800037D9
0x1800036d5  mov     dword ptr [rax], 8180000h
0x1800036db  lea     r12, [rsi+10h]
0x1800036df  add     rax, 20h ; ' '
0x1800036e3  mov     ecx, 818h
0x1800036e8  mov     [rsi+8], rax
0x1800036ec  xor     eax, eax
0x1800036ee  mov     [r12], ax
0x1800036f3  lea     rax, [rsi+838h]
0x1800036fa  mov     [rsi+18h], rax
0x1800036fe  mov     [rsi+12h], cx
0x180003702  mov     rcx, [r15+8]
0x180003706  test    rcx, rcx
0x180003709  jz      short loc_180003737
0x18000370b  mov     rdx, rsi
0x18000370e  call    GetKeyPath
0x180003713  mov     ebx, eax
0x180003715  test    eax, eax
0x180003717  js      loc_1800037BF
0x18000371d  lea     rdx, Source; "\\"
0x180003724  mov     rcx, rsi; Destination
0x180003727  call    cs:__imp_RtlAppendUnicodeToString
0x18000372d  mov     ebx, eax
0x18000372f  test    eax, eax
0x180003731  js      loc_1800037BF
0x180003737  mov     rdx, rbp; Source
0x18000373a  mov     rcx, rsi; Destination
0x18000373d  call    cs:__imp_RtlAppendUnicodeStringToString
0x180003743  mov     ebx, eax
0x180003745  test    eax, eax
0x180003747  js      short loc_1800037BF
0x180003749  call    Wow64DetectMachineTypeInternal
0x18000374e  mov     [rsp+68h+var_40], ax
0x180003753  lea     rcx, off_180022240
0x18000375a  mov     r9, rdi
0x18000375d  mov     dword ptr [rsp+68h+ResultLength], 200h
0x180003765  mov     r8, r12
0x180003768  mov     rdx, rsi
0x18000376b  call    Wow64RedirectKeyPathInternal
0x180003770  mov     ebx, eax
0x180003772  test    eax, eax
0x180003774  js      short loc_1800037BF
0x180003776  mov     ecx, [rdi+8]
0x180003779  test    ecx, 300h
0x18000377f  jnz     short loc_180003791
0x180003781  mov     eax, [r13+0]
0x180003785  and     eax, 300h
0x18000378a  or      eax, ecx
0x18000378c  mov     [rdi+8], eax
0x18000378f  jmp     short loc_180003793
0x180003791  mov     eax, ecx
0x180003793  mov     [r13+0], eax
0x180003797  cmp     byte ptr [rdi], 0
0x18000379a  mov     eax, [rsp+68h+KeyInformation]
0x18000379e  jz      short loc_1800037AC
0x1800037a0  mov     qword ptr [r15+8], 0
0x1800037a8  mov     [r15+10h], r12
0x1800037ac  cmp     [r13+0], eax
0x1800037b0  mov     rax, [rsp+68h+arg_20]
0x1800037b8  setnz   cl
0x1800037bb  mov     [rax], cl
0x1800037bd  jmp     short loc_1800037D9
0x1800037bf  mov     rcx, gs:60h
0x1800037c8  mov     r8, rsi; P
0x1800037cb  xor     edx, edx; Flags
0x1800037cd  mov     rcx, [rcx+30h]; HeapHandle
0x1800037d1  call    cs:__imp_RtlFreeHeap
0x1800037d7  xor     esi, esi
0x1800037d9  mov     rax, [rsp+68h+arg_28]
0x1800037e1  mov     [rax], rsi
0x1800037e4  mov     eax, ebx
0x1800037e6  mov     rbx, [rsp+68h+arg_0]
0x1800037eb  add     rsp, 30h
0x1800037ef  pop     r15
0x1800037f1  pop     r14
0x1800037f3  pop     r13
0x1800037f5  pop     r12
0x1800037f7  pop     rdi
0x1800037f8  pop     rsi
0x1800037f9  pop     rbp
0x1800037fa  retn
```
