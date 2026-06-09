# AslpFileLargeMapCreate

- ea: `0x140011180`
- end: `0x140011396`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: `__int64 __fastcall(void ***, HANDLE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140010c90`

## callees

- `0x140007074`
- `0x140011180`
- `0x14001139c`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x1400112b7`
- `ntdll!ZwMapViewOfSection` at `0x14001132b`
- `ntdll!ZwMapViewOfSection` at `0x1400112b7`
- `ntdll!ZwMapViewOfSection` at `0x14001132b`
- `ntdll!ZwCreateSection` at `0x140011234`
- `ntdll!ZwCreateSection` at `0x140011234`
- `ntdll!RtlAllocateHeap` at `0x1400111c7`
- `ntdll!RtlAllocateHeap` at `0x1400111c7`

## string_xrefs

- `0x140011240`: `ZwCreateSection failed [%x]`
- `0x14001124d`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(void ***a1, HANDLE *a2)
{
  void **Heap; // rax
  void **v5; // rbx
  unsigned int v6; // edi
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // rsi
  ULONG SectionPageProtection[2]; // [rsp+20h] [rbp-60h]
  HANDLE FileHandle; // [rsp+30h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void **v15; // [rsp+C0h] [rbp+40h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v15 = Heap;
  v5 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    goto LABEL_15;
  }
  ObjectAttributes.Length = 48;
  FileHandle = *a2;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = ZwCreateSection(Heap + 1, 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwCreateSection failed [%x]";
    v9 = 346;
LABEL_5:
    SectionPageProtection[0] = v7;
    AslLogCallPrintf(1, "AslpFileLargeMapCreate", v9, v8, *(_QWORD *)SectionPageProtection);
    goto LABEL_15;
  }
  v5[7] = (char *)a2[2] - (unsigned __int16)((unsigned __int16)a2[2] - 4096) - 4096;
  v7 = ZwMapViewOfSection(
         v5[1],
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         v5 + 5,
         0,
         0,
         (PLARGE_INTEGER)v5 + 7,
         (PSIZE_T)v5 + 6,
         ViewUnmap,
         0x500000u,
         2u);
  v6 = v7;
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v9 = 374;
    goto LABEL_5;
  }
  v10 = (unsigned __int64)a2[2];
  if ( v10 > 0x20000000 )
    v10 = 0x20000000;
  do
  {
    v5[3] = (void *)v10;
    v5[4] = 0;
    v7 = ZwMapViewOfSection(
           v5[1],
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           v5 + 2,
           0,
           0,
           (PLARGE_INTEGER)v5 + 4,
           (PSIZE_T)v5 + 3,
           ViewUnmap,
           0x500000u,
           2u);
    v6 = v7;
    if ( v7 != -1073741801 )
      break;
    v10 >>= 1;
  }
  while ( v10 >= 0x100000 );
  if ( v7 < 0 )
  {
    v8 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v9 = 416;
    goto LABEL_5;
  }
  *v5 = a2;
  *a1 = v5;
  v5 = 0;
  v15 = 0;
  v6 = 0;
LABEL_15:
  if ( v5 )
    AslpFileLargeMapDelete(&v15);
  return v6;
}

```

## disassembly

