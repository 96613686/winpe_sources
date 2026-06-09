# ReadParameters2

- ea: `0x14004aaf4`
- end: `0x14004abcb`
- name: `ReadParameters2`
- size: `215`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14004abd4`

## callees

- `0x140048e50`
- `0x14004aaf4`
- `0x14004b260`

## pseudocode

```c
void __fastcall ReadParameters2(__int64 a1, void *a2)
{
  int v4; // eax
  int v5; // eax
  __int16 v6; // cx
  int v7; // eax
  __int16 v8; // ax
  int SingleParameter; // ebx
  int v10; // eax

  v4 = NbtReadSingleParameter(a2, L"NodeType", 0, 0) - 1;
  if ( !v4 )
  {
    v8 = 1;
LABEL_6:
    NodeType = v8;
    goto LABEL_7;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = 4;
    v7 = v5 - 2;
    if ( v7 )
    {
      if ( v7 == 4 )
        v8 = 8;
      else
        v8 = 4097;
      goto LABEL_6;
    }
  }
  else
  {
    v6 = 2;
  }
  v8 = v6;
  NodeType = v6;
LABEL_7:
  RegistryNodeType = v8;
  SingleParameter = NbtReadSingleParameter(a2, L"BroadcastAddress", 0xFFFFFFFF, 0);
  v10 = NbtReadSingleParameter(a2, L"BroadcastAddress", 0, 0);
  if ( SingleParameter == v10 )
  {
    byte_140039642 = 1;
    dword_14003961C = v10;
  }
  else
  {
    byte_140039642 = 0;
  }
  ReadScope(a1, a2);
}

```

## disassembly

```asm
0x14004aaf4  push    rbx
0x14004aaf6  push    rbp
0x14004aaf7  push    rsi
0x14004aaf8  push    rdi
0x14004aaf9  sub     rsp, 28h
0x14004aafd  mov     rdi, rdx
0x14004ab00  mov     rsi, rcx
0x14004ab03  mov     rcx, rdi; KeyHandle
0x14004ab06  lea     rdx, aNodetype; "NodeType"
0x14004ab0d  xor     r9d, r9d
0x14004ab10  xor     r8d, r8d
0x14004ab13  call    NbtReadSingleParameter
0x14004ab18  mov     ebp, 1
0x14004ab1d  sub     eax, ebp
0x14004ab1f  jz      loc_14004ABC3
0x14004ab25  sub     eax, ebp
0x14004ab27  jz      short loc_14004AB99
0x14004ab29  lea     ecx, [rbp+3]
0x14004ab2c  sub     eax, 2
0x14004ab2f  jz      short loc_14004AB9E
0x14004ab31  cmp     eax, ecx
0x14004ab33  jz      loc_14004ABB9
0x14004ab39  mov     eax, 1001h
0x14004ab3e  mov     cs:NodeType, ax
0x14004ab45  xor     r9d, r9d
0x14004ab48  mov     cs:RegistryNodeType, ax
0x14004ab4f  or      r8d, 0FFFFFFFFh
0x14004ab53  lea     rdx, aBroadcastaddre; "BroadcastAddress"
0x14004ab5a  mov     rcx, rdi; KeyHandle
0x14004ab5d  call    NbtReadSingleParameter
0x14004ab62  xor     r9d, r9d
0x14004ab65  lea     rdx, aBroadcastaddre; "BroadcastAddress"
0x14004ab6c  xor     r8d, r8d
0x14004ab6f  mov     rcx, rdi; KeyHandle
0x14004ab72  mov     ebx, eax
0x14004ab74  call    NbtReadSingleParameter
0x14004ab79  cmp     ebx, eax
0x14004ab7b  jz      short loc_14004ABAA
0x14004ab7d  mov     cs:byte_140039642, 0
0x14004ab84  mov     rdx, rdi
0x14004ab87  mov     rcx, rsi
0x14004ab8a  call    ReadScope
0x14004ab8f  add     rsp, 28h
0x14004ab93  pop     rdi
0x14004ab94  pop     rsi
0x14004ab95  pop     rbp
0x14004ab96  pop     rbx
0x14004ab97  retn
0x14004ab99  mov     ecx, 2
0x14004ab9e  movzx   eax, cx
0x14004aba1  mov     cs:NodeType, cx
0x14004aba8  jmp     short loc_14004AB45
0x14004abaa  mov     cs:byte_140039642, bpl
0x14004abb1  mov     cs:dword_14003961C, eax
0x14004abb7  jmp     short loc_14004AB84
0x14004abb9  mov     eax, 8
0x14004abbe  jmp     loc_14004AB3E
0x14004abc3  movzx   eax, bp
0x14004abc6  jmp     loc_14004AB3E
```
