# SC_RAW::CreatePartitionTable(void)

- ea: `0x140010a30`
- end: `0x140010af4`
- name: `?CreatePartitionTable@SC_RAW@@QEAAJXZ`
- size: `196`
- prototype: `__int64 __fastcall(SC_RAW *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000ea44`

## callees

- `0x14000f264`
- `0x140010a30`
- `0x140011440`

## pseudocode

```c
__int64 __fastcall SC_RAW::CreatePartitionTable(SC_DISK **this)
{
  __int64 v2; // rbx
  int v3; // edx

  v2 = *((_QWORD *)*this + 33);
  memset((void *)(v2 + 446), 0, 0x40u);
  *(_DWORD *)(v2 + 440) = 0;
  *(_WORD *)(v2 + 510) = 0;
  v3 = SC_DISK::WriteSectors(*this, 1u, 0, 0);
  if ( v3 >= 0 && *((_DWORD *)*this + 64) == 1 )
  {
    memset(*((void **)*this + 33), 0, 1 << *((_DWORD *)*this + 60));
    v3 = SC_DISK::WriteSectors(*this, 1u, 1u, 0);
    if ( v3 >= 0 && (*((_DWORD *)*this + 50) & 1) == 0 )
      return (unsigned int)SC_DISK::WriteSectors(*this, 1u, *((_QWORD *)*this + 31) - 1LL, 0);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140010a30  mov     [rsp+arg_0], rbx
0x140010a35  push    rdi
0x140010a36  sub     rsp, 20h
0x140010a3a  mov     rax, [rcx]
0x140010a3d  xor     edx, edx; Val
0x140010a3f  mov     rdi, rcx
0x140010a42  mov     rbx, [rax+108h]
0x140010a49  lea     r8d, [rdx+40h]; Size
0x140010a4d  lea     rcx, [rbx+1BEh]; void *
0x140010a54  call    memset
0x140010a59  xor     eax, eax
0x140010a5b  mov     dword ptr [rbx+1B8h], 0
0x140010a65  mov     [rbx+1FEh], ax
0x140010a6c  xor     r9d, r9d; void *
0x140010a6f  mov     rcx, [rdi]; this
0x140010a72  xor     r8d, r8d; unsigned __int64
0x140010a75  lea     ebx, [rax+1]
0x140010a78  mov     edx, ebx; unsigned int
0x140010a7a  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x140010a7f  mov     edx, eax
0x140010a81  test    eax, eax
0x140010a83  js      short loc_140010AE6
0x140010a85  mov     r9, [rdi]
0x140010a88  cmp     [r9+100h], ebx
0x140010a8f  jnz     short loc_140010AE6
0x140010a91  mov     ecx, [r9+0F0h]
0x140010a98  mov     eax, ebx
0x140010a9a  shl     eax, cl
0x140010a9c  xor     edx, edx; Val
0x140010a9e  mov     rcx, [r9+108h]; void *
0x140010aa5  movsxd  r8, eax; Size
0x140010aa8  call    memset
0x140010aad  mov     rcx, [rdi]; this
0x140010ab0  xor     r9d, r9d; void *
0x140010ab3  mov     r8d, ebx; unsigned __int64
0x140010ab6  mov     edx, ebx; unsigned int
0x140010ab8  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x140010abd  mov     edx, eax
0x140010abf  test    eax, eax
0x140010ac1  js      short loc_140010AE6
0x140010ac3  mov     rcx, [rdi]; this
0x140010ac6  mov     eax, [rcx+0C8h]
0x140010acc  test    bl, al
0x140010ace  jnz     short loc_140010AE6
0x140010ad0  mov     r8, [rcx+0F8h]
0x140010ad7  xor     r9d, r9d; void *
0x140010ada  sub     r8, rbx; unsigned __int64
0x140010add  mov     edx, ebx; unsigned int
0x140010adf  call    ?WriteSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::WriteSectors(ulong,unsigned __int64,void *)
0x140010ae4  mov     edx, eax
0x140010ae6  mov     rbx, [rsp+28h+arg_0]
0x140010aeb  mov     eax, edx
0x140010aed  add     rsp, 20h
0x140010af1  pop     rdi
0x140010af2  retn
```
