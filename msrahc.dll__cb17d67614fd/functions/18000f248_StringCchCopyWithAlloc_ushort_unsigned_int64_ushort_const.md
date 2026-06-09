# StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)

- ea: `0x18000f248`
- end: `0x18000f2cb`
- name: `?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z`
- size: `131`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d520`
- `0x18000da10`
- `0x18000efc0`
- `0x18000f17c`
- `0x180018730`

## callees

- `0x180006b04`
- `0x18000f248`
- `0x18000f2d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f290`

## pseudocode

```c
__int64 __fastcall StringCchCopyWithAlloc(unsigned __int16 **a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  unsigned __int64 v6; // rdi
  unsigned __int16 *v7; // rax
  unsigned __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  if ( !a1 || !a3 )
    return 2147942487LL;
  v8 = 0;
  result = StringCchLengthW(a3, a2 - 1, &v8);
  if ( (int)result >= 0 )
  {
    v6 = v8;
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2 * v8 + 2);
    *a1 = v7;
    if ( v7 )
      return StringCchCopyW(v7, v6 + 1, (size_t *)a3);
    else
      return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000f248  mov     rax, rsp
0x18000f24b  mov     [rax+10h], rbx
0x18000f24f  mov     [rax+18h], rsi
0x18000f253  push    rdi
0x18000f254  sub     rsp, 20h
0x18000f258  mov     rbx, r8
0x18000f25b  mov     rsi, rcx
0x18000f25e  test    rcx, rcx
0x18000f261  jz      short loc_18000F2B6
0x18000f263  test    rbx, rbx
0x18000f266  jz      short loc_18000F2B6
0x18000f268  dec     rdx; unsigned __int64
0x18000f26b  mov     qword ptr [rax+8], 0
0x18000f273  lea     r8, [rax+8]; unsigned __int64 *
0x18000f277  mov     rcx, rbx; unsigned __int16 *
0x18000f27a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f27f  test    eax, eax
0x18000f281  js      short loc_18000F2BB
0x18000f283  mov     rdi, [rsp+28h+arg_0]
0x18000f288  lea     rcx, ds:2[rdi*2]; cb
0x18000f290  call    cs:__imp_CoTaskMemAlloc
0x18000f296  mov     [rsi], rax
0x18000f299  test    rax, rax
0x18000f29c  jnz     short loc_18000F2A5
0x18000f29e  mov     eax, 8007000Eh
0x18000f2a3  jmp     short loc_18000F2BB
0x18000f2a5  lea     rdx, [rdi+1]; unsigned __int64
0x18000f2a9  mov     r8, rbx; unsigned __int16 *
0x18000f2ac  mov     rcx, rax; unsigned __int16 *
0x18000f2af  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f2b4  jmp     short loc_18000F2BB
0x18000f2b6  mov     eax, 80070057h
0x18000f2bb  mov     rbx, [rsp+28h+arg_8]
0x18000f2c0  mov     rsi, [rsp+28h+arg_10]
0x18000f2c5  add     rsp, 20h
0x18000f2c9  pop     rdi
0x18000f2ca  retn
```
