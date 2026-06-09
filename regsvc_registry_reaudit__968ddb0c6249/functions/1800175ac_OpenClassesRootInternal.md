# OpenClassesRootInternal

- ea: `0x1800175ac`
- end: `0x180017681`
- name: `OpenClassesRootInternal`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a2d0`

## callees

- `0x1800173cc`
- `0x1800175ac`
- `0x18001d38c`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001767a`
- `ntdll!RtlFreeHeap` at `0x18001765e`
- `ntdll!RtlFreeHeap` at `0x18001765e`

## pseudocode

```c
ULONG __fastcall OpenClassesRootInternal(__int64 a1, ACCESS_MASK a2, void **a3)
{
  int inited; // eax
  int v6; // r9d
  PVOID v7; // rbx
  NTSTATUS v8; // edi
  int v10; // [rsp+30h] [rbp-40h]
  __int128 v11; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v12; // [rsp+50h] [rbp-20h]
  int v13; // [rsp+58h] [rbp-18h]
  int v14; // [rsp+5Ch] [rbp-14h]
  PVOID v15; // [rsp+60h] [rbp-10h]
  __int64 v16; // [rsp+68h] [rbp-8h]
  PVOID P; // [rsp+A8h] [rbp+38h] BYREF

  P = 0;
  DWORD1(v11) = 0;
  v14 = 0;
  inited = InitSecurityAcls(&P);
  v7 = P;
  v8 = inited;
  if ( inited >= 0 )
  {
    v12 = L"DD";
    LODWORD(v11) = 48;
    *((_QWORD *)&v11 + 1) = 0;
    v13 = 64;
    v15 = P;
    v16 = 0;
    v8 = Wow64NtCreateKey(a3, a2, &v11, v6, 0, 0, v10, 0);
  }
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  return RtlNtStatusToDosError(v8);
}

```

## disassembly

```asm
0x1800175ac  mov     [rsp-18h+arg_0], rbx
0x1800175b1  mov     [rsp-18h+arg_8], rsi
0x1800175b6  mov     [rsp-18h+P], r9
0x1800175bb  push    rbp
0x1800175bc  push    rdi
0x1800175bd  push    r14
0x1800175bf  mov     rbp, rsp
0x1800175c2  sub     rsp, 70h
0x1800175c6  xor     eax, eax
0x1800175c8  mov     [rbp+P], 0
0x1800175d0  lea     rcx, [rbp+P]
0x1800175d4  mov     [rbp+var_2C], eax
0x1800175d7  mov     [rbp+var_14], eax
0x1800175da  mov     rsi, r8
0x1800175dd  mov     r14d, edx
0x1800175e0  call    InitSecurityAcls
0x1800175e5  mov     rbx, [rbp+P]
0x1800175e9  mov     edi, eax
0x1800175eb  test    eax, eax
0x1800175ed  js      short loc_180017647
0x1800175ef  lea     rax, ClassesStringKey; "DD"
0x1800175f6  mov     [rsp+70h+var_38], 0
0x1800175ff  mov     [rsp+70h+var_48], 0
0x180017607  lea     r8, [rbp+var_30]
0x18001760b  mov     edx, r14d
0x18001760e  mov     [rbp+var_20], rax
0x180017612  mov     rcx, rsi
0x180017615  mov     [rsp+70h+var_50], 0
0x18001761e  mov     [rbp+var_30], 30h ; '0'
0x180017625  mov     [rbp+var_28], 0
0x18001762d  mov     [rbp+var_18], 40h ; '@'
0x180017634  mov     [rbp+var_10], rbx
0x180017638  mov     [rbp+var_8], 0
0x180017640  call    Wow64NtCreateKey
0x180017645  mov     edi, eax
0x180017647  test    rbx, rbx
0x18001764a  jz      short loc_180017664
0x18001764c  mov     rcx, gs:60h
0x180017655  mov     r8, rbx; P
0x180017658  xor     edx, edx; Flags
0x18001765a  mov     rcx, [rcx+30h]; HeapHandle
0x18001765e  call    cs:__imp_RtlFreeHeap
0x180017664  mov     ecx, edi
0x180017666  lea     r11, [rsp+70h+var_s0]
0x18001766b  mov     rbx, [r11+20h]
0x18001766f  mov     rsi, [r11+28h]
0x180017673  mov     rsp, r11
0x180017676  pop     r14
0x180017678  pop     rdi
0x180017679  pop     rbp
0x18001767a  jmp     cs:__imp_RtlNtStatusToDosError
```
