# lldpGetPortAdminConfig

- ea: `0x14000e614`
- end: `0x14000e65b`
- name: `lldpGetPortAdminConfig`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000ec14`
- `0x14000f0b0`

## callees

- `0x140004340`
- `0x14000e614`

## pseudocode

```c
__int64 __fastcall lldpGetPortAdminConfig(__int64 a1, __int64 a2)
{
  __int64 v2; // r11
  unsigned int v3; // r10d
  __int64 result; // rax
  __int64 v5; // r10
  __int64 v6; // rdx
  __int64 v7; // r9

  *(_DWORD *)a2 = 1;
  v2 = a1;
  *(_QWORD *)(a2 + 8) = 44;
  v3 = 0;
  do
  {
    result = lldpGetConfig(v2, v3);
    v6 = 3 * v5;
    v3 = v5 + 1;
    *(_DWORD *)((unsigned int)dword_14000B064[2 * v6] + v7) = result;
  }
  while ( v3 < 7 );
  return result;
}

```

## disassembly

```asm
0x14000e614  sub     rsp, 28h
0x14000e618  mov     r9, rdx
0x14000e61b  mov     dword ptr [rdx], 1
0x14000e621  mov     r11, rcx
0x14000e624  mov     qword ptr [rdx+8], 2Ch ; ','
0x14000e62c  xor     r10d, r10d
0x14000e62f  mov     edx, r10d
0x14000e632  mov     rcx, r11
0x14000e635  call    lldpGetConfig
0x14000e63a  lea     rdx, [r10+r10*2]
0x14000e63e  inc     r10d
0x14000e641  lea     rcx, dword_14000B064
0x14000e648  mov     ecx, [rcx+rdx*8]
0x14000e64b  mov     [rcx+r9], eax
0x14000e64f  cmp     r10d, 7
0x14000e653  jb      short loc_14000E62F
0x14000e655  add     rsp, 28h
0x14000e659  retn
```
