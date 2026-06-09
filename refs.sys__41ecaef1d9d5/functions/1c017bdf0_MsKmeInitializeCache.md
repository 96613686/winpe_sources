# MsKmeInitializeCache

- ea: `0x1c017bdf0`
- end: `0x1c017bff9`
- name: `MsKmeInitializeCache`
- size: `521`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x1c0002bac`
- `0x1c0067040`
- `0x1c0068960`
- `0x1c015331c`
- `0x1c017bdf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1c017bfc3`
- `ntoskrnl!ObfDereferenceObject` at `0x1c017bfc3`
- `ntoskrnl!CcInitializeCacheMap` at `0x1c017bf10`
- `ntoskrnl!CcInitializeCacheMap` at `0x1c017bf10`
- `ntoskrnl!IoCreateStreamFileObjectEx2` at `0x1c017be79`
- `ntoskrnl!IoCreateStreamFileObjectEx2` at `0x1c017be79`
- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x1c017bf2b`
- `ntoskrnl!CcSetAdditionalCacheAttributesEx` at `0x1c017bf2b`
- `ntoskrnl!MmDisableModifiedWriteOfSection` at `0x1c017bf40`
- `ntoskrnl!MmDisableModifiedWriteOfSection` at `0x1c017bf40`

## pseudocode

```c
__int64 __fastcall MsKmeInitializeCache(__int64 a1, _QWORD *a2, __int64 a3, PFILE_OBJECT *a4)
{
  SECTION_OBJECT_POINTERS *v7; // r14
  __int64 v8; // rcx
  WCHAR *v9; // rdx
  unsigned int v10; // ebx
  __int64 v11; // r8
  PFILE_OBJECT v12; // rax
  __int64 v13; // rax
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-60h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-58h]
  __int128 v17; // [rsp+48h] [rbp-50h] BYREF
  struct _CC_FILE_SIZES FileSizes; // [rsp+58h] [rbp-40h] BYREF

  memset(&FileSizes, 0, sizeof(FileSizes));
  FileObject = 0;
  v7 = (SECTION_OBJECT_POINTERS *)(a2[30] + 32LL);
  v17 = 0;
  LODWORD(v17) = 196624;
  v8 = a2[16];
  *((_QWORD *)&v17 + 1) = v8 - 336;
  v10 = IoCreateStreamFileObjectEx2(&v17, 0, *(_QWORD *)(*(_QWORD *)(v8 + 208) + 16LL), &FileObject, 0);
  v16 = v10;
  if ( a3 )
  {
    FileObject->FileName.MaximumLength = *(_WORD *)(a3 + 2);
    FileObject->FileName.Length = *(_WORD *)a3;
    v9 = *(WCHAR **)(a3 + 8);
    FileObject->FileName.Buffer = v9;
  }
  FileObject->ReadAccess = 1;
  FileObject->WriteAccess = 1;
  FileObject->DeleteAccess = 1;
  LOBYTE(v9) = 1;
  RefsIncrementCloseCounts(a2, v9, 0);
  FileSizes.ValidDataLength.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
  FileObject->Flags |= 0x20000000u;
  FileSizes.AllocationSize.QuadPart &= v11;
  RefsSetFileObject(FileObject, 5, a2, 0);
  FileObject->SectionObjectPointer = v7;
  CcInitializeCacheMap(FileObject, &FileSizes, 1u, &Callbacks, a2);
  CcSetAdditionalCacheAttributesEx(FileObject, 46);
  MmDisableModifiedWriteOfSection(FileObject->SectionObjectPointer);
  v12 = FileObject;
  a2[29] = FileObject;
  *a4 = v12;
  v13 = a2[16];
  if ( !*(_QWORD *)(v13 + 88) )
    *(_QWORD *)(v13 + 88) = a2;
  return v10;
}

```

## disassembly

