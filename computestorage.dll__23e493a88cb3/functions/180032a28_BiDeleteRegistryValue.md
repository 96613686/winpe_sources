# BiDeleteRegistryValue

- ea: `0x180032a28`
- end: `0x180032af9`
- name: `BiDeleteRegistryValue`
- size: `209`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18002dcec`
- `0x18002dfa8`
- `0x18002e188`
- `0x18002e390`

## callees

- `0x180032a28`
- `0x180032bc4`
- `0x180033914`
- `0x180039298`
- `0x18003a500`

## import_xrefs

- `ntdll!ZwDeleteValueKey` at `0x180032aac`
- `ntdll!ZwDeleteValueKey` at `0x180032aac`
- `ntdll!ZwClose` at `0x180032ada`
- `ntdll!ZwClose` at `0x180032ada`
- `ntdll!RtlInitUnicodeString` at `0x180032a4a`
- `ntdll!RtlInitUnicodeString` at `0x180032a4a`

## pseudocode

```c
__int64 __fastcall BiDeleteRegistryValue(__int64 a1, const WCHAR *a2, void *a3)
{
  unsigned __int64 v4; // rsi
  int v5; // eax
  unsigned __int64 v6; // rbx
  unsigned int v7; // edi
  unsigned int v8; // eax
  NTSTATUS v9; // eax
  struct _UNICODE_STRING ValueName; // [rsp+20h] [rbp-18h] BYREF
  HANDLE KeyHandle; // [rsp+50h] [rbp+18h] BYREF

  KeyHandle = a3;
  ValueName = 0;
  RtlInitUnicodeString(&ValueName, a2);
  v4 = a1 & 0xFFFFFFFFFFFFFFFDuLL;
  KeyHandle = 0;
  v5 = BiOpenKey(v4, L"Description", 131103, &KeyHandle);
  v6 = (unsigned __int64)KeyHandle;
  v7 = v5;
  if ( v5 >= 0 )
  {
    if ( ((unsigned __int8)KeyHandle & 1) != 0 )
    {
      v8 = ORDeleteValue((unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL, ValueName.Buffer);
      v9 = BiDosErrorToNtStatus(v8);
    }
    else
    {
      v9 = ZwDeleteValueKey(KeyHandle, &ValueName);
    }
    v7 = v9;
  }
  if ( v6 != v4 && v6 )
  {
    if ( (v6 & 1) != 0 )
      ORCloseKey(v6 & 0xFFFFFFFFFFFFFFFEuLL);
    else
      ZwClose((HANDLE)v6);
  }
  return v7;
}

```

## disassembly

```asm
0x180032a28  mov     rax, rsp
0x180032a2b  mov     [rax+8], rbx
0x180032a2f  mov     [rax+10h], rsi
0x180032a33  mov     [rax+18h], r8
0x180032a37  push    rdi
0x180032a38  sub     rsp, 30h
0x180032a3c  mov     rsi, rcx
0x180032a3f  xorps   xmm0, xmm0
0x180032a42  lea     rcx, [rax-18h]; DestinationString
0x180032a46  movups  xmmword ptr [rax-18h], xmm0
0x180032a4a  call    cs:__imp_RtlInitUnicodeString
0x180032a51  nop     dword ptr [rax+rax+00h]
0x180032a56  and     rsi, 0FFFFFFFFFFFFFFFDh
0x180032a5a  mov     [rsp+38h+KeyHandle], 0
0x180032a63  mov     rcx, rsi
0x180032a66  lea     r9, [rsp+38h+KeyHandle]
0x180032a6b  mov     r8d, 2001Fh
0x180032a71  lea     rdx, aDescription; "Description"
0x180032a78  call    BiOpenKey
0x180032a7d  mov     rbx, [rsp+38h+KeyHandle]
0x180032a82  mov     edi, eax
0x180032a84  test    eax, eax
0x180032a86  js      short loc_180032ABA
0x180032a88  mov     rcx, rbx; KeyHandle
0x180032a8b  test    bl, 1
0x180032a8e  jz      short loc_180032AA7
0x180032a90  mov     rdx, [rsp+38h+ValueName.Buffer]
0x180032a95  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180032a99  call    ORDeleteValue
0x180032a9e  mov     ecx, eax
0x180032aa0  call    BiDosErrorToNtStatus
0x180032aa5  jmp     short loc_180032AB8
0x180032aa7  lea     rdx, [rsp+38h+ValueName]; ValueName
0x180032aac  call    cs:__imp_ZwDeleteValueKey
0x180032ab3  nop     dword ptr [rax+rax+00h]
0x180032ab8  mov     edi, eax
0x180032aba  cmp     rbx, rsi
0x180032abd  jz      short loc_180032AE6
0x180032abf  test    rbx, rbx
0x180032ac2  jz      short loc_180032AE6
0x180032ac4  test    bl, 1
0x180032ac7  jz      short loc_180032AD7
0x180032ac9  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180032acd  mov     rcx, rbx
0x180032ad0  call    ORCloseKey
0x180032ad5  jmp     short loc_180032AE6
0x180032ad7  mov     rcx, rbx; Handle
0x180032ada  call    cs:__imp_ZwClose
0x180032ae1  nop     dword ptr [rax+rax+00h]
0x180032ae6  mov     rbx, [rsp+38h+arg_0]
0x180032aeb  mov     eax, edi
0x180032aed  mov     rsi, [rsp+38h+arg_8]
0x180032af2  add     rsp, 30h
0x180032af6  pop     rdi
0x180032af7  retn
```
