# CWFPClientsHelperClass::ResolveAttributes(ulong,tagHELPER_ATTRIBUTE * const,ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180009e80`
- end: `0x18000a012`
- name: `?ResolveAttributes@CWFPClientsHelperClass@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@PEAKPEAPEAU2@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CWFPClientsHelperClass *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *const, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180008a4c`
- `0x180009e80`
- `0x18001130e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fd4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fcb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fd4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009f0d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180009f0d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009e9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWFPClientsHelperClass::ResolveAttributes(
        CWFPClientsHelperClass *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3,
        unsigned int *a4,
        struct tagHELPER_ATTRIBUTE **a5)
{
  OLECHAR *v8; // rbp
  signed int v9; // ebx
  struct tagHELPER_ATTRIBUTE *v10; // r14
  int v11; // ebx
  struct tagHELPER_ATTRIBUTE *v12; // rsi
  __int64 result; // rax
  struct tagHELPER_ATTRIBUTE *v14; // rax
  struct tagHELPER_ATTRIBUTE *v15; // rdi
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  __int64 v18; // rsi
  unsigned __int16 *v19; // rax

  v8 = (OLECHAR *)CoTaskMemAlloc(0x100u);
  if ( !v8 )
    goto LABEL_2;
  v10 = 0;
  v11 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      v12 = &a3[v11];
      if ( !wcscmp_0(v12->pwszName, L"providerguid") && v12->type == AT_GUID )
        break;
      if ( ++v11 >= a2 )
        goto LABEL_7;
    }
    v10 = &a3[v11];
  }
  else
  {
LABEL_7:
    if ( v11 == a2 )
      return 2147942487LL;
  }
  if ( !StringFromGUID2(&v10->Guid, v8, 128) )
  {
    v9 = -2147467259;
    goto LABEL_23;
  }
  *a4 = 1;
  v14 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(0x90u);
  v15 = v14;
  if ( !v14 )
  {
LABEL_2:
    v9 = -2147024882;
LABEL_23:
    CoTaskMemFree(v8);
    result = (unsigned int)v9;
    *a5 = 0;
    return result;
  }
  v14->pwszName = 0;
  v16 = 127;
  v17 = L"ProviderID";
  do
  {
    if ( !*v17 )
      break;
    ++v17;
    --v16;
  }
  while ( v16 );
  v9 = v16 == 0 ? 0x80070057 : 0;
  v18 = (127 - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
  {
LABEL_20:
    if ( v15->pwszName )
      CoTaskMemFree(v15->pwszName);
    CoTaskMemFree(v15);
    goto LABEL_23;
  }
  v19 = (unsigned __int16 *)CoTaskMemAlloc(2 * v18 + 2);
  v15->pwszName = v19;
  if ( !v19 )
  {
    v9 = -2147024882;
    goto LABEL_20;
  }
  v9 = StringCchCopyW(v19, v18 + 1, L"ProviderID");
  if ( v9 < 0 )
    goto LABEL_20;
  v15->type = AT_STRING;
  v15->Int64 = (LONGLONG)v8;
  *a5 = v15;
  return 0;
}

```

## disassembly

