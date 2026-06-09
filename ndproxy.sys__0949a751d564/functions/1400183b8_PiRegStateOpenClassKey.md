# PiRegStateOpenClassKey

- ea: `0x1400183b8`
- end: `0x140018543`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018734`
- `0x1400188a0`

## callees

- `0x140007fc0`
- `0x1400183b8`
- `0x140018b1c`
- `0x140018bf0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400184f9`
- `ntoskrnl!ZwClose` at `0x1400184f9`
- `ntoskrnl!_snwprintf` at `0x140018499`
- `ntoskrnl!_snwprintf` at `0x140018499`

## string_xrefs

- `0x140018412`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x1400183b8  mov     [rsp-8+arg_8], rbx
0x1400183bd  push    rbp
0x1400183be  push    rsi
0x1400183bf  push    rdi
0x1400183c0  push    r12
0x1400183c2  push    r13
0x1400183c4  push    r14
0x1400183c6  push    r15
0x1400183c8  lea     rbp, [rsp-1Fh]
0x1400183cd  sub     rsp, 0F0h
0x1400183d4  mov     rax, cs:__security_cookie
0x1400183db  xor     rax, rsp
0x1400183de  mov     [rbp+4Fh+var_40], rax
0x1400183e2  mov     r12, [rbp+4Fh+arg_20]
0x1400183e6  xor     ebx, ebx
0x1400183e8  mov     [rbp+4Fh+Handle], rbx
0x1400183ec  mov     r14, r9
0x1400183ef  mov     [rbp+4Fh+var_A0], rbx
0x1400183f3  mov     r13d, r8d
0x1400183f6  mov     [rbp+4Fh+var_B0], ebx
0x1400183f9  mov     r15, rcx
0x1400183fc  mov     [r12], rbx
0x140018400  test    r9, r9
0x140018403  jz      short loc_140018408
0x140018405  mov     [r9], ebx
0x140018408  lea     r9, [rbp+4Fh+Handle]
0x14001840c  mov     r8d, 20019h
0x140018412  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140018419  xor     ecx, ecx
0x14001841b  call    CmRegUtilOpenExistingWstrKey
0x140018420  test    eax, eax
0x140018422  js      loc_14001851B
0x140018428  movzx   ecx, byte ptr [r15+0Eh]
0x14001842d  movzx   edx, byte ptr [r15+0Dh]
0x140018432  movzx   r8d, byte ptr [r15+0Ch]
0x140018437  movzx   r9d, byte ptr [r15+0Bh]
0x14001843c  movzx   eax, byte ptr [r15+0Fh]
0x140018441  movzx   r10d, byte ptr [r15+0Ah]
0x140018446  movzx   r11d, byte ptr [r15+9]
0x14001844b  movzx   ebx, byte ptr [r15+8]
0x140018450  movzx   edi, word ptr [r15+6]
0x140018455  movzx   esi, word ptr [r15+4]
0x14001845a  mov     [rsp+120h+var_B8], eax
0x14001845e  mov     [rsp+120h+var_C0], ecx
0x140018462  lea     rcx, [rbp+4Fh+Dest]; Dest
0x140018466  mov     [rsp+120h+var_C8], edx
0x14001846a  mov     edx, 27h ; '''; Count
0x14001846f  mov     [rsp+120h+var_D0], r8d
0x140018474  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14001847b  mov     [rsp+120h+var_D8], r9d
0x140018480  mov     r9d, [r15]
0x140018483  mov     [rsp+120h+var_E0], r10d
0x140018488  mov     [rsp+120h+var_E8], r11d
0x14001848d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140018491  mov     dword ptr [rsp+120h+var_F8], edi
0x140018495  mov     dword ptr [rsp+120h+var_100], esi
0x140018499  call    cs:__imp__snwprintf
0x1400184a0  nop     dword ptr [rax+rax+00h]
0x1400184a5  mov     rbx, [rbp+4Fh+Handle]
0x1400184a9  lea     rdx, [rbp+4Fh+Dest]
0x1400184ad  xor     eax, eax
0x1400184af  mov     rcx, rbx
0x1400184b2  mov     [rbp+4Fh+var_44], ax
0x1400184b6  test    r13d, r13d
0x1400184b9  jz      short loc_1400184E0
0x1400184bb  lea     rax, [rbp+4Fh+var_A0]
0x1400184bf  mov     [rsp+120h+var_F0], rax
0x1400184c4  lea     rax, [rbp+4Fh+var_B0]
0x1400184c8  mov     [rsp+120h+var_F8], rax
0x1400184cd  mov     [rsp+120h+var_100], 0
0x1400184d6  call    CmRegUtilCreateWstrKey
0x1400184db  mov     esi, [rbp+4Fh+var_B0]
0x1400184de  jmp     short loc_1400184F4
0x1400184e0  lea     r9, [rbp+4Fh+var_A0]
0x1400184e4  mov     r8d, 0F003Fh
0x1400184ea  call    CmRegUtilOpenExistingWstrKey
0x1400184ef  mov     esi, 2
0x1400184f4  mov     rcx, rbx; Handle
0x1400184f7  mov     edi, eax
0x1400184f9  call    cs:__imp_ZwClose
0x140018500  nop     dword ptr [rax+rax+00h]
0x140018505  test    edi, edi
0x140018507  js      short loc_140018519
0x140018509  mov     rax, [rbp+4Fh+var_A0]
0x14001850d  mov     [r12], rax
0x140018511  test    r14, r14
0x140018514  jz      short loc_140018519
0x140018516  mov     [r14], esi
0x140018519  mov     eax, edi
0x14001851b  mov     rcx, [rbp+4Fh+var_40]
0x14001851f  xor     rcx, rsp; StackCookie
0x140018522  call    __security_check_cookie
0x140018527  mov     rbx, [rsp+120h+arg_8]
0x14001852f  add     rsp, 0F0h
0x140018536  pop     r15
0x140018538  pop     r14
0x14001853a  pop     r13
0x14001853c  pop     r12
0x14001853e  pop     rdi
0x14001853f  pop     rsi
0x140018540  pop     rbp
0x140018541  retn
```
