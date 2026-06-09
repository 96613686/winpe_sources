# FreeTapiLine

- ea: `0x140006c1c`
- end: `0x140006ca6`
- name: `FreeTapiLine`
- size: `138`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140005ca4`
- `0x1400062c0`
- `0x140006cac`
- `0x140011850`
- `0x140012590`
- `0x140012880`
- `0x1400130a0`
- `0x140013610`
- `0x140013bc0`
- `0x1400146c0`
- `0x140014ca0`

## callees

- `0x140006c1c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c87`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c6b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006c87`

## pseudocode

```c
void __fastcall FreeTapiLine(_QWORD *P)
{
  __int64 i; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rax
  _QWORD *v5; // rdx

  for ( i = 0; (unsigned int)i < *(_DWORD *)(P[9] + 48LL); i = (unsigned int)(i + 1) )
  {
    v3 = *(_QWORD **)(P[14] + 8 * i);
    if ( v3 )
    {
      v4 = *v3;
      if ( *(_QWORD **)(*v3 + 8LL) != v3 || (v5 = (_QWORD *)v3[1], (_QWORD *)*v5 != v3) )
        __fastfail(3u);
      *v5 = v4;
      *(_QWORD *)(v4 + 8) = v5;
      *(_QWORD *)(P[14] + 8 * i) = 0;
      --*((_DWORD *)P + 22);
      ExFreePoolWithTag(v3, 0);
    }
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140006c1c  mov     [rsp+arg_0], rbx
0x140006c21  push    rdi
0x140006c22  sub     rsp, 20h
0x140006c26  mov     rax, [rcx+48h]
0x140006c2a  xor     edi, edi
0x140006c2c  mov     rbx, rcx
0x140006c2f  cmp     [rax+30h], edi
0x140006c32  jbe     short loc_140006C82
0x140006c34  mov     rax, [rbx+70h]
0x140006c38  mov     rcx, [rax+rdi*8]; P
0x140006c3c  test    rcx, rcx
0x140006c3f  jz      short loc_140006C77
0x140006c41  mov     rax, [rcx]
0x140006c44  cmp     [rax+8], rcx
0x140006c48  jnz     short loc_140006C9F
0x140006c4a  mov     rdx, [rcx+8]
0x140006c4e  cmp     [rdx], rcx
0x140006c51  jnz     short loc_140006C9F
0x140006c53  mov     [rdx], rax
0x140006c56  mov     [rax+8], rdx
0x140006c5a  xor     edx, edx; Tag
0x140006c5c  mov     rax, [rbx+70h]
0x140006c60  mov     qword ptr [rax+rdi*8], 0
0x140006c68  dec     dword ptr [rbx+58h]
0x140006c6b  call    cs:__imp_ExFreePoolWithTag
0x140006c72  nop     dword ptr [rax+rax+00h]
0x140006c77  mov     rax, [rbx+48h]
0x140006c7b  inc     edi
0x140006c7d  cmp     edi, [rax+30h]
0x140006c80  jb      short loc_140006C34
0x140006c82  xor     edx, edx; Tag
0x140006c84  mov     rcx, rbx; P
0x140006c87  call    cs:__imp_ExFreePoolWithTag
0x140006c8e  nop     dword ptr [rax+rax+00h]
0x140006c93  mov     rbx, [rsp+28h+arg_0]
0x140006c98  add     rsp, 20h
0x140006c9c  pop     rdi
0x140006c9d  retn
0x140006c9f  mov     ecx, 3
0x140006ca4  int     29h; Win8: RtlFailFast(ecx)
```
