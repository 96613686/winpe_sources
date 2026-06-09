# NfsGetMappingConfiguration(_MI_Context *,_MSFT_NfsMappingStore_Self *)

- ea: `0x180010a7c`
- end: `0x180010cf9`
- name: `?NfsGetMappingConfiguration@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_MSFT_NfsMappingStore_Self@@@Z`
- size: `637`
- prototype: `enum _MI_Result __fastcall(MI_Instance *self, struct _MSFT_NfsMappingStore_Self *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008f80`

## callees

- `0x1800098c4`
- `0x18000be78`
- `0x18000e030`
- `0x18000eae4`
- `0x18000ec88`
- `0x18000efc8`
- `0x18000f544`
- `0x180010184`
- `0x180010a7c`
- `0x180013a40`
- `0x180014588`
- `0x18002143c`
- `0x180021598`
- `0x180035b02`
- `0x180035b40`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010c31`
- `KERNEL32!GetLastError` at `0x180010c31`
- `KERNEL32!GetFileAttributesW` at `0x180010c1e`
- `KERNEL32!GetFileAttributesW` at `0x180010c1e`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180010bc3`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180010bc3`

## string_xrefs

- `0x180010bf5`: `\system32\drivers\etc\passwd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NfsGetMappingConfiguration(MI_Instance *self, struct _MSFT_NfsMappingStore_Self *a2)
{
  enum _MI_Result CimProperty; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  const WCHAR *v8; // rcx
  LPCWSTR *v9; // r9
  __int64 v10; // rdx
  const wchar_t *v12; // [rsp+30h] [rbp-D0h] BYREF
  struct _MSFT_NfsMappingStore_Self *v13; // [rsp+38h] [rbp-C8h] BYREF
  int v14; // [rsp+40h] [rbp-C0h]
  _QWORD v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v16; // [rsp+58h] [rbp-A8h]
  MI_Instance *v17; // [rsp+60h] [rbp-A0h]
  int v18; // [rsp+68h] [rbp-98h]
  __int64 v19; // [rsp+6Ch] [rbp-94h]
  _BYTE v20[48]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v22; // [rsp+C0h] [rbp-40h]
  MI_Instance selfa; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v24; // [rsp+178h] [rbp+78h]
  WCHAR Buffer[264]; // [rsp+180h] [rbp+80h] BYREF

  v22 = 7;
  lpFileName[2] = 0;
  LOWORD(lpFileName[0]) = 0;
  memset_0(&selfa, 0, 0xB0u);
  v15[0] = &CWMIContext::`vftable';
  v17 = self;
  v15[1] = 0;
  v16 = 0;
  v19 = 0;
  v18 = 0;
  CNfsRegHive::CNfsRegHive((CNfsRegHive *)v20, 1);
  v13 = a2;
  v14 = 0;
  CLock::AcquireLock((CLock *)&v13);
  if ( !self || !self->ft )
  {
    CimProperty = MI_RESULT_INVALID_PARAMETER;
LABEL_20:
    if ( !self )
      goto LABEL_23;
    goto LABEL_21;
  }
  CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, void *, MI_Instance *))self->ft->IsA)(
                  self,
                  &MSFT_NfsMappingStore_rtti,
                  &selfa);
  if ( CimProperty )
    goto LABEL_20;
  v12 = L"nfsunm";
  CimProperty = ((unsigned int (__fastcall *)(MI_Instance *, _QWORD, const wchar_t **, __int64, _DWORD))selfa.ft->SetElementAt)(
                  &selfa,
                  0,
                  &v12,
                  13,
                  0);
  if ( CimProperty == MI_RESULT_OK )
  {
    CimProperty = NfsGetCimProperty(&selfa, (struct _NFS_CIMPROPERTY_REGKEY_PAIR *)off_180054B00, 7u);
    if ( CimProperty == MI_RESULT_OK )
    {
      if ( GetSystemWindowsDirectoryW(Buffer, 0x105u) - 1 > 0x103 )
      {
        CimProperty = MI_RESULT_FAILED;
      }
      else
      {
        v5 = std::char_traits<unsigned short>::length(Buffer);
        std::wstring::assign(lpFileName, Buffer, v5);
        v6 = std::char_traits<unsigned short>::length(L"\\system32\\drivers\\etc\\passwd");
        std::wstring::append(lpFileName, v7, v6);
        v8 = (const WCHAR *)lpFileName;
        if ( v22 >= 8 )
          v8 = lpFileName[0];
        if ( GetFileAttributesW(v8) == -1 )
        {
          if ( GetLastError() == 2 )
          {
            v24 = 256;
          }
          else
          {
            v9 = lpFileName;
            if ( v22 >= 8 )
              v9 = (LPCWSTR *)lpFileName[0];
            CWMIContext::WriteError((CWMIContext *)v15, 0, 0xC0001024, v9);
          }
        }
        else
        {
          v24 = 257;
        }
        CimProperty = MI_Instance_Destruct(self);
      }
    }
  }
  MI_Instance_Destruct(&selfa);
LABEL_21:
  if ( self->ft )
    ((void (__fastcall *)(MI_Instance *, _QWORD))self->ft->Clone)(self, (unsigned int)CimProperty);
LABEL_23:
  CLock::ReleaseLock((CLock *)&v13);
  CNfsRegHive::~CNfsRegHive((CNfsRegHive *)v20);
  CWMIContext::~CWMIContext((CWMIContext *)v15);
  LOBYTE(v10) = 1;
  std::wstring::_Tidy(lpFileName, v10, 0);
  return (unsigned int)CimProperty;
}

```

## disassembly

```asm
0x180010a7c  mov     [rsp-8+arg_8], rbx
0x180010a81  mov     [rsp-8+arg_10], rdi
0x180010a86  push    rbp
0x180010a87  lea     rbp, [rsp-2A0h]
0x180010a8f  sub     rsp, 3A0h
0x180010a96  mov     rax, cs:__security_cookie
0x180010a9d  xor     rax, rsp
0x180010aa0  mov     [rbp+2A0h+var_10], rax
0x180010aa7  mov     rbx, rdx
0x180010aaa  mov     rdi, rcx
0x180010aad  mov     [rbp+2A0h+var_2E0], 7
0x180010ab5  mov     [rbp+2A0h+var_2E8], 0
0x180010abd  xor     eax, eax
0x180010abf  mov     word ptr [rbp+2A0h+lpFileName], ax
0x180010ac3  xor     edx, edx; Val
0x180010ac5  mov     r8d, 0B0h; Size
0x180010acb  lea     rcx, [rbp+2A0h+self]; void *
0x180010acf  call    memset_0
0x180010ad4  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180010adb  mov     [rsp+3A0h+var_358], rax
0x180010ae0  mov     [rsp+3A0h+var_340], rdi
0x180010ae5  mov     [rsp+3A0h+var_350], 0
0x180010aee  mov     [rsp+3A0h+var_348], 0
0x180010af5  mov     [rsp+3A0h+var_334], 0
0x180010afe  mov     [rsp+3A0h+var_338], 0
0x180010b06  mov     edx, 1; int
0x180010b0b  lea     rcx, [rsp+3A0h+var_328]; this
0x180010b10  call    ??0CNfsRegHive@@QEAA@H@Z; CNfsRegHive::CNfsRegHive(int)
0x180010b15  nop
0x180010b16  mov     [rsp+3A0h+var_368], rbx
0x180010b1b  mov     [rsp+3A0h+var_360], 0
0x180010b23  lea     rcx, [rsp+3A0h+var_368]; this
0x180010b28  call    ?AcquireLock@CLock@@QEAAXXZ; CLock::AcquireLock(void)
0x180010b2d  test    rdi, rdi
0x180010b30  jz      loc_180010C84
0x180010b36  mov     rax, [rdi]
0x180010b39  test    rax, rax
0x180010b3c  jz      loc_180010C84
0x180010b42  lea     r8, [rbp+2A0h+self]
0x180010b46  lea     rdx, MSFT_NfsMappingStore_rtti
0x180010b4d  mov     rcx, rdi
0x180010b50  mov     rax, [rax+18h]
0x180010b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b59  mov     ebx, eax
0x180010b5b  test    eax, eax
0x180010b5d  jnz     loc_180010C89
0x180010b63  lea     rax, aNfsunm; "nfsunm"
0x180010b6a  mov     [rsp+3A0h+var_370], rax
0x180010b6f  mov     rax, [rbp+2A0h+self.ft]
0x180010b73  mov     [rsp+3A0h+var_380], ebx
0x180010b77  lea     r9d, [rbx+0Dh]
0x180010b7b  lea     r8, [rsp+3A0h+var_370]
0x180010b80  xor     edx, edx
0x180010b82  lea     rcx, [rbp+2A0h+self]
0x180010b86  mov     rax, [rax+50h]
0x180010b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8f  mov     ebx, eax
0x180010b91  test    eax, eax
0x180010b93  jnz     loc_180010C79
0x180010b99  lea     r8d, [rax+7]; unsigned int
0x180010b9d  lea     rdx, off_180054B00; struct _NFS_CIMPROPERTY_REGKEY_PAIR *
0x180010ba4  lea     rcx, [rbp+2A0h+self]; self
0x180010ba8  call    ?NfsGetCimProperty@@YA?AW4_MI_Result@@PEAU_MI_Instance@@PEAU_NFS_CIMPROPERTY_REGKEY_PAIR@@K@Z; NfsGetCimProperty(_MI_Instance *,_NFS_CIMPROPERTY_REGKEY_PAIR *,ulong)
0x180010bad  mov     ebx, eax
0x180010baf  test    eax, eax
0x180010bb1  jnz     loc_180010C79
0x180010bb7  mov     edx, 105h; uSize
0x180010bbc  lea     rcx, [rbp+2A0h+Buffer]; lpBuffer
0x180010bc3  call    cs:__imp_GetSystemWindowsDirectoryW
0x180010bc9  dec     eax
0x180010bcb  cmp     eax, 103h
0x180010bd0  ja      loc_180010C74
0x180010bd6  lea     rcx, [rbp+2A0h+Buffer]
0x180010bdd  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180010be2  mov     r8, rax
0x180010be5  lea     rdx, [rbp+2A0h+Buffer]
0x180010bec  lea     rcx, [rbp+2A0h+lpFileName]
0x180010bf0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180010bf5  lea     rcx, aSystem32Driver; "\\system32\\drivers\\etc\\passwd"
0x180010bfc  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180010c01  mov     r8, rax
0x180010c04  mov     rdx, rcx
0x180010c07  lea     rcx, [rbp+2A0h+lpFileName]
0x180010c0b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180010c10  lea     rcx, [rbp+2A0h+lpFileName]
0x180010c14  cmp     [rbp+2A0h+var_2E0], 8
0x180010c19  cmovnb  rcx, [rbp+2A0h+lpFileName]; lpFileName
0x180010c1e  call    cs:__imp_GetFileAttributesW
0x180010c24  cmp     eax, 0FFFFFFFFh
0x180010c27  jz      short loc_180010C31
0x180010c29  mov     [rbp+2A0h+var_228], 101h
0x180010c2f  jmp     short loc_180010C64
0x180010c31  call    cs:__imp_GetLastError
0x180010c37  cmp     eax, 2
0x180010c3a  jnz     short loc_180010C44
0x180010c3c  mov     [rbp+2A0h+var_228], 100h
0x180010c42  jmp     short loc_180010C64
0x180010c44  lea     r9, [rbp+2A0h+lpFileName]
0x180010c48  cmp     [rbp+2A0h+var_2E0], 8
0x180010c4d  cmovnb  r9, [rbp+2A0h+lpFileName]
0x180010c52  xor     edx, edx; unsigned int
0x180010c54  mov     r8d, 0C0001024h; unsigned int
0x180010c5a  lea     rcx, [rsp+3A0h+var_358]; this
0x180010c5f  call    ?WriteError@CWMIContext@@UEAAXKKZZ; CWMIContext::WriteError(ulong,ulong,...)
0x180010c64  lea     rdx, [rbp+2A0h+self]
0x180010c68  mov     rcx, rdi; self
0x180010c6b  call    MI_Instance_Destruct
0x180010c70  mov     ebx, eax
0x180010c72  jmp     short loc_180010C79
0x180010c74  mov     ebx, 1
0x180010c79  lea     rcx, [rbp+2A0h+self]; self
0x180010c7d  call    MI_Instance_Destruct
0x180010c82  jmp     short loc_180010C8E
0x180010c84  mov     ebx, 4
0x180010c89  test    rdi, rdi
0x180010c8c  jz      short loc_180010CA4
0x180010c8e  mov     rax, [rdi]
0x180010c91  test    rax, rax
0x180010c94  jz      short loc_180010CA4
0x180010c96  mov     edx, ebx
0x180010c98  mov     rcx, rdi
0x180010c9b  mov     rax, [rax]
0x180010c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ca3  nop
0x180010ca4  lea     rcx, [rsp+3A0h+var_368]; this
0x180010ca9  call    ?ReleaseLock@CLock@@QEAAXXZ; CLock::ReleaseLock(void)
0x180010cae  nop
0x180010caf  lea     rcx, [rsp+3A0h+var_328]; this
0x180010cb4  call    ??1CNfsRegHive@@QEAA@XZ; CNfsRegHive::~CNfsRegHive(void)
0x180010cb9  nop
0x180010cba  lea     rcx, [rsp+3A0h+var_358]; this
0x180010cbf  call    ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
0x180010cc4  nop
0x180010cc5  xor     r8d, r8d
0x180010cc8  mov     dl, 1
0x180010cca  lea     rcx, [rbp+2A0h+lpFileName]
0x180010cce  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180010cd3  mov     eax, ebx
0x180010cd5  mov     rcx, [rbp+2A0h+var_10]
0x180010cdc  xor     rcx, rsp; StackCookie
0x180010cdf  call    __security_check_cookie
0x180010ce4  lea     r11, [rsp+3A0h+var_s0]
0x180010cec  mov     rbx, [r11+18h]
0x180010cf0  mov     rdi, [r11+20h]
0x180010cf4  mov     rsp, r11
0x180010cf7  pop     rbp
0x180010cf8  retn
```
