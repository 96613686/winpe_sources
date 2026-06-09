# MupAttempttoLoadRegistryPoliciesKeyRunOnce

- ea: `0x140004b40`
- end: `0x140004c1c`
- name: `MupAttempttoLoadRegistryPoliciesKeyRunOnce`
- size: `220`
- prototype: `RTL_RUN_ONCE_INIT_FN`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002a14`
- `0x140002e74`
- `0x140004b40`
- `0x140016bf0`
- `0x140016d74`
- `0x140016edc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140004bc2`
- `ntoskrnl!ZwClose` at `0x140004bc2`

## pseudocode

```c
__int64 __fastcall MupAttempttoLoadRegistryPoliciesKeyRunOnce(PRTL_RUN_ONCE a1, void **a2, PVOID *a3)
{
  HANDLE *v3; // rbx
  int v5; // edi

  v3 = a2 + 3;
  v5 = MupiOpenPoliciesKeyFromRegistry(a2 + 3);
  if ( v5 < 0
    || (LOBYTE(MupEnableMailslotsByPolicy) = MupiReadEnableMailslotsFromPoliciesRegistry(*v3, 0),
        v5 = MupiRegisterPoliciesKeyRegistryChangeNotification(a2),
        v5 < 0) )
  {
    if ( *v3 )
    {
      ZwClose(*v3);
      *v3 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_4108bb1397623747c94676978a28aeb5_Traceguids,
        (unsigned int)v5);
    }
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_4108bb1397623747c94676978a28aeb5_Traceguids);
    }
    return 1;
  }
}

```

## disassembly

```asm
0x140004b40  mov     [rsp+arg_0], rbx
0x140004b45  mov     [rsp+arg_8], rsi
0x140004b4a  push    rdi
0x140004b4b  sub     rsp, 20h
0x140004b4f  lea     rbx, [rdx+18h]
0x140004b53  mov     rsi, rdx
0x140004b56  mov     rcx, rbx
0x140004b59  call    MupiOpenPoliciesKeyFromRegistry
0x140004b5e  mov     edi, eax
0x140004b60  test    eax, eax
0x140004b62  js      short loc_140004BBA
0x140004b64  mov     rcx, [rbx]; KeyHandle
0x140004b67  xor     edx, edx
0x140004b69  call    MupiReadEnableMailslotsFromPoliciesRegistry
0x140004b6e  mov     rcx, rsi
0x140004b71  mov     byte ptr cs:MupEnableMailslotsByPolicy, al
0x140004b77  call    MupiRegisterPoliciesKeyRegistryChangeNotification
0x140004b7c  mov     edi, eax
0x140004b7e  test    eax, eax
0x140004b80  js      short loc_140004BBA
0x140004b82  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b89  lea     rax, WPP_GLOBAL_Control
0x140004b90  cmp     rcx, rax
0x140004b93  jz      short loc_140004BB3
0x140004b95  test    dword ptr [rcx+2Ch], 2000000h
0x140004b9c  jz      short loc_140004BB3
0x140004b9e  mov     rcx, [rcx+18h]
0x140004ba2  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004ba9  mov     edx, 0Ah
0x140004bae  call    WPP_SF_
0x140004bb3  mov     eax, 1
0x140004bb8  jmp     short loc_140004C0B
0x140004bba  mov     rcx, [rbx]; Handle
0x140004bbd  test    rcx, rcx
0x140004bc0  jz      short loc_140004BD5
0x140004bc2  call    cs:__imp_ZwClose
0x140004bc9  nop     dword ptr [rax+rax+00h]
0x140004bce  mov     qword ptr [rbx], 0
0x140004bd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bdc  lea     rax, WPP_GLOBAL_Control
0x140004be3  cmp     rcx, rax
0x140004be6  jz      short loc_140004C09
0x140004be8  test    dword ptr [rcx+2Ch], 1000000h
0x140004bef  jz      short loc_140004C09
0x140004bf1  mov     rcx, [rcx+18h]
0x140004bf5  lea     r8, WPP_4108bb1397623747c94676978a28aeb5_Traceguids
0x140004bfc  mov     edx, 0Bh
0x140004c01  mov     r9d, edi
0x140004c04  call    WPP_SF_d
0x140004c09  xor     eax, eax
0x140004c0b  mov     rbx, [rsp+28h+arg_0]
0x140004c10  mov     rsi, [rsp+28h+arg_8]
0x140004c15  add     rsp, 20h
0x140004c19  pop     rdi
0x140004c1a  retn
```
