# NfsGetRegistryPath

- ea: `0x1400147f0`
- end: `0x14001495d`
- name: `NfsGetRegistryPath`
- size: `365`
- prototype: `__int64 __usercall@<rax>(PUNICODE_STRING Destination@<rcx>, PCUNICODE_STRING SourceString@<rdx>, PCWSTR@<r8>, __int64, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140038550`

## callees

- `0x1400147f0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400148bc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400148bc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014923`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140014923`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400148d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400148d5`
- `ntoskrnl!ExAllocatePool2` at `0x140014874`
- `ntoskrnl!ExAllocatePool2` at `0x140014874`

## pseudocode

```c
NTSTATUS __fastcall NfsGetRegistryPath(
        PUNICODE_STRING Destination,
        PCUNICODE_STRING SourceString,
        PCWSTR a3,
        int a4,
        _DWORD *a5,
        unsigned int a6)
{
  int v9; // r9d
  int v10; // r9d
  NTSTATUS result; // eax
  USHORT v12; // ax
  WCHAR *Pool2; // rax
  unsigned int v14; // eax
  NTSTATUS v15; // ebp
  PWSTR Buffer; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( a4 == 4 )
  {
    v14 = 4;
  }
  else
  {
    v9 = a4 - 1;
    if ( v9 )
    {
      v10 = v9 - 2;
      if ( !v10 )
      {
        if ( a6 < 4 || a6 == 0x80000000 )
          return -1073741789;
        if ( a6 != 4 )
          *a5 = -a6;
        goto LABEL_10;
      }
      if ( v10 != 4 )
        return -1073741811;
    }
    v14 = 16;
  }
  if ( a6 < v14 )
    return -1073741789;
LABEL_10:
  Destination->Length = 0;
  v12 = SourceString->Length + 512;
  Destination->MaximumLength = v12;
  Pool2 = (WCHAR *)ExAllocatePool2(258, v12, 1668507214);
  Destination->Buffer = Pool2;
  if ( !Pool2 )
    return -1073741823;
  v15 = 0;
  RtlCopyUnicodeString(Destination, SourceString);
  if ( !a3 )
    goto LABEL_21;
  RtlInitUnicodeString(&DestinationString, a3);
  if ( *a3 != 92 )
  {
    Buffer = Destination->Buffer;
    if ( Buffer[((unsigned __int64)Destination->Length >> 1) - 1] != 92 )
    {
      Buffer[(unsigned __int64)Destination->Length >> 1] = 92;
      Destination->Buffer[((unsigned __int64)Destination->Length >> 1) + 1] = 0;
      Destination->Length += 2;
    }
  }
  result = RtlAppendUnicodeStringToString(Destination, &DestinationString);
  v15 = result;
  if ( result >= 0 )
  {
LABEL_21:
    Destination->Buffer[(unsigned __int64)Destination->Length >> 1] = 0;
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x1400147f0  mov     [rsp+arg_8], rbx
0x1400147f5  mov     [rsp+arg_10], rsi
0x1400147fa  push    rdi
0x1400147fb  sub     rsp, 30h
0x1400147ff  xorps   xmm0, xmm0
0x140014802  mov     rdi, r8
0x140014805  mov     rsi, rdx
0x140014808  mov     rbx, rcx
0x14001480b  movups  xmmword ptr [rsp+38h+DestinationString.Length], xmm0
0x140014810  cmp     r9d, 4
0x140014814  jz      loc_14001489A
0x14001481a  sub     r9d, 1
0x14001481e  jz      short loc_140014893
0x140014820  sub     r9d, 2
0x140014824  jz      short loc_140014836
0x140014826  cmp     r9d, 4
0x14001482a  jz      short loc_140014893
0x14001482c  mov     eax, 0C000000Dh
0x140014831  jmp     loc_14001494C
0x140014836  mov     ecx, [rsp+38h+arg_28]
0x14001483a  cmp     ecx, 4
0x14001483d  jb      short loc_1400148A5
0x14001483f  cmp     ecx, 80000000h
0x140014845  jz      short loc_1400148A5
0x140014847  cmp     ecx, 4
0x14001484a  jz      short loc_140014855
0x14001484c  mov     rax, [rsp+38h+arg_20]
0x140014851  neg     ecx
0x140014853  mov     [rax], ecx
0x140014855  xor     eax, eax
0x140014857  mov     ecx, 102h
0x14001485c  mov     [rbx], ax
0x14001485f  mov     r8d, 6373664Eh
0x140014865  mov     eax, 200h
0x14001486a  add     ax, [rdx]
0x14001486d  movzx   edx, ax
0x140014870  mov     [rbx+2], dx
0x140014874  call    cs:__imp_ExAllocatePool2
0x14001487b  nop     dword ptr [rax+rax+00h]
0x140014880  mov     [rbx+8], rax
0x140014884  test    rax, rax
0x140014887  jnz     short loc_1400148AF
0x140014889  mov     eax, 0C0000001h
0x14001488e  jmp     loc_14001494C
0x140014893  mov     eax, 10h
0x140014898  jmp     short loc_14001489F
0x14001489a  mov     eax, 4
0x14001489f  cmp     [rsp+38h+arg_28], eax
0x1400148a3  jnb     short loc_140014855
0x1400148a5  mov     eax, 0C0000023h
0x1400148aa  jmp     loc_14001494C
0x1400148af  mov     [rsp+38h+arg_0], rbp
0x1400148b4  mov     rdx, rsi; SourceString
0x1400148b7  mov     rcx, rbx; DestinationString
0x1400148ba  xor     ebp, ebp
0x1400148bc  call    cs:__imp_RtlCopyUnicodeString
0x1400148c3  nop     dword ptr [rax+rax+00h]
0x1400148c8  test    rdi, rdi
0x1400148cb  jz      short loc_140014935
0x1400148cd  mov     rdx, rdi; SourceString
0x1400148d0  lea     rcx, [rsp+38h+DestinationString]; DestinationString
0x1400148d5  call    cs:__imp_RtlInitUnicodeString
0x1400148dc  nop     dword ptr [rax+rax+00h]
0x1400148e1  cmp     word ptr [rdi], 5Ch ; '\'
0x1400148e5  jz      short loc_14001491B
0x1400148e7  movzx   ecx, word ptr [rbx]
0x1400148ea  mov     rdx, [rbx+8]
0x1400148ee  mov     eax, ecx
0x1400148f0  shr     rax, 1
0x1400148f3  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x1400148f9  jz      short loc_14001491B
0x1400148fb  mov     eax, ecx
0x1400148fd  shr     rax, 1
0x140014900  mov     word ptr [rdx+rax*2], 5Ch ; '\'
0x140014906  xor     eax, eax
0x140014908  movzx   edx, word ptr [rbx]
0x14001490b  mov     rcx, [rbx+8]
0x14001490f  shr     rdx, 1
0x140014912  mov     [rcx+rdx*2+2], ax
0x140014917  add     word ptr [rbx], 2
0x14001491b  lea     rdx, [rsp+38h+DestinationString]; Source
0x140014920  mov     rcx, rbx; Destination
0x140014923  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001492a  nop     dword ptr [rax+rax+00h]
0x14001492f  mov     ebp, eax
0x140014931  test    eax, eax
0x140014933  js      short loc_140014947
0x140014935  movzx   edx, word ptr [rbx]
0x140014938  mov     rcx, [rbx+8]
0x14001493c  shr     rdx, 1
0x14001493f  xor     eax, eax
0x140014941  mov     [rcx+rdx*2], ax
0x140014945  mov     eax, ebp
0x140014947  mov     rbp, [rsp+38h+arg_0]
0x14001494c  mov     rbx, [rsp+38h+arg_8]
0x140014951  mov     rsi, [rsp+38h+arg_10]
0x140014956  add     rsp, 30h
0x14001495a  pop     rdi
0x14001495b  retn
```
