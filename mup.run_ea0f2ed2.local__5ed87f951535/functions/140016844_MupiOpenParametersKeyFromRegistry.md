# MupiOpenParametersKeyFromRegistry

- ea: `0x140016844`
- end: `0x1400169db`
- name: `MupiOpenParametersKeyFromRegistry`
- size: `407`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400045d0`
- `0x1400046c0`
- `0x1400048f0`

## callees

- `0x140016844`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140016995`
- `ntoskrnl!ZwClose` at `0x140016995`
- `ntoskrnl!ZwOpenKey` at `0x14001688e`
- `ntoskrnl!ZwOpenKey` at `0x14001688e`
- `ntoskrnl!ZwCreateKey` at `0x140016978`
- `ntoskrnl!ZwCreateKey` at `0x140016978`

## pseudocode

```c
__int64 __fastcall MupiOpenParametersKeyFromRegistry(void **a1)
{
  NTSTATUS v2; // ebx
  unsigned __int16 v3; // si
  const wchar_t *v4; // rdx
  unsigned __int16 v5; // cx
  unsigned __int16 v7; // [rsp+40h] [rbp-19h] BYREF
  int v8; // [rsp+42h] [rbp-17h]
  __int16 v9; // [rsp+46h] [rbp-13h]
  const wchar_t *v10; // [rsp+48h] [rbp-11h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *KeyHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&WPP_MAIN_CB.Queue.Wcb.DeviceObject;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenKey(a1, 0x20019u, &ObjectAttributes);
  if ( v2 == -1073741772 )
  {
    v3 = 0;
    v4 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Mup\\Parameters";
    v8 = 134;
    v9 = 0;
    v5 = 0;
    v10 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Mup\\Parameters";
    while ( 1 )
    {
      v7 = v5;
      if ( v5 > 0x84u )
        break;
      KeyHandle = 0;
      while ( (unsigned int)v5 + 2 <= 0x84 && v4[(unsigned __int64)v5 >> 1] != 92 )
      {
        v5 += 2;
        v7 = v5;
      }
      if ( (unsigned __int16)(v5 - 1) <= 0x82u )
        ++v3;
      if ( v3 > 5u )
      {
        ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        ObjectAttributes.Attributes = 576;
        v2 = ZwCreateKey(&KeyHandle, 0x20019u, &ObjectAttributes, 0, 0, 0, 0);
        if ( v2 < 0 )
          goto LABEL_19;
        if ( v7 == 132 )
        {
          *a1 = KeyHandle;
          return 0;
        }
        ZwClose(KeyHandle);
        v4 = v10;
        v5 = v7;
      }
      v5 += 2;
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
0x140016844  push    rbp
0x140016846  push    rbx
0x140016847  push    rsi
0x140016848  push    rdi
0x140016849  push    r12
0x14001684b  push    r15
0x14001684d  lea     rbp, [rsp-2Fh]
0x140016852  sub     rsp, 88h
0x140016859  xor     eax, eax
0x14001685b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016863  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140016867  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001686b  lea     rax, WPP_MAIN_CB.Queue+30h
0x140016872  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14001687a  xorps   xmm0, xmm0
0x14001687d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016881  mov     edx, 20019h; DesiredAccess
0x140016886  mov     rdi, rcx
0x140016889  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001688e  call    cs:__imp_ZwOpenKey
0x140016895  nop     dword ptr [rax+rax+00h]
0x14001689a  mov     ebx, eax
0x14001689c  cmp     eax, 0C0000034h
0x1400168a1  jnz     loc_1400169CE
0x1400168a7  mov     ecx, cs:dword_140007132
0x1400168ad  xor     esi, esi
0x1400168af  mov     rdx, cs:off_140007138; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400168b6  mov     r15d, 84h
0x1400168bc  mov     [rbp+57h+var_6E], ecx
0x1400168bf  movzx   ecx, cs:word_140007136
0x1400168c6  mov     [rbp+57h+var_6A], cx
0x1400168ca  lea     r12d, [rsi+2]
0x1400168ce  xor     ecx, ecx
0x1400168d0  mov     [rbp+57h+var_68], rdx
0x1400168d4  mov     [rbp+57h+var_70], cx
0x1400168d8  cmp     cx, r15w
0x1400168dc  ja      loc_1400169CE
0x1400168e2  mov     [rbp+57h+KeyHandle], 0
0x1400168ea  jmp     short loc_140016901
0x1400168ec  movzx   eax, cx
0x1400168ef  shr     rax, 1
0x1400168f2  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1400168f7  jz      short loc_14001690C
0x1400168f9  add     cx, r12w
0x1400168fd  mov     [rbp+57h+var_70], cx
0x140016901  movzx   eax, cx
0x140016904  add     eax, r12d
0x140016907  cmp     eax, r15d
0x14001690a  jbe     short loc_1400168EC
0x14001690c  lea     eax, [rcx-1]
0x14001690f  mov     r8d, 82h
0x140016915  cmp     ax, r8w
0x140016919  ja      short loc_14001691E
0x14001691b  inc     si
0x14001691e  cmp     si, 5
0x140016922  jbe     loc_1400169A9
0x140016928  lea     rax, [rbp+57h+var_70]
0x14001692c  mov     [rsp+0B0h+Disposition], 0; Disposition
0x140016935  xorps   xmm0, xmm0
0x140016938  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140016940  xor     r9d, r9d; TitleIndex
0x140016943  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016947  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001694b  mov     [rsp+0B0h+Class], 0; Class
0x140016954  mov     edx, 20019h; DesiredAccess
0x140016959  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140016960  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140016964  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14001696c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016971  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140016978  call    cs:__imp_ZwCreateKey
0x14001697f  nop     dword ptr [rax+rax+00h]
0x140016984  mov     ebx, eax
0x140016986  test    eax, eax
0x140016988  js      short loc_1400169D2
0x14001698a  cmp     [rbp+57h+var_70], r15w
0x14001698f  jz      short loc_1400169B2
0x140016991  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140016995  call    cs:__imp_ZwClose
0x14001699c  nop     dword ptr [rax+rax+00h]
0x1400169a1  mov     rdx, [rbp+57h+var_68]
0x1400169a5  movzx   ecx, [rbp+57h+var_70]
0x1400169a9  add     cx, r12w
0x1400169ad  jmp     loc_1400168D4
0x1400169b2  mov     rax, [rbp+57h+KeyHandle]
0x1400169b6  mov     [rdi], rax
0x1400169b9  xor     ebx, ebx
0x1400169bb  mov     eax, ebx
0x1400169bd  add     rsp, 88h
0x1400169c4  pop     r15
0x1400169c6  pop     r12
0x1400169c8  pop     rdi
0x1400169c9  pop     rsi
0x1400169ca  pop     rbx
0x1400169cb  pop     rbp
0x1400169cc  retn
0x1400169ce  test    ebx, ebx
0x1400169d0  jns     short loc_1400169B9
0x1400169d2  mov     qword ptr [rdi], 0
0x1400169d9  jmp     short loc_1400169BB
```
