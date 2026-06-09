# WriteAddressToRegistry(HKEY__ *,ushort const *,bool,uchar *)

- ea: `0x180045018`
- end: `0x180045221`
- name: `?WriteAddressToRegistry@@YAKPEAUHKEY__@@PEBG_NPEAE@Z`
- size: `521`
- prototype: `unsigned int __fastcall(HKEY hKey, LPCWSTR lpValueName, bool, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f420`

## callees

- `0x180045018`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!malloc` at `0x1800450d1`
- `msvcrt!malloc` at `0x180045172`
- `msvcrt!malloc` at `0x1800450d1`
- `msvcrt!malloc` at `0x180045172`
- `msvcrt!free` at `0x1800451e1`
- `msvcrt!free` at `0x1800451e1`
- `ntdll!RtlIpv4AddressToStringW` at `0x180045156`
- `ntdll!RtlIpv4AddressToStringW` at `0x180045156`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004519c`
- `ntdll!RtlIpv6AddressToStringW` at `0x18004519c`
- `ADVAPI32!RegSetValueExW` at `0x1800451cf`
- `ADVAPI32!RegSetValueExW` at `0x1800451cf`

## string_xrefs

- `0x1800450ac`: `WriteAddressToRegistry`
- `0x180045103`: `WriteAddressToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WriteAddressToRegistry(HKEY hKey, LPCWSTR lpValueName, char a3, unsigned __int8 *a4)
{
  BYTE *lpData; // rdi
  WCHAR *v9; // rbx
  void (*v10)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  __int64 v11; // rsi
  BYTE *v12; // rax
  __int64 v13; // r14
  BYTE *v14; // rax
  unsigned int v15; // r14d
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+68h] [rbp-98h]
  int v24; // [rsp+6Ch] [rbp-94h]
  int v25; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v26[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v18 = 0;
  lpData = 0;
  v9 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v20 = 0;
  v19 = 0;
  v21 = 0;
  v22 = 0;
  v23 = -1;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v19, L"WriteAddressToRegistry", &v18, v10);
  v11 = *(unsigned int *)a4;
  if ( a3 )
  {
    if ( (_DWORD)v11 )
    {
      v12 = (BYTE *)malloc(100 * v11);
      lpData = v12;
      if ( !v12 )
        goto LABEL_6;
      v9 = (WCHAR *)v12;
    }
    v13 = 0;
    if ( (_DWORD)v11 )
    {
      do
      {
        v9 = RtlIpv4AddressToStringW((const struct in_addr *)(*((_QWORD *)a4 + 1) + 4 * v13), v9) + 1;
        v13 = (unsigned int)(v13 + 1);
      }
      while ( (unsigned int)v13 < *(_DWORD *)a4 );
LABEL_17:
      *v9 = 0;
      v18 = RegSetValueExW(hKey, lpValueName, 0, 7u, lpData, (_DWORD)v9 + 2 - (_DWORD)lpData);
    }
  }
  else
  {
    if ( (_DWORD)v11 )
    {
      v14 = (BYTE *)malloc(100 * v11);
      lpData = v14;
      if ( !v14 )
      {
LABEL_6:
        v18 = 8;
        if ( (_QWORD)xmmword_180071090 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"%s: malloc (%ws) failed: %d.", L"WriteAddressToRegistry", lpValueName, 8);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v25);
        }
        goto LABEL_20;
      }
      v9 = (WCHAR *)v14;
    }
    v15 = 0;
    if ( (_DWORD)v11 )
    {
      do
        v9 = RtlIpv6AddressToStringW((const struct in6_addr *)(*((_QWORD *)a4 + 1) + 16LL * v15++), v9) + 1;
      while ( v15 < *(_DWORD *)a4 );
      goto LABEL_17;
    }
  }
  if ( lpData )
    free(lpData);
LABEL_20:
  v16 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v19);
  return v16;
}

```

## disassembly

