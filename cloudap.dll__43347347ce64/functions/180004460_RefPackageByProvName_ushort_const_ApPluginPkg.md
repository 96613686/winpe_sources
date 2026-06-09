# RefPackageByProvName(ushort const *,_ApPluginPkg * *)

- ea: `0x180004460`
- end: `0x18000462c`
- name: `?RefPackageByProvName@@YAJPEBGPEAPEAU_ApPluginPkg@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _ApPluginPkg **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180017780`
- `0x180020b10`

## callees

- `0x180004460`
- `0x1800046f4`
- `0x18004cf50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800044d2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800044d2`
- `ntdll!RtlReleaseResource` at `0x1800044f5`
- `ntdll!RtlReleaseResource` at `0x18000452a`
- `ntdll!RtlReleaseResource` at `0x180004609`
- `ntdll!RtlReleaseResource` at `0x1800044f5`
- `ntdll!RtlReleaseResource` at `0x18000452a`
- `ntdll!RtlReleaseResource` at `0x180004609`
- `ntdll!RtlInitUnicodeString` at `0x180004555`
- `ntdll!RtlInitUnicodeString` at `0x180004563`
- `ntdll!RtlInitUnicodeString` at `0x180004555`
- `ntdll!RtlInitUnicodeString` at `0x180004563`
- `ntdll!RtlAcquireResourceShared` at `0x180004483`
- `ntdll!RtlAcquireResourceShared` at `0x180004517`
- `ntdll!RtlAcquireResourceShared` at `0x180004483`
- `ntdll!RtlAcquireResourceShared` at `0x180004517`
- `ntdll!RtlCompareUnicodeString` at `0x180004576`
- `ntdll!RtlCompareUnicodeString` at `0x180004576`

## pseudocode

```c
__int64 __fastcall RefPackageByProvName(WCHAR *a1, struct _ApPluginPkg **a2)
{
  struct _ApPluginPkg *v4; // rdi
  unsigned int v5; // r14d
  __int64 v6; // rsi
  char *v7; // rbx
  LONG v8; // eax
  bool v9; // zf
  struct _RTL_BALANCED_NODE *v11; // rbx
  LONG v12; // eax
  struct _RTL_BALANCED_NODE *v13; // rbx
  int v14; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF

  *a2 = 0;
  RtlAcquireResourceShared(&g_PackageListLock, 1u);
  v4 = g_pPlugins;
  if ( !g_pPlugins )
  {
LABEL_10:
    RtlReleaseResource(&g_PackageListLock);
    return 2148074257LL;
  }
  v5 = 0;
  while ( 2 )
  {
    if ( v5 >= g_cPlugins )
      goto LABEL_10;
    v6 = 392LL * v5;
    DestinationString = 0;
    String2 = 0;
    v7 = (char *)v4 + v6 + 24;
    if ( (g_ulTestFlags & 2) != 0 )
    {
      v8 = _o__wcsicmp(a1, (char *)v4 + v6 + 24);
LABEL_6:
      v4 = g_pPlugins;
      v9 = v8 == 0;
      goto LABEL_7;
    }
    if ( !a1 )
    {
      v9 = v7 == 0;
LABEL_7:
      if ( v9 )
      {
        *a2 = (struct _ApPluginPkg *)((char *)v4 + v6);
        return 0;
      }
      goto LABEL_11;
    }
    if ( v7 )
    {
      RtlInitUnicodeString(&DestinationString, a1);
      RtlInitUnicodeString(&String2, (PCWSTR)((char *)v4 + v6 + 24));
      v8 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
      goto LABEL_6;
    }
LABEL_11:
    RtlAcquireResourceShared(*(PRTL_RESOURCE *)((char *)v4 + v6 + 360), 1u);
    if ( !a1 )
      goto LABEL_12;
    v11 = *(struct _RTL_BALANCED_NODE **)((char *)v4 + v6 + 376);
    if ( !v11 )
      goto LABEL_21;
    while ( 1 )
    {
      v12 = SubPkgTable_CompareNames(a1, v11);
      if ( v12 >= 0 )
        break;
      v11 = v11->Children[0];
LABEL_19:
      if ( !v11 )
        goto LABEL_20;
    }
    if ( v12 > 0 )
    {
      v11 = v11->Children[1];
      goto LABEL_19;
    }
LABEL_20:
    if ( v11 )
    {
LABEL_27:
      if ( (struct _ApPluginPkg *)((char *)g_pPlugins + v6) )
        RtlReleaseResource(*(PRTL_RESOURCE *)((char *)g_pPlugins + v6 + 360));
      goto LABEL_29;
    }
LABEL_21:
    v13 = *(struct _RTL_BALANCED_NODE **)((char *)v4 + v6 + 384);
    if ( !v13 )
      goto LABEL_12;
    while ( 2 )
    {
      v14 = SubPkgTable_CompareDnsNames(a1, v13);
      if ( v14 < 0 )
      {
        v13 = v13->Children[0];
        goto LABEL_24;
      }
      if ( v14 > 0 )
      {
        v13 = v13->Children[1];
LABEL_24:
        if ( !v13 )
          break;
        continue;
      }
      break;
    }
    if ( !v13 )
    {
LABEL_12:
      RtlReleaseResource(*(PRTL_RESOURCE *)((char *)v4 + v6 + 360));
      v4 = g_pPlugins;
      ++v5;
      continue;
    }
    break;
  }
  if ( v13 != (struct _RTL_BALANCED_NODE *)24 )
    goto LABEL_27;
LABEL_29:
  *a2 = (struct _ApPluginPkg *)((char *)g_pPlugins + v6);
  return 0;
}

```

