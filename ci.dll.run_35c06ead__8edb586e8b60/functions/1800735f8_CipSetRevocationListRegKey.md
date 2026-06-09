# CipSetRevocationListRegKey

- ea: `0x1800735f8`
- end: `0x1800736fe`
- name: `CipSetRevocationListRegKey`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005e670`

## callees

- `0x1800735f8`
- `0x180073704`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x180073673`
- `ntoskrnl!ZwCreateKey` at `0x180073673`
- `ntoskrnl!ZwClose` at `0x1800736e6`
- `ntoskrnl!ZwClose` at `0x1800736e6`

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
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_180030A40;
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
0x1800735f8  push    rbp
0x1800735fa  push    rbx
0x1800735fb  push    rsi
0x1800735fc  push    rdi
0x1800735fd  mov     rbp, rsp
0x180073600  sub     rsp, 78h
0x180073604  mov     [rbp+KeyHandle], 0
0x18007360c  mov     rbx, rcx
0x18007360f  test    rcx, rcx
0x180073612  jnz     short loc_18007361B
0x180073614  xor     eax, eax
0x180073616  jmp     loc_1800736F4
0x18007361b  mov     esi, [rcx+68h]
0x18007361e  lea     rax, qword_180030A40
0x180073625  xorps   xmm0, xmm0
0x180073628  mov     [rsp+78h+Disposition], 0; Disposition
0x180073631  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x180073639  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18007363d  xor     r9d, r9d; TitleIndex
0x180073640  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180073644  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180073648  mov     [rsp+78h+Class], 0; Class
0x180073651  mov     edx, 20006h; DesiredAccess
0x180073656  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007365e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180073663  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007366b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x180073673  call    cs:__imp_ZwCreateKey
0x18007367a  nop     dword ptr [rax+rax+00h]
0x18007367f  mov     edi, eax
0x180073681  test    eax, eax
0x180073683  js      short loc_1800736DD
0x180073685  cmp     qword ptr [rbx+60h], 0
0x18007368a  jz      short loc_1800736B8
0x18007368c  cmp     qword ptr [rbx+58h], 0
0x180073691  jz      short loc_1800736B8
0x180073693  mov     r8, [rbp+KeyHandle]
0x180073697  lea     rdx, aLn; "LN"
0x18007369e  cmp     esi, 3
0x1800736a1  jnz     short loc_1800736A9
0x1800736a3  mov     rcx, [rbx+60h]
0x1800736a7  jmp     short loc_1800736AD
0x1800736a9  mov     rcx, [rbx+58h]
0x1800736ad  call    CipSetTimeInRegKey
0x1800736b2  mov     edi, eax
0x1800736b4  test    eax, eax
0x1800736b6  js      short loc_1800736DD
0x1800736b8  test    esi, esi
0x1800736ba  jnz     short loc_1800736C2
0x1800736bc  mov     rcx, [rbx+48h]
0x1800736c0  jmp     short loc_1800736CB
0x1800736c2  cmp     esi, 1
0x1800736c5  jnz     short loc_1800736DD
0x1800736c7  mov     rcx, [rbx+50h]
0x1800736cb  mov     r8, [rbp+KeyHandle]
0x1800736cf  lea     rdx, aBd; "BD"
0x1800736d6  call    CipSetTimeInRegKey
0x1800736db  mov     edi, eax
0x1800736dd  mov     rcx, [rbp+KeyHandle]; Handle
0x1800736e1  test    rcx, rcx
0x1800736e4  jz      short loc_1800736F2
0x1800736e6  call    cs:__imp_ZwClose
0x1800736ed  nop     dword ptr [rax+rax+00h]
0x1800736f2  mov     eax, edi
0x1800736f4  add     rsp, 78h
0x1800736f8  pop     rdi
0x1800736f9  pop     rsi
0x1800736fa  pop     rbx
0x1800736fb  pop     rbp
0x1800736fc  retn
```
