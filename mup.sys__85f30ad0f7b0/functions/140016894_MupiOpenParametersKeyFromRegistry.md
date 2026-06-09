# MupiOpenParametersKeyFromRegistry

- ea: `0x140016894`
- end: `0x140016a2b`
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

- `0x140016894`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400169e5`
- `ntoskrnl!ZwClose` at `0x1400169e5`
- `ntoskrnl!ZwOpenKey` at `0x1400168de`
- `ntoskrnl!ZwOpenKey` at `0x1400168de`
- `ntoskrnl!ZwCreateKey` at `0x1400169c8`
- `ntoskrnl!ZwCreateKey` at `0x1400169c8`

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
0x140016894  push    rbp
0x140016896  push    rbx
0x140016897  push    rsi
0x140016898  push    rdi
0x140016899  push    r12
0x14001689b  push    r15
0x14001689d  lea     rbp, [rsp-2Fh]
0x1400168a2  sub     rsp, 88h
0x1400168a9  xor     eax, eax
0x1400168ab  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400168b3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1400168b7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400168bb  lea     rax, WPP_MAIN_CB.Queue+30h
0x1400168c2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400168ca  xorps   xmm0, xmm0
0x1400168cd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400168d1  mov     edx, 20019h; DesiredAccess
0x1400168d6  mov     rdi, rcx
0x1400168d9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400168de  call    cs:__imp_ZwOpenKey
0x1400168e5  nop     dword ptr [rax+rax+00h]
0x1400168ea  mov     ebx, eax
0x1400168ec  cmp     eax, 0C0000034h
0x1400168f1  jnz     loc_140016A1E
0x1400168f7  mov     ecx, cs:dword_140007132
0x1400168fd  xor     esi, esi
0x1400168ff  mov     rdx, cs:off_140007138; "\\Registry\\Machine\\System\\CurrentCon"...
0x140016906  mov     r15d, 84h
0x14001690c  mov     [rbp+57h+var_6E], ecx
0x14001690f  movzx   ecx, cs:word_140007136
0x140016916  mov     [rbp+57h+var_6A], cx
0x14001691a  lea     r12d, [rsi+2]
0x14001691e  xor     ecx, ecx
0x140016920  mov     [rbp+57h+var_68], rdx
0x140016924  mov     [rbp+57h+var_70], cx
0x140016928  cmp     cx, r15w
0x14001692c  ja      loc_140016A1E
0x140016932  mov     [rbp+57h+KeyHandle], 0
0x14001693a  jmp     short loc_140016951
0x14001693c  movzx   eax, cx
0x14001693f  shr     rax, 1
0x140016942  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x140016947  jz      short loc_14001695C
0x140016949  add     cx, r12w
0x14001694d  mov     [rbp+57h+var_70], cx
0x140016951  movzx   eax, cx
0x140016954  add     eax, r12d
0x140016957  cmp     eax, r15d
0x14001695a  jbe     short loc_14001693C
0x14001695c  lea     eax, [rcx-1]
0x14001695f  mov     r8d, 82h
0x140016965  cmp     ax, r8w
0x140016969  ja      short loc_14001696E
0x14001696b  inc     si
0x14001696e  cmp     si, 5
0x140016972  jbe     loc_1400169F9
0x140016978  lea     rax, [rbp+57h+var_70]
0x14001697c  mov     [rsp+0B0h+Disposition], 0; Disposition
0x140016985  xorps   xmm0, xmm0
0x140016988  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x140016990  xor     r9d, r9d; TitleIndex
0x140016993  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140016997  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14001699b  mov     [rsp+0B0h+Class], 0; Class
0x1400169a4  mov     edx, 20019h; DesiredAccess
0x1400169a9  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400169b0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1400169b4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400169bc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400169c1  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400169c8  call    cs:__imp_ZwCreateKey
0x1400169cf  nop     dword ptr [rax+rax+00h]
0x1400169d4  mov     ebx, eax
0x1400169d6  test    eax, eax
0x1400169d8  js      short loc_140016A22
0x1400169da  cmp     [rbp+57h+var_70], r15w
0x1400169df  jz      short loc_140016A02
0x1400169e1  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400169e5  call    cs:__imp_ZwClose
0x1400169ec  nop     dword ptr [rax+rax+00h]
0x1400169f1  mov     rdx, [rbp+57h+var_68]
0x1400169f5  movzx   ecx, [rbp+57h+var_70]
0x1400169f9  add     cx, r12w
0x1400169fd  jmp     loc_140016924
0x140016a02  mov     rax, [rbp+57h+KeyHandle]
0x140016a06  mov     [rdi], rax
0x140016a09  xor     ebx, ebx
0x140016a0b  mov     eax, ebx
0x140016a0d  add     rsp, 88h
0x140016a14  pop     r15
0x140016a16  pop     r12
0x140016a18  pop     rdi
0x140016a19  pop     rsi
0x140016a1a  pop     rbx
0x140016a1b  pop     rbp
0x140016a1c  retn
0x140016a1e  test    ebx, ebx
0x140016a20  jns     short loc_140016A09
0x140016a22  mov     qword ptr [rdi], 0
0x140016a29  jmp     short loc_140016A0B
```