```asm
0x140011180  mov     [rsp-28h+arg_0], rbx
0x140011185  mov     [rsp-28h+arg_8], rsi
0x14001118a  push    rbp
0x14001118b  push    rdi
0x14001118c  push    r13
0x14001118e  push    r14
0x140011190  push    r15
0x140011192  mov     rbp, rsp
0x140011195  sub     rsp, 80h
0x14001119c  xorps   xmm0, xmm0
0x14001119f  mov     r15, rcx
0x1400111a2  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400111a6  mov     r14, rdx
0x1400111a9  mov     edx, 8; Flags
0x1400111ae  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400111b2  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400111b6  mov     rcx, gs:60h
0x1400111bf  lea     r8d, [rdx+38h]; Size
0x1400111c3  mov     rcx, [rcx+30h]; HeapHandle
0x1400111c7  call    cs:__imp_RtlAllocateHeap
0x1400111cd  mov     [rbp+arg_10], rax
0x1400111d1  mov     rbx, rax
0x1400111d4  test    rax, rax
0x1400111d7  jnz     short loc_1400111E3
0x1400111d9  mov     edi, 0C0000017h
0x1400111de  jmp     loc_14001136A
0x1400111e3  lea     rcx, [rax+8]; SectionHandle
0x1400111e7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400111ee  mov     rax, [r14]
0x1400111f1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400111f5  mov     [rsp+80h+FileHandle], rax; FileHandle
0x1400111fa  xorps   xmm0, xmm0
0x1400111fd  mov     r13d, 2
0x140011203  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x14001120b  xor     r9d, r9d; MaximumSize
0x14001120e  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x140011213  mov     edx, 0F0005h; DesiredAccess
0x140011218  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140011220  mov     [rbp+ObjectAttributes.Attributes], 0
0x140011227  mov     [rbp+ObjectAttributes.ObjectName], 0
0x14001122f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140011234  call    cs:__imp_ZwCreateSection
0x14001123a  mov     edi, eax
0x14001123c  test    eax, eax
0x14001123e  jns     short loc_140011267
0x140011240  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x140011247  mov     r8d, 15Ah
0x14001124d  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140011254  mov     [rsp+80h+SectionPageProtection], eax
0x140011258  mov     ecx, 1
0x14001125d  call    AslLogCallPrintf
0x140011262  jmp     loc_14001136A
0x140011267  mov     rcx, [r14+10h]
0x14001126b  lea     rdx, [rbx+38h]
0x14001126f  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x140011274  lea     r8, [rbx+28h]; BaseAddress
0x140011278  add     rcx, 0FFFFFFFFFFFFF000h
0x14001127f  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x140011287  movzx   eax, cx
0x14001128a  xor     r9d, r9d; ZeroBits
0x14001128d  sub     rcx, rax
0x140011290  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x140011295  mov     [rdx], rcx
0x140011298  lea     rax, [rbx+30h]
0x14001129c  mov     rcx, [rbx+8]; SectionHandle
0x1400112a0  mov     [rsp+80h+FileHandle], rax; ViewSize
0x1400112a5  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x1400112aa  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400112ae  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1400112b7  call    cs:__imp_ZwMapViewOfSection
0x1400112bd  mov     edi, eax
0x1400112bf  test    eax, eax
0x1400112c1  jns     short loc_1400112D5
0x1400112c3  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x1400112ca  mov     r8d, 176h
0x1400112d0  jmp     loc_14001124D
0x1400112d5  mov     rsi, [r14+10h]
0x1400112d9  mov     eax, 20000000h
0x1400112de  cmp     rsi, rax
0x1400112e1  cmova   rsi, rax
0x1400112e5  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1400112ea  lea     rcx, [rbx+18h]
0x1400112ee  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x1400112f6  lea     rax, [rbx+20h]
0x1400112fa  mov     [rcx], rsi
0x1400112fd  lea     r8, [rbx+10h]; BaseAddress
0x140011301  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x140011306  xor     r9d, r9d; ZeroBits
0x140011309  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x14001130e  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140011312  mov     qword ptr [rax], 0
0x140011319  mov     rcx, [rbx+8]; SectionHandle
0x14001131d  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x140011322  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x14001132b  call    cs:__imp_ZwMapViewOfSection
0x140011331  mov     edi, eax
0x140011333  cmp     eax, 0C0000017h
0x140011338  jnz     short loc_140011346
0x14001133a  shr     rsi, 1
0x14001133d  cmp     rsi, 100000h
0x140011344  jnb     short loc_1400112E5
0x140011346  test    eax, eax
0x140011348  jns     short loc_14001135C
0x14001134a  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x140011351  mov     r8d, 1A0h
0x140011357  jmp     loc_14001124D
0x14001135c  mov     [rbx], r14
0x14001135f  mov     [r15], rbx
0x140011362  xor     ebx, ebx
0x140011364  mov     [rbp+arg_10], rbx
0x140011368  xor     edi, edi
0x14001136a  test    rbx, rbx
0x14001136d  jz      short loc_140011378
0x14001136f  lea     rcx, [rbp+arg_10]
0x140011373  call    AslpFileLargeMapDelete
0x140011378  lea     r11, [rsp+80h+var_s0]
0x140011380  mov     eax, edi
0x140011382  mov     rbx, [r11+30h]
0x140011386  mov     rsi, [r11+38h]
0x14001138a  mov     rsp, r11
0x14001138d  pop     r15
0x14001138f  pop     r14
0x140011391  pop     r13
0x140011393  pop     rdi
0x140011394  pop     rbp
0x140011395  retn
```
