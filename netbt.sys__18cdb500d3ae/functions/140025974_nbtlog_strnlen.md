# nbtlog_strnlen

- ea: `0x140025974`
- end: `0x140025986`
- name: `nbtlog_strnlen`
- size: `18`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x140040008`
- `0x1400400dc`
- `0x140040628`
- `0x1400407dc`
- `0x140040f48`
- `0x1400411d4`
- `0x140041444`
- `0x140041580`
- `0x1400418f0`
- `0x1400421a8`
- `0x140042ea0`

## callees

- `0x140025974`

## pseudocode

```c
__int64 __fastcall nbtlog_strnlen(_BYTE *a1)
{
  __int64 result; // rax

  result = 0;
  do
  {
    if ( !*a1 )
      break;
    result = (unsigned int)(result + 1);
    ++a1;
  }
  while ( (int)result < 15 );
  return result;
}

```

## disassembly

```asm
0x140025974  xor     eax, eax
0x140025976  cmp     byte ptr [rcx], 0
0x140025979  jz      short locret_140025985
0x14002597b  inc     eax
0x14002597d  inc     rcx
0x140025980  cmp     eax, 0Fh
0x140025983  jl      short loc_140025976
0x140025985  retn
```
