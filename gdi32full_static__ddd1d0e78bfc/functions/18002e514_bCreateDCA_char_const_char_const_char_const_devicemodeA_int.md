# bCreateDCA(char const *,char const *,char const *,_devicemodeA *,int)

- ea: `0x18002e514`
- end: `0x18002e6e2`
- name: `?bCreateDCA@@YAPEAUHDC__@@PEBD00PEAU_devicemodeA@@H@Z`
- size: `462`
- prototype: `HDC __fastcall(const char *String1, PCSZ Source, PCSZ, DEVMODEA *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002e4f0`
- `0x180031580`
- `0x180032004`

## callees

- `0x18002e514`
- `0x18002e6f0`
- `0x18006d4d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002e55e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002e55e`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002e587`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002e690`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002e587`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x18002e690`
- `ntdll!RtlFreeHeap` at `0x18002e614`
- `ntdll!RtlFreeHeap` at `0x18002e614`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5e8`
- `ntdll!RtlFreeUnicodeString` at `0x18002e6d1`
- `ntdll!RtlFreeUnicodeString` at `0x18002e5e8`
- `ntdll!RtlFreeUnicodeString` at `0x18002e6d1`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e633`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e662`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e633`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e662`

## pseudocode

```c
HDC __fastcall bCreateDCA(const char *String1, PCSZ Source, PCSZ a3, DEVMODEA *a4, int a5)
{
  HDC DCW; // r12
  const char *v8; // rdi
  struct _UNICODE_STRING *p_Destination; // rbp
  int v11; // ebx
  struct _UNICODE_STRING *v12; // rsi
  DEVMODEW *v13; // rdi
  _UNICODE_STRING Destination; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING v16; // [rsp+40h] [rbp-48h] BYREF

  DCW = 0;
  v8 = Source;
  Destination = 0;
  v16 = 0;
  if ( !Source || _strnicmp(Source, "\\\\.\\DISPLAY", 0xBu) )
  {
    p_Destination = 0;
    v11 = 0;
    if ( !String1 )
      goto LABEL_17;
    if ( !(unsigned int)_o__stricmp(String1, "DISPLAY") )
    {
      v11 = 1;
      goto LABEL_8;
    }
    if ( _strnicmp(String1, "\\\\.\\DISPLAY", 0xBu) )
    {
LABEL_17:
      if ( !v8 )
        goto LABEL_8;
      goto LABEL_18;
    }
    v8 = String1;
  }
  v11 = 1;
LABEL_18:
  if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, v8) )
    return DCW;
  p_Destination = &Destination;
LABEL_8:
  v12 = 0;
  v13 = 0;
  if ( !a3 )
    goto LABEL_9;
  if ( RtlCreateUnicodeStringFromAsciiz(&v16, a3) )
  {
    v12 = &v16;
LABEL_9:
    if ( !a4 || v11 && !a4->dmDeviceName[0] || (v13 = GdiConvertToDevmodeW(a4)) != 0 )
      DCW = hdcCreateDCW(p_Destination, v12, v13, v11, a5, 0);
  }
  if ( p_Destination )
    RtlFreeUnicodeString(p_Destination);
  if ( v12 )
    RtlFreeUnicodeString(v12);
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  return DCW;
}

