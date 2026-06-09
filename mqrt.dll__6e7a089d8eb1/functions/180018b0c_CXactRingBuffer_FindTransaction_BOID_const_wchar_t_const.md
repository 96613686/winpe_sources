# CXactRingBuffer::FindTransaction(BOID const &,wchar_t * const)

- ea: `0x180018b0c`
- end: `0x180018bd0`
- name: `?FindTransaction@CXactRingBuffer@@QEAAHAEBUBOID@@QEA_W@Z`
- size: `196`
- prototype: `int(CXactRingBuffer *__hidden this, const struct BOID *, wchar_t *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018f4c`

## callees

- `0x180013bbc`
- `0x180018b0c`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x180018b6e`
- `ntdll!RtlCompareMemory` at `0x180018b6e`
- `KERNEL32!LeaveCriticalSection` at `0x180018ba3`
- `KERNEL32!LeaveCriticalSection` at `0x180018bb4`
- `KERNEL32!LeaveCriticalSection` at `0x180018ba3`
- `KERNEL32!LeaveCriticalSection` at `0x180018bb4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CXactRingBuffer::FindTransaction(CXactRingBuffer *this, const struct BOID *a2, wchar_t *const a3)
{
  int i; // ebx
  __int64 *v6; // rdi
  __int64 v7; // rax
  char *v8; // r8
  int v9; // edx
  int v10; // ecx

  CCriticalSection::Lock((CCriticalSection *)&stru_18003D448);
  for ( i = 0; i < 16; ++i )
  {
    v6 = &g_xactRingBuffer[3 * i];
    if ( v6[2] && a3 && RtlCompareMemory(a2, &g_xactRingBuffer[3 * i], 0x10u) == 16 )
    {
      v7 = v6[2];
      v8 = (char *)a3 - v7;
      do
      {
        v9 = *(unsigned __int16 *)&v8[v7];
        v10 = *(unsigned __int16 *)v7 - v9;
        if ( v10 )
          break;
        v7 += 2;
      }
      while ( v9 );
      if ( !v10 )
      {
        LeaveCriticalSection(&stru_18003D448);
        return 1;
      }
    }
  }
  LeaveCriticalSection(&stru_18003D448);
  return 0;
}

```

## disassembly

```asm
0x180018b0c  mov     rax, rsp
0x180018b0f  mov     [rax+10h], rbx
0x180018b13  mov     [rax+18h], rbp
0x180018b17  mov     [rax+8], rcx
0x180018b1b  push    rsi
0x180018b1c  push    rdi
0x180018b1d  push    r14
0x180018b1f  sub     rsp, 20h
0x180018b23  mov     rsi, r8
0x180018b26  mov     rbp, rdx
0x180018b29  lea     r14, stru_18003D448
0x180018b30  mov     [rax+8], r14
0x180018b34  mov     rcx, r14; this
0x180018b37  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x180018b3c  nop
0x180018b3d  xor     ebx, ebx
0x180018b3f  cmp     ebx, 10h
0x180018b42  jge     short loc_180018BB1
0x180018b44  movsxd  rax, ebx
0x180018b47  lea     rcx, [rax+rax*2]
0x180018b4b  lea     rax, ?g_xactRingBuffer@@3VCXactRingBuffer@@A; CXactRingBuffer g_xactRingBuffer
0x180018b52  lea     rdi, [rax+rcx*8]
0x180018b56  cmp     qword ptr [rdi+10h], 0
0x180018b5b  jz      short loc_180018B9C
0x180018b5d  test    rsi, rsi
0x180018b60  jz      short loc_180018B9C
0x180018b62  mov     r8d, 10h; Length
0x180018b68  mov     rdx, rdi; Source2
0x180018b6b  mov     rcx, rbp; Source1
0x180018b6e  call    cs:__imp_RtlCompareMemory
0x180018b74  cmp     rax, 10h
0x180018b78  jnz     short loc_180018B9C
0x180018b7a  mov     rax, [rdi+10h]
0x180018b7e  mov     r8, rsi
0x180018b81  sub     r8, rax
0x180018b84  movzx   ecx, word ptr [rax]
0x180018b87  movzx   edx, word ptr [rax+r8]
0x180018b8c  sub     ecx, edx
0x180018b8e  jnz     short loc_180018B98
0x180018b90  add     rax, 2
0x180018b94  test    edx, edx
0x180018b96  jnz     short loc_180018B84
0x180018b98  test    ecx, ecx
0x180018b9a  jz      short loc_180018BA0
0x180018b9c  inc     ebx
0x180018b9e  jmp     short loc_180018B3F
0x180018ba0  mov     rcx, r14; lpCriticalSection
0x180018ba3  call    cs:__imp_LeaveCriticalSection
0x180018ba9  nop
0x180018baa  mov     eax, 1
0x180018baf  jmp     short loc_180018BBD
0x180018bb1  mov     rcx, r14; lpCriticalSection
0x180018bb4  call    cs:__imp_LeaveCriticalSection
0x180018bba  nop
0x180018bbb  xor     eax, eax
0x180018bbd  mov     rbx, [rsp+38h+arg_8]
0x180018bc2  mov     rbp, [rsp+38h+arg_10]
0x180018bc7  add     rsp, 20h
0x180018bcb  pop     r14
0x180018bcd  pop     rdi
0x180018bce  pop     rsi
0x180018bcf  retn
```
