# NtOfsPutData

- ea: `0x140004264`
- end: `0x140004491`
- name: `NtOfsPutData`
- size: `557`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140050780`
- `0x140050cf0`
- `0x140053b10`
- `0x140053c18`
- `0x140054480`
- `0x140056ccc`

## callees

- `0x140003434`
- `0x140004264`
- `0x14000c380`
- `0x14003e870`
- `0x1400465f4`

## import_xrefs

- `ntoskrnl!CcPreparePinWrite` at `0x140004344`
- `ntoskrnl!CcPreparePinWrite` at `0x1400043f3`
- `ntoskrnl!CcPreparePinWrite` at `0x140004344`
- `ntoskrnl!CcPreparePinWrite` at `0x1400043f3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000446e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cf60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000446e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000cf60`
- `ntoskrnl!CcUnpinData` at `0x14000441c`
- `ntoskrnl!CcUnpinData` at `0x14000444d`
- `ntoskrnl!CcUnpinData` at `0x14000cf38`
- `ntoskrnl!CcUnpinData` at `0x14000441c`
- `ntoskrnl!CcUnpinData` at `0x14000444d`
- `ntoskrnl!CcUnpinData` at `0x14000cf38`

## pseudocode

```c
void __fastcall NtOfsPutData(_WORD *a1, __int64 a2, __int64 a3, __int64 a4, void *Src)
{
  size_t v5; // rsi
  char v7; // di
  __int64 v8; // rcx
  PVOID Buffer; // [rsp+48h] [rbp-30h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+50h] [rbp-28h] BYREF
  PVOID Bcb; // [rsp+90h] [rbp+18h] BYREF

  v5 = (unsigned int)a4;
  FileOffset.QuadPart = 0;
  v7 = 0;
  Bcb = 0;
  Buffer = 0;
  if ( (byte_140017D4D & 2) == 0 )
    return;
  if ( *a1 == 1288 && a1[1] == 144 && *(_WORD *)a2 == 1282 )
  {
    FatAcquireExclusiveFcb(a1, a2, a3, a4);
    v7 = 1;
    if ( (*(_DWORD *)(a2 + 192) & 0x10000) != 0 )
    {
      if ( (unsigned int)v5 <= *(_DWORD *)(a2 + 32) )
      {
        CcPreparePinWrite(*(PFILE_OBJECT *)(*(_QWORD *)(a2 + 176) + 360LL), &FileOffset, v5, 0, 1u, &Bcb, &Buffer);
        memmove(Buffer, Src, v5);
LABEL_11:
        CcUnpinData(Bcb);
        Bcb = 0;
        FatFlushFile(v8, a2, 1);
      }
    }
    else if ( (__int64)(v5 + FileOffset.QuadPart) <= *(unsigned int *)(a2 + 132) )
    {
      CcPreparePinWrite(*(PFILE_OBJECT *)(a2 + 424), &FileOffset, v5, 0, 1u, &Bcb, &Buffer);
      memmove(Buffer, Src, (unsigned int)v5);
      if ( !FileOffset.QuadPart )
      {
        EfsSetEfsInfoCallback((_DWORD)Buffer, v5, 2, a2 + 132, 4);
        EfsSetEfsInfoCallback((_DWORD)Buffer, v5, 3, a2 + 32, 8);
      }
      goto LABEL_11;
    }
  }
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v7 )
    ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
}

