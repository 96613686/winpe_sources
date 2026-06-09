# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x18003bea0`
- end: `0x18003bedb`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006d84`
- `0x18003bea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003beab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003beab`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  __int64 result; // rax

  DeleteCriticalSection(&stru_1800534B8);
  if ( qword_1800534E0 )
  {
    free(qword_1800534E0);
    result = 0;
    qword_1800534E0 = 0;
  }
  else
  {
    result = 0;
  }
  qword_1800534E8 = 0;
  return result;
}

```

## disassembly

```asm
0x18003bea0  sub     rsp, 28h
0x18003bea4  lea     rcx, stru_1800534B8; lpCriticalSection
0x18003beab  call    cs:__imp_DeleteCriticalSection
0x18003beb1  mov     rcx, cs:qword_1800534E0; Block
0x18003beb8  test    rcx, rcx
0x18003bebb  jz      short loc_18003BECD
0x18003bebd  call    free
0x18003bec2  xor     eax, eax
0x18003bec4  mov     cs:qword_1800534E0, rax
0x18003becb  jmp     short loc_18003BECF
0x18003becd  xor     eax, eax
0x18003becf  mov     cs:qword_1800534E8, rax
0x18003bed6  add     rsp, 28h
0x18003beda  retn
```
