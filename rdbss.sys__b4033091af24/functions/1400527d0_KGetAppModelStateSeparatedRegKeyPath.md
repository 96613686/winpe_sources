# KGetAppModelStateSeparatedRegKeyPath

- ea: `0x1400527d0`
- end: `0x1400528f6`
- name: `KGetAppModelStateSeparatedRegKeyPath`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x140052a74`

## callees

- `0x1400527d0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140052860`
- `ntoskrnl!ExAllocatePool2` at `0x140052860`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400528d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400528d4`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005282a`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400528a2`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x14005282a`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1400528a2`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400528ba`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400528ba`

## string_xrefs

- `0x14005280f`: `TargetNtPath`
- `0x140052888`: `TargetNtPath`

## pseudocode

```c
__int64 __fastcall KGetAppModelStateSeparatedRegKeyPath(__int64 a1, __int64 a2, UNICODE_STRING *a3)
{
  NTSTATUS inited; // ebx
  int PersistedStateLocation; // eax
  void *Pool2; // rdi
  unsigned int v10; // [rsp+70h] [rbp+18h] BYREF

  v10 = 0;
  if ( a3 )
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(a1, L"TargetNtPath", a2, 0, 0, 0, &v10);
    inited = PersistedStateLocation;
    if ( PersistedStateLocation < 0 )
    {
      if ( PersistedStateLocation == -2147483643 )
      {
        Pool2 = (void *)ExAllocatePool2(256, v10, 1299214401);
        if ( Pool2 )
        {
          inited = RtlGetPersistedStateLocation(a1, L"TargetNtPath", a2, 0, Pool2, v10, &v10);
          if ( inited < 0 || (inited = RtlInitUnicodeStringEx(a3, (PCWSTR)Pool2), inited < 0) )
            ExFreePoolWithTag(Pool2, 0x4D707041u);
        }
        else
        {
          return (unsigned int)-1073741670;
        }
      }
    }
    else
    {
      return (unsigned int)-1073741823;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400527d0  mov     [rsp+arg_0], rbx
0x1400527d5  mov     [rsp+arg_8], rbp
0x1400527da  push    rsi
0x1400527db  push    rdi
0x1400527dc  push    r14
0x1400527de  sub     rsp, 40h
0x1400527e2  mov     [rsp+58h+arg_10], 0
0x1400527ea  mov     rsi, r8
0x1400527ed  mov     rbp, rdx
0x1400527f0  mov     r14, rcx
0x1400527f3  test    r8, r8
0x1400527f6  jnz     short loc_140052802
0x1400527f8  mov     ebx, 0C000000Dh
0x1400527fd  jmp     loc_1400528E0
0x140052802  lea     rax, [rsp+58h+arg_10]
0x140052807  xor     r9d, r9d
0x14005280a  mov     [rsp+58h+var_28], rax
0x14005280f  lea     rdx, aTargetntpath; "TargetNtPath"
0x140052816  mov     [rsp+58h+var_30], 0
0x14005281e  mov     r8, rbp
0x140052821  mov     [rsp+58h+var_38], 0
0x14005282a  call    cs:__imp_RtlGetPersistedStateLocation
0x140052831  nop     dword ptr [rax+rax+00h]
0x140052836  mov     ebx, eax
0x140052838  test    eax, eax
0x14005283a  js      short loc_140052846
0x14005283c  mov     ebx, 0C0000001h
0x140052841  jmp     loc_1400528E0
0x140052846  cmp     eax, 80000005h
0x14005284b  jnz     loc_1400528E0
0x140052851  mov     edx, [rsp+58h+arg_10]
0x140052855  mov     ecx, 100h
0x14005285a  mov     r8d, 4D707041h
0x140052860  call    cs:__imp_ExAllocatePool2
0x140052867  nop     dword ptr [rax+rax+00h]
0x14005286c  mov     rdi, rax
0x14005286f  test    rax, rax
0x140052872  jnz     short loc_14005287B
0x140052874  mov     ebx, 0C000009Ah
0x140052879  jmp     short loc_1400528E0
0x14005287b  lea     rax, [rsp+58h+arg_10]
0x140052880  xor     r9d, r9d
0x140052883  mov     [rsp+58h+var_28], rax
0x140052888  lea     rdx, aTargetntpath; "TargetNtPath"
0x14005288f  mov     eax, [rsp+58h+arg_10]
0x140052893  mov     r8, rbp
0x140052896  mov     [rsp+58h+var_30], eax
0x14005289a  mov     rcx, r14
0x14005289d  mov     [rsp+58h+var_38], rdi
0x1400528a2  call    cs:__imp_RtlGetPersistedStateLocation
0x1400528a9  nop     dword ptr [rax+rax+00h]
0x1400528ae  mov     ebx, eax
0x1400528b0  test    eax, eax
0x1400528b2  js      short loc_1400528CC
0x1400528b4  mov     rdx, rdi; SourceString
0x1400528b7  mov     rcx, rsi; DestinationString
0x1400528ba  call    cs:__imp_RtlInitUnicodeStringEx
0x1400528c1  nop     dword ptr [rax+rax+00h]
0x1400528c6  mov     ebx, eax
0x1400528c8  test    eax, eax
0x1400528ca  jns     short loc_1400528E0
0x1400528cc  mov     edx, 4D707041h; Tag
0x1400528d1  mov     rcx, rdi; P
0x1400528d4  call    cs:__imp_ExFreePoolWithTag
0x1400528db  nop     dword ptr [rax+rax+00h]
0x1400528e0  mov     rbp, [rsp+58h+arg_8]
0x1400528e5  mov     eax, ebx
0x1400528e7  mov     rbx, [rsp+58h+arg_0]
0x1400528ec  add     rsp, 40h
0x1400528f0  pop     r14
0x1400528f2  pop     rdi
0x1400528f3  pop     rsi
0x1400528f4  retn
```
