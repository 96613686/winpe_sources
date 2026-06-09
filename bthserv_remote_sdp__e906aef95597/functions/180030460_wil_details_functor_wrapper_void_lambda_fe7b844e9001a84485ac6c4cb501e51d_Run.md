# wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run

- ea: `0x180030460`
- end: `0x180030529`
- name: `wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002ddec`

## callees

- `0x180003740`
- `0x180011b9c`
- `0x180030460`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800304e3`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800304b7`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800304b7`

## string_xrefs

- `0x180030514`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_fe7b844e9001a84485ac6c4cb501e51d___::Run(__int64 a1)
{
  __int64 v1; // rbx
  __int64 *v2; // rcx
  __int64 v3; // rcx
  signed int LastError; // eax
  unsigned int v6; // ecx
  unsigned int v7; // eax
  int v8; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD BytesReturned; // [rsp+50h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 8);
  BytesReturned = 0;
  v2 = **(__int64 ***)v1;
  if ( v2 )
    v3 = *v2;
  else
    v3 = -1;
  if ( !DeviceIoControl(
          (HANDLE)v3,
          0x4111C4u,
          **(LPVOID **)(v1 + 8),
          **(_DWORD **)(v1 + 16),
          0,
          0,
          &BytesReturned,
          **(LPOVERLAPPED **)(v1 + 24))
    && GetLastError() != 997 )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    **(_DWORD **)(v1 + 32) = v6;
    v7 = wil::verify_hresult<long>(**(unsigned int **)(v1 + 32));
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v7,
      v8);
  }
  return 0;
}

```

## disassembly

```asm
0x180030460  push    rbx
0x180030462  sub     rsp, 40h
0x180030466  mov     rbx, [rcx+8]
0x18003046a  and     [rsp+48h+BytesReturned], 0
0x18003046f  mov     rax, [rbx+18h]
0x180030473  mov     rdx, [rax]
0x180030476  mov     rax, [rbx+10h]
0x18003047a  mov     r9d, [rax]; nInBufferSize
0x18003047d  mov     rax, [rbx+8]
0x180030481  mov     r8, [rax]; lpInBuffer
0x180030484  mov     rax, [rbx]
0x180030487  mov     rcx, [rax]
0x18003048a  test    rcx, rcx
0x18003048d  jz      short loc_180030494
0x18003048f  mov     rcx, [rcx]
0x180030492  jmp     short loc_180030498
0x180030494  or      rcx, 0FFFFFFFFFFFFFFFFh; hDevice
0x180030498  mov     [rsp+48h+lpOverlapped], rdx; lpOverlapped
0x18003049d  lea     rax, [rsp+48h+BytesReturned]
0x1800304a2  mov     [rsp+48h+lpBytesReturned], rax; lpBytesReturned
0x1800304a7  mov     edx, 4111C4h; dwIoControlCode
0x1800304ac  and     [rsp+48h+var_20], 0
0x1800304b1  and     [rsp+48h+var_28], 0
0x1800304b7  call    cs:__imp_DeviceIoControl
0x1800304be  nop     dword ptr [rax+rax+00h]
0x1800304c3  test    eax, eax
0x1800304c5  jnz     short loc_1800304DA
0x1800304c7  call    cs:__imp_GetLastError
0x1800304ce  nop     dword ptr [rax+rax+00h]
0x1800304d3  cmp     eax, 3E5h
0x1800304d8  jnz     short loc_1800304E3
0x1800304da  xor     eax, eax
0x1800304dc  add     rsp, 40h
0x1800304e0  pop     rbx
0x1800304e1  retn
0x1800304e3  call    cs:__imp_GetLastError
0x1800304ea  nop     dword ptr [rax+rax+00h]
0x1800304ef  mov     ecx, eax
0x1800304f1  test    eax, eax
0x1800304f3  jle     short loc_1800304FE
0x1800304f5  movzx   ecx, ax
0x1800304f8  or      ecx, 80070000h
0x1800304fe  mov     rax, [rbx+20h]
0x180030502  mov     [rax], ecx
0x180030504  mov     rcx, [rbx+20h]
0x180030508  mov     ecx, [rcx]
0x18003050a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003050f  mov     rcx, [rsp+48h]; this
0x180030514  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18003051b  mov     r9d, eax; char *
0x18003051e  mov     edx, 0D6h; void *
0x180030523  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
