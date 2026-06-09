# MupiOpenUncHardeningRegistryKey

- ea: `0x14001524c`
- end: `0x1400153ca`
- name: `MupiOpenUncHardeningRegistryKey`
- size: `382`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140014bc0`
- `0x140014ef0`
- `0x140015430`

## callees

- `0x14001524c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140015388`
- `ntoskrnl!ZwClose` at `0x140015388`
- `ntoskrnl!ZwOpenKey` at `0x140015296`
- `ntoskrnl!ZwOpenKey` at `0x140015296`
- `ntoskrnl!ZwCreateKey` at `0x14001536b`
- `ntoskrnl!ZwCreateKey` at `0x14001536b`

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
0x14001524c  push    rbp
0x14001524e  push    rbx
0x14001524f  push    rsi
0x140015250  push    rdi
0x140015251  push    r12
0x140015253  push    r15
0x140015255  lea     rbp, [rsp-2Fh]
0x14001525a  sub     rsp, 88h
0x140015261  xor     eax, eax
0x140015263  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14001526b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x14001526f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140015273  lea     rax, MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH
0x14001527a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x140015282  xorps   xmm0, xmm0
0x140015285  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140015289  mov     edx, 20019h; DesiredAccess
0x14001528e  mov     rdi, rcx
0x140015291  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015296  call    cs:__imp_ZwOpenKey
0x14001529d  nop     dword ptr [rax+rax+00h]
0x1400152a2  mov     ebx, eax
0x1400152a4  cmp     eax, 0C0000034h
0x1400152a9  jnz     loc_1400153BD
0x1400152af  movups  xmm0, xmmword ptr cs:MUPI_HARDENED_PATHS_REGISTRY_KEY_PATH
0x1400152b6  xor     esi, esi
0x1400152b8  mov     r15d, 0A6h
0x1400152be  xor     edx, edx
0x1400152c0  movdqu  [rbp+57h+var_70], xmm0
0x1400152c5  lea     r12d, [rsi+2]
0x1400152c9  mov     word ptr [rbp+57h+var_70], dx
0x1400152cd  cmp     dx, r15w
0x1400152d1  ja      loc_1400153BD
0x1400152d7  mov     [rbp+57h+KeyHandle], 0
0x1400152df  jmp     short loc_1400152FA
0x1400152e1  mov     rax, qword ptr [rbp+57h+var_70+8]
0x1400152e5  movzx   ecx, dx
0x1400152e8  shr     rcx, 1
0x1400152eb  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x1400152f0  jz      short loc_140015305
0x1400152f2  add     dx, r12w
0x1400152f6  mov     word ptr [rbp+57h+var_70], dx
0x1400152fa  movzx   eax, dx
0x1400152fd  add     eax, r12d
0x140015300  cmp     eax, r15d
0x140015303  jbe     short loc_1400152E1
0x140015305  lea     eax, [rdx-1]
0x140015308  mov     ecx, 0A4h
0x14001530d  cmp     ax, cx
0x140015310  ja      short loc_140015315
0x140015312  inc     si
0x140015315  cmp     si, 4
0x140015319  jbe     short loc_140015398
0x14001531b  lea     rax, [rbp+57h+var_70]
0x14001531f  mov     [rsp+0B0h+Disposition], 0; Disposition
0x140015328  xorps   xmm0, xmm0
0x14001532b  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140015333  xor     r9d, r9d; TitleIndex
0x140015336  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14001533a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001533e  mov     [rsp+0B0h+Class], 0; Class
0x140015347  mov     edx, 20019h; DesiredAccess
0x14001534c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140015353  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140015357  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001535f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140015364  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001536b  call    cs:__imp_ZwCreateKey
0x140015372  nop     dword ptr [rax+rax+00h]
0x140015377  mov     ebx, eax
0x140015379  test    eax, eax
0x14001537b  js      short loc_1400153C1
0x14001537d  cmp     word ptr [rbp+57h+var_70], r15w
0x140015382  jz      short loc_1400153A1
0x140015384  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140015388  call    cs:__imp_ZwClose
0x14001538f  nop     dword ptr [rax+rax+00h]
0x140015394  movzx   edx, word ptr [rbp+57h+var_70]
0x140015398  add     dx, r12w
0x14001539c  jmp     loc_1400152C9
0x1400153a1  mov     rax, [rbp+57h+KeyHandle]
0x1400153a5  mov     [rdi], rax
0x1400153a8  xor     ebx, ebx
0x1400153aa  mov     eax, ebx
0x1400153ac  add     rsp, 88h
0x1400153b3  pop     r15
0x1400153b5  pop     r12
0x1400153b7  pop     rdi
0x1400153b8  pop     rsi
0x1400153b9  pop     rbx
0x1400153ba  pop     rbp
0x1400153bb  retn
0x1400153bd  test    ebx, ebx
0x1400153bf  jns     short loc_1400153A8
0x1400153c1  mov     qword ptr [rdi], 0
0x1400153c8  jmp     short loc_1400153AA
```
