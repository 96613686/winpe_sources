# McGenEventWrite_EtwEventWriteTransfer

- ea: `0x180004594`
- end: `0x1800045e1`
- name: `McGenEventWrite_EtwEventWriteTransfer`
- size: `77`
- prototype: ``
- caller_count: `25`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a10`
- `0x180001c10`
- `0x180003030`
- `0x1800035f0`
- `0x1800052c0`
- `0x180005b5c`
- `0x180007310`
- `0x180007c50`
- `0x1800080e0`
- `0x180008cc0`
- `0x18000a320`
- `0x18000b2e0`
- `0x18000be7c`
- `0x18000bff4`
- `0x18000c2ec`
- `0x180011650`
- `0x1800127c0`
- `0x180013774`
- `0x180013800`
- `0x180013910`
- `0x180013a20`
- `0x180013bd0`
- `0x180014af0`
- `0x180014b4c`
- `0x180014c84`

## callees

- `0x180004594`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800045c7`
- `ntdll!EtwEventWriteTransfer` at `0x1800045c7`

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
0x180004594  sub     rsp, 38h
0x180004598  mov     r8, [rcx+8]
0x18000459c  mov     rax, [rsp+38h+arg_20]
0x1800045a1  test    r8, r8
0x1800045a4  jnz     short loc_1800045D2
0x1800045a6  mov     [rax], r8
0x1800045a9  xor     r10d, r10d
0x1800045ac  mov     [rax+8], r8d
0x1800045b0  xor     r8d, r8d
0x1800045b3  mov     [rsp+38h+var_10], rax
0x1800045b8  mov     [rax+0Ch], r10d
0x1800045bc  mov     rcx, [rcx]
0x1800045bf  mov     [rsp+38h+var_18], r9d
0x1800045c4  xor     r9d, r9d
0x1800045c7  call    cs:__imp_EtwEventWriteTransfer
0x1800045cd  add     rsp, 38h
0x1800045d1  retn
0x1800045d2  mov     [rax], r8
0x1800045d5  mov     r10d, 2
0x1800045db  movzx   r8d, word ptr [r8]
0x1800045df  jmp     short loc_1800045AC
```