```

## disassembly

```asm
0x140004264  mov     rax, rsp
0x140004267  mov     [rax+8], rbx
0x14000426b  mov     [rax+20h], rsi
0x14000426f  mov     [rax+18h], r8
0x140004273  mov     [rax+10h], rdx
0x140004277  push    rdi
0x140004278  push    r14
0x14000427a  push    r15
0x14000427c  sub     rsp, 60h
0x140004280  mov     esi, r9d
0x140004283  mov     rbx, rdx
0x140004286  mov     qword ptr [rax-28h], 0
0x14000428e  xor     dil, dil
0x140004291  mov     [rax-38h], dil
0x140004295  mov     qword ptr [rax+18h], 0
0x14000429d  mov     qword ptr [rax-30h], 0
0x1400042a5  test    cs:byte_140017D4D, 2
0x1400042ac  jz      loc_14000447A
0x1400042b2  mov     eax, 508h
0x1400042b7  cmp     [rcx], ax
0x1400042ba  jnz     loc_140004440
0x1400042c0  mov     eax, 90h
0x1400042c5  cmp     [rcx+2], ax
0x1400042c9  jnz     loc_140004440
0x1400042cf  mov     eax, 502h
0x1400042d4  cmp     [rdx], ax
0x1400042d7  jnz     loc_140004440
0x1400042dd  call    FatAcquireExclusiveFcb
0x1400042e2  mov     edi, 1
0x1400042e7  mov     [rsp+78h+var_38], dil
0x1400042ec  test    dword ptr [rbx+0C0h], 10000h
0x1400042f6  jnz     loc_1400043AA
0x1400042fc  lea     r14, [rbx+84h]
0x140004303  mov     rcx, qword ptr [rsp+78h+FileOffset]
0x140004308  add     rcx, rsi
0x14000430b  mov     eax, [r14]
0x14000430e  cmp     rcx, rax
0x140004311  jg      loc_140004440
0x140004317  lea     rax, [rsp+78h+var_30]
0x14000431c  mov     [rsp+78h+Buffer], rax; Buffer
0x140004321  lea     rax, [rsp+78h+arg_10]
0x140004329  mov     [rsp+78h+Bcb], rax; Bcb
0x14000432e  mov     [rsp+78h+Flags], edi; Flags
0x140004332  xor     r9d, r9d; Zero
0x140004335  mov     r8d, esi; Length
0x140004338  lea     rdx, [rsp+78h+FileOffset]; FileOffset
0x14000433d  mov     rcx, [rbx+1A8h]; FileObject
0x140004344  call    cs:__imp_CcPreparePinWrite
0x14000434b  nop     dword ptr [rax+rax+00h]
0x140004350  mov     r8d, esi; Size
0x140004353  mov     rdx, [rsp+78h+Src]; Src
0x14000435b  mov     rcx, [rsp+78h+var_30]; void *
0x140004360  call    memmove
0x140004365  cmp     qword ptr [rsp+78h+FileOffset], 0
0x14000436b  jnz     loc_140004414
0x140004371  mov     [rsp+78h+Flags], 4
0x140004379  mov     r9, r14
0x14000437c  lea     r8d, [rdi+1]
0x140004380  mov     edx, esi
0x140004382  mov     rcx, [rsp+78h+var_30]
0x140004387  call    EfsSetEfsInfoCallback
0x14000438c  lea     r9, [rbx+20h]
0x140004390  mov     [rsp+78h+Flags], 8
0x140004398  lea     r8d, [rdi+2]
0x14000439c  mov     edx, esi
0x14000439e  mov     rcx, [rsp+78h+var_30]
0x1400043a3  call    EfsSetEfsInfoCallback
0x1400043a8  jmp     short loc_140004414
0x1400043aa  cmp     qword ptr [rsp+78h+FileOffset], 0
0x1400043b0  jnz     loc_140004440
0x1400043b6  cmp     esi, [rbx+20h]
0x1400043b9  ja      loc_140004440
0x1400043bf  mov     rcx, [rbx+0B0h]
0x1400043c6  lea     rax, [rsp+78h+var_30]
0x1400043cb  mov     [rsp+78h+Buffer], rax; Buffer
0x1400043d0  lea     rax, [rsp+78h+arg_10]
0x1400043d8  mov     [rsp+78h+Bcb], rax; Bcb
0x1400043dd  mov     [rsp+78h+Flags], edi; Flags
0x1400043e1  xor     r9d, r9d; Zero
0x1400043e4  mov     r8d, esi; Length
0x1400043e7  lea     rdx, [rsp+78h+FileOffset]; FileOffset
0x1400043ec  mov     rcx, [rcx+168h]; FileObject
0x1400043f3  call    cs:__imp_CcPreparePinWrite
0x1400043fa  nop     dword ptr [rax+rax+00h]
0x1400043ff  mov     r8, rsi; Size
0x140004402  mov     rdx, [rsp+78h+Src]; Src
0x14000440a  mov     rcx, [rsp+78h+var_30]; void *
0x14000440f  call    memmove
0x140004414  mov     rcx, [rsp+78h+arg_10]; Bcb
0x14000441c  call    cs:__imp_CcUnpinData
0x140004423  nop     dword ptr [rax+rax+00h]
0x140004428  mov     [rsp+78h+arg_10], 0
0x140004434  mov     r8d, edi
0x140004437  mov     rdx, rbx
0x14000443a  call    FatFlushFile
0x14000443f  nop
0x140004440  mov     rcx, [rsp+78h+arg_10]; Bcb
0x140004448  test    rcx, rcx
0x14000444b  jz      short loc_140004465
0x14000444d  call    cs:__imp_CcUnpinData
0x140004454  nop     dword ptr [rax+rax+00h]
0x140004459  mov     [rsp+78h+arg_10], 0
0x140004465  test    dil, dil
0x140004468  jz      short loc_14000447A
0x14000446a  mov     rcx, [rbx+8]; Resource
0x14000446e  call    cs:__imp_ExReleaseResourceLite
0x140004475  nop     dword ptr [rax+rax+00h]
0x14000447a  lea     r11, [rsp+78h+var_18]
0x14000447f  mov     rbx, [r11+20h]
0x140004483  mov     rsi, [r11+38h]
0x140004487  mov     rsp, r11
0x14000448a  pop     r15
0x14000448c  pop     r14
0x14000448e  pop     rdi
0x14000448f  retn
0x14000cf23  push    rbp
0x14000cf25  sub     rsp, 40h
0x14000cf29  mov     rbp, rdx
0x14000cf2c  mov     rcx, [rbp+90h]; Bcb
0x14000cf33  test    rcx, rcx
0x14000cf36  jz      short loc_14000CF4F
0x14000cf38  call    cs:__imp_CcUnpinData
0x14000cf3f  nop     dword ptr [rax+rax+00h]
0x14000cf44  mov     qword ptr [rbp+90h], 0
0x14000cf4f  cmp     byte ptr [rbp+40h], 0
0x14000cf53  jz      short loc_14000CF70
0x14000cf55  mov     rcx, [rbp+88h]
0x14000cf5c  mov     rcx, [rcx+8]; Resource
0x14000cf60  call    cs:__imp_ExReleaseResourceLite
0x14000cf67  nop     dword ptr [rax+rax+00h]
0x14000cf6c  mov     byte ptr [rbp+40h], 0
0x14000cf70  add     rsp, 40h
0x14000cf74  pop     rbp
0x14000cf75  retn
```
