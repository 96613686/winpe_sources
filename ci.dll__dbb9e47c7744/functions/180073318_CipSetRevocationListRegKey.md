# CipSetRevocationListRegKey

- ea: `0x180073318`
- end: `0x18007341e`
- name: `CipSetRevocationListRegKey`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005e6d0`

## callees

- `0x180073318`
- `0x180073424`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180073393`
- `ntoskrnl!ZwCreateKey` at `0x180073393`
- `ntoskrnl!ZwClose` at `0x180073406`
- `ntoskrnl!ZwClose` at `0x180073406`

## pseudocode

```c
__int64 __fastcall CipSetRevocationListRegKey(__int64 a1)
{
  int v3; // esi
  NTSTATUS v4; // edi
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  KeyHandle = 0;
  if ( !a1 )
    return 0;
  v3 = *(_DWORD *)(a1 + 104);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180030A60;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  v4 = ZwCreateKey(&KeyHandle, 0x20006u, &ObjectAttributes, 0, 0, 0, 0);
  if ( v4 >= 0 )
  {
    if ( !*(_QWORD *)(a1 + 96)
      || !*(_QWORD *)(a1 + 88)
      || (v3 != 3 ? (v5 = *(_QWORD *)(a1 + 88)) : (v5 = *(_QWORD *)(a1 + 96)),
          v4 = CipSetTimeInRegKey(v5, L"LN", KeyHandle),
          v4 >= 0) )
    {
      if ( !v3 )
      {
        v6 = *(_QWORD *)(a1 + 72);
LABEL_14:
        v4 = CipSetTimeInRegKey(v6, L"BD", KeyHandle);
        goto LABEL_15;
      }
      if ( v3 == 1 )
      {
        v6 = *(_QWORD *)(a1 + 80);
        goto LABEL_14;
      }
    }
  }
LABEL_15:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180073318  push    rbp
0x18007331a  push    rbx
0x18007331b  push    rsi
0x18007331c  push    rdi
0x18007331d  mov     rbp, rsp
0x180073320  sub     rsp, 78h
0x180073324  mov     [rbp+KeyHandle], 0
0x18007332c  mov     rbx, rcx
0x18007332f  test    rcx, rcx
0x180073332  jnz     short loc_18007333B
0x180073334  xor     eax, eax
0x180073336  jmp     loc_180073414
0x18007333b  mov     esi, [rcx+68h]
0x18007333e  lea     rax, qword_180030A60
0x180073345  xorps   xmm0, xmm0
0x180073348  mov     [rsp+78h+Disposition], 0; Disposition
0x180073351  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x180073359  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18007335d  xor     r9d, r9d; TitleIndex
0x180073360  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180073364  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180073368  mov     [rsp+78h+Class], 0; Class
0x180073371  mov     edx, 20006h; DesiredAccess
0x180073376  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007337e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180073383  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007338b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x180073393  call    cs:__imp_ZwCreateKey
0x18007339a  nop     dword ptr [rax+rax+00h]
0x18007339f  mov     edi, eax
0x1800733a1  test    eax, eax
0x1800733a3  js      short loc_1800733FD
0x1800733a5  cmp     qword ptr [rbx+60h], 0
0x1800733aa  jz      short loc_1800733D8
0x1800733ac  cmp     qword ptr [rbx+58h], 0
0x1800733b1  jz      short loc_1800733D8
0x1800733b3  mov     r8, [rbp+KeyHandle]
0x1800733b7  lea     rdx, aLn; "LN"
0x1800733be  cmp     esi, 3
0x1800733c1  jnz     short loc_1800733C9
0x1800733c3  mov     rcx, [rbx+60h]
0x1800733c7  jmp     short loc_1800733CD
0x1800733c9  mov     rcx, [rbx+58h]
0x1800733cd  call    CipSetTimeInRegKey
0x1800733d2  mov     edi, eax
0x1800733d4  test    eax, eax
0x1800733d6  js      short loc_1800733FD
0x1800733d8  test    esi, esi
0x1800733da  jnz     short loc_1800733E2
0x1800733dc  mov     rcx, [rbx+48h]
0x1800733e0  jmp     short loc_1800733EB
0x1800733e2  cmp     esi, 1
0x1800733e5  jnz     short loc_1800733FD
0x1800733e7  mov     rcx, [rbx+50h]
0x1800733eb  mov     r8, [rbp+KeyHandle]
0x1800733ef  lea     rdx, aBd; "BD"
0x1800733f6  call    CipSetTimeInRegKey
0x1800733fb  mov     edi, eax
0x1800733fd  mov     rcx, [rbp+KeyHandle]; Handle
0x180073401  test    rcx, rcx
0x180073404  jz      short loc_180073412
0x180073406  call    cs:__imp_ZwClose
0x18007340d  nop     dword ptr [rax+rax+00h]
0x180073412  mov     eax, edi
0x180073414  add     rsp, 78h
0x180073418  pop     rdi
0x180073419  pop     rsi
0x18007341a  pop     rbx
0x18007341b  pop     rbp
0x18007341c  retn
```
