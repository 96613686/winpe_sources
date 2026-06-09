# _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)

- ea: `0x1800184c8`
- end: `0x180018549`
- name: `?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z`
- size: `129`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int *, struct tagHYPOTHESIS **, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f5bc`
- `0x18000f7c8`
- `0x1800104f0`
- `0x180018378`

## callees

- `0x1800184c8`
- `0x1800185fc`
- `0x18001a178`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018504`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _hypothesis_builder::Detach(
        _hypothesis_builder *this,
        unsigned int *a2,
        struct tagHYPOTHESIS **a3,
        unsigned int *a4)
{
  __int64 v7; // rdi
  _BYTE *v8; // rax
  __int64 result; // rax

  if ( !a3 || !a2 )
    return 2147942487LL;
  if ( !*((_QWORD *)this + 4) )
  {
    if ( *((_DWORD *)this + 4) || *((_QWORD *)this + 3) )
      MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
    v7 = 32;
    v8 = CoTaskMemAlloc(0x20u);
    *((_QWORD *)this + 4) = v8;
    if ( !v8 )
      return 2147942414LL;
    do
    {
      *v8++ = 0;
      --v7;
    }
    while ( v7 );
  }
  _hypothesis_builder::DoDetach(this, a3);
  result = 0;
  *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x1800184c8  push    rbx
0x1800184ca  push    rbp
0x1800184cb  push    rsi
0x1800184cc  push    rdi
0x1800184cd  sub     rsp, 28h
0x1800184d1  mov     rbp, r8
0x1800184d4  mov     rsi, rdx
0x1800184d7  mov     rbx, rcx
0x1800184da  test    r8, r8
0x1800184dd  jz      short loc_18001853B
0x1800184df  test    rdx, rdx
0x1800184e2  jz      short loc_18001853B
0x1800184e4  cmp     qword ptr [rcx+20h], 0
0x1800184e9  jnz     short loc_180018526
0x1800184eb  cmp     dword ptr [rcx+10h], 0
0x1800184ef  jnz     short loc_1800184F8
0x1800184f1  cmp     qword ptr [rcx+18h], 0
0x1800184f6  jz      short loc_1800184FD
0x1800184f8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800184fd  mov     edi, 20h ; ' '
0x180018502  mov     ecx, edi; cb
0x180018504  call    cs:__imp_CoTaskMemAlloc
0x18001850a  mov     [rbx+20h], rax
0x18001850e  test    rax, rax
0x180018511  jnz     short loc_18001851A
0x180018513  mov     eax, 8007000Eh
0x180018518  jmp     short loc_180018540
0x18001851a  mov     byte ptr [rax], 0
0x18001851d  inc     rax
0x180018520  sub     rdi, 1
0x180018524  jnz     short loc_18001851A
0x180018526  mov     rdx, rbp; struct tagHYPOTHESIS **
0x180018529  mov     rcx, rbx; this
0x18001852c  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x180018531  xor     eax, eax
0x180018533  mov     dword ptr [rsi], 1
0x180018539  jmp     short loc_180018540
0x18001853b  mov     eax, 80070057h
0x180018540  add     rsp, 28h
0x180018544  pop     rdi
0x180018545  pop     rsi
0x180018546  pop     rbp
0x180018547  pop     rbx
0x180018548  retn
```
