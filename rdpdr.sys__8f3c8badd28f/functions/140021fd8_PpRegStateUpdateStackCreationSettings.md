# PpRegStateUpdateStackCreationSettings

- ea: `0x140021fd8`
- end: `0x14002214c`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140020f00`

## callees

- `0x140005d08`
- `0x140021af0`
- `0x140021fd8`
- `0x140022300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140022066`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022066`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400220d0`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400220d0`
- `ntoskrnl!ZwClose` at `0x1400220bc`
- `ntoskrnl!ZwClose` at `0x14002212d`
- `ntoskrnl!ZwClose` at `0x1400220bc`
- `ntoskrnl!ZwClose` at `0x14002212d`
- `ntoskrnl!ZwSetValueKey` at `0x14002211b`
- `ntoskrnl!ZwSetValueKey` at `0x14002211b`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140022046`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x140022046`

## string_xrefs

- `0x1400220e0`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !HIDWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        HIDWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) = 2;
      }
      else
      {
        HIDWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( HIDWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x140021fd8  mov     [rsp-8+arg_0], rbx
0x140021fdd  mov     [rsp-8+arg_8], rdi
0x140021fe2  push    rbp
0x140021fe3  mov     rbp, rsp
0x140021fe6  sub     rsp, 60h
0x140021fea  lea     rax, [rbp+Handle]
0x140021fee  mov     [rbp+P], 0
0x140021ff6  xor     r9d, r9d
0x140021ff9  mov     [rsp+60h+Data], rax
0x140021ffe  xor     r8d, r8d
0x140022001  mov     [rbp+KeyHandle], 0
0x140022009  mov     rdi, rdx
0x14002200c  mov     [rbp+Handle], 0
0x140022014  call    PiRegStateOpenClassKey
0x140022019  test    eax, eax
0x14002201b  js      loc_14002213B
0x140022021  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 0
0x140022028  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x14002202f  jnz     short loc_14002207E
0x140022031  xor     edx, edx
0x140022033  lea     rax, [rbp+P]
0x140022037  mov     r9b, 1
0x14002203a  mov     [rsp+60h+Data], rax
0x14002203f  mov     rcx, rbx
0x140022042  lea     r8d, [rdx+1]
0x140022046  call    cs:__imp_SeCaptureSecurityDescriptor
0x14002204d  nop     dword ptr [rax+rax+00h]
0x140022052  test    eax, eax
0x140022054  js      short loc_140022074
0x140022056  mov     rcx, [rbp+P]; P
0x14002205a  xor     edx, edx; Tag
0x14002205c  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 1
0x140022066  call    cs:__imp_ExFreePoolWithTag
0x14002206d  nop     dword ptr [rax+rax+00h]
0x140022072  jmp     short loc_14002207E
0x140022074  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 2
0x14002207e  mov     rcx, [rbp+Handle]
0x140022082  lea     rdx, aProperties; "Properties"
0x140022089  xor     eax, eax
0x14002208b  cmp     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+4, 1
0x140022092  cmovnz  rbx, rax
0x140022096  lea     rax, [rbp+KeyHandle]
0x14002209a  mov     [rsp+60h+var_30], rax
0x14002209f  mov     qword ptr [rsp+60h+DataSize], 0
0x1400220a8  mov     [rsp+60h+Data], rbx
0x1400220ad  mov     [rbp+P], rbx
0x1400220b1  call    CmRegUtilCreateWstrKey
0x1400220b6  mov     rcx, [rbp+Handle]; Handle
0x1400220ba  mov     ebx, eax
0x1400220bc  call    cs:__imp_ZwClose
0x1400220c3  nop     dword ptr [rax+rax+00h]
0x1400220c8  test    ebx, ebx
0x1400220ca  js      short loc_140022139
0x1400220cc  mov     rcx, [rdi+8]; SecurityDescriptor
0x1400220d0  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400220d7  nop     dword ptr [rax+rax+00h]
0x1400220dc  mov     r11, [rdi+8]
0x1400220e0  lea     rdx, aSecurity; "Security"
0x1400220e7  xorps   xmm0, xmm0
0x1400220ea  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400220ee  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400220f2  mov     r10d, eax
0x1400220f5  call    WdmlibRtlInitUnicodeStringEx
0x1400220fa  mov     ebx, eax
0x1400220fc  test    eax, eax
0x1400220fe  js      short loc_140022129
0x140022100  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140022104  lea     rdx, [rbp+DestinationString]; ValueName
0x140022108  mov     [rsp+60h+DataSize], r10d; DataSize
0x14002210d  mov     r9d, 3; Type
0x140022113  xor     r8d, r8d; TitleIndex
0x140022116  mov     [rsp+60h+Data], r11; Data
0x14002211b  call    cs:__imp_ZwSetValueKey
0x140022122  nop     dword ptr [rax+rax+00h]
0x140022127  mov     ebx, eax
0x140022129  mov     rcx, [rbp+KeyHandle]; Handle
0x14002212d  call    cs:__imp_ZwClose
0x140022134  nop     dword ptr [rax+rax+00h]
0x140022139  mov     eax, ebx
0x14002213b  mov     rbx, [rsp+60h+arg_0]
0x140022140  mov     rdi, [rsp+60h+arg_8]
0x140022145  add     rsp, 60h
0x140022149  pop     rbp
0x14002214a  retn
```
