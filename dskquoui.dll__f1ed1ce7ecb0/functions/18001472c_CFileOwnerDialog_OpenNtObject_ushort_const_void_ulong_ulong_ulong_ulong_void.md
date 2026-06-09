# CFileOwnerDialog::OpenNtObject(ushort const *,void *,ulong,ulong,ulong,ulong,void * *)

- ea: `0x18001472c`
- end: `0x18001483d`
- name: `?OpenNtObject@CFileOwnerDialog@@AEAAJPEBGPEAXKKKKPEAPEAX@Z`
- size: `273`
- prototype: `int(CFileOwnerDialog *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001230c`
- `0x180014850`

## callees

- `0x18001472c`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001476c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001476c`
- `ntdll!NtCreateFile` at `0x180014809`
- `ntdll!NtCreateFile` at `0x180014809`
- `ntdll!RtlFreeHeap` at `0x180014829`
- `ntdll!RtlFreeHeap` at `0x180014829`
- `ntdll!RtlInitUnicodeString` at `0x180014796`
- `ntdll!RtlInitUnicodeString` at `0x180014796`

## pseudocode

```c
__int64 __fastcall CFileOwnerDialog::OpenNtObject(
        CFileOwnerDialog *this,
        const unsigned __int16 *a2,
        void *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        void **FileHandle)
{
  BOOLEAN v9; // al
  bool v10; // di
  unsigned int v11; // ebx
  _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtPathName = 0;
  IoStatusBlock = 0;
  if ( a3 )
  {
    v10 = 0;
    RtlInitUnicodeString(&NtPathName, a2);
    goto LABEL_5;
  }
  v9 = RtlDosPathNameToNtPathName_U(a2, &NtPathName, 0, 0);
  v10 = v9 != 0;
  v11 = v9 == 0 ? 0xC0000001 : 0;
  if ( v9 )
  {
LABEL_5:
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a3;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = NtCreateFile(FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0x20u, 0, 0);
  }
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return v11;
}

```

## disassembly

```asm
0x18001472c  push    rbp
0x18001472e  push    rbx
0x18001472f  push    rsi
0x180014730  push    rdi
0x180014731  lea     rbp, [rsp-1Fh]
0x180014736  sub     rsp, 0B8h
0x18001473d  xorps   xmm0, xmm0
0x180014740  xorps   xmm1, xmm1
0x180014743  mov     rsi, r8
0x180014746  mov     rax, rdx
0x180014749  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x18001474d  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x180014751  movups  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014755  movups  xmmword ptr [rbp+37h+NtPathName.Length], xmm0
0x180014759  movups  xmmword ptr [rbp+37h+IoStatusBlock], xmm1
0x18001475d  test    r8, r8
0x180014760  jnz     short loc_18001478F
0x180014762  xor     r9d, r9d; DirectoryInfo
0x180014765  lea     rdx, [rbp+37h+NtPathName]; NtPathName
0x180014769  mov     rcx, rax; DosPathName
0x18001476c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180014772  test    al, al
0x180014774  mov     cl, al
0x180014776  setnz   dil
0x18001477a  neg     cl
0x18001477c  sbb     ebx, ebx
0x18001477e  not     ebx
0x180014780  and     ebx, 0C0000001h
0x180014786  test    al, al
0x180014788  jnz     short loc_18001479C
0x18001478a  jmp     loc_180014811
0x18001478f  xor     dil, dil
0x180014792  lea     rcx, [rbp+37h+NtPathName]; DestinationString
0x180014796  call    cs:__imp_RtlInitUnicodeString
0x18001479c  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x1800147a0  lea     rax, [rbp+37h+NtPathName]
0x1800147a4  mov     [rsp+0D0h+EaLength], 0; EaLength
0x1800147ac  lea     r9, [rbp+37h+IoStatusBlock]; IoStatusBlock
0x1800147b0  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x1800147b9  lea     r8, [rbp+37h+ObjectAttributes]; ObjectAttributes
0x1800147bd  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800147c5  xorps   xmm0, xmm0
0x1800147c8  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x1800147d0  mov     edx, 100080h; DesiredAccess
0x1800147d5  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x1800147dd  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x1800147e5  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x1800147ee  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x1800147f5  mov     [rbp+37h+ObjectAttributes.RootDirectory], rsi
0x1800147f9  mov     [rbp+37h+ObjectAttributes.Attributes], 40h ; '@'
0x180014800  mov     [rbp+37h+ObjectAttributes.ObjectName], rax
0x180014804  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014809  call    cs:__imp_NtCreateFile
0x18001480f  mov     ebx, eax
0x180014811  test    dil, dil
0x180014814  jz      short loc_18001482F
0x180014816  mov     rcx, gs:60h
0x18001481f  xor     edx, edx; Flags
0x180014821  mov     r8, [rbp+37h+NtPathName.Buffer]; P
0x180014825  mov     rcx, [rcx+30h]; HeapHandle
0x180014829  call    cs:__imp_RtlFreeHeap
0x18001482f  mov     eax, ebx
0x180014831  add     rsp, 0B8h
0x180014838  pop     rdi
0x180014839  pop     rsi
0x18001483a  pop     rbx
0x18001483b  pop     rbp
0x18001483c  retn
```
