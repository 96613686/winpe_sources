# DrCreateSrvCall

- ea: `0x14002cf60`
- end: `0x14002d0b3`
- name: `DrCreateSrvCall`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400035a0`
- `0x140006560`
- `0x14002cf60`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14002d000`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002d000`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002d019`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002d019`

## pseudocode

```c
__int64 __fastcall DrCreateSrvCall(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  unsigned __int16 v5; // dx
  wchar_t *v6; // r8
  unsigned __int16 v7; // cx
  int v8; // eax
  UNICODE_STRING String1; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
      *(_QWORD *)(a1 + 64));
  v4 = *(_QWORD *)(a1 + 64);
  v5 = *(_WORD *)v4;
  v6 = *(wchar_t **)(v4 + 8);
  v7 = *(_WORD *)(v4 + 2);
  if ( *(_WORD *)v4 >= 2u && v7 >= 2u && *v6 == 92 )
  {
    ++v6;
    v5 -= 2;
    v7 -= 2;
  }
  String1.Length = v5;
  String1.MaximumLength = v7;
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  DestinationString = 0;
  String1.Buffer = v6;
  RtlInitUnicodeString(&DestinationString, L"tsclient");
  if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
        *(_QWORD *)(a1 + 64));
    v8 = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_bd9402812a03393f9299abe31314ec3e_Traceguids,
        *(_QWORD *)(a1 + 64));
    v8 = -1073741620;
  }
  *(_DWORD *)(a2 + 280) = v8;
  (*(void (__fastcall **)(__int64))(a2 + 272))(a2);
  return 259;
}

```

## disassembly

```asm
0x14002cf60  mov     [rsp+arg_0], rbx
0x14002cf65  mov     [rsp+arg_8], rsi
0x14002cf6a  push    rdi
0x14002cf6b  sub     rsp, 40h
0x14002cf6f  mov     rdi, rdx
0x14002cf72  mov     rbx, rcx
0x14002cf75  mov     rcx, cs:WPP_GLOBAL_Control
0x14002cf7c  lea     rsi, WPP_GLOBAL_Control
0x14002cf83  cmp     rcx, rsi
0x14002cf86  jz      short loc_14002CFA7
0x14002cf88  cmp     byte ptr [rcx+29h], 4
0x14002cf8c  jb      short loc_14002CFA7
0x14002cf8e  mov     r9, [rbx+40h]
0x14002cf92  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x14002cf99  mov     rcx, [rcx+18h]
0x14002cf9d  mov     edx, 0Ah
0x14002cfa2  call    WPP_SF_Z
0x14002cfa7  mov     rax, [rbx+40h]
0x14002cfab  movzx   edx, word ptr [rax]
0x14002cfae  mov     r8, [rax+8]
0x14002cfb2  movzx   ecx, word ptr [rax+2]
0x14002cfb6  cmp     dx, 2
0x14002cfba  jb      short loc_14002CFD5
0x14002cfbc  cmp     cx, 2
0x14002cfc0  jb      short loc_14002CFD5
0x14002cfc2  cmp     word ptr [r8], 5Ch ; '\'
0x14002cfc7  jnz     short loc_14002CFD5
0x14002cfc9  add     r8, 2
0x14002cfcd  sub     dx, 2
0x14002cfd1  sub     cx, 2
0x14002cfd5  mov     [rsp+48h+String1.Length], dx
0x14002cfda  xorps   xmm0, xmm0
0x14002cfdd  mov     [rsp+48h+String1.MaximumLength], cx
0x14002cfe2  lea     rdx, aTsclient; "tsclient"
0x14002cfe9  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14002cfee  mov     dword ptr [rsp+48h+String1+4], 0
0x14002cff6  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14002cffb  mov     [rsp+48h+String1.Buffer], r8
0x14002d000  call    cs:__imp_RtlInitUnicodeString
0x14002d007  nop     dword ptr [rax+rax+00h]
0x14002d00c  mov     r8b, 1; CaseInSensitive
0x14002d00f  lea     rdx, [rsp+48h+DestinationString]; String2
0x14002d014  lea     rcx, [rsp+48h+String1]; String1
0x14002d019  call    cs:__imp_RtlEqualUnicodeString
0x14002d020  nop     dword ptr [rax+rax+00h]
0x14002d025  test    al, al
0x14002d027  jz      short loc_14002D058
0x14002d029  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d030  cmp     rcx, rsi
0x14002d033  jz      short loc_14002D054
0x14002d035  cmp     byte ptr [rcx+29h], 4
0x14002d039  jb      short loc_14002D054
0x14002d03b  mov     r9, [rbx+40h]
0x14002d03f  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x14002d046  mov     rcx, [rcx+18h]
0x14002d04a  mov     edx, 0Bh
0x14002d04f  call    WPP_SF_Z
0x14002d054  xor     eax, eax
0x14002d056  jmp     short loc_14002D088
0x14002d058  mov     rcx, cs:WPP_GLOBAL_Control
0x14002d05f  cmp     rcx, rsi
0x14002d062  jz      short loc_14002D083
0x14002d064  cmp     byte ptr [rcx+29h], 4
0x14002d068  jb      short loc_14002D083
0x14002d06a  mov     r9, [rbx+40h]
0x14002d06e  lea     r8, WPP_bd9402812a03393f9299abe31314ec3e_Traceguids
0x14002d075  mov     rcx, [rcx+18h]
0x14002d079  mov     edx, 0Ch
0x14002d07e  call    WPP_SF_Z
0x14002d083  mov     eax, 0C00000CCh
0x14002d088  mov     [rdi+118h], eax
0x14002d08e  mov     rcx, rdi
0x14002d091  mov     rax, [rdi+110h]
0x14002d098  call    _guard_dispatch_icall
0x14002d09d  mov     rbx, [rsp+48h+arg_0]
0x14002d0a2  mov     eax, 103h
0x14002d0a7  mov     rsi, [rsp+48h+arg_8]
0x14002d0ac  add     rsp, 40h
0x14002d0b0  pop     rdi
0x14002d0b1  retn
```
