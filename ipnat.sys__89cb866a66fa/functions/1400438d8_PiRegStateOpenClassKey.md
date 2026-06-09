# PiRegStateOpenClassKey

- ea: `0x1400438d8`
- end: `0x140043a63`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140043c54`
- `0x140043dc0`

## callees

- `0x14002c6d0`
- `0x1400438d8`
- `0x14004403c`
- `0x140044110`

## import_xrefs

- `ntoskrnl!_snwprintf` at `0x1400439b9`
- `ntoskrnl!_snwprintf` at `0x1400439b9`
- `ntoskrnl!ZwClose` at `0x140043a19`
- `ntoskrnl!ZwClose` at `0x140043a19`

## string_xrefs

- `0x140043932`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x1400438d8  mov     [rsp-8+arg_8], rbx
0x1400438dd  push    rbp
0x1400438de  push    rsi
0x1400438df  push    rdi
0x1400438e0  push    r12
0x1400438e2  push    r13
0x1400438e4  push    r14
0x1400438e6  push    r15
0x1400438e8  lea     rbp, [rsp-1Fh]
0x1400438ed  sub     rsp, 0F0h
0x1400438f4  mov     rax, cs:__security_cookie
0x1400438fb  xor     rax, rsp
0x1400438fe  mov     [rbp+4Fh+var_40], rax
0x140043902  mov     r12, [rbp+4Fh+arg_20]
0x140043906  xor     ebx, ebx
0x140043908  mov     [rbp+4Fh+Handle], rbx
0x14004390c  mov     r14, r9
0x14004390f  mov     [rbp+4Fh+var_A0], rbx
0x140043913  mov     r13d, r8d
0x140043916  mov     [rbp+4Fh+var_B0], ebx
0x140043919  mov     r15, rcx
0x14004391c  mov     [r12], rbx
0x140043920  test    r9, r9
0x140043923  jz      short loc_140043928
0x140043925  mov     [r9], ebx
0x140043928  lea     r9, [rbp+4Fh+Handle]
0x14004392c  mov     r8d, 20019h
0x140043932  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140043939  xor     ecx, ecx
0x14004393b  call    CmRegUtilOpenExistingWstrKey
0x140043940  test    eax, eax
0x140043942  js      loc_140043A3B
0x140043948  movzx   ecx, byte ptr [r15+0Eh]
0x14004394d  movzx   edx, byte ptr [r15+0Dh]
0x140043952  movzx   r8d, byte ptr [r15+0Ch]
0x140043957  movzx   r9d, byte ptr [r15+0Bh]
0x14004395c  movzx   eax, byte ptr [r15+0Fh]
0x140043961  movzx   r10d, byte ptr [r15+0Ah]
0x140043966  movzx   r11d, byte ptr [r15+9]
0x14004396b  movzx   ebx, byte ptr [r15+8]
0x140043970  movzx   edi, word ptr [r15+6]
0x140043975  movzx   esi, word ptr [r15+4]
0x14004397a  mov     [rsp+120h+var_B8], eax
0x14004397e  mov     [rsp+120h+var_C0], ecx
0x140043982  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140043986  mov     [rsp+120h+var_C8], edx
0x14004398a  mov     edx, 27h ; '''; Count
0x14004398f  mov     [rsp+120h+var_D0], r8d
0x140043994  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14004399b  mov     [rsp+120h+var_D8], r9d
0x1400439a0  mov     r9d, [r15]
0x1400439a3  mov     [rsp+120h+var_E0], r10d
0x1400439a8  mov     [rsp+120h+var_E8], r11d
0x1400439ad  mov     dword ptr [rsp+120h+var_F0], ebx
0x1400439b1  mov     dword ptr [rsp+120h+var_F8], edi
0x1400439b5  mov     dword ptr [rsp+120h+var_100], esi
0x1400439b9  call    cs:__imp__snwprintf
0x1400439c0  nop     dword ptr [rax+rax+00h]
0x1400439c5  mov     rbx, [rbp+4Fh+Handle]
0x1400439c9  lea     rdx, [rbp+4Fh+Dest]
0x1400439cd  xor     eax, eax
0x1400439cf  mov     rcx, rbx
0x1400439d2  mov     [rbp+4Fh+var_44], ax
0x1400439d6  test    r13d, r13d
0x1400439d9  jz      short loc_140043A00
0x1400439db  lea     rax, [rbp+4Fh+var_A0]
0x1400439df  mov     [rsp+120h+var_F0], rax
0x1400439e4  lea     rax, [rbp+4Fh+var_B0]
0x1400439e8  mov     [rsp+120h+var_F8], rax
0x1400439ed  mov     [rsp+120h+var_100], 0
0x1400439f6  call    CmRegUtilCreateWstrKey
0x1400439fb  mov     esi, [rbp+4Fh+var_B0]
0x1400439fe  jmp     short loc_140043A14
0x140043a00  lea     r9, [rbp+4Fh+var_A0]
0x140043a04  mov     r8d, 0F003Fh
0x140043a0a  call    CmRegUtilOpenExistingWstrKey
0x140043a0f  mov     esi, 2
0x140043a14  mov     rcx, rbx; Handle
0x140043a17  mov     edi, eax
0x140043a19  call    cs:__imp_ZwClose
0x140043a20  nop     dword ptr [rax+rax+00h]
0x140043a25  test    edi, edi
0x140043a27  js      short loc_140043A39
0x140043a29  mov     rax, [rbp+4Fh+var_A0]
0x140043a2d  mov     [r12], rax
0x140043a31  test    r14, r14
0x140043a34  jz      short loc_140043A39
0x140043a36  mov     [r14], esi
0x140043a39  mov     eax, edi
0x140043a3b  mov     rcx, [rbp+4Fh+var_40]
0x140043a3f  xor     rcx, rsp; StackCookie
0x140043a42  call    __security_check_cookie
0x140043a47  mov     rbx, [rsp+120h+arg_8]
0x140043a4f  add     rsp, 0F0h
0x140043a56  pop     r15
0x140043a58  pop     r14
0x140043a5a  pop     r13
0x140043a5c  pop     r12
0x140043a5e  pop     rdi
0x140043a5f  pop     rsi
0x140043a60  pop     rbp
0x140043a61  retn
```
