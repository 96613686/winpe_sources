# AutoExecutionPowerHold::AutoExecutionPowerHold(void)

- ea: `0x18000d1a4`
- end: `0x18000d23c`
- name: `??0AutoExecutionPowerHold@@QEAA@XZ`
- size: `152`
- prototype: `AutoExecutionPowerHold *__fastcall(AutoExecutionPowerHold *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180010160`

## callees

- `0x18000d1a4`
- `0x18000e3d0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18000d219`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18000d228`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18000d219`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18000d228`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18000d1ed`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerCreateRequest` at `0x18000d1ed`

## string_xrefs

- `0x18000d1c3`: `OOBE scanning updates`

## pseudocode

```c
AutoExecutionPowerHold *__fastcall AutoExecutionPowerHold::AutoExecutionPowerHold(AutoExecutionPowerHold *this)
{
  HANDLE v2; // rdi
  _REASON_CONTEXT Context; // [rsp+20h] [rbp-28h] BYREF

  *((_QWORD *)this + 1) = -1;
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Context.Version = 0;
  Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)L"OOBE scanning updates";
  Context.Flags = 1;
  *(_OWORD *)(&Context.Reason.SimpleReasonString + 1) = 0;
  v2 = PowerCreateRequest(&Context);
  if ( v2 == *((HANDLE *)this + 1) )
  {
    v2 = (HANDLE)*((_QWORD *)this + 1);
  }
  else
  {
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::Close(this);
    *((_QWORD *)this + 1) = v2;
  }
  if ( v2 != (HANDLE)-1LL )
  {
    PowerSetRequest(v2, PowerRequestDisplayRequired);
    PowerSetRequest(*((HANDLE *)this + 1), PowerRequestExecutionRequired);
  }
  return this;
}

```

## disassembly

```asm
0x18000d1a4  mov     [rsp+arg_0], rbx
0x18000d1a9  push    rdi
0x18000d1aa  sub     rsp, 40h
0x18000d1ae  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x18000d1b5  mov     qword ptr [rcx+8], 0FFFFFFFFFFFFFFFFh
0x18000d1bd  mov     [rcx], rax
0x18000d1c0  mov     rbx, rcx
0x18000d1c3  lea     rax, aOobeScanningUp; "OOBE scanning updates"
0x18000d1ca  mov     [rsp+48h+Context.Version], 0
0x18000d1d2  xorps   xmm0, xmm0
0x18000d1d5  mov     qword ptr [rsp+48h+Context.Reason], rax
0x18000d1da  lea     rcx, [rsp+48h+Context]; Context
0x18000d1df  mov     [rsp+48h+Context.Flags], 1
0x18000d1e7  movdqu  xmmword ptr [rsp+48h+Context.Reason+8], xmm0
0x18000d1ed  call    cs:__imp_PowerCreateRequest
0x18000d1f3  mov     rdi, rax
0x18000d1f6  cmp     rax, [rbx+8]
0x18000d1fa  jz      short loc_18000D20A
0x18000d1fc  mov     rcx, rbx
0x18000d1ff  call    ?Close@?$HandleT@UHANDLETraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits>::Close(void)
0x18000d204  mov     [rbx+8], rdi
0x18000d208  jmp     short loc_18000D20E
0x18000d20a  mov     rdi, [rbx+8]
0x18000d20e  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000d212  jz      short loc_18000D22E
0x18000d214  xor     edx, edx; RequestType
0x18000d216  mov     rcx, rdi; PowerRequest
0x18000d219  call    cs:__imp_PowerSetRequest
0x18000d21f  mov     rcx, [rbx+8]; PowerRequest
0x18000d223  mov     edx, 3; RequestType
0x18000d228  call    cs:__imp_PowerSetRequest
0x18000d22e  mov     rax, rbx
0x18000d231  mov     rbx, [rsp+48h+arg_0]
0x18000d236  add     rsp, 40h
0x18000d23a  pop     rdi
0x18000d23b  retn
```
