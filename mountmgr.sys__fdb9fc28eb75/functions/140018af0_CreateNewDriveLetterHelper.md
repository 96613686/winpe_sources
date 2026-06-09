# CreateNewDriveLetterHelper

- ea: `0x140018af0`
- end: `0x140018cc3`
- name: `CreateNewDriveLetterHelper`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x14000acd8`

## callees

- `0x140002f80`
- `0x140017540`
- `0x140018af0`
- `0x140018cd0`
- `0x140018da0`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x140018ca7`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140018ca7`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140018b17`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140018c27`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140018b17`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140018c27`
- `ntoskrnl!ExAllocatePool2` at `0x140018b3c`
- `ntoskrnl!ExAllocatePool2` at `0x140018b89`
- `ntoskrnl!ExAllocatePool2` at `0x140018b3c`
- `ntoskrnl!ExAllocatePool2` at `0x140018b89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bd1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bd1`

## string_xrefs

- `0x140018c84`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall CreateNewDriveLetterHelper(__int64 a1, unsigned __int8 a2)
{
  __int16 v2; // bp
  unsigned int v4; // r14d
  _QWORD *Pool2; // rsi
  int SymbolicLink; // ebp
  __int64 v7; // rdx
  void *v8; // rax
  int IsDosDeviceLocallyMapped; // ebp
  _QWORD *v11; // rcx
  char v12; // [rsp+78h] [rbp+10h] BYREF

  v2 = a2;
  v12 = 0;
  v4 = a2 - 64;
  if ( (int)ObIsDosDeviceLocallyMapped(v4, &v12) >= 0 )
  {
    if ( v12 )
      return (unsigned int)-1073741771;
  }
  else
  {
    v12 = 0;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(258, 40, 1098149453);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v7 = (unsigned __int16)word_1400070BA;
  *((_WORD *)Pool2 + 12) = word_1400070B8;
  *((_WORD *)Pool2 + 13) = v7;
  v8 = (void *)ExAllocatePool2(258, v7, 1098149453);
  Pool2[4] = v8;
  if ( !v8 )
  {
    SymbolicLink = -1073741670;
LABEL_9:
    if ( Pool2[4] )
    {
      if ( v12 )
        GlobalDeleteSymbolicLink(Pool2 + 3);
      ExFreePoolWithTag((PVOID)Pool2[4], 0);
    }
    ExFreePoolWithTag(Pool2, 0);
    return (unsigned int)SymbolicLink;
  }
  memmove(v8, off_1400070C0, (unsigned __int16)word_1400070BA);
  *(_WORD *)(Pool2[4] + 24LL) = v2;
  SymbolicLink = GlobalCreateSymbolicLink((const UNICODE_STRING *)(Pool2 + 3), (__int128 *)(a1 + 80));
  if ( SymbolicLink < 0 )
    goto LABEL_9;
  IsDosDeviceLocallyMapped = ObIsDosDeviceLocallyMapped(v4, &v12);
  if ( IsDosDeviceLocallyMapped >= 0 )
  {
    if ( v12 )
    {
      SymbolicLink = -1073741771;
      goto LABEL_9;
    }
  }
  else
  {
    v12 = 0;
    IsDosDeviceLocallyMapped = 0;
  }
  v11 = *(_QWORD **)(a1 + 24);
  if ( *v11 != a1 + 16 )
    __fastfail(3u);
  *Pool2 = a1 + 16;
  Pool2[1] = v11;
  *v11 = Pool2;
  *(_QWORD *)(a1 + 24) = Pool2;
  *((_BYTE *)Pool2 + 16) = 1;
  SendLinkCreated(v11, Pool2 + 3);
  RtlWriteRegistryValue(
    0,
    L"\\Registry\\Machine\\System\\MountedDevices",
    (PCWSTR)Pool2[4],
    3u,
    (PVOID)(*(_QWORD *)(a1 + 96) + 2LL),
    **(unsigned __int16 **)(a1 + 96));
  return (unsigned int)IsDosDeviceLocallyMapped;
}

```

## disassembly

