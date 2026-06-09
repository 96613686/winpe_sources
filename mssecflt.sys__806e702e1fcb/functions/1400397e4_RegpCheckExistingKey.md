# RegpCheckExistingKey

- ea: `0x1400397e4`
- end: `0x140039966`
- name: `RegpCheckExistingKey`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140038e64`

## callees

- `0x140011650`
- `0x14002aa18`
- `0x140034874`
- `0x1400349e0`
- `0x140034af8`
- `0x1400397e4`

## import_xrefs

- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039937`
- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039937`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400398b5`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400398b5`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140039849`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140039849`
- `ntoskrnl!RtlInitUnicodeString` at `0x140039833`
- `ntoskrnl!RtlInitUnicodeString` at `0x140039890`
- `ntoskrnl!RtlInitUnicodeString` at `0x140039833`
- `ntoskrnl!RtlInitUnicodeString` at `0x140039890`

## string_xrefs

- `0x14003981d`: `\Registry`

## pseudocode

```c
__int64 __fastcall RegpCheckExistingKey(_QWORD *a1, _BYTE *a2, _QWORD *a3)
{
  int KeyObjectIDEx; // ebx
  void *v7; // rdi
  int appended; // eax
  struct _UNICODE_STRING *v10; // [rsp+30h] [rbp-40h] BYREF
  __int64 v11; // [rsp+38h] [rbp-38h] BYREF
  __int64 v12; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING v14; // [rsp+58h] [rbp-18h] BYREF

  KeyObjectIDEx = 0;
  *a3 = 0;
  *a2 = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry");
  if ( RtlPrefixUnicodeString(&DestinationString, (PCUNICODE_STRING)*a1, 1u) )
    v7 = 0;
  else
    v7 = (void *)a1[1];
  if ( RegpDoesKeyExist(v7, (struct _UNICODE_STRING *)*a1) )
  {
    *a2 = 1;
    goto LABEL_13;
  }
  if ( v7 )
  {
    v14 = 0;
    RtlInitUnicodeString(&v14, L"\\");
    KeyObjectIDEx = CmCallbackGetKeyObjectIDEx((char *)RegData + 8, v7, 0, &v12, 0);
    if ( KeyObjectIDEx < 0 )
      goto LABEL_13;
    KeyObjectIDEx = SecAppendUnicodeStringToUnicodeString(v12, &v14, &v11, 1953719123);
    if ( KeyObjectIDEx < 0 )
      goto LABEL_13;
    appended = SecAppendUnicodeStringToUnicodeString(v11, *a1, &v10, 1953719123);
  }
  else
  {
    appended = RegpCopyUnicodeString((PCUNICODE_STRING)*a1, &v10);
  }
  KeyObjectIDEx = appended;
  if ( appended >= 0 )
  {
    *a3 = v10;
    v10 = 0;
  }
LABEL_13:
  RegpFreeUnicodeString(v11);
  RegpFreeUnicodeString(v10);
  if ( v12 )
    CmCallbackReleaseKeyObjectIDEx();
  return (unsigned int)KeyObjectIDEx;
}

