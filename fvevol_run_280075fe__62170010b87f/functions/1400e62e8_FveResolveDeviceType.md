# FveResolveDeviceType

- ea: `0x1400e62e8`
- end: `0x1400e6411`
- name: `FveResolveDeviceType`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14006f9a0`
- `0x140085180`

## callees

- `0x14000aef4`
- `0x1400e62e8`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e6356`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e6388`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e6356`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400e6388`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e6314`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e632c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e6314`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400e632c`

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
0x1400e62e8  mov     rax, rsp
0x1400e62eb  mov     [rax+8], rbx
0x1400e62ef  push    rdi
0x1400e62f0  sub     rsp, 50h
0x1400e62f4  mov     rdi, [rcx+8]
0x1400e62f8  lea     rdx, aDriverVolmgr; "\\Driver\\volmgr"
0x1400e62ff  mov     rbx, rcx
0x1400e6302  xorps   xmm0, xmm0
0x1400e6305  xorps   xmm1, xmm1
0x1400e6308  lea     rcx, [rax-28h]; DestinationString
0x1400e630c  movups  xmmword ptr [rax-28h], xmm0
0x1400e6310  movups  xmmword ptr [rax-18h], xmm1
0x1400e6314  call    cs:__imp_RtlInitUnicodeString
0x1400e631b  nop     dword ptr [rax+rax+00h]
0x1400e6320  lea     rdx, aDriverCsvvbus; "\\Driver\\csvvbus"
0x1400e6327  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400e632c  call    cs:__imp_RtlInitUnicodeString
0x1400e6333  nop     dword ptr [rax+rax+00h]
0x1400e6338  cmp     dword ptr [rbx+10h], 0FFFFFFFFh
0x1400e633c  jnz     loc_1400E6403
0x1400e6342  mov     rax, [rbx+78h]
0x1400e6346  lea     rdx, [rsp+58h+String2]; String2
0x1400e634b  mov     r8b, 1; CaseInSensitive
0x1400e634e  mov     rcx, [rax+8]
0x1400e6352  add     rcx, 38h ; '8'; String1
0x1400e6356  call    cs:__imp_RtlCompareUnicodeString
0x1400e635d  nop     dword ptr [rax+rax+00h]
0x1400e6362  test    eax, eax
0x1400e6364  jnz     short loc_1400E6374
0x1400e6366  mov     dword ptr [rbx+10h], 1
0x1400e636d  mov     eax, 2Ch ; ','
0x1400e6372  jmp     short loc_1400E63B2
0x1400e6374  mov     rax, [rbx+78h]
0x1400e6378  lea     rdx, [rsp+58h+DestinationString]; String2
0x1400e637d  mov     r8b, 1; CaseInSensitive
0x1400e6380  mov     rcx, [rax+8]
0x1400e6384  add     rcx, 38h ; '8'; String1
0x1400e6388  call    cs:__imp_RtlCompareUnicodeString
0x1400e638f  nop     dword ptr [rax+rax+00h]
0x1400e6394  test    eax, eax
0x1400e6396  jnz     short loc_1400E63A6
0x1400e6398  mov     dword ptr [rbx+10h], 2
0x1400e639f  mov     eax, 30h ; '0'
0x1400e63a4  jmp     short loc_1400E63B2
0x1400e63a6  mov     dword ptr [rbx+10h], 0
0x1400e63ad  mov     eax, 28h ; '('
0x1400e63b2  mov     r8d, 1
0x1400e63b8  lock xadd [rdi+rax], r8d
0x1400e63be  inc     r8d
0x1400e63c1  mov     [rbx+14h], r8d
0x1400e63c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400e63cc  lea     rax, WPP_GLOBAL_Control
0x1400e63d3  cmp     rcx, rax
0x1400e63d6  jz      short loc_1400E6403
0x1400e63d8  mov     eax, [rcx+2Ch]
0x1400e63db  test    al, 8
0x1400e63dd  jz      short loc_1400E6403
0x1400e63df  cmp     byte ptr [rcx+29h], 5
0x1400e63e3  jb      short loc_1400E6403
0x1400e63e5  mov     r9d, [rbx+10h]
0x1400e63e9  mov     edx, 98h
0x1400e63ee  mov     rcx, [rcx+18h]
0x1400e63f2  mov     [rsp+58h+var_38], r8d
0x1400e63f7  lea     r8, WPP_1a6edff1c2d232a6eb817989127b08c7_Traceguids
0x1400e63fe  call    WPP_SF_Dd
0x1400e6403  mov     rbx, [rsp+58h+arg_0]
0x1400e6408  xor     eax, eax
0x1400e640a  add     rsp, 50h
0x1400e640e  pop     rdi
0x1400e640f  retn
```
