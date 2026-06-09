# AslpFileLargeMapCreate

- ea: `0x180074cd8`
- end: `0x180074eee`
- name: `AslpFileLargeMapCreate`
- size: `534`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180074b40`

## callees

- `0x1800212e4`
- `0x180074cd8`
- `0x180074ef4`

## import_xrefs

- `ntdll!ZwCreateSection` at `0x180074d8c`
- `ntdll!ZwCreateSection` at `0x180074d8c`
- `ntdll!ZwMapViewOfSection` at `0x180074e0f`
- `ntdll!ZwMapViewOfSection` at `0x180074e83`
- `ntdll!ZwMapViewOfSection` at `0x180074e0f`
- `ntdll!ZwMapViewOfSection` at `0x180074e83`
- `ntdll!RtlAllocateHeap` at `0x180074d1f`
- `ntdll!RtlAllocateHeap` at `0x180074d1f`

## string_xrefs

- `0x180074d98`: `ZwCreateSection failed [%x]`
- `0x180074da5`: `AslpFileLargeMapCreate`

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
0x180074cd8  mov     [rsp-28h+arg_0], rbx
0x180074cdd  mov     [rsp-28h+arg_8], rsi
0x180074ce2  push    rbp
0x180074ce3  push    rdi
0x180074ce4  push    r13
0x180074ce6  push    r14
0x180074ce8  push    r15
0x180074cea  mov     rbp, rsp
0x180074ced  sub     rsp, 80h
0x180074cf4  xorps   xmm0, xmm0
0x180074cf7  mov     r15, rcx
0x180074cfa  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180074cfe  mov     r14, rdx
0x180074d01  mov     edx, 8; Flags
0x180074d06  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180074d0a  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180074d0e  mov     rcx, gs:60h
0x180074d17  lea     r8d, [rdx+38h]; Size
0x180074d1b  mov     rcx, [rcx+30h]; HeapHandle
0x180074d1f  call    cs:__imp_RtlAllocateHeap
0x180074d25  mov     [rbp+arg_10], rax
0x180074d29  mov     rbx, rax
0x180074d2c  test    rax, rax
0x180074d2f  jnz     short loc_180074D3B
0x180074d31  mov     edi, 0C0000017h
0x180074d36  jmp     loc_180074EC2
0x180074d3b  lea     rcx, [rax+8]; SectionHandle
0x180074d3f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180074d46  mov     rax, [r14]
0x180074d49  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180074d4d  mov     [rsp+80h+FileHandle], rax; FileHandle
0x180074d52  xorps   xmm0, xmm0
0x180074d55  mov     r13d, 2
0x180074d5b  mov     [rsp+80h+AllocationAttributes], 8000000h; AllocationAttributes
0x180074d63  xor     r9d, r9d; MaximumSize
0x180074d66  mov     [rsp+80h+SectionPageProtection], r13d; SectionPageProtection
0x180074d6b  mov     edx, 0F0005h; DesiredAccess
0x180074d70  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180074d78  mov     [rbp+ObjectAttributes.Attributes], 0
0x180074d7f  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180074d87  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180074d8c  call    cs:__imp_ZwCreateSection
0x180074d92  mov     edi, eax
0x180074d94  test    eax, eax
0x180074d96  jns     short loc_180074DBF
0x180074d98  lea     r9, aZwcreatesectio; "ZwCreateSection failed [%x]"
0x180074d9f  mov     r8d, 15Ah
0x180074da5  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x180074dac  mov     [rsp+80h+SectionPageProtection], eax
0x180074db0  mov     ecx, 1
0x180074db5  call    AslLogCallPrintf
0x180074dba  jmp     loc_180074EC2
0x180074dbf  mov     rcx, [r14+10h]
0x180074dc3  lea     rdx, [rbx+38h]
0x180074dc7  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180074dcc  lea     r8, [rbx+28h]; BaseAddress
0x180074dd0  add     rcx, 0FFFFFFFFFFFFF000h
0x180074dd7  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180074ddf  movzx   eax, cx
0x180074de2  xor     r9d, r9d; ZeroBits
0x180074de5  sub     rcx, rax
0x180074de8  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180074ded  mov     [rdx], rcx
0x180074df0  lea     rax, [rbx+30h]
0x180074df4  mov     rcx, [rbx+8]; SectionHandle
0x180074df8  mov     [rsp+80h+FileHandle], rax; ViewSize
0x180074dfd  mov     qword ptr [rsp+80h+AllocationAttributes], rdx; SectionOffset
0x180074e02  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180074e06  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180074e0f  call    cs:__imp_ZwMapViewOfSection
0x180074e15  mov     edi, eax
0x180074e17  test    eax, eax
0x180074e19  jns     short loc_180074E2D
0x180074e1b  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the en"...
0x180074e22  mov     r8d, 176h
0x180074e28  jmp     loc_180074DA5
0x180074e2d  mov     rsi, [r14+10h]
0x180074e31  mov     eax, 20000000h
0x180074e36  cmp     rsi, rax
0x180074e39  cmova   rsi, rax
0x180074e3d  mov     [rsp+80h+Win32Protect], r13d; Win32Protect
0x180074e42  lea     rcx, [rbx+18h]
0x180074e46  mov     [rsp+80h+AllocationType], 500000h; AllocationType
0x180074e4e  lea     rax, [rbx+20h]
0x180074e52  mov     [rcx], rsi
0x180074e55  lea     r8, [rbx+10h]; BaseAddress
0x180074e59  mov     [rsp+80h+InheritDisposition], r13d; InheritDisposition
0x180074e5e  xor     r9d, r9d; ZeroBits
0x180074e61  mov     [rsp+80h+FileHandle], rcx; ViewSize
0x180074e66  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180074e6a  mov     qword ptr [rax], 0
0x180074e71  mov     rcx, [rbx+8]; SectionHandle
0x180074e75  mov     qword ptr [rsp+80h+AllocationAttributes], rax; SectionOffset
0x180074e7a  mov     qword ptr [rsp+80h+SectionPageProtection], 0; CommitSize
0x180074e83  call    cs:__imp_ZwMapViewOfSection
0x180074e89  mov     edi, eax
0x180074e8b  cmp     eax, 0C0000017h
0x180074e90  jnz     short loc_180074E9E
0x180074e92  shr     rsi, 1
0x180074e95  cmp     rsi, 100000h
0x180074e9c  jnb     short loc_180074E3D
0x180074e9e  test    eax, eax
0x180074ea0  jns     short loc_180074EB4
0x180074ea2  lea     r9, aZwmapviewofsec; "ZwMapViewOfSection failed to map the st"...
0x180074ea9  mov     r8d, 1A0h
0x180074eaf  jmp     loc_180074DA5
0x180074eb4  mov     [rbx], r14
0x180074eb7  mov     [r15], rbx
0x180074eba  xor     ebx, ebx
0x180074ebc  mov     [rbp+arg_10], rbx
0x180074ec0  xor     edi, edi
0x180074ec2  test    rbx, rbx
0x180074ec5  jz      short loc_180074ED0
0x180074ec7  lea     rcx, [rbp+arg_10]
0x180074ecb  call    AslpFileLargeMapDelete
0x180074ed0  lea     r11, [rsp+80h+var_s0]
0x180074ed8  mov     eax, edi
0x180074eda  mov     rbx, [r11+30h]
0x180074ede  mov     rsi, [r11+38h]
0x180074ee2  mov     rsp, r11
0x180074ee5  pop     r15
0x180074ee7  pop     r14
0x180074ee9  pop     r13
0x180074eeb  pop     rdi
0x180074eec  pop     rbp
0x180074eed  retn
```
