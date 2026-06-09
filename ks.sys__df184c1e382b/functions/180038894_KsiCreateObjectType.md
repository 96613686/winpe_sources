# KsiCreateObjectType

- ea: `0x180038894`
- end: `0x180038a5b`
- name: `KsiCreateObjectType`
- size: `455`
- prototype: `__int64 __fastcall(void *, const wchar_t *, const void *, unsigned int, int, void **FileHandle)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180033b30`
- `0x1800372d0`
- `0x180037580`
- `0x180039400`

## callees

- `0x180006f80`
- `0x180019d00`
- `0x18001a000`
- `0x180038894`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x180038a0c`
- `ntoskrnl!IoCreateFile` at `0x180038a0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180038a20`
- `ntoskrnl!ExFreePoolWithTag` at `0x180038a20`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003891e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003891e`

## pseudocode

```c
__int64 __fastcall KsiCreateObjectType(
        void *a1,
        const wchar_t *a2,
        const void *a3,
        unsigned int a4,
        int a5,
        void **FileHandle)
{
  size_t v6; // r12
  __int64 v9; // rdi
  unsigned __int64 v10; // rsi
  unsigned int v11; // eax
  unsigned int v12; // ecx
  size_t v13; // r14
  char *PoolWithTag; // rbx
  NTSTATUS v15; // r14d
  __int128 v17; // [rsp+70h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF

  v6 = a4;
  v9 = -1;
  IoStatusBlock = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, 44);
  do
    ++v9;
  while ( a2[v9] );
  v10 = 2LL * (unsigned int)v9;
  if ( v10 > 0xFFFFFFFF )
    return 3221225621LL;
  v11 = v10 + 2;
  if ( (int)v10 + 2 < (unsigned int)v10 )
    return 3221225621LL;
  v12 = v11 + a4;
  if ( v11 + a4 < v11 )
    return 3221225621LL;
  v13 = v12;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1025, v12, 0x706F534Bu);
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_9;
    return 3221225626LL;
  }
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, (unsigned int)v13);
LABEL_9:
  v15 = RtlStringCbCopyW((NTSTRSAFE_PWSTR)PoolWithTag, v13, a2);
  if ( v15 >= 0 )
  {
    *(_WORD *)&PoolWithTag[v10] = 92;
    memmove(&PoolWithTag[2 * (unsigned int)(v9 + 1)], a3, v6);
    ObjectAttributes.RootDirectory = a1;
    LOWORD(v17) = v6 + 2 * (v9 + 1);
    WORD1(v17) = v17;
    *((_QWORD *)&v17 + 1) = PoolWithTag;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v17;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = IoCreateFile(
            FileHandle,
            a5 & 0xFFFFFDFF,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            0,
            1u,
            0,
            0,
            0,
            CreateFileTypeNone,
            0,
            0x101u);
  }
  ExFreePoolWithTag(PoolWithTag, 0);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180038894  mov     [rsp-8+arg_0], rcx
0x180038899  push    rbp
0x18003889a  push    rbx
0x18003889b  push    rsi
0x18003889c  push    rdi
0x18003889d  push    r12
0x18003889f  push    r13
0x1800388a1  push    r14
0x1800388a3  push    r15
0x1800388a5  lea     rbp, [rsp-0Fh]
0x1800388aa  sub     rsp, 0C8h
0x1800388b1  xorps   xmm0, xmm0
0x1800388b4  mov     r12d, r9d
0x1800388b7  xorps   xmm1, xmm1
0x1800388ba  xor     eax, eax
0x1800388bc  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1800388c0  mov     r13, r8
0x1800388c3  mov     r15, rdx
0x1800388c6  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x1800388ca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800388ce  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x1800388d2  movups  [rbp+47h+var_90], xmm1
0x1800388d6  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x1800388da  inc     rdi
0x1800388dd  cmp     [rdx+rdi*2], ax
0x1800388e1  jnz     short loc_1800388DA
0x1800388e3  mov     eax, edi
0x1800388e5  lea     rsi, [rax+rax]
0x1800388e9  mov     eax, 0FFFFFFFFh
0x1800388ee  cmp     rsi, rax
0x1800388f1  ja      loc_180038A41
0x1800388f7  lea     eax, [rsi+2]
0x1800388fa  cmp     eax, esi
0x1800388fc  jb      loc_180038A41
0x180038902  lea     ecx, [rax+r12]
0x180038906  cmp     ecx, eax
0x180038908  jb      loc_180038A41
0x18003890e  mov     r14d, ecx
0x180038911  mov     r8d, 706F534Bh; Tag
0x180038917  mov     edx, ecx; NumberOfBytes
0x180038919  mov     ecx, 401h; PoolType
0x18003891e  call    cs:__imp_ExAllocatePoolWithTag
0x180038925  nop     dword ptr [rax+rax+00h]
0x18003892a  mov     rbx, rax
0x18003892d  xor     eax, eax
0x18003892f  cmp     cs:ExPoolZeroingNativelySupported, al
0x180038935  jnz     loc_180038A31
0x18003893b  test    rbx, rbx
0x18003893e  jz      loc_180038A3A
0x180038944  mov     r8d, r14d; Size
0x180038947  xor     edx, edx; Val
0x180038949  mov     rcx, rbx; void *
0x18003894c  call    memset
0x180038951  mov     r8, r15; pszSrc
0x180038954  mov     rdx, r14; cbDest
0x180038957  mov     rcx, rbx; pszDest
0x18003895a  call    RtlStringCbCopyW
0x18003895f  xor     r15d, r15d
0x180038962  mov     r14d, eax
0x180038965  test    eax, eax
0x180038967  js      loc_180038A1B
0x18003896d  lea     eax, [rdi+1]
0x180038970  mov     word ptr [rsi+rbx], 5Ch ; '\'
0x180038976  lea     rcx, [rbx+rax*2]; void *
0x18003897a  mov     r8, r12; Size
0x18003897d  mov     rdx, r13; Src
0x180038980  call    memmove
0x180038985  mov     rax, [rbp+47h+arg_0]
0x180038989  lea     ecx, [r15+1]
0x18003898d  mov     edx, [rbp+47h+arg_20]
0x180038990  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x180038994  mov     [rsp+100h+Options], 101h; Options
0x18003899c  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1800389a0  mov     [rsp+100h+InternalParameters], r15; InternalParameters
0x1800389a5  add     di, cx
0x1800389a8  mov     [rsp+100h+CreateFileType], r15d; CreateFileType
0x1800389ad  add     di, di
0x1800389b0  mov     [rsp+100h+EaLength], r15d; EaLength
0x1800389b5  add     di, r12w
0x1800389b9  mov     [rsp+100h+EaBuffer], r15; EaBuffer
0x1800389be  xorps   xmm0, xmm0
0x1800389c1  mov     [rsp+100h+CreateOptions], r15d; CreateOptions
0x1800389c6  btr     edx, 9; DesiredAccess
0x1800389ca  mov     [rsp+100h+Disposition], ecx; Disposition
0x1800389ce  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x1800389d2  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x1800389d6  lea     rax, [rbp+47h+var_90]
0x1800389da  mov     [rsp+100h+ShareAccess], r15d; ShareAccess
0x1800389df  mov     [rsp+100h+FileAttributes], r15d; FileAttributes
0x1800389e4  mov     word ptr [rbp+47h+var_90], di
0x1800389e8  mov     word ptr [rbp+47h+var_90+2], di
0x1800389ec  mov     [rsp+100h+AllocationSize], r15; AllocationSize
0x1800389f1  mov     qword ptr [rbp+47h+var_90+8], rbx
0x1800389f5  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800389fc  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x180038a03  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x180038a07  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x180038a0c  call    cs:__imp_IoCreateFile
0x180038a13  nop     dword ptr [rax+rax+00h]
0x180038a18  mov     r14d, eax
0x180038a1b  xor     edx, edx; Tag
0x180038a1d  mov     rcx, rbx; P
0x180038a20  call    cs:__imp_ExFreePoolWithTag
0x180038a27  nop     dword ptr [rax+rax+00h]
0x180038a2c  mov     eax, r14d
0x180038a2f  jmp     short loc_180038A46
0x180038a31  test    rbx, rbx
0x180038a34  jnz     loc_180038951
0x180038a3a  mov     eax, 0C000009Ah
0x180038a3f  jmp     short loc_180038A46
0x180038a41  mov     eax, 0C0000095h
0x180038a46  add     rsp, 0C8h
0x180038a4d  pop     r15
0x180038a4f  pop     r14
0x180038a51  pop     r13
0x180038a53  pop     r12
0x180038a55  pop     rdi
0x180038a56  pop     rsi
0x180038a57  pop     rbx
0x180038a58  pop     rbp
0x180038a59  retn
```
