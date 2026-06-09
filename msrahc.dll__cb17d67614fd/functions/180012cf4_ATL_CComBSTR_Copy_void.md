# ATL::CComBSTR::Copy(void)

- ea: `0x180012cf4`
- end: `0x180012d24`
- name: `?Copy@CComBSTR@ATL@@QEBAPEAGXZ`
- size: `48`
- prototype: `BSTR __fastcall(LPCSTR *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180014030`
- `0x180014070`
- `0x180014260`

## callees

- `0x180012cf4`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x180012d0d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180012d0d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180012d1d`

## pseudocode

```c
BSTR __fastcall ATL::CComBSTR::Copy(LPCSTR *this)
{
  CHAR *v2; // rcx
  UINT v4; // eax

  v2 = (CHAR *)*this;
  if ( !v2 )
    return 0;
  v4 = SysStringByteLen((BSTR)v2);
  return SysAllocStringByteLen(*this, v4);
}

```

## disassembly

```asm
0x180012cf4  push    rbx
0x180012cf6  sub     rsp, 20h
0x180012cfa  mov     rbx, rcx
0x180012cfd  mov     rcx, [rcx]; bstr
0x180012d00  test    rcx, rcx
0x180012d03  jnz     short loc_180012D0D
0x180012d05  xor     eax, eax
0x180012d07  add     rsp, 20h
0x180012d0b  pop     rbx
0x180012d0c  retn
0x180012d0d  call    cs:__imp_SysStringByteLen
0x180012d13  mov     rcx, [rbx]
0x180012d16  mov     edx, eax
0x180012d18  add     rsp, 20h
0x180012d1c  pop     rbx
0x180012d1d  jmp     cs:__imp_SysAllocStringByteLen
```
