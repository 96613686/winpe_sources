# HidpFdoPowerCompletion

- ea: `0x18000f4f0`
- end: `0x18000f89f`
- name: `HidpFdoPowerCompletion`
- size: `943`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000f4f0`
- `0x18000f8a8`
- `0x18000ff44`
- `0x180010814`
- `0x1800163bc`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000f710`
- `ntoskrnl!PoGetSystemWake` at `0x18000f740`
- `ntoskrnl!PoGetSystemWake` at `0x18000f740`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f724`
- `ntoskrnl!PoStartNextPowerIrp` at `0x18000f724`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f5ac`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f79b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f5ac`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x18000f79b`

## pseudocode

```c
__int64 __fastcall HidpFdoPowerCompletion(__int64 a1, IRP *a2, __int64 a3)
{
  int Status; // ebp
  $E18ADDA25AF0B5F6794A1D3AE4197A6C *v4; // r14
  char v6; // di
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  _QWORD *v8; // rbx
  unsigned __int8 MinorFunction; // al
  unsigned int Options; // ecx
  __int64 v11; // rax
  int v12; // edx
  int v13; // r8d
  __int64 *v14; // rdx
  unsigned int LowPart; // ecx
  __int64 v17; // rdx
  int v18; // edx

  Status = a2->IoStatus.Status;
  v4 = &a2->Tail.Overlay.64;
  v6 = 1;
  if ( a2->PendingReturned )
    v4->CurrentStackLocation->Control |= 1u;
  if ( *(_BYTE *)(a3 + 24) )
    a3 = *(_QWORD *)(a3 + 96);
  CurrentStackLocation = v4->CurrentStackLocation;
  v8 = (_QWORD *)(a3 + 32);
  MinorFunction = CurrentStackLocation->MinorFunction;
  if ( MinorFunction )
  {
    if ( Status >= 0 )
    {
      if ( MinorFunction != 2 )
        return (unsigned int)Status;
      Options = CurrentStackLocation->Parameters.Create.Options;
      if ( Options )
      {
        if ( Options == 1 && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
        {
          if ( *(_DWORD *)(a3 + 396) != 1 )
          {
            v11 = *(_QWORD *)(a3 + 40);
            *(_DWORD *)(a3 + 396) = 1;
            if ( !*(_BYTE *)(v11 + 296) && !*(_BYTE *)(a3 + 444) )
              HidpStartAllPingPongs(a3 + 32, 1);
          }
          IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)v8 + 20, a2, 0x20u);
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
            v13 = 0;
            LOBYTE(v12) = 0;
          }
          else
          {
            LOBYTE(v12) = 1;
            v13 = 0;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            v6 = 0;
          }
          if ( (_BYTE)v12 || v6 )
          {
            LOBYTE(v13) = v6;
            WPP_RECORDER_AND_TRACE_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              v12,
              v13,
              v8[84],
              5,
              9,
              39,
              (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
              *v8);
          }
        }
        return (unsigned int)Status;
      }
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      *(_DWORD *)(a3 + 392) = LowPart;
      if ( LowPart != 1 || *(_BYTE *)(*(_QWORD *)(a3 + 40) + 297LL) )
      {
        Status = -1073741802;
        a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        *(_QWORD *)(a3 + 536) = a2;
        if ( LowPart != 1 )
        {
          v17 = 2027;
LABEL_34:
          HIDSM_AddHidsmEvent(v8, v17);
          return (unsigned int)Status;
        }
      }
      else
      {
        *(_QWORD *)(a3 + 536) = MmBadPointer;
        PoStartNextPowerIrp(a2);
        Status = 0;
      }
      v17 = 2026;
      goto LABEL_34;
    }
    v14 = WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids;
    if ( MinorFunction == 2
      && CurrentStackLocation->Parameters.Create.Options == 1
      && CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 1 )
    {
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a3 + 672), a2, 0x20u);
      LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(a3) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
      {
        LOBYTE(a3) = 0;
      }
      if ( (_BYTE)v18 || (_BYTE)a3 )
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          a3,
          v8[84],
          5,
          9,
          40,
          (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
          *v8);
      v14 = WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids;
    }
    if ( Status != -1073741536 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v6 = 0;
      }
      if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = v6;
        LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qqcd(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v14,
          a3,
          v8[84],
          3,
          9,
          41,
          (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
          *v8,
          (char)a2,
          CurrentStackLocation->MinorFunction,
          a2->IoStatus.Status);
      }
    }
  }
  else
  {
    if ( Status >= 0 && PoGetSystemWake(a2) )
      *((_BYTE *)v8 + 380) = 1;
    return _InterlockedExchange((volatile __int32 *)v8 + 94, 7) != 4 ? 0xC0000016 : 0;
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x18000f4f0  push    rbx
0x18000f4f2  push    rbp
0x18000f4f3  push    rsi
0x18000f4f4  push    rdi
0x18000f4f5  push    r12
0x18000f4f7  push    r13
0x18000f4f9  push    r14
0x18000f4fb  sub     rsp, 60h
0x18000f4ff  mov     ebp, [rdx+30h]
0x18000f502  lea     r14, [rdx+0B8h]
0x18000f509  xor     r9d, r9d
0x18000f50c  mov     rsi, rdx
0x18000f50f  mov     edi, 1
0x18000f514  cmp     [rdx+41h], r9b
0x18000f518  jz      short loc_18000F521
0x18000f51a  mov     rax, [r14]
0x18000f51d  or      [rax+3], dil
0x18000f521  cmp     [r8+18h], r9b
0x18000f525  jnz     loc_18000F759
0x18000f52b  mov     r14, [r14]
0x18000f52e  lea     rbx, [r8+20h]
0x18000f532  mov     al, [r14+1]
0x18000f536  test    al, al
0x18000f538  jz      loc_18000F6E1
0x18000f53e  test    ebp, ebp
0x18000f540  js      loc_18000F642
0x18000f546  cmp     al, 2
0x18000f548  jnz     loc_18000F697
0x18000f54e  mov     ecx, [r14+10h]
0x18000f552  test    ecx, ecx
0x18000f554  jz      loc_18000F6A9
0x18000f55a  cmp     ecx, edi
0x18000f55c  jnz     loc_18000F697
0x18000f562  mov     edx, [r14+18h]
0x18000f566  cmp     edx, edi
0x18000f568  jnz     loc_18000F697
0x18000f56e  cmp     [rbx+16Ch], edi
0x18000f574  jz      short loc_18000F59C
0x18000f576  mov     rax, [rbx+8]
0x18000f57a  mov     [rbx+16Ch], edx
0x18000f580  cmp     [rax+128h], r9b
0x18000f587  jnz     short loc_18000F59C
0x18000f589  cmp     [rbx+19Ch], r9b
0x18000f590  jnz     short loc_18000F59C
0x18000f592  mov     edx, edi
0x18000f594  mov     rcx, rbx
0x18000f597  call    HidpStartAllPingPongs
0x18000f59c  lea     rcx, [rbx+280h]; RemoveLock
0x18000f5a3  mov     r8d, 20h ; ' '; RemlockSize
0x18000f5a9  mov     rdx, rsi; Tag
0x18000f5ac  call    cs:__imp_IoReleaseRemoveLockEx
0x18000f5b3  nop     dword ptr [rax+rax+00h]
0x18000f5b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f5bf  lea     r13, WPP_GLOBAL_Control
0x18000f5c6  cmp     rcx, r13
0x18000f5c9  jz      short loc_18000F5D8
0x18000f5cb  test    dword ptr [rcx+2Ch], 100h
0x18000f5d2  jnz     loc_18000F762
0x18000f5d8  xor     r8d, r8d
0x18000f5db  mov     dl, r8b
0x18000f5de  lea     r12, WPP_RECORDER_INITIALIZED
0x18000f5e5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f5ec  jz      short loc_18000F5F5
0x18000f5ee  cmp     [rcx+48h], r8w
0x18000f5f3  jnz     short loc_18000F5F8
0x18000f5f5  mov     dil, r8b
0x18000f5f8  test    dl, dl
0x18000f5fa  jnz     short loc_18000F605
0x18000f5fc  test    dil, dil
0x18000f5ff  jz      loc_18000F697
0x18000f605  mov     rax, [rbx]
0x18000f608  mov     r8b, dil
0x18000f60b  mov     r9, [rbx+2A0h]
0x18000f612  mov     rcx, [rcx+18h]
0x18000f616  mov     [rsp+98h+var_58], rax
0x18000f61b  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18000f622  mov     [rsp+98h+var_60], rax
0x18000f627  mov     [rsp+98h+var_68], 27h ; '''
0x18000f62e  mov     [rsp+98h+var_70], 9
0x18000f636  mov     [rsp+98h+var_78], 5
0x18000f63b  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000f640  jmp     short loc_18000F697
0x18000f642  lea     r13, WPP_GLOBAL_Control
0x18000f649  lea     r12, WPP_RECORDER_INITIALIZED
0x18000f650  lea     rdx, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18000f657  cmp     al, 2
0x18000f659  jz      loc_18000F777
0x18000f65f  cmp     ebp, 0C0000120h
0x18000f665  jz      short loc_18000F697
0x18000f667  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f66e  cmp     rcx, r13
0x18000f671  jnz     loc_18000F836
0x18000f677  mov     dil, r9b
0x18000f67a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f681  setnz   r8b
0x18000f685  test    dil, dil
0x18000f688  jnz     loc_18000F852
0x18000f68e  test    r8b, r8b
0x18000f691  jnz     loc_18000F852
0x18000f697  mov     eax, ebp
0x18000f699  add     rsp, 60h
0x18000f69d  pop     r14
0x18000f69f  pop     r13
0x18000f6a1  pop     r12
0x18000f6a3  pop     rdi
0x18000f6a4  pop     rsi
0x18000f6a5  pop     rbp
0x18000f6a6  pop     rbx
0x18000f6a7  retn
0x18000f6a9  mov     ecx, [r14+18h]
0x18000f6ad  mov     [rbx+168h], ecx
0x18000f6b3  cmp     ecx, edi
0x18000f6b5  jz      short loc_18000F703
0x18000f6b7  mov     rax, [rdx+0B8h]
0x18000f6be  mov     ebp, 0C0000016h
0x18000f6c3  or      [rax+3], dil
0x18000f6c7  mov     [rbx+1F8h], rsi
0x18000f6ce  cmp     ecx, edi
0x18000f6d0  jz      short loc_18000F736
0x18000f6d2  mov     edx, 7EBh
0x18000f6d7  mov     rcx, rbx
0x18000f6da  call    HIDSM_AddHidsmEvent
0x18000f6df  jmp     short loc_18000F697
0x18000f6e1  test    ebp, ebp
0x18000f6e3  jns     short loc_18000F73D
0x18000f6e5  mov     ecx, 7
0x18000f6ea  mov     eax, 4
0x18000f6ef  xchg    ecx, [rbx+178h]
0x18000f6f5  sub     eax, ecx
0x18000f6f7  neg     eax
0x18000f6f9  sbb     ebp, ebp
0x18000f6fb  and     ebp, 0C0000016h
0x18000f701  jmp     short loc_18000F697
0x18000f703  mov     rax, [rbx+8]
0x18000f707  cmp     [rax+129h], r9b
0x18000f70e  jnz     short loc_18000F6B7
0x18000f710  mov     rax, cs:MmBadPointer
0x18000f717  mov     rcx, [rax]
0x18000f71a  mov     [rbx+1F8h], rcx
0x18000f721  mov     rcx, rsi; Irp
0x18000f724  call    cs:__imp_PoStartNextPowerIrp
0x18000f72b  nop     dword ptr [rax+rax+00h]
0x18000f730  xor     r8d, r8d
0x18000f733  mov     ebp, r8d
0x18000f736  mov     edx, 7EAh
0x18000f73b  jmp     short loc_18000F6D7
0x18000f73d  mov     rcx, rsi; Irp
0x18000f740  call    cs:__imp_PoGetSystemWake
0x18000f747  nop     dword ptr [rax+rax+00h]
0x18000f74c  test    al, al
0x18000f74e  jz      short loc_18000F6E5
0x18000f750  mov     [rbx+17Ch], dil
0x18000f757  jmp     short loc_18000F6E5
0x18000f759  mov     r8, [r8+60h]
0x18000f75d  jmp     loc_18000F52B
0x18000f762  cmp     byte ptr [rcx+29h], 5
0x18000f766  jb      loc_18000F5D8
0x18000f76c  mov     dl, dil
0x18000f76f  xor     r8d, r8d
0x18000f772  jmp     loc_18000F5DE
0x18000f777  cmp     [r14+10h], edi
0x18000f77b  jnz     loc_18000F65F
0x18000f781  cmp     [r14+18h], edi
0x18000f785  jnz     loc_18000F65F
0x18000f78b  lea     rcx, [rbx+280h]; RemoveLock
0x18000f792  mov     r8d, 20h ; ' '; RemlockSize
0x18000f798  mov     rdx, rsi; Tag
0x18000f79b  call    cs:__imp_IoReleaseRemoveLockEx
0x18000f7a2  nop     dword ptr [rax+rax+00h]
0x18000f7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7ae  cmp     rcx, r13
0x18000f7b1  jz      short loc_18000F7CA
0x18000f7b3  test    dword ptr [rcx+2Ch], 100h
0x18000f7ba  jz      short loc_18000F7CA
0x18000f7bc  cmp     byte ptr [rcx+29h], 5
0x18000f7c0  jb      short loc_18000F7CA
0x18000f7c2  mov     dl, dil
0x18000f7c5  xor     r9d, r9d
0x18000f7c8  jmp     short loc_18000F7D0
0x18000f7ca  xor     r9d, r9d
0x18000f7cd  mov     dl, r9b
0x18000f7d0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000f7d7  jz      short loc_18000F7E3
0x18000f7d9  mov     r8b, dil
0x18000f7dc  cmp     [rcx+48h], r9w
0x18000f7e1  jnz     short loc_18000F7E6
0x18000f7e3  mov     r8b, r9b
0x18000f7e6  test    dl, dl
0x18000f7e8  jnz     short loc_18000F7EF
0x18000f7ea  test    r8b, r8b
0x18000f7ed  jz      short loc_18000F82A
0x18000f7ef  mov     rax, [rbx]
0x18000f7f2  mov     r9, [rbx+2A0h]
0x18000f7f9  mov     rcx, [rcx+18h]
0x18000f7fd  mov     [rsp+98h+var_58], rax
0x18000f802  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18000f809  mov     [rsp+98h+var_60], rax
0x18000f80e  mov     [rsp+98h+var_68], 28h ; '('
0x18000f815  mov     [rsp+98h+var_70], 9
0x18000f81d  mov     [rsp+98h+var_78], 5
0x18000f822  call    WPP_RECORDER_AND_TRACE_SF_q
0x18000f827  xor     r9d, r9d
0x18000f82a  lea     rdx, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18000f831  jmp     loc_18000F65F
0x18000f836  test    dword ptr [rcx+2Ch], 100h
0x18000f83d  jz      loc_18000F677
0x18000f843  cmp     byte ptr [rcx+29h], 3
0x18000f847  jnb     loc_18000F67A
0x18000f84d  jmp     loc_18000F677
0x18000f852  mov     eax, [rsi+30h]
0x18000f855  mov     r9, [rbx+2A0h]
0x18000f85c  mov     rcx, [rcx+18h]
0x18000f860  mov     [rsp+98h+var_40], eax
0x18000f864  mov     al, [r14+1]
0x18000f868  mov     [rsp+98h+var_48], al
0x18000f86c  mov     rax, [rbx]
0x18000f86f  mov     [rsp+98h+var_50], rsi
0x18000f874  mov     [rsp+98h+var_58], rax
0x18000f879  mov     [rsp+98h+var_60], rdx
0x18000f87e  mov     dl, dil
0x18000f881  mov     [rsp+98h+var_68], 29h ; ')'
0x18000f888  mov     [rsp+98h+var_70], 9
0x18000f890  mov     [rsp+98h+var_78], 3
0x18000f895  call    WPP_RECORDER_AND_TRACE_SF_qqcd
0x18000f89a  jmp     loc_18000F697
```