```asm
0x180045018  mov     [rsp-8+arg_10], rbx
0x18004501d  push    rbp
0x18004501e  push    rsi
0x18004501f  push    rdi
0x180045020  push    r12
0x180045022  push    r13
0x180045024  push    r14
0x180045026  push    r15
0x180045028  lea     rbp, [rsp-790h]
0x180045030  sub     rsp, 890h
0x180045037  mov     rax, cs:__security_cookie
0x18004503e  xor     rax, rsp
0x180045041  mov     [rbp+7C0h+var_40], rax
0x180045048  mov     r15, r9
0x18004504b  mov     r14b, r8b
0x18004504e  mov     r12, rdx
0x180045051  mov     r13, rcx
0x180045054  mov     [rsp+8C0h+var_890], 0
0x18004505c  xor     edi, edi
0x18004505e  xor     ebx, ebx
0x180045060  xor     eax, eax
0x180045062  mov     [rbp+7C0h+var_840], eax
0x180045065  xor     edx, edx; Val
0x180045067  mov     r8d, 7FCh; Size
0x18004506d  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180045071  call    memset_0
0x180045076  xorps   xmm0, xmm0
0x180045079  movdqu  [rsp+8C0h+var_880], xmm0
0x18004507f  mov     [rsp+8C0h+var_888], rbx
0x180045084  xorps   xmm1, xmm1
0x180045087  movdqu  [rsp+8C0h+var_870], xmm1
0x18004508d  mov     [rsp+8C0h+var_860], rbx
0x180045092  mov     [rsp+8C0h+var_858], 0FFFFFFFFh
0x18004509a  mov     [rsp+8C0h+var_854], ebx
0x18004509e  cmp     qword ptr cs:xmmword_180071090+8, rbx
0x1800450a5  jz      short loc_1800450BD
0x1800450a7  lea     r8, [rsp+8C0h+var_890]; unsigned int *
0x1800450ac  lea     rdx, aWriteaddressto; "WriteAddressToRegistry"
0x1800450b3  lea     rcx, [rsp+8C0h+var_888]; this
0x1800450b8  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x1800450bd  mov     esi, [r15]
0x1800450c0  test    r14b, r14b
0x1800450c3  jz      loc_18004516A
0x1800450c9  test    esi, esi
0x1800450cb  jz      short loc_180045140
0x1800450cd  imul    rcx, rsi, 64h ; 'd'; Size
0x1800450d1  call    cs:__imp_malloc
0x1800450d7  mov     rdi, rax
0x1800450da  test    rax, rax
0x1800450dd  jnz     short loc_18004513D
0x1800450df  mov     ecx, 8
0x1800450e4  mov     [rsp+8C0h+var_890], ecx
0x1800450e8  cmp     qword ptr cs:xmmword_180071090, 0
0x1800450f0  jz      loc_1800451E7
0x1800450f6  xor     eax, eax
0x1800450f8  mov     word ptr [rbp+7C0h+var_840], ax
0x1800450fc  mov     dword ptr [rsp+8C0h+lpData], ecx
0x180045100  mov     r9, r12
0x180045103  lea     r8, aWriteaddressto; "WriteAddressToRegistry"
0x18004510a  lea     rdx, aSMallocWsFaile; "%s: malloc (%ws) failed: %d."
0x180045111  lea     rcx, [rbp+7C0h+var_840]
0x180045115  call    FormatRRASErrorString
0x18004511a  lea     r8, [rbp+7C0h+var_840]
0x18004511e  mov     rdx, qword ptr cs:xmmword_180071090
0x180045125  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18004512c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180045133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045138  jmp     loc_1800451E7
0x18004513d  mov     rbx, rax
0x180045140  xor     r14d, r14d
0x180045143  test    esi, esi
0x180045145  jz      loc_1800451D9
0x18004514b  mov     rax, [r15+8]
0x18004514f  lea     rcx, [rax+r14*4]; Addr
0x180045153  mov     rdx, rbx; S
0x180045156  call    cs:__imp_RtlIpv4AddressToStringW
0x18004515c  lea     rbx, [rax+2]
0x180045160  inc     r14d
0x180045163  cmp     r14d, [r15]
0x180045166  jb      short loc_18004514B
0x180045168  jmp     short loc_1800451AE
0x18004516a  test    esi, esi
0x18004516c  jz      short loc_180045187
0x18004516e  imul    rcx, rsi, 64h ; 'd'; Size
0x180045172  call    cs:__imp_malloc
0x180045178  mov     rdi, rax
0x18004517b  test    rax, rax
0x18004517e  jz      loc_1800450DF
0x180045184  mov     rbx, rax
0x180045187  xor     r14d, r14d
0x18004518a  test    esi, esi
0x18004518c  jz      short loc_1800451D9
0x18004518e  mov     ecx, r14d
0x180045191  shl     rcx, 4
0x180045195  add     rcx, [r15+8]; Addr
0x180045199  mov     rdx, rbx; S
0x18004519c  call    cs:__imp_RtlIpv6AddressToStringW
0x1800451a2  lea     rbx, [rax+2]
0x1800451a6  inc     r14d
0x1800451a9  cmp     r14d, [r15]
0x1800451ac  jb      short loc_18004518E
0x1800451ae  xor     eax, eax
0x1800451b0  mov     [rbx], ax
0x1800451b3  add     rbx, 2
0x1800451b7  sub     ebx, edi
0x1800451b9  mov     [rsp+8C0h+cbData], ebx; cbData
0x1800451bd  mov     [rsp+8C0h+lpData], rdi; lpData
0x1800451c2  lea     r9d, [rax+7]; dwType
0x1800451c6  xor     r8d, r8d; Reserved
0x1800451c9  mov     rdx, r12; lpValueName
0x1800451cc  mov     rcx, r13; hKey
0x1800451cf  call    cs:__imp_RegSetValueExW
0x1800451d5  mov     [rsp+8C0h+var_890], eax
0x1800451d9  test    rdi, rdi
0x1800451dc  jz      short loc_1800451E7
0x1800451de  mov     rcx, rdi; Block
0x1800451e1  call    cs:__imp_free
0x1800451e7  mov     ebx, [rsp+8C0h+var_890]
0x1800451eb  lea     rcx, [rsp+8C0h+var_888]; this
0x1800451f0  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800451f5  mov     eax, ebx
0x1800451f7  mov     rcx, [rbp+7C0h+var_40]
0x1800451fe  xor     rcx, rsp; StackCookie
0x180045201  call    __security_check_cookie
0x180045206  mov     rbx, [rsp+8C0h+arg_10]
0x18004520e  add     rsp, 890h
0x180045215  pop     r15
0x180045217  pop     r14
0x180045219  pop     r13
0x18004521b  pop     r12
0x18004521d  pop     rdi
0x18004521e  pop     rsi
0x18004521f  pop     rbp
0x180045220  retn
```
