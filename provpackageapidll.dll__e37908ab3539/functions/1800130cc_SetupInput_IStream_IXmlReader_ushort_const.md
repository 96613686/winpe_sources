# SetupInput(IStream * *,IXmlReader * *,ushort const *)

- ea: `0x1800130cc`
- end: `0x1800131a4`
- name: `?SetupInput@@YAJPEAPEAUIStream@@PEAPEAUIXmlReader@@PEBG@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct IStream **, struct IXmlReader **ppvObject, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010438`
- `0x1800112a4`
- `0x180011e38`
- `0x180012444`
- `0x180012b94`

## callees

- `0x180006014`
- `0x18001176c`
- `0x1800130cc`
- `0x180019010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18001311e`
- `XmlLite!CreateXmlReader` at `0x18001311e`

## string_xrefs

- `0x180013108`: `Failed to create file stream`
- `0x18001312a`: `Failed to create XML reader`
- `0x18001314b`: `Failed to set reader input`

## pseudocode

```c
__int64 __fastcall SetupInput(struct IStream **a1, struct IXmlReader **ppvObject, const unsigned __int16 *a3)
{
  HRESULT XmlReader; // ebx

  *ppvObject = 0;
  *a1 = 0;
  XmlReader = FileStream::Create(a3, 0, 0, a1);
  if ( XmlReader >= 0 )
  {
    XmlReader = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, (void **)ppvObject, 0);
    if ( XmlReader >= 0 )
    {
      XmlReader = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*ppvObject)->lpVtbl->SetInput)(*ppvObject, *a1);
      if ( XmlReader >= 0 )
        return (unsigned int)XmlReader;
      ProvPackageLog(3u, L"Failed to set reader input");
    }
    else
    {
      ProvPackageLog(3u, L"Failed to create XML reader");
    }
  }
  else
  {
    ProvPackageLog(3u, L"Failed to create file stream");
  }
  if ( *ppvObject )
  {
    ((void (__fastcall *)(_QWORD))(*ppvObject)->lpVtbl->Release)(*ppvObject);
    *ppvObject = 0;
  }
  if ( *a1 )
  {
    ((void (__fastcall *)(_QWORD))(*a1)->lpVtbl->Release)(*a1);
    *a1 = 0;
  }
  return (unsigned int)XmlReader;
}

```

## disassembly

```asm
0x1800130cc  mov     [rsp+arg_0], rbx
0x1800130d1  mov     [rsp+arg_8], rsi
0x1800130d6  push    rdi
0x1800130d7  sub     rsp, 20h
0x1800130db  mov     rax, r8
0x1800130de  mov     qword ptr [rdx], 0
0x1800130e5  mov     qword ptr [rcx], 0
0x1800130ec  mov     rdi, rdx
0x1800130ef  mov     rsi, rcx
0x1800130f2  mov     r9, rcx; struct IStream **
0x1800130f5  mov     rcx, rax; unsigned __int16 *
0x1800130f8  xor     r8d, r8d; int
0x1800130fb  xor     edx, edx; int
0x1800130fd  call    ?Create@FileStream@@SAJPEBGHHPEAPEAUIStream@@@Z; FileStream::Create(ushort const *,int,int,IStream * *)
0x180013102  mov     ebx, eax
0x180013104  test    eax, eax
0x180013106  jns     short loc_180013111
0x180013108  lea     rdx, aFailedToCreate_3; "Failed to create file stream"
0x18001310f  jmp     short loc_180013152
0x180013111  xor     r8d, r8d; pMalloc
0x180013114  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18001311b  mov     rdx, rdi; ppvObject
0x18001311e  call    cs:__imp_CreateXmlReader
0x180013124  mov     ebx, eax
0x180013126  test    eax, eax
0x180013128  jns     short loc_180013133
0x18001312a  lea     rdx, aFailedToCreate_6; "Failed to create XML reader"
0x180013131  jmp     short loc_180013152
0x180013133  mov     rcx, [rdi]
0x180013136  mov     rdx, [rsi]
0x180013139  mov     rax, [rcx]
0x18001313c  mov     rax, [rax+18h]
0x180013140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013145  mov     ebx, eax
0x180013147  test    eax, eax
0x180013149  jns     short loc_180013192
0x18001314b  lea     rdx, aFailedToSetRea; "Failed to set reader input"
0x180013152  mov     ecx, 3
0x180013157  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x18001315c  mov     rcx, [rdi]
0x18001315f  test    rcx, rcx
0x180013162  jz      short loc_180013177
0x180013164  mov     rax, [rcx]
0x180013167  mov     rax, [rax+10h]
0x18001316b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013170  mov     qword ptr [rdi], 0
0x180013177  mov     rcx, [rsi]
0x18001317a  test    rcx, rcx
0x18001317d  jz      short loc_180013192
0x18001317f  mov     rax, [rcx]
0x180013182  mov     rax, [rax+10h]
0x180013186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001318b  mov     qword ptr [rsi], 0
0x180013192  mov     rsi, [rsp+28h+arg_8]
0x180013197  mov     eax, ebx
0x180013199  mov     rbx, [rsp+28h+arg_0]
0x18001319e  add     rsp, 20h
0x1800131a2  pop     rdi
0x1800131a3  retn
```
