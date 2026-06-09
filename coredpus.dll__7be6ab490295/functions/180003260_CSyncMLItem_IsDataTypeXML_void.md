# CSyncMLItem::IsDataTypeXML(void)

- ea: `0x180003260`
- end: `0x1800032c3`
- name: `?IsDataTypeXML@CSyncMLItem@@QEBAHXZ`
- size: `99`
- prototype: `__int64 __fastcall(CSyncMLItem *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007e80`
- `0x180008620`
- `0x18000a0d0`

## callees

- `0x180003260`
- `0x180003330`
- `0x180003350`

## pseudocode

```c
_BOOL8 __fastcall CSyncMLItem::IsDataTypeXML(CSyncMLItem *this)
{
  __int64 i; // rax
  unsigned int v2; // eax
  CSyncMLMeta *v3; // r9

  if ( *((_QWORD *)this + 2) )
  {
LABEL_6:
    v2 = CSyncMLMeta::SyncMLPropToIndex(0);
    return (unsigned int)CSyncMLMeta::GetPropertyEx(v3, v2, (void *)1) == 13;
  }
  else
  {
    for ( i = *((_QWORD *)this + 1); i; i = *(_QWORD *)(i + 136) )
    {
      if ( *(_QWORD *)(i + 96) )
        goto LABEL_6;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180003260  sub     rsp, 28h
0x180003264  mov     r9, [rcx+10h]
0x180003268  test    r9, r9
0x18000326b  jnz     short loc_180003288
0x18000326d  mov     rax, [rcx+8]
0x180003271  test    rax, rax
0x180003274  jz      short loc_1800032B0
0x180003276  mov     r9, [rax+60h]
0x18000327a  test    r9, r9
0x18000327d  jnz     short loc_180003288
0x18000327f  mov     rax, [rax+88h]
0x180003286  jmp     short loc_180003271
0x180003288  xor     ecx, ecx
0x18000328a  call    ?SyncMLPropToIndex@CSyncMLMeta@@CAKW4SyncMLProp@@@Z; CSyncMLMeta::SyncMLPropToIndex(SyncMLProp)
0x18000328f  mov     edx, eax; unsigned int
0x180003291  mov     r8d, 1; void *
0x180003297  mov     rcx, r9; this
0x18000329a  call    ?GetPropertyEx@CSyncMLMeta@@AEBAPEAXKPEAX@Z; CSyncMLMeta::GetPropertyEx(ulong,void *)
0x18000329f  mov     rcx, rax
0x1800032a2  xor     eax, eax
0x1800032a4  cmp     ecx, 0Dh
0x1800032a7  setz    al
0x1800032aa  add     rsp, 28h
0x1800032ae  retn
0x1800032b0  xor     eax, eax
0x1800032b2  mov     ecx, 1
0x1800032b7  cmp     ecx, 0Dh
0x1800032ba  setz    al
0x1800032bd  add     rsp, 28h
0x1800032c1  retn
```
