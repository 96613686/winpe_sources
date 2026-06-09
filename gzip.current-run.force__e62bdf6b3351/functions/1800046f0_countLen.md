# countLen

- ea: `0x1800046f0`
- end: `0x180004754`
- name: `countLen`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800045c0`
- `0x1800046f0`

## callees

- `0x1800046f0`

## pseudocode

```c
__int64 __fastcall countLen(_DWORD *a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 result; // rax
  int v9; // ecx

  if ( a2 < a1[865] )
  {
    LODWORD(result) = a1[874];
    v9 = a1[866];
    if ( (int)result >= v9 )
      LODWORD(result) = v9;
    result = (int)result;
    ++a1[(int)result + 876];
  }
  else
  {
    v5 = a1[a2];
    ++a1[874];
    countLen(a1, (unsigned __int16)v5, a3, a4);
    result = countLen(a1, HIWORD(v5), v6, v7);
    --a1[874];
  }
  return result;
}

```

## disassembly

```asm
0x1800046f0  push    rbx
0x1800046f2  sub     rsp, 20h
0x1800046f6  mov     rbx, rcx
0x1800046f9  cmp     edx, [rcx+0D84h]
0x1800046ff  jl      short loc_180004738
0x180004701  movsxd  rax, edx
0x180004704  mov     [rsp+28h+arg_0], rdi
0x180004709  mov     edi, [rcx+rax*4]
0x18000470c  inc     dword ptr [rcx+0DA8h]
0x180004712  movzx   edx, di
0x180004715  call    countLen
0x18000471a  shr     edi, 10h
0x18000471d  mov     rcx, rbx
0x180004720  mov     edx, edi
0x180004722  call    countLen
0x180004727  dec     dword ptr [rbx+0DA8h]
0x18000472d  mov     rdi, [rsp+28h+arg_0]
0x180004732  add     rsp, 20h
0x180004736  pop     rbx
0x180004737  retn
0x180004738  mov     eax, [rbx+0DA8h]
0x18000473e  mov     ecx, [rcx+0D88h]
0x180004744  cmp     eax, ecx
0x180004746  cmovge  eax, ecx
0x180004749  cdqe
0x18000474b  inc     dword ptr [rbx+rax*4+0DB0h]
0x180004752  jmp     short loc_180004732
```
