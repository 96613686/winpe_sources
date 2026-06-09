# HsmOsIsVailSupported

- ea: `0x1400131d4`
- end: `0x14001320e`
- name: `HsmOsIsVailSupported`
- size: `58`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140087080`
- `0x140087490`

## callees

- `0x1400131d4`

## import_xrefs

- `ntoskrnl!RtlIsApiSetImplemented` at `0x1400131e7`
- `ntoskrnl!RtlIsApiSetImplemented` at `0x1400131e7`

## string_xrefs

- `0x1400131e0`: `SchemaExt-Composable-Vail`

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
0x1400131d4  push    rbx
0x1400131d6  sub     rsp, 20h
0x1400131da  mov     rbx, rcx
0x1400131dd  mov     byte ptr [rcx], 0
0x1400131e0  lea     rcx, aSchemaextCompo; "SchemaExt-Composable-Vail"
0x1400131e7  call    cs:__imp_RtlIsApiSetImplemented
0x1400131ee  nop     dword ptr [rax+rax+00h]
0x1400131f3  test    eax, eax
0x1400131f5  js      short loc_1400131FC
0x1400131f7  mov     byte ptr [rbx], 1
0x1400131fa  jmp     short loc_140013207
0x1400131fc  cmp     eax, 0C0000225h
0x140013201  jnz     short loc_140013207
0x140013203  xor     eax, eax
0x140013205  mov     [rbx], al
0x140013207  add     rsp, 20h
0x14001320b  pop     rbx
0x14001320c  retn
```
