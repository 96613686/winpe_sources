# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18000a07c`
- end: `0x18000a0ce`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a0d4`
- `0x18000c6f4`
- `0x180010020`
- `0x1800100e0`
- `0x180012d14`
- `0x180012df0`
- `0x180012ec4`
- `0x180012fac`
- `0x1800142ac`
- `0x1800143b0`

## callees

- `0x18000a07c`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000a0c3`
- `ntdll!EtwEventWriteTransfer` at `0x18000a0c3`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18002B008;
  if ( qword_18002B008 )
  {
    *(_QWORD *)a5 = qword_18002B008;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    *(_QWORD *)a5 = 0;
    v6 = 0;
  }
  *(_DWORD *)(a5 + 8) = (_DWORD)v5;
  *(_DWORD *)(a5 + 12) = v6;
  return EtwEventWriteTransfer(S_Perflib_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18000a07c  sub     rsp, 38h
0x18000a080  mov     rcx, cs:qword_18002B008
0x18000a087  mov     rax, [rsp+38h+arg_20]
0x18000a08c  test    rcx, rcx
0x18000a08f  jnz     short loc_18000A099
0x18000a091  mov     [rax], rcx
0x18000a094  xor     r8d, r8d
0x18000a097  jmp     short loc_18000A0A5
0x18000a099  mov     [rax], rcx
0x18000a09c  mov     r8d, 2
0x18000a0a2  movzx   ecx, word ptr [rcx]
0x18000a0a5  mov     [rax+8], ecx
0x18000a0a8  mov     [rax+0Ch], r8d
0x18000a0ac  xor     r8d, r8d
0x18000a0af  mov     rcx, cs:S_Perflib_Context
0x18000a0b6  mov     [rsp+38h+var_10], rax
0x18000a0bb  mov     [rsp+38h+var_18], r9d
0x18000a0c0  xor     r9d, r9d
0x18000a0c3  call    cs:__imp_EtwEventWriteTransfer
0x18000a0c9  add     rsp, 38h
0x18000a0cd  retn
```
