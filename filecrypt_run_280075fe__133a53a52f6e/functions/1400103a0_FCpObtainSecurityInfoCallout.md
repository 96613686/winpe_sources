# FCpObtainSecurityInfoCallout

- ea: `0x1400103a0`
- end: `0x1400104fa`
- name: `FCpObtainSecurityInfoCallout`
- size: `346`
- prototype: `EXPAND_STACK_CALLOUT`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002fd0`
- `0x1400103a0`
- `0x140010500`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010466`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001048c`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400104b2`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140010466`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14001048c`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400104b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010442`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010442`

## pseudocode

```c
void __fastcall FCpObtainSecurityInfoCallout(char *Parameter)
{
  UNICODE_STRING *v1; // r14
  char *v2; // rbp
  PVOID *p_P; // rdx
  PVOID v5; // rcx
  int SecurityDescriptor; // esi
  __int64 v7; // r8
  const wchar_t *v8; // rax
  PVOID P; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(UNICODE_STRING **)Parameter;
  v2 = Parameter + 8;
  p_P = &P;
  *((_QWORD *)Parameter + 2) = 0;
  P = 0;
  if ( Parameter != (char *)-8LL )
    p_P = (PVOID *)(Parameter + 8);
  if ( v1->Length )
  {
    SecurityDescriptor = StSecGetSecurityDescriptor(
                           v1,
                           (__int64)p_P,
                           (wchar_t **)Parameter + 2,
                           (_DWORD *)Parameter + 6);
    if ( !v2 )
    {
      v5 = P;
      if ( P )
        ExFreePoolWithTag(P, 0x70537453u);
    }
    if ( SecurityDescriptor < 0 )
    {
      if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(
          (__int64)v5,
          (const EVENT_DESCRIPTOR *)GetSecurityDescriptorFailure,
          v7,
          SecurityDescriptor);
      goto LABEL_9;
    }
    if ( *((_QWORD *)Parameter + 2) )
    {
LABEL_9:
      *((_DWORD *)Parameter + 8) = SecurityDescriptor;
      return;
    }
    if ( (gFCFlags & 4) != 0 )
    {
      v8 = L"{0b7992da-c5e6-41e3-b24f-55419b997a15}";
    }
    else
    {
      if ( (gFCFlags & 2) == 0 )
        goto LABEL_9;
      if ( RtlPrefixUnicodeString(&gMusicPath, v1, 1u) )
      {
        v8 = L"MusicChamber";
      }
      else if ( RtlPrefixUnicodeString(&gPicturesPath, v1, 1u) )
      {
        v8 = L"PicturesChamber";
      }
      else
      {
        if ( !RtlPrefixUnicodeString(&gVideosPath, v1, 1u) )
        {
LABEL_21:
          *((_DWORD *)Parameter + 6) = 1;
          goto LABEL_9;
        }
        v8 = L"VideosChamber";
      }
    }
    *((_QWORD *)Parameter + 2) = v8;
    goto LABEL_21;
  }
  *((_DWORD *)Parameter + 8) = 0;
}

```

## disassembly

