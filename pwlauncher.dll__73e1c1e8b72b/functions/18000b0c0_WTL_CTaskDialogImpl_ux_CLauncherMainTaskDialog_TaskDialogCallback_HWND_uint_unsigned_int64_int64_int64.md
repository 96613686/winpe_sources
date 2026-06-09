# WTL::CTaskDialogImpl<ux::CLauncherMainTaskDialog>::TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000b0c0`
- end: `0x18000b146`
- name: `?TaskDialogCallback@?$CTaskDialogImpl@VCLauncherMainTaskDialog@ux@@@WTL@@SAJPEAUHWND__@@I_K_J2@Z`
- size: `134`
- prototype: `__int64 __fastcall(ux::CLauncherMainTaskDialog *, unsigned int, int, const unsigned __int16 *, ux::CLauncherMainTaskDialog *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000a4e8`
- `0x18000a62c`
- `0x18000a85c`
- `0x18000aa0c`
- `0x18000b0c0`

## pseudocode

```c
__int64 __fastcall WTL::CTaskDialogImpl<ux::CLauncherMainTaskDialog>::TaskDialogCallback(
        ux::CLauncherMainTaskDialog *a1,
        unsigned int a2,
        int a3,
        const unsigned __int16 *a4,
        ux::CLauncherMainTaskDialog *a5)
{
  unsigned int v5; // ebx
  unsigned int v6; // edx
  unsigned int v7; // edx
  unsigned int v8; // edx

  v5 = 0;
  if ( a2 > 5 )
  {
    v8 = a2 - 6;
    if ( v8 )
    {
      if ( v8 == 1 )
      {
        *((_QWORD *)a5 + 21) = a1;
        ux::CLauncherMainTaskDialog::OnDialogConstructed((HWND *)a5);
      }
    }
    else
    {
      ux::CLauncherMainTaskDialog::OnRadioButtonClicked(a5, a3);
    }
  }
  else if ( a2 == 5 )
  {
    *((_QWORD *)a5 + 21) = 0;
  }
  else if ( a2 )
  {
    v6 = a2 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        if ( v7 == 1 )
          ux::CLauncherMainTaskDialog::OnHyperlinkClicked(a1, a4);
      }
      else
      {
        return (unsigned __int8)ux::CLauncherMainTaskDialog::OnButtonClicked(a5, a3);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b0c0  push    rbx
0x18000b0c2  sub     rsp, 20h
0x18000b0c6  xor     ebx, ebx
0x18000b0c8  mov     rax, rcx
0x18000b0cb  cmp     edx, 5
0x18000b0ce  ja      short loc_18000B10F
0x18000b0d0  jz      short loc_18000B101
0x18000b0d2  test    edx, edx
0x18000b0d4  jz      short loc_18000B13E
0x18000b0d6  sub     edx, 1
0x18000b0d9  jz      short loc_18000B13E
0x18000b0db  sub     edx, 1
0x18000b0de  jz      short loc_18000B0EF
0x18000b0e0  sub     edx, 1
0x18000b0e3  jnz     short loc_18000B13E
0x18000b0e5  mov     rdx, r9; unsigned __int16 *
0x18000b0e8  call    ?OnHyperlinkClicked@CLauncherMainTaskDialog@ux@@QEAAXPEBG@Z; ux::CLauncherMainTaskDialog::OnHyperlinkClicked(ushort const *)
0x18000b0ed  jmp     short loc_18000B13E
0x18000b0ef  mov     rcx, [rsp+28h+arg_20]; this
0x18000b0f4  mov     edx, r8d; int
0x18000b0f7  call    ?OnButtonClicked@CLauncherMainTaskDialog@ux@@QEAA_NH@Z; ux::CLauncherMainTaskDialog::OnButtonClicked(int)
0x18000b0fc  movzx   ebx, al
0x18000b0ff  jmp     short loc_18000B13E
0x18000b101  mov     rax, [rsp+28h+arg_20]
0x18000b106  mov     [rax+0A8h], rbx
0x18000b10d  jmp     short loc_18000B13E
0x18000b10f  sub     edx, 6
0x18000b112  jz      short loc_18000B131
0x18000b114  sub     edx, 1
0x18000b117  jz      short loc_18000B11E
0x18000b119  sub     edx, 1
0x18000b11c  jmp     short loc_18000B13E
0x18000b11e  mov     rcx, [rsp+28h+arg_20]; this
0x18000b123  mov     [rcx+0A8h], rax
0x18000b12a  call    ?OnDialogConstructed@CLauncherMainTaskDialog@ux@@QEAAXXZ; ux::CLauncherMainTaskDialog::OnDialogConstructed(void)
0x18000b12f  jmp     short loc_18000B13E
0x18000b131  mov     rcx, [rsp+28h+arg_20]; this
0x18000b136  mov     edx, r8d; int
0x18000b139  call    ?OnRadioButtonClicked@CLauncherMainTaskDialog@ux@@QEAAXH@Z; ux::CLauncherMainTaskDialog::OnRadioButtonClicked(int)
0x18000b13e  mov     eax, ebx
0x18000b140  add     rsp, 20h
0x18000b144  pop     rbx
0x18000b145  retn
```
