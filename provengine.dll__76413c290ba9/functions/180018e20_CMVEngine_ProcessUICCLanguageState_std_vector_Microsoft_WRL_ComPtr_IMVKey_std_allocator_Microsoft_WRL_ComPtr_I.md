# CMVEngine::ProcessUICCLanguageState(std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>> const &)

- ea: `0x180018e20`
- end: `0x180018f6e`
- name: `?ProcessUICCLanguageState@CMVEngine@@AEAAJAEBV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@Z`
- size: `334`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015740`

## callees

- `0x1800010c8`
- `0x1800098dc`
- `0x1800162f0`
- `0x180018e20`
- `0x180043750`

## import_xrefs

- `DMCmnUtils!DmWnfPublish` at `0x180018ef3`
- `DMCmnUtils!DmWnfPublish` at `0x180018ef3`

## pseudocode

```c
__int64 __fastcall CMVEngine::ProcessUICCLanguageState(__int64 a1, __int64 *a2)
{
  int v4; // ebx
  __int64 result; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-58h]
  int v9; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-44h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11[2]; // [rsp+38h] [rbp-40h] BYREF
  int *v12; // [rsp+58h] [rbp-20h]
  __int64 v13; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)&unk_18004EE98, 0, 0, 2u, v11);
  v4 = CMVEngine::HandleUiccLanguage(a1, a2);
  if ( (unsigned int)dword_18005A000 > 4 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)byte_18004E719, 0, 0, 2u, v11);
  if ( v4 >= 0 )
  {
    v9 = 0;
    v6 = DmWnfPublish((struct _WNF_STATE_NAME)WNF_DEVM_PROVISIONING_COMPLETE, (const unsigned __int8 *)&v9, 4u);
    v7 = v6;
    if ( (unsigned int)dword_18005A000 > 4 )
    {
      v10 = v6;
      v13 = 4;
      v12 = (int *)&v10;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18005A000, (unsigned __int8 *)&unk_18004F248, 0, 0, 3u, v11);
    }
    result = 0;
    if ( v7 != -2147024894 )
      return v7;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)v4,
      v8);
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180018e20  mov     [rsp+arg_10], rbx
0x180018e25  push    rdi
0x180018e26  sub     rsp, 70h
0x180018e2a  mov     rax, cs:__security_cookie
0x180018e31  xor     rax, rsp
0x180018e34  mov     [rsp+78h+var_10], rax
0x180018e39  mov     eax, cs:dword_18005A000
0x180018e3f  mov     rdi, rdx
0x180018e42  mov     rbx, rcx
0x180018e45  cmp     eax, 4
0x180018e48  jbe     short loc_180018E75
0x180018e4a  lea     rax, [rsp+78h+var_40]
0x180018e4f  xor     r9d, r9d
0x180018e52  mov     [rsp+78h+var_50], rax
0x180018e57  lea     rdx, unk_18004EE98
0x180018e5e  xor     r8d, r8d
0x180018e61  mov     [rsp+78h+var_58], 2
0x180018e69  lea     rcx, dword_18005A000
0x180018e70  call    _tlgWriteTransfer_EventWriteTransfer
0x180018e75  mov     rdx, rdi
0x180018e78  mov     rcx, rbx
0x180018e7b  call    ?HandleUiccLanguage@CMVEngine@@AEAAJAEBV?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@Z; CMVEngine::HandleUiccLanguage(std::vector<Microsoft::WRL::ComPtr<IMVKey>> const &)
0x180018e80  mov     ecx, cs:dword_18005A000
0x180018e86  mov     ebx, eax
0x180018e88  cmp     ecx, 4
0x180018e8b  jbe     short loc_180018EB8
0x180018e8d  lea     rax, [rsp+78h+var_40]
0x180018e92  xor     r9d, r9d
0x180018e95  mov     [rsp+78h+var_50], rax
0x180018e9a  lea     rdx, byte_18004E719
0x180018ea1  xor     r8d, r8d
0x180018ea4  mov     [rsp+78h+var_58], 2; int
0x180018eac  lea     rcx, dword_18005A000
0x180018eb3  call    _tlgWriteTransfer_EventWriteTransfer
0x180018eb8  test    ebx, ebx
0x180018eba  jns     short loc_180018ED9
0x180018ebc  mov     rcx, [rsp+78h]; this
0x180018ec1  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180018ec8  mov     r9d, ebx; char *
0x180018ecb  mov     edx, 9F4h; void *
0x180018ed0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018ed5  mov     eax, ebx
0x180018ed7  jmp     short loc_180018F53
0x180018ed9  mov     rcx, cs:WNF_DEVM_PROVISIONING_COMPLETE
0x180018ee0  lea     rdx, [rsp+78h+var_48]
0x180018ee5  mov     r8d, 4
0x180018eeb  mov     [rsp+78h+var_48], 0
0x180018ef3  call    cs:__imp_?DmWnfPublish@@YAJU_WNF_STATE_NAME@@PEBEK@Z; DmWnfPublish(_WNF_STATE_NAME,uchar const *,ulong)
0x180018ef9  mov     ecx, cs:dword_18005A000
0x180018eff  mov     ebx, eax
0x180018f01  cmp     ecx, 4
0x180018f04  jbe     short loc_180018F48
0x180018f06  mov     [rsp+78h+var_44], eax
0x180018f0a  lea     rdx, unk_18004F248
0x180018f11  lea     rax, [rsp+78h+var_44]
0x180018f16  mov     [rsp+78h+var_18], 4
0x180018f1f  mov     [rsp+78h+var_20], rax
0x180018f24  lea     rcx, dword_18005A000
0x180018f2b  lea     rax, [rsp+78h+var_40]
0x180018f30  xor     r9d, r9d
0x180018f33  mov     [rsp+78h+var_50], rax
0x180018f38  xor     r8d, r8d
0x180018f3b  mov     [rsp+78h+var_58], 3
0x180018f43  call    _tlgWriteTransfer_EventWriteTransfer
0x180018f48  xor     eax, eax
0x180018f4a  cmp     ebx, 80070002h
0x180018f50  cmovnz  eax, ebx
0x180018f53  mov     rcx, [rsp+78h+var_10]
0x180018f58  xor     rcx, rsp; StackCookie
0x180018f5b  call    __security_check_cookie
0x180018f60  mov     rbx, [rsp+78h+arg_10]
0x180018f68  add     rsp, 70h
0x180018f6c  pop     rdi
0x180018f6d  retn
```
