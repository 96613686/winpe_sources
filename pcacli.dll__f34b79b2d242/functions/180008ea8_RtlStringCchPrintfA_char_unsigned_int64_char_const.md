# RtlStringCchPrintfA(char *,unsigned __int64,char const *,...)

- ea: `0x180008ea8`
- end: `0x180008efa`
- name: `?RtlStringCchPrintfA@@YAJPEAD_KPEBDZZ`
- size: `82`
- prototype: `__int64(char *, unsigned __int64, const char *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007200`
- `0x180008c40`
- `0x1800092ac`
- `0x180009cf0`
- `0x18000a208`

## callees

- `0x1800071a0`
- `0x180008ea8`

## pseudocode

```c
__int64 RtlStringCchPrintfA(char *a1, unsigned __int64 a2, const char *a3, ...)
{
  __int64 result; // rax
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( !a2 )
    return 3221225485LL;
  if ( a2 <= 0x7FFFFFFF )
    return RtlStringVPrintfWorkerA(a1, a2, a3, a3, (__int64 *)va);
  result = 3221225485LL;
  *a1 = 0;
  return result;
}

```

## disassembly

```asm
0x180008ea8  mov     [rsp+arg_10], r8
0x180008ead  mov     [rsp+arg_18], r9
0x180008eb2  sub     rsp, 48h
0x180008eb6  test    rdx, rdx
0x180008eb9  jz      short loc_180008EE8
0x180008ebb  cmp     rdx, 7FFFFFFFh
0x180008ec2  jbe     short loc_180008ECB
0x180008ec4  mov     eax, 0C000000Dh
0x180008ec9  jmp     short loc_180008EF2
0x180008ecb  lea     rax, [rsp+48h+arg_18]
0x180008ed0  mov     [rsp+48h+var_18], 0
0x180008ed9  mov     r9, r8
0x180008edc  mov     [rsp+48h+var_28], rax
0x180008ee1  call    RtlStringVPrintfWorkerA
0x180008ee6  jmp     short loc_180008EF5
0x180008ee8  mov     eax, 0C000000Dh
0x180008eed  test    rdx, rdx
0x180008ef0  jz      short loc_180008EF5
0x180008ef2  mov     byte ptr [rcx], 0
0x180008ef5  add     rsp, 48h
0x180008ef9  retn
```
