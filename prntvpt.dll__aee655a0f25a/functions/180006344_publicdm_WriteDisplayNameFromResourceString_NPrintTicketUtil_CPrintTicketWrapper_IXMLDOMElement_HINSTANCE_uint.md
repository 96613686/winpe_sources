# publicdm::WriteDisplayNameFromResourceString(NPrintTicketUtil::CPrintTicketWrapper *,IXMLDOMElement *,HINSTANCE__ *,uint)

- ea: `0x180006344`
- end: `0x18000648d`
- name: `?WriteDisplayNameFromResourceString@publicdm@@YAJPEAVCPrintTicketWrapper@NPrintTicketUtil@@PEAUIXMLDOMElement@@PEAUHINSTANCE__@@I@Z`
- size: `329`
- prototype: `int(publicdm *__hidden this, struct NPrintTicketUtil::CPrintTicketWrapper *, struct IXMLDOMElement *, HINSTANCE, unsigned int)`
- caller_count: `12`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006130`
- `0x1800077f0`
- `0x18001b590`
- `0x18001bae0`
- `0x18001bbac`
- `0x18001c514`
- `0x18001c67c`
- `0x18001d090`
- `0x18001e520`
- `0x18001f720`
- `0x180020bd0`
- `0x180021260`

## callees

- `0x180006344`
- `0x18000f970`
- `0x1800103e8`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800063ad`
- `KERNEL32!GetLastError` at `0x1800063ad`
- `USER32!LoadStringW` at `0x1800063a3`
- `USER32!LoadStringW` at `0x1800063a3`

## string_xrefs

- `0x18000643e`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x180006445`: `http://www.w3.org/2001/XMLSchema`

## pseudocode

