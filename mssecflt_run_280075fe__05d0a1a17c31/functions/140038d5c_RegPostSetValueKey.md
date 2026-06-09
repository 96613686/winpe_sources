# RegPostSetValueKey

- ea: `0x140038d5c`
- end: `0x140038e61`
- name: `RegPostSetValueKey`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140033020`

## callees

- `0x140033a8c`
- `0x140033bb8`
- `0x140038164`
- `0x140038d5c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140038e02`
- `ntoskrnl!RtlCompareMemory` at `0x140038e02`

## pseudocode

```c
__int64 __fastcall RegPostSetValueKey(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // rax
  _DWORD *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rbx

  v2 = 0;
  v3 = MpRegpFetchCallContext();
  v4 = v3;
  if ( a1 && (v5 = *(_QWORD *)(a1 + 16)) != 0 )
  {
    if ( *(int *)(a1 + 8) >= 0 )
    {
      if ( !v3 )
        return v2;
      if ( *(_WORD *)v3 == 0xEB01 )
      {
        v6 = *(_QWORD *)(v3 + 72);
        if ( v6 && *(_QWORD *)(v4 + 40) )
        {
          if ( *(_BYTE *)(v6 + 16) == 1
            && (v7 = *(_DWORD **)(v4 + 56)) != 0
            && *(_DWORD *)(v5 + 20) == v7[1]
            && (v8 = *(_DWORD *)(v5 + 32), v8 == v7[2])
            && (v9 = *(unsigned int *)(v5 + 32), v9 == RtlCompareMemory(*(const void **)(v5 + 24), v7 + 3, v8)) )
          {
            v2 = 0;
          }
          else
          {
            RegIssueSetValueEvent(v5, v4);
          }
        }
        else
        {
          v2 = -1073741823;
        }
      }
      else
      {
        v2 = -1073741788;
      }
    }
  }
  else
  {
    v2 = -1073741811;
  }
  if ( v4 )
    MpRegpFreeCallContext(v4);
  return v2;
}

```

## disassembly

```asm
0x140038d5c  mov     [rsp+arg_10], rbx
0x140038d61  push    rsi
0x140038d62  push    rdi
0x140038d63  push    r14
0x140038d65  sub     rsp, 30h
0x140038d69  mov     rbx, rcx
0x140038d6c  xor     edi, edi
0x140038d6e  call    MpRegpFetchCallContext
0x140038d73  mov     rsi, rax
0x140038d76  mov     [rsp+48h+arg_0], rax
0x140038d7b  test    rbx, rbx
0x140038d7e  jz      loc_140038E3E
0x140038d84  mov     r14, [rbx+10h]
0x140038d88  mov     [rsp+48h+arg_8], r14
0x140038d8d  test    r14, r14
0x140038d90  jz      loc_140038E3E
0x140038d96  cmp     [rbx+8], edi
0x140038d99  jl      loc_140038E43
0x140038d9f  test    rax, rax
0x140038da2  jz      loc_140038E50
0x140038da8  mov     eax, 0EB01h
0x140038dad  cmp     ax, [rsi]
0x140038db0  jz      short loc_140038DBC
0x140038db2  mov     edi, 0C0000024h
0x140038db7  jmp     loc_140038E43
0x140038dbc  mov     rax, [rsi+48h]
0x140038dc0  test    rax, rax
0x140038dc3  jnz     short loc_140038DCC
0x140038dc5  mov     edi, 0C0000001h
0x140038dca  jmp     short loc_140038E43
0x140038dcc  cmp     [rsi+28h], rdi
0x140038dd0  jz      short loc_140038DC5
0x140038dd2  cmp     byte ptr [rax+10h], 1
0x140038dd6  jnz     short loc_140038E31
0x140038dd8  mov     rdx, [rsi+38h]
0x140038ddc  test    rdx, rdx
0x140038ddf  jz      short loc_140038E31
0x140038de1  mov     eax, [rdx+4]
0x140038de4  cmp     [r14+14h], eax
0x140038de8  jnz     short loc_140038E31
0x140038dea  mov     eax, [r14+20h]
0x140038dee  cmp     eax, [rdx+8]
0x140038df1  jnz     short loc_140038E31
0x140038df3  mov     ebx, [r14+20h]
0x140038df7  mov     r8d, eax; Length
0x140038dfa  add     rdx, 0Ch; Source2
0x140038dfe  mov     rcx, [r14+18h]; Source1
0x140038e02  call    cs:__imp_RtlCompareMemory
0x140038e09  nop     dword ptr [rax+rax+00h]
0x140038e0e  cmp     rbx, rax
0x140038e11  jnz     short loc_140038E1B
0x140038e13  xor     edi, edi
0x140038e15  mov     [rsp+48h+var_28], edi
0x140038e19  jmp     short loc_140038E43
0x140038e1b  jmp     short loc_140038E2D
0x140038e1d  mov     edi, eax
0x140038e1f  mov     [rsp+48h+var_28], eax
0x140038e23  mov     rsi, [rsp+48h+arg_0]
0x140038e28  mov     r14, [rsp+48h+arg_8]
0x140038e2d  test    edi, edi
0x140038e2f  js      short loc_140038E43
0x140038e31  mov     rdx, rsi
0x140038e34  mov     rcx, r14
0x140038e37  call    RegIssueSetValueEvent
0x140038e3c  jmp     short loc_140038E43
0x140038e3e  mov     edi, 0C000000Dh
0x140038e43  test    rsi, rsi
0x140038e46  jz      short loc_140038E50
0x140038e48  mov     rcx, rsi
0x140038e4b  call    MpRegpFreeCallContext
0x140038e50  mov     eax, edi
0x140038e52  mov     rbx, [rsp+48h+arg_10]
0x140038e57  add     rsp, 30h
0x140038e5b  pop     r14
0x140038e5d  pop     rdi
0x140038e5e  pop     rsi
0x140038e5f  retn
```
