# ResolveLocalILinkInfo(_ilinkinfoW const *,ushort *,int,ulong)

- ea: `0x180001840`
- end: `0x1800018b9`
- name: `?ResolveLocalILinkInfo@@YAHPEBU_ilinkinfoW@@PEAGHK@Z`
- size: `121`
- prototype: `__int64 __fastcall(const CHAR *, unsigned __int16 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001780`

## callees

- `0x1800019e0`
- `0x1800031f0`
- `0x180005750`

## pseudocode

```c
__int64 __fastcall ResolveLocalILinkInfo(const CHAR *a1, unsigned __int16 *a2, __int64 a3, unsigned int a4)
{
  int v8; // [rsp+20h] [rbp-238h]
  unsigned __int16 v9[264]; // [rsp+30h] [rbp-228h] BYREF

  GetLocalPathFromILinkInfo(a1, v9);
  return SearchForLocalPath((const struct _volumeid *)&a1[*((unsigned int *)a1 + 3)], v9, (a4 >> 5) & 1, a2, v8);
}

```

## disassembly

```asm
0x180001840  mov     [rsp+arg_10], rbx
0x180001845  mov     [rsp+arg_18], rsi
0x18000184a  push    rdi
0x18000184b  sub     rsp, 250h
0x180001852  mov     rax, cs:__security_cookie
0x180001859  xor     rax, rsp
0x18000185c  mov     [rsp+258h+var_18], rax
0x180001864  mov     rdi, rdx
0x180001867  mov     esi, r9d
0x18000186a  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18000186f  mov     rbx, rcx
0x180001872  call    ?GetLocalPathFromILinkInfo@@YAXPEBU_ilinkinfoW@@PEAGH@Z; GetLocalPathFromILinkInfo(_ilinkinfoW const *,ushort *,int)
0x180001877  mov     ecx, [rbx+0Ch]
0x18000187a  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x18000187f  shr     esi, 5
0x180001882  add     rcx, rbx; struct _volumeid *
0x180001885  and     esi, 1
0x180001888  mov     r9, rdi; unsigned __int16 *
0x18000188b  mov     r8d, esi; unsigned int
0x18000188e  call    ?SearchForLocalPath@@YAHPEBU_volumeid@@PEBGKPEAGH@Z; SearchForLocalPath(_volumeid const *,ushort const *,ulong,ushort *,int)
0x180001893  mov     rcx, [rsp+258h+var_18]
0x18000189b  xor     rcx, rsp; StackCookie
0x18000189e  call    __security_check_cookie
0x1800018a3  lea     r11, [rsp+258h+var_8]
0x1800018ab  mov     rbx, [r11+20h]
0x1800018af  mov     rsi, [r11+28h]
0x1800018b3  mov     rsp, r11
0x1800018b6  pop     rdi
0x1800018b7  retn
```
