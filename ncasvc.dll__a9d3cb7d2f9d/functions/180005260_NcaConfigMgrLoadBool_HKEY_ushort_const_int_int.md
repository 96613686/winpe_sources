# NcaConfigMgrLoadBool(HKEY__ *,ushort const *,int,int *)

- ea: `0x180005260`
- end: `0x1800052c2`
- name: `?NcaConfigMgrLoadBool@@YAJPEAUHKEY__@@PEBGHPEAH@Z`
- size: `98`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, __int64, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180005770`

## callees

- `0x180005260`
- `0x18001a654`

## pseudocode

```c
__int64 __fastcall NcaConfigMgrLoadBool(HKEY a1, const unsigned __int16 *a2, __int64 a3, int *a4)
{
  int DWord; // ecx
  __int64 result; // rax
  int v7; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF

  Data = 0;
  v7 = 0;
  *a4 = 0;
  DWord = NcaRegQueryDWord(a1, 0, a2, (LPBYTE)&Data, (__int64)&v7);
  if ( v7 == 1 )
    *a4 = Data != 0;
  result = 0;
  if ( DWord == -2147024882 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x180005260  mov     rax, rsp
0x180005263  mov     [rax+18h], r8d
0x180005267  push    rbx
0x180005268  sub     rsp, 30h
0x18000526c  mov     dword ptr [rax+20h], 0
0x180005273  mov     rbx, r9
0x180005276  mov     dword ptr [rax+18h], 0
0x18000527d  lea     rax, [rax+18h]
0x180005281  mov     dword ptr [r9], 0
0x180005288  mov     r8, rdx; lpValueName
0x18000528b  lea     r9, [rsp+38h+Data]; lpData
0x180005290  mov     [rsp+38h+var_18], rax; __int64
0x180005295  xor     edx, edx; lpSubKey
0x180005297  call    NcaRegQueryDWord
0x18000529c  cmp     [rsp+38h+arg_10], 1
0x1800052a1  mov     ecx, eax
0x1800052a3  jnz     short loc_1800052B0
0x1800052a5  xor     eax, eax
0x1800052a7  cmp     [rsp+38h+Data], eax
0x1800052ab  setnz   al
0x1800052ae  mov     [rbx], eax
0x1800052b0  xor     eax, eax
0x1800052b2  cmp     ecx, 8007000Eh
0x1800052b8  cmovz   eax, ecx
0x1800052bb  add     rsp, 30h
0x1800052bf  pop     rbx
0x1800052c0  retn
```
