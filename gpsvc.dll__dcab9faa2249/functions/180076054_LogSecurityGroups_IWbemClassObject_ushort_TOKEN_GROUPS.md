# LogSecurityGroups(IWbemClassObject *,ushort *,_TOKEN_GROUPS *)

- ea: `0x180076054`
- end: `0x1800762f5`
- name: `?LogSecurityGroups@@YAJPEAUIWbemClassObject@@PEAGPEAU_TOKEN_GROUPS@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(struct IWbemClassObject *, unsigned __int16 *, struct _TOKEN_GROUPS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b1224`

## callees

- `0x1800535a0`
- `0x180075ec0`
- `0x180076054`
- `0x1800762fc`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800760ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800760ee`
- `ntdll!RtlFreeUnicodeString` at `0x18007614f`
- `ntdll!RtlFreeUnicodeString` at `0x18007614f`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007612d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18007612d`
- `OLEAUT32!__imp_SysFreeString` at `0x180076172`
- `OLEAUT32!__imp_SysFreeString` at `0x1800761d7`
- `OLEAUT32!__imp_SysFreeString` at `0x180076172`
- `OLEAUT32!__imp_SysFreeString` at `0x1800761d7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180076093`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180076093`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180076163`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180076163`

## string_xrefs

- `0x1800760ba`: `LogSecurityGroups: Failed to allocate memory`
- `0x1800760dd`: `LogSecurityGroups: Failed to allocate memory`
- `0x1800761fc`: `LogSecurityGroups: RtlConvertSidToUnicodeString failed, status = 0x%x`
- `0x180076224`: `LogSecurityGroups: RtlConvertSidToUnicodeString failed, status = 0x%x`
- `0x18007619a`: `LogSecurityGroups: Failed to SafeArrayPutElement with 0x%x`
- `0x1800761c2`: `LogSecurityGroups: Failed to SafeArrayPutElement with 0x%x`
- `0x180076294`: `LogSecurityGroups: PutInstance failed with 0x%x`
- `0x1800762bc`: `LogSecurityGroups: PutInstance failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LogSecurityGroups(struct IWbemClassObject *a1, unsigned __int16 *a2, struct _TOKEN_GROUPS *a3)
{
  SAFEARRAY *v6; // rdi
  signed int LastError; // eax
  unsigned int v8; // ebx
  DWORD i; // eax
  NTSTATUS v10; // ebx
  OLECHAR *v11; // rbx
  HRESULT v12; // esi
  void *pv; // [rsp+30h] [rbp-40h] BYREF
  SAFEARRAY *v15; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-20h] BYREF
  LONG rgIndices; // [rsp+C0h] [rbp+50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+C8h] [rbp+58h] BYREF

  rgsabound.lLbound = 0;
  rgsabound.cElements = a3->GroupCount;
  UnicodeString = 0;
  v6 = SafeArrayCreate(8u, 1u, &rgsabound);
  v15 = v6;
  if ( v6 )
  {
    rgIndices = 0;
    for ( i = 0; i < a3->GroupCount; i = ++rgIndices )
    {
      v10 = RtlConvertSidToUnicodeString(&UnicodeString, a3->Groups[i].Sid, 1u);
      if ( v10 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(
              2u,
              L"LogSecurityGroups: RtlConvertSidToUnicodeString failed, status = 0x%x",
              (unsigned int)v10);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(
              2u,
              L"LogSecurityGroups: RtlConvertSidToUnicodeString failed, status = 0x%x",
              (unsigned int)v10);
          }
        }
        v8 = v10 | 0x10000000;
        goto LABEL_37;
      }
      XBStr::XBStr((XBStr *)&pv, UnicodeString.Buffer);
      RtlFreeUnicodeString(&UnicodeString);
      v11 = (OLECHAR *)pv;
      v12 = SafeArrayPutElement(v6, &rgIndices, pv);
      if ( v12 < 0 )
      {
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(2u, L"LogSecurityGroups: Failed to SafeArrayPutElement with 0x%x", (unsigned int)v12);
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(2u, L"LogSecurityGroups: Failed to SafeArrayPutElement with 0x%x", (unsigned int)v12);
          }
        }
        SysFreeString(v11);
        v8 = v12;
        goto LABEL_37;
      }
      SysFreeString(v11);
    }
    v17[0] = 8200;
    v17[2] = 0;
    v17[1] = v6;
    v8 = ((__int64 (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, _QWORD, _QWORD *, _DWORD))a1->lpVtbl->Put)(
           a1,
           a2,
           0,
           v17,
           0);
    if ( (v8 & 0x80000000) == 0 )
    {
      v8 = 0;
    }
    else if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"LogSecurityGroups: PutInstance failed with 0x%x", v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"LogSecurityGroups: PutInstance failed with 0x%x", v8);
      }
    }
  }
  else
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"LogSecurityGroups: Failed to allocate memory");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"LogSecurityGroups: Failed to allocate memory");
      }
    }
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_37:
  XSafeArray::~XSafeArray((XSafeArray *)&v15);
  return v8;
}

