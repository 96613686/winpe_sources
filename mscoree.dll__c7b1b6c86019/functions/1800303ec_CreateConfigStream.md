# CreateConfigStream

- ea: `0x1800303ec`
- end: `0x180030522`
- name: `CreateConfigStream`
- size: `310`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPSTREAM *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001280`
- `0x1800321e4`

## callees

- `0x180003740`
- `0x18002a7c8`
- `0x180030060`
- `0x18003007c`
- `0x1800300c0`
- `0x180030384`
- `0x1800303ec`
- `0x180045020`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800304bc`
- `KERNEL32!CreateFileW` at `0x1800304bc`
- `SHLWAPI!UrlIsW` at `0x180030432`
- `SHLWAPI!UrlIsW` at `0x180030432`
- `urlmon!URLOpenBlockingStreamW` at `0x180030450`
- `urlmon!URLOpenBlockingStreamW` at `0x180030450`

## pseudocode

```c
__int64 __fastcall CreateConfigStream(LPCWSTR lpFileName, LPSTREAM *a2)
{
  unsigned int v4; // edx
  HRESULT LastError; // edi
  const struct NoThrow *v6; // rdx
  IStream *v7; // rax
  IStream *v8; // rbx
  struct IStreamVtbl *FileW; // rax
  _DWORD v11[14]; // [rsp+40h] [rbp-38h] BYREF

  SOIntolerantTransitionHandler::SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v11);
  if ( (unsigned int)SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread(
                       (SOIntolerantTransitionHandler *)v11,
                       v4) )
  {
    if ( a2 )
    {
      if ( UrlIsW(lpFileName, URLIS_URL) )
      {
        LastError = URLOpenBlockingStreamW(0, lpFileName, a2, 0, 0);
      }
      else
      {
        v7 = (IStream *)operator new(0x20u, v6);
        v8 = v7;
        if ( v7 )
        {
          _unknown<IStream,&_GUID const IID_IStream>::_unknown<IStream,&_GUID const IID_IStream>(v7);
          v8[2].lpVtbl = (struct IStreamVtbl *)-1LL;
          v8->lpVtbl = (struct IStreamVtbl *)&XMLParserShimFileStream::`vftable';
          LOBYTE(v8[3].lpVtbl) = 1;
          if ( lpFileName
            && (LastError = 0,
                FileW = (struct IStreamVtbl *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0),
                v8[2].lpVtbl = FileW,
                FileW != (struct IStreamVtbl *)-1LL)
            || (((void (__fastcall *)(IStream *, __int64))v8->lpVtbl[1].QueryInterface)(v8, 1),
                LastError = HRESULT_FROM_GetLastError(),
                LastError >= 0) )
          {
            ((void (__fastcall *)(IStream *))v8->lpVtbl->AddRef)(v8);
            *a2 = v8;
          }
        }
        else
        {
          LastError = -2147024882;
        }
      }
    }
    else
    {
      LastError = -2147467261;
    }
  }
  else
  {
    LastError = -2147023895;
  }
  v11[0] = 0;
  SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler((SOIntolerantTransitionHandler *)v11);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800303ec  push    rbx
