# SipFile::OpenCommon(ushort const *)

- ea: `0x180004918`
- end: `0x1800049b2`
- name: `?OpenCommon@SipFile@@AEAAKPEBG@Z`
- size: `154`
- prototype: `unsigned int(SipFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004834`

## callees

- `0x180001014`
- `0x180002ce0`
- `0x180004918`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall SipFile::OpenCommon(SipFile *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  _WORD *v6; // rax

  if ( !a2 )
    return 87;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  *((_DWORD *)this + 12) = v5;
  v6 = operator new(saturated_mul((unsigned int)(v5 + 1), 2u));
  *((_QWORD *)this + 5) = v6;
  if ( !v6 )
    return 8;
  v6[*((unsigned int *)this + 12)] = 0;
  result = StringCchCopyNW(
             *((unsigned __int16 **)this + 5),
             (unsigned int)(*((_DWORD *)this + 12) + 1),
             a2,
             *((unsigned int *)this + 12));
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(SipFile *))(*(_QWORD *)this + 56LL))(this);
  return result;
}

```

## disassembly

```asm
0x180004918  mov     [rsp+arg_0], rbx
0x18000491d  mov     [rsp+arg_8], rsi
0x180004922  push    rdi
0x180004923  sub     rsp, 20h
0x180004927  xor     esi, esi
0x180004929  mov     rdi, rdx
0x18000492c  mov     rbx, rcx
0x18000492f  test    rdx, rdx
0x180004932  jnz     short loc_180004939
0x180004934  lea     eax, [rdx+57h]
0x180004937  jmp     short loc_1800049A2
0x180004939  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000493d  mov     rax, r8
0x180004940  inc     rax
0x180004943  cmp     [rdx+rax*2], si
0x180004947  jnz     short loc_180004940
0x180004949  mov     [rcx+30h], eax
0x18000494c  lea     ecx, [rax+1]
0x18000494f  mov     eax, 2
0x180004954  mul     rcx
0x180004957  cmovb   rax, r8
0x18000495b  mov     rcx, rax; Size
0x18000495e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004963  mov     [rbx+28h], rax
0x180004967  test    rax, rax
0x18000496a  jnz     short loc_180004973
0x18000496c  mov     eax, 8
0x180004971  jmp     short loc_1800049A2
0x180004973  mov     ecx, [rbx+30h]
0x180004976  mov     r8, rdi; unsigned __int16 *
0x180004979  mov     [rax+rcx*2], si
0x18000497d  mov     eax, [rbx+30h]
0x180004980  mov     rcx, [rbx+28h]; unsigned __int16 *
0x180004984  mov     r9d, eax; unsigned __int64
0x180004987  lea     edx, [rax+1]; unsigned __int64
0x18000498a  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000498f  test    eax, eax
0x180004991  js      short loc_1800049A2
0x180004993  mov     rax, [rbx]
0x180004996  mov     rcx, rbx
0x180004999  mov     rax, [rax+38h]
0x18000499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049a2  mov     rbx, [rsp+28h+arg_0]
0x1800049a7  mov     rsi, [rsp+28h+arg_8]
0x1800049ac  add     rsp, 20h
0x1800049b0  pop     rdi
0x1800049b1  retn
```