## disassembly

```asm
0x180004460  push    rbx
0x180004462  push    rbp
0x180004463  push    rsi
0x180004464  push    rdi
0x180004465  push    r14
0x180004467  push    r15
0x180004469  sub     rsp, 48h
0x18000446d  mov     r15, rdx
0x180004470  mov     qword ptr [rdx], 0
0x180004477  mov     rbp, rcx
0x18000447a  mov     dl, 1; Wait
0x18000447c  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x180004483  call    cs:__imp_RtlAcquireResourceShared
0x180004489  mov     rdi, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180004490  test    rdi, rdi
0x180004493  jz      short loc_1800044EE
0x180004495  xor     r14d, r14d
0x180004498  cmp     r14d, cs:?g_cPlugins@@3KA; ulong g_cPlugins
0x18000449f  jnb     short loc_1800044EE
0x1800044a1  mov     eax, r14d
0x1800044a4  xorps   xmm0, xmm0
0x1800044a7  imul    rsi, rax, 188h
0x1800044ae  xorps   xmm1, xmm1
0x1800044b1  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800044b6  movups  xmmword ptr [rsp+78h+String2.Length], xmm1
0x1800044bb  mov     eax, cs:?g_ulTestFlags@@3KA; ulong g_ulTestFlags
0x1800044c1  lea     rbx, [rsi+18h]
0x1800044c5  add     rbx, rdi
0x1800044c8  test    al, 2
0x1800044ca  jz      short loc_18000453F
0x1800044cc  mov     rdx, rbx
0x1800044cf  mov     rcx, rbp
0x1800044d2  call    cs:__imp__o__wcsicmp
0x1800044d8  mov     rdi, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800044df  test    eax, eax
0x1800044e1  jnz     short loc_18000450D
0x1800044e3  lea     rax, [rsi+rdi]
0x1800044e7  mov     [r15], rax
0x1800044ea  xor     eax, eax
0x1800044ec  jmp     short loc_180004500
0x1800044ee  lea     rcx, ?g_PackageListLock@@3U_RTL_RESOURCE@@A; Resource
0x1800044f5  call    cs:__imp_RtlReleaseResource
0x1800044fb  mov     eax, 80090311h
0x180004500  add     rsp, 48h
0x180004504  pop     r15
0x180004506  pop     r14
0x180004508  pop     rdi
0x180004509  pop     rsi
0x18000450a  pop     rbp
0x18000450b  pop     rbx
0x18000450c  retn
0x18000450d  mov     rcx, [rsi+rdi+168h]; Resource
0x180004515  mov     dl, 1; Wait
0x180004517  call    cs:__imp_RtlAcquireResourceShared
0x18000451d  test    rbp, rbp
0x180004520  jnz     short loc_180004581
0x180004522  mov     rcx, [rsi+rdi+168h]; Resource
0x18000452a  call    cs:__imp_RtlReleaseResource
0x180004530  mov     rdi, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x180004537  inc     r14d
0x18000453a  jmp     loc_180004498
0x18000453f  test    rbp, rbp
0x180004542  jz      loc_180004611
0x180004548  test    rbx, rbx
0x18000454b  jz      short loc_18000450D
0x18000454d  mov     rdx, rbp; SourceString
0x180004550  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x180004555  call    cs:__imp_RtlInitUnicodeString
0x18000455b  mov     rdx, rbx; SourceString
0x18000455e  lea     rcx, [rsp+78h+String2]; DestinationString
0x180004563  call    cs:__imp_RtlInitUnicodeString
0x180004569  mov     r8b, 1; CaseInsensitive
0x18000456c  lea     rdx, [rsp+78h+String2]; String2
0x180004571  lea     rcx, [rsp+78h+DestinationString]; String1
0x180004576  call    cs:__imp_RtlCompareUnicodeString
0x18000457c  jmp     loc_1800044D8
0x180004581  mov     rbx, [rsi+rdi+178h]
0x180004589  test    rbx, rbx
0x18000458c  jz      short loc_1800045AA
0x18000458e  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x180004591  mov     rcx, rbp; SourceString
0x180004594  call    ?SubPkgTable_CompareNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareNames(void *,_RTL_BALANCED_NODE *)
0x180004599  test    eax, eax
0x18000459b  jns     short loc_180004619
0x18000459d  mov     rbx, [rbx]
0x1800045a0  test    rbx, rbx
0x1800045a3  jnz     short loc_18000458E
0x1800045a5  test    rbx, rbx
0x1800045a8  jnz     short loc_1800045E4
0x1800045aa  mov     rbx, [rsi+rdi+180h]
0x1800045b2  test    rbx, rbx
0x1800045b5  jz      loc_180004522
0x1800045bb  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x1800045be  mov     rcx, rbp; void *
0x1800045c1  call    ?SubPkgTable_CompareDnsNames@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; SubPkgTable_CompareDnsNames(void *,_RTL_BALANCED_NODE *)
0x1800045c6  test    eax, eax
0x1800045c8  jns     short loc_180004624
0x1800045ca  mov     rbx, [rbx]
0x1800045cd  test    rbx, rbx
0x1800045d0  jnz     short loc_1800045BB
0x1800045d2  test    rbx, rbx
0x1800045d5  jz      loc_180004522
0x1800045db  lea     rax, [rbx-18h]
0x1800045df  test    rax, rax
0x1800045e2  jz      short loc_1800045F0
0x1800045e4  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800045eb  add     rcx, rsi
0x1800045ee  jnz     short loc_180004602
0x1800045f0  mov     rcx, cs:?g_pPlugins@@3PEAU_ApPluginPkg@@EA; _ApPluginPkg * g_pPlugins
0x1800045f7  add     rcx, rsi
0x1800045fa  mov     [r15], rcx
0x1800045fd  jmp     loc_1800044EA
0x180004602  mov     rcx, [rcx+168h]; Resource
0x180004609  call    cs:__imp_RtlReleaseResource
0x18000460f  jmp     short loc_1800045F0
0x180004611  test    rbx, rbx
0x180004614  jmp     loc_1800044E1
0x180004619  jle     short loc_1800045A5
0x18000461b  mov     rbx, [rbx+8]
0x18000461f  jmp     loc_1800045A0
0x180004624  jle     short loc_1800045D2
0x180004626  mov     rbx, [rbx+8]
0x18000462a  jmp     short loc_1800045CD
```