```c
int __fastcall publicdm::WriteDisplayNameFromResourceString(
        publicdm *this,
        struct NPrintTicketUtil::CPrintTicketWrapper *a2,
        struct IXMLDOMElement *a3,
        HINSTANCE a4)
{
  UINT v4; // edi
  int result; // eax
  bool v9; // sf
  __int64 v10; // rdx
  int v11; // r8d
  unsigned __int64 i; // rcx
  WCHAR Buffer[512]; // [rsp+50h] [rbp-438h] BYREF

  v4 = (unsigned int)a4;
  if ( !a3 )
    return 1;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( LoadStringW((HINSTANCE)a3, v4, Buffer, 512) )
    goto LABEL_7;
  result = GetLastError();
  v9 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v9 = result < 0;
  }
  if ( !v9 )
  {
LABEL_7:
    v10 = 0;
    Buffer[511] = 0;
    v11 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= 0x200 )
        return (*(__int64 (__fastcall **)(publicdm *, struct NPrintTicketUtil::CPrintTicketWrapper *, const OLECHAR *, const wchar_t *, WCHAR *, _DWORD, const wchar_t *, const char *, _QWORD))(*(_QWORD *)this + 8LL))(
                 this,
                 a2,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"DisplayName",
                 Buffer,
                 0,
                 L"http://www.w3.org/2001/XMLSchema",
                 L"string",
                 0);
      if ( i < 0x1FF && Buffer[i] == 38 )
      {
        if ( Buffer[i + 1] != 38 )
        {
          if ( v11 )
            goto LABEL_15;
          v11 = 1;
        }
        ++i;
      }
LABEL_15:
      Buffer[v10] = Buffer[i];
      if ( !Buffer[i] )
        return (*(__int64 (__fastcall **)(publicdm *, struct NPrintTicketUtil::CPrintTicketWrapper *, const OLECHAR *, const wchar_t *, WCHAR *, _DWORD, const wchar_t *, const char *, _QWORD))(*(_QWORD *)this + 8LL))(
                 this,
                 a2,
                 L"http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords",
                 L"DisplayName",
                 Buffer,
                 0,
                 L"http://www.w3.org/2001/XMLSchema",
                 L"string",
                 0);
      ++v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006344  push    rbx
0x180006346  push    rbp
0x180006347  push    rsi
0x180006348  push    rdi
0x180006349  push    r14
0x18000634b  sub     rsp, 460h
0x180006352  mov     rax, cs:__security_cookie
0x180006359  xor     rax, rsp
0x18000635c  mov     [rsp+488h+var_38], rax
0x180006364  xor     r14d, r14d
0x180006367  mov     edi, r9d
0x18000636a  mov     rbx, r8
0x18000636d  mov     rbp, rdx
0x180006370  mov     rsi, rcx
0x180006373  test    r8, r8
0x180006376  jnz     short loc_180006381
0x180006378  lea     eax, [r8+1]
0x18000637c  jmp     loc_18000646F
0x180006381  xor     edx, edx; Val
0x180006383  lea     rcx, [rsp+488h+Buffer]; void *
0x180006388  mov     r8d, 400h; Size
0x18000638e  call    memset_0
0x180006393  mov     r9d, 200h; cchBufferMax
0x180006399  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x18000639e  mov     edx, edi; uID
0x1800063a0  mov     rcx, rbx; hInstance
0x1800063a3  call    cs:__imp_LoadStringW
0x1800063a9  test    eax, eax
0x1800063ab  jnz     short loc_1800063C7
0x1800063ad  call    cs:__imp_GetLastError
0x1800063b3  test    eax, eax
0x1800063b5  jle     short loc_1800063C1
0x1800063b7  movzx   eax, ax
0x1800063ba  or      eax, 80070000h
0x1800063bf  test    eax, eax
0x1800063c1  js      loc_18000646F
0x1800063c7  mov     rdx, r14
0x1800063ca  mov     [rsp+488h+var_3A], r14w
0x1800063d3  mov     r8d, r14d
0x1800063d6  mov     rcx, r14
0x1800063d9  cmp     rcx, 200h
0x1800063e0  jnb     short loc_180006423
0x1800063e2  cmp     rcx, 1FFh
0x1800063e9  jnb     short loc_180006409
0x1800063eb  cmp     [rsp+rcx*2+488h+Buffer], 26h ; '&'
0x1800063f1  jnz     short loc_180006409
0x1800063f3  cmp     [rsp+rcx*2+488h+var_436], 26h ; '&'
0x1800063f9  jz      short loc_180006406
0x1800063fb  test    r8d, r8d
0x1800063fe  jnz     short loc_180006409
0x180006400  mov     r8d, 1
0x180006406  inc     rcx
0x180006409  movzx   eax, [rsp+rcx*2+488h+Buffer]
0x18000640e  mov     [rsp+rdx*2+488h+Buffer], ax
0x180006413  cmp     [rsp+rcx*2+488h+Buffer], r14w
0x180006419  jz      short loc_180006423
0x18000641b  inc     rcx
0x18000641e  inc     rdx
0x180006421  jmp     short loc_1800063D9
0x180006423  mov     rax, [rsi]
0x180006426  lea     rcx, aString; "string"
0x18000642d  mov     [rsp+488h+var_448], r14
0x180006432  lea     r9, aDisplayname; "DisplayName"
0x180006439  mov     [rsp+488h+var_450], rcx
0x18000643e  lea     r8, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x180006445  lea     rcx, aHttpWwwW3Org20; "http://www.w3.org/2001/XMLSchema"
0x18000644c  mov     rdx, rbp
0x18000644f  mov     rax, [rax+8]
0x180006453  mov     [rsp+488h+var_458], rcx
0x180006458  lea     rcx, [rsp+488h+Buffer]
0x18000645d  mov     [rsp+488h+var_460], r14d
0x180006462  mov     [rsp+488h+var_468], rcx
0x180006467  mov     rcx, rsi
0x18000646a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000646f  mov     rcx, [rsp+488h+var_38]
0x180006477  xor     rcx, rsp; StackCookie
0x18000647a  call    __security_check_cookie
0x18000647f  add     rsp, 460h
0x180006486  pop     r14
0x180006488  pop     rdi
0x180006489  pop     rsi
0x18000648a  pop     rbp
0x18000648b  pop     rbx
0x18000648c  retn
```
