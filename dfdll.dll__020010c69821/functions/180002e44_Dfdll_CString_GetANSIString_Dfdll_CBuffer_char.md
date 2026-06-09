# Dfdll::CString::GetANSIString(Dfdll::CBuffer<char> &)

- ea: `0x180002e44`
- end: `0x180002f24`
- name: `?GetANSIString@CString@Dfdll@@QEAAJAEAV?$CBuffer@D@2@@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002988`

## callees

- `0x180001fc8`
- `0x180002e44`
- `0x18001efd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002e85`
- `KERNEL32!GetLastError` at `0x180002e85`
- `KERNEL32!WideCharToMultiByte` at `0x180002e7b`
- `KERNEL32!WideCharToMultiByte` at `0x180002ee9`
- `KERNEL32!WideCharToMultiByte` at `0x180002e7b`
- `KERNEL32!WideCharToMultiByte` at `0x180002ee9`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::GetANSIString(__int64 a1, __int64 a2)
{
  int v4; // eax
  signed int LastError; // eax
  signed int v6; // ecx
  int cbMultiByte; // edi

  v4 = WideCharToMultiByte(0, 0, *(LPCWCH *)(a1 + 16), *(_DWORD *)(a1 + 32), 0, 0, 0, 0);
  if ( v4 <= 0 )
    goto LABEL_2;
  v6 = Dfdll::CBufferBase::Allocate((Dfdll::CBufferBase *)a2, v4 + 1);
  if ( v6 < 0 )
    return (unsigned int)v6;
  cbMultiByte = *(_DWORD *)(a2 + 16);
  if ( !cbMultiByte )
    return (unsigned int)-2147024883;
  if ( WideCharToMultiByte(0, 0, *(LPCWCH *)(a1 + 16), *(_DWORD *)(a1 + 32), *(LPSTR *)(a2 + 8), cbMultiByte, 0, 0) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a2 + 40LL))(a2, (unsigned int)(cbMultiByte - 1));
    if ( v6 >= 0 )
      return 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v6 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      return (unsigned int)LastError;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002e44  mov     rax, rsp
0x180002e47  mov     [rax+8], rbx
0x180002e4b  mov     [rax+10h], rbp
0x180002e4f  mov     [rax+18h], rsi
0x180002e53  push    rdi
0x180002e54  sub     rsp, 40h
0x180002e58  mov     r9d, [rcx+20h]; cchWideChar
0x180002e5c  xor     ebp, ebp
0x180002e5e  mov     r8, [rcx+10h]; lpWideCharStr
0x180002e62  mov     rbx, rdx
0x180002e65  mov     [rax-10h], rbp
0x180002e69  mov     rsi, rcx
0x180002e6c  mov     [rax-18h], rbp
0x180002e70  xor     edx, edx; dwFlags
0x180002e72  mov     [rax-20h], ebp
0x180002e75  xor     ecx, ecx; CodePage
0x180002e77  mov     [rax-28h], rbp
0x180002e7b  call    cs:__imp_WideCharToMultiByte
0x180002e81  test    eax, eax
0x180002e83  jg      short loc_180002E9B
0x180002e85  call    cs:__imp_GetLastError
0x180002e8b  movzx   ecx, ax
0x180002e8e  or      ecx, 80070000h
0x180002e94  test    eax, eax
0x180002e96  cmovle  ecx, eax
0x180002e99  jmp     short loc_180002F0D
0x180002e9b  cmp     eax, 0FFFFFFFEh
0x180002e9e  jbe     short loc_180002EA7
0x180002ea0  mov     ecx, 80070216h
0x180002ea5  jmp     short loc_180002F0D
0x180002ea7  lea     edx, [rax+1]; unsigned int
0x180002eaa  mov     rcx, rbx; this
0x180002ead  call    ?Allocate@CBufferBase@Dfdll@@QEAAJI@Z; Dfdll::CBufferBase::Allocate(uint)
0x180002eb2  mov     ecx, eax
0x180002eb4  test    eax, eax
0x180002eb6  js      short loc_180002F0D
0x180002eb8  mov     edi, [rbx+10h]
0x180002ebb  test    edi, edi
0x180002ebd  jnz     short loc_180002EC6
0x180002ebf  mov     ecx, 8007000Dh
0x180002ec4  jmp     short loc_180002F0D
0x180002ec6  mov     rax, [rbx+8]
0x180002eca  xor     edx, edx; dwFlags
0x180002ecc  mov     r9d, [rsi+20h]; cchWideChar
0x180002ed0  xor     ecx, ecx; CodePage
0x180002ed2  mov     r8, [rsi+10h]; lpWideCharStr
0x180002ed6  mov     [rsp+48h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x180002edb  mov     [rsp+48h+lpDefaultChar], rbp; lpDefaultChar
0x180002ee0  mov     [rsp+48h+cbMultiByte], edi; cbMultiByte
0x180002ee4  mov     [rsp+48h+lpMultiByteStr], rax; lpMultiByteStr
0x180002ee9  call    cs:__imp_WideCharToMultiByte
0x180002eef  test    eax, eax
0x180002ef1  jz      short loc_180002E85
0x180002ef3  mov     rax, [rbx]
0x180002ef6  lea     edx, [rdi-1]
0x180002ef9  mov     rcx, rbx
0x180002efc  mov     rax, [rax+28h]
0x180002f00  call    cs:__guard_dispatch_icall_fptr
0x180002f06  test    eax, eax
0x180002f08  mov     ecx, eax
0x180002f0a  cmovns  ecx, ebp
0x180002f0d  mov     rbx, [rsp+48h+arg_0]
0x180002f12  mov     eax, ecx
0x180002f14  mov     rbp, [rsp+48h+arg_8]
0x180002f19  mov     rsi, [rsp+48h+arg_10]
0x180002f1e  add     rsp, 40h
0x180002f22  pop     rdi
0x180002f23  retn
```
