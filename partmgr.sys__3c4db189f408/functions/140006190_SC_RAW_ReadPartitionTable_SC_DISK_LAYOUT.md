# SC_RAW::ReadPartitionTable(SC_DISK_LAYOUT * *)

- ea: `0x140006190`
- end: `0x140006279`
- name: `?ReadPartitionTable@SC_RAW@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(SC_RAW *this, struct SC_DISK_LAYOUT **, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000a33c`

## callees

- `0x14000590c`
- `0x140006190`
- `0x14000a530`
- `0x140011440`

## pseudocode

```c
__int64 __fastcall SC_RAW::ReadPartitionTable(SC_RAW *this, struct SC_DISK_LAYOUT **a2, unsigned __int8 a3)
{
  __int64 v3; // rax
  MBR_HEADER *v6; // rsi
  char *v7; // rax
  char *v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rdx
  char v11; // r8

  v3 = *(_QWORD *)this;
  *a2 = 0;
  v6 = *(MBR_HEADER **)(v3 + 264);
  v7 = (char *)SC_ENV::Allocate(0xC0u, (unsigned int)a2, a3, 0);
  v8 = v7;
  if ( v7 )
  {
    v9 = 0;
    memset(v7 + 12, 0, 0xB4u);
    if ( *(_DWORD *)(*(_QWORD *)this + 224LL) == 11 || *((_WORD *)v6 + 255) == 0xAA55 )
    {
      *(_DWORD *)v8 = 0;
      *((_DWORD *)v8 + 1) = 1;
      *((_DWORD *)v8 + 2) = 1;
      *((_DWORD *)v8 + 3) = MBR_HEADER::CheckSum(v6);
      *((_DWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 7) = 0;
      *((_QWORD *)v8 + 8) = *(_QWORD *)(v10 + 248) << *(_DWORD *)(v10 + 240);
      *((_DWORD *)v8 + 18) = 0;
      *((_WORD *)v8 + 40) = 4;
      v8[82] = v11;
      *((_DWORD *)v8 + 21) = 0;
      *((_DWORD *)v8 + 22) = *((_DWORD *)v8 + 2);
      *((_DWORD *)v8 + 23) = 0;
      *((_QWORD *)v8 + 12) = 0;
    }
    else
    {
      *(_QWORD *)v8 = 0;
      *((_DWORD *)v8 + 2) = 0;
      *((_DWORD *)v8 + 3) = MBR_HEADER::CheckSum(v6);
    }
    *a2 = (struct SC_DISK_LAYOUT *)v8;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v9;
}

```

## disassembly

```asm
0x140006190  push    rbx
0x140006192  push    rsi
0x140006193  push    rdi
0x140006194  push    r14
0x140006196  push    r15
0x140006198  sub     rsp, 20h
0x14000619c  mov     rax, [rcx]
0x14000619f  mov     r15, rcx
0x1400061a2  xor     r9d, r9d; unsigned int
0x1400061a5  mov     qword ptr [rdx], 0
0x1400061ac  mov     ecx, 0C0h; unsigned __int64
0x1400061b1  mov     r14, rdx
0x1400061b4  mov     rsi, [rax+108h]
0x1400061bb  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400061c0  mov     rbx, rax
0x1400061c3  test    rax, rax
0x1400061c6  jnz     short loc_1400061D2
0x1400061c8  mov     edi, 0C000009Ah
0x1400061cd  jmp     loc_14000626A
0x1400061d2  lea     rcx, [rax+0Ch]; void *
0x1400061d6  xor     edx, edx; Val
0x1400061d8  mov     r8d, 0B4h; Size
0x1400061de  xor     edi, edi
0x1400061e0  call    memset
0x1400061e5  mov     rdx, [r15]
0x1400061e8  cmp     dword ptr [rdx+0E0h], 0Bh
0x1400061ef  jz      short loc_140006212
0x1400061f1  mov     eax, 0AA55h
0x1400061f6  cmp     [rsi+1FEh], ax
0x1400061fd  jz      short loc_140006212
0x1400061ff  mov     rcx, rsi; this
0x140006202  mov     [rbx], rdi
0x140006205  mov     [rbx+8], edi
0x140006208  call    ?CheckSum@MBR_HEADER@@QEAAKXZ; MBR_HEADER::CheckSum(void)
0x14000620d  mov     [rbx+0Ch], eax
0x140006210  jmp     short loc_140006267
0x140006212  mov     r8d, 1
0x140006218  mov     [rbx], edi
0x14000621a  mov     rcx, rsi; this
0x14000621d  mov     [rbx+4], r8d
0x140006221  mov     [rbx+8], r8d
0x140006225  call    ?CheckSum@MBR_HEADER@@QEAAKXZ; MBR_HEADER::CheckSum(void)
0x14000622a  mov     [rbx+0Ch], eax
0x14000622d  mov     [rbx+30h], edi
0x140006230  mov     [rbx+38h], rdi
0x140006234  mov     ecx, [rdx+0F0h]
0x14000623a  mov     rax, [rdx+0F8h]
0x140006241  shl     rax, cl
0x140006244  mov     [rbx+40h], rax
0x140006248  mov     [rbx+48h], edi
0x14000624b  mov     word ptr [rbx+50h], 4
0x140006251  mov     [rbx+52h], r8b
0x140006255  mov     [rbx+54h], edi
0x140006258  mov     ecx, [rbx+8]
0x14000625b  mov     [rbx+58h], ecx
0x14000625e  xor     ecx, ecx
0x140006260  mov     [rbx+5Ch], ecx
0x140006263  mov     [rbx+60h], rcx
0x140006267  mov     [r14], rbx
0x14000626a  mov     eax, edi
0x14000626c  add     rsp, 20h
0x140006270  pop     r15
0x140006272  pop     r14
0x140006274  pop     rdi
0x140006275  pop     rsi
0x140006276  pop     rbx
0x140006277  retn
```
