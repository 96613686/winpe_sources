# GetDriveLetter(ushort const *)

- ea: `0x18003bc28`
- end: `0x18003bd07`
- name: `?GetDriveLetter@@YAGPEBG@Z`
- size: `223`
- prototype: `unsigned __int16 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180053b80`

## callees

- `0x18003bc28`
- `0x180042800`
- `0x180043100`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003bc65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003bc8d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003bc65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003bc8d`
- `ntdll!RtlGetCurrentDirectory_U` at `0x18003bcd3`
- `ntdll!RtlGetCurrentDirectory_U` at `0x18003bcd3`

## pseudocode

```c
__int64 __fastcall GetDriveLetter(const unsigned __int16 *a1)
{
  __int64 result; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( !a1 )
    return 0;
  if ( *a1 )
  {
    if ( !(unsigned int)_o__wcsnicmp(a1, L"\\\\?\\", 4) )
    {
      result = a1[4];
      if ( (_WORD)result )
      {
        if ( a1[5] == 58 )
          return result;
        if ( !(unsigned int)_o__wcsnicmp(a1, L"\\\\?\\UNC\\", -1) )
          return 92;
      }
    }
    if ( a1[1] == 58 || *a1 == 92 && a1[1] == 92 )
      return *a1;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( (RtlGetCurrentDirectory_U(0x208u, Buffer) & 0x80000000) == 0 )
    return Buffer[0];
  else
    return 0;
}

```

## disassembly

```asm
0x18003bc28  mov     [rsp+arg_8], rbx
0x18003bc2d  push    rdi
0x18003bc2e  sub     rsp, 240h
0x18003bc35  mov     rax, cs:__security_cookie
0x18003bc3c  xor     rax, rsp
0x18003bc3f  mov     [rsp+248h+var_18], rax
0x18003bc47  xor     edi, edi
0x18003bc49  mov     rbx, rcx
0x18003bc4c  test    rcx, rcx
0x18003bc4f  jz      loc_18003BCE4
0x18003bc55  cmp     [rcx], di
0x18003bc58  jz      short loc_18003BCB8
0x18003bc5a  lea     r8d, [rdi+4]
0x18003bc5e  lea     rdx, asc_180067DD8; "\\\\?\\"
0x18003bc65  call    cs:__imp__o__wcsnicmp
0x18003bc6b  test    eax, eax
0x18003bc6d  jnz     short loc_18003BC9C
0x18003bc6f  movzx   eax, word ptr [rbx+8]
0x18003bc73  test    ax, ax
0x18003bc76  jz      short loc_18003BC9C
0x18003bc78  cmp     word ptr [rbx+0Ah], 3Ah ; ':'
0x18003bc7d  jz      short loc_18003BCE6
0x18003bc7f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003bc83  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x18003bc8a  mov     rcx, rbx
0x18003bc8d  call    cs:__imp__o__wcsnicmp
0x18003bc93  test    eax, eax
0x18003bc95  jnz     short loc_18003BC9C
0x18003bc97  lea     eax, [rdi+5Ch]
0x18003bc9a  jmp     short loc_18003BCE6
0x18003bc9c  cmp     word ptr [rbx+2], 3Ah ; ':'
0x18003bca1  jz      short loc_18003BCB3
0x18003bca3  mov     eax, 5Ch ; '\'
0x18003bca8  cmp     [rbx], ax
0x18003bcab  jnz     short loc_18003BCB8
0x18003bcad  cmp     [rbx+2], ax
0x18003bcb1  jnz     short loc_18003BCB8
0x18003bcb3  movzx   eax, word ptr [rbx]
0x18003bcb6  jmp     short loc_18003BCE6
0x18003bcb8  mov     ebx, 208h
0x18003bcbd  lea     rcx, [rsp+248h+Buffer]; void *
0x18003bcc2  mov     r8d, ebx; Size
0x18003bcc5  xor     edx, edx; Val
0x18003bcc7  call    memset_0
0x18003bccc  lea     rdx, [rsp+248h+Buffer]; Buffer
0x18003bcd1  mov     ecx, ebx; MaximumLength
0x18003bcd3  call    cs:__imp_RtlGetCurrentDirectory_U
0x18003bcd9  test    eax, eax
0x18003bcdb  js      short loc_18003BCE4
0x18003bcdd  movzx   eax, [rsp+248h+Buffer]
0x18003bce2  jmp     short loc_18003BCE6
0x18003bce4  mov     eax, edi
0x18003bce6  mov     rcx, [rsp+248h+var_18]
0x18003bcee  xor     rcx, rsp; StackCookie
0x18003bcf1  call    __security_check_cookie
0x18003bcf6  mov     rbx, [rsp+248h+arg_8]
0x18003bcfe  add     rsp, 240h
0x18003bd05  pop     rdi
0x18003bd06  retn
```
