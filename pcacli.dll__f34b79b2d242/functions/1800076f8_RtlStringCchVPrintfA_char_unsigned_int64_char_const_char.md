# RtlStringCchVPrintfA(char *,unsigned __int64,char const *,char *)

- ea: `0x1800076f8`
- end: `0x180007732`
- name: `?RtlStringCchVPrintfA@@YAJPEAD_KPEBD0@Z`
- size: `58`
- prototype: `__int64 __fastcall(char *, unsigned __int64, const char *, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800092ac`
- `0x180009cf0`

## callees

- `0x1800071a0`
- `0x1800076f8`

## pseudocode

```c
__int64 __fastcall RtlStringCchVPrintfA(char *a1, unsigned __int64 a2, const char *a3, char *a4)
{
  __int64 result; // rax

  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
    return RtlStringVPrintfWorkerA(a1, a2, a3, a3, a4);
  result = 3221225485LL;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x1800076f8  sub     rsp, 38h
0x1800076fc  test    rdx, rdx
0x1800076ff  jz      short loc_180007720
0x180007701  cmp     rdx, 7FFFFFFFh
0x180007708  jbe     short loc_180007711
0x18000770a  mov     eax, 0C000000Dh
0x18000770f  jmp     short loc_18000772A
0x180007711  mov     [rsp+38h+var_18], r9
0x180007716  mov     r9, r8
0x180007719  call    RtlStringVPrintfWorkerA
0x18000771e  jmp     short loc_18000772D
0x180007720  mov     eax, 0C000000Dh
0x180007725  test    rdx, rdx
0x180007728  jz      short loc_18000772D
0x18000772a  mov     byte ptr [rcx], 0
0x18000772d  add     rsp, 38h
0x180007731  retn
```
