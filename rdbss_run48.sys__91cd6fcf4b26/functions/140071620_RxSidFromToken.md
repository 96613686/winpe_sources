# RxSidFromToken

- ea: `0x140071620`
- end: `0x1400716ed`
- name: `RxSidFromToken`
- size: `205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x140016e20`
- `0x140071620`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140071681`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400716a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140071681`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400716a5`
- `ntoskrnl!SeQueryInformationToken` at `0x140071640`
- `ntoskrnl!SeQueryInformationToken` at `0x140071640`
- `ntoskrnl!RtlCopySid` at `0x14007166e`
- `ntoskrnl!RtlCopySid` at `0x14007166e`

## pseudocode

```c
__int64 __fastcall RxSidFromToken(void *a1, void *a2)
{
  unsigned int v3; // ebx
  ULONG v4; // ecx
  PVOID TokenInformation; // [rsp+40h] [rbp+18h] BYREF

  TokenInformation = 0;
  v3 = SeQueryInformationToken(a1, TokenUser, &TokenInformation);
  if ( (v3 & 0x80000000) == 0 )
  {
    v4 = 4 * *(unsigned __int8 *)(*(_QWORD *)TokenInformation + 1LL) + 8;
    if ( v4 <= 0x44 )
    {
      RtlCopySid(v4, a2, *(PSID *)TokenInformation);
      ExFreePoolWithTag(TokenInformation, 0);
      return v3;
    }
    v3 = -2147483643;
    ExFreePoolWithTag(TokenInformation, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140071620  mov     [rsp+arg_0], rbx
0x140071625  push    rdi
0x140071626  sub     rsp, 20h
0x14007162a  mov     rdi, rdx
0x14007162d  mov     [rsp+28h+TokenInformation], 0
0x140071636  mov     edx, 1; TokenInformationClass
0x14007163b  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x140071640  call    cs:__imp_SeQueryInformationToken
0x140071647  nop     dword ptr [rax+rax+00h]
0x14007164c  mov     ebx, eax
0x14007164e  test    eax, eax
0x140071650  js      short loc_1400716B1
0x140071652  mov     r9, [rsp+28h+TokenInformation]
0x140071657  mov     r8, [r9]; SourceSid
0x14007165a  movzx   ecx, byte ptr [r8+1]
0x14007165f  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x140071666  cmp     ecx, 44h ; 'D'
0x140071669  ja      short loc_14007169B
0x14007166b  mov     rdx, rdi; DestinationSid
0x14007166e  call    cs:__imp_RtlCopySid
0x140071675  nop     dword ptr [rax+rax+00h]
0x14007167a  mov     rcx, [rsp+28h+TokenInformation]; P
0x14007167f  xor     edx, edx; Tag
0x140071681  call    cs:__imp_ExFreePoolWithTag
0x140071688  nop     dword ptr [rax+rax+00h]
0x14007168d  mov     eax, ebx
0x14007168f  mov     rbx, [rsp+28h+arg_0]
0x140071694  add     rsp, 20h
0x140071698  pop     rdi
0x140071699  retn
0x14007169b  xor     edx, edx; Tag
0x14007169d  mov     rcx, r9; P
0x1400716a0  mov     ebx, 80000005h
0x1400716a5  call    cs:__imp_ExFreePoolWithTag
0x1400716ac  nop     dword ptr [rax+rax+00h]
0x1400716b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400716b8  lea     rax, WPP_GLOBAL_Control
0x1400716bf  cmp     rcx, rax
0x1400716c2  jz      short loc_14007168D
0x1400716c4  test    dword ptr [rcx+2Ch], 1000h
0x1400716cb  jz      short loc_14007168D
0x1400716cd  cmp     byte ptr [rcx+29h], 2
0x1400716d1  jb      short loc_14007168D
0x1400716d3  mov     rcx, [rcx+18h]
0x1400716d7  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x1400716de  mov     edx, 10h
0x1400716e3  mov     r9d, ebx
0x1400716e6  call    WPP_SF_d
0x1400716eb  jmp     short loc_14007168D
```