```

## disassembly

```asm
0x18002e514  push    rbx
0x18002e516  push    rbp
0x18002e517  push    rsi
0x18002e518  push    rdi
0x18002e519  push    r12
0x18002e51b  push    r14
0x18002e51d  push    r15
0x18002e51f  sub     rsp, 50h
0x18002e523  xor     r12d, r12d
0x18002e526  xorps   xmm0, xmm0
0x18002e529  xorps   xmm1, xmm1
0x18002e52c  mov     r14, r9
0x18002e52f  mov     r15, r8
0x18002e532  mov     rdi, rdx
0x18002e535  mov     rsi, rcx
0x18002e538  movups  xmmword ptr [rsp+88h+Destination.Length], xmm0
0x18002e53d  movups  xmmword ptr [rsp+88h+var_48.Length], xmm1
0x18002e542  test    rdx, rdx
0x18002e545  jnz     short loc_18002E577
0x18002e547  xor     ebp, ebp
0x18002e549  xor     ebx, ebx
0x18002e54b  test    rsi, rsi
0x18002e54e  jz      loc_18002E622
0x18002e554  lea     rdx, String1; "DISPLAY"
0x18002e55b  mov     rcx, rsi
0x18002e55e  call    cs:__imp__o__stricmp
0x18002e565  nop     dword ptr [rax+rax+00h]
0x18002e56a  test    eax, eax
0x18002e56c  jnz     loc_18002E680
0x18002e572  lea     ebx, [rbp+1]
0x18002e575  jmp     short loc_18002E5A6
0x18002e577  mov     r8d, 0Bh; MaxCount
0x18002e57d  lea     rdx, aDevadev2gujrgj+48h; "\\\\.\\DISPLAY"
0x18002e584  mov     rcx, rdi; String1
0x18002e587  call    cs:__imp__strnicmp
0x18002e58e  nop     dword ptr [rax+rax+00h]
0x18002e593  test    eax, eax
0x18002e595  jnz     short loc_18002E547
0x18002e597  mov     ebx, 1
0x18002e59c  jmp     loc_18002E62B
0x18002e5a1  lea     rbp, [rsp+88h+Destination]
0x18002e5a6  xor     esi, esi
0x18002e5a8  xor     edi, edi
0x18002e5aa  test    r15, r15
0x18002e5ad  jnz     loc_18002E65A
0x18002e5b3  test    r14, r14
0x18002e5b6  jnz     loc_18002E6A8
0x18002e5bc  mov     edx, [rsp+88h+arg_20]
0x18002e5c3  mov     r9d, ebx; int
0x18002e5c6  mov     [rsp+88h+var_60], r12d; int
0x18002e5cb  mov     r8, rdi; struct _devicemodeW *
0x18002e5ce  mov     [rsp+88h+var_68], edx; int
0x18002e5d2  mov     rcx, rbp; struct _UNICODE_STRING *
0x18002e5d5  mov     rdx, rsi; struct _UNICODE_STRING *
0x18002e5d8  call    ?hdcCreateDCW@@YAPEAUHDC__@@PEAU_UNICODE_STRING@@0PEBU_devicemodeW@@HHH@Z; hdcCreateDCW(_UNICODE_STRING *,_UNICODE_STRING *,_devicemodeW const *,int,int,int)
0x18002e5dd  mov     r12, rax
0x18002e5e0  test    rbp, rbp
0x18002e5e3  jz      short loc_18002E5F4
0x18002e5e5  mov     rcx, rbp; UnicodeString
0x18002e5e8  call    cs:__imp_RtlFreeUnicodeString
0x18002e5ef  nop     dword ptr [rax+rax+00h]
0x18002e5f4  test    rsi, rsi
0x18002e5f7  jnz     loc_18002E6CE
0x18002e5fd  test    rdi, rdi
0x18002e600  jz      short loc_18002E647
0x18002e602  mov     rcx, gs:60h
0x18002e60b  mov     r8, rdi; P
0x18002e60e  xor     edx, edx; Flags
0x18002e610  mov     rcx, [rcx+30h]; HeapHandle
0x18002e614  call    cs:__imp_RtlFreeHeap
0x18002e61b  nop     dword ptr [rax+rax+00h]
0x18002e620  jmp     short loc_18002E647
0x18002e622  test    rdi, rdi
0x18002e625  jz      loc_18002E5A6
0x18002e62b  mov     rdx, rdi; Source
0x18002e62e  lea     rcx, [rsp+88h+Destination]; Destination
0x18002e633  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18002e63a  nop     dword ptr [rax+rax+00h]
0x18002e63f  test    al, al
0x18002e641  jnz     loc_18002E5A1
0x18002e647  mov     rax, r12
0x18002e64a  add     rsp, 50h
0x18002e64e  pop     r15
0x18002e650  pop     r14
0x18002e652  pop     r12
0x18002e654  pop     rdi
0x18002e655  pop     rsi
0x18002e656  pop     rbp
0x18002e657  pop     rbx
0x18002e658  retn
0x18002e65a  mov     rdx, r15; Source
0x18002e65d  lea     rcx, [rsp+88h+var_48]; Destination
0x18002e662  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18002e669  nop     dword ptr [rax+rax+00h]
0x18002e66e  test    al, al
0x18002e670  jz      loc_18002E5E0
0x18002e676  lea     rsi, [rsp+88h+var_48]
0x18002e67b  jmp     loc_18002E5B3
0x18002e680  mov     r8d, 0Bh; MaxCount
0x18002e686  lea     rdx, aDevadev2gujrgj+48h; "\\\\.\\DISPLAY"
0x18002e68d  mov     rcx, rsi; String1
0x18002e690  call    cs:__imp__strnicmp
0x18002e697  nop     dword ptr [rax+rax+00h]
0x18002e69c  test    eax, eax
0x18002e69e  jnz     short loc_18002E622
0x18002e6a0  mov     rdi, rsi
0x18002e6a3  jmp     loc_18002E597
0x18002e6a8  test    ebx, ebx
0x18002e6aa  jz      short loc_18002E6B5
0x18002e6ac  cmp     [r14], dil
0x18002e6af  jz      loc_18002E5BC
0x18002e6b5  mov     rcx, r14; DEVMODEA *
0x18002e6b8  call    GdiConvertToDevmodeW
0x18002e6bd  mov     rdi, rax
0x18002e6c0  test    rax, rax
0x18002e6c3  jz      loc_18002E5E0
0x18002e6c9  jmp     loc_18002E5BC
0x18002e6ce  mov     rcx, rsi; UnicodeString
0x18002e6d1  call    cs:__imp_RtlFreeUnicodeString
0x18002e6d8  nop     dword ptr [rax+rax+00h]
0x18002e6dd  jmp     loc_18002E5FD
```
