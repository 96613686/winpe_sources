# ASN1BERDecCheck

- ea: `0x180001f50`
- end: `0x180001f79`
- name: `ASN1BERDecCheck`
- size: `41`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x1800014b0`
- `0x1800016e0`
- `0x180001b30`
- `0x180001c20`
- `0x180002200`
- `0x1800026b0`
- `0x180002c20`
- `0x180003270`
- `0x1800036f0`
- `0x180003be0`
- `0x180004030`
- `0x180004340`
- `0x180004a60`
- `0x180004ee0`
- `0x180005300`
- `0x180005f50`

## callees

- `0x180001f50`
- `0x180004310`

## pseudocode

```c
__int64 __fastcall ASN1BERDecCheck(_DWORD *a1, unsigned int a2)
{
  if ( a2 <= a1[4] + a1[6] - a1[10] )
    return 1;
  ASN1DecSetError((__int64)a1, 0xFFFFFC16);
  return 0;
}

```

## disassembly

```asm
0x180001f50  sub     rsp, 28h
0x180001f54  mov     eax, [rcx+18h]
0x180001f57  sub     eax, [rcx+28h]
0x180001f5a  add     eax, [rcx+10h]
0x180001f5d  cmp     edx, eax
0x180001f5f  ja      short loc_180001F6B
0x180001f61  mov     eax, 1
0x180001f66  add     rsp, 28h
0x180001f6a  retn
0x180001f6b  mov     edx, 0FFFFFC16h
0x180001f70  call    ASN1DecSetError
0x180001f75  xor     eax, eax
0x180001f77  jmp     short loc_180001F66
```
