# MupiAddKnownProvider

- ea: `0x140012930`
- end: `0x1400129c4`
- name: `MupiAddKnownProvider`
- size: `148`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f2a0`
- `0x140012750`

## callees

- `0x140003564`
- `0x140012930`
- `0x1400129cc`
- `0x140012a1c`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14001295c`
- `ntoskrnl!RtlComputeCrc32` at `0x14001295c`

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
0x140012930  mov     [rsp+arg_0], rbx
0x140012935  mov     [rsp+arg_8], rsi
0x14001293a  push    rdi
0x14001293b  sub     rsp, 30h
0x14001293f  mov     esi, r9d
0x140012942  mov     rdi, rcx
0x140012945  call    MupiAllocProvider
0x14001294a  mov     rbx, rax
0x14001294d  test    rax, rax
0x140012950  jz      short loc_140012973
0x140012952  movzx   r8d, word ptr [rdi]; Length
0x140012956  xor     ecx, ecx; InitialCrc
0x140012958  mov     rdx, [rdi+8]; Buffer
0x14001295c  call    cs:__imp_RtlComputeCrc32
0x140012963  nop     dword ptr [rax+rax+00h]
0x140012968  mov     rcx, rbx
0x14001296b  mov     [rbx+38h], eax
0x14001296e  call    MupiAddProviderToList
0x140012973  mov     rcx, cs:WPP_GLOBAL_Control
0x14001297a  lea     rax, WPP_GLOBAL_Control
0x140012981  cmp     rcx, rax
0x140012984  jz      short loc_1400129B0
0x140012986  test    dword ptr [rcx+2Ch], 4000000h
0x14001298d  jz      short loc_1400129B0
0x14001298f  mov     rcx, [rcx+18h]
0x140012993  lea     r8, WPP_b8ec61bc8b283db232150b702b34e2f1_Traceguids
0x14001299a  mov     edx, 15h
0x14001299f  mov     [rsp+38h+var_10], rbx
0x1400129a4  mov     r9, rdi
0x1400129a7  mov     [rsp+38h+var_18], esi
0x1400129ab  call    WPP_SF_ZDq
0x1400129b0  mov     rsi, [rsp+38h+arg_8]
0x1400129b5  mov     rax, rbx
0x1400129b8  mov     rbx, [rsp+38h+arg_0]
0x1400129bd  add     rsp, 30h
0x1400129c1  pop     rdi
0x1400129c2  retn
```