```

## disassembly

```asm
0x180076054  mov     [rsp-38h+arg_0], rbx
0x180076059  push    rbp
0x18007605a  push    rsi
0x18007605b  push    rdi
0x18007605c  push    r12
0x18007605e  push    r13
0x180076060  push    r14
0x180076062  push    r15
0x180076064  mov     rbp, rsp
0x180076067  sub     rsp, 70h
0x18007606b  mov     r14, r8
0x18007606e  mov     r12, rdx
0x180076071  mov     r15, rcx
0x180076074  xor     r13d, r13d
0x180076077  mov     [rbp+rgsabound.lLbound], r13d
0x18007607b  mov     eax, [r8]
0x18007607e  mov     [rbp+rgsabound.cElements], eax
0x180076081  xorps   xmm0, xmm0
0x180076084  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x180076088  lea     ecx, [r13+8]; vt
0x18007608c  lea     r8, [rbp+rgsabound]; rgsabound
0x180076090  lea     edx, [rcx-7]; cDims
0x180076093  call    cs:__imp_SafeArrayCreate
0x180076099  mov     rdi, rax
0x18007609c  mov     [rbp+var_38], rax
0x1800760a0  test    rax, rax
0x1800760a3  jnz     short loc_18007610C
0x1800760a5  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800760ac  jz      short loc_1800760EE
0x1800760ae  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800760b5  test    rax, rax
0x1800760b8  jz      short loc_1800760CB
0x1800760ba  lea     rdx, aLogsecuritygro_0; "LogSecurityGroups: Failed to allocate m"...
0x1800760c1  lea     ecx, [rdi+2]
0x1800760c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800760c9  jmp     short loc_1800760EE
0x1800760cb  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800760d2  jz      short loc_1800760EE
0x1800760d4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800760db  jz      short loc_1800760EE
0x1800760dd  lea     rdx, aLogsecuritygro_0; "LogSecurityGroups: Failed to allocate m"...
0x1800760e4  mov     ecx, 2; unsigned int
0x1800760e9  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800760ee  call    cs:__imp_GetLastError
0x1800760f4  mov     ebx, eax
0x1800760f6  test    eax, eax
0x1800760f8  jle     loc_1800762D2
0x1800760fe  movzx   ebx, ax
0x180076101  or      ebx, 80070000h
0x180076107  jmp     loc_1800762D2
0x18007610c  mov     [rbp+rgIndices], r13d
0x180076110  mov     eax, r13d
0x180076113  cmp     eax, [r14]
0x180076116  jnb     loc_18007623E
0x18007611c  mov     edx, eax
0x18007611e  add     rdx, rdx
0x180076121  mov     r8b, 1; AllocateDestinationString
0x180076124  mov     rdx, [r14+rdx*8+8]; Sid
0x180076129  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007612d  call    cs:__imp_RtlConvertSidToUnicodeString
0x180076133  mov     ebx, eax
0x180076135  test    eax, eax
0x180076137  js      loc_1800761E4
0x18007613d  mov     rdx, [rbp+UnicodeString.Buffer]; unsigned __int16 *
0x180076141  lea     rcx, [rbp+pv]; this
0x180076145  call    ??0XBStr@@QEAA@PEBG@Z; XBStr::XBStr(ushort const *)
0x18007614a  nop
0x18007614b  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18007614f  call    cs:__imp_RtlFreeUnicodeString
0x180076155  mov     rbx, [rbp+pv]
0x180076159  mov     r8, rbx; pv
0x18007615c  lea     rdx, [rbp+rgIndices]; rgIndices
0x180076160  mov     rcx, rdi; psa
0x180076163  call    cs:__imp_SafeArrayPutElement
0x180076169  mov     esi, eax
0x18007616b  test    eax, eax
0x18007616d  js      short loc_180076182
0x18007616f  mov     rcx, rbx; bstrString
0x180076172  call    cs:__imp_SysFreeString
0x180076178  mov     eax, [rbp+rgIndices]
0x18007617b  inc     eax
0x18007617d  mov     [rbp+rgIndices], eax
0x180076180  jmp     short loc_180076113
0x180076182  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180076189  jz      short loc_1800761D4
0x18007618b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180076192  test    rax, rax
0x180076195  jz      short loc_1800761AD
0x180076197  mov     r8d, esi
0x18007619a  lea     rdx, aLogsecuritygro; "LogSecurityGroups: Failed to SafeArrayP"...
0x1800761a1  mov     ecx, 2
0x1800761a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800761ab  jmp     short loc_1800761D4
0x1800761ad  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800761b4  jz      short loc_1800761D4
0x1800761b6  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800761bd  jz      short loc_1800761D4
0x1800761bf  mov     r8d, esi
0x1800761c2  lea     rdx, aLogsecuritygro; "LogSecurityGroups: Failed to SafeArrayP"...
0x1800761c9  mov     ecx, 2; unsigned int
0x1800761ce  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800761d3  nop
0x1800761d4  mov     rcx, rbx; bstrString
0x1800761d7  call    cs:__imp_SysFreeString
0x1800761dd  mov     ebx, esi
0x1800761df  jmp     loc_1800762D2
0x1800761e4  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x1800761eb  jz      short loc_180076235
0x1800761ed  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800761f4  test    rax, rax
0x1800761f7  jz      short loc_18007620F
0x1800761f9  mov     r8d, ebx
0x1800761fc  lea     rdx, aLogsecuritygro_2; "LogSecurityGroups: RtlConvertSidToUnico"...
0x180076203  mov     ecx, 2
0x180076208  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007620d  jmp     short loc_180076235
0x18007620f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x180076216  jz      short loc_180076235
0x180076218  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18007621f  jz      short loc_180076235
0x180076221  mov     r8d, ebx
0x180076224  lea     rdx, aLogsecuritygro_2; "LogSecurityGroups: RtlConvertSidToUnico"...
0x18007622b  mov     ecx, 2; unsigned int
0x180076230  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180076235  bts     ebx, 1Ch
0x180076239  jmp     loc_1800762D2
0x18007623e  xorps   xmm0, xmm0
0x180076241  xor     eax, eax
0x180076243  movups  [rbp+var_20], xmm0
0x180076247  mov     [rbp+var_10], rax
0x18007624b  mov     eax, 2008h
0x180076250  mov     word ptr [rbp+var_20], ax
0x180076254  mov     qword ptr [rbp+var_20+8], rdi
0x180076258  mov     rax, [r15]
0x18007625b  mov     [rsp+70h+var_50], r13d
0x180076260  lea     r9, [rbp+var_20]
0x180076264  xor     r8d, r8d
0x180076267  mov     rdx, r12
0x18007626a  mov     rcx, r15
0x18007626d  mov     rax, [rax+28h]
0x180076271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076276  mov     ebx, eax
0x180076278  test    eax, eax
0x18007627a  jns     short loc_1800762CF
0x18007627c  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x180076283  jz      short loc_1800762D2
0x180076285  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18007628c  test    rax, rax
0x18007628f  jz      short loc_1800762A7
0x180076291  mov     r8d, ebx
0x180076294  lea     rdx, aLogsecuritygro_1; "LogSecurityGroups: PutInstance failed w"...
0x18007629b  mov     ecx, 2
0x1800762a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800762a5  jmp     short loc_1800762D2
0x1800762a7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x1800762ae  jz      short loc_1800762D2
0x1800762b0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800762b7  jz      short loc_1800762D2
0x1800762b9  mov     r8d, ebx
0x1800762bc  lea     rdx, aLogsecuritygro_1; "LogSecurityGroups: PutInstance failed w"...
0x1800762c3  mov     ecx, 2; unsigned int
0x1800762c8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800762cd  jmp     short loc_1800762D2
0x1800762cf  mov     ebx, r13d
0x1800762d2  lea     rcx, [rbp+var_38]; this
0x1800762d6  call    ??1XSafeArray@@QEAA@XZ; XSafeArray::~XSafeArray(void)
0x1800762db  mov     eax, ebx
0x1800762dd  mov     rbx, [rsp+70h+arg_0]
0x1800762e5  add     rsp, 70h
0x1800762e9  pop     r15
0x1800762eb  pop     r14
0x1800762ed  pop     r13
0x1800762ef  pop     r12
0x1800762f1  pop     rdi
0x1800762f2  pop     rsi
0x1800762f3  pop     rbp
0x1800762f4  retn
```
