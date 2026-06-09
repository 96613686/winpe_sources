# DusmPublishToWcm(DusmConnection const &,_WCM_OPCODE,uchar const *,ulong)

- ea: `0x18001b7c0`
- end: `0x18001b87f`
- name: `?DusmPublishToWcm@@YAKAEBVDusmConnection@@W4_WCM_OPCODE@@PEBEK@Z`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800186fc`
- `0x180019608`
- `0x18003050c`

## callees

- `0x180007c90`
- `0x180012fcc`
- `0x18001842c`
- `0x18001b7c0`

## import_xrefs

- `wcmapi!WcmOpenHandle` at `0x18001b80c`
- `wcmapi!WcmOpenHandle` at `0x18001b80c`
- `wcmapi!WcmSetParameter` at `0x18001b84e`
- `wcmapi!WcmSetParameter` at `0x18001b84e`

## pseudocode

```c
__int64 __fastcall DusmPublishToWcm(__int64 a1, unsigned int a2, __int64 a3, int a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rax
  __int64 *v11; // [rsp+40h] [rbp-58h] BYREF
  char v12; // [rsp+48h] [rbp-50h]
  __int64 v13; // [rsp+50h] [rbp-48h] BYREF
  int v14; // [rsp+58h] [rbp-40h] BYREF

  v13 = 0;
  v14 = 0;
  v11 = &v13;
  v8 = WcmOpenHandle(1, 0, &v14, &v13);
  if ( !v8 )
  {
    if ( *(_QWORD *)(a1 + 64) )
      v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1 + 48);
    else
      v9 = 0;
    v8 = WcmSetParameter(v13, a1 + 32, v9, a2, 0, a4, a3);
  }
  v12 = 0;
  DusmPublishToWcm_::_2_::_lambda_1_::operator()(&v11);
  return v8;
}

```

## disassembly

```asm
0x18001b7c0  mov     r11, rsp
0x18001b7c3  push    rbx
0x18001b7c4  push    rbp
0x18001b7c5  push    rsi
0x18001b7c6  push    rdi
0x18001b7c7  push    r14
0x18001b7c9  sub     rsp, 70h
0x18001b7cd  mov     rax, cs:__security_cookie
0x18001b7d4  xor     rax, rsp
0x18001b7d7  mov     [rsp+98h+var_38], rax
0x18001b7dc  mov     esi, edx
0x18001b7de  mov     qword ptr [r11-48h], 0
0x18001b7e6  xor     edx, edx
0x18001b7e8  mov     [rsp+98h+var_40], 0
0x18001b7f0  mov     r14d, r9d
0x18001b7f3  lea     rax, [r11-48h]
0x18001b7f7  mov     rbp, r8
0x18001b7fa  mov     [r11-58h], rax
0x18001b7fe  mov     rdi, rcx
0x18001b801  lea     r9, [r11-48h]
0x18001b805  lea     ecx, [rdx+1]
0x18001b808  lea     r8, [r11-40h]
0x18001b80c  call    cs:__imp_WcmOpenHandle
0x18001b812  mov     ebx, eax
0x18001b814  test    eax, eax
0x18001b816  jnz     short loc_18001B856
0x18001b818  lea     rcx, [rdi+30h]
0x18001b81c  cmp     qword ptr [rcx+10h], 0
0x18001b821  jnz     short loc_18001B827
0x18001b823  xor     eax, eax
0x18001b825  jmp     short loc_18001B82C
0x18001b827  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b82c  mov     rcx, [rsp+98h+var_48]
0x18001b831  lea     rdx, [rdi+20h]
0x18001b835  mov     [rsp+98h+var_68], rbp
0x18001b83a  mov     r9d, esi
0x18001b83d  mov     [rsp+98h+var_70], r14d
0x18001b842  mov     r8, rax
0x18001b845  mov     [rsp+98h+var_78], 0
0x18001b84e  call    cs:__imp_WcmSetParameter
0x18001b854  mov     ebx, eax
0x18001b856  lea     rcx, [rsp+98h+var_58]
0x18001b85b  mov     [rsp+98h+var_50], 0
0x18001b860  call    _DusmPublishToWcm____2____lambda_1___operator__
0x18001b865  mov     eax, ebx
0x18001b867  mov     rcx, [rsp+98h+var_38]
0x18001b86c  xor     rcx, rsp; StackCookie
0x18001b86f  call    __security_check_cookie
0x18001b874  add     rsp, 70h
0x18001b878  pop     r14
0x18001b87a  pop     rdi
0x18001b87b  pop     rsi
0x18001b87c  pop     rbp
0x18001b87d  pop     rbx
0x18001b87e  retn
```
