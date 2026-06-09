# MupiAddKnownProvider

- ea: `0x1400128e0`
- end: `0x140012974`
- name: `MupiAddKnownProvider`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f2a0`
- `0x140012700`

## callees

- `0x140003564`
- `0x1400128e0`
- `0x14001297c`
- `0x1400129cc`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14001290c`
- `ntoskrnl!RtlComputeCrc32` at `0x14001290c`

## pseudocode

```c
char *__fastcall MupiAddKnownProvider(unsigned __int16 *a1, const UNICODE_STRING *a2, const UNICODE_STRING *a3, int a4)
{
  char v4; // si
  char *v6; // rbx

  v4 = a4;
  v6 = MupiAllocProvider((PCUNICODE_STRING)a1, a2, a3, a4);
  if ( v6 )
  {
    *((_DWORD *)v6 + 14) = RtlComputeCrc32(0, *((PUCHAR *)a1 + 1), *a1);
    MupiAddProviderToList(v6);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_ZDq(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      (unsigned int)WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids,
      (_DWORD)a1,
      v4,
      (char)v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1400128e0  mov     [rsp+arg_0], rbx
0x1400128e5  mov     [rsp+arg_8], rsi
0x1400128ea  push    rdi
0x1400128eb  sub     rsp, 30h
0x1400128ef  mov     esi, r9d
0x1400128f2  mov     rdi, rcx
0x1400128f5  call    MupiAllocProvider
0x1400128fa  mov     rbx, rax
0x1400128fd  test    rax, rax
0x140012900  jz      short loc_140012923
0x140012902  movzx   r8d, word ptr [rdi]; Length
0x140012906  xor     ecx, ecx; InitialCrc
0x140012908  mov     rdx, [rdi+8]; Buffer
0x14001290c  call    cs:__imp_RtlComputeCrc32
0x140012913  nop     dword ptr [rax+rax+00h]
0x140012918  mov     rcx, rbx
0x14001291b  mov     [rbx+38h], eax
0x14001291e  call    MupiAddProviderToList
0x140012923  mov     rcx, cs:WPP_GLOBAL_Control
0x14001292a  lea     rax, WPP_GLOBAL_Control
0x140012931  cmp     rcx, rax
0x140012934  jz      short loc_140012960
0x140012936  test    dword ptr [rcx+2Ch], 4000000h
0x14001293d  jz      short loc_140012960
0x14001293f  mov     rcx, [rcx+18h]
0x140012943  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001294a  mov     edx, 15h
0x14001294f  mov     [rsp+38h+var_10], rbx
0x140012954  mov     r9, rdi
0x140012957  mov     [rsp+38h+var_18], esi
0x14001295b  call    WPP_SF_ZDq
0x140012960  mov     rsi, [rsp+38h+arg_8]
0x140012965  mov     rax, rbx
0x140012968  mov     rbx, [rsp+38h+arg_0]
0x14001296d  add     rsp, 30h
0x140012971  pop     rdi
0x140012972  retn
```
