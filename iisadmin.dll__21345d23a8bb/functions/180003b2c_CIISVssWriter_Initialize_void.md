# CIISVssWriter::Initialize(void)

- ea: `0x180003b2c`
- end: `0x180003c9c`
- name: `?Initialize@CIISVssWriter@@QEAAHXZ`
- size: `368`
- prototype: `__int64 __fastcall(CIISVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800038d0`

## callees

- `0x180003b2c`
- `0x180005010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003c35`
- `ole32!CoCreateInstance` at `0x180003c35`
- `VSSAPI!CreateWriter` at `0x180003b6b`
- `VSSAPI!CreateWriter` at `0x180003b6b`
- `IisRTL!PuDbgPrint` at `0x180003c73`
- `IisRTL!PuDbgPrint` at `0x180003c73`

## string_xrefs

- `0x180003b7e`: `IIS Metabase Writer`
- `0x180003c60`: `CIISVssWriter::Initialize`
- `0x180003c67`: `inetsrv\iis\mb\iisadmin\mdwriter.cxx`
- `0x180003c52`: `Error creating MDCOM object.  hr = %x\n`

## pseudocode

```c
__int64 __fastcall CIISVssWriter::Initialize(CIISVssWriter *this)
{
  struct CIISVssWriter *v1; // rsi
  _QWORD *v2; // rdi
  int Writer; // ebx
  __int64 v4; // rcx
  __int64 (__fastcall *v5)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char); // rax
  HRESULT Instance; // eax
  __int64 v8; // [rsp+28h] [rbp-70h]
  char v9; // [rsp+58h] [rbp-40h]
  __int128 v10; // [rsp+70h] [rbp-28h] BYREF

  v1 = g_pIISVssWriter;
  v2 = (_QWORD *)((char *)g_pIISVssWriter + 8);
  if ( *((_QWORD *)g_pIISVssWriter + 1) )
  {
    Writer = -2147467259;
    goto LABEL_6;
  }
  Writer = CreateWriter(g_pIISVssWriter, (char *)g_pIISVssWriter + 8);
  if ( Writer < 0 )
  {
LABEL_6:
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v8) = Writer;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        97,
        "CIISVssWriter::Initialize",
        "Error in base object Initialize().  hr = %x\n",
        v8);
    }
    return 0;
  }
  v4 = *v2;
  v9 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int128 *, const wchar_t *, _QWORD, _DWORD, _DWORD, int, int, int, int, int, char))(*(_QWORD *)*v2 + 24LL);
  v10 = xmmword_180006FB8;
  Writer = v5(v4, &v10, L"IIS Metabase Writer", 0, 0, 0, 2, 3, 3, 60000, 1, v9);
  if ( Writer < 0 )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
    goto LABEL_6;
  }
  Instance = CoCreateInstance(&CLSID_MSAdminBase_W, 0, 0x15u, &IID_IMSAdminBase_W, (LPVOID *)v1 + 2);
  if ( Instance < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(v8) = Instance;
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cxx",
        107,
        "CIISVssWriter::Initialize",
        "Error creating MDCOM object.  hr = %x\n",
        v8);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180003b2c  mov     rax, rsp
0x180003b2f  mov     [rax+8], rbx
0x180003b33  mov     [rax+10h], rsi
0x180003b37  push    rdi
0x180003b38  sub     rsp, 90h
0x180003b3f  mov     rsi, cs:?g_pIISVssWriter@@3PEAVCIISVssWriter@@EA; CIISVssWriter * g_pIISVssWriter
0x180003b46  movaps  xmmword ptr [rax-18h], xmm6
0x180003b4a  lea     rdi, [rsi+8]
0x180003b4e  cmp     qword ptr [rdi], 0
0x180003b52  jz      short loc_180003B5E
0x180003b54  mov     ebx, 80004005h
0x180003b59  jmp     loc_180003BFC
0x180003b5e  movups  xmm6, cs:xmmword_180006FB8
0x180003b65  mov     rdx, rdi
0x180003b68  mov     rcx, rsi
0x180003b6b  call    cs:__imp_CreateWriter
0x180003b71  mov     ebx, eax
0x180003b73  test    eax, eax
0x180003b75  js      loc_180003BFC
0x180003b7b  mov     rcx, [rdi]
0x180003b7e  lea     r8, aIisMetabaseWri; "IIS Metabase Writer"
0x180003b85  mov     [rsp+98h+var_40], 0
0x180003b8a  lea     rdx, [rsp+98h+var_28]
0x180003b8f  mov     [rsp+98h+var_48], 1
0x180003b97  xor     r9d, r9d
0x180003b9a  mov     [rsp+98h+var_50], 0EA60h
0x180003ba2  mov     rax, [rcx]
0x180003ba5  mov     [rsp+98h+var_58], 3
0x180003bad  mov     [rsp+98h+var_60], 3
0x180003bb5  mov     [rsp+98h+var_68], 2
0x180003bbd  mov     rax, [rax+18h]
0x180003bc1  mov     dword ptr [rsp+98h+var_70], 0
0x180003bc9  movdqa  [rsp+98h+var_28], xmm6
0x180003bcf  mov     dword ptr [rsp+98h+ppv], 0
0x180003bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bdc  mov     ebx, eax
0x180003bde  test    eax, eax
0x180003be0  jns     short loc_180003BF8
0x180003be2  mov     rcx, [rdi]
0x180003be5  mov     rax, [rcx]
0x180003be8  mov     rax, [rax+10h]
0x180003bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bf1  mov     qword ptr [rdi], 0
0x180003bf8  test    ebx, ebx
0x180003bfa  jns     short loc_180003C18
0x180003bfc  test    byte ptr cs:g_dwDebugFlags, 3
0x180003c03  jz      short loc_180003C79
0x180003c05  mov     dword ptr [rsp+98h+var_70], ebx
0x180003c09  lea     rax, aErrorInBaseObj; "Error in base object Initialize().  hr "...
0x180003c10  mov     r8d, 61h ; 'a'
0x180003c16  jmp     short loc_180003C59
0x180003c18  xor     edx, edx; pUnkOuter
0x180003c1a  lea     rax, [rsi+10h]
0x180003c1e  lea     r9, IID_IMSAdminBase_W; riid
0x180003c25  mov     [rsp+98h+ppv], rax; ppv
0x180003c2a  lea     rcx, CLSID_MSAdminBase_W; rclsid
0x180003c31  lea     r8d, [rdx+15h]; dwClsContext
0x180003c35  call    cs:__imp_CoCreateInstance
0x180003c3b  test    eax, eax
0x180003c3d  jns     short loc_180003C7D
0x180003c3f  test    byte ptr cs:g_dwDebugFlags, 3
0x180003c46  jz      short loc_180003C79
0x180003c48  mov     dword ptr [rsp+98h+var_70], eax
0x180003c4c  mov     r8d, 6Bh ; 'k'
0x180003c52  lea     rax, aErrorCreatingM; "Error creating MDCOM object.  hr = %x\n"
0x180003c59  mov     rcx, cs:g_pDebug
0x180003c60  lea     r9, aCiisvsswriterI; "CIISVssWriter::Initialize"
0x180003c67  lea     rdx, aInetsrvIisMbIi; "inetsrv\\iis\\mb\\iisadmin\\mdwriter.cx"...
0x180003c6e  mov     [rsp+98h+ppv], rax
0x180003c73  call    cs:__imp_PuDbgPrint
0x180003c79  xor     eax, eax
0x180003c7b  jmp     short loc_180003C82
0x180003c7d  mov     eax, 1
0x180003c82  lea     r11, [rsp+98h+var_8]
0x180003c8a  mov     rbx, [r11+10h]
0x180003c8e  mov     rsi, [r11+18h]
0x180003c92  movaps  xmm6, xmmword ptr [r11-10h]
0x180003c97  mov     rsp, r11
0x180003c9a  pop     rdi
0x180003c9b  retn
```
