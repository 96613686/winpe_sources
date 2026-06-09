# TokenListToGuidArray(ushort *,ushort,_GUID * *,uint *)

- ea: `0x1800329a0`
- end: `0x180032a96`
- name: `?TokenListToGuidArray@@YAJPEAGGPEAPEAU_GUID@@PEAI@Z`
- size: `246`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16, struct _GUID **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180032b34`

## callees

- `0x1800026d0`
- `0x1800026dc`
- `0x1800026f4`
- `0x1800329a0`
- `0x180032a9c`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180032a26`
- `ntdll!RtlInitUnicodeString` at `0x180032a26`
- `ntdll!RtlGUIDFromString` at `0x180032a3f`
- `ntdll!RtlGUIDFromString` at `0x180032a3f`

## pseudocode

```c
__int64 __fastcall TokenListToGuidArray(unsigned __int16 *a1, __int64 a2, struct _GUID **a3, unsigned int *a4)
{
  NTSTATUS v7; // edi
  size_t v8; // r14
  struct _GUID *v9; // rax
  wchar_t *i; // rcx
  wchar_t *v11; // rax
  wchar_t Delimiter; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-18h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+38h] BYREF
  wchar_t *Context; // [rsp+80h] [rbp+40h] BYREF

  *a3 = 0;
  *a4 = 0;
  Context = 0;
  v15 = 0;
  Delimiter = 59;
  DestinationString = 0;
  v7 = ValidateTokenArray(a1, 0x3Bu, 0x26u, &v15);
  if ( v7 >= 0 && (v8 = 16LL * v15, v9 = (struct _GUID *)o_malloc_0(v8), (*a3 = v9) != 0) )
  {
    for ( i = a1; ; i = 0 )
    {
      v11 = o_wcstok_s_0(i, &Delimiter, &Context);
      if ( !v11 )
        break;
      if ( 16 * (unsigned __int64)(*a4 + 1) > v8 )
        goto LABEL_9;
      RtlInitUnicodeString(&DestinationString, v11);
      v7 = RtlGUIDFromString(&DestinationString, &(*a3)[*a4]);
      if ( v7 < 0 )
        goto LABEL_9;
      ++*a4;
    }
  }
  else
  {
LABEL_9:
    v7 = -1073741823;
    if ( *a3 )
    {
      free(*a3);
      *a3 = 0;
    }
    *a4 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800329a0  mov     [rsp-28h+arg_0], rbx
0x1800329a5  mov     word ptr [rsp-28h+arg_8], dx
0x1800329aa  push    rbp
0x1800329ab  push    rsi
0x1800329ac  push    rdi
0x1800329ad  push    r14
0x1800329af  push    r15
0x1800329b1  mov     rbp, rsp
0x1800329b4  sub     rsp, 40h
0x1800329b8  and     qword ptr [r8], 0
0x1800329bc  mov     edx, 3Bh ; ';'; unsigned __int16
0x1800329c1  and     dword ptr [r9], 0
0x1800329c5  mov     rbx, r9
0x1800329c8  and     [rbp+Context], 0
0x1800329cd  lea     r9, [rbp+arg_8]; unsigned int *
0x1800329d1  and     [rbp+arg_8], 0
0x1800329d5  mov     rsi, r8
0x1800329d8  xorps   xmm0, xmm0
0x1800329db  mov     [rbp+Delimiter], dx
0x1800329df  lea     r8d, [rdx-15h]; unsigned int
0x1800329e3  mov     r15, rcx
0x1800329e6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800329ea  call    ?ValidateTokenArray@@YAJPEAGGIPEAI@Z; ValidateTokenArray(ushort *,ushort,uint,uint *)
0x1800329ef  mov     edi, eax
0x1800329f1  test    eax, eax
0x1800329f3  js      short loc_180032A69
0x1800329f5  mov     r14d, [rbp+arg_8]
0x1800329f9  shl     r14, 4
0x1800329fd  mov     rcx, r14; Size
0x180032a00  call    _o_malloc_0
0x180032a05  mov     [rsi], rax
0x180032a08  test    rax, rax
0x180032a0b  jz      short loc_180032A69
0x180032a0d  mov     rcx, r15
0x180032a10  jmp     short loc_180032A55
0x180032a12  mov     edx, [rbx]
0x180032a14  inc     edx
0x180032a16  shl     rdx, 4
0x180032a1a  cmp     rdx, r14
0x180032a1d  ja      short loc_180032A69
0x180032a1f  mov     rdx, rax; SourceString
0x180032a22  lea     rcx, [rbp+DestinationString]; DestinationString
0x180032a26  call    cs:__imp_RtlInitUnicodeString
0x180032a2d  nop     dword ptr [rax+rax+00h]
0x180032a32  mov     edx, [rbx]
0x180032a34  lea     rcx, [rbp+DestinationString]; GuidString
0x180032a38  shl     rdx, 4
0x180032a3c  add     rdx, [rsi]; Guid
0x180032a3f  call    cs:__imp_RtlGUIDFromString
0x180032a46  nop     dword ptr [rax+rax+00h]
0x180032a4b  mov     edi, eax
0x180032a4d  test    eax, eax
0x180032a4f  js      short loc_180032A69
0x180032a51  inc     dword ptr [rbx]
0x180032a53  xor     ecx, ecx; String
0x180032a55  lea     r8, [rbp+Context]; Context
0x180032a59  lea     rdx, [rbp+Delimiter]; Delimiter
0x180032a5d  call    _o_wcstok_s_0
0x180032a62  test    rax, rax
0x180032a65  jnz     short loc_180032A12
0x180032a67  jmp     short loc_180032A82
0x180032a69  mov     rcx, [rsi]; Block
0x180032a6c  mov     edi, 0C0000001h
0x180032a71  test    rcx, rcx
0x180032a74  jz      short loc_180032A7F
0x180032a76  call    free
0x180032a7b  and     qword ptr [rsi], 0
0x180032a7f  and     dword ptr [rbx], 0
0x180032a82  mov     rbx, [rsp+40h+arg_0]
0x180032a87  mov     eax, edi
0x180032a89  add     rsp, 40h
0x180032a8d  pop     r15
0x180032a8f  pop     r14
0x180032a91  pop     rdi
0x180032a92  pop     rsi
0x180032a93  pop     rbp
0x180032a94  retn
```
