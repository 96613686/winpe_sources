# bCreateDCA(char const *,char const *,char const *,_devicemodeA *,int)

- ea: `0x1800255c4`
- end: `0x180025756`
- name: `?bCreateDCA@@YAPEAUHDC__@@PEBD00PEAU_devicemodeA@@H@Z`
- size: `402`
- prototype: `HDC __fastcall(const char *String1, PCSZ Source, PCSZ, DEVMODEA *, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800255a0`
- `0x1800281d0`
- `0x180028bac`

## callees

- `0x1800255c4`
- `0x180025760`
- `0x1800690b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002560e`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18002560e`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025631`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025710`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025631`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x180025710`
- `ntdll!RtlFreeHeap` at `0x1800256af`
- `ntdll!RtlFreeHeap` at `0x1800256af`
- `ntdll!RtlFreeUnicodeString` at `0x180025689`
- `ntdll!RtlFreeUnicodeString` at `0x18002574b`
- `ntdll!RtlFreeUnicodeString` at `0x180025689`
- `ntdll!RtlFreeUnicodeString` at `0x18002574b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800256c4`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800256ec`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800256c4`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x1800256ec`

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
0x1800255c4  push    rbx
0x1800255c6  push    rbp
0x1800255c7  push    rsi
0x1800255c8  push    rdi
0x1800255c9  push    r12
0x1800255cb  push    r14
0x1800255cd  push    r15
0x1800255cf  sub     rsp, 50h
0x1800255d3  xor     r12d, r12d
0x1800255d6  xorps   xmm0, xmm0
0x1800255d9  xorps   xmm1, xmm1
0x1800255dc  mov     r14, r9
0x1800255df  mov     r15, r8
0x1800255e2  mov     rdi, rdx
0x1800255e5  mov     rsi, rcx
0x1800255e8  movups  xmmword ptr [rsp+88h+Destination.Length], xmm0
0x1800255ed  movups  xmmword ptr [rsp+88h+var_48.Length], xmm1
0x1800255f2  test    rdx, rdx
0x1800255f5  jnz     short loc_180025621
0x1800255f7  xor     ebp, ebp
0x1800255f9  xor     ebx, ebx
0x1800255fb  test    rsi, rsi
0x1800255fe  jz      loc_1800256B7
0x180025604  lea     rdx, String1; "DISPLAY"
0x18002560b  mov     rcx, rsi
0x18002560e  call    cs:__imp__o__stricmp
0x180025614  test    eax, eax
0x180025616  jnz     loc_180025700
0x18002561c  lea     ebx, [rbp+1]
0x18002561f  jmp     short loc_180025647
0x180025621  mov     r8d, 0Bh; MaxCount
0x180025627  lea     rdx, String2; "\\\\.\\DISPLAY"
0x18002562e  mov     rcx, rdi; String1
0x180025631  call    cs:__imp__strnicmp
0x180025637  test    eax, eax
0x180025639  jnz     short loc_1800255F7
0x18002563b  mov     ebx, 1
0x180025640  jmp     short loc_1800256BC
0x180025642  lea     rbp, [rsp+88h+Destination]
0x180025647  xor     esi, esi
0x180025649  xor     edi, edi
0x18002564b  test    r15, r15
0x18002564e  jnz     loc_1800256E4
0x180025654  test    r14, r14
0x180025657  jnz     loc_180025722
0x18002565d  mov     edx, [rsp+88h+arg_20]
0x180025664  mov     r9d, ebx; int
0x180025667  mov     [rsp+88h+var_60], r12d; int
0x18002566c  mov     r8, rdi; struct _devicemodeW *
0x18002566f  mov     [rsp+88h+var_68], edx; int
0x180025673  mov     rcx, rbp; struct _UNICODE_STRING *
0x180025676  mov     rdx, rsi; struct _UNICODE_STRING *
0x180025679  call    ?hdcCreateDCW@@YAPEAUHDC__@@PEAU_UNICODE_STRING@@0PEBU_devicemodeW@@HHH@Z; hdcCreateDCW(_UNICODE_STRING *,_UNICODE_STRING *,_devicemodeW const *,int,int,int)
0x18002567e  mov     r12, rax
0x180025681  test    rbp, rbp
0x180025684  jz      short loc_18002568F
0x180025686  mov     rcx, rbp; UnicodeString
0x180025689  call    cs:__imp_RtlFreeUnicodeString
0x18002568f  test    rsi, rsi
0x180025692  jnz     loc_180025748
0x180025698  test    rdi, rdi
0x18002569b  jz      short loc_1800256D2
0x18002569d  mov     rcx, gs:60h
0x1800256a6  mov     r8, rdi; P
0x1800256a9  xor     edx, edx; Flags
0x1800256ab  mov     rcx, [rcx+30h]; HeapHandle
0x1800256af  call    cs:__imp_RtlFreeHeap
0x1800256b5  jmp     short loc_1800256D2
0x1800256b7  test    rdi, rdi
0x1800256ba  jz      short loc_180025647
0x1800256bc  mov     rdx, rdi; Source
0x1800256bf  lea     rcx, [rsp+88h+Destination]; Destination
0x1800256c4  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x1800256ca  test    al, al
0x1800256cc  jnz     loc_180025642
0x1800256d2  mov     rax, r12
0x1800256d5  add     rsp, 50h
0x1800256d9  pop     r15
0x1800256db  pop     r14
0x1800256dd  pop     r12
0x1800256df  pop     rdi
0x1800256e0  pop     rsi
0x1800256e1  pop     rbp
0x1800256e2  pop     rbx
0x1800256e3  retn
0x1800256e4  mov     rdx, r15; Source
0x1800256e7  lea     rcx, [rsp+88h+var_48]; Destination
0x1800256ec  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x1800256f2  test    al, al
0x1800256f4  jz      short loc_180025681
0x1800256f6  lea     rsi, [rsp+88h+var_48]
0x1800256fb  jmp     loc_180025654
0x180025700  mov     r8d, 0Bh; MaxCount
0x180025706  lea     rdx, String2; "\\\\.\\DISPLAY"
0x18002570d  mov     rcx, rsi; String1
0x180025710  call    cs:__imp__strnicmp
0x180025716  test    eax, eax
0x180025718  jnz     short loc_1800256B7
0x18002571a  mov     rdi, rsi
0x18002571d  jmp     loc_18002563B
0x180025722  test    ebx, ebx
0x180025724  jz      short loc_18002572F
0x180025726  cmp     [r14], dil
0x180025729  jz      loc_18002565D
0x18002572f  mov     rcx, r14; DEVMODEA *
0x180025732  call    GdiConvertToDevmodeW
0x180025737  mov     rdi, rax
0x18002573a  test    rax, rax
0x18002573d  jz      loc_180025681
0x180025743  jmp     loc_18002565D
0x180025748  mov     rcx, rsi; UnicodeString
0x18002574b  call    cs:__imp_RtlFreeUnicodeString
0x180025751  jmp     loc_180025698
```
