# LuafvFreeStoreFile

- ea: `0x14001dbd0`
- end: `0x14001dca0`
- name: `LuafvFreeStoreFile`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140018f20`
- `0x14001a378`
- `0x14001dbb0`
- `0x140025820`

## callees

- `0x14001d8e0`
- `0x14001dbd0`
- `0x14001dd40`
- `0x14001de78`

## import_xrefs

- `FLTMGR!FltClose` at `0x14001dc49`
- `FLTMGR!FltClose` at `0x14001dc62`
- `FLTMGR!FltClose` at `0x14001dc49`
- `FLTMGR!FltClose` at `0x14001dc62`

## pseudocode

```c
__int64 __fastcall LuafvFreeStoreFile(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  HANDLE *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  v2 = a1[4];
  if ( v2 )
    LuafvDereferenceTableNodeEx(v2, 0, 0);
  v3 = a1[10];
  if ( v3 )
    LuafvDereferenceTableNodeEx(v3, 0, 0);
  v4 = a1[13];
  if ( v4 )
    LuafvDereferenceUserStore(v4);
  v5 = (HANDLE *)a1[12];
  if ( v5 )
  {
    if ( *v5 )
      FltClose(*v5);
    v9 = *(void **)(a1[12] + 32LL);
    if ( v9 )
      FltClose(v9);
    v10 = *(_QWORD *)(a1[12] + 16LL);
    if ( v10 )
      LuafvFreePool(v10);
    v11 = *(_QWORD *)(a1[12] + 48LL);
    if ( v11 )
      LuafvFreePool(v11);
    LuafvFreePool(a1[12]);
  }
  v6 = a1[3];
  if ( v6 )
    LuafvFreePool(v6);
  v7 = a1[9];
  if ( v7 )
    LuafvFreePool(v7);
  return LuafvFreePool(a1);
}

```

## disassembly

```asm
0x14001dbd0  push    rbx
0x14001dbd2  sub     rsp, 20h
0x14001dbd6  mov     rbx, rcx
0x14001dbd9  mov     rcx, [rcx+20h]
0x14001dbdd  test    rcx, rcx
0x14001dbe0  jz      short loc_14001DBEC
0x14001dbe2  xor     r8d, r8d
0x14001dbe5  xor     edx, edx
0x14001dbe7  call    LuafvDereferenceTableNodeEx
0x14001dbec  mov     rcx, [rbx+50h]
0x14001dbf0  test    rcx, rcx
0x14001dbf3  jz      short loc_14001DBFF
0x14001dbf5  xor     r8d, r8d
0x14001dbf8  xor     edx, edx
0x14001dbfa  call    LuafvDereferenceTableNodeEx
0x14001dbff  mov     rcx, [rbx+68h]
0x14001dc03  test    rcx, rcx
0x14001dc06  jz      short loc_14001DC0D
0x14001dc08  call    LuafvDereferenceUserStore
0x14001dc0d  mov     rax, [rbx+60h]
0x14001dc11  test    rax, rax
0x14001dc14  jnz     short loc_14001DC41
0x14001dc16  mov     rcx, [rbx+18h]
0x14001dc1a  test    rcx, rcx
0x14001dc1d  jz      short loc_14001DC24
0x14001dc1f  call    LuafvFreePool
0x14001dc24  mov     rcx, [rbx+48h]
0x14001dc28  test    rcx, rcx
0x14001dc2b  jz      short loc_14001DC32
0x14001dc2d  call    LuafvFreePool
0x14001dc32  mov     rcx, rbx
0x14001dc35  call    LuafvFreePool
0x14001dc3a  add     rsp, 20h
0x14001dc3e  pop     rbx
0x14001dc3f  retn
0x14001dc41  mov     rcx, [rax]; FileHandle
0x14001dc44  test    rcx, rcx
0x14001dc47  jz      short loc_14001DC55
0x14001dc49  call    cs:__imp_FltClose
0x14001dc50  nop     dword ptr [rax+rax+00h]
0x14001dc55  mov     rax, [rbx+60h]
0x14001dc59  mov     rcx, [rax+20h]; FileHandle
0x14001dc5d  test    rcx, rcx
0x14001dc60  jz      short loc_14001DC6E
0x14001dc62  call    cs:__imp_FltClose
0x14001dc69  nop     dword ptr [rax+rax+00h]
0x14001dc6e  mov     rax, [rbx+60h]
0x14001dc72  mov     rcx, [rax+10h]
0x14001dc76  test    rcx, rcx
0x14001dc79  jz      short loc_14001DC80
0x14001dc7b  call    LuafvFreePool
0x14001dc80  mov     rax, [rbx+60h]
0x14001dc84  mov     rcx, [rax+30h]
0x14001dc88  test    rcx, rcx
0x14001dc8b  jz      short loc_14001DC92
0x14001dc8d  call    LuafvFreePool
0x14001dc92  mov     rcx, [rbx+60h]
0x14001dc96  call    LuafvFreePool
0x14001dc9b  jmp     loc_14001DC16
```
