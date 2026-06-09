# PiRegStateOpenClassKey

- ea: `0x1400535f8`
- end: `0x140053783`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140053974`
- `0x140053ae0`

## callees

- `0x140017e40`
- `0x1400535f8`
- `0x140053e08`
- `0x140053e68`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140053739`
- `ntoskrnl!ZwClose` at `0x140053739`
- `ntoskrnl!_snwprintf` at `0x1400536d9`
- `ntoskrnl!_snwprintf` at `0x1400536d9`

## string_xrefs

- `0x140053652`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x1400535f8  mov     [rsp-8+arg_8], rbx
0x1400535fd  push    rbp
0x1400535fe  push    rsi
0x1400535ff  push    rdi
0x140053600  push    r12
0x140053602  push    r13
0x140053604  push    r14
0x140053606  push    r15
0x140053608  lea     rbp, [rsp-1Fh]
0x14005360d  sub     rsp, 0F0h
0x140053614  mov     rax, cs:__security_cookie
0x14005361b  xor     rax, rsp
0x14005361e  mov     [rbp+4Fh+var_40], rax
0x140053622  mov     r12, [rbp+4Fh+arg_20]
0x140053626  xor     ebx, ebx
0x140053628  mov     [rbp+4Fh+Handle], rbx
0x14005362c  mov     r14, r9
0x14005362f  mov     [rbp+4Fh+var_A0], rbx
0x140053633  mov     r13d, r8d
0x140053636  mov     [rbp+4Fh+var_B0], ebx
0x140053639  mov     r15, rcx
0x14005363c  mov     [r12], rbx
0x140053640  test    r9, r9
0x140053643  jz      short loc_140053648
0x140053645  mov     [r9], ebx
0x140053648  lea     r9, [rbp+4Fh+Handle]
0x14005364c  mov     r8d, 20019h
0x140053652  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140053659  xor     ecx, ecx
0x14005365b  call    CmRegUtilOpenExistingWstrKey
0x140053660  test    eax, eax
0x140053662  js      loc_14005375B
0x140053668  movzx   ecx, byte ptr [r15+0Eh]
0x14005366d  movzx   edx, byte ptr [r15+0Dh]
0x140053672  movzx   r8d, byte ptr [r15+0Ch]
0x140053677  movzx   r9d, byte ptr [r15+0Bh]
0x14005367c  movzx   eax, byte ptr [r15+0Fh]
0x140053681  movzx   r10d, byte ptr [r15+0Ah]
0x140053686  movzx   r11d, byte ptr [r15+9]
0x14005368b  movzx   ebx, byte ptr [r15+8]
0x140053690  movzx   edi, word ptr [r15+6]
0x140053695  movzx   esi, word ptr [r15+4]
0x14005369a  mov     [rsp+120h+var_B8], eax
0x14005369e  mov     [rsp+120h+var_C0], ecx
0x1400536a2  lea     rcx, [rbp+4Fh+Dest]; Dest
0x1400536a6  mov     [rsp+120h+var_C8], edx
0x1400536aa  mov     edx, 27h ; '''; Count
0x1400536af  mov     [rsp+120h+var_D0], r8d
0x1400536b4  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x1400536bb  mov     [rsp+120h+var_D8], r9d
0x1400536c0  mov     r9d, [r15]
0x1400536c3  mov     [rsp+120h+var_E0], r10d
0x1400536c8  mov     [rsp+120h+var_E8], r11d
0x1400536cd  mov     dword ptr [rsp+120h+var_F0], ebx
0x1400536d1  mov     dword ptr [rsp+120h+var_F8], edi
0x1400536d5  mov     dword ptr [rsp+120h+var_100], esi
0x1400536d9  call    cs:__imp__snwprintf
0x1400536e0  nop     dword ptr [rax+rax+00h]
0x1400536e5  mov     rbx, [rbp+4Fh+Handle]
0x1400536e9  lea     rdx, [rbp+4Fh+Dest]
0x1400536ed  xor     eax, eax
0x1400536ef  mov     rcx, rbx
0x1400536f2  mov     [rbp+4Fh+var_44], ax
0x1400536f6  test    r13d, r13d
0x1400536f9  jz      short loc_140053720
0x1400536fb  lea     rax, [rbp+4Fh+var_A0]
0x1400536ff  mov     [rsp+120h+var_F0], rax
0x140053704  lea     rax, [rbp+4Fh+var_B0]
0x140053708  mov     [rsp+120h+var_F8], rax
0x14005370d  mov     [rsp+120h+var_100], 0
0x140053716  call    CmRegUtilCreateWstrKey
0x14005371b  mov     esi, [rbp+4Fh+var_B0]
0x14005371e  jmp     short loc_140053734
0x140053720  lea     r9, [rbp+4Fh+var_A0]
0x140053724  mov     r8d, 0F003Fh
0x14005372a  call    CmRegUtilOpenExistingWstrKey
0x14005372f  mov     esi, 2
0x140053734  mov     rcx, rbx; Handle
0x140053737  mov     edi, eax
0x140053739  call    cs:__imp_ZwClose
0x140053740  nop     dword ptr [rax+rax+00h]
0x140053745  test    edi, edi
0x140053747  js      short loc_140053759
0x140053749  mov     rax, [rbp+4Fh+var_A0]
0x14005374d  mov     [r12], rax
0x140053751  test    r14, r14
0x140053754  jz      short loc_140053759
0x140053756  mov     [r14], esi
0x140053759  mov     eax, edi
0x14005375b  mov     rcx, [rbp+4Fh+var_40]
0x14005375f  xor     rcx, rsp; StackCookie
0x140053762  call    __security_check_cookie
0x140053767  mov     rbx, [rsp+120h+arg_8]
0x14005376f  add     rsp, 0F0h
0x140053776  pop     r15
0x140053778  pop     r14
0x14005377a  pop     r13
0x14005377c  pop     r12
0x14005377e  pop     rdi
0x14005377f  pop     rsi
0x140053780  pop     rbp
0x140053781  retn
```
