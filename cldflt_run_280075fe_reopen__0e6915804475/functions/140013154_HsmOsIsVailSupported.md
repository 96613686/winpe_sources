# HsmOsIsVailSupported

- ea: `0x140013154`
- end: `0x14001318e`
- name: `HsmOsIsVailSupported`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140087080`
- `0x140087490`

## callees

- `0x140013154`

## import_xrefs

- `ntoskrnl!RtlIsApiSetImplemented` at `0x140013167`
- `ntoskrnl!RtlIsApiSetImplemented` at `0x140013167`

## string_xrefs

- `0x140013160`: `SchemaExt-Composable-Vail`

## pseudocode

```c
__int64 __fastcall HsmOsIsVailSupported(_BYTE *a1)
{
  __int64 result; // rax

  *a1 = 0;
  result = RtlIsApiSetImplemented("SchemaExt-Composable-Vail");
  if ( (int)result < 0 )
  {
    if ( (_DWORD)result == -1073741275 )
    {
      result = 0;
      *a1 = 0;
    }
  }
  else
  {
    *a1 = 1;
  }
  return result;
}

```

## disassembly

```asm
0x140013154  push    rbx
0x140013156  sub     rsp, 20h
0x14001315a  mov     rbx, rcx
0x14001315d  mov     byte ptr [rcx], 0
0x140013160  lea     rcx, aSchemaextCompo; "SchemaExt-Composable-Vail"
0x140013167  call    cs:__imp_RtlIsApiSetImplemented
0x14001316e  nop     dword ptr [rax+rax+00h]
0x140013173  test    eax, eax
0x140013175  js      short loc_14001317C
0x140013177  mov     byte ptr [rbx], 1
0x14001317a  jmp     short loc_140013187
0x14001317c  cmp     eax, 0C0000225h
0x140013181  jnz     short loc_140013187
0x140013183  xor     eax, eax
0x140013185  mov     [rbx], al
0x140013187  add     rsp, 20h
0x14001318b  pop     rbx
0x14001318c  retn
```
