# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180009fe4`
- end: `0x18000a038`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `84`
- prototype: ``
- caller_count: `24`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a040`
- `0x18000a154`
- `0x18001177c`
- `0x180011ae0`
- `0x1800120c4`
- `0x180012140`
- `0x18001acdc`
- `0x18001b67c`
- `0x18001cfa0`
- `0x18001d080`
- `0x18001d124`
- `0x18001d1fc`
- `0x18001d298`
- `0x18001d328`
- `0x18001d3d0`
- `0x180020984`
- `0x180026488`
- `0x180026850`
- `0x180029d84`
- `0x18002f444`
- `0x180036db1`
- `0x180036f32`
- `0x180037269`
- `0x18003756e`

## callees

- `0x180009fe4`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18000a026`
- `ntdll!EtwEventWriteTransfer` at `0x18000a026`

## pseudocode

```c
__int64 __fastcall McGenEventWrite_EtwEventWriteTransfer(_QWORD *a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  unsigned __int16 *v5; // r8
  int v6; // r10d

  v5 = (unsigned __int16 *)a1[1];
  if ( v5 )
  {
    *(_QWORD *)a5 = v5;
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
  return EtwEventWriteTransfer(*a1, a2, 0, 0, a4, a5);
}

```

## disassembly

```asm
0x180009fe4  sub     rsp, 38h
0x180009fe8  mov     r8, [rcx+8]
0x180009fec  mov     rax, [rsp+38h+arg_20]
0x180009ff1  test    r8, r8
0x180009ff4  jnz     short loc_180009FFE
0x180009ff6  mov     [rax], r8
0x180009ff9  xor     r10d, r10d
0x180009ffc  jmp     short loc_18000A00B
0x180009ffe  mov     [rax], r8
0x18000a001  mov     r10d, 2
0x18000a007  movzx   r8d, word ptr [r8]
0x18000a00b  mov     [rax+8], r8d
0x18000a00f  xor     r8d, r8d
0x18000a012  mov     [rsp+38h+var_10], rax
0x18000a017  mov     [rax+0Ch], r10d
0x18000a01b  mov     rcx, [rcx]
0x18000a01e  mov     [rsp+38h+var_18], r9d
0x18000a023  xor     r9d, r9d
0x18000a026  call    cs:__imp_EtwEventWriteTransfer
0x18000a02d  nop     dword ptr [rax+rax+00h]
0x18000a032  add     rsp, 38h
0x18000a036  retn
```
