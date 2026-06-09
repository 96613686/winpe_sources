# PrjfPostFsControl

- ea: `0x14002eb70`
- end: `0x14002ec29`
- name: `PrjfPostFsControl`
- size: `185`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000b1a0`
- `0x14002e1a4`
- `0x14002eb70`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x14002ebc1`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14002ebc1`
- `FLTMGR!FltReleaseContext` at `0x14002ebd0`
- `FLTMGR!FltReleaseContext` at `0x14002ebd0`

## string_xrefs

- `0x14002ec03`: `This is only possible when PrjMarkDirectoryAsPlaceholder() starts using PrjMarkDirectoryAsPlaceholder`

## pseudocode

```c
__int64 __fastcall PrjfPostFsControl(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  int v5; // r8d

  v4 = 0;
  v5 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 40LL);
  if ( v5 != 589856 )
  {
    switch ( v5 )
    {
      case 589988:
        return (unsigned int)PrjfFsctlSetReparsePointPostOp(a1, a2, a3);
      case 590860:
        MicrosoftTelemetryAssertTriggeredMsgKM("This is only possible when PrjMarkDirectoryAsPlaceholder() starts using PrjMarkDirectoryAsPlaceholder");
        return v4;
      case 623428:
      case 623592:
        if ( *(int *)(a1 + 24) < 0 )
        {
          if ( !a3 )
            return v4;
        }
        else
        {
          if ( !a3 )
          {
            MicrosoftTelemetryAssertTriggeredMsgKM("Missing streamhandle context!");
            return v4;
          }
          *(_DWORD *)(a3 + 40) |= 4u;
        }
        goto LABEL_8;
    }
    if ( a3 )
    {
      ExReleaseRundownProtection((PEX_RUNDOWN_REF)(a3 + 80));
LABEL_8:
      FltReleaseContext((PFLT_CONTEXT)a3);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14002eb70  mov     [rsp+arg_0], rbx
0x14002eb75  push    rdi
0x14002eb76  sub     rsp, 20h
0x14002eb7a  mov     rax, [rcx+10h]
0x14002eb7e  mov     rbx, r8
0x14002eb81  xor     edi, edi
0x14002eb83  mov     r8d, [rax+28h]
0x14002eb87  cmp     r8d, 90020h
0x14002eb8e  jz      loc_14002EC1B
0x14002eb94  cmp     r8d, 900A4h
0x14002eb9b  jz      short loc_14002EC11
0x14002eb9d  cmp     r8d, 9040Ch
0x14002eba4  jz      short loc_14002EC03
0x14002eba6  cmp     r8d, 98344h
0x14002ebad  jz      short loc_14002EBDE
0x14002ebaf  cmp     r8d, 983E8h
0x14002ebb6  jz      short loc_14002EBDE
0x14002ebb8  test    rbx, rbx
0x14002ebbb  jz      short loc_14002EC1B
0x14002ebbd  lea     rcx, [rbx+50h]; RunRef
0x14002ebc1  call    cs:__imp_ExReleaseRundownProtection
0x14002ebc8  nop     dword ptr [rax+rax+00h]
0x14002ebcd  mov     rcx, rbx; Context
0x14002ebd0  call    cs:__imp_FltReleaseContext
0x14002ebd7  nop     dword ptr [rax+rax+00h]
0x14002ebdc  jmp     short loc_14002EC1B
0x14002ebde  cmp     [rcx+18h], edi
0x14002ebe1  jl      short loc_14002EBFC
0x14002ebe3  test    rbx, rbx
0x14002ebe6  jnz     short loc_14002EBF6
0x14002ebe8  lea     rcx, aMissingStreamh; "Missing streamhandle context!"
0x14002ebef  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002ebf4  jmp     short loc_14002EC1B
0x14002ebf6  or      dword ptr [rbx+28h], 4
0x14002ebfa  jmp     short loc_14002EBCD
0x14002ebfc  test    rbx, rbx
0x14002ebff  jz      short loc_14002EC1B
0x14002ec01  jmp     short loc_14002EBCD
0x14002ec03  lea     rcx, aThisIsOnlyPoss; "This is only possible when PrjMarkDirec"...
0x14002ec0a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002ec0f  jmp     short loc_14002EC1B
0x14002ec11  mov     r8, rbx
0x14002ec14  call    PrjfFsctlSetReparsePointPostOp
0x14002ec19  mov     edi, eax
0x14002ec1b  mov     rbx, [rsp+28h+arg_0]
0x14002ec20  mov     eax, edi
0x14002ec22  add     rsp, 20h
0x14002ec26  pop     rdi
0x14002ec27  retn
```
