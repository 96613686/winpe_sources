# FveResolveDeviceType

- ea: `0x1400e8b98`
- end: `0x1400e8cc1`
- name: `FveResolveDeviceType`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140071a30`
- `0x140087220`

## callees

- `0x14000afb4`
- `0x1400e8b98`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e8c06`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e8c38`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e8c06`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e8c38`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e8bc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e8bdc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e8bc4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e8bdc`

## pseudocode

```c
__int64 __fastcall FveResolveDeviceType(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v3; // rax
  signed __int32 v4; // r8d
  UNICODE_STRING String2; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  String2 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&String2, L"\\Driver\\volmgr");
  RtlInitUnicodeString(&DestinationString, L"\\Driver\\csvvbus");
  if ( *(_DWORD *)(a1 + 16) == -1 )
  {
    if ( RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) + 56LL), &String2, 1u) )
    {
      if ( RtlCompareUnicodeString(
             (PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL) + 56LL),
             &DestinationString,
             1u) )
      {
        *(_DWORD *)(a1 + 16) = 0;
        v3 = 40;
      }
      else
      {
        *(_DWORD *)(a1 + 16) = 2;
        v3 = 48;
      }
    }
    else
    {
      *(_DWORD *)(a1 + 16) = 1;
      v3 = 44;
    }
    v4 = _InterlockedIncrement((volatile signed __int32 *)(v1 + v3));
    *(_DWORD *)(a1 + 20) = v4;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        152,
        WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids,
        *(unsigned int *)(a1 + 16),
        v4);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400e8b98  mov     rax, rsp
0x1400e8b9b  mov     [rax+8], rbx
0x1400e8b9f  push    rdi
0x1400e8ba0  sub     rsp, 50h
0x1400e8ba4  mov     rdi, [rcx+8]
0x1400e8ba8  lea     rdx, aDriverVolmgr; "\\Driver\\volmgr"
0x1400e8baf  mov     rbx, rcx
0x1400e8bb2  xorps   xmm0, xmm0
0x1400e8bb5  xorps   xmm1, xmm1
0x1400e8bb8  lea     rcx, [rax-28h]; DestinationString
0x1400e8bbc  movups  xmmword ptr [rax-28h], xmm0
0x1400e8bc0  movups  xmmword ptr [rax-18h], xmm1
0x1400e8bc4  call    cs:__imp_RtlInitUnicodeString
0x1400e8bcb  nop     dword ptr [rax+rax+00h]
0x1400e8bd0  lea     rdx, aDriverCsvvbus; "\\Driver\\csvvbus"
0x1400e8bd7  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400e8bdc  call    cs:__imp_RtlInitUnicodeString
0x1400e8be3  nop     dword ptr [rax+rax+00h]
0x1400e8be8  cmp     dword ptr [rbx+10h], 0FFFFFFFFh
0x1400e8bec  jnz     loc_1400E8CB3
0x1400e8bf2  mov     rax, [rbx+78h]
0x1400e8bf6  lea     rdx, [rsp+58h+String2]; String2
0x1400e8bfb  mov     r8b, 1; CaseInSensitive
0x1400e8bfe  mov     rcx, [rax+8]
0x1400e8c02  add     rcx, 38h ; '8'; String1
0x1400e8c06  call    cs:__imp_RtlCompareUnicodeString
0x1400e8c0d  nop     dword ptr [rax+rax+00h]
0x1400e8c12  test    eax, eax
0x1400e8c14  jnz     short loc_1400E8C24
0x1400e8c16  mov     dword ptr [rbx+10h], 1
0x1400e8c1d  mov     eax, 2Ch ; ','
0x1400e8c22  jmp     short loc_1400E8C62
0x1400e8c24  mov     rax, [rbx+78h]
0x1400e8c28  lea     rdx, [rsp+58h+DestinationString]; String2
0x1400e8c2d  mov     r8b, 1; CaseInSensitive
0x1400e8c30  mov     rcx, [rax+8]
0x1400e8c34  add     rcx, 38h ; '8'; String1
0x1400e8c38  call    cs:__imp_RtlCompareUnicodeString
0x1400e8c3f  nop     dword ptr [rax+rax+00h]
0x1400e8c44  test    eax, eax
0x1400e8c46  jnz     short loc_1400E8C56
0x1400e8c48  mov     dword ptr [rbx+10h], 2
0x1400e8c4f  mov     eax, 30h ; '0'
0x1400e8c54  jmp     short loc_1400E8C62
0x1400e8c56  mov     dword ptr [rbx+10h], 0
0x1400e8c5d  mov     eax, 28h ; '('
0x1400e8c62  mov     r8d, 1
0x1400e8c68  lock xadd [rdi+rax], r8d
0x1400e8c6e  inc     r8d
0x1400e8c71  mov     [rbx+14h], r8d
0x1400e8c75  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e8c7c  lea     rax, WPP_GLOBAL_Control
0x1400e8c83  cmp     rcx, rax
0x1400e8c86  jz      short loc_1400E8CB3
0x1400e8c88  mov     eax, [rcx+2Ch]
0x1400e8c8b  test    al, 8
0x1400e8c8d  jz      short loc_1400E8CB3
0x1400e8c8f  cmp     byte ptr [rcx+29h], 5
0x1400e8c93  jb      short loc_1400E8CB3
0x1400e8c95  mov     r9d, [rbx+10h]
0x1400e8c99  mov     edx, 98h
0x1400e8c9e  mov     rcx, [rcx+18h]
0x1400e8ca2  mov     [rsp+58h+var_38], r8d
0x1400e8ca7  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e8cae  call    WPP_SF_Dd
0x1400e8cb3  mov     rbx, [rsp+58h+arg_0]
0x1400e8cb8  xor     eax, eax
0x1400e8cba  add     rsp, 50h
0x1400e8cbe  pop     rdi
0x1400e8cbf  retn
```
