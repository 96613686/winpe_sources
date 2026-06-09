# wil::details::lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___::_lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___

- ea: `0x18003e294`
- end: `0x18003e2b7`
- name: `wil::details::lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___::_lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180041ef8`

## callees

- `0x18003e294`

## import_xrefs

- `WS2_32!WSALookupServiceEnd` at `0x18003e2ac`
- `WS2_32!WSALookupServiceEnd` at `0x18003e2ac`

## pseudocode

```c
int __fastcall wil::details::lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___::_lambda_call__NlaNspInfo::Enumerate_::_2_::_lambda_1___(
        __int64 a1)
{
  _QWORD *v1; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    v1 = *(_QWORD **)a1;
    if ( !**(_QWORD **)a1 )
      LODWORD(v1) = WSALookupServiceEnd(0);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18003e294  sub     rsp, 28h
0x18003e298  xor     edx, edx
0x18003e29a  cmp     [rcx+8], dl
0x18003e29d  jz      short loc_18003E2B2
0x18003e29f  mov     [rcx+8], dl
0x18003e2a2  mov     rax, [rcx]
0x18003e2a5  cmp     [rax], rdx
0x18003e2a8  jnz     short loc_18003E2B2
0x18003e2aa  xor     ecx, ecx; hLookup
0x18003e2ac  call    cs:__imp_WSALookupServiceEnd
0x18003e2b2  add     rsp, 28h
0x18003e2b6  retn
```
