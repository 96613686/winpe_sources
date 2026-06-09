# InstallDefaultOID(ldap *)

- ea: `0x1800300f8`
- end: `0x18003021c`
- name: `?InstallDefaultOID@@YAJPEAUldap@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(struct ldap *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180030224`

## callees

- `0x180008400`
- `0x180012450`
- `0x18001d6dc`
- `0x18002a668`
- `0x18002bbb8`
- `0x18002c6a4`
- `0x1800300f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800301a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800301f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030207`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030193`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800301a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800301f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030207`

## pseudocode

```c
__int64 __fastcall InstallDefaultOID(struct ldap *a1)
{
  unsigned __int16 *v1; // rdi
  unsigned int i; // ebp
  int v4; // eax
  unsigned int v5; // edx
  unsigned int v6; // ebx
  int v7; // eax
  HINSTANCE v8; // rcx
  unsigned __int16 *ResourceStringNoCache; // rax
  unsigned __int16 *v10; // rsi
  int v11; // eax
  unsigned int v12; // ecx
  HLOCAL hMem; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  hMem = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      v6 = 0;
      goto LABEL_18;
    }
    v4 = CAOIDBuildOID(
           (unsigned int)a1,
           (const unsigned __int16 *)*(&g_rgDefaultOIDInfo + 2 * i),
           (unsigned __int16 **)&hMem,
           a1);
    v6 = v4;
    if ( v4 )
    {
      CSPrintErrorLineFile(0x1B0E0328u, v4);
      v1 = (unsigned __int16 *)hMem;
      goto LABEL_18;
    }
    v1 = (unsigned __int16 *)hMem;
    v7 = I_CAOIDAdd(*((_DWORD *)&g_rgDefaultOIDInfo + 4 * i + 3), v5, (const unsigned __int16 *)hMem, a1);
    if ( v7 != -2146885627 )
      v6 = v7;
    if ( v6 )
      break;
    ResourceStringNoCache = myLoadResourceStringNoCache(v8, *((_DWORD *)&g_rgDefaultOIDInfo + 4 * i + 2));
    v10 = ResourceStringNoCache;
    if ( !ResourceStringNoCache )
    {
      v11 = myHLastError();
      v6 = v11;
      v12 = 455279400;
      goto LABEL_14;
    }
    v11 = I_CAOIDSetProperty(v1, 1u, ResourceStringNoCache, a1);
    v6 = v11;
    if ( v11 )
    {
      v12 = 455803688;
LABEL_14:
      CSPrintErrorLineFile(v12, v11);
      goto LABEL_19;
    }
    if ( v1 )
    {
      LocalFree(v1);
      v1 = 0;
      hMem = 0;
    }
    LocalFree(v10);
  }
  CSPrintErrorLineFile(0x1B1B0328u, v6);
LABEL_18:
  v10 = 0;
LABEL_19:
  if ( v1 )
    LocalFree(v1);
  if ( v10 )
    LocalFree(v10);
  return v6;
}

```

## disassembly

