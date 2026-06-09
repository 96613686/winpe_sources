# HsmOsGetProcessCommandLineByAttributionInfo

- ea: `0x140008d4c`
- end: `0x140008e87`
- name: `HsmOsGetProcessCommandLineByAttributionInfo`
- size: `315`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140008d1c`
- `0x140076810`

## callees

- `0x140008d4c`
- `0x140008e90`
- `0x14001e280`

## import_xrefs

- `ntoskrnl!ZwOpenProcess` at `0x140008dd5`
- `ntoskrnl!ZwOpenProcess` at `0x140008dd5`
- `ntoskrnl!ZwClose` at `0x140008e12`
- `ntoskrnl!ZwClose` at `0x140008e12`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140008dfb`
- `ntoskrnl!ZwQueryInformationProcess` at `0x140008dfb`

## pseudocode

```c
__int64 __fastcall HsmOsGetProcessCommandLineByAttributionInfo(__int64 a1, _QWORD *a2, ULONG a3, ULONG *a4)
{
  __int64 v4; // r10
  NTSTATUS InformationProcess; // ebx
  __int64 v10; // rdx
  __int64 v11; // rbx
  _CLIENT_ID ClientId; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *ProcessHandle; // [rsp+90h] [rbp+20h] BYREF

  v4 = *(_QWORD *)(a1 + 8);
  ProcessHandle = 0;
  ClientId = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( v4 )
  {
    v10 = *(unsigned __int16 *)(v4 + 58);
    v11 = 2 * (unsigned int)*(unsigned __int16 *)(v4 + 60);
    if ( a4 )
      *a4 = v11 + 16;
    if ( a3 < (unsigned __int64)(v11 + 16) )
      return (unsigned int)-1073741820;
    a2[1] = a2 + 2;
    memmove(a2 + 2, (const void *)(v4 + 74 + 2 * v10), (unsigned int)v11);
    *(_WORD *)a2 = v11;
    *((_WORD *)a2 + 1) = a3 - 16;
    InformationProcess = 0;
  }
  else
  {
    ClientId.UniqueProcess = HsmOsGetProcessId(a1);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    InformationProcess = ZwOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
    if ( InformationProcess >= 0 )
      InformationProcess = ZwQueryInformationProcess(
                             ProcessHandle,
                             ProcessImageFileMapping|ProcessUserModeIOPL,
                             a2,
                             a3,
                             a4);
  }
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x140008d4c  mov     [rsp-18h+arg_8], rbx
0x140008d51  mov     [rsp-18h+arg_10], rsi
0x140008d56  push    rbp
0x140008d57  push    rdi
0x140008d58  push    r14
0x140008d5a  mov     rbp, rsp
0x140008d5d  sub     rsp, 70h
0x140008d61  mov     r10, [rcx+8]
0x140008d65  xorps   xmm1, xmm1
0x140008d68  mov     esi, r8d
0x140008d6b  xorps   xmm0, xmm0
0x140008d6e  mov     [rbp+ProcessHandle], 0
0x140008d76  mov     rdi, r9
0x140008d79  mov     r14, rdx
0x140008d7c  movups  xmmword ptr [rbp+ClientId.UniqueProcess], xmm0
0x140008d80  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x140008d84  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x140008d88  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x140008d8c  test    r10, r10
0x140008d8f  jnz     loc_140008E36
0x140008d95  call    HsmOsGetProcessId
0x140008d9a  xorps   xmm0, xmm0
0x140008d9d  mov     [rbp+ClientId.UniqueProcess], rax
0x140008da1  lea     r9, [rbp+ClientId]; ClientId
0x140008da5  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140008dac  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140008db0  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140008db8  mov     edx, 400h; DesiredAccess
0x140008dbd  mov     [rbp+ObjectAttributes.Attributes], 200h
0x140008dc4  lea     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140008dc8  mov     [rbp+ObjectAttributes.ObjectName], 0
0x140008dd0  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140008dd5  call    cs:__imp_ZwOpenProcess
0x140008ddc  nop     dword ptr [rax+rax+00h]
0x140008de1  mov     ebx, eax
0x140008de3  test    eax, eax
0x140008de5  js      short loc_140008E09
0x140008de7  mov     rcx, [rbp+ProcessHandle]; ProcessHandle
0x140008deb  mov     r9d, esi; ProcessInformationLength
0x140008dee  mov     r8, r14; ProcessInformation
0x140008df1  mov     [rsp+70h+ReturnLength], rdi; ReturnLength
0x140008df6  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x140008dfb  call    cs:__imp_ZwQueryInformationProcess
0x140008e02  nop     dword ptr [rax+rax+00h]
0x140008e07  mov     ebx, eax
0x140008e09  mov     rcx, [rbp+ProcessHandle]; Handle
0x140008e0d  test    rcx, rcx
0x140008e10  jz      short loc_140008E1E
0x140008e12  call    cs:__imp_ZwClose
0x140008e19  nop     dword ptr [rax+rax+00h]
0x140008e1e  lea     r11, [rsp+70h+var_s0]
0x140008e23  mov     eax, ebx
0x140008e25  mov     rbx, [r11+28h]
0x140008e29  mov     rsi, [r11+30h]
0x140008e2d  mov     rsp, r11
0x140008e30  pop     r14
0x140008e32  pop     rdi
0x140008e33  pop     rbp
0x140008e34  retn
0x140008e36  movzx   eax, word ptr [r10+3Ch]
0x140008e3b  movzx   edx, word ptr [r10+3Ah]
0x140008e40  lea     ebx, [rax+rax]
0x140008e43  test    rdi, rdi
0x140008e46  jz      short loc_140008E4E
0x140008e48  lea     eax, [rbx+10h]
0x140008e4b  mov     [r9], eax
0x140008e4e  lea     rcx, [rbx+10h]
0x140008e52  mov     r8d, ebx; Size
0x140008e55  cmp     rsi, rcx
0x140008e58  jnb     short loc_140008E61
0x140008e5a  mov     ebx, 0C0000004h
0x140008e5f  jmp     short loc_140008E1E
0x140008e61  add     r10, 4Ah ; 'J'
0x140008e65  lea     rcx, [r14+10h]; void *
0x140008e69  mov     [r14+8], rcx
0x140008e6d  lea     rdx, [r10+rdx*2]; Src
0x140008e71  call    memmove
0x140008e76  sub     si, 10h
0x140008e7a  mov     [r14], bx
0x140008e7e  mov     [r14+2], si
0x140008e83  xor     ebx, ebx
0x140008e85  jmp     short loc_140008E09
```
