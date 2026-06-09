# PiRegStateOpenClassKey

- ea: `0x140044248`
- end: `0x1400443d3`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400445c4`
- `0x140044730`

## callees

- `0x1400371f0`
- `0x140044248`
- `0x140044a58`
- `0x140044ab8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140044389`
- `ntoskrnl!ZwClose` at `0x140044389`
- `ntoskrnl!_snwprintf` at `0x140044329`
- `ntoskrnl!_snwprintf` at `0x140044329`

## string_xrefs

- `0x1400442a2`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x140044248  mov     [rsp-8+arg_8], rbx
0x14004424d  push    rbp
0x14004424e  push    rsi
0x14004424f  push    rdi
0x140044250  push    r12
0x140044252  push    r13
0x140044254  push    r14
0x140044256  push    r15
0x140044258  lea     rbp, [rsp-1Fh]
0x14004425d  sub     rsp, 0F0h
0x140044264  mov     rax, cs:__security_cookie
0x14004426b  xor     rax, rsp
0x14004426e  mov     [rbp+4Fh+var_40], rax
0x140044272  mov     r12, [rbp+4Fh+arg_20]
0x140044276  xor     ebx, ebx
0x140044278  mov     [rbp+4Fh+Handle], rbx
0x14004427c  mov     r14, r9
0x14004427f  mov     [rbp+4Fh+var_A0], rbx
0x140044283  mov     r13d, r8d
0x140044286  mov     [rbp+4Fh+var_B0], ebx
0x140044289  mov     r15, rcx
0x14004428c  mov     [r12], rbx
0x140044290  test    r9, r9
0x140044293  jz      short loc_140044298
0x140044295  mov     [r9], ebx
0x140044298  lea     r9, [rbp+4Fh+Handle]
0x14004429c  mov     r8d, 20019h
0x1400442a2  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400442a9  xor     ecx, ecx
0x1400442ab  call    CmRegUtilOpenExistingWstrKey
0x1400442b0  test    eax, eax
0x1400442b2  js      loc_1400443AB
0x1400442b8  movzx   ecx, byte ptr [r15+0Eh]
0x1400442bd  movzx   edx, byte ptr [r15+0Dh]
0x1400442c2  movzx   r8d, byte ptr [r15+0Ch]
0x1400442c7  movzx   r9d, byte ptr [r15+0Bh]
0x1400442cc  movzx   eax, byte ptr [r15+0Fh]
0x1400442d1  movzx   r10d, byte ptr [r15+0Ah]
0x1400442d6  movzx   r11d, byte ptr [r15+9]
0x1400442db  movzx   ebx, byte ptr [r15+8]
0x1400442e0  movzx   edi, word ptr [r15+6]
0x1400442e5  movzx   esi, word ptr [r15+4]
0x1400442ea  mov     [rsp+120h+var_B8], eax
0x1400442ee  mov     [rsp+120h+var_C0], ecx
0x1400442f2  lea     rcx, [rbp+4Fh+Dest]; Dest
0x1400442f6  mov     [rsp+120h+var_C8], edx
0x1400442fa  mov     edx, 27h ; '''; Count
0x1400442ff  mov     [rsp+120h+var_D0], r8d
0x140044304  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x14004430b  mov     [rsp+120h+var_D8], r9d
0x140044310  mov     r9d, [r15]
0x140044313  mov     [rsp+120h+var_E0], r10d
0x140044318  mov     [rsp+120h+var_E8], r11d
0x14004431d  mov     dword ptr [rsp+120h+var_F0], ebx
0x140044321  mov     dword ptr [rsp+120h+var_F8], edi
0x140044325  mov     dword ptr [rsp+120h+var_100], esi
0x140044329  call    cs:__imp__snwprintf
0x140044330  nop     dword ptr [rax+rax+00h]
0x140044335  mov     rbx, [rbp+4Fh+Handle]
0x140044339  lea     rdx, [rbp+4Fh+Dest]
0x14004433d  xor     eax, eax
0x14004433f  mov     rcx, rbx
0x140044342  mov     [rbp+4Fh+var_44], ax
0x140044346  test    r13d, r13d
0x140044349  jz      short loc_140044370
0x14004434b  lea     rax, [rbp+4Fh+var_A0]
0x14004434f  mov     [rsp+120h+var_F0], rax
0x140044354  lea     rax, [rbp+4Fh+var_B0]
0x140044358  mov     [rsp+120h+var_F8], rax
0x14004435d  mov     [rsp+120h+var_100], 0
0x140044366  call    CmRegUtilCreateWstrKey
0x14004436b  mov     esi, [rbp+4Fh+var_B0]
0x14004436e  jmp     short loc_140044384
0x140044370  lea     r9, [rbp+4Fh+var_A0]
0x140044374  mov     r8d, 0F003Fh
0x14004437a  call    CmRegUtilOpenExistingWstrKey
0x14004437f  mov     esi, 2
0x140044384  mov     rcx, rbx; Handle
0x140044387  mov     edi, eax
0x140044389  call    cs:__imp_ZwClose
0x140044390  nop     dword ptr [rax+rax+00h]
0x140044395  test    edi, edi
0x140044397  js      short loc_1400443A9
0x140044399  mov     rax, [rbp+4Fh+var_A0]
0x14004439d  mov     [r12], rax
0x1400443a1  test    r14, r14
0x1400443a4  jz      short loc_1400443A9
0x1400443a6  mov     [r14], esi
0x1400443a9  mov     eax, edi
0x1400443ab  mov     rcx, [rbp+4Fh+var_40]
0x1400443af  xor     rcx, rsp; StackCookie
0x1400443b2  call    __security_check_cookie
0x1400443b7  mov     rbx, [rsp+120h+arg_8]
0x1400443bf  add     rsp, 0F0h
0x1400443c6  pop     r15
0x1400443c8  pop     r14
0x1400443ca  pop     r13
0x1400443cc  pop     r12
0x1400443ce  pop     rdi
0x1400443cf  pop     rsi
0x1400443d0  pop     rbp
0x1400443d1  retn
```
