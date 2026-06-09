# AslpFileLargeMapCreate

- ea: `0x18001241c`
- end: `0x180012632`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011f2c`

## callees

- `0x18000e240`
- `0x18001241c`
- `0x180012638`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x180012553`
- `ntdll!ZwMapViewOfSection` at `0x1800125c7`
- `ntdll!ZwMapViewOfSection` at `0x180012553`
- `ntdll!ZwMapViewOfSection` at `0x1800125c7`
- `ntdll!ZwCreateSection` at `0x1800124d0`
- `ntdll!ZwCreateSection` at `0x1800124d0`
- `ntdll!RtlAllocateHeap` at `0x180012463`
- `ntdll!RtlAllocateHeap` at `0x180012463`

## string_xrefs

- `0x1800124dc`: `ZwCreateSection failed [%x]`
- `0x1800124e9`: `AslpFileLargeMapCreate`

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
0x18001241c  mov     [rsp-28h+arg_0], rbx
0x180012421  mov     [rsp-28h+arg_8], rsi
0x180012426  push    rbp
0x180012427  push    rdi
0x180012428  push    r13
0x18001242a  push    r14
0x18001242c  push    r15
0x18001242e  mov     rbp, rsp
0x180012431  sub     rsp, 80h
0x180012438  xorps   xmm0, xmm0
0x18001243b  mov     r15, rcx
0x18001243e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180012442  mov     r14, rdx
0x180012445  mov     edx, 8; Flags
0x18001244a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001244e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180012452  mov     rcx, gs:60h
0x18001245b  lea     r8d, [rdx+38h]; Size
0x18001245f  mov     rcx, [rcx+30h]; HeapHandle
0x180012463  call    cs:__imp_RtlAllocateHeap
0x180012469  mov     [rbp+arg_10], rax
0x18001246d  mov     rbx, rax
0x180012470  test    rax, rax
0x180012473  jnz     short loc_18001247F
0x180012475  mov     edi, 0C0000017h
0x18001247a  jmp     loc_180012606
0x18001247f  lea     rcx, [rax+8]; SectionHandle
0x180012483  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001248a  mov     rax, [r14]
0x18001248d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180012491  mov     [rsp+80h+FileHandle], rax; FileHandle
0x180012496  xorps   xmm0, xmm0
0x180012499  mov     r13d, 2
0x18001249f  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x1800124a7  xor     r9d, r9d; MaximumSize
0x1800124aa  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x1800124af  mov     edx, 0F0005h; DesiredAccess
0x1800124b4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800124bc  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800124c3  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800124cb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800124d0  call    cs:__imp_ZwCreateSection
0x1800124d6  mov     edi, eax
0x1800124d8  test    eax, eax
0x1800124da  jns     short loc_180012503
0x1800124dc  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x1800124e3  mov     r8d, 15Ah
0x1800124e9  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x1800124f0  mov     [rsp+80h+SectionPageProtection], eax
0x1800124f4  mov     ecx, 1
0x1800124f9  call    AslLogCallPrintf
0x1800124fe  jmp     loc_180012606
0x180012503  mov     rcx, [r14+10h]
0x180012507  lea     rdx, [rbx+38h]
0x18001250b  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180012510  lea     r8, [rbx+28h]; BaseAddress
0x180012514  add     rcx, 0FFFFFFFFFFFFF000h
0x18001251b  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180012523  movzx   eax, cx
0x180012526  xor     r9d, r9d; ZeroBits
0x180012529  sub     rcx, rax
0x18001252c  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180012531  mov     [rdx], rcx
0x180012534  lea     rax, [rbx+30h]
0x180012538  mov     rcx, [rbx+8]; SectionHandle
0x18001253c  mov     [rsp+80h+FileHandle], rax; ViewSize
0x180012541  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x180012546  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001254a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180012553  call    cs:__imp_ZwMapViewOfSection
0x180012559  mov     edi, eax
0x18001255b  test    eax, eax
0x18001255d  jns     short loc_180012571
0x18001255f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x180012566  mov     r8d, 176h
0x18001256c  jmp     loc_1800124E9
0x180012571  mov     rsi, [r14+10h]
0x180012575  mov     eax, 20000000h
0x18001257a  cmp     rsi, rax
0x18001257d  cmova   rsi, rax
0x180012581  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180012586  lea     rcx, [rbx+18h]
0x18001258a  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180012592  lea     rax, [rbx+20h]
0x180012596  mov     [rcx], rsi
0x180012599  lea     r8, [rbx+10h]; BaseAddress
0x18001259d  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x1800125a2  xor     r9d, r9d; ZeroBits
0x1800125a5  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x1800125aa  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800125ae  mov     qword ptr [rax], 0
0x1800125b5  mov     rcx, [rbx+8]; SectionHandle
0x1800125b9  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x1800125be  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1800125c7  call    cs:__imp_ZwMapViewOfSection
0x1800125cd  mov     edi, eax
0x1800125cf  cmp     eax, 0C0000017h
0x1800125d4  jnz     short loc_1800125E2
0x1800125d6  shr     rsi, 1
0x1800125d9  cmp     rsi, 100000h
0x1800125e0  jnb     short loc_180012581
0x1800125e2  test    eax, eax
0x1800125e4  jns     short loc_1800125F8
0x1800125e6  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x1800125ed  mov     r8d, 1A0h
0x1800125f3  jmp     loc_1800124E9
0x1800125f8  mov     [rbx], r14
0x1800125fb  mov     [r15], rbx
0x1800125fe  xor     ebx, ebx
0x180012600  mov     [rbp+arg_10], rbx
0x180012604  xor     edi, edi
0x180012606  test    rbx, rbx
0x180012609  jz      short loc_180012614
0x18001260b  lea     rcx, [rbp+arg_10]
0x18001260f  call    AslpFileLargeMapDelete
0x180012614  lea     r11, [rsp+80h+var_s0]
0x18001261c  mov     eax, edi
0x18001261e  mov     rbx, [r11+30h]
0x180012622  mov     rsi, [r11+38h]
0x180012626  mov     rsp, r11
0x180012629  pop     r15
0x18001262b  pop     r14
0x18001262d  pop     r13
0x18001262f  pop     rdi
0x180012630  pop     rbp
0x180012631  retn
```