```asm
0x1800300f8  push    rbx
0x1800300fa  push    rbp
0x1800300fb  push    rsi
0x1800300fc  push    rdi
0x1800300fd  push    r14
0x1800300ff  push    r15
0x180030101  sub     rsp, 28h
0x180030105  xor     edi, edi
0x180030107  lea     r15, ?g_rgDefaultOIDInfo@@3PAU_CERT_DEFAULT_OID_INFO@@A; _CERT_DEFAULT_OID_INFO near * g_rgDefaultOIDInfo
0x18003010e  mov     [rsp+58h+hMem], rdi
0x180030113  xor     ebp, ebp
0x180030115  mov     r14, rcx
0x180030118  cmp     ebp, 3
0x18003011b  jnb     loc_1800301ED
0x180030121  mov     esi, ebp
0x180030123  lea     r8, [rsp+58h+hMem]; unsigned __int16 **
0x180030128  add     rsi, rsi
0x18003012b  mov     r9, r14; struct ldap *
0x18003012e  mov     rdx, [r15+rsi*8]; unsigned __int16 *
0x180030132  call    ?CAOIDBuildOID@@YAJKPEBGPEAPEAGPEAUldap@@@Z; CAOIDBuildOID(ulong,ushort const *,ushort * *,ldap *)
0x180030137  mov     ebx, eax
0x180030139  test    eax, eax
0x18003013b  jnz     loc_1800301DA
0x180030141  mov     rdi, [rsp+58h+hMem]
0x180030146  mov     r9, r14; struct ldap *
0x180030149  mov     ecx, [r15+rsi*8+0Ch]; unsigned int
0x18003014e  mov     r8, rdi; unsigned __int16 *
0x180030151  call    ?I_CAOIDAdd@@YAJKKPEBGPEAUldap@@@Z; I_CAOIDAdd(ulong,ulong,ushort const *,ldap *)
0x180030156  cmp     eax, 80092005h
0x18003015b  cmovnz  ebx, eax
0x18003015e  test    ebx, ebx
0x180030160  jnz     short loc_1800301CC
0x180030162  mov     edx, [r15+rsi*8+8]; unsigned int
0x180030167  call    ?myLoadResourceStringNoCache@@YAPEAGPEAUHINSTANCE__@@K@Z; myLoadResourceStringNoCache(HINSTANCE__ *,ulong)
0x18003016c  mov     rsi, rax
0x18003016f  test    rax, rax
0x180030172  jz      short loc_1800301B7
0x180030174  mov     r9, r14; struct ldap *
0x180030177  lea     edx, [rbx+1]; unsigned int
0x18003017a  mov     r8, rax; void *
0x18003017d  mov     rcx, rdi; unsigned __int16 *
0x180030180  call    ?I_CAOIDSetProperty@@YAJPEBGKPEAXPEAUldap@@@Z; I_CAOIDSetProperty(ushort const *,ulong,void *,ldap *)
0x180030185  mov     ebx, eax
0x180030187  test    eax, eax
0x180030189  jnz     short loc_1800301B0
0x18003018b  test    rdi, rdi
0x18003018e  jz      short loc_1800301A0
0x180030190  mov     rcx, rdi; hMem
0x180030193  call    cs:__imp_LocalFree
0x180030199  xor     edi, edi
0x18003019b  mov     [rsp+58h+hMem], rdi
0x1800301a0  mov     rcx, rsi; hMem
0x1800301a3  call    cs:__imp_LocalFree
0x1800301a9  inc     ebp
0x1800301ab  jmp     loc_180030118
0x1800301b0  mov     ecx, 1B2B0328h
0x1800301b5  jmp     short loc_1800301C3
0x1800301b7  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800301bc  mov     ebx, eax
0x1800301be  mov     ecx, 1B230328h; unsigned int
0x1800301c3  mov     edx, eax; int
0x1800301c5  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800301ca  jmp     short loc_1800301F1
0x1800301cc  mov     edx, ebx; int
0x1800301ce  mov     ecx, 1B1B0328h; unsigned int
0x1800301d3  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800301d8  jmp     short loc_1800301EF
0x1800301da  mov     edx, eax; int
0x1800301dc  mov     ecx, 1B0E0328h; unsigned int
0x1800301e1  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800301e6  mov     rdi, [rsp+58h+hMem]
0x1800301eb  jmp     short loc_1800301EF
0x1800301ed  xor     ebx, ebx
0x1800301ef  xor     esi, esi
0x1800301f1  test    rdi, rdi
0x1800301f4  jz      short loc_1800301FF
0x1800301f6  mov     rcx, rdi; hMem
0x1800301f9  call    cs:__imp_LocalFree
0x1800301ff  test    rsi, rsi
0x180030202  jz      short loc_18003020D
0x180030204  mov     rcx, rsi; hMem
0x180030207  call    cs:__imp_LocalFree
0x18003020d  mov     eax, ebx
0x18003020f  add     rsp, 28h
0x180030213  pop     r15
0x180030215  pop     r14
0x180030217  pop     rdi
0x180030218  pop     rsi
0x180030219  pop     rbp
0x18003021a  pop     rbx
0x18003021b  retn
```
