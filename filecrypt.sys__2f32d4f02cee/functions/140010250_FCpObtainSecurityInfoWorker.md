# FCpObtainSecurityInfoWorker

- ea: `0x140010250`
- end: `0x140010397`
- name: `FCpObtainSecurityInfoWorker`
- size: `327`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String2)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f2f0`

## callees

- `0x140002fd0`
- `0x140010250`
- `0x140010500`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010304`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001032a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010350`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010304`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001032a`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010350`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400102d6`

## pseudocode

```c
__int64 __fastcall FCpObtainSecurityInfoWorker(UNICODE_STRING *String2, PVOID *a2, wchar_t **a3, _DWORD *a4)
{
  __int64 result; // rax
  bool v6; // zf
  PVOID *p_P; // rdx
  PVOID v11; // rcx
  unsigned int SecurityDescriptor; // ebx
  __int64 v13; // r8
  const wchar_t *v14; // rax
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  result = 0;
  v6 = a2 == 0;
  *a3 = 0;
  p_P = &P;
  P = 0;
  if ( !v6 )
    p_P = a2;
  if ( String2->Length )
  {
    SecurityDescriptor = StSecGetSecurityDescriptor(String2, (__int64)p_P, a3, a4);
    if ( !a2 )
    {
      v11 = P;
      if ( P )
        ExFreePoolWithTag(P, 0x70537453u);
    }
    if ( (SecurityDescriptor & 0x80000000) != 0 )
    {
      if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer((__int64)v11, &GetSecurityDescriptorFailure, v13, SecurityDescriptor);
      return SecurityDescriptor;
    }
    if ( *a3 )
      return SecurityDescriptor;
    if ( (gFCFlags & 4) != 0 )
    {
      *a3 = L"{0b7992da-c5e6-41e3-b24f-55419b997a15}";
      *a4 = 1;
      return SecurityDescriptor;
    }
    if ( (gFCFlags & 2) == 0 )
      return SecurityDescriptor;
    if ( RtlPrefixUnicodeString(&gMusicPath, String2, 1u) )
    {
      v14 = L"MusicChamber";
    }
    else if ( RtlPrefixUnicodeString(&gPicturesPath, String2, 1u) )
    {
      v14 = L"PicturesChamber";
    }
    else
    {
      if ( !RtlPrefixUnicodeString(&gVideosPath, String2, 1u) )
      {
LABEL_21:
        *a4 = 1;
        return SecurityDescriptor;
      }
      v14 = L"VideosChamber";
    }
    *a3 = (wchar_t *)v14;
    goto LABEL_21;
  }
  return result;
}

```

## disassembly

```asm
0x140010250  mov     [rsp+arg_10], rbp
0x140010255  push    rsi
0x140010256  push    rdi
0x140010257  push    r14
0x140010259  sub     rsp, 20h
0x14001025d  xor     eax, eax
0x14001025f  mov     rsi, rdx
0x140010262  test    rsi, rsi
0x140010265  mov     [r8], rax
0x140010268  lea     rdx, [rsp+38h+P]
0x14001026d  mov     [rsp+38h+P], rax
0x140010272  cmovnz  rdx, rsi
0x140010276  mov     r14, r9
0x140010279  mov     rdi, r8
0x14001027c  mov     rbp, rcx
0x14001027f  cmp     [rcx], ax
0x140010282  jz      short loc_1400102B8
0x140010284  mov     [rsp+38h+arg_8], rbx
0x140010289  call    StSecGetSecurityDescriptor
0x14001028e  mov     ebx, eax
0x140010290  test    rsi, rsi
0x140010293  jz      short loc_1400102C7
0x140010295  test    ebx, ebx
0x140010297  js      loc_140010376
0x14001029d  cmp     qword ptr [rdi], 0
0x1400102a1  jnz     short loc_1400102B1
0x1400102a3  mov     eax, cs:gFCFlags
0x1400102a9  test    al, 4
0x1400102ab  jnz     short loc_1400102E4
0x1400102ad  test    al, 2
0x1400102af  jnz     short loc_1400102F7
0x1400102b1  mov     eax, ebx
0x1400102b3  mov     rbx, [rsp+38h+arg_8]
0x1400102b8  mov     rbp, [rsp+38h+arg_10]
0x1400102bd  add     rsp, 20h
0x1400102c1  pop     r14
0x1400102c3  pop     rdi
0x1400102c4  pop     rsi
0x1400102c5  retn
0x1400102c7  mov     rcx, [rsp+38h+P]; P
0x1400102cc  test    rcx, rcx
0x1400102cf  jz      short loc_140010295
0x1400102d1  mov     edx, 70537453h; Tag
0x1400102d6  call    cs:__imp_ExFreePoolWithTag
0x1400102dd  nop     dword ptr [rax+rax+00h]
0x1400102e2  jmp     short loc_140010295
0x1400102e4  lea     rax, a0b7992daC5e641; "{0b7992da-c5e6-41e3-b24f-55419b997a15}"
0x1400102eb  mov     [rdi], rax
0x1400102ee  mov     dword ptr [r14], 1
0x1400102f5  jmp     short loc_1400102B1
0x1400102f7  mov     r8b, 1; CaseInSensitive
0x1400102fa  lea     rcx, gMusicPath; String1
0x140010301  mov     rdx, rbp; String2
0x140010304  call    cs:__imp_RtlPrefixUnicodeString
0x14001030b  nop     dword ptr [rax+rax+00h]
0x140010310  test    al, al
0x140010312  jz      short loc_14001031D
0x140010314  lea     rax, aMusicchamber; "MusicChamber"
0x14001031b  jmp     short loc_140010367
0x14001031d  mov     r8b, 1; CaseInSensitive
0x140010320  lea     rcx, gPicturesPath; String1
0x140010327  mov     rdx, rbp; String2
0x14001032a  call    cs:__imp_RtlPrefixUnicodeString
0x140010331  nop     dword ptr [rax+rax+00h]
0x140010336  test    al, al
0x140010338  jz      short loc_140010343
0x14001033a  lea     rax, aPictureschambe; "PicturesChamber"
0x140010341  jmp     short loc_140010367
0x140010343  mov     r8b, 1; CaseInSensitive
0x140010346  lea     rcx, gVideosPath; String1
0x14001034d  mov     rdx, rbp; String2
0x140010350  call    cs:__imp_RtlPrefixUnicodeString
0x140010357  nop     dword ptr [rax+rax+00h]
0x14001035c  test    al, al
0x14001035e  jz      short loc_14001036A
0x140010360  lea     rax, aVideoschamber; "VideosChamber"
0x140010367  mov     [rdi], rax
0x14001036a  mov     dword ptr [r14], 1
0x140010371  jmp     loc_1400102B1
0x140010376  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x14001037d  jz      loc_1400102B1
0x140010383  mov     r9d, ebx
0x140010386  lea     rdx, GetSecurityDescriptorFailure
0x14001038d  call    McTemplateK0d_EtwWriteTransfer
0x140010392  jmp     loc_1400102B1
```
