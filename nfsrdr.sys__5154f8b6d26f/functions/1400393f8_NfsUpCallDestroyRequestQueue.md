# NfsUpCallDestroyRequestQueue

- ea: `0x1400393f8`
- end: `0x1400394a4`
- name: `NfsUpCallDestroyRequestQueue`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400232dc`
- `0x14002d428`

## callees

- `0x1400393f8`
- `0x140039b40`
- `0x14003a170`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140039463`
- `ntoskrnl!ExDeleteResourceLite` at `0x140039463`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039477`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039477`

## pseudocode

```c
__int64 __fastcall NfsUpCallDestroyRequestQueue(_QWORD *a1)
{
  __int64 v2; // rbx
  int v3; // edx
  int v4; // edi
  int v5; // edx

  if ( !a1 || (v2 = *a1) == 0 )
    return (unsigned int)-1073741811;
  v3 = *(_DWORD *)(v2 + 136);
  v4 = 0;
  if ( !v3 )
    goto LABEL_12;
  v5 = v3 - 1;
  if ( v5 )
  {
    if ( v5 != 2 )
      return (unsigned int)-1073741436;
    goto LABEL_9;
  }
  v4 = NfsUpCallShutdownRequestQueue(*a1);
  if ( v4 >= 0 && *(_DWORD *)(v2 + 136) == 3 )
  {
LABEL_9:
    if ( *(_QWORD *)v2 )
    {
      UpCallDestroyQueue(*(PVOID *)v2);
      *(_QWORD *)v2 = 0;
    }
    ExDeleteResourceLite((PERESOURCE)(v2 + 8));
LABEL_12:
    ExFreePoolWithTag((PVOID)v2, 0x5573664Eu);
    *a1 = 0;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400393f8  mov     [rsp+arg_0], rbx
0x1400393fd  mov     [rsp+arg_8], rsi
0x140039402  push    rdi
0x140039403  sub     rsp, 20h
0x140039407  mov     rsi, rcx
0x14003940a  test    rcx, rcx
0x14003940d  jz      short loc_14003948C
0x14003940f  mov     rbx, [rcx]
0x140039412  test    rbx, rbx
0x140039415  jz      short loc_14003948C
0x140039417  mov     edx, [rbx+88h]
0x14003941d  xor     edi, edi
0x14003941f  test    edx, edx
0x140039421  jz      short loc_14003946F
0x140039423  sub     edx, 1
0x140039426  jz      short loc_140039434
0x140039428  cmp     edx, 2
0x14003942b  jz      short loc_14003944B
0x14003942d  mov     edi, 0C0000184h
0x140039432  jmp     short loc_140039491
0x140039434  mov     rcx, rbx
0x140039437  call    NfsUpCallShutdownRequestQueue
0x14003943c  mov     edi, eax
0x14003943e  test    eax, eax
0x140039440  js      short loc_140039491
0x140039442  cmp     dword ptr [rbx+88h], 3
0x140039449  jnz     short loc_140039491
0x14003944b  mov     rcx, [rbx]; P
0x14003944e  test    rcx, rcx
0x140039451  jz      short loc_14003945F
0x140039453  call    UpCallDestroyQueue
0x140039458  mov     qword ptr [rbx], 0
0x14003945f  lea     rcx, [rbx+8]; Resource
0x140039463  call    cs:__imp_ExDeleteResourceLite
0x14003946a  nop     dword ptr [rax+rax+00h]
0x14003946f  mov     edx, 5573664Eh; Tag
0x140039474  mov     rcx, rbx; P
0x140039477  call    cs:__imp_ExFreePoolWithTag
0x14003947e  nop     dword ptr [rax+rax+00h]
0x140039483  mov     qword ptr [rsi], 0
0x14003948a  jmp     short loc_140039491
0x14003948c  mov     edi, 0C000000Dh
0x140039491  mov     rbx, [rsp+28h+arg_0]
0x140039496  mov     eax, edi
0x140039498  mov     rsi, [rsp+28h+arg_8]
0x14003949d  add     rsp, 20h
0x1400394a1  pop     rdi
0x1400394a2  retn
```
