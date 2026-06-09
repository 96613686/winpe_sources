# FreeConnectionOptionData

- ea: `0x140010c28`
- end: `0x140010c87`
- name: `FreeConnectionOptionData`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400104d8`
- `0x140010be8`
- `0x140027acc`

## callees

- `0x140010c28`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140010c6b`
- `ntoskrnl!IofCompleteRequest` at `0x140010c6b`

## pseudocode

```c
_QWORD *__fastcall FreeConnectionOptionData(__int64 a1)
{
  _QWORD **v1; // rbx
  _QWORD *result; // rax
  _QWORD *v3; // rcx

  v1 = (_QWORD **)(a1 + 96);
  while ( 1 )
  {
    result = *v1;
    if ( *v1 == v1 )
      break;
    if ( (_QWORD **)result[1] != v1 || (v3 = (_QWORD *)*result, *(_QWORD **)(*result + 8LL) != result) )
      __fastfail(3u);
    *v1 = v3;
    v3[1] = v1;
    result[1] = 0;
    *result = 0;
    IofCompleteRequest((PIRP)(result - 21), 0);
  }
  return result;
}

```

## disassembly

```asm
0x140010c28  push    rbx
0x140010c2a  sub     rsp, 20h
0x140010c2e  lea     rbx, [rcx+60h]
0x140010c32  mov     rax, [rbx]
0x140010c35  cmp     rax, rbx
0x140010c38  jz      short loc_140010C79
0x140010c3a  cmp     [rax+8], rbx
0x140010c3e  jnz     short loc_140010C80
0x140010c40  mov     rcx, [rax]
0x140010c43  cmp     [rcx+8], rax
0x140010c47  jnz     short loc_140010C80
0x140010c49  mov     [rbx], rcx
0x140010c4c  xor     edx, edx; PriorityBoost
0x140010c4e  mov     [rcx+8], rbx
0x140010c52  lea     rcx, [rax-0A8h]; Irp
0x140010c59  mov     qword ptr [rcx+0B0h], 0
0x140010c64  mov     qword ptr [rax], 0
0x140010c6b  call    cs:__imp_IofCompleteRequest
0x140010c72  nop     dword ptr [rax+rax+00h]
0x140010c77  jmp     short loc_140010C32
0x140010c79  add     rsp, 20h
0x140010c7d  pop     rbx
0x140010c7e  retn
0x140010c80  mov     ecx, 3
0x140010c85  int     29h; Win8: RtlFailFast(ecx)
```
