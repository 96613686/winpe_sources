# NpFindPrefix

- ea: `0x140012730`
- end: `0x1400127e8`
- name: `NpFindPrefix`
- size: `184`
- prototype: `PUNICODE_PREFIX_TABLE_ENTRY __fastcall(struct _UNICODE_PREFIX_TABLE *, __m128i *, char, __int64)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b354`
- `0x14000bf50`
- `0x14000c3b4`
- `0x14000f610`
- `0x140011490`
- `0x140011aa0`
- `0x1400131e0`
- `0x1400137d4`

## callees

- `0x140012730`

## import_xrefs

- `ntoskrnl!RtlFindUnicodePrefix` at `0x140012797`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x140012797`

## pseudocode

```c
PUNICODE_PREFIX_TABLE_ENTRY __fastcall NpFindPrefix(struct _UNICODE_PREFIX_TABLE *a1, __m128i *a2, char a3, __int64 a4)
{
  UNICODE_STRING v4; // xmm0
  USHORT v6; // dx
  ULONG v7; // r8d
  PUNICODE_PREFIX_TABLE_ENTRY result; // rax
  unsigned __int64 RightChild_low; // rdx
  __int16 v10; // cx
  UNICODE_STRING FullName; // [rsp+20h] [rbp-18h] BYREF

  v4 = (UNICODE_STRING)*a2;
  v6 = _mm_cvtsi128_si32(*a2);
  FullName = v4;
  if ( v6 >= 2u && *FullName.Buffer == 92 )
  {
    FullName.MaximumLength -= 2;
    v6 -= 2;
    FullName.Length = v6;
    ++FullName.Buffer;
  }
  if ( a3 )
    v7 = 0;
  else
    v7 = v6;
  result = RtlFindUnicodePrefix(a1 + 9, &FullName, v7);
  if ( result )
  {
    RightChild_low = LOWORD(result[-1].Links.RightChild);
    result = (PUNICODE_PREFIX_TABLE_ENTRY)((char *)result - 176);
    v10 = FullName.Length - RightChild_low;
    *(_WORD *)a4 = FullName.Length - RightChild_low;
    *(_WORD *)(a4 + 2) = v10;
    *(_QWORD *)(a4 + 8) = &FullName.Buffer[RightChild_low >> 1];
  }
  else
  {
    *(UNICODE_STRING *)a4 = FullName;
  }
  return result;
}

```

## disassembly

```asm
0x140012730  push    rbx
0x140012732  sub     rsp, 30h
0x140012736  movups  xmm0, xmmword ptr [rdx]
0x140012739  mov     rbx, r9
0x14001273c  movd    edx, xmm0
0x140012740  movups  xmmword ptr [rsp+38h+FullName.Length], xmm0
0x140012745  cmp     dx, 2
0x140012749  jb      short loc_140012783
0x14001274b  mov     r9, [rsp+38h+FullName.Buffer]
0x140012750  mov     eax, 5Ch ; '\'
0x140012755  cmp     ax, [r9]
0x140012759  jnz     short loc_140012783
0x14001275b  mov     rax, qword ptr [rsp+38h+FullName.Length]
0x140012760  shr     rax, 10h
0x140012764  sub     ax, 2
0x140012768  mov     [rsp+38h+FullName.MaximumLength], ax
0x14001276d  mov     eax, 0FFFEh
0x140012772  add     dx, ax
0x140012775  add     r9, 2
0x140012779  mov     [rsp+38h+FullName.Length], dx
0x14001277e  mov     [rsp+38h+FullName.Buffer], r9
0x140012783  test    r8b, r8b
0x140012786  jz      short loc_1400127E2
0x140012788  xor     r8d, r8d; CaseInsensitiveIndex
0x14001278b  add     rcx, 0D8h; PrefixTable
0x140012792  lea     rdx, [rsp+38h+FullName]; FullName
0x140012797  call    cs:__imp_RtlFindUnicodePrefix
0x14001279e  nop     dword ptr [rax+rax+00h]
0x1400127a3  test    rax, rax
0x1400127a6  jnz     short loc_1400127B7
0x1400127a8  movups  xmm0, xmmword ptr [rsp+38h+FullName.Length]
0x1400127ad  movups  xmmword ptr [rbx], xmm0
0x1400127b0  add     rsp, 30h
0x1400127b4  pop     rbx
0x1400127b5  retn
0x1400127b7  movzx   edx, word ptr [rax-10h]
0x1400127bb  add     rax, 0FFFFFFFFFFFFFF50h
0x1400127c1  movzx   ecx, [rsp+38h+FullName.Length]
0x1400127c6  sub     cx, dx
0x1400127c9  mov     [rbx], cx
0x1400127cc  mov     [rbx+2], cx
0x1400127d0  mov     rcx, [rsp+38h+FullName.Buffer]
0x1400127d5  shr     rdx, 1
0x1400127d8  lea     rdx, [rcx+rdx*2]
0x1400127dc  mov     [rbx+8], rdx
0x1400127e0  jmp     short loc_1400127B0
0x1400127e2  movzx   r8d, dx
0x1400127e6  jmp     short loc_14001278B
```
