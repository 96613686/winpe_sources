# KerbImpersonateClient(_LUID *,void * *)

- ea: `0x18001018c`
- end: `0x180010320`
- name: `?KerbImpersonateClient@@YAJPEAU_LUID@@PEAPEAX@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct _LUID *, void **)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180051720`
- `0x18005228c`
- `0x18005f044`
- `0x1800603d8`
- `0x180062d28`
- `0x1800994bc`
- `0x1800b63a4`
- `0x1800bb92c`
- `0x1800bbb14`
- `0x1800bbc48`
- `0x1800bbff4`

## callees

- `0x18001018c`
- `0x18008b70c`
- `0x1800f5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001026d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001026d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010263`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010263`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010308`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800102f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010308`
- `ntdll!NtOpenThreadToken` at `0x1800101c5`
- `ntdll!NtOpenThreadToken` at `0x1800101c5`

## string_xrefs

- `0x180010273`: `Unable to impersonate the client token handle %d.\n`
- `0x18001022c`: `Unable to get the client token handle for %#x:%#x, error %#x.\n`
- `0x1800102b2`: `unable to impersonate the client %#x.\n`
- `0x180010235`: `KerbImpersonateClient`
- `0x180010280`: `KerbImpersonateClient`
- `0x1800102c3`: `KerbImpersonateClient`

## pseudocode

```c
__int64 __fastcall KerbImpersonateClient(struct _LUID *a1, void **a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  DWORD LastError; // eax
  int v7; // eax
  HANDLE hObject; // [rsp+60h] [rbp+18h] BYREF
  HANDLE Token; // [rsp+68h] [rbp+20h] BYREF

  Token = 0;
  hObject = 0;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &hObject);
  if ( (int)(v4 + 0x80000000) < 0 || v4 == -1073741700 )
  {
    if ( v4 == -1073741700 )
      hObject = 0;
    if ( a1 && *(_QWORD *)a1 )
    {
      v5 = ((__int64 (__fastcall *)(struct _LUID *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a1, &Token);
      v4 = v5;
      if ( v5 < 0 )
      {
        KerbTracerT::Log(
          1,
          "KerbImpersonateClient",
          387,
          "Unable to get the client token handle for %#x:%#x, error %#x.\n",
          a1->HighPart,
          a1->LowPart,
          v5);
        goto LABEL_16;
      }
      if ( !SetThreadToken(0, Token) )
      {
        LastError = GetLastError();
        KerbTracerT::Log(
          1,
          "KerbImpersonateClient",
          393,
          "Unable to impersonate the client token handle %d.\n",
          LastError);
        v4 = -1073741555;
        goto LABEL_16;
      }
    }
    else
    {
      v7 = ((__int64 (__fastcall *)(__int64))LsaFunctions->ImpersonateClient)(3221225596LL);
      v4 = v7;
      if ( v7 < 0 )
      {
        KerbTracerT::Log(1, "KerbImpersonateClient", 374, "unable to impersonate the client %#x.\n", v7);
        goto LABEL_16;
      }
    }
    if ( a2 )
    {
      *a2 = hObject;
      hObject = 0;
    }
    v4 = 0;
  }
LABEL_16:
  if ( Token )
    CloseHandle(Token);
  if ( hObject )
    CloseHandle(hObject);
  return v4;
}

```

## disassembly

