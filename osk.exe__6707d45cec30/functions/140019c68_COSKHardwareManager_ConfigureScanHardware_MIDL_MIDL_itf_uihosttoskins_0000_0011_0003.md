# COSKHardwareManager::ConfigureScanHardware(__MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *)

- ea: `0x140019c68`
- end: `0x140019d0c`
- name: `?ConfigureScanHardware@COSKHardwareManager@@QEAAXPEAU__MIDL___MIDL_itf_uihosttoskins_0000_0011_0003@@@Z`
- size: `164`
- prototype: `void __fastcall(COSKHardwareManager *__hidden this, struct __MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140013b1c`

## callees

- `0x14000def8`
- `0x14000df20`
- `0x140019c68`

## import_xrefs

- `WINMM!joySetCapture` at `0x140019cc4`
- `WINMM!joySetCapture` at `0x140019cc4`

## pseudocode

```c
void __fastcall COSKHardwareManager::ConfigureScanHardware(
        HWND *this,
        struct __MIDL___MIDL_itf_uihosttoskins_0000_0011_0003 *a2)
{
  MMRESULT v3; // eax

  if ( *((_DWORD *)a2 + 1) == 3 && *((_DWORD *)a2 + 4) && !*((_DWORD *)this + 2) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_74269121aeae302946f94be8b6cc61dc_Traceguids);
    v3 = joySetCapture(*this, 0, 0, 0);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_74269121aeae302946f94be8b6cc61dc_Traceguids, v3);
    }
    else
    {
      *((_DWORD *)this + 2) = 1;
    }
  }
}

```

## disassembly

```asm
0x140019c68  mov     [rsp+arg_0], rbx
0x140019c6d  push    rdi
0x140019c6e  sub     rsp, 20h
0x140019c72  cmp     dword ptr [rdx+4], 3
0x140019c76  mov     rbx, rcx
0x140019c79  jnz     loc_140019D01
0x140019c7f  cmp     dword ptr [rdx+10h], 0
0x140019c83  jz      short loc_140019D01
0x140019c85  cmp     dword ptr [rcx+8], 0
0x140019c89  jnz     short loc_140019D01
0x140019c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140019c92  lea     rdi, WPP_GLOBAL_Control
0x140019c99  cmp     rcx, rdi
0x140019c9c  jz      short loc_140019CB9
0x140019c9e  test    byte ptr [rcx+1Ch], 10h
0x140019ca2  jz      short loc_140019CB9
0x140019ca4  mov     rcx, [rcx+10h]
0x140019ca8  lea     r8, WPP_74269121aeae302946f94be8b6cc61dc_Traceguids
0x140019caf  mov     edx, 0Eh
0x140019cb4  call    WPP_SF_
0x140019cb9  mov     rcx, [rbx]; hwnd
0x140019cbc  xor     r9d, r9d; fChanged
0x140019cbf  xor     r8d, r8d; uPeriod
0x140019cc2  xor     edx, edx; uJoyID
0x140019cc4  call    cs:__imp_joySetCapture
0x140019cca  test    eax, eax
0x140019ccc  jnz     short loc_140019CD7
0x140019cce  mov     dword ptr [rbx+8], 1
0x140019cd5  jmp     short loc_140019D01
0x140019cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140019cde  cmp     rcx, rdi
0x140019ce1  jz      short loc_140019D01
0x140019ce3  test    byte ptr [rcx+1Ch], 1
0x140019ce7  jz      short loc_140019D01
0x140019ce9  mov     rcx, [rcx+10h]
0x140019ced  lea     r8, WPP_74269121aeae302946f94be8b6cc61dc_Traceguids
0x140019cf4  mov     edx, 0Fh
0x140019cf9  mov     r9d, eax
0x140019cfc  call    WPP_SF_d
0x140019d01  mov     rbx, [rsp+28h+arg_0]
0x140019d06  add     rsp, 20h
0x140019d0a  pop     rdi
0x140019d0b  retn
```
