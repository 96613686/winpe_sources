# CSMBSecurityInformation::SetSecurity(ulong,void *)

- ea: `0x1800237c0`
- end: `0x1800238d0`
- name: `?SetSecurity@CSMBSecurityInformation@@EEAAJKPEAX@Z`
- size: `272`
- prototype: `int(CSMBSecurityInformation *__hidden this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800237c0`
- `0x1800238d8`
- `0x18002637c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800237e9`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x1800237e9`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023815`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180023815`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023822`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180023822`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002386f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002386f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023833`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023833`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023887`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800238ab`

## pseudocode

```c
__int64 __fastcall CSMBSecurityInformation::SetSecurity(HLOCAL **this, __int64 a2, void *a3)
{
  HLOCAL v3; // rbp
  int Error; // ebx
  HLOCAL v7; // rsi
  DWORD Size; // [rsp+20h] [rbp-28h] BYREF
  DWORD Size_4; // [rsp+24h] [rbp-24h] BYREF
  WORD pControl; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  if ( !a3 )
  {
    Error = 0;
LABEL_16:
    LocalFree(*this[55]);
    *this[55] = v3;
    return (unsigned int)Error;
  }
  if ( IsValidSecurityDescriptor(a3) )
  {
    pControl = 0;
    Size_4 = 0;
    if ( GetSecurityDescriptorControl(a3, &pControl, &Size_4) )
    {
      Size = GetSecurityDescriptorLength(a3);
      v7 = LocalAlloc(0x40u, Size);
      if ( v7 )
      {
        Error = 0;
        if ( (pControl & 0x8000u) == 0 )
        {
          if ( !MakeSelfRelativeSD(a3, v7, &Size) )
          {
            Error = ResultFromLastError();
            if ( Error < 0 )
            {
              LocalFree(v7);
              return (unsigned int)Error;
            }
          }
        }
        else
        {
          memcpy_0(v7, a3, Size);
        }
        v3 = v7;
      }
      else
      {
        Error = -2147024882;
      }
    }
    else
    {
      Error = ResultFromLastError();
    }
    if ( Error >= 0 )
      goto LABEL_16;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800237c0  mov     [rsp+arg_0], rbx
0x1800237c5  mov     [rsp+arg_8], rbp
0x1800237ca  push    rsi
0x1800237cb  push    rdi
0x1800237cc  push    r14
0x1800237ce  sub     rsp, 30h
0x1800237d2  xor     ebp, ebp
0x1800237d4  mov     rdi, r8
0x1800237d7  mov     r14, rcx
0x1800237da  test    r8, r8
0x1800237dd  jnz     short loc_1800237E6
0x1800237df  xor     ebx, ebx
0x1800237e1  jmp     loc_1800238A1
0x1800237e6  mov     rcx, rdi; pSecurityDescriptor
0x1800237e9  call    cs:__imp_IsValidSecurityDescriptor
0x1800237ef  test    eax, eax
0x1800237f1  jnz     short loc_1800237FD
0x1800237f3  mov     ebx, 80070057h
0x1800237f8  jmp     loc_1800238BB
0x1800237fd  xor     eax, eax
0x1800237ff  lea     r8, [rsp+48h+Size+4]; lpdwRevision
0x180023804  lea     rdx, [rsp+48h+pControl]; pControl
0x180023809  mov     [rsp+48h+pControl], ax
0x18002380e  mov     rcx, rdi; pSecurityDescriptor
0x180023811  mov     [rsp+48h+Size+4], eax
0x180023815  call    cs:__imp_GetSecurityDescriptorControl
0x18002381b  test    eax, eax
0x18002381d  jz      short loc_180023896
0x18002381f  mov     rcx, rdi; pSecurityDescriptor
0x180023822  call    cs:__imp_GetSecurityDescriptorLength
0x180023828  mov     edx, eax; uBytes
0x18002382a  mov     ecx, 40h ; '@'; uFlags
0x18002382f  mov     [rsp+48h+Size], edx
0x180023833  call    cs:__imp_LocalAlloc
0x180023839  mov     rsi, rax
0x18002383c  test    rax, rax
0x18002383f  jz      short loc_18002388F
0x180023841  xor     ebx, ebx
0x180023843  mov     eax, 8000h
0x180023848  test    [rsp+48h+pControl], ax
0x18002384d  jz      short loc_180023864
0x18002384f  mov     r8d, [rsp+48h+Size]; Size
0x180023854  mov     rdx, rdi; Src
0x180023857  mov     rcx, rsi; void *
0x18002385a  call    memcpy_0
0x18002385f  mov     rbp, rsi
0x180023862  jmp     short loc_18002389D
0x180023864  lea     r8, [rsp+48h+Size]; lpdwBufferLength
0x180023869  mov     rdx, rsi; pSelfRelativeSecurityDescriptor
0x18002386c  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18002386f  call    cs:__imp_MakeSelfRelativeSD
0x180023875  test    eax, eax
0x180023877  jnz     short loc_18002385F
0x180023879  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002387e  mov     ebx, eax
0x180023880  test    eax, eax
0x180023882  jns     short loc_18002385F
0x180023884  mov     rcx, rsi; hMem
0x180023887  call    cs:__imp_LocalFree
0x18002388d  jmp     short loc_1800238BB
0x18002388f  mov     ebx, 8007000Eh
0x180023894  jmp     short loc_18002389D
0x180023896  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002389b  mov     ebx, eax
0x18002389d  test    ebx, ebx
0x18002389f  js      short loc_1800238BB
0x1800238a1  mov     rcx, [r14+1B8h]
0x1800238a8  mov     rcx, [rcx]; hMem
0x1800238ab  call    cs:__imp_LocalFree
0x1800238b1  mov     rcx, [r14+1B8h]
0x1800238b8  mov     [rcx], rbp
0x1800238bb  mov     rbp, [rsp+48h+arg_8]
0x1800238c0  mov     eax, ebx
0x1800238c2  mov     rbx, [rsp+48h+arg_0]
0x1800238c7  add     rsp, 30h
0x1800238cb  pop     r14
0x1800238cd  pop     rdi
0x1800238ce  pop     rsi
0x1800238cf  retn
```
