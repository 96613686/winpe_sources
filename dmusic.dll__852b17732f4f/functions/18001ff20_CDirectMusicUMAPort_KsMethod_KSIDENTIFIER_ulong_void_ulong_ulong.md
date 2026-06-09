# CDirectMusicUMAPort::KsMethod(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18001ff20`
- end: `0x18001ff7b`
- name: `?KsMethod@CDirectMusicUMAPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `91`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18001ff20`
- `0x1800212e4`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::KsMethod(
        void **this,
        struct KSIDENTIFIER *a2,
        unsigned int a3,
        void *a4,
        DWORD a5,
        unsigned int *lpNumberOfBytesTransferred)
{
  if ( a3 && !a2 || !lpNumberOfBytesTransferred )
    return 2147500035LL;
  if ( this[2] )
    return SyncIoctl(this[114], 0x2F000Fu, a2, a3, a4, a5, lpNumberOfBytesTransferred);
  return 2289570100LL;
}

```

## disassembly

```asm
0x18001ff20  sub     rsp, 48h
0x18001ff24  test    r8d, r8d
0x18001ff27  jz      short loc_18001FF2E
0x18001ff29  test    rdx, rdx
0x18001ff2c  jz      short loc_18001FF38
0x18001ff2e  mov     rax, [rsp+48h+arg_28]
0x18001ff33  test    rax, rax
0x18001ff36  jnz     short loc_18001FF3F
0x18001ff38  mov     eax, 80004003h
0x18001ff3d  jmp     short loc_18001FF76
0x18001ff3f  cmp     qword ptr [rcx+10h], 0
0x18001ff44  jnz     short loc_18001FF4D
0x18001ff46  mov     eax, 88781134h
0x18001ff4b  jmp     short loc_18001FF76
0x18001ff4d  mov     rcx, [rcx+390h]; void *
0x18001ff54  mov     [rsp+48h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001ff59  mov     eax, [rsp+48h+arg_20]
0x18001ff5d  mov     [rsp+48h+var_20], eax; DWORD
0x18001ff61  mov     [rsp+48h+var_28], r9; void *
0x18001ff66  mov     r9d, r8d; unsigned int
0x18001ff69  mov     r8, rdx; void *
0x18001ff6c  mov     edx, 2F000Fh; unsigned int
0x18001ff71  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001ff76  add     rsp, 48h
0x18001ff7a  retn
```