```asm
0x18001018c  mov     rax, rsp
0x18001018f  mov     [rax+8], rbx
0x180010193  mov     [rax+10h], rsi
0x180010197  push    rdi
0x180010198  sub     rsp, 40h
0x18001019c  mov     rsi, rdx
0x18001019f  mov     qword ptr [rax+20h], 0
0x1800101a7  mov     rdi, rcx
0x1800101aa  mov     qword ptr [rax+18h], 0
0x1800101b2  mov     edx, 0Ch; DesiredAccess
0x1800101b7  lea     r9, [rax+18h]; TokenHandle
0x1800101bb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800101c2  mov     r8b, 1; OpenAsSelf
0x1800101c5  call    cs:__imp_NtOpenThreadToken
0x1800101cb  mov     ebx, eax
0x1800101cd  mov     ecx, 0C000007Ch
0x1800101d2  mov     eax, 80000000h
0x1800101d7  lea     edx, [rbx+rax]
0x1800101da  test    eax, edx
0x1800101dc  jnz     short loc_1800101E6
0x1800101de  cmp     ebx, ecx
0x1800101e0  jnz     loc_1800102EE
0x1800101e6  cmp     ebx, ecx
0x1800101e8  jnz     short loc_1800101F3
0x1800101ea  mov     [rsp+48h+hObject], 0
0x1800101f3  test    rdi, rdi
0x1800101f6  jz      loc_18001029C
0x1800101fc  mov     eax, [rdi+4]
0x1800101ff  or      eax, [rdi]
0x180010201  jz      loc_18001029C
0x180010207  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x18001020e  lea     rdx, [rsp+48h+Token]
0x180010213  mov     rcx, rdi
0x180010216  mov     rax, [rax+170h]
0x18001021d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010222  mov     ebx, eax
0x180010224  test    eax, eax
0x180010226  jns     short loc_18001025C
0x180010228  mov     [rsp+48h+var_18], eax
0x18001022c  lea     r9, aUnableToGetThe_1; "Unable to get the client token handle f"...
0x180010233  mov     eax, [rdi]
0x180010235  lea     rdx, aKerbimpersonat_0; "KerbImpersonateClient"
0x18001023c  mov     [rsp+48h+var_20], eax
0x180010240  mov     r8d, 183h
0x180010246  mov     eax, [rdi+4]
0x180010249  mov     ecx, 1
0x18001024e  mov     [rsp+48h+var_28], eax
0x180010252  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180010257  jmp     loc_1800102EE
0x18001025c  mov     rdx, [rsp+48h+Token]; Token
0x180010261  xor     ecx, ecx; Thread
0x180010263  call    cs:__imp_SetThreadToken
0x180010269  test    eax, eax
0x18001026b  jnz     short loc_1800102D6
0x18001026d  call    cs:__imp_GetLastError
0x180010273  lea     r9, aUnableToImpers; "Unable to impersonate the client token "...
0x18001027a  mov     r8d, 189h
0x180010280  lea     rdx, aKerbimpersonat_0; "KerbImpersonateClient"
0x180010287  mov     [rsp+48h+var_28], eax
0x18001028b  mov     ecx, 1
0x180010290  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180010295  mov     ebx, 0C000010Dh
0x18001029a  jmp     short loc_1800102EE
0x18001029c  mov     rax, cs:?LsaFunctions@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * LsaFunctions
0x1800102a3  mov     rax, [rax+58h]
0x1800102a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102ac  mov     ebx, eax
0x1800102ae  test    eax, eax
0x1800102b0  jns     short loc_1800102D6
0x1800102b2  lea     r9, aUnableToImpers_1; "unable to impersonate the client %#x.\n"
0x1800102b9  mov     [rsp+48h+var_28], eax
0x1800102bd  mov     r8d, 176h
0x1800102c3  lea     rdx, aKerbimpersonat_0; "KerbImpersonateClient"
0x1800102ca  mov     ecx, 1
0x1800102cf  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800102d4  jmp     short loc_1800102EE
0x1800102d6  test    rsi, rsi
0x1800102d9  jz      short loc_1800102EC
0x1800102db  mov     rax, [rsp+48h+hObject]
0x1800102e0  mov     [rsi], rax
0x1800102e3  mov     [rsp+48h+hObject], 0
0x1800102ec  xor     ebx, ebx
0x1800102ee  mov     rcx, [rsp+48h+Token]; hObject
0x1800102f3  test    rcx, rcx
0x1800102f6  jz      short loc_1800102FE
0x1800102f8  call    cs:__imp_CloseHandle
0x1800102fe  mov     rcx, [rsp+48h+hObject]; hObject
0x180010303  test    rcx, rcx
0x180010306  jz      short loc_18001030E
0x180010308  call    cs:__imp_CloseHandle
0x18001030e  mov     rsi, [rsp+48h+arg_8]
0x180010313  mov     eax, ebx
0x180010315  mov     rbx, [rsp+48h+arg_0]
0x18001031a  add     rsp, 40h
0x18001031e  pop     rdi
0x18001031f  retn
```
