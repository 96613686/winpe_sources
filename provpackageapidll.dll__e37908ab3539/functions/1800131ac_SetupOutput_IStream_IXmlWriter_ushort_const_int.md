# SetupOutput(IStream * *,IXmlWriter * *,ushort const *,int)

- ea: `0x1800131ac`
- end: `0x18001328a`
- name: `?SetupOutput@@YAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@PEBGH@Z`
- size: `222`
- prototype: `__int64 __fastcall(struct IStream **, struct IXmlWriter **ppvObject, const unsigned __int16 *, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010438`
- `0x1800112a4`
- `0x180013688`
- `0x180013c18`

## callees

- `0x180006014`
- `0x18001176c`
- `0x1800131ac`
- `0x180019010`

## import_xrefs

- `XmlLite!CreateXmlWriter` at `0x180013204`
- `XmlLite!CreateXmlWriter` at `0x180013204`

## string_xrefs

- `0x1800131ee`: `Failed to create file stream`
- `0x180013210`: `Failed to create XML writer`
- `0x180013231`: `Failed to set writer output`

## pseudocode

```c
__int64 __fastcall SetupOutput(struct IStream **a1, struct IXmlWriter **ppvObject, const unsigned __int16 *a3, int a4)
{
  HRESULT XmlWriter; // ebx

  *ppvObject = 0;
  *a1 = 0;
  XmlWriter = FileStream::Create(a3, 1, a4, a1);
  if ( XmlWriter >= 0 )
  {
    XmlWriter = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, (void **)ppvObject, 0);
    if ( XmlWriter >= 0 )
    {
      XmlWriter = ((__int64 (__fastcall *)(_QWORD, _QWORD))(*ppvObject)->lpVtbl->SetOutput)(*ppvObject, *a1);
      if ( XmlWriter >= 0 )
        return (unsigned int)XmlWriter;
      ProvPackageLog(3u, L"Failed to set writer output");
    }
    else
    {
      ProvPackageLog(3u, L"Failed to create XML writer");
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
  return (unsigned int)XmlWriter;
}

```

## disassembly

```asm
0x1800131ac  mov     [rsp+arg_0], rbx
0x1800131b1  mov     [rsp+arg_8], rsi
0x1800131b6  push    rdi
0x1800131b7  sub     rsp, 20h
0x1800131bb  mov     eax, r9d
0x1800131be  mov     qword ptr [rdx], 0
0x1800131c5  mov     r10, r8
0x1800131c8  mov     qword ptr [rcx], 0
0x1800131cf  mov     r9, rcx; struct IStream **
0x1800131d2  mov     rdi, rdx
0x1800131d5  mov     rsi, rcx
0x1800131d8  mov     r8d, eax; int
0x1800131db  mov     rcx, r10; unsigned __int16 *
0x1800131de  mov     edx, 1; int
0x1800131e3  call    ?Create@FileStream@@SAJPEBGHHPEAPEAUIStream@@@Z; FileStream::Create(ushort const *,int,int,IStream * *)
0x1800131e8  mov     ebx, eax
0x1800131ea  test    eax, eax
0x1800131ec  jns     short loc_1800131F7
0x1800131ee  lea     rdx, aFailedToCreate_3; "Failed to create file stream"
0x1800131f5  jmp     short loc_180013238
0x1800131f7  xor     r8d, r8d; pMalloc
0x1800131fa  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x180013201  mov     rdx, rdi; ppvObject
0x180013204  call    cs:__imp_CreateXmlWriter
0x18001320a  mov     ebx, eax
0x18001320c  test    eax, eax
0x18001320e  jns     short loc_180013219
0x180013210  lea     rdx, aFailedToCreate_7; "Failed to create XML writer"
0x180013217  jmp     short loc_180013238
0x180013219  mov     rcx, [rdi]
0x18001321c  mov     rdx, [rsi]
0x18001321f  mov     rax, [rcx]
0x180013222  mov     rax, [rax+18h]
0x180013226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001322b  mov     ebx, eax
0x18001322d  test    eax, eax
0x18001322f  jns     short loc_180013278
0x180013231  lea     rdx, aFailedToSetWri; "Failed to set writer output"
0x180013238  mov     ecx, 3
0x18001323d  call    ?ProvPackageLog@@YAXW4_PROVPACKAGELOGLEVEL@@PEBGZZ; ProvPackageLog(_PROVPACKAGELOGLEVEL,ushort const *,...)
0x180013242  mov     rcx, [rdi]
0x180013245  test    rcx, rcx
0x180013248  jz      short loc_18001325D
0x18001324a  mov     rax, [rcx]
0x18001324d  mov     rax, [rax+10h]
0x180013251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013256  mov     qword ptr [rdi], 0
0x18001325d  mov     rcx, [rsi]
0x180013260  test    rcx, rcx
0x180013263  jz      short loc_180013278
0x180013265  mov     rax, [rcx]
0x180013268  mov     rax, [rax+10h]
0x18001326c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013271  mov     qword ptr [rsi], 0
0x180013278  mov     rsi, [rsp+28h+arg_8]
0x18001327d  mov     eax, ebx
0x18001327f  mov     rbx, [rsp+28h+arg_0]
0x180013284  add     rsp, 20h
0x180013288  pop     rdi
0x180013289  retn
```
