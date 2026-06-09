# CPath::Copy(ushort const *)

- ea: `0x1800083f0`
- end: `0x1800084d7`
- name: `?Copy@CPath@@QEAAJPEBG@Z`
- size: `231`
- prototype: `__int64 __fastcall(CPath *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800020a0`
- `0x18000df30`
- `0x18001057c`
- `0x180012638`
- `0x180025ee8`

## callees

- `0x1800083f0`
- `0x1800102a8`
- `0x18002ac30`

## import_xrefs

- `ntdll!RtlpEnsureBufferSize` at `0x180008449`
- `ntdll!RtlpEnsureBufferSize` at `0x180008449`
- `ntdll!RtlInitUnicodeString` at `0x18000840a`
- `ntdll!RtlInitUnicodeString` at `0x18000840a`

## pseudocode

```c
__int64 __fastcall CPath::Copy(CPath *this, const unsigned __int16 *a2)
{
  __int64 Length; // rdx
  SIZE_T v4; // r8
  int v5; // ecx
  __int64 *v6; // rsi
  __int64 result; // rax
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Length = DestinationString.Length;
  *((_WORD *)this + 260) = 0;
  v4 = Length + 2;
  if ( (unsigned __int64)(Length + 2) > 0xFFFE )
  {
    v5 = -1073741562;
    return ResultFromNtStatus(v5);
  }
  v6 = (__int64 *)((char *)this + 536);
  if ( this == (CPath *)-536LL || v4 > *((_QWORD *)this + 69) )
  {
    if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)this + 536), v4) < 0 )
    {
      v5 = -1073741801;
      return ResultFromNtStatus(v5);
    }
    LOWORD(Length) = DestinationString.Length;
  }
  v8 = *v6;
  v9 = (unsigned __int64)*((unsigned __int16 *)this + 260) >> 1;
  *((_QWORD *)this + 66) = *v6;
  memmove_0((void *)(v8 + 2 * v9), DestinationString.Buffer, (unsigned __int16)Length);
  result = 0;
  v10 = *((_QWORD *)this + 66);
  v11 = (unsigned __int16)(*((_WORD *)this + 260) + DestinationString.Length);
  *((_WORD *)this + 260) = v11;
  *((_WORD *)this + 261) = v11 + 2;
  *(_WORD *)(v10 + 2 * (v11 >> 1)) = 0;
  return result;
}

```

## disassembly

```asm
0x1800083f0  mov     [rsp+arg_8], rbx
0x1800083f5  push    rsi
0x1800083f6  sub     rsp, 30h
0x1800083fa  mov     rbx, rcx
0x1800083fd  xorps   xmm0, xmm0
0x180008400  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x180008405  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x18000840a  call    cs:__imp_RtlInitUnicodeString
0x180008410  movzx   edx, [rsp+38h+DestinationString.Length]
0x180008415  xor     eax, eax
0x180008417  mov     [rbx+208h], ax
0x18000841e  lea     r8, [rdx+2]; RequiredSize
0x180008422  cmp     r8, 0FFFEh
0x180008429  jbe     short loc_180008432
0x18000842b  mov     ecx, 0C0000106h
0x180008430  jmp     short loc_180008458
0x180008432  lea     rsi, [rbx+218h]
0x180008439  test    rsi, rsi
0x18000843c  jz      short loc_180008444
0x18000843e  cmp     r8, [rsi+10h]
0x180008442  jbe     short loc_180008464
0x180008444  mov     rdx, rsi; Buffer
0x180008447  xor     ecx, ecx; Flags
0x180008449  call    cs:__imp_RtlpEnsureBufferSize
0x18000844f  test    eax, eax
0x180008451  jns     short loc_18000845F
0x180008453  mov     ecx, 0C0000017h; int
0x180008458  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000845d  jmp     short loc_1800084CC
0x18000845f  movzx   edx, [rsp+38h+DestinationString.Length]
0x180008464  mov     rcx, [rsi]
0x180008467  movzx   eax, word ptr [rbx+208h]
0x18000846e  shr     rax, 1
0x180008471  mov     [rbx+210h], rcx
0x180008478  movzx   r8d, dx; Size
0x18000847c  mov     rdx, [rsp+38h+DestinationString.Buffer]; Src
0x180008481  lea     rcx, [rcx+rax*2]; void *
0x180008485  mov     [rsp+38h+arg_0], rdi
0x18000848a  xor     edi, edi
0x18000848c  call    memmove_0
0x180008491  movzx   ecx, [rsp+38h+DestinationString.Length]
0x180008496  mov     eax, edi
0x180008498  add     cx, [rbx+208h]
0x18000849f  mov     rdx, [rbx+210h]
0x1800084a6  mov     rdi, [rsp+38h+arg_0]
0x1800084ab  movzx   r8d, cx
0x1800084af  mov     [rbx+208h], r8w
0x1800084b7  lea     ecx, [r8+2]
0x1800084bb  shr     r8, 1
0x1800084be  mov     [rbx+20Ah], cx
0x1800084c5  xor     ecx, ecx
0x1800084c7  mov     [rdx+r8*2], cx
0x1800084cc  mov     rbx, [rsp+38h+arg_8]
0x1800084d1  add     rsp, 30h
0x1800084d5  pop     rsi
0x1800084d6  retn
```