```

## disassembly

```asm
0x1400397e4  mov     [rsp-28h+arg_18], rbx
0x1400397e9  push    rbp
0x1400397ea  push    rsi
0x1400397eb  push    rdi
0x1400397ec  push    r14
0x1400397ee  push    r15
0x1400397f0  mov     rbp, rsp
0x1400397f3  sub     rsp, 70h
0x1400397f7  mov     rax, cs:__security_cookie
0x1400397fe  xor     rax, rsp
0x140039801  mov     [rbp+var_8], rax
0x140039805  xor     ebx, ebx
0x140039807  mov     r14, rdx
0x14003980a  mov     [r8], rbx
0x14003980d  mov     rsi, rcx
0x140039810  mov     [rdx], bl
0x140039812  lea     rcx, [rbp+DestinationString]; DestinationString
0x140039816  xorps   xmm0, xmm0
0x140039819  mov     [rbp+var_30], rbx
0x14003981d  lea     rdx, aRegistry; "\\Registry"
0x140039824  mov     [rbp+var_38], rbx
0x140039828  mov     r15, r8
0x14003982b  mov     [rbp+var_40], rbx
0x14003982f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140039833  call    cs:__imp_RtlInitUnicodeString
0x14003983a  nop     dword ptr [rax+rax+00h]
0x14003983f  mov     rdx, [rsi]; String2
0x140039842  lea     rcx, [rbp+DestinationString]; String1
0x140039846  mov     r8b, 1; CaseInSensitive
0x140039849  call    cs:__imp_RtlPrefixUnicodeString
0x140039850  nop     dword ptr [rax+rax+00h]
0x140039855  test    al, al
0x140039857  jz      short loc_14003985D
0x140039859  xor     edi, edi
0x14003985b  jmp     short loc_140039861
0x14003985d  mov     rdi, [rsi+8]
0x140039861  mov     rdx, [rsi]
0x140039864  mov     rcx, rdi
0x140039867  call    RegpDoesKeyExist
0x14003986c  test    al, al
0x14003986e  jz      short loc_140039879
0x140039870  mov     byte ptr [r14], 1
0x140039874  jmp     loc_14003991C
0x140039879  test    rdi, rdi
0x14003987c  jz      short loc_1400398FB
0x14003987e  xorps   xmm0, xmm0
0x140039881  lea     rdx, asc_140015EB4; "\\"
0x140039888  lea     rcx, [rbp+var_18]; DestinationString
0x14003988c  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x140039890  call    cs:__imp_RtlInitUnicodeString
0x140039897  nop     dword ptr [rax+rax+00h]
0x14003989c  mov     rcx, cs:RegData
0x1400398a3  lea     r9, [rbp+var_30]
0x1400398a7  add     rcx, 8
0x1400398ab  mov     [rsp+70h+var_50], ebx
0x1400398af  xor     r8d, r8d
0x1400398b2  mov     rdx, rdi
0x1400398b5  call    cs:__imp_CmCallbackGetKeyObjectIDEx
0x1400398bc  nop     dword ptr [rax+rax+00h]
0x1400398c1  mov     ebx, eax
0x1400398c3  test    eax, eax
0x1400398c5  js      short loc_14003991C
0x1400398c7  mov     rcx, [rbp+var_30]
0x1400398cb  lea     r8, [rbp+var_38]
0x1400398cf  mov     edi, 74736353h
0x1400398d4  lea     rdx, [rbp+var_18]
0x1400398d8  mov     r9d, edi
0x1400398db  call    SecAppendUnicodeStringToUnicodeString
0x1400398e0  mov     ebx, eax
0x1400398e2  test    eax, eax
0x1400398e4  js      short loc_14003991C
0x1400398e6  mov     rdx, [rsi]
0x1400398e9  lea     r8, [rbp+var_40]
0x1400398ed  mov     rcx, [rbp+var_38]
0x1400398f1  mov     r9d, edi
0x1400398f4  call    SecAppendUnicodeStringToUnicodeString
0x1400398f9  jmp     short loc_140039907
0x1400398fb  mov     rcx, [rsi]; SourceString
0x1400398fe  lea     rdx, [rbp+var_40]
0x140039902  call    RegpCopyUnicodeString
0x140039907  mov     ebx, eax
0x140039909  test    eax, eax
0x14003990b  js      short loc_14003991C
0x14003990d  mov     rax, [rbp+var_40]
0x140039911  mov     [r15], rax
0x140039914  mov     [rbp+var_40], 0
0x14003991c  mov     rcx, [rbp+var_38]
0x140039920  call    RegpFreeUnicodeString
0x140039925  mov     rcx, [rbp+var_40]
0x140039929  call    RegpFreeUnicodeString
0x14003992e  mov     rcx, [rbp+var_30]
0x140039932  test    rcx, rcx
0x140039935  jz      short loc_140039943
0x140039937  call    cs:__imp_CmCallbackReleaseKeyObjectIDEx
0x14003993e  nop     dword ptr [rax+rax+00h]
0x140039943  mov     eax, ebx
0x140039945  mov     rcx, [rbp+var_8]
0x140039949  xor     rcx, rsp; StackCookie
0x14003994c  call    __security_check_cookie
0x140039951  mov     rbx, [rsp+70h+arg_18]
0x140039959  add     rsp, 70h
0x14003995d  pop     r15
0x14003995f  pop     r14
0x140039961  pop     rdi
0x140039962  pop     rsi
0x140039963  pop     rbp
0x140039964  retn
```
