# PiRegStateOpenClassKey

- ea: `0x140011b98`
- end: `0x140011d23`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140011f14`
- `0x140012080`

## callees

- `0x140003920`
- `0x140011b98`
- `0x1400123a8`
- `0x140012408`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140011cd9`
- `ntoskrnl!ZwClose` at `0x140011cd9`
- `ntoskrnl!_snwprintf` at `0x140011c79`
- `ntoskrnl!_snwprintf` at `0x140011c79`

## string_xrefs

- `0x140011bf2`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, int *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  int v9; // r8d
  int v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS WstrKey; // eax
  int v13; // esi
  int v14; // edi
  int v15; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-59h] BYREF
  void *v17[2]; // [rsp+80h] [rbp-51h] BYREF
  wchar_t Dest[40]; // [rsp+90h] [rbp-41h] BYREF

  Handle = 0;
  v17[0] = 0;
  v15 = 0;
  *a5 = 0;
  if ( a4 )
    *a4 = 0;
  result = CmRegUtilOpenExistingWstrKey(
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Class",
             131097,
             &Handle);
  if ( result >= 0 )
  {
    _snwprintf(
      Dest,
      0x27u,
      L"{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
      *a1,
      *((unsigned __int16 *)a1 + 2),
      *((unsigned __int16 *)a1 + 3),
      *((unsigned __int8 *)a1 + 8),
      *((unsigned __int8 *)a1 + 9),
      *((unsigned __int8 *)a1 + 10),
      *((unsigned __int8 *)a1 + 11),
      *((unsigned __int8 *)a1 + 12),
      *((unsigned __int8 *)a1 + 13),
      *((unsigned __int8 *)a1 + 14),
      *((unsigned __int8 *)a1 + 15));
    v11 = Handle;
    Dest[38] = 0;
    if ( a3 )
    {
      WstrKey = CmRegUtilCreateWstrKey((_DWORD)Handle, (unsigned int)Dest, v9, v10, 0, (__int64)&v15, (__int64)v17);
      v13 = v15;
    }
    else
    {
      WstrKey = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = WstrKey;
    ZwClose(v11);
    if ( v14 >= 0 )
    {
      *a5 = v17[0];
      if ( a4 )
        *a4 = v13;
    }
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x140011b98  mov     [rsp-8+arg_8], rbx
0x140011b9d  push    rbp
0x140011b9e  push    rsi
0x140011b9f  push    rdi
0x140011ba0  push    r12
0x140011ba2  push    r13
0x140011ba4  push    r14
0x140011ba6  push    r15
0x140011ba8  lea     rbp, [rsp-1Fh]
0x140011bad  sub     rsp, 0F0h
0x140011bb4  mov     rax, cs:__security_cookie
0x140011bbb  xor     rax, rsp
0x140011bbe  mov     [rbp+4Fh+var_40], rax
0x140011bc2  mov     r12, [rbp+4Fh+arg_20]
0x140011bc6  xor     ebx, ebx
0x140011bc8  mov     [rbp+4Fh+Handle], rbx
0x140011bcc  mov     r14, r9
0x140011bcf  mov     [rbp+4Fh+var_A0], rbx
0x140011bd3  mov     r13d, r8d
0x140011bd6  mov     [rbp+4Fh+var_B0], ebx
0x140011bd9  mov     r15, rcx
0x140011bdc  mov     [r12], rbx
0x140011be0  test    r9, r9
0x140011be3  jz      short loc_140011BE8
0x140011be5  mov     [r9], ebx
0x140011be8  lea     r9, [rbp+4Fh+Handle]
0x140011bec  mov     r8d, 20019h
0x140011bf2  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140011bf9  xor     ecx, ecx
0x140011bfb  call    CmRegUtilOpenExistingWstrKey
0x140011c00  test    eax, eax
0x140011c02  js      loc_140011CFB
0x140011c08  movzx   ecx, byte ptr [r15+0Eh]
0x140011c0d  movzx   edx, byte ptr [r15+0Dh]
0x140011c12  movzx   r8d, byte ptr [r15+0Ch]
0x140011c17  movzx   r9d, byte ptr [r15+0Bh]
0x140011c1c  movzx   eax, byte ptr [r15+0Fh]
0x140011c21  movzx   r10d, byte ptr [r15+0Ah]
0x140011c26  movzx   r11d, byte ptr [r15+9]
0x140011c2b  movzx   ebx, byte ptr [r15+8]
0x140011c30  movzx   edi, word ptr [r15+6]
0x140011c35  movzx   esi, word ptr [r15+4]
0x140011c3a  mov     [rsp+120h+var_B8], eax
0x140011c3e  mov     [rsp+120h+var_C0], ecx
0x140011c42  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140011c46  mov     [rsp+120h+var_C8], edx
0x140011c4a  mov     edx, 27h ; '''; Count
0x140011c4f  mov     [rsp+120h+var_D0], r8d
0x140011c54  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140011c5b  mov     [rsp+120h+var_D8], r9d
0x140011c60  mov     r9d, [r15]
0x140011c63  mov     [rsp+120h+var_E0], r10d
0x140011c68  mov     [rsp+120h+var_E8], r11d
0x140011c6d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140011c71  mov     dword ptr [rsp+120h+var_F8], edi
0x140011c75  mov     dword ptr [rsp+120h+var_100], esi
0x140011c79  call    cs:__imp__snwprintf
0x140011c80  nop     dword ptr [rax+rax+00h]
0x140011c85  mov     rbx, [rbp+4Fh+Handle]
0x140011c89  lea     rdx, [rbp+4Fh+Dest]
0x140011c8d  xor     eax, eax
0x140011c8f  mov     rcx, rbx
0x140011c92  mov     [rbp+4Fh+var_44], ax
0x140011c96  test    r13d, r13d
0x140011c99  jz      short loc_140011CC0
0x140011c9b  lea     rax, [rbp+4Fh+var_A0]
0x140011c9f  mov     [rsp+120h+var_F0], rax
0x140011ca4  lea     rax, [rbp+4Fh+var_B0]
0x140011ca8  mov     [rsp+120h+var_F8], rax
0x140011cad  mov     [rsp+120h+var_100], 0
0x140011cb6  call    CmRegUtilCreateWstrKey
0x140011cbb  mov     esi, [rbp+4Fh+var_B0]
0x140011cbe  jmp     short loc_140011CD4
0x140011cc0  lea     r9, [rbp+4Fh+var_A0]
0x140011cc4  mov     r8d, 0F003Fh
0x140011cca  call    CmRegUtilOpenExistingWstrKey
0x140011ccf  mov     esi, 2
0x140011cd4  mov     rcx, rbx; Handle
0x140011cd7  mov     edi, eax
0x140011cd9  call    cs:__imp_ZwClose
0x140011ce0  nop     dword ptr [rax+rax+00h]
0x140011ce5  test    edi, edi
0x140011ce7  js      short loc_140011CF9
0x140011ce9  mov     rax, [rbp+4Fh+var_A0]
0x140011ced  mov     [r12], rax
0x140011cf1  test    r14, r14
0x140011cf4  jz      short loc_140011CF9
0x140011cf6  mov     [r14], esi
0x140011cf9  mov     eax, edi
0x140011cfb  mov     rcx, [rbp+4Fh+var_40]
0x140011cff  xor     rcx, rsp; StackCookie
0x140011d02  call    __security_check_cookie
0x140011d07  mov     rbx, [rsp+120h+arg_8]
0x140011d0f  add     rsp, 0F0h
0x140011d16  pop     r15
0x140011d18  pop     r14
0x140011d1a  pop     r13
0x140011d1c  pop     r12
0x140011d1e  pop     rdi
0x140011d1f  pop     rsi
0x140011d20  pop     rbp
0x140011d21  retn
```
