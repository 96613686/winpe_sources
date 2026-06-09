# ClasspWriteSrbErrorResultEvent

- ea: `0x1400073d4`
- end: `0x140007405`
- name: `ClasspWriteSrbErrorResultEvent`
- size: `49`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000de10`
- `0x140010400`
- `0x140011ba0`
- `0x140016350`

## callees

- `0x1400066cc`
- `0x1400073d4`
- `0x14003bf7c`

## pseudocode

```c
void __fastcall ClasspWriteSrbErrorResultEvent(int a1, __int64 a2, unsigned int a3, __int64 a4, char a5)
{
  int v5; // eax

  v5 = *(unsigned __int8 *)(a4 + 2);
  if ( (_BYTE)v5 == 40 )
    v5 = *(_DWORD *)(a4 + 20);
  if ( v5 )
    ClasspWriteNonScsiSrbErrorResultEvent(a1, a2, a3, a4, a5);
  else
    ClasspWriteScsiSrbErrorResultEvent(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1400073d4  sub     rsp, 38h
0x1400073d8  movzx   eax, byte ptr [r9+2]
0x1400073dd  cmp     al, 28h ; '('
0x1400073df  jz      short loc_1400073F8
0x1400073e1  test    eax, eax
0x1400073e3  mov     al, [rsp+38h+arg_20]
0x1400073e7  mov     [rsp+38h+var_18], al
0x1400073eb  jnz     short loc_1400073FE
0x1400073ed  call    ClasspWriteScsiSrbErrorResultEvent
0x1400073f2  add     rsp, 38h
0x1400073f6  retn
0x1400073f8  mov     eax, [r9+14h]
0x1400073fc  jmp     short loc_1400073E1
0x1400073fe  call    ClasspWriteNonScsiSrbErrorResultEvent
0x140007403  jmp     short loc_1400073F2
```