0x1800303ee  push    rsi
0x1800303ef  push    rdi
0x1800303f0  push    r14
0x1800303f2  sub     rsp, 58h
0x1800303f6  mov     rsi, rcx
0x1800303f9  mov     r14, rdx
0x1800303fc  lea     rcx, [rsp+78h+var_38]; this
0x180030401  call    ??0SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::SOIntolerantTransitionHandler(void)
0x180030406  lea     rcx, [rsp+78h+var_38]; this
0x18003040b  call    ?RetailStackProbeNoThrowNoThread@SOIntolerantTransitionHandler@@QEAAHI@Z; SOIntolerantTransitionHandler::RetailStackProbeNoThrowNoThread(uint)
0x180030410  test    eax, eax
0x180030412  jnz     short loc_18003041E
0x180030414  mov     edi, 800703E9h
0x180030419  jmp     loc_180030504
0x18003041e  test    r14, r14
0x180030421  jnz     short loc_18003042D
0x180030423  mov     edi, 80004003h
0x180030428  jmp     loc_180030504
0x18003042d  xor     edx, edx; UrlIs
0x18003042f  mov     rcx, rsi; pszUrl
0x180030432  call    cs:__imp_UrlIsW
0x180030438  test    eax, eax
0x18003043a  jz      short loc_18003045D
0x18003043c  xor     r9d, r9d; DWORD
0x18003043f  mov     [rsp+78h+var_58], 0; LPBINDSTATUSCALLBACK
0x180030448  mov     r8, r14; LPSTREAM *
0x18003044b  mov     rdx, rsi; LPCWSTR
0x18003044e  xor     ecx, ecx; LPUNKNOWN
0x180030450  call    cs:__imp_URLOpenBlockingStreamW
0x180030456  mov     edi, eax
0x180030458  jmp     loc_180030504
0x18003045d  mov     ecx, 20h ; ' '; unsigned __int64
0x180030462  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180030467  mov     rbx, rax
0x18003046a  test    rax, rax
0x18003046d  jz      loc_1800304FF
0x180030473  mov     rcx, rax
0x180030476  call    ??0?$_unknown@UIStream@@$1?IID_IStream@@3U_GUID@@B@@QEAA@XZ; _unknown<IStream,&_GUID const IID_IStream>::_unknown<IStream,&_GUID const IID_IStream>(void)
0x18003047b  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180030483  lea     rcx, ??_7XMLParserShimFileStream@@6B@; const XMLParserShimFileStream::`vftable'
0x18003048a  mov     [rbx], rcx
0x18003048d  mov     byte ptr [rbx+18h], 1
0x180030491  test    rsi, rsi
0x180030494  jz      short loc_1800304CC
0x180030496  xor     edi, edi
0x180030498  xor     r9d, r9d; lpSecurityAttributes
0x18003049b  mov     [rsp+78h+hTemplateFile], rdi; hTemplateFile
0x1800304a0  mov     edx, 80000000h; dwDesiredAccess
0x1800304a5  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800304ad  mov     rcx, rsi; lpFileName
0x1800304b0  mov     dword ptr [rsp+78h+var_58], 3; dwCreationDisposition
0x1800304b8  lea     r8d, [rdi+1]; dwShareMode
0x1800304bc  call    cs:__imp_CreateFileW
0x1800304c2  mov     [rbx+10h], rax
0x1800304c6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800304ca  jnz     short loc_1800304EB
0x1800304cc  mov     rax, [rbx]
0x1800304cf  mov     edx, 1
0x1800304d4  mov     rcx, rbx
0x1800304d7  mov     rax, [rax+70h]
0x1800304db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304e0  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x1800304e5  mov     edi, eax
0x1800304e7  test    eax, eax
0x1800304e9  js      short loc_180030504
0x1800304eb  mov     rax, [rbx]
0x1800304ee  mov     rcx, rbx
0x1800304f1  mov     rax, [rax+8]
0x1800304f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304fa  mov     [r14], rbx
0x1800304fd  jmp     short loc_180030504
0x1800304ff  mov     edi, 8007000Eh
0x180030504  lea     rcx, [rsp+78h+var_38]; this
0x180030509  mov     [rsp+78h+var_38], 0
0x180030511  call    ??1SOIntolerantTransitionHandler@@QEAA@XZ; SOIntolerantTransitionHandler::~SOIntolerantTransitionHandler(void)
0x180030516  mov     eax, edi
0x180030518  add     rsp, 58h
0x18003051c  pop     r14
0x18003051e  pop     rdi
0x18003051f  pop     rsi
0x180030520  pop     rbx
0x180030521  retn
```
