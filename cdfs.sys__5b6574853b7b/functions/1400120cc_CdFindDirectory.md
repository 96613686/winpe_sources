# CdFindDirectory

- ea: `0x1400120cc`
- end: `0x140012192`
- name: `CdFindDirectory`
- size: `198`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1400135d0`

## callees

- `0x14000b684`
- `0x1400120cc`
- `0x140012464`
- `0x140012884`
- `0x14001292c`
- `0x140012a14`
- `0x1400164dc`

## pseudocode

```c
char __fastcall CdFindDirectory(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  char v5; // bp
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rcx

  v5 = 0;
  if ( !*(_QWORD *)(a2 + 472) )
    CdCreateInternalStream(a1, *(_QWORD *)(a2 + 120), a2, a2 + 344);
  CdLookupDirent(a1, a2, *(_DWORD *)(a2 + 480), *(_QWORD *)(a5 + 8));
  CdUpdateDirentFromRawDirent(a1, v9, *(_QWORD *)(a5 + 8), *(_QWORD *)(a5 + 8) + 32LL);
  while ( 1 )
  {
    v10 = *(_QWORD *)(a5 + 8);
    if ( (*(_BYTE *)(v10 + 56) & 2) != 0 )
    {
      CdUpdateDirentName(a1, v10 + 32, 1);
      if ( (*(_BYTE *)(v10 + 57) & 2) == 0 )
      {
        if ( (unsigned __int8)CdIsNameInExpression(v11, v10 + 120, a3) )
          break;
      }
    }
    if ( !CdLookupNextInitialFileDirent(a1, a2, a5) )
      return v5;
  }
  return 1;
}

```

## disassembly

```asm
0x1400120cc  push    rbx
0x1400120ce  push    rbp
0x1400120cf  push    rsi
0x1400120d0  push    rdi
0x1400120d1  push    r14
0x1400120d3  push    r15
0x1400120d5  sub     rsp, 38h
0x1400120d9  xor     bpl, bpl
0x1400120dc  mov     r15, r8
0x1400120df  cmp     qword ptr [rdx+1D8h], 0
0x1400120e7  mov     rbx, rdx
0x1400120ea  mov     rdi, rcx
0x1400120ed  jnz     short loc_140012102
0x1400120ef  lea     r9, [rdx+158h]
0x1400120f6  mov     r8, rdx
0x1400120f9  mov     rdx, [rdx+78h]
0x1400120fd  call    CdCreateInternalStream
0x140012102  mov     r14, [rsp+68h+arg_20]
0x14001210a  mov     rdx, rbx
0x14001210d  mov     r8d, [rbx+1E0h]
0x140012114  mov     rcx, rdi
0x140012117  mov     r9, [r14+8]
0x14001211b  call    CdLookupDirent
0x140012120  mov     r8, [r14+8]
0x140012124  mov     rcx, rdi
0x140012127  lea     r9, [r8+20h]
0x14001212b  call    CdUpdateDirentFromRawDirent
0x140012130  mov     rsi, [r14+8]
0x140012134  test    byte ptr [rsi+38h], 2
0x140012138  jz      short loc_14001216A
0x14001213a  mov     r8d, 1
0x140012140  lea     rdx, [rsi+20h]
0x140012144  mov     rcx, rdi
0x140012147  call    CdUpdateDirentName
0x14001214c  test    byte ptr [rsi+39h], 2
0x140012150  jnz     short loc_14001216A
0x140012152  lea     rdx, [rsi+78h]
0x140012156  mov     [rsp+68h+var_48], 1
0x14001215b  xor     r9d, r9d
0x14001215e  mov     r8, r15
0x140012161  call    CdIsNameInExpression
0x140012166  test    al, al
0x140012168  jnz     short loc_14001217E
0x14001216a  mov     r8, r14
0x14001216d  mov     rdx, rbx
0x140012170  mov     rcx, rdi
0x140012173  call    CdLookupNextInitialFileDirent
0x140012178  test    al, al
0x14001217a  jnz     short loc_140012130
0x14001217c  jmp     short loc_140012181
0x14001217e  mov     bpl, 1
0x140012181  mov     al, bpl
0x140012184  add     rsp, 38h
0x140012188  pop     r15
0x14001218a  pop     r14
0x14001218c  pop     rdi
0x14001218d  pop     rsi
0x14001218e  pop     rbp
0x14001218f  pop     rbx
0x140012190  retn
```
