# PiRegStateOpenClassKey

- ea: `0x140021af0`
- end: `0x140021c7b`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140021e6c`
- `0x140021fd8`

## callees

- `0x140006480`
- `0x140021af0`
- `0x140022300`
- `0x140022360`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021c31`
- `ntoskrnl!ZwClose` at `0x140021c31`
- `ntoskrnl!_snwprintf` at `0x140021bd1`
- `ntoskrnl!_snwprintf` at `0x140021bd1`

## string_xrefs

- `0x140021b4a`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x140021af0  mov     [rsp-8+arg_8], rbx
0x140021af5  push    rbp
0x140021af6  push    rsi
0x140021af7  push    rdi
0x140021af8  push    r12
0x140021afa  push    r13
0x140021afc  push    r14
0x140021afe  push    r15
0x140021b00  lea     rbp, [rsp-1Fh]
0x140021b05  sub     rsp, 0F0h
0x140021b0c  mov     rax, cs:__security_cookie
0x140021b13  xor     rax, rsp
0x140021b16  mov     [rbp+4Fh+var_40], rax
0x140021b1a  mov     r12, [rbp+4Fh+arg_20]
0x140021b1e  xor     ebx, ebx
0x140021b20  mov     [rbp+4Fh+Handle], rbx
0x140021b24  mov     r14, r9
0x140021b27  mov     [rbp+4Fh+var_A0], rbx
0x140021b2b  mov     r13d, r8d
0x140021b2e  mov     [rbp+4Fh+var_B0], ebx
0x140021b31  mov     r15, rcx
0x140021b34  mov     [r12], rbx
0x140021b38  test    r9, r9
0x140021b3b  jz      short loc_140021B40
0x140021b3d  mov     [r9], ebx
0x140021b40  lea     r9, [rbp+4Fh+Handle]
0x140021b44  mov     r8d, 20019h
0x140021b4a  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140021b51  xor     ecx, ecx
0x140021b53  call    CmRegUtilOpenExistingWstrKey
0x140021b58  test    eax, eax
0x140021b5a  js      loc_140021C53
0x140021b60  movzx   ecx, byte ptr [r15+0Eh]
0x140021b65  movzx   edx, byte ptr [r15+0Dh]
0x140021b6a  movzx   r8d, byte ptr [r15+0Ch]
0x140021b6f  movzx   r9d, byte ptr [r15+0Bh]
0x140021b74  movzx   eax, byte ptr [r15+0Fh]
0x140021b79  movzx   r10d, byte ptr [r15+0Ah]
0x140021b7e  movzx   r11d, byte ptr [r15+9]
0x140021b83  movzx   ebx, byte ptr [r15+8]
0x140021b88  movzx   edi, word ptr [r15+6]
0x140021b8d  movzx   esi, word ptr [r15+4]
0x140021b92  mov     [rsp+120h+var_B8], eax
0x140021b96  mov     [rsp+120h+var_C0], ecx
0x140021b9a  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140021b9e  mov     [rsp+120h+var_C8], edx
0x140021ba2  mov     edx, 27h ; '''; Count
0x140021ba7  mov     [rsp+120h+var_D0], r8d
0x140021bac  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x140021bb3  mov     [rsp+120h+var_D8], r9d
0x140021bb8  mov     r9d, [r15]
0x140021bbb  mov     [rsp+120h+var_E0], r10d
0x140021bc0  mov     [rsp+120h+var_E8], r11d
0x140021bc5  mov     dword ptr [rsp+120h+var_F0], ebx
0x140021bc9  mov     dword ptr [rsp+120h+var_F8], edi
0x140021bcd  mov     dword ptr [rsp+120h+var_100], esi
0x140021bd1  call    cs:__imp__snwprintf
0x140021bd8  nop     dword ptr [rax+rax+00h]
0x140021bdd  mov     rbx, [rbp+4Fh+Handle]
0x140021be1  lea     rdx, [rbp+4Fh+Dest]
0x140021be5  xor     eax, eax
0x140021be7  mov     rcx, rbx
0x140021bea  mov     [rbp+4Fh+var_44], ax
0x140021bee  test    r13d, r13d
0x140021bf1  jz      short loc_140021C18
0x140021bf3  lea     rax, [rbp+4Fh+var_A0]
0x140021bf7  mov     [rsp+120h+var_F0], rax
0x140021bfc  lea     rax, [rbp+4Fh+var_B0]
0x140021c00  mov     [rsp+120h+var_F8], rax
0x140021c05  mov     [rsp+120h+var_100], 0
0x140021c0e  call    CmRegUtilCreateWstrKey
0x140021c13  mov     esi, [rbp+4Fh+var_B0]
0x140021c16  jmp     short loc_140021C2C
0x140021c18  lea     r9, [rbp+4Fh+var_A0]
0x140021c1c  mov     r8d, 0F003Fh
0x140021c22  call    CmRegUtilOpenExistingWstrKey
0x140021c27  mov     esi, 2
0x140021c2c  mov     rcx, rbx; Handle
0x140021c2f  mov     edi, eax
0x140021c31  call    cs:__imp_ZwClose
0x140021c38  nop     dword ptr [rax+rax+00h]
0x140021c3d  test    edi, edi
0x140021c3f  js      short loc_140021C51
0x140021c41  mov     rax, [rbp+4Fh+var_A0]
0x140021c45  mov     [r12], rax
0x140021c49  test    r14, r14
0x140021c4c  jz      short loc_140021C51
0x140021c4e  mov     [r14], esi
0x140021c51  mov     eax, edi
0x140021c53  mov     rcx, [rbp+4Fh+var_40]
0x140021c57  xor     rcx, rsp; StackCookie
0x140021c5a  call    __security_check_cookie
0x140021c5f  mov     rbx, [rsp+120h+arg_8]
0x140021c67  add     rsp, 0F0h
0x140021c6e  pop     r15
0x140021c70  pop     r14
0x140021c72  pop     r13
0x140021c74  pop     r12
0x140021c76  pop     rdi
0x140021c77  pop     rsi
0x140021c78  pop     rbp
0x140021c79  retn
```
