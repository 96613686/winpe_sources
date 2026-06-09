# Marshal::JsonParser::PeekValueType(void)

- ea: `0x14001b8a8`
- end: `0x14001b930`
- name: `?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140010274`
- `0x140010724`
- `0x140010c74`
- `0x1400111d0`
- `0x14001a3c4`
- `0x14001ae48`
- `0x14001e274`

## callees

- `0x140002d4e`
- `0x14001b8a8`

## pseudocode

```c
__int64 __fastcall Marshal::JsonParser::PeekValueType(_QWORD *a1)
{
  unsigned __int64 v1; // rdx
  unsigned int v2; // ecx
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  v1 = a1[2];
  if ( v1 >= a1[1] )
    goto LABEL_17;
  v2 = *(unsigned __int16 *)(*a1 + 2 * v1);
  switch ( v2 )
  {
    case '"':
      return 1;
    case '[':
      return 2;
    case 'f':
      return 4;
    case 'n':
      return 5;
    case 't':
      return 4;
  }
  if ( v2 != 123 )
  {
    if ( v2 >= 0x30 && v2 <= 0x39 || v2 == 45 )
      return 0;
LABEL_17:
    pExceptionObject = 2;
    throw (Marshal::JsonParser::ParseException *)&pExceptionObject;
  }
  return 3;
}

```

## disassembly

```asm
0x14001b8a8  sub     rsp, 28h
0x14001b8ac  mov     rdx, [rcx+10h]
0x14001b8b0  cmp     rdx, [rcx+8]
0x14001b8b4  jnb     short loc_14001B915
0x14001b8b6  mov     rax, [rcx]
0x14001b8b9  movzx   ecx, word ptr [rax+rdx*2]
0x14001b8bd  cmp     ecx, 22h ; '"'
0x14001b8c0  jz      short loc_14001B90E
0x14001b8c2  cmp     ecx, 5Bh ; '['
0x14001b8c5  jz      short loc_14001B907
0x14001b8c7  cmp     ecx, 66h ; 'f'
0x14001b8ca  jz      short loc_14001B900
0x14001b8cc  cmp     ecx, 6Eh ; 'n'
0x14001b8cf  jz      short loc_14001B8F9
0x14001b8d1  cmp     ecx, 74h ; 't'
0x14001b8d4  jz      short loc_14001B900
0x14001b8d6  cmp     ecx, 7Bh ; '{'
0x14001b8d9  jz      short loc_14001B8F2
0x14001b8db  cmp     ecx, 30h ; '0'
0x14001b8de  jb      short loc_14001B8E5
0x14001b8e0  cmp     ecx, 39h ; '9'
0x14001b8e3  jbe     short loc_14001B8EA
0x14001b8e5  cmp     ecx, 2Dh ; '-'
0x14001b8e8  jnz     short loc_14001B915
0x14001b8ea  xor     eax, eax
0x14001b8ec  add     rsp, 28h
0x14001b8f0  retn
0x14001b8f2  mov     eax, 3
0x14001b8f7  jmp     short loc_14001B8EC
0x14001b8f9  mov     eax, 5
0x14001b8fe  jmp     short loc_14001B8EC
0x14001b900  mov     eax, 4
0x14001b905  jmp     short loc_14001B8EC
0x14001b907  mov     eax, 2
0x14001b90c  jmp     short loc_14001B8EC
0x14001b90e  mov     eax, 1
0x14001b913  jmp     short loc_14001B8EC
0x14001b915  mov     eax, 2
0x14001b91a  lea     rdx, _TI1?AUParseException@JsonParser@Marshal@@; pThrowInfo
0x14001b921  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14001b926  mov     [rsp+28h+pExceptionObject], eax
0x14001b92a  call    _CxxThrowException_0
```
