# PCW_COUNTERSET_BASE::InsertNode(_RTL_RB_TREE *,_UNICODE_STRING const *,PCW_COUNTERSET_BASE *)

- ea: `0x14000f094`
- end: `0x14000f12e`
- name: `?InsertNode@PCW_COUNTERSET_BASE@@KAXPEAU_RTL_RB_TREE@@PEBU_UNICODE_STRING@@PEAV1@@Z`
- size: `154`
- prototype: `void __fastcall(struct _RTL_RB_TREE *, const struct _UNICODE_STRING *, struct PCW_COUNTERSET_BASE *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d460`
- `0x14000ed84`

## callees

- `0x14000f094`
- `0x14000f134`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f0fd`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000f0fd`

## pseudocode

```c
void __fastcall PCW_COUNTERSET_BASE::InsertNode(
        unsigned __int64 a1,
        const struct _UNICODE_STRING *a2,
        struct PCW_COUNTERSET_BASE *a3)
{
  struct PCW_COUNTERSET_BASE *v3; // r14
  __int64 v4; // rbx
  int v7; // esi
  __int64 v8; // rax

  v3 = a3;
  v4 = *(_QWORD *)a1;
  if ( (*(_BYTE *)(a1 + 8) & 1) != 0 )
  {
    if ( !v4 )
    {
LABEL_11:
      LOBYTE(a3) = 0;
      goto LABEL_12;
    }
    v4 ^= a1;
  }
  LOBYTE(a3) = 0;
  v7 = *(_BYTE *)(a1 + 8) & 1;
  if ( v4 )
  {
    while ( 1 )
    {
      if ( PcwpRbNameCompareNoCase(a2, v4) < 0 )
      {
        v8 = *(_QWORD *)v4;
        if ( v7 )
        {
          if ( !v8 )
            goto LABEL_11;
          v8 ^= v4;
        }
        if ( !v8 )
          goto LABEL_11;
      }
      else
      {
        v8 = *(_QWORD *)(v4 + 8);
        if ( v7 )
        {
          if ( !v8 )
            goto LABEL_10;
          v8 ^= v4;
        }
        if ( !v8 )
        {
LABEL_10:
          LOBYTE(a3) = 1;
          break;
        }
      }
      v4 = v8;
    }
  }
LABEL_12:
  RtlRbInsertNodeEx(a1, v4, a3, v3);
}

```

## disassembly

```asm
0x14000f094  push    rbx
0x14000f096  push    rbp
0x14000f097  push    rsi
0x14000f098  push    rdi
0x14000f099  push    r14
0x14000f09b  sub     rsp, 20h
0x14000f09f  test    byte ptr [rcx+8], 1
0x14000f0a3  mov     r14, r8
0x14000f0a6  mov     rbx, [rcx]
0x14000f0a9  mov     rbp, rdx
0x14000f0ac  mov     rdi, rcx
0x14000f0af  jz      short loc_14000F0B9
0x14000f0b1  test    rbx, rbx
0x14000f0b4  jz      short loc_14000F0F1
0x14000f0b6  xor     rbx, rcx
0x14000f0b9  movzx   esi, byte ptr [rcx+8]
0x14000f0bd  xor     r8b, r8b
0x14000f0c0  and     esi, 1
0x14000f0c3  test    rbx, rbx
0x14000f0c6  jz      short loc_14000F0F4
0x14000f0c8  mov     rdx, rbx
0x14000f0cb  mov     rcx, rbp
0x14000f0ce  call    PcwpRbNameCompareNoCase
0x14000f0d3  test    eax, eax
0x14000f0d5  js      short loc_14000F115
0x14000f0d7  mov     rax, [rbx+8]
0x14000f0db  test    esi, esi
0x14000f0dd  jz      short loc_14000F0E7
0x14000f0df  test    rax, rax
0x14000f0e2  jz      short loc_14000F0EC
0x14000f0e4  xor     rax, rbx
0x14000f0e7  test    rax, rax
0x14000f0ea  jnz     short loc_14000F129
0x14000f0ec  mov     r8b, 1
0x14000f0ef  jmp     short loc_14000F0F4
0x14000f0f1  xor     r8b, r8b
0x14000f0f4  mov     r9, r14
0x14000f0f7  mov     rdx, rbx
0x14000f0fa  mov     rcx, rdi
0x14000f0fd  call    cs:__imp_RtlRbInsertNodeEx
0x14000f104  nop     dword ptr [rax+rax+00h]
0x14000f109  add     rsp, 20h
0x14000f10d  pop     r14
0x14000f10f  pop     rdi
0x14000f110  pop     rsi
0x14000f111  pop     rbp
0x14000f112  pop     rbx
0x14000f113  retn
0x14000f115  mov     rax, [rbx]
0x14000f118  test    esi, esi
0x14000f11a  jz      short loc_14000F124
0x14000f11c  test    rax, rax
0x14000f11f  jz      short loc_14000F0F1
0x14000f121  xor     rax, rbx
0x14000f124  test    rax, rax
0x14000f127  jz      short loc_14000F0F1
0x14000f129  mov     rbx, rax
0x14000f12c  jmp     short loc_14000F0C8
```
