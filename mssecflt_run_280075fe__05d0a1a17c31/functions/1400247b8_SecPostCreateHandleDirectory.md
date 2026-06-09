# SecPostCreateHandleDirectory

- ea: `0x1400247b8`
- end: `0x1400248fd`
- name: `SecPostCreateHandleDirectory`
- size: `325`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140023e10`

## callees

- `0x140010347`
- `0x1400103e3`
- `0x140011650`
- `0x1400247b8`
- `0x140027ec4`
- `0x140028c20`
- `0x140028f7c`
- `0x1400290c4`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14002486e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002486e`

## pseudocode

```c
void __fastcall SecPostCreateHandleDirectory(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  ULONG_PTR Information; // rax
  int v3; // esi
  PFLT_CONTEXT Context; // [rsp+28h] [rbp-20h] BYREF
  _BYTE v7[8]; // [rsp+30h] [rbp-18h] BYREF

  Information = CallbackData->IoStatus.Information;
  v3 = 2;
  Context = 0;
  v7[0] = 0;
  if ( Information != 2
    && Information != 3
    && (Information || CallbackData->Iopb->Parameters.Create.Options >= 0x1000000)
    && (xmmword_14001B740 & 0x10000000) != 0 )
  {
    if ( FltGetInstanceContext_0(*(PFLT_INSTANCE *)(a2 + 24), &Context) >= 0 )
    {
      if ( !(unsigned __int8)SecIsRemoteDeviceType(*((unsigned int *)Context + 17))
        || !RtlCompareUnicodeString(&MupDeviceFileName, (PCUNICODE_STRING)(*(_QWORD *)(a2 + 32) + 88LL), 1u) )
      {
        if ( !(unsigned __int8)SecGetKernelModeEcpFromCallbackData(*(PFLT_FILTER *)(a2 + 8))
          || (int)SecIsSrvClientLocalhost(MEMORY[8], v7) < 0
          || v7[0] )
        {
          goto LABEL_14;
        }
        v3 = 1;
      }
      SecSendOpenNetShareEvent(CallbackData, a2, v3, 0);
    }
LABEL_14:
    if ( Context )
      FltReleaseContext_0(Context);
  }
}

```

## disassembly

```asm
0x1400247b8  mov     r11, rsp
0x1400247bb  mov     [r11+18h], rbx
0x1400247bf  mov     [r11+20h], rsi
0x1400247c3  push    rdi
0x1400247c4  sub     rsp, 40h
0x1400247c8  mov     rax, cs:__security_cookie
0x1400247cf  xor     rax, rsp
0x1400247d2  mov     [rsp+48h+var_10], rax
0x1400247d7  mov     rax, [rcx+20h]
0x1400247db  mov     esi, 2
0x1400247e0  mov     qword ptr [r11-20h], 0
0x1400247e8  mov     rdi, rdx
0x1400247eb  mov     qword ptr [r11-28h], 0
0x1400247f3  mov     rbx, rcx
0x1400247f6  mov     [rsp+48h+var_18], 0
0x1400247fb  cmp     rax, rsi
0x1400247fe  jz      loc_1400248DF
0x140024804  cmp     rax, 3
0x140024808  jz      loc_1400248DF
0x14002480e  test    rax, rax
0x140024811  jnz     short loc_140024824
0x140024813  mov     rax, [rcx+10h]
0x140024817  cmp     dword ptr [rax+20h], 1000000h
0x14002481e  jb      loc_1400248DF
0x140024824  test    qword ptr cs:xmmword_14001B740, 10000000h
0x14002482f  jz      loc_1400248DF
0x140024835  mov     rcx, [rdi+18h]; Instance
0x140024839  lea     rdx, [rsp+48h+Context]; Context
0x14002483e  call    FltGetInstanceContext_0
0x140024843  test    eax, eax
0x140024845  js      loc_1400248D0
0x14002484b  mov     rcx, [rsp+48h+Context]
0x140024850  mov     ecx, [rcx+44h]
0x140024853  call    SecIsRemoteDeviceType
0x140024858  test    al, al
0x14002485a  jz      short loc_14002487E
0x14002485c  mov     rdx, [rdi+20h]
0x140024860  lea     rcx, MupDeviceFileName; String1
0x140024867  add     rdx, 58h ; 'X'; String2
0x14002486b  mov     r8b, 1; CaseInSensitive
0x14002486e  call    cs:__imp_RtlCompareUnicodeString
0x140024875  nop     dword ptr [rax+rax+00h]
0x14002487a  test    eax, eax
0x14002487c  jnz     short loc_1400248BD
0x14002487e  mov     rcx, [rdi+8]; Filter
0x140024882  lea     r9, [rsp+48h+var_28]
0x140024887  lea     r8, GUID_ECP_SRV_OPEN
0x14002488e  mov     rdx, rbx
0x140024891  call    SecGetKernelModeEcpFromCallbackData
0x140024896  test    al, al
0x140024898  jz      short loc_1400248D0
0x14002489a  mov     rcx, [rsp+48h+var_28]
0x14002489f  lea     rdx, [rsp+48h+var_18]
0x1400248a4  mov     rcx, [rcx+8]
0x1400248a8  call    SecIsSrvClientLocalhost
0x1400248ad  test    eax, eax
0x1400248af  js      short loc_1400248D0
0x1400248b1  cmp     [rsp+48h+var_18], 0
0x1400248b6  jnz     short loc_1400248D0
0x1400248b8  mov     esi, 1
0x1400248bd  mov     r9, [rsp+48h+var_28]
0x1400248c2  mov     r8d, esi
0x1400248c5  mov     rdx, rdi
0x1400248c8  mov     rcx, rbx; CallbackData
0x1400248cb  call    SecSendOpenNetShareEvent
0x1400248d0  mov     rcx, [rsp+48h+Context]; Context
0x1400248d5  test    rcx, rcx
0x1400248d8  jz      short loc_1400248DF
0x1400248da  call    FltReleaseContext_0
0x1400248df  mov     rcx, [rsp+48h+var_10]
0x1400248e4  xor     rcx, rsp; StackCookie
0x1400248e7  call    __security_check_cookie
0x1400248ec  mov     rbx, [rsp+48h+arg_10]
0x1400248f1  mov     rsi, [rsp+48h+arg_18]
0x1400248f6  add     rsp, 40h
0x1400248fa  pop     rdi
0x1400248fb  retn
```
