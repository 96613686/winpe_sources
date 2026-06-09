# RegSecReadAllowedPath

- ea: `0x180018364`
- end: `0x180018531`
- name: `RegSecReadAllowedPath`
- size: `461`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001782c`

## callees

- `0x180018364`
- `0x18001d7b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180018462`
- `ntdll!RtlFreeHeap` at `0x1800184fd`
- `ntdll!RtlFreeHeap` at `0x180018462`
- `ntdll!RtlFreeHeap` at `0x1800184fd`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001839d`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800184e1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001839d`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800184e1`
- `ntdll!RtlAllocateHeap` at `0x180018410`
- `ntdll!RtlAllocateHeap` at `0x1800184bd`
- `ntdll!RtlAllocateHeap` at `0x180018410`
- `ntdll!RtlAllocateHeap` at `0x1800184bd`

## pseudocode

```c
__int64 __fastcall RegSecReadAllowedPath(
        HANDLE KeyHandle,
        __int64 a2,
        struct _UNICODE_STRING **a3,
        WCHAR **a4,
        unsigned int *a5)
{
  int v8; // eax
  WCHAR *Heap; // rbx
  const WCHAR *v11; // rdi
  unsigned int v12; // esi
  _WORD *i; // rax
  struct _UNICODE_STRING *v14; // rbp
  int v15; // r14d
  SIZE_T v16; // [rsp+20h] [rbp-68h]
  SIZE_T v17; // [rsp+20h] [rbp-68h]
  struct _UNICODE_STRING ValueName; // [rsp+30h] [rbp-58h] BYREF
  ULONG Size; // [rsp+98h] [rbp+10h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+14h]

  Size_4 = HIDWORD(a2);
  ValueName = 0;
  Size = 0;
  if ( RtlInitUnicodeStringEx(&ValueName, MachineValue) >= 0 )
  {
    LODWORD(v16) = 0;
    v8 = Wow64NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, 0, v16, &Size);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, Size);
      if ( Heap )
      {
        LODWORD(v17) = Size;
        if ( (int)Wow64NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, Heap, v17, &Size) >= 0
          && *((_DWORD *)Heap + 1) == 7 )
        {
          v11 = Heap + 6;
          v12 = 0;
          for ( i = Heap + 6; *i; ++v12 )
          {
            do
              ++i;
            while ( *i );
            ++i;
          }
          v14 = (struct _UNICODE_STRING *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * v12);
          if ( v14 )
          {
            v15 = 0;
            while ( *v11 )
            {
              if ( RtlInitUnicodeStringEx(&v14[v15], v11) < 0 )
              {
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
                goto LABEL_9;
              }
              while ( *v11 )
                ++v11;
              ++v15;
              ++v11;
            }
            *a5 = v12;
            *a4 = Heap;
            *a3 = v14;
            return 1;
          }
        }
LABEL_9:
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      }
    }
    else if ( v8 == -1073741766 || v8 == -1073741772 )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180018364  mov     rax, rsp
0x180018367  mov     [rax+10h], rdx
0x18001836b  push    rbx
0x18001836c  push    rbp
0x18001836d  push    rsi
0x18001836e  push    rdi
0x18001836f  push    r12
0x180018371  push    r13
0x180018373  push    r14
0x180018375  push    r15
0x180018377  sub     rsp, 48h
0x18001837b  mov     rdi, rcx
0x18001837e  lea     rdx, MachineValue; "Machine"
0x180018385  xorps   xmm0, xmm0
0x180018388  lea     rcx, [rax-58h]; DestinationString
0x18001838c  xor     r13d, r13d
0x18001838f  mov     r15, r9
0x180018392  movups  xmmword ptr [rax-58h], xmm0
0x180018396  mov     [rax+10h], r13d
0x18001839a  mov     r12, r8
0x18001839d  call    cs:__imp_RtlInitUnicodeStringEx
0x1800183a3  test    eax, eax
0x1800183a5  js      loc_180018468
0x1800183ab  lea     rax, [rsp+88h+Size]
0x1800183b3  xor     r9d, r9d; void *
0x1800183b6  mov     [rsp+88h+var_60], rax; PULONG
0x1800183bb  lea     r8d, [r13+2]; KeyValueInformationClass
0x1800183bf  lea     rdx, [rsp+88h+ValueName]; ValueName
0x1800183c4  mov     dword ptr [rsp+88h+var_68], r13d; Size
0x1800183c9  mov     rcx, rdi; KeyHandle
0x1800183cc  call    Wow64NtQueryValueKey
0x1800183d1  mov     edx, 80000000h
0x1800183d6  lea     ecx, [rax+rdx]
0x1800183d9  test    edx, ecx
0x1800183db  jnz     short loc_1800183F9
0x1800183dd  cmp     eax, 0C0000023h
0x1800183e2  jz      short loc_1800183F9
0x1800183e4  cmp     eax, 0C000003Ah
0x1800183e9  jz      short loc_1800183F2
0x1800183eb  cmp     eax, 0C0000034h
0x1800183f0  jnz     short loc_180018468
0x1800183f2  mov     eax, 1
0x1800183f7  jmp     short loc_18001846A
0x1800183f9  mov     rcx, gs:60h
0x180018402  xor     edx, edx; Flags
0x180018404  mov     r8d, dword ptr [rsp+88h+Size]; Size
0x18001840c  mov     rcx, [rcx+30h]; HeapHandle
0x180018410  call    cs:__imp_RtlAllocateHeap
0x180018416  mov     rbx, rax
0x180018419  test    rax, rax
0x18001841c  jz      short loc_180018468
0x18001841e  mov     ecx, dword ptr [rsp+88h+Size]
0x180018425  lea     rax, [rsp+88h+Size]
0x18001842d  mov     [rsp+88h+var_60], rax; PULONG
0x180018432  lea     rdx, [rsp+88h+ValueName]; ValueName
0x180018437  mov     dword ptr [rsp+88h+var_68], ecx; Size
0x18001843b  mov     r9, rbx; void *
0x18001843e  mov     rcx, rdi; KeyHandle
0x180018441  mov     r8d, 2; KeyValueInformationClass
0x180018447  call    Wow64NtQueryValueKey
0x18001844c  test    eax, eax
0x18001844e  jns     short loc_18001847B
0x180018450  mov     rcx, gs:60h
0x180018459  mov     r8, rbx; P
0x18001845c  xor     edx, edx; Flags
0x18001845e  mov     rcx, [rcx+30h]; HeapHandle
0x180018462  call    cs:__imp_RtlFreeHeap
0x180018468  xor     eax, eax
0x18001846a  add     rsp, 48h
0x18001846e  pop     r15
0x180018470  pop     r14
0x180018472  pop     r13
0x180018474  pop     r12
0x180018476  pop     rdi
0x180018477  pop     rsi
0x180018478  pop     rbp
0x180018479  pop     rbx
0x18001847a  retn
0x18001847b  cmp     dword ptr [rbx+4], 7
0x18001847f  jnz     short loc_180018450
0x180018481  lea     rdi, [rbx+0Ch]
0x180018485  mov     esi, r13d
0x180018488  mov     rax, rdi
0x18001848b  cmp     [rdi], r13w
0x18001848f  jz      short loc_1800184A7
0x180018491  add     rax, 2
0x180018495  cmp     [rax], r13w
0x180018499  jnz     short loc_180018491
0x18001849b  add     rax, 2
0x18001849f  inc     esi
0x1800184a1  cmp     [rax], r13w
0x1800184a5  jnz     short loc_180018491
0x1800184a7  mov     rcx, gs:60h
0x1800184b0  xor     edx, edx; Flags
0x1800184b2  mov     r8d, esi
0x1800184b5  shl     r8, 4; Size
0x1800184b9  mov     rcx, [rcx+30h]; HeapHandle
0x1800184bd  call    cs:__imp_RtlAllocateHeap
0x1800184c3  mov     rbp, rax
0x1800184c6  test    rax, rax
0x1800184c9  jz      short loc_180018450
0x1800184cb  mov     r14d, r13d
0x1800184ce  cmp     [rdi], r13w
0x1800184d2  jz      short loc_18001851B
0x1800184d4  mov     ecx, r14d
0x1800184d7  mov     rdx, rdi; SourceString
0x1800184da  shl     rcx, 4
0x1800184de  add     rcx, rbp; DestinationString
0x1800184e1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800184e7  test    eax, eax
0x1800184e9  jns     short loc_18001850C
0x1800184eb  mov     rcx, gs:60h
0x1800184f4  mov     r8, rbp; P
0x1800184f7  xor     edx, edx; Flags
0x1800184f9  mov     rcx, [rcx+30h]; HeapHandle
0x1800184fd  call    cs:__imp_RtlFreeHeap
0x180018503  jmp     loc_180018450
0x180018508  add     rdi, 2
0x18001850c  cmp     [rdi], r13w
0x180018510  jnz     short loc_180018508
0x180018512  inc     r14d
0x180018515  add     rdi, 2
0x180018519  jmp     short loc_1800184CE
0x18001851b  mov     rax, [rsp+88h+arg_20]
0x180018523  mov     [rax], esi
0x180018525  mov     [r15], rbx
0x180018528  mov     [r12], rbp
0x18001852c  jmp     loc_1800183F2
```
