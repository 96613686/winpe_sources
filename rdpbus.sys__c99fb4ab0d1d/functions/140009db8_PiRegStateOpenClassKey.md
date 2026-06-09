# PiRegStateOpenClassKey

- ea: `0x140009db8`
- end: `0x140009f43`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000a134`
- `0x14000a2a0`

## callees

- `0x140002520`
- `0x140009db8`
- `0x14000a5c8`
- `0x14000a628`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140009ef9`
- `ntoskrnl!ZwClose` at `0x140009ef9`
- `ntoskrnl!_snwprintf` at `0x140009e99`
- `ntoskrnl!_snwprintf` at `0x140009e99`

## string_xrefs

- `0x140009e12`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x140009db8  mov     [rsp-8+arg_8], rbx
0x140009dbd  push    rbp
0x140009dbe  push    rsi
0x140009dbf  push    rdi
0x140009dc0  push    r12
0x140009dc2  push    r13
0x140009dc4  push    r14
0x140009dc6  push    r15
0x140009dc8  lea     rbp, [rsp-1Fh]
0x140009dcd  sub     rsp, 0F0h
0x140009dd4  mov     rax, cs:__security_cookie
0x140009ddb  xor     rax, rsp
0x140009dde  mov     [rbp+4Fh+var_40], rax
0x140009de2  mov     r12, [rbp+4Fh+arg_20]
0x140009de6  xor     ebx, ebx
0x140009de8  mov     [rbp+4Fh+Handle], rbx
0x140009dec  mov     r14, r9
0x140009def  mov     [rbp+4Fh+var_A0], rbx
0x140009df3  mov     r13d, r8d
0x140009df6  mov     [rbp+4Fh+var_B0], ebx
0x140009df9  mov     r15, rcx
0x140009dfc  mov     [r12], rbx
0x140009e00  test    r9, r9
0x140009e03  jz      short loc_140009E08
0x140009e05  mov     [r9], ebx
0x140009e08  lea     r9, [rbp+4Fh+Handle]
0x140009e0c  mov     r8d, 20019h
0x140009e12  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140009e19  xor     ecx, ecx
0x140009e1b  call    CmRegUtilOpenExistingWstrKey
0x140009e20  test    eax, eax
0x140009e22  js      loc_140009F1B
0x140009e28  movzx   ecx, byte ptr [r15+0Eh]
0x140009e2d  movzx   edx, byte ptr [r15+0Dh]
0x140009e32  movzx   r8d, byte ptr [r15+0Ch]
0x140009e37  movzx   r9d, byte ptr [r15+0Bh]
0x140009e3c  movzx   eax, byte ptr [r15+0Fh]
0x140009e41  movzx   r10d, byte ptr [r15+0Ah]
0x140009e46  movzx   r11d, byte ptr [r15+9]
0x140009e4b  movzx   ebx, byte ptr [r15+8]
0x140009e50  movzx   edi, word ptr [r15+6]
0x140009e55  movzx   esi, word ptr [r15+4]
0x140009e5a  mov     [rsp+120h+var_B8], eax
0x140009e5e  mov     [rsp+120h+var_C0], ecx
0x140009e62  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140009e66  mov     [rsp+120h+var_C8], edx
0x140009e6a  mov     edx, 27h ; '''; Count
0x140009e6f  mov     [rsp+120h+var_D0], r8d
0x140009e74  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140009e7b  mov     [rsp+120h+var_D8], r9d
0x140009e80  mov     r9d, [r15]
0x140009e83  mov     [rsp+120h+var_E0], r10d
0x140009e88  mov     [rsp+120h+var_E8], r11d
0x140009e8d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140009e91  mov     dword ptr [rsp+120h+var_F8], edi
0x140009e95  mov     dword ptr [rsp+120h+var_100], esi
0x140009e99  call    cs:__imp__snwprintf
0x140009ea0  nop     dword ptr [rax+rax+00h]
0x140009ea5  mov     rbx, [rbp+4Fh+Handle]
0x140009ea9  lea     rdx, [rbp+4Fh+Dest]
0x140009ead  xor     eax, eax
0x140009eaf  mov     rcx, rbx
0x140009eb2  mov     [rbp+4Fh+var_44], ax
0x140009eb6  test    r13d, r13d
0x140009eb9  jz      short loc_140009EE0
0x140009ebb  lea     rax, [rbp+4Fh+var_A0]
0x140009ebf  mov     [rsp+120h+var_F0], rax
0x140009ec4  lea     rax, [rbp+4Fh+var_B0]
0x140009ec8  mov     [rsp+120h+var_F8], rax
0x140009ecd  mov     [rsp+120h+var_100], 0
0x140009ed6  call    CmRegUtilCreateWstrKey
0x140009edb  mov     esi, [rbp+4Fh+var_B0]
0x140009ede  jmp     short loc_140009EF4
0x140009ee0  lea     r9, [rbp+4Fh+var_A0]
0x140009ee4  mov     r8d, 0F003Fh
0x140009eea  call    CmRegUtilOpenExistingWstrKey
0x140009eef  mov     esi, 2
0x140009ef4  mov     rcx, rbx; Handle
0x140009ef7  mov     edi, eax
0x140009ef9  call    cs:__imp_ZwClose
0x140009f00  nop     dword ptr [rax+rax+00h]
0x140009f05  test    edi, edi
0x140009f07  js      short loc_140009F19
0x140009f09  mov     rax, [rbp+4Fh+var_A0]
0x140009f0d  mov     [r12], rax
0x140009f11  test    r14, r14
0x140009f14  jz      short loc_140009F19
0x140009f16  mov     [r14], esi
0x140009f19  mov     eax, edi
0x140009f1b  mov     rcx, [rbp+4Fh+var_40]
0x140009f1f  xor     rcx, rsp; StackCookie
0x140009f22  call    __security_check_cookie
0x140009f27  mov     rbx, [rsp+120h+arg_8]
0x140009f2f  add     rsp, 0F0h
0x140009f36  pop     r15
0x140009f38  pop     r14
0x140009f3a  pop     r13
0x140009f3c  pop     r12
0x140009f3e  pop     rdi
0x140009f3f  pop     rsi
0x140009f40  pop     rbp
0x140009f41  retn
```
