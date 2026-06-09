# CuipAMInitializeAPCProc(unsigned __int64)

- ea: `0x140006a30`
- end: `0x140006b1e`
- name: `?CuipAMInitializeAPCProc@@YAX_K@Z`
- size: `238`
- prototype: `void __fastcall(ULONG_PTR Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006a30`
- `0x14000fbec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006a8e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x140006a4c`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x140006a4c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140006a83`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140006a83`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006a40`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140006a40`
- `Amsi!AmsiUacInitialize` at `0x140006a5a`
- `Amsi!AmsiUacInitialize` at `0x140006a5a`

## pseudocode

```c
void __fastcall CuipAMInitializeAPCProc(ULONG_PTR Parameter)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  int v4; // eax

  v2 = CoInitializeEx(0, 2u);
  if ( v2 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_D(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids,
        (unsigned int)v2);
  }
  else
  {
    v3 = CoEnableCallCancellation(0);
    if ( v3 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          11,
          WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids,
          (unsigned int)v3);
      goto LABEL_8;
    }
    v4 = AmsiUacInitialize(Parameter + 32);
    if ( v4 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          12,
          WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids,
          (unsigned int)v4);
      CoDisableCallCancellation(0);
LABEL_8:
      CoUninitialize();
    }
  }
}

```

## disassembly

```asm
0x140006a30  push    rbx
0x140006a32  sub     rsp, 20h
0x140006a36  mov     rbx, rcx
0x140006a39  mov     edx, 2; dwCoInit
0x140006a3e  xor     ecx, ecx; pvReserved
0x140006a40  call    cs:__imp_CoInitializeEx
0x140006a46  test    eax, eax
0x140006a48  js      short loc_140006A9B
0x140006a4a  xor     ecx, ecx; pReserved
0x140006a4c  call    cs:__imp_CoEnableCallCancellation
0x140006a52  test    eax, eax
0x140006a54  js      short loc_140006ACE
0x140006a56  lea     rcx, [rbx+20h]
0x140006a5a  call    cs:__imp_AmsiUacInitialize
0x140006a60  test    eax, eax
0x140006a62  jns     short loc_140006A95
0x140006a64  mov     rcx, cs:WPP_GLOBAL_Control
0x140006a6b  lea     rdx, WPP_GLOBAL_Control
0x140006a72  cmp     rcx, rdx
0x140006a75  jz      short loc_140006A81
0x140006a77  test    byte ptr [rcx+1Ch], 2
0x140006a7b  jnz     loc_140006B01
0x140006a81  xor     ecx, ecx; pReserved
0x140006a83  call    cs:__imp_CoDisableCallCancellation
0x140006a89  add     rsp, 20h
0x140006a8d  pop     rbx
0x140006a8e  jmp     cs:__imp_CoUninitialize
0x140006a95  add     rsp, 20h
0x140006a99  pop     rbx
0x140006a9a  retn
0x140006a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006aa2  lea     rdx, WPP_GLOBAL_Control
0x140006aa9  cmp     rcx, rdx
0x140006aac  jz      short loc_140006A95
0x140006aae  test    byte ptr [rcx+1Ch], 2
0x140006ab2  jz      short loc_140006A95
0x140006ab4  mov     rcx, [rcx+10h]
0x140006ab8  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140006abf  mov     edx, 0Ah
0x140006ac4  mov     r9d, eax
0x140006ac7  call    WPP_SF_D
0x140006acc  jmp     short loc_140006A95
0x140006ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ad5  lea     rdx, WPP_GLOBAL_Control
0x140006adc  cmp     rcx, rdx
0x140006adf  jz      short loc_140006A89
0x140006ae1  test    byte ptr [rcx+1Ch], 2
0x140006ae5  jz      short loc_140006A89
0x140006ae7  mov     rcx, [rcx+10h]
0x140006aeb  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140006af2  mov     edx, 0Bh
0x140006af7  mov     r9d, eax
0x140006afa  call    WPP_SF_D
0x140006aff  jmp     short loc_140006A89
0x140006b01  mov     rcx, [rcx+10h]
0x140006b05  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x140006b0c  mov     edx, 0Ch
0x140006b11  mov     r9d, eax
0x140006b14  call    WPP_SF_D
0x140006b19  jmp     loc_140006A81
```
