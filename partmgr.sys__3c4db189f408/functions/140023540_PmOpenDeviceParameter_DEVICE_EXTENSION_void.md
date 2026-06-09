# PmOpenDeviceParameter(_DEVICE_EXTENSION *,void * *)

- ea: `0x140023540`
- end: `0x140023663`
- name: `?PmOpenDeviceParameter@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAX@Z`
- size: `291`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, void **)`
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001fbdc`
- `0x14001fcbc`
- `0x14001fda0`
- `0x14002032c`
- `0x140023310`
- `0x140023394`

## callees

- `0x140023540`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14002361f`
- `ntoskrnl!ZwClose` at `0x140023655`
- `ntoskrnl!ZwClose` at `0x14002361f`
- `ntoskrnl!ZwClose` at `0x140023655`
- `ntoskrnl!ZwCreateKey` at `0x1400235ed`
- `ntoskrnl!ZwCreateKey` at `0x1400235ed`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140023582`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140023582`

## pseudocode

```c
NTSTATUS __fastcall PmOpenDeviceParameter(struct _DEVICE_EXTENSION *a1, void **a2)
{
  struct _DEVICE_OBJECT *v2; // rcx
  NTSTATUS result; // eax
  NTSTATUS v5; // ebx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  v2 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 3);
  *a2 = 0;
  Handle = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  result = IoOpenDeviceRegistryKey(v2, 1u, 0x20019u, &Handle);
  v5 = result;
  if ( result < 0 )
  {
    Handle = 0;
    if ( !KeyHandle )
      return result;
    ZwClose(KeyHandle);
  }
  else
  {
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.ObjectName = &Partmgr;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwCreateKey(&KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
    if ( v5 >= 0 )
      *a2 = KeyHandle;
    KeyHandle = 0;
  }
  if ( Handle )
    ZwClose(Handle);
  return v5;
}

```

## disassembly

```asm
0x140023540  mov     rax, rsp
0x140023543  mov     [rax+18h], rbx
0x140023547  mov     [rax+20h], rsi
0x14002354b  push    rdi
0x14002354c  sub     rsp, 70h
0x140023550  mov     rcx, [rcx+18h]; DeviceObject
0x140023554  lea     r9, [rax+10h]; DeviceRegKey
0x140023558  xorps   xmm0, xmm0
0x14002355b  xor     esi, esi
0x14002355d  mov     [rdx], rsi
0x140023560  mov     rdi, rdx
0x140023563  mov     edx, 1; DevInstKeyType
0x140023568  mov     [rax+10h], rsi
0x14002356c  mov     r8d, 20019h; DesiredAccess
0x140023572  mov     [rax+8], rsi
0x140023576  movups  xmmword ptr [rax-38h], xmm0
0x14002357a  movups  xmmword ptr [rax-28h], xmm0
0x14002357e  movups  xmmword ptr [rax-18h], xmm0
0x140023582  call    cs:__imp_IoOpenDeviceRegistryKey
0x140023589  nop     dword ptr [rax+rax+00h]
0x14002358e  mov     ebx, eax
0x140023590  test    eax, eax
0x140023592  js      loc_140023640
0x140023598  mov     rax, [rsp+78h+Handle]
0x1400235a0  lea     r8, [rsp+78h+ObjectAttributes]; ObjectAttributes
0x1400235a5  mov     [rsp+78h+ObjectAttributes.RootDirectory], rax
0x1400235aa  lea     rcx, [rsp+78h+KeyHandle]; KeyHandle
0x1400235b2  lea     rax, ?Partmgr@@3U_UNICODE_STRING@@A; _UNICODE_STRING Partmgr
0x1400235b9  mov     [rsp+78h+Disposition], rsi; Disposition
0x1400235be  xorps   xmm0, xmm0
0x1400235c1  mov     [rsp+78h+CreateOptions], esi; CreateOptions
0x1400235c5  xor     r9d, r9d; TitleIndex
0x1400235c8  mov     [rsp+78h+ObjectAttributes.ObjectName], rax
0x1400235cd  mov     edx, 2001Fh; DesiredAccess
0x1400235d2  mov     [rsp+78h+ObjectAttributes.Length], 30h ; '0'
0x1400235da  mov     [rsp+78h+ObjectAttributes.Attributes], 240h
0x1400235e2  movdqu  xmmword ptr [rsp+78h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400235e8  mov     [rsp+78h+Class], rsi; Class
0x1400235ed  call    cs:__imp_ZwCreateKey
0x1400235f4  nop     dword ptr [rax+rax+00h]
0x1400235f9  mov     ebx, eax
0x1400235fb  test    eax, eax
0x1400235fd  js      short loc_14002360A
0x1400235ff  mov     rax, [rsp+78h+KeyHandle]
0x140023607  mov     [rdi], rax
0x14002360a  mov     [rsp+78h+KeyHandle], rsi
0x140023612  mov     rcx, [rsp+78h+Handle]; Handle
0x14002361a  test    rcx, rcx
0x14002361d  jz      short loc_14002362B
0x14002361f  call    cs:__imp_ZwClose
0x140023626  nop     dword ptr [rax+rax+00h]
0x14002362b  mov     eax, ebx
0x14002362d  lea     r11, [rsp+78h+var_8]
0x140023632  mov     rbx, [r11+20h]
0x140023636  mov     rsi, [r11+28h]
0x14002363a  mov     rsp, r11
0x14002363d  pop     rdi
0x14002363e  retn
0x140023640  mov     [rsp+78h+Handle], rsi
0x140023648  mov     rcx, [rsp+78h+KeyHandle]; Handle
0x140023650  test    rcx, rcx
0x140023653  jz      short loc_14002362D
0x140023655  call    cs:__imp_ZwClose
0x14002365c  nop     dword ptr [rax+rax+00h]
0x140023661  jmp     short loc_140023612
```
