# Microsoft::HostGuardian::Client::VsmCaAgent::VsmCaAgent(void)

- ea: `0x1800125f4`
- end: `0x1800126d4`
- name: `??0VsmCaAgent@Client@HostGuardian@Microsoft@@AEAA@XZ`
- size: `224`
- prototype: `void *__fastcall(Microsoft::HostGuardian::Client::VsmCaAgent *this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800136a4`

## callees

- `0x180001770`
- `0x1800077a0`
- `0x1800125f4`
- `0x180013220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012674`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180012674`

## string_xrefs

- `0x18001268a`: `Instantiated CAAgent.`

## pseudocode

```c
void *__fastcall Microsoft::HostGuardian::Client::VsmCaAgent::VsmCaAgent(
        Microsoft::HostGuardian::Client::VsmCaAgent *this)
{
  __int64 v1; // r8
  _BYTE v3[16]; // [rsp+40h] [rbp-38h] BYREF
  const wchar_t *v4; // [rsp+50h] [rbp-28h]
  __int64 v5; // [rsp+58h] [rbp-20h]

  qword_180020620 = 0;
  qword_180020628 = 0;
  qword_180020630 = 0;
  qword_180020638 = 0;
  qword_180020640 = -1;
  qword_180020648 = 0;
  byte_180020650 = 0;
  InitializeCriticalSectionEx(&stru_180020658, 0, 0);
  if ( (Microsoft_Windows_HostGuardianClient_ServiceEnableBits & 2) != 0 )
  {
    v4 = L"Instantiated CAAgent.";
    v5 = 44;
    McGenEventWrite_EventWriteTransfer(v3, ServiceDebugInformational, v1, 2, v3);
  }
  Microsoft::HostGuardian::Client::VsmCaAgent::Initialize((Microsoft::HostGuardian::Client::VsmCaAgent *)&qword_180020620);
  return &qword_180020620;
}

```

## disassembly

```asm
0x1800125f4  push    rdi
0x1800125f6  sub     rsp, 70h
0x1800125fa  mov     rax, cs:__security_cookie
0x180012601  xor     rax, rsp
0x180012604  mov     [rsp+78h+var_18], rax
0x180012609  mov     rax, [rsp+78h+var_48]
0x18001260e  mov     [rsp+78h+var_48], rax
0x180012613  lea     rdi, qword_180020620
0x18001261a  mov     [rsp+78h+var_48], rdi
0x18001261f  mov     cs:qword_180020620, 0
0x18001262a  mov     cs:qword_180020628, 0
0x180012635  mov     cs:qword_180020630, 0
0x180012640  mov     cs:qword_180020638, 0
0x18001264b  mov     cs:qword_180020640, 0FFFFFFFFFFFFFFFFh
0x180012656  mov     cs:qword_180020648, 0
0x180012661  mov     cs:byte_180020650, 0
0x180012668  xor     r8d, r8d; Flags
0x18001266b  xor     edx, edx; dwSpinCount
0x18001266d  lea     rcx, stru_180020658; lpCriticalSection
0x180012674  call    cs:__imp_InitializeCriticalSectionEx
0x18001267a  nop
0x18001267b  mov     r9d, 2
0x180012681  test    byte ptr cs:Microsoft_Windows_HostGuardianClient_ServiceEnableBits, r9b
0x180012688  jz      short loc_1800126B5
0x18001268a  lea     rcx, aInstantiatedCa; "Instantiated CAAgent."
0x180012691  mov     [rsp+78h+var_28], rcx
0x180012696  mov     [rsp+78h+var_20], 2Ch ; ','
0x18001269f  lea     rcx, [rsp+78h+var_38]
0x1800126a4  mov     [rsp+78h+var_58], rcx
0x1800126a9  lea     rdx, ServiceDebugInformational
0x1800126b0  call    McGenEventWrite_EventWriteTransfer
0x1800126b5  mov     rcx, rdi; this
0x1800126b8  call    ?Initialize@VsmCaAgent@Client@HostGuardian@Microsoft@@AEAAXXZ; Microsoft::HostGuardian::Client::VsmCaAgent::Initialize(void)
0x1800126bd  nop
0x1800126be  mov     rax, rdi
0x1800126c1  mov     rcx, [rsp+78h+var_18]
0x1800126c6  xor     rcx, rsp; StackCookie
0x1800126c9  call    __security_check_cookie
0x1800126ce  add     rsp, 70h
0x1800126d2  pop     rdi
0x1800126d3  retn
```
