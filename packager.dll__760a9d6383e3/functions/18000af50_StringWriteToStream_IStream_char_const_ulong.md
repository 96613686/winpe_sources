# StringWriteToStream(IStream *,char const *,ulong *)

- ea: `0x18000af50`
- end: `0x18000afae`
- name: `?StringWriteToStream@@YAJPEAUIStream@@PEBDPEAK@Z`
- size: `94`
- prototype: `__int64 __fastcall(struct IStream *, const char *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075c4`
- `0x1800080a8`
- `0x180008dcc`

## callees

- `0x18000af50`
- `0x18000e010`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18000af73`
- `KERNEL32!lstrlenA` at `0x18000af73`

## pseudocode

```c
__int64 __fastcall StringWriteToStream(struct IStream *a1, const char *a2, unsigned int *a3)
{
  int v6; // eax
  __int64 result; // rax
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  v6 = lstrlenA(a2);
  result = ((__int64 (__fastcall *)(struct IStream *, const char *, _QWORD, int *))a1->lpVtbl->Write)(
             a1,
             a2,
             (unsigned int)(v6 + 1),
             &v8);
  if ( (int)result >= 0 )
    *a3 += v8;
  return result;
}

```

## disassembly

```asm
0x18000af50  mov     [rsp+arg_8], rbx
0x18000af55  mov     [rsp+arg_10], rsi
0x18000af5a  push    rdi
0x18000af5b  sub     rsp, 30h
0x18000af5f  mov     rdi, rcx
0x18000af62  mov     [rsp+38h+arg_0], 0
0x18000af6a  mov     rcx, rdx; lpString
0x18000af6d  mov     rsi, r8
0x18000af70  mov     rbx, rdx
0x18000af73  call    cs:__imp_lstrlenA
0x18000af79  lea     r9, [rsp+38h+arg_0]
0x18000af7e  mov     rdx, rbx
0x18000af81  mov     rcx, rdi
0x18000af84  lea     r8d, [rax+1]
0x18000af88  mov     rax, [rdi]
0x18000af8b  mov     rax, [rax+20h]
0x18000af8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af94  test    eax, eax
0x18000af96  js      short loc_18000AF9E
0x18000af98  mov     ecx, [rsp+38h+arg_0]
0x18000af9c  add     [rsi], ecx
0x18000af9e  mov     rbx, [rsp+38h+arg_8]
0x18000afa3  mov     rsi, [rsp+38h+arg_10]
0x18000afa8  add     rsp, 30h
0x18000afac  pop     rdi
0x18000afad  retn
```
