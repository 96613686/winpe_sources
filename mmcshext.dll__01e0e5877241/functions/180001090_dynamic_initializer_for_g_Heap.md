# _dynamic_initializer_for__g_Heap__

- ea: `0x180001090`
- end: `0x180001133`
- name: `_dynamic_initializer_for__g_Heap__`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001090`
- `0x1800096e8`
- `0x180009c48`

## import_xrefs

- `KERNEL32!HeapCreate` at `0x1800010b7`
- `KERNEL32!HeapCreate` at `0x1800010b7`
- `KERNEL32!GetLastError` at `0x180001115`
- `KERNEL32!GetLastError` at `0x180001115`
- `KERNEL32!GetSystemInfo` at `0x1800010aa`
- `KERNEL32!GetSystemInfo` at `0x1800010aa`

## pseudocode

```c
_UNKNOWN **dynamic_initializer_for__g_Heap__()
{
  _UNKNOWN **result; // rax
  DWORD LastError; // eax
  __int64 v2; // rdx
  __int64 v3; // r8
  struct _SYSTEM_INFO v4; // [rsp+20h] [rbp-38h] BYREF

  memset(&v4, 0, sizeof(v4));
  GetSystemInfo(&v4);
  qword_1800128C8 = HeapCreate(0, 0, 0);
  if ( qword_1800128C8 )
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      return (_UNKNOWN **)WPP_SF_q(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            16,
                            WPP_cdac69d58e113e0c8ccf6cdb6e0ba022_Traceguids,
                            qword_1800128C8);
  }
  else
  {
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      return (_UNKNOWN **)WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v3, LastError);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001090  mov     rax, rsp
0x180001093  sub     rsp, 58h
0x180001097  xorps   xmm0, xmm0
0x18000109a  lea     rcx, [rax-38h]; lpSystemInfo
0x18000109e  movups  xmmword ptr [rax-38h], xmm0
0x1800010a2  movups  xmmword ptr [rax-28h], xmm0
0x1800010a6  movups  xmmword ptr [rax-18h], xmm0
0x1800010aa  call    cs:__imp_GetSystemInfo
0x1800010b0  xor     r8d, r8d; dwMaximumSize
0x1800010b3  xor     edx, edx; dwInitialSize
0x1800010b5  xor     ecx, ecx; flOptions
0x1800010b7  call    cs:__imp_HeapCreate
0x1800010bd  mov     cs:qword_1800128C8, rax
0x1800010c4  mov     r9, rax
0x1800010c7  test    rax, rax
0x1800010ca  jz      short loc_1800010FC
0x1800010cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800010d3  lea     rax, WPP_GLOBAL_Control
0x1800010da  cmp     rcx, rax
0x1800010dd  jz      short loc_18000112E
0x1800010df  cmp     byte ptr [rcx+19h], 5
0x1800010e3  jb      short loc_18000112E
0x1800010e5  mov     rcx, [rcx+10h]
0x1800010e9  lea     r8, WPP_cdac69d58e113e0c8ccf6cdb6e0ba022_Traceguids
0x1800010f0  mov     edx, 10h
0x1800010f5  call    WPP_SF_q
0x1800010fa  jmp     short loc_18000112E
0x1800010fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180001103  lea     rax, WPP_GLOBAL_Control
0x18000110a  cmp     rcx, rax
0x18000110d  jz      short loc_18000112E
0x18000110f  cmp     byte ptr [rcx+19h], 2
0x180001113  jb      short loc_18000112E
0x180001115  call    cs:__imp_GetLastError
0x18000111b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001122  mov     r9d, eax
0x180001125  mov     rcx, [rcx+10h]
0x180001129  call    WPP_SF_D
0x18000112e  add     rsp, 58h
0x180001132  retn
```
