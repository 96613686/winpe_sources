# AslpFileLargeMapCreate

- ea: `0x18007373c`
- end: `0x180073952`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007324c`

## callees

- `0x180066c10`
- `0x18007373c`
- `0x180073958`

## import_xrefs

- `ntdll!ZwMapViewOfSection` at `0x180073873`
- `ntdll!ZwMapViewOfSection` at `0x1800738e7`
- `ntdll!ZwMapViewOfSection` at `0x180073873`
- `ntdll!ZwMapViewOfSection` at `0x1800738e7`
- `ntdll!ZwCreateSection` at `0x1800737f0`
- `ntdll!ZwCreateSection` at `0x1800737f0`
- `ntdll!RtlAllocateHeap` at `0x180073783`
- `ntdll!RtlAllocateHeap` at `0x180073783`

## string_xrefs

- `0x1800737fc`: `ZwCreateSection failed [%x]`
- `0x180073809`: `AslpFileLargeMapCreate`

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
0x18007373c  mov     [rsp-28h+arg_0], rbx
0x180073741  mov     [rsp-28h+arg_8], rsi
0x180073746  push    rbp
0x180073747  push    rdi
0x180073748  push    r13
0x18007374a  push    r14
0x18007374c  push    r15
0x18007374e  mov     rbp, rsp
0x180073751  sub     rsp, 80h
0x180073758  xorps   xmm0, xmm0
0x18007375b  mov     r15, rcx
0x18007375e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180073762  mov     r14, rdx
0x180073765  mov     edx, 8; Flags
0x18007376a  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18007376e  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180073772  mov     rcx, gs:60h
0x18007377b  lea     r8d, [rdx+38h]; Size
0x18007377f  mov     rcx, [rcx+30h]; HeapHandle
0x180073783  call    cs:__imp_RtlAllocateHeap
0x180073789  mov     [rbp+arg_10], rax
0x18007378d  mov     rbx, rax
0x180073790  test    rax, rax
0x180073793  jnz     short loc_18007379F
0x180073795  mov     edi, 0C0000017h
0x18007379a  jmp     loc_180073926
0x18007379f  lea     rcx, [rax+8]; SectionHandle
0x1800737a3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800737aa  mov     rax, [r14]
0x1800737ad  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800737b1  mov     [rsp+80h+FileHandle], rax; FileHandle
0x1800737b6  xorps   xmm0, xmm0
0x1800737b9  mov     r13d, 2
0x1800737bf  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x1800737c7  xor     r9d, r9d; MaximumSize
0x1800737ca  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x1800737cf  mov     edx, 0F0005h; DesiredAccess
0x1800737d4  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800737dc  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800737e3  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1800737eb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800737f0  call    cs:__imp_ZwCreateSection
0x1800737f6  mov     edi, eax
0x1800737f8  test    eax, eax
0x1800737fa  jns     short loc_180073823
0x1800737fc  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x180073803  mov     r8d, 15Ah
0x180073809  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x180073810  mov     [rsp+80h+SectionPageProtection], eax
0x180073814  mov     ecx, 1
0x180073819  call    AslLogCallPrintf
0x18007381e  jmp     loc_180073926
0x180073823  mov     rcx, [r14+10h]
0x180073827  lea     rdx, [rbx+38h]
0x18007382b  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180073830  lea     r8, [rbx+28h]; BaseAddress
0x180073834  add     rcx, 0FFFFFFFFFFFFF000h
0x18007383b  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180073843  movzx   eax, cx
0x180073846  xor     r9d, r9d; ZeroBits
0x180073849  sub     rcx, rax
0x18007384c  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180073851  mov     [rdx], rcx
0x180073854  lea     rax, [rbx+30h]
0x180073858  mov     rcx, [rbx+8]; SectionHandle
0x18007385c  mov     [rsp+80h+FileHandle], rax; ViewSize
0x180073861  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x180073866  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007386a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180073873  call    cs:__imp_ZwMapViewOfSection
0x180073879  mov     edi, eax
0x18007387b  test    eax, eax
0x18007387d  jns     short loc_180073891
0x18007387f  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x180073886  mov     r8d, 176h
0x18007388c  jmp     loc_180073809
0x180073891  mov     rsi, [r14+10h]
0x180073895  mov     eax, 20000000h
0x18007389a  cmp     rsi, rax
0x18007389d  cmova   rsi, rax
0x1800738a1  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x1800738a6  lea     rcx, [rbx+18h]
0x1800738aa  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x1800738b2  lea     rax, [rbx+20h]
0x1800738b6  mov     [rcx], rsi
0x1800738b9  lea     r8, [rbx+10h]; BaseAddress
0x1800738bd  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x1800738c2  xor     r9d, r9d; ZeroBits
0x1800738c5  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x1800738ca  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800738ce  mov     qword ptr [rax], 0
0x1800738d5  mov     rcx, [rbx+8]; SectionHandle
0x1800738d9  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x1800738de  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x1800738e7  call    cs:__imp_ZwMapViewOfSection
0x1800738ed  mov     edi, eax
0x1800738ef  cmp     eax, 0C0000017h
0x1800738f4  jnz     short loc_180073902
0x1800738f6  shr     rsi, 1
0x1800738f9  cmp     rsi, 100000h
0x180073900  jnb     short loc_1800738A1
0x180073902  test    eax, eax
0x180073904  jns     short loc_180073918
0x180073906  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x18007390d  mov     r8d, 1A0h
0x180073913  jmp     loc_180073809
0x180073918  mov     [rbx], r14
0x18007391b  mov     [r15], rbx
0x18007391e  xor     ebx, ebx
0x180073920  mov     [rbp+arg_10], rbx
0x180073924  xor     edi, edi
0x180073926  test    rbx, rbx
0x180073929  jz      short loc_180073934
0x18007392b  lea     rcx, [rbp+arg_10]
0x18007392f  call    AslpFileLargeMapDelete
0x180073934  lea     r11, [rsp+80h+var_s0]
0x18007393c  mov     eax, edi
0x18007393e  mov     rbx, [r11+30h]
0x180073942  mov     rsi, [r11+38h]
0x180073946  mov     rsp, r11
0x180073949  pop     r15
0x18007394b  pop     r14
0x18007394d  pop     r13
0x18007394f  pop     rdi
0x180073950  pop     rbp
0x180073951  retn
```
