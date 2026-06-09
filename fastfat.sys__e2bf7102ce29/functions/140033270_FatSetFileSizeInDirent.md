# FatSetFileSizeInDirent

- ea: `0x140033270`
- end: `0x1400333ac`
- name: `FatSetFileSizeInDirent`
- size: `316`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops, installer_update`

## callers

- `0x14000363c`
- `0x140004554`
- `0x140024bd4`
- `0x1400333b4`
- `0x14003816c`
- `0x14003ad44`
- `0x14003b9d0`
- `0x14004af08`

## callees

- `0x1400019b8`
- `0x1400319bc`
- `0x140033270`
- `0x14003805c`

## import_xrefs

- `ntoskrnl!CcUnpinData` at `0x140033368`
- `ntoskrnl!CcUnpinData` at `0x14005d30c`
- `ntoskrnl!CcUnpinData` at `0x140033368`
- `ntoskrnl!CcUnpinData` at `0x14005d30c`

## pseudocode

```c
void __fastcall FatSetFileSizeInDirent(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  char v5; // r15
  int v6; // esi
  __int64 v7; // rcx
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF
  PVOID Bcb; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  Bcb = 0;
  v4 = 0;
  v5 = 0;
  v6 = *(_DWORD *)(a2 + 32);
  FatGetDirentFromFcbOrDcb(a1, a2, 0, (unsigned int)&v8, (__int64)&Bcb);
  if ( v6 != *(_DWORD *)(v8 + 28) )
  {
    *(_DWORD *)(v8 + 28) = v6;
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 184) + 200LL) & 0x400000) != 0 && (*(_DWORD *)(a2 + 192) & 0x8000) != 0 )
    {
      v7 = v8;
      v4 = *(unsigned int *)(v8 + 28);
      v5 = 1;
      *(_BYTE *)(a2 + 136) = ((v4 + 15) & 0xF0) - v4;
      *(_DWORD *)(v7 + 28) = (*(_DWORD *)(v7 + 28) + 15) & 0xFFFFFFF0;
      *(_DWORD *)(v8 + 28) += *(_DWORD *)(a2 + 132);
      *(_BYTE *)(v8 + 12) = *(_BYTE *)(v8 + 12) & 0x1B
                          | (4 * (*(_BYTE *)(a2 + 136) & 1 | (4 * (*(_BYTE *)(a2 + 136) & 0xFE))));
    }
    FatSetDirtyBcb(a1, Bcb, *(_QWORD *)(a2 + 184), 1);
  }
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v5 )
    FatUpdateFileHeader(a1, a2, *(_DWORD *)(a2 + 132), v4);
}

```

## disassembly

```asm
0x140033270  mov     r11, rsp
0x140033273  mov     [r11+8], rbx
0x140033277  mov     [r11+10h], rsi
0x14003327b  mov     [r11+18h], r8
0x14003327f  push    rdi
0x140033280  push    r14
0x140033282  push    r15
0x140033284  sub     rsp, 30h
0x140033288  mov     rbx, rdx
0x14003328b  mov     rdi, rcx
0x14003328e  mov     qword ptr [r11+18h], 0
0x140033296  mov     qword ptr [r11+20h], 0
0x14003329e  xor     r14d, r14d
0x1400332a1  xor     r15b, r15b
0x1400332a4  mov     esi, [rdx+20h]
0x1400332a7  lea     rax, [r11+20h]
0x1400332ab  mov     [r11-28h], rax
0x1400332af  lea     r9, [r11+18h]
0x1400332b3  xor     r8d, r8d
0x1400332b6  call    FatGetDirentFromFcbOrDcb
0x1400332bb  nop
0x1400332bc  mov     rax, [rsp+48h+arg_10]
0x1400332c1  cmp     esi, [rax+1Ch]
0x1400332c4  jz      loc_14003335E
0x1400332ca  mov     [rax+1Ch], esi
0x1400332cd  mov     rax, [rbx+0B8h]
0x1400332d4  mov     ecx, [rax+0C8h]
0x1400332da  bt      ecx, 16h
0x1400332de  jnb     short loc_140033346
0x1400332e0  test    dword ptr [rbx+0C0h], 8000h
0x1400332ea  jz      short loc_140033346
0x1400332ec  mov     rcx, [rsp+48h+arg_10]
0x1400332f1  mov     r14d, [rcx+1Ch]
0x1400332f5  mov     r15b, 1
0x1400332f8  lea     eax, [r14+0Fh]
0x1400332fc  and     al, 0F0h
0x1400332fe  sub     al, r14b
0x140033301  mov     [rbx+88h], al
0x140033307  mov     eax, [rcx+1Ch]
0x14003330a  add     eax, 0Fh
0x14003330d  and     eax, 0FFFFFFF0h
0x140033310  mov     [rcx+1Ch], eax
0x140033313  mov     rcx, [rsp+48h+arg_10]
0x140033318  mov     eax, [rbx+84h]
0x14003331e  add     [rcx+1Ch], eax
0x140033321  mov     al, [rbx+88h]
0x140033327  mov     rdx, [rsp+48h+arg_10]
0x14003332c  mov     cl, al
0x14003332e  and     cl, 0FEh
0x140033331  shl     cl, 2
0x140033334  and     al, r15b
0x140033337  or      cl, al
0x140033339  shl     cl, 2
0x14003333c  mov     al, [rdx+0Ch]
0x14003333f  and     al, 1Bh
0x140033341  or      cl, al
0x140033343  mov     [rdx+0Ch], cl
0x140033346  mov     r9b, 1
0x140033349  mov     r8, [rbx+0B8h]
0x140033350  mov     rdx, [rsp+48h+Bcb]
0x140033355  mov     rcx, rdi
0x140033358  call    FatSetDirtyBcb
0x14003335d  nop
0x14003335e  mov     rcx, [rsp+48h+Bcb]; Bcb
0x140033363  test    rcx, rcx
0x140033366  jz      short loc_14003337D
0x140033368  call    cs:__imp_CcUnpinData
0x14003336f  nop     dword ptr [rax+rax+00h]
0x140033374  mov     [rsp+48h+Bcb], 0
0x14003337d  test    r15b, r15b
0x140033380  jz      short loc_140033397
0x140033382  mov     r9, r14
0x140033385  mov     r8d, [rbx+84h]
0x14003338c  mov     rdx, rbx
0x14003338f  mov     rcx, rdi
0x140033392  call    FatUpdateFileHeader
0x140033397  mov     rbx, [rsp+48h+arg_0]
0x14003339c  mov     rsi, [rsp+48h+arg_8]
0x1400333a1  add     rsp, 30h
0x1400333a5  pop     r15
0x1400333a7  pop     r14
0x1400333a9  pop     rdi
0x1400333aa  retn
0x14005d2fa  push    rbp
0x14005d2fc  sub     rsp, 30h
0x14005d300  mov     rbp, rdx
0x14005d303  mov     rcx, [rbp+68h]; Bcb
0x14005d307  test    rcx, rcx
0x14005d30a  jz      short loc_14005D319
0x14005d30c  call    cs:__imp_CcUnpinData
0x14005d313  nop     dword ptr [rax+rax+00h]
0x14005d318  nop
0x14005d319  add     rsp, 30h
0x14005d31d  pop     rbp
0x14005d31e  retn
```
