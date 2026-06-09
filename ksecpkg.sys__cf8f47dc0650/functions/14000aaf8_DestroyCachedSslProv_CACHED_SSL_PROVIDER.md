# DestroyCachedSslProv(CACHED_SSL_PROVIDER *)

- ea: `0x14000aaf8`
- end: `0x14000ab44`
- name: `?DestroyCachedSslProv@@YAXPEAUCACHED_SSL_PROVIDER@@@Z`
- size: `76`
- prototype: `void __fastcall(struct CACHED_SSL_PROVIDER *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002510`
- `0x14000aaac`

## callees

- `0x14000aaf8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ab29`
- `cng!SslFreeObject` at `0x14000ab0b`
- `cng!SslFreeObject` at `0x14000ab0b`

## pseudocode

```c
void __fastcall DestroyCachedSslProv(struct CACHED_SSL_PROVIDER *a1)
{
  __int64 v2; // rcx
  void *v3; // rcx

  v2 = *(_QWORD *)a1;
  if ( v2 )
  {
    SslFreeObject(v2, 0);
    *(_QWORD *)a1 = 0;
  }
  v3 = (void *)*((_QWORD *)a1 + 1);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *((_QWORD *)a1 + 1) = 0;
  }
}

```

## disassembly

```asm
0x14000aaf8  push    rbx
0x14000aafa  sub     rsp, 20h
0x14000aafe  mov     rbx, rcx
0x14000ab01  mov     rcx, [rcx]
0x14000ab04  test    rcx, rcx
0x14000ab07  jz      short loc_14000AB1E
0x14000ab09  xor     edx, edx
0x14000ab0b  call    cs:__imp_SslFreeObject
0x14000ab12  nop     dword ptr [rax+rax+00h]
0x14000ab17  mov     qword ptr [rbx], 0
0x14000ab1e  mov     rcx, [rbx+8]; P
0x14000ab22  test    rcx, rcx
0x14000ab25  jz      short loc_14000AB3D
0x14000ab27  xor     edx, edx; Tag
0x14000ab29  call    cs:__imp_ExFreePoolWithTag
0x14000ab30  nop     dword ptr [rax+rax+00h]
0x14000ab35  mov     qword ptr [rbx+8], 0
0x14000ab3d  add     rsp, 20h
0x14000ab41  pop     rbx
0x14000ab42  retn
```
