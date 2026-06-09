# MupiRerouteCreateToProvider

- ea: `0x140010424`
- end: `0x14001052c`
- name: `MupiRerouteCreateToProvider`
- size: `264`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001bbb0`

## callees

- `0x140002ccc`
- `0x140010424`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400104a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400104a5`
- `ntoskrnl!ExAllocatePool2` at `0x14001046c`
- `ntoskrnl!ExAllocatePool2` at `0x14001046c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104de`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104bd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400104de`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010491`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140010491`

## pseudocode

```c
__int64 __fastcall MupiRerouteCreateToProvider(__int64 a1, const UNICODE_STRING *a2, int a3)
{
  UNICODE_STRING *v3; // rdi
  unsigned int v6; // ecx
  NTSTATUS appended; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  v3 = (UNICODE_STRING *)(a1 + 88);
  v6 = *(unsigned __int16 *)(a1 + 88) + a2->Length;
  DestinationString = 0;
  if ( v6 <= 0xFFFF )
  {
    DestinationString.MaximumLength = v6;
    DestinationString.Buffer = (PWSTR)ExAllocatePool2(258, (unsigned __int16)v6, 1850111309);
    if ( DestinationString.Buffer )
    {
      RtlCopyUnicodeString(&DestinationString, a2);
      appended = RtlAppendUnicodeStringToString(&DestinationString, v3);
      if ( appended < 0 )
      {
        ExFreePoolWithTag(DestinationString.Buffer, 0);
      }
      else
      {
        ExFreePoolWithTag(*(PVOID *)(a1 + 96), 0);
        appended = 260;
        *v3 = DestinationString;
      }
    }
    else
    {
      appended = -1073741670;
    }
  }
  else
  {
    appended = -1073741562;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_ZqZD(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, (_DWORD)v3, a1, (__int64)a2, appended);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140010424  push    rbx
0x140010426  push    rbp
0x140010427  push    rsi
0x140010428  push    rdi
0x140010429  sub     rsp, 58h
0x14001042d  lea     rdi, [rcx+58h]
0x140010431  mov     rsi, rcx
0x140010434  movzx   eax, word ptr [rdi]
0x140010437  xorps   xmm0, xmm0
0x14001043a  movzx   ecx, word ptr [rdx]
0x14001043d  mov     rbp, rdx
0x140010440  add     ecx, eax
0x140010442  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140010447  cmp     ecx, 0FFFFh
0x14001044d  jbe     short loc_140010459
0x14001044f  mov     ebx, 0C0000106h
0x140010454  jmp     loc_1400104EA
0x140010459  movzx   edx, cx
0x14001045c  mov     r8d, 6E46754Dh
0x140010462  mov     ecx, 102h
0x140010467  mov     [rsp+78h+DestinationString.MaximumLength], dx
0x14001046c  call    cs:__imp_ExAllocatePool2
0x140010473  nop     dword ptr [rax+rax+00h]
0x140010478  mov     [rsp+78h+DestinationString.Buffer], rax
0x14001047d  test    rax, rax
0x140010480  jnz     short loc_140010489
0x140010482  mov     ebx, 0C000009Ah
0x140010487  jmp     short loc_1400104EA
0x140010489  mov     rdx, rbp; SourceString
0x14001048c  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140010491  call    cs:__imp_RtlCopyUnicodeString
0x140010498  nop     dword ptr [rax+rax+00h]
0x14001049d  mov     rdx, rdi; Source
0x1400104a0  lea     rcx, [rsp+78h+DestinationString]; Destination
0x1400104a5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400104ac  nop     dword ptr [rax+rax+00h]
0x1400104b1  xor     edx, edx; Tag
0x1400104b3  mov     ebx, eax
0x1400104b5  test    eax, eax
0x1400104b7  js      short loc_1400104D9
0x1400104b9  mov     rcx, [rsi+60h]; P
0x1400104bd  call    cs:__imp_ExFreePoolWithTag
0x1400104c4  nop     dword ptr [rax+rax+00h]
0x1400104c9  movups  xmm0, xmmword ptr [rsp+78h+DestinationString.Length]
0x1400104ce  mov     ebx, 104h
0x1400104d3  movdqu  xmmword ptr [rdi], xmm0
0x1400104d7  jmp     short loc_1400104EA
0x1400104d9  mov     rcx, [rsp+78h+DestinationString.Buffer]; P
0x1400104de  call    cs:__imp_ExFreePoolWithTag
0x1400104e5  nop     dword ptr [rax+rax+00h]
0x1400104ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400104f1  lea     rax, WPP_GLOBAL_Control
0x1400104f8  cmp     rcx, rax
0x1400104fb  jz      short loc_140010520
0x1400104fd  test    dword ptr [rcx+2Ch], 2000000h
0x140010504  jz      short loc_140010520
0x140010506  mov     rcx, [rcx+18h]
0x14001050a  mov     r9, rdi
0x14001050d  mov     [rsp+78h+var_48], ebx
0x140010511  mov     [rsp+78h+var_50], rbp
0x140010516  mov     [rsp+78h+var_58], rsi
0x14001051b  call    WPP_SF_ZqZD
0x140010520  mov     eax, ebx
0x140010522  add     rsp, 58h
0x140010526  pop     rdi
0x140010527  pop     rsi
0x140010528  pop     rbp
0x140010529  pop     rbx
0x14001052a  retn
```