```asm
0x1400103a0  mov     [rsp+arg_18], rbx
0x1400103a5  push    rbp
0x1400103a6  push    rdi
0x1400103a7  push    r14
0x1400103a9  sub     rsp, 20h
0x1400103ad  mov     r14, [rcx]
0x1400103b0  lea     rbp, [rcx+8]
0x1400103b4  xor     eax, eax
0x1400103b6  lea     rdx, [rsp+38h+P]
0x1400103bb  test    rbp, rbp
0x1400103be  mov     [rcx+10h], rax
0x1400103c2  mov     rbx, rcx
0x1400103c5  mov     [rsp+38h+P], rax
0x1400103ca  cmovnz  rdx, rbp
0x1400103ce  cmp     [r14], ax
0x1400103d2  jz      short loc_14001042E
0x1400103d4  lea     r9, [rcx+18h]
0x1400103d8  mov     [rsp+38h+arg_8], rsi
0x1400103dd  lea     r8, [rcx+10h]
0x1400103e1  mov     [rsp+38h+arg_10], r15
0x1400103e6  mov     rcx, r14
0x1400103e9  call    StSecGetSecurityDescriptor
0x1400103ee  mov     esi, eax
0x1400103f0  test    rbp, rbp
0x1400103f3  jz      short loc_140010433
0x1400103f5  test    esi, esi
0x1400103f7  js      loc_1400104D9
0x1400103fd  cmp     qword ptr [rbx+10h], 0
0x140010402  jnz     short loc_140010412
0x140010404  mov     eax, cs:gFCFlags
0x14001040a  test    al, 4
0x14001040c  jnz     short loc_140010450
0x14001040e  test    al, 2
0x140010410  jnz     short loc_140010459
0x140010412  mov     r15, [rsp+38h+arg_10]
0x140010417  mov     [rbx+20h], esi
0x14001041a  mov     rsi, [rsp+38h+arg_8]
0x14001041f  mov     rbx, [rsp+38h+arg_18]
0x140010424  add     rsp, 20h
0x140010428  pop     r14
0x14001042a  pop     rdi
0x14001042b  pop     rbp
0x14001042c  retn
0x14001042e  mov     [rcx+20h], eax
0x140010431  jmp     short loc_14001041F
0x140010433  mov     rcx, [rsp+38h+P]; P
0x140010438  test    rcx, rcx
0x14001043b  jz      short loc_1400103F5
0x14001043d  mov     edx, 70537453h; Tag
0x140010442  call    cs:__imp_ExFreePoolWithTag
0x140010449  nop     dword ptr [rax+rax+00h]
0x14001044e  jmp     short loc_1400103F5
0x140010450  lea     rax, a0b7992daC5e641; "{0b7992da-c5e6-41e3-b24f-55419b997a15}"
0x140010457  jmp     short loc_1400104C9
0x140010459  mov     r8b, 1; CaseInSensitive
0x14001045c  lea     rcx, gMusicPath; String1
0x140010463  mov     rdx, r14; String2
0x140010466  call    cs:__imp_RtlPrefixUnicodeString
0x14001046d  nop     dword ptr [rax+rax+00h]
0x140010472  test    al, al
0x140010474  jz      short loc_14001047F
0x140010476  lea     rax, aMusicchamber; "MusicChamber"
0x14001047d  jmp     short loc_1400104C9
0x14001047f  mov     r8b, 1; CaseInSensitive
0x140010482  lea     rcx, gPicturesPath; String1
0x140010489  mov     rdx, r14; String2
0x14001048c  call    cs:__imp_RtlPrefixUnicodeString
0x140010493  nop     dword ptr [rax+rax+00h]
0x140010498  test    al, al
0x14001049a  jz      short loc_1400104A5
0x14001049c  lea     rax, aPictureschambe; "PicturesChamber"
0x1400104a3  jmp     short loc_1400104C9
0x1400104a5  mov     r8b, 1; CaseInSensitive
0x1400104a8  lea     rcx, gVideosPath; String1
0x1400104af  mov     rdx, r14; String2
0x1400104b2  call    cs:__imp_RtlPrefixUnicodeString
0x1400104b9  nop     dword ptr [rax+rax+00h]
0x1400104be  test    al, al
0x1400104c0  jz      short loc_1400104CD
0x1400104c2  lea     rax, aVideoschamber; "VideosChamber"
0x1400104c9  mov     [rbx+10h], rax
0x1400104cd  mov     dword ptr [rbx+18h], 1
0x1400104d4  jmp     loc_140010412
0x1400104d9  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x1400104e0  jz      loc_140010412
0x1400104e6  mov     r9d, esi
0x1400104e9  lea     rdx, GetSecurityDescriptorFailure
0x1400104f0  call    McTemplateK0d_EtwWriteTransfer
0x1400104f5  jmp     loc_140010412
```
