# StRtlIoStorInfoSetSenseCode

- ea: `0x140036950`
- end: `0x1400369e1`
- name: `StRtlIoStorInfoSetSenseCode`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14001c190`
- `0x14001dab0`
- `0x140020080`
- `0x140030d80`

## callees

- `0x140036950`

## import_xrefs

- `ntoskrnl!IoGetGenericIrpExtension` at `0x140036977`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x140036977`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1400369cb`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x1400369cb`

## pseudocode

```c
__int64 __fastcall StRtlIoStorInfoSetSenseCode(__int64 a1, char a2, char a3, char a4)
{
  int GenericIrpExtension; // eax
  __int64 v9; // r9
  _DWORD v11[14]; // [rsp+20h] [rbp-38h] BYREF

  v11[0] = 0;
  GenericIrpExtension = IoGetGenericIrpExtension(a1, v11, 4);
  if ( (int)(GenericIrpExtension + 0x80000000) >= 0 && GenericIrpExtension != -1073741275 )
    return 3221225485LL;
  BYTE2(v11[0]) = a3;
  HIBYTE(v11[0]) = a4;
  BYTE1(v11[0]) = (16 * a2) | BYTE1(v11[0]) & 7 | 8;
  LOBYTE(v9) = 1;
  return IoSetGenericIrpExtension(a1, v11, 4, v9);
}

```

## disassembly

```asm
0x140036950  push    rbx
0x140036952  push    rbp
0x140036953  push    rsi
0x140036954  push    rdi
0x140036955  sub     rsp, 38h
0x140036959  mov     bpl, r8b
0x14003695c  mov     [rsp+58h+var_38], 0
0x140036964  mov     bl, dl
0x140036966  mov     r8d, 4
0x14003696c  lea     rdx, [rsp+58h+var_38]
0x140036971  mov     sil, r9b
0x140036974  mov     rdi, rcx
0x140036977  call    cs:__imp_IoGetGenericIrpExtension
0x14003697e  nop     dword ptr [rax+rax+00h]
0x140036983  mov     ecx, 80000000h
0x140036988  lea     r10d, [rax+rcx]
0x14003698c  test    ecx, r10d
0x14003698f  jnz     short loc_14003699F
0x140036991  cmp     eax, 0C0000225h
0x140036996  jz      short loc_14003699F
0x140036998  mov     eax, 0C000000Dh
0x14003699d  jmp     short loc_1400369D7
0x14003699f  mov     al, byte ptr [rsp+58h+var_38+1]
0x1400369a3  lea     rdx, [rsp+58h+var_38]
0x1400369a8  and     al, 7
0x1400369aa  shl     bl, 4
0x1400369ad  or      al, bl
0x1400369af  mov     byte ptr [rsp+58h+var_38+2], bpl
0x1400369b4  or      al, 8
0x1400369b6  mov     byte ptr [rsp+58h+var_38+3], sil
0x1400369bb  mov     r8d, 4
0x1400369c1  mov     byte ptr [rsp+58h+var_38+1], al
0x1400369c5  mov     r9b, 1
0x1400369c8  mov     rcx, rdi
0x1400369cb  call    cs:__imp_IoSetGenericIrpExtension
0x1400369d2  nop     dword ptr [rax+rax+00h]
0x1400369d7  add     rsp, 38h
0x1400369db  pop     rdi
0x1400369dc  pop     rsi
0x1400369dd  pop     rbp
0x1400369de  pop     rbx
0x1400369df  retn
```
