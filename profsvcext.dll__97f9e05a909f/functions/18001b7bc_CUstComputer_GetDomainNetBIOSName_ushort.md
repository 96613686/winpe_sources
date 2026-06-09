# CUstComputer::GetDomainNetBIOSName(ushort * *)

- ea: `0x18001b7bc`
- end: `0x18001b89a`
- name: `?GetDomainNetBIOSName@CUstComputer@@SAJPEAPEAG@Z`
- size: `222`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b214`

## callees

- `0x18001afc8`
- `0x18001b008`
- `0x18001b7bc`
- `0x18001d264`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18001b882`
- `netutils!NetApiBufferFree` at `0x18001b882`
- `wkscli!NetGetJoinInformation` at `0x18001b7e8`
- `wkscli!NetGetJoinInformation` at `0x18001b7e8`

## pseudocode

```c
__int64 __fastcall CUstComputer::GetDomainNetBIOSName(unsigned __int16 **a1)
{
  signed int JoinInformation; // eax
  unsigned int StringCopy; // ebx
  UstCommon::CImpersonator *v4; // rcx
  int v6; // [rsp+38h] [rbp+10h] BYREF
  LPVOID Buffer; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  Buffer = 0;
  JoinInformation = NetGetJoinInformation(0, (LPWSTR *)&Buffer, (PNETSETUP_JOIN_STATUS)&v6);
  StringCopy = JoinInformation;
  if ( !JoinInformation )
  {
    v4 = WPP_GLOBAL_Control;
LABEL_10:
    if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)v4 + 2), 44, WPP_ab0185983553356c12180ac14bccd298_Traceguids, Buffer);
    StringCopy = CUstUtil::CreateStringCopy((unsigned __int16 *)Buffer, a1);
    goto LABEL_14;
  }
  if ( JoinInformation > 0 )
    StringCopy = (unsigned __int16)JoinInformation | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_ab0185983553356c12180ac14bccd298_Traceguids, StringCopy);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (StringCopy & 0x80000000) == 0 )
    goto LABEL_10;
LABEL_14:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  return StringCopy;
}

```

## disassembly

```asm
0x18001b7bc  mov     rax, rsp
0x18001b7bf  mov     [rax+8], rbx
0x18001b7c3  mov     [rax+20h], rsi
0x18001b7c7  push    rdi
0x18001b7c8  sub     rsp, 20h
0x18001b7cc  mov     rdi, rcx
0x18001b7cf  mov     dword ptr [rax+10h], 0
0x18001b7d6  xor     ecx, ecx; lpServer
0x18001b7d8  mov     qword ptr [rax+18h], 0
0x18001b7e0  lea     r8, [rax+10h]; BufferType
0x18001b7e4  lea     rdx, [rax+18h]; lpNameBuffer
0x18001b7e8  call    cs:__imp_NetGetJoinInformation
0x18001b7ee  lea     rsi, WPP_GLOBAL_Control
0x18001b7f5  mov     ebx, eax
0x18001b7f7  test    eax, eax
0x18001b7f9  jz      short loc_18001B83D
0x18001b7fb  jle     short loc_18001B806
0x18001b7fd  movzx   ebx, ax
0x18001b800  or      ebx, 80070000h
0x18001b806  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b80d  cmp     rcx, rsi
0x18001b810  jz      short loc_18001B837
0x18001b812  test    byte ptr [rcx+1Ch], 1
0x18001b816  jz      short loc_18001B837
0x18001b818  mov     rcx, [rcx+10h]
0x18001b81c  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b823  mov     edx, 2Bh ; '+'
0x18001b828  mov     r9d, ebx
0x18001b82b  call    WPP_SF_d
0x18001b830  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b837  test    ebx, ebx
0x18001b839  js      short loc_18001B878
0x18001b83b  jmp     short loc_18001B844
0x18001b83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b844  cmp     rcx, rsi
0x18001b847  jz      short loc_18001B869
0x18001b849  test    byte ptr [rcx+1Ch], 2
0x18001b84d  jz      short loc_18001B869
0x18001b84f  mov     r9, [rsp+28h+Buffer]
0x18001b854  lea     r8, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b85b  mov     rcx, [rcx+10h]
0x18001b85f  mov     edx, 2Ch ; ','
0x18001b864  call    WPP_SF_S
0x18001b869  mov     rcx, [rsp+28h+Buffer]; unsigned __int16 *
0x18001b86e  mov     rdx, rdi; unsigned __int16 **
0x18001b871  call    ?CreateStringCopy@CUstUtil@@SAJPEAGPEAPEAG@Z; CUstUtil::CreateStringCopy(ushort *,ushort * *)
0x18001b876  mov     ebx, eax
0x18001b878  mov     rcx, [rsp+28h+Buffer]; Buffer
0x18001b87d  test    rcx, rcx
0x18001b880  jz      short loc_18001B888
0x18001b882  call    cs:__imp_NetApiBufferFree
0x18001b888  mov     rsi, [rsp+28h+arg_18]
0x18001b88d  mov     eax, ebx
0x18001b88f  mov     rbx, [rsp+28h+arg_0]
0x18001b894  add     rsp, 20h
0x18001b898  pop     rdi
0x18001b899  retn
```
