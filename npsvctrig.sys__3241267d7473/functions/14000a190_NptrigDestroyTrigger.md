# NptrigDestroyTrigger

- ea: `0x14000a190`
- end: `0x14000a317`
- name: `NptrigDestroyTrigger`
- size: `391`
- prototype: `void __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009f50`

## callees

- `0x140008ed0`
- `0x14000a190`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2de`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a2de`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a1af`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000a1af`
- `ntoskrnl!RtlCompareMemory` at `0x14000a220`
- `ntoskrnl!RtlCompareMemory` at `0x14000a220`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a1c4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a280`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a1c4`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a280`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a260`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a2ca`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a2f5`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a260`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a2ca`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a2f5`

## pseudocode

```c
void __fastcall NptrigDestroyTrigger(PCWSTR SourceString)
{
  PWSTR Buffer; // rbp
  unsigned int Length; // esi
  __int64 *i; // rbx
  __int64 *v4; // rax
  __int64 **v5; // rcx
  char *v6; // rcx
  char *DeviceExtension; // rcx
  _QWORD *j; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  FltAcquirePushLockExclusiveEx(WPP_MAIN_CB.DeviceExtension, 0);
  Buffer = DestinationString.Buffer;
  Length = DestinationString.Length;
  if ( *DestinationString.Buffer == 92 )
  {
    Length = DestinationString.Length - 2;
    Buffer = DestinationString.Buffer + 1;
  }
  for ( i = (__int64 *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1); ; i = (__int64 *)*i )
  {
    if ( i == (__int64 *)WPP_MAIN_CB.DeviceExtension + 1 )
    {
      FltReleasePushLockEx(WPP_MAIN_CB.DeviceExtension, 0);
      return;
    }
    if ( *((unsigned __int16 *)i + 8) == Length && RtlCompareMemory(Buffer, (const void *)i[3], Length) == Length )
      break;
  }
  v4 = (__int64 *)*i;
  if ( *(__int64 **)(*i + 8) != i || (v5 = (__int64 **)i[1], *v5 != i) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = (__int64)v5;
  FltReleasePushLockEx(WPP_MAIN_CB.DeviceExtension, 0);
  v6 = (char *)WPP_MAIN_CB.DeviceExtension + 24;
  *((_DWORD *)i + 8) = 4;
  FltAcquirePushLockExclusiveEx(v6, 0);
  DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
  for ( j = (_QWORD *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 4);
        j != (_QWORD *)WPP_MAIN_CB.DeviceExtension + 4;
        j = (_QWORD *)*j )
  {
    NptrigReleasePendingRequests(i, j, 3221225524LL);
    DeviceExtension = (char *)WPP_MAIN_CB.DeviceExtension;
  }
  FltReleasePushLockEx(DeviceExtension + 24, 0);
  ExFreePoolWithTag(i, 0x6774704Eu);
}

```

## disassembly

```asm
0x14000a190  mov     [rsp+arg_8], rbx
0x14000a195  mov     [rsp+arg_10], rbp
0x14000a19a  push    rsi
0x14000a19b  sub     rsp, 30h
0x14000a19f  xorps   xmm0, xmm0
0x14000a1a2  mov     rdx, rcx; SourceString
0x14000a1a5  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x14000a1aa  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x14000a1af  call    cs:__imp_RtlInitUnicodeString
0x14000a1b6  nop     dword ptr [rax+rax+00h]
0x14000a1bb  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a1c2  xor     edx, edx
0x14000a1c4  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14000a1cb  nop     dword ptr [rax+rax+00h]
0x14000a1d0  mov     rbp, [rsp+38h+DestinationString.Buffer]
0x14000a1d5  movzx   esi, [rsp+38h+DestinationString.Length]
0x14000a1da  cmp     word ptr [rbp+0], 5Ch ; '\'
0x14000a1df  jnz     short loc_14000A1E8
0x14000a1e1  sub     esi, 2
0x14000a1e4  add     rbp, 2
0x14000a1e8  mov     rbx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a1ef  mov     [rsp+38h+arg_0], rdi
0x14000a1f4  mov     rbx, [rbx+8]
0x14000a1f8  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a1ff  lea     rax, [rcx+8]
0x14000a203  cmp     rbx, rax
0x14000a206  jz      loc_14000A2F3
0x14000a20c  movzx   eax, word ptr [rbx+10h]
0x14000a210  cmp     eax, esi
0x14000a212  jnz     short loc_14000A231
0x14000a214  mov     rdx, [rbx+18h]; Source2
0x14000a218  mov     rcx, rbp; Source1
0x14000a21b  mov     r8d, esi; Length
0x14000a21e  mov     edi, esi
0x14000a220  call    cs:__imp_RtlCompareMemory
0x14000a227  nop     dword ptr [rax+rax+00h]
0x14000a22c  cmp     rax, rdi
0x14000a22f  jz      short loc_14000A236
0x14000a231  mov     rbx, [rbx]
0x14000a234  jmp     short loc_14000A1F8
0x14000a236  mov     rax, [rbx]
0x14000a239  cmp     [rax+8], rbx
0x14000a23d  jnz     loc_14000A2EC
0x14000a243  mov     rcx, [rbx+8]
0x14000a247  cmp     [rcx], rbx
0x14000a24a  jnz     loc_14000A2EC
0x14000a250  mov     [rcx], rax
0x14000a253  xor     edx, edx
0x14000a255  mov     [rax+8], rcx
0x14000a259  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a260  call    cs:__imp_FltReleasePushLockEx
0x14000a267  nop     dword ptr [rax+rax+00h]
0x14000a26c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a273  xor     edx, edx
0x14000a275  add     rcx, 18h
0x14000a279  mov     dword ptr [rbx+20h], 4
0x14000a280  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14000a287  nop     dword ptr [rax+rax+00h]
0x14000a28c  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a293  mov     rdi, [rcx+20h]
0x14000a297  lea     rax, [rcx+20h]
0x14000a29b  cmp     rdi, rax
0x14000a29e  jz      short loc_14000A2C4
0x14000a2a0  mov     r8d, 0C0000034h
0x14000a2a6  mov     rdx, rdi
0x14000a2a9  mov     rcx, rbx
0x14000a2ac  call    NptrigReleasePendingRequests
0x14000a2b1  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a2b8  mov     rdi, [rdi]
0x14000a2bb  lea     rax, [rcx+20h]
0x14000a2bf  cmp     rdi, rax
0x14000a2c2  jnz     short loc_14000A2A0
0x14000a2c4  add     rcx, 18h
0x14000a2c8  xor     edx, edx
0x14000a2ca  call    cs:__imp_FltReleasePushLockEx
0x14000a2d1  nop     dword ptr [rax+rax+00h]
0x14000a2d6  mov     edx, 6774704Eh; Tag
0x14000a2db  mov     rcx, rbx; P
0x14000a2de  call    cs:__imp_ExFreePoolWithTag
0x14000a2e5  nop     dword ptr [rax+rax+00h]
0x14000a2ea  jmp     short loc_14000A301
0x14000a2ec  mov     ecx, 3
0x14000a2f1  int     29h; Win8: RtlFailFast(ecx)
0x14000a2f3  xor     edx, edx
0x14000a2f5  call    cs:__imp_FltReleasePushLockEx
0x14000a2fc  nop     dword ptr [rax+rax+00h]
0x14000a301  mov     rdi, [rsp+38h+arg_0]
0x14000a306  mov     rbx, [rsp+38h+arg_8]
0x14000a30b  mov     rbp, [rsp+38h+arg_10]
0x14000a310  add     rsp, 30h
0x14000a314  pop     rsi
0x14000a315  retn
```
