# RtlpQueryDiskSpacePolicyByHandle

- ea: `0x1800027c0`
- end: `0x180002880`
- name: `RtlpQueryDiskSpacePolicyByHandle`
- size: `192`
- prototype: `NTSTATUS __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180002658`

## callees

- `0x1800027c0`
- `0x1800029d0`

## import_xrefs

- `ntdll!NtQueryVolumeInformationFile` at `0x180002805`
- `ntdll!NtQueryVolumeInformationFile` at `0x180002805`

## pseudocode

```c
NTSTATUS __fastcall RtlpQueryDiskSpacePolicyByHandle(void *a1, int *a2)
{
  NTSTATUS result; // eax
  unsigned __int64 v4; // rcx
  int v5; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  __int128 FsInformation; // [rsp+40h] [rbp-38h] BYREF
  __int128 v8; // [rsp+50h] [rbp-28h]

  IoStatusBlock = 0;
  FsInformation = 0;
  v8 = 0;
  result = NtQueryVolumeInformationFile(a1, &IoStatusBlock, &FsInformation, 0x20u, FileFsFullSizeInformation);
  if ( result >= 0 )
  {
    v4 = FsInformation * DWORD2(v8) * (unsigned __int64)HIDWORD(v8);
    if ( v4 > 0x200000000LL )
    {
      if ( v4 > 0x800000000LL )
      {
        v5 = 20;
        if ( v4 <= 0x2000000000LL )
          v5 = 15;
        *a2 = v5;
      }
      else
      {
        *a2 = 10;
      }
    }
    else
    {
      *a2 = 5;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800027c0  push    rbx
0x1800027c2  sub     rsp, 70h
0x1800027c6  mov     rax, cs:__security_cookie
0x1800027cd  xor     rax, rsp
0x1800027d0  mov     [rsp+78h+var_18], rax
0x1800027d5  xorps   xmm1, xmm1
0x1800027d8  mov     [rsp+78h+FsInformationClass], 7; FsInformationClass
0x1800027e0  mov     rbx, rdx
0x1800027e3  lea     r8, [rsp+78h+FsInformation]; FsInformation
0x1800027e8  xorps   xmm0, xmm0
0x1800027eb  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x1800027f0  mov     r9d, 20h ; ' '; Length
0x1800027f6  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x1800027fb  movups  [rsp+78h+FsInformation], xmm1
0x180002800  movups  [rsp+78h+var_28], xmm1
0x180002805  call    cs:__imp_NtQueryVolumeInformationFile
0x18000280b  test    eax, eax
0x18000280d  js      short loc_18000286D
0x18000280f  mov     eax, dword ptr [rsp+78h+var_28+8]
0x180002813  mov     ecx, dword ptr [rsp+78h+var_28+0Ch]
0x180002817  imul    rcx, rax
0x18000281b  mov     rax, 200000000h
0x180002825  imul    rcx, qword ptr [rsp+78h+FsInformation]
0x18000282b  cmp     rcx, rax
0x18000282e  ja      short loc_180002838
0x180002830  mov     dword ptr [rbx], 5
0x180002836  jmp     short loc_18000286B
0x180002838  mov     rax, 800000000h
0x180002842  cmp     rcx, rax
0x180002845  ja      short loc_18000284F
0x180002847  mov     dword ptr [rbx], 0Ah
0x18000284d  jmp     short loc_18000286B
0x18000284f  mov     eax, 14h
0x180002854  mov     rdx, 2000000000h
0x18000285e  cmp     rcx, rdx
0x180002861  lea     r8d, [rax-5]
0x180002865  cmovbe  eax, r8d
0x180002869  mov     [rbx], eax
0x18000286b  xor     eax, eax
0x18000286d  mov     rcx, [rsp+78h+var_18]
0x180002872  xor     rcx, rsp; StackCookie
0x180002875  call    __security_check_cookie
0x18000287a  add     rsp, 70h
0x18000287e  pop     rbx
0x18000287f  retn
```
