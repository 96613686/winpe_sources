# AslpFileLargeMapCreate

- ea: `0x18001f0c8`
- end: `0x18001f2de`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ebd8`

## callees

- `0x1800152d0`
- `0x18001f0c8`
- `0x18001f2e4`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x18001f17c`
- `ntdll!ZwCreateSection` at `0x18001f17c`
- `ntdll!RtlAllocateHeap` at `0x18001f10f`
- `ntdll!RtlAllocateHeap` at `0x18001f10f`
- `ntdll!ZwMapViewOfSection` at `0x18001f1ff`
- `ntdll!ZwMapViewOfSection` at `0x18001f273`
- `ntdll!ZwMapViewOfSection` at `0x18001f1ff`
- `ntdll!ZwMapViewOfSection` at `0x18001f273`

## string_xrefs

- `0x18001f188`: `ZwCreateSection failed [%x]`
- `0x18001f195`: `AslpFileLargeMapCreate`

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
0x18001f0c8  mov     [rsp-28h+arg_0], rbx
0x18001f0cd  mov     [rsp-28h+arg_8], rsi
0x18001f0d2  push    rbp
0x18001f0d3  push    rdi
0x18001f0d4  push    r13
0x18001f0d6  push    r14
0x18001f0d8  push    r15
0x18001f0da  mov     rbp, rsp
0x18001f0dd  sub     rsp, 80h
0x18001f0e4  xorps   xmm0, xmm0
0x18001f0e7  mov     r15, rcx
0x18001f0ea  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001f0ee  mov     r14, rdx
0x18001f0f1  mov     edx, 8; Flags
0x18001f0f6  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001f0fa  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001f0fe  mov     rcx, gs:60h
0x18001f107  lea     r8d, [rdx+38h]; Size
0x18001f10b  mov     rcx, [rcx+30h]; HeapHandle
0x18001f10f  call    cs:__imp_RtlAllocateHeap
0x18001f115  mov     [rbp+arg_10], rax
0x18001f119  mov     rbx, rax
0x18001f11c  test    rax, rax
0x18001f11f  jnz     short loc_18001F12B
0x18001f121  mov     edi, 0C0000017h
0x18001f126  jmp     loc_18001F2B2
0x18001f12b  lea     rcx, [rax+8]; SectionHandle
0x18001f12f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001f136  mov     rax, [r14]
0x18001f139  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001f13d  mov     [rsp+80h+FileHandle], rax; FileHandle
0x18001f142  xorps   xmm0, xmm0
0x18001f145  mov     r13d, 2
0x18001f14b  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x18001f153  xor     r9d, r9d; MaximumSize
0x18001f156  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18001f15b  mov     edx, 0F0005h; DesiredAccess
0x18001f160  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18001f168  mov     [rbp+ObjectAttributes.Attributes], 0
0x18001f16f  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18001f177  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001f17c  call    cs:__imp_ZwCreateSection
0x18001f182  mov     edi, eax
0x18001f184  test    eax, eax
0x18001f186  jns     short loc_18001F1AF
0x18001f188  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x18001f18f  mov     r8d, 15Ah
0x18001f195  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x18001f19c  mov     [rsp+80h+SectionPageProtection], eax
0x18001f1a0  mov     ecx, 1
0x18001f1a5  call    AslLogCallPrintf
0x18001f1aa  jmp     loc_18001F2B2
0x18001f1af  mov     rcx, [r14+10h]
0x18001f1b3  lea     rdx, [rbx+38h]
0x18001f1b7  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18001f1bc  lea     r8, [rbx+28h]; BaseAddress
0x18001f1c0  add     rcx, 0FFFFFFFFFFFFF000h
0x18001f1c7  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18001f1cf  movzx   eax, cx
0x18001f1d2  xor     r9d, r9d; ZeroBits
0x18001f1d5  sub     rcx, rax
0x18001f1d8  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18001f1dd  mov     [rdx], rcx
0x18001f1e0  lea     rax, [rbx+30h]
0x18001f1e4  mov     rcx, [rbx+8]; SectionHandle
0x18001f1e8  mov     [rsp+80h+FileHandle], rax; ViewSize
0x18001f1ed  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x18001f1f2  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001f1f6  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18001f1ff  call    cs:__imp_ZwMapViewOfSection
0x18001f205  mov     edi, eax
0x18001f207  test    eax, eax
0x18001f209  jns     short loc_18001F21D
0x18001f20b  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x18001f212  mov     r8d, 176h
0x18001f218  jmp     loc_18001F195
0x18001f21d  mov     rsi, [r14+10h]
0x18001f221  mov     eax, 20000000h
0x18001f226  cmp     rsi, rax
0x18001f229  cmova   rsi, rax
0x18001f22d  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18001f232  lea     rcx, [rbx+18h]
0x18001f236  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18001f23e  lea     rax, [rbx+20h]
0x18001f242  mov     [rcx], rsi
0x18001f245  lea     r8, [rbx+10h]; BaseAddress
0x18001f249  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18001f24e  xor     r9d, r9d; ZeroBits
0x18001f251  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18001f256  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001f25a  mov     qword ptr [rax], 0
0x18001f261  mov     rcx, [rbx+8]; SectionHandle
0x18001f265  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18001f26a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18001f273  call    cs:__imp_ZwMapViewOfSection
0x18001f279  mov     edi, eax
0x18001f27b  cmp     eax, 0C0000017h
0x18001f280  jnz     short loc_18001F28E
0x18001f282  shr     rsi, 1
0x18001f285  cmp     rsi, 100000h
0x18001f28c  jnb     short loc_18001F22D
0x18001f28e  test    eax, eax
0x18001f290  jns     short loc_18001F2A4
0x18001f292  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18001f299  mov     r8d, 1A0h
0x18001f29f  jmp     loc_18001F195
0x18001f2a4  mov     [rbx], r14
0x18001f2a7  mov     [r15], rbx
0x18001f2aa  xor     ebx, ebx
0x18001f2ac  mov     [rbp+arg_10], rbx
0x18001f2b0  xor     edi, edi
0x18001f2b2  test    rbx, rbx
0x18001f2b5  jz      short loc_18001F2C0
0x18001f2b7  lea     rcx, [rbp+arg_10]
0x18001f2bb  call    AslpFileLargeMapDelete
0x18001f2c0  lea     r11, [rsp+80h+var_s0]
0x18001f2c8  mov     eax, edi
0x18001f2ca  mov     rbx, [r11+30h]
0x18001f2ce  mov     rsi, [r11+38h]
0x18001f2d2  mov     rsp, r11
0x18001f2d5  pop     r15
0x18001f2d7  pop     r14
0x18001f2d9  pop     r13
0x18001f2db  pop     rdi
0x18001f2dc  pop     rbp
0x18001f2dd  retn
```
