# _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)

- ea: `0x18000dab4`
- end: `0x18000db3c`
- name: `?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z`
- size: `136`
- prototype: `__int64 __fastcall(_hypothesis_builder *__hidden this, unsigned int *, struct tagHYPOTHESIS **, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006ac0`
- `0x1800086b0`
- `0x180009e60`
- `0x18000ad60`

## callees

- `0x18000dab4`
- `0x18000dbf8`
- `0x18000dd64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000daf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000daf0`

## pseudocode

```c
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
      MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
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
0x18000dab4  push    rbx
0x18000dab6  push    rbp
0x18000dab7  push    rsi
0x18000dab8  push    rdi
0x18000dab9  sub     rsp, 28h
0x18000dabd  mov     rbp, r8
0x18000dac0  mov     rsi, rdx
0x18000dac3  mov     rbx, rcx
0x18000dac6  test    r8, r8
0x18000dac9  jz      short loc_18000DB2D
0x18000dacb  test    rdx, rdx
0x18000dace  jz      short loc_18000DB2D
0x18000dad0  cmp     qword ptr [rcx+20h], 0
0x18000dad5  jnz     short loc_18000DB18
0x18000dad7  cmp     dword ptr [rcx+10h], 0
0x18000dadb  jnz     short loc_18000DAE4
0x18000dadd  cmp     qword ptr [rcx+18h], 0
0x18000dae2  jz      short loc_18000DAE9
0x18000dae4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dae9  mov     edi, 20h ; ' '
0x18000daee  mov     ecx, edi; cb
0x18000daf0  call    cs:__imp_CoTaskMemAlloc
0x18000daf7  nop     dword ptr [rax+rax+00h]
0x18000dafc  mov     [rbx+20h], rax
0x18000db00  test    rax, rax
0x18000db03  jnz     short loc_18000DB0C
0x18000db05  mov     eax, 8007000Eh
0x18000db0a  jmp     short loc_18000DB32
0x18000db0c  mov     byte ptr [rax], 0
0x18000db0f  inc     rax
0x18000db12  sub     rdi, 1
0x18000db16  jnz     short loc_18000DB0C
0x18000db18  mov     rdx, rbp; struct tagHYPOTHESIS **
0x18000db1b  mov     rcx, rbx; this
0x18000db1e  call    ?DoDetach@_hypothesis_builder@@IEAAXPEAPEAUtagHYPOTHESIS@@@Z; _hypothesis_builder::DoDetach(tagHYPOTHESIS * *)
0x18000db23  xor     eax, eax
0x18000db25  mov     dword ptr [rsi], 1
0x18000db2b  jmp     short loc_18000DB32
0x18000db2d  mov     eax, 80070057h
0x18000db32  add     rsp, 28h
0x18000db36  pop     rdi
0x18000db37  pop     rsi
0x18000db38  pop     rbp
0x18000db39  pop     rbx
0x18000db3a  retn
```
