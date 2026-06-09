# CipSetRevocationListRegKey

- ea: `0x180072068`
- end: `0x18007216e`
- name: `CipSetRevocationListRegKey`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18005dfd0`

## callees

- `0x180072068`
- `0x180072174`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x1800720e3`
- `ntoskrnl!ZwCreateKey` at `0x1800720e3`
- `ntoskrnl!ZwClose` at `0x180072156`
- `ntoskrnl!ZwClose` at `0x180072156`

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
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1800309C0;
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
0x180072068  push    rbp
0x18007206a  push    rbx
0x18007206b  push    rsi
0x18007206c  push    rdi
0x18007206d  mov     rbp, rsp
0x180072070  sub     rsp, 78h
0x180072074  mov     [rbp+KeyHandle], 0
0x18007207c  mov     rbx, rcx
0x18007207f  test    rcx, rcx
0x180072082  jnz     short loc_18007208B
0x180072084  xor     eax, eax
0x180072086  jmp     loc_180072164
0x18007208b  mov     esi, [rcx+68h]
0x18007208e  lea     rax, qword_1800309C0
0x180072095  xorps   xmm0, xmm0
0x180072098  mov     [rsp+78h+Disposition], 0; Disposition
0x1800720a1  mov     [rsp+78h+CreateOptions], 0; CreateOptions
0x1800720a9  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1800720ad  xor     r9d, r9d; TitleIndex
0x1800720b0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800720b4  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800720b8  mov     [rsp+78h+Class], 0; Class
0x1800720c1  mov     edx, 20006h; DesiredAccess
0x1800720c6  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800720ce  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800720d3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800720db  mov     qword ptr [rbp+ObjectAttributes.Attributes], 240h
0x1800720e3  call    cs:__imp_ZwCreateKey
0x1800720ea  nop     dword ptr [rax+rax+00h]
0x1800720ef  mov     edi, eax
0x1800720f1  test    eax, eax
0x1800720f3  js      short loc_18007214D
0x1800720f5  cmp     qword ptr [rbx+60h], 0
0x1800720fa  jz      short loc_180072128
0x1800720fc  cmp     qword ptr [rbx+58h], 0
0x180072101  jz      short loc_180072128
0x180072103  mov     r8, [rbp+KeyHandle]
0x180072107  lea     rdx, aLn; "LN"
0x18007210e  cmp     esi, 3
0x180072111  jnz     short loc_180072119
0x180072113  mov     rcx, [rbx+60h]
0x180072117  jmp     short loc_18007211D
0x180072119  mov     rcx, [rbx+58h]
0x18007211d  call    CipSetTimeInRegKey
0x180072122  mov     edi, eax
0x180072124  test    eax, eax
0x180072126  js      short loc_18007214D
0x180072128  test    esi, esi
0x18007212a  jnz     short loc_180072132
0x18007212c  mov     rcx, [rbx+48h]
0x180072130  jmp     short loc_18007213B
0x180072132  cmp     esi, 1
0x180072135  jnz     short loc_18007214D
0x180072137  mov     rcx, [rbx+50h]
0x18007213b  mov     r8, [rbp+KeyHandle]
0x18007213f  lea     rdx, aBd; "BD"
0x180072146  call    CipSetTimeInRegKey
0x18007214b  mov     edi, eax
0x18007214d  mov     rcx, [rbp+KeyHandle]; Handle
0x180072151  test    rcx, rcx
0x180072154  jz      short loc_180072162
0x180072156  call    cs:__imp_ZwClose
0x18007215d  nop     dword ptr [rax+rax+00h]
0x180072162  mov     eax, edi
0x180072164  add     rsp, 78h
0x180072168  pop     rdi
0x180072169  pop     rsi
0x18007216a  pop     rbx
0x18007216b  pop     rbp
0x18007216c  retn
```
