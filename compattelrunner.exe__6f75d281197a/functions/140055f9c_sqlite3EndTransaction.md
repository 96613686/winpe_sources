# sqlite3EndTransaction

- ea: `0x140055f9c`
- end: `0x140056010`
- name: `sqlite3EndTransaction`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a40bc`

## callees

- `0x14004bdbc`
- `0x140055f9c`
- `0x14005f5fc`
- `0x1400738a0`

## string_xrefs

- `0x140055fb4`: `COMMIT`
- `0x140055fbb`: `ROLLBACK`

## pseudocode

```c
__int64 __fastcall sqlite3EndTransaction(__int64 a1, int a2)
{
  const char *v2; // r8
  BOOL v4; // edi
  __int64 result; // rax

  v2 = "ROLLBACK";
  v4 = a2 == 12;
  if ( a2 != 12 )
    v2 = "COMMIT";
  result = sqlite3AuthCheck(a1, 22, (_DWORD)v2, 0, 0);
  if ( !(_DWORD)result )
  {
    result = sqlite3GetVdbe(a1);
    if ( result )
      return sqlite3VdbeAddOp3(result, 1, 1, v4, 0);
  }
  return result;
}

```

## disassembly

```asm
0x140055f9c  mov     [rsp+arg_0], rbx
0x140055fa1  push    rdi
0x140055fa2  sub     rsp, 30h
0x140055fa6  xor     edi, edi
0x140055fa8  mov     [rsp+38h+var_18], 0
0x140055fb1  cmp     edx, 0Ch
0x140055fb4  lea     rax, aCommit; "COMMIT"
0x140055fbb  lea     r8, aRollback; "ROLLBACK"
0x140055fc2  mov     rbx, rcx
0x140055fc5  setz    dil
0x140055fc9  cmovnz  r8, rax
0x140055fcd  xor     r9d, r9d
0x140055fd0  lea     edx, [r9+16h]
0x140055fd4  call    sqlite3AuthCheck
0x140055fd9  test    eax, eax
0x140055fdb  jnz     short loc_140056005
0x140055fdd  mov     rcx, rbx
0x140055fe0  call    sqlite3GetVdbe
0x140055fe5  test    rax, rax
0x140055fe8  jz      short loc_140056005
0x140055fea  mov     edx, 1
0x140055fef  mov     dword ptr [rsp+38h+var_18], 0
0x140055ff7  mov     r8d, edx
0x140055ffa  mov     r9d, edi
0x140055ffd  mov     rcx, rax
0x140056000  call    sqlite3VdbeAddOp3
0x140056005  mov     rbx, [rsp+38h+arg_0]
0x14005600a  add     rsp, 30h
0x14005600e  pop     rdi
0x14005600f  retn
```
