# HacPurgePostfix

- ea: `0x140020154`
- end: `0x14002022d`
- name: `HacPurgePostfix`
- size: `217`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003bd0`
- `0x140004530`
- `0x14000f274`
- `0x1400124ec`
- `0x1400145f0`
- `0x14001c694`

## callees

- `0x140003380`
- `0x140005c90`
- `0x140008140`
- `0x140020154`
- `0x1400206e4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400201af`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400201af`
- `ntoskrnl!KeReleaseMutex` at `0x14002020f`
- `ntoskrnl!KeReleaseMutex` at `0x14002020f`

## pseudocode

```c
LONG __fastcall HacPurgePostfix(__int64 a1, const UNICODE_STRING *a2)
{
  struct _KMUTANT *Buffer; // rax
  __int64 v5; // rdi
  const UNICODE_STRING *v6; // rbx
  const UNICODE_STRING *v7; // r14
  int Length; // r12d
  int v9; // r15d
  const UNICODE_STRING *v10; // rbp

  HacAcquireLock(a2);
  Buffer = (struct _KMUTANT *)a2[2].Buffer;
  if ( Buffer[1].Header.LockNV )
  {
    v5 = 0;
    do
    {
      v6 = (const UNICODE_STRING *)*((_QWORD *)&Buffer[2].Header.WaitListHead.Flink->Flink + v5);
      if ( v6 )
      {
        v7 = a2 + 4;
        do
        {
          Length = v7->Length;
          v9 = v6[4].Length;
          v10 = *(const UNICODE_STRING **)&v6->Length;
          if ( (unsigned __int16)Length < (unsigned __int16)v9
            && RtlCompareUnicodeString(v6 + 4, a2 + 4, 0) == v9 - Length
            && v6[4].Buffer[(unsigned __int64)v7->Length >> 1] == 92 )
          {
            HacReference(v6);
            HacpRemoveEntry(v6);
            HacDereference(a1, v6);
          }
          v6 = v10;
        }
        while ( v10 );
      }
      Buffer = (struct _KMUTANT *)a2[2].Buffer;
      v5 = (unsigned int)(v5 + 1);
    }
    while ( (unsigned int)v5 < Buffer[1].Header.LockNV );
  }
  return KeReleaseMutex(Buffer, 0);
}

```

## disassembly

```asm
0x140020154  push    rbx
0x140020156  push    rbp
0x140020157  push    rsi
0x140020158  push    rdi
0x140020159  push    r12
0x14002015b  push    r13
0x14002015d  push    r14
0x14002015f  push    r15
0x140020161  sub     rsp, 28h
0x140020165  mov     r13, rcx
0x140020168  mov     rsi, rdx
0x14002016b  mov     rcx, rdx
0x14002016e  call    HacAcquireLock
0x140020173  mov     rax, [rsi+28h]
0x140020177  cmp     dword ptr [rax+38h], 0
0x14002017b  jbe     loc_14002020A
0x140020181  xor     edi, edi
0x140020183  mov     rax, [rax+78h]
0x140020187  mov     rbx, [rax+rdi*8]
0x14002018b  test    rbx, rbx
0x14002018e  jz      short loc_1400201FB
0x140020190  lea     r14, [rsi+40h]
0x140020194  movzx   r12d, word ptr [r14]
0x140020198  lea     rcx, [rbx+40h]; String1
0x14002019c  movzx   r15d, word ptr [rcx]
0x1400201a0  mov     rbp, [rbx]
0x1400201a3  cmp     r12w, r15w
0x1400201a7  jnb     short loc_1400201F3
0x1400201a9  xor     r8d, r8d; CaseInSensitive
0x1400201ac  mov     rdx, r14; String2
0x1400201af  call    cs:__imp_RtlCompareUnicodeString
0x1400201b6  nop     dword ptr [rax+rax+00h]
0x1400201bb  mov     r8d, r15d
0x1400201be  sub     r8d, r12d
0x1400201c1  cmp     eax, r8d
0x1400201c4  jnz     short loc_1400201F3
0x1400201c6  movzx   ecx, word ptr [r14]
0x1400201ca  mov     rax, [rbx+48h]
0x1400201ce  shr     rcx, 1
0x1400201d1  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400201d6  jnz     short loc_1400201F3
0x1400201d8  mov     rcx, rbx
0x1400201db  call    HacReference
0x1400201e0  mov     rcx, rbx
0x1400201e3  call    HacpRemoveEntry
0x1400201e8  mov     rdx, rbx
0x1400201eb  mov     rcx, r13
0x1400201ee  call    HacDereference
0x1400201f3  mov     rbx, rbp
0x1400201f6  test    rbp, rbp
0x1400201f9  jnz     short loc_140020194
0x1400201fb  mov     rax, [rsi+28h]
0x1400201ff  inc     edi
0x140020201  cmp     edi, [rax+38h]
0x140020204  jb      loc_140020183
0x14002020a  xor     edx, edx; Wait
0x14002020c  mov     rcx, rax; Mutex
0x14002020f  call    cs:__imp_KeReleaseMutex
0x140020216  nop     dword ptr [rax+rax+00h]
0x14002021b  add     rsp, 28h
0x14002021f  pop     r15
0x140020221  pop     r14
0x140020223  pop     r13
0x140020225  pop     r12
0x140020227  pop     rdi
0x140020228  pop     rsi
0x140020229  pop     rbp
0x14002022a  pop     rbx
0x14002022b  retn
```
