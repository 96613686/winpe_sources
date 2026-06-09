# PiRegStateOpenClassKey

- ea: `0x14000ff68`
- end: `0x1400100f3`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400102e4`
- `0x140010450`

## callees

- `0x140001370`
- `0x14000ff68`
- `0x1400105cc`
- `0x1400106a0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400100a9`
- `ntoskrnl!ZwClose` at `0x1400100a9`
- `ntoskrnl!_snwprintf` at `0x140010049`
- `ntoskrnl!_snwprintf` at `0x140010049`

## string_xrefs

- `0x14000ffc2`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

## pseudocode

```c
NTSTATUS __fastcall PiRegStateOpenClassKey(unsigned int *a1, __int64 a2, int a3, ULONG *a4, _QWORD *a5)
{
  NTSTATUS result; // eax
  __int64 v9; // r8
  ULONG v10; // r9d
  HANDLE v11; // rbx
  NTSTATUS v12; // eax
  ULONG v13; // esi
  int v14; // edi
  ULONG v15; // [rsp+70h] [rbp-61h] BYREF
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
      v12 = CmRegUtilCreateWstrKey((__int64)Handle, Dest, v9, v10, 0, &v15, v17);
      v13 = v15;
    }
    else
    {
      v12 = CmRegUtilOpenExistingWstrKey((__int64)Handle, Dest, 983103, v17);
      v13 = 2;
    }
    v14 = v12;
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
0x14000ff68  mov     [rsp-8+arg_8], rbx
0x14000ff6d  push    rbp
0x14000ff6e  push    rsi
0x14000ff6f  push    rdi
0x14000ff70  push    r12
0x14000ff72  push    r13
0x14000ff74  push    r14
0x14000ff76  push    r15
0x14000ff78  lea     rbp, [rsp-1Fh]
0x14000ff7d  sub     rsp, 0F0h
0x14000ff84  mov     rax, cs:__security_cookie
0x14000ff8b  xor     rax, rsp
0x14000ff8e  mov     [rbp+4Fh+var_40], rax
0x14000ff92  mov     r12, [rbp+4Fh+arg_20]
0x14000ff96  xor     ebx, ebx
0x14000ff98  mov     [rbp+4Fh+Handle], rbx
0x14000ff9c  mov     r14, r9
0x14000ff9f  mov     [rbp+4Fh+var_A0], rbx
0x14000ffa3  mov     r13d, r8d
0x14000ffa6  mov     [rbp+4Fh+var_B0], ebx
0x14000ffa9  mov     r15, rcx
0x14000ffac  mov     [r12], rbx
0x14000ffb0  test    r9, r9
0x14000ffb3  jz      short loc_14000FFB8
0x14000ffb5  mov     [r9], ebx
0x14000ffb8  lea     r9, [rbp+4Fh+Handle]
0x14000ffbc  mov     r8d, 20019h
0x14000ffc2  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000ffc9  xor     ecx, ecx
0x14000ffcb  call    CmRegUtilOpenExistingWstrKey
0x14000ffd0  test    eax, eax
0x14000ffd2  js      loc_1400100CB
0x14000ffd8  movzx   ecx, byte ptr [r15+0Eh]
0x14000ffdd  movzx   edx, byte ptr [r15+0Dh]
0x14000ffe2  movzx   r8d, byte ptr [r15+0Ch]
0x14000ffe7  movzx   r9d, byte ptr [r15+0Bh]
0x14000ffec  movzx   eax, byte ptr [r15+0Fh]
0x14000fff1  movzx   r10d, byte ptr [r15+0Ah]
0x14000fff6  movzx   r11d, byte ptr [r15+9]
0x14000fffb  movzx   ebx, byte ptr [r15+8]
0x140010000  movzx   edi, word ptr [r15+6]
0x140010005  movzx   esi, word ptr [r15+4]
0x14001000a  mov     [rsp+120h+var_B8], eax
0x14001000e  mov     [rsp+120h+var_C0], ecx
0x140010012  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140010016  mov     [rsp+120h+var_C8], edx
0x14001001a  mov     edx, 27h ; '''; Count
0x14001001f  mov     [rsp+120h+var_D0], r8d
0x140010024  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14001002b  mov     [rsp+120h+var_D8], r9d
0x140010030  mov     r9d, [r15]
0x140010033  mov     [rsp+120h+var_E0], r10d
0x140010038  mov     [rsp+120h+var_E8], r11d
0x14001003d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140010041  mov     dword ptr [rsp+120h+var_F8], edi
0x140010045  mov     dword ptr [rsp+120h+var_100], esi
0x140010049  call    cs:__imp__snwprintf
0x140010050  nop     dword ptr [rax+rax+00h]
0x140010055  mov     rbx, [rbp+4Fh+Handle]
0x140010059  lea     rdx, [rbp+4Fh+Dest]
0x14001005d  xor     eax, eax
0x14001005f  mov     rcx, rbx
0x140010062  mov     [rbp+4Fh+var_44], ax
0x140010066  test    r13d, r13d
0x140010069  jz      short loc_140010090
0x14001006b  lea     rax, [rbp+4Fh+var_A0]
0x14001006f  mov     [rsp+120h+var_F0], rax
0x140010074  lea     rax, [rbp+4Fh+var_B0]
0x140010078  mov     [rsp+120h+var_F8], rax
0x14001007d  mov     [rsp+120h+var_100], 0
0x140010086  call    CmRegUtilCreateWstrKey
0x14001008b  mov     esi, [rbp+4Fh+var_B0]
0x14001008e  jmp     short loc_1400100A4
0x140010090  lea     r9, [rbp+4Fh+var_A0]
0x140010094  mov     r8d, 0F003Fh
0x14001009a  call    CmRegUtilOpenExistingWstrKey
0x14001009f  mov     esi, 2
0x1400100a4  mov     rcx, rbx; Handle
0x1400100a7  mov     edi, eax
0x1400100a9  call    cs:__imp_ZwClose
0x1400100b0  nop     dword ptr [rax+rax+00h]
0x1400100b5  test    edi, edi
0x1400100b7  js      short loc_1400100C9
0x1400100b9  mov     rax, [rbp+4Fh+var_A0]
0x1400100bd  mov     [r12], rax
0x1400100c1  test    r14, r14
0x1400100c4  jz      short loc_1400100C9
0x1400100c6  mov     [r14], esi
0x1400100c9  mov     eax, edi
0x1400100cb  mov     rcx, [rbp+4Fh+var_40]
0x1400100cf  xor     rcx, rsp; StackCookie
0x1400100d2  call    __security_check_cookie
0x1400100d7  mov     rbx, [rsp+120h+arg_8]
0x1400100df  add     rsp, 0F0h
0x1400100e6  pop     r15
0x1400100e8  pop     r14
0x1400100ea  pop     r13
0x1400100ec  pop     r12
0x1400100ee  pop     rdi
0x1400100ef  pop     rsi
0x1400100f0  pop     rbp
0x1400100f1  retn
```
