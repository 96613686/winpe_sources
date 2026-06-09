# CopyMSIForUpdate(ushort const *,ushort const *,ushort * *)

- ea: `0x180024a88`
- end: `0x180024bf8`
- name: `?CopyMSIForUpdate@@YAJPEBG0PEAPEAG@Z`
- size: `368`
- prototype: `signed int __fastcall(LPCWSTR lpExistingFileName, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18002673c`

## callees

- `0x18000a01c`
- `0x18001ec1c`
- `0x180024a88`
- `0x1800266f4`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024ad8`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180024ace`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180024ace`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180024bb8`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180024bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024bc5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024b77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024b77`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall CopyMSIForUpdate(LPCWSTR lpExistingFileName, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  DWORD TempPathW; // eax
  signed int result; // eax
  size_t v8; // rdx
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  int v12; // edi
  size_t pcchLength[2]; // [rsp+20h] [rbp-2E8h] BYREF
  WCHAR Buffer[344]; // [rsp+30h] [rbp-2D8h] BYREF

  pcchLength[0] = 0;
  *a3 = 0;
  TempPathW = GetTempPathW(0x154u, Buffer);
  if ( !TempPathW )
  {
LABEL_2:
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  if ( TempPathW > 0x154 )
    return -2147418113;
  result = StringCchCatW(Buffer, 0x154u, a2);
  if ( result >= 0 )
  {
    result = StringCchCatW(Buffer, 0x154u, L".MSI");
    if ( result >= 0 )
    {
      result = StringLengthWorkerW(Buffer, v8, pcchLength);
      if ( result >= 0 )
      {
        v9 = pcchLength[0] + 1;
        if ( pcchLength[0] + 1 < pcchLength[0] )
          return -2147024362;
        v10 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v9, 2u));
        v11 = v10;
        if ( !v10 )
          return -2147024882;
        v12 = StringCchCopyW(v10, v9, Buffer);
        if ( v12 < 0 )
        {
          CoTaskMemFree(v11);
          return v12;
        }
        if ( CopyFileW(lpExistingFileName, v11, 0) )
        {
          *a3 = v11;
          return 0;
        }
        CoTaskMemFree(v11);
        goto LABEL_2;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024a88  mov     [rsp+arg_18], rbx
0x180024a8d  push    rbp
0x180024a8e  push    rsi
0x180024a8f  push    rdi
0x180024a90  sub     rsp, 2F0h
0x180024a97  mov     rax, cs:__security_cookie
0x180024a9e  xor     rax, rsp
0x180024aa1  mov     [rsp+308h+var_28], rax
0x180024aa9  mov     rbx, rdx
0x180024aac  mov     [rsp+308h+pcchLength], 0
0x180024ab5  mov     rbp, rcx
0x180024ab8  mov     qword ptr [r8], 0
0x180024abf  mov     edi, 154h
0x180024ac4  lea     rdx, [rsp+308h+Buffer]; lpBuffer
0x180024ac9  mov     ecx, edi; nBufferLength
0x180024acb  mov     rsi, r8
0x180024ace  call    cs:__imp_GetTempPathW
0x180024ad4  test    eax, eax
0x180024ad6  jnz     short loc_180024AF3
0x180024ad8  call    cs:__imp_GetLastError
0x180024ade  test    eax, eax
0x180024ae0  jle     loc_180024BD5
0x180024ae6  movzx   eax, ax
0x180024ae9  or      eax, 80070000h
0x180024aee  jmp     loc_180024BD5
0x180024af3  cmp     eax, edi
0x180024af5  jbe     short loc_180024B01
0x180024af7  mov     eax, 8000FFFFh
0x180024afc  jmp     loc_180024BD5
0x180024b01  mov     r8, rbx; unsigned __int16 *
0x180024b04  lea     rcx, [rsp+308h+Buffer]; unsigned __int16 *
0x180024b09  mov     rdx, rdi; unsigned __int64
0x180024b0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024b11  test    eax, eax
0x180024b13  js      loc_180024BD5
0x180024b19  lea     r8, aMsi; ".MSI"
0x180024b20  mov     rdx, rdi; unsigned __int64
0x180024b23  lea     rcx, [rsp+308h+Buffer]; unsigned __int16 *
0x180024b28  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180024b2d  test    eax, eax
0x180024b2f  js      loc_180024BD5
0x180024b35  lea     r8, [rsp+308h+pcchLength]; pcchLength
0x180024b3a  lea     rcx, [rsp+308h+Buffer]; psz
0x180024b3f  call    StringLengthWorkerW
0x180024b44  test    eax, eax
0x180024b46  js      loc_180024BD5
0x180024b4c  mov     rax, [rsp+308h+pcchLength]
0x180024b51  lea     rdi, [rax+1]
0x180024b55  cmp     rdi, rax
0x180024b58  jnb     short loc_180024B61
0x180024b5a  mov     eax, 80070216h
0x180024b5f  jmp     short loc_180024BD5
0x180024b61  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180024b68  mov     eax, 2
0x180024b6d  mul     rdi
0x180024b70  cmovb   rax, rcx
0x180024b74  mov     rcx, rax; cb
0x180024b77  call    cs:__imp_CoTaskMemAlloc
0x180024b7d  mov     rbx, rax
0x180024b80  test    rax, rax
0x180024b83  jnz     short loc_180024B8C
0x180024b85  mov     eax, 8007000Eh
0x180024b8a  jmp     short loc_180024BD5
0x180024b8c  lea     r8, [rsp+308h+Buffer]; unsigned __int16 *
0x180024b91  mov     rdx, rdi; unsigned __int64
0x180024b94  mov     rcx, rbx; unsigned __int16 *
0x180024b97  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180024b9c  mov     edi, eax
0x180024b9e  test    eax, eax
0x180024ba0  jns     short loc_180024BAF
0x180024ba2  mov     rcx, rbx; pv
0x180024ba5  call    cs:__imp_CoTaskMemFree
0x180024bab  mov     eax, edi
0x180024bad  jmp     short loc_180024BD5
0x180024baf  xor     r8d, r8d; bFailIfExists
0x180024bb2  mov     rdx, rbx; lpNewFileName
0x180024bb5  mov     rcx, rbp; lpExistingFileName
0x180024bb8  call    cs:__imp_CopyFileW
0x180024bbe  test    eax, eax
0x180024bc0  jnz     short loc_180024BD0
0x180024bc2  mov     rcx, rbx; pv
0x180024bc5  call    cs:__imp_CoTaskMemFree
0x180024bcb  jmp     loc_180024AD8
0x180024bd0  mov     [rsi], rbx
0x180024bd3  xor     eax, eax
0x180024bd5  mov     rcx, [rsp+308h+var_28]
0x180024bdd  xor     rcx, rsp; StackCookie
0x180024be0  call    __security_check_cookie
0x180024be5  mov     rbx, [rsp+308h+arg_18]
0x180024bed  add     rsp, 2F0h
0x180024bf4  pop     rdi
0x180024bf5  pop     rsi
0x180024bf6  pop     rbp
0x180024bf7  retn
```
