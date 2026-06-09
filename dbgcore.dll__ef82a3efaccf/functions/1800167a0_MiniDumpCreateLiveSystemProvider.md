# MiniDumpCreateLiveSystemProvider

- ea: `0x1800167a0`
- end: `0x1800168da`
- name: `MiniDumpCreateLiveSystemProvider`
- size: `314`
- prototype: `__int64 __fastcall(struct MiniDumpAllocationProvider *, struct MiniDumpStatusProvider *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800062f4`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800167a0`
- `0x180023114`
- `0x1800251f4`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x1800167f2`
- `ntdll!RtlGetVersion` at `0x1800167f2`

## pseudocode

```c
signed int __fastcall MiniDumpCreateLiveSystemProvider(
        struct MiniDumpAllocationProvider *a1,
        struct MiniDumpStatusProvider *a2,
        NtWin32LiveSystemProvider **a3)
{
  NTSTATUS Version; // eax
  signed int result; // eax
  DWORD dwBuildNumber; // edi
  _QWORD *v9; // rax
  NtWin32LiveSystemProvider *v10; // rax
  NtWin32LiveSystemProvider *v11; // rbx
  int v12; // edi
  struct _OSVERSIONINFOW v13; // [rsp+20h] [rbp-268h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+140h] [rbp-148h] BYREF

  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
    return Version | 0x10000000;
  if ( VersionInformation.dwPlatformId != 2 )
    return -2147024809;
  memset_0(&v13.dwMajorVersion, 0, 0x110u);
  v13.dwOSVersionInfoSize = 276;
  result = NtWin32LiveSystemProvider::GetTrueNTVersion(&v13);
  if ( result >= 0 )
  {
    dwBuildNumber = v13.dwBuildNumber;
    v9 = (_QWORD *)(*(__int64 (__fastcall **)(struct MiniDumpAllocationProvider *, __int64))(*(_QWORD *)a1 + 8LL))(
                     a1,
                     1112);
    if ( v9 )
      *v9 = a1;
    if ( v9 == (_QWORD *)-8LL )
      return -2147024882;
    v10 = NtWin32LiveSystemProvider::NtWin32LiveSystemProvider(
            (NtWin32LiveSystemProvider *)(v9 + 1),
            a1,
            a2,
            dwBuildNumber);
    v11 = v10;
    if ( !v10 )
    {
      return -2147024882;
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(NtWin32LiveSystemProvider *))(*(_QWORD *)v10 + 568LL))(v10);
      if ( v12 )
      {
        (**(void (__fastcall ***)(NtWin32LiveSystemProvider *))v11)(v11);
        return v12;
      }
      else
      {
        *a3 = v11;
        return 0;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800167a0  mov     [rsp+arg_18], rbx
0x1800167a5  push    rbp
0x1800167a6  push    rsi
0x1800167a7  push    rdi
0x1800167a8  sub     rsp, 270h
0x1800167af  mov     rax, cs:__security_cookie
0x1800167b6  xor     rax, rsp
0x1800167b9  mov     [rsp+288h+var_28], rax
0x1800167c1  mov     rsi, r8
0x1800167c4  mov     rbp, rdx
0x1800167c7  mov     rbx, rcx
0x1800167ca  xor     edx, edx; Val
0x1800167cc  mov     r8d, 118h; Size
0x1800167d2  lea     rcx, [rsp+288h+VersionInformation.dwMajorVersion]; void *
0x1800167da  call    memset_0
0x1800167df  lea     rcx, [rsp+288h+VersionInformation]; lpVersionInformation
0x1800167e7  mov     [rsp+288h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800167f2  call    cs:__imp_RtlGetVersion
0x1800167f8  test    eax, eax
0x1800167fa  jns     short loc_180016805
0x1800167fc  bts     eax, 1Ch
0x180016800  jmp     loc_1800168B7
0x180016805  cmp     [rsp+288h+VersionInformation.dwPlatformId], 2
0x18001680d  jnz     loc_1800168B2
0x180016813  xor     edx, edx; Val
0x180016815  lea     rcx, [rsp+288h+var_268.dwMajorVersion]; void *
0x18001681a  mov     r8d, 110h; Size
0x180016820  call    memset_0
0x180016825  lea     rcx, [rsp+288h+var_268]; struct _OSVERSIONINFOW *
0x18001682a  mov     [rsp+288h+var_268.dwOSVersionInfoSize], 114h
0x180016832  call    ?GetTrueNTVersion@NtWin32LiveSystemProvider@@SAJPEAU_OSVERSIONINFOW@@@Z; NtWin32LiveSystemProvider::GetTrueNTVersion(_OSVERSIONINFOW *)
0x180016837  test    eax, eax
0x180016839  js      short loc_1800168B7
0x18001683b  mov     rax, [rbx]
0x18001683e  mov     edx, 458h
0x180016843  mov     edi, [rsp+288h+var_268.dwBuildNumber]
0x180016847  mov     rcx, rbx
0x18001684a  mov     rax, [rax+8]
0x18001684e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016853  test    rax, rax
0x180016856  jz      short loc_18001685B
0x180016858  mov     [rax], rbx
0x18001685b  lea     rcx, [rax+8]; this
0x18001685f  test    rcx, rcx
0x180016862  jz      short loc_1800168AB
0x180016864  mov     r9d, edi; unsigned int
0x180016867  mov     r8, rbp; struct MiniDumpStatusProvider *
0x18001686a  mov     rdx, rbx; struct MiniDumpAllocationProvider *
0x18001686d  call    ??0NtWin32LiveSystemProvider@@QEAA@PEAVMiniDumpAllocationProvider@@PEAVMiniDumpStatusProvider@@K@Z; NtWin32LiveSystemProvider::NtWin32LiveSystemProvider(MiniDumpAllocationProvider *,MiniDumpStatusProvider *,ulong)
0x180016872  mov     rbx, rax
0x180016875  test    rax, rax
0x180016878  jz      short loc_1800168AB
0x18001687a  mov     rcx, [rax]
0x18001687d  mov     rax, [rcx+238h]
0x180016884  mov     rcx, rbx
0x180016887  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001688c  mov     edi, eax
0x18001688e  test    eax, eax
0x180016890  jz      short loc_1800168A4
0x180016892  mov     rcx, [rbx]
0x180016895  mov     rax, [rcx]
0x180016898  mov     rcx, rbx
0x18001689b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168a0  mov     eax, edi
0x1800168a2  jmp     short loc_1800168B7
0x1800168a4  mov     [rsi], rbx
0x1800168a7  xor     eax, eax
0x1800168a9  jmp     short loc_1800168B7
0x1800168ab  mov     eax, 8007000Eh
0x1800168b0  jmp     short loc_1800168B7
0x1800168b2  mov     eax, 80070057h
0x1800168b7  mov     rcx, [rsp+288h+var_28]
0x1800168bf  xor     rcx, rsp; StackCookie
0x1800168c2  call    __security_check_cookie
0x1800168c7  mov     rbx, [rsp+288h+arg_18]
0x1800168cf  add     rsp, 270h
0x1800168d6  pop     rdi
0x1800168d7  pop     rsi
0x1800168d8  pop     rbp
0x1800168d9  retn
```
