# RegScan::GetLongFileName(ushort *,ushort * *)

- ea: `0x180050a34`
- end: `0x180050ad3`
- name: `?GetLongFileName@RegScan@@AEAAJPEAGPEAPEAG@Z`
- size: `159`
- prototype: `int(RegScan *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050adc`
- `0x180052654`

## callees

- `0x180050a34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050abc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050a8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050a5e`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180050a52`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180050aaf`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180050a52`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180050aaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall RegScan::GetLongFileName(RegScan *this, unsigned __int16 *a2, unsigned __int16 **a3)
{
  DWORD LongPathNameW; // eax
  DWORD v6; // edi
  int result; // eax
  unsigned __int16 *v8; // rbx

  *a3 = 0;
  LongPathNameW = GetLongPathNameW(a2, 0, 0);
  v6 = LongPathNameW;
  if ( LongPathNameW )
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(LongPathNameW + 2, 2u));
    if ( !v8 )
      return -2147024882;
    *v8 = 0;
    if ( GetLongPathNameW(a2, v8, v6 + 1) )
    {
      *a3 = v8;
      return 0;
    }
    CoTaskMemFree(v8);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180050a34  push    rbx
0x180050a36  push    rbp
0x180050a37  push    rsi
0x180050a38  push    rdi
0x180050a39  sub     rsp, 28h
0x180050a3d  mov     rsi, r8
0x180050a40  mov     rbp, rdx
0x180050a43  mov     qword ptr [r8], 0
0x180050a4a  xor     r8d, r8d; cchBuffer
0x180050a4d  xor     edx, edx; lpszLongPath
0x180050a4f  mov     rcx, rbp; lpszShortPath
0x180050a52  call    cs:__imp_GetLongPathNameW
0x180050a58  mov     edi, eax
0x180050a5a  test    eax, eax
0x180050a5c  jnz     short loc_180050A72
0x180050a5e  call    cs:__imp_GetLastError
0x180050a64  test    eax, eax
0x180050a66  jle     short loc_180050ACA
0x180050a68  movzx   eax, ax
0x180050a6b  or      eax, 80070000h
0x180050a70  jmp     short loc_180050ACA
0x180050a72  lea     ecx, [rax+2]
0x180050a75  mov     eax, 2
0x180050a7a  mul     rcx
0x180050a7d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180050a84  cmovb   rax, rcx
0x180050a88  mov     rcx, rax; cb
0x180050a8b  call    cs:__imp_CoTaskMemAlloc
0x180050a91  mov     rbx, rax
0x180050a94  test    rax, rax
0x180050a97  jnz     short loc_180050AA0
0x180050a99  mov     eax, 8007000Eh
0x180050a9e  jmp     short loc_180050ACA
0x180050aa0  xor     eax, eax
0x180050aa2  mov     [rbx], ax
0x180050aa5  lea     r8d, [rdi+1]; cchBuffer
0x180050aa9  mov     rdx, rbx; lpszLongPath
0x180050aac  mov     rcx, rbp; lpszShortPath
0x180050aaf  call    cs:__imp_GetLongPathNameW
0x180050ab5  test    eax, eax
0x180050ab7  jnz     short loc_180050AC5
0x180050ab9  mov     rcx, rbx; pv
0x180050abc  call    cs:__imp_CoTaskMemFree
0x180050ac2  nop
0x180050ac3  jmp     short loc_180050A5E
0x180050ac5  mov     [rsi], rbx
0x180050ac8  xor     eax, eax
0x180050aca  add     rsp, 28h
0x180050ace  pop     rdi
0x180050acf  pop     rsi
0x180050ad0  pop     rbp
0x180050ad1  pop     rbx
0x180050ad2  retn
```
