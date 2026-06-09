# PiRegStateOpenClassKey

- ea: `0x140046508`
- end: `0x140046693`
- name: `PiRegStateOpenClassKey`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140046884`
- `0x1400469f0`

## callees

- `0x140030f40`
- `0x140046508`
- `0x140046d18`
- `0x140046d78`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140046649`
- `ntoskrnl!ZwClose` at `0x140046649`
- `ntoskrnl!_snwprintf` at `0x1400465e9`
- `ntoskrnl!_snwprintf` at `0x1400465e9`

## string_xrefs

- `0x140046562`: `\Registry\Machine\System\CurrentControlSet\Control\Class`

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
0x140046508  mov     [rsp-8+arg_8], rbx
0x14004650d  push    rbp
0x14004650e  push    rsi
0x14004650f  push    rdi
0x140046510  push    r12
0x140046512  push    r13
0x140046514  push    r14
0x140046516  push    r15
0x140046518  lea     rbp, [rsp-1Fh]
0x14004651d  sub     rsp, 0F0h
0x140046524  mov     rax, cs:__security_cookie
0x14004652b  xor     rax, rsp
0x14004652e  mov     [rbp+4Fh+var_40], rax
0x140046532  mov     r12, [rbp+4Fh+arg_20]
0x140046536  xor     ebx, ebx
0x140046538  mov     [rbp+4Fh+Handle], rbx
0x14004653c  mov     r14, r9
0x14004653f  mov     [rbp+4Fh+var_A0], rbx
0x140046543  mov     r13d, r8d
0x140046546  mov     [rbp+4Fh+var_B0], ebx
0x140046549  mov     r15, rcx
0x14004654c  mov     [r12], rbx
0x140046550  test    r9, r9
0x140046553  jz      short loc_140046558
0x140046555  mov     [r9], ebx
0x140046558  lea     r9, [rbp+4Fh+Handle]
0x14004655c  mov     r8d, 20019h
0x140046562  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140046569  xor     ecx, ecx
0x14004656b  call    CmRegUtilOpenExistingWstrKey
0x140046570  test    eax, eax
0x140046572  js      loc_14004666B
0x140046578  movzx   ecx, byte ptr [r15+0Eh]
0x14004657d  movzx   edx, byte ptr [r15+0Dh]
0x140046582  movzx   r8d, byte ptr [r15+0Ch]
0x140046587  movzx   r9d, byte ptr [r15+0Bh]
0x14004658c  movzx   eax, byte ptr [r15+0Fh]
0x140046591  movzx   r10d, byte ptr [r15+0Ah]
0x140046596  movzx   r11d, byte ptr [r15+9]
0x14004659b  movzx   ebx, byte ptr [r15+8]
0x1400465a0  movzx   edi, word ptr [r15+6]
0x1400465a5  movzx   esi, word ptr [r15+4]
0x1400465aa  mov     [rsp+120h+var_B8], eax
0x1400465ae  mov     [rsp+120h+var_C0], ecx
0x1400465b2  lea     rcx, [rbp+4Fh+Dest]; Dest
0x1400465b6  mov     [rsp+120h+var_C8], edx
0x1400465ba  mov     edx, 27h ; '''; Count
0x1400465bf  mov     [rsp+120h+var_D0], r8d
0x1400465c4  lea     r8, a08x04x04x02x02; "{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%0"...
0x1400465cb  mov     [rsp+120h+var_D8], r9d
0x1400465d0  mov     r9d, [r15]
0x1400465d3  mov     [rsp+120h+var_E0], r10d
0x1400465d8  mov     [rsp+120h+var_E8], r11d
0x1400465dd  mov     dword ptr [rsp+120h+var_F0], ebx
0x1400465e1  mov     dword ptr [rsp+120h+var_F8], edi
0x1400465e5  mov     dword ptr [rsp+120h+var_100], esi
0x1400465e9  call    cs:__imp__snwprintf
0x1400465f0  nop     dword ptr [rax+rax+00h]
0x1400465f5  mov     rbx, [rbp+4Fh+Handle]
0x1400465f9  lea     rdx, [rbp+4Fh+Dest]
0x1400465fd  xor     eax, eax
0x1400465ff  mov     rcx, rbx
0x140046602  mov     [rbp+4Fh+var_44], ax
0x140046606  test    r13d, r13d
0x140046609  jz      short loc_140046630
0x14004660b  lea     rax, [rbp+4Fh+var_A0]
0x14004660f  mov     [rsp+120h+var_F0], rax
0x140046614  lea     rax, [rbp+4Fh+var_B0]
0x140046618  mov     [rsp+120h+var_F8], rax
0x14004661d  mov     [rsp+120h+var_100], 0
0x140046626  call    CmRegUtilCreateWstrKey
0x14004662b  mov     esi, [rbp+4Fh+var_B0]
0x14004662e  jmp     short loc_140046644
0x140046630  lea     r9, [rbp+4Fh+var_A0]
0x140046634  mov     r8d, 0F003Fh
0x14004663a  call    CmRegUtilOpenExistingWstrKey
0x14004663f  mov     esi, 2
0x140046644  mov     rcx, rbx; Handle
0x140046647  mov     edi, eax
0x140046649  call    cs:__imp_ZwClose
0x140046650  nop     dword ptr [rax+rax+00h]
0x140046655  test    edi, edi
0x140046657  js      short loc_140046669
0x140046659  mov     rax, [rbp+4Fh+var_A0]
0x14004665d  mov     [r12], rax
0x140046661  test    r14, r14
0x140046664  jz      short loc_140046669
0x140046666  mov     [r14], esi
0x140046669  mov     eax, edi
0x14004666b  mov     rcx, [rbp+4Fh+var_40]
0x14004666f  xor     rcx, rsp; StackCookie
0x140046672  call    __security_check_cookie
0x140046677  mov     rbx, [rsp+120h+arg_8]
0x14004667f  add     rsp, 0F0h
0x140046686  pop     r15
0x140046688  pop     r14
0x14004668a  pop     r13
0x14004668c  pop     r12
0x14004668e  pop     rdi
0x14004668f  pop     rsi
0x140046690  pop     rbp
0x140046691  retn
```
