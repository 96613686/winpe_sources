# RegpCopyUnicodeString

- ea: `0x140034874`
- end: `0x1400349df`
- name: `RegpCopyUnicodeString`
- size: `363`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400397e4`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140034874`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140034985`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140034985`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003490e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003490e`

## pseudocode

```c
__int64 __fastcall RegpCopyUnicodeString(PCUNICODE_STRING SourceString, struct _UNICODE_STRING **a2)
{
  struct _UNICODE_STRING *v4; // rdi
  signed int v5; // esi
  unsigned int v6; // r14d
  struct _UNICODE_STRING *PoolWithTag; // rax
  unsigned int v8; // r14d
  USHORT v9; // ax

  v4 = 0;
  if ( a2 )
  {
    if ( SourceString )
      v6 = SourceString->MaximumLength + 16;
    else
      v6 = 18;
    if ( qword_140020008 )
      PoolWithTag = (struct _UNICODE_STRING *)qword_140020008(256, v6, 1953719123);
    else
      PoolWithTag = (struct _UNICODE_STRING *)ExAllocatePoolWithTag(PagedPool, v6, 0x74736353u);
    v4 = PoolWithTag;
    if ( PoolWithTag )
    {
      if ( v6 < 0x10 )
      {
        v8 = -1;
        v5 = -1073741675;
      }
      else
      {
        v8 = v6 - 16;
        v5 = 0;
      }
      if ( v5 >= 0 )
      {
        v9 = v8 > 0xFFFF ? -1 : v8;
        v4->MaximumLength = v9;
        v5 = v8 > 0xFFFF ? 0xC0000095 : 0;
        if ( v8 <= 0xFFFF )
        {
          v4->Buffer = &v4[1].Length;
          if ( SourceString )
          {
            RtlCopyUnicodeString(v4, SourceString);
          }
          else
          {
            v4->Length = 2;
            v4[1].Length = 0;
          }
          *a2 = v4;
          v4 = 0;
          v5 = 0;
        }
      }
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    v5 = -1073741811;
  }
  if ( v4 )
    SecFreePool(v4, 0x74736353u);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140034874  mov     rax, rsp
0x140034877  mov     [rax+20h], rbx
0x14003487b  mov     [rax+10h], rdx
0x14003487f  mov     [rax+8], rcx
0x140034883  push    rsi
0x140034884  push    rdi
0x140034885  push    r12
0x140034887  push    r14
0x140034889  push    r15
0x14003488b  sub     rsp, 30h
0x14003488f  mov     r12, rdx
0x140034892  mov     r15, rcx
0x140034895  xor     ebx, ebx
0x140034897  mov     edi, ebx
0x140034899  mov     [rax-38h], ebx
0x14003489c  mov     esi, ebx
0x14003489e  test    rdx, rdx
0x1400348a1  jnz     short loc_1400348AD
0x1400348a3  mov     esi, 0C000000Dh
0x1400348a8  jmp     loc_1400349B8
0x1400348ad  test    rcx, rcx
0x1400348b0  jz      short loc_1400348BD
0x1400348b2  movzx   r14d, word ptr [rcx+2]
0x1400348b7  add     r14d, 10h
0x1400348bb  jmp     short loc_1400348C3
0x1400348bd  mov     r14d, 12h
0x1400348c3  mov     [rsp+58h+var_38], r14d
0x1400348c8  jmp     short loc_1400348DF
0x1400348ca  mov     esi, eax
0x1400348cc  xor     ebx, ebx
0x1400348ce  mov     r12, [rsp+58h+arg_8]
0x1400348d3  mov     r15, [rsp+58h+arg_0]
0x1400348d8  mov     edi, ebx
0x1400348da  mov     r14d, [rsp+58h+var_38]
0x1400348df  test    esi, esi
0x1400348e1  js      loc_1400349B8
0x1400348e7  mov     edx, r14d; NumberOfBytes
0x1400348ea  mov     rax, cs:qword_140020008
0x1400348f1  mov     r8d, 74736353h; Tag
0x1400348f7  test    rax, rax
0x1400348fa  jz      short loc_140034909
0x1400348fc  mov     ecx, 100h
0x140034901  call    cs:__guard_dispatch_icall_fptr
0x140034907  jmp     short loc_14003491A
0x140034909  mov     ecx, 1; PoolType
0x14003490e  call    cs:__imp_ExAllocatePoolWithTag
0x140034915  nop     dword ptr [rax+rax+00h]
0x14003491a  mov     rdi, rax
0x14003491d  mov     [rsp+58h+arg_10], rax
0x140034922  test    rax, rax
0x140034925  jnz     short loc_140034931
0x140034927  mov     esi, 0C000009Ah
0x14003492c  jmp     loc_1400349B8
0x140034931  cmp     r14d, 10h
0x140034935  jb      short loc_14003493F
0x140034937  add     r14d, 0FFFFFFF0h
0x14003493b  mov     esi, ebx
0x14003493d  jmp     short loc_140034948
0x14003493f  or      r14d, 0FFFFFFFFh
0x140034943  mov     esi, 0C0000095h
0x140034948  test    esi, esi
0x14003494a  js      short loc_1400349B8
0x14003494c  mov     ecx, 0FFFFh
0x140034951  cmp     r14d, ecx
0x140034954  ja      short loc_14003495C
0x140034956  movzx   eax, r14w
0x14003495a  jmp     short loc_14003495E
0x14003495c  mov     eax, ecx
0x14003495e  mov     [rdi+2], ax
0x140034962  cmp     ecx, r14d
0x140034965  sbb     esi, esi
0x140034967  and     esi, 0C0000095h
0x14003496d  cmp     r14d, ecx
0x140034970  ja      short loc_1400349B8
0x140034972  lea     rax, [rdi+10h]
0x140034976  mov     [rdi+8], rax
0x14003497a  test    r15, r15
0x14003497d  jz      short loc_1400349A7
0x14003497f  mov     rdx, r15; SourceString
0x140034982  mov     rcx, rdi; DestinationString
0x140034985  call    cs:__imp_RtlCopyUnicodeString
0x14003498c  nop     dword ptr [rax+rax+00h]
0x140034991  jmp     short loc_1400349A1
0x140034993  mov     esi, eax
0x140034995  xor     ebx, ebx
0x140034997  mov     r12, [rsp+58h+arg_8]
0x14003499c  mov     rdi, [rsp+58h+arg_10]
0x1400349a1  test    esi, esi
0x1400349a3  js      short loc_1400349B8
0x1400349a5  jmp     short loc_1400349AF
0x1400349a7  mov     word ptr [rdi], 2
0x1400349ac  mov     [rax], bx
0x1400349af  mov     [r12], rdi
0x1400349b3  mov     rdi, rbx
0x1400349b6  mov     esi, ebx
0x1400349b8  test    rdi, rdi
0x1400349bb  jz      short loc_1400349CA
0x1400349bd  mov     edx, 74736353h; Tag
0x1400349c2  mov     rcx, rdi; P
0x1400349c5  call    SecFreePool
0x1400349ca  mov     eax, esi
0x1400349cc  mov     rbx, [rsp+58h+arg_18]
0x1400349d1  add     rsp, 30h
0x1400349d5  pop     r15
0x1400349d7  pop     r14
0x1400349d9  pop     r12
0x1400349db  pop     rdi
0x1400349dc  pop     rsi
0x1400349dd  retn
```
