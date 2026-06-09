# FatUpdateFileHeader

- ea: `0x14003805c`
- end: `0x140038164`
- name: `FatUpdateFileHeader`
- size: `264`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140033270`
- `0x140034054`
- `0x14003b00c`
- `0x14003b9d0`
- `0x14003e028`

## callees

- `0x14000179c`
- `0x1400018a4`
- `0x140003434`
- `0x14003805c`

## import_xrefs

- `ntoskrnl!CcPreparePinWrite` at `0x1400380e0`
- `ntoskrnl!CcPreparePinWrite` at `0x1400380e0`
- `ntoskrnl!CcUnpinData` at `0x14003813b`
- `ntoskrnl!CcUnpinData` at `0x14005e165`
- `ntoskrnl!CcUnpinData` at `0x14003813b`
- `ntoskrnl!CcUnpinData` at `0x14005e165`

## pseudocode

```c
void FatUpdateFileHeader(__int64 a1, __int64 a2, int a3, ...)
{
  ULONG v5; // ebx
  PVOID Bcb; // [rsp+48h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+50h] [rbp-28h] BYREF
  int v8; // [rsp+90h] [rbp+18h] BYREF
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v8 = a3;
  Bcb = 0;
  Buffer = 0;
  FatOpenFileHeader(a1, 0, a2);
  v5 = 1 << *(_BYTE *)(*(_QWORD *)(a2 + 184) + 377LL);
  CcPreparePinWrite(*(PFILE_OBJECT *)(a2 + 424), &FatLargeZero, v5, 0, 1u, &Bcb, &Buffer);
  EfsSetEfsInfoCallback((_DWORD)Buffer, v5, 2, (unsigned int)&v8, 4);
  EfsSetEfsInfoCallback((_DWORD)Buffer, v5, 3, (unsigned int)va, 8);
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  FatCloseFileHeader(a1, a2);
}

```

## disassembly

```asm
0x14003805c  mov     rax, rsp
0x14003805f  mov     [rax+20h], r9
0x140038063  mov     [rax+18h], r8d
0x140038067  mov     [rax+10h], rdx
0x14003806b  mov     [rax+8], rcx
0x14003806f  push    rbx
0x140038070  push    rsi
0x140038071  push    rdi
0x140038072  sub     rsp, 60h
0x140038076  mov     rdi, rdx
0x140038079  mov     rsi, rcx
0x14003807c  mov     qword ptr [rax-30h], 0
0x140038084  mov     qword ptr [rax-28h], 0
0x14003808c  mov     byte ptr [rax-38h], 0
0x140038090  mov     r8, rdx
0x140038093  xor     edx, edx
0x140038095  call    FatOpenFileHeader
0x14003809a  mov     edx, 1
0x14003809f  mov     [rsp+78h+var_38], dl
0x1400380a3  mov     rcx, [rdi+0B8h]
0x1400380aa  mov     cl, [rcx+179h]
0x1400380b0  mov     ebx, edx
0x1400380b2  shl     ebx, cl
0x1400380b4  lea     rax, [rsp+78h+var_28]
0x1400380b9  mov     [rsp+78h+Buffer], rax; Buffer
0x1400380be  lea     rax, [rsp+78h+var_30]
0x1400380c3  mov     [rsp+78h+Bcb], rax; Bcb
0x1400380c8  mov     [rsp+78h+Flags], edx; Flags
0x1400380cc  xor     r9d, r9d; Zero
0x1400380cf  mov     r8d, ebx; Length
0x1400380d2  lea     rdx, FatLargeZero; FileOffset
0x1400380d9  mov     rcx, [rdi+1A8h]; FileObject
0x1400380e0  call    cs:__imp_CcPreparePinWrite
0x1400380e7  nop     dword ptr [rax+rax+00h]
0x1400380ec  mov     [rsp+78h+Flags], 4
0x1400380f4  lea     r9, [rsp+78h+arg_10]
0x1400380fc  mov     r8d, 2
0x140038102  mov     edx, ebx
0x140038104  mov     rcx, [rsp+78h+var_28]
0x140038109  call    EfsSetEfsInfoCallback
0x14003810e  mov     [rsp+78h+Flags], 8
0x140038116  lea     r9, [rsp+78h+arg_18]
0x14003811e  mov     r8d, 3
0x140038124  mov     edx, ebx
0x140038126  mov     rcx, [rsp+78h+var_28]
0x14003812b  call    EfsSetEfsInfoCallback
0x140038130  nop
0x140038131  mov     rcx, [rsp+78h+var_30]; Bcb
0x140038136  test    rcx, rcx
0x140038139  jz      short loc_140038150
0x14003813b  call    cs:__imp_CcUnpinData
0x140038142  nop     dword ptr [rax+rax+00h]
0x140038147  mov     [rsp+78h+var_30], 0
0x140038150  mov     rdx, rdi
0x140038153  mov     rcx, rsi
0x140038156  call    FatCloseFileHeader
0x14003815b  add     rsp, 60h
0x14003815f  pop     rdi
0x140038160  pop     rsi
0x140038161  pop     rbx
0x140038162  retn
0x14005e153  push    rbp
0x14005e155  sub     rsp, 40h
0x14005e159  mov     rbp, rdx
0x14005e15c  mov     rcx, [rbp+48h]; Bcb
0x14005e160  test    rcx, rcx
0x14005e163  jz      short loc_14005E179
0x14005e165  call    cs:__imp_CcUnpinData
0x14005e16c  nop     dword ptr [rax+rax+00h]
0x14005e171  mov     qword ptr [rbp+48h], 0
0x14005e179  cmp     byte ptr [rbp+40h], 0
0x14005e17d  jz      short loc_14005E196
0x14005e17f  mov     rdx, [rbp+88h]
0x14005e186  mov     rcx, [rbp+80h]
0x14005e18d  call    FatCloseFileHeader
0x14005e192  mov     byte ptr [rbp+40h], 0
0x14005e196  add     rsp, 40h
0x14005e19a  pop     rbp
0x14005e19b  retn
```
