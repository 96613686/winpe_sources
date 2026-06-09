# HrAStrToBStr(char const *,ushort * *)

- ea: `0x180050bb8`
- end: `0x180050c0d`
- name: `?HrAStrToBStr@@YAJPEBDPEAPEAG@Z`
- size: `85`
- prototype: `int(const char *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800514a0`
- `0x1800525d8`

## callees

- `0x180050bb8`
- `0x180050c14`
- `0x180052948`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050bfa`

## pseudocode

```c
__int64 __fastcall HrAStrToBStr(const char *a1, unsigned __int16 **a2)
{
  unsigned int v3; // edi
  LPVOID pv; // [rsp+40h] [rbp+18h] BYREF

  pv = 0;
  v3 = HrAStrToWStr(a1, (unsigned __int16 **)&pv);
  if ( !v3 )
    v3 = HrWStrToBStr((const unsigned __int16 *)pv, a2);
  if ( pv )
    CoTaskMemFree(pv);
  return v3;
}

```

## disassembly

```asm
0x180050bb8  mov     [rsp+arg_0], rsi
0x180050bbd  push    rdi
0x180050bbe  sub     rsp, 20h
0x180050bc2  mov     rsi, rdx
0x180050bc5  mov     [rsp+28h+pv], 0
0x180050bce  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x180050bd3  call    ?HrAStrToWStr@@YAJPEBDPEAPEAG@Z; HrAStrToWStr(char const *,ushort * *)
0x180050bd8  mov     edi, eax
0x180050bda  test    eax, eax
0x180050bdc  jnz     short loc_180050BED
0x180050bde  mov     rcx, [rsp+28h+pv]; unsigned __int16 *
0x180050be3  mov     rdx, rsi; unsigned __int16 **
0x180050be6  call    ?HrWStrToBStr@@YAJPEBGPEAPEAG@Z; HrWStrToBStr(ushort const *,ushort * *)
0x180050beb  mov     edi, eax
0x180050bed  cmp     [rsp+28h+pv], 0
0x180050bf3  jz      short loc_180050C00
0x180050bf5  mov     rcx, [rsp+28h+pv]; pv
0x180050bfa  call    cs:__imp_CoTaskMemFree
0x180050c00  mov     rsi, [rsp+28h+arg_0]
0x180050c05  mov     eax, edi
0x180050c07  add     rsp, 20h
0x180050c0b  pop     rdi
0x180050c0c  retn
```
