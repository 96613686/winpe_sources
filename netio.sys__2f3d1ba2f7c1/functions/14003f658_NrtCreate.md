# NrtCreate

- ea: `0x14003f658`
- end: `0x14003f77a`
- name: `NrtCreate`
- size: `290`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14003fb60`

## callees

- `0x14003f658`
- `0x14003f780`
- `0x140050ea4`
- `0x1400769f0`

## import_xrefs

- `ntoskrnl!RtlEqualString` at `0x14003f6c8`
- `ntoskrnl!RtlEqualString` at `0x14003f70a`
- `ntoskrnl!RtlEqualString` at `0x14003f6c8`
- `ntoskrnl!RtlEqualString` at `0x14003f70a`
- `ntoskrnl!RtlInitString` at `0x14003f6af`
- `ntoskrnl!RtlInitString` at `0x14003f6f1`
- `ntoskrnl!RtlInitString` at `0x14003f6af`
- `ntoskrnl!RtlInitString` at `0x14003f6f1`

## string_xrefs

- `0x14003f689`: `NrtOpenPacket`
- `0x14003f6e5`: `NrtCloneOpenPacket`

## pseudocode

```c
__int64 __fastcall NrtCreate(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  int Handler; // eax
  unsigned int v6; // ebx
  STRING String2; // [rsp+20h] [rbp-28h] BYREF
  _STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  v3 = *(_QWORD *)(a1 + 24);
  String2 = 0;
  DestinationString = 0;
  if ( v3 )
  {
    String2.MaximumLength = *(unsigned __int8 *)(v3 + 5) + 1;
    String2.Length = *(unsigned __int8 *)(v3 + 5);
    String2.Buffer = (PCHAR)(v3 + 8);
    RtlInitString(&DestinationString, "NrtOpenPacket");
    if ( RtlEqualString(&DestinationString, &String2, 0) )
    {
      Handler = NrtCreateHandler(a1, a2);
      goto LABEL_6;
    }
    RtlInitString(&DestinationString, "NrtCloneOpenPacket");
    if ( RtlEqualString(&DestinationString, &String2, 0) )
    {
      Handler = NrtCloneHandler(a1, a2);
LABEL_6:
      v6 = Handler;
      if ( Handler >= 0 )
        return v6;
      goto LABEL_9;
    }
  }
  v6 = -1073741811;
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_2117715bc64139be8f5a086042a30ce6_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x14003f658  mov     [rsp+arg_0], rbx
0x14003f65d  push    rdi
0x14003f65e  sub     rsp, 40h
0x14003f662  mov     rbx, rcx
0x14003f665  xorps   xmm0, xmm0
0x14003f668  mov     rcx, [rcx+18h]
0x14003f66c  xorps   xmm1, xmm1
0x14003f66f  mov     rdi, rdx
0x14003f672  movups  xmmword ptr [rsp+48h+String2.Length], xmm0
0x14003f677  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm1
0x14003f67c  test    rcx, rcx
0x14003f67f  jz      loc_14003F72D
0x14003f685  movzx   eax, byte ptr [rcx+5]
0x14003f689  lea     rdx, aNrtopenpacket; "NrtOpenPacket"
0x14003f690  inc     ax
0x14003f693  mov     [rsp+48h+String2.MaximumLength], ax
0x14003f698  movzx   eax, byte ptr [rcx+5]
0x14003f69c  mov     [rsp+48h+String2.Length], ax
0x14003f6a1  lea     rax, [rcx+8]
0x14003f6a5  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14003f6aa  mov     [rsp+48h+String2.Buffer], rax
0x14003f6af  call    cs:__imp_RtlInitString
0x14003f6b6  nop     dword ptr [rax+rax+00h]
0x14003f6bb  xor     r8d, r8d; CaseInSensitive
0x14003f6be  lea     rdx, [rsp+48h+String2]; String2
0x14003f6c3  lea     rcx, [rsp+48h+DestinationString]; String1
0x14003f6c8  call    cs:__imp_RtlEqualString
0x14003f6cf  nop     dword ptr [rax+rax+00h]
0x14003f6d4  test    al, al
0x14003f6d6  jz      short loc_14003F6E5
0x14003f6d8  mov     rdx, rdi
0x14003f6db  mov     rcx, rbx
0x14003f6de  call    NrtCreateHandler
0x14003f6e3  jmp     short loc_14003F725
0x14003f6e5  lea     rdx, aNrtcloneopenpa; "NrtCloneOpenPacket"
0x14003f6ec  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14003f6f1  call    cs:__imp_RtlInitString
0x14003f6f8  nop     dword ptr [rax+rax+00h]
0x14003f6fd  xor     r8d, r8d; CaseInSensitive
0x14003f700  lea     rdx, [rsp+48h+String2]; String2
0x14003f705  lea     rcx, [rsp+48h+DestinationString]; String1
0x14003f70a  call    cs:__imp_RtlEqualString
0x14003f711  nop     dword ptr [rax+rax+00h]
0x14003f716  test    al, al
0x14003f718  jz      short loc_14003F72D
0x14003f71a  mov     rdx, rdi
0x14003f71d  mov     rcx, rbx
0x14003f720  call    NrtCloneHandler
0x14003f725  mov     ebx, eax
0x14003f727  test    eax, eax
0x14003f729  js      short loc_14003F732
0x14003f72b  jmp     short loc_14003F76C
0x14003f72d  mov     ebx, 0C000000Dh
0x14003f732  mov     rcx, cs:WPP_GLOBAL_Control
0x14003f739  lea     rax, WPP_GLOBAL_Control
0x14003f740  cmp     rcx, rax
0x14003f743  jz      short loc_14003F76C
0x14003f745  cmp     byte ptr [rcx+29h], 2
0x14003f749  jb      short loc_14003F76C
0x14003f74b  test    dword ptr [rcx+2Ch], 100000h
0x14003f752  jz      short loc_14003F76C
0x14003f754  mov     rcx, [rcx+18h]
0x14003f758  lea     r8, WPP_2117715bc64139be8f5a086042a30ce6_Traceguids
0x14003f75f  mov     edx, 0Eh
0x14003f764  mov     r9d, ebx
0x14003f767  call    WPP_SF_d
0x14003f76c  mov     eax, ebx
0x14003f76e  mov     rbx, [rsp+48h+arg_0]
0x14003f773  add     rsp, 40h
0x14003f777  pop     rdi
0x14003f778  retn
```
