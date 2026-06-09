# RtlNameValueArray::Free(void)

- ea: `0x1400085f4`
- end: `0x1400086a5`
- name: `?Free@RtlNameValueArray@@QEAAXXZ`
- size: `177`
- prototype: `void __fastcall(RtlNameValueArray *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140005b3c`
- `0x140006460`

## callees

- `0x14000233f`
- `0x1400085f4`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x140008638`
- `ntdll!RtlFreeHeap` at `0x140008686`
- `ntdll!RtlFreeHeap` at `0x140008638`
- `ntdll!RtlFreeHeap` at `0x140008686`

## pseudocode

```c
void __fastcall RtlNameValueArray::Free(RtlNameValueArray *this)
{
  unsigned __int64 v2; // rcx
  unsigned __int64 i; // rdi
  PVOID *v4; // rax
  unsigned __int128 v5; // rax
  void *v6; // r8

  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    for ( i = 0; i < v2; ++i )
    {
      v4 = 0;
      if ( i < v2 )
      {
        if ( !is_mul_ok(*((_QWORD *)this + 1), i)
          || (v4 = (PVOID *)(*((_QWORD *)this + 5) + *((_QWORD *)this + 1) * i),
              (unsigned __int64)v4 < *((_QWORD *)this + 5)) )
        {
          v4 = 0;
        }
      }
      if ( *v4 )
        RtlFreeHeap(*(HANDLE *)this, 0, *v4);
      v2 = *((_QWORD *)this + 2);
    }
    if ( v2 && is_mul_ok(v2, *((_QWORD *)this + 1)) )
    {
      v5 = v2 * (unsigned __int128)*((unsigned __int64 *)this + 1);
      memset_0(*((void **)this + 5), SDWORD2(v5), v5);
      *((_QWORD *)this + 2) = 0;
    }
  }
  v6 = (void *)*((_QWORD *)this + 5);
  if ( v6 )
    RtlFreeHeap(*(HANDLE *)this, 0, v6);
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x1400085f4  mov     [rsp+arg_8], rbx
0x1400085f9  push    rdi
0x1400085fa  sub     rsp, 20h
0x1400085fe  mov     rbx, rcx
0x140008601  mov     rcx, [rcx+10h]
0x140008605  test    rcx, rcx
0x140008608  jz      short loc_140008678
0x14000860a  xor     edi, edi
0x14000860c  xor     eax, eax
0x14000860e  cmp     rdi, rcx
0x140008611  jnb     short loc_14000862B
0x140008613  mov     rax, rdi
0x140008616  mul     qword ptr [rbx+8]
0x14000861a  test    rdx, rdx
0x14000861d  jnz     short loc_140008629
0x14000861f  add     rax, [rbx+28h]
0x140008623  cmp     rax, [rbx+28h]
0x140008627  jnb     short loc_14000862B
0x140008629  xor     eax, eax
0x14000862b  mov     r8, [rax]; P
0x14000862e  test    r8, r8
0x140008631  jz      short loc_14000863E
0x140008633  mov     rcx, [rbx]; HeapHandle
0x140008636  xor     edx, edx; Flags
0x140008638  call    cs:__imp_RtlFreeHeap
0x14000863e  mov     rcx, [rbx+10h]
0x140008642  inc     rdi
0x140008645  cmp     rdi, rcx
0x140008648  jb      short loc_14000860C
0x14000864a  test    rcx, rcx
0x14000864d  jz      short loc_140008678
0x14000864f  mov     rax, [rbx+8]
0x140008653  mul     rcx
0x140008656  mov     [rsp+28h+arg_0], 0
0x14000865f  test    rdx, rdx
0x140008662  jnz     short loc_140008678
0x140008664  mov     rcx, [rbx+28h]; void *
0x140008668  mov     r8, rax; Size
0x14000866b  call    memset_0
0x140008670  mov     qword ptr [rbx+10h], 0
0x140008678  mov     r8, [rbx+28h]; P
0x14000867c  test    r8, r8
0x14000867f  jz      short loc_14000868C
0x140008681  mov     rcx, [rbx]; HeapHandle
0x140008684  xor     edx, edx; Flags
0x140008686  call    cs:__imp_RtlFreeHeap
0x14000868c  xorps   xmm0, xmm0
0x14000868f  movups  xmmword ptr [rbx], xmm0
0x140008692  movups  xmmword ptr [rbx+10h], xmm0
0x140008696  movups  xmmword ptr [rbx+20h], xmm0
0x14000869a  mov     rbx, [rsp+28h+arg_8]
0x14000869f  add     rsp, 20h
0x1400086a3  pop     rdi
0x1400086a4  retn
```
