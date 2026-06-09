# WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x18000b050`
- end: `0x18000b0ac`
- name: `?TaskDialogCallback@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@SAJPEAUHWND__@@I_K_J2@Z`
- size: `92`
- prototype: `__int64 __fastcall(OLECHAR *, unsigned int, __int64, const unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a710`
- `0x18000b050`

## pseudocode

```c
__int64 __fastcall WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::TaskDialogCallback(
        OLECHAR *a1,
        unsigned int a2,
        __int64 a3,
        const unsigned __int16 *a4,
        __int64 a5)
{
  if ( a2 > 5 )
  {
    if ( a2 == 7 )
      *(_QWORD *)(a5 + 168) = a1;
  }
  else if ( a2 == 5 )
  {
    *(_QWORD *)(a5 + 168) = 0;
  }
  else if ( a2 == 3 )
  {
    ux::CLauncherErrorTaskDialog::OnHyperlinkClicked(a1, a4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b050  sub     rsp, 28h
0x18000b054  cmp     edx, 5
0x18000b057  ja      short loc_18000B08A
0x18000b059  jz      short loc_18000B078
0x18000b05b  test    edx, edx
0x18000b05d  jz      short loc_18000B0A5
0x18000b05f  sub     edx, 1
0x18000b062  jz      short loc_18000B0A5
0x18000b064  sub     edx, 1
0x18000b067  jz      short loc_18000B0A5
0x18000b069  cmp     edx, 1
0x18000b06c  jnz     short loc_18000B0A5
0x18000b06e  mov     rdx, r9; unsigned __int16 *
0x18000b071  call    ?OnHyperlinkClicked@CLauncherErrorTaskDialog@ux@@QEAAXPEBG@Z; ux::CLauncherErrorTaskDialog::OnHyperlinkClicked(ushort const *)
0x18000b076  jmp     short loc_18000B0A5
0x18000b078  mov     rax, [rsp+28h+arg_20]
0x18000b07d  mov     qword ptr [rax+0A8h], 0
0x18000b088  jmp     short loc_18000B0A5
0x18000b08a  sub     edx, 6
0x18000b08d  jz      short loc_18000B0A5
0x18000b08f  sub     edx, 1
0x18000b092  jz      short loc_18000B099
0x18000b094  sub     edx, 1
0x18000b097  jmp     short loc_18000B0A5
0x18000b099  mov     rax, [rsp+28h+arg_20]
0x18000b09e  mov     [rax+0A8h], rcx
0x18000b0a5  xor     eax, eax
0x18000b0a7  add     rsp, 28h
0x18000b0ab  retn
```
