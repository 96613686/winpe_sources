# AddHardwareKey

- ea: `0x140001064`
- end: `0x140001169`
- name: `AddHardwareKey`
- size: `261`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140001430`
- `0x140001c70`
- `0x140002000`
- `0x140002270`

## callees

- `0x140001064`
- `0x140001280`
- `0x1400028e8`
- `0x140003e00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001134`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001134`

## pseudocode

```c
void __fastcall AddHardwareKey(__int64 a1, char a2)
{
  void *v4; // rdi
  unsigned int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // [rsp+60h] [rbp+18h] BYREF

  v7 = 0;
  if ( g_fHwProvAvailable )
  {
    if ( !*(_QWORD *)(a1 + 24) && !*(_BYTE *)(a1 + 12) && !*(_BYTE *)(a1 + 108) )
    {
      v4 = (void *)ProvAlloc((unsigned int)g_cbHardwareKeyObjectSize);
      if ( v4 )
      {
        v5 = *(_DWORD *)(a1 + 8);
        if ( v5 >= 3 )
          v6 = 0;
        else
          v6 = g_hAlgHardware[v5];
        if ( (*(int (__fastcall **)(__int64, __int64 *, void *, _QWORD, __int64, _DWORD, _DWORD))(g_pHwCipherFunctionTable
                                                                                                + 40))(
               v6,
               &v7,
               v4,
               (unsigned int)g_cbHardwareKeyObjectSize,
               a1 + 56,
               *(_DWORD *)(a1 + 88),
               0) >= 0 )
        {
          *(_QWORD *)(a1 + 24) = v7;
          *(_QWORD *)(a1 + 32) = v4;
        }
        else
        {
          if ( a2 )
            SwitchKeyToSoftwareOnly(a1);
          else
            *(_BYTE *)(a1 + 108) = 1;
          ExFreePoolWithTag(v4, 0x48676E43u);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x140001064  mov     [rsp+arg_0], rbx
0x140001069  mov     [rsp+arg_8], rsi
0x14000106e  push    rdi
0x14000106f  sub     rsp, 40h
0x140001073  cmp     cs:g_fHwProvAvailable, 0
0x14000107a  mov     sil, dl
0x14000107d  mov     rbx, rcx
0x140001080  mov     [rsp+48h+arg_10], 0
0x140001089  jz      loc_140001158
0x14000108f  cmp     qword ptr [rcx+18h], 0
0x140001094  jnz     loc_140001158
0x14000109a  cmp     byte ptr [rcx+0Ch], 0
0x14000109e  jnz     loc_140001158
0x1400010a4  cmp     byte ptr [rcx+6Ch], 0
0x1400010a8  jnz     loc_140001158
0x1400010ae  mov     ecx, cs:g_cbHardwareKeyObjectSize; Size
0x1400010b4  call    ProvAlloc
0x1400010b9  mov     rdi, rax
0x1400010bc  test    rax, rax
0x1400010bf  jz      loc_140001158
0x1400010c5  mov     eax, [rbx+8]
0x1400010c8  cmp     eax, 3
0x1400010cb  jnb     short loc_1400010DC
0x1400010cd  mov     ecx, eax
0x1400010cf  lea     rax, g_hAlgHardware
0x1400010d6  mov     rcx, [rax+rcx*8]
0x1400010da  jmp     short loc_1400010DE
0x1400010dc  xor     ecx, ecx
0x1400010de  mov     edx, [rbx+58h]
0x1400010e1  lea     r8, [rbx+38h]
0x1400010e5  mov     rax, cs:g_pHwCipherFunctionTable
0x1400010ec  mov     r9d, cs:g_cbHardwareKeyObjectSize
0x1400010f3  mov     [rsp+48h+var_18], 0
0x1400010fb  mov     [rsp+48h+var_20], edx
0x1400010ff  lea     rdx, [rsp+48h+arg_10]
0x140001104  mov     rax, [rax+28h]
0x140001108  mov     [rsp+48h+var_28], r8
0x14000110d  mov     r8, rdi
0x140001110  call    _guard_dispatch_icall
0x140001115  test    eax, eax
0x140001117  jns     short loc_140001142
0x140001119  test    sil, sil
0x14000111c  jz      short loc_140001128
0x14000111e  mov     rcx, rbx
0x140001121  call    SwitchKeyToSoftwareOnly
0x140001126  jmp     short loc_14000112C
0x140001128  mov     byte ptr [rbx+6Ch], 1
0x14000112c  mov     edx, 48676E43h; Tag
0x140001131  mov     rcx, rdi; P
0x140001134  call    cs:__imp_ExFreePoolWithTag
0x14000113b  nop     dword ptr [rax+rax+00h]
0x140001140  jmp     short loc_140001158
0x140001142  mov     rax, [rsp+48h+arg_10]
0x140001147  mov     [rbx+18h], rax
0x14000114b  mov     [rsp+48h+arg_10], 0
0x140001154  mov     [rbx+20h], rdi
0x140001158  mov     rbx, [rsp+48h+arg_0]
0x14000115d  mov     rsi, [rsp+48h+arg_8]
0x140001162  add     rsp, 40h
0x140001166  pop     rdi
0x140001167  retn
```
