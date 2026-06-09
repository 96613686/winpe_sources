# AslpFileLargeMapCreate

- ea: `0x140b03728`
- end: `0x140b0398d`
- name: `AslpFileLargeMapCreate`
- size: `613`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140739f38`

## callees

- `0x1406dd8e0`
- `0x1406ddd20`
- `0x140738694`
- `0x1408bf658`
- `0x1408c2f88`
- `0x140a508a0`
- `0x140b03728`

## string_xrefs

- `0x140b037d0`: `ZwCreateSection failed [%x]`
- `0x140b037dd`: `AslpFileLargeMapCreate`
- `0x140b03888`: `AslpFileLargeMapCreate`

## pseudocode

```c
__int64 __fastcall AslpFileLargeMapCreate(__int64 *a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rbx
  NTSTATUS v6; // edi
  const char *v7; // r9
  int v8; // r8d
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // r8d
  unsigned __int64 v12; // rsi
  NTSTATUS v13; // eax
  HANDLE v14; // rax
  HANDLE FileHandle; // [rsp+30h] [rbp-39h]
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int64 v18; // [rsp+E0h] [rbp+77h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v4 = AslAlloc(a1, 80);
  v18 = v4;
  v5 = v4;
  if ( !v4 )
  {
    v6 = -1073741801;
    goto LABEL_20;
  }
  ObjectAttributes.Length = 48;
  FileHandle = *(HANDLE *)a2;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = ZwCreateSection((PHANDLE)(v4 + 8), 0xF0005u, &ObjectAttributes, 0, 2u, 0x8000000u, FileHandle);
  if ( v6 < 0 )
  {
    v7 = "ZwCreateSection failed [%x]";
    v8 = 346;
LABEL_5:
    AslLogCallPrintf(1, (unsigned int)"AslpFileLargeMapCreate", v8, (_DWORD)v7);
    goto LABEL_20;
  }
  *(_QWORD *)(v5 + 64) = *(_QWORD *)(a2 + 16) - 4096LL - (unsigned __int16)(*(_QWORD *)(a2 + 16) - 4096);
  v6 = ZwMapViewOfSection(
         *(HANDLE *)(v5 + 8),
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         (PVOID *)(v5 + 48),
         0,
         0,
         (PLARGE_INTEGER)(v5 + 64),
         (PSIZE_T)(v5 + 56),
         ViewUnmap,
         0x500000u,
         2u);
  if ( v6 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the end of the file [%x]";
    v8 = 374;
    goto LABEL_5;
  }
  v9 = MmSecureVirtualMemory(*(PVOID *)(v5 + 48), *(_QWORD *)(v5 + 56), 2u);
  *(_QWORD *)(v5 + 72) = v9;
  if ( !v9 )
  {
    v10 = "MmSecureVirtualMemory failed to secure the end view";
    v11 = 381;
LABEL_10:
    AslLogCallPrintf(1, (unsigned int)"AslpFileLargeMapCreate", v11, (_DWORD)v10);
    v6 = -1073741823;
    goto LABEL_20;
  }
  v12 = *(_QWORD *)(a2 + 16);
  if ( v12 > 0x20000000 )
    v12 = 0x20000000;
  do
  {
    *(_QWORD *)(v5 + 24) = v12;
    *(_QWORD *)(v5 + 32) = 0;
    v13 = ZwMapViewOfSection(
            *(HANDLE *)(v5 + 8),
            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
            (PVOID *)(v5 + 16),
            0,
            0,
            (PLARGE_INTEGER)(v5 + 32),
            (PSIZE_T)(v5 + 24),
            ViewUnmap,
            0x500000u,
            2u);
    v6 = v13;
    if ( v13 != -1073741801 )
      break;
    v12 >>= 1;
  }
  while ( v12 >= 0x100000 );
  if ( v13 < 0 )
  {
    v7 = "ZwMapViewOfSection failed to map the start of the file [%x]";
    v8 = 416;
    goto LABEL_5;
  }
  v14 = MmSecureVirtualMemory(*(PVOID *)(v5 + 16), *(_QWORD *)(v5 + 24), 2u);
  *(_QWORD *)(v5 + 40) = v14;
  if ( !v14 )
  {
    v10 = "MmSecureVirtualMemory failed to secure the start view";
    v11 = 423;
    goto LABEL_10;
  }
  *(_QWORD *)v5 = a2;
  *a1 = v5;
  v5 = 0;
  v18 = 0;
  v6 = 0;
LABEL_20:
  if ( v5 )
    AslpFileLargeMapDelete(&v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140b03728  push    rbp
0x140b0372a  push    rbx
0x140b0372b  push    rsi
0x140b0372c  push    rdi
0x140b0372d  push    r12
0x140b0372f  push    r13
0x140b03731  push    r14
0x140b03733  push    r15
0x140b03735  lea     rbp, [rsp-1Fh]
0x140b0373a  sub     rsp, 88h
0x140b03741  xorps   xmm0, xmm0
0x140b03744  mov     r14, rdx
0x140b03747  mov     edx, 50h ; 'P'
0x140b0374c  mov     r13, rcx
0x140b0374f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140b03753  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140b03757  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140b0375b  call    AslAlloc
0x140b03760  mov     [rbp+57h+arg_10], rax
0x140b03764  mov     rbx, rax
0x140b03767  test    rax, rax
0x140b0376a  jnz     short loc_140B03776
0x140b0376c  mov     edi, 0C0000017h
0x140b03771  jmp     loc_140B03968
0x140b03776  lea     rcx, [rax+8]; SectionHandle
0x140b0377a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140b03781  mov     rax, [r14]
0x140b03784  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140b03788  mov     [rsp+0C0h+FileHandle], rax; FileHandle
0x140b0378d  xorps   xmm0, xmm0
0x140b03790  mov     esi, 2
0x140b03795  mov     [rsp+0C0h+AllocationAttributes], 8000000h; AllocationAttributes
0x140b0379d  xor     r9d, r9d; MaximumSize
0x140b037a0  mov     [rsp+0C0h+SectionPageProtection], esi; SectionPageProtection
0x140b037a4  mov     edx, 0F0005h; DesiredAccess
0x140b037a9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140b037b1  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x140b037b8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140b037c0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140b037c5  call    ZwCreateSection
0x140b037ca  mov     edi, eax
0x140b037cc  test    eax, eax
0x140b037ce  jns     short loc_140B037F7
0x140b037d0  lea     r9, aZwcreatesectio_0; "ZwCreateSection failed [%x]"
0x140b037d7  mov     r8d, 15Ah
0x140b037dd  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140b037e4  mov     [rsp+0C0h+SectionPageProtection], eax
0x140b037e8  mov     ecx, 1
0x140b037ed  call    AslLogCallPrintf
0x140b037f2  jmp     loc_140B03968
0x140b037f7  mov     rcx, [r14+10h]
0x140b037fb  lea     rdx, [rbx+40h]
0x140b037ff  mov     [rsp+0C0h+Win32Protect], esi; Win32Protect
0x140b03803  lea     r8, [rbx+30h]; BaseAddress
0x140b03807  add     rcx, 0FFFFFFFFFFFFF000h
0x140b0380e  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140b03816  movzx   eax, cx
0x140b03819  xor     r9d, r9d; ZeroBits
0x140b0381c  sub     rcx, rax
0x140b0381f  mov     [rsp+0C0h+InheritDisposition], esi; InheritDisposition
0x140b03823  mov     [rdx], rcx
0x140b03826  lea     rax, [rbx+38h]
0x140b0382a  mov     rcx, [rbx+8]; SectionHandle
0x140b0382e  mov     [rsp+0C0h+FileHandle], rax; ViewSize
0x140b03833  mov     qword ptr [rsp+0C0h+AllocationAttributes], rdx; SectionOffset
0x140b03838  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140b0383c  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140b03845  call    ZwMapViewOfSection
0x140b0384a  mov     edi, eax
0x140b0384c  test    eax, eax
0x140b0384e  jns     short loc_140B03862
0x140b03850  lea     r9, aZwmapviewofsec_2; "ZwMapViewOfSection failed to map the en"...
0x140b03857  mov     r8d, 176h
0x140b0385d  jmp     loc_140B037DD
0x140b03862  mov     rdx, [rbx+38h]; Size
0x140b03866  mov     r8d, esi; ProbeMode
0x140b03869  mov     rcx, [rbx+30h]; Address
0x140b0386d  call    MmSecureVirtualMemory
0x140b03872  mov     [rbx+48h], rax
0x140b03876  test    rax, rax
0x140b03879  jnz     short loc_140B038A3
0x140b0387b  lea     r9, aMmsecurevirtua_0; "MmSecureVirtualMemory failed to secure "...
0x140b03882  mov     r8d, 17Dh
0x140b03888  lea     rdx, aAslpfilelargem; "AslpFileLargeMapCreate"
0x140b0388f  mov     ecx, 1
0x140b03894  call    AslLogCallPrintf
0x140b03899  mov     edi, 0C0000001h
0x140b0389e  jmp     loc_140B03968
0x140b038a3  mov     rsi, [r14+10h]
0x140b038a7  mov     eax, 20000000h
0x140b038ac  cmp     rsi, rax
0x140b038af  cmova   rsi, rax
0x140b038b3  mov     ecx, 2
0x140b038b8  lea     rax, [rbx+20h]
0x140b038bc  mov     [rsp+0C0h+Win32Protect], ecx; Win32Protect
0x140b038c0  lea     r15, [rbx+18h]
0x140b038c4  mov     [rsp+0C0h+AllocationType], 500000h; AllocationType
0x140b038cc  lea     r8, [rbx+10h]; BaseAddress
0x140b038d0  mov     [rsp+0C0h+InheritDisposition], ecx; InheritDisposition
0x140b038d4  xor     r9d, r9d; ZeroBits
0x140b038d7  mov     [r15], rsi
0x140b038da  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140b038de  mov     [rsp+0C0h+FileHandle], r15; ViewSize
0x140b038e3  mov     qword ptr [rax], 0
0x140b038ea  mov     rcx, [rbx+8]; SectionHandle
0x140b038ee  mov     qword ptr [rsp+0C0h+AllocationAttributes], rax; SectionOffset
0x140b038f3  mov     qword ptr [rsp+0C0h+SectionPageProtection], 0; CommitSize
0x140b038fc  call    ZwMapViewOfSection
0x140b03901  mov     edi, eax
0x140b03903  cmp     eax, 0C0000017h
0x140b03908  jnz     short loc_140B03916
0x140b0390a  shr     rsi, 1
0x140b0390d  cmp     rsi, 100000h
0x140b03914  jnb     short loc_140B038B3
0x140b03916  test    eax, eax
0x140b03918  jns     short loc_140B0392C
0x140b0391a  lea     r9, aZwmapviewofsec_0; "ZwMapViewOfSection failed to map the st"...
0x140b03921  mov     r8d, 1A0h
0x140b03927  jmp     loc_140B037DD
0x140b0392c  mov     rdx, [r15]; Size
0x140b0392f  mov     r8d, 2; ProbeMode
0x140b03935  mov     rcx, [rbx+10h]; Address
0x140b03939  call    MmSecureVirtualMemory
0x140b0393e  mov     [rbx+28h], rax
0x140b03942  test    rax, rax
0x140b03945  jnz     short loc_140B03959
0x140b03947  lea     r9, aMmsecurevirtua_1; "MmSecureVirtualMemory failed to secure "...
0x140b0394e  mov     r8d, 1A7h
0x140b03954  jmp     loc_140B03888
0x140b03959  mov     [rbx], r14
0x140b0395c  mov     [r13+0], rbx
0x140b03960  xor     ebx, ebx
0x140b03962  mov     [rbp+57h+arg_10], rbx
0x140b03966  xor     edi, edi
0x140b03968  test    rbx, rbx
0x140b0396b  jz      short loc_140B03976
0x140b0396d  lea     rcx, [rbp+57h+arg_10]
0x140b03971  call    AslpFileLargeMapDelete
0x140b03976  mov     eax, edi
0x140b03978  add     rsp, 88h
0x140b0397f  pop     r15
0x140b03981  pop     r14
0x140b03983  pop     r13
0x140b03985  pop     r12
0x140b03987  pop     rdi
0x140b03988  pop     rsi
0x140b03989  pop     rbx
0x140b0398a  pop     rbp
0x140b0398b  retn
```
