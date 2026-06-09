# MupiOpenUncHardeningRegistryKey

- ea: `0x1400151fc`
- end: `0x14001537a`
- name: `MupiOpenUncHardeningRegistryKey`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014b70`
- `0x140014ea0`
- `0x1400153e0`

## callees

- `0x1400151fc`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140015338`
- `ntoskrnl!ZwClose` at `0x140015338`
- `ntoskrnl!ZwOpenKey` at `0x140015246`
- `ntoskrnl!ZwOpenKey` at `0x140015246`
- `ntoskrnl!ZwCreateKey` at `0x14001531b`
- `ntoskrnl!ZwCreateKey` at `0x14001531b`

## pseudocode

```c
__int64 __fastcall MupiOpenUncHardeningRegistryKey(void **a1)
{
  NTSTATUS v2; // ebx
  unsigned __int16 v3; // si
  unsigned __int16 v4; // dx
  __int128 v6; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(a1, 0x20019u, &ObjectAttributes);
  if ( v2 == -1073741772 )
  {
    v3 = 0;
    v4 = 0;
    v6 = *(_OWORD *)MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH;
    while ( 1 )
    {
      LOWORD(v6) = v4;
      if ( v4 > 0xA6u )
        break;
      KeyHandle = 0;
      while ( (unsigned int)v4 + 2 <= 0xA6 && *(_WORD *)(*((_QWORD *)&v6 + 1) + 2 * ((unsigned __int64)v4 >> 1)) != 92 )
      {
        v4 += 2;
        LOWORD(v6) = v4;
      }
      if ( (unsigned __int16)(v4 - 1) <= 0xA4u )
        ++v3;
      if ( v3 > 4u )
      {
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v6;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        v2 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
        if ( v2 < 0 )
          goto LABEL_19;
        if ( (_WORD)v6 == 166 )
        {
          *a1 = KeyHandle;
          return 0;
        }
        ZwClose(KeyHandle);
        v4 = v6;
      }
      v4 += 2;
    }
  }
  if ( v2 >= 0 )
    return 0;
  else
LABEL_19:
    *a1 = 0;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400151fc  push    rbp
0x1400151fe  push    rbx
0x1400151ff  push    rsi
0x140015200  push    rdi
0x140015201  push    r12
0x140015203  push    r15
0x140015205  lea     rbp, [rsp-2Fh]
0x14001520a  sub     rsp, 88h
0x140015211  xor     eax, eax
0x140015213  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001521b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001521f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140015223  lea     rax, MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH
0x14001522a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140015232  xorps   xmm0, xmm0
0x140015235  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140015239  mov     edx, 20019h; DesiredAccess
0x14001523e  mov     rdi, rcx
0x140015241  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015246  call    cs:__imp_ZwOpenKey
0x14001524d  nop     dword ptr [rax+rax+00h]
0x140015252  mov     ebx, eax
0x140015254  cmp     eax, 0C0000034h
0x140015259  jnz     loc_14001536D
0x14001525f  movups  xmm0, xmmword ptr cs:MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH
0x140015266  xor     esi, esi
0x140015268  mov     r15d, 0A6h
0x14001526e  xor     edx, edx
0x140015270  movdqu  [rbp+57h+var_70], xmm0
0x140015275  lea     r12d, [rsi+2]
0x140015279  mov     word ptr [rbp+57h+var_70], dx
0x14001527d  cmp     dx, r15w
0x140015281  ja      loc_14001536D
0x140015287  mov     [rbp+57h+KeyHandle], 0
0x14001528f  jmp     short loc_1400152AA
0x140015291  mov     rax, qword ptr [rbp+57h+var_70+8]
0x140015295  movzx   ecx, dx
0x140015298  shr     rcx, 1
0x14001529b  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400152a0  jz      short loc_1400152B5
0x1400152a2  add     dx, r12w
0x1400152a6  mov     word ptr [rbp+57h+var_70], dx
0x1400152aa  movzx   eax, dx
0x1400152ad  add     eax, r12d
0x1400152b0  cmp     eax, r15d
0x1400152b3  jbe     short loc_140015291
0x1400152b5  lea     eax, [rdx-1]
0x1400152b8  mov     ecx, 0A4h
0x1400152bd  cmp     ax, cx
0x1400152c0  ja      short loc_1400152C5
0x1400152c2  inc     si
0x1400152c5  cmp     si, 4
0x1400152c9  jbe     short loc_140015348
0x1400152cb  lea     rax, [rbp+57h+var_70]
0x1400152cf  mov     [rsp+0B0h+Disposition], 0; Disposition
0x1400152d8  xorps   xmm0, xmm0
0x1400152db  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x1400152e3  xor     r9d, r9d; TitleIndex
0x1400152e6  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400152ea  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400152ee  mov     [rsp+0B0h+Class], 0; Class
0x1400152f7  mov     edx, 20019h; DesiredAccess
0x1400152fc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140015303  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140015307  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001530f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015314  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001531b  call    cs:__imp_ZwCreateKey
0x140015322  nop     dword ptr [rax+rax+00h]
0x140015327  mov     ebx, eax
0x140015329  test    eax, eax
0x14001532b  js      short loc_140015371
0x14001532d  cmp     word ptr [rbp+57h+var_70], r15w
0x140015332  jz      short loc_140015351
0x140015334  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140015338  call    cs:__imp_ZwClose
0x14001533f  nop     dword ptr [rax+rax+00h]
0x140015344  movzx   edx, word ptr [rbp+57h+var_70]
0x140015348  add     dx, r12w
0x14001534c  jmp     loc_140015279
0x140015351  mov     rax, [rbp+57h+KeyHandle]
0x140015355  mov     [rdi], rax
0x140015358  xor     ebx, ebx
0x14001535a  mov     eax, ebx
0x14001535c  add     rsp, 88h
0x140015363  pop     r15
0x140015365  pop     r12
0x140015367  pop     rdi
0x140015368  pop     rsi
0x140015369  pop     rbx
0x14001536a  pop     rbp
0x14001536b  retn
0x14001536d  test    ebx, ebx
0x14001536f  jns     short loc_140015358
0x140015371  mov     qword ptr [rdi], 0
0x140015378  jmp     short loc_14001535A
```
