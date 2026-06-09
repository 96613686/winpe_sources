# PcwpReferenceObjectByHandle_PCW_QUERY_

- ea: `0x140009828`
- end: `0x1400098b0`
- name: `PcwpReferenceObjectByHandle_PCW_QUERY_`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140009d40`
- `0x14000a040`
- `0x14000a580`
- `0x14000a920`

## callees

- `0x140009828`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140009850`
- `ntoskrnl!ObfDereferenceObject` at `0x140009850`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009883`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140009883`

## pseudocode

```c
NTSTATUS __fastcall PcwpReferenceObjectByHandle_PCW_QUERY_(void **a1, void *a2, ACCESS_MASK a3)
{
  struct _OBJECT_TYPE *v3; // rbp
  void *v5; // rcx
  NTSTATUS result; // eax
  _DWORD *v9; // rcx
  PVOID Object; // [rsp+60h] [rbp+8h] BYREF

  v3 = PcwObjectType;
  v5 = *a1;
  *a1 = 0;
  if ( v5 )
    ObfDereferenceObject(v5);
  Object = 0;
  result = ObReferenceObjectByHandle(a2, a3, v3, 1, &Object, 0);
  v9 = Object;
  *a1 = Object;
  if ( result >= 0 )
  {
    if ( *v9 )
      return -1073741788;
  }
  return result;
}

```

## disassembly

```asm
0x140009828  push    rbx
0x14000982a  push    rbp
0x14000982b  push    rsi
0x14000982c  push    rdi
0x14000982d  sub     rsp, 38h
0x140009831  mov     rbp, cs:?PcwObjectType@@3PEAU_OBJECT_TYPE@@EA; _OBJECT_TYPE * PcwObjectType
0x140009838  mov     rbx, rcx
0x14000983b  mov     rcx, [rcx]; Object
0x14000983e  mov     edi, r8d
0x140009841  mov     rsi, rdx
0x140009844  mov     qword ptr [rbx], 0
0x14000984b  test    rcx, rcx
0x14000984e  jz      short loc_14000985C
0x140009850  call    cs:__imp_ObfDereferenceObject
0x140009857  nop     dword ptr [rax+rax+00h]
0x14000985c  lea     rax, [rsp+58h+arg_0]
0x140009861  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x14000986a  mov     r9b, 1; AccessMode
0x14000986d  mov     [rsp+58h+Object], rax; Object
0x140009872  mov     r8, rbp; ObjectType
0x140009875  mov     [rsp+58h+arg_0], 0
0x14000987e  mov     edx, edi; DesiredAccess
0x140009880  mov     rcx, rsi; Handle
0x140009883  call    cs:__imp_ObReferenceObjectByHandle
0x14000988a  nop     dword ptr [rax+rax+00h]
0x14000988f  mov     rcx, [rsp+58h+arg_0]
0x140009894  mov     [rbx], rcx
0x140009897  test    eax, eax
0x140009899  js      short loc_1400098A6
0x14000989b  cmp     dword ptr [rcx], 0
0x14000989e  mov     edx, 0C0000024h
0x1400098a3  cmovnz  eax, edx
0x1400098a6  add     rsp, 38h
0x1400098aa  pop     rdi
0x1400098ab  pop     rsi
0x1400098ac  pop     rbp
0x1400098ad  pop     rbx
0x1400098ae  retn
```
