# CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(uint)

- ea: `0x1800136ec`
- end: `0x18001376c`
- name: `??_G?$CGenericTableMap@_KVCProxySurfaceElement@@@@QEAAPEAXI@Z`
- size: `128`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180002e90`
- `0x1800056c8`
- `0x1800061c0`

## callees

- `0x18000d470`
- `0x1800136ec`

## import_xrefs

- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18001374d`
- `ntdll!RtlEnumerateGenericTableWithoutSplaying` at `0x18001374d`
- `ntdll!RtlDeleteElementGenericTable` at `0x180013724`
- `ntdll!RtlDeleteElementGenericTable` at `0x180013724`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180013736`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x180013736`

## pseudocode

```c
struct _RTL_GENERIC_TABLE *__fastcall CGenericTableMap<unsigned __int64,CProxySurfaceElement>::`scalar deleting destructor'(
        struct _RTL_GENERIC_TABLE *a1)
{
  struct _RTL_GENERIC_TABLE *i; // rbx
  _QWORD *v2; // rax
  _QWORD Buffer[3]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v5; // [rsp+38h] [rbp-20h]
  char v6; // [rsp+48h] [rbp-10h]
  PVOID RestartKey; // [rsp+60h] [rbp+8h] BYREF

  for ( i = a1; ; a1 = i )
  {
    RestartKey = 0;
    v2 = RtlEnumerateGenericTableWithoutSplaying(a1, &RestartKey);
    if ( !v2 )
      break;
    Buffer[0] = *v2;
    v5 = 0;
    Buffer[1] = 0;
    Buffer[2] = 0;
    v6 = 0;
    if ( !RtlDeleteElementGenericTable(i, Buffer) )
      RaiseFailFastException(0, 0, 1u);
  }
  operator delete(i, 0x48u);
  return i;
}

```

## disassembly

```asm
0x1800136ec  push    rbx
0x1800136ee  sub     rsp, 50h
0x1800136f2  mov     rbx, rcx
0x1800136f5  jmp     short loc_18001373F
0x1800136f7  mov     rax, [rax]
0x1800136fa  lea     rdx, [rsp+58h+Buffer]; Buffer
0x1800136ff  xorps   xmm0, xmm0
0x180013702  mov     [rsp+58h+Buffer], rax
0x180013707  movdqu  [rsp+58h+var_20], xmm0
0x18001370d  mov     [rsp+58h+var_30], 0
0x180013716  mov     [rsp+58h+var_28], 0
0x18001371f  mov     [rsp+58h+var_10], 0
0x180013724  call    cs:__imp_RtlDeleteElementGenericTable
0x18001372a  test    al, al
0x18001372c  jnz     short loc_18001373C
0x18001372e  xor     edx, edx; pContextRecord
0x180013730  xor     ecx, ecx; pExceptionRecord
0x180013732  lea     r8d, [rdx+1]; dwFlags
0x180013736  call    cs:__imp_RaiseFailFastException
0x18001373c  mov     rcx, rbx; Table
0x18001373f  lea     rdx, [rsp+58h+RestartKey]; RestartKey
0x180013744  mov     [rsp+58h+RestartKey], 0
0x18001374d  call    cs:__imp_RtlEnumerateGenericTableWithoutSplaying
0x180013753  mov     rcx, rbx; void *
0x180013756  test    rax, rax
0x180013759  jnz     short loc_1800136F7
0x18001375b  lea     edx, [rax+48h]; unsigned __int64
0x18001375e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013763  mov     rax, rbx
0x180013766  add     rsp, 50h
0x18001376a  pop     rbx
0x18001376b  retn
```
