# CDirectMusicUMAPort::KsEvent(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18001feb0`
- end: `0x18001ff0b`
- name: `?KsEvent@CDirectMusicUMAPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `91`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x18001feb0`
- `0x1800212e4`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::KsEvent(
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
    return SyncIoctl(this[114], 0x2F0007u, a2, a3, a4, a5, lpNumberOfBytesTransferred);
  return 2289570100LL;
}

```

## disassembly

```asm
0x18001feb0  sub     rsp, 48h
0x18001feb4  test    r8d, r8d
0x18001feb7  jz      short loc_18001FEBE
0x18001feb9  test    rdx, rdx
0x18001febc  jz      short loc_18001FEC8
0x18001febe  mov     rax, [rsp+48h+arg_28]
0x18001fec3  test    rax, rax
0x18001fec6  jnz     short loc_18001FECF
0x18001fec8  mov     eax, 80004003h
0x18001fecd  jmp     short loc_18001FF06
0x18001fecf  cmp     qword ptr [rcx+10h], 0
0x18001fed4  jnz     short loc_18001FEDD
0x18001fed6  mov     eax, 88781134h
0x18001fedb  jmp     short loc_18001FF06
0x18001fedd  mov     rcx, [rcx+390h]; void *
0x18001fee4  mov     [rsp+48h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18001fee9  mov     eax, [rsp+48h+arg_20]
0x18001feed  mov     [rsp+48h+var_20], eax; DWORD
0x18001fef1  mov     [rsp+48h+var_28], r9; void *
0x18001fef6  mov     r9d, r8d; unsigned int
0x18001fef9  mov     r8, rdx; void *
0x18001fefc  mov     edx, 2F0007h; unsigned int
0x18001ff01  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x18001ff06  add     rsp, 48h
0x18001ff0a  retn
```
