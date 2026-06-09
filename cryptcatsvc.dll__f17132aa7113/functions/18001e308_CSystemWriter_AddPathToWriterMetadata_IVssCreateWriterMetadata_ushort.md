# CSystemWriter::AddPathToWriterMetadata(IVssCreateWriterMetadata *,ushort *)

- ea: `0x18001e308`
- end: `0x18001e393`
- name: `?AddPathToWriterMetadata@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAG@Z`
- size: `139`
- prototype: `bool(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001e124`
- `0x18001e1d4`

## callees

- `0x180006e54`
- `0x18001e308`
- `0x18001ec34`
- `0x180022010`

## string_xrefs

- `0x18001e36e`: `AddCoreCbsFiles : AddPathToWriterMetadata : AddFilesToFileGroup failed.`

## pseudocode

```c
char __fastcall CSystemWriter::AddPathToWriterMetadata(
        CSystemWriter *this,
        struct IVssCreateWriterMetadata *a2,
        unsigned __int16 *a3)
{
  char v5; // bl
  unsigned int v6; // eax
  char v8; // [rsp+28h] [rbp-30h]

  v5 = 1;
  if ( (unsigned int)VerifyDirectoryPath(a3) )
  {
    v8 = 1;
    v6 = (*(__int64 (__fastcall **)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, unsigned __int16 *, const wchar_t *, char, _QWORD, int))(*(_QWORD *)a2 + 40LL))(
           a2,
           0,
           L"System Files",
           a3,
           L"*.*",
           v8,
           0,
           3855);
    if ( v6 )
    {
      CSystemWriter::LogSystemErrorEvent(
        0x201u,
        L"AddCoreCbsFiles : AddPathToWriterMetadata : AddFilesToFileGroup failed.",
        v6);
      return 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18001e308  mov     [rsp+arg_0], rbx
0x18001e30d  mov     [rsp+arg_8], rsi
0x18001e312  push    rdi
0x18001e313  sub     rsp, 50h
0x18001e317  mov     rcx, r8; lpSrc
0x18001e31a  mov     rdi, r8
0x18001e31d  mov     rsi, rdx
0x18001e320  mov     bl, 1
0x18001e322  call    ?VerifyDirectoryPath@@YAHPEAG@Z; VerifyDirectoryPath(ushort *)
0x18001e327  test    eax, eax
0x18001e329  jz      short loc_18001E381
0x18001e32b  mov     rax, [rsi]
0x18001e32e  lea     rcx, asc_180024ED8; "*.*"
0x18001e335  mov     [rsp+58h+var_20], 0F0Fh
0x18001e33d  lea     r8, aSystemFiles; "System Files"
0x18001e344  mov     [rsp+58h+var_28], 0
0x18001e34d  mov     r9, rdi
0x18001e350  mov     [rsp+58h+var_30], bl
0x18001e354  xor     edx, edx
0x18001e356  mov     rax, [rax+28h]
0x18001e35a  mov     [rsp+58h+var_38], rcx
0x18001e35f  mov     rcx, rsi
0x18001e362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e367  test    eax, eax
0x18001e369  jz      short loc_18001E381
0x18001e36b  mov     r8d, eax; unsigned int
0x18001e36e  lea     rdx, aAddcorecbsfile; "AddCoreCbsFiles : AddPathToWriterMetada"...
0x18001e375  mov     ecx, 201h; unsigned int
0x18001e37a  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x18001e37f  xor     bl, bl
0x18001e381  mov     rsi, [rsp+58h+arg_8]
0x18001e386  mov     al, bl
0x18001e388  mov     rbx, [rsp+58h+arg_0]
0x18001e38d  add     rsp, 50h
0x18001e391  pop     rdi
0x18001e392  retn
```
