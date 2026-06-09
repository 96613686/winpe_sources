# CNtfsStorage::InitFromName(ushort const *,void *,int,ulong)

- ea: `0x180053b80`
- end: `0x180053c6a`
- name: `?InitFromName@CNtfsStorage@@QEAAJPEBGPEAXHK@Z`
- size: `234`
- prototype: `__int64 __fastcall(CNtfsStorage *__hidden this, const unsigned __int16 *, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180053d30`

## callees

- `0x180034068`
- `0x18003bc28`
- `0x180053aa4`
- `0x180053b80`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180053c46`
- `ntdll!RtlFreeHeap` at `0x180053c46`
- `ntdll!NtClose` at `0x180053c57`
- `ntdll!NtClose` at `0x180053c57`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180053bb6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180053bb6`

## pseudocode

```c
__int64 __fastcall CNtfsStorage::InitFromName(CNtfsStorage *this, const unsigned __int16 *a2, void *a3, int a4)
{
  int v8; // ebx
  PWSTR Buffer; // rdi
  int v10; // r9d
  const unsigned __int16 *v11; // r8
  unsigned int v13; // [rsp+20h] [rbp-68h]
  unsigned int v14; // [rsp+28h] [rbp-60h]
  HANDLE Handle; // [rsp+40h] [rbp-48h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+48h] [rbp-40h] BYREF

  Handle = (HANDLE)-1LL;
  NtPathName = 0;
  if ( RtlDosPathNameToNtPathName_U(a2, &NtPathName, 0, 0) )
  {
    Buffer = NtPathName.Buffer;
    v10 = 0;
    if ( a4 && (*((_DWORD *)this + 18) & 0x1000) != 0 )
      v10 = 4096;
    v8 = CNtfsStorage::OpenNtFileHandle(&NtPathName, 0, a3, v10 | 0x40u, 0, a4, &Handle);
    if ( v8 >= 0 )
    {
      *((_WORD *)this + 38) = GetDriveLetter(a2);
      v8 = CNtfsStorage::InitFromMainStreamHandle(this, &Handle, v11, a4, v13, v14);
    }
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( Handle != (HANDLE)-1LL )
      NtClose(Handle);
  }
  else
  {
    return (unsigned int)-2147286788;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180053b80  push    rbx
0x180053b82  push    rbp
0x180053b83  push    rsi
0x180053b84  push    rdi
0x180053b85  push    r14
0x180053b87  sub     rsp, 60h
0x180053b8b  mov     r14, rdx
0x180053b8e  mov     [rsp+88h+Handle], 0FFFFFFFFFFFFFFFFh
0x180053b97  mov     esi, r9d
0x180053b9a  lea     rdx, [rsp+88h+NtPathName]; NtPathName
0x180053b9f  mov     rbx, r8
0x180053ba2  mov     rbp, rcx
0x180053ba5  xorps   xmm0, xmm0
0x180053ba8  mov     rcx, r14; DosPathName
0x180053bab  xor     r9d, r9d; DirectoryInfo
0x180053bae  xor     r8d, r8d; NtFileNamePart
0x180053bb1  movups  xmmword ptr [rsp+88h+NtPathName.Length], xmm0
0x180053bb6  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180053bbc  test    al, al
0x180053bbe  jnz     short loc_180053BCA
0x180053bc0  mov     ebx, 800300FCh
0x180053bc5  jmp     loc_180053C5D
0x180053bca  mov     rdi, [rsp+88h+NtPathName.Buffer]
0x180053bcf  xor     r9d, r9d
0x180053bd2  test    esi, esi
0x180053bd4  jz      short loc_180053BE2
0x180053bd6  mov     eax, 1000h
0x180053bdb  test    [rbp+48h], eax
0x180053bde  cmovnz  r9d, eax
0x180053be2  lea     rax, [rsp+88h+Handle]
0x180053be7  or      r9d, 40h; unsigned int
0x180053beb  mov     [rsp+88h+var_58], rax; void **
0x180053bf0  lea     rcx, [rsp+88h+NtPathName]; struct _UNICODE_STRING *
0x180053bf5  mov     [rsp+88h+var_60], esi; unsigned int
0x180053bf9  mov     r8, rbx; void *
0x180053bfc  xor     edx, edx; void *
0x180053bfe  mov     [rsp+88h+var_68], 0; unsigned int
0x180053c06  call    ?OpenNtFileHandle@CNtfsStorage@@CAJAEBU_UNICODE_STRING@@PEAX1KKHPEAPEAX@Z; CNtfsStorage::OpenNtFileHandle(_UNICODE_STRING const &,void *,void *,ulong,ulong,int,void * *)
0x180053c0b  mov     ebx, eax
0x180053c0d  test    eax, eax
0x180053c0f  js      short loc_180053C2F
0x180053c11  mov     rcx, r14; unsigned __int16 *
0x180053c14  call    ?GetDriveLetter@@YAGPEBG@Z; GetDriveLetter(ushort const *)
0x180053c19  mov     r9d, esi; int
0x180053c1c  mov     [rbp+4Ch], ax
0x180053c20  lea     rdx, [rsp+88h+Handle]; void **
0x180053c25  mov     rcx, rbp; this
0x180053c28  call    ?InitFromMainStreamHandle@CNtfsStorage@@QEAAJPEAPEAXPEBGHKK@Z; CNtfsStorage::InitFromMainStreamHandle(void * *,ushort const *,int,ulong,ulong)
0x180053c2d  mov     ebx, eax
0x180053c2f  test    rdi, rdi
0x180053c32  jz      short loc_180053C4C
0x180053c34  mov     rcx, gs:60h
0x180053c3d  mov     r8, rdi; P
0x180053c40  xor     edx, edx; Flags
0x180053c42  mov     rcx, [rcx+30h]; HeapHandle
0x180053c46  call    cs:__imp_RtlFreeHeap
0x180053c4c  mov     rcx, [rsp+88h+Handle]; Handle
0x180053c51  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180053c55  jz      short loc_180053C5D
0x180053c57  call    cs:__imp_NtClose
0x180053c5d  mov     eax, ebx
0x180053c5f  add     rsp, 60h
0x180053c63  pop     r14
0x180053c65  pop     rdi
0x180053c66  pop     rsi
0x180053c67  pop     rbp
0x180053c68  pop     rbx
0x180053c69  retn
```
