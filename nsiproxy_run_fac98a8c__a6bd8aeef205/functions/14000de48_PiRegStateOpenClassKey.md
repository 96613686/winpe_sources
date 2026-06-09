# PiRegStateOpenClassKey

- ea: `0x14000de48`
- end: `0x14000dfd3`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000e1c4`
- `0x14000e330`

## callees

- `0x140006530`
- `0x14000de48`
- `0x14000e658`
- `0x14000e6b8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000df89`
- `ntoskrnl!ZwClose` at `0x14000df89`
- `ntoskrnl!_snwprintf` at `0x14000df29`
- `ntoskrnl!_snwprintf` at `0x14000df29`

## string_xrefs

- `0x14000dea2`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x14000de48  mov     [rsp-8+arg_8], rbx
0x14000de4d  push    rbp
0x14000de4e  push    rsi
0x14000de4f  push    rdi
0x14000de50  push    r12
0x14000de52  push    r13
0x14000de54  push    r14
0x14000de56  push    r15
0x14000de58  lea     rbp, [rsp-1Fh]
0x14000de5d  sub     rsp, 0F0h
0x14000de64  mov     rax, cs:__security_cookie
0x14000de6b  xor     rax, rsp
0x14000de6e  mov     [rbp+4Fh+var_40], rax
0x14000de72  mov     r12, [rbp+4Fh+arg_20]
0x14000de76  xor     ebx, ebx
0x14000de78  mov     [rbp+4Fh+Handle], rbx
0x14000de7c  mov     r14, r9
0x14000de7f  mov     [rbp+4Fh+var_A0], rbx
0x14000de83  mov     r13d, r8d
0x14000de86  mov     [rbp+4Fh+var_B0], ebx
0x14000de89  mov     r15, rcx
0x14000de8c  mov     [r12], rbx
0x14000de90  test    r9, r9
0x14000de93  jz      short loc_14000DE98
0x14000de95  mov     [r9], ebx
0x14000de98  lea     r9, [rbp+4Fh+Handle]
0x14000de9c  mov     r8d, 20019h
0x14000dea2  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14000dea9  xor     ecx, ecx
0x14000deab  call    CmRegUtilOpenExistingWstrKey
0x14000deb0  test    eax, eax
0x14000deb2  js      loc_14000DFAB
0x14000deb8  movzx   ecx, byte ptr [r15+0Eh]
0x14000debd  movzx   edx, byte ptr [r15+0Dh]
0x14000dec2  movzx   r8d, byte ptr [r15+0Ch]
0x14000dec7  movzx   r9d, byte ptr [r15+0Bh]
0x14000decc  movzx   eax, byte ptr [r15+0Fh]
0x14000ded1  movzx   r10d, byte ptr [r15+0Ah]
0x14000ded6  movzx   r11d, byte ptr [r15+9]
0x14000dedb  movzx   ebx, byte ptr [r15+8]
0x14000dee0  movzx   edi, word ptr [r15+6]
0x14000dee5  movzx   esi, word ptr [r15+4]
0x14000deea  mov     [rsp+120h+var_B8], eax
0x14000deee  mov     [rsp+120h+var_C0], ecx
0x14000def2  lea     rcx, [rbp+4Fh+Dest]; Dest
0x14000def6  mov     [rsp+120h+var_C8], edx
0x14000defa  mov     edx, 27h ; '''; Count
0x14000deff  mov     [rsp+120h+var_D0], r8d
0x14000df04  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14000df0b  mov     [rsp+120h+var_D8], r9d
0x14000df10  mov     r9d, [r15]
0x14000df13  mov     [rsp+120h+var_E0], r10d
0x14000df18  mov     [rsp+120h+var_E8], r11d
0x14000df1d  mov     dword ptr [rsp+120h+var_F0], ebx
0x14000df21  mov     dword ptr [rsp+120h+var_F8], edi
0x14000df25  mov     dword ptr [rsp+120h+var_100], esi
0x14000df29  call    cs:__imp__snwprintf
0x14000df30  nop     dword ptr [rax+rax+00h]
0x14000df35  mov     rbx, [rbp+4Fh+Handle]
0x14000df39  lea     rdx, [rbp+4Fh+Dest]
0x14000df3d  xor     eax, eax
0x14000df3f  mov     rcx, rbx
0x14000df42  mov     [rbp+4Fh+var_44], ax
0x14000df46  test    r13d, r13d
0x14000df49  jz      short loc_14000DF70
0x14000df4b  lea     rax, [rbp+4Fh+var_A0]
0x14000df4f  mov     [rsp+120h+var_F0], rax
0x14000df54  lea     rax, [rbp+4Fh+var_B0]
0x14000df58  mov     [rsp+120h+var_F8], rax
0x14000df5d  mov     [rsp+120h+var_100], 0
0x14000df66  call    CmRegUtilCreateWstrKey
0x14000df6b  mov     esi, [rbp+4Fh+var_B0]
0x14000df6e  jmp     short loc_14000DF84
0x14000df70  lea     r9, [rbp+4Fh+var_A0]
0x14000df74  mov     r8d, 0F003Fh
0x14000df7a  call    CmRegUtilOpenExistingWstrKey
0x14000df7f  mov     esi, 2
0x14000df84  mov     rcx, rbx; Handle
0x14000df87  mov     edi, eax
0x14000df89  call    cs:__imp_ZwClose
0x14000df90  nop     dword ptr [rax+rax+00h]
0x14000df95  test    edi, edi
0x14000df97  js      short loc_14000DFA9
0x14000df99  mov     rax, [rbp+4Fh+var_A0]
0x14000df9d  mov     [r12], rax
0x14000dfa1  test    r14, r14
0x14000dfa4  jz      short loc_14000DFA9
0x14000dfa6  mov     [r14], esi
0x14000dfa9  mov     eax, edi
0x14000dfab  mov     rcx, [rbp+4Fh+var_40]
0x14000dfaf  xor     rcx, rsp; StackCookie
0x14000dfb2  call    __security_check_cookie
0x14000dfb7  mov     rbx, [rsp+120h+arg_8]
0x14000dfbf  add     rsp, 0F0h
0x14000dfc6  pop     r15
0x14000dfc8  pop     r14
0x14000dfca  pop     r13
0x14000dfcc  pop     r12
0x14000dfce  pop     rdi
0x14000dfcf  pop     rsi
0x14000dfd0  pop     rbp
0x14000dfd1  retn
```
