# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x18001a5fc`
- end: `0x18001a64e`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `82`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015794`
- `0x180018d60`
- `0x180018dd0`
- `0x180018ec0`
- `0x180018ff4`
- `0x18001a39c`
- `0x180028d10`
- `0x18002cdfc`
- `0x18002e894`
- `0x180033010`
- `0x180040cd0`
- `0x1800441ec`
- `0x180054cf8`
- `0x18005aa94`
- `0x18005aae4`
- `0x18005ab60`
- `0x18005abc4`
- `0x18005ac3c`
- `0x18005acf0`
- `0x18005ad84`
- `0x18005c54c`
- `0x18005f95c`
- `0x18005fa00`
- `0x180062cd8`
- `0x18006495c`
- `0x18006be80`

## callees

- `0x18001a5fc`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18001a635`
- `ntdll!EtwEventWriteTransfer` at `0x18001a635`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18009A008;
  if ( qword_18009A008 )
  {
    *(_QWORD *)a5 = qword_18009A008;
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
  return EtwEventWriteTransfer(NCSI_EVT_GUID_Context, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x18001a5fc  sub     rsp, 38h
0x18001a600  mov     rcx, cs:qword_18009A008
0x18001a607  mov     rax, [rsp+38h+arg_20]
0x18001a60c  test    rcx, rcx
0x18001a60f  jnz     short loc_18001A640
0x18001a611  mov     [rax], rcx
0x18001a614  xor     r8d, r8d
0x18001a617  mov     [rax+8], ecx
0x18001a61a  mov     [rax+0Ch], r8d
0x18001a61e  xor     r8d, r8d
0x18001a621  mov     rcx, cs:NCSI_EVT_GUID_Context
0x18001a628  mov     [rsp+38h+var_10], rax
0x18001a62d  mov     [rsp+38h+var_18], r9d
0x18001a632  xor     r9d, r9d
0x18001a635  call    cs:__imp_EtwEventWriteTransfer
0x18001a63b  add     rsp, 38h
0x18001a63f  retn
0x18001a640  mov     [rax], rcx
0x18001a643  mov     r8d, 2
0x18001a649  movzx   ecx, word ptr [rcx]
0x18001a64c  jmp     short loc_18001A617
```
