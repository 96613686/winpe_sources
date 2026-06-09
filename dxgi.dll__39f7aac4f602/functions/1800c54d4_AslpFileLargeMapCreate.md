# AslpFileLargeMapCreate

- ea: `0x1800c54d4`
- end: `0x1800c56ea`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c4f60`

## callees

- `0x18004281c`
- `0x1800c54d4`
- `0x1800c56f0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800c551b`
- `ntdll!RtlAllocateHeap` at `0x1800c551b`
- `ntdll!ZwCreateSection` at `0x1800c5588`
- `ntdll!ZwCreateSection` at `0x1800c5588`
- `ntdll!ZwMapViewOfSection` at `0x1800c560b`
- `ntdll!ZwMapViewOfSection` at `0x1800c567f`
- `ntdll!ZwMapViewOfSection` at `0x1800c560b`
- `ntdll!ZwMapViewOfSection` at `0x1800c567f`

## string_xrefs

- `0x1800c5594`: `ZwCreateSection failed [%x]`
- `0x1800c55a1`: `AslpFileLargeMapCreate`

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
0x1800c54d4  mov     [rsp-28h+arg_0], rbx
0x1800c54d9  mov     [rsp-28h+arg_8], rsi
0x1800c54de  push    rbp
0x1800c54df  push    rdi
0x1800c54e0  push    r13
0x1800c54e2  push    r14
0x1800c54e4  push    r15
0x1800c54e6  mov     rbp, rsp
0x1800c54e9  sub     rsp, 80h
0x1800c54f0  xorps   xmm0, xmm0
0x1800c54f3  mov     r15, rcx
0x1800c54f6  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800c54fa  mov     r14, rdx
0x1800c54fd  mov     edx, 8; Flags
0x1800c5502  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800c5506  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c550a  mov     rcx, gs:60h
0x1800c5513  lea     r8d, [rdx+38h]; Size
0x1800c5517  mov     rcx, [rcx+30h]; HeapHandle
0x1800c551b  call    cs:__imp_RtlAllocateHeap
0x1800c5521  mov     [rbp+arg_10], rax
0x1800c5525  mov     rbx, rax
0x1800c5528  test    rax, rax
0x1800c552b  jnz     short loc_1800C5537
0x1800c552d  mov     edi, 0C0000017h
0x1800c5532  jmp     loc_1800C56BE
0x1800c5537  lea     rcx, [rax+8]; SectionHandle
0x1800c553b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800c5542  mov     rax, [r14]
0x1800c5545  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800c5549  mov     [rsp+80h+FileHandle], rax; FileHandle
0x1800c554e  xorps   xmm0, xmm0
0x1800c5551  mov     r13d, 2
0x1800c5557  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x1800c555f  xor     r9d, r9d; MaximumSize
0x1800c5562  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x1800c5567  mov     edx, 0F0005h; DesiredAccess
0x1800c556c  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800c5574  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800c557b  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800c5583  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800c5588  call    cs:__imp_ZwCreateSection
0x1800c558e  mov     edi, eax
0x1800c5590  test    eax, eax
0x1800c5592  jns     short loc_1800C55BB
0x1800c5594  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x1800c559b  mov     r8d, 15Ah
0x1800c55a1  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x1800c55a8  mov     [rsp+80h+SectionPageProtection], eax
0x1800c55ac  mov     ecx, 1
0x1800c55b1  call    AslLogCallPrintf
0x1800c55b6  jmp     loc_1800C56BE
0x1800c55bb  mov     rcx, [r14+10h]
0x1800c55bf  lea     rdx, [rbx+38h]
0x1800c55c3  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1800c55c8  lea     r8, [rbx+28h]; BaseAddress
0x1800c55cc  add     rcx, 0FFFFFFFFFFFFF000h
0x1800c55d3  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x1800c55db  movzx   eax, cx
0x1800c55de  xor     r9d, r9d; ZeroBits
0x1800c55e1  sub     rcx, rax
0x1800c55e4  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x1800c55e9  mov     [rdx], rcx
0x1800c55ec  lea     rax, [rbx+30h]
0x1800c55f0  mov     rcx, [rbx+8]; SectionHandle
0x1800c55f4  mov     [rsp+80h+FileHandle], rax; ViewSize
0x1800c55f9  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x1800c55fe  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800c5602  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1800c560b  call    cs:__imp_ZwMapViewOfSection
0x1800c5611  mov     edi, eax
0x1800c5613  test    eax, eax
0x1800c5615  jns     short loc_1800C5629
0x1800c5617  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x1800c561e  mov     r8d, 176h
0x1800c5624  jmp     loc_1800C55A1
0x1800c5629  mov     rsi, [r14+10h]
0x1800c562d  mov     eax, 20000000h
0x1800c5632  cmp     rsi, rax
0x1800c5635  cmova   rsi, rax
0x1800c5639  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1800c563e  lea     rcx, [rbx+18h]
0x1800c5642  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x1800c564a  lea     rax, [rbx+20h]
0x1800c564e  mov     [rcx], rsi
0x1800c5651  lea     r8, [rbx+10h]; BaseAddress
0x1800c5655  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x1800c565a  xor     r9d, r9d; ZeroBits
0x1800c565d  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x1800c5662  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800c5666  mov     qword ptr [rax], 0
0x1800c566d  mov     rcx, [rbx+8]; SectionHandle
0x1800c5671  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x1800c5676  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1800c567f  call    cs:__imp_ZwMapViewOfSection
0x1800c5685  mov     edi, eax
0x1800c5687  cmp     eax, 0C0000017h
0x1800c568c  jnz     short loc_1800C569A
0x1800c568e  shr     rsi, 1
0x1800c5691  cmp     rsi, 100000h
0x1800c5698  jnb     short loc_1800C5639
0x1800c569a  test    eax, eax
0x1800c569c  jns     short loc_1800C56B0
0x1800c569e  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x1800c56a5  mov     r8d, 1A0h
0x1800c56ab  jmp     loc_1800C55A1
0x1800c56b0  mov     [rbx], r14
0x1800c56b3  mov     [r15], rbx
0x1800c56b6  xor     ebx, ebx
0x1800c56b8  mov     [rbp+arg_10], rbx
0x1800c56bc  xor     edi, edi
0x1800c56be  test    rbx, rbx
0x1800c56c1  jz      short loc_1800C56CC
0x1800c56c3  lea     rcx, [rbp+arg_10]
0x1800c56c7  call    AslpFileLargeMapDelete
0x1800c56cc  lea     r11, [rsp+80h+var_s0]
0x1800c56d4  mov     eax, edi
0x1800c56d6  mov     rbx, [r11+30h]
0x1800c56da  mov     rsi, [r11+38h]
0x1800c56de  mov     rsp, r11
0x1800c56e1  pop     r15
0x1800c56e3  pop     r14
0x1800c56e5  pop     r13
0x1800c56e7  pop     rdi
0x1800c56e8  pop     rbp
0x1800c56e9  retn
```