```asm
0x1c017bdf0  mov     r11, rsp
0x1c017bdf3  mov     [r11+8], rbx
0x1c017bdf7  mov     [r11+18h], rsi
0x1c017bdfb  push    rdi
0x1c017bdfc  push    r14
0x1c017bdfe  push    r15
0x1c017be00  sub     rsp, 80h
0x1c017be07  mov     rax, cs:__security_cookie
0x1c017be0e  xor     rax, rsp
0x1c017be11  mov     [rsp+98h+var_28], rax
0x1c017be16  mov     r15, r9
0x1c017be19  mov     rsi, r8
0x1c017be1c  mov     rdi, rdx
0x1c017be1f  xorps   xmm0, xmm0
0x1c017be22  xor     eax, eax
0x1c017be24  movups  xmmword ptr [rsp+98h+FileSizes.AllocationSize], xmm0
0x1c017be29  mov     [r11-30h], rax
0x1c017be2d  and     [r11-60h], rax
0x1c017be31  mov     [rsp+98h+var_68], al
0x1c017be35  mov     r14, [rdx+0F0h]
0x1c017be3c  add     r14, 20h ; ' '
0x1c017be40  movups  [rsp+98h+var_50], xmm0
0x1c017be45  mov     dword ptr [rsp+98h+var_50], 30010h
0x1c017be4d  mov     rcx, [rdx+80h]
0x1c017be54  lea     rax, [rcx-150h]
0x1c017be5b  mov     [r11-48h], rax
0x1c017be5f  mov     r8, [rcx+0D0h]
0x1c017be66  and     qword ptr [r11-78h], 0
0x1c017be6b  lea     r9, [r11-60h]
0x1c017be6f  mov     r8, [r8+10h]
0x1c017be73  xor     edx, edx
0x1c017be75  lea     rcx, [r11-50h]
0x1c017be79  call    cs:__imp_IoCreateStreamFileObjectEx2
0x1c017be80  nop     dword ptr [rax+rax+00h]
0x1c017be85  mov     ebx, eax
0x1c017be87  mov     [rsp+98h+var_58], eax
0x1c017be8b  test    rsi, rsi
0x1c017be8e  jnz     loc_1C017BF6F
0x1c017be94  mov     rax, [rsp+98h+FileObject]
0x1c017be99  mov     byte ptr [rax+4Ah], 1
0x1c017be9d  mov     rax, [rsp+98h+FileObject]
0x1c017bea2  mov     byte ptr [rax+4Bh], 1
0x1c017bea6  mov     rax, [rsp+98h+FileObject]
0x1c017beab  mov     byte ptr [rax+4Ch], 1
0x1c017beaf  xor     r8d, r8d
0x1c017beb2  mov     dl, 1
0x1c017beb4  mov     rcx, rdi
0x1c017beb7  call    RefsIncrementCloseCounts
0x1c017bebc  mov     rdx, 7FFFFFFFFFFFFFFFh
0x1c017bec6  mov     qword ptr [rsp+98h+FileSizes.ValidDataLength], rdx
0x1c017becb  mov     rax, [rsp+98h+FileObject]
0x1c017bed0  bts     dword ptr [rax+50h], 1Dh
0x1c017bed5  and     qword ptr [rsp+98h+FileSizes.AllocationSize], r8
0x1c017beda  xor     r9d, r9d
0x1c017bedd  mov     r8, rdi
0x1c017bee0  lea     edx, [r9+5]
0x1c017bee4  mov     rcx, [rsp+98h+FileObject]
0x1c017bee9  call    RefsSetFileObject
0x1c017beee  mov     rcx, [rsp+98h+FileObject]
0x1c017bef3  mov     [rcx+28h], r14
0x1c017bef7  mov     [rsp+98h+LazyWriteContext], rdi; LazyWriteContext
0x1c017befc  lea     r9, Callbacks; Callbacks
0x1c017bf03  mov     r8b, 1; PinAccess
0x1c017bf06  lea     rdx, [rsp+98h+FileSizes]; FileSizes
0x1c017bf0b  mov     rcx, [rsp+98h+FileObject]; FileObject
0x1c017bf10  call    cs:__imp_CcInitializeCacheMap
0x1c017bf17  nop     dword ptr [rax+rax+00h]
0x1c017bf1c  mov     [rsp+98h+var_68], 1
0x1c017bf21  mov     edx, 2Eh ; '.'
0x1c017bf26  mov     rcx, [rsp+98h+FileObject]
0x1c017bf2b  call    cs:__imp_CcSetAdditionalCacheAttributesEx
0x1c017bf32  nop     dword ptr [rax+rax+00h]
0x1c017bf37  mov     rcx, [rsp+98h+FileObject]
0x1c017bf3c  mov     rcx, [rcx+28h]
0x1c017bf40  call    cs:__imp_MmDisableModifiedWriteOfSection
0x1c017bf47  nop     dword ptr [rax+rax+00h]
0x1c017bf4c  mov     rax, [rsp+98h+FileObject]
0x1c017bf51  mov     [rdi+0E8h], rax
0x1c017bf58  mov     [r15], rax
0x1c017bf5b  mov     rax, [rdi+80h]
0x1c017bf62  cmp     qword ptr [rax+58h], 0
0x1c017bf67  jnz     short loc_1C017BF9A
0x1c017bf69  mov     [rax+58h], rdi
0x1c017bf6d  jmp     short loc_1C017BF9A
0x1c017bf6f  movzx   edx, word ptr [rsi+2]
0x1c017bf73  mov     rcx, [rsp+98h+FileObject]
0x1c017bf78  mov     [rcx+5Ah], dx
0x1c017bf7c  movzx   edx, word ptr [rsi]
0x1c017bf7f  mov     rcx, [rsp+98h+FileObject]
0x1c017bf84  mov     [rcx+58h], dx
0x1c017bf88  mov     rdx, [rsi+8]
0x1c017bf8c  mov     rcx, [rsp+98h+FileObject]
0x1c017bf91  mov     [rcx+60h], rdx
0x1c017bf95  jmp     loc_1C017BE94
0x1c017bf9a  jmp     short loc_1C017BFD0
0x1c017bf9c  mov     ebx, eax
0x1c017bf9e  mov     [rsp+98h+var_58], eax
0x1c017bfa2  test    eax, eax
0x1c017bfa4  jns     short loc_1C017BFD0
0x1c017bfa6  cmp     [rsp+98h+var_68], 0
0x1c017bfab  jz      short loc_1C017BFB9
0x1c017bfad  xor     edx, edx
0x1c017bfaf  mov     rcx, [rsp+98h+FileObject]
0x1c017bfb4  call    RefsUninitializeCacheMap
0x1c017bfb9  mov     rcx, [rsp+98h+FileObject]; Object
0x1c017bfbe  test    rcx, rcx
0x1c017bfc1  jz      short loc_1C017BFD0
0x1c017bfc3  call    cs:__imp_ObfDereferenceObject
0x1c017bfca  nop     dword ptr [rax+rax+00h]
0x1c017bfcf  nop
0x1c017bfd0  mov     eax, ebx
0x1c017bfd2  mov     rcx, [rsp+98h+var_28]
0x1c017bfd7  xor     rcx, rsp; StackCookie
0x1c017bfda  call    __security_check_cookie
0x1c017bfdf  lea     r11, [rsp+98h+var_18]
0x1c017bfe7  mov     rbx, [r11+20h]
0x1c017bfeb  mov     rsi, [r11+30h]
0x1c017bfef  mov     rsp, r11
0x1c017bff2  pop     r15
0x1c017bff4  pop     r14
0x1c017bff6  pop     rdi
0x1c017bff7  retn
```