```asm
0x140018af0  push    rbx
0x140018af2  push    rbp
0x140018af3  push    rsi
0x140018af4  push    rdi
0x140018af5  push    r14
0x140018af7  push    r15
0x140018af9  sub     rsp, 38h
0x140018afd  movzx   ebp, dl
0x140018b00  mov     r15, rcx
0x140018b03  mov     r14d, ebp
0x140018b06  mov     [rsp+68h+arg_8], 0
0x140018b0b  add     r14d, 0FFFFFFC0h
0x140018b0f  lea     rdx, [rsp+68h+arg_8]
0x140018b14  mov     ecx, r14d
0x140018b17  call    cs:__imp_ObIsDosDeviceLocallyMapped
0x140018b1e  nop     dword ptr [rax+rax+00h]
0x140018b23  test    eax, eax
0x140018b25  jns     short loc_140018B5A
0x140018b27  mov     [rsp+68h+arg_8], 0
0x140018b2c  mov     edx, 28h ; '('
0x140018b31  mov     ecx, 102h
0x140018b36  mov     r8d, 41746E4Dh
0x140018b3c  call    cs:__imp_ExAllocatePool2
0x140018b43  nop     dword ptr [rax+rax+00h]
0x140018b48  mov     rsi, rax
0x140018b4b  test    rax, rax
0x140018b4e  jnz     short loc_140018B68
0x140018b50  mov     ebp, 0C000009Ah
0x140018b55  jmp     loc_140018BDD
0x140018b5a  cmp     [rsp+68h+arg_8], 0
0x140018b5f  jz      short loc_140018B2C
0x140018b61  mov     ebp, 0C0000035h
0x140018b66  jmp     short loc_140018BDD
0x140018b68  movzx   eax, cs:word_1400070B8
0x140018b6f  mov     ecx, 102h
0x140018b74  movzx   edx, cs:word_1400070BA
0x140018b7b  mov     r8d, 41746E4Dh
0x140018b81  mov     [rsi+18h], ax
0x140018b85  mov     [rsi+1Ah], dx
0x140018b89  call    cs:__imp_ExAllocatePool2
0x140018b90  nop     dword ptr [rax+rax+00h]
0x140018b95  mov     [rsi+20h], rax
0x140018b99  test    rax, rax
0x140018b9c  jnz     short loc_140018BED
0x140018b9e  mov     ebp, 0C000009Ah
0x140018ba3  cmp     qword ptr [rsi+20h], 0
0x140018ba8  jz      short loc_140018BCC
0x140018baa  cmp     [rsp+68h+arg_8], 0
0x140018baf  jz      short loc_140018BBA
0x140018bb1  lea     rcx, [rsi+18h]
0x140018bb5  call    GlobalDeleteSymbolicLink
0x140018bba  mov     rcx, [rsi+20h]; P
0x140018bbe  xor     edx, edx; Tag
0x140018bc0  call    cs:__imp_ExFreePoolWithTag
0x140018bc7  nop     dword ptr [rax+rax+00h]
0x140018bcc  xor     edx, edx; Tag
0x140018bce  mov     rcx, rsi; P
0x140018bd1  call    cs:__imp_ExFreePoolWithTag
0x140018bd8  nop     dword ptr [rax+rax+00h]
0x140018bdd  mov     eax, ebp
0x140018bdf  add     rsp, 38h
0x140018be3  pop     r15
0x140018be5  pop     r14
0x140018be7  pop     rdi
0x140018be8  pop     rsi
0x140018be9  pop     rbp
0x140018bea  pop     rbx
0x140018beb  retn
0x140018bed  movzx   r8d, cs:word_1400070BA; Size
0x140018bf5  mov     rcx, rax; void *
0x140018bf8  mov     rdx, cs:off_1400070C0; Src
0x140018bff  call    memmove
0x140018c04  mov     rax, [rsi+20h]
0x140018c08  lea     rdx, [r15+50h]
0x140018c0c  lea     rcx, [rsi+18h]
0x140018c10  mov     [rax+18h], bp
0x140018c14  call    GlobalCreateSymbolicLink
0x140018c19  mov     ebp, eax
0x140018c1b  test    eax, eax
0x140018c1d  js      short loc_140018BA3
0x140018c1f  lea     rdx, [rsp+68h+arg_8]
0x140018c24  mov     ecx, r14d
0x140018c27  call    cs:__imp_ObIsDosDeviceLocallyMapped
0x140018c2e  nop     dword ptr [rax+rax+00h]
0x140018c33  mov     ebp, eax
0x140018c35  test    eax, eax
0x140018c37  jns     short loc_140018C54
0x140018c39  mov     [rsp+68h+arg_8], 0
0x140018c3e  xor     ebp, ebp
0x140018c40  mov     rcx, [r15+18h]
0x140018c44  lea     rax, [r15+10h]
0x140018c48  cmp     [rcx], rax
0x140018c4b  jz      short loc_140018C65
0x140018c4d  mov     ecx, 3
0x140018c52  int     29h; Win8: RtlFailFast(ecx)
0x140018c54  cmp     [rsp+68h+arg_8], 0
0x140018c59  jz      short loc_140018C40
0x140018c5b  mov     ebp, 0C0000035h
0x140018c60  jmp     loc_140018BA3
0x140018c65  mov     [rsi], rax
0x140018c68  lea     rdx, [rsi+18h]
0x140018c6c  mov     [rsi+8], rcx
0x140018c70  mov     [rcx], rsi
0x140018c73  mov     [rax+8], rsi
0x140018c77  mov     byte ptr [rsi+10h], 1
0x140018c7b  call    SendLinkCreated
0x140018c80  mov     rax, [r15+60h]
0x140018c84  lea     rdx, Path; "\\Registry\\Machine\\System\\MountedDev"...
0x140018c8b  mov     r8, [rsi+20h]; ValueName
0x140018c8f  mov     r9d, 3; ValueType
0x140018c95  movzx   ecx, word ptr [rax]
0x140018c98  add     rax, 2
0x140018c9c  mov     [rsp+68h+ValueLength], ecx; ValueLength
0x140018ca0  xor     ecx, ecx; RelativeTo
0x140018ca2  mov     [rsp+68h+ValueData], rax; ValueData
0x140018ca7  call    cs:__imp_RtlWriteRegistryValue
0x140018cae  nop     dword ptr [rax+rax+00h]
0x140018cb3  mov     eax, ebp
0x140018cb5  add     rsp, 38h
0x140018cb9  pop     r15
0x140018cbb  pop     r14
0x140018cbd  pop     rdi
0x140018cbe  pop     rsi
0x140018cbf  pop     rbp
0x140018cc0  pop     rbx
0x140018cc1  retn
```
