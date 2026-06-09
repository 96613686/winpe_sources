# LuafvFreeStoreFile

- ea: `0x14001dc20`
- end: `0x14001dcf0`
- name: `LuafvFreeStoreFile`
- size: `208`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140018f70`
- `0x14001a3c8`
- `0x14001dc00`
- `0x1400258a0`

## callees

- `0x14001d930`
- `0x14001dc20`
- `0x14001dd90`
- `0x14001dec8`

## import_xrefs

- `FLTMGR!FltClose` at `0x14001dc99`
- `FLTMGR!FltClose` at `0x14001dcb2`
- `FLTMGR!FltClose` at `0x14001dc99`
- `FLTMGR!FltClose` at `0x14001dcb2`

## pseudocode

```c
void __fastcall LuafvFreeStoreFile(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  HANDLE *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

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
    v8 = *(void **)(a1[12] + 32LL);
    if ( v8 )
      FltClose(v8);
    v9 = *(_QWORD *)(a1[12] + 16LL);
    if ( v9 )
      LuafvFreePool(v9);
    v10 = *(_QWORD *)(a1[12] + 48LL);
    if ( v10 )
      LuafvFreePool(v10);
    LuafvFreePool(a1[12]);
  }
  v6 = a1[3];
  if ( v6 )
    LuafvFreePool(v6);
  v7 = a1[9];
  if ( v7 )
    LuafvFreePool(v7);
  LuafvFreePool((__int64)a1);
}

```

## disassembly

```asm
0x14001dc20  push    rbx
0x14001dc22  sub     rsp, 20h
0x14001dc26  mov     rbx, rcx
0x14001dc29  mov     rcx, [rcx+20h]
0x14001dc2d  test    rcx, rcx
0x14001dc30  jz      short loc_14001DC3C
0x14001dc32  xor     r8d, r8d
0x14001dc35  xor     edx, edx
0x14001dc37  call    LuafvDereferenceTableNodeEx
0x14001dc3c  mov     rcx, [rbx+50h]
0x14001dc40  test    rcx, rcx
0x14001dc43  jz      short loc_14001DC4F
0x14001dc45  xor     r8d, r8d
0x14001dc48  xor     edx, edx
0x14001dc4a  call    LuafvDereferenceTableNodeEx
0x14001dc4f  mov     rcx, [rbx+68h]
0x14001dc53  test    rcx, rcx
0x14001dc56  jz      short loc_14001DC5D
0x14001dc58  call    LuafvDereferenceUserStore
0x14001dc5d  mov     rax, [rbx+60h]
0x14001dc61  test    rax, rax
0x14001dc64  jnz     short loc_14001DC91
0x14001dc66  mov     rcx, [rbx+18h]
0x14001dc6a  test    rcx, rcx
0x14001dc6d  jz      short loc_14001DC74
0x14001dc6f  call    LuafvFreePool
0x14001dc74  mov     rcx, [rbx+48h]
0x14001dc78  test    rcx, rcx
0x14001dc7b  jz      short loc_14001DC82
0x14001dc7d  call    LuafvFreePool
0x14001dc82  mov     rcx, rbx
0x14001dc85  call    LuafvFreePool
0x14001dc8a  add     rsp, 20h
0x14001dc8e  pop     rbx
0x14001dc8f  retn
0x14001dc91  mov     rcx, [rax]; FileHandle
0x14001dc94  test    rcx, rcx
0x14001dc97  jz      short loc_14001DCA5
0x14001dc99  call    cs:__imp_FltClose
0x14001dca0  nop     dword ptr [rax+rax+00h]
0x14001dca5  mov     rax, [rbx+60h]
0x14001dca9  mov     rcx, [rax+20h]; FileHandle
0x14001dcad  test    rcx, rcx
0x14001dcb0  jz      short loc_14001DCBE
0x14001dcb2  call    cs:__imp_FltClose
0x14001dcb9  nop     dword ptr [rax+rax+00h]
0x14001dcbe  mov     rax, [rbx+60h]
0x14001dcc2  mov     rcx, [rax+10h]
0x14001dcc6  test    rcx, rcx
0x14001dcc9  jz      short loc_14001DCD0
0x14001dccb  call    LuafvFreePool
0x14001dcd0  mov     rax, [rbx+60h]
0x14001dcd4  mov     rcx, [rax+30h]
0x14001dcd8  test    rcx, rcx
0x14001dcdb  jz      short loc_14001DCE2
0x14001dcdd  call    LuafvFreePool
0x14001dce2  mov     rcx, [rbx+60h]
0x14001dce6  call    LuafvFreePool
0x14001dceb  jmp     loc_14001DC66
```
