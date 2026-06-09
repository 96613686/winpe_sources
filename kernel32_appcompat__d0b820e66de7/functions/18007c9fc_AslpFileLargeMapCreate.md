# AslpFileLargeMapCreate

- ea: `0x18007c9fc`
- end: `0x18007cc2b`
- name: `AslpFileLargeMapCreate`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007c864`

## callees

- `0x18001f138`
- `0x18007c9fc`
- `0x18007cc34`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x18007cab6`
- `ntdll!ZwCreateSection` at `0x18007cab6`
- `ntdll!ZwMapViewOfSection` at `0x18007cb3f`
- `ntdll!ZwMapViewOfSection` at `0x18007cbb9`
- `ntdll!ZwMapViewOfSection` at `0x18007cb3f`
- `ntdll!ZwMapViewOfSection` at `0x18007cbb9`
- `ntdll!RtlAllocateHeap` at `0x18007ca43`
- `ntdll!RtlAllocateHeap` at `0x18007ca43`

## string_xrefs

- `0x18007cac8`: `ZwCreateSection failed [%x]`
- `0x18007cad5`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(void ***a1, HANDLE *a2)
{
  void **Heap; // rax
  void **v5; // rbx
  NTSTATUS v6; // edi
  const char *v7; // r9
  int v8; // r8d
  unsigned __int64 v9; // rsi
  NTSTATUS v10; // eax
  HANDLE FileHandle; // [rsp+30h] [rbp-50h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void **v14; // [rsp+C0h] [rbp+40h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Heap = (void **)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x40u);
  v14 = Heap;
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
  v6 = ZwCreateSection(Heap + 1, 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  if ( v6 < 0 )
  {
    v7 = "ZwCreateSection failed [%x]";
    v8 = 346;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"AslpFileLargeMapCreate", v8, (_DWORD)v7);
    goto LABEL_15;
  }
  v5[7] = (char *)a2[2] - (unsigned __int16)((unsigned __int16)a2[2] - 4096) - 4096;
  v6 = ZwMapViewOfSection(
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
  if ( v6 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v8 = 374;
    goto LABEL_5;
  }
  v9 = (unsigned __int64)a2[2];
  if ( v9 > 0x20000000 )
    v9 = 0x20000000;
  do
  {
    v5[3] = (void *)v9;
    v5[4] = 0;
    v10 = ZwMapViewOfSection(
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
    v6 = v10;
    if ( v10 != -1073741801 )
      break;
    v9 >>= 1;
  }
  while ( v9 >= 0x100000 );
  if ( v10 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v8 = 416;
    goto LABEL_5;
  }
  *v5 = a2;
  *a1 = v5;
  v5 = 0;
  v14 = 0;
  v6 = 0;
LABEL_15:
  if ( v5 )
    AslpFileLargeMapDelete(&v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007c9fc  mov     [rsp-28h+arg_0], rbx
0x18007ca01  mov     [rsp-28h+arg_8], rsi
0x18007ca06  push    rbp
0x18007ca07  push    rdi
0x18007ca08  push    r13
0x18007ca0a  push    r14
0x18007ca0c  push    r15
0x18007ca0e  mov     rbp, rsp
0x18007ca11  sub     rsp, 80h
0x18007ca18  xorps   xmm0, xmm0
0x18007ca1b  mov     r15, rcx
0x18007ca1e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18007ca22  mov     r14, rdx
0x18007ca25  mov     edx, 8; Flags
0x18007ca2a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007ca2e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007ca32  mov     rcx, gs:60h
0x18007ca3b  lea     r8d, [rdx+38h]; Size
0x18007ca3f  mov     rcx, [rcx+30h]; HeapHandle
0x18007ca43  call    cs:__imp_RtlAllocateHeap
0x18007ca4a  nop     dword ptr [rax+rax+00h]
0x18007ca4f  mov     [rbp+arg_10], rax
0x18007ca53  mov     rbx, rax
0x18007ca56  test    rax, rax
0x18007ca59  jnz     short loc_18007CA65
0x18007ca5b  mov     edi, 0C0000017h
0x18007ca60  jmp     loc_18007CBFE
0x18007ca65  lea     rcx, [rax+8]; SectionHandle
0x18007ca69  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18007ca70  mov     rax, [r14]
0x18007ca73  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18007ca77  mov     [rsp+80h+FileHandle], rax; FileHandle
0x18007ca7c  xorps   xmm0, xmm0
0x18007ca7f  mov     r13d, 2
0x18007ca85  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x18007ca8d  xor     r9d, r9d; MaximumSize
0x18007ca90  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x18007ca95  mov     edx, 0F0005h; DesiredAccess
0x18007ca9a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18007caa2  mov     [rbp+ObjectAttributes.Attributes], 0
0x18007caa9  mov     [rbp+ObjectAttributes.ObjectName], 0
0x18007cab1  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18007cab6  call    cs:__imp_ZwCreateSection
0x18007cabd  nop     dword ptr [rax+rax+00h]
0x18007cac2  mov     edi, eax
0x18007cac4  test    eax, eax
0x18007cac6  jns     short loc_18007CAEF
0x18007cac8  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x18007cacf  mov     r8d, 15Ah
0x18007cad5  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x18007cadc  mov     [rsp+80h+SectionPageProtection], eax
0x18007cae0  mov     ecx, 1
0x18007cae5  call    AslLogCallPrintf
0x18007caea  jmp     loc_18007CBFE
0x18007caef  mov     rcx, [r14+10h]
0x18007caf3  lea     rdx, [rbx+38h]
0x18007caf7  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18007cafc  lea     r8, [rbx+28h]; BaseAddress
0x18007cb00  add     rcx, 0FFFFFFFFFFFFF000h
0x18007cb07  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18007cb0f  movzx   eax, cx
0x18007cb12  xor     r9d, r9d; ZeroBits
0x18007cb15  sub     rcx, rax
0x18007cb18  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18007cb1d  mov     [rdx], rcx
0x18007cb20  lea     rax, [rbx+30h]
0x18007cb24  mov     rcx, [rbx+8]; SectionHandle
0x18007cb28  mov     [rsp+80h+FileHandle], rax; ViewSize
0x18007cb2d  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x18007cb32  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007cb36  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18007cb3f  call    cs:__imp_ZwMapViewOfSection
0x18007cb46  nop     dword ptr [rax+rax+00h]
0x18007cb4b  mov     edi, eax
0x18007cb4d  test    eax, eax
0x18007cb4f  jns     short loc_18007CB63
0x18007cb51  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x18007cb58  mov     r8d, 176h
0x18007cb5e  jmp     loc_18007CAD5
0x18007cb63  mov     rsi, [r14+10h]
0x18007cb67  mov     eax, 20000000h
0x18007cb6c  cmp     rsi, rax
0x18007cb6f  cmova   rsi, rax
0x18007cb73  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x18007cb78  lea     rcx, [rbx+18h]
0x18007cb7c  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x18007cb84  lea     rax, [rbx+20h]
0x18007cb88  mov     [rcx], rsi
0x18007cb8b  lea     r8, [rbx+10h]; BaseAddress
0x18007cb8f  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x18007cb94  xor     r9d, r9d; ZeroBits
0x18007cb97  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x18007cb9c  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007cba0  mov     qword ptr [rax], 0
0x18007cba7  mov     rcx, [rbx+8]; SectionHandle
0x18007cbab  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x18007cbb0  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x18007cbb9  call    cs:__imp_ZwMapViewOfSection
0x18007cbc0  nop     dword ptr [rax+rax+00h]
0x18007cbc5  mov     edi, eax
0x18007cbc7  cmp     eax, 0C0000017h
0x18007cbcc  jnz     short loc_18007CBDA
0x18007cbce  shr     rsi, 1
0x18007cbd1  cmp     rsi, 100000h
0x18007cbd8  jnb     short loc_18007CB73
0x18007cbda  test    eax, eax
0x18007cbdc  jns     short loc_18007CBF0
0x18007cbde  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18007cbe5  mov     r8d, 1A0h
0x18007cbeb  jmp     loc_18007CAD5
0x18007cbf0  mov     [rbx], r14
0x18007cbf3  mov     [r15], rbx
0x18007cbf6  xor     ebx, ebx
0x18007cbf8  mov     [rbp+arg_10], rbx
0x18007cbfc  xor     edi, edi
0x18007cbfe  test    rbx, rbx
0x18007cc01  jz      short loc_18007CC0C
0x18007cc03  lea     rcx, [rbp+arg_10]
0x18007cc07  call    AslpFileLargeMapDelete
0x18007cc0c  lea     r11, [rsp+80h+var_s0]
0x18007cc14  mov     eax, edi
0x18007cc16  mov     rbx, [r11+30h]
0x18007cc1a  mov     rsi, [r11+38h]
0x18007cc1e  mov     rsp, r11
0x18007cc21  pop     r15
0x18007cc23  pop     r14
0x18007cc25  pop     r13
0x18007cc27  pop     rdi
0x18007cc28  pop     rbp
0x18007cc29  retn
```