```asm
0x180009e80  push    rbx
0x180009e82  push    rbp
0x180009e83  push    rsi
0x180009e84  push    rdi
0x180009e85  push    r12
0x180009e87  push    r13
0x180009e89  push    r14
0x180009e8b  push    r15
0x180009e8d  sub     rsp, 28h
0x180009e91  mov     ecx, 100h; cb
0x180009e96  mov     r15, r9
0x180009e99  mov     r12, r8
0x180009e9c  mov     edi, edx
0x180009e9e  call    cs:__imp_CoTaskMemAlloc
0x180009ea4  xor     r13d, r13d
0x180009ea7  mov     rbp, rax
0x180009eaa  test    rax, rax
0x180009ead  jnz     short loc_180009EB9
0x180009eaf  mov     ebx, 8007000Eh
0x180009eb4  jmp     loc_180009FD1
0x180009eb9  mov     r14, r13
0x180009ebc  mov     ebx, r13d
0x180009ebf  test    edi, edi
0x180009ec1  jz      short loc_180009EEF
0x180009ec3  mov     eax, ebx
0x180009ec5  lea     rdx, aProviderguid; "providerguid"
0x180009ecc  lea     rsi, [rax+rax*8]
0x180009ed0  shl     rsi, 4
0x180009ed4  add     rsi, r12
0x180009ed7  mov     rcx, [rsi]; String1
0x180009eda  call    wcscmp_0
0x180009edf  test    eax, eax
0x180009ee1  jnz     short loc_180009EE9
0x180009ee3  cmp     dword ptr [rsi+8], 0Bh
0x180009ee7  jz      short loc_180009EFD
0x180009ee9  inc     ebx
0x180009eeb  cmp     ebx, edi
0x180009eed  jb      short loc_180009EC3
0x180009eef  cmp     ebx, edi
0x180009ef1  jnz     short loc_180009F00
0x180009ef3  mov     eax, 80070057h
0x180009ef8  jmp     loc_18000A001
0x180009efd  mov     r14, rsi
0x180009f00  lea     rcx, [r14+10h]; rguid
0x180009f04  mov     r8d, 80h; cchMax
0x180009f0a  mov     rdx, rbp; lpsz
0x180009f0d  call    cs:__imp_StringFromGUID2
0x180009f13  test    eax, eax
0x180009f15  jnz     short loc_180009F21
0x180009f17  mov     ebx, 80004005h
0x180009f1c  jmp     loc_180009FD1
0x180009f21  mov     ecx, 90h; cb
0x180009f26  mov     dword ptr [r15], 1
0x180009f2d  call    cs:__imp_CoTaskMemAlloc
0x180009f33  mov     rdi, rax
0x180009f36  test    rax, rax
0x180009f39  jz      loc_180009EAF
0x180009f3f  mov     edx, 7Fh
0x180009f44  mov     [rax], r13
0x180009f47  mov     ecx, edx
0x180009f49  lea     rax, aProviderid; "ProviderID"
0x180009f50  cmp     [rax], r13w
0x180009f54  jz      short loc_180009F60
0x180009f56  add     rax, 2
0x180009f5a  sub     rcx, 1
0x180009f5e  jnz     short loc_180009F50
0x180009f60  mov     rax, rcx
0x180009f63  neg     rax
0x180009f66  mov     rax, rcx
0x180009f69  sbb     ebx, ebx
0x180009f6b  sub     rdx, rcx
0x180009f6e  not     ebx
0x180009f70  and     ebx, 80070057h
0x180009f76  neg     rax
0x180009f79  sbb     rsi, rsi
0x180009f7c  and     rsi, rdx
0x180009f7f  test    rcx, rcx
0x180009f82  jz      short loc_180009FBA
0x180009f84  lea     rcx, ds:2[rsi*2]; cb
0x180009f8c  call    cs:__imp_CoTaskMemAlloc
0x180009f92  mov     [rdi], rax
0x180009f95  test    rax, rax
0x180009f98  jnz     short loc_180009FA1
0x180009f9a  mov     ebx, 8007000Eh
0x180009f9f  jmp     short loc_180009FBA
0x180009fa1  lea     rdx, [rsi+1]; unsigned __int64
0x180009fa5  mov     rcx, rax; unsigned __int16 *
0x180009fa8  lea     r8, aProviderid; "ProviderID"
0x180009faf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009fb4  mov     ebx, eax
0x180009fb6  test    eax, eax
0x180009fb8  jns     short loc_180009FE9
0x180009fba  mov     rcx, [rdi]; pv
0x180009fbd  test    rcx, rcx
0x180009fc0  jz      short loc_180009FC8
0x180009fc2  call    cs:__imp_CoTaskMemFree
0x180009fc8  mov     rcx, rdi; pv
0x180009fcb  call    cs:__imp_CoTaskMemFree
0x180009fd1  mov     rcx, rbp; pv
0x180009fd4  call    cs:__imp_CoTaskMemFree
0x180009fda  mov     rcx, [rsp+68h+arg_20]
0x180009fe2  mov     eax, ebx
0x180009fe4  mov     [rcx], r13
0x180009fe7  jmp     short loc_18000A001
0x180009fe9  mov     rax, [rsp+68h+arg_20]
0x180009ff1  mov     dword ptr [rdi+8], 0Ah
0x180009ff8  mov     [rdi+10h], rbp
0x180009ffc  mov     [rax], rdi
0x180009fff  xor     eax, eax
0x18000a001  add     rsp, 28h
0x18000a005  pop     r15
0x18000a007  pop     r14
0x18000a009  pop     r13
0x18000a00b  pop     r12
0x18000a00d  pop     rdi
0x18000a00e  pop     rsi
0x18000a00f  pop     rbp
0x18000a010  pop     rbx
0x18000a011  retn
```
