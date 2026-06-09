# EfsRpcReadFileRaw_Downlevel

- ea: `0x180007bf0`
- end: `0x180007c1a`
- name: `EfsRpcReadFileRaw_Downlevel`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180007bf0`
- `0x180009200`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007c13`
- `RPCRT4!RpcRaiseException` at `0x180007c13`

## pseudocode

```c
__int64 __fastcall EfsRpcReadFileRaw_Downlevel(__int64 a1, void *a2)
{
  __int64 result; // rax

  if ( !a2 || !a1 )
  {
    LODWORD(result) = 5;
LABEL_6:
    RpcRaiseException(result);
  }
  result = EfsReadFileRaw(a1, a2);
  if ( (_DWORD)result )
    goto LABEL_6;
  return result;
}

```

## disassembly

```asm
0x180007bf0  sub     rsp, 28h
0x180007bf4  test    rdx, rdx
0x180007bf7  jz      short loc_180007C0C
0x180007bf9  test    rcx, rcx
0x180007bfc  jz      short loc_180007C0C
0x180007bfe  call    EfsReadFileRaw
0x180007c03  test    eax, eax
0x180007c05  jnz     short loc_180007C11
0x180007c07  add     rsp, 28h
0x180007c0b  retn
0x180007c0c  mov     eax, 5
0x180007c11  mov     ecx, eax; exception
0x180007c13  call    cs:__imp_RpcRaiseException
```
