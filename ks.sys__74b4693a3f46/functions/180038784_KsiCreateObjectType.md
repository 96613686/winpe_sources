# KsiCreateObjectType

- ea: `0x180038784`
- end: `0x18003894b`
- name: `KsiCreateObjectType`
- size: `455`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180033b30`
- `0x1800371c0`
- `0x180037470`
- `0x1800393b0`

## callees

- `0x180006f80`
- `0x180019cc0`
- `0x180019fc0`
- `0x180038784`

## import_xrefs

- `ntoskrnl!IoCreateFile` at `0x1800388fc`
- `ntoskrnl!IoCreateFile` at `0x1800388fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x180038910`
- `ntoskrnl!ExFreePoolWithTag` at `0x180038910`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003880e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003880e`

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
0x180038784  mov     [rsp-8+arg_0], rcx
0x180038789  push    rbp
0x18003878a  push    rbx
0x18003878b  push    rsi
0x18003878c  push    rdi
0x18003878d  push    r12
0x18003878f  push    r13
0x180038791  push    r14
0x180038793  push    r15
0x180038795  lea     rbp, [rsp-0Fh]
0x18003879a  sub     rsp, 0C8h
0x1800387a1  xorps   xmm0, xmm0
0x1800387a4  mov     r12d, r9d
0x1800387a7  xorps   xmm1, xmm1
0x1800387aa  xor     eax, eax
0x1800387ac  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x1800387b0  mov     r13, r8
0x1800387b3  mov     r15, rdx
0x1800387b6  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x1800387ba  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800387be  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x1800387c2  movups  [rbp+47h+var_90], xmm1
0x1800387c6  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x1800387ca  inc     rdi
0x1800387cd  cmp     [rdx+rdi*2], ax
0x1800387d1  jnz     short loc_1800387CA
0x1800387d3  mov     eax, edi
0x1800387d5  lea     rsi, [rax+rax]
0x1800387d9  mov     eax, 0FFFFFFFFh
0x1800387de  cmp     rsi, rax
0x1800387e1  ja      loc_180038931
0x1800387e7  lea     eax, [rsi+2]
0x1800387ea  cmp     eax, esi
0x1800387ec  jb      loc_180038931
0x1800387f2  lea     ecx, [rax+r12]
0x1800387f6  cmp     ecx, eax
0x1800387f8  jb      loc_180038931
0x1800387fe  mov     r14d, ecx
0x180038801  mov     r8d, 706F534Bh; Tag
0x180038807  mov     edx, ecx; NumberOfBytes
0x180038809  mov     ecx, 401h; PoolType
0x18003880e  call    cs:__imp_ExAllocatePoolWithTag
0x180038815  nop     dword ptr [rax+rax+00h]
0x18003881a  mov     rbx, rax
0x18003881d  xor     eax, eax
0x18003881f  cmp     cs:ExPoolZeroingNativelySupported, al
0x180038825  jnz     loc_180038921
0x18003882b  test    rbx, rbx
0x18003882e  jz      loc_18003892A
0x180038834  mov     r8d, r14d; Size
0x180038837  xor     edx, edx; Val
0x180038839  mov     rcx, rbx; void *
0x18003883c  call    memset
0x180038841  mov     r8, r15; pszSrc
0x180038844  mov     rdx, r14; cbDest
0x180038847  mov     rcx, rbx; pszDest
0x18003884a  call    RtlStringCbCopyW
0x18003884f  xor     r15d, r15d
0x180038852  mov     r14d, eax
0x180038855  test    eax, eax
0x180038857  js      loc_18003890B
0x18003885d  lea     eax, [rdi+1]
0x180038860  mov     word ptr [rsi+rbx], 5Ch ; '\'
0x180038866  lea     rcx, [rbx+rax*2]; void *
0x18003886a  mov     r8, r12; Size
0x18003886d  mov     rdx, r13; Src
0x180038870  call    memmove
0x180038875  mov     rax, [rbp+47h+arg_0]
0x180038879  lea     ecx, [r15+1]
0x18003887d  mov     edx, [rbp+47h+arg_20]
0x180038880  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x180038884  mov     [rsp+100h+Options], 101h; Options
0x18003888c  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x180038890  mov     [rsp+100h+InternalParameters], r15; InternalParameters
0x180038895  add     di, cx
0x180038898  mov     [rsp+100h+CreateFileType], r15d; CreateFileType
0x18003889d  add     di, di
0x1800388a0  mov     [rsp+100h+EaLength], r15d; EaLength
0x1800388a5  add     di, r12w
0x1800388a9  mov     [rsp+100h+EaBuffer], r15; EaBuffer
0x1800388ae  xorps   xmm0, xmm0
0x1800388b1  mov     [rsp+100h+CreateOptions], r15d; CreateOptions
0x1800388b6  btr     edx, 9; DesiredAccess
0x1800388ba  mov     [rsp+100h+Disposition], ecx; Disposition
0x1800388be  mov     rcx, [rbp+47h+FileHandle]; FileHandle
0x1800388c2  mov     [rbp+47h+ObjectAttributes.RootDirectory], rax
0x1800388c6  lea     rax, [rbp+47h+var_90]
0x1800388ca  mov     [rsp+100h+ShareAccess], r15d; ShareAccess
0x1800388cf  mov     [rsp+100h+FileAttributes], r15d; FileAttributes
0x1800388d4  mov     word ptr [rbp+47h+var_90], di
0x1800388d8  mov     word ptr [rbp+47h+var_90+2], di
0x1800388dc  mov     [rsp+100h+AllocationSize], r15; AllocationSize
0x1800388e1  mov     qword ptr [rbp+47h+var_90+8], rbx
0x1800388e5  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800388ec  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x1800388f3  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x1800388f7  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800388fc  call    cs:__imp_IoCreateFile
0x180038903  nop     dword ptr [rax+rax+00h]
0x180038908  mov     r14d, eax
0x18003890b  xor     edx, edx; Tag
0x18003890d  mov     rcx, rbx; P
0x180038910  call    cs:__imp_ExFreePoolWithTag
0x180038917  nop     dword ptr [rax+rax+00h]
0x18003891c  mov     eax, r14d
0x18003891f  jmp     short loc_180038936
0x180038921  test    rbx, rbx
0x180038924  jnz     loc_180038841
0x18003892a  mov     eax, 0C000009Ah
0x18003892f  jmp     short loc_180038936
0x180038931  mov     eax, 0C0000095h
0x180038936  add     rsp, 0C8h
0x18003893d  pop     r15
0x18003893f  pop     r14
0x180038941  pop     r13
0x180038943  pop     r12
0x180038945  pop     rdi
0x180038946  pop     rsi
0x180038947  pop     rbx
0x180038948  pop     rbp
0x180038949  retn
```
